# RtlpProcessIFEOKeyFilter

- ea: `0x1800d4d20`
- end: `0x1800d516b`
- name: `RtlpProcessIFEOKeyFilter`
- size: `1099`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d4a58`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x180029480`
- `0x18007b660`
- `0x1800d4d20`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`
- `0x18015f120`
- `0x180162810`

## string_xrefs

- `0x1800d4f4a`: `FilterFullPath`

## pseudocode

```c
__int64 __fastcall RtlpProcessIFEOKeyFilter(HANDLE *a1, unsigned int a2, __int128 *a3)
{
  unsigned int v3; // r15d
  size_t v6; // rax
  HANDLE v7; // rcx
  __int64 result; // rax
  __int128 v9; // xmm0
  size_t v10; // rax
  __int64 v11; // r8
  __int64 v12; // rdi
  char v13; // al
  unsigned __int16 v14; // r13
  __int64 v15; // rax
  _BYTE *v16; // rcx
  int v17; // ebx
  size_t v18; // rax
  int v19; // ecx
  __int64 Heap_0; // rax
  int v21; // eax
  void *ProcessHeap; // rcx
  int v23; // eax
  int v24; // [rsp+20h] [rbp-E0h]
  unsigned int v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+34h] [rbp-CCh]
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v28; // [rsp+40h] [rbp-C0h]
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v31; // [rsp+60h] [rbp-A0h]
  unsigned int v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+70h] [rbp-90h]
  _BYTE v34[48]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v35[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v36; // [rsp+B4h] [rbp-4Ch]
  int v37; // [rsp+B8h] [rbp-48h]
  int v38; // [rsp+BCh] [rbp-44h]

  v32 = a2;
  v3 = 0;
  v25 = 0;
  v28 = L"UseFilter";
  Handle = 0;
  memset(v34, 0, 44);
  v27 = 0;
  v6 = wcslen(L"UseFilter");
  if ( v6 > 0x7FFE )
    return 3221225734LL;
  v7 = *a1;
  LOWORD(v27) = 2 * v6;
  WORD1(v27) = 2 * v6 + 2;
  v26 = 544;
  result = NtQueryValueKey(v7, &v27, 2, v35, 544, &v25);
  if ( (int)result < 0 )
  {
    if ( (_DWORD)result == -1073741772 || (_DWORD)result == -1073741789 || (_DWORD)result == -2147483643 )
      return 0;
    return result;
  }
  if ( v36 != 4 || v37 != 4 || !v38 )
    return 0;
  v9 = *a3;
  v27 = 0;
  v28 = L"\\??\\";
  v30 = v9;
  v10 = wcslen(L"\\??\\");
  if ( v10 > 0x7FFE )
    return 3221225734LL;
  LOWORD(v27) = 2 * v10;
  v31 = v35;
  LOBYTE(v11) = 1;
  WORD1(v27) = 2 * v10 + 2;
  v12 = 0;
  v13 = RtlPrefixUnicodeString(&v27, &v30, v11);
  v14 = v30;
  if ( v13 )
  {
    v14 = v30 - 8;
    v15 = *((_QWORD *)&v30 + 1) + 8LL;
  }
  else
  {
    v15 = *((_QWORD *)&v30 + 1);
  }
  v16 = v35;
  v33 = v15;
  *(_QWORD *)&v30 = v35;
  while ( 1 )
  {
    v17 = ((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD, _BYTE *, int, unsigned int *))NtEnumerateKey)(
            *a1,
            v3,
            0,
            v16,
            v26,
            &v25);
    if ( v17 >= 0 )
    {
      LOWORD(v27) = *(_WORD *)(v30 + 12);
      WORD1(v27) = *(_WORD *)(v30 + 12);
      v28 = (const wchar_t *)(v30 + 16);
      *(_QWORD *)&v34[8] = *a1;
      *(_QWORD *)&v34[16] = &v27;
      *(_DWORD *)v34 = 48;
      *(_DWORD *)&v34[24] = 576;
      *(_OWORD *)&v34[32] = 0;
      v17 = NtOpenKey(&Handle, v32, v34);
      if ( v17 >= 0 )
        break;
    }
LABEL_35:
    ++v3;
    if ( v17 < 0 )
      goto LABEL_36;
LABEL_31:
    v16 = (_BYTE *)v30;
  }
  v27 = 0;
  v28 = L"FilterFullPath";
  v18 = wcslen(L"FilterFullPath");
  if ( v18 > 0x7FFE )
  {
    v17 = -1073741562;
    NtClose(Handle);
    goto LABEL_36;
  }
  v19 = v26;
  LOWORD(v27) = 2 * v18;
  WORD1(v27) = 2 * v18 + 2;
  Heap_0 = (__int64)v31;
  while ( 1 )
  {
    v21 = NtQueryValueKey(Handle, &v27, 2, Heap_0, v19, &v25);
    v17 = v21;
    if ( v21 != -2147483643 && v21 != -1073741789 )
    {
      Heap_0 = (__int64)v31;
      v19 = v26;
      goto LABEL_24;
    }
    if ( v12 )
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v12);
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    if ( !ProcessHeap )
      break;
    Heap_0 = RtlAllocateHeap_0(ProcessHeap, (unsigned int)(NtdllBaseTag + 1572864), v25);
    v12 = Heap_0;
    if ( !Heap_0 )
      goto LABEL_47;
    v19 = v25;
    v26 = v25;
    v31 = (_BYTE *)Heap_0;
    *(_QWORD *)&v30 = Heap_0;
LABEL_24:
    if ( v17 != -2147483643 && v17 != -1073741789 )
      goto LABEL_26;
  }
  v12 = 0;
LABEL_47:
  v17 = -1073741801;
LABEL_26:
  if ( v17 < 0 )
  {
    NtClose(Handle);
    v23 = 0;
    if ( v17 != -1073741772 )
      v23 = v17;
    v17 = v23;
    goto LABEL_35;
  }
  if ( *((_DWORD *)v31 + 1) != 1
    || *((_DWORD *)v31 + 2) > 0xFFFEu
    || (LOBYTE(v24) = 1,
        (unsigned int)RtlCompareUnicodeStrings(
                        v33,
                        (unsigned __int64)v14 >> 1,
                        v31 + 12,
                        (unsigned __int64)(unsigned __int16)(*((_WORD *)v31 + 4) - 2) >> 1,
                        v24)) )
  {
    NtClose(Handle);
    ++v3;
    goto LABEL_31;
  }
LABEL_36:
  if ( v12 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v12);
  if ( v17 >= 0 )
  {
    NtClose(*a1);
    *a1 = Handle;
  }
  result = 0;
  if ( v17 != -2147483622 )
    return (unsigned int)v17;
  return result;
}

```

## disassembly

```asm
0x1800d4d20  mov     [rsp-8+arg_18], rbx
0x1800d4d25  push    rbp
0x1800d4d26  push    rdi
0x1800d4d27  push    r12
0x1800d4d29  push    r13
0x1800d4d2b  push    r15
0x1800d4d2d  lea     rbp, [rsp-1E0h]
0x1800d4d35  sub     rsp, 2E0h
0x1800d4d3c  mov     rax, cs:__security_cookie
0x1800d4d43  xor     rax, rsp
0x1800d4d46  mov     [rbp+200h+var_30], rax
0x1800d4d4d  xorps   xmm0, xmm0
0x1800d4d50  mov     [rsp+300h+var_298], edx
0x1800d4d54  xor     r15d, r15d
0x1800d4d57  mov     r12, rcx
0x1800d4d5a  lea     rcx, aUsefilter; "UseFilter"
0x1800d4d61  mov     [rsp+300h+var_2D0], r15d
0x1800d4d66  movups  [rbp+200h+var_278], xmm0
0x1800d4d6a  xor     eax, eax
0x1800d4d6c  mov     [rsp+300h+var_2C0], rcx
0x1800d4d71  movups  [rbp+200h+var_278+0Ch], xmm0
0x1800d4d75  mov     rbx, r8
0x1800d4d78  mov     [rsp+300h+Handle], r15
0x1800d4d7d  movups  [rsp+300h+var_288], xmm0
0x1800d4d82  mov     [rsp+300h+var_2C8], r15
0x1800d4d87  call    wcslen
0x1800d4d8c  cmp     rax, 7FFEh
0x1800d4d92  ja      loc_1800D5143
0x1800d4d98  mov     rcx, [r12]
0x1800d4d9c  lea     edi, [r15+2]
0x1800d4da0  add     ax, ax
0x1800d4da3  lea     r9, [rbp+200h+var_250]
0x1800d4da7  mov     word ptr [rsp+300h+var_2C8], ax
0x1800d4dac  lea     rdx, [rsp+300h+var_2C8]
0x1800d4db1  add     ax, di
0x1800d4db4  mov     r8d, edi
0x1800d4db7  mov     word ptr [rsp+300h+var_2C8+2], ax
0x1800d4dbc  lea     rax, [rsp+300h+var_2D0]
0x1800d4dc1  mov     [rsp+300h+var_2D8], rax
0x1800d4dc6  mov     eax, 220h
0x1800d4dcb  mov     [rsp+300h+var_2CC], eax
0x1800d4dcf  mov     [rsp+300h+var_2E0], eax
0x1800d4dd3  call    NtQueryValueKey
0x1800d4dd8  test    eax, eax
0x1800d4dda  jns     short loc_1800D4E12
0x1800d4ddc  cmp     eax, 0C0000034h
0x1800d4de1  jnz     loc_1800D5107
0x1800d4de7  mov     eax, r15d
0x1800d4dea  mov     rcx, [rbp+200h+var_30]
0x1800d4df1  xor     rcx, rsp; StackCookie
0x1800d4df4  call    __security_check_cookie
0x1800d4df9  mov     rbx, [rsp+300h+arg_18]
0x1800d4e01  add     rsp, 2E0h
0x1800d4e08  pop     r15
0x1800d4e0a  pop     r13
0x1800d4e0c  pop     r12
0x1800d4e0e  pop     rdi
0x1800d4e0f  pop     rbp
0x1800d4e10  retn
0x1800d4e12  cmp     [rbp+200h+var_24C], 4
0x1800d4e16  jnz     loc_1800D512E
0x1800d4e1c  cmp     [rbp+200h+var_248], 4
0x1800d4e20  jnz     loc_1800D512E
0x1800d4e26  cmp     [rbp+200h+var_244], r15d
0x1800d4e2a  jz      loc_1800D512E
0x1800d4e30  movups  xmm0, xmmword ptr [rbx]
0x1800d4e33  lea     rcx, asc_18017CFE8; "\\??\\"
0x1800d4e3a  mov     [rsp+300h+var_2C8], r15
0x1800d4e3f  mov     [rsp+300h+var_2C0], rcx
0x1800d4e44  movdqu  [rsp+300h+var_2B0], xmm0
0x1800d4e4a  call    wcslen
0x1800d4e4f  cmp     rax, 7FFEh
0x1800d4e55  ja      loc_1800D5143
0x1800d4e5b  add     ax, ax
0x1800d4e5e  lea     rcx, [rbp+200h+var_250]
0x1800d4e62  mov     word ptr [rsp+300h+var_2C8], ax
0x1800d4e67  lea     rdx, [rsp+300h+var_2B0]
0x1800d4e6c  add     ax, di
0x1800d4e6f  mov     [rsp+300h+var_2A0], rcx
0x1800d4e74  mov     r8b, 1
0x1800d4e77  mov     word ptr [rsp+300h+var_2C8+2], ax
0x1800d4e7c  lea     rcx, [rsp+300h+var_2C8]
0x1800d4e81  mov     rdi, r15
0x1800d4e84  call    RtlPrefixUnicodeString
0x1800d4e89  movzx   r13d, word ptr [rsp+300h+var_2B0]
0x1800d4e8f  test    al, al
0x1800d4e91  jz      loc_1800D5161
0x1800d4e97  mov     eax, 0FFF8h
0x1800d4e9c  add     r13w, ax
0x1800d4ea0  mov     rax, qword ptr [rsp+300h+var_2B0+8]
0x1800d4ea5  add     rax, 8
0x1800d4ea9  lea     rcx, [rbp+200h+var_250]
0x1800d4ead  mov     [rsp+300h+var_290], rax
0x1800d4eb2  mov     qword ptr [rsp+300h+var_2B0], rcx
0x1800d4eb7  lea     rax, [rsp+300h+var_2D0]
0x1800d4ebc  mov     r9, rcx
0x1800d4ebf  mov     rcx, [r12]
0x1800d4ec3  xor     r8d, r8d
0x1800d4ec6  mov     [rsp+300h+var_2D8], rax
0x1800d4ecb  mov     edx, r15d
0x1800d4ece  mov     eax, [rsp+300h+var_2CC]
0x1800d4ed2  mov     [rsp+300h+var_2E0], eax
0x1800d4ed6  call    NtEnumerateKey
0x1800d4edb  mov     ebx, eax
0x1800d4edd  test    eax, eax
0x1800d4edf  js      loc_1800D50BE
0x1800d4ee5  mov     rcx, qword ptr [rsp+300h+var_2B0]
0x1800d4eea  lea     r8, [rsp+300h+var_288]
0x1800d4eef  mov     edx, [rsp+300h+var_298]
0x1800d4ef3  xorps   xmm0, xmm0
0x1800d4ef6  movzx   eax, word ptr [rcx+0Ch]
0x1800d4efa  mov     word ptr [rsp+300h+var_2C8], ax
0x1800d4eff  movzx   eax, word ptr [rcx+0Ch]
0x1800d4f03  mov     word ptr [rsp+300h+var_2C8+2], ax
0x1800d4f08  lea     rax, [rcx+10h]
0x1800d4f0c  mov     [rsp+300h+var_2C0], rax
0x1800d4f11  lea     rcx, [rsp+300h+Handle]
0x1800d4f16  mov     rax, [r12]
0x1800d4f1a  mov     qword ptr [rbp+200h+var_288+8], rax
0x1800d4f1e  lea     rax, [rsp+300h+var_2C8]
0x1800d4f23  mov     qword ptr [rbp+200h+var_278], rax
0x1800d4f27  mov     dword ptr [rsp+300h+var_288], 30h ; '0'
0x1800d4f2f  mov     dword ptr [rbp+200h+var_278+8], 240h
0x1800d4f36  movdqu  [rbp+200h+var_268], xmm0
0x1800d4f3b  call    NtOpenKey
0x1800d4f40  mov     ebx, eax
0x1800d4f42  test    eax, eax
0x1800d4f44  js      loc_1800D50BE
0x1800d4f4a  lea     rax, aFilterfullpath; "FilterFullPath"
0x1800d4f51  mov     [rsp+300h+var_2C8], 0
0x1800d4f5a  mov     rcx, rax; String
0x1800d4f5d  mov     [rsp+300h+var_2C0], rax
0x1800d4f62  call    wcslen
0x1800d4f67  cmp     rax, 7FFEh
0x1800d4f6d  ja      loc_1800D514D
0x1800d4f73  mov     ecx, [rsp+300h+var_2CC]
0x1800d4f77  add     ax, ax
0x1800d4f7a  mov     word ptr [rsp+300h+var_2C8], ax
0x1800d4f7f  mov     r8d, 2
0x1800d4f85  add     ax, r8w
0x1800d4f89  mov     word ptr [rsp+300h+var_2C8+2], ax
0x1800d4f8e  mov     rax, [rsp+300h+var_2A0]
0x1800d4f93  lea     rdx, [rsp+300h+var_2D0]
0x1800d4f98  mov     r9, rax
0x1800d4f9b  mov     [rsp+300h+var_2D8], rdx
0x1800d4fa0  lea     rdx, [rsp+300h+var_2C8]
0x1800d4fa5  mov     [rsp+300h+var_2E0], ecx
0x1800d4fa9  mov     rcx, [rsp+300h+Handle]
0x1800d4fae  call    NtQueryValueKey
0x1800d4fb3  mov     ebx, eax
0x1800d4fb5  cmp     eax, 80000005h
0x1800d4fba  jz      short loc_1800D4FC7
0x1800d4fbc  cmp     eax, 0C0000023h
0x1800d4fc1  jnz     loc_1800D5135
0x1800d4fc7  test    rdi, rdi
0x1800d4fca  jz      short loc_1800D4FE3
0x1800d4fcc  mov     rcx, gs:60h
0x1800d4fd5  mov     r8, rdi
0x1800d4fd8  xor     edx, edx
0x1800d4fda  mov     rcx, [rcx+30h]
0x1800d4fde  call    RtlFreeHeap_0
0x1800d4fe3  mov     rax, gs:60h
0x1800d4fec  mov     rcx, [rax+30h]
0x1800d4ff0  test    rcx, rcx
0x1800d4ff3  jz      loc_1800D5122
0x1800d4ff9  mov     edx, cs:NtdllBaseTag
0x1800d4fff  mov     r8d, [rsp+300h+var_2D0]
0x1800d5004  add     edx, 180000h
0x1800d500a  call    RtlAllocateHeap_0
0x1800d500f  mov     rdi, rax
0x1800d5012  test    rax, rax
0x1800d5015  jz      loc_1800D5124
0x1800d501b  mov     ecx, [rsp+300h+var_2D0]
0x1800d501f  mov     [rsp+300h+var_2CC], ecx
0x1800d5023  mov     [rsp+300h+var_2A0], rax
0x1800d5028  mov     qword ptr [rsp+300h+var_2B0], rax
0x1800d502d  mov     r8d, 2
0x1800d5033  cmp     ebx, 80000005h
0x1800d5039  jz      loc_1800D4F93
0x1800d503f  cmp     ebx, 0C0000023h
0x1800d5045  jz      loc_1800D4F93
0x1800d504b  test    ebx, ebx
0x1800d504d  js      short loc_1800D50A7
0x1800d504f  mov     rcx, [rsp+300h+var_2A0]
0x1800d5054  cmp     dword ptr [rcx+4], 1
0x1800d5058  jnz     short loc_1800D5090
0x1800d505a  cmp     dword ptr [rcx+8], 0FFFEh
0x1800d5061  ja      short loc_1800D5090
0x1800d5063  movzx   eax, word ptr [rcx+8]
0x1800d5067  lea     r8, [rcx+0Ch]
0x1800d506b  mov     rcx, [rsp+300h+var_290]
0x1800d5070  sub     ax, 2
0x1800d5074  movzx   r9d, ax
0x1800d5078  movzx   edx, r13w
0x1800d507c  shr     r9, 1
0x1800d507f  shr     rdx, 1
0x1800d5082  mov     byte ptr [rsp+300h+var_2E0], 1
0x1800d5087  call    RtlCompareUnicodeStrings
0x1800d508c  test    eax, eax
0x1800d508e  jz      short loc_1800D50C5
0x1800d5090  mov     rcx, [rsp+300h+Handle]; Handle
0x1800d5095  call    NtClose
0x1800d509a  inc     r15d
0x1800d509d  mov     rcx, qword ptr [rsp+300h+var_2B0]
0x1800d50a2  jmp     loc_1800D4EB7
0x1800d50a7  mov     rcx, [rsp+300h+Handle]; Handle
0x1800d50ac  call    NtClose
0x1800d50b1  xor     eax, eax
0x1800d50b3  cmp     ebx, 0C0000034h
0x1800d50b9  cmovnz  eax, ebx
0x1800d50bc  mov     ebx, eax
0x1800d50be  inc     r15d
0x1800d50c1  test    ebx, ebx
0x1800d50c3  jns     short loc_1800D509D
0x1800d50c5  test    rdi, rdi
0x1800d50c8  jz      short loc_1800D50E1
0x1800d50ca  mov     rcx, gs:60h
0x1800d50d3  mov     r8, rdi
0x1800d50d6  xor     edx, edx
0x1800d50d8  mov     rcx, [rcx+30h]
0x1800d50dc  call    RtlFreeHeap_0
0x1800d50e1  test    ebx, ebx
0x1800d50e3  js      short loc_1800D50F7
0x1800d50e5  mov     rcx, [r12]; Handle
0x1800d50e9  call    NtClose
0x1800d50ee  mov     rax, [rsp+300h+Handle]
0x1800d50f3  mov     [r12], rax
0x1800d50f7  xor     eax, eax
0x1800d50f9  cmp     ebx, 8000001Ah
0x1800d50ff  cmovnz  eax, ebx
0x1800d5102  jmp     loc_1800D4DEA
0x1800d5107  cmp     eax, 0C0000023h
0x1800d510c  jz      loc_1800D4DE7
0x1800d5112  cmp     eax, 80000005h
0x1800d5117  jnz     loc_1800D4DEA
0x1800d511d  jmp     loc_1800D4DE7
0x1800d5122  xor     edi, edi
0x1800d5124  mov     ebx, 0C0000017h
0x1800d5129  jmp     loc_1800D504B
0x1800d512e  xor     eax, eax
0x1800d5130  jmp     loc_1800D4DEA
0x1800d5135  mov     rax, [rsp+300h+var_2A0]
0x1800d513a  mov     ecx, [rsp+300h+var_2CC]
0x1800d513e  jmp     loc_1800D502D
0x1800d5143  mov     eax, 0C0000106h
0x1800d5148  jmp     loc_1800D4DEA
0x1800d514d  mov     rcx, [rsp+300h+Handle]; Handle
0x1800d5152  mov     ebx, 0C0000106h
0x1800d5157  call    NtClose
0x1800d515c  jmp     loc_1800D50C5
0x1800d5161  mov     rax, qword ptr [rsp+300h+var_2B0+8]
0x1800d5166  jmp     loc_1800D4EA9
```

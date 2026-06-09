# RtlpProcessIFEOKeyFilter

- ea: `0x180073ac0`
- end: `0x180073f0b`
- name: `RtlpProcessIFEOKeyFilter`
- size: `1099`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800737f8`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x180029590`
- `0x18005ec80`
- `0x180073ac0`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x18015e910`
- `0x180162000`

## string_xrefs

- `0x180073cea`: `FilterFullPath`

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
0x180073ac0  mov     [rsp-8+arg_18], rbx
0x180073ac5  push    rbp
0x180073ac6  push    rdi
0x180073ac7  push    r12
0x180073ac9  push    r13
0x180073acb  push    r15
0x180073acd  lea     rbp, [rsp-1E0h]
0x180073ad5  sub     rsp, 2E0h
0x180073adc  mov     rax, cs:__security_cookie
0x180073ae3  xor     rax, rsp
0x180073ae6  mov     [rbp+200h+var_30], rax
0x180073aed  xorps   xmm0, xmm0
0x180073af0  mov     [rsp+300h+var_298], edx
0x180073af4  xor     r15d, r15d
0x180073af7  mov     r12, rcx
0x180073afa  lea     rcx, aUsefilter; "UseFilter"
0x180073b01  mov     [rsp+300h+var_2D0], r15d
0x180073b06  movups  [rbp+200h+var_278], xmm0
0x180073b0a  xor     eax, eax
0x180073b0c  mov     [rsp+300h+var_2C0], rcx
0x180073b11  movups  [rbp+200h+var_278+0Ch], xmm0
0x180073b15  mov     rbx, r8
0x180073b18  mov     [rsp+300h+Handle], r15
0x180073b1d  movups  [rsp+300h+var_288], xmm0
0x180073b22  mov     [rsp+300h+var_2C8], r15
0x180073b27  call    wcslen
0x180073b2c  cmp     rax, 7FFEh
0x180073b32  ja      loc_180073EE3
0x180073b38  mov     rcx, [r12]
0x180073b3c  lea     edi, [r15+2]
0x180073b40  add     ax, ax
0x180073b43  lea     r9, [rbp+200h+var_250]
0x180073b47  mov     word ptr [rsp+300h+var_2C8], ax
0x180073b4c  lea     rdx, [rsp+300h+var_2C8]
0x180073b51  add     ax, di
0x180073b54  mov     r8d, edi
0x180073b57  mov     word ptr [rsp+300h+var_2C8+2], ax
0x180073b5c  lea     rax, [rsp+300h+var_2D0]
0x180073b61  mov     [rsp+300h+var_2D8], rax
0x180073b66  mov     eax, 220h
0x180073b6b  mov     [rsp+300h+var_2CC], eax
0x180073b6f  mov     [rsp+300h+var_2E0], eax
0x180073b73  call    NtQueryValueKey
0x180073b78  test    eax, eax
0x180073b7a  jns     short loc_180073BB2
0x180073b7c  cmp     eax, 0C0000034h
0x180073b81  jnz     loc_180073EA7
0x180073b87  mov     eax, r15d
0x180073b8a  mov     rcx, [rbp+200h+var_30]
0x180073b91  xor     rcx, rsp; StackCookie
0x180073b94  call    __security_check_cookie
0x180073b99  mov     rbx, [rsp+300h+arg_18]
0x180073ba1  add     rsp, 2E0h
0x180073ba8  pop     r15
0x180073baa  pop     r13
0x180073bac  pop     r12
0x180073bae  pop     rdi
0x180073baf  pop     rbp
0x180073bb0  retn
0x180073bb2  cmp     [rbp+200h+var_24C], 4
0x180073bb6  jnz     loc_180073ECE
0x180073bbc  cmp     [rbp+200h+var_248], 4
0x180073bc0  jnz     loc_180073ECE
0x180073bc6  cmp     [rbp+200h+var_244], r15d
0x180073bca  jz      loc_180073ECE
0x180073bd0  movups  xmm0, xmmword ptr [rbx]
0x180073bd3  lea     rcx, asc_1801787F0; "\\??\\"
0x180073bda  mov     [rsp+300h+var_2C8], r15
0x180073bdf  mov     [rsp+300h+var_2C0], rcx
0x180073be4  movdqu  [rsp+300h+var_2B0], xmm0
0x180073bea  call    wcslen
0x180073bef  cmp     rax, 7FFEh
0x180073bf5  ja      loc_180073EE3
0x180073bfb  add     ax, ax
0x180073bfe  lea     rcx, [rbp+200h+var_250]
0x180073c02  mov     word ptr [rsp+300h+var_2C8], ax
0x180073c07  lea     rdx, [rsp+300h+var_2B0]
0x180073c0c  add     ax, di
0x180073c0f  mov     [rsp+300h+var_2A0], rcx
0x180073c14  mov     r8b, 1
0x180073c17  mov     word ptr [rsp+300h+var_2C8+2], ax
0x180073c1c  lea     rcx, [rsp+300h+var_2C8]
0x180073c21  mov     rdi, r15
0x180073c24  call    RtlPrefixUnicodeString
0x180073c29  movzx   r13d, word ptr [rsp+300h+var_2B0]
0x180073c2f  test    al, al
0x180073c31  jz      loc_180073F01
0x180073c37  mov     eax, 0FFF8h
0x180073c3c  add     r13w, ax
0x180073c40  mov     rax, qword ptr [rsp+300h+var_2B0+8]
0x180073c45  add     rax, 8
0x180073c49  lea     rcx, [rbp+200h+var_250]
0x180073c4d  mov     [rsp+300h+var_290], rax
0x180073c52  mov     qword ptr [rsp+300h+var_2B0], rcx
0x180073c57  lea     rax, [rsp+300h+var_2D0]
0x180073c5c  mov     r9, rcx
0x180073c5f  mov     rcx, [r12]
0x180073c63  xor     r8d, r8d
0x180073c66  mov     [rsp+300h+var_2D8], rax
0x180073c6b  mov     edx, r15d
0x180073c6e  mov     eax, [rsp+300h+var_2CC]
0x180073c72  mov     [rsp+300h+var_2E0], eax
0x180073c76  call    NtEnumerateKey
0x180073c7b  mov     ebx, eax
0x180073c7d  test    eax, eax
0x180073c7f  js      loc_180073E5E
0x180073c85  mov     rcx, qword ptr [rsp+300h+var_2B0]
0x180073c8a  lea     r8, [rsp+300h+var_288]
0x180073c8f  mov     edx, [rsp+300h+var_298]
0x180073c93  xorps   xmm0, xmm0
0x180073c96  movzx   eax, word ptr [rcx+0Ch]
0x180073c9a  mov     word ptr [rsp+300h+var_2C8], ax
0x180073c9f  movzx   eax, word ptr [rcx+0Ch]
0x180073ca3  mov     word ptr [rsp+300h+var_2C8+2], ax
0x180073ca8  lea     rax, [rcx+10h]
0x180073cac  mov     [rsp+300h+var_2C0], rax
0x180073cb1  lea     rcx, [rsp+300h+Handle]
0x180073cb6  mov     rax, [r12]
0x180073cba  mov     qword ptr [rbp+200h+var_288+8], rax
0x180073cbe  lea     rax, [rsp+300h+var_2C8]
0x180073cc3  mov     qword ptr [rbp+200h+var_278], rax
0x180073cc7  mov     dword ptr [rsp+300h+var_288], 30h ; '0'
0x180073ccf  mov     dword ptr [rbp+200h+var_278+8], 240h
0x180073cd6  movdqu  [rbp+200h+var_268], xmm0
0x180073cdb  call    NtOpenKey
0x180073ce0  mov     ebx, eax
0x180073ce2  test    eax, eax
0x180073ce4  js      loc_180073E5E
0x180073cea  lea     rax, aFilterfullpath; "FilterFullPath"
0x180073cf1  mov     [rsp+300h+var_2C8], 0
0x180073cfa  mov     rcx, rax; String
0x180073cfd  mov     [rsp+300h+var_2C0], rax
0x180073d02  call    wcslen
0x180073d07  cmp     rax, 7FFEh
0x180073d0d  ja      loc_180073EED
0x180073d13  mov     ecx, [rsp+300h+var_2CC]
0x180073d17  add     ax, ax
0x180073d1a  mov     word ptr [rsp+300h+var_2C8], ax
0x180073d1f  mov     r8d, 2
0x180073d25  add     ax, r8w
0x180073d29  mov     word ptr [rsp+300h+var_2C8+2], ax
0x180073d2e  mov     rax, [rsp+300h+var_2A0]
0x180073d33  lea     rdx, [rsp+300h+var_2D0]
0x180073d38  mov     r9, rax
0x180073d3b  mov     [rsp+300h+var_2D8], rdx
0x180073d40  lea     rdx, [rsp+300h+var_2C8]
0x180073d45  mov     [rsp+300h+var_2E0], ecx
0x180073d49  mov     rcx, [rsp+300h+Handle]
0x180073d4e  call    NtQueryValueKey
0x180073d53  mov     ebx, eax
0x180073d55  cmp     eax, 80000005h
0x180073d5a  jz      short loc_180073D67
0x180073d5c  cmp     eax, 0C0000023h
0x180073d61  jnz     loc_180073ED5
0x180073d67  test    rdi, rdi
0x180073d6a  jz      short loc_180073D83
0x180073d6c  mov     rcx, gs:60h
0x180073d75  mov     r8, rdi
0x180073d78  xor     edx, edx
0x180073d7a  mov     rcx, [rcx+30h]
0x180073d7e  call    RtlFreeHeap_0
0x180073d83  mov     rax, gs:60h
0x180073d8c  mov     rcx, [rax+30h]
0x180073d90  test    rcx, rcx
0x180073d93  jz      loc_180073EC2
0x180073d99  mov     edx, cs:NtdllBaseTag
0x180073d9f  mov     r8d, [rsp+300h+var_2D0]
0x180073da4  add     edx, 180000h
0x180073daa  call    RtlAllocateHeap_0
0x180073daf  mov     rdi, rax
0x180073db2  test    rax, rax
0x180073db5  jz      loc_180073EC4
0x180073dbb  mov     ecx, [rsp+300h+var_2D0]
0x180073dbf  mov     [rsp+300h+var_2CC], ecx
0x180073dc3  mov     [rsp+300h+var_2A0], rax
0x180073dc8  mov     qword ptr [rsp+300h+var_2B0], rax
0x180073dcd  mov     r8d, 2
0x180073dd3  cmp     ebx, 80000005h
0x180073dd9  jz      loc_180073D33
0x180073ddf  cmp     ebx, 0C0000023h
0x180073de5  jz      loc_180073D33
0x180073deb  test    ebx, ebx
0x180073ded  js      short loc_180073E47
0x180073def  mov     rcx, [rsp+300h+var_2A0]
0x180073df4  cmp     dword ptr [rcx+4], 1
0x180073df8  jnz     short loc_180073E30
0x180073dfa  cmp     dword ptr [rcx+8], 0FFFEh
0x180073e01  ja      short loc_180073E30
0x180073e03  movzx   eax, word ptr [rcx+8]
0x180073e07  lea     r8, [rcx+0Ch]
0x180073e0b  mov     rcx, [rsp+300h+var_290]
0x180073e10  sub     ax, 2
0x180073e14  movzx   r9d, ax
0x180073e18  movzx   edx, r13w
0x180073e1c  shr     r9, 1
0x180073e1f  shr     rdx, 1
0x180073e22  mov     byte ptr [rsp+300h+var_2E0], 1
0x180073e27  call    RtlCompareUnicodeStrings
0x180073e2c  test    eax, eax
0x180073e2e  jz      short loc_180073E65
0x180073e30  mov     rcx, [rsp+300h+Handle]; Handle
0x180073e35  call    NtClose
0x180073e3a  inc     r15d
0x180073e3d  mov     rcx, qword ptr [rsp+300h+var_2B0]
0x180073e42  jmp     loc_180073C57
0x180073e47  mov     rcx, [rsp+300h+Handle]; Handle
0x180073e4c  call    NtClose
0x180073e51  xor     eax, eax
0x180073e53  cmp     ebx, 0C0000034h
0x180073e59  cmovnz  eax, ebx
0x180073e5c  mov     ebx, eax
0x180073e5e  inc     r15d
0x180073e61  test    ebx, ebx
0x180073e63  jns     short loc_180073E3D
0x180073e65  test    rdi, rdi
0x180073e68  jz      short loc_180073E81
0x180073e6a  mov     rcx, gs:60h
0x180073e73  mov     r8, rdi
0x180073e76  xor     edx, edx
0x180073e78  mov     rcx, [rcx+30h]
0x180073e7c  call    RtlFreeHeap_0
0x180073e81  test    ebx, ebx
0x180073e83  js      short loc_180073E97
0x180073e85  mov     rcx, [r12]; Handle
0x180073e89  call    NtClose
0x180073e8e  mov     rax, [rsp+300h+Handle]
0x180073e93  mov     [r12], rax
0x180073e97  xor     eax, eax
0x180073e99  cmp     ebx, 8000001Ah
0x180073e9f  cmovnz  eax, ebx
0x180073ea2  jmp     loc_180073B8A
0x180073ea7  cmp     eax, 0C0000023h
0x180073eac  jz      loc_180073B87
0x180073eb2  cmp     eax, 80000005h
0x180073eb7  jnz     loc_180073B8A
0x180073ebd  jmp     loc_180073B87
0x180073ec2  xor     edi, edi
0x180073ec4  mov     ebx, 0C0000017h
0x180073ec9  jmp     loc_180073DEB
0x180073ece  xor     eax, eax
0x180073ed0  jmp     loc_180073B8A
0x180073ed5  mov     rax, [rsp+300h+var_2A0]
0x180073eda  mov     ecx, [rsp+300h+var_2CC]
0x180073ede  jmp     loc_180073DCD
0x180073ee3  mov     eax, 0C0000106h
0x180073ee8  jmp     loc_180073B8A
0x180073eed  mov     rcx, [rsp+300h+Handle]; Handle
0x180073ef2  mov     ebx, 0C0000106h
0x180073ef7  call    NtClose
0x180073efc  jmp     loc_180073E65
0x180073f01  mov     rax, qword ptr [rsp+300h+var_2B0+8]
0x180073f06  jmp     loc_180073C49
```

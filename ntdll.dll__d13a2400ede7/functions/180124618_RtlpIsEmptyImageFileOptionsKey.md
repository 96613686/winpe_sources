# RtlpIsEmptyImageFileOptionsKey

- ea: `0x180124618`
- end: `0x18012484c`
- name: `RtlpIsEmptyImageFileOptionsKey`
- size: `564`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180124618`
- `0x18013b95c`

## callees

- `0x180029480`
- `0x18002a5b0`
- `0x180124618`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015ed40`
- `0x18015f120`
- `0x180162810`

## string_xrefs

- `0x1801246e7`: `FilterFullPath`

## pseudocode

```c
bool __fastcall RtlpIsEmptyImageFileOptionsKey(__int64 a1)
{
  int inited; // ebx
  unsigned int v3; // edi
  int v4; // edi
  unsigned int v5; // esi
  char IsEmptyImageFileOptionsKey; // bl
  int v8; // [rsp+20h] [rbp-E0h]
  int v9; // [rsp+20h] [rbp-E0h]
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v14; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v17; // [rsp+A8h] [rbp-58h]
  __int16 v18; // [rsp+ACh] [rbp-54h] BYREF
  char v19; // [rsp+B0h] [rbp-50h] BYREF

  inited = 0;
  v10 = 0;
  Handle = 0;
  v3 = 0;
  v11 = 0;
  v13 = 0;
  v14 = 0;
  memset(v15, 0, 44);
  while ( inited >= 0 )
  {
    inited = ZwEnumerateValueKey(a1, v3, 0, v16, 560, &v10);
    if ( inited >= 0 )
    {
      if ( v3 )
        return 0;
      LOWORD(v11) = v17;
      WORD1(v11) = v17;
      *((_QWORD *)&v11 + 1) = &v18;
      if ( (int)RtlInitUnicodeStringEx(&v13, L"UseFilter") < 0 )
        return 0;
      inited = RtlInitUnicodeStringEx(&v14, L"FilterFullPath");
      if ( inited < 0 )
        return 0;
      LOBYTE(v8) = 1;
      if ( (unsigned int)RtlCompareUnicodeStrings(
                           *((_QWORD *)&v11 + 1),
                           (unsigned __int64)(unsigned __int16)v11 >> 1,
                           *((_QWORD *)&v13 + 1),
                           (unsigned __int64)(unsigned __int16)v13 >> 1,
                           v8) )
      {
        LOBYTE(v9) = 1;
        if ( (unsigned int)RtlCompareUnicodeStrings(
                             *((_QWORD *)&v11 + 1),
                             (unsigned __int64)(unsigned __int16)v11 >> 1,
                             *((_QWORD *)&v14 + 1),
                             (unsigned __int64)(unsigned __int16)v14 >> 1,
                             v9) )
          return 0;
      }
    }
    ++v3;
  }
  if ( inited != -2147483622 )
    return 0;
  v4 = 0;
  v5 = 0;
  while ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _BYTE *, int, int *))NtEnumerateKey)(
           a1,
           v5,
           0,
           v16,
           560,
           &v10);
    if ( v4 >= 0 )
    {
      LOWORD(v11) = v18;
      WORD1(v11) = v18;
      *(_DWORD *)v15 = 48;
      *((_QWORD *)&v11 + 1) = &v19;
      *(_QWORD *)&v15[8] = a1;
      *(_QWORD *)&v15[16] = &v11;
      *(_DWORD *)&v15[24] = 576;
      *(_OWORD *)&v15[32] = 0;
      v4 = NtOpenKey(&Handle, 9, v15);
      if ( v4 >= 0 )
      {
        IsEmptyImageFileOptionsKey = RtlpIsEmptyImageFileOptionsKey(Handle);
        NtClose(Handle);
        if ( !IsEmptyImageFileOptionsKey )
          return 0;
      }
    }
    ++v5;
  }
  return v4 == -2147483622;
}

```

## disassembly

```asm
0x180124618  mov     [rsp-8+arg_8], rbx
0x18012461d  mov     [rsp-8+arg_10], rsi
0x180124622  push    rbp
0x180124623  push    rdi
0x180124624  push    r14
0x180124626  lea     rbp, [rsp-1E0h]
0x18012462e  sub     rsp, 2E0h
0x180124635  mov     rax, cs:__security_cookie
0x18012463c  xor     rax, rsp
0x18012463f  mov     [rbp+1F0h+var_20], rax
0x180124646  xorps   xmm0, xmm0
0x180124649  xor     ebx, ebx
0x18012464b  xorps   xmm1, xmm1
0x18012464e  mov     [rsp+2F0h+var_2C0], ebx
0x180124652  xor     eax, eax
0x180124654  mov     [rsp+2F0h+Handle], rbx
0x180124659  movups  [rbp+1F0h+var_270], xmm0
0x18012465d  mov     r14, rcx
0x180124660  xor     edi, edi
0x180124662  movups  [rbp+1F0h+var_270+0Ch], xmm0
0x180124666  movups  [rsp+2F0h+var_2B8], xmm0
0x18012466b  movups  [rsp+2F0h+var_2A0], xmm1
0x180124670  movups  [rsp+2F0h+var_290], xmm0
0x180124675  movups  [rsp+2F0h+var_280], xmm0
0x18012467a  test    ebx, ebx
0x18012467c  js      loc_18012475F
0x180124682  lea     rax, [rsp+2F0h+var_2C0]
0x180124687  xor     r8d, r8d
0x18012468a  mov     [rsp+2F0h+var_2C8], rax
0x18012468f  lea     r9, [rbp+1F0h+var_250]
0x180124693  mov     edx, edi
0x180124695  mov     [rsp+2F0h+var_2D0], 230h
0x18012469d  mov     rcx, r14
0x1801246a0  call    ZwEnumerateValueKey
0x1801246a5  mov     ebx, eax
0x1801246a7  test    eax, eax
0x1801246a9  js      loc_180124758
0x1801246af  test    edi, edi
0x1801246b1  jnz     loc_180124822
0x1801246b7  movzx   eax, [rbp+1F0h+var_248]
0x1801246bb  lea     rdx, aUsefilter; "UseFilter"
0x1801246c2  mov     word ptr [rsp+2F0h+var_2B8], ax
0x1801246c7  lea     rcx, [rsp+2F0h+var_2A0]
0x1801246cc  mov     word ptr [rsp+2F0h+var_2B8+2], ax
0x1801246d1  lea     rax, [rbp+1F0h+var_244]
0x1801246d5  mov     qword ptr [rsp+2F0h+var_2B8+8], rax
0x1801246da  call    RtlInitUnicodeStringEx
0x1801246df  test    eax, eax
0x1801246e1  js      loc_180124822
0x1801246e7  lea     rdx, aFilterfullpath; "FilterFullPath"
0x1801246ee  lea     rcx, [rsp+2F0h+var_290]
0x1801246f3  call    RtlInitUnicodeStringEx
0x1801246f8  mov     ebx, eax
0x1801246fa  test    eax, eax
0x1801246fc  js      loc_180124822
0x180124702  movzx   edx, word ptr [rsp+2F0h+var_2B8]
0x180124707  movzx   r9d, word ptr [rsp+2F0h+var_2A0]
0x18012470d  mov     r8, qword ptr [rsp+2F0h+var_2A0+8]
0x180124712  mov     rcx, qword ptr [rsp+2F0h+var_2B8+8]
0x180124717  shr     r9, 1
0x18012471a  shr     rdx, 1
0x18012471d  mov     byte ptr [rsp+2F0h+var_2D0], 1
0x180124722  call    RtlCompareUnicodeStrings
0x180124727  test    eax, eax
0x180124729  jz      short loc_180124758
0x18012472b  movzx   edx, word ptr [rsp+2F0h+var_2B8]
0x180124730  movzx   r9d, word ptr [rsp+2F0h+var_290]
0x180124736  mov     r8, qword ptr [rsp+2F0h+var_290+8]
0x18012473b  mov     rcx, qword ptr [rsp+2F0h+var_2B8+8]
0x180124740  shr     r9, 1
0x180124743  shr     rdx, 1
0x180124746  mov     byte ptr [rsp+2F0h+var_2D0], 1
0x18012474b  call    RtlCompareUnicodeStrings
0x180124750  test    eax, eax
0x180124752  jnz     loc_180124822
0x180124758  inc     edi
0x18012475a  jmp     loc_18012467A
0x18012475f  cmp     ebx, 8000001Ah
0x180124765  jnz     loc_180124822
0x18012476b  xor     edi, edi
0x18012476d  xor     esi, esi
0x18012476f  test    edi, edi
0x180124771  js      loc_180124817
0x180124777  lea     rax, [rsp+2F0h+var_2C0]
0x18012477c  xor     r8d, r8d
0x18012477f  mov     [rsp+2F0h+var_2C8], rax
0x180124784  lea     r9, [rbp+1F0h+var_250]
0x180124788  mov     edx, esi
0x18012478a  mov     [rsp+2F0h+var_2D0], 230h
0x180124792  mov     rcx, r14
0x180124795  call    NtEnumerateKey
0x18012479a  mov     edi, eax
0x18012479c  test    eax, eax
0x18012479e  js      short loc_180124810
0x1801247a0  movzx   eax, [rbp+1F0h+var_244]
0x1801247a4  lea     r8, [rsp+2F0h+var_280]
0x1801247a9  mov     word ptr [rsp+2F0h+var_2B8], ax
0x1801247ae  lea     rcx, [rsp+2F0h+Handle]
0x1801247b3  mov     word ptr [rsp+2F0h+var_2B8+2], ax
0x1801247b8  xorps   xmm0, xmm0
0x1801247bb  lea     rax, [rbp+1F0h+var_240]
0x1801247bf  mov     dword ptr [rsp+2F0h+var_280], 30h ; '0'
0x1801247c7  mov     qword ptr [rsp+2F0h+var_2B8+8], rax
0x1801247cc  mov     edx, 9
0x1801247d1  lea     rax, [rsp+2F0h+var_2B8]
0x1801247d6  mov     qword ptr [rsp+2F0h+var_280+8], r14
0x1801247db  mov     qword ptr [rbp+1F0h+var_270], rax
0x1801247df  mov     dword ptr [rbp+1F0h+var_270+8], 240h
0x1801247e6  movdqu  [rbp+1F0h+var_260], xmm0
0x1801247eb  call    NtOpenKey
0x1801247f0  mov     edi, eax
0x1801247f2  test    eax, eax
0x1801247f4  js      short loc_180124810
0x1801247f6  mov     rcx, [rsp+2F0h+Handle]
0x1801247fb  call    RtlpIsEmptyImageFileOptionsKey
0x180124800  mov     rcx, [rsp+2F0h+Handle]; Handle
0x180124805  mov     bl, al
0x180124807  call    NtClose
0x18012480c  test    bl, bl
0x18012480e  jz      short loc_180124822
0x180124810  inc     esi
0x180124812  jmp     loc_18012476F
0x180124817  cmp     edi, 8000001Ah
0x18012481d  setz    al
0x180124820  jmp     short loc_180124824
0x180124822  xor     al, al
0x180124824  mov     rcx, [rbp+1F0h+var_20]
0x18012482b  xor     rcx, rsp; StackCookie
0x18012482e  call    __security_check_cookie
0x180124833  lea     r11, [rsp+2F0h+var_10]
0x18012483b  mov     rbx, [r11+28h]
0x18012483f  mov     rsi, [r11+30h]
0x180124843  mov     rsp, r11
0x180124846  pop     r14
0x180124848  pop     rdi
0x180124849  pop     rbp
0x18012484a  retn
```

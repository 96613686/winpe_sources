# UpdatePrivateTable

- ea: `0x1800087e8`
- end: `0x180008988`
- name: `UpdatePrivateTable`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180007fa4`

## callees

- `0x1800087e8`
- `0x180019b9c`
- `0x18001a060`
- `0x18001a2cc`
- `0x18001a808`
- `0x18001aadc`
- `0x18001ac90`

## pseudocode

```c
__int16 __fastcall UpdatePrivateTable(
        _QWORD *a1,
        unsigned int *a2,
        __int64 a3,
        unsigned __int16 a4,
        __int16 a5,
        __int16 a6,
        int a7)
{
  __int64 v7; // r14
  __int16 result; // ax
  unsigned int TTDirectory; // ebx
  __int16 v13; // cx
  int v14; // ebx
  unsigned int v15; // ecx
  unsigned __int16 i; // bx
  unsigned int v17; // esi
  unsigned int v18; // [rsp+30h] [rbp-48h] BYREF
  _DWORD v19[2]; // [rsp+38h] [rbp-40h] BYREF
  __int16 v20; // [rsp+40h] [rbp-38h]
  __int16 v21; // [rsp+42h] [rbp-36h]
  __int16 v22; // [rsp+44h] [rbp-34h]
  __int16 v23; // [rsp+46h] [rbp-32h]
  __int16 v24; // [rsp+48h] [rbp-30h]
  __int16 v25; // [rsp+4Ah] [rbp-2Eh]
  __int128 v26; // [rsp+50h] [rbp-28h] BYREF

  v7 = a4;
  v25 = 0;
  LOWORD(v18) = 0;
  v26 = 0;
  if ( (unsigned __int16)(a6 - 1) > 1u )
    return 0;
  TTDirectory = GetTTDirectory((__int64)a1, (__int64)"dttf", (__int64)&v26);
  result = ZeroLongWordAlign(a1, *a2, (char *)&v26 + 8);
  if ( !result )
  {
    HIDWORD(v26) = (unsigned __int16)GetGenericSize(&DTTF_HEADER_CONTROL) + 2 * v7;
    if ( TTDirectory )
    {
      result = WriteGeneric((__int64)a1, (__int64)&v26, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, TTDirectory, &v18);
      if ( !result )
      {
        v13 = *(_WORD *)(a3 + 2 * v7 - 2);
        v14 = DWORD2(v26);
        v19[1] = a7;
        v22 = a6;
        v20 = a5;
        v21 = v13;
        v19[0] = 0x10000;
        v23 = 0;
        v24 = v7;
        result = WriteGeneric(
                   (__int64)a1,
                   (__int64)v19,
                   0x12u,
                   (unsigned __int8 *)&DTTF_HEADER_CONTROL,
                   DWORD2(v26),
                   &v18);
        if ( !result )
        {
          v15 = v14 + (unsigned __int16)v18;
          for ( i = 0; ; ++i )
          {
            v18 = v15;
            v17 = v15;
            if ( i >= (unsigned __int16)v7 )
              break;
            result = WriteWord(a1, *(_WORD *)(a3 + 2LL * i), v15);
            if ( result )
              return result;
            v15 = v17 + 2;
          }
          result = ZeroLongWordAlign(a1, v15, &v18);
          if ( !result )
          {
            *a2 = v18;
            return 0;
          }
        }
      }
    }
    else
    {
      return 1000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800087e8  push    rbp
0x1800087ea  push    rbx
0x1800087eb  push    rsi
0x1800087ec  push    rdi
0x1800087ed  push    r12
0x1800087ef  push    r13
0x1800087f1  push    r14
0x1800087f3  push    r15
0x1800087f5  mov     rbp, rsp
0x1800087f8  sub     rsp, 78h
0x1800087fc  mov     rax, cs:__security_cookie
0x180008803  xor     rax, rsp
0x180008806  mov     [rbp+var_18], rax
0x18000880a  movzx   r12d, [rbp+arg_28]
0x18000880f  xor     esi, esi
0x180008811  xorps   xmm0, xmm0
0x180008814  movzx   r14d, r9w
0x180008818  mov     r13, r8
0x18000881b  mov     [rbp+var_2E], si
0x18000881f  mov     r15, rdx
0x180008822  mov     word ptr [rbp+var_48], si
0x180008826  lea     eax, [r12-1]
0x18000882b  mov     rdi, rcx
0x18000882e  movups  [rbp+var_28], xmm0
0x180008832  cmp     ax, 1
0x180008836  jbe     short loc_18000883F
0x180008838  mov     eax, esi
0x18000883a  jmp     loc_18000896B
0x18000883f  lea     r8, [rbp+var_28]
0x180008843  lea     rdx, aDttf; "dttf"
0x18000884a  call    GetTTDirectory
0x18000884f  mov     edx, [r15]
0x180008852  lea     r8, [rbp+var_28+8]
0x180008856  mov     rcx, rdi
0x180008859  mov     ebx, eax
0x18000885b  call    ZeroLongWordAlign
0x180008860  test    ax, ax
0x180008863  jnz     loc_18000896B
0x180008869  lea     rcx, DTTF_HEADER_CONTROL
0x180008870  call    GetGenericSize
0x180008875  movzx   eax, ax
0x180008878  lea     ecx, [rax+r14*2]
0x18000887c  mov     dword ptr [rbp+var_28+0Ch], ecx
0x18000887f  test    ebx, ebx
0x180008881  jnz     short loc_18000888D
0x180008883  mov     eax, 3E8h
0x180008888  jmp     loc_18000896B
0x18000888d  lea     rax, [rbp+var_48]
0x180008891  mov     r8d, 10h
0x180008897  mov     [rsp+78h+var_50], rax
0x18000889c  lea     r9, DIRECTORY_CONTROL
0x1800088a3  lea     rdx, [rbp+var_28]
0x1800088a7  mov     [rsp+78h+var_58], ebx
0x1800088ab  mov     rcx, rdi
0x1800088ae  call    WriteGeneric
0x1800088b3  test    ax, ax
0x1800088b6  jnz     loc_18000896B
0x1800088bc  mov     eax, [rbp+arg_30]
0x1800088bf  lea     r9, DTTF_HEADER_CONTROL
0x1800088c6  movzx   ecx, word ptr [r13+r14*2-2]
0x1800088cc  lea     rdx, [rbp+var_40]
0x1800088d0  mov     ebx, dword ptr [rbp+var_28+8]
0x1800088d3  mov     [rbp+var_3C], eax
0x1800088d6  movzx   eax, [rbp+arg_20]
0x1800088da  mov     [rbp+var_34], r12w
0x1800088df  xor     r12d, r12d
0x1800088e2  mov     [rbp+var_38], ax
0x1800088e6  lea     rax, [rbp+var_48]
0x1800088ea  mov     [rbp+var_36], cx
0x1800088ee  mov     rcx, rdi
0x1800088f1  mov     [rsp+78h+var_50], rax
0x1800088f6  lea     r8d, [r12+12h]
0x1800088fb  mov     [rsp+78h+var_58], ebx
0x1800088ff  mov     [rbp+var_40], 10000h
0x180008906  mov     [rbp+var_32], r12w
0x18000890b  mov     [rbp+var_30], r14w
0x180008910  call    WriteGeneric
0x180008915  test    ax, ax
0x180008918  jnz     short loc_18000896B
0x18000891a  movzx   ecx, word ptr [rbp+var_48]
0x18000891e  add     ecx, ebx
0x180008920  mov     ebx, r12d
0x180008923  mov     [rbp+var_48], ecx
0x180008926  mov     esi, ecx
0x180008928  cmp     bx, r14w
0x18000892c  jnb     short loc_18000894F
0x18000892e  movzx   edx, bx
0x180008931  mov     r8d, ecx
0x180008934  mov     rcx, rdi
0x180008937  movzx   edx, word ptr [r13+rdx*2+0]
0x18000893d  call    WriteWord
0x180008942  test    ax, ax
0x180008945  jnz     short loc_18000896B
0x180008947  lea     ecx, [rsi+2]
0x18000894a  inc     bx
0x18000894d  jmp     short loc_180008923
0x18000894f  mov     edx, ecx
0x180008951  lea     r8, [rbp+var_48]
0x180008955  mov     rcx, rdi
0x180008958  call    ZeroLongWordAlign
0x18000895d  test    ax, ax
0x180008960  jnz     short loc_18000896B
0x180008962  mov     eax, [rbp+var_48]
0x180008965  mov     [r15], eax
0x180008968  mov     eax, r12d
0x18000896b  mov     rcx, [rbp+var_18]
0x18000896f  xor     rcx, rsp; StackCookie
0x180008972  call    __security_check_cookie
0x180008977  add     rsp, 78h
0x18000897b  pop     r15
0x18000897d  pop     r14
0x18000897f  pop     r13
0x180008981  pop     r12
0x180008983  pop     rdi
0x180008984  pop     rsi
0x180008985  pop     rbx
0x180008986  pop     rbp
0x180008987  retn
```

# RouterGetKeyDataBlob

- ea: `0x1800666f8`
- end: `0x180066890`
- name: `RouterGetKeyDataBlob`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006632c`

## callees

- `0x18001155c`
- `0x180025ec0`
- `0x180025fb0`
- `0x1800666f8`
- `0x1800a4260`
- `0x1800a4300`
- `0x1800a45c0`

## string_xrefs

- `0x180066784`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x180066810`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

## pseudocode

```c
__int64 __fastcall RouterGetKeyDataBlob(__int64 a1, void *a2, unsigned int a3)
{
  __int64 v3; // rax
  __int64 v5; // r15
  __int64 (__fastcall *v6)(__int64, _QWORD, const wchar_t *, char *, unsigned int, unsigned int *, _DWORD); // r12
  size_t v7; // rbp
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned int v12; // eax
  _BYTE *v13; // rdi
  char *v14; // rsi
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  unsigned int v22; // [rsp+40h] [rbp-A8h] BYREF
  _DWORD v23[3]; // [rsp+44h] [rbp-A4h] BYREF
  char v24; // [rsp+50h] [rbp-98h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v5 = *(_QWORD *)(a1 + 16);
  v22 = 0;
  v23[0] = 0;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, char *, unsigned int, unsigned int *, _DWORD))(v3 + 120);
  v7 = a3;
  v8 = v6(v5, 0, L"KeyDataBlob", 0, 0, &v22, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 70;
    v11 = (unsigned int)v8;
LABEL_3:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c", v10);
    return v9;
  }
  v12 = v22;
  if ( v22 > 0x4C )
  {
    v15 = BCryptAlloc(v22);
    v13 = (_BYTE *)v15;
    if ( !v15 )
    {
      v9 = -1073741801;
      v10 = 87;
      v11 = 3221225495LL;
      goto LABEL_3;
    }
    v14 = (char *)v15;
    v12 = v22;
  }
  else
  {
    v13 = 0;
    v14 = &v24;
  }
  v16 = v6(v5, 0, L"KeyDataBlob", v14, v12, v23, 0);
  v9 = v16;
  if ( v16 < 0 )
  {
    v17 = 107;
    v18 = (unsigned int)v16;
LABEL_11:
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c", v17);
    goto LABEL_15;
  }
  if ( (_DWORD)v7 != *((_DWORD *)v14 + 2) )
  {
    v9 = -1073741811;
    v17 = 116;
    v18 = 3221225485LL;
    goto LABEL_11;
  }
  memmove(a2, v14 + 12, v7);
  v9 = 0;
LABEL_15:
  if ( v13 )
  {
    v19 = v22;
    v20 = v13;
    if ( v22 )
    {
      do
      {
        *v20++ = 0;
        --v19;
      }
      while ( v19 );
    }
    BCryptFree(v13);
  }
  return v9;
}

```

## disassembly

```asm
0x1800666f8  push    rbx
0x1800666fa  push    rbp
0x1800666fb  push    rsi
0x1800666fc  push    rdi
0x1800666fd  push    r12
0x1800666ff  push    r14
0x180066701  push    r15
0x180066703  sub     rsp, 0B0h
0x18006670a  mov     rax, cs:__security_cookie
0x180066711  xor     rax, rsp
0x180066714  mov     [rsp+0E8h+var_48], rax
0x18006671c  mov     rax, [rcx+8]
0x180066720  mov     r14, rdx
0x180066723  mov     r15, [rcx+10h]
0x180066727  xor     r9d, r9d
0x18006672a  mov     [rsp+0E8h+var_A8], 0
0x180066732  xor     edx, edx
0x180066734  mov     [rsp+0E8h+var_A4], 0
0x18006673c  mov     rcx, r15
0x18006673f  mov     r12, [rax+78h]
0x180066743  lea     rax, [rsp+0E8h+var_A8]
0x180066748  mov     [rsp+0E8h+var_B8], 0
0x180066750  mov     [rsp+0E8h+var_C0], rax
0x180066755  mov     rax, r12
0x180066758  mov     ebp, r8d
0x18006675b  lea     r8, aKeydatablob; "KeyDataBlob"
0x180066762  mov     [rsp+0E8h+var_C8], 0
0x18006676a  call    _guard_dispatch_icall
0x18006676f  mov     ebx, eax
0x180066771  test    eax, eax
0x180066773  jns     short loc_180066795
0x180066775  mov     r9d, 46h ; 'F'
0x18006677b  mov     ecx, eax
0x18006677d  lea     rdx, aStatus; "Status"
0x180066784  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006678b  call    DebugTraceError
0x180066790  jmp     loc_18006686B
0x180066795  mov     eax, [rsp+0E8h+var_A8]
0x180066799  cmp     eax, 4Ch ; 'L'
0x18006679c  ja      short loc_1800667A7
0x18006679e  xor     edi, edi
0x1800667a0  lea     rsi, [rsp+0E8h+var_98]
0x1800667a5  jmp     short loc_1800667CE
0x1800667a7  mov     rcx, rax
0x1800667aa  call    BCryptAlloc
0x1800667af  mov     rdi, rax
0x1800667b2  test    rax, rax
0x1800667b5  jnz     short loc_1800667C7
0x1800667b7  mov     ebx, 0C0000017h
0x1800667bc  lea     r9d, [rax+57h]
0x1800667c0  mov     ecx, 0C0000017h
0x1800667c5  jmp     short loc_18006677D
0x1800667c7  mov     rsi, rax
0x1800667ca  mov     eax, [rsp+0E8h+var_A8]
0x1800667ce  lea     rcx, [rsp+0E8h+var_A4]
0x1800667d3  mov     [rsp+0E8h+var_B8], 0
0x1800667db  mov     [rsp+0E8h+var_C0], rcx
0x1800667e0  lea     r8, aKeydatablob; "KeyDataBlob"
0x1800667e7  mov     [rsp+0E8h+var_C8], eax
0x1800667eb  mov     r9, rsi
0x1800667ee  mov     rax, r12
0x1800667f1  xor     edx, edx
0x1800667f3  mov     rcx, r15
0x1800667f6  call    _guard_dispatch_icall
0x1800667fb  mov     ebx, eax
0x1800667fd  test    eax, eax
0x1800667ff  jns     short loc_18006681E
0x180066801  mov     r9d, 6Bh ; 'k'
0x180066807  mov     ecx, eax
0x180066809  lea     rdx, aStatus; "Status"
0x180066810  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180066817  call    DebugTraceError
0x18006681c  jmp     short loc_180066846
0x18006681e  cmp     ebp, [rsi+8]
0x180066821  jz      short loc_180066835
0x180066823  mov     ebx, 0C000000Dh
0x180066828  mov     r9d, 74h ; 't'
0x18006682e  mov     ecx, 0C000000Dh
0x180066833  jmp     short loc_180066809
0x180066835  mov     r8, rbp; Size
0x180066838  lea     rdx, [rsi+0Ch]; Src
0x18006683c  mov     rcx, r14; void *
0x18006683f  call    memmove
0x180066844  xor     ebx, ebx
0x180066846  test    rdi, rdi
0x180066849  jz      short loc_18006686B
0x18006684b  mov     eax, [rsp+0E8h+var_A8]
0x18006684f  mov     rcx, rdi
0x180066852  test    rax, rax
0x180066855  jz      short loc_180066863
0x180066857  mov     byte ptr [rcx], 0
0x18006685a  inc     rcx
0x18006685d  sub     rax, 1
0x180066861  jnz     short loc_180066857
0x180066863  mov     rcx, rdi; P
0x180066866  call    BCryptFree
0x18006686b  mov     eax, ebx
0x18006686d  mov     rcx, [rsp+0E8h+var_48]
0x180066875  xor     rcx, rsp; StackCookie
0x180066878  call    __security_check_cookie
0x18006687d  add     rsp, 0B0h
0x180066884  pop     r15
0x180066886  pop     r14
0x180066888  pop     r12
0x18006688a  pop     rdi
0x18006688b  pop     rsi
0x18006688c  pop     rbp
0x18006688d  pop     rbx
0x18006688e  retn
```

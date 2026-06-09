# RouterGetKeyDataBlob

- ea: `0x18005ce18`
- end: `0x18005cfb0`
- name: `RouterGetKeyDataBlob`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005ca4c`

## callees

- `0x18000743c`
- `0x180018e40`
- `0x180018f30`
- `0x18005ce18`
- `0x18009f650`
- `0x18009f6d0`
- `0x18009f780`

## string_xrefs

- `0x18005cea4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18005cf30`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

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
0x18005ce18  push    rbx
0x18005ce1a  push    rbp
0x18005ce1b  push    rsi
0x18005ce1c  push    rdi
0x18005ce1d  push    r12
0x18005ce1f  push    r14
0x18005ce21  push    r15
0x18005ce23  sub     rsp, 0B0h
0x18005ce2a  mov     rax, cs:__security_cookie
0x18005ce31  xor     rax, rsp
0x18005ce34  mov     [rsp+0E8h+var_48], rax
0x18005ce3c  mov     rax, [rcx+8]
0x18005ce40  mov     r14, rdx
0x18005ce43  mov     r15, [rcx+10h]
0x18005ce47  xor     r9d, r9d
0x18005ce4a  mov     [rsp+0E8h+var_A8], 0
0x18005ce52  xor     edx, edx
0x18005ce54  mov     [rsp+0E8h+var_A4], 0
0x18005ce5c  mov     rcx, r15
0x18005ce5f  mov     r12, [rax+78h]
0x18005ce63  lea     rax, [rsp+0E8h+var_A8]
0x18005ce68  mov     [rsp+0E8h+var_B8], 0
0x18005ce70  mov     [rsp+0E8h+var_C0], rax
0x18005ce75  mov     rax, r12
0x18005ce78  mov     ebp, r8d
0x18005ce7b  lea     r8, aKeydatablob; "KeyDataBlob"
0x18005ce82  mov     [rsp+0E8h+var_C8], 0
0x18005ce8a  call    _guard_dispatch_icall
0x18005ce8f  mov     ebx, eax
0x18005ce91  test    eax, eax
0x18005ce93  jns     short loc_18005CEB5
0x18005ce95  mov     r9d, 46h ; 'F'
0x18005ce9b  mov     ecx, eax
0x18005ce9d  lea     rdx, aStatus; "Status"
0x18005cea4  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005ceab  call    DebugTraceError
0x18005ceb0  jmp     loc_18005CF8B
0x18005ceb5  mov     eax, [rsp+0E8h+var_A8]
0x18005ceb9  cmp     eax, 4Ch ; 'L'
0x18005cebc  ja      short loc_18005CEC7
0x18005cebe  xor     edi, edi
0x18005cec0  lea     rsi, [rsp+0E8h+var_98]
0x18005cec5  jmp     short loc_18005CEEE
0x18005cec7  mov     rcx, rax
0x18005ceca  call    BCryptAlloc
0x18005cecf  mov     rdi, rax
0x18005ced2  test    rax, rax
0x18005ced5  jnz     short loc_18005CEE7
0x18005ced7  mov     ebx, 0C0000017h
0x18005cedc  lea     r9d, [rax+57h]
0x18005cee0  mov     ecx, 0C0000017h
0x18005cee5  jmp     short loc_18005CE9D
0x18005cee7  mov     rsi, rax
0x18005ceea  mov     eax, [rsp+0E8h+var_A8]
0x18005ceee  lea     rcx, [rsp+0E8h+var_A4]
0x18005cef3  mov     [rsp+0E8h+var_B8], 0
0x18005cefb  mov     [rsp+0E8h+var_C0], rcx
0x18005cf00  lea     r8, aKeydatablob; "KeyDataBlob"
0x18005cf07  mov     [rsp+0E8h+var_C8], eax
0x18005cf0b  mov     r9, rsi
0x18005cf0e  mov     rax, r12
0x18005cf11  xor     edx, edx
0x18005cf13  mov     rcx, r15
0x18005cf16  call    _guard_dispatch_icall
0x18005cf1b  mov     ebx, eax
0x18005cf1d  test    eax, eax
0x18005cf1f  jns     short loc_18005CF3E
0x18005cf21  mov     r9d, 6Bh ; 'k'
0x18005cf27  mov     ecx, eax
0x18005cf29  lea     rdx, aStatus; "Status"
0x18005cf30  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cf37  call    DebugTraceError
0x18005cf3c  jmp     short loc_18005CF66
0x18005cf3e  cmp     ebp, [rsi+8]
0x18005cf41  jz      short loc_18005CF55
0x18005cf43  mov     ebx, 0C000000Dh
0x18005cf48  mov     r9d, 74h ; 't'
0x18005cf4e  mov     ecx, 0C000000Dh
0x18005cf53  jmp     short loc_18005CF29
0x18005cf55  mov     r8, rbp; Size
0x18005cf58  lea     rdx, [rsi+0Ch]; Src
0x18005cf5c  mov     rcx, r14; void *
0x18005cf5f  call    memmove
0x18005cf64  xor     ebx, ebx
0x18005cf66  test    rdi, rdi
0x18005cf69  jz      short loc_18005CF8B
0x18005cf6b  mov     eax, [rsp+0E8h+var_A8]
0x18005cf6f  mov     rcx, rdi
0x18005cf72  test    rax, rax
0x18005cf75  jz      short loc_18005CF83
0x18005cf77  mov     byte ptr [rcx], 0
0x18005cf7a  inc     rcx
0x18005cf7d  sub     rax, 1
0x18005cf81  jnz     short loc_18005CF77
0x18005cf83  mov     rcx, rdi; P
0x18005cf86  call    BCryptFree
0x18005cf8b  mov     eax, ebx
0x18005cf8d  mov     rcx, [rsp+0E8h+var_48]
0x18005cf95  xor     rcx, rsp; StackCookie
0x18005cf98  call    __security_check_cookie
0x18005cf9d  add     rsp, 0B0h
0x18005cfa4  pop     r15
0x18005cfa6  pop     r14
0x18005cfa8  pop     r12
0x18005cfaa  pop     rdi
0x18005cfab  pop     rsi
0x18005cfac  pop     rbp
0x18005cfad  pop     rbx
0x18005cfae  retn
```

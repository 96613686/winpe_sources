# MSCryptEccSetProperty

- ea: `0x18004a668`
- end: `0x18004a7a0`
- name: `MSCryptEccSetProperty`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004a640`
- `0x18007ff40`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x18004a668`
- `0x18004a7a8`
- `0x18004aa90`

## string_xrefs

- `0x18004a6d6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004a72b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a8c14`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetProperty(_DWORD *a1, const wchar_t *a2, __int64 a3, unsigned int a4, int a5, int a6)
{
  int v6; // eax
  int v7; // edx
  unsigned int v8; // edi
  int v9; // r8d
  _QWORD *v10; // rcx
  __int64 v12; // r9
  char v13; // [rsp+30h] [rbp-18h]

  if ( a5 )
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        112);
    return v8;
  }
  if ( !a1 || *a1 < 0xCu )
  {
    v12 = 445;
    goto LABEL_22;
  }
  v6 = a1[1];
  if ( v6 == 1297301836 )
  {
    v8 = MSCryptEccSetAlgProperty((int)a1, a2, a3, a4, a6);
    if ( (v8 & 0x80000000) != 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        v13 = -107;
LABEL_9:
        WPP_SF_sDsd(
          v10[3],
          v7,
          v9,
          (unsigned int)"Status",
          v8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          v13);
        return v8;
      }
      return v8;
    }
    return 0;
  }
  if ( v6 != 1297304409 )
  {
    v12 = 453;
LABEL_22:
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
    v8 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3959);
    return v8;
  }
  v8 = MSCryptEccSetKeyProperty(a1);
  if ( (v8 & 0x80000000) == 0 )
    return 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v7 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v7 & 1) != 0 )
    {
      v13 = -120;
      goto LABEL_9;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18004a668  mov     [rsp+arg_0], rbx
0x18004a66d  push    rdi
0x18004a66e  sub     rsp, 40h
0x18004a672  cmp     [rsp+48h+arg_20], 0
0x18004a677  jnz     loc_18004A704
0x18004a67d  test    rcx, rcx
0x18004a680  jz      loc_18004A795
0x18004a686  cmp     dword ptr [rcx], 0Ch
0x18004a689  jb      loc_18004A795
0x18004a68f  mov     eax, [rcx+4]
0x18004a692  cmp     eax, 4D53414Ch
0x18004a697  jnz     loc_18004A77C
0x18004a69d  mov     eax, [rsp+48h+arg_28]
0x18004a6a1  mov     [rsp+48h+var_28], eax
0x18004a6a5  call    MSCryptEccSetAlgProperty
0x18004a6aa  mov     edi, eax
0x18004a6ac  test    eax, eax
0x18004a6ae  jns     loc_18004A78E
0x18004a6b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a6bb  lea     rax, WPP_GLOBAL_Control
0x18004a6c2  cmp     rcx, rax
0x18004a6c5  jz      short loc_18004A6F6
0x18004a6c7  mov     eax, [rcx+2Ch]
0x18004a6ca  test    al, 1
0x18004a6cc  jz      short loc_18004A6F6
0x18004a6ce  mov     dword ptr [rsp+48h+var_18], 0F95h
0x18004a6d6  lea     rbx, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a6dd  mov     [rsp+48h+var_20], rbx
0x18004a6e2  mov     [rsp+48h+var_28], edi
0x18004a6e6  mov     rcx, [rcx+18h]
0x18004a6ea  lea     r9, aStatus; "Status"
0x18004a6f1  call    WPP_SF_sDsd
0x18004a6f6  mov     rbx, [rsp+48h+arg_0]
0x18004a6fb  mov     eax, edi
0x18004a6fd  add     rsp, 40h
0x18004a701  pop     rdi
0x18004a702  retn
0x18004a704  mov     edi, 0C000000Dh
0x18004a709  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a710  lea     rax, WPP_GLOBAL_Control
0x18004a717  cmp     rcx, rax
0x18004a71a  jz      short loc_18004A6F6
0x18004a71c  mov     eax, [rcx+2Ch]
0x18004a71f  test    al, 1
0x18004a721  jz      short loc_18004A6F6
0x18004a723  mov     dword ptr [rsp+48h+var_18], 0F70h
0x18004a72b  lea     rbx, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a732  mov     [rsp+48h+var_20], rbx
0x18004a737  mov     [rsp+48h+var_28], 0C000000Dh
0x18004a73f  jmp     short loc_18004A6E6
0x18004a741  mov     eax, [rsp+48h+arg_28]
0x18004a745  mov     [rsp+48h+var_28], eax
0x18004a749  call    MSCryptEccSetKeyProperty
0x18004a74e  mov     edi, eax
0x18004a750  test    eax, eax
0x18004a752  jns     short loc_18004A78E
0x18004a754  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a75b  lea     rax, WPP_GLOBAL_Control
0x18004a762  cmp     rcx, rax
0x18004a765  jz      short loc_18004A6F6
0x18004a767  mov     edx, [rcx+2Ch]
0x18004a76a  test    dl, 1
0x18004a76d  jz      short loc_18004A6F6
0x18004a76f  mov     dword ptr [rsp+48h+var_18], 0F88h
0x18004a777  jmp     loc_18004A6D6
0x18004a77c  cmp     eax, 4D534B59h
0x18004a781  jz      short loc_18004A741
0x18004a783  mov     r9d, 1C5h
0x18004a789  jmp     loc_1800A8C14
0x18004a78e  xor     edi, edi
0x18004a790  jmp     loc_18004A6F6
0x18004a795  mov     r9d, 1BDh
0x18004a79b  jmp     loc_1800A8C14
0x1800a8c14  lea     rbx, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a8c1b  mov     r8, rbx
0x1800a8c1e  lea     rdx, aStatus; "Status"
0x1800a8c25  mov     ecx, 0C0000008h
0x1800a8c2a  call    DebugTraceError
0x1800a8c2f  mov     r9d, 0F77h
0x1800a8c35  lea     rdx, aStatus; "Status"
0x1800a8c3c  mov     r8, rbx
0x1800a8c3f  mov     ecx, 0C0000008h
0x1800a8c44  mov     edi, 0C0000008h
0x1800a8c49  call    DebugTraceError
0x1800a8c4e  nop
0x1800a8c4f  jmp     loc_18004A6F6
```

# CPSRevertToSelf(void *)

- ea: `0x180006510`
- end: `0x1800065a9`
- name: `?CPSRevertToSelf@@YAKPEAX@Z`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004920`
- `0x180005880`
- `0x1800060e0`
- `0x180008498`
- `0x180008c3c`
- `0x18000e9c0`
- `0x18000fbb4`
- `0x180010870`
- `0x180014c80`
- `0x180018a20`
- `0x1800193c0`
- `0x180019f40`
- `0x18002b0ec`
- `0x18002e310`

## callees

- `0x180006510`
- `0x180007f10`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x180006564`
- `RPCRT4!RpcRevertToSelfEx` at `0x180006564`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006538`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000657e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000657e`

## string_xrefs

- `0x180006592`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall CPSRevertToSelf(_QWORD *a1)
{
  unsigned int v1; // ebx
  void *v3; // rcx
  DWORD LastError; // eax
  __int64 v5; // r9

  if ( a1 )
  {
    v1 = 87;
    if ( *(_DWORD *)a1 == 624 )
    {
      if ( *((_DWORD *)a1 + 4) || a1[3] )
      {
        if ( RevertToSelf() )
          return 0;
        LastError = GetLastError();
        v1 = LastError;
        v5 = 858;
      }
      else
      {
        v3 = (void *)a1[1];
        if ( !v3 )
          return v1;
        LastError = RpcRevertToSelfEx(v3);
        v1 = LastError;
        if ( !LastError )
          return v1;
        v5 = 872;
      }
      DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", v5);
    }
    return v1;
  }
  return 0;
}

```

## disassembly

```asm
0x180006510  sub     rsp, 28h
0x180006514  test    rcx, rcx
0x180006517  jz      short loc_180006557
0x180006519  cmp     dword ptr [rcx], 270h
0x18000651f  mov     [rsp+28h+var_8], rbx
0x180006524  mov     ebx, 57h ; 'W'
0x180006529  jnz     short loc_18000654A
0x18000652b  cmp     dword ptr [rcx+10h], 0
0x18000652f  jnz     short loc_180006538
0x180006531  cmp     qword ptr [rcx+18h], 0
0x180006536  jz      short loc_18000655B
0x180006538  call    cs:__imp_RevertToSelf
0x18000653f  nop     dword ptr [rax+rax+00h]
0x180006544  test    eax, eax
0x180006546  jz      short loc_18000657E
0x180006548  xor     ebx, ebx
0x18000654a  mov     eax, ebx
0x18000654c  mov     rbx, [rsp+28h+var_8]
0x180006551  add     rsp, 28h
0x180006555  retn
0x180006557  xor     eax, eax
0x180006559  jmp     short loc_180006551
0x18000655b  mov     rcx, [rcx+8]; BindingHandle
0x18000655f  test    rcx, rcx
0x180006562  jz      short loc_18000654A
0x180006564  call    cs:__imp_RpcRevertToSelfEx
0x18000656b  nop     dword ptr [rax+rax+00h]
0x180006570  mov     ebx, eax
0x180006572  test    eax, eax
0x180006574  jz      short loc_18000654A
0x180006576  mov     r9d, 368h
0x18000657c  jmp     short loc_180006592
0x18000657e  call    cs:__imp_GetLastError
0x180006585  nop     dword ptr [rax+rax+00h]
0x18000658a  mov     ebx, eax
0x18000658c  mov     r9d, 35Ah
0x180006592  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180006599  mov     ecx, eax
0x18000659b  lea     rdx, aDwlasterror; "dwLastError"
0x1800065a2  call    DebugTraceError
0x1800065a7  jmp     short loc_18000654A
```

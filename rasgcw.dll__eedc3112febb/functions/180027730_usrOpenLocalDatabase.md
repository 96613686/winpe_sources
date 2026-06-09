# usrOpenLocalDatabase

- ea: `0x180027730`
- end: `0x1800277c7`
- name: `usrOpenLocalDatabase`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002049c`

## callees

- `0x180021438`
- `0x180021470`
- `0x180026710`
- `0x180027730`
- `0x1800277d0`

## import_xrefs

- `MPRAPI!MprAdminUserServerConnect` at `0x18002776f`
- `MPRAPI!MprAdminUserServerConnect` at `0x18002776f`

## string_xrefs

- `0x18002779a`: `usrOpenLocalDb: unable to load user db 0x%08x`

## pseudocode

```c
__int64 __fastcall usrOpenLocalDatabase(_QWORD *a1)
{
  __int64 result; // rax
  __int64 v3; // rax
  _DWORD *v4; // rbx
  unsigned int v5; // esi

  if ( !a1 )
    return 87;
  v3 = RassrvAlloc(48, 1);
  v4 = (_DWORD *)v3;
  if ( !v3 )
    return 8;
  v5 = MprAdminUserServerConnect(0, 1, v3);
  if ( v5 )
  {
    RassrvFree(v4);
  }
  else
  {
    result = usrReloadLocalDatabase((__int64)v4);
    v5 = result;
    if ( !(_DWORD)result )
    {
      *a1 = v4;
      v4[8] = 0;
      return result;
    }
    DbgOutputTrace("usrOpenLocalDb: unable to load user db 0x%08x", result);
    RassrvFree(v4);
    *a1 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180027730  mov     [rsp+arg_0], rbx
0x180027735  mov     [rsp+arg_8], rsi
0x18002773a  push    rdi
0x18002773b  sub     rsp, 20h
0x18002773f  mov     rdi, rcx
0x180027742  test    rcx, rcx
0x180027745  jnz     short loc_18002774C
0x180027747  lea     eax, [rcx+57h]
0x18002774a  jmp     short loc_1800277B7
0x18002774c  mov     esi, 1
0x180027751  mov     edx, esi
0x180027753  lea     ecx, [rsi+2Fh]
0x180027756  call    RassrvAlloc
0x18002775b  mov     rbx, rax
0x18002775e  test    rax, rax
0x180027761  jnz     short loc_180027768
0x180027763  lea     eax, [rsi+7]
0x180027766  jmp     short loc_1800277B7
0x180027768  mov     r8, rbx
0x18002776b  mov     edx, esi
0x18002776d  xor     ecx, ecx
0x18002776f  call    cs:__imp_MprAdminUserServerConnect
0x180027775  mov     esi, eax
0x180027777  mov     rcx, rbx; lpMem
0x18002777a  test    eax, eax
0x18002777c  jz      short loc_180027785
0x18002777e  call    RassrvFree
0x180027783  jmp     short loc_1800277B5
0x180027785  call    usrReloadLocalDatabase
0x18002778a  mov     esi, eax
0x18002778c  test    eax, eax
0x18002778e  jnz     short loc_180027798
0x180027790  mov     [rdi], rbx
0x180027793  mov     [rbx+20h], eax
0x180027796  jmp     short loc_1800277B7
0x180027798  mov     edx, esi
0x18002779a  lea     rcx, aUsropenlocaldb; "usrOpenLocalDb: unable to load user db "...
0x1800277a1  call    DbgOutputTrace
0x1800277a6  mov     rcx, rbx; lpMem
0x1800277a9  call    RassrvFree
0x1800277ae  mov     qword ptr [rdi], 0
0x1800277b5  mov     eax, esi
0x1800277b7  mov     rbx, [rsp+28h+arg_0]
0x1800277bc  mov     rsi, [rsp+28h+arg_8]
0x1800277c1  add     rsp, 20h
0x1800277c5  pop     rdi
0x1800277c6  retn
```

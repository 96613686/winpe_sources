# FtpCloneServerID(_ITEMIDLIST const *)

- ea: `0x18001bd14`
- end: `0x18001bd6f`
- name: `?FtpCloneServerID@@YAPEFAU_ITEMIDLIST@@PEFBU1@@Z`
- size: `91`
- prototype: `struct _ITEMIDLIST *__fastcall(LPCITEMIDLIST pidl)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800110d4`
- `0x180013f20`
- `0x1800142a0`
- `0x18001fea8`
- `0x180020a4c`
- `0x180020c38`

## callees

- `0x18001bd14`
- `0x18001bda4`

## import_xrefs

- `SHELL32!__imp_ILRemoveLastID` at `0x18001bd54`
- `SHELL32!__imp_ILRemoveLastID` at `0x18001bd54`
- `SHELL32!__imp_ILClone` at `0x18001bd36`
- `SHELL32!__imp_ILClone` at `0x18001bd36`

## pseudocode

```c
struct _ITEMIDLIST *__fastcall FtpCloneServerID(LPCITEMIDLIST pidl)
{
  ITEMIDLIST *v2; // rbx
  _WORD *v3; // rax

  v2 = 0;
  if ( (unsigned int)FtpID_IsServerItemID(pidl) )
  {
    v2 = ILClone(pidl);
    if ( v2 )
    {
      while ( 1 )
      {
        v3 = (USHORT *)((char *)&v2->mkid.cb + v2->mkid.cb);
        if ( !v3 || !*v3 )
          break;
        ILRemoveLastID(v2);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001bd14  mov     [rsp+arg_0], rbx
0x18001bd19  mov     [rsp+arg_8], rsi
0x18001bd1e  push    rdi
0x18001bd1f  sub     rsp, 20h
0x18001bd23  xor     esi, esi
0x18001bd25  mov     rdi, rcx
0x18001bd28  mov     ebx, esi
0x18001bd2a  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001bd2f  test    eax, eax
0x18001bd31  jz      short loc_18001BD5C
0x18001bd33  mov     rcx, rdi; pidl
0x18001bd36  call    cs:__imp_ILClone
0x18001bd3c  mov     rbx, rax
0x18001bd3f  test    rax, rax
0x18001bd42  jz      short loc_18001BD5C
0x18001bd44  movzx   eax, word ptr [rbx]
0x18001bd47  add     rax, rbx
0x18001bd4a  jz      short loc_18001BD5C
0x18001bd4c  cmp     [rax], si
0x18001bd4f  jz      short loc_18001BD5C
0x18001bd51  mov     rcx, rbx; pidl
0x18001bd54  call    cs:__imp_ILRemoveLastID
0x18001bd5a  jmp     short loc_18001BD44
0x18001bd5c  mov     rsi, [rsp+28h+arg_8]
0x18001bd61  mov     rax, rbx
0x18001bd64  mov     rbx, [rsp+28h+arg_0]
0x18001bd69  add     rsp, 20h
0x18001bd6d  pop     rdi
0x18001bd6e  retn
```

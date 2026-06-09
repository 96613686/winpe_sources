# CClfsLogFcbPhysical::AcquireForReadAhead(uchar)

- ea: `0x14000e1c0`
- end: `0x14000e24c`
- name: `?AcquireForReadAhead@CClfsLogFcbPhysical@@UEAAEE@Z`
- size: `140`
- prototype: `unsigned __int8(CClfsLogFcbPhysical *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000e1c0`
- `0x140066e00`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000e23c`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000e23c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000e1f2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000e1f2`

## pseudocode

```c
BOOLEAN __fastcall CClfsLogFcbPhysical::AcquireForReadAhead(union _CLS_LSN *this, BOOLEAN a2)
{
  struct _ERESOURCE *v4; // rsi
  BOOLEAN result; // al
  unsigned __int8 v6; // bl
  union _CLS_LSN *v7; // rdi

  if ( (signed __int64)CClfsLogFcbPhysical::LsnToCacheOffset((CClfsLogFcbPhysical *)this, this + 60) > (signed __int64)this[11].ullOffset )
    return 0;
  v4 = (struct _ERESOURCE *)&this[25];
  result = ExAcquireResourceSharedLite((PERESOURCE)&this[25], a2);
  v6 = result;
  v7 = this + 171;
  if ( v7 && CLFS_LSN_INVALID.ullOffset == v7->ullOffset )
  {
    if ( result )
    {
      v6 = 0;
      ExReleaseResourceForThreadLite(v4, (ERESOURCE_THREAD)KeGetCurrentThread());
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14000e1c0  mov     [rsp+arg_0], rbx
0x14000e1c5  mov     [rsp+arg_8], rsi
0x14000e1ca  push    rdi
0x14000e1cb  sub     rsp, 20h
0x14000e1cf  mov     bl, dl
0x14000e1d1  mov     rdi, rcx
0x14000e1d4  lea     rdx, [rcx+1E0h]; union _CLS_LSN *
0x14000e1db  call    ?LsnToCacheOffset@CClfsLogFcbPhysical@@AEAA_KAEBT_CLS_LSN@@@Z; CClfsLogFcbPhysical::LsnToCacheOffset(_CLS_LSN const &)
0x14000e1e0  cmp     rax, [rdi+58h]
0x14000e1e4  jg      short loc_14000E226
0x14000e1e6  lea     rsi, [rdi+0C8h]
0x14000e1ed  mov     dl, bl; Wait
0x14000e1ef  mov     rcx, rsi; Resource
0x14000e1f2  call    cs:__imp_ExAcquireResourceSharedLite
0x14000e1f9  nop     dword ptr [rax+rax+00h]
0x14000e1fe  mov     bl, al
0x14000e200  add     rdi, 558h
0x14000e207  jz      short loc_14000E215
0x14000e209  mov     rdx, qword ptr cs:CLFS_LSN_INVALID
0x14000e210  cmp     rdx, [rdi]
0x14000e213  jz      short loc_14000E22A
0x14000e215  mov     rbx, [rsp+28h+arg_0]
0x14000e21a  mov     rsi, [rsp+28h+arg_8]
0x14000e21f  add     rsp, 20h
0x14000e223  pop     rdi
0x14000e224  retn
0x14000e226  xor     bl, bl
0x14000e228  jmp     short loc_14000E248
0x14000e22a  test    al, al
0x14000e22c  jz      short loc_14000E248
0x14000e22e  mov     rdx, gs:188h; ResourceThreadId
0x14000e237  xor     bl, bl
0x14000e239  mov     rcx, rsi; Resource
0x14000e23c  call    cs:__imp_ExReleaseResourceForThreadLite
0x14000e243  nop     dword ptr [rax+rax+00h]
0x14000e248  mov     al, bl
0x14000e24a  jmp     short loc_14000E215
```

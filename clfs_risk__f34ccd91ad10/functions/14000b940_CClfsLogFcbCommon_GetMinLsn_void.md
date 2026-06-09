# CClfsLogFcbCommon::GetMinLsn(void)

- ea: `0x14000b940`
- end: `0x14000b9d6`
- name: `?GetMinLsn@CClfsLogFcbCommon@@UEAA?AT_CLS_LSN@@XZ`
- size: `150`
- prototype: `union _CLS_LSN(CClfsLogFcbCommon *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140008c40`
- `0x14000b940`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000b997`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000b997`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000b968`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000b968`

## pseudocode

```c
union _CLS_LSN __fastcall CClfsLogFcbCommon::GetMinLsn(CClfsLogFcbCommon *this, CLFS_LSN *a2)
{
  *a2 = CLFS_LSN_INVALID;
  ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 200), 1u);
  *a2 = *(CLFS_LSN *)((char *)this + 488);
  if ( (*((_BYTE *)this + 376) & 0x20) != 0 && ClfsLsnLess((const CLFS_LSN *)this + 62, a2) )
    *a2 = *(CLFS_LSN *)((char *)this + 496);
  ExReleaseResourceForThreadLite((PERESOURCE)((char *)this + 200), (ERESOURCE_THREAD)KeGetCurrentThread());
  return (union _CLS_LSN)a2;
}

```

## disassembly

```asm
0x14000b940  mov     [rsp+arg_0], rbx
0x14000b945  mov     [rsp+arg_8], rsi
0x14000b94a  push    rdi
0x14000b94b  sub     rsp, 20h
0x14000b94f  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14000b956  mov     rdi, rdx
0x14000b959  mov     [rdx], rax
0x14000b95c  mov     rbx, rcx
0x14000b95f  mov     dl, 1; Wait
0x14000b961  add     rcx, 0C8h; Resource
0x14000b968  call    cs:__imp_ExAcquireResourceSharedLite
0x14000b96f  nop     dword ptr [rax+rax+00h]
0x14000b974  mov     rax, [rbx+1E8h]
0x14000b97b  mov     [rdi], rax
0x14000b97e  test    byte ptr [rbx+178h], 20h
0x14000b985  jnz     short loc_14000B9B7
0x14000b987  mov     rdx, gs:188h; ResourceThreadId
0x14000b990  lea     rcx, [rbx+0C8h]; Resource
0x14000b997  call    cs:__imp_ExReleaseResourceForThreadLite
0x14000b99e  nop     dword ptr [rax+rax+00h]
0x14000b9a3  mov     rbx, [rsp+28h+arg_0]
0x14000b9a8  mov     rax, rdi
0x14000b9ab  mov     rsi, [rsp+28h+arg_8]
0x14000b9b0  add     rsp, 20h
0x14000b9b4  pop     rdi
0x14000b9b5  retn
0x14000b9b7  mov     rdx, rdi; plsn2
0x14000b9ba  lea     rcx, [rbx+1F0h]; plsn1
0x14000b9c1  call    ClfsLsnLess
0x14000b9c6  test    al, al
0x14000b9c8  jz      short loc_14000B987
0x14000b9ca  mov     rax, [rbx+1F0h]
0x14000b9d1  mov     [rdi], rax
0x14000b9d4  jmp     short loc_14000B987
```

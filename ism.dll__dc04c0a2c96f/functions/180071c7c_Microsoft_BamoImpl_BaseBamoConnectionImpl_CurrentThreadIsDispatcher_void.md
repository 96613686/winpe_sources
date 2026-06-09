# Microsoft::BamoImpl::BaseBamoConnectionImpl::CurrentThreadIsDispatcher(void)

- ea: `0x180071c7c`
- end: `0x180071cf1`
- name: `?CurrentThreadIsDispatcher@BaseBamoConnectionImpl@BamoImpl@Microsoft@@QEBA_NXZ`
- size: `117`
- prototype: `bool __fastcall(Microsoft::BamoImpl::BaseBamoConnectionImpl *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180071bb8`
- `0x1800e0284`

## callees

- `0x180071c7c`
- `0x18008dcac`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071c8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071ce1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071c8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071ce1`

## pseudocode

```c
char __fastcall Microsoft::BamoImpl::BaseBamoConnectionImpl::CurrentThreadIsDispatcher(
        Microsoft::BamoImpl::BaseBamoConnectionImpl *this)
{
  __int64 v3; // rcx
  int v4; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v7; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 6) )
    return *((_DWORD *)this + 6) == GetCurrentThreadId();
  if ( !*((_DWORD *)this + 47) )
  {
    v3 = *((_QWORD *)this + 7);
    v7 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v3 + 88LL))(v3, &v7);
    if ( v4 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x25E,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
        (const char *)(unsigned int)v4,
        v5);
    return v7 == GetCurrentThreadId();
  }
  return 1;
}

```

## disassembly

```asm
0x180071c7c  push    rbx; int
0x180071c7e  sub     rsp, 20h
0x180071c82  cmp     dword ptr [rcx+18h], 0
0x180071c86  mov     rbx, rcx
0x180071c89  jz      short loc_180071C9D
0x180071c8b  call    cs:__imp_GetCurrentThreadId
0x180071c91  cmp     [rbx+18h], eax
0x180071c94  setz    al
0x180071c97  add     rsp, 20h
0x180071c9b  pop     rbx
0x180071c9c  retn
0x180071c9d  cmp     dword ptr [rcx+0BCh], 0
0x180071ca4  ja      short loc_180071CED
0x180071ca6  mov     rcx, [rcx+38h]
0x180071caa  lea     rdx, [rsp+28h+arg_0]
0x180071caf  mov     [rsp+28h+arg_0], 0
0x180071cb7  mov     rax, [rcx]
0x180071cba  mov     rax, [rax+58h]
0x180071cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071cc3  test    eax, eax
0x180071cc5  jns     short loc_180071CE1
0x180071cc7  mov     rcx, [rsp+28h]; this
0x180071ccc  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x180071cd3  mov     r9d, eax; char *
0x180071cd6  mov     edx, 25Eh; void *
0x180071cdb  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180071ce1  call    cs:__imp_GetCurrentThreadId
0x180071ce7  cmp     [rsp+28h+arg_0], eax
0x180071ceb  jmp     short loc_180071C94
0x180071ced  mov     al, 1
0x180071cef  jmp     short loc_180071C97
```

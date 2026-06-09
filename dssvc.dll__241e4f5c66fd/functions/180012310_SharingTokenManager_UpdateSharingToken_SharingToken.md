# SharingTokenManager::UpdateSharingToken(SharingToken *)

- ea: `0x180012310`
- end: `0x18001235e`
- name: `?UpdateSharingToken@SharingTokenManager@@QEAAJPEAVSharingToken@@@Z`
- size: `78`
- prototype: `__int64 __fastcall(SharingTokenManager *__hidden this, struct SharingToken *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000ceb4`
- `0x180012194`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x180012310`
- `0x180017c90`

## string_xrefs

- `0x180012347`: `SharingTokenManager::UpdateSharingToken`

## pseudocode

```c
__int64 __fastcall SharingTokenManager::UpdateSharingToken(RTL_SRWLOCK *this, struct SharingToken *a2)
{
  int updated; // ebx
  int *v3; // rax
  int v5; // [rsp+20h] [rbp-18h]

  if ( !LODWORD(this->Ptr) )
  {
    updated = -1055719422;
LABEL_4:
    v3 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)this);
    v5 = updated;
    DSLogger::LogError((DSLogger *)v3, L"SharingTokenManager::UpdateSharingToken", 107, L"hr=0x%x.", v5);
    return (unsigned int)updated;
  }
  updated = SharingTokenDatabase::UpdateToken(this + 1, a2);
  if ( updated < 0 )
    goto LABEL_4;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180012310  push    rbx
0x180012312  sub     rsp, 30h
0x180012316  cmp     dword ptr [rcx], 0
0x180012319  jnz     short loc_180012322
0x18001231b  mov     ebx, 0C1130002h
0x180012320  jmp     short loc_180012331
0x180012322  add     rcx, 8; this
0x180012326  call    ?UpdateToken@SharingTokenDatabase@@QEAAJPEAVSharingToken@@@Z; SharingTokenDatabase::UpdateToken(SharingToken *)
0x18001232b  mov     ebx, eax
0x18001232d  test    eax, eax
0x18001232f  jns     short loc_180012356
0x180012331  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012336  lea     r9, aHr0xX; "hr=0x%x."
0x18001233d  mov     [rsp+38h+var_18], ebx
0x180012341  mov     r8d, 6Bh ; 'k'; unsigned int
0x180012347  lea     rdx, aSharingtokenma_0; "SharingTokenManager::UpdateSharingToken"
0x18001234e  mov     rcx, rax; this
0x180012351  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012356  mov     eax, ebx
0x180012358  add     rsp, 30h
0x18001235c  pop     rbx
0x18001235d  retn
```

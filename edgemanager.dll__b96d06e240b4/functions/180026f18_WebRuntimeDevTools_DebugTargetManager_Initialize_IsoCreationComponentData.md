# WebRuntimeDevTools::DebugTargetManager::Initialize(_IsoCreationComponentData *)

- ea: `0x180026f18`
- end: `0x180026fee`
- name: `?Initialize@DebugTargetManager@WebRuntimeDevTools@@QEAAJPEAU_IsoCreationComponentData@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(WebRuntimeDevTools::DebugTargetManager *__hidden this, struct _IsoCreationComponentData *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180026eb0`

## callees

- `0x180026f18`
- `0x180037b5c`
- `0x18006932c`
- `0x18006ea64`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026fc0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026fc0`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x180026f43`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x180026f43`
- `edgeIso!__imp_?IsoReferenceThread@@YAKK@Z` at `0x180026faf`
- `edgeIso!__imp_?IsoReferenceThread@@YAKK@Z` at `0x180026faf`

## pseudocode

```c
__int64 __fastcall WebRuntimeDevTools::DebugTargetManager::Initialize(
        WebRuntimeDevTools::DebugTargetManager *this,
        struct _IsoCreationComponentData *a2)
{
  __int64 v3; // rcx
  unsigned int ArtifactAddress; // ebx
  __int64 v5; // rcx
  HANDLE v6; // rcx
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  _IsoComponent *v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = 0;
  v3 = *((unsigned int *)a2 + 102);
  *((_DWORD *)this + 18) = v3;
  ArtifactAddress = IsoGetArtifactAddress(v3, 1, &v10);
  if ( !ArtifactAddress )
  {
    v5 = *(_QWORD *)this;
    *((_QWORD *)this + 8) = *((_QWORD *)v10 + 7);
    (*(void (__fastcall **)(WebRuntimeDevTools::DebugTargetManager *))(v5 + 8))(this);
    _IsoComponent::SetAppObj(v10, this);
    *((_DWORD *)v10 + 12) = 4;
    *((_WORD *)v10 + 1) = 525;
    _IsoComponent::SetFromSHAREDMEM_64BITVALUE(
      v10,
      *((unsigned int *)v10 + 12),
      WebRuntimeDevTools::DebugTargetManager::LCIEProcessMessage);
    IsoReferenceThread(*((_DWORD *)v10 + 10));
    v6 = WebRuntimeDevTools::DebugTargetManager::s_isoCompCreatedEvent;
    *((_BYTE *)this + 80) = 1;
    if ( !SetEvent(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\debugtargetmanager.cpp",
        v7);
  }
  return ArtifactAddress;
}

```

## disassembly

```asm
0x180026f18  mov     [rsp+arg_8], rbx
0x180026f1d  push    rdi
0x180026f1e  sub     rsp, 20h
0x180026f22  mov     rdi, rcx
0x180026f25  mov     [rsp+28h+arg_0], 0
0x180026f2e  mov     ecx, [rdx+198h]
0x180026f34  lea     r8, [rsp+28h+arg_0]
0x180026f39  xor     r9d, r9d
0x180026f3c  mov     [rdi+48h], ecx
0x180026f3f  lea     edx, [r9+1]
0x180026f43  call    cs:__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,IsoArtifactType,_IsoArtifact * *,ulong *)
0x180026f49  mov     ebx, eax
0x180026f4b  test    eax, eax
0x180026f4d  jnz     loc_180026FE1
0x180026f53  mov     rcx, [rsp+28h+arg_0]
0x180026f58  mov     rdx, [rcx+38h]
0x180026f5c  mov     rcx, [rdi]
0x180026f5f  mov     [rdi+40h], rdx
0x180026f63  mov     rax, [rcx+8]
0x180026f67  mov     rcx, rdi
0x180026f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f6f  mov     rcx, [rsp+28h+arg_0]; this
0x180026f74  mov     rdx, rdi; void *
0x180026f77  call    ?SetAppObj@_IsoComponent@@QEAAXQEAX@Z; _IsoComponent::SetAppObj(void * const)
0x180026f7c  mov     rax, [rsp+28h+arg_0]
0x180026f81  lea     r8, ?LCIEProcessMessage@DebugTargetManager@WebRuntimeDevTools@@SA_JPEAUHWND__@@I_K_J@Z; WebRuntimeDevTools::DebugTargetManager::LCIEProcessMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180026f88  mov     dword ptr [rax+30h], 4
0x180026f8f  mov     rax, [rsp+28h+arg_0]
0x180026f94  mov     word ptr [rax+2], 20Dh
0x180026f9a  mov     rcx, [rsp+28h+arg_0]
0x180026f9f  mov     edx, [rcx+30h]
0x180026fa2  call    ?SetFromSHAREDMEM_64BITVALUE@_IsoComponent@@QEAAXW4_IsoComponentDispatchType@@USHAREDMEM_64BITVALUE@@@Z; _IsoComponent::SetFromSHAREDMEM_64BITVALUE(_IsoComponentDispatchType,SHAREDMEM_64BITVALUE)
0x180026fa7  mov     rcx, [rsp+28h+arg_0]
0x180026fac  mov     ecx, [rcx+28h]
0x180026faf  call    cs:__imp_?IsoReferenceThread@@YAKK@Z; IsoReferenceThread(ulong)
0x180026fb5  mov     rcx, cs:?s_isoCompCreatedEvent@DebugTargetManager@WebRuntimeDevTools@@0PEAXEA; hEvent
0x180026fbc  mov     byte ptr [rdi+50h], 1
0x180026fc0  call    cs:__imp_SetEvent
0x180026fc6  test    eax, eax
0x180026fc8  jnz     short loc_180026FE1
0x180026fca  mov     rcx, [rsp+28h]; this
0x180026fcf  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180026fd6  mov     edx, 161h; void *
0x180026fdb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180026fe1  mov     eax, ebx
0x180026fe3  mov     rbx, [rsp+28h+arg_8]
0x180026fe8  add     rsp, 20h
0x180026fec  pop     rdi
0x180026fed  retn
```

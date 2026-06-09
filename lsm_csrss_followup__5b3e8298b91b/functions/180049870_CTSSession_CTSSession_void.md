# CTSSession::~CTSSession(void)

- ea: `0x180049870`
- end: `0x1800499b9`
- name: `??1CTSSession@@UEAA@XZ`
- size: `329`
- prototype: `void __fastcall(CTSSession *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180065b30`

## callees

- `0x180008f64`
- `0x18000fb08`
- `0x180010f20`
- `0x180021c68`
- `0x180045a44`
- `0x180049870`
- `0x1800499c0`
- `0x1800499f0`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18004990d`
- `ntdll!RtlDeleteResource` at `0x18004998a`
- `ntdll!RtlDeleteResource` at `0x18004990d`
- `ntdll!RtlDeleteResource` at `0x18004998a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800498b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800498b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTSSession::~CTSSession(CTSSession *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CTSSession::`vftable';
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((char *)this + 5936);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((char *)this + 5928);
  CTSSessionSecurityDescriptor::~CTSSessionSecurityDescriptor((CTSSession *)((char *)this + 5872));
  v2 = (void *)*((_QWORD *)this + 404);
  if ( v2 )
    CloseHandle(v2);
  v3 = *((_QWORD *)this + 260);
  if ( v3 )
  {
    std::_Deallocate<16>(v3, (*((_QWORD *)this + 262) - v3) & 0xFFFFFFFFFFFFFFFCuLL);
    *((_QWORD *)this + 260) = 0;
    *((_QWORD *)this + 261) = 0;
    *((_QWORD *)this + 262) = 0;
  }
  if ( *((_DWORD *)this + 488) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1856));
  *((_DWORD *)this + 488) = 0;
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((char *)this + 1848);
  SmartPtr<CSessionList>::~SmartPtr<CSessionList>((char *)this + 1840);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((char *)this + 1832);
  SmartPtr<CEventDispatcher>::~SmartPtr<CEventDispatcher>((char *)this + 1824);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((char *)this + 1816);
  CTSSession::CCommonSessionData::~CCommonSessionData((CTSSession *)((char *)this + 1728));
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((char *)this + 1712);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((char *)this + 1704);
  if ( *((_DWORD *)this + 424) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1600));
  *((_DWORD *)this + 424) = 0;
  *(_QWORD *)this = &CTSPrivateObject<ITSSessionPrivate>::`vftable';
  RemoveTrackingObject((struct _LIST_ENTRY *)((char *)this + 1576));
}

```

## disassembly

```asm
0x180049870  mov     [rsp+arg_0], rbx
0x180049875  push    rdi
0x180049876  sub     rsp, 20h
0x18004987a  mov     rbx, rcx
0x18004987d  lea     rax, ??_7CTSSession@@6B@; const CTSSession::`vftable'
0x180049884  mov     [rcx], rax
0x180049887  add     rcx, 1730h
0x18004988e  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180049893  lea     rcx, [rbx+1728h]
0x18004989a  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18004989f  lea     rcx, [rbx+16F0h]; this
0x1800498a6  call    ??1CTSSessionSecurityDescriptor@@UEAA@XZ; CTSSessionSecurityDescriptor::~CTSSessionSecurityDescriptor(void)
0x1800498ab  mov     rcx, [rbx+0CA0h]; hObject
0x1800498b2  test    rcx, rcx
0x1800498b5  jz      short loc_1800498BD
0x1800498b7  call    cs:__imp_CloseHandle
0x1800498bd  mov     rcx, [rbx+820h]
0x1800498c4  test    rcx, rcx
0x1800498c7  jz      short loc_1800498FD
0x1800498c9  mov     rdx, [rbx+830h]
0x1800498d0  sub     rdx, rcx
0x1800498d3  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1800498d7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800498dc  mov     qword ptr [rbx+820h], 0
0x1800498e7  mov     qword ptr [rbx+828h], 0
0x1800498f2  mov     qword ptr [rbx+830h], 0
0x1800498fd  lea     rdi, [rbx+740h]
0x180049904  cmp     dword ptr [rdi+60h], 0
0x180049908  jz      short loc_180049913
0x18004990a  mov     rcx, rdi; Resource
0x18004990d  call    cs:__imp_RtlDeleteResource
0x180049913  mov     dword ptr [rdi+60h], 0
0x18004991a  lea     rcx, [rbx+738h]
0x180049921  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180049926  lea     rcx, [rbx+730h]
0x18004992d  call    ??1?$SmartPtr@VCSessionList@@@@QEAA@XZ; SmartPtr<CSessionList>::~SmartPtr<CSessionList>(void)
0x180049932  lea     rcx, [rbx+728h]
0x180049939  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18004993e  lea     rcx, [rbx+720h]
0x180049945  call    ??1?$SmartPtr@VCEventDispatcher@@@@QEAA@XZ; SmartPtr<CEventDispatcher>::~SmartPtr<CEventDispatcher>(void)
0x18004994a  lea     rcx, [rbx+718h]
0x180049951  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180049956  lea     rcx, [rbx+6C0h]; this
0x18004995d  call    ??1CCommonSessionData@CTSSession@@UEAA@XZ; CTSSession::CCommonSessionData::~CCommonSessionData(void)
0x180049962  lea     rcx, [rbx+6B0h]
0x180049969  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18004996e  lea     rcx, [rbx+6A8h]
0x180049975  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18004997a  lea     rdi, [rbx+640h]
0x180049981  cmp     dword ptr [rdi+60h], 0
0x180049985  jz      short loc_180049990
0x180049987  mov     rcx, rdi; Resource
0x18004998a  call    cs:__imp_RtlDeleteResource
0x180049990  mov     dword ptr [rdi+60h], 0
0x180049997  lea     rax, ??_7?$CTSPrivateObject@VITSSessionPrivate@@@@6B@; const CTSPrivateObject<ITSSessionPrivate>::`vftable'
0x18004999e  mov     [rbx], rax
0x1800499a1  lea     rcx, [rbx+628h]; struct _LIST_ENTRY *
0x1800499a8  call    ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
0x1800499ad  nop
0x1800499ae  mov     rbx, [rsp+28h+arg_0]
0x1800499b3  add     rsp, 20h
0x1800499b7  pop     rdi
0x1800499b8  retn
```

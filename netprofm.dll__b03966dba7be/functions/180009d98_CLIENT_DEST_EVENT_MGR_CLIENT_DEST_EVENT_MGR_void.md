# CLIENT_DEST_EVENT_MGR::~CLIENT_DEST_EVENT_MGR(void)

- ea: `0x180009d98`
- end: `0x180009e0c`
- name: `??1CLIENT_DEST_EVENT_MGR@@QEAA@XZ`
- size: `116`
- prototype: `void __fastcall(CLIENT_DEST_EVENT_MGR *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180015dc4`

## callees

- `0x180009d98`
- `0x18000c650`
- `0x18000c818`
- `0x180017768`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009dec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009dec`

## pseudocode

```c
void __fastcall CLIENT_DEST_EVENT_MGR::~CLIENT_DEST_EVENT_MGR(CLIENT_DEST_EVENT_MGR *this)
{
  _QWORD **v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 64);
  v2 = (_QWORD **)*((_QWORD *)this + 6);
  *v2[1] = 0;
  v3 = *v2;
  if ( *v2 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      std::_Deallocate<16>(v3, 0x18u);
      v3 = v4;
    }
    while ( v4 );
  }
  std::_Deallocate<16>(*((void **)this + 6), 0x18u);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *(_QWORD *)this )
    wil::details::DestroyThreadPoolWait<0>::Destroy(*(PTP_WAIT *)this);
}

```

## disassembly

```asm
0x180009d98  mov     [rsp+arg_0], rbx
0x180009d9d  push    rdi
0x180009d9e  sub     rsp, 20h
0x180009da2  mov     rdi, rcx
0x180009da5  add     rcx, 40h ; '@'
0x180009da9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009dae  mov     rdx, [rdi+30h]
0x180009db2  mov     rax, [rdx+8]
0x180009db6  mov     qword ptr [rax], 0
0x180009dbd  mov     rcx, [rdx]
0x180009dc0  test    rcx, rcx
0x180009dc3  jz      short loc_180009DDA
0x180009dc5  mov     rbx, [rcx]
0x180009dc8  mov     edx, 18h
0x180009dcd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009dd2  mov     rcx, rbx
0x180009dd5  test    rbx, rbx
0x180009dd8  jnz     short loc_180009DC5
0x180009dda  mov     rcx, [rdi+30h]
0x180009dde  mov     edx, 18h
0x180009de3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009de8  lea     rcx, [rdi+8]; lpCriticalSection
0x180009dec  call    cs:__imp_DeleteCriticalSection
0x180009df2  mov     rcx, [rdi]; pwa
0x180009df5  test    rcx, rcx
0x180009df8  jnz     short loc_180009E05
0x180009dfa  mov     rbx, [rsp+28h+arg_0]
0x180009dff  add     rsp, 20h
0x180009e03  pop     rdi
0x180009e04  retn
0x180009e05  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x180009e0a  jmp     short loc_180009DFA
```

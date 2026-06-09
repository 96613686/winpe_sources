# CDXVAFrameManager::~CDXVAFrameManager(void)

- ea: `0x1800528e0`
- end: `0x180052965`
- name: `??1CDXVAFrameManager@@UEAA@XZ`
- size: `133`
- prototype: `void __fastcall(CDXVAFrameManager *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004b340`
- `0x18004b390`
- `0x180052990`

## callees

- `0x18003af40`
- `0x18005296c`
- `0x1800533c0`
- `0x180053700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052949`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052954`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052949`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052954`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDXVAFrameManager::~CDXVAFrameManager(CDXVAFrameManager *this)
{
  *(_QWORD *)this = &CDXVAFrameManager::`vftable';
  CDXVAFrameManager::Cleanup(this, 2, 0);
  CDXVAFrameManager::Close(this);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___T_Z((char *)this + 112);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___T_Z((char *)this + 104);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___T_Z((char *)this + 120);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 120);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 112);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x1800528e0  push    rbx
0x1800528e2  push    rsi
0x1800528e3  push    rdi
0x1800528e4  push    r14
0x1800528e6  sub     rsp, 28h
0x1800528ea  mov     r14, rcx
0x1800528ed  lea     rax, ??_7CDXVAFrameManager@@6B@; const CDXVAFrameManager::`vftable'
0x1800528f4  mov     [rcx], rax
0x1800528f7  xor     r9d, r9d
0x1800528fa  xor     r8d, r8d
0x1800528fd  lea     edx, [r9+2]
0x180052901  call    ?Cleanup@CDXVAFrameManager@@UEAAJW4FRAMEMGR_CLEANUP_STATE@@PEAI1@Z; CDXVAFrameManager::Cleanup(FRAMEMGR_CLEANUP_STATE,uint *,uint *)
0x180052906  mov     rcx, r14; this
0x180052909  call    ?Close@CDXVAFrameManager@@UEAAJXZ; CDXVAFrameManager::Close(void)
0x18005290e  lea     rcx, [r14+70h]
0x180052912  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$T@Z
0x180052917  lea     rcx, [r14+68h]
0x18005291b  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$T@Z
0x180052920  lea     rcx, [r14+78h]
0x180052924  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$T@Z
0x180052929  lea     rcx, [r14+78h]
0x18005292d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180052932  lea     rcx, [r14+70h]
0x180052936  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005293b  lea     rcx, [r14+68h]
0x18005293f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180052944  nop
0x180052945  lea     rcx, [r14+40h]; lpCriticalSection
0x180052949  call    cs:__imp_DeleteCriticalSection
0x18005294f  nop
0x180052950  lea     rcx, [r14+18h]; lpCriticalSection
0x180052954  call    cs:__imp_DeleteCriticalSection
0x18005295a  nop
0x18005295b  add     rsp, 28h
0x18005295f  pop     r14
0x180052961  pop     rdi
0x180052962  pop     rsi
0x180052963  pop     rbx
0x180052964  retn
```

# Windows::Compat::Inventory::Service::InventoryScheduler::MakeInventoryScheduler(char const *,HKEY__ *,HKEY__ *)

- ea: `0x18002867c`
- end: `0x18002878d`
- name: `?MakeInventoryScheduler@InventoryScheduler@Service@Inventory@Compat@Windows@@SAPEAV12345@PEBDPEAUHKEY__@@1@Z`
- size: `273`
- prototype: `HANDLE *__fastcall(const char *, HKEY, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011720`

## callees

- `0x180002c40`
- `0x180003af4`
- `0x1800108d4`
- `0x1800110f8`
- `0x1800152d0`
- `0x18001ff40`
- `0x18002867c`
- `0x18002e458`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028757`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028757`

## string_xrefs

- `0x18002877b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800286b2`: `Windows::Compat::Inventory::Service::InventoryScheduler::MakeInventoryScheduler`
- `0x1800286fa`: `Windows::Compat::Inventory::Service::InventoryScheduler::MakeInventoryScheduler`

## pseudocode

```c
HANDLE *__fastcall Windows::Compat::Inventory::Service::InventoryScheduler::MakeInventoryScheduler(
        const char *a1,
        HKEY a2,
        HKEY a3)
{
  HANDLE *v4; // rbx
  HKEY v5; // r8
  HKEY v6; // r9
  HKEY v7; // r8
  HKEY v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  const char *v13; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  Windows::Compat::Inventory::Service::CrmInventoryScheduler *v17; // [rsp+58h] [rbp+10h]

  v4 = 0;
  if ( (unsigned __int8)IsCrmRegisterPresent() )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::InventoryScheduler::MakeInventoryScheduler",
      14,
      "Creating new CrmInventoryScheduler");
    v17 = (Windows::Compat::Inventory::Service::CrmInventoryScheduler *)operator new(0xA0u);
    v4 = (HANDLE *)Windows::Compat::Inventory::Service::CrmInventoryScheduler::CrmInventoryScheduler(v17, a1, v5, v6);
  }
  if ( !v4 )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::InventoryScheduler::MakeInventoryScheduler",
      33,
      "Creating new BasicInventoryScheduler");
    v4 = (HANDLE *)operator new(0x80u);
    Windows::Compat::Inventory::Service::InventoryScheduler::InventoryScheduler(
      (Windows::Compat::Inventory::Service::InventoryScheduler *)v4,
      a1,
      v7,
      v8);
    *v4 = &Windows::Compat::Inventory::Service::BasicInventoryScheduler::`vftable';
    v4[15] = 0;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      v4 + 6,
      v9,
      v10,
      0);
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      v4 + 7,
      v11,
      v12,
      0);
    if ( !SetEvent(v4[5]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v13);
  }
  return v4;
}

```

## disassembly

```asm
0x18002867c  mov     rax, rsp
0x18002867f  mov     [rax+20h], rbx
0x180028683  mov     [rax+18h], r8
0x180028687  mov     [rax+10h], rdx
0x18002868b  mov     [rax+8], rcx
0x18002868f  push    rdi
0x180028690  sub     rsp, 40h
0x180028694  mov     rdi, rcx
0x180028697  xor     ebx, ebx
0x180028699  mov     [rsp+48h+arg_10], rbx
0x18002869e  call    IsCrmRegisterPresent
0x1800286a3  test    al, al
0x1800286a5  jz      short loc_1800286E3
0x1800286a7  lea     r9, aCreatingNewCrm; "Creating new CrmInventoryScheduler"
0x1800286ae  lea     r8d, [rbx+0Eh]
0x1800286b2  lea     rdx, aWindowsCompatI_84; "Windows::Compat::Inventory::Service::In"...
0x1800286b9  lea     ecx, [rbx+3]
0x1800286bc  call    AslLogCallPrintf
0x1800286c1  mov     ecx, 0A0h; Size
0x1800286c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800286cb  mov     [rsp+48h+arg_8], rax
0x1800286d0  mov     rdx, rdi; char *
0x1800286d3  mov     rcx, rax; this
0x1800286d6  call    ??0CrmInventoryScheduler@Service@Inventory@Compat@Windows@@QEAA@PEBDPEAUHKEY__@@1@Z; Windows::Compat::Inventory::Service::CrmInventoryScheduler::CrmInventoryScheduler(char const *,HKEY__ *,HKEY__ *)
0x1800286db  mov     rbx, rax
0x1800286de  mov     [rsp+48h+arg_10], rax
0x1800286e3  jmp     short loc_1800286EA
0x1800286e5  mov     rbx, [rsp+48h+arg_10]
0x1800286ea  test    rbx, rbx
0x1800286ed  jnz     short loc_18002876D
0x1800286ef  lea     r9, aCreatingNewBas; "Creating new BasicInventoryScheduler"
0x1800286f6  lea     r8d, [rbx+21h]
0x1800286fa  lea     rdx, aWindowsCompatI_84; "Windows::Compat::Inventory::Service::In"...
0x180028701  lea     ecx, [rbx+3]
0x180028704  call    AslLogCallPrintf
0x180028709  mov     ecx, 80h; Size
0x18002870e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028713  mov     rbx, rax
0x180028716  mov     [rsp+48h+arg_10], rax
0x18002871b  mov     rdx, [rsp+48h+arg_0]; char *
0x180028720  mov     rcx, rax; this
0x180028723  call    ??0InventoryScheduler@Service@Inventory@Compat@Windows@@IEAA@PEBDPEAUHKEY__@@1@Z; Windows::Compat::Inventory::Service::InventoryScheduler::InventoryScheduler(char const *,HKEY__ *,HKEY__ *)
0x180028728  nop
0x180028729  lea     rax, ??_7BasicInventoryScheduler@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::BasicInventoryScheduler::`vftable'
0x180028730  mov     [rbx], rax
0x180028733  mov     qword ptr [rbx+78h], 0
0x18002873b  lea     rcx, [rbx+30h]
0x18002873f  xor     r9d, r9d
0x180028742  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180028747  lea     rcx, [rbx+38h]
0x18002874b  xor     r9d, r9d
0x18002874e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180028753  mov     rcx, [rbx+28h]; hEvent
0x180028757  call    cs:__imp_SetEvent
0x18002875d  mov     rcx, [rsp+48h]; this
0x180028762  test    eax, eax
0x180028764  jz      short loc_18002877B
0x180028766  jmp     short loc_18002876D
0x180028768  jmp     loc_1800286E5
0x18002876d  mov     rax, rbx
0x180028770  mov     rbx, [rsp+48h+arg_18]
0x180028775  add     rsp, 40h
0x180028779  pop     rdi
0x18002877a  retn
0x18002877b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180028782  mov     edx, 0A01h; void *
0x180028787  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

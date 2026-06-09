# KsControlWnfNotify::Initialize(ushort const *)

- ea: `0x10037431`
- end: `0x10037567`
- name: `?Initialize@KsControlWnfNotify@@QAEJPBG@Z`
- size: `310`
- prototype: `int __thiscall(KsControlWnfNotify *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1000cf60`

## callees

- `0x100075ad`
- `0x1000f598`
- `0x1002d510`
- `0x10037431`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1003748e`
- `ole32!CoCreateInstance` at `0x1003748e`
- `MFPlat!MFStartup` at `0x1003744c`
- `MFPlat!MFStartup` at `0x1003744c`

## pseudocode

```c
void *__thiscall KsControlWnfNotify::Initialize(KsControlWnfNotify *this, const unsigned __int16 *a2)
{
  void *v3; // esi
  LPVOID v4; // edi
  int v5; // ecx
  int v6; // eax
  int (__thiscall *v7)(_DWORD, LPVOID, _DWORD, GUID *, int *); // esi
  int v8; // ecx
  int v9; // edi
  unsigned int v11; // [esp+0h] [ebp-1Ch]
  const char *v12; // [esp+4h] [ebp-18h]
  int v13; // [esp+8h] [ebp-14h]
  LPVOID ppv; // [esp+14h] [ebp-8h] BYREF
  int v15; // [esp+18h] [ebp-4h] BYREF

  ppv = 0;
  v15 = 0;
  v3 = (void *)MFStartup(0x20070u, 0);
  if ( (int)v3 < 0 )
    goto LABEL_7;
  *((_BYTE *)this + 28) = 1;
  ppv = 0;
  v3 = (void *)CoCreateInstance(
                 &CLSID_FrameServerMonitorObjectFactory,
                 0,
                 1u,
                 &_GUID_473ae402_5e85_4176_ba86_285b5ce2cb94,
                 &ppv);
  if ( (int)v3 < 0 )
    goto LABEL_7;
  v4 = ppv;
  v5 = v15;
  v6 = *(_DWORD *)ppv;
  v15 = 0;
  v7 = *(int (__thiscall **)(_DWORD, LPVOID, _DWORD, GUID *, int *))(v6 + 12);
  if ( v5 )
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v5 + 8))(*(_DWORD *)(*(_DWORD *)v5 + 8), v5);
  v3 = (void *)v7(v7, v4, 0, &_GUID_746ea290_a034_4497_8afd_952a87bdd3d5, &v15);
  if ( (int)v3 >= 0
    && (v3 = (void *)(*(int (__thiscall **)(_DWORD, int, int, const unsigned __int16 *, _DWORD))(*(_DWORD *)v15 + 12))(
                       *(_DWORD *)(*(_DWORD *)v15 + 12),
                       v15,
                       6,
                       a2,
                       0),
        (int)v3 >= 0) )
  {
    v8 = v15;
    v9 = *(_DWORD *)this;
    *(_DWORD *)this = v15;
    if ( v8 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v8 + 4))(*(_DWORD *)(*(_DWORD *)v8 + 4), v8);
    if ( v9 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v9 + 8))(*(_DWORD *)(*(_DWORD *)v9 + 8), v9);
    v3 = 0;
  }
  else
  {
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\kscontrolwnfnotify.cpp",
      v3,
      v11,
      v12,
      v13);
  }
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v15);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&ppv);
  return v3;
}

```

## disassembly

```asm
0x10037431  mov     edi, edi
0x10037433  push    ebp
0x10037434  mov     ebp, esp
0x10037436  sub     esp, 10h
0x10037439  push    ebx; int
0x1003743a  push    esi; char *
0x1003743b  push    edi; unsigned int
0x1003743c  xor     edi, edi
0x1003743e  mov     ebx, ecx
0x10037440  push    edi; dwFlags
0x10037441  push    20070h; Version
0x10037446  mov     [ebp+ppv], edi
0x10037449  mov     [ebp+var_4], edi
0x1003744c  call    ds:__imp__MFStartup@8; MFStartup(x,x)
0x10037452  mov     esi, eax
0x10037454  test    esi, esi
0x10037456  jns     short loc_1003745F
0x10037458  push    1Eh
0x1003745a  jmp     loc_1003750C
0x1003745f  mov     ecx, [ebp+ppv]
0x10037462  mov     byte ptr [ebx+1Ch], 1
0x10037466  mov     [ebp+ppv], edi
0x10037469  test    ecx, ecx
0x1003746b  jz      short loc_1003747D
0x1003746d  mov     eax, [ecx]
0x1003746f  push    ecx
0x10037470  mov     esi, [eax+8]
0x10037473  mov     ecx, esi; this
0x10037475  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003747b  call    esi
0x1003747d  lea     eax, [ebp+ppv]
0x10037480  push    eax; ppv
0x10037481  push    offset __GUID_473ae402_5e85_4176_ba86_285b5ce2cb94; riid
0x10037486  push    1; dwClsContext
0x10037488  push    edi; pUnkOuter
0x10037489  push    offset _CLSID_FrameServerMonitorObjectFactory; rclsid
0x1003748e  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10037494  mov     esi, eax
0x10037496  test    esi, esi
0x10037498  jns     short loc_1003749E
0x1003749a  push    21h ; '!'
0x1003749c  jmp     short loc_1003750C
0x1003749e  mov     edi, [ebp+ppv]
0x100374a1  mov     ecx, [ebp+var_4]
0x100374a4  mov     eax, [edi]
0x100374a6  mov     [ebp+var_4], 0
0x100374ad  mov     esi, [eax+0Ch]
0x100374b0  mov     [ebp+var_C], esi
0x100374b3  test    ecx, ecx
0x100374b5  jz      short loc_100374CA
0x100374b7  mov     eax, [ecx]
0x100374b9  push    ecx
0x100374ba  mov     esi, [eax+8]
0x100374bd  mov     ecx, esi; this
0x100374bf  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100374c5  call    esi
0x100374c7  mov     esi, [ebp+var_C]
0x100374ca  lea     eax, [ebp+var_4]
0x100374cd  mov     ecx, esi; this
0x100374cf  push    eax
0x100374d0  push    offset __GUID_746ea290_a034_4497_8afd_952a87bdd3d5
0x100374d5  push    0
0x100374d7  push    edi
0x100374d8  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100374de  call    esi
0x100374e0  mov     esi, eax
0x100374e2  test    esi, esi
0x100374e4  jns     short loc_100374EA
0x100374e6  push    22h ; '"'
0x100374e8  jmp     short loc_1003750C
0x100374ea  mov     ecx, [ebp+var_4]
0x100374ed  push    0
0x100374ef  push    [ebp+arg_0]
0x100374f2  mov     eax, [ecx]
0x100374f4  push    6
0x100374f6  push    ecx
0x100374f7  mov     esi, [eax+0Ch]
0x100374fa  mov     ecx, esi; this
0x100374fc  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037502  call    esi
0x10037504  mov     esi, eax
0x10037506  test    esi, esi
0x10037508  jns     short loc_1003751D
0x1003750a  push    23h ; '#'
0x1003750c  mov     ecx, [ebp+4]
0x1003750f  pop     edx
0x10037510  push    esi; void *
0x10037511  push    offset aMultimediaDsho_1; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10037516  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1003751b  jmp     short loc_1003754E
0x1003751d  mov     ecx, [ebp+var_4]
0x10037520  mov     edi, [ebx]
0x10037522  mov     [ebx], ecx
0x10037524  test    ecx, ecx
0x10037526  jz      short loc_10037538
0x10037528  mov     eax, [ecx]
0x1003752a  push    ecx
0x1003752b  mov     esi, [eax+4]
0x1003752e  mov     ecx, esi; this
0x10037530  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037536  call    esi
0x10037538  test    edi, edi
0x1003753a  jz      short loc_1003754C
0x1003753c  mov     eax, [edi]
0x1003753e  push    edi
0x1003753f  mov     esi, [eax+8]
0x10037542  mov     ecx, esi; this
0x10037544  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003754a  call    esi
0x1003754c  xor     esi, esi
0x1003754e  lea     ecx, [ebp+var_4]
0x10037551  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10037556  lea     ecx, [ebp+ppv]
0x10037559  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1003755e  pop     edi
0x1003755f  mov     eax, esi
0x10037561  pop     esi
0x10037562  pop     ebx
0x10037563  leave
0x10037564  retn    4
```

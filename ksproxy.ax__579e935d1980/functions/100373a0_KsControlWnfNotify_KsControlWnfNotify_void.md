# KsControlWnfNotify::~KsControlWnfNotify(void)

- ea: `0x100373a0`
- end: `0x1003742b`
- name: `??1KsControlWnfNotify@@QAE@XZ`
- size: `139`
- prototype: `void __thiscall(KsControlWnfNotify *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1000cf60`
- `0x1000f5dc`

## callees

- `0x1000f598`
- `0x1002d510`
- `0x100373a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1003741b`
- `KERNEL32!DeleteCriticalSection` at `0x1003741b`
- `MFPlat!MFShutdown` at `0x10037411`
- `MFPlat!MFShutdown` at `0x10037411`

## pseudocode

```c
void __thiscall KsControlWnfNotify::~KsControlWnfNotify(KsControlWnfNotify *this)
{
  _DWORD **v2; // ecx
  _DWORD **v3; // ecx
  int v4; // [esp+4h] [ebp-4h] BYREF

  v2 = *(_DWORD ***)this;
  if ( v2 )
  {
    v4 = 0;
    if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**v2)(
           **v2,
           v2,
           &_GUID_97ec2ea4_0e42_4937_97ac_9d6d328824e1,
           &v4) >= 0 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v4 + 12))(*(_DWORD *)(*(_DWORD *)v4 + 12), v4);
    v3 = *(_DWORD ***)this;
    *(_DWORD *)this = 0;
    if ( v3 )
      ((void (__thiscall *)(_DWORD, _DWORD **))(*v3)[2])((*v3)[2], v3);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v4);
  }
  if ( *((_BYTE *)this + 28) )
    MFShutdown();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 4));
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(this);
}

```

## disassembly

```asm
0x100373a0  mov     edi, edi
0x100373a2  push    ebp
0x100373a3  mov     ebp, esp
0x100373a5  push    ecx
0x100373a6  push    edi
0x100373a7  mov     edi, ecx
0x100373a9  mov     ecx, [edi]
0x100373ab  test    ecx, ecx
0x100373ad  jz      short loc_1003740B
0x100373af  mov     [ebp+var_4], 0
0x100373b6  mov     eax, [ecx]
0x100373b8  push    esi
0x100373b9  mov     esi, [eax]
0x100373bb  lea     eax, [ebp+var_4]
0x100373be  push    eax
0x100373bf  push    offset __GUID_97ec2ea4_0e42_4937_97ac_9d6d328824e1
0x100373c4  push    ecx
0x100373c5  mov     ecx, esi; this
0x100373c7  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100373cd  call    esi
0x100373cf  test    eax, eax
0x100373d1  js      short loc_100373E6
0x100373d3  mov     eax, [ebp+var_4]
0x100373d6  push    eax
0x100373d7  mov     ecx, [eax]
0x100373d9  mov     esi, [ecx+0Ch]
0x100373dc  mov     ecx, esi; this
0x100373de  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100373e4  call    esi
0x100373e6  mov     ecx, [edi]
0x100373e8  mov     dword ptr [edi], 0
0x100373ee  test    ecx, ecx
0x100373f0  jz      short loc_10037402
0x100373f2  mov     eax, [ecx]
0x100373f4  push    ecx
0x100373f5  mov     esi, [eax+8]
0x100373f8  mov     ecx, esi; this
0x100373fa  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037400  call    esi
0x10037402  lea     ecx, [ebp+var_4]
0x10037405  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1003740a  pop     esi
0x1003740b  cmp     byte ptr [edi+1Ch], 0
0x1003740f  jz      short loc_10037417
0x10037411  call    ds:__imp__MFShutdown@0; MFShutdown()
0x10037417  lea     eax, [edi+4]
0x1003741a  push    eax; lpCriticalSection
0x1003741b  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10037421  mov     ecx, edi
0x10037423  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10037428  pop     edi
0x10037429  leave
0x1003742a  retn
```

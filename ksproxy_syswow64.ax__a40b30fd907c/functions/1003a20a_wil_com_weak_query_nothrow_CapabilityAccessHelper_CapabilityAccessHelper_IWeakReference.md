# wil::com_weak_query_nothrow<CapabilityAccessHelper *>(CapabilityAccessHelper * &&,IWeakReference * *)

- ea: `0x1003a20a`
- end: `0x1003a25b`
- name: `??$com_weak_query_nothrow@PAVCapabilityAccessHelper@@@wil@@YGJ$$QAPAVCapabilityAccessHelper@@PAPAUIWeakReference@@@Z`
- size: `81`
- prototype: `int __fastcall(char **, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10039e3c`

## callees

- `0x1000f598`
- `0x1002d510`
- `0x100390ca`
- `0x1003a20a`

## pseudocode

```c
int __fastcall wil::com_weak_query_nothrow<CapabilityAccessHelper *>(char **a1, _DWORD *a2)
{
  char *v2; // ecx
  int v4; // esi
  void *v6; // [esp+8h] [ebp-4h] BYREF

  v2 = *a1;
  v6 = 0;
  *a2 = 0;
  v4 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>>(
         v2,
         &_GUID_00000038_0000_0000_c000_000000000046,
         &v6);
  if ( v4 >= 0 )
    v4 = (*(int (__thiscall **)(_DWORD, void *, _DWORD *))(*(_DWORD *)v6 + 12))(*(_DWORD *)(*(_DWORD *)v6 + 12), v6, a2);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>((int *)&v6);
  return v4;
}

```

## disassembly

```asm
0x1003a20a  mov     edi, edi
0x1003a20c  push    ebp
0x1003a20d  mov     ebp, esp
0x1003a20f  push    ecx
0x1003a210  mov     ecx, [ecx]
0x1003a212  lea     eax, [ebp+var_4]
0x1003a215  push    esi
0x1003a216  push    edi
0x1003a217  mov     edi, edx
0x1003a219  mov     [ebp+var_4], 0
0x1003a220  push    eax
0x1003a221  mov     edx, offset __GUID_00000038_0000_0000_c000_000000000046
0x1003a226  mov     dword ptr [edi], 0
0x1003a22c  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@123@ABU_GUID@@PAPAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x1003a231  mov     esi, eax
0x1003a233  test    esi, esi
0x1003a235  js      short loc_1003A24D
0x1003a237  mov     ecx, [ebp+var_4]
0x1003a23a  push    edi
0x1003a23b  push    ecx
0x1003a23c  mov     eax, [ecx]
0x1003a23e  mov     esi, [eax+0Ch]
0x1003a241  mov     ecx, esi; this
0x1003a243  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003a249  call    esi
0x1003a24b  mov     esi, eax
0x1003a24d  lea     ecx, [ebp+var_4]
0x1003a250  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1003a255  pop     edi
0x1003a256  mov     eax, esi
0x1003a258  pop     esi
0x1003a259  leave
0x1003a25a  retn
```

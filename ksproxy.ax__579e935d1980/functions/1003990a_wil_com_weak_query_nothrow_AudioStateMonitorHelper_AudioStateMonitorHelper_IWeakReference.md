# wil::com_weak_query_nothrow<AudioStateMonitorHelper *>(AudioStateMonitorHelper * &&,IWeakReference * *)

- ea: `0x1003990a`
- end: `0x1003995b`
- name: `??$com_weak_query_nothrow@PAVAudioStateMonitorHelper@@@wil@@YGJ$$QAPAVAudioStateMonitorHelper@@PAPAUIWeakReference@@@Z`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10039550`

## callees

- `0x1000f598`
- `0x1002d510`
- `0x10039210`
- `0x1003990a`

## pseudocode

```c
int __fastcall wil::com_weak_query_nothrow<AudioStateMonitorHelper *>(int *a1, _DWORD *a2)
{
  int v2; // ecx
  int v4; // esi
  int v6; // [esp+8h] [ebp-4h] BYREF

  v2 = *a1;
  v6 = 0;
  *a2 = 0;
  v4 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>>(
         v2,
         &_GUID_00000038_0000_0000_c000_000000000046,
         &v6);
  if ( v4 >= 0 )
    v4 = (*(int (__thiscall **)(_DWORD, int, _DWORD *))(*(_DWORD *)v6 + 12))(*(_DWORD *)(*(_DWORD *)v6 + 12), v6, a2);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v6);
  return v4;
}

```

## disassembly

```asm
0x1003990a  mov     edi, edi
0x1003990c  push    ebp
0x1003990d  mov     ebp, esp
0x1003990f  push    ecx
0x10039910  mov     ecx, [ecx]
0x10039912  lea     eax, [ebp+var_4]
0x10039915  push    esi
0x10039916  push    edi
0x10039917  mov     edi, edx
0x10039919  mov     [ebp+var_4], 0
0x10039920  push    eax
0x10039921  mov     edx, offset __GUID_00000038_0000_0000_c000_000000000046
0x10039926  mov     dword ptr [edi], 0
0x1003992c  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioStateMonitorHelper@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioStateMonitorHelper@@VFtmBase@23@@123@ABU_GUID@@PAPAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x10039931  mov     esi, eax
0x10039933  test    esi, esi
0x10039935  js      short loc_1003994D
0x10039937  mov     ecx, [ebp+var_4]
0x1003993a  push    edi
0x1003993b  push    ecx
0x1003993c  mov     eax, [ecx]
0x1003993e  mov     esi, [eax+0Ch]
0x10039941  mov     ecx, esi; this
0x10039943  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10039949  call    esi
0x1003994b  mov     esi, eax
0x1003994d  lea     ecx, [ebp+var_4]
0x10039950  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10039955  pop     edi
0x10039956  mov     eax, esi
0x10039958  pop     esi
0x10039959  leave
0x1003995a  retn
```

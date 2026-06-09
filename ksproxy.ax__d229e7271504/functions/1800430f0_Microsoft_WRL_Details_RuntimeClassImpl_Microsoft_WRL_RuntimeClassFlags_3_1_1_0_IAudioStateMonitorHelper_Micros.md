# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800430f0`
- end: `0x180043161`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioStateMonitorHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180043024`
- `0x1800430f0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180043112`
- `ole32!CoTaskMemAlloc` at `0x180043112`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioStateMonitorHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    (__int64)v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800430f0  mov     [rsp+arg_0], rbx
0x1800430f5  push    rdi
0x1800430f6  sub     rsp, 20h
0x1800430fa  mov     qword ptr [r8], 0
0x180043101  mov     ecx, 30h ; '0'; cb
0x180043106  mov     dword ptr [rdx], 0
0x18004310c  mov     rbx, r8
0x18004310f  mov     rdi, rdx
0x180043112  call    cs:__imp_CoTaskMemAlloc
0x180043119  nop     dword ptr [rax+rax+00h]
0x18004311e  mov     r8, rax
0x180043121  test    rax, rax
0x180043124  jnz     short loc_18004312D
0x180043126  mov     eax, 8007000Eh
0x18004312b  jmp     short loc_180043155
0x18004312d  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x180043134  lea     rdx, [rsp+28h+arg_8]
0x180043139  mov     [rsp+28h+arg_8], 1
0x180043141  movdqu  xmmword ptr [rax], xmm0
0x180043145  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioStateMonitorHelper@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioStateMonitorHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18004314a  mov     dword ptr [rdi], 3
0x180043150  xor     eax, eax
0x180043152  mov     [rbx], r8
0x180043155  mov     rbx, [rsp+28h+arg_0]
0x18004315a  add     rsp, 20h
0x18004315e  pop     rdi
0x18004315f  retn
```

# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Networking::NetworkOperators::IProvisioningAgent,Microsoft::WRL::CloakedIid<IInitializeWithWindow>,IInspectable>::GetIids(ulong *,_GUID * *)

- ea: `0x18005ae00`
- end: `0x18005ae6d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIProvisioningAgent@NetworkOperators@Networking@Windows@@U?$CloakedIid@UIInitializeWithWindow@@@23@UIInspectable@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `HRESULT __fastcall(Windows::Networking::NetworkOperators::ProvisioningAgent *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005ae80`

## callees

- `0x18005ae00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ae22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ae22`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Networking::NetworkOperators::IProvisioningAgent,Microsoft::WRL::CloakedIid<IInitializeWithWindow>,IInspectable>::GetIids(
        Windows::Networking::NetworkOperators::ProvisioningAgent *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_217700e0_8201_11df_adb9_f4ce462d9137;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  *iidCount = 3;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x18005ae00  mov     [rsp+arg_0], rbx
0x18005ae05  push    rdi
0x18005ae06  sub     rsp, 20h
0x18005ae0a  mov     qword ptr [iids], 0
0x18005ae11  mov     ecx, 30h ; '0'; cb
0x18005ae16  mov     dword ptr [iidCount], 0
0x18005ae1c  mov     rbx, iids
0x18005ae1f  mov     rdi, iidCount
0x18005ae22  call    cs:__imp_CoTaskMemAlloc
0x18005ae28  test    rax, rax
0x18005ae2b  jnz     short loc_18005AE34
0x18005ae2d  mov     eax, 8007000Eh
0x18005ae32  jmp     short loc_18005AE62
0x18005ae34  movups  xmm0, xmmword ptr cs:_GUID_217700e0_8201_11df_adb9_f4ce462d9137.Data1
0x18005ae3b  movdqu  xmmword ptr [rax], xmm0
0x18005ae3f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18005ae46  movdqu  xmmword ptr [rax+10h], xmm1
0x18005ae4b  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18005ae52  movdqu  xmmword ptr [rax+20h], xmm0
0x18005ae57  mov     dword ptr [rdi], 3
0x18005ae5d  mov     [rbx], rax
0x18005ae60  xor     eax, eax
0x18005ae62  mov     rbx, [rsp+28h+arg_0]
0x18005ae67  add     rsp, 20h
0x18005ae6b  pop     rdi
0x18005ae6c  retn
```

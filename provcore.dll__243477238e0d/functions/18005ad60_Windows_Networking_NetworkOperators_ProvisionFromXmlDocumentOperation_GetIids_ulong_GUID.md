# Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation::GetIids(ulong *,_GUID * *)

- ea: `0x18005ad60`
- end: `0x18005add9`
- name: `?GetIids@ProvisionFromXmlDocumentOperation@NetworkOperators@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: `HRESULT __fastcall(Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005ade0`
- `0x18005adf0`

## callees

- `0x18005ad60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ad82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ad82`

## pseudocode

```c
__int64 __fastcall Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation::GetIids(
        Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000036_0000_0000_c000_000000000046;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_9f8fe338_c6b1_5614_a14f_8977a77e17f2;
  v5[3] = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  *iidCount = 4;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x18005ad60  mov     [rsp+arg_0], rbx
0x18005ad65  push    rdi
0x18005ad66  sub     rsp, 20h
0x18005ad6a  mov     qword ptr [iids], 0
0x18005ad71  mov     ecx, 40h ; '@'; cb
0x18005ad76  mov     dword ptr [iidCount], 0
0x18005ad7c  mov     rbx, iids
0x18005ad7f  mov     rdi, iidCount
0x18005ad82  call    cs:__imp_CoTaskMemAlloc
0x18005ad88  test    rax, rax
0x18005ad8b  jnz     short loc_18005AD94
0x18005ad8d  mov     eax, 8007000Eh
0x18005ad92  jmp     short loc_18005ADCE
0x18005ad94  movups  xmm0, xmmword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data1
0x18005ad9b  movdqu  xmmword ptr [rax], xmm0
0x18005ad9f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18005ada6  movdqu  xmmword ptr [rax+10h], xmm1
0x18005adab  movups  xmm0, xmmword ptr cs:_GUID_9f8fe338_c6b1_5614_a14f_8977a77e17f2.Data1
0x18005adb2  movdqu  xmmword ptr [rax+20h], xmm0
0x18005adb7  movups  xmm1, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18005adbe  movdqu  xmmword ptr [rax+30h], xmm1
0x18005adc3  mov     dword ptr [rdi], 4
0x18005adc9  mov     [rbx], rax
0x18005adcc  xor     eax, eax
0x18005adce  mov     rbx, [rsp+28h+arg_0]
0x18005add3  add     rsp, 20h
0x18005add7  pop     rdi
0x18005add8  retn
```

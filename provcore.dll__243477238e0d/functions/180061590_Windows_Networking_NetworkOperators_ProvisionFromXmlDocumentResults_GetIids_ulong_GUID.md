# Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults::GetIids(ulong *,_GUID * *)

- ea: `0x180061590`
- end: `0x1800615fd`
- name: `?GetIids@ProvisionFromXmlDocumentResults@NetworkOperators@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `HRESULT __fastcall(Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180061610`

## callees

- `0x180061590`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800615b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800615b2`

## pseudocode

```c
__int64 __fastcall Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults::GetIids(
        Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_217700e0_8203_11df_adb9_f4ce462d9137;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  *iidCount = 3;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x180061590  mov     [rsp+arg_0], rbx
0x180061595  push    rdi
0x180061596  sub     rsp, 20h
0x18006159a  mov     qword ptr [iids], 0
0x1800615a1  mov     ecx, 30h ; '0'; cb
0x1800615a6  mov     dword ptr [iidCount], 0
0x1800615ac  mov     rbx, iids
0x1800615af  mov     rdi, iidCount
0x1800615b2  call    cs:__imp_CoTaskMemAlloc
0x1800615b8  test    rax, rax
0x1800615bb  jnz     short loc_1800615C4
0x1800615bd  mov     eax, 8007000Eh
0x1800615c2  jmp     short loc_1800615F2
0x1800615c4  movups  xmm0, xmmword ptr cs:_GUID_217700e0_8203_11df_adb9_f4ce462d9137.Data1
0x1800615cb  movdqu  xmmword ptr [rax], xmm0
0x1800615cf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800615d6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800615db  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x1800615e2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800615e7  mov     dword ptr [rdi], 3
0x1800615ed  mov     [rbx], rax
0x1800615f0  xor     eax, eax
0x1800615f2  mov     rbx, [rsp+28h+arg_0]
0x1800615f7  add     rsp, 20h
0x1800615fb  pop     rdi
0x1800615fc  retn
```

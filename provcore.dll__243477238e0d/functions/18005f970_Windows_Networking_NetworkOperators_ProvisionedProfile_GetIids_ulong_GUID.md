# Windows::Networking::NetworkOperators::ProvisionedProfile::GetIids(ulong *,_GUID * *)

- ea: `0x18005f970`
- end: `0x18005f9dd`
- name: `?GetIids@ProvisionedProfile@NetworkOperators@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `HRESULT __fastcall(Windows::Networking::NetworkOperators::ProvisionedProfile *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005f9f0`

## callees

- `0x18005f970`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005f992`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005f992`

## pseudocode

```c
__int64 __fastcall Windows::Networking::NetworkOperators::ProvisionedProfile::GetIids(
        Windows::Networking::NetworkOperators::ProvisionedProfile *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_217700e0_8202_11df_adb9_f4ce462d9137;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  *iidCount = 3;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x18005f970  mov     [rsp+arg_0], rbx
0x18005f975  push    rdi
0x18005f976  sub     rsp, 20h
0x18005f97a  mov     qword ptr [iids], 0
0x18005f981  mov     ecx, 30h ; '0'; cb
0x18005f986  mov     dword ptr [iidCount], 0
0x18005f98c  mov     rbx, iids
0x18005f98f  mov     rdi, iidCount
0x18005f992  call    cs:__imp_CoTaskMemAlloc
0x18005f998  test    rax, rax
0x18005f99b  jnz     short loc_18005F9A4
0x18005f99d  mov     eax, 8007000Eh
0x18005f9a2  jmp     short loc_18005F9D2
0x18005f9a4  movups  xmm0, xmmword ptr cs:_GUID_217700e0_8202_11df_adb9_f4ce462d9137.Data1
0x18005f9ab  movdqu  xmmword ptr [rax], xmm0
0x18005f9af  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18005f9b6  movdqu  xmmword ptr [rax+10h], xmm1
0x18005f9bb  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18005f9c2  movdqu  xmmword ptr [rax+20h], xmm0
0x18005f9c7  mov     dword ptr [rdi], 3
0x18005f9cd  mov     [rbx], rax
0x18005f9d0  xor     eax, eax
0x18005f9d2  mov     rbx, [rsp+28h+arg_0]
0x18005f9d7  add     rsp, 20h
0x18005f9db  pop     rdi
0x18005f9dc  retn
```

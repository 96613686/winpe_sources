# Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::NetworkMediaType>>::GetIids(ulong *,_GUID * *)

- ea: `0x180017940`
- end: `0x1800179ad`
- name: `?GetIids@?$Vector@W4NetworkMediaType@UX@Networking@Windows@@U?$DefaultEqualityPredicate@W4NetworkMediaType@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4NetworkMediaType@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@W4NetworkMediaType@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800179c0`

## callees

- `0x180017940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017962`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017962`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<enum Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<enum Windows::Networking::UX::NetworkMediaType>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_501a5755_064c_5034_9e9a_1d94e924d5a8;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_cbc84f97_31e2_52f7_bdac_e9c22b4968e4;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180017940  mov     [rsp+arg_0], rbx
0x180017945  push    rdi
0x180017946  sub     rsp, 20h
0x18001794a  mov     qword ptr [r8], 0
0x180017951  mov     ecx, 30h ; '0'; cb
0x180017956  mov     dword ptr [rdx], 0
0x18001795c  mov     rbx, r8
0x18001795f  mov     rdi, rdx
0x180017962  call    cs:__imp_CoTaskMemAlloc
0x180017968  test    rax, rax
0x18001796b  jnz     short loc_180017974
0x18001796d  mov     eax, 8007000Eh
0x180017972  jmp     short loc_1800179A2
0x180017974  movups  xmm0, xmmword ptr cs:_GUID_501a5755_064c_5034_9e9a_1d94e924d5a8.Data1
0x18001797b  movdqu  xmmword ptr [rax], xmm0
0x18001797f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180017986  movdqu  xmmword ptr [rax+10h], xmm1
0x18001798b  movups  xmm0, xmmword ptr cs:_GUID_cbc84f97_31e2_52f7_bdac_e9c22b4968e4.Data1
0x180017992  movdqu  xmmword ptr [rax+20h], xmm0
0x180017997  mov     dword ptr [rdi], 3
0x18001799d  mov     [rbx], rax
0x1800179a0  xor     eax, eax
0x1800179a2  mov     rbx, [rsp+28h+arg_0]
0x1800179a7  add     rsp, 20h
0x1800179ab  pop     rdi
0x1800179ac  retn
```

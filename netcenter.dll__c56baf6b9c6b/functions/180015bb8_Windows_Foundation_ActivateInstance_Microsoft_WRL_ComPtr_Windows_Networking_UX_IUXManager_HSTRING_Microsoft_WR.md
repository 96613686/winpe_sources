# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>)

- ea: `0x180015bb8`
- end: `0x180015c50`
- name: `??$ActivateInstance@V?$ComPtr@UIUXManager@UX@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUXManager@UX@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016cb8`

## callees

- `0x180015bb8`
- `0x180018708`
- `0x18002239c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015be8`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015be8`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>(
        __int64 a1,
        __int64 *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_6f9bbe05_ff62_4f69_8d02_9de60cac77d7, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(
             v6,
             &GUID_6f9bbe05_ff62_4f69_8d02_9de60cac77d7,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015bb8  mov     [rsp+arg_0], rbx
0x180015bbd  push    rdi
0x180015bbe  sub     rsp, 20h
0x180015bc2  mov     rbx, rdx
0x180015bc5  mov     rdi, rcx
0x180015bc8  mov     rcx, rdx
0x180015bcb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x180015bd0  mov     qword ptr [rbx], 0
0x180015bd7  mov     [rsp+28h+arg_8], 0
0x180015be0  lea     rdx, [rsp+28h+arg_8]
0x180015be5  mov     rcx, rdi
0x180015be8  call    cs:__imp_RoActivateInstance
0x180015bee  mov     edi, eax
0x180015bf0  test    eax, eax
0x180015bf2  js      short loc_180015C43
0x180015bf4  mov     r8d, 10h; Size
0x180015bfa  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180015c01  lea     rcx, _GUID_6f9bbe05_ff62_4f69_8d02_9de60cac77d7; Buf1
0x180015c08  call    memcmp_0
0x180015c0d  mov     rcx, [rsp+28h+arg_8]
0x180015c12  test    eax, eax
0x180015c14  jnz     short loc_180015C1B
0x180015c16  mov     [rbx], rcx
0x180015c19  jmp     short loc_180015C43
0x180015c1b  mov     rax, [rcx]
0x180015c1e  mov     r8, rbx
0x180015c21  lea     rdx, _GUID_6f9bbe05_ff62_4f69_8d02_9de60cac77d7
0x180015c28  mov     rax, [rax]
0x180015c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c30  mov     edi, eax
0x180015c32  mov     rcx, [rsp+28h+arg_8]
0x180015c37  mov     rax, [rcx]
0x180015c3a  mov     rax, [rax+10h]
0x180015c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c43  mov     eax, edi
0x180015c45  mov     rbx, [rsp+28h+arg_0]
0x180015c4a  add     rsp, 20h
0x180015c4e  pop     rdi
0x180015c4f  retn
```

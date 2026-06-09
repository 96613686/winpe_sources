# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Networking::UX::NetworkMediaType>>::GetIids(ulong *,_GUID * *)

- ea: `0x180017840`
- end: `0x1800178a1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@W4NetworkMediaType@UX@Networking@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180017840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017862`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017862`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<enum Windows::Networking::UX::NetworkMediaType>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_b6b89422_2717_512f_a610_ef9cebff447b;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180017840  mov     [rsp+arg_0], rbx
0x180017845  push    rdi
0x180017846  sub     rsp, 20h
0x18001784a  mov     qword ptr [r8], 0
0x180017851  mov     ecx, 20h ; ' '; cb
0x180017856  mov     dword ptr [rdx], 0
0x18001785c  mov     rbx, r8
0x18001785f  mov     rdi, rdx
0x180017862  call    cs:__imp_CoTaskMemAlloc
0x180017868  test    rax, rax
0x18001786b  jnz     short loc_180017874
0x18001786d  mov     eax, 8007000Eh
0x180017872  jmp     short loc_180017896
0x180017874  movups  xmm0, xmmword ptr cs:_GUID_b6b89422_2717_512f_a610_ef9cebff447b.Data1
0x18001787b  movdqu  xmmword ptr [rax], xmm0
0x18001787f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180017886  movdqu  xmmword ptr [rax+10h], xmm1
0x18001788b  mov     dword ptr [rdi], 2
0x180017891  mov     [rbx], rax
0x180017894  xor     eax, eax
0x180017896  mov     rbx, [rsp+28h+arg_0]
0x18001789b  add     rsp, 20h
0x18001789f  pop     rdi
0x1800178a0  retn
```

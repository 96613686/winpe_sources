# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>)

- ea: `0x180007254`
- end: `0x180007300`
- name: `??$ActivateInstance@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010720`
- `0x1800108e0`
- `0x180010aa0`

## callees

- `0x180007254`
- `0x1800133d6`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180007298`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180007298`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rcx
  int v5; // edi
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v4 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *a2 = 0;
  v7 = 0;
  v5 = RoActivateInstance(a1, &v7);
  if ( v5 >= 0 )
  {
    if ( !memcmp_0(&GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v7;
    }
    else
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v7)(
             v7,
             &GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007254  mov     [rsp+arg_0], rbx
0x180007259  push    rdi
0x18000725a  sub     rsp, 20h
0x18000725e  mov     rbx, rdx
0x180007261  mov     rdi, rcx
0x180007264  mov     rcx, [rdx]
0x180007267  test    rcx, rcx
0x18000726a  jz      short loc_180007280
0x18000726c  mov     qword ptr [rdx], 0
0x180007273  mov     rax, [rcx]
0x180007276  mov     rax, [rax+10h]
0x18000727a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000727f  nop
0x180007280  mov     qword ptr [rbx], 0
0x180007287  mov     [rsp+28h+arg_8], 0
0x180007290  lea     rdx, [rsp+28h+arg_8]
0x180007295  mov     rcx, rdi
0x180007298  call    cs:__imp_RoActivateInstance
0x18000729e  mov     edi, eax
0x1800072a0  test    eax, eax
0x1800072a2  js      short loc_1800072F3
0x1800072a4  mov     r8d, 10h; Size
0x1800072aa  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800072b1  lea     rcx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494; Buf1
0x1800072b8  call    memcmp_0
0x1800072bd  mov     rcx, [rsp+28h+arg_8]
0x1800072c2  test    eax, eax
0x1800072c4  jnz     short loc_1800072CB
0x1800072c6  mov     [rbx], rcx
0x1800072c9  jmp     short loc_1800072F3
0x1800072cb  mov     rax, [rcx]
0x1800072ce  mov     r8, rbx
0x1800072d1  lea     rdx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494
0x1800072d8  mov     rax, [rax]
0x1800072db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e0  mov     edi, eax
0x1800072e2  mov     rcx, [rsp+28h+arg_8]
0x1800072e7  mov     rax, [rcx]
0x1800072ea  mov     rax, [rax+10h]
0x1800072ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072f3  mov     eax, edi
0x1800072f5  mov     rbx, [rsp+28h+arg_0]
0x1800072fa  add     rsp, 20h
0x1800072fe  pop     rdi
0x1800072ff  retn
```

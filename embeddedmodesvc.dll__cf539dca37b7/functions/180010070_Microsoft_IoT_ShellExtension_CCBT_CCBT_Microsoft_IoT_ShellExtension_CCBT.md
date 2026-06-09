# Microsoft::IoT::ShellExtension::CCBT::CCBT(Microsoft::IoT::ShellExtension::CCBT &&)

- ea: `0x180010070`
- end: `0x1800100f8`
- name: `??0CCBT@ShellExtension@IoT@Microsoft@@QEAA@$$QEAV0123@@Z`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f304`
- `0x18000fae0`
- `0x18000fd70`
- `0x1800114f0`

## callees

- `0x18000d1cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBT::CCBT(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // r8
  __int64 v3; // r9

  *a1 = *a2;
  a1[1] = a2[1];
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    a1 + 2,
    a2 + 2);
  *(_QWORD *)(v3 + 32) = *(_QWORD *)(v2 + 32);
  *(_QWORD *)(v2 + 32) = 0;
  *(_QWORD *)(v3 + 40) = *(_QWORD *)(v2 + 40);
  *(_QWORD *)(v2 + 40) = 0;
  *(_QWORD *)(v3 + 48) = *(_QWORD *)(v2 + 48);
  *(_QWORD *)(v2 + 48) = 0;
  *(_DWORD *)(v3 + 56) = *(_DWORD *)(v2 + 56);
  *(_OWORD *)(v3 + 60) = *(_OWORD *)(v2 + 60);
  *(_WORD *)(v3 + 76) = *(_WORD *)(v2 + 76);
  *(_BYTE *)(v3 + 78) = *(_BYTE *)(v2 + 78);
  *(_BYTE *)(v3 + 79) = *(_BYTE *)(v2 + 79);
  *(_BYTE *)(v3 + 80) = *(_BYTE *)(v2 + 80);
  return v3;
}

```

## disassembly

```asm
0x180010070  sub     rsp, 28h
0x180010074  mov     rax, [rdx]
0x180010077  mov     r8, rdx
0x18001007a  mov     [rcx], rax
0x18001007d  mov     r9, rcx
0x180010080  mov     rax, [rdx+8]
0x180010084  add     rdx, 10h
0x180010088  mov     [rcx+8], rax
0x18001008c  add     rcx, 10h
0x180010090  call    ??0?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x180010095  mov     rax, [r8+20h]
0x180010099  xor     ecx, ecx
0x18001009b  mov     [r9+20h], rax
0x18001009f  mov     [r8+20h], rcx
0x1800100a3  mov     rax, [r8+28h]
0x1800100a7  mov     [r9+28h], rax
0x1800100ab  mov     [r8+28h], rcx
0x1800100af  mov     rax, [r8+30h]
0x1800100b3  mov     [r9+30h], rax
0x1800100b7  mov     [r8+30h], rcx
0x1800100bb  mov     eax, [r8+38h]
0x1800100bf  mov     [r9+38h], eax
0x1800100c3  movups  xmm0, xmmword ptr [r8+3Ch]
0x1800100c8  movdqu  xmmword ptr [r9+3Ch], xmm0
0x1800100ce  movzx   eax, word ptr [r8+4Ch]
0x1800100d3  mov     [r9+4Ch], ax
0x1800100d8  mov     al, [r8+4Eh]
0x1800100dc  mov     [r9+4Eh], al
0x1800100e0  mov     al, [r8+4Fh]
0x1800100e4  mov     [r9+4Fh], al
0x1800100e8  mov     al, [r8+50h]
0x1800100ec  mov     [r9+50h], al
0x1800100f0  mov     rax, r9
0x1800100f3  add     rsp, 28h
0x1800100f7  retn
```

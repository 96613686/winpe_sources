# uus::Utility::GetStableFolder(void)

- ea: `0x180001520`
- end: `0x18000157f`
- name: `?GetStableFolder@Utility@uus@@SA?AVpath@filesystem@std@@XZ`
- size: `95`
- prototype: `void *__fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800035b0`
- `0x1800087c0`

## callees

- `0x180001520`
- `0x1800015e0`
- `0x180002fcc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001570`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001570`

## pseudocode

```c
void *__fastcall uus::Utility::GetStableFolder(void *a1)
{
  __int64 v2; // rax
  _QWORD v4[3]; // [rsp+30h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  pv = a1;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(&pv);
  v2 = -1;
  do
    ++v2;
  while ( *((_WORD *)pv + v2) );
  v4[0] = pv;
  v4[1] = v2;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(a1, v4);
  if ( pv )
    CoTaskMemFree(pv);
  return a1;
}

```

## disassembly

```asm
0x180001520  mov     [rsp+pv], rcx
0x180001525  push    rbx
0x180001526  sub     rsp, 40h
0x18000152a  mov     rbx, rcx
0x18000152d  lea     rcx, [rsp+48h+pv]
0x180001532  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180001537  nop
0x180001538  mov     rdx, [rsp+48h+pv]
0x18000153d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001544  inc     rax
0x180001547  cmp     word ptr [rdx+rax*2], 0
0x18000154c  jnz     short loc_180001544
0x18000154e  mov     [rsp+48h+var_18], rdx
0x180001553  mov     [rsp+48h+var_10], rax
0x180001558  lea     rdx, [rsp+48h+var_18]
0x18000155d  mov     rcx, rbx
0x180001560  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180001565  nop
0x180001566  mov     rcx, [rsp+48h+pv]; pv
0x18000156b  test    rcx, rcx
0x18000156e  jz      short loc_180001576
0x180001570  call    cs:__imp_CoTaskMemFree
0x180001576  mov     rax, rbx
0x180001579  add     rsp, 40h
0x18000157d  pop     rbx
0x18000157e  retn
```

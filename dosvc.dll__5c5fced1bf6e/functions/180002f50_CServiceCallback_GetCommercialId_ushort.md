# CServiceCallback::GetCommercialId(ushort * *)

- ea: `0x180002f50`
- end: `0x180002fc3`
- name: `?GetCommercialId@CServiceCallback@@EEBAJPEAPEAG@Z`
- size: `115`
- prototype: `__int64 __fastcall(CServiceCallback *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001790`
- `0x180001d00`
- `0x180002f50`
- `0x180003290`

## string_xrefs

- `0x180002f91`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`

## pseudocode

```c
__int64 __fastcall CServiceCallback::GetCommercialId(CServiceCallback *this, unsigned __int16 **a2)
{
  const unsigned __int16 *CommercialId; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int16 *v7; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  CommercialId = Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId();
  if ( !CommercialId || !*CommercialId )
    return 2147943568LL;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v7,
    CommercialId,
    -1);
  if ( v7 )
  {
    *a2 = v7;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
      (const char *)0x8007000ELL,
      v5);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180002f50  mov     [rsp+arg_0], rbx
0x180002f55  push    rdi; int
0x180002f56  sub     rsp, 20h
0x180002f5a  xor     edi, edi
0x180002f5c  mov     rbx, rdx
0x180002f5f  mov     [rdx], rdi
0x180002f62  call    ?GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ; Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)
0x180002f67  test    rax, rax
0x180002f6a  jz      short loc_180002FB3
0x180002f6c  cmp     [rax], di
0x180002f6f  jz      short loc_180002FB3
0x180002f71  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002f75  lea     rcx, [rsp+28h+arg_8]
0x180002f7a  mov     rdx, rax
0x180002f7d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180002f82  mov     rax, [rsp+28h+arg_8]
0x180002f87  test    rax, rax
0x180002f8a  jnz     short loc_180002FAC
0x180002f8c  mov     rcx, [rsp+28h]; this
0x180002f91  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x180002f98  mov     ebx, 8007000Eh
0x180002f9d  lea     edx, [rdi+6Eh]; void *
0x180002fa0  mov     r9d, ebx; char *
0x180002fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002fa8  mov     eax, ebx
0x180002faa  jmp     short loc_180002FB8
0x180002fac  mov     [rbx], rax
0x180002faf  xor     eax, eax
0x180002fb1  jmp     short loc_180002FB8
0x180002fb3  mov     eax, 80070490h
0x180002fb8  mov     rbx, [rsp+28h+arg_0]
0x180002fbd  add     rsp, 20h
0x180002fc1  pop     rdi
0x180002fc2  retn
```

# Windows::Compat::Inventory::AppFootprint::AppFootprintTracer::IsEnabled(bool &)

- ea: `0x1800ccef0`
- end: `0x1800cd044`
- name: `?IsEnabled@AppFootprintTracer@AppFootprint@Inventory@Compat@Windows@@UEAA_NAEA_N@Z`
- size: `340`
- prototype: `bool __fastcall(Windows::Compat::Inventory::AppFootprint::AppFootprintTracer *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800108d4`
- `0x1800152d0`
- `0x180031898`
- `0x1800ccc0c`
- `0x1800ccef0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ccff6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ccff6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800ccfe6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800ccfe6`

## string_xrefs

- `0x1800cd01b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800cd032`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800ccfb9`: `Windows::Compat::Inventory::AppFootprint::AppFootprintTracer::IsEnabled`
- `0x1800ccf73`: `Windows::Compat::Inventory::AppFootprint::AppFootprintModule::IsEnabled`

## pseudocode

```c
bool __fastcall Windows::Compat::Inventory::AppFootprint::AppFootprintTracer::IsEnabled(
        Windows::Compat::Inventory::AppFootprint::AppFootprintTracer *this,
        bool *a2)
{
  bool v4; // di
  __int64 (__fastcall *v5)(int *, int *); // rax
  int v6; // ebx
  const char *v7; // r9
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  v12 = 0;
  v4 = 0;
  if ( (int)Windows::Compat::Inventory::AppFootprint::AppFootprintModule::DllAcquireRelease((__int64)this + 24, 0) < 0 )
  {
    v6 = -2147467259;
  }
  else
  {
    v5 = (__int64 (__fastcall *)(int *, int *))*((_QWORD *)this + 4);
    if ( v5 )
    {
      v6 = v5(&v11, &v12);
      if ( v6 >= 0 )
      {
        v4 = v11 != 0;
        *a2 = v12 != 0;
      }
    }
    else
    {
      v6 = -2147467259;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::AppFootprint::AppFootprintModule::IsEnabled",
        215,
        "AppFootprintIsEnabled is NULL [%#x]",
        -2147467259);
    }
    Windows::Compat::Inventory::AppFootprint::AppFootprintModule::DllAcquireRelease((__int64)this + 24, 1);
  }
  if ( *a2 && !v4 )
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::AppFootprint::AppFootprintTracer::IsEnabled",
      98,
      "AppFootprintTracer is disabled but testOverride is true [%#x]",
      -2147418113);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone>::GetImpl'::`2'::impl) )
  {
    if ( v6 >= 0 && v4 )
    {
      if ( !ResetEvent(*((HANDLE *)this + 7)) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA06,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v7);
    }
    else if ( !SetEvent(*((HANDLE *)this + 7)) )
    {
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800ccef0  mov     rax, rsp
0x1800ccef3  mov     [rax+18h], rbx
0x1800ccef7  mov     [rax+20h], rbp
0x1800ccefb  push    rsi
0x1800ccefc  push    rdi
0x1800ccefd  push    r14
0x1800cceff  sub     rsp, 30h
0x1800ccf03  mov     r14, rdx
0x1800ccf06  mov     dword ptr [rax+8], 0
0x1800ccf0d  mov     rbp, rcx
0x1800ccf10  mov     dword ptr [rax+10h], 0
0x1800ccf17  xor     edx, edx
0x1800ccf19  add     rcx, 18h
0x1800ccf1d  xor     dil, dil
0x1800ccf20  call    ?DllAcquireRelease@AppFootprintModule@AppFootprint@Inventory@Compat@Windows@@AEAAJW4Action@12345@@Z; Windows::Compat::Inventory::AppFootprint::AppFootprintModule::DllAcquireRelease(Windows::Compat::Inventory::AppFootprint::AppFootprintModule::Action)
0x1800ccf25  test    eax, eax
0x1800ccf27  js      short loc_1800CCF94
0x1800ccf29  mov     rax, [rbp+20h]
0x1800ccf2d  test    rax, rax
0x1800ccf30  jz      short loc_1800CCF5D
0x1800ccf32  lea     rdx, [rsp+48h+arg_8]
0x1800ccf37  lea     rcx, [rsp+48h+arg_0]
0x1800ccf3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccf41  mov     ebx, eax
0x1800ccf43  test    eax, eax
0x1800ccf45  js      short loc_1800CCF84
0x1800ccf47  cmp     [rsp+48h+arg_0], 0
0x1800ccf4c  setnz   dil
0x1800ccf50  cmp     [rsp+48h+arg_8], 0
0x1800ccf55  setnz   al
0x1800ccf58  mov     [r14], al
0x1800ccf5b  jmp     short loc_1800CCF84
0x1800ccf5d  mov     ebx, 80004005h
0x1800ccf62  lea     r9, aAppfootprintis; "AppFootprintIsEnabled is NULL [%#x]"
0x1800ccf69  mov     r8d, 0D7h
0x1800ccf6f  mov     [rsp+48h+var_28], ebx
0x1800ccf73  lea     rdx, aWindowsCompatI_91; "Windows::Compat::Inventory::AppFootprin"...
0x1800ccf7a  mov     ecx, 1
0x1800ccf7f  call    AslLogCallPrintf
0x1800ccf84  mov     edx, 1
0x1800ccf89  lea     rcx, [rbp+18h]
0x1800ccf8d  call    ?DllAcquireRelease@AppFootprintModule@AppFootprint@Inventory@Compat@Windows@@AEAAJW4Action@12345@@Z; Windows::Compat::Inventory::AppFootprint::AppFootprintModule::DllAcquireRelease(Windows::Compat::Inventory::AppFootprint::AppFootprintModule::Action)
0x1800ccf92  jmp     short loc_1800CCF99
0x1800ccf94  mov     ebx, 80004005h
0x1800ccf99  cmp     byte ptr [r14], 0
0x1800ccf9d  jz      short loc_1800CCFC9
0x1800ccf9f  test    dil, dil
0x1800ccfa2  jnz     short loc_1800CCFC9
0x1800ccfa4  mov     r8d, 62h ; 'b'
0x1800ccfaa  mov     [rsp+48h+var_28], 8000FFFFh
0x1800ccfb2  lea     r9, aAppfootprinttr; "AppFootprintTracer is disabled but test"...
0x1800ccfb9  lea     rdx, aWindowsCompatI_41; "Windows::Compat::Inventory::AppFootprin"...
0x1800ccfc0  lea     ecx, [r8-61h]
0x1800ccfc4  call    AslLogCallPrintf
0x1800ccfc9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone> `wil::Feature<__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone>::GetImpl(void)'::`2'::impl
0x1800ccfd0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone>::__private_IsEnabled(void)
0x1800ccfd5  test    al, al
0x1800ccfd7  jnz     short loc_1800CD000
0x1800ccfd9  test    ebx, ebx
0x1800ccfdb  js      short loc_1800CCFF2
0x1800ccfdd  test    dil, dil
0x1800ccfe0  jz      short loc_1800CCFF2
0x1800ccfe2  mov     rcx, [rbp+38h]; hEvent
0x1800ccfe6  call    cs:__imp_ResetEvent
0x1800ccfec  test    eax, eax
0x1800ccfee  jz      short loc_1800CD02D
0x1800ccff0  jmp     short loc_1800CD000
0x1800ccff2  mov     rcx, [rbp+38h]; hEvent
0x1800ccff6  call    cs:__imp_SetEvent
0x1800ccffc  test    eax, eax
0x1800ccffe  jz      short loc_1800CD016
0x1800cd000  mov     rbx, [rsp+48h+arg_10]
0x1800cd005  mov     al, dil
0x1800cd008  mov     rbp, [rsp+48h+arg_18]
0x1800cd00d  add     rsp, 30h
0x1800cd011  pop     r14
0x1800cd013  pop     rdi
0x1800cd014  pop     rsi
0x1800cd015  retn
0x1800cd016  mov     rcx, [rsp+48h]; this
0x1800cd01b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cd022  mov     edx, 0A01h; void *
0x1800cd027  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800cd02d  mov     rcx, [rsp+48h]; this
0x1800cd032  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cd039  mov     edx, 0A06h; void *
0x1800cd03e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

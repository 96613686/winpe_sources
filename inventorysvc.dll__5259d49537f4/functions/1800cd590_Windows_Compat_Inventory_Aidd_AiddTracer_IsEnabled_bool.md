# Windows::Compat::Inventory::Aidd::AiddTracer::IsEnabled(bool &)

- ea: `0x1800cd590`
- end: `0x1800cd6d4`
- name: `?IsEnabled@AiddTracer@Aidd@Inventory@Compat@Windows@@UEAA_NAEA_N@Z`
- size: `324`
- prototype: `bool __fastcall(Windows::Compat::Inventory::Aidd::AiddTracer *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800108d4`
- `0x1800152d0`
- `0x1800cd2bc`
- `0x1800cd590`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cd686`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cd686`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800cd676`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800cd676`

## string_xrefs

- `0x1800cd6ab`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800cd6c2`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800cd659`: `Windows::Compat::Inventory::Aidd::AiddTracer::IsEnabled`
- `0x1800cd613`: `Windows::Compat::Inventory::Aidd::AiddModule::IsEnabled`

## pseudocode

```c
bool __fastcall Windows::Compat::Inventory::Aidd::AiddTracer::IsEnabled(
        Windows::Compat::Inventory::Aidd::AiddTracer *this,
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
  if ( (int)Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease((__int64)this + 24, 0) < 0 )
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
        "Windows::Compat::Inventory::Aidd::AiddModule::IsEnabled",
        154,
        "AiddIsEnabled is NULL [%#x]",
        -2147467259);
    }
    Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease((__int64)this + 24, 1);
  }
  if ( *a2 && !v4 )
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Aidd::AiddTracer::IsEnabled",
      44,
      "AiddTracer is disabled but testOverride is true [%#x]",
      -2147418113);
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
  return v4;
}

```

## disassembly

```asm
0x1800cd590  mov     rax, rsp
0x1800cd593  mov     [rax+18h], rbx
0x1800cd597  mov     [rax+20h], rbp
0x1800cd59b  push    rsi
0x1800cd59c  push    rdi
0x1800cd59d  push    r14
0x1800cd59f  sub     rsp, 30h
0x1800cd5a3  mov     r14, rdx
0x1800cd5a6  mov     dword ptr [rax+8], 0
0x1800cd5ad  mov     rbp, rcx
0x1800cd5b0  mov     dword ptr [rax+10h], 0
0x1800cd5b7  xor     edx, edx
0x1800cd5b9  add     rcx, 18h
0x1800cd5bd  xor     dil, dil
0x1800cd5c0  call    ?DllAcquireRelease@AiddModule@Aidd@Inventory@Compat@Windows@@AEAAJW4Action@12345@@Z; Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease(Windows::Compat::Inventory::Aidd::AiddModule::Action)
0x1800cd5c5  test    eax, eax
0x1800cd5c7  js      short loc_1800CD634
0x1800cd5c9  mov     rax, [rbp+20h]
0x1800cd5cd  test    rax, rax
0x1800cd5d0  jz      short loc_1800CD5FD
0x1800cd5d2  lea     rdx, [rsp+48h+arg_8]
0x1800cd5d7  lea     rcx, [rsp+48h+arg_0]
0x1800cd5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd5e1  mov     ebx, eax
0x1800cd5e3  test    eax, eax
0x1800cd5e5  js      short loc_1800CD624
0x1800cd5e7  cmp     [rsp+48h+arg_0], 0
0x1800cd5ec  setnz   dil
0x1800cd5f0  cmp     [rsp+48h+arg_8], 0
0x1800cd5f5  setnz   al
0x1800cd5f8  mov     [r14], al
0x1800cd5fb  jmp     short loc_1800CD624
0x1800cd5fd  mov     ebx, 80004005h
0x1800cd602  lea     r9, aAiddisenabledI; "AiddIsEnabled is NULL [%#x]"
0x1800cd609  mov     r8d, 9Ah
0x1800cd60f  mov     [rsp+48h+var_28], ebx
0x1800cd613  lea     rdx, aWindowsCompatI_38; "Windows::Compat::Inventory::Aidd::AiddM"...
0x1800cd61a  mov     ecx, 1
0x1800cd61f  call    AslLogCallPrintf
0x1800cd624  mov     edx, 1
0x1800cd629  lea     rcx, [rbp+18h]
0x1800cd62d  call    ?DllAcquireRelease@AiddModule@Aidd@Inventory@Compat@Windows@@AEAAJW4Action@12345@@Z; Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease(Windows::Compat::Inventory::Aidd::AiddModule::Action)
0x1800cd632  jmp     short loc_1800CD639
0x1800cd634  mov     ebx, 80004005h
0x1800cd639  cmp     byte ptr [r14], 0
0x1800cd63d  jz      short loc_1800CD669
0x1800cd63f  test    dil, dil
0x1800cd642  jnz     short loc_1800CD669
0x1800cd644  mov     r8d, 2Ch ; ','
0x1800cd64a  mov     [rsp+48h+var_28], 8000FFFFh
0x1800cd652  lea     r9, aAiddtracerIsDi; "AiddTracer is disabled but testOverride"...
0x1800cd659  lea     rdx, aWindowsCompatI_66; "Windows::Compat::Inventory::Aidd::AiddT"...
0x1800cd660  lea     ecx, [r8-2Bh]
0x1800cd664  call    AslLogCallPrintf
0x1800cd669  test    ebx, ebx
0x1800cd66b  js      short loc_1800CD682
0x1800cd66d  test    dil, dil
0x1800cd670  jz      short loc_1800CD682
0x1800cd672  mov     rcx, [rbp+38h]; hEvent
0x1800cd676  call    cs:__imp_ResetEvent
0x1800cd67c  test    eax, eax
0x1800cd67e  jz      short loc_1800CD6BD
0x1800cd680  jmp     short loc_1800CD690
0x1800cd682  mov     rcx, [rbp+38h]; hEvent
0x1800cd686  call    cs:__imp_SetEvent
0x1800cd68c  test    eax, eax
0x1800cd68e  jz      short loc_1800CD6A6
0x1800cd690  mov     rbx, [rsp+48h+arg_10]
0x1800cd695  mov     al, dil
0x1800cd698  mov     rbp, [rsp+48h+arg_18]
0x1800cd69d  add     rsp, 30h
0x1800cd6a1  pop     r14
0x1800cd6a3  pop     rdi
0x1800cd6a4  pop     rsi
0x1800cd6a5  retn
0x1800cd6a6  mov     rcx, [rsp+48h]; this
0x1800cd6ab  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cd6b2  mov     edx, 0A01h; void *
0x1800cd6b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800cd6bd  mov     rcx, [rsp+48h]; this
0x1800cd6c2  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cd6c9  mov     edx, 0A06h; void *
0x1800cd6ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

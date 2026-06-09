# Windows::Compat::Inventory::Service::TraceController::Start(void)

- ea: `0x180031400`
- end: `0x18003153b`
- name: `?Start@TraceController@Service@Inventory@Compat@Windows@@QEAAJXZ`
- size: `315`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::Service::TraceController *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011720`
- `0x180030600`

## callees

- `0x180002c40`
- `0x180009060`
- `0x1800108d4`
- `0x180011334`
- `0x180031400`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003150b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003150b`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800314f7`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800314f7`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800314b7`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800314b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180031419`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180031436`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180031419`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180031436`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180031448`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180031448`

## string_xrefs

- `0x180031517`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180031529`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::Service::TraceController::Start(
        Windows::Compat::Inventory::Service::TraceController *this)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  const char *v5; // r9
  _DWORD *v6; // rdi
  _QWORD *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  int v11; // r8d
  __int64 v12; // rcx
  int v13; // [rsp+38h] [rbp-10h] BYREF
  int v14; // [rsp+3Ch] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 4);
  v3 = WaitForSingleObjectEx(v2, 0, 0);
  if ( v3 == 258 )
  {
    v6 = (_DWORD *)((char *)this + 56);
  }
  else
  {
    if ( v3 || WaitForSingleObjectEx(v2, 0, 0) )
      goto LABEL_14;
    if ( !ResetEvent(*((HANDLE *)this + 4)) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA06,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v5);
    v6 = (_DWORD *)((char *)this + 56);
    if ( !*((_DWORD *)this + 14) )
    {
LABEL_10:
      v8 = operator new(8u);
      *v8 = this;
      v9 = _o__beginthreadex(
             0,
             0,
             std::thread::_Invoke_std::tuple__lambda_22bc8609c400eaea622e89b14508690d____0_,
             v8,
             0,
             &v13);
      if ( v9 )
      {
        v10 = *((_QWORD *)this + 6);
        v11 = *((_DWORD *)this + 14);
        v12 = *((unsigned int *)this + 15);
        *((_QWORD *)this + 6) = v9;
        *((_DWORD *)this + 14) = v13;
        *((_DWORD *)this + 15) = v14;
        v13 = v11;
        v14 = v12;
        if ( !v11 )
          return 0;
        _o_terminate(v12, v10);
      }
      v13 = 0;
      std::_Throw_Cpp_error(6);
LABEL_14:
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xB07,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
    std::thread::join((Windows::Compat::Inventory::Service::TraceController *)((char *)this + 48));
  }
  if ( !*v6 )
    goto LABEL_10;
  return 0;
}

```

## disassembly

```asm
0x180031400  mov     [rsp+arg_8], rbx
0x180031405  push    rdi
0x180031406  sub     rsp, 40h
0x18003140a  mov     rbx, rcx
0x18003140d  mov     rdi, [rcx+20h]
0x180031411  xor     r8d, r8d; bAlertable
0x180031414  xor     edx, edx; dwMilliseconds
0x180031416  mov     rcx, rdi; hHandle
0x180031419  call    cs:__imp_WaitForSingleObjectEx
0x18003141f  cmp     eax, 102h
0x180031424  jz      short loc_18003146F
0x180031426  test    eax, eax
0x180031428  jnz     loc_180031512
0x18003142e  xor     r8d, r8d; bAlertable
0x180031431  xor     edx, edx; dwMilliseconds
0x180031433  mov     rcx, rdi; hHandle
0x180031436  call    cs:__imp_WaitForSingleObjectEx
0x18003143c  test    eax, eax
0x18003143e  jnz     loc_180031512
0x180031444  mov     rcx, [rbx+20h]; hEvent
0x180031448  call    cs:__imp_ResetEvent
0x18003144e  mov     rcx, [rsp+48h]; this
0x180031453  test    eax, eax
0x180031455  jz      loc_180031529
0x18003145b  lea     rdi, [rbx+38h]
0x18003145f  cmp     dword ptr [rdi], 0
0x180031462  jz      short loc_180031485
0x180031464  lea     rcx, [rbx+30h]; this
0x180031468  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x18003146d  jmp     short loc_180031473
0x18003146f  lea     rdi, [rbx+38h]
0x180031473  cmp     dword ptr [rdi], 0
0x180031476  jz      short loc_180031485
0x180031478  xor     eax, eax
0x18003147a  mov     rbx, [rsp+48h+arg_8]
0x18003147f  add     rsp, 40h
0x180031483  pop     rdi
0x180031484  retn
0x180031485  mov     ecx, 8; Size
0x18003148a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003148f  mov     [rax], rbx
0x180031492  mov     [rsp+48h+arg_0], rax
0x180031497  lea     rcx, [rsp+48h+var_10]
0x18003149c  mov     [rsp+48h+var_20], rcx
0x1800314a1  mov     [rsp+48h+var_28], 0
0x1800314a9  mov     r9, rax
0x1800314ac  lea     r8, std__thread___Invoke_std__tuple__lambda_22bc8609c400eaea622e89b14508690d____0_
0x1800314b3  xor     edx, edx
0x1800314b5  xor     ecx, ecx
0x1800314b7  call    cs:__imp__o__beginthreadex
0x1800314bd  mov     [rsp+48h+var_18], rax
0x1800314c2  test    rax, rax
0x1800314c5  jz      short loc_1800314FE
0x1800314c7  mov     rdx, [rbx+30h]
0x1800314cb  mov     r8d, [rbx+38h]
0x1800314cf  mov     ecx, [rbx+3Ch]
0x1800314d2  mov     [rbx+30h], rax
0x1800314d6  mov     eax, [rsp+48h+var_10]
0x1800314da  mov     [rbx+38h], eax
0x1800314dd  mov     eax, [rsp+48h+var_C]
0x1800314e1  mov     [rbx+3Ch], eax
0x1800314e4  mov     [rsp+48h+var_18], rdx
0x1800314e9  mov     [rsp+48h+var_10], r8d
0x1800314ee  mov     [rsp+48h+var_C], ecx
0x1800314f2  test    r8d, r8d
0x1800314f5  jz      short loc_180031478
0x1800314f7  call    cs:__imp__o_terminate
0x1800314fd  nop
0x1800314fe  mov     [rsp+48h+var_10], 0
0x180031506  mov     ecx, 6
0x18003150b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180031511  nop
0x180031512  mov     rcx, [rsp+48h]; this
0x180031517  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003151e  mov     edx, 0B07h; void *
0x180031523  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180031529  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180031530  mov     edx, 0A06h; void *
0x180031535  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

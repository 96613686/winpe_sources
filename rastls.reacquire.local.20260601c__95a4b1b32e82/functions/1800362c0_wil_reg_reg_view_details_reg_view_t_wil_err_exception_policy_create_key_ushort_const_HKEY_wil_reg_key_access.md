# wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::create_key(ushort const *,HKEY__ * *,wil::reg::key_access)

- ea: `0x1800362c0`
- end: `0x180036364`
- name: `?create_key@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBAXPEBGPEAPEAUHKEY__@@W4key_access@34@@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180067024`

## callees

- `0x1800362c0`
- `0x180036468`
- `0x18003fe64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036322`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036322`

## string_xrefs

- `0x1800362fb`: `SYSTEM\CurrentControlSet\Services\RasMan\Profiles\`
- `0x180036343`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
int __fastcall wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::create_key(
        HKEY *a1,
        __int64 a2,
        HKEY *a3)
{
  REGSAM samDesired; // eax
  int result; // eax
  bool v7; // sf
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD dwDisposition; // [rsp+78h] [rbp+20h] BYREF

  *a3 = 0;
  dwDisposition = 0;
  samDesired = wil::reg::reg_view_details::get_access_flags(1);
  result = RegCreateKeyExW(
             *a1,
             L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Profiles\\",
             0,
             0,
             0,
             samDesired,
             0,
             a3,
             &dwDisposition);
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( v7 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)result,
      dwOptions);
  return result;
}

```

## disassembly

```asm
0x1800362c0  mov     [rsp+arg_0], rbx
0x1800362c5  mov     [rsp+dwDisposition], r9d
0x1800362ca  push    rdi
0x1800362cb  sub     rsp, 50h
0x1800362cf  mov     rdi, rcx
0x1800362d2  mov     qword ptr [r8], 0
0x1800362d9  mov     ecx, 1
0x1800362de  mov     [rsp+58h+dwDisposition], 0
0x1800362e6  mov     rbx, r8
0x1800362e9  call    ?get_access_flags@reg_view_details@reg@wil@@YAKW4key_access@23@@Z; wil::reg::reg_view_details::get_access_flags(wil::reg::key_access)
0x1800362ee  lea     rcx, [rsp+58h+dwDisposition]
0x1800362f3  xor     r9d, r9d; lpClass
0x1800362f6  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x1800362fb  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180036302  mov     rcx, [rdi]; hKey
0x180036305  xor     r8d, r8d; Reserved
0x180036308  mov     [rsp+58h+phkResult], rbx; phkResult
0x18003630d  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180036316  mov     [rsp+58h+samDesired], eax; samDesired
0x18003631a  mov     [rsp+58h+dwOptions], 0; int
0x180036322  call    cs:__imp_RegCreateKeyExW
0x180036329  nop     dword ptr [rax+rax+00h]
0x18003632e  test    eax, eax
0x180036330  jle     short loc_18003633C
0x180036332  movzx   eax, ax
0x180036335  or      eax, 80070000h
0x18003633a  test    eax, eax
0x18003633c  jns     short loc_180036358
0x18003633e  mov     rcx, [rsp+58h]; this
0x180036343  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003634a  mov     r9d, eax; char *
0x18003634d  mov     edx, 1CBEh; void *
0x180036352  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180036358  mov     rbx, [rsp+58h+arg_0]
0x18003635d  add     rsp, 50h
0x180036361  pop     rdi
0x180036362  retn
```

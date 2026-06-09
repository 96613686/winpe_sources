# wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::create_key(ushort const *,HKEY__ * *,wil::reg::key_access)

- ea: `0x180025bb0`
- end: `0x180025c55`
- name: `?create_key@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBAXPEBGPEAPEAUHKEY__@@W4key_access@34@@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002346c`

## callees

- `0x180025bb0`
- `0x180025dc8`
- `0x18002661c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025c15`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025c15`

## string_xrefs

- `0x180025c30`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
int __fastcall wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::create_key(
        HKEY *a1,
        const WCHAR *a2,
        HKEY *a3)
{
  REGSAM samDesired; // eax
  int result; // eax
  bool v8; // sf
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD dwDisposition; // [rsp+78h] [rbp+20h] BYREF

  *a3 = 0;
  dwDisposition = 0;
  samDesired = wil::reg::reg_view_details::get_access_flags(1);
  result = RegCreateKeyExW(*a1, a2, 0, 0, 0, samDesired, 0, a3, &dwDisposition);
  v8 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v8 = result < 0;
  }
  if ( v8 )
    wil::details::in1diag3::Throw_Hr(
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
0x180025bb0  mov     rax, rsp
0x180025bb3  mov     [rax+8], rbx
0x180025bb7  mov     [rax+10h], rsi
0x180025bbb  mov     [rax+20h], r9d
0x180025bbf  push    rdi
0x180025bc0  sub     rsp, 50h
0x180025bc4  mov     rsi, rcx
0x180025bc7  mov     qword ptr [r8], 0
0x180025bce  mov     ecx, 1
0x180025bd3  mov     dword ptr [rax+20h], 0
0x180025bda  mov     rbx, r8
0x180025bdd  mov     rdi, rdx
0x180025be0  call    ?get_access_flags@reg_view_details@reg@wil@@YAKW4key_access@23@@Z; wil::reg::reg_view_details::get_access_flags(wil::reg::key_access)
0x180025be5  lea     rcx, [rsp+58h+dwDisposition]
0x180025bea  xor     r9d, r9d; lpClass
0x180025bed  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x180025bf2  xor     r8d, r8d; Reserved
0x180025bf5  mov     rcx, [rsi]; hKey
0x180025bf8  mov     rdx, rdi; lpSubKey
0x180025bfb  mov     [rsp+58h+phkResult], rbx; phkResult
0x180025c00  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180025c09  mov     [rsp+58h+samDesired], eax; samDesired
0x180025c0d  mov     [rsp+58h+dwOptions], 0; int
0x180025c15  call    cs:__imp_RegCreateKeyExW
0x180025c1b  test    eax, eax
0x180025c1d  jle     short loc_180025C29
0x180025c1f  movzx   eax, ax
0x180025c22  or      eax, 80070000h
0x180025c27  test    eax, eax
0x180025c29  jns     short loc_180025C45
0x180025c2b  mov     rcx, [rsp+58h]; this
0x180025c30  lea     r8, aOnecoreInterna_16; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025c37  mov     r9d, eax; char *
0x180025c3a  mov     edx, 1CBEh; void *
0x180025c3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025c45  mov     rbx, [rsp+58h+arg_0]
0x180025c4a  mov     rsi, [rsp+58h+arg_8]
0x180025c4f  add     rsp, 50h
0x180025c53  pop     rdi
0x180025c54  retn
```

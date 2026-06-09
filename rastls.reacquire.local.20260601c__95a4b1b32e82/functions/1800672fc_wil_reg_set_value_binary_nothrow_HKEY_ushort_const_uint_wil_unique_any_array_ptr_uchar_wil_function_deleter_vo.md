# wil::reg::set_value_binary_nothrow(HKEY__ *,ushort const *,uint,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> const &)

- ea: `0x1800672fc`
- end: `0x180067362`
- name: `?set_value_binary_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGIAEBV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@2@@Z`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180067370`

## callees

- `0x18002dc28`
- `0x1800672fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006731d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006731d`

## string_xrefs

- `0x180067341`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
__int64 __fastcall wil::reg::set_value_binary_nothrow(HKEY a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = RegSetKeyValueW(a1, 0, a2, 3u, *(LPCVOID *)a4, *(_DWORD *)(a4 + 8));
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
    return 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x387,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
      (const char *)v5,
      lpData);
  return v5;
}

```

## disassembly

```asm
0x1800672fc  push    rbx
0x1800672fe  sub     rsp, 30h
0x180067302  mov     eax, [r9+8]
0x180067306  mov     r8, rdx; lpValueName
0x180067309  mov     [rsp+38h+cbData], eax; cbData
0x18006730d  xor     edx, edx; lpSubKey
0x18006730f  mov     rax, [r9]
0x180067312  mov     r9d, 3; dwType
0x180067318  mov     [rsp+38h+lpData], rax; int
0x18006731d  call    cs:__imp_RegSetKeyValueW
0x180067324  nop     dword ptr [rax+rax+00h]
0x180067329  mov     ebx, eax
0x18006732b  test    eax, eax
0x18006732d  jle     short loc_180067338
0x18006732f  movzx   ebx, ax
0x180067332  or      ebx, 80070000h
0x180067338  test    ebx, ebx
0x18006733a  jns     short loc_180067357
0x18006733c  mov     rcx, [rsp+38h]; this
0x180067341  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180067348  mov     r9d, ebx; char *
0x18006734b  mov     edx, 387h; void *
0x180067350  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067355  jmp     short loc_180067359
0x180067357  xor     ebx, ebx
0x180067359  mov     eax, ebx
0x18006735b  add     rsp, 30h
0x18006735f  pop     rbx
0x180067360  retn
```

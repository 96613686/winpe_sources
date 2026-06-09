# wil::reg::set_value_binary_nothrow(HKEY__ *,ushort const *,uint,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> const &)

- ea: `0x1800638b4`
- end: `0x180063913`
- name: `?set_value_binary_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGIAEBV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@2@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180063920`

## callees

- `0x18002b7b4`
- `0x1800638b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800638d5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800638d5`

## string_xrefs

- `0x1800638f3`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

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
0x1800638b4  push    rbx
0x1800638b6  sub     rsp, 30h
0x1800638ba  mov     eax, [r9+8]
0x1800638be  mov     r8, rdx; lpValueName
0x1800638c1  mov     [rsp+38h+cbData], eax; cbData
0x1800638c5  xor     edx, edx; lpSubKey
0x1800638c7  mov     rax, [r9]
0x1800638ca  mov     r9d, 3; dwType
0x1800638d0  mov     [rsp+38h+lpData], rax; int
0x1800638d5  call    cs:__imp_RegSetKeyValueW
0x1800638db  mov     ebx, eax
0x1800638dd  test    eax, eax
0x1800638df  jle     short loc_1800638EA
0x1800638e1  movzx   ebx, ax
0x1800638e4  or      ebx, 80070000h
0x1800638ea  test    ebx, ebx
0x1800638ec  jns     short loc_180063909
0x1800638ee  mov     rcx, [rsp+38h]; this
0x1800638f3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800638fa  mov     r9d, ebx; char *
0x1800638fd  mov     edx, 387h; void *
0x180063902  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063907  jmp     short loc_18006390B
0x180063909  xor     ebx, ebx
0x18006390b  mov     eax, ebx
0x18006390d  add     rsp, 30h
0x180063911  pop     rbx
0x180063912  retn
```

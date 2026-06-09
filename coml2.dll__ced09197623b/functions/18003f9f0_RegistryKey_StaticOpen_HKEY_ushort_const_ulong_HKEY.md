# RegistryKey::StaticOpen(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18003f9f0`
- end: `0x18003fa66`
- name: `?StaticOpen@RegistryKey@@CAJPEAUHKEY__@@PEBGKPEAPEAU2@@Z`
- size: `118`
- prototype: `static int(HKEY, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800368a4`
- `0x1800369a0`

## callees

- `0x18003f9f0`
- `0x18004c820`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fa12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fa12`

## string_xrefs

- `0x18003fa40`: `onecore\internal\com\inc\combase\RegistryKey.hpp`
- `0x18003fa34`: `path:%ls`

## pseudocode

```c
__int64 __fastcall RegistryKey::StaticOpen(HKEY a1, const unsigned __int16 *a2, __int64 a3, HKEY *phkResult)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20119u, phkResult);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 != -2147024894 )
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\internal\\com\\inc\\combase\\RegistryKey.hpp",
      (const char *)v6,
      (int)"path:%ls",
      (const char *)a2);
  return v6;
}

```

## disassembly

```asm
0x18003f9f0  mov     [rsp+arg_0], rbx
0x18003f9f5  push    rdi
0x18003f9f6  sub     rsp, 30h
0x18003f9fa  mov     [rsp+38h+phkResult], r9; phkResult
0x18003f9ff  xor     r8d, r8d; ulOptions
0x18003fa02  mov     r9d, 20119h; samDesired
0x18003fa08  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003fa0f  mov     rdi, rdx
0x18003fa12  call    cs:__imp_RegOpenKeyExW
0x18003fa18  mov     ebx, eax
0x18003fa1a  test    eax, eax
0x18003fa1c  jle     short loc_18003FA27
0x18003fa1e  movzx   ebx, ax
0x18003fa21  or      ebx, 80070000h
0x18003fa27  cmp     ebx, 80070002h
0x18003fa2d  jz      short loc_18003FA59
0x18003fa2f  mov     rcx, [rsp+38h]; this
0x18003fa34  lea     rax, aPathLs; "path:%ls"
0x18003fa3b  mov     [rsp+38h+var_10], rdi; char *
0x18003fa40  lea     r8, aOnecoreInterna_3; "onecore\\internal\\com\\inc\\combase\\R"...
0x18003fa47  mov     r9d, ebx; char *
0x18003fa4a  mov     [rsp+38h+phkResult], rax; int
0x18003fa4f  mov     edx, 10Eh; void *
0x18003fa54  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003fa59  mov     eax, ebx
0x18003fa5b  mov     rbx, [rsp+38h+arg_0]
0x18003fa60  add     rsp, 30h
0x18003fa64  pop     rdi
0x18003fa65  retn
```

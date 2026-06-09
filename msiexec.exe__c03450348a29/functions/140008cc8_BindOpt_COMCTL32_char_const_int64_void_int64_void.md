# BindOpt_COMCTL32(char const *,__int64 (**)(void),__int64 (*)(void))

- ea: `0x140008cc8`
- end: `0x140008d59`
- name: `?BindOpt_COMCTL32@@YAP6A_JXZPEBDPEAP6A_JXZP6A_JXZ@Z`
- size: `145`
- prototype: `__int64 (*__fastcall(const char *, __int64 (**)(void), __int64 (*)(void)))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009340`

## callees

- `0x140008cc8`

## import_xrefs

- `KERNEL32!Sleep` at `0x140008cdf`
- `KERNEL32!Sleep` at `0x140008cdf`
- `KERNEL32!LoadLibraryW` at `0x140008d03`
- `KERNEL32!LoadLibraryW` at `0x140008d03`
- `KERNEL32!GetProcAddress` at `0x140008d2a`
- `KERNEL32!GetProcAddress` at `0x140008d2a`

## string_xrefs

- `0x140008cfc`: `COMCTL32`
- `0x140008d20`: `InitCommonControlsEx`

## pseudocode

```c
int (*__fastcall BindOpt_COMCTL32(
        const char *a1,
        __int64 (**a2)(void),
        __int64 (*a3)(void)))(struct tagINITCOMMONCONTROLSEX *)
{
  HMODULE LibraryW; // rax
  int (*result)(struct tagINITCOMMONCONTROLSEX *); // rax

  while ( _InterlockedExchange(&dword_1400111D0, 1) == 1 )
    Sleep(0xAu);
  LibraryW = hModule;
  if ( byte_1400101A3 )
  {
    if ( hModule )
      goto LABEL_8;
    LibraryW = LoadLibraryW(L"COMCTL32");
    hModule = LibraryW;
    if ( LibraryW )
      goto LABEL_8;
    byte_1400101A3 = 0;
  }
  if ( !LibraryW )
  {
LABEL_9:
    result = (int (*)(struct tagINITCOMMONCONTROLSEX *))COMCTL32::E_InitCommonControlsEx;
    COMCTL32::InitCommonControlsEx = (int (*)(struct tagINITCOMMONCONTROLSEX *))COMCTL32::E_InitCommonControlsEx;
    goto LABEL_10;
  }
LABEL_8:
  result = (int (*)(struct tagINITCOMMONCONTROLSEX *))GetProcAddress(LibraryW, "InitCommonControlsEx");
  COMCTL32::InitCommonControlsEx = result;
  if ( !result )
    goto LABEL_9;
LABEL_10:
  dword_1400111D0 = 0;
  return result;
}

```

## disassembly

```asm
0x140008cc8  sub     rsp, 28h
0x140008ccc  mov     eax, 1
0x140008cd1  xchg    eax, cs:dword_1400111D0
0x140008cd7  cmp     eax, 1
0x140008cda  jnz     short loc_140008CE7
0x140008cdc  lea     ecx, [rax+9]; dwMilliseconds
0x140008cdf  call    cs:__imp_Sleep
0x140008ce5  jmp     short loc_140008CCC
0x140008ce7  cmp     cs:byte_1400101A3, 0
0x140008cee  mov     rax, cs:hModule
0x140008cf5  jz      short loc_140008D1B
0x140008cf7  test    rax, rax
0x140008cfa  jnz     short loc_140008D20
0x140008cfc  lea     rcx, aComctl32; "COMCTL32"
0x140008d03  call    cs:__imp_LoadLibraryW
0x140008d09  mov     cs:hModule, rax
0x140008d10  test    rax, rax
0x140008d13  jnz     short loc_140008D20
0x140008d15  mov     cs:byte_1400101A3, al
0x140008d1b  test    rax, rax
0x140008d1e  jz      short loc_140008D3C
0x140008d20  lea     rdx, aInitcommoncont_0; "InitCommonControlsEx"
0x140008d27  mov     rcx, rax; hModule
0x140008d2a  call    cs:__imp_GetProcAddress
0x140008d30  mov     cs:?InitCommonControlsEx@COMCTL32@@3P6AHPEAUtagINITCOMMONCONTROLSEX@@@ZEA, rax; int (*COMCTL32::InitCommonControlsEx)(tagINITCOMMONCONTROLSEX *)
0x140008d37  test    rax, rax
0x140008d3a  jnz     short loc_140008D4A
0x140008d3c  lea     rax, COMCTL32__E_InitCommonControlsEx
0x140008d43  mov     cs:?InitCommonControlsEx@COMCTL32@@3P6AHPEAUtagINITCOMMONCONTROLSEX@@@ZEA, rax; int (*COMCTL32::InitCommonControlsEx)(tagINITCOMMONCONTROLSEX *)
0x140008d4a  mov     cs:dword_1400111D0, 0
0x140008d54  add     rsp, 28h
0x140008d58  retn
```

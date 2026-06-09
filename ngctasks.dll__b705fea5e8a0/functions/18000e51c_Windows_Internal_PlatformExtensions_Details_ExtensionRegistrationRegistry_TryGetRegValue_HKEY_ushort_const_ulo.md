# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)

- ea: `0x18000e51c`
- end: `0x18000e576`
- name: `?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z`
- size: `90`
- prototype: `static int(HKEY, const unsigned __int16 *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b164`

## callees

- `0x18000cc58`
- `0x18000e51c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e540`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e540`

## string_xrefs

- `0x18000e55a`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
        HKEY a1,
        const unsigned __int16 *a2,
        DWORD a3,
        void *pvData,
        unsigned int *pcbData)
{
  unsigned int ValueW; // eax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  ValueW = RegGetValueW(a1, 0, a2, a3, 0, pvData, pcbData);
  v6 = 0;
  if ( ValueW != 2 )
    v6 = (const char *)ValueW;
  if ( (_DWORD)v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x118,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
             v6,
             (unsigned int)pcbData);
  else
    return 0;
}

```

## disassembly

```asm
0x18000e51c  sub     rsp, 48h
0x18000e520  mov     rax, [rsp+48h+arg_20]
0x18000e525  mov     [rsp+48h+pcbData], rax; pcbData
0x18000e52a  mov     [rsp+48h+pvData], r9; pvData
0x18000e52f  mov     r9d, r8d; dwFlags
0x18000e532  mov     r8, rdx; lpValue
0x18000e535  mov     [rsp+48h+pdwType], 0; pdwType
0x18000e53e  xor     edx, edx; lpSubKey
0x18000e540  call    cs:__imp_RegGetValueW
0x18000e546  xor     r9d, r9d
0x18000e549  cmp     eax, 2
0x18000e54c  cmovnz  r9d, eax; char *
0x18000e550  test    r9d, r9d
0x18000e553  jz      short loc_18000E56F
0x18000e555  mov     rcx, [rsp+48h]; this
0x18000e55a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000e561  mov     edx, 118h; void *
0x18000e566  add     rsp, 48h
0x18000e56a  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000e56f  xor     eax, eax
0x18000e571  add     rsp, 48h
0x18000e575  retn
```

# ComputeService::MachineLocalSettingsStore::QueryValueImpl(ushort const *,ulong,uchar *,ulong *)

- ea: `0x18002b2bc`
- end: `0x18002b32f`
- name: `?QueryValueImpl@MachineLocalSettingsStore@ComputeService@@AEBA_NPEBGKPEAEPEAK@Z`
- size: `115`
- prototype: `bool(ComputeService::MachineLocalSettingsStore *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002aec0`
- `0x18002aef0`
- `0x18002af40`
- `0x18002b030`
- `0x18002b270`

## callees

- `0x180012818`
- `0x18002b2bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b2e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b2e6`

## string_xrefs

- `0x18002b31a`: `onecore\vm\compute\management\shared\compute\machinelocalsettingsstore.cpp`

## pseudocode

```c
char __fastcall ComputeService::MachineLocalSettingsStore::QueryValueImpl(
        HKEY *this,
        const unsigned __int16 *a2,
        DWORD a3,
        unsigned __int8 *pvData,
        unsigned int *pcbData)
{
  unsigned int ValueW; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  ValueW = RegGetValueW(this[1], 0, a2, a3, 0, pvData, pcbData);
  switch ( ValueW )
  {
    case 0u:
      return 1;
    case 2u:
      *pcbData = 0;
      break;
    case 0xEAu:
      break;
    default:
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1B3,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\machinelocalsettingsstore.cpp",
        (const char *)ValueW,
        pdwType);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b2bc  push    rbx
0x18002b2be  sub     rsp, 40h
0x18002b2c2  mov     rbx, [rsp+48h+arg_20]
0x18002b2c7  mov     rcx, [rcx+8]; hkey
0x18002b2cb  mov     [rsp+48h+pcbData], rbx; pcbData
0x18002b2d0  mov     [rsp+48h+pvData], r9; pvData
0x18002b2d5  mov     r9d, r8d; dwFlags
0x18002b2d8  mov     r8, rdx; lpValue
0x18002b2db  mov     [rsp+48h+pdwType], 0; unsigned int
0x18002b2e4  xor     edx, edx; lpSubKey
0x18002b2e6  call    cs:__imp_RegGetValueW
0x18002b2ed  nop     dword ptr [rax+rax+00h]
0x18002b2f2  test    eax, eax
0x18002b2f4  jnz     short loc_18002B2FF
0x18002b2f6  mov     al, 1
0x18002b2f8  add     rsp, 40h
0x18002b2fc  pop     rbx
0x18002b2fd  retn
0x18002b2ff  cmp     eax, 2
0x18002b302  jnz     short loc_18002B30E
0x18002b304  mov     dword ptr [rbx], 0
0x18002b30a  xor     al, al
0x18002b30c  jmp     short loc_18002B2F8
0x18002b30e  cmp     eax, 0EAh
0x18002b313  jz      short loc_18002B30A
0x18002b315  mov     rcx, [rsp+48h]; this
0x18002b31a  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\management\\share"...
0x18002b321  mov     r9d, eax; char *
0x18002b324  mov     edx, 1B3h; void *
0x18002b329  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```

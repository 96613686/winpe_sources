# GetCryptoProvider(HKEY__ *,bool,ushort *,ulong)

- ea: `0x180036bec`
- end: `0x180036c3e`
- name: `?GetCryptoProvider@@YAJPEAUHKEY__@@_NPEAGK@Z`
- size: `82`
- prototype: `__int64 __fastcall(HKEY, bool, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038cf4`

## callees

- `0x180036bec`
- `0x180044e94`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetString` at `0x180036c1d`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180036c1d`

## pseudocode

```c
__int64 __fastcall GetCryptoProvider(HKEY a1, __int64 a2, unsigned __int16 *a3)
{
  int String; // ecx
  __int64 result; // rax

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  String = OmaDmRegistryGetString(a1, 0, L"CurCryptoProvider", a3, 0x100u);
  result = 0;
  if ( String >= 0 )
    return (unsigned int)String;
  return result;
}

```

## disassembly

```asm
0x180036bec  mov     [rsp+arg_0], rbx
0x180036bf1  push    rdi
0x180036bf2  sub     rsp, 30h
0x180036bf6  mov     rbx, r8
0x180036bf9  mov     rdi, rcx
0x180036bfc  test    r8, r8
0x180036bff  jnz     short loc_180036C06
0x180036c01  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "nullptr != cryptoProvider")
0x180036c06  mov     r9, rbx
0x180036c09  mov     [rsp+38h+var_18], 100h
0x180036c11  lea     r8, aCurcryptoprovi; "CurCryptoProvider"
0x180036c18  xor     edx, edx
0x180036c1a  mov     rcx, rdi
0x180036c1d  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180036c24  nop     dword ptr [rax+rax+00h]
0x180036c29  mov     rbx, [rsp+38h+arg_0]
0x180036c2e  mov     ecx, eax
0x180036c30  xor     eax, eax
0x180036c32  test    ecx, ecx
0x180036c34  cmovns  eax, ecx
0x180036c37  add     rsp, 30h
0x180036c3b  pop     rdi
0x180036c3c  retn
```

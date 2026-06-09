# SupplicantGetAuthRestartReasonDescription

- ea: `0x18001d180`
- end: `0x18001d201`
- name: `SupplicantGetAuthRestartReasonDescription`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012660`

## callees

- `0x18001d180`

## string_xrefs

- `0x18001d1d2`: `ConfigurationChanged`

## pseudocode

```c
const wchar_t *__fastcall SupplicantGetAuthRestartReasonDescription(int a1)
{
  __int64 v1; // rdx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx

  v1 = 0;
  if ( !a1 )
    return L"PeerInitiated";
  v2 = a1 - 1;
  if ( !v2 )
    return L"MsmInitiated";
  v3 = v2 - 1;
  if ( !v3 )
    return L"HeldStateTimeout";
  v4 = v3 - 1;
  if ( !v4 )
    return L"AuthTimeout";
  v5 = v4 - 1;
  if ( !v5 )
    return L"ConfigurationChanged";
  v6 = v5 - 1;
  if ( !v6 )
    return L"UserChanged";
  v7 = v6 - 1;
  if ( !v7 )
    return L"QuarantineStateChanged";
  v8 = v7 - 1;
  if ( !v8 )
    return L"Alternate credentials trial";
  if ( v8 == 1 )
    return L"Invalid";
  return (const wchar_t *)v1;
}

```

## disassembly

```asm
0x18001d180  xor     edx, edx
0x18001d182  test    ecx, ecx
0x18001d184  jz      short loc_18001D1F6
0x18001d186  sub     ecx, 1
0x18001d189  jz      short loc_18001D1ED
0x18001d18b  sub     ecx, 1
0x18001d18e  jz      short loc_18001D1E4
0x18001d190  sub     ecx, 1
0x18001d193  jz      short loc_18001D1DB
0x18001d195  sub     ecx, 1
0x18001d198  jz      short loc_18001D1D2
0x18001d19a  sub     ecx, 1
0x18001d19d  jz      short loc_18001D1C9
0x18001d19f  sub     ecx, 1
0x18001d1a2  jz      short loc_18001D1C0
0x18001d1a4  sub     ecx, 1
0x18001d1a7  jz      short loc_18001D1B7
0x18001d1a9  cmp     ecx, 1
0x18001d1ac  jnz     short loc_18001D1FD
0x18001d1ae  lea     rdx, aInvalid; "Invalid"
0x18001d1b5  jmp     short loc_18001D1FD
0x18001d1b7  lea     rdx, aAlternateCrede; "Alternate credentials trial"
0x18001d1be  jmp     short loc_18001D1FD
0x18001d1c0  lea     rdx, aQuarantinestat; "QuarantineStateChanged"
0x18001d1c7  jmp     short loc_18001D1FD
0x18001d1c9  lea     rdx, aUserchanged; "UserChanged"
0x18001d1d0  jmp     short loc_18001D1FD
0x18001d1d2  lea     rdx, aConfigurationc; "ConfigurationChanged"
0x18001d1d9  jmp     short loc_18001D1FD
0x18001d1db  lea     rdx, aAuthtimeout; "AuthTimeout"
0x18001d1e2  jmp     short loc_18001D1FD
0x18001d1e4  lea     rdx, aHeldstatetimeo; "HeldStateTimeout"
0x18001d1eb  jmp     short loc_18001D1FD
0x18001d1ed  lea     rdx, aMsminitiated; "MsmInitiated"
0x18001d1f4  jmp     short loc_18001D1FD
0x18001d1f6  lea     rdx, aPeerinitiated; "PeerInitiated"
0x18001d1fd  mov     rax, rdx
0x18001d200  retn
```

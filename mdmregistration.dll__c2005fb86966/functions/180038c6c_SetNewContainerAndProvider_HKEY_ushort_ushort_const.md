# SetNewContainerAndProvider(HKEY__ *,ushort *,ushort const *)

- ea: `0x180038c6c`
- end: `0x180038cee`
- name: `?SetNewContainerAndProvider@@YAJPEAUHKEY__@@PEAGPEBG@Z`
- size: `130`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180034b80`
- `0x180037f5c`

## callees

- `0x180038c6c`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180038c88`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180038cbc`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180038c88`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180038cbc`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x180038c9b`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x180038ccd`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x180038c9b`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x180038ccd`

## pseudocode

```c
int __fastcall SetNewContainerAndProvider(HKEY a1, unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int result; // eax
  int v6; // eax
  int v7; // ecx

  if ( a2 )
    result = OmaDmRegistrySetString(a1, 0, L"NewKeyContainer", a2);
  else
    result = OmaDmRegistryDeleteValue(a1, 0, L"NewKeyContainer");
  if ( result >= 0 )
  {
    if ( a3 )
      v6 = OmaDmRegistrySetString(a1, 0, L"NewCryptoProvider", a3);
    else
      v6 = OmaDmRegistryDeleteValue(a1, 0, L"NewCryptoProvider");
    v7 = v6;
    result = 0;
    if ( v7 < 0 )
      return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180038c6c  mov     [rsp+arg_0], rbx
0x180038c71  push    rdi
0x180038c72  sub     rsp, 20h
0x180038c76  mov     rdi, r8
0x180038c79  lea     r8, aNewkeycontaine; "NewKeyContainer"
0x180038c80  mov     rbx, rcx
0x180038c83  test    rdx, rdx
0x180038c86  jnz     short loc_180038C96
0x180038c88  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x180038c8f  nop     dword ptr [rax+rax+00h]
0x180038c94  jmp     short loc_180038CA7
0x180038c96  mov     r9, rdx
0x180038c99  xor     edx, edx
0x180038c9b  call    cs:__imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180038ca2  nop     dword ptr [rax+rax+00h]
0x180038ca7  test    eax, eax
0x180038ca9  js      short loc_180038CE2
0x180038cab  xor     edx, edx
0x180038cad  lea     r8, aNewcryptoprovi; "NewCryptoProvider"
0x180038cb4  mov     rcx, rbx
0x180038cb7  test    rdi, rdi
0x180038cba  jnz     short loc_180038CCA
0x180038cbc  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x180038cc3  nop     dword ptr [rax+rax+00h]
0x180038cc8  jmp     short loc_180038CD9
0x180038cca  mov     r9, rdi
0x180038ccd  call    cs:__imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180038cd4  nop     dword ptr [rax+rax+00h]
0x180038cd9  mov     ecx, eax
0x180038cdb  xor     eax, eax
0x180038cdd  test    ecx, ecx
0x180038cdf  cmovs   eax, ecx
0x180038ce2  mov     rbx, [rsp+28h+arg_0]
0x180038ce7  add     rsp, 20h
0x180038ceb  pop     rdi
0x180038cec  retn
```

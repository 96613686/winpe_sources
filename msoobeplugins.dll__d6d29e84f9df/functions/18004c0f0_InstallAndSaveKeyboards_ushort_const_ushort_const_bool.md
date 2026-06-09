# InstallAndSaveKeyboards(ushort const *,ushort const *,bool)

- ea: `0x18004c0f0`
- end: `0x18004c1bc`
- name: `?InstallAndSaveKeyboards@@YAXPEBG0_N@Z`
- size: `204`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18004c1d0`
- `0x18004c3b0`
- `0x18004c55c`
- `0x18005b3b0`

## callees

- `0x18004c0f0`
- `0x1800b8834`

## import_xrefs

- `Input!__imp_InstallLayoutOrTip` at `0x18004c10e`
- `Input!__imp_InstallLayoutOrTip` at `0x18004c138`
- `Input!__imp_InstallLayoutOrTip` at `0x18004c10e`
- `Input!__imp_InstallLayoutOrTip` at `0x18004c138`
- `Input!__imp_SaveDefaultUserInputSettings` at `0x18004c17c`
- `Input!__imp_SaveDefaultUserInputSettings` at `0x18004c17c`
- `Input!__imp_SaveSystemAcctInputSettings` at `0x18004c199`
- `Input!__imp_SaveSystemAcctInputSettings` at `0x18004c199`
- `Input!__imp_SetDefaultLayoutOrTip` at `0x18004c158`
- `Input!__imp_SetDefaultLayoutOrTip` at `0x18004c158`

## string_xrefs

- `0x18004c142`: `Failed to install default keyboard layout`
- `0x18004c118`: `Failed to install keyboard layouts`
- `0x18004c162`: `Failed to set default keyboard layout into registry`

## pseudocode

```c
void __fastcall InstallAndSaveKeyboards(const unsigned __int16 *a1, const unsigned __int16 *a2, char a3)
{
  unsigned __int8 v4; // bl

  v4 = a3 ^ 1;
  if ( a1 )
  {
    if ( (unsigned int)InstallLayoutOrTip(a1, v4 << 6) )
      v4 = 0;
    else
      UnattendLogW(0, L"Failed to install keyboard layouts");
  }
  if ( a2 )
  {
    if ( !(unsigned int)InstallLayoutOrTip(a2, v4 << 6) )
      UnattendLogW(0, L"Failed to install default keyboard layout");
    if ( !(unsigned int)SetDefaultLayoutOrTip(a2, 1) )
      UnattendLogW(0, L"Failed to set default keyboard layout into registry");
  }
  if ( !(unsigned int)SaveDefaultUserInputSettings(0, -2147483647) )
    UnattendLogW(0, L"Failed to save default user input settings");
  if ( !(unsigned int)SaveSystemAcctInputSettings(0, -2147483647) )
    UnattendLogW(0, L"Failed to save system account input settings");
}

```

## disassembly

```asm
0x18004c0f0  mov     [rsp+arg_0], rbx
0x18004c0f5  push    rdi
0x18004c0f6  sub     rsp, 20h
0x18004c0fa  mov     bl, r8b
0x18004c0fd  mov     rdi, rdx
0x18004c100  xor     bl, 1
0x18004c103  test    rcx, rcx
0x18004c106  jz      short loc_18004C12A
0x18004c108  movzx   edx, bl
0x18004c10b  shl     edx, 6
0x18004c10e  call    cs:__imp_InstallLayoutOrTip
0x18004c114  test    eax, eax
0x18004c116  jnz     short loc_18004C128
0x18004c118  lea     rdx, aFailedToInstal_3; "Failed to install keyboard layouts"
0x18004c11f  xor     ecx, ecx
0x18004c121  call    UnattendLogW
0x18004c126  jmp     short loc_18004C12A
0x18004c128  xor     bl, bl
0x18004c12a  test    rdi, rdi
0x18004c12d  jz      short loc_18004C170
0x18004c12f  movzx   edx, bl
0x18004c132  mov     rcx, rdi
0x18004c135  shl     edx, 6
0x18004c138  call    cs:__imp_InstallLayoutOrTip
0x18004c13e  test    eax, eax
0x18004c140  jnz     short loc_18004C150
0x18004c142  lea     rdx, aFailedToInstal; "Failed to install default keyboard layo"...
0x18004c149  xor     ecx, ecx
0x18004c14b  call    UnattendLogW
0x18004c150  mov     edx, 1
0x18004c155  mov     rcx, rdi
0x18004c158  call    cs:__imp_SetDefaultLayoutOrTip
0x18004c15e  test    eax, eax
0x18004c160  jnz     short loc_18004C170
0x18004c162  lea     rdx, aFailedToSetDef; "Failed to set default keyboard layout i"...
0x18004c169  xor     ecx, ecx
0x18004c16b  call    UnattendLogW
0x18004c170  mov     rbx, 0FFFFFFFF80000001h
0x18004c177  xor     ecx, ecx
0x18004c179  mov     rdx, rbx
0x18004c17c  call    cs:__imp_SaveDefaultUserInputSettings
0x18004c182  test    eax, eax
0x18004c184  jnz     short loc_18004C194
0x18004c186  lea     rdx, aFailedToSaveDe; "Failed to save default user input setti"...
0x18004c18d  xor     ecx, ecx
0x18004c18f  call    UnattendLogW
0x18004c194  mov     rdx, rbx
0x18004c197  xor     ecx, ecx
0x18004c199  call    cs:__imp_SaveSystemAcctInputSettings
0x18004c19f  test    eax, eax
0x18004c1a1  jnz     short loc_18004C1B1
0x18004c1a3  lea     rdx, aFailedToSaveSy; "Failed to save system account input set"...
0x18004c1aa  xor     ecx, ecx
0x18004c1ac  call    UnattendLogW
0x18004c1b1  mov     rbx, [rsp+28h+arg_0]
0x18004c1b6  add     rsp, 20h
0x18004c1ba  pop     rdi
0x18004c1bb  retn
```

# MoveLogonPreferences

- ea: `0x180009918`
- end: `0x180009a27`
- name: `MoveLogonPreferences`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009368`

## callees

- `0x18000929c`
- `0x180009464`
- `0x180009918`
- `0x180009a30`
- `0x18000a0c4`
- `0x18000b0ce`

## import_xrefs

- `KERNEL32!RegCloseKey` at `0x1800099a6`
- `KERNEL32!RegCloseKey` at `0x180009a10`
- `KERNEL32!RegCloseKey` at `0x1800099a6`
- `KERNEL32!RegCloseKey` at `0x180009a10`
- `KERNEL32!RegOpenKeyExW` at `0x18000996d`
- `KERNEL32!RegOpenKeyExW` at `0x180009998`
- `KERNEL32!RegOpenKeyExW` at `0x18000996d`
- `KERNEL32!RegOpenKeyExW` at `0x180009998`
- `rtutils!TracePrintfExA` at `0x180009a06`
- `rtutils!TracePrintfExA` at `0x180009a06`

## string_xrefs

- `0x1800099fa`: `MoveLogonPreferences=%d`

## pseudocode

```c
LSTATUS MoveLogonPreferences()
{
  LSTATUS result; // eax
  int UserPreferences; // ebx
  _BYTE v2[192]; // [rsp+30h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+100h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+108h] [rbp+6Fh] BYREF

  phkResult = 0;
  hKey = 0;
  memset_0(v2, 0, 0xB8u);
  result = RegOpenKeyExW(HKEY_USERS, L".DEFAULT\\Software\\Microsoft\\RAS Phonebook", 0, 0x20019u, &phkResult);
  if ( !result )
  {
    if ( RegOpenKeyExW(HKEY_USERS, L".DEFAULT\\Software\\Microsoft\\RAS Logon Phonebook", 0, 0x20019u, &hKey) )
    {
      UserPreferences = SetDefaultUserPreferences(v2);
      if ( !UserPreferences )
      {
        UserPreferences = ReadUserPreferences(phkResult, v2);
        if ( !UserPreferences )
          UserPreferences = DwSetUserPreferences(v2, 1);
      }
      DestroyUserPreferences(v2);
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "MoveLogonPreferences=%d", UserPreferences);
    }
    else
    {
      RegCloseKey(hKey);
    }
    return RegCloseKey(phkResult);
  }
  return result;
}

```

## disassembly

```asm
0x180009918  mov     [rsp-8+arg_10], rbx
0x18000991d  push    rbp
0x18000991e  lea     rbp, [rsp-57h]
0x180009923  sub     rsp, 0F0h
0x18000992a  xor     edx, edx; Val
0x18000992c  mov     [rbp+57h+arg_0], 0
0x180009934  mov     r8d, 0B8h; Size
0x18000993a  mov     [rbp+57h+hKey], 0
0x180009942  lea     rcx, [rbp+57h+var_C0]; void *
0x180009946  call    memset_0
0x18000994b  lea     rax, [rbp+57h+arg_0]
0x18000994f  mov     ebx, 20019h
0x180009954  mov     r9d, ebx; samDesired
0x180009957  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18000995c  xor     r8d, r8d; ulOptions
0x18000995f  lea     rdx, aDefaultSoftwar_0; ".DEFAULT\\Software\\Microsoft\\RAS Phon"...
0x180009966  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000996d  call    cs:__imp_RegOpenKeyExW
0x180009973  test    eax, eax
0x180009975  jnz     loc_180009A16
0x18000997b  lea     rax, [rbp+57h+hKey]
0x18000997f  mov     r9d, ebx; samDesired
0x180009982  xor     r8d, r8d; ulOptions
0x180009985  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18000998a  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x180009991  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180009998  call    cs:__imp_RegOpenKeyExW
0x18000999e  test    eax, eax
0x1800099a0  jnz     short loc_1800099AE
0x1800099a2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800099a6  call    cs:__imp_RegCloseKey
0x1800099ac  jmp     short loc_180009A0C
0x1800099ae  mov     edx, 1
0x1800099b3  lea     rcx, [rbp+57h+var_C0]; void *
0x1800099b7  call    SetDefaultUserPreferences
0x1800099bc  mov     ebx, eax
0x1800099be  test    eax, eax
0x1800099c0  jnz     short loc_1800099E3
0x1800099c2  mov     rcx, [rbp+57h+arg_0]; hKey
0x1800099c6  lea     rdx, [rbp+57h+var_C0]; void *
0x1800099ca  call    ReadUserPreferences
0x1800099cf  mov     ebx, eax
0x1800099d1  test    eax, eax
0x1800099d3  jnz     short loc_1800099E3
0x1800099d5  lea     edx, [rax+1]
0x1800099d8  lea     rcx, [rbp+57h+var_C0]
0x1800099dc  call    DwSetUserPreferences
0x1800099e1  mov     ebx, eax
0x1800099e3  lea     rcx, [rbp+57h+var_C0]; void *
0x1800099e7  call    DestroyUserPreferences
0x1800099ec  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800099f2  cmp     ecx, 0FFFFFFFFh
0x1800099f5  jz      short loc_180009A0C
0x1800099f7  mov     r9d, ebx
0x1800099fa  lea     r8, aMovelogonprefe; "MoveLogonPreferences=%d"
0x180009a01  mov     edx, 0Ch; dwFlags
0x180009a06  call    cs:__imp_TracePrintfExA
0x180009a0c  mov     rcx, [rbp+57h+arg_0]; hKey
0x180009a10  call    cs:__imp_RegCloseKey
0x180009a16  mov     rbx, [rsp+0F0h+arg_10]
0x180009a1e  add     rsp, 0F0h
0x180009a25  pop     rbp
0x180009a26  retn
```

# IntlCopyDefaultUserLocale(ulong)

- ea: `0x180022100`
- end: `0x18002217a`
- name: `?IntlCopyDefaultUserLocale@@YAKK@Z`
- size: `122`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180012f38`
- `0x1800130b4`
- `0x180022100`
- `0x1800261f0`
- `0x180026234`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022129`

## pseudocode

```c
__int64 __fastcall IntlCopyDefaultUserLocale(int a1)
{
  int v2; // ebx
  DWORD LastError; // ebx
  unsigned int v4; // edi

  if ( (a1 & 0xFFFFFFFE) != 0 )
    return 87;
  v2 = a1 & 1;
  if ( (a1 & 1) == 0 || (unsigned int)Input_LoadAndInitFunctions() )
  {
    v4 = Intl_SaveDefaultUserSettings(HKEY_CURRENT_USER, 0, v2);
    if ( !v4 )
      v4 = Intl_SaveSystemAcctSettings(HKEY_CURRENT_USER, 0, v2);
    if ( v2 )
      Input_Unload();
    return v4;
  }
  else
  {
    LastError = GetLastError();
    Input_Unload();
    return LastError;
  }
}

```

## disassembly

```asm
0x180022100  mov     [rsp+arg_0], rbx
0x180022105  push    rdi
0x180022106  sub     rsp, 20h
0x18002210a  mov     ebx, ecx
0x18002210c  test    ecx, 0FFFFFFFEh
0x180022112  jz      short loc_18002211B
0x180022114  mov     eax, 57h ; 'W'
0x180022119  jmp     short loc_18002216F
0x18002211b  and     ebx, 1
0x18002211e  jz      short loc_18002213A
0x180022120  call    ?Input_LoadAndInitFunctions@@YAHXZ; Input_LoadAndInitFunctions(void)
0x180022125  test    eax, eax
0x180022127  jnz     short loc_18002213A
0x180022129  call    cs:__imp_GetLastError
0x18002212f  mov     ebx, eax
0x180022131  call    ?Input_Unload@@YAXXZ; Input_Unload(void)
0x180022136  mov     eax, ebx
0x180022138  jmp     short loc_18002216F
0x18002213a  mov     r8d, ebx; int
0x18002213d  xor     edx, edx; HWND
0x18002213f  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180022146  call    ?Intl_SaveDefaultUserSettings@@YAKPEAUHKEY__@@PEAUHWND__@@H@Z; Intl_SaveDefaultUserSettings(HKEY__ *,HWND__ *,int)
0x18002214b  mov     edi, eax
0x18002214d  test    eax, eax
0x18002214f  jnz     short loc_180022164
0x180022151  mov     r8d, ebx; int
0x180022154  xor     edx, edx; HWND
0x180022156  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18002215d  call    ?Intl_SaveSystemAcctSettings@@YAKPEAUHKEY__@@PEAUHWND__@@H@Z; Intl_SaveSystemAcctSettings(HKEY__ *,HWND__ *,int)
0x180022162  mov     edi, eax
0x180022164  test    ebx, ebx
0x180022166  jz      short loc_18002216D
0x180022168  call    ?Input_Unload@@YAXXZ; Input_Unload(void)
0x18002216d  mov     eax, edi
0x18002216f  mov     rbx, [rsp+28h+arg_0]
0x180022174  add     rsp, 20h
0x180022178  pop     rdi
0x180022179  retn
```

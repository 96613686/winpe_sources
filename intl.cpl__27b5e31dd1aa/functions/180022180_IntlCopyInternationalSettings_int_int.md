# IntlCopyInternationalSettings(int,int)

- ea: `0x180022180`
- end: `0x180022226`
- name: `?IntlCopyInternationalSettings@@YAKHH@Z`
- size: `166`
- prototype: `unsigned int __fastcall(int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180012f38`
- `0x1800130b4`
- `0x180022180`
- `0x1800261f0`
- `0x180026234`
- `0x180026304`
- `0x180026994`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall IntlCopyInternationalSettings(int a1, int a2)
{
  int v5; // edi
  unsigned int v6; // ebx

  if ( !a1 && !a2 )
    return 87;
  if ( !(unsigned int)Input_LoadAndInitFunctions() )
  {
    Input_Unload();
    return GetLastError();
  }
  if ( a1 )
  {
    v5 = Intl_SaveSystemAcctSettings(HKEY_CURRENT_USER, 0, 1);
    if ( v5 )
    {
      Input_Unload();
      return v5;
    }
    Intl_SetUILanguageForSystemAccts(HKEY_CURRENT_USER, 0);
  }
  if ( !a2 )
    goto LABEL_13;
  v6 = Intl_SaveDefaultUserSettings(HKEY_CURRENT_USER, 0, 1);
  if ( !v6 )
  {
    Intl_SaveUISettingsToNtUserFile(HKEY_CURRENT_USER);
LABEL_13:
    v6 = 0;
  }
  Input_Unload();
  return v6;
}

```

## disassembly

```asm
0x180022180  mov     [rsp+arg_8], rbx
0x180022185  mov     [rsp+arg_10], rsi
0x18002218a  push    rdi
0x18002218b  sub     rsp, 20h
0x18002218f  mov     ebx, edx
0x180022191  mov     edi, ecx
0x180022193  test    ecx, ecx
0x180022195  jnz     short loc_1800221A0
0x180022197  test    edx, edx
0x180022199  jnz     short loc_1800221A0
0x18002219b  lea     eax, [rdx+57h]
0x18002219e  jmp     short loc_180022216
0x1800221a0  call    ?Input_LoadAndInitFunctions@@YAHXZ; Input_LoadAndInitFunctions(void)
0x1800221a5  test    eax, eax
0x1800221a7  jnz     short loc_1800221B6
0x1800221a9  call    ?Input_Unload@@YAXXZ; Input_Unload(void)
0x1800221ae  call    cs:__imp_GetLastError
0x1800221b4  jmp     short loc_180022216
0x1800221b6  mov     [rsp+28h+arg_1], 1
0x1800221bb  mov     rsi, 0FFFFFFFF80000001h
0x1800221c2  test    edi, edi
0x1800221c4  jz      short loc_1800221ED
0x1800221c6  xor     edx, edx; HWND
0x1800221c8  lea     r8d, [rdx+1]; int
0x1800221cc  mov     rcx, rsi; HKEY
0x1800221cf  call    ?Intl_SaveSystemAcctSettings@@YAKPEAUHKEY__@@PEAUHWND__@@H@Z; Intl_SaveSystemAcctSettings(HKEY__ *,HWND__ *,int)
0x1800221d4  mov     edi, eax
0x1800221d6  test    eax, eax
0x1800221d8  jz      short loc_1800221E3
0x1800221da  call    ?Input_Unload@@YAXXZ; Input_Unload(void)
0x1800221df  mov     eax, edi
0x1800221e1  jmp     short loc_180022216
0x1800221e3  xor     edx, edx; unsigned int *
0x1800221e5  mov     rcx, rsi; hKey
0x1800221e8  call    ?Intl_SetUILanguageForSystemAccts@@YAXPEAUHKEY__@@PEAK@Z; Intl_SetUILanguageForSystemAccts(HKEY__ *,ulong *)
0x1800221ed  test    ebx, ebx
0x1800221ef  jz      short loc_18002220D
0x1800221f1  xor     edx, edx; HWND
0x1800221f3  lea     r8d, [rdx+1]; int
0x1800221f7  mov     rcx, rsi; HKEY
0x1800221fa  call    ?Intl_SaveDefaultUserSettings@@YAKPEAUHKEY__@@PEAUHWND__@@H@Z; Intl_SaveDefaultUserSettings(HKEY__ *,HWND__ *,int)
0x1800221ff  mov     ebx, eax
0x180022201  test    eax, eax
0x180022203  jnz     short loc_18002220F
0x180022205  mov     rcx, rsi; hKey
0x180022208  call    ?Intl_SaveUISettingsToNtUserFile@@YAXPEAUHKEY__@@@Z; Intl_SaveUISettingsToNtUserFile(HKEY__ *)
0x18002220d  xor     ebx, ebx
0x18002220f  call    ?Input_Unload@@YAXXZ; Input_Unload(void)
0x180022214  mov     eax, ebx
0x180022216  mov     rbx, [rsp+28h+arg_8]
0x18002221b  mov     rsi, [rsp+28h+arg_10]
0x180022220  add     rsp, 20h
0x180022224  pop     rdi
0x180022225  retn
```

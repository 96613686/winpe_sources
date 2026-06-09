# CCPlaySound

- ea: `0x1800181a0`
- end: `0x180018308`
- name: `CCPlaySound`
- size: `360`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003ef24`
- `0x1800530b4`
- `0x180056f4c`
- `0x18005736c`

## callees

- `0x1800115f0`
- `0x1800181a0`
- `0x18001ac40`
- `0x180090020`

## import_xrefs

- `ADVAPI32!RegQueryValueW` at `0x180018276`
- `ADVAPI32!RegQueryValueW` at `0x180018276`
- `KERNEL32!LoadLibraryW` at `0x1800182a4`
- `KERNEL32!LoadLibraryW` at `0x1800182a4`
- `KERNEL32!GetProcAddress` at `0x1800182b9`
- `KERNEL32!GetProcAddress` at `0x1800182b9`
- `KERNEL32!GetModuleHandleW` at `0x180018292`
- `KERNEL32!GetModuleHandleW` at `0x180018292`
- `KERNEL32!lstrlenW` at `0x18001822c`
- `KERNEL32!lstrlenW` at `0x180018239`
- `KERNEL32!lstrlenW` at `0x18001822c`
- `KERNEL32!lstrlenW` at `0x180018239`

## string_xrefs

- `0x18001828b`: `winmm.dll`
- `0x18001829d`: `winmm.dll`

## pseudocode

```c
void __fastcall CCPlaySound(const WCHAR *a1)
{
  int v2; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  LONG cbData[4]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR String[48]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Data[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  if ( !g_fNeverPlaySound )
  {
    wcscpy(String, L"AppEvents\\Schemes\\Apps\\.Default\\%s\\.current");
    cbData[0] = 520;
    v2 = lstrlenW(a1);
    if ( (unsigned int)(lstrlenW(String) + v2) < 0x104 )
    {
      StringCchPrintfW(SubKey, 0x104u, String, a1);
      if ( !RegQueryValueW(HKEY_CURRENT_USER, SubKey, Data, cbData) && (unsigned __int64)cbData[0] > 2 )
      {
        ModuleHandleW = GetModuleHandleW(L"winmm.dll");
        if ( ModuleHandleW || (ModuleHandleW = LoadLibraryW(L"winmm.dll")) != 0 )
        {
          ProcAddress = GetProcAddress(ModuleHandleW, "PlaySoundW");
          if ( ProcAddress )
            ((void (__fastcall *)(WCHAR *, _QWORD, __int64))ProcAddress)(Data, 0, 2228227);
          else
            g_fNeverPlaySound = 1;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800181a0  mov     [rsp-8+arg_8], rbx
0x1800181a5  mov     [rsp-8+arg_10], rdi
0x1800181aa  push    rbp
0x1800181ab  lea     rbp, [rsp-3C0h]
0x1800181b3  sub     rsp, 4C0h
0x1800181ba  mov     rax, cs:__security_cookie
0x1800181c1  xor     rax, rsp
0x1800181c4  mov     [rbp+3C0h+var_10], rax
0x1800181cb  cmp     cs:g_fNeverPlaySound, 0
0x1800181d2  mov     rdi, rcx
0x1800181d5  jnz     loc_1800182E4
0x1800181db  movaps  xmm0, xmmword ptr cs:aAppeventsSchem; "AppEvents\\Schemes\\Apps\\.Default\\%s"...
0x1800181e2  movaps  xmm1, xmmword ptr cs:aAppeventsSchem+10h; "s\\Schemes\\Apps\\.Default\\%s\\.curren"...
0x1800181e9  movaps  xmmword ptr [rsp+4C0h+String], xmm0
0x1800181ee  movaps  xmm0, xmmword ptr cs:aAppeventsSchem+20h; "s\\Apps\\.Default\\%s\\.current"
0x1800181f5  movaps  [rsp+4C0h+var_480], xmm1
0x1800181fa  movaps  xmm1, xmmword ptr cs:aAppeventsSchem+30h; "Default\\%s\\.current"
0x180018201  movaps  [rsp+4C0h+var_470], xmm0
0x180018206  movaps  xmm0, xmmword ptr cs:aAppeventsSchem+40h; "%s\\.current"
0x18001820d  movaps  [rsp+4C0h+var_460], xmm1
0x180018212  movsd   xmm1, qword ptr cs:aAppeventsSchem+50h; "ent"
0x18001821a  movaps  [rsp+4C0h+var_450], xmm0
0x18001821f  movsd   [rbp+3C0h+var_440], xmm1
0x180018224  mov     [rsp+4C0h+cbData], 208h
0x18001822c  call    cs:__imp_lstrlenW
0x180018232  lea     rcx, [rsp+4C0h+String]; lpString
0x180018237  mov     ebx, eax
0x180018239  call    cs:__imp_lstrlenW
0x18001823f  add     ebx, eax
0x180018241  mov     edx, 104h; unsigned __int64
0x180018246  cmp     ebx, edx
0x180018248  jnb     loc_1800182E4
0x18001824e  mov     r9, rdi
0x180018251  lea     r8, [rsp+4C0h+String]; unsigned __int16 *
0x180018256  lea     rcx, [rbp+3C0h+SubKey]; Buffer
0x18001825a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001825f  lea     r9, [rsp+4C0h+cbData]; lpcbData
0x180018264  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001826b  lea     r8, [rbp+3C0h+Data]; lpData
0x180018272  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x180018276  call    cs:__imp_RegQueryValueW
0x18001827c  test    eax, eax
0x18001827e  jnz     short loc_1800182E4
0x180018280  movsxd  rax, [rsp+4C0h+cbData]
0x180018285  cmp     rax, 2
0x180018289  jbe     short loc_1800182E4
0x18001828b  lea     rcx, c_szWinMMDll; "winmm.dll"
0x180018292  call    cs:__imp_GetModuleHandleW
0x180018298  test    rax, rax
0x18001829b  jnz     short loc_1800182AF
0x18001829d  lea     rcx, c_szWinMMDll; "winmm.dll"
0x1800182a4  call    cs:__imp_LoadLibraryW
0x1800182aa  test    rax, rax
0x1800182ad  jz      short loc_1800182E4
0x1800182af  lea     rdx, c_szPlaySound; "PlaySoundW"
0x1800182b6  mov     rcx, rax; hModule
0x1800182b9  call    cs:__imp_GetProcAddress
0x1800182bf  test    rax, rax
0x1800182c2  jnz     short loc_1800182D0
0x1800182c4  mov     cs:g_fNeverPlaySound, 1
0x1800182ce  jmp     short loc_1800182E4
0x1800182d0  xor     edx, edx
0x1800182d2  lea     rcx, [rbp+3C0h+Data]
0x1800182d9  mov     r8d, 220003h
0x1800182df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182e4  mov     rcx, [rbp+3C0h+var_10]
0x1800182eb  xor     rcx, rsp; StackCookie
0x1800182ee  call    __security_check_cookie
0x1800182f3  lea     r11, [rsp+4C0h+var_s0]
0x1800182fb  mov     rbx, [r11+18h]
0x1800182ff  mov     rdi, [r11+20h]
0x180018303  mov     rsp, r11
0x180018306  pop     rbp
0x180018307  retn
```

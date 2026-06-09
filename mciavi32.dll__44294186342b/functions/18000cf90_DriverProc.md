# DriverProc

- ea: `0x18000cf90`
- end: `0x18000d0f7`
- name: `DriverProc`
- size: `359`
- prototype: `LRESULT __fastcall(DWORD_PTR, HDRVR, UINT, LPARAM, unsigned int *lParam2)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000cf90`
- `0x18000d6bc`
- `0x18000f360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d07a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d07a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d066`
- `USER32!UnregisterClassW` at `0x18000d052`
- `USER32!UnregisterClassW` at `0x18000d052`
- `WINMM!DefDriverProc` at `0x18000d01b`
- `WINMM!DefDriverProc` at `0x18000d01b`
- `WINMM!GetDriverModuleHandle` at `0x18000d0cd`
- `WINMM!GetDriverModuleHandle` at `0x18000d0cd`
- `WINMM!mciFreeCommandResource` at `0x18000d034`
- `WINMM!mciFreeCommandResource` at `0x18000d034`

## pseudocode

```c
LRESULT __fastcall DriverProc(DWORD_PTR a1, HDRVR a2, UINT a3, LPARAM a4, unsigned int *lParam2)
{
  __int64 v5; // rcx

  switch ( a3 )
  {
    case 1u:
      hmod = GetDriverModuleHandle(a2);
      dword_180018378 = 0;
      return (unsigned int)sub_18000D6BC() != 0;
    case 2u:
      return 1;
    case 3u:
      if ( !lParam2 )
        return 10000;
      lParam2[3] = wTable;
      lParam2[4] = 520;
      return *lParam2;
    case 4u:
      return qword_180018380 == 0;
    case 5u:
      return 1;
  }
  if ( a3 != 6 )
  {
    if ( a3 - 7 >= 2 )
    {
      if ( WORD1(a1) || a3 - 2048 > 0xFFF )
        return DefDriverProc(a1, a2, a3, a4, (LPARAM)lParam2);
      else
        return (unsigned int)sub_18000F360(a1);
    }
    return 1;
  }
  if ( wTable != -1 )
  {
    mciFreeCommandResource(wTable);
    wTable = -1;
  }
  UnregisterClassW(ClassName, hmod);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  DeleteCriticalSection(&CriticalSection);
  v5 = 1;
  hmod = 0;
  return v5;
}

```

## disassembly

```asm
0x18000cf90  push    rbx
0x18000cf92  sub     rsp, 30h
0x18000cf96  mov     eax, r8d
0x18000cf99  mov     r10d, r8d
0x18000cf9c  sub     eax, 1
0x18000cf9f  jz      loc_18000D0CA
0x18000cfa5  sub     eax, 1
0x18000cfa8  jz      loc_18000D0C3
0x18000cfae  sub     eax, 1
0x18000cfb1  jz      loc_18000D09E
0x18000cfb7  sub     eax, 1
0x18000cfba  jz      loc_18000D08E
0x18000cfc0  sub     eax, 1
0x18000cfc3  jz      loc_18000D0C3
0x18000cfc9  sub     eax, 1
0x18000cfcc  jz      short loc_18000D029
0x18000cfce  sub     eax, 1
0x18000cfd1  jz      loc_18000D0C3
0x18000cfd7  cmp     eax, 1
0x18000cfda  jz      loc_18000D0C3
0x18000cfe0  mov     rax, rcx
0x18000cfe3  shr     rax, 10h
0x18000cfe7  test    ax, ax
0x18000cfea  jnz     short loc_18000D011
0x18000cfec  lea     eax, [r8-800h]
0x18000cff3  cmp     eax, 0FFFh
0x18000cff8  ja      short loc_18000D011
0x18000cffa  mov     r8d, r9d
0x18000cffd  mov     edx, r10d
0x18000d000  mov     r9, [rsp+38h+arg_20]
0x18000d005  call    sub_18000F360
0x18000d00a  mov     ecx, eax; dwDriverIdentifier
0x18000d00c  jmp     loc_18000D0EE
0x18000d011  mov     rax, [rsp+38h+arg_20]
0x18000d016  mov     [rsp+38h+lParam2], rax; lParam2
0x18000d01b  call    cs:DefDriverProc
0x18000d021  mov     rcx, rax
0x18000d024  jmp     loc_18000D0EE
0x18000d029  mov     ecx, cs:wTable; wTable
0x18000d02f  cmp     ecx, 0FFFFFFFFh
0x18000d032  jz      short loc_18000D044
0x18000d034  call    cs:mciFreeCommandResource
0x18000d03a  mov     cs:wTable, 0FFFFFFFFh
0x18000d044  mov     rdx, cs:hmod; hInstance
0x18000d04b  lea     rcx, ClassName; "AVIWnd32"
0x18000d052  call    cs:UnregisterClassW
0x18000d058  mov     rcx, cs:hKey; hKey
0x18000d05f  xor     ebx, ebx
0x18000d061  test    rcx, rcx
0x18000d064  jz      short loc_18000D073
0x18000d066  call    cs:RegCloseKey
0x18000d06c  mov     cs:hKey, rbx
0x18000d073  lea     rcx, CriticalSection; lpCriticalSection
0x18000d07a  call    cs:DeleteCriticalSection
0x18000d080  mov     ecx, 1
0x18000d085  mov     cs:hmod, rbx
0x18000d08c  jmp     short loc_18000D0EE
0x18000d08e  xor     ebx, ebx
0x18000d090  cmp     cs:qword_180018380, rbx
0x18000d097  mov     ecx, ebx
0x18000d099  setz    cl
0x18000d09c  jmp     short loc_18000D0EE
0x18000d09e  mov     rcx, [rsp+38h+arg_20]
0x18000d0a3  test    rcx, rcx
0x18000d0a6  jnz     short loc_18000D0AF
0x18000d0a8  mov     ecx, 2710h
0x18000d0ad  jmp     short loc_18000D0EE
0x18000d0af  mov     eax, cs:wTable
0x18000d0b5  mov     [rcx+0Ch], eax
0x18000d0b8  mov     dword ptr [rcx+10h], 208h
0x18000d0bf  mov     ecx, [rcx]
0x18000d0c1  jmp     short loc_18000D0EE
0x18000d0c3  mov     ecx, 1
0x18000d0c8  jmp     short loc_18000D0EE
0x18000d0ca  mov     rcx, rdx; hDriver
0x18000d0cd  call    cs:GetDriverModuleHandle
0x18000d0d3  xor     ebx, ebx
0x18000d0d5  mov     cs:hmod, rax
0x18000d0dc  mov     cs:dword_180018378, ebx
0x18000d0e2  call    sub_18000D6BC
0x18000d0e7  test    eax, eax
0x18000d0e9  mov     ecx, ebx
0x18000d0eb  setnz   cl
0x18000d0ee  mov     rax, rcx
0x18000d0f1  add     rsp, 30h
0x18000d0f5  pop     rbx
0x18000d0f6  retn
```

# DhcpV6ServerEventLog

- ea: `0x180067fd0`
- end: `0x1800681a9`
- name: `DhcpV6ServerEventLog`
- size: `473`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002a00`
- `0x180013380`
- `0x180025bf4`

## callees

- `0x180002854`
- `0x180067fd0`
- `0x18008f044`
- `0x1800cc9e0`

## import_xrefs

- `msvcrt!_ultoa` at `0x18006805d`
- `msvcrt!_ultoa` at `0x18006805d`
- `KERNEL32!FreeLibrary` at `0x1800680cd`
- `KERNEL32!FreeLibrary` at `0x1800680cd`
- `KERNEL32!FormatMessageW` at `0x1800680bc`
- `KERNEL32!FormatMessageW` at `0x1800680bc`
- `KERNEL32!LocalFree` at `0x18006812b`
- `KERNEL32!LocalFree` at `0x18006812b`
- `KERNEL32!LoadLibraryExW` at `0x180068088`
- `KERNEL32!LoadLibraryExW` at `0x180068088`

## string_xrefs

- `0x18006807f`: `dhcpssvc.dll`

## pseudocode

```c
_UNKNOWN **__fastcall DhcpV6ServerEventLog(__int64 a1, unsigned int a2, unsigned int a3)
{
  unsigned int v5; // esi
  __int64 v6; // r8
  char *v7; // rdx
  char v8; // al
  char *v9; // rax
  __int64 v10; // rcx
  HMODULE Library; // rdi
  DWORD v12; // ebx
  unsigned int v13; // ebx
  _UNKNOWN **result; // rax
  char *hMem; // [rsp+48h] [rbp-11h]
  WCHAR lpBuffer[4]; // [rsp+50h] [rbp-9h] BYREF
  char v18[2]; // [rsp+58h] [rbp-1h] BYREF
  char Buffer[38]; // [rsp+5Ah] [rbp+1h] BYREF

  v5 = a1;
  if ( a3 )
  {
    v6 = 33;
    v7 = v18;
    do
    {
      if ( v6 == -2147483613 )
        break;
      v8 = v7["%%" - v18];
      if ( !v8 )
        break;
      *v7++ = v8;
      --v6;
    }
    while ( v6 );
    v9 = v7 - 1;
    if ( v6 )
      v9 = v7;
    *v9 = 0;
    _ultoa(a3, Buffer, 10);
    *(_QWORD *)lpBuffer = 0;
    if ( a3 - 10000 > 0x18
      || (Library = LoadLibraryExW(L"dhcpssvc.dll", 0, 0),
          v12 = FormatMessageW(0xB00u, Library, a3, 0x400u, lpBuffer, 0, 0),
          FreeLibrary(Library),
          !v12)
      || (hMem = *(char **)lpBuffer) == 0 )
    {
      hMem = v18;
    }
    v13 = DhcpReportEventA(v10, v5, a2);
    result = (_UNKNOWN **)v18;
    if ( hMem != v18 )
      result = (_UNKNOWN **)LocalFree(hMem);
  }
  else
  {
    result = (_UNKNOWN **)DhcpReportEventA(a1, (unsigned int)a1, a2);
    v13 = (unsigned int)result;
  }
  if ( v13 )
  {
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      return (_UNKNOWN **)WPP_SF_D(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            17,
                            &WPP_3a03f93c2ffe32d69ed1170ace27464b_Traceguids,
                            v13);
  }
  return result;
}

```

## disassembly

```asm
0x180067fd0  push    rbp
0x180067fd2  push    rbx
0x180067fd3  push    rsi
0x180067fd4  push    rdi
0x180067fd5  push    r14
0x180067fd7  lea     rbp, [rsp-37h]
0x180067fdc  sub     rsp, 90h
0x180067fe3  mov     rax, cs:__security_cookie
0x180067fea  xor     rax, rsp
0x180067fed  mov     [rbp+57h+var_30], rax
0x180067ff1  and     [rbp+57h+hMem], 0
0x180067ff6  mov     r10d, r8d
0x180067ff9  mov     [rbp+57h+dwMessageId], r8d
0x180067ffd  mov     r14d, edx
0x180068000  mov     esi, ecx
0x180068002  test    r8d, r8d
0x180068005  jz      loc_180068139
0x18006800b  lea     r9, asc_1800E4968; "%%"
0x180068012  mov     r8d, 21h ; '!'
0x180068018  lea     rax, [rbp+57h+var_58]
0x18006801c  sub     r9, rax
0x18006801f  lea     rdx, [rbp+57h+var_58]
0x180068023  lea     rax, [r8+7FFFFFDDh]
0x18006802a  test    rax, rax
0x18006802d  jz      short loc_180068042
0x18006802f  mov     al, [r9+rdx]
0x180068033  test    al, al
0x180068035  jz      short loc_180068042
0x180068037  mov     [rdx], al
0x180068039  inc     rdx
0x18006803c  sub     r8, 1
0x180068040  jnz     short loc_180068023
0x180068042  test    r8, r8
0x180068045  lea     rax, [rdx-1]
0x180068049  mov     r8d, 0Ah; Radix
0x18006804f  mov     ecx, r10d; Value
0x180068052  cmovnz  rax, rdx
0x180068056  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18006805a  mov     byte ptr [rax], 0
0x18006805d  call    cs:__imp__ultoa
0x180068064  nop     dword ptr [rax+rax+00h]
0x180068069  mov     ebx, [rbp+57h+dwMessageId]
0x18006806c  and     qword ptr [rbp+57h+var_60], 0
0x180068071  lea     eax, [rbx-2710h]
0x180068077  cmp     eax, 18h
0x18006807a  ja      short loc_1800680EA
0x18006807c  xor     r8d, r8d; dwFlags
0x18006807f  lea     rcx, LibFileName; "dhcpssvc.dll"
0x180068086  xor     edx, edx; hFile
0x180068088  call    cs:__imp_LoadLibraryExW
0x18006808f  nop     dword ptr [rax+rax+00h]
0x180068094  and     [rsp+0B0h+var_80], 0
0x18006809a  mov     r9d, 400h; dwLanguageId
0x1800680a0  and     dword ptr [rsp+0B0h+var_88], 0
0x1800680a5  mov     rdi, rax
0x1800680a8  lea     rax, [rbp+57h+var_60]
0x1800680ac  mov     rdx, rdi; lpSource
0x1800680af  mov     r8d, ebx; dwMessageId
0x1800680b2  mov     [rsp+0B0h+lpBuffer], rax; lpBuffer
0x1800680b7  mov     ecx, 0B00h; dwFlags
0x1800680bc  call    cs:__imp_FormatMessageW
0x1800680c3  nop     dword ptr [rax+rax+00h]
0x1800680c8  mov     rcx, rdi; hLibModule
0x1800680cb  mov     ebx, eax
0x1800680cd  call    cs:__imp_FreeLibrary
0x1800680d4  nop     dword ptr [rax+rax+00h]
0x1800680d9  test    ebx, ebx
0x1800680db  jz      short loc_1800680EA
0x1800680dd  mov     rax, qword ptr [rbp+57h+var_60]
0x1800680e1  mov     [rbp+57h+hMem], rax
0x1800680e5  test    rax, rax
0x1800680e8  jnz     short loc_1800680F2
0x1800680ea  lea     rax, [rbp+57h+var_58]
0x1800680ee  mov     [rbp+57h+hMem], rax
0x1800680f2  lea     rax, [rbp+57h+dwMessageId]
0x1800680f6  mov     r9d, 1
0x1800680fc  mov     [rsp+0B0h+var_80], rax
0x180068101  mov     r8d, r14d
0x180068104  lea     rax, [rbp+57h+hMem]
0x180068108  mov     edx, esi
0x18006810a  mov     [rsp+0B0h+var_88], rax
0x18006810f  mov     dword ptr [rsp+0B0h+lpBuffer], 4
0x180068117  call    DhcpReportEventA
0x18006811c  mov     rcx, [rbp+57h+hMem]; hMem
0x180068120  mov     ebx, eax
0x180068122  lea     rax, [rbp+57h+var_58]
0x180068126  cmp     rcx, rax
0x180068129  jz      short loc_180068159
0x18006812b  call    cs:__imp_LocalFree
0x180068132  nop     dword ptr [rax+rax+00h]
0x180068137  jmp     short loc_180068159
0x180068139  and     [rsp+0B0h+var_80], 0
0x18006813f  xor     r9d, r9d
0x180068142  and     [rsp+0B0h+var_88], 0
0x180068148  mov     r8d, r14d
0x18006814b  and     dword ptr [rsp+0B0h+lpBuffer], 0
0x180068150  mov     edx, esi
0x180068152  call    DhcpReportEventA
0x180068157  mov     ebx, eax
0x180068159  test    ebx, ebx
0x18006815b  jz      short loc_18006818E
0x18006815d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068164  lea     rax, WPP_GLOBAL_Control
0x18006816b  cmp     rcx, rax
0x18006816e  jz      short loc_18006818E
0x180068170  test    byte ptr [rcx+1Ch], 10h
0x180068174  jz      short loc_18006818E
0x180068176  mov     rcx, [rcx+10h]
0x18006817a  lea     r8, WPP_3a03f93c2ffe32d69ed1170ace27464b_Traceguids
0x180068181  mov     edx, 11h
0x180068186  mov     r9d, ebx
0x180068189  call    WPP_SF_D
0x18006818e  mov     rcx, [rbp+57h+var_30]
0x180068192  xor     rcx, rsp; StackCookie
0x180068195  call    __security_check_cookie
0x18006819a  add     rsp, 90h
0x1800681a1  pop     r14
0x1800681a3  pop     rdi
0x1800681a4  pop     rsi
0x1800681a5  pop     rbx
0x1800681a6  pop     rbp
0x1800681a7  retn
```

# FileBrowser(HWND__ *,ushort *,unsigned __int64,ushort const *,ushort const *,int)

- ea: `0x14003f464`
- end: `0x14003f936`
- name: `?FileBrowser@@YAJPEAUHWND__@@PEAG_KPEBG3H@Z`
- size: `1234`
- prototype: `__int64 __fastcall(HWND, unsigned __int16 *, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002e470`
- `0x14003afa0`

## callees

- `0x1400039b1`
- `0x140006fe0`
- `0x1400070b0`
- `0x140010eb4`
- `0x140020420`
- `0x14003f464`
- `0x140041c54`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003f58b`
- `KERNEL32!GetLastError` at `0x14003f58b`
- `KERNEL32!HeapAlloc` at `0x14003f52a`
- `KERNEL32!HeapAlloc` at `0x14003f60a`
- `KERNEL32!HeapAlloc` at `0x14003f66b`
- `KERNEL32!HeapAlloc` at `0x14003f52a`
- `KERNEL32!HeapAlloc` at `0x14003f60a`
- `KERNEL32!HeapAlloc` at `0x14003f66b`
- `KERNEL32!HeapFree` at `0x14003f8b3`
- `KERNEL32!HeapFree` at `0x14003f8d8`
- `KERNEL32!HeapFree` at `0x14003f8fd`
- `KERNEL32!HeapFree` at `0x14003f8b3`
- `KERNEL32!HeapFree` at `0x14003f8d8`
- `KERNEL32!HeapFree` at `0x14003f8fd`
- `KERNEL32!GetProcessHeap` at `0x14003f516`
- `KERNEL32!GetProcessHeap` at `0x14003f5f6`
- `KERNEL32!GetProcessHeap` at `0x14003f657`
- `KERNEL32!GetProcessHeap` at `0x14003f89f`
- `KERNEL32!GetProcessHeap` at `0x14003f8c4`
- `KERNEL32!GetProcessHeap` at `0x14003f8e9`
- `KERNEL32!GetProcessHeap` at `0x14003f516`
- `KERNEL32!GetProcessHeap` at `0x14003f5f6`
- `KERNEL32!GetProcessHeap` at `0x14003f657`
- `KERNEL32!GetProcessHeap` at `0x14003f89f`
- `KERNEL32!GetProcessHeap` at `0x14003f8c4`
- `KERNEL32!GetProcessHeap` at `0x14003f8e9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14003f57b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14003f57b`
- `COMDLG32!GetOpenFileNameW` at `0x14003f850`
- `COMDLG32!GetOpenFileNameW` at `0x14003f850`
- `COMDLG32!CommDlgExtendedError` at `0x14003f863`
- `COMDLG32!CommDlgExtendedError` at `0x14003f863`

## pseudocode

```c
__int64 __fastcall FileBrowser(
        HWND a1,
        unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6)
{
  WCHAR *v9; // r12
  WCHAR *v10; // r13
  HANDLE v11; // rax
  WCHAR *v12; // rax
  signed int v13; // ebx
  signed int LastError; // eax
  unsigned __int16 *v15; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v17; // rax
  HANDLE v18; // rax
  int LocalString; // eax
  int v20; // r9d
  __int64 v21; // rsi
  __int64 v22; // r15
  __int64 v23; // r14
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  HANDLE v27; // rax
  HANDLE v28; // rax
  HANDLE v29; // rax
  tagOFNW v31; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[256]; // [rsp+D0h] [rbp-30h] BYREF

  v9 = 0;
  v10 = 0;
  memset_0(&v31, 0, sizeof(v31));
  v31.hInstance = g_hInstance;
  v31.lStructSize = 152;
  v31.hwndOwner = a1;
  *a2 = 0;
  v31.nFilterIndex = 1;
  v31.lpstrFile = a2;
  v31.nMaxFileTitle = 0;
  v31.Flags = a6 != 0 ? 4100 : 4;
  if ( !dword_14007F4A8 )
  {
LABEL_10:
    v15 = 0;
    if ( a4 && a5 )
    {
      ProcessHeap = GetProcessHeap();
      v17 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
      v15 = v17;
      if ( !v17 )
      {
        v13 = -2147024882;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FileBrowser", 244, -2147024882);
        goto LABEL_46;
      }
      memset_0(v17, 0, 0x208u);
      v18 = GetProcessHeap();
      v10 = (WCHAR *)HeapAlloc(v18, 0, 0x208u);
      if ( !v10 )
      {
        LocalString = -2147024882;
        v20 = 247;
        v13 = -2147024882;
LABEL_16:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FileBrowser", v20, LocalString);
        goto LABEL_45;
      }
      LocalString = StringCchPrintfW(v15, 0x104u, L"%s (%s)", a4, a5);
      v13 = LocalString;
      if ( LocalString < 0 )
      {
        v20 = 255;
        goto LABEL_16;
      }
      v21 = -1;
      v22 = -1;
      do
        ++v22;
      while ( v15[v22] );
      LocalString = StringCchCatW(v15, 0x104u, L" ");
      v13 = LocalString;
      if ( LocalString < 0 )
      {
        v20 = 263;
        goto LABEL_16;
      }
      v13 = StringCchCatW(v15, 0x104u, a5);
      if ( v13 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FileBrowser", 266, v13);
        goto LABEL_45;
      }
      v23 = -1;
      do
        ++v23;
      while ( v15[v23] );
      LocalString = StringCchCatW(v15, 0x104u, L" ");
      v13 = LocalString;
      if ( LocalString < 0 )
      {
        v20 = 274;
        goto LABEL_16;
      }
      LocalString = DwzLoadLocalString(0x87u, v10, 0x104u);
      v13 = LocalString;
      if ( LocalString < 0 )
      {
        v20 = 277;
        goto LABEL_16;
      }
      v13 = StringCchCatW(v15, 0x104u, v10);
      if ( v13 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FileBrowser", 280, v13);
        goto LABEL_45;
      }
      do
        ++v21;
      while ( v15[v21] );
      v13 = StringCchCatW(v15, 0x104u, L" *.*");
      if ( v13 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FileBrowser", 288, v13);
        goto LABEL_45;
      }
      v15[v22] = 0;
      v15[v23] = 0;
      v15[v21] = 0;
      v31.lpstrFilter = v15;
    }
    v24 = ULongLongToULong(0x104u, &v31.nMaxFile);
    v13 = v24;
    if ( v24 >= 0 )
    {
      Buffer[0] = 0;
      v26 = DwzLoadLocalString(0xFCu, Buffer, 0x100u);
      v13 = v26;
      if ( v26 >= 0 )
      {
        v31.lpstrTitle = Buffer;
        if ( !GetOpenFileNameW(&v31) )
        {
          v13 = 1;
          if ( CommDlgExtendedError() )
          {
            v13 = -2147467259;
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FileBrowser", 321, -2147467259);
          }
        }
      }
      else
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FileBrowser", 310, v26);
      }
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FileBrowser", v25 + 42, v24);
    }
    if ( !v15 )
    {
LABEL_46:
      if ( !v9 )
        goto LABEL_48;
      goto LABEL_47;
    }
LABEL_45:
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v15);
    goto LABEL_46;
  }
  v11 = GetProcessHeap();
  v12 = (WCHAR *)HeapAlloc(v11, 0, 0x208u);
  v9 = v12;
  if ( !v12 )
  {
    v13 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FileBrowser", 234, -2147024882);
    return (unsigned int)v13;
  }
  if ( ExpandEnvironmentStringsW(L"%userprofile%", v12, 0x104u) )
    goto LABEL_9;
  LastError = GetLastError();
  v13 = LastError;
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  if ( v13 >= 0 )
  {
LABEL_9:
    v31.lpstrInitialDir = v9;
    dword_14007F4A8 = 0;
    goto LABEL_10;
  }
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FileBrowser", 237, v13);
LABEL_47:
  v28 = GetProcessHeap();
  HeapFree(v28, 0, v9);
LABEL_48:
  if ( v10 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v10);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14003f464  mov     [rsp-8+arg_10], rbx
0x14003f469  push    rbp
0x14003f46a  push    rsi
0x14003f46b  push    rdi
0x14003f46c  push    r12
0x14003f46e  push    r13
0x14003f470  push    r14
0x14003f472  push    r15
0x14003f474  lea     rbp, [rsp-1E0h]
0x14003f47c  sub     rsp, 2E0h
0x14003f483  mov     rax, cs:__security_cookie
0x14003f48a  xor     rax, rsp
0x14003f48d  mov     [rbp+210h+var_40], rax
0x14003f494  mov     r14, [rbp+210h+arg_20]
0x14003f49b  xor     eax, eax
0x14003f49d  mov     rdi, rdx
0x14003f4a0  mov     rbx, rcx
0x14003f4a3  mov     r15d, 98h
0x14003f4a9  lea     rcx, [rsp+310h+var_2E0]; void *
0x14003f4ae  mov     r8d, r15d; Size
0x14003f4b1  xor     edx, edx; Val
0x14003f4b3  mov     rsi, r9
0x14003f4b6  mov     r12d, eax
0x14003f4b9  mov     r13d, eax
0x14003f4bc  call    memset_0
0x14003f4c1  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x14003f4c8  xor     ecx, ecx
0x14003f4ca  mov     [rsp+310h+var_2E0.hInstance], rax
0x14003f4cf  mov     [rsp+310h+var_2E0.lStructSize], r15d
0x14003f4d4  xor     r15d, r15d
0x14003f4d7  neg     [rbp+210h+arg_28]
0x14003f4dd  mov     [rsp+310h+var_2E0.hwndOwner], rbx
0x14003f4e2  mov     ebx, 208h
0x14003f4e7  sbb     eax, eax
0x14003f4e9  mov     [rdi], cx
0x14003f4ec  and     eax, 1000h
0x14003f4f1  mov     [rsp+310h+var_2E0.nFilterIndex], 1
0x14003f4f9  add     eax, 4
0x14003f4fc  mov     [rsp+310h+var_2E0.lpstrFile], rdi
0x14003f501  cmp     cs:dword_14007F4A8, r15d
0x14003f508  mov     [rsp+310h+var_2E0.nMaxFileTitle], r15d
0x14003f50d  mov     [rbp+210h+var_2E0.Flags], eax
0x14003f510  jz      loc_14003F5E1
0x14003f516  call    cs:__imp_GetProcessHeap
0x14003f51d  nop     dword ptr [rax+rax+00h]
0x14003f522  mov     r8d, ebx; dwBytes
0x14003f525  xor     edx, edx; dwFlags
0x14003f527  mov     rcx, rax; hHeap
0x14003f52a  call    cs:__imp_HeapAlloc
0x14003f531  nop     dword ptr [rax+rax+00h]
0x14003f536  mov     r12, rax
0x14003f539  test    rax, rax
0x14003f53c  jnz     short loc_14003F56B
0x14003f53e  mov     eax, 8007000Eh
0x14003f543  lea     r8, aFilebrowser; "FileBrowser"
0x14003f54a  mov     r9d, 0EAh
0x14003f550  mov     dword ptr [rsp+310h+var_2F0], eax
0x14003f554  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003f55b  mov     ebx, eax
0x14003f55d  lea     ecx, [r13+1]; Level
0x14003f561  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003f566  jmp     loc_14003F909
0x14003f56b  mov     r8d, 104h; nSize
0x14003f571  lea     rcx, aUserprofile; "%userprofile%"
0x14003f578  mov     rdx, r12; lpDst
0x14003f57b  call    cs:__imp_ExpandEnvironmentStringsW
0x14003f582  nop     dword ptr [rax+rax+00h]
0x14003f587  test    eax, eax
0x14003f589  jnz     short loc_14003F5D6
0x14003f58b  call    cs:__imp_GetLastError
0x14003f592  nop     dword ptr [rax+rax+00h]
0x14003f597  mov     ebx, eax
0x14003f599  test    eax, eax
0x14003f59b  jle     short loc_14003F5A6
0x14003f59d  movzx   ebx, ax
0x14003f5a0  or      ebx, 80070000h
0x14003f5a6  test    ebx, ebx
0x14003f5a8  jns     short loc_14003F5D1
0x14003f5aa  mov     r9d, 0EDh
0x14003f5b0  mov     dword ptr [rsp+310h+var_2F0], ebx
0x14003f5b4  lea     r8, aFilebrowser; "FileBrowser"
0x14003f5bb  mov     ecx, 1; Level
0x14003f5c0  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003f5c7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003f5cc  jmp     loc_14003F8C4
0x14003f5d1  mov     ebx, 208h
0x14003f5d6  mov     [rbp+210h+var_2E0.lpstrInitialDir], r12
0x14003f5da  mov     cs:dword_14007F4A8, r15d
0x14003f5e1  mov     rdi, r15
0x14003f5e4  test    rsi, rsi
0x14003f5e7  jz      loc_14003F7FA
0x14003f5ed  test    r14, r14
0x14003f5f0  jz      loc_14003F7FA
0x14003f5f6  call    cs:__imp_GetProcessHeap
0x14003f5fd  nop     dword ptr [rax+rax+00h]
0x14003f602  mov     r8, rbx; dwBytes
0x14003f605  xor     edx, edx; dwFlags
0x14003f607  mov     rcx, rax; hHeap
0x14003f60a  call    cs:__imp_HeapAlloc
0x14003f611  nop     dword ptr [rax+rax+00h]
0x14003f616  mov     rdi, rax
0x14003f619  test    rax, rax
0x14003f61c  jnz     short loc_14003F64A
0x14003f61e  mov     eax, 8007000Eh
0x14003f623  lea     r8, aFilebrowser; "FileBrowser"
0x14003f62a  mov     r9d, 0F4h
0x14003f630  mov     dword ptr [rsp+310h+var_2F0], eax
0x14003f634  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003f63b  mov     ebx, eax
0x14003f63d  lea     ecx, [rdi+1]; Level
0x14003f640  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003f645  jmp     loc_14003F8BF
0x14003f64a  mov     r8, rbx; Size
0x14003f64d  xor     edx, edx; Val
0x14003f64f  mov     rcx, rdi; void *
0x14003f652  call    memset_0
0x14003f657  call    cs:__imp_GetProcessHeap
0x14003f65e  nop     dword ptr [rax+rax+00h]
0x14003f663  mov     r8, rbx; dwBytes
0x14003f666  xor     edx, edx; dwFlags
0x14003f668  mov     rcx, rax; hHeap
0x14003f66b  call    cs:__imp_HeapAlloc
0x14003f672  nop     dword ptr [rax+rax+00h]
0x14003f677  mov     r13, rax
0x14003f67a  test    rax, rax
0x14003f67d  jnz     short loc_14003F6AD
0x14003f67f  mov     eax, 8007000Eh
0x14003f684  mov     r9d, 0F7h
0x14003f68a  mov     ebx, eax
0x14003f68c  mov     dword ptr [rsp+310h+var_2F0], eax
0x14003f690  lea     r8, aFilebrowser; "FileBrowser"
0x14003f697  mov     ecx, 1; Level
0x14003f69c  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003f6a3  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003f6a8  jmp     loc_14003F89F
0x14003f6ad  mov     r9, rsi
0x14003f6b0  mov     [rsp+310h+var_2F0], r14
0x14003f6b5  lea     r8, aSS; "%s (%s)"
0x14003f6bc  mov     edx, 104h; unsigned __int64
0x14003f6c1  mov     rcx, rdi; unsigned __int16 *
0x14003f6c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003f6c9  mov     ebx, eax
0x14003f6cb  test    eax, eax
0x14003f6cd  jns     short loc_14003F6D7
0x14003f6cf  mov     r9d, 0FFh
0x14003f6d5  jmp     short loc_14003F68C
0x14003f6d7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14003f6db  mov     r15, rsi
0x14003f6de  xor     ecx, ecx
0x14003f6e0  inc     r15
0x14003f6e3  cmp     [rdi+r15*2], cx
0x14003f6e8  jnz     short loc_14003F6E0
0x14003f6ea  lea     r8, pszSubIdList; " "
0x14003f6f1  mov     edx, 104h; unsigned __int64
0x14003f6f6  mov     rcx, rdi; unsigned __int16 *
0x14003f6f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003f6fe  mov     ebx, eax
0x14003f700  test    eax, eax
0x14003f702  jns     short loc_14003F70C
0x14003f704  mov     r9d, 107h
0x14003f70a  jmp     short loc_14003F68C
0x14003f70c  mov     r8, r14; unsigned __int16 *
0x14003f70f  mov     edx, 104h; unsigned __int64
0x14003f714  mov     rcx, rdi; unsigned __int16 *
0x14003f717  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003f71c  mov     ebx, eax
0x14003f71e  xor     eax, eax
0x14003f720  test    ebx, ebx
0x14003f722  jns     short loc_14003F733
0x14003f724  mov     dword ptr [rsp+310h+var_2F0], ebx
0x14003f728  mov     r9d, 10Ah
0x14003f72e  jmp     loc_14003F690
0x14003f733  mov     r14, rsi
0x14003f736  inc     r14
0x14003f739  cmp     [rdi+r14*2], ax
0x14003f73e  jnz     short loc_14003F736
0x14003f740  lea     r8, pszSubIdList; " "
0x14003f747  mov     edx, 104h; unsigned __int64
0x14003f74c  mov     rcx, rdi; unsigned __int16 *
0x14003f74f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003f754  mov     ebx, eax
0x14003f756  test    eax, eax
0x14003f758  jns     short loc_14003F765
0x14003f75a  mov     r9d, 112h
0x14003f760  jmp     loc_14003F68C
0x14003f765  mov     r8d, 104h; cchBufferMax
0x14003f76b  mov     rdx, r13; lpBuffer
0x14003f76e  lea     ecx, [r8-7Dh]; uID
0x14003f772  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14003f777  mov     ebx, eax
0x14003f779  test    eax, eax
0x14003f77b  jns     short loc_14003F788
0x14003f77d  mov     r9d, 115h
0x14003f783  jmp     loc_14003F68C
0x14003f788  mov     r8, r13; unsigned __int16 *
0x14003f78b  mov     edx, 104h; unsigned __int64
0x14003f790  mov     rcx, rdi; unsigned __int16 *
0x14003f793  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003f798  mov     ebx, eax
0x14003f79a  xor     eax, eax
0x14003f79c  test    ebx, ebx
0x14003f79e  jns     short loc_14003F7AF
0x14003f7a0  mov     dword ptr [rsp+310h+var_2F0], ebx
0x14003f7a4  mov     r9d, 118h
0x14003f7aa  jmp     loc_14003F690
0x14003f7af  inc     rsi
0x14003f7b2  cmp     [rdi+rsi*2], ax
0x14003f7b6  jnz     short loc_14003F7AF
0x14003f7b8  lea     r8, asc_140071108; " *.*"
0x14003f7bf  mov     edx, 104h; unsigned __int64
0x14003f7c4  mov     rcx, rdi; unsigned __int16 *
0x14003f7c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003f7cc  mov     ebx, eax
0x14003f7ce  xor     eax, eax
0x14003f7d0  test    ebx, ebx
0x14003f7d2  jns     short loc_14003F7E3
0x14003f7d4  mov     dword ptr [rsp+310h+var_2F0], ebx
0x14003f7d8  mov     r9d, 120h
0x14003f7de  jmp     loc_14003F690
0x14003f7e3  mov     [rdi+r15*2], ax
0x14003f7e8  xor     r15d, r15d
0x14003f7eb  mov     [rdi+r14*2], r15w
0x14003f7f0  mov     [rdi+rsi*2], r15w
0x14003f7f5  mov     [rsp+310h+var_2E0.lpstrFilter], rdi
0x14003f7fa  lea     rdx, [rsp+310h+var_2E0.nMaxFile]; unsigned int *
0x14003f7ff  mov     ecx, 104h; unsigned __int64
0x14003f804  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14003f809  mov     ebx, eax
0x14003f80b  test    eax, eax
0x14003f80d  jns     short loc_14003F819
0x14003f80f  mov     dword ptr [rsp+310h+var_2F0], eax
0x14003f813  lea     r9d, [rcx+2Ah]
0x14003f817  jmp     short loc_14003F882
0x14003f819  mov     r8d, 100h; cchBufferMax
0x14003f81f  mov     [rbp+210h+Buffer], r15w
0x14003f824  lea     rdx, [rbp+210h+Buffer]; lpBuffer
0x14003f828  lea     ecx, [r8-4]; uID
0x14003f82c  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14003f831  mov     ebx, eax
0x14003f833  test    eax, eax
0x14003f835  jns     short loc_14003F843
0x14003f837  mov     dword ptr [rsp+310h+var_2F0], eax
0x14003f83b  mov     r9d, 136h
0x14003f841  jmp     short loc_14003F882
0x14003f843  lea     rax, [rbp+210h+Buffer]
0x14003f847  lea     rcx, [rsp+310h+var_2E0]; LPOPENFILENAMEW
0x14003f84c  mov     [rbp+210h+var_2E0.lpstrTitle], rax
0x14003f850  call    cs:__imp_GetOpenFileNameW
0x14003f857  nop     dword ptr [rax+rax+00h]
0x14003f85c  test    eax, eax
0x14003f85e  jnz     short loc_14003F89A
0x14003f860  lea     ebx, [rax+1]
0x14003f863  call    cs:__imp_CommDlgExtendedError
0x14003f86a  nop     dword ptr [rax+rax+00h]
0x14003f86f  test    eax, eax
0x14003f871  jz      short loc_14003F89A
0x14003f873  mov     ebx, 80004005h
0x14003f878  mov     r9d, 141h
0x14003f87e  mov     dword ptr [rsp+310h+var_2F0], ebx
0x14003f882  lea     r8, aFilebrowser; "FileBrowser"
0x14003f889  mov     ecx, 1; Level
0x14003f88e  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003f895  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003f89a  test    rdi, rdi
0x14003f89d  jz      short loc_14003F8BF
0x14003f89f  call    cs:__imp_GetProcessHeap
0x14003f8a6  nop     dword ptr [rax+rax+00h]
0x14003f8ab  mov     r8, rdi; lpMem
0x14003f8ae  xor     edx, edx; dwFlags
0x14003f8b0  mov     rcx, rax; hHeap
0x14003f8b3  call    cs:__imp_HeapFree
0x14003f8ba  nop     dword ptr [rax+rax+00h]
0x14003f8bf  test    r12, r12
0x14003f8c2  jz      short loc_14003F8E4
0x14003f8c4  call    cs:__imp_GetProcessHeap
0x14003f8cb  nop     dword ptr [rax+rax+00h]
0x14003f8d0  mov     r8, r12; lpMem
0x14003f8d3  xor     edx, edx; dwFlags
0x14003f8d5  mov     rcx, rax; hHeap
0x14003f8d8  call    cs:__imp_HeapFree
0x14003f8df  nop     dword ptr [rax+rax+00h]
0x14003f8e4  test    r13, r13
0x14003f8e7  jz      short loc_14003F909
0x14003f8e9  call    cs:__imp_GetProcessHeap
0x14003f8f0  nop     dword ptr [rax+rax+00h]
0x14003f8f5  mov     r8, r13; lpMem
0x14003f8f8  xor     edx, edx; dwFlags
0x14003f8fa  mov     rcx, rax; hHeap
0x14003f8fd  call    cs:__imp_HeapFree
0x14003f904  nop     dword ptr [rax+rax+00h]
0x14003f909  mov     eax, ebx
0x14003f90b  mov     rcx, [rbp+210h+var_40]
0x14003f912  xor     rcx, rsp; StackCookie
0x14003f915  call    __security_check_cookie
0x14003f91a  mov     rbx, [rsp+310h+arg_10]
0x14003f922  add     rsp, 2E0h
0x14003f929  pop     r15
0x14003f92b  pop     r14
0x14003f92d  pop     r13
0x14003f92f  pop     r12
  ... truncated ...
```

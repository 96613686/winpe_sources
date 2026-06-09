# CTSCredManAssistant::Initialize(void)

- ea: `0x1400aa170`
- end: `0x1400aa3e0`
- name: `?Initialize@CTSCredManAssistant@@MEAAJXZ`
- size: `624`
- prototype: `__int64 __fastcall(CTSCredManAssistant *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x1400947cc`
- `0x1400aa170`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1400aa19c`
- `KERNEL32!LoadLibraryExW` at `0x1400aa19c`
- `KERNEL32!GetProcAddress` at `0x1400aa1f7`
- `KERNEL32!GetProcAddress` at `0x1400aa253`
- `KERNEL32!GetProcAddress` at `0x1400aa2af`
- `KERNEL32!GetProcAddress` at `0x1400aa30b`
- `KERNEL32!GetProcAddress` at `0x1400aa360`
- `KERNEL32!GetProcAddress` at `0x1400aa1f7`
- `KERNEL32!GetProcAddress` at `0x1400aa253`
- `KERNEL32!GetProcAddress` at `0x1400aa2af`
- `KERNEL32!GetProcAddress` at `0x1400aa30b`
- `KERNEL32!GetProcAddress` at `0x1400aa360`
- `KERNEL32!GetLastError` at `0x1400aa1d6`
- `KERNEL32!GetLastError` at `0x1400aa231`
- `KERNEL32!GetLastError` at `0x1400aa28d`
- `KERNEL32!GetLastError` at `0x1400aa2e9`
- `KERNEL32!GetLastError` at `0x1400aa341`
- `KERNEL32!GetLastError` at `0x1400aa38e`
- `KERNEL32!GetLastError` at `0x1400aa3be`
- `KERNEL32!GetLastError` at `0x1400aa1d6`
- `KERNEL32!GetLastError` at `0x1400aa231`
- `KERNEL32!GetLastError` at `0x1400aa28d`
- `KERNEL32!GetLastError` at `0x1400aa2e9`
- `KERNEL32!GetLastError` at `0x1400aa341`
- `KERNEL32!GetLastError` at `0x1400aa38e`
- `KERNEL32!GetLastError` at `0x1400aa3be`

## string_xrefs

- `0x1400aa193`: `sspicli.dll`
- `0x1400aa2a8`: `SspiPrepareForCredWrite`
- `0x1400aa304`: `SspiPrepareForCredRead`

## pseudocode

```c
__int64 __fastcall CTSCredManAssistant::Initialize(CTSCredManAssistant *this)
{
  unsigned int v2; // ebx
  HMODULE Library; // rax
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  FARPROC ProcAddress; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  signed int v12; // eax

  *((_DWORD *)this + 5) |= 2u;
  v2 = 0;
  if ( !(unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater() )
    return v2;
  Library = LoadLibraryExW(L"sspicli.dll", 0, 0);
  *((_QWORD *)this + 5) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "SspiUnmarshalAuthIdentity");
    *((_QWORD *)this + 6) = ProcAddress;
    if ( ProcAddress )
    {
      v8 = GetProcAddress(*((HMODULE *)this + 5), "SspiFreeAuthIdentity");
      *((_QWORD *)this + 7) = v8;
      if ( v8 )
      {
        v9 = GetProcAddress(*((HMODULE *)this + 5), "SspiPrepareForCredWrite");
        *((_QWORD *)this + 8) = v9;
        if ( v9 )
        {
          v10 = GetProcAddress(*((HMODULE *)this + 5), "SspiPrepareForCredRead");
          *((_QWORD *)this + 9) = v10;
          if ( v10 )
          {
            v11 = GetProcAddress(*((HMODULE *)this + 5), "SspiLocalFree");
            *((_QWORD *)this + 10) = v11;
            if ( v11 )
              return v2;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_33;
            }
            LastError = GetLastError();
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v6 = 20;
            goto LABEL_32;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v6 = 19;
            goto LABEL_32;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v6 = 18;
          goto LABEL_32;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 17;
        goto LABEL_32;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 16;
      goto LABEL_32;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 15;
LABEL_32:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
  }
LABEL_33:
  v12 = GetLastError();
  v2 = v12;
  if ( v12 > 0 )
    return (unsigned __int16)v12 | 0x80070000;
  return v2;
}

```

## disassembly

```asm
0x1400aa170  mov     [rsp+arg_0], rbx
0x1400aa175  push    rdi
0x1400aa176  sub     rsp, 30h
0x1400aa17a  or      dword ptr [rcx+14h], 2
0x1400aa17e  mov     rdi, rcx
0x1400aa181  xor     ebx, ebx
0x1400aa183  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400aa188  test    eax, eax
0x1400aa18a  jz      loc_1400AA3D3
0x1400aa190  xor     r8d, r8d; dwFlags
0x1400aa193  lea     rcx, aSspicliDll; "sspicli.dll"
0x1400aa19a  xor     edx, edx; hFile
0x1400aa19c  call    cs:__imp_LoadLibraryExW
0x1400aa1a2  mov     [rdi+28h], rax
0x1400aa1a6  test    rax, rax
0x1400aa1a9  jnz     short loc_1400AA1ED
0x1400aa1ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa1b2  lea     rax, WPP_GLOBAL_Control
0x1400aa1b9  cmp     rcx, rax
0x1400aa1bc  jz      loc_1400AA3BE
0x1400aa1c2  test    byte ptr [rcx+1Ch], 1
0x1400aa1c6  jz      loc_1400AA3BE
0x1400aa1cc  cmp     byte ptr [rcx+19h], 2
0x1400aa1d0  jb      loc_1400AA3BE
0x1400aa1d6  call    cs:__imp_GetLastError
0x1400aa1dc  mov     ebx, eax
0x1400aa1de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa1e3  mov     edx, 0Fh
0x1400aa1e8  jmp     loc_1400AA3A0
0x1400aa1ed  lea     rdx, aSspiunmarshala_0; "SspiUnmarshalAuthIdentity"
0x1400aa1f4  mov     rcx, rax; hModule
0x1400aa1f7  call    cs:__imp_GetProcAddress
0x1400aa1fd  mov     [rdi+30h], rax
0x1400aa201  test    rax, rax
0x1400aa204  jnz     short loc_1400AA248
0x1400aa206  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa20d  lea     rax, WPP_GLOBAL_Control
0x1400aa214  cmp     rcx, rax
0x1400aa217  jz      loc_1400AA3BE
0x1400aa21d  test    byte ptr [rcx+1Ch], 1
0x1400aa221  jz      loc_1400AA3BE
0x1400aa227  cmp     byte ptr [rcx+19h], 2
0x1400aa22b  jb      loc_1400AA3BE
0x1400aa231  call    cs:__imp_GetLastError
0x1400aa237  mov     ebx, eax
0x1400aa239  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa23e  mov     edx, 10h
0x1400aa243  jmp     loc_1400AA3A0
0x1400aa248  mov     rcx, [rdi+28h]; hModule
0x1400aa24c  lea     rdx, aSspifreeauthid; "SspiFreeAuthIdentity"
0x1400aa253  call    cs:__imp_GetProcAddress
0x1400aa259  mov     [rdi+38h], rax
0x1400aa25d  test    rax, rax
0x1400aa260  jnz     short loc_1400AA2A4
0x1400aa262  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa269  lea     rax, WPP_GLOBAL_Control
0x1400aa270  cmp     rcx, rax
0x1400aa273  jz      loc_1400AA3BE
0x1400aa279  test    byte ptr [rcx+1Ch], 1
0x1400aa27d  jz      loc_1400AA3BE
0x1400aa283  cmp     byte ptr [rcx+19h], 2
0x1400aa287  jb      loc_1400AA3BE
0x1400aa28d  call    cs:__imp_GetLastError
0x1400aa293  mov     ebx, eax
0x1400aa295  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa29a  mov     edx, 11h
0x1400aa29f  jmp     loc_1400AA3A0
0x1400aa2a4  mov     rcx, [rdi+28h]; hModule
0x1400aa2a8  lea     rdx, aSspipreparefor_0; "SspiPrepareForCredWrite"
0x1400aa2af  call    cs:__imp_GetProcAddress
0x1400aa2b5  mov     [rdi+40h], rax
0x1400aa2b9  test    rax, rax
0x1400aa2bc  jnz     short loc_1400AA300
0x1400aa2be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa2c5  lea     rax, WPP_GLOBAL_Control
0x1400aa2cc  cmp     rcx, rax
0x1400aa2cf  jz      loc_1400AA3BE
0x1400aa2d5  test    byte ptr [rcx+1Ch], 1
0x1400aa2d9  jz      loc_1400AA3BE
0x1400aa2df  cmp     byte ptr [rcx+19h], 2
0x1400aa2e3  jb      loc_1400AA3BE
0x1400aa2e9  call    cs:__imp_GetLastError
0x1400aa2ef  mov     ebx, eax
0x1400aa2f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa2f6  mov     edx, 12h
0x1400aa2fb  jmp     loc_1400AA3A0
0x1400aa300  mov     rcx, [rdi+28h]; hModule
0x1400aa304  lea     rdx, aSspipreparefor_1; "SspiPrepareForCredRead"
0x1400aa30b  call    cs:__imp_GetProcAddress
0x1400aa311  mov     [rdi+48h], rax
0x1400aa315  test    rax, rax
0x1400aa318  jnz     short loc_1400AA355
0x1400aa31a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa321  lea     rax, WPP_GLOBAL_Control
0x1400aa328  cmp     rcx, rax
0x1400aa32b  jz      loc_1400AA3BE
0x1400aa331  test    byte ptr [rcx+1Ch], 1
0x1400aa335  jz      loc_1400AA3BE
0x1400aa33b  cmp     byte ptr [rcx+19h], 2
0x1400aa33f  jb      short loc_1400AA3BE
0x1400aa341  call    cs:__imp_GetLastError
0x1400aa347  mov     ebx, eax
0x1400aa349  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa34e  mov     edx, 13h
0x1400aa353  jmp     short loc_1400AA3A0
0x1400aa355  mov     rcx, [rdi+28h]; hModule
0x1400aa359  lea     rdx, aSspilocalfree; "SspiLocalFree"
0x1400aa360  call    cs:__imp_GetProcAddress
0x1400aa366  mov     [rdi+50h], rax
0x1400aa36a  test    rax, rax
0x1400aa36d  jnz     short loc_1400AA3D3
0x1400aa36f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa376  lea     rax, WPP_GLOBAL_Control
0x1400aa37d  cmp     rcx, rax
0x1400aa380  jz      short loc_1400AA3BE
0x1400aa382  test    byte ptr [rcx+1Ch], 1
0x1400aa386  jz      short loc_1400AA3BE
0x1400aa388  cmp     byte ptr [rcx+19h], 2
0x1400aa38c  jb      short loc_1400AA3BE
0x1400aa38e  call    cs:__imp_GetLastError
0x1400aa394  mov     ebx, eax
0x1400aa396  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa39b  mov     edx, 14h
0x1400aa3a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa3a7  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400aa3ae  mov     r9d, eax
0x1400aa3b1  mov     [rsp+38h+var_18], ebx
0x1400aa3b5  mov     rcx, [rcx+10h]
0x1400aa3b9  call    WPP_SF_Dd
0x1400aa3be  call    cs:__imp_GetLastError
0x1400aa3c4  mov     ebx, eax
0x1400aa3c6  test    eax, eax
0x1400aa3c8  jle     short loc_1400AA3D3
0x1400aa3ca  movzx   ebx, ax
0x1400aa3cd  or      ebx, 80070000h
0x1400aa3d3  mov     eax, ebx
0x1400aa3d5  mov     rbx, [rsp+38h+arg_0]
0x1400aa3da  add     rsp, 30h
0x1400aa3de  pop     rdi
0x1400aa3df  retn
```

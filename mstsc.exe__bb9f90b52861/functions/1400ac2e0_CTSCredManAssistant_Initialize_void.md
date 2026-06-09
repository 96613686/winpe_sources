# CTSCredManAssistant::Initialize(void)

- ea: `0x1400ac2e0`
- end: `0x1400ac550`
- name: `?Initialize@CTSCredManAssistant@@MEAAJXZ`
- size: `624`
- prototype: `__int64 __fastcall(CTSCredManAssistant *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14009693c`
- `0x1400ac2e0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1400ac30c`
- `KERNEL32!LoadLibraryExW` at `0x1400ac30c`
- `KERNEL32!GetProcAddress` at `0x1400ac367`
- `KERNEL32!GetProcAddress` at `0x1400ac3c3`
- `KERNEL32!GetProcAddress` at `0x1400ac41f`
- `KERNEL32!GetProcAddress` at `0x1400ac47b`
- `KERNEL32!GetProcAddress` at `0x1400ac4d0`
- `KERNEL32!GetProcAddress` at `0x1400ac367`
- `KERNEL32!GetProcAddress` at `0x1400ac3c3`
- `KERNEL32!GetProcAddress` at `0x1400ac41f`
- `KERNEL32!GetProcAddress` at `0x1400ac47b`
- `KERNEL32!GetProcAddress` at `0x1400ac4d0`
- `KERNEL32!GetLastError` at `0x1400ac346`
- `KERNEL32!GetLastError` at `0x1400ac3a1`
- `KERNEL32!GetLastError` at `0x1400ac3fd`
- `KERNEL32!GetLastError` at `0x1400ac459`
- `KERNEL32!GetLastError` at `0x1400ac4b1`
- `KERNEL32!GetLastError` at `0x1400ac4fe`
- `KERNEL32!GetLastError` at `0x1400ac52e`
- `KERNEL32!GetLastError` at `0x1400ac346`
- `KERNEL32!GetLastError` at `0x1400ac3a1`
- `KERNEL32!GetLastError` at `0x1400ac3fd`
- `KERNEL32!GetLastError` at `0x1400ac459`
- `KERNEL32!GetLastError` at `0x1400ac4b1`
- `KERNEL32!GetLastError` at `0x1400ac4fe`
- `KERNEL32!GetLastError` at `0x1400ac52e`

## string_xrefs

- `0x1400ac418`: `SspiPrepareForCredWrite`
- `0x1400ac474`: `SspiPrepareForCredRead`
- `0x1400ac303`: `sspicli.dll`

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
0x1400ac2e0  mov     [rsp+arg_0], rbx
0x1400ac2e5  push    rdi
0x1400ac2e6  sub     rsp, 30h
0x1400ac2ea  or      dword ptr [rcx+14h], 2
0x1400ac2ee  mov     rdi, rcx
0x1400ac2f1  xor     ebx, ebx
0x1400ac2f3  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400ac2f8  test    eax, eax
0x1400ac2fa  jz      loc_1400AC543
0x1400ac300  xor     r8d, r8d; dwFlags
0x1400ac303  lea     rcx, aSspicliDll; "sspicli.dll"
0x1400ac30a  xor     edx, edx; hFile
0x1400ac30c  call    cs:__imp_LoadLibraryExW
0x1400ac312  mov     [rdi+28h], rax
0x1400ac316  test    rax, rax
0x1400ac319  jnz     short loc_1400AC35D
0x1400ac31b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ac322  lea     rax, WPP_GLOBAL_Control
0x1400ac329  cmp     rcx, rax
0x1400ac32c  jz      loc_1400AC52E
0x1400ac332  test    byte ptr [rcx+1Ch], 1
0x1400ac336  jz      loc_1400AC52E
0x1400ac33c  cmp     byte ptr [rcx+19h], 2
0x1400ac340  jb      loc_1400AC52E
0x1400ac346  call    cs:__imp_GetLastError
0x1400ac34c  mov     ebx, eax
0x1400ac34e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ac353  mov     edx, 0Fh
0x1400ac358  jmp     loc_1400AC510
0x1400ac35d  lea     rdx, aSspiunmarshala_0; "SspiUnmarshalAuthIdentity"
0x1400ac364  mov     rcx, rax; hModule
0x1400ac367  call    cs:__imp_GetProcAddress
0x1400ac36d  mov     [rdi+30h], rax
0x1400ac371  test    rax, rax
0x1400ac374  jnz     short loc_1400AC3B8
0x1400ac376  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ac37d  lea     rax, WPP_GLOBAL_Control
0x1400ac384  cmp     rcx, rax
0x1400ac387  jz      loc_1400AC52E
0x1400ac38d  test    byte ptr [rcx+1Ch], 1
0x1400ac391  jz      loc_1400AC52E
0x1400ac397  cmp     byte ptr [rcx+19h], 2
0x1400ac39b  jb      loc_1400AC52E
0x1400ac3a1  call    cs:__imp_GetLastError
0x1400ac3a7  mov     ebx, eax
0x1400ac3a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ac3ae  mov     edx, 10h
0x1400ac3b3  jmp     loc_1400AC510
0x1400ac3b8  mov     rcx, [rdi+28h]; hModule
0x1400ac3bc  lea     rdx, aSspifreeauthid; "SspiFreeAuthIdentity"
0x1400ac3c3  call    cs:__imp_GetProcAddress
0x1400ac3c9  mov     [rdi+38h], rax
0x1400ac3cd  test    rax, rax
0x1400ac3d0  jnz     short loc_1400AC414
0x1400ac3d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ac3d9  lea     rax, WPP_GLOBAL_Control
0x1400ac3e0  cmp     rcx, rax
0x1400ac3e3  jz      loc_1400AC52E
0x1400ac3e9  test    byte ptr [rcx+1Ch], 1
0x1400ac3ed  jz      loc_1400AC52E
0x1400ac3f3  cmp     byte ptr [rcx+19h], 2
0x1400ac3f7  jb      loc_1400AC52E
0x1400ac3fd  call    cs:__imp_GetLastError
0x1400ac403  mov     ebx, eax
0x1400ac405  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ac40a  mov     edx, 11h
0x1400ac40f  jmp     loc_1400AC510
0x1400ac414  mov     rcx, [rdi+28h]; hModule
0x1400ac418  lea     rdx, aSspipreparefor_0; "SspiPrepareForCredWrite"
0x1400ac41f  call    cs:__imp_GetProcAddress
0x1400ac425  mov     [rdi+40h], rax
0x1400ac429  test    rax, rax
0x1400ac42c  jnz     short loc_1400AC470
0x1400ac42e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ac435  lea     rax, WPP_GLOBAL_Control
0x1400ac43c  cmp     rcx, rax
0x1400ac43f  jz      loc_1400AC52E
0x1400ac445  test    byte ptr [rcx+1Ch], 1
0x1400ac449  jz      loc_1400AC52E
0x1400ac44f  cmp     byte ptr [rcx+19h], 2
0x1400ac453  jb      loc_1400AC52E
0x1400ac459  call    cs:__imp_GetLastError
0x1400ac45f  mov     ebx, eax
0x1400ac461  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ac466  mov     edx, 12h
0x1400ac46b  jmp     loc_1400AC510
0x1400ac470  mov     rcx, [rdi+28h]; hModule
0x1400ac474  lea     rdx, aSspipreparefor_1; "SspiPrepareForCredRead"
0x1400ac47b  call    cs:__imp_GetProcAddress
0x1400ac481  mov     [rdi+48h], rax
0x1400ac485  test    rax, rax
0x1400ac488  jnz     short loc_1400AC4C5
0x1400ac48a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ac491  lea     rax, WPP_GLOBAL_Control
0x1400ac498  cmp     rcx, rax
0x1400ac49b  jz      loc_1400AC52E
0x1400ac4a1  test    byte ptr [rcx+1Ch], 1
0x1400ac4a5  jz      loc_1400AC52E
0x1400ac4ab  cmp     byte ptr [rcx+19h], 2
0x1400ac4af  jb      short loc_1400AC52E
0x1400ac4b1  call    cs:__imp_GetLastError
0x1400ac4b7  mov     ebx, eax
0x1400ac4b9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ac4be  mov     edx, 13h
0x1400ac4c3  jmp     short loc_1400AC510
0x1400ac4c5  mov     rcx, [rdi+28h]; hModule
0x1400ac4c9  lea     rdx, aSspilocalfree; "SspiLocalFree"
0x1400ac4d0  call    cs:__imp_GetProcAddress
0x1400ac4d6  mov     [rdi+50h], rax
0x1400ac4da  test    rax, rax
0x1400ac4dd  jnz     short loc_1400AC543
0x1400ac4df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ac4e6  lea     rax, WPP_GLOBAL_Control
0x1400ac4ed  cmp     rcx, rax
0x1400ac4f0  jz      short loc_1400AC52E
0x1400ac4f2  test    byte ptr [rcx+1Ch], 1
0x1400ac4f6  jz      short loc_1400AC52E
0x1400ac4f8  cmp     byte ptr [rcx+19h], 2
0x1400ac4fc  jb      short loc_1400AC52E
0x1400ac4fe  call    cs:__imp_GetLastError
0x1400ac504  mov     ebx, eax
0x1400ac506  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ac50b  mov     edx, 14h
0x1400ac510  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ac517  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ac51e  mov     r9d, eax
0x1400ac521  mov     [rsp+38h+var_18], ebx
0x1400ac525  mov     rcx, [rcx+10h]
0x1400ac529  call    WPP_SF_Dd
0x1400ac52e  call    cs:__imp_GetLastError
0x1400ac534  mov     ebx, eax
0x1400ac536  test    eax, eax
0x1400ac538  jle     short loc_1400AC543
0x1400ac53a  movzx   ebx, ax
0x1400ac53d  or      ebx, 80070000h
0x1400ac543  mov     eax, ebx
0x1400ac545  mov     rbx, [rsp+38h+arg_0]
0x1400ac54a  add     rsp, 30h
0x1400ac54e  pop     rdi
0x1400ac54f  retn
```

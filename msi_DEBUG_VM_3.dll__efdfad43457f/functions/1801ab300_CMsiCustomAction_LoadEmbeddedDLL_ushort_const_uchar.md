# CMsiCustomAction::LoadEmbeddedDLL(ushort const *,uchar)

- ea: `0x1801ab300`
- end: `0x1801ab5b1`
- name: `?LoadEmbeddedDLL@CMsiCustomAction@@UEAAJPEBGE@Z`
- size: `689`
- prototype: `int(CMsiCustomAction *__hidden this, const unsigned __int16 *, unsigned __int8)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180022120`
- `0x180025a18`
- `0x18006e484`
- `0x1800c2bf0`
- `0x1801ab300`
- `0x1801ae1f0`
- `0x18024f4b8`
- `0x18025ab2a`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1801ab3c9`
- `KERNEL32!LeaveCriticalSection` at `0x1801ab4f4`
- `KERNEL32!LeaveCriticalSection` at `0x1801ab57d`
- `KERNEL32!LeaveCriticalSection` at `0x1801ab3c9`
- `KERNEL32!LeaveCriticalSection` at `0x1801ab4f4`
- `KERNEL32!LeaveCriticalSection` at `0x1801ab57d`
- `KERNEL32!IsDebuggerPresent` at `0x1801ab42e`
- `KERNEL32!IsDebuggerPresent` at `0x1801ab42e`
- `KERNEL32!GetProcAddress` at `0x1801ab3ea`
- `KERNEL32!GetProcAddress` at `0x1801ab401`
- `KERNEL32!GetProcAddress` at `0x1801ab418`
- `KERNEL32!GetProcAddress` at `0x1801ab3ea`
- `KERNEL32!GetProcAddress` at `0x1801ab401`
- `KERNEL32!GetProcAddress` at `0x1801ab418`
- `KERNEL32!EnterCriticalSection` at `0x1801ab345`
- `KERNEL32!EnterCriticalSection` at `0x1801ab345`
- `KERNEL32!GetCurrentProcessId` at `0x1801ab459`
- `KERNEL32!GetCurrentProcessId` at `0x1801ab461`
- `KERNEL32!GetCurrentProcessId` at `0x1801ab459`
- `KERNEL32!GetCurrentProcessId` at `0x1801ab461`
- `KERNEL32!SetErrorMode` at `0x1801ab39b`
- `KERNEL32!SetErrorMode` at `0x1801ab3bb`
- `KERNEL32!SetErrorMode` at `0x1801ab56b`
- `KERNEL32!SetErrorMode` at `0x1801ab39b`
- `KERNEL32!SetErrorMode` at `0x1801ab3bb`
- `KERNEL32!SetErrorMode` at `0x1801ab56b`
- `USER32!MessageBoxW` at `0x1801ab4eb`
- `USER32!MessageBoxW` at `0x1801ab4eb`

## string_xrefs

- `0x1801ab384`: `EEUI - Custom action server trying to load this DLL: %s`
- `0x1801ab555`: `EEUI - Custom action server threw an exception during load: (%u), returning %u`

## pseudocode

```c
__int64 __fastcall CMsiCustomAction::LoadEmbeddedDLL(CMsiCustomAction *this, const unsigned __int16 *a2, char a3)
{
  UINT v6; // r14d
  HMODULE LibraryW; // rbx
  DWORD CurrentProcessId; // ebx
  DWORD v10; // eax
  unsigned __int16 *v11; // [rsp+20h] [rbp-308h]
  WCHAR Caption; // [rsp+80h] [rbp-2A8h] BYREF
  _BYTE v13[126]; // [rsp+82h] [rbp-2A6h] BYREF
  WCHAR Text; // [rsp+100h] [rbp-228h] BYREF
  _BYTE v15[510]; // [rsp+102h] [rbp-226h] BYREF

  CMsiCustomAction::WaitForCAMainThread(this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 792));
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"EEUI - Custom action server trying to load this DLL: %s",
      a2,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  v6 = SetErrorMode(1u);
  LibraryW = (HMODULE)IsolationAwareLoadLibraryW(a2);
  SetErrorMode(v6);
  if ( LibraryW )
  {
    *((_QWORD *)this + 98) = LibraryW;
    *((_QWORD *)this + 95) = GetProcAddress(LibraryW, "InitializeEmbeddedUI");
    *((_QWORD *)this + 96) = GetProcAddress(LibraryW, "ShutdownEmbeddedUI");
    *((_QWORD *)this + 97) = GetProcAddress(LibraryW, "EmbeddedUIHandler");
    if ( a3 )
    {
      if ( !IsDebuggerPresent() )
      {
        Text = 0;
        memset_0(v15, 0, sizeof(v15));
        CurrentProcessId = GetCurrentProcessId();
        v10 = GetCurrentProcessId();
        LODWORD(v11) = CurrentProcessId;
        if ( (int)StringCchPrintfW(
                    &Text,
                    0x100u,
                    L"To debug Embedded UI, attach your debugger to process %d (0x%X) and press OK",
                    v10,
                    v11) >= 0 )
        {
          Caption = 0;
          memset_0(v13, 0, sizeof(v13));
          if ( !(unsigned int)MsiLoadStringW((HMODULE)0xFFFFFFFFFFFFFFFFLL, 0) )
            Caption = 0;
          MessageBoxW(0, &Text, &Caption, 0x200000u);
        }
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 792));
    return 0;
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 792));
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x1801ab300  mov     [rsp+arg_10], rbx
0x1801ab305  mov     [rsp+arg_18], rsi
0x1801ab30a  push    rdi
0x1801ab30b  push    r14
0x1801ab30d  push    r15
0x1801ab30f  sub     rsp, 310h
0x1801ab316  mov     rax, cs:__security_cookie
0x1801ab31d  xor     rax, rsp
0x1801ab320  mov     [rsp+328h+var_28], rax
0x1801ab328  mov     r15b, r8b
0x1801ab32b  mov     rbx, rdx
0x1801ab32e  mov     rdi, rcx
0x1801ab331  mov     [rsp+328h+var_2C0], rcx
0x1801ab336  call    ?WaitForCAMainThread@CMsiCustomAction@@AEAAXXZ; CMsiCustomAction::WaitForCAMainThread(void)
0x1801ab33b  lea     rsi, [rdi+318h]
0x1801ab342  mov     rcx, rsi; lpCriticalSection
0x1801ab345  call    cs:__imp_EnterCriticalSection
0x1801ab34b  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801ab352  jz      short loc_1801AB396
0x1801ab354  xor     edx, edx; unsigned __int16
0x1801ab356  mov     [rsp+328h+var_2D0], rdx; void *
0x1801ab35b  mov     [rsp+328h+var_2D8], edx; unsigned int
0x1801ab35f  lea     rax, aNull; "(NULL)"
0x1801ab366  mov     [rsp+328h+var_2E0], rax; unsigned __int16 *
0x1801ab36b  mov     [rsp+328h+var_2E8], rax; unsigned __int16 *
0x1801ab370  mov     [rsp+328h+var_2F0], rax; unsigned __int16 *
0x1801ab375  mov     [rsp+328h+var_2F8], rax; unsigned __int16 *
0x1801ab37a  mov     [rsp+328h+var_300], rax; unsigned __int16 *
0x1801ab37f  mov     [rsp+328h+var_308], rbx; unsigned __int16 *
0x1801ab384  lea     r9, aEeuiCustomActi_0; "EEUI - Custom action server trying to l"...
0x1801ab38b  xor     r8d, r8d; int
0x1801ab38e  lea     ecx, [rdx+9]; int
0x1801ab391  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801ab396  mov     ecx, 1; uMode
0x1801ab39b  call    cs:__imp_SetErrorMode
0x1801ab3a1  mov     r14d, eax
0x1801ab3a4  mov     [rsp+328h+uMode], eax
0x1801ab3a8  mov     rcx, rbx; lpLibFileName
0x1801ab3ab  call    IsolationAwareLoadLibraryW
0x1801ab3b0  mov     rbx, rax
0x1801ab3b3  mov     [rsp+328h+var_2B8], rax
0x1801ab3b8  mov     ecx, r14d; uMode
0x1801ab3bb  call    cs:__imp_SetErrorMode
0x1801ab3c1  test    rbx, rbx
0x1801ab3c4  jnz     short loc_1801AB3D9
0x1801ab3c6  mov     rcx, rsi; lpCriticalSection
0x1801ab3c9  call    cs:__imp_LeaveCriticalSection
0x1801ab3cf  mov     eax, 80004005h
0x1801ab3d4  jmp     loc_1801AB588
0x1801ab3d9  mov     [rdi+310h], rbx
0x1801ab3e0  lea     rdx, aInitializeembe; "InitializeEmbeddedUI"
0x1801ab3e7  mov     rcx, rbx; hModule
0x1801ab3ea  call    cs:__imp_GetProcAddress
0x1801ab3f0  mov     [rdi+2F8h], rax
0x1801ab3f7  lea     rdx, aShutdownembedd; "ShutdownEmbeddedUI"
0x1801ab3fe  mov     rcx, rbx; hModule
0x1801ab401  call    cs:__imp_GetProcAddress
0x1801ab407  mov     [rdi+300h], rax
0x1801ab40e  lea     rdx, aEmbeddeduihand; "EmbeddedUIHandler"
0x1801ab415  mov     rcx, rbx; hModule
0x1801ab418  call    cs:__imp_GetProcAddress
0x1801ab41e  mov     [rdi+308h], rax
0x1801ab425  test    r15b, r15b
0x1801ab428  jz      loc_1801AB4F1
0x1801ab42e  call    cs:__imp_IsDebuggerPresent
0x1801ab434  test    eax, eax
0x1801ab436  jnz     loc_1801AB4F1
0x1801ab43c  mov     [rsp+328h+Text], ax
0x1801ab444  xor     edx, edx; Val
0x1801ab446  mov     r8d, 1FEh; Size
0x1801ab44c  lea     rcx, [rsp+328h+var_226]; void *
0x1801ab454  call    memset_0
0x1801ab459  call    cs:__imp_GetCurrentProcessId
0x1801ab45f  mov     ebx, eax
0x1801ab461  call    cs:__imp_GetCurrentProcessId
0x1801ab467  mov     dword ptr [rsp+328h+var_308], ebx
0x1801ab46b  mov     r9d, eax
0x1801ab46e  lea     r8, aToDebugEmbedde; "To debug Embedded UI, attach your debug"...
0x1801ab475  mov     edx, 100h; unsigned __int64
0x1801ab47a  lea     rcx, [rsp+328h+Text]; unsigned __int16 *
0x1801ab482  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801ab487  test    eax, eax
0x1801ab489  js      short loc_1801AB4F1
0x1801ab48b  xor     eax, eax
0x1801ab48d  mov     [rsp+328h+Caption], ax
0x1801ab495  xor     edx, edx; Val
0x1801ab497  lea     r8d, [rax+7Eh]; Size
0x1801ab49b  lea     rcx, [rsp+328h+var_2A6]; void *
0x1801ab4a3  call    memset_0
0x1801ab4a8  xor     eax, eax
0x1801ab4aa  mov     word ptr [rsp+328h+var_308], ax; unsigned __int16
0x1801ab4af  lea     r9d, [rax+40h]
0x1801ab4b3  lea     r8, [rsp+328h+Caption]
0x1801ab4bb  lea     edx, [rax+1Ch]
0x1801ab4be  or      rcx, 0FFFFFFFFFFFFFFFFh; hModule
0x1801ab4c2  call    MsiLoadStringW
0x1801ab4c7  test    eax, eax
0x1801ab4c9  jnz     short loc_1801AB4D3
0x1801ab4cb  mov     [rsp+328h+Caption], ax
0x1801ab4d3  mov     r9d, 200000h; uType
0x1801ab4d9  lea     r8, [rsp+328h+Caption]; lpCaption
0x1801ab4e1  lea     rdx, [rsp+328h+Text]; lpText
0x1801ab4e9  xor     ecx, ecx; hWnd
0x1801ab4eb  call    cs:__imp_MessageBoxW
0x1801ab4f1  mov     rcx, rsi; lpCriticalSection
0x1801ab4f4  call    cs:__imp_LeaveCriticalSection
0x1801ab4fa  xor     eax, eax
0x1801ab4fc  jmp     loc_1801AB588
0x1801ab501  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801ab508  jz      short loc_1801AB567
0x1801ab50a  mov     eax, eax
0x1801ab50c  xor     edx, edx; unsigned __int16
0x1801ab50e  mov     [rsp+328h+var_2D0], rdx; void *
0x1801ab513  mov     [rsp+328h+var_2D8], edx; unsigned int
0x1801ab517  lea     rcx, aNull; "(NULL)"
0x1801ab51e  mov     [rsp+328h+var_2E0], rcx; unsigned __int16 *
0x1801ab523  lea     rcx, aNull; "(NULL)"
0x1801ab52a  mov     [rsp+328h+var_2E8], rcx; unsigned __int16 *
0x1801ab52f  lea     rcx, aNull; "(NULL)"
0x1801ab536  mov     [rsp+328h+var_2F0], rcx; unsigned __int16 *
0x1801ab53b  lea     rcx, aNull; "(NULL)"
0x1801ab542  mov     [rsp+328h+var_2F8], rcx; unsigned __int16 *
0x1801ab547  mov     [rsp+328h+var_300], 643h; unsigned __int16 *
0x1801ab550  mov     [rsp+328h+var_308], rax; unsigned __int16 *
0x1801ab555  lea     r9, aEeuiCustomActi_1; "EEUI - Custom action server threw an ex"...
0x1801ab55c  xor     r8d, r8d; int
0x1801ab55f  lea     ecx, [rdx+9]; int
0x1801ab562  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801ab567  mov     ecx, [rsp+328h+uMode]; uMode
0x1801ab56b  call    cs:__imp_SetErrorMode
0x1801ab571  mov     rcx, [rsp+328h+var_2C0]
0x1801ab576  add     rcx, 318h; lpCriticalSection
0x1801ab57d  call    cs:__imp_LeaveCriticalSection
0x1801ab583  mov     eax, 80004005h
0x1801ab588  mov     rcx, [rsp+328h+var_28]
0x1801ab590  xor     rcx, rsp; StackCookie
0x1801ab593  call    __security_check_cookie
0x1801ab598  lea     r11, [rsp+328h+var_18]
0x1801ab5a0  mov     rbx, [r11+30h]
0x1801ab5a4  mov     rsi, [r11+38h]
0x1801ab5a8  mov     rsp, r11
0x1801ab5ab  pop     r15
0x1801ab5ad  pop     r14
0x1801ab5af  pop     rdi
0x1801ab5b0  retn
0x18025b176  push    rbp
0x18025b178  sub     rsp, 60h
0x18025b17c  mov     rbp, rdx
0x18025b17f  call    ?CustomActionExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; CustomActionExceptionFilter(_EXCEPTION_POINTERS *)
0x18025b184  nop
0x18025b185  add     rsp, 60h
0x18025b189  pop     rbp
0x18025b18a  retn
```

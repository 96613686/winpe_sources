# CMemoryDiagnosticHandler::AdjustPrivilege(ushort const *,int)

- ea: `0x18001a3e4`
- end: `0x18001a597`
- name: `?AdjustPrivilege@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z`
- size: `435`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001d094`

## callees

- `0x180002e50`
- `0x18001a3e4`
- `0x18001e21c`
- `0x18001e24c`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18001a417`
- `KERNEL32!GetCurrentProcess` at `0x18001a417`
- `KERNEL32!CloseHandle` at `0x18001a541`
- `KERNEL32!CloseHandle` at `0x18001a541`
- `KERNEL32!GetLastError` at `0x18001a43b`
- `KERNEL32!GetLastError` at `0x18001a494`
- `KERNEL32!GetLastError` at `0x18001a4f3`
- `KERNEL32!GetLastError` at `0x18001a43b`
- `KERNEL32!GetLastError` at `0x18001a494`
- `KERNEL32!GetLastError` at `0x18001a4f3`
- `ADVAPI32!OpenProcessToken` at `0x18001a42a`
- `ADVAPI32!OpenProcessToken` at `0x18001a42a`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18001a4e9`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18001a4e9`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18001a48a`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18001a48a`

## string_xrefs

- `0x18001a481`: `SeProfileSingleProcessPrivilege`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::AdjustPrivilege(
        CMemoryDiagnosticHandler *this,
        const unsigned __int16 *a2,
        int a3)
{
  HANDLE CurrentProcess; // rax
  signed int v5; // eax
  __int64 v6; // r8
  unsigned int v7; // ebx
  CMemoryDiagnosticHandler *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    Luid[0].LowPart = 1;
    if ( LookupPrivilegeValueW(0, L"SeProfileSingleProcessPrivilege", (PLUID)&Luid[0].HighPart) )
    {
      v7 = 0;
      Luid[1].HighPart = a3 != 0 ? 2 : 0;
      if ( AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0x10u, 0, 0) )
      {
LABEL_20:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_21;
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 13;
        goto LABEL_19;
      }
    }
    else
    {
      v10 = GetLastError();
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 12;
        goto LABEL_19;
      }
    }
  }
  else
  {
    v5 = GetLastError();
    v7 = v5;
    if ( v5 > 0 )
      v7 = (unsigned __int16)v5 | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 11;
LABEL_19:
      WPP_SF_(*((_QWORD *)v8 + 2), v9);
      goto LABEL_20;
    }
  }
LABEL_21:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    v8 = WPP_GLOBAL_Control;
    TokenHandle = (void *)-1LL;
  }
  if ( (v7 & 0x80000000) != 0 && v8 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v8 + 2), 10, v6, v7);
  return v7;
}

```

## disassembly

```asm
0x18001a3e4  mov     [rsp+arg_0], rbx
0x18001a3e9  mov     [rsp+arg_8], rdi
0x18001a3ee  push    r14
0x18001a3f0  sub     rsp, 50h
0x18001a3f4  mov     rax, cs:__security_cookie
0x18001a3fb  xor     rax, rsp
0x18001a3fe  mov     [rsp+58h+var_10], rax
0x18001a403  xorps   xmm0, xmm0
0x18001a406  mov     [rsp+58h+TokenHandle], 0
0x18001a40f  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x18001a414  mov     edi, r8d
0x18001a417  call    cs:__imp_GetCurrentProcess
0x18001a41d  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18001a422  mov     edx, 28h ; '('; DesiredAccess
0x18001a427  mov     rcx, rax; ProcessHandle
0x18001a42a  call    cs:__imp_OpenProcessToken
0x18001a430  lea     r14, WPP_GLOBAL_Control
0x18001a437  test    eax, eax
0x18001a439  jnz     short loc_18001A474
0x18001a43b  call    cs:__imp_GetLastError
0x18001a441  mov     ebx, eax
0x18001a443  test    eax, eax
0x18001a445  jle     short loc_18001A450
0x18001a447  movzx   ebx, ax
0x18001a44a  or      ebx, 80070000h
0x18001a450  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a457  cmp     rcx, r14
0x18001a45a  jz      loc_18001A52F
0x18001a460  test    byte ptr [rcx+1Ch], 1
0x18001a464  jz      loc_18001A52F
0x18001a46a  mov     edx, 0Bh
0x18001a46f  jmp     loc_18001A51F
0x18001a474  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x18001a479  mov     [rsp+58h+Luid.LowPart], 1
0x18001a481  lea     rdx, Name; "SeProfileSingleProcessPrivilege"
0x18001a488  xor     ecx, ecx; lpSystemName
0x18001a48a  call    cs:__imp_LookupPrivilegeValueW
0x18001a490  test    eax, eax
0x18001a492  jnz     short loc_18001A4C2
0x18001a494  call    cs:__imp_GetLastError
0x18001a49a  mov     ebx, eax
0x18001a49c  test    eax, eax
0x18001a49e  jle     short loc_18001A4A9
0x18001a4a0  movzx   ebx, ax
0x18001a4a3  or      ebx, 80070000h
0x18001a4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4b0  cmp     rcx, r14
0x18001a4b3  jz      short loc_18001A52F
0x18001a4b5  test    byte ptr [rcx+1Ch], 1
0x18001a4b9  jz      short loc_18001A52F
0x18001a4bb  mov     edx, 0Ch
0x18001a4c0  jmp     short loc_18001A51F
0x18001a4c2  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18001a4c7  lea     r8, [rsp+58h+Luid]; NewState
0x18001a4cc  xor     ebx, ebx
0x18001a4ce  neg     edi
0x18001a4d0  mov     [rsp+58h+ReturnLength], rbx; ReturnLength
0x18001a4d5  mov     [rsp+58h+PreviousState], rbx; PreviousState
0x18001a4da  sbb     eax, eax
0x18001a4dc  xor     edx, edx; DisableAllPrivileges
0x18001a4de  and     eax, 2
0x18001a4e1  lea     r9d, [rbx+10h]; BufferLength
0x18001a4e5  mov     [rsp+58h+Luid.HighPart+8], eax
0x18001a4e9  call    cs:__imp_AdjustTokenPrivileges
0x18001a4ef  test    eax, eax
0x18001a4f1  jnz     short loc_18001A528
0x18001a4f3  call    cs:__imp_GetLastError
0x18001a4f9  mov     ebx, eax
0x18001a4fb  test    eax, eax
0x18001a4fd  jle     short loc_18001A508
0x18001a4ff  movzx   ebx, ax
0x18001a502  or      ebx, 80070000h
0x18001a508  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a50f  cmp     rcx, r14
0x18001a512  jz      short loc_18001A52F
0x18001a514  test    byte ptr [rcx+1Ch], 1
0x18001a518  jz      short loc_18001A52F
0x18001a51a  mov     edx, 0Dh
0x18001a51f  mov     rcx, [rcx+10h]
0x18001a523  call    WPP_SF_
0x18001a528  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a52f  mov     rdx, [rsp+58h+TokenHandle]
0x18001a534  lea     rax, [rdx-1]
0x18001a538  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a53c  ja      short loc_18001A557
0x18001a53e  mov     rcx, rdx; hObject
0x18001a541  call    cs:__imp_CloseHandle
0x18001a547  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a54e  mov     [rsp+58h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001a557  test    ebx, ebx
0x18001a559  jns     short loc_18001A577
0x18001a55b  cmp     rcx, r14
0x18001a55e  jz      short loc_18001A577
0x18001a560  test    byte ptr [rcx+1Ch], 1
0x18001a564  jz      short loc_18001A577
0x18001a566  mov     rcx, [rcx+10h]
0x18001a56a  mov     edx, 0Ah
0x18001a56f  mov     r9d, ebx
0x18001a572  call    WPP_SF_d
0x18001a577  mov     eax, ebx
0x18001a579  mov     rcx, [rsp+58h+var_10]
0x18001a57e  xor     rcx, rsp; StackCookie
0x18001a581  call    __security_check_cookie
0x18001a586  mov     rbx, [rsp+58h+arg_0]
0x18001a58b  mov     rdi, [rsp+58h+arg_8]
0x18001a590  add     rsp, 50h
0x18001a594  pop     r14
0x18001a596  retn
```

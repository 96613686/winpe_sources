# CMemoryDiagnosticHandler::AdjustPrivilege(ushort const *,int)

- ea: `0x18001b364`
- end: `0x18001b549`
- name: `?AdjustPrivilege@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z`
- size: `485`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001e31c`

## callees

- `0x1800026b0`
- `0x18001b364`
- `0x18001f560`
- `0x18001f594`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18001b395`
- `KERNEL32!GetCurrentProcess` at `0x18001b395`
- `KERNEL32!CloseHandle` at `0x18001b4ef`
- `KERNEL32!CloseHandle` at `0x18001b4ef`
- `KERNEL32!GetLastError` at `0x18001b3c3`
- `KERNEL32!GetLastError` at `0x18001b428`
- `KERNEL32!GetLastError` at `0x18001b49b`
- `KERNEL32!GetLastError` at `0x18001b3c3`
- `KERNEL32!GetLastError` at `0x18001b428`
- `KERNEL32!GetLastError` at `0x18001b49b`
- `ADVAPI32!OpenProcessToken` at `0x18001b3ac`
- `ADVAPI32!OpenProcessToken` at `0x18001b3ac`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18001b48b`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18001b48b`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18001b418`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18001b418`

## string_xrefs

- `0x18001b40f`: `SeProfileSingleProcessPrivilege`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::AdjustPrivilege(
        CMemoryDiagnosticHandler *this,
        const unsigned __int16 *a2,
        int a3)
{
  unsigned int v3; // ebx
  HANDLE CurrentProcess; // rax
  signed int v6; // eax
  __int64 v7; // r8
  CMemoryDiagnosticHandler *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  v3 = 0;
  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    Luid[0].LowPart = 1;
    if ( LookupPrivilegeValueW(0, L"SeProfileSingleProcessPrivilege", (PLUID)&Luid[0].HighPart) )
    {
      Luid[1].HighPart = a3 != 0 ? 2 : 0;
      if ( AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0x10u, 0, 0) )
      {
LABEL_20:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_21;
      }
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
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
      v3 = v10;
      if ( v10 > 0 )
        v3 = (unsigned __int16)v10 | 0x80070000;
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
    v6 = GetLastError();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
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
    TokenHandle = (void *)-1LL;
    v8 = WPP_GLOBAL_Control;
  }
  if ( (v3 & 0x80000000) != 0 && v8 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)v8 + 2), 10, v7, v3);
  return v3;
}

```

## disassembly

```asm
0x18001b364  mov     [rsp+arg_0], rbx
0x18001b369  mov     [rsp+arg_8], rdi
0x18001b36e  push    r14
0x18001b370  sub     rsp, 50h
0x18001b374  mov     rax, cs:__security_cookie
0x18001b37b  xor     rax, rsp
0x18001b37e  mov     [rsp+58h+var_10], rax
0x18001b383  xorps   xmm0, xmm0
0x18001b386  xor     ebx, ebx
0x18001b388  and     [rsp+58h+TokenHandle], rbx
0x18001b38d  mov     edi, r8d
0x18001b390  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x18001b395  call    cs:__imp_GetCurrentProcess
0x18001b39c  nop     dword ptr [rax+rax+00h]
0x18001b3a1  mov     rcx, rax; ProcessHandle
0x18001b3a4  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18001b3a9  lea     edx, [rbx+28h]; DesiredAccess
0x18001b3ac  call    cs:__imp_OpenProcessToken
0x18001b3b3  nop     dword ptr [rax+rax+00h]
0x18001b3b8  lea     r14, WPP_GLOBAL_Control
0x18001b3bf  test    eax, eax
0x18001b3c1  jnz     short loc_18001B402
0x18001b3c3  call    cs:__imp_GetLastError
0x18001b3ca  nop     dword ptr [rax+rax+00h]
0x18001b3cf  mov     ebx, eax
0x18001b3d1  test    eax, eax
0x18001b3d3  jle     short loc_18001B3DE
0x18001b3d5  movzx   ebx, ax
0x18001b3d8  or      ebx, 80070000h
0x18001b3de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3e5  cmp     rcx, r14
0x18001b3e8  jz      loc_18001B4DD
0x18001b3ee  test    byte ptr [rcx+1Ch], 1
0x18001b3f2  jz      loc_18001B4DD
0x18001b3f8  mov     edx, 0Bh
0x18001b3fd  jmp     loc_18001B4CD
0x18001b402  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x18001b407  mov     [rsp+58h+Luid.LowPart], 1
0x18001b40f  lea     rdx, Name; "SeProfileSingleProcessPrivilege"
0x18001b416  xor     ecx, ecx; lpSystemName
0x18001b418  call    cs:__imp_LookupPrivilegeValueW
0x18001b41f  nop     dword ptr [rax+rax+00h]
0x18001b424  test    eax, eax
0x18001b426  jnz     short loc_18001B464
0x18001b428  call    cs:__imp_GetLastError
0x18001b42f  nop     dword ptr [rax+rax+00h]
0x18001b434  mov     ebx, eax
0x18001b436  test    eax, eax
0x18001b438  jle     short loc_18001B443
0x18001b43a  movzx   ebx, ax
0x18001b43d  or      ebx, 80070000h
0x18001b443  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b44a  cmp     rcx, r14
0x18001b44d  jz      loc_18001B4DD
0x18001b453  test    byte ptr [rcx+1Ch], 1
0x18001b457  jz      loc_18001B4DD
0x18001b45d  mov     edx, 0Ch
0x18001b462  jmp     short loc_18001B4CD
0x18001b464  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18001b469  lea     r8, [rsp+58h+Luid]; NewState
0x18001b46e  neg     edi
0x18001b470  mov     r9d, 10h; BufferLength
0x18001b476  sbb     eax, eax
0x18001b478  and     [rsp+58h+var_30], rbx
0x18001b47d  and     [rsp+58h+var_38], rbx
0x18001b482  and     eax, 2
0x18001b485  xor     edx, edx; DisableAllPrivileges
0x18001b487  mov     [rsp+58h+Luid.HighPart+8], eax
0x18001b48b  call    cs:__imp_AdjustTokenPrivileges
0x18001b492  nop     dword ptr [rax+rax+00h]
0x18001b497  test    eax, eax
0x18001b499  jnz     short loc_18001B4D6
0x18001b49b  call    cs:__imp_GetLastError
0x18001b4a2  nop     dword ptr [rax+rax+00h]
0x18001b4a7  mov     ebx, eax
0x18001b4a9  test    eax, eax
0x18001b4ab  jle     short loc_18001B4B6
0x18001b4ad  movzx   ebx, ax
0x18001b4b0  or      ebx, 80070000h
0x18001b4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4bd  cmp     rcx, r14
0x18001b4c0  jz      short loc_18001B4DD
0x18001b4c2  test    byte ptr [rcx+1Ch], 1
0x18001b4c6  jz      short loc_18001B4DD
0x18001b4c8  mov     edx, 0Dh
0x18001b4cd  mov     rcx, [rcx+10h]
0x18001b4d1  call    WPP_SF_
0x18001b4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4dd  mov     rdx, [rsp+58h+TokenHandle]
0x18001b4e2  lea     rax, [rdx-1]
0x18001b4e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b4ea  ja      short loc_18001B508
0x18001b4ec  mov     rcx, rdx; hObject
0x18001b4ef  call    cs:__imp_CloseHandle
0x18001b4f6  nop     dword ptr [rax+rax+00h]
0x18001b4fb  or      [rsp+58h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001b501  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b508  test    ebx, ebx
0x18001b50a  jns     short loc_18001B528
0x18001b50c  cmp     rcx, r14
0x18001b50f  jz      short loc_18001B528
0x18001b511  test    byte ptr [rcx+1Ch], 1
0x18001b515  jz      short loc_18001B528
0x18001b517  mov     rcx, [rcx+10h]
0x18001b51b  mov     edx, 0Ah
0x18001b520  mov     r9d, ebx
0x18001b523  call    WPP_SF_D
0x18001b528  mov     eax, ebx
0x18001b52a  mov     rcx, [rsp+58h+var_10]
0x18001b52f  xor     rcx, rsp; StackCookie
0x18001b532  call    __security_check_cookie
0x18001b537  mov     rbx, [rsp+58h+arg_0]
0x18001b53c  mov     rdi, [rsp+58h+arg_8]
0x18001b541  add     rsp, 50h
0x18001b545  pop     r14
0x18001b547  retn
```

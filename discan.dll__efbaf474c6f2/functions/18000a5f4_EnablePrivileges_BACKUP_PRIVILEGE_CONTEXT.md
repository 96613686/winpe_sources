# EnablePrivileges(_BACKUP_PRIVILEGE_CONTEXT *)

- ea: `0x18000a5f4`
- end: `0x18000aae5`
- name: `?EnablePrivileges@@YAJPEAU_BACKUP_PRIVILEGE_CONTEXT@@@Z`
- size: `1265`
- prototype: `__int64 __fastcall(struct _BACKUP_PRIVILEGE_CONTEXT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800168dc`

## callees

- `0x1800031a0`
- `0x1800032f8`
- `0x180006470`
- `0x180006498`
- `0x180006688`
- `0x18000a5f4`
- `0x1800128c8`
- `0x180037620`

## import_xrefs

- `ADVAPI32!AdjustTokenPrivileges` at `0x18000aa13`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000aa13`
- `ADVAPI32!PrivilegeCheck` at `0x18000a8e1`
- `ADVAPI32!PrivilegeCheck` at `0x18000a8e1`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000a84b`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000a84b`
- `ADVAPI32!OpenProcessToken` at `0x18000a769`
- `ADVAPI32!OpenProcessToken` at `0x18000a769`
- `ADVAPI32!OpenThreadToken` at `0x18000a6fb`
- `ADVAPI32!OpenThreadToken` at `0x18000a6fb`
- `KERNEL32!GetLastError` at `0x18000a709`
- `KERNEL32!GetLastError` at `0x18000a777`
- `KERNEL32!GetLastError` at `0x18000a862`
- `KERNEL32!GetLastError` at `0x18000a8eb`
- `KERNEL32!GetLastError` at `0x18000aa1d`
- `KERNEL32!GetLastError` at `0x18000a709`
- `KERNEL32!GetLastError` at `0x18000a777`
- `KERNEL32!GetLastError` at `0x18000a862`
- `KERNEL32!GetLastError` at `0x18000a8eb`
- `KERNEL32!GetLastError` at `0x18000aa1d`
- `KERNEL32!GetCurrentThread` at `0x18000a6e5`
- `KERNEL32!GetCurrentThread` at `0x18000a6e5`
- `KERNEL32!GetCurrentProcess` at `0x18000a75a`
- `KERNEL32!GetCurrentProcess` at `0x18000a75a`

## string_xrefs

- `0x18000a629`: `EnablePrivileges`

## pseudocode

```c
__int64 __fastcall EnablePrivileges(struct _BACKUP_PRIVILEGE_CONTEXT *a1)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v4; // rdx
  USHORT v5; // dx
  USHORT v6; // ax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v9; // ebx
  HANDLE CurrentProcess; // rax
  signed int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // rdi
  signed int v16; // eax
  signed int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  signed int v20; // eax
  void *v21; // rax
  WINBOOL pfResult; // [rsp+30h] [rbp-69h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-61h] BYREF
  int v25; // [rsp+40h] [rbp-59h]
  char v26; // [rsp+44h] [rbp-55h]
  const char *v27; // [rsp+48h] [rbp-51h] BYREF
  int v28; // [rsp+50h] [rbp-49h]
  USHORT v29; // [rsp+58h] [rbp-41h]
  USHORT v30; // [rsp+5Ah] [rbp-3Fh]
  int v31; // [rsp+5Ch] [rbp-3Dh]
  char *v32; // [rsp+60h] [rbp-39h]
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+68h] [rbp-31h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+98h] [rbp-1h] BYREF
  __int128 v35; // [rsp+A8h] [rbp+Fh]
  __int64 v36; // [rsp+B8h] [rbp+1Fh]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v27 = "EnablePrivileges";
  v28 = 0;
  v4 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v4 + 16) = "EnablePrivileges";
  v5 = ++*(_WORD *)(v4 + 8);
  v6 = Length;
  if ( v5 < Length )
  {
    v6 = v5;
    Length = v5;
  }
  v29 = v6;
  v31 = 0;
  v32 = off_180047060;
  v30 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"EnablePrivileges");
  }
  TokenHandle = 0;
  *((_DWORD *)a1 + 4) = 0;
  v25 = 0;
  v26 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v28 = v9;
    if ( v9 != -2147023888 )
    {
      if ( v9 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 12;
          goto LABEL_28;
        }
      }
      goto LABEL_73;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids);
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      v11 = GetLastError();
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      v28 = v9;
      if ( v9 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 11;
LABEL_28:
          WPP_SF_d(v12[2], v13, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, (unsigned int)v9);
          goto LABEL_73;
        }
      }
      goto LABEL_73;
    }
  }
  v14 = 0;
  memset(RequiredPrivileges.Privilege, 0, 36);
  RequiredPrivileges.PrivilegeCount = 3;
  RequiredPrivileges.Control = 1;
  while ( (unsigned int)v14 < 3 )
  {
    v15 = (unsigned int)v14;
    if ( !LookupPrivilegeValueW(0, (LPCWSTR)(&RequiredPrivilegeNames)[v14], &RequiredPrivileges.Privilege[v14].Luid) )
    {
      v16 = GetLastError();
      v9 = v16;
      if ( v16 > 0 )
        v9 = (unsigned __int16)v16 | 0x80070000;
      v28 = v9;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
          (unsigned int)(&RequiredPrivilegeNames)[v15],
          v9);
      }
      goto LABEL_73;
    }
    RequiredPrivileges.Privilege[v14].Attributes = 0x80000000;
    v14 = (unsigned int)(v14 + 1);
  }
  pfResult = 0;
  if ( PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult) )
  {
    if ( pfResult )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids);
      }
      v28 = 1;
      v9 = 1;
      goto LABEL_73;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids);
    }
  }
  else
  {
    v17 = GetLastError();
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
        (unsigned int)v17);
    }
  }
  v18 = 0;
  v36 = 0;
  NewState = 0;
  NewState.PrivilegeCount = 3;
  v19 = 0;
  v35 = 0;
  do
  {
    ++v18;
    NewState.Privileges[v19].Luid = RequiredPrivileges.Privilege[v19].Luid;
    NewState.Privileges[v19++].Attributes = 2;
  }
  while ( v18 != 3 );
  if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x28u, (PTOKEN_PRIVILEGES)((char *)a1 + 20), (PDWORD)a1 + 4) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids);
    }
    if ( !v26 || (v21 = 0, !v25) )
    {
      v21 = TokenHandle;
      TokenHandle = 0;
    }
    *(_QWORD *)a1 = v21;
    v9 = 0;
    v28 = 0;
  }
  else
  {
    v20 = GetLastError();
    v9 = v20;
    if ( v20 > 0 )
      v9 = (unsigned __int16)v20 | 0x80070000;
    v28 = v9;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 17;
      goto LABEL_28;
    }
  }
LABEL_73:
  CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(&TokenHandle);
  CHResultImp::~CHResultImp((CHResultImp *)&v27);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a5f4  mov     [rsp-8+arg_8], rbx
0x18000a5f9  mov     [rsp-8+arg_10], rsi
0x18000a5fe  push    rbp
0x18000a5ff  push    rdi
0x18000a600  push    r13
0x18000a602  push    r14
0x18000a604  push    r15
0x18000a606  lea     rbp, [rsp-37h]
0x18000a60b  sub     rsp, 0D0h
0x18000a612  mov     rax, cs:__security_cookie
0x18000a619  xor     rax, rsp
0x18000a61c  mov     [rbp+57h+var_30], rax
0x18000a620  mov     rax, gs:58h
0x18000a629  lea     r8, aEnableprivileg; "EnablePrivileges"
0x18000a630  mov     edx, cs:_tls_index
0x18000a636  mov     r14, rcx
0x18000a639  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18000a640  mov     r13d, 1
0x18000a646  mov     [rbp+57h+var_A8], r8
0x18000a64a  mov     [rbp+57h+var_A0], 0
0x18000a651  mov     rdx, [rax+rdx*8]
0x18000a655  mov     eax, 10h
0x18000a65a  mov     [rax+rdx], r8
0x18000a65e  mov     eax, 8
0x18000a663  add     [rax+rdx], r13w
0x18000a668  movzx   edx, word ptr [rax+rdx]
0x18000a66c  movzx   eax, cx
0x18000a66f  cmp     dx, cx
0x18000a672  cmovb   ax, dx
0x18000a676  cmovb   cx, dx
0x18000a67a  mov     [rbp+57h+var_98], ax
0x18000a67e  xor     eax, eax
0x18000a680  mov     [rbp+57h+var_94], eax
0x18000a683  mov     rax, cs:off_180047060; "                                       "...
0x18000a68a  mov     [rbp+57h+var_90], rax
0x18000a68e  mov     [rbp+57h+var_96], cx
0x18000a692  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a699  lea     rdi, WPP_GLOBAL_Control
0x18000a6a0  cmp     rcx, rdi
0x18000a6a3  jz      short loc_18000A6C7
0x18000a6a5  test    [rcx+1Ch], r13b
0x18000a6a9  jz      short loc_18000A6C7
0x18000a6ab  cmp     byte ptr [rcx+19h], 5
0x18000a6af  jb      short loc_18000A6C7
0x18000a6b1  mov     rcx, [rcx+10h]; LoggerHandle
0x18000a6b5  lea     edx, [r13+0Ch]
0x18000a6b9  lea     r9, [rbp+57h+var_98]
0x18000a6bd  mov     [rsp+0F0h+PreviousState], r8; __int64
0x18000a6c2  call    WPP_SF_aZs
0x18000a6c7  lea     r15, [r14+10h]
0x18000a6cb  mov     [rbp+57h+TokenHandle], 0
0x18000a6d3  mov     dword ptr [r15], 0
0x18000a6da  mov     [rbp+57h+var_B0], 0
0x18000a6e1  mov     [rbp+57h+var_AC], 0
0x18000a6e5  call    cs:__imp_GetCurrentThread
0x18000a6eb  xor     r8d, r8d; OpenAsSelf
0x18000a6ee  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000a6f2  mov     rcx, rax; ThreadHandle
0x18000a6f5  lea     esi, [r8+28h]
0x18000a6f9  mov     edx, esi; DesiredAccess
0x18000a6fb  call    cs:__imp_OpenThreadToken
0x18000a701  test    eax, eax
0x18000a703  jnz     loc_18000A80B
0x18000a709  call    cs:__imp_GetLastError
0x18000a70f  mov     ebx, eax
0x18000a711  test    eax, eax
0x18000a713  jle     short loc_18000A71E
0x18000a715  movzx   ebx, ax
0x18000a718  or      ebx, 80070000h
0x18000a71e  mov     [rbp+57h+var_A0], ebx
0x18000a721  cmp     ebx, 800703F0h
0x18000a727  jnz     loc_18000A7C2
0x18000a72d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a734  cmp     rcx, rdi
0x18000a737  jz      short loc_18000A75A
0x18000a739  test    [rcx+1Ch], r13b
0x18000a73d  jz      short loc_18000A75A
0x18000a73f  cmp     byte ptr [rcx+19h], 4
0x18000a743  jb      short loc_18000A75A
0x18000a745  mov     rcx, [rcx+10h]
0x18000a749  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000a750  mov     edx, 0Ah
0x18000a755  call    WPP_SF_
0x18000a75a  call    cs:__imp_GetCurrentProcess
0x18000a760  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000a764  mov     edx, esi; DesiredAccess
0x18000a766  mov     rcx, rax; ProcessHandle
0x18000a769  call    cs:__imp_OpenProcessToken
0x18000a76f  test    eax, eax
0x18000a771  jnz     loc_18000A80B
0x18000a777  call    cs:__imp_GetLastError
0x18000a77d  mov     ebx, eax
0x18000a77f  test    eax, eax
0x18000a781  jle     short loc_18000A78C
0x18000a783  movzx   ebx, ax
0x18000a786  or      ebx, 80070000h
0x18000a78c  mov     [rbp+57h+var_A0], ebx
0x18000a78f  test    ebx, ebx
0x18000a791  jns     loc_18000AAA9
0x18000a797  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a79e  cmp     rcx, rdi
0x18000a7a1  jz      loc_18000AAA9
0x18000a7a7  test    [rcx+1Ch], r13b
0x18000a7ab  jz      loc_18000AAA9
0x18000a7b1  cmp     byte ptr [rcx+19h], 2
0x18000a7b5  jb      loc_18000AAA9
0x18000a7bb  mov     edx, 0Bh
0x18000a7c0  jmp     short loc_18000A7F3
0x18000a7c2  test    ebx, ebx
0x18000a7c4  jns     loc_18000AAA9
0x18000a7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7d1  cmp     rcx, rdi
0x18000a7d4  jz      loc_18000AAA9
0x18000a7da  test    [rcx+1Ch], r13b
0x18000a7de  jz      loc_18000AAA9
0x18000a7e4  cmp     byte ptr [rcx+19h], 2
0x18000a7e8  jb      loc_18000AAA9
0x18000a7ee  mov     edx, 0Ch
0x18000a7f3  mov     rcx, [rcx+10h]
0x18000a7f7  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000a7fe  mov     r9d, ebx
0x18000a801  call    WPP_SF_d
0x18000a806  jmp     loc_18000AAA9
0x18000a80b  xorps   xmm0, xmm0
0x18000a80e  xor     ebx, ebx
0x18000a810  movups  xmmword ptr [rbp+57h+RequiredPrivileges.PrivilegeCount], xmm0
0x18000a814  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], 3
0x18000a81b  movups  xmmword ptr [rbp+57h+RequiredPrivileges.Privilege.Attributes], xmm0
0x18000a81f  mov     [rbp+57h+RequiredPrivileges.Control], r13d
0x18000a823  movups  xmmword ptr [rbp+57h+RequiredPrivileges.Privilege.Attributes+0Ch], xmm0
0x18000a827  cmp     ebx, 3
0x18000a82a  jnb     loc_18000A8CE
0x18000a830  lea     rax, ?RequiredPrivilegeNames@@3PAPEBGA; ushort const * near * RequiredPrivilegeNames
0x18000a837  mov     edi, ebx
0x18000a839  mov     rdx, [rax+rbx*8]; lpName
0x18000a83d  lea     rsi, [rbx+rbx*2]
0x18000a841  lea     r8, [rbp+57h+RequiredPrivileges.Privilege]
0x18000a845  xor     ecx, ecx; lpSystemName
0x18000a847  lea     r8, [r8+rsi*4]; lpLuid
0x18000a84b  call    cs:__imp_LookupPrivilegeValueW
0x18000a851  test    eax, eax
0x18000a853  jz      short loc_18000A862
0x18000a855  mov     [rbp+rsi*4+57h+RequiredPrivileges.Privilege.Attributes], 80000000h
0x18000a85d  add     ebx, r13d
0x18000a860  jmp     short loc_18000A827
0x18000a862  call    cs:__imp_GetLastError
0x18000a868  mov     ebx, eax
0x18000a86a  test    eax, eax
0x18000a86c  jle     short loc_18000A877
0x18000a86e  movzx   ebx, ax
0x18000a871  or      ebx, 80070000h
0x18000a877  mov     [rbp+57h+var_A0], ebx
0x18000a87a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a881  lea     rax, WPP_GLOBAL_Control
0x18000a888  cmp     rcx, rax
0x18000a88b  jz      loc_18000AAA9
0x18000a891  test    [rcx+1Ch], r13b
0x18000a895  jz      loc_18000AAA9
0x18000a89b  cmp     byte ptr [rcx+19h], 2
0x18000a89f  jb      loc_18000AAA9
0x18000a8a5  mov     rcx, [rcx+10h]
0x18000a8a9  lea     r9, ?RequiredPrivilegeNames@@3PAPEBGA; ushort const * near * RequiredPrivilegeNames
0x18000a8b0  mov     r9, [r9+rdi*8]
0x18000a8b4  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000a8bb  mov     edx, 0Dh
0x18000a8c0  mov     dword ptr [rsp+0F0h+PreviousState], ebx
0x18000a8c4  call    WPP_SF_Sd
0x18000a8c9  jmp     loc_18000AAA9
0x18000a8ce  mov     rcx, [rbp+57h+TokenHandle]; ClientToken
0x18000a8d2  lea     r8, [rbp+57h+pfResult]; pfResult
0x18000a8d6  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x18000a8da  mov     [rbp+57h+pfResult], 0
0x18000a8e1  call    cs:__imp_PrivilegeCheck
0x18000a8e7  test    eax, eax
0x18000a8e9  jnz     short loc_18000A942
0x18000a8eb  call    cs:__imp_GetLastError
0x18000a8f1  test    eax, eax
0x18000a8f3  jle     short loc_18000A8FD
0x18000a8f5  movzx   eax, ax
0x18000a8f8  or      eax, 80070000h
0x18000a8fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a904  lea     rdi, WPP_GLOBAL_Control
0x18000a90b  cmp     rcx, rdi
0x18000a90e  jz      loc_18000A9BC
0x18000a914  test    [rcx+1Ch], r13b
0x18000a918  jz      loc_18000A9BC
0x18000a91e  cmp     byte ptr [rcx+19h], 2
0x18000a922  jb      loc_18000A9BC
0x18000a928  mov     rcx, [rcx+10h]
0x18000a92c  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000a933  mov     edx, 0Eh
0x18000a938  mov     r9d, eax
0x18000a93b  call    WPP_SF_d
0x18000a940  jmp     short loc_18000A9BC
0x18000a942  cmp     [rbp+57h+pfResult], 0
0x18000a946  jz      short loc_18000A988
0x18000a948  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a94f  lea     rax, WPP_GLOBAL_Control
0x18000a956  cmp     rcx, rax
0x18000a959  jz      short loc_18000A97C
0x18000a95b  test    [rcx+1Ch], r13b
0x18000a95f  jz      short loc_18000A97C
0x18000a961  cmp     byte ptr [rcx+19h], 4
0x18000a965  jb      short loc_18000A97C
0x18000a967  mov     rcx, [rcx+10h]
0x18000a96b  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000a972  mov     edx, 0Fh
0x18000a977  call    WPP_SF_
0x18000a97c  mov     [rbp+57h+var_A0], r13d
0x18000a980  mov     ebx, r13d
0x18000a983  jmp     loc_18000AAA9
0x18000a988  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a98f  lea     rdi, WPP_GLOBAL_Control
0x18000a996  cmp     rcx, rdi
0x18000a999  jz      short loc_18000A9BC
0x18000a99b  test    [rcx+1Ch], r13b
0x18000a99f  jz      short loc_18000A9BC
0x18000a9a1  cmp     byte ptr [rcx+19h], 4
0x18000a9a5  jb      short loc_18000A9BC
0x18000a9a7  mov     rcx, [rcx+10h]
0x18000a9ab  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000a9b2  mov     edx, 10h
0x18000a9b7  call    WPP_SF_
0x18000a9bc  xorps   xmm0, xmm0
0x18000a9bf  xor     eax, eax
0x18000a9c1  xor     edx, edx
0x18000a9c3  mov     [rbp+57h+var_38], rax
0x18000a9c7  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x18000a9cb  mov     [rbp+57h+NewState.PrivilegeCount], 3
0x18000a9d2  xor     ecx, ecx
0x18000a9d4  movups  [rbp+57h+var_48], xmm0
0x18000a9d8  mov     rax, qword ptr [rbp+rcx+57h+RequiredPrivileges.Privilege.Luid.LowPart]
0x18000a9dd  add     rdx, r13
0x18000a9e0  mov     qword ptr [rbp+rcx+57h+NewState.Privileges.Luid.LowPart], rax
0x18000a9e5  mov     [rbp+rcx+57h+NewState.Privileges.Attributes], 2
0x18000a9ed  lea     rcx, [rcx+0Ch]
0x18000a9f1  cmp     rdx, 3
0x18000a9f5  jnz     short loc_18000A9D8
0x18000a9f7  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000a9fb  lea     rax, [r14+14h]
0x18000a9ff  lea     r9d, [rdx+25h]; BufferLength
0x18000aa03  mov     [rsp+0F0h+ReturnLength], r15; ReturnLength
0x18000aa08  xor     edx, edx; DisableAllPrivileges
0x18000aa0a  mov     [rsp+0F0h+PreviousState], rax; PreviousState
0x18000aa0f  lea     r8, [rbp+57h+NewState]; NewState
0x18000aa13  call    cs:__imp_AdjustTokenPrivileges
0x18000aa19  test    eax, eax
0x18000aa1b  jnz     short loc_18000AA57
0x18000aa1d  call    cs:__imp_GetLastError
0x18000aa23  mov     ebx, eax
0x18000aa25  test    eax, eax
0x18000aa27  jle     short loc_18000AA32
0x18000aa29  movzx   ebx, ax
0x18000aa2c  or      ebx, 80070000h
0x18000aa32  mov     [rbp+57h+var_A0], ebx
0x18000aa35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa3c  cmp     rcx, rdi
0x18000aa3f  jz      short loc_18000AAA9
0x18000aa41  test    [rcx+1Ch], r13b
0x18000aa45  jz      short loc_18000AAA9
0x18000aa47  cmp     byte ptr [rcx+19h], 2
0x18000aa4b  jb      short loc_18000AAA9
0x18000aa4d  mov     edx, 11h
0x18000aa52  jmp     loc_18000A7F3
0x18000aa57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa5e  cmp     rcx, rdi
0x18000aa61  jz      short loc_18000AA84
0x18000aa63  test    [rcx+1Ch], r13b
0x18000aa67  jz      short loc_18000AA84
0x18000aa69  cmp     byte ptr [rcx+19h], 4
0x18000aa6d  jb      short loc_18000AA84
0x18000aa6f  mov     rcx, [rcx+10h]
0x18000aa73  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000aa7a  mov     edx, 12h
0x18000aa7f  call    WPP_SF_
0x18000aa84  cmp     [rbp+57h+var_AC], 0
0x18000aa88  jz      short loc_18000AA91
0x18000aa8a  xor     eax, eax
0x18000aa8c  cmp     [rbp+57h+var_B0], eax
0x18000aa8f  jnz     short loc_18000AA9D
0x18000aa91  mov     rax, [rbp+57h+TokenHandle]
0x18000aa95  mov     [rbp+57h+TokenHandle], 0
0x18000aa9d  mov     [r14], rax
0x18000aaa0  xor     ebx, ebx
0x18000aaa2  mov     [rbp+57h+var_A0], 0
0x18000aaa9  lea     rcx, [rbp+57h+TokenHandle]
0x18000aaad  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x18000aab2  lea     rcx, [rbp+57h+var_A8]; this
0x18000aab6  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18000aabb  mov     eax, ebx
0x18000aabd  mov     rcx, [rbp+57h+var_30]
0x18000aac1  xor     rcx, rsp; StackCookie
0x18000aac4  call    __security_check_cookie
0x18000aac9  lea     r11, [rsp+0F0h+var_20]
0x18000aad1  mov     rbx, [r11+38h]
0x18000aad5  mov     rsi, [r11+40h]
0x18000aad9  mov     rsp, r11
0x18000aadc  pop     r15
0x18000aade  pop     r14
0x18000aae0  pop     r13
  ... truncated ...
```

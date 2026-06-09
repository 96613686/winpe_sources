# CSessionBaseRW::CacheUserSid(void *)

- ea: `0x18000c004`
- end: `0x18000c357`
- name: `?CacheUserSid@CSessionBaseRW@@IEAAJPEAX@Z`
- size: `851`
- prototype: `__int64 __fastcall(CSessionBaseRW *__hidden this, void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180019dd0`
- `0x1800228b0`
- `0x180022d20`

## callees

- `0x180002524`
- `0x180006914`
- `0x180007818`
- `0x1800091a4`
- `0x1800093a8`
- `0x18000c004`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000c313`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000c313`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18000c28a`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18000c28a`
- `ADVAPI32!GetTokenInformation` at `0x18000c152`
- `ADVAPI32!GetTokenInformation` at `0x18000c22c`
- `ADVAPI32!GetTokenInformation` at `0x18000c152`
- `ADVAPI32!GetTokenInformation` at `0x18000c22c`
- `ADVAPI32!OpenProcessToken` at `0x18000c08c`
- `ADVAPI32!OpenProcessToken` at `0x18000c08c`
- `ADVAPI32!OpenThreadToken` at `0x18000c060`
- `ADVAPI32!OpenThreadToken` at `0x18000c060`
- `KERNEL32!GetLastError` at `0x18000c06e`
- `KERNEL32!GetLastError` at `0x18000c09a`
- `KERNEL32!GetLastError` at `0x18000c0ed`
- `KERNEL32!GetLastError` at `0x18000c15c`
- `KERNEL32!GetLastError` at `0x18000c167`
- `KERNEL32!GetLastError` at `0x18000c236`
- `KERNEL32!GetLastError` at `0x18000c294`
- `KERNEL32!GetLastError` at `0x18000c06e`
- `KERNEL32!GetLastError` at `0x18000c09a`
- `KERNEL32!GetLastError` at `0x18000c0ed`
- `KERNEL32!GetLastError` at `0x18000c15c`
- `KERNEL32!GetLastError` at `0x18000c167`
- `KERNEL32!GetLastError` at `0x18000c236`
- `KERNEL32!GetLastError` at `0x18000c294`
- `KERNEL32!CloseHandle` at `0x18000c343`
- `KERNEL32!CloseHandle` at `0x18000c343`
- `KERNEL32!GetCurrentThread` at `0x18000c045`
- `KERNEL32!GetCurrentThread` at `0x18000c045`
- `KERNEL32!GetCurrentProcess` at `0x18000c07b`
- `KERNEL32!GetCurrentProcess` at `0x18000c07b`
- `KERNEL32!LocalFree` at `0x18000c323`
- `KERNEL32!LocalFree` at `0x18000c323`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CSessionBaseRW::CacheUserSid(CSessionBaseRW *this, void *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  signed int v9; // eax
  signed int LastError; // eax
  PSID *v11; // r14
  signed int v12; // eax
  signed int v13; // eax
  unsigned int v14; // eax
  int v16; // [rsp+30h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-20h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-18h] BYREF
  PSID *v19; // [rsp+48h] [rbp-10h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v21; // [rsp+70h] [rbp+18h]
  int v22; // [rsp+78h] [rbp+20h]

  TokenHandle = 0;
  v22 = 0;
  TokenInformationLength = 0;
  StringSid = 0;
  v19 = 0;
  if ( a2 )
  {
    TokenHandle = a2;
    goto LABEL_18;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
LABEL_16:
    v22 = 1;
LABEL_18:
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v6);
      goto LABEL_48;
    }
    v11 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    v19 = v11;
    if ( !v11 )
    {
      v6 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, "buf");
      goto LABEL_48;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
    {
      if ( ConvertSidToStringSidW(*v11, &StringSid) )
      {
        v14 = ocslen(StringSid);
        try
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 264, StringSid, v14);
          v6 = 0;
        }
        catch ( ATL::CAtlException v16 )
        {
          v21 = v16;
          if ( v16 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              183,
              &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
              (unsigned int)v16);
          v11 = v19;
          v6 = v21;
          if ( !v19 )
            goto LABEL_48;
        }
      }
      else
      {
        v13 = GetLastError();
        v6 = v13;
        if ( v13 > 0 )
          v6 = (unsigned __int16)v13 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v6);
      }
    }
    else
    {
      v12 = GetLastError();
      v6 = v12;
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v6);
    }
    operator delete[](v11);
    goto LABEL_48;
  }
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      v5 = GetLastError();
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 177;
LABEL_10:
        WPP_SF_d(v7[2], v8, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v6);
        goto LABEL_48;
      }
      goto LABEL_48;
    }
    goto LABEL_16;
  }
  v9 = GetLastError();
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 178;
    goto LABEL_10;
  }
LABEL_48:
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( v22 && TokenHandle )
    CloseHandle(TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x18000c004  mov     rax, rsp
0x18000c007  mov     [rax+8], rbx
0x18000c00b  push    r14
0x18000c00d  sub     rsp, 50h
0x18000c011  mov     rbx, rcx
0x18000c014  mov     qword ptr [rax-20h], 0
0x18000c01c  mov     [rsp+58h+arg_18], 0
0x18000c024  mov     dword ptr [rax+10h], 0
0x18000c02b  mov     qword ptr [rax-18h], 0
0x18000c033  mov     [rsp+58h+var_10], 0
0x18000c03c  test    rdx, rdx
0x18000c03f  jnz     loc_18000C134
0x18000c045  call    cs:__imp_GetCurrentThread
0x18000c04b  mov     rcx, rax; ThreadHandle
0x18000c04e  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18000c053  mov     r8d, 1; OpenAsSelf
0x18000c059  lea     r14d, [r8+7]
0x18000c05d  mov     edx, r14d; DesiredAccess
0x18000c060  call    cs:__imp_OpenThreadToken
0x18000c066  test    eax, eax
0x18000c068  jnz     loc_18000C12A
0x18000c06e  call    cs:__imp_GetLastError
0x18000c074  cmp     eax, 3F0h
0x18000c079  jnz     short loc_18000C0ED
0x18000c07b  call    cs:__imp_GetCurrentProcess
0x18000c081  mov     rcx, rax; ProcessHandle
0x18000c084  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18000c089  mov     edx, r14d; DesiredAccess
0x18000c08c  call    cs:__imp_OpenProcessToken
0x18000c092  test    eax, eax
0x18000c094  jnz     loc_18000C12A
0x18000c09a  call    cs:__imp_GetLastError
0x18000c0a0  mov     ebx, eax
0x18000c0a2  test    eax, eax
0x18000c0a4  jle     short loc_18000C0AF
0x18000c0a6  movzx   ebx, ax
0x18000c0a9  or      ebx, 80070000h
0x18000c0af  lea     rax, WPP_GLOBAL_Control
0x18000c0b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0bd  cmp     rcx, rax
0x18000c0c0  jz      loc_18000C319
0x18000c0c6  test    byte ptr [rcx+1Ch], 1
0x18000c0ca  jz      loc_18000C319
0x18000c0d0  mov     edx, 0B1h
0x18000c0d5  mov     r9d, ebx
0x18000c0d8  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000c0df  mov     rcx, [rcx+10h]
0x18000c0e3  call    WPP_SF_d
0x18000c0e8  jmp     loc_18000C319
0x18000c0ed  call    cs:__imp_GetLastError
0x18000c0f3  mov     ebx, eax
0x18000c0f5  test    eax, eax
0x18000c0f7  jle     short loc_18000C102
0x18000c0f9  movzx   ebx, ax
0x18000c0fc  or      ebx, 80070000h
0x18000c102  lea     rax, WPP_GLOBAL_Control
0x18000c109  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c110  cmp     rcx, rax
0x18000c113  jz      loc_18000C319
0x18000c119  test    byte ptr [rcx+1Ch], 1
0x18000c11d  jz      loc_18000C319
0x18000c123  mov     edx, 0B2h
0x18000c128  jmp     short loc_18000C0D5
0x18000c12a  mov     [rsp+58h+arg_18], 1
0x18000c132  jmp     short loc_18000C139
0x18000c134  mov     [rsp+58h+TokenHandle], rdx
0x18000c139  lea     rax, [rsp+58h+TokenInformationLength]
0x18000c13e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c143  xor     r9d, r9d; TokenInformationLength
0x18000c146  xor     r8d, r8d; TokenInformation
0x18000c149  lea     edx, [r9+1]; TokenInformationClass
0x18000c14d  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000c152  call    cs:__imp_GetTokenInformation
0x18000c158  test    eax, eax
0x18000c15a  jnz     short loc_18000C1B3
0x18000c15c  call    cs:__imp_GetLastError
0x18000c162  cmp     eax, 7Ah ; 'z'
0x18000c165  jz      short loc_18000C1B3
0x18000c167  call    cs:__imp_GetLastError
0x18000c16d  mov     ebx, eax
0x18000c16f  test    eax, eax
0x18000c171  jle     short loc_18000C17C
0x18000c173  movzx   ebx, ax
0x18000c176  or      ebx, 80070000h
0x18000c17c  lea     rax, WPP_GLOBAL_Control
0x18000c183  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c18a  cmp     rcx, rax
0x18000c18d  jz      short loc_18000C1AE
0x18000c18f  test    byte ptr [rcx+1Ch], 1
0x18000c193  jz      short loc_18000C1AE
0x18000c195  mov     edx, 0B3h
0x18000c19a  mov     r9d, ebx
0x18000c19d  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000c1a4  mov     rcx, [rcx+10h]
0x18000c1a8  call    WPP_SF_d
0x18000c1ad  nop
0x18000c1ae  jmp     loc_18000C319
0x18000c1b3  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18000c1b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c1be  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000c1c3  mov     r14, rax
0x18000c1c6  mov     [rsp+58h+var_10], rax
0x18000c1cb  test    rax, rax
0x18000c1ce  jnz     short loc_18000C210
0x18000c1d0  mov     ebx, 8007000Eh
0x18000c1d5  lea     rax, WPP_GLOBAL_Control
0x18000c1dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1e3  cmp     rcx, rax
0x18000c1e6  jz      short loc_18000C20B
0x18000c1e8  test    byte ptr [rcx+1Ch], 1
0x18000c1ec  jz      short loc_18000C20B
0x18000c1ee  mov     edx, 0B4h
0x18000c1f3  lea     r9, aBuf; "buf"
0x18000c1fa  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000c201  mov     rcx, [rcx+10h]
0x18000c205  call    WPP_SF_s
0x18000c20a  nop
0x18000c20b  jmp     loc_18000C319
0x18000c210  lea     rax, [rsp+58h+TokenInformationLength]
0x18000c215  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c21a  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000c21f  mov     r8, r14; TokenInformation
0x18000c222  mov     edx, 1; TokenInformationClass
0x18000c227  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000c22c  call    cs:__imp_GetTokenInformation
0x18000c232  test    eax, eax
0x18000c234  jnz     short loc_18000C282
0x18000c236  call    cs:__imp_GetLastError
0x18000c23c  mov     ebx, eax
0x18000c23e  test    eax, eax
0x18000c240  jle     short loc_18000C24B
0x18000c242  movzx   ebx, ax
0x18000c245  or      ebx, 80070000h
0x18000c24b  lea     rax, WPP_GLOBAL_Control
0x18000c252  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c259  cmp     rcx, rax
0x18000c25c  jz      short loc_18000C27D
0x18000c25e  test    byte ptr [rcx+1Ch], 1
0x18000c262  jz      short loc_18000C27D
0x18000c264  mov     edx, 0B5h
0x18000c269  mov     r9d, ebx
0x18000c26c  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000c273  mov     rcx, [rcx+10h]
0x18000c277  call    WPP_SF_d
0x18000c27c  nop
0x18000c27d  jmp     loc_18000C310
0x18000c282  lea     rdx, [rsp+58h+StringSid]; StringSid
0x18000c287  mov     rcx, [r14]; Sid
0x18000c28a  call    cs:__imp_ConvertSidToStringSidW
0x18000c290  test    eax, eax
0x18000c292  jnz     short loc_18000C2DD
0x18000c294  call    cs:__imp_GetLastError
0x18000c29a  mov     ebx, eax
0x18000c29c  test    eax, eax
0x18000c29e  jle     short loc_18000C2A9
0x18000c2a0  movzx   ebx, ax
0x18000c2a3  or      ebx, 80070000h
0x18000c2a9  lea     rax, WPP_GLOBAL_Control
0x18000c2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2b7  cmp     rcx, rax
0x18000c2ba  jz      short loc_18000C2DB
0x18000c2bc  test    byte ptr [rcx+1Ch], 1
0x18000c2c0  jz      short loc_18000C2DB
0x18000c2c2  mov     edx, 0B6h
0x18000c2c7  mov     r9d, ebx
0x18000c2ca  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000c2d1  mov     rcx, [rcx+10h]
0x18000c2d5  call    WPP_SF_d
0x18000c2da  nop
0x18000c2db  jmp     short loc_18000C310
0x18000c2dd  mov     rcx, [rsp+58h+StringSid]; unsigned __int16 *
0x18000c2e2  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18000c2e7  mov     r8d, eax
0x18000c2ea  lea     rcx, [rbx+108h]
0x18000c2f1  mov     rdx, [rsp+58h+StringSid]
0x18000c2f6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000c2fb  nop
0x18000c2fc  xor     ebx, ebx
0x18000c2fe  jmp     short loc_18000C310
0x18000c300  jmp     short $+2
0x18000c302  mov     r14, [rsp+58h+var_10]
0x18000c307  mov     ebx, [rsp+58h+arg_10]
0x18000c30b  test    r14, r14
0x18000c30e  jz      short loc_18000C319
0x18000c310  mov     rcx, r14
0x18000c313  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000c319  mov     rcx, [rsp+58h+StringSid]; hMem
0x18000c31e  test    rcx, rcx
0x18000c321  jz      short loc_18000C332
0x18000c323  call    cs:__imp_LocalFree
0x18000c329  mov     [rsp+58h+StringSid], 0
0x18000c332  cmp     [rsp+58h+arg_18], 0
0x18000c337  jz      short loc_18000C349
0x18000c339  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000c33e  test    rcx, rcx
0x18000c341  jz      short loc_18000C349
0x18000c343  call    cs:__imp_CloseHandle
0x18000c349  mov     eax, ebx
0x18000c34b  mov     rbx, [rsp+58h+arg_0]
0x18000c350  add     rsp, 50h
0x18000c354  pop     r14
0x18000c356  retn
```

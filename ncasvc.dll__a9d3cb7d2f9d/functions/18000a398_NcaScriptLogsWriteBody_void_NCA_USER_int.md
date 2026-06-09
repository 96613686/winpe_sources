# NcaScriptLogsWriteBody(void *,NCA_USER_ *,int *)

- ea: `0x18000a398`
- end: `0x18000a94d`
- name: `?NcaScriptLogsWriteBody@@YAKPEAXPEAUNCA_USER_@@PEAH@Z`
- size: `1461`
- prototype: `__int64 __fastcall(void *, void **, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ae34`

## callees

- `0x180003770`
- `0x180004f34`
- `0x1800066ac`
- `0x180006d70`
- `0x1800092f0`
- `0x180009ce0`
- `0x18000a398`
- `0x180018fd4`
- `0x180019100`
- `0x180019c70`
- `0x18001cc3e`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a4fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a4fc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000a83e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000a83e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a40a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a46d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a84f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a40a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a46d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a84f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000a8dc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000a8dc`
- `KERNEL32!CreateJobObjectW` at `0x18000a3f5`
- `KERNEL32!CreateJobObjectW` at `0x18000a458`
- `KERNEL32!CreateJobObjectW` at `0x18000a4a7`
- `KERNEL32!CreateJobObjectW` at `0x18000a3f5`
- `KERNEL32!CreateJobObjectW` at `0x18000a458`
- `KERNEL32!CreateJobObjectW` at `0x18000a4a7`
- `KERNEL32!TerminateJobObject` at `0x18000a89d`
- `KERNEL32!TerminateJobObject` at `0x18000a89d`

## pseudocode

```c
__int64 __fastcall NcaScriptLogsWriteBody(void *a1, void **a2, int *a3)
{
  __int64 v3; // rbx
  DWORD CustomCommandCopy; // edi
  _QWORD *v7; // rax
  __int64 v8; // rdx
  unsigned int v9; // r12d
  unsigned int v10; // esi
  void *v11; // rbx
  int v12; // eax
  __int64 v13; // r9
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  _QWORD *v18; // rax
  __int64 v19; // rdx
  unsigned int v20; // r14d
  __int64 v21; // rsi
  __int64 v22; // rbx
  __int64 j; // rsi
  _QWORD *v25; // rax
  __int64 v26; // rdx
  __int64 i; // rdx
  DWORD v28; // eax
  __int64 v29; // r8
  HANDLE v30; // r14
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-69h] BYREF
  void *Src; // [rsp+38h] [rbp-61h] BYREF
  HANDLE hFile; // [rsp+40h] [rbp-59h]
  __int64 v34; // [rsp+50h] [rbp-49h] BYREF
  void *v35; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v37[8]; // [rsp+68h] [rbp-31h] BYREF
  void *v38; // [rsp+70h] [rbp-29h]
  _BYTE v40[8]; // [rsp+80h] [rbp-19h] BYREF
  void *v41; // [rsp+88h] [rbp-11h]
  HANDLE Handles[2]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v44; // [rsp+B0h] [rbp+17h]

  v3 = 0;
  hFile = a1;
  NumberOfBytesWritten = 0;
  v34 = 0;
  memset_0(&v35, 0, 0x40u);
  v44 = 0;
  *(_OWORD *)Handles = 0;
  if ( CreateJobObjectW(0, 0) )
  {
    if ( CreateJobObjectW(0, 0) )
    {
      if ( CreateJobObjectW(0, 0) )
      {
        AcquireSRWLockShared(&SRWLock);
        v9 = xmmword_180028BE8;
        v10 = 0;
        if ( (unsigned int)xmmword_180028BE8 > 0x14 )
          v9 = 20;
        while ( v10 < v9 )
        {
          Src = 0;
          CustomCommandCopy = NcaConfigMgrGetCustomCommandCopy(v10, &Src);
          if ( CustomCommandCopy )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_29;
            v26 = 70;
            goto LABEL_53;
          }
          v11 = Src;
          v12 = NcaStringCopy(Src);
          v13 = (unsigned int)v12;
          if ( v12 < 0 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_29;
            v19 = 71;
            goto LABEL_28;
          }
          v14 = NcaStringCopy(v11);
          v13 = (unsigned int)v14;
          if ( v14 < 0 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_29;
            v19 = 72;
LABEL_28:
            WPP_SF_d(v18[2], v19, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, v13);
            goto LABEL_29;
          }
          v15 = NcaStringCopy(v11);
          v3 = 0;
          if ( v15 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                73,
                WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids,
                (unsigned int)v15);
            goto LABEL_29;
          }
          NcaCustomCommandEmpty(&Src, v16, v17, (unsigned int)v15);
          ++v10;
        }
        NcaExcludeShareLockLeave(1, &SRWLock);
        CustomCommandCopy = NcaScriptLogsRunCommands(
                              (struct NCA_COMMAND_ENVIROMENT_ *)&gScriptLogAdminCommands,
                              0x14u,
                              a2[4],
                              (struct NCA_PROCESS_ENVIRONMENT_ *)&v34,
                              a3);
        if ( CustomCommandCopy )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_29;
          v26 = 74;
        }
        else
        {
          CustomCommandCopy = NcaScriptLogsRunCommands(
                                (struct NCA_COMMAND_ENVIROMENT_ *)&gScriptLogUserCommands,
                                2u,
                                a2[4],
                                (struct NCA_PROCESS_ENVIRONMENT_ *)v37,
                                0);
          if ( CustomCommandCopy )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_29;
            v26 = 75;
          }
          else
          {
            CustomCommandCopy = NcaScriptLogsRunCommands(
                                  (struct NCA_COMMAND_ENVIROMENT_ *)&gScriptLogCustomCommands,
                                  0x14u,
                                  a2[4],
                                  (struct NCA_PROCESS_ENVIRONMENT_ *)v40,
                                  a3);
            if ( CustomCommandCopy )
            {
              v25 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_29;
              v26 = 76;
            }
            else
            {
              for ( i = 0; i != 3; ++i )
                Handles[i] = (HANDLE)*(&v34 + 3 * i);
              v28 = WaitForMultipleObjects(3u, Handles, 1, 0x1D4C0u);
              if ( v28 != -1 )
              {
                if ( v28 == 258 )
                {
                  do
                    TerminateJobObject(*(HANDLE *)&v37[24 * v3++ - 8], 0x5B4u);
                  while ( v3 != 3 );
                  v29 = -1;
                  v3 = 0;
                  do
                    ++v29;
                  while ( *((_WORD *)qword_180029610 + v29) );
                  v30 = hFile;
                  WriteFile(hFile, qword_180029610, 2 * v29, &NumberOfBytesWritten, 0);
                }
                else
                {
                  v30 = hFile;
                }
                do
                  NcaCloseHandle(*(_QWORD *)&v37[24 * v3++ - 8]);
                while ( v3 != 3 );
                NcaScriptLogsFinishProcess(v30, (struct NCA_COMMAND_ENVIROMENT_ *)&gScriptLogAdminCommands, 0x14u, v35);
                NcaScriptLogsFinishProcess(v30, (struct NCA_COMMAND_ENVIROMENT_ *)&gScriptLogUserCommands, 2u, v38);
                NcaScriptLogsFinishProcess(v30, (struct NCA_COMMAND_ENVIROMENT_ *)&gScriptLogCustomCommands, v9, v41);
                CustomCommandCopy = 0;
LABEL_29:
                v20 = 0;
                if ( v9 )
                {
                  v21 = 0;
                  do
                  {
                    v22 = 3 * v21;
                    NcaFree(*(&gScriptLogCustomCommands + 3 * v21));
                    NcaFree(*(&gScriptLogCustomCommands + 3 * v21 + 1));
                    NcaFree(*(&gScriptLogCustomCommands + 3 * v21 + 2));
                    ++v20;
                    ++v21;
                    *(&gScriptLogCustomCommands + v22) = 0;
                  }
                  while ( v20 < v9 );
                }
                goto LABEL_32;
              }
              CustomCommandCopy = GetLastError();
              v25 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_29;
              v26 = 77;
            }
          }
        }
LABEL_53:
        WPP_SF_d(v25[2], v26, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, CustomCommandCopy);
        goto LABEL_29;
      }
      CustomCommandCopy = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 69;
        goto LABEL_5;
      }
    }
    else
    {
      CustomCommandCopy = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 68;
        goto LABEL_5;
      }
    }
  }
  else
  {
    CustomCommandCopy = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 67;
LABEL_5:
      WPP_SF_d(v7[2], v8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, CustomCommandCopy);
    }
  }
LABEL_32:
  for ( j = 0; j != 3; ++j )
  {
    NcaCloseHandle(*(&v35 + 3 * j));
    NcaCloseHandle(*(&v34 + 3 * j));
  }
  return CustomCommandCopy;
}

```

## disassembly

```asm
0x18000a398  mov     [rsp-8+arg_18], rbx
0x18000a39d  push    rbp
0x18000a39e  push    rsi
0x18000a39f  push    rdi
0x18000a3a0  push    r12
0x18000a3a2  push    r13
0x18000a3a4  push    r14
0x18000a3a6  push    r15
0x18000a3a8  lea     rbp, [rsp-27h]
0x18000a3ad  sub     rsp, 0C0h
0x18000a3b4  mov     rax, cs:__security_cookie
0x18000a3bb  xor     rax, rsp
0x18000a3be  mov     [rbp+57h+var_38], rax
0x18000a3c2  xor     ebx, ebx
0x18000a3c4  mov     [rbp+57h+hFile], rcx
0x18000a3c8  mov     r13, r8
0x18000a3cb  mov     [rbp+57h+NumberOfBytesWritten], ebx
0x18000a3ce  mov     r15, rdx
0x18000a3d1  mov     [rbp+57h+var_A0], rbx
0x18000a3d5  xor     edx, edx; Val
0x18000a3d7  lea     rcx, [rbp+57h+var_98]; void *
0x18000a3db  lea     r8d, [rbx+40h]; Size
0x18000a3df  call    memset_0
0x18000a3e4  xorps   xmm0, xmm0
0x18000a3e7  xor     eax, eax
0x18000a3e9  xor     edx, edx; lpName
0x18000a3eb  mov     [rbp+57h+var_40], rax
0x18000a3ef  xor     ecx, ecx; lpJobAttributes
0x18000a3f1  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x18000a3f5  call    cs:__imp_CreateJobObjectW
0x18000a3fc  nop     dword ptr [rax+rax+00h]
0x18000a401  mov     [rbp+57h+hJob], rax
0x18000a405  test    rax, rax
0x18000a408  jnz     short loc_18000A454
0x18000a40a  call    cs:__imp_GetLastError
0x18000a411  nop     dword ptr [rax+rax+00h]
0x18000a416  mov     edi, eax
0x18000a418  mov     rax, cs:WPP_GLOBAL_Control
0x18000a41f  lea     rcx, WPP_GLOBAL_Control
0x18000a426  cmp     rax, rcx
0x18000a429  jz      loc_18000A649
0x18000a42f  test    byte ptr [rax+1Ch], 1
0x18000a433  jz      loc_18000A649
0x18000a439  lea     edx, [rbx+43h]
0x18000a43c  mov     rcx, [rax+10h]
0x18000a440  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x18000a447  mov     r9d, edi
0x18000a44a  call    WPP_SF_d
0x18000a44f  jmp     loc_18000A649
0x18000a454  xor     edx, edx; lpName
0x18000a456  xor     ecx, ecx; lpJobAttributes
0x18000a458  call    cs:__imp_CreateJobObjectW
0x18000a45f  nop     dword ptr [rax+rax+00h]
0x18000a464  mov     [rbp+57h+var_78], rax
0x18000a468  test    rax, rax
0x18000a46b  jnz     short loc_18000A4A3
0x18000a46d  call    cs:__imp_GetLastError
0x18000a474  nop     dword ptr [rax+rax+00h]
0x18000a479  mov     edi, eax
0x18000a47b  mov     rax, cs:WPP_GLOBAL_Control
0x18000a482  lea     rcx, WPP_GLOBAL_Control
0x18000a489  cmp     rax, rcx
0x18000a48c  jz      loc_18000A649
0x18000a492  test    byte ptr [rax+1Ch], 1
0x18000a496  jz      loc_18000A649
0x18000a49c  mov     edx, 44h ; 'D'
0x18000a4a1  jmp     short loc_18000A43C
0x18000a4a3  xor     edx, edx; lpName
0x18000a4a5  xor     ecx, ecx; lpJobAttributes
0x18000a4a7  call    cs:__imp_CreateJobObjectW
0x18000a4ae  nop     dword ptr [rax+rax+00h]
0x18000a4b3  mov     [rbp+57h+var_60], rax
0x18000a4b7  test    rax, rax
0x18000a4ba  jnz     short loc_18000A4F5
0x18000a4bc  call    cs:__imp_GetLastError
0x18000a4c3  nop     dword ptr [rax+rax+00h]
0x18000a4c8  mov     edi, eax
0x18000a4ca  mov     rax, cs:WPP_GLOBAL_Control
0x18000a4d1  lea     rcx, WPP_GLOBAL_Control
0x18000a4d8  cmp     rax, rcx
0x18000a4db  jz      loc_18000A649
0x18000a4e1  test    byte ptr [rax+1Ch], 1
0x18000a4e5  jz      loc_18000A649
0x18000a4eb  mov     edx, 45h ; 'E'
0x18000a4f0  jmp     loc_18000A43C
0x18000a4f5  lea     rcx, SRWLock; SRWLock
0x18000a4fc  call    cs:__imp_AcquireSRWLockShared
0x18000a503  nop     dword ptr [rax+rax+00h]
0x18000a508  mov     r12d, dword ptr cs:xmmword_180028BE8
0x18000a50f  mov     r14d, 14h
0x18000a515  cmp     r12d, r14d
0x18000a518  mov     esi, ebx
0x18000a51a  cmova   r12d, r14d
0x18000a51e  lea     r14, ?gScriptLogCustomCommands@@3PAUNCA_COMMAND_ENVIROMENT_@@A; NCA_COMMAND_ENVIROMENT_ near * gScriptLogCustomCommands
0x18000a525  cmp     esi, r12d
0x18000a528  jnb     loc_18000A700
0x18000a52e  lea     rdx, [rbp+57h+Src]
0x18000a532  mov     [rbp+57h+Src], rbx
0x18000a536  mov     ecx, esi
0x18000a538  call    NcaConfigMgrGetCustomCommandCopy
0x18000a53d  mov     edi, eax
0x18000a53f  test    eax, eax
0x18000a541  jnz     loc_18000A6C2
0x18000a547  mov     rbx, [rbp+57h+Src]
0x18000a54b  mov     eax, esi
0x18000a54d  lea     rcx, [rax+rax*2]
0x18000a551  lea     r14, [r14+rcx*8]
0x18000a555  mov     rcx, rbx; Src
0x18000a558  mov     rdx, r14
0x18000a55b  call    NcaStringCopy
0x18000a560  mov     r9d, eax
0x18000a563  test    eax, eax
0x18000a565  js      loc_18000A697
0x18000a56b  lea     rdx, [r14+8]
0x18000a56f  mov     rcx, rbx; Src
0x18000a572  call    NcaStringCopy
0x18000a577  mov     r9d, eax
0x18000a57a  test    eax, eax
0x18000a57c  js      short loc_18000A5D3
0x18000a57e  lea     rdx, [r14+10h]
0x18000a582  mov     rcx, rbx; Src
0x18000a585  call    NcaStringCopy
0x18000a58a  xor     ebx, ebx
0x18000a58c  mov     r9d, eax
0x18000a58f  test    eax, eax
0x18000a591  js      short loc_18000A5A3
0x18000a593  lea     rcx, [rbp+57h+Src]
0x18000a597  call    NcaCustomCommandEmpty
0x18000a59c  inc     esi
0x18000a59e  jmp     loc_18000A51E
0x18000a5a3  mov     rax, cs:WPP_GLOBAL_Control
0x18000a5aa  lea     rcx, WPP_GLOBAL_Control
0x18000a5b1  cmp     rax, rcx
0x18000a5b4  jz      short loc_18000A603
0x18000a5b6  test    byte ptr [rax+1Ch], 1
0x18000a5ba  jz      short loc_18000A603
0x18000a5bc  mov     rcx, [rax+10h]
0x18000a5c0  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x18000a5c7  mov     edx, 49h ; 'I'
0x18000a5cc  call    WPP_SF_d
0x18000a5d1  jmp     short loc_18000A603
0x18000a5d3  mov     rax, cs:WPP_GLOBAL_Control
0x18000a5da  lea     rcx, WPP_GLOBAL_Control
0x18000a5e1  cmp     rax, rcx
0x18000a5e4  jz      short loc_18000A601
0x18000a5e6  test    byte ptr [rax+1Ch], 1
0x18000a5ea  jz      short loc_18000A601
0x18000a5ec  mov     edx, 48h ; 'H'
0x18000a5f1  mov     rcx, [rax+10h]
0x18000a5f5  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x18000a5fc  call    WPP_SF_d
0x18000a601  xor     ebx, ebx
0x18000a603  lea     r15, ?gScriptLogCustomCommands@@3PAUNCA_COMMAND_ENVIROMENT_@@A; NCA_COMMAND_ENVIROMENT_ near * gScriptLogCustomCommands
0x18000a60a  mov     r14d, ebx
0x18000a60d  test    r12d, r12d
0x18000a610  jz      short loc_18000A649
0x18000a612  mov     rsi, rbx
0x18000a615  lea     rbx, [rsi+rsi*2]
0x18000a619  mov     rcx, [r15+rbx*8]; lpMem
0x18000a61d  call    NcaFree
0x18000a622  mov     rcx, [r15+rbx*8+8]; lpMem
0x18000a627  call    NcaFree
0x18000a62c  mov     rcx, [r15+rbx*8+10h]; lpMem
0x18000a631  call    NcaFree
0x18000a636  xor     eax, eax
0x18000a638  inc     r14d
0x18000a63b  inc     rsi
0x18000a63e  mov     [r15+rbx*8], rax
0x18000a642  cmp     r14d, r12d
0x18000a645  jb      short loc_18000A615
0x18000a647  xor     ebx, ebx
0x18000a649  mov     rsi, rbx
0x18000a64c  lea     rbx, [rsi+rsi*2]
0x18000a650  mov     rcx, [rbp+rbx*8+57h+var_98]
0x18000a655  call    NcaCloseHandle
0x18000a65a  mov     rcx, [rbp+rbx*8+57h+var_A0]
0x18000a65f  call    NcaCloseHandle
0x18000a664  inc     rsi
0x18000a667  cmp     rsi, 3
0x18000a66b  jnz     short loc_18000A64C
0x18000a66d  mov     eax, edi
0x18000a66f  mov     rcx, [rbp+57h+var_38]
0x18000a673  xor     rcx, rsp; StackCookie
0x18000a676  call    __security_check_cookie
0x18000a67b  mov     rbx, [rsp+0F0h+arg_18]
0x18000a683  add     rsp, 0C0h
0x18000a68a  pop     r15
0x18000a68c  pop     r14
0x18000a68e  pop     r13
0x18000a690  pop     r12
0x18000a692  pop     rdi
0x18000a693  pop     rsi
0x18000a694  pop     rbp
0x18000a695  retn
0x18000a697  mov     rax, cs:WPP_GLOBAL_Control
0x18000a69e  lea     rcx, WPP_GLOBAL_Control
0x18000a6a5  cmp     rax, rcx
0x18000a6a8  jz      loc_18000A601
0x18000a6ae  test    byte ptr [rax+1Ch], 1
0x18000a6b2  jz      loc_18000A601
0x18000a6b8  mov     edx, 47h ; 'G'
0x18000a6bd  jmp     loc_18000A5F1
0x18000a6c2  mov     rax, cs:WPP_GLOBAL_Control
0x18000a6c9  lea     rcx, WPP_GLOBAL_Control
0x18000a6d0  cmp     rax, rcx
0x18000a6d3  jz      loc_18000A603
0x18000a6d9  test    byte ptr [rax+1Ch], 1
0x18000a6dd  jz      loc_18000A603
0x18000a6e3  mov     edx, 46h ; 'F'
0x18000a6e8  mov     rcx, [rax+10h]
0x18000a6ec  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x18000a6f3  mov     r9d, edi
0x18000a6f6  call    WPP_SF_d
0x18000a6fb  jmp     loc_18000A603
0x18000a700  lea     rdx, SRWLock
0x18000a707  mov     ecx, 1
0x18000a70c  call    NcaExcludeShareLockLeave
0x18000a711  mov     r8, [r15+20h]; void *
0x18000a715  lea     r9, [rbp+57h+var_A0]; struct NCA_PROCESS_ENVIRONMENT_ *
0x18000a719  mov     r14d, 14h
0x18000a71f  mov     [rsp+0F0h+lpOverlapped], r13; int *
0x18000a724  mov     edx, r14d; unsigned int
0x18000a727  lea     rcx, ?gScriptLogAdminCommands@@3PAUNCA_COMMAND_ENVIROMENT_@@A; struct NCA_COMMAND_ENVIROMENT_ *
0x18000a72e  call    ?NcaScriptLogsRunCommands@@YAKPEAUNCA_COMMAND_ENVIROMENT_@@KPEAXPEAUNCA_PROCESS_ENVIRONMENT_@@PEAH@Z; NcaScriptLogsRunCommands(NCA_COMMAND_ENVIROMENT_ *,ulong,void *,NCA_PROCESS_ENVIRONMENT_ *,int *)
0x18000a733  mov     edi, eax
0x18000a735  test    eax, eax
0x18000a737  jz      short loc_18000A760
0x18000a739  mov     rax, cs:WPP_GLOBAL_Control
0x18000a740  lea     rcx, WPP_GLOBAL_Control
0x18000a747  cmp     rax, rcx
0x18000a74a  jz      loc_18000A603
0x18000a750  test    byte ptr [rax+1Ch], 1
0x18000a754  jz      loc_18000A603
0x18000a75a  lea     edx, [r14+36h]
0x18000a75e  jmp     short loc_18000A6E8
0x18000a760  mov     r8, [r15+20h]; void *
0x18000a764  lea     r9, [rbp+57h+var_88]; struct NCA_PROCESS_ENVIRONMENT_ *
0x18000a768  mov     esi, 2
0x18000a76d  mov     [rsp+0F0h+lpOverlapped], rbx; int *
0x18000a772  mov     edx, esi; unsigned int
0x18000a774  lea     rcx, ?gScriptLogUserCommands@@3PAUNCA_COMMAND_ENVIROMENT_@@A; struct NCA_COMMAND_ENVIROMENT_ *
0x18000a77b  call    ?NcaScriptLogsRunCommands@@YAKPEAUNCA_COMMAND_ENVIROMENT_@@KPEAXPEAUNCA_PROCESS_ENVIRONMENT_@@PEAH@Z; NcaScriptLogsRunCommands(NCA_COMMAND_ENVIROMENT_ *,ulong,void *,NCA_PROCESS_ENVIRONMENT_ *,int *)
0x18000a780  mov     edi, eax
0x18000a782  test    eax, eax
0x18000a784  jz      short loc_18000A7AF
0x18000a786  mov     rax, cs:WPP_GLOBAL_Control
0x18000a78d  lea     rcx, WPP_GLOBAL_Control
0x18000a794  cmp     rax, rcx
0x18000a797  jz      loc_18000A603
0x18000a79d  test    byte ptr [rax+1Ch], 1
0x18000a7a1  jz      loc_18000A603
0x18000a7a7  lea     edx, [rsi+49h]
0x18000a7aa  jmp     loc_18000A6E8
0x18000a7af  mov     r8, [r15+20h]; void *
0x18000a7b3  lea     r9, [rbp+57h+var_70]; struct NCA_PROCESS_ENVIRONMENT_ *
0x18000a7b7  lea     r15, ?gScriptLogCustomCommands@@3PAUNCA_COMMAND_ENVIROMENT_@@A; NCA_COMMAND_ENVIROMENT_ near * gScriptLogCustomCommands
0x18000a7be  mov     [rsp+0F0h+lpOverlapped], r13; int *
0x18000a7c3  mov     rcx, r15; struct NCA_COMMAND_ENVIROMENT_ *
0x18000a7c6  mov     edx, r14d; unsigned int
0x18000a7c9  call    ?NcaScriptLogsRunCommands@@YAKPEAUNCA_COMMAND_ENVIROMENT_@@KPEAXPEAUNCA_PROCESS_ENVIRONMENT_@@PEAH@Z; NcaScriptLogsRunCommands(NCA_COMMAND_ENVIROMENT_ *,ulong,void *,NCA_PROCESS_ENVIRONMENT_ *,int *)
0x18000a7ce  mov     edi, eax
0x18000a7d0  test    eax, eax
0x18000a7d2  jz      short loc_18000A812
0x18000a7d4  mov     rax, cs:WPP_GLOBAL_Control
0x18000a7db  lea     rcx, WPP_GLOBAL_Control
0x18000a7e2  cmp     rax, rcx
0x18000a7e5  jz      loc_18000A60A
0x18000a7eb  test    byte ptr [rax+1Ch], 1
0x18000a7ef  jz      loc_18000A60A
0x18000a7f5  mov     edx, 4Ch ; 'L'
0x18000a7fa  mov     rcx, [rax+10h]
0x18000a7fe  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x18000a805  mov     r9d, edi
0x18000a808  call    WPP_SF_d
0x18000a80d  jmp     loc_18000A60A
0x18000a812  mov     rdx, rbx
0x18000a815  lea     rax, [rdx+rdx*2]
0x18000a819  mov     rcx, [rbp+rax*8+57h+var_A0]
0x18000a81e  mov     [rbp+rdx*8+57h+Handles], rcx
0x18000a823  inc     rdx
0x18000a826  cmp     rdx, 3
0x18000a82a  jnz     short loc_18000A815
0x18000a82c  lea     r8d, [rdx-2]; bWaitAll
0x18000a830  mov     r9d, 1D4C0h; dwMilliseconds
0x18000a836  lea     ecx, [r8+2]; nCount
0x18000a83a  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000a83e  call    cs:__imp_WaitForMultipleObjects
0x18000a845  nop     dword ptr [rax+rax+00h]
0x18000a84a  cmp     eax, 0FFFFFFFFh
0x18000a84d  jnz     short loc_18000A888
0x18000a84f  call    cs:__imp_GetLastError
0x18000a856  nop     dword ptr [rax+rax+00h]
0x18000a85b  mov     edi, eax
0x18000a85d  mov     rax, cs:WPP_GLOBAL_Control
0x18000a864  lea     rcx, WPP_GLOBAL_Control
0x18000a86b  cmp     rax, rcx
0x18000a86e  jz      loc_18000A60A
0x18000a874  test    byte ptr [rax+1Ch], 1
0x18000a878  jz      loc_18000A60A
0x18000a87e  mov     edx, 4Dh ; 'M'
  ... truncated ...
```

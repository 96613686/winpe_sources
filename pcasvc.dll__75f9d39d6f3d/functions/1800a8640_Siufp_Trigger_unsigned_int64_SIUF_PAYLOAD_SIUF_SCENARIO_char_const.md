# Siufp_Trigger(unsigned __int64,_SIUF_PAYLOAD *,_SIUF_SCENARIO,char const *)

- ea: `0x1800a8640`
- end: `0x1800a8a80`
- name: `?Siufp_Trigger@@YAK_KPEAU_SIUF_PAYLOAD@@W4_SIUF_SCENARIO@@PEBD@Z`
- size: `1088`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021d20`
- `0x1800a80f0`

## callees

- `0x180005180`
- `0x18000dc08`
- `0x180012920`
- `0x180013fac`
- `0x1800170ac`
- `0x18001b320`
- `0x180021f0c`
- `0x180056256`
- `0x18007a9cf`
- `0x1800a8640`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800a8801`
- `msvcrt!wcscpy_s` at `0x1800a8801`
- `ntdll!EtwEventWriteNoRegistration` at `0x1800a89b3`
- `ntdll!EtwEventWriteNoRegistration` at `0x1800a89b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8a36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8697`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a88fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a88fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a86b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a8a19`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a86b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a8a19`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a8a29`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a8a29`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a88f3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a88f3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a88b4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a88b4`

## string_xrefs

- `0x1800a886b`: `Failed to construct store path`
- `0x1800a8903`: `Failed to impersonate user [%d]`
- `0x1800a8899`: `CompatParameter1`

## pseudocode

```c
__int64 __fastcall Siufp_Trigger(unsigned __int64 a1, char *a2, int a3, const char *a4)
{
  struct _PCA_CHAIN *v8; // rsi
  unsigned int v9; // ebp
  __int64 v10; // rbx
  unsigned int ProgramInfo; // edi
  __int64 v12; // rbx
  char *v13; // rdi
  __int64 v14; // rax
  const char *v15; // r9
  int v16; // r8d
  struct _PCA_CHAIN *v17; // rax
  DWORD LastError; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 *v23; // rbx
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  int v29[4]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR SubKey[512]; // [rsp+50h] [rbp-448h] BYREF

  v29[0] = 0;
  v8 = PcapChainFromHandle(a1);
  v9 = *((_DWORD *)PcapChainFromHandle(a1) + 4);
  EnterCriticalSection(&stru_180158698);
  if ( !qword_180158700 )
  {
    v10 = qword_1801586D8;
    if ( qword_1801586D8 )
    {
      if ( GetTickCount64() - v10 < 0x3A98 )
      {
        PcaTracePrintf("Siuf", v9, 0, "IgnoreTrigger,Waiting for possible toast event");
LABEL_5:
        ProgramInfo = 0;
        goto LABEL_48;
      }
    }
  }
  memset_0(qword_1801586E0, 0, 0xB30u);
  qword_1801586D8 = 0;
  *(_DWORD *)a2 = v9;
  *((_QWORD *)a2 + 4) = 0;
  *((_DWORD *)a2 + 146) = a3;
  *((_QWORD *)a2 + 292) = PcaChainGetRunTime(a1);
  *((_DWORD *)a2 + 145) = *((_DWORD *)PcapChainFromHandle(a1) + 1374);
  ProgramInfo = PcaUtilityGetProgramInfo(
                  (unsigned __int16 *)a2 + 294,
                  (unsigned __int16 *)a2 + 339,
                  (unsigned __int16 *)a2 + 384,
                  (unsigned __int16 *)a2 + 904,
                  (unsigned __int16 *)a2 + 644,
                  (unsigned int *)a2 + 582,
                  v29,
                  (const unsigned __int16 *)v8 + 1568);
  if ( ProgramInfo )
  {
    AslLogCallPrintf(1, (unsigned int)"Siufp_Trigger", 895, (unsigned int)"Failed to retrieve program info [%d]");
    goto LABEL_48;
  }
  v12 = -1;
  v13 = a2 + 2344;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)&v13[2 * v14] );
  if ( !v14 )
  {
    if ( v29[0] )
    {
      PcaTracePrintf("Siuf", v9, 0, "Skipping,No shortcut for orphan");
      goto LABEL_5;
    }
    wcscpy_s((wchar_t *)a2 + 1172, 0x104u, (const wchar_t *)a2 + 384);
    PcaTracePrintf("Siuf", v9, 0, "Program name,%S", (const wchar_t *)a2 + 1172);
  }
  if ( StringCchPrintfW(SubKey, 0x200u, L"%s\\%s\\%s", (char *)v8 + 36, L"Software\\Microsoft\\Siuf", L"Rules") < 0 )
  {
    ProgramInfo = 87;
    AslLogCallPrintf(1, (unsigned int)"Siufp_Trigger", 926, (unsigned int)"Failed to construct store path");
    goto LABEL_48;
  }
  do
    ++v12;
  while ( *(_WORD *)&v13[2 * v12] );
  ProgramInfo = RegSetKeyValueW(HKEY_USERS, SubKey, L"CompatParameter1", 1u, a2 + 2344, 2 * v12);
  if ( ProgramInfo )
  {
    v15 = "Failed to set value [%d]";
    v16 = 937;
LABEL_19:
    AslLogCallPrintf(1, (unsigned int)"Siufp_Trigger", v16, (_DWORD)v15);
    goto LABEL_48;
  }
  v17 = PcapChainFromHandle(a1);
  if ( !ImpersonateLoggedOnUser(*((HANDLE *)v17 + 667)) )
  {
    LastError = GetLastError();
    v15 = "Failed to impersonate user [%d]";
    v16 = 949;
    ProgramInfo = LastError;
    goto LABEL_19;
  }
  v19 = *((_DWORD *)a2 + 140);
  if ( v19 > 5 )
  {
    v24 = v19 - 6;
    if ( !v24 )
    {
      v23 = AE_PCA_SIUF_TRIGGER_6;
      goto LABEL_44;
    }
    v25 = v24 - 1;
    if ( !v25 )
    {
      v23 = AE_PCA_SIUF_TRIGGER_7;
      goto LABEL_44;
    }
    v26 = v25 - 1;
    if ( !v26 )
    {
      v23 = AE_PCA_SIUF_TRIGGER_8;
      goto LABEL_44;
    }
    v27 = v26 - 1;
    if ( !v27 )
    {
      v23 = (__int64 *)"O";
      goto LABEL_44;
    }
    if ( v27 == 1 )
    {
      v23 = AE_PCA_SIUF_TRIGGER_10;
      goto LABEL_44;
    }
    goto LABEL_32;
  }
  if ( v19 == 5 )
  {
    v23 = AE_PCA_SIUF_TRIGGER_5;
    goto LABEL_44;
  }
  if ( !v19 )
    goto LABEL_32;
  v20 = v19 - 1;
  if ( !v20 )
    goto LABEL_32;
  v21 = v20 - 1;
  if ( !v21 )
  {
    v23 = AE_PCA_SIUF_TRIGGER_2;
    goto LABEL_44;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    v23 = AE_PCA_SIUF_TRIGGER_3;
    goto LABEL_44;
  }
  if ( v22 != 1 )
  {
LABEL_32:
    v23 = AE_PCA_SIUF_TRIGGER;
    goto LABEL_44;
  }
  v23 = AE_PCA_SIUF_TRIGGER_4;
LABEL_44:
  ProgramInfo = EtwEventWriteNoRegistration(&AE_LOG, v23, 0, 0);
  if ( ProgramInfo )
  {
    AslLogCallPrintf(1, (unsigned int)"Siufp_Trigger", 996, (unsigned int)"Failed to emit Siuf escalation event [%d]");
  }
  else
  {
    PcaTracePrintf("Siuf", v9, 0, "Trigger sent,%s,EventId,%d", a4, *(unsigned __int16 *)v23);
    memcpy_0(qword_1801586E0, a2, 0xB30u);
    qword_1801586D8 = GetTickCount64();
    ProgramInfo = 0;
  }
  RevertToSelf();
LABEL_48:
  LeaveCriticalSection(&stru_180158698);
  PcaChainSetSlot(a1, 11, 0, 0, 0);
  return ProgramInfo;
}

```

## disassembly

```asm
0x1800a8640  mov     [rsp+arg_10], rbx
0x1800a8645  push    rbp
0x1800a8646  push    rsi
0x1800a8647  push    rdi
0x1800a8648  push    r12
0x1800a864a  push    r13
0x1800a864c  push    r14
0x1800a864e  push    r15
0x1800a8650  sub     rsp, 460h
0x1800a8657  mov     rax, cs:__security_cookie
0x1800a865e  xor     rax, rsp
0x1800a8661  mov     [rsp+498h+var_48], rax
0x1800a8669  xor     r12d, r12d
0x1800a866c  mov     r13, r9
0x1800a866f  mov     [rsp+498h+var_458], r12d
0x1800a8674  mov     edi, r8d
0x1800a8677  mov     r14, rdx
0x1800a867a  mov     r15, rcx
0x1800a867d  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800a8682  mov     rcx, r15; unsigned __int64
0x1800a8685  mov     rsi, rax
0x1800a8688  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800a868d  lea     rcx, stru_180158698; lpCriticalSection
0x1800a8694  mov     ebp, [rax+10h]
0x1800a8697  call    cs:__imp_EnterCriticalSection
0x1800a869d  cmp     cs:qword_180158700, r12
0x1800a86a4  jnz     short loc_1800A86E3
0x1800a86a6  mov     rbx, cs:qword_1801586D8
0x1800a86ad  test    rbx, rbx
0x1800a86b0  jz      short loc_1800A86E3
0x1800a86b2  call    cs:__imp_GetTickCount64
0x1800a86b8  sub     rax, rbx
0x1800a86bb  cmp     rax, 3A98h
0x1800a86c1  jnb     short loc_1800A86E3
0x1800a86c3  lea     r9, aIgnoretriggerW; "IgnoreTrigger,Waiting for possible toas"...
0x1800a86ca  xor     r8d, r8d; unsigned int
0x1800a86cd  mov     edx, ebp; unsigned int
0x1800a86cf  lea     rcx, aSiuf; "Siuf"
0x1800a86d6  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a86db  mov     edi, r12d
0x1800a86de  jmp     loc_1800A8A2F
0x1800a86e3  xor     edx, edx; Val
0x1800a86e5  lea     rcx, qword_1801586E0; void *
0x1800a86ec  mov     r8d, 0B30h; Size
0x1800a86f2  call    memset_0
0x1800a86f7  mov     cs:qword_1801586D8, r12
0x1800a86fe  mov     rcx, r15; unsigned __int64
0x1800a8701  mov     [r14], ebp
0x1800a8704  mov     [r14+20h], r12
0x1800a8708  mov     [r14+248h], edi
0x1800a870f  call    ?PcaChainGetRunTime@@YA_K_K@Z; PcaChainGetRunTime(unsigned __int64)
0x1800a8714  mov     rcx, r15; unsigned __int64
0x1800a8717  mov     [r14+920h], rax
0x1800a871e  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800a8723  lea     r8, [r14+918h]
0x1800a872a  lea     r10, [r14+508h]
0x1800a8731  lea     r12, [r14+300h]
0x1800a8738  mov     ecx, [rax+1578h]
0x1800a873e  lea     r9, [r14+710h]; unsigned __int16 *
0x1800a8745  lea     rax, [rsi+0C40h]
0x1800a874c  mov     [r14+244h], ecx
0x1800a8753  mov     [rsp+498h+var_460], rax; unsigned __int16 *
0x1800a8758  lea     rdx, [r14+2A6h]; unsigned __int16 *
0x1800a875f  lea     rax, [rsp+498h+var_458]
0x1800a8764  mov     [rsp+498h+var_468], rax; int *
0x1800a8769  lea     rcx, [r14+24Ch]; unsigned __int16 *
0x1800a8770  mov     qword ptr [rsp+498h+cbData], r8; unsigned int *
0x1800a8775  mov     r8, r12; unsigned __int16 *
0x1800a8778  mov     [rsp+498h+lpData], r10; unsigned __int16 *
0x1800a877d  call    ?PcaUtilityGetProgramInfo@@YAKPEAG0000PEAIPEAHPEBG@Z; PcaUtilityGetProgramInfo(ushort *,ushort *,ushort *,ushort *,ushort *,uint *,int *,ushort const *)
0x1800a8782  xor     ecx, ecx
0x1800a8784  mov     edi, eax
0x1800a8786  test    eax, eax
0x1800a8788  jz      short loc_1800A87B4
0x1800a878a  lea     r9, aFailedToRetrie_11; "Failed to retrieve program info [%d]"
0x1800a8791  mov     dword ptr [rsp+498h+lpData], eax
0x1800a8795  mov     r8d, 37Fh
0x1800a879b  lea     rdx, aSiufpTrigger; "Siufp_Trigger"
0x1800a87a2  mov     ecx, 1
0x1800a87a7  call    AslLogCallPrintf
0x1800a87ac  xor     r12d, r12d
0x1800a87af  jmp     loc_1800A8A2F
0x1800a87b4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a87b8  lea     rdi, [r14+928h]
0x1800a87bf  mov     rax, rbx
0x1800a87c2  inc     rax
0x1800a87c5  cmp     [rdi+rax*2], cx
0x1800a87c9  jnz     short loc_1800A87C2
0x1800a87cb  test    rax, rax
0x1800a87ce  jnz     short loc_1800A8824
0x1800a87d0  cmp     [rsp+498h+var_458], ecx
0x1800a87d4  jz      short loc_1800A87F6
0x1800a87d6  lea     r9, aSkippingNoShor; "Skipping,No shortcut for orphan"
0x1800a87dd  xor     r8d, r8d; unsigned int
0x1800a87e0  mov     edx, ebp; unsigned int
0x1800a87e2  lea     rcx, aSiuf; "Siuf"
0x1800a87e9  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a87ee  xor     r12d, r12d
0x1800a87f1  jmp     loc_1800A86DB
0x1800a87f6  mov     r8, r12; Source
0x1800a87f9  mov     edx, 104h; SizeInWords
0x1800a87fe  mov     rcx, rdi; Destination
0x1800a8801  call    cs:__imp_wcscpy_s
0x1800a8807  lea     r9, aProgramNameS; "Program name,%S"
0x1800a880e  mov     [rsp+498h+lpData], rdi
0x1800a8813  xor     r8d, r8d; unsigned int
0x1800a8816  lea     rcx, aSiuf; "Siuf"
0x1800a881d  mov     edx, ebp; unsigned int
0x1800a881f  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a8824  lea     rax, aRules; "Rules"
0x1800a882b  mov     edx, 200h; unsigned __int64
0x1800a8830  mov     qword ptr [rsp+498h+cbData], rax
0x1800a8835  lea     r9, [rsi+24h]
0x1800a8839  lea     rax, aSoftwareMicros_1; "Software\\Microsoft\\Siuf"
0x1800a8840  lea     r8, aSSS; "%s\\%s\\%s"
0x1800a8847  mov     [rsp+498h+lpData], rax
0x1800a884c  lea     rcx, [rsp+498h+SubKey]; unsigned __int16 *
0x1800a8851  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a8856  xor     r12d, r12d
0x1800a8859  test    eax, eax
0x1800a885b  jns     short loc_1800A8883
0x1800a885d  lea     edi, [r12+57h]
0x1800a8862  mov     r8d, 39Eh
0x1800a8868  lea     ecx, [rdi-56h]
0x1800a886b  lea     r9, aFailedToConstr_0; "Failed to construct store path"
0x1800a8872  lea     rdx, aSiufpTrigger; "Siufp_Trigger"
0x1800a8879  call    AslLogCallPrintf
0x1800a887e  jmp     loc_1800A8A2F
0x1800a8883  inc     rbx
0x1800a8886  cmp     [rdi+rbx*2], r12w
0x1800a888b  jnz     short loc_1800A8883
0x1800a888d  lea     eax, [rbx+rbx]
0x1800a8890  mov     esi, 1
0x1800a8895  mov     [rsp+498h+cbData], eax; cbData
0x1800a8899  lea     r8, aCompatparamete; "CompatParameter1"
0x1800a88a0  mov     r9d, esi; dwType
0x1800a88a3  mov     [rsp+498h+lpData], rdi; lpData
0x1800a88a8  lea     rdx, [rsp+498h+SubKey]; lpSubKey
0x1800a88ad  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800a88b4  call    cs:__imp_RegSetKeyValueW
0x1800a88ba  mov     edi, eax
0x1800a88bc  test    eax, eax
0x1800a88be  jz      short loc_1800A88E4
0x1800a88c0  lea     r9, aFailedToSetVal_1; "Failed to set value [%d]"
0x1800a88c7  mov     r8d, 3A9h
0x1800a88cd  lea     rdx, aSiufpTrigger; "Siufp_Trigger"
0x1800a88d4  mov     dword ptr [rsp+498h+lpData], eax
0x1800a88d8  mov     ecx, esi
0x1800a88da  call    AslLogCallPrintf
0x1800a88df  jmp     loc_1800A8A2F
0x1800a88e4  mov     rcx, r15; unsigned __int64
0x1800a88e7  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800a88ec  mov     rcx, [rax+14D8h]; hToken
0x1800a88f3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a88f9  test    eax, eax
0x1800a88fb  jnz     short loc_1800A8914
0x1800a88fd  call    cs:__imp_GetLastError
0x1800a8903  lea     r9, aFailedToImpers_0; "Failed to impersonate user [%d]"
0x1800a890a  mov     r8d, 3B5h
0x1800a8910  mov     edi, eax
0x1800a8912  jmp     short loc_1800A88CD
0x1800a8914  mov     eax, [r14+230h]
0x1800a891b  cmp     eax, 5
0x1800a891e  ja      short loc_1800A8963
0x1800a8920  jz      short loc_1800A895A
0x1800a8922  test    eax, eax
0x1800a8924  jz      short loc_1800A8951
0x1800a8926  sub     eax, esi
0x1800a8928  jz      short loc_1800A8951
0x1800a892a  sub     eax, esi
0x1800a892c  jz      short loc_1800A8948
0x1800a892e  sub     eax, esi
0x1800a8930  jz      short loc_1800A893F
0x1800a8932  cmp     eax, esi
0x1800a8934  jnz     short loc_1800A8951
0x1800a8936  lea     rbx, AE_PCA_SIUF_TRIGGER_4
0x1800a893d  jmp     short loc_1800A89A3
0x1800a893f  lea     rbx, AE_PCA_SIUF_TRIGGER_3
0x1800a8946  jmp     short loc_1800A89A3
0x1800a8948  lea     rbx, AE_PCA_SIUF_TRIGGER_2
0x1800a894f  jmp     short loc_1800A89A3
0x1800a8951  lea     rbx, AE_PCA_SIUF_TRIGGER
0x1800a8958  jmp     short loc_1800A89A3
0x1800a895a  lea     rbx, AE_PCA_SIUF_TRIGGER_5
0x1800a8961  jmp     short loc_1800A89A3
0x1800a8963  sub     eax, 6
0x1800a8966  jz      short loc_1800A899C
0x1800a8968  sub     eax, esi
0x1800a896a  jz      short loc_1800A8993
0x1800a896c  sub     eax, esi
0x1800a896e  jz      short loc_1800A898A
0x1800a8970  sub     eax, esi
0x1800a8972  jz      short loc_1800A8981
0x1800a8974  cmp     eax, esi
0x1800a8976  jnz     short loc_1800A8951
0x1800a8978  lea     rbx, AE_PCA_SIUF_TRIGGER_10
0x1800a897f  jmp     short loc_1800A89A3
0x1800a8981  lea     rbx, AE_PCA_SIUF_TRIGGER_9; "O"
0x1800a8988  jmp     short loc_1800A89A3
0x1800a898a  lea     rbx, AE_PCA_SIUF_TRIGGER_8
0x1800a8991  jmp     short loc_1800A89A3
0x1800a8993  lea     rbx, AE_PCA_SIUF_TRIGGER_7
0x1800a899a  jmp     short loc_1800A89A3
0x1800a899c  lea     rbx, AE_PCA_SIUF_TRIGGER_6
0x1800a89a3  xor     r9d, r9d
0x1800a89a6  lea     rcx, AE_LOG
0x1800a89ad  xor     r8d, r8d
0x1800a89b0  mov     rdx, rbx
0x1800a89b3  call    cs:__imp_EtwEventWriteNoRegistration
0x1800a89b9  mov     edi, eax
0x1800a89bb  test    eax, eax
0x1800a89bd  jz      short loc_1800A89E0
0x1800a89bf  lea     r9, aFailedToEmitSi; "Failed to emit Siuf escalation event [%"...
0x1800a89c6  mov     dword ptr [rsp+498h+lpData], eax
0x1800a89ca  mov     r8d, 3E4h
0x1800a89d0  lea     rdx, aSiufpTrigger; "Siufp_Trigger"
0x1800a89d7  mov     ecx, esi
0x1800a89d9  call    AslLogCallPrintf
0x1800a89de  jmp     short loc_1800A8A29
0x1800a89e0  movzx   eax, word ptr [rbx]
0x1800a89e3  lea     r9, aTriggerSentSEv; "Trigger sent,%s,EventId,%d"
0x1800a89ea  mov     [rsp+498h+cbData], eax
0x1800a89ee  lea     rcx, aSiuf; "Siuf"
0x1800a89f5  xor     r8d, r8d; unsigned int
0x1800a89f8  mov     [rsp+498h+lpData], r13
0x1800a89fd  mov     edx, ebp; unsigned int
0x1800a89ff  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a8a04  lea     rcx, qword_1801586E0; void *
0x1800a8a0b  mov     rdx, r14; Src
0x1800a8a0e  mov     r8d, 0B30h; Size
0x1800a8a14  call    memcpy_0
0x1800a8a19  call    cs:__imp_GetTickCount64
0x1800a8a1f  mov     cs:qword_1801586D8, rax
0x1800a8a26  mov     edi, r12d
0x1800a8a29  call    cs:__imp_RevertToSelf
0x1800a8a2f  lea     rcx, stru_180158698; lpCriticalSection
0x1800a8a36  call    cs:__imp_LeaveCriticalSection
0x1800a8a3c  xor     r9d, r9d
0x1800a8a3f  mov     [rsp+498h+lpData], r12
0x1800a8a44  xor     r8d, r8d
0x1800a8a47  mov     rcx, r15
0x1800a8a4a  lea     edx, [r9+0Bh]
0x1800a8a4e  call    ?PcaChainSetSlot@@YAK_KW4_PCA_SLOT_ID@@PEAX0P6AX2@Z@Z; PcaChainSetSlot(unsigned __int64,_PCA_SLOT_ID,void *,unsigned __int64,void (*)(void *))
0x1800a8a53  mov     eax, edi
0x1800a8a55  mov     rcx, [rsp+498h+var_48]
0x1800a8a5d  xor     rcx, rsp; StackCookie
0x1800a8a60  call    __security_check_cookie
0x1800a8a65  mov     rbx, [rsp+498h+arg_10]
0x1800a8a6d  add     rsp, 460h
0x1800a8a74  pop     r15
0x1800a8a76  pop     r14
0x1800a8a78  pop     r13
0x1800a8a7a  pop     r12
0x1800a8a7c  pop     rdi
0x1800a8a7d  pop     rsi
0x1800a8a7e  pop     rbp
0x1800a8a7f  retn
```

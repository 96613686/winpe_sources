# CUserSessionCollection::CollectSessions(void)

- ea: `0x180029350`
- end: `0x180029933`
- name: `?CollectSessions@CUserSessionCollection@@AEAAKXZ`
- size: `1507`
- prototype: `unsigned int __fastcall(CUserSessionCollection *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a908`

## callees

- `0x180013ae0`
- `0x180028880`
- `0x18002910c`
- `0x180029188`
- `0x180029350`
- `0x18002993c`
- `0x180029a64`
- `0x180029c60`
- `0x180029f38`
- `0x18002a048`
- `0x18002a12c`
- `0x18002a670`
- `0x18002a7a0`
- `0x180067fc4`
- `0x1800f1b14`
- `0x1800f1cac`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `msvcrt!free` at `0x180029731`
- `msvcrt!free` at `0x18002983a`
- `msvcrt!free` at `0x180029731`
- `msvcrt!free` at `0x18002983a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180029450`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180029450`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800296ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800296fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800298df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800296ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800296fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800298df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029436`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029494`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800298c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029436`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029494`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800298c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002990e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002990e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029920`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800298fb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800298fb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800294c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800294fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180029550`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800294c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800294fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180029550`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800298b9`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800298b9`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800298b2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800293d3`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180029657`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180029782`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800293d3`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180029657`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180029782`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x18002966e`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x18002966e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002968d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800296da`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002968d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800296da`

## string_xrefs

- `0x1800298ab`: `onecore\admin\wmi\wbem\providers\win32provider\common\session.cpp`
- `0x180029890`: `Token of process %d contains an invalid sid`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CUserSessionCollection::CollectSessions(__int64 **this)
{
  __int64 **v1; // r12
  __int64 v2; // rdi
  const unsigned __int16 *v3; // rdx
  CUserSessionCollection *v4; // rcx
  __int64 v5; // rcx
  DWORD ProcessList; // r14d
  char *v7; // rsi
  char *v8; // r13
  int v9; // esi
  __int64 v10; // rbx
  char *v11; // r13
  HANDLE v12; // rbx
  DWORD v13; // r14d
  void *v14; // rax
  int v15; // r14d
  int v16; // r15d
  __int64 *v17; // rdx
  __int64 v18; // rbx
  __int64 *i; // rax
  unsigned __int64 v20; // r9
  bool v21; // dl
  int v22; // r8d
  __int64 v23; // rax
  CSession *v24; // rcx
  char *j; // rbx
  void *v27; // rbx
  __int64 v28; // r8
  __int64 *v29; // rcx
  __int64 v30; // [rsp+28h] [rbp-D8h]
  DWORD LastError; // [rsp+30h] [rbp-D0h]
  DWORD TokenInformationLength; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  void **v34; // [rsp+40h] [rbp-C0h]
  LPVOID v35; // [rsp+48h] [rbp-B8h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h]
  CUserSessionCollection *v38; // [rsp+68h] [rbp-98h]
  void **v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+78h] [rbp-88h]
  char v41[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v42; // [rsp+88h] [rbp-78h]
  unsigned __int64 v43; // [rsp+90h] [rbp-70h]
  char v44[8]; // [rsp+98h] [rbp-68h] BYREF
  void **v45; // [rsp+A0h] [rbp-60h] BYREF
  void *v46; // [rsp+A8h] [rbp-58h]
  char v47; // [rsp+B0h] [rbp-50h]
  void **v48; // [rsp+C0h] [rbp-40h] BYREF
  char v49[8]; // [rsp+C8h] [rbp-38h] BYREF
  int v50; // [rsp+D0h] [rbp-30h]
  __int64 v51; // [rsp+D8h] [rbp-28h]
  int v52; // [rsp+E0h] [rbp-20h]
  int v53; // [rsp+E4h] [rbp-1Ch]
  __int64 v54; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v55; // [rsp+F0h] [rbp-10h]
  char v56[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v57[40]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v58; // [rsp+138h] [rbp+38h]
  __int64 v59; // [rsp+140h] [rbp+40h]
  _BYTE v60[24]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v61[64]; // [rsp+168h] [rbp+68h] BYREF
  int TokenInformation; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v63; // [rsp+1ACh] [rbp+ACh]
  __int128 v64; // [rsp+1BCh] [rbp+BCh]
  __int128 v65; // [rsp+1CCh] [rbp+CCh]
  int v66; // [rsp+1DCh] [rbp+DCh]

  v1 = this;
  v38 = (CUserSessionCollection *)this;
  *(_OWORD *)Block = 0;
  v37 = 0;
  v2 = -1;
  v42 = -1;
  TokenHandle = (HANDLE)-1LL;
  TokenInformation = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  TokenInformationLength = 0;
  CHString::CHString((CHString *)v44);
  CUserSessionCollection::EnablePrivilegeOnCurrentThread(v4, v3);
  ProcessList = CUserSessionCollection::GetProcessList(v5, Block);
  v7 = (char *)Block[1];
  v8 = (char *)Block[0];
  if ( !ProcessList )
  {
    v43 = 0xAAAAAAAAAAAAAAABuLL * (((char *)Block[1] - (char *)Block[0]) >> 3);
    if ( v43 )
    {
      v34 = 0;
      v9 = 0;
      v10 = 0;
      while ( 1 )
      {
        SetLastError(0);
        v11 = &v8[24 * v10];
        v12 = OpenProcess(0x400u, 0, *((_DWORD *)v11 + 2));
        if ( v2 != -1 )
          CloseHandle((HANDLE)v2);
        v2 = (__int64)v12;
        v42 = (__int64)v12;
        if ( !v12 )
          goto LABEL_7;
        SetLastError(0);
        v13 = 0;
        LastError = 0;
        if ( TokenHandle != (HANDLE)-1LL )
          CloseHandle(TokenHandle);
        TokenHandle = (HANDLE)-1LL;
        if ( !OpenProcessToken(v12, 8u, &TokenHandle) )
        {
LABEL_7:
          LastError = GetLastError();
          v13 = LastError;
        }
        if ( TokenHandle )
        {
          if ( !v13 )
          {
            SetLastError(0);
            LastError = 0;
            if ( !GetTokenInformation(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &TokenInformationLength) )
            {
              v13 = GetLastError();
              LastError = v13;
            }
          }
        }
        std::unique_ptr<unsigned char [0]>::unique_ptr<unsigned char [0]>(&v35);
        if ( !v13 && !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
        {
          v13 = GetLastError();
          LastError = v13;
          if ( v13 == 122 )
          {
            v14 = operator new(TokenInformationLength);
            std::unique_ptr<unsigned char [0]>::reset(&v35, v14);
            v34 = (void **)v35;
            if ( GetTokenInformation(TokenHandle, TokenUser, v35, TokenInformationLength, &TokenInformationLength) )
            {
              v13 = 0;
              LastError = 0;
            }
            else
            {
              v13 = GetLastError();
              LastError = v13;
            }
          }
        }
        if ( !v34 || v13 )
          goto LABEL_35;
        v15 = DWORD1(v63);
        v16 = DWORD2(v63);
        v17 = v1[1];
        v18 = *v17;
        while ( 1 )
        {
          if ( (__int64 *)v18 == v17 )
          {
            v27 = *v34;
            v48 = &CSession::`vftable';
            CHString::CHString((CHString *)v49);
            v54 = 0;
            v55 = 0;
            v52 = v15;
            v53 = v16;
            v50 = 0;
            v51 = 0;
            std::vector<CProcess>::push_back(&v54, v11);
            CUser::CUser((CUser *)&v45, v27);
            if ( v47 )
            {
              CUser::CUser((CUser *)v60, (PSID *)&v45);
              CSession::CSession((CSession *)v61, (const struct CSession *)&v48);
              std::_Tree<std::_Tmap_traits<CUser,CSession,CUserComp,std::allocator<std::pair<CUser const,CSession>>,1>>::_Insert_nohint<std::pair<CUser const,CSession>,std::_Nil>(
                v1 + 1,
                (__int64)v56,
                v28,
                (__int64)v60);
              CSession::~CSession((CSession *)v61);
              CUser::~CUser((CUser *)v60);
            }
            else
            {
              LODWORD(v30) = *((_DWORD *)v11 + 2);
              ProviderLog::LocalLogMessage(
                captainsLog,
                L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\common\\session.cpp",
                286,
                1,
                L"Token of process %d contains an invalid sid",
                v30);
            }
            v45 = &CUser::`vftable';
            if ( v46 )
            {
              free(v46);
              v46 = 0;
            }
            v24 = (CSession *)&v48;
            goto LABEL_34;
          }
          if ( *(_QWORD *)(v18 + 88) == *(_QWORD *)((char *)&v63 + 4) )
            break;
          if ( !*(_BYTE *)(v18 + 25) )
          {
            i = *(__int64 **)(v18 + 16);
            if ( *((_BYTE *)i + 25) )
            {
              for ( i = *(__int64 **)(v18 + 8); !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
              {
                if ( v18 != i[2] )
                  break;
                v18 = (__int64)i;
              }
LABEL_26:
              v18 = (__int64)i;
            }
            else
            {
              v29 = (__int64 *)*i;
              if ( *(_BYTE *)(*i + 25) )
                goto LABEL_26;
              do
              {
                v18 = (__int64)v29;
                v29 = (__int64 *)*v29;
              }
              while ( !*((_BYTE *)v29 + 25) );
            }
          }
        }
        CSession::CSession((CSession *)v57, (const struct CSession *)(v18 + 56));
        v20 = 0xAAAAAAAAAAAAAAABuLL * ((v59 - v58) >> 3);
        if ( v20 )
        {
          v21 = 0;
          v22 = 0;
          v23 = 0;
          while ( !v21 )
          {
            v21 = *(_DWORD *)(v58 + 24 * v23 + 8) == *((_DWORD *)v11 + 2);
            v23 = ++v22;
            if ( v22 >= v20 )
            {
              if ( v21 )
                break;
              goto LABEL_32;
            }
          }
        }
        else
        {
LABEL_32:
          v39 = &CProcess::`vftable';
          CHString::CHString((CHString *)v41);
          v40 = *((_DWORD *)v11 + 2);
          CHString::operator=(v41, v11 + 16);
          std::vector<CProcess>::push_back(v18 + 96, &v39);
          v39 = &CProcess::`vftable';
          CHString::~CHString((CHString *)v41);
        }
        v24 = (CSession *)v57;
LABEL_34:
        CSession::~CSession(v24);
        v1 = (__int64 **)v38;
LABEL_35:
        CDeleteUs<_PROCESSOR_POWER_INFORMATION>::~CDeleteUs<_PROCESSOR_POWER_INFORMATION>(&v35);
        v10 = ++v9;
        v8 = (char *)Block[0];
        if ( v9 >= v43 )
        {
          v7 = (char *)Block[1];
          ProcessList = LastError;
          break;
        }
      }
    }
  }
  CUserSessionCollection::CollectNoProcessesSessions((CUserSessionCollection *)v1);
  CHString::~CHString((CHString *)v44);
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  if ( v2 != -1 )
    CloseHandle((HANDLE)v2);
  if ( v8 )
  {
    for ( j = v8; j != v7; j += 24 )
      (**(void (__fastcall ***)(char *, _QWORD))j)(j, 0);
    free(v8);
    *(_OWORD *)Block = 0;
    v37 = 0;
  }
  return ProcessList;
}

```

## disassembly

```asm
0x180029350  push    rbp
0x180029352  push    rbx
0x180029353  push    rsi
0x180029354  push    rdi
0x180029355  push    r12
0x180029357  push    r13
0x180029359  push    r14
0x18002935b  push    r15
0x18002935d  lea     rbp, [rsp-0F8h]
0x180029365  sub     rsp, 1F8h
0x18002936c  mov     rax, cs:__security_cookie
0x180029373  xor     rax, rsp
0x180029376  mov     [rbp+130h+var_50], rax
0x18002937d  mov     r12, rcx
0x180029380  mov     [rsp+230h+var_1C8], rcx
0x180029385  xorps   xmm0, xmm0
0x180029388  movdqu  xmmword ptr [rsp+230h+Block], xmm0
0x18002938e  xor     r15d, r15d
0x180029391  mov     [rsp+230h+var_1D0], r15
0x180029396  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18002939d  mov     [rbp+130h+var_1A8], rdi
0x1800293a1  mov     [rsp+230h+TokenHandle], rdi
0x1800293a6  mov     [rbp+130h+TokenInformation], r15d
0x1800293ad  xor     eax, eax
0x1800293af  movups  [rbp+130h+var_84], xmm0
0x1800293b6  movups  [rbp+130h+var_74], xmm0
0x1800293bd  movups  [rbp+130h+var_64], xmm0
0x1800293c4  mov     [rbp+130h+var_54], eax
0x1800293ca  mov     [rsp+230h+TokenInformationLength], r15d
0x1800293cf  lea     rcx, [rbp+130h+var_198]
0x1800293d3  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800293d9  nop
0x1800293da  call    ?EnablePrivilegeOnCurrentThread@CUserSessionCollection@@AEBAKPEBG@Z; CUserSessionCollection::EnablePrivilegeOnCurrentThread(ushort const *)
0x1800293df  lea     rdx, [rsp+230h+Block]
0x1800293e4  call    ?GetProcessList@CUserSessionCollection@@AEBAKAEAV?$vector@VCProcess@@V?$allocator@VCProcess@@@std@@@std@@@Z; CUserSessionCollection::GetProcessList(std::vector<CProcess> &)
0x1800293e9  mov     r14d, eax
0x1800293ec  mov     rsi, [rsp+230h+Block+8]
0x1800293f1  mov     r13, [rsp+230h+Block]
0x1800293f6  test    eax, eax
0x1800293f8  jnz     loc_1800296CD
0x1800293fe  mov     rax, rsi
0x180029401  sub     rax, r13
0x180029404  sar     rax, 3
0x180029408  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180029412  imul    rax, rcx
0x180029416  mov     [rbp+130h+var_1A0], rax
0x18002941a  test    rax, rax
0x18002941d  jz      loc_1800296CD
0x180029423  mov     [rsp+230h+var_1F0], r15
0x180029428  mov     esi, r15d
0x18002942b  mov     ebx, r15d
0x18002942e  mov     r15d, 1
0x180029434  xor     ecx, ecx; dwErrCode
0x180029436  call    cs:__imp_SetLastError
0x18002943c  lea     rax, [rbx+rbx*2]
0x180029440  lea     r13, [r13+rax*8+0]
0x180029445  mov     r8d, [r13+8]; dwProcessId
0x180029449  xor     edx, edx; bInheritHandle
0x18002944b  mov     ecx, 400h; dwDesiredAccess
0x180029450  call    cs:__imp_OpenProcess
0x180029456  mov     rbx, rax
0x180029459  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002945d  jz      short loc_180029468
0x18002945f  mov     rcx, rdi; hObject
0x180029462  call    cs:__imp_CloseHandle
0x180029468  mov     rdi, rbx
0x18002946b  mov     [rbp+130h+var_1A8], rbx
0x18002946f  test    rbx, rbx
0x180029472  jnz     loc_1800298C4
0x180029478  call    cs:__imp_GetLastError
0x18002947e  mov     [rsp+230h+var_200], eax
0x180029482  mov     r14d, eax
0x180029485  cmp     [rsp+230h+TokenHandle], 0
0x18002948b  jz      short loc_1800294CE
0x18002948d  test    r14d, r14d
0x180029490  jnz     short loc_1800294CE
0x180029492  xor     ecx, ecx; dwErrCode
0x180029494  call    cs:__imp_SetLastError
0x18002949a  mov     [rsp+230h+var_200], r14d
0x18002949f  lea     rax, [rsp+230h+TokenInformationLength]
0x1800294a4  mov     [rsp+230h+ReturnLength], rax; ReturnLength
0x1800294a9  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800294af  lea     r8, [rbp+130h+TokenInformation]; TokenInformation
0x1800294b6  mov     edx, 0Ah; TokenInformationClass
0x1800294bb  mov     rcx, [rsp+230h+TokenHandle]; TokenHandle
0x1800294c0  call    cs:__imp_GetTokenInformation
0x1800294c6  test    eax, eax
0x1800294c8  jz      loc_18002990E
0x1800294ce  lea     rcx, [rsp+230h+var_1E8]
0x1800294d3  call    ??0?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::unique_ptr<uchar [0]>(void)
0x1800294d8  nop
0x1800294d9  test    r14d, r14d
0x1800294dc  jnz     loc_180029566
0x1800294e2  lea     rax, [rsp+230h+TokenInformationLength]
0x1800294e7  mov     [rsp+230h+ReturnLength], rax; ReturnLength
0x1800294ec  xor     r9d, r9d; TokenInformationLength
0x1800294ef  xor     r8d, r8d; TokenInformation
0x1800294f2  mov     edx, r15d; TokenInformationClass
0x1800294f5  mov     rcx, [rsp+230h+TokenHandle]; TokenHandle
0x1800294fa  call    cs:__imp_GetTokenInformation
0x180029500  test    eax, eax
0x180029502  jnz     short loc_180029566
0x180029504  call    cs:__imp_GetLastError
0x18002950a  mov     r14d, eax
0x18002950d  mov     [rsp+230h+var_200], eax
0x180029511  cmp     eax, 7Ah ; 'z'
0x180029514  jnz     short loc_180029566
0x180029516  mov     ecx, [rsp+230h+TokenInformationLength]; unsigned __int64
0x18002951a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002951f  mov     rdx, rax
0x180029522  lea     rcx, [rsp+230h+var_1E8]
0x180029527  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0]>::reset(uchar *)
0x18002952c  mov     rax, [rsp+230h+var_1E8]
0x180029531  mov     [rsp+230h+var_1F0], rax
0x180029536  lea     rcx, [rsp+230h+TokenInformationLength]
0x18002953b  mov     [rsp+230h+ReturnLength], rcx; ReturnLength
0x180029540  mov     r9d, [rsp+230h+TokenInformationLength]; TokenInformationLength
0x180029545  mov     r8, rax; TokenInformation
0x180029548  mov     edx, r15d; TokenInformationClass
0x18002954b  mov     rcx, [rsp+230h+TokenHandle]; TokenHandle
0x180029550  call    cs:__imp_GetTokenInformation
0x180029556  test    eax, eax
0x180029558  jz      loc_180029920
0x18002955e  xor     r14d, r14d
0x180029561  mov     [rsp+230h+var_200], r14d
0x180029566  cmp     [rsp+230h+var_1F0], 0
0x18002956c  jz      loc_1800296A2
0x180029572  test    r14d, r14d
0x180029575  jnz     loc_1800296A2
0x18002957b  mov     r14d, dword ptr [rbp+130h+var_84+4]
0x180029582  mov     r15d, dword ptr [rbp+130h+var_84+8]
0x180029589  mov     rdx, [r12+8]
0x18002958e  mov     rbx, [rdx]
0x180029591  cmp     rbx, rdx
0x180029594  jz      loc_18002976B
0x18002959a  mov     rcx, [rbx+58h]
0x18002959e  mov     rax, rcx
0x1800295a1  shr     rax, 20h
0x1800295a5  cmp     ecx, r14d
0x1800295a8  jz      short loc_1800295D7
0x1800295aa  cmp     byte ptr [rbx+19h], 0
0x1800295ae  jnz     short loc_180029591
0x1800295b0  mov     rax, [rbx+10h]
0x1800295b4  cmp     byte ptr [rax+19h], 0
0x1800295b8  jz      loc_180029851
0x1800295be  mov     rax, [rbx+8]
0x1800295c2  cmp     byte ptr [rax+19h], 0
0x1800295c6  jnz     short loc_1800295D2
0x1800295c8  cmp     rbx, [rax+10h]
0x1800295cc  jz      loc_180029872
0x1800295d2  mov     rbx, rax
0x1800295d5  jmp     short loc_180029591
0x1800295d7  cmp     eax, r15d
0x1800295da  jnz     short loc_1800295AA
0x1800295dc  lea     rdx, [rbx+38h]; struct CSession *
0x1800295e0  lea     rcx, [rbp+130h+var_120]; this
0x1800295e4  call    ??0CSession@@QEAA@AEBV0@@Z; CSession::CSession(CSession const &)
0x1800295e9  nop
0x1800295ea  mov     r9, [rbp+130h+var_F0]
0x1800295ee  mov     r10, [rbp+130h+var_F8]
0x1800295f2  sub     r9, r10
0x1800295f5  sar     r9, 3
0x1800295f9  mov     rax, 0AAAAAAAAAAAAAAABh
0x180029603  imul    r9, rax
0x180029607  mov     r15d, 1
0x18002960d  test    r9, r9
0x180029610  jz      short loc_180029647
0x180029612  xor     dl, dl
0x180029614  xor     r8d, r8d
0x180029617  xor     eax, eax
0x180029619  nop     dword ptr [rax+00000000h]
0x180029620  test    dl, dl
0x180029622  jnz     short loc_180029694
0x180029624  lea     rcx, [rax+rax*2]
0x180029628  movzx   edx, dl
0x18002962b  mov     eax, [r13+8]
0x18002962f  cmp     [r10+rcx*8+8], eax
0x180029634  cmovz   edx, r15d
0x180029638  inc     r8d
0x18002963b  movsxd  rax, r8d
0x18002963e  cmp     rax, r9
0x180029641  jb      short loc_180029620
0x180029643  test    dl, dl
0x180029645  jnz     short loc_180029694
0x180029647  lea     r14, ??_7CProcess@@6B@; const CProcess::`vftable'
0x18002964e  mov     [rsp+230h+var_1C0], r14
0x180029653  lea     rcx, [rbp+130h+var_1B0]
0x180029657  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18002965d  nop
0x18002965e  mov     eax, [r13+8]
0x180029662  mov     [rsp+230h+var_1B8], eax
0x180029666  lea     rdx, [r13+10h]
0x18002966a  lea     rcx, [rbp+130h+var_1B0]
0x18002966e  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x180029674  nop
0x180029675  lea     rcx, [rbx+60h]
0x180029679  lea     rdx, [rsp+230h+var_1C0]
0x18002967e  call    ?push_back@?$vector@VCProcess@@V?$allocator@VCProcess@@@std@@@std@@QEAAX$$QEAVCProcess@@@Z; std::vector<CProcess>::push_back(CProcess &&)
0x180029683  nop
0x180029684  mov     [rsp+230h+var_1C0], r14
0x180029689  lea     rcx, [rbp+130h+var_1B0]
0x18002968d  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180029693  nop
0x180029694  lea     rcx, [rbp+130h+var_120]; this
0x180029698  call    ??1CSession@@UEAA@XZ; CSession::~CSession(void)
0x18002969d  mov     r12, [rsp+230h+var_1C8]
0x1800296a2  lea     rcx, [rsp+230h+var_1E8]
0x1800296a7  call    ??1?$CDeleteUs@U_PROCESSOR_POWER_INFORMATION@@@@QEAA@XZ; CDeleteUs<_PROCESSOR_POWER_INFORMATION>::~CDeleteUs<_PROCESSOR_POWER_INFORMATION>(void)
0x1800296ac  inc     esi
0x1800296ae  movsxd  rbx, esi
0x1800296b1  cmp     rbx, [rbp+130h+var_1A0]
0x1800296b5  mov     r13, [rsp+230h+Block]
0x1800296ba  jb      loc_180029434
0x1800296c0  mov     rsi, [rsp+230h+Block+8]
0x1800296c5  mov     r14d, [rsp+230h+var_200]
0x1800296ca  xor     r15d, r15d
0x1800296cd  mov     rcx, r12; this
0x1800296d0  call    ?CollectNoProcessesSessions@CUserSessionCollection@@AEAAKXZ; CUserSessionCollection::CollectNoProcessesSessions(void)
0x1800296d5  nop
0x1800296d6  lea     rcx, [rbp+130h+var_198]
0x1800296da  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800296e0  nop
0x1800296e1  mov     rcx, [rsp+230h+TokenHandle]; hObject
0x1800296e6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800296ea  jz      short loc_1800296F3
0x1800296ec  call    cs:__imp_CloseHandle
0x1800296f2  nop
0x1800296f3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800296f7  jz      short loc_180029703
0x1800296f9  mov     rcx, rdi; hObject
0x1800296fc  call    cs:__imp_CloseHandle
0x180029702  nop
0x180029703  test    r13, r13
0x180029706  jz      short loc_180029745
0x180029708  mov     rbx, r13
0x18002970b  cmp     r13, rsi
0x18002970e  jz      short loc_180029729
0x180029710  mov     rax, [rbx]
0x180029713  xor     edx, edx
0x180029715  mov     rcx, rbx
0x180029718  mov     rax, [rax]
0x18002971b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029720  add     rbx, 18h
0x180029724  cmp     rbx, rsi
0x180029727  jnz     short loc_180029710
0x180029729  test    r13, r13
0x18002972c  jz      short loc_180029737
0x18002972e  mov     rcx, r13; Block
0x180029731  call    cs:__imp_free
0x180029737  xorps   xmm0, xmm0
0x18002973a  movdqu  xmmword ptr [rsp+230h+Block], xmm0
0x180029740  mov     [rsp+230h+var_1D0], r15
0x180029745  mov     eax, r14d
0x180029748  mov     rcx, [rbp+130h+var_50]
0x18002974f  xor     rcx, rsp; StackCookie
0x180029752  call    __security_check_cookie
0x180029757  add     rsp, 1F8h
0x18002975e  pop     r15
0x180029760  pop     r14
0x180029762  pop     r13
0x180029764  pop     r12
0x180029766  pop     rdi
0x180029767  pop     rsi
0x180029768  pop     rbx
0x180029769  pop     rbp
0x18002976a  retn
0x18002976b  mov     rbx, [rsp+230h+var_1F0]
0x180029770  mov     rbx, [rbx]
0x180029773  lea     rax, ??_7CSession@@6B@; const CSession::`vftable'
0x18002977a  mov     [rbp+130h+var_170], rax
0x18002977e  lea     rcx, [rbp+130h+var_168]
0x180029782  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180029788  nop
0x180029789  mov     [rbp+130h+var_148], 0
0x180029791  xorps   xmm0, xmm0
0x180029794  movdqa  [rbp+130h+var_140], xmm0
0x180029799  mov     [rbp+130h+var_150], r14d
0x18002979d  mov     [rbp+130h+var_14C], r15d
0x1800297a1  mov     [rbp+130h+var_160], 0
0x1800297a8  mov     [rbp+130h+var_158], 0
0x1800297b0  mov     rdx, r13
0x1800297b3  lea     rcx, [rbp+130h+var_148]
0x1800297b7  call    ?push_back@?$vector@VCProcess@@V?$allocator@VCProcess@@@std@@@std@@QEAAXAEBVCProcess@@@Z; std::vector<CProcess>::push_back(CProcess const &)
0x1800297bc  mov     rdx, rbx; void *
0x1800297bf  lea     rcx, [rbp+130h+var_190]; this
0x1800297c3  call    ??0CUser@@QEAA@PEAX@Z; CUser::CUser(void *)
0x1800297c8  nop
0x1800297c9  cmp     [rbp+130h+var_180], 0
0x1800297cd  jz      loc_180029888
0x1800297d3  lea     rdx, [rbp+130h+var_190]; struct CUser *
0x1800297d7  lea     rcx, [rbp+130h+var_E0]; this
0x1800297db  call    ??0CUser@@QEAA@AEBV0@@Z; CUser::CUser(CUser const &)
0x1800297e0  nop
0x1800297e1  lea     rdx, [rbp+130h+var_170]; struct CSession *
0x1800297e5  lea     rcx, [rbp+130h+var_C8]; this
0x1800297e9  call    ??0CSession@@QEAA@AEBV0@@Z; CSession::CSession(CSession const &)
0x1800297ee  nop
0x1800297ef  movzx   eax, cs:byte_1801904CF
0x1800297f6  mov     byte ptr [rsp+230h+ReturnLength], al
0x1800297fa  lea     r9, [rbp+130h+var_E0]
  ... truncated ...
```

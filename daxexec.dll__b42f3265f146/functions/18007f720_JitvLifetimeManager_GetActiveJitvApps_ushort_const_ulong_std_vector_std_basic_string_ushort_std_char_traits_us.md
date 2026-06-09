# JitvLifetimeManager::GetActiveJitvApps(ushort const * *,ulong,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18007f720`
- end: `0x18007fb50`
- name: `?GetActiveJitvApps@JitvLifetimeManager@@AEAAXPEAPEBGKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1072`
- prototype: `void __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007f040`

## callees

- `0x180004f70`
- `0x18000e074`
- `0x1800125f4`
- `0x180012fb8`
- `0x180013510`
- `0x1800210fc`
- `0x180032cf0`
- `0x18005db00`
- `0x18007c7b0`
- `0x18007f720`
- `0x1800ae644`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f891`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007f84d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007f84d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f8d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007fa45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f8d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007fa45`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007f87d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007f974`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007f87d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007f974`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x18007f9af`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x18007f9af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa91`

## pseudocode

```c
void __fastcall JitvLifetimeManager::GetActiveJitvApps(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // ebx
  unsigned int v6; // r13d
  __m128i si128; // xmm6
  __int64 v8; // rdx
  __int64 v9; // r8
  _QWORD *v10; // rcx
  int ProcessesInVirtualizationContext; // eax
  void *v12; // rcx
  unsigned int v13; // r12d
  DWORD ProcessId; // eax
  const char *v15; // r9
  DWORD v16; // r15d
  void *v17; // rsi
  char *v18; // rbx
  unsigned __int16 **v19; // r8
  signed int LastError; // eax
  signed int ProcessAppId; // edi
  __int64 v22; // r8
  _OWORD *v23; // rdx
  HANDLE v24; // rax
  const char *v25; // r9
  void *v26; // rbx
  const char *v27; // r9
  __int64 v28; // r8
  _OWORD *v29; // rdx
  void *v30; // rcx
  unsigned int v31; // eax
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID v33; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v34; // [rsp+30h] [rbp-D0h]
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+40h] [rbp-C0h]
  HANDLE v37; // [rsp+48h] [rbp-B8h]
  __int128 v38; // [rsp+50h] [rbp-B0h] BYREF
  __m128i v39; // [rsp+60h] [rbp-A0h]
  _OWORD v40[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v41[4]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR BaseName[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  if ( a3 )
  {
    v5 = a3;
    v34 = a3;
    v36 = a2;
    v6 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v32 = 0;
      v33 = 0;
      v8 = *(_QWORD *)(a2 + 8LL * v6);
      memset(v40, 0, sizeof(v40));
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      std::wstring::_Construct<1,unsigned short const *>(v40, v8, v9);
      GetPackageFamilyNameFromFullName(v41, v40);
      std::wstring::~wstring(v40);
      *(_QWORD *)&v38 = &v33;
      *((_QWORD *)&v38 + 1) = 0;
      v39.m128i_i8[0] = 1;
      v10 = v41;
      if ( v41[3] > 7u )
        v10 = (_QWORD *)v41[0];
      ProcessesInVirtualizationContext = GetProcessesInVirtualizationContext(
                                           (__int64)v10,
                                           (__int64)&v32,
                                           (__int64)&v38 + 8);
      if ( ProcessesInVirtualizationContext < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
          (const char *)(unsigned int)ProcessesInVirtualizationContext,
          v32);
      if ( v39.m128i_i8[0] )
      {
        v12 = *(void **)v38;
        *(_QWORD *)v38 = *((_QWORD *)&v38 + 1);
        if ( v12 )
          CoTaskMemFree(v12);
      }
      v13 = 0;
      if ( v32 )
      {
        do
        {
          ProcessId = GetProcessId(*((HANDLE *)v33 + v13));
          v16 = ProcessId;
          if ( !ProcessId )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x76,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
              v15);
          v17 = 0;
          pv = 0;
          v18 = (char *)OpenProcess(0x1000u, 0, ProcessId);
          if ( !v18 )
          {
            LastError = GetLastError();
            ProcessAppId = LastError;
            if ( LastError > 0 )
              ProcessAppId = (unsigned __int16)LastError | 0x80070000;
            if ( ProcessAppId < 0 )
              goto LABEL_26;
          }
          ProcessAppId = CallerIdentity::GetProcessAppId(v18, &pv, v19);
          if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v18);
          v17 = pv;
          if ( ProcessAppId >= 0 )
          {
            v38 = 0;
            v39 = 0;
            v22 = -1;
            do
              ++v22;
            while ( *((_WORD *)pv + v22) );
            std::wstring::_Construct<1,unsigned short const *>(&v38, pv, v22);
            v23 = *(_OWORD **)(a4 + 8);
            if ( v23 == *(_OWORD **)(a4 + 16) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a4, v23, &v38);
            }
            else
            {
              *v23 = v38;
              v23[1] = v39;
              v39 = si128;
              LOWORD(v38) = 0;
              *(_QWORD *)(a4 + 8) += 32LL;
            }
            std::wstring::~wstring(&v38);
          }
          else
          {
LABEL_26:
            if ( ProcessAppId != -2147023728 )
            {
              v31 = wil::verify_hresult((unsigned int)ProcessAppId);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x8A,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
                (const char *)v31,
                v32);
            }
            v24 = OpenProcess(0x410u, 0, v16);
            v26 = v24;
            v37 = v24;
            if ( v24 == (HANDLE)-1LL )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x82,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
                v25);
            if ( !K32GetModuleBaseNameW(v24, 0, BaseName, 0x104u) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x85,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
                v27);
            v38 = 0;
            v39 = 0;
            v28 = -1;
            do
              ++v28;
            while ( BaseName[v28] );
            std::wstring::_Construct<1,unsigned short const *>(&v38, BaseName, v28);
            v29 = *(_OWORD **)(a4 + 8);
            if ( v29 == *(_OWORD **)(a4 + 16) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a4, v29, &v38);
            }
            else
            {
              *v29 = v38;
              v29[1] = v39;
              v39 = si128;
              LOWORD(v38) = 0;
              *(_QWORD *)(a4 + 8) += 32LL;
            }
            std::wstring::~wstring(&v38);
            if ( v26 )
              CloseHandle(v26);
          }
          if ( v17 )
            CoTaskMemFree(v17);
          ++v13;
        }
        while ( v13 < v32 );
        v5 = v34;
      }
      std::wstring::~wstring(v41);
      v30 = v33;
      v33 = 0;
      if ( v30 )
        CoTaskMemFree(v30);
      if ( ++v6 >= v5 )
        break;
      a2 = v36;
    }
  }
}

```

## disassembly

```asm
0x18007f720  test    r8d, r8d
0x18007f723  jz      locret_18007FADD
0x18007f729  mov     rax, rsp
0x18007f72c  mov     [rax+8], rbx
0x18007f730  push    rbp
0x18007f731  push    rsi
0x18007f732  push    rdi
0x18007f733  push    r12
0x18007f735  push    r13
0x18007f737  push    r14
0x18007f739  push    r15
0x18007f73b  lea     rbp, [rax-218h]
0x18007f742  sub     rsp, 2E0h
0x18007f749  movaps  xmmword ptr [rax-48h], xmm6
0x18007f74d  mov     rax, cs:__security_cookie
0x18007f754  xor     rax, rsp
0x18007f757  mov     [rbp+210h+var_50], rax
0x18007f75e  mov     r14, r9
0x18007f761  mov     ebx, r8d
0x18007f764  mov     [rsp+310h+var_2E0], ebx
0x18007f768  mov     [rsp+310h+var_2D0], rdx
0x18007f76d  xor     edi, edi
0x18007f76f  mov     r13d, edi
0x18007f772  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18007f77a  mov     [rsp+310h+var_2F0], edi; int
0x18007f77e  mov     [rsp+310h+var_2E8], rdi
0x18007f783  mov     eax, r13d
0x18007f786  mov     rdx, [rdx+rax*8]
0x18007f78a  xorps   xmm0, xmm0
0x18007f78d  movups  [rsp+310h+var_2A0], xmm0
0x18007f792  xorps   xmm1, xmm1
0x18007f795  movdqu  [rbp+210h+var_290], xmm1
0x18007f79a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007f79e  inc     r8
0x18007f7a1  cmp     [rdx+r8*2], di
0x18007f7a6  jnz     short loc_18007F79E
0x18007f7a8  lea     rcx, [rsp+310h+var_2A0]
0x18007f7ad  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007f7b2  nop
0x18007f7b3  lea     rdx, [rsp+310h+var_2A0]
0x18007f7b8  lea     rcx, [rbp+210h+var_280]
0x18007f7bc  call    ?GetPackageFamilyNameFromFullName@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; GetPackageFamilyNameFromFullName(std::wstring const &)
0x18007f7c1  nop
0x18007f7c2  lea     rcx, [rsp+310h+var_2A0]; void *
0x18007f7c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007f7cc  lea     rax, [rsp+310h+var_2E8]
0x18007f7d1  mov     qword ptr [rsp+310h+var_2C0], rax
0x18007f7d6  mov     qword ptr [rsp+310h+var_2C0+8], rdi
0x18007f7db  mov     byte ptr [rsp+310h+var_2B0], 1
0x18007f7e0  lea     rcx, [rbp+210h+var_280]
0x18007f7e4  cmp     [rbp+210h+var_268], 7
0x18007f7e9  cmova   rcx, [rbp+210h+var_280]
0x18007f7ee  lea     r8, [rsp+310h+var_2C0+8]
0x18007f7f3  lea     rdx, [rsp+310h+var_2F0]
0x18007f7f8  call    GetProcessesInVirtualizationContext
0x18007f7fd  mov     rcx, [rbp+218h]; this
0x18007f804  test    eax, eax
0x18007f806  js      loc_18007FADF
0x18007f80c  cmp     byte ptr [rsp+310h+var_2B0], dil
0x18007f811  jz      short loc_18007F834
0x18007f813  mov     rdx, qword ptr [rsp+310h+var_2C0]
0x18007f818  mov     rcx, [rdx]; pv
0x18007f81b  mov     rax, qword ptr [rsp+310h+var_2C0+8]
0x18007f820  mov     [rdx], rax
0x18007f823  test    rcx, rcx
0x18007f826  jz      short loc_18007F834
0x18007f828  call    cs:__imp_CoTaskMemFree
0x18007f82f  nop     dword ptr [rax+rax+00h]
0x18007f834  mov     r12d, edi
0x18007f837  cmp     [rsp+310h+var_2F0], edi
0x18007f83b  jbe     loc_18007FA78
0x18007f841  mov     eax, r12d
0x18007f844  mov     rcx, [rsp+310h+var_2E8]
0x18007f849  mov     rcx, [rcx+rax*8]; Process
0x18007f84d  call    cs:__imp_GetProcessId
0x18007f854  nop     dword ptr [rax+rax+00h]
0x18007f859  mov     r15d, eax
0x18007f85c  mov     rcx, [rbp+218h]; this
0x18007f863  test    eax, eax
0x18007f865  jz      loc_18007FB3E
0x18007f86b  mov     rsi, rdi
0x18007f86e  mov     [rsp+310h+pv], rdi
0x18007f873  mov     r8d, eax; dwProcessId
0x18007f876  xor     edx, edx; bInheritHandle
0x18007f878  mov     ecx, 1000h; dwDesiredAccess
0x18007f87d  call    cs:__imp_OpenProcess
0x18007f884  nop     dword ptr [rax+rax+00h]
0x18007f889  mov     rbx, rax
0x18007f88c  test    rax, rax
0x18007f88f  jnz     short loc_18007F8B4
0x18007f891  call    cs:__imp_GetLastError
0x18007f898  nop     dword ptr [rax+rax+00h]
0x18007f89d  mov     edi, eax
0x18007f89f  test    eax, eax
0x18007f8a1  jle     short loc_18007F8AC
0x18007f8a3  movzx   edi, ax
0x18007f8a6  or      edi, 80070000h
0x18007f8ac  test    edi, edi
0x18007f8ae  js      loc_18007F95E
0x18007f8b4  lea     rdx, [rsp+310h+pv]; void *
0x18007f8b9  mov     rcx, rbx; ProcessHandle
0x18007f8bc  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x18007f8c1  mov     edi, eax
0x18007f8c3  lea     rcx, [rbx-1]
0x18007f8c7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18007f8cb  ja      short loc_18007F8DC
0x18007f8cd  mov     rcx, rbx; hObject
0x18007f8d0  call    cs:__imp_CloseHandle
0x18007f8d7  nop     dword ptr [rax+rax+00h]
0x18007f8dc  mov     rsi, [rsp+310h+pv]
0x18007f8e1  test    edi, edi
0x18007f8e3  js      short loc_18007F95E
0x18007f8e5  xorps   xmm0, xmm0
0x18007f8e8  movups  [rsp+310h+var_2C0], xmm0
0x18007f8ed  xorps   xmm1, xmm1
0x18007f8f0  movdqu  [rsp+310h+var_2B0], xmm1
0x18007f8f6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007f8fa  xor     edi, edi
0x18007f8fc  inc     r8
0x18007f8ff  cmp     [rsi+r8*2], di
0x18007f904  jnz     short loc_18007F8FC
0x18007f906  mov     rdx, rsi
0x18007f909  lea     rcx, [rsp+310h+var_2C0]
0x18007f90e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007f913  nop
0x18007f914  mov     rdx, [r14+8]
0x18007f918  cmp     rdx, [r14+10h]
0x18007f91c  jz      short loc_18007F941
0x18007f91e  movups  xmm0, [rsp+310h+var_2C0]
0x18007f923  movups  xmmword ptr [rdx], xmm0
0x18007f926  movups  xmm1, [rsp+310h+var_2B0]
0x18007f92b  movups  xmmword ptr [rdx+10h], xmm1
0x18007f92f  movdqu  [rsp+310h+var_2B0], xmm6
0x18007f935  mov     word ptr [rsp+310h+var_2C0], di
0x18007f93a  add     qword ptr [r14+8], 20h ; ' '
0x18007f93f  jmp     short loc_18007F94F
0x18007f941  lea     r8, [rsp+310h+var_2C0]
0x18007f946  mov     rcx, r14
0x18007f949  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18007f94e  nop
0x18007f94f  lea     rcx, [rsp+310h+var_2C0]; void *
0x18007f954  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007f959  jmp     loc_18007FA52
0x18007f95e  cmp     edi, 80070490h
0x18007f964  jnz     loc_18007FB1B
0x18007f96a  mov     r8d, r15d; dwProcessId
0x18007f96d  xor     edx, edx; bInheritHandle
0x18007f96f  mov     ecx, 410h; dwDesiredAccess
0x18007f974  call    cs:__imp_OpenProcess
0x18007f97b  nop     dword ptr [rax+rax+00h]
0x18007f980  mov     rbx, rax
0x18007f983  mov     [rsp+310h+var_2C8], rax
0x18007f988  mov     rcx, [rbp+218h]; this
0x18007f98f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007f993  jz      loc_18007FB09
0x18007f999  mov     rdi, [rbp+218h]
0x18007f9a0  mov     r9d, 104h; nSize
0x18007f9a6  lea     r8, [rbp+210h+BaseName]; lpBaseName
0x18007f9aa  xor     edx, edx; hModule
0x18007f9ac  mov     rcx, rax; hProcess
0x18007f9af  call    cs:__imp_K32GetModuleBaseNameW
0x18007f9b6  nop     dword ptr [rax+rax+00h]
0x18007f9bb  test    eax, eax
0x18007f9bd  jz      loc_18007FAF4
0x18007f9c3  xorps   xmm0, xmm0
0x18007f9c6  movups  [rsp+310h+var_2C0], xmm0
0x18007f9cb  xorps   xmm1, xmm1
0x18007f9ce  movdqu  [rsp+310h+var_2B0], xmm1
0x18007f9d4  lea     rax, [rbp+210h+BaseName]
0x18007f9d8  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007f9dc  xor     edi, edi
0x18007f9de  inc     r8
0x18007f9e1  cmp     [rax+r8*2], di
0x18007f9e6  jnz     short loc_18007F9DE
0x18007f9e8  lea     rdx, [rbp+210h+BaseName]
0x18007f9ec  lea     rcx, [rsp+310h+var_2C0]
0x18007f9f1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007f9f6  nop
0x18007f9f7  mov     rdx, [r14+8]
0x18007f9fb  cmp     rdx, [r14+10h]
0x18007f9ff  jz      short loc_18007FA24
0x18007fa01  movups  xmm0, [rsp+310h+var_2C0]
0x18007fa06  movups  xmmword ptr [rdx], xmm0
0x18007fa09  movups  xmm1, [rsp+310h+var_2B0]
0x18007fa0e  movups  xmmword ptr [rdx+10h], xmm1
0x18007fa12  movdqu  [rsp+310h+var_2B0], xmm6
0x18007fa18  mov     word ptr [rsp+310h+var_2C0], di
0x18007fa1d  add     qword ptr [r14+8], 20h ; ' '
0x18007fa22  jmp     short loc_18007FA32
0x18007fa24  lea     r8, [rsp+310h+var_2C0]
0x18007fa29  mov     rcx, r14
0x18007fa2c  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18007fa31  nop
0x18007fa32  lea     rcx, [rsp+310h+var_2C0]; void *
0x18007fa37  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007fa3c  nop
0x18007fa3d  test    rbx, rbx
0x18007fa40  jz      short loc_18007FA52
0x18007fa42  mov     rcx, rbx; hObject
0x18007fa45  call    cs:__imp_CloseHandle
0x18007fa4c  nop     dword ptr [rax+rax+00h]
0x18007fa51  nop
0x18007fa52  test    rsi, rsi
0x18007fa55  jz      short loc_18007FA66
0x18007fa57  mov     rcx, rsi; pv
0x18007fa5a  call    cs:__imp_CoTaskMemFree
0x18007fa61  nop     dword ptr [rax+rax+00h]
0x18007fa66  inc     r12d
0x18007fa69  cmp     r12d, [rsp+310h+var_2F0]
0x18007fa6e  jb      loc_18007F841
0x18007fa74  mov     ebx, [rsp+310h+var_2E0]
0x18007fa78  lea     rcx, [rbp+210h+var_280]; void *
0x18007fa7c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007fa81  nop
0x18007fa82  mov     rcx, [rsp+310h+var_2E8]; pv
0x18007fa87  mov     [rsp+310h+var_2E8], rdi
0x18007fa8c  test    rcx, rcx
0x18007fa8f  jz      short loc_18007FA9D
0x18007fa91  call    cs:__imp_CoTaskMemFree
0x18007fa98  nop     dword ptr [rax+rax+00h]
0x18007fa9d  inc     r13d
0x18007faa0  cmp     r13d, ebx
0x18007faa3  jnb     short loc_18007FAAF
0x18007faa5  mov     rdx, [rsp+310h+var_2D0]
0x18007faaa  jmp     loc_18007F77A
0x18007faaf  mov     rcx, [rbp+210h+var_50]
0x18007fab6  xor     rcx, rsp; StackCookie
0x18007fab9  call    __security_check_cookie
0x18007fabe  lea     r11, [rsp+310h+var_30]
0x18007fac6  mov     rbx, [r11+40h]
0x18007faca  movaps  xmm6, xmmword ptr [r11-10h]
0x18007facf  mov     rsp, r11
0x18007fad2  pop     r15
0x18007fad4  pop     r14
0x18007fad6  pop     r13
0x18007fad8  pop     r12
0x18007fada  pop     rdi
0x18007fadb  pop     rsi
0x18007fadc  pop     rbp
0x18007fadd  retn
0x18007fadf  mov     r9d, eax; char *
0x18007fae2  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007fae9  mov     edx, 72h ; 'r'; void *
0x18007faee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007faf4  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007fafb  mov     edx, 85h; void *
0x18007fb00  mov     rcx, rdi; this
0x18007fb03  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007fb09  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007fb10  mov     edx, 82h; void *
0x18007fb15  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007fb1b  mov     ecx, edi
0x18007fb1d  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18007fb22  mov     r9d, eax; char *
0x18007fb25  mov     rcx, [rbp+218h]; this
0x18007fb2c  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007fb33  mov     edx, 8Ah; void *
0x18007fb38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007fb3e  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007fb45  mov     edx, 76h ; 'v'; void *
0x18007fb4a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

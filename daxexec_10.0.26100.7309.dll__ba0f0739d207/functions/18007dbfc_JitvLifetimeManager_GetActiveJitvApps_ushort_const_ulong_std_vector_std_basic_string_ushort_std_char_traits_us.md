# JitvLifetimeManager::GetActiveJitvApps(ushort const * *,ulong,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18007dbfc`
- end: `0x18007e02d`
- name: `?GetActiveJitvApps@JitvLifetimeManager@@AEAAXPEAPEBGKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1073`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007d540`

## callees

- `0x1800053a0`
- `0x18000c37c`
- `0x180010a84`
- `0x180011300`
- `0x180011820`
- `0x18002031c`
- `0x18003112c`
- `0x18005c0fc`
- `0x18007ac10`
- `0x18007dbfc`
- `0x1800ad1ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dd60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dd60`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007dd1c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007dd1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007dd9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007df27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007dd9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007df27`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007dd4c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007de4d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007dd4c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007de4d`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x18007de88`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x18007de88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007dcf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007df3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007df73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007dcf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007df3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007df73`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall JitvLifetimeManager::GetActiveJitvApps(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // ebx
  unsigned int v6; // r13d
  __int64 v7; // rdx
  __int64 v8; // r8
  _QWORD *v9; // rcx
  int ProcessesInVirtualizationContext; // eax
  void *v11; // rcx
  unsigned int v12; // r15d
  DWORD ProcessId; // eax
  const char *v14; // r9
  DWORD v15; // r12d
  _WORD *v16; // rbx
  HANDLE v17; // rdi
  unsigned __int16 **v18; // r8
  signed int LastError; // esi
  bool v20; // sf
  __int64 v21; // r8
  _OWORD *v22; // rdx
  HANDLE v23; // rax
  const char *v24; // r9
  void *v25; // rdi
  const char *v26; // r9
  __int64 v27; // r8
  _OWORD *v28; // rdx
  void *v29; // rcx
  unsigned int v30; // eax
  int v31; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v33; // [rsp+30h] [rbp-D0h]
  _WORD *v34; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C0h]
  HANDLE v36; // [rsp+48h] [rbp-B8h]
  __int128 v37; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v38; // [rsp+60h] [rbp-A0h]
  __int128 v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h]
  __int64 v41; // [rsp+88h] [rbp-78h]
  _QWORD v42[4]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR BaseName[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  if ( a3 )
  {
    v5 = a3;
    v33 = a3;
    v35 = a2;
    v6 = 0;
    while ( 1 )
    {
      v31 = 0;
      pv = 0;
      v7 = *(_QWORD *)(a2 + 8LL * v6);
      v39 = 0;
      v40 = 0;
      v41 = 0;
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(v7 + 2 * v8) );
      std::wstring::_Construct<1,unsigned short const *>(&v39, v7, v8);
      GetPackageFamilyNameFromFullName(v42, &v39);
      std::wstring::~wstring(&v39);
      *(_QWORD *)&v37 = &pv;
      *((_QWORD *)&v37 + 1) = 0;
      LOBYTE(v38) = 1;
      v9 = v42;
      if ( v42[3] > 7u )
        v9 = (_QWORD *)v42[0];
      ProcessesInVirtualizationContext = GetProcessesInVirtualizationContext(v9, &v31, (char *)&v37 + 8);
      if ( ProcessesInVirtualizationContext < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
          (const char *)(unsigned int)ProcessesInVirtualizationContext,
          v31);
      if ( (_BYTE)v38 )
      {
        v11 = *(void **)v37;
        *(_QWORD *)v37 = *((_QWORD *)&v37 + 1);
        if ( v11 )
          CoTaskMemFree(v11);
      }
      v12 = 0;
      if ( v31 )
      {
        do
        {
          ProcessId = GetProcessId(*((HANDLE *)pv + v12));
          v15 = ProcessId;
          if ( !ProcessId )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x76,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
              v14);
          v16 = 0;
          v34 = 0;
          v17 = OpenProcess(0x1000u, 0, ProcessId);
          if ( v17 )
            goto LABEL_17;
          LastError = GetLastError();
          v20 = LastError < 0;
          if ( LastError > 0 )
          {
            LastError = (unsigned __int16)LastError | 0x80070000;
            v20 = LastError < 0;
          }
          if ( !v20 )
          {
LABEL_17:
            LastError = CallerIdentity::GetProcessAppId(v17, &v34, v18);
            if ( v17 && v17 != (HANDLE)-1LL )
              CloseHandle(v17);
            v16 = v34;
          }
          if ( LastError < 0 )
          {
            if ( LastError != -2147023728 )
            {
              v30 = wil::verify_hresult((unsigned int)LastError);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x8A,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
                (const char *)v30,
                v31);
            }
            v23 = OpenProcess(0x410u, 0, v15);
            v25 = v23;
            v36 = v23;
            if ( v23 == (HANDLE)-1LL )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x82,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
                v24);
            if ( !K32GetModuleBaseNameW(v23, 0, BaseName, 0x104u) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x85,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
                v26);
            v37 = 0;
            v38 = 0u;
            v27 = -1;
            do
              ++v27;
            while ( BaseName[v27] );
            std::wstring::_Construct<1,unsigned short const *>(&v37, BaseName, v27);
            v28 = *(_OWORD **)(a4 + 8);
            if ( v28 == *(_OWORD **)(a4 + 16) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a4, v28, &v37);
            }
            else
            {
              *v28 = v37;
              v28[1] = v38;
              *(_QWORD *)&v38 = 0;
              *((_QWORD *)&v38 + 1) = 7;
              LOWORD(v37) = 0;
              *(_QWORD *)(a4 + 8) += 32LL;
            }
            std::wstring::~wstring(&v37);
            if ( v25 )
              CloseHandle(v25);
          }
          else
          {
            v37 = 0;
            v38 = 0u;
            v21 = -1;
            do
              ++v21;
            while ( v16[v21] );
            std::wstring::_Construct<1,unsigned short const *>(&v37, v16, v21);
            v22 = *(_OWORD **)(a4 + 8);
            if ( v22 == *(_OWORD **)(a4 + 16) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a4, v22, &v37);
            }
            else
            {
              *v22 = v37;
              v22[1] = v38;
              *(_QWORD *)&v38 = 0;
              *((_QWORD *)&v38 + 1) = 7;
              LOWORD(v37) = 0;
              *(_QWORD *)(a4 + 8) += 32LL;
            }
            std::wstring::~wstring(&v37);
          }
          if ( v16 )
            CoTaskMemFree(v16);
          ++v12;
        }
        while ( v12 < v31 );
        v5 = v33;
      }
      std::wstring::~wstring(v42);
      v29 = pv;
      pv = 0;
      if ( v29 )
        CoTaskMemFree(v29);
      if ( ++v6 >= v5 )
        break;
      a2 = v35;
    }
  }
}

```

## disassembly

```asm
0x18007dbfc  test    r8d, r8d
0x18007dbff  jz      locret_18007DFBA
0x18007dc05  mov     [rsp-8+arg_0], rbx
0x18007dc0a  push    rbp
0x18007dc0b  push    rsi
0x18007dc0c  push    rdi
0x18007dc0d  push    r12
0x18007dc0f  push    r13
0x18007dc11  push    r14
0x18007dc13  push    r15
0x18007dc15  lea     rbp, [rsp-1D0h]
0x18007dc1d  sub     rsp, 2D0h
0x18007dc24  mov     rax, cs:__security_cookie
0x18007dc2b  xor     rax, rsp
0x18007dc2e  mov     [rbp+200h+var_40], rax
0x18007dc35  mov     r14, r9
0x18007dc38  mov     ebx, r8d
0x18007dc3b  mov     [rsp+300h+var_2D0], ebx
0x18007dc3f  mov     [rsp+300h+var_2C0], rdx
0x18007dc44  xor     esi, esi
0x18007dc46  mov     r13d, esi
0x18007dc49  mov     [rsp+300h+var_2E0], esi; int
0x18007dc4d  mov     [rsp+300h+pv], rsi
0x18007dc52  mov     eax, r13d
0x18007dc55  mov     rdx, [rdx+rax*8]
0x18007dc59  xorps   xmm0, xmm0
0x18007dc5c  movups  [rsp+300h+var_290], xmm0
0x18007dc61  mov     [rbp+200h+var_280], rsi
0x18007dc65  mov     [rbp+200h+var_278], rsi
0x18007dc69  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007dc6d  inc     r8
0x18007dc70  cmp     [rdx+r8*2], si
0x18007dc75  jnz     short loc_18007DC6D
0x18007dc77  lea     rcx, [rsp+300h+var_290]
0x18007dc7c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007dc81  nop
0x18007dc82  lea     rdx, [rsp+300h+var_290]
0x18007dc87  lea     rcx, [rbp+200h+var_270]
0x18007dc8b  call    ?GetPackageFamilyNameFromFullName@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; GetPackageFamilyNameFromFullName(std::wstring const &)
0x18007dc90  nop
0x18007dc91  lea     rcx, [rsp+300h+var_290]; void *
0x18007dc96  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007dc9b  lea     rax, [rsp+300h+pv]
0x18007dca0  mov     qword ptr [rsp+300h+var_2B0], rax
0x18007dca5  mov     qword ptr [rsp+300h+var_2B0+8], rsi
0x18007dcaa  mov     byte ptr [rsp+300h+var_2A0], 1
0x18007dcaf  lea     rcx, [rbp+200h+var_270]
0x18007dcb3  cmp     [rbp+200h+var_258], 7
0x18007dcb8  cmova   rcx, [rbp+200h+var_270]
0x18007dcbd  lea     r8, [rsp+300h+var_2B0+8]
0x18007dcc2  lea     rdx, [rsp+300h+var_2E0]
0x18007dcc7  call    GetProcessesInVirtualizationContext
0x18007dccc  mov     rcx, [rbp+208h]; this
0x18007dcd3  test    eax, eax
0x18007dcd5  js      loc_18007DFBC
0x18007dcdb  cmp     byte ptr [rsp+300h+var_2A0], sil
0x18007dce0  jz      short loc_18007DD03
0x18007dce2  mov     rdx, qword ptr [rsp+300h+var_2B0]
0x18007dce7  mov     rcx, [rdx]; pv
0x18007dcea  mov     rax, qword ptr [rsp+300h+var_2B0+8]
0x18007dcef  mov     [rdx], rax
0x18007dcf2  test    rcx, rcx
0x18007dcf5  jz      short loc_18007DD03
0x18007dcf7  call    cs:__imp_CoTaskMemFree
0x18007dcfe  nop     dword ptr [rax+rax+00h]
0x18007dd03  mov     r15d, esi
0x18007dd06  cmp     [rsp+300h+var_2E0], esi
0x18007dd0a  jbe     loc_18007DF5A
0x18007dd10  mov     eax, r15d
0x18007dd13  mov     rcx, [rsp+300h+pv]
0x18007dd18  mov     rcx, [rcx+rax*8]; Process
0x18007dd1c  call    cs:__imp_GetProcessId
0x18007dd23  nop     dword ptr [rax+rax+00h]
0x18007dd28  mov     r12d, eax
0x18007dd2b  mov     rcx, [rbp+208h]; this
0x18007dd32  test    eax, eax
0x18007dd34  jz      loc_18007E01B
0x18007dd3a  mov     rbx, rsi
0x18007dd3d  mov     [rsp+300h+var_2C8], rbx
0x18007dd42  mov     r8d, eax; dwProcessId
0x18007dd45  xor     edx, edx; bInheritHandle
0x18007dd47  mov     ecx, 1000h; dwDesiredAccess
0x18007dd4c  call    cs:__imp_OpenProcess
0x18007dd53  nop     dword ptr [rax+rax+00h]
0x18007dd58  mov     rdi, rax
0x18007dd5b  test    rax, rax
0x18007dd5e  jnz     short loc_18007DD7F
0x18007dd60  call    cs:__imp_GetLastError
0x18007dd67  nop     dword ptr [rax+rax+00h]
0x18007dd6c  mov     esi, eax
0x18007dd6e  test    eax, eax
0x18007dd70  jle     short loc_18007DD7D
0x18007dd72  movzx   esi, si
0x18007dd75  or      esi, 80070000h
0x18007dd7b  test    esi, esi
0x18007dd7d  js      short loc_18007DDAD
0x18007dd7f  lea     rdx, [rsp+300h+var_2C8]; void *
0x18007dd84  mov     rcx, rdi; ProcessHandle
0x18007dd87  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x18007dd8c  mov     esi, eax
0x18007dd8e  test    rdi, rdi
0x18007dd91  jz      short loc_18007DDA8
0x18007dd93  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18007dd97  jz      short loc_18007DDA8
0x18007dd99  mov     rcx, rdi; hObject
0x18007dd9c  call    cs:__imp_CloseHandle
0x18007dda3  nop     dword ptr [rax+rax+00h]
0x18007dda8  mov     rbx, [rsp+300h+var_2C8]
0x18007ddad  test    esi, esi
0x18007ddaf  js      loc_18007DE37
0x18007ddb5  xorps   xmm0, xmm0
0x18007ddb8  movups  [rsp+300h+var_2B0], xmm0
0x18007ddbd  xor     esi, esi
0x18007ddbf  mov     qword ptr [rsp+300h+var_2A0], rsi
0x18007ddc4  mov     qword ptr [rsp+300h+var_2A0+8], rsi
0x18007ddc9  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007ddcd  inc     r8
0x18007ddd0  cmp     [rbx+r8*2], si
0x18007ddd5  jnz     short loc_18007DDCD
0x18007ddd7  mov     rdx, rbx
0x18007ddda  lea     rcx, [rsp+300h+var_2B0]
0x18007dddf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007dde4  nop
0x18007dde5  mov     rdx, [r14+8]
0x18007dde9  cmp     rdx, [r14+10h]
0x18007dded  jz      short loc_18007DE1A
0x18007ddef  movups  xmm0, [rsp+300h+var_2B0]
0x18007ddf4  movups  xmmword ptr [rdx], xmm0
0x18007ddf7  movups  xmm1, [rsp+300h+var_2A0]
0x18007ddfc  movups  xmmword ptr [rdx+10h], xmm1
0x18007de00  mov     qword ptr [rsp+300h+var_2A0], rsi
0x18007de05  mov     qword ptr [rsp+300h+var_2A0+8], 7
0x18007de0e  mov     word ptr [rsp+300h+var_2B0], si
0x18007de13  add     qword ptr [r14+8], 20h ; ' '
0x18007de18  jmp     short loc_18007DE28
0x18007de1a  lea     r8, [rsp+300h+var_2B0]
0x18007de1f  mov     rcx, r14
0x18007de22  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18007de27  nop
0x18007de28  lea     rcx, [rsp+300h+var_2B0]; void *
0x18007de2d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007de32  jmp     loc_18007DF34
0x18007de37  cmp     esi, 80070490h
0x18007de3d  jnz     loc_18007DFF8
0x18007de43  mov     r8d, r12d; dwProcessId
0x18007de46  xor     edx, edx; bInheritHandle
0x18007de48  mov     ecx, 410h; dwDesiredAccess
0x18007de4d  call    cs:__imp_OpenProcess
0x18007de54  nop     dword ptr [rax+rax+00h]
0x18007de59  mov     rdi, rax
0x18007de5c  mov     [rsp+300h+var_2B8], rax
0x18007de61  mov     rcx, [rbp+208h]; this
0x18007de68  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007de6c  jz      loc_18007DFE6
0x18007de72  mov     rsi, [rbp+208h]
0x18007de79  mov     r9d, 104h; nSize
0x18007de7f  lea     r8, [rbp+200h+BaseName]; lpBaseName
0x18007de83  xor     edx, edx; hModule
0x18007de85  mov     rcx, rax; hProcess
0x18007de88  call    cs:__imp_K32GetModuleBaseNameW
0x18007de8f  nop     dword ptr [rax+rax+00h]
0x18007de94  test    eax, eax
0x18007de96  jz      loc_18007DFD1
0x18007de9c  xorps   xmm0, xmm0
0x18007de9f  movups  [rsp+300h+var_2B0], xmm0
0x18007dea4  xor     esi, esi
0x18007dea6  mov     qword ptr [rsp+300h+var_2A0], rsi
0x18007deab  mov     qword ptr [rsp+300h+var_2A0+8], rsi
0x18007deb0  lea     rax, [rbp+200h+BaseName]
0x18007deb4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007deb8  inc     r8
0x18007debb  cmp     [rax+r8*2], si
0x18007dec0  jnz     short loc_18007DEB8
0x18007dec2  lea     rdx, [rbp+200h+BaseName]
0x18007dec6  lea     rcx, [rsp+300h+var_2B0]
0x18007decb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007ded0  nop
0x18007ded1  mov     rdx, [r14+8]
0x18007ded5  cmp     rdx, [r14+10h]
0x18007ded9  jz      short loc_18007DF06
0x18007dedb  movups  xmm0, [rsp+300h+var_2B0]
0x18007dee0  movups  xmmword ptr [rdx], xmm0
0x18007dee3  movups  xmm1, [rsp+300h+var_2A0]
0x18007dee8  movups  xmmword ptr [rdx+10h], xmm1
0x18007deec  mov     qword ptr [rsp+300h+var_2A0], rsi
0x18007def1  mov     qword ptr [rsp+300h+var_2A0+8], 7
0x18007defa  mov     word ptr [rsp+300h+var_2B0], si
0x18007deff  add     qword ptr [r14+8], 20h ; ' '
0x18007df04  jmp     short loc_18007DF14
0x18007df06  lea     r8, [rsp+300h+var_2B0]
0x18007df0b  mov     rcx, r14
0x18007df0e  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18007df13  nop
0x18007df14  lea     rcx, [rsp+300h+var_2B0]; void *
0x18007df19  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007df1e  nop
0x18007df1f  test    rdi, rdi
0x18007df22  jz      short loc_18007DF34
0x18007df24  mov     rcx, rdi; hObject
0x18007df27  call    cs:__imp_CloseHandle
0x18007df2e  nop     dword ptr [rax+rax+00h]
0x18007df33  nop
0x18007df34  test    rbx, rbx
0x18007df37  jz      short loc_18007DF48
0x18007df39  mov     rcx, rbx; pv
0x18007df3c  call    cs:__imp_CoTaskMemFree
0x18007df43  nop     dword ptr [rax+rax+00h]
0x18007df48  inc     r15d
0x18007df4b  cmp     r15d, [rsp+300h+var_2E0]
0x18007df50  jb      loc_18007DD10
0x18007df56  mov     ebx, [rsp+300h+var_2D0]
0x18007df5a  lea     rcx, [rbp+200h+var_270]; void *
0x18007df5e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007df63  nop
0x18007df64  mov     rcx, [rsp+300h+pv]; pv
0x18007df69  mov     [rsp+300h+pv], rsi
0x18007df6e  test    rcx, rcx
0x18007df71  jz      short loc_18007DF7F
0x18007df73  call    cs:__imp_CoTaskMemFree
0x18007df7a  nop     dword ptr [rax+rax+00h]
0x18007df7f  inc     r13d
0x18007df82  cmp     r13d, ebx
0x18007df85  jnb     short loc_18007DF91
0x18007df87  mov     rdx, [rsp+300h+var_2C0]
0x18007df8c  jmp     loc_18007DC49
0x18007df91  mov     rcx, [rbp+200h+var_40]
0x18007df98  xor     rcx, rsp; StackCookie
0x18007df9b  call    __security_check_cookie
0x18007dfa0  mov     rbx, [rsp+300h+arg_0]
0x18007dfa8  add     rsp, 2D0h
0x18007dfaf  pop     r15
0x18007dfb1  pop     r14
0x18007dfb3  pop     r13
0x18007dfb5  pop     r12
0x18007dfb7  pop     rdi
0x18007dfb8  pop     rsi
0x18007dfb9  pop     rbp
0x18007dfba  retn
0x18007dfbc  mov     r9d, eax; char *
0x18007dfbf  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007dfc6  mov     edx, 72h ; 'r'; void *
0x18007dfcb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007dfd1  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007dfd8  mov     edx, 85h; void *
0x18007dfdd  mov     rcx, rsi; this
0x18007dfe0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007dfe6  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007dfed  mov     edx, 82h; void *
0x18007dff2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007dff8  mov     ecx, esi
0x18007dffa  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18007dfff  mov     r9d, eax; char *
0x18007e002  mov     rcx, [rbp+208h]; this
0x18007e009  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007e010  mov     edx, 8Ah; void *
0x18007e015  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e01b  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007e022  mov     edx, 76h ; 'v'; void *
0x18007e027  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

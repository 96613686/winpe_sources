# GetCurrentUserSID(CAPITempBufferRef<uchar> &)

- ea: `0x18001386c`
- end: `0x180013b76`
- name: `?GetCurrentUserSID@@YAKAEAV?$CAPITempBufferRef@E@@@Z`
- size: `778`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180011280`
- `0x180013b7c`
- `0x1800811d8`
- `0x18014b5dc`
- `0x1801629b4`
- `0x18020f4c4`

## callees

- `0x18000c4bc`
- `0x18001386c`
- `0x180013fe4`
- `0x1800bfc6c`
- `0x18014b72c`
- `0x18015383c`
- `0x180265240`

## import_xrefs

- `ADVAPI32!CopySid` at `0x180013a2e`
- `ADVAPI32!CopySid` at `0x180013a2e`
- `ADVAPI32!GetTokenInformation` at `0x180013a0e`
- `ADVAPI32!GetTokenInformation` at `0x180013a0e`
- `ADVAPI32!OpenThreadToken` at `0x180013991`
- `ADVAPI32!OpenThreadToken` at `0x180013991`
- `ADVAPI32!OpenProcessToken` at `0x1800139ce`
- `ADVAPI32!OpenProcessToken` at `0x1800139ce`
- `KERNEL32!CloseHandle` at `0x180013a4d`
- `KERNEL32!CloseHandle` at `0x180013a4d`
- `KERNEL32!LeaveCriticalSection` at `0x18001391a`
- `KERNEL32!LeaveCriticalSection` at `0x18001391a`
- `KERNEL32!GetLastError` at `0x1800139a1`
- `KERNEL32!GetLastError` at `0x180013aa5`
- `KERNEL32!GetLastError` at `0x180013b01`
- `KERNEL32!GetLastError` at `0x180013b63`
- `KERNEL32!GetLastError` at `0x1800139a1`
- `KERNEL32!GetLastError` at `0x180013aa5`
- `KERNEL32!GetLastError` at `0x180013b01`
- `KERNEL32!GetLastError` at `0x180013b63`
- `KERNEL32!EnterCriticalSection` at `0x1800138ea`
- `KERNEL32!EnterCriticalSection` at `0x1800138ea`
- `KERNEL32!GlobalAlloc` at `0x180013ac6`
- `KERNEL32!GlobalAlloc` at `0x180013ac6`
- `KERNEL32!GetCurrentThread` at `0x180013977`
- `KERNEL32!GetCurrentThread` at `0x180013977`
- `KERNEL32!GetCurrentProcess` at `0x1800139b8`
- `KERNEL32!GetCurrentProcess` at `0x1800139b8`
- `KERNEL32!GlobalFree` at `0x180013add`
- `KERNEL32!GlobalFree` at `0x180013add`
- `KERNEL32!TlsGetValue` at `0x180013901`
- `KERNEL32!TlsGetValue` at `0x180013901`

## string_xrefs

- `0x180013b2a`: `GetTokenInformation failed with error %d`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSID(__int64 a1)
{
  __int64 v1; // rbx
  HGLOBAL v3; // rsi
  int v4; // eax
  bool v5; // dl
  int v6; // ecx
  unsigned int v7; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  bool v9; // si
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  HGLOBAL v13; // rbx
  bool *v15; // rdx
  DWORD v16; // eax
  void *TokenHandle; // [rsp+60h] [rbp-49h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp-41h] BYREF
  PSID TokenInformation[12]; // [rsp+70h] [rbp-39h] BYREF

  v1 = a1 + 16;
  if ( *(int *)(a1 + 12) < 72 )
    v3 = GlobalAlloc(0, 0x48u);
  else
    v3 = (HGLOBAL)(a1 + 16);
  if ( v3 )
  {
    if ( *(_QWORD *)a1 != v1 )
      GlobalFree(*(HGLOBAL *)a1);
    *(_QWORD *)a1 = v3;
    *(_DWORD *)(a1 + 8) = 72;
    TokenHandle = 0;
    v4 = RunningAsLocalSystem();
    if ( v4 == -1 )
      return 5;
    v6 = g_scServerContext;
    v7 = 0;
    if ( g_scServerContext == 2 || v4 == 1 )
    {
      EnterCriticalSection(&g_csImpersonationLock);
      if ( g_dwImpersonationSlot != -1 )
        v7 = (unsigned int)TlsGetValue(g_dwImpersonationSlot) >> 29;
      LeaveCriticalSection(&g_csImpersonationLock);
      v6 = g_scServerContext;
    }
    if ( v6 == 2 && v7 == 1 )
    {
      CCoImpersonate::CCoImpersonate((CCoImpersonate *)&ReturnLength, v5);
      LastError = OpenUserToken(&TokenHandle, v15);
      CCoImpersonate::~CCoImpersonate((CCoImpersonate *)&ReturnLength);
      v9 = LastError == 0;
LABEL_16:
      if ( !LastError )
      {
LABEL_26:
        v13 = *(HGLOBAL *)a1;
        ReturnLength = 0;
        if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
        {
          if ( CopySid(0x48u, v13, TokenInformation[0]) )
            LastError = 0;
          else
            LastError = GetLastError();
        }
        else
        {
          v16 = GetLastError();
          LastError = v16;
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"GetTokenInformation failed with error %d",
              (const unsigned __int16 *)v16,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
        }
        if ( v9 )
          CloseHandle(TokenHandle);
      }
      return LastError;
    }
    lpVtbl = (struct IUnknownVtbl *)Token;
    v9 = 0;
    if ( !Token && v6 == 2 )
    {
      if ( !CMsiTransaction::m_pMsiTransaction )
      {
        TokenHandle = 0;
        goto LABEL_20;
      }
      lpVtbl = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
    }
    LastError = 0;
    TokenHandle = lpVtbl;
    if ( lpVtbl )
      goto LABEL_16;
LABEL_20:
    LastError = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError == 1008 )
      {
        LastError = 0;
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
          LastError = GetLastError();
      }
    }
    if ( LastError )
      return LastError;
    v9 = 1;
    goto LABEL_26;
  }
  return 14;
}

```

## disassembly

```asm
0x18001386c  push    rbp
0x18001386e  push    rbx
0x18001386f  push    rsi
0x180013870  push    rdi
0x180013871  lea     rbp, [rsp-3Fh]
0x180013876  sub     rsp, 0E8h
0x18001387d  mov     rax, cs:__security_cookie
0x180013884  xor     rax, rsp
0x180013887  mov     [rbp+57h+var_30], rax
0x18001388b  cmp     dword ptr [rcx+0Ch], 48h ; 'H'
0x18001388f  lea     rbx, [rcx+10h]
0x180013893  mov     rdi, rcx
0x180013896  jl      loc_180013ABF
0x18001389c  mov     rsi, rbx
0x18001389f  test    rsi, rsi
0x1800138a2  jz      loc_180013AB8
0x1800138a8  cmp     [rdi], rbx
0x1800138ab  jnz     loc_180013ADA
0x1800138b1  mov     [rdi], rsi
0x1800138b4  mov     dword ptr [rdi+8], 48h ; 'H'
0x1800138bb  mov     [rbp+57h+TokenHandle], 0
0x1800138c3  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x1800138c8  cmp     eax, 0FFFFFFFFh
0x1800138cb  jz      loc_180013AEE
0x1800138d1  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x1800138d7  xor     ebx, ebx
0x1800138d9  cmp     ecx, 2
0x1800138dc  jz      short loc_1800138E3
0x1800138de  cmp     eax, 1
0x1800138e1  jnz     short loc_18001392C
0x1800138e3  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800138ea  call    cs:__imp_EnterCriticalSection
0x1800138f1  nop     dword ptr [rax+rax+00h]
0x1800138f6  mov     ecx, cs:?g_dwImpersonationSlot@@3KA; dwTlsIndex
0x1800138fc  cmp     ecx, 0FFFFFFFFh
0x1800138ff  jz      short loc_180013913
0x180013901  call    cs:__imp_TlsGetValue
0x180013908  nop     dword ptr [rax+rax+00h]
0x18001390d  mov     rbx, rax
0x180013910  shr     ebx, 1Dh
0x180013913  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001391a  call    cs:__imp_LeaveCriticalSection
0x180013921  nop     dword ptr [rax+rax+00h]
0x180013926  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x18001392c  cmp     ecx, 2
0x18001392f  jz      loc_180013A74
0x180013935  mov     rax, cs:Token
0x18001393c  xor     sil, sil
0x18001393f  test    rax, rax
0x180013942  jnz     short loc_180013949
0x180013944  cmp     ecx, 2
0x180013947  jz      short loc_180013961
0x180013949  xor     ebx, ebx
0x18001394b  mov     [rbp+57h+TokenHandle], rax
0x18001394f  test    rax, rax
0x180013952  jz      short loc_180013975
0x180013954  test    ebx, ebx
0x180013956  jnz     loc_180013A59
0x18001395c  jmp     loc_1800139E9
0x180013961  mov     rax, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x180013968  test    rax, rax
0x18001396b  jnz     loc_180013AF8
0x180013971  mov     [rbp+57h+TokenHandle], rax
0x180013975  xor     ebx, ebx
0x180013977  call    cs:__imp_GetCurrentThread
0x18001397e  nop     dword ptr [rax+rax+00h]
0x180013983  mov     rcx, rax; ThreadHandle
0x180013986  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001398a  lea     edx, [rbx+0Ch]; DesiredAccess
0x18001398d  lea     r8d, [rbx+1]; OpenAsSelf
0x180013991  call    cs:__imp_OpenThreadToken
0x180013998  nop     dword ptr [rax+rax+00h]
0x18001399d  test    eax, eax
0x18001399f  jnz     short loc_1800139E2
0x1800139a1  call    cs:__imp_GetLastError
0x1800139a8  nop     dword ptr [rax+rax+00h]
0x1800139ad  mov     ebx, eax
0x1800139af  cmp     eax, 3F0h
0x1800139b4  jnz     short loc_1800139E2
0x1800139b6  xor     ebx, ebx
0x1800139b8  call    cs:__imp_GetCurrentProcess
0x1800139bf  nop     dword ptr [rax+rax+00h]
0x1800139c4  mov     rcx, rax; ProcessHandle
0x1800139c7  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800139cb  lea     edx, [rbx+0Ch]; DesiredAccess
0x1800139ce  call    cs:__imp_OpenProcessToken
0x1800139d5  nop     dword ptr [rax+rax+00h]
0x1800139da  test    eax, eax
0x1800139dc  jz      loc_180013AA5
0x1800139e2  test    ebx, ebx
0x1800139e4  jnz     short loc_180013A59
0x1800139e6  mov     sil, 1
0x1800139e9  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800139ed  lea     rax, [rbp+57h+var_98]
0x1800139f1  mov     rbx, [rdi]
0x1800139f4  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800139f8  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800139fe  mov     [rbp+57h+var_98], 0
0x180013a05  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180013a0a  lea     edx, [r9-57h]; TokenInformationClass
0x180013a0e  call    cs:__imp_GetTokenInformation
0x180013a15  nop     dword ptr [rax+rax+00h]
0x180013a1a  test    eax, eax
0x180013a1c  jz      loc_180013B01
0x180013a22  mov     r8, [rbp+57h+TokenInformation]; pSourceSid
0x180013a26  mov     rdx, rbx; pDestinationSid
0x180013a29  mov     ecx, 48h ; 'H'; nDestinationSidLength
0x180013a2e  call    cs:__imp_CopySid
0x180013a35  nop     dword ptr [rax+rax+00h]
0x180013a3a  test    eax, eax
0x180013a3c  jz      loc_180013B63
0x180013a42  xor     ebx, ebx
0x180013a44  test    sil, sil
0x180013a47  jz      short loc_180013A59
0x180013a49  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180013a4d  call    cs:__imp_CloseHandle
0x180013a54  nop     dword ptr [rax+rax+00h]
0x180013a59  mov     eax, ebx
0x180013a5b  mov     rcx, [rbp+57h+var_30]
0x180013a5f  xor     rcx, rsp; StackCookie
0x180013a62  call    __security_check_cookie
0x180013a67  add     rsp, 0E8h
0x180013a6e  pop     rdi
0x180013a6f  pop     rsi
0x180013a70  pop     rbx
0x180013a71  pop     rbp
0x180013a72  retn
0x180013a74  cmp     ebx, 1
0x180013a77  jnz     loc_180013935
0x180013a7d  lea     rcx, [rbp+57h+var_98]; this
0x180013a81  call    ??0CCoImpersonate@@QEAA@_N@Z; CCoImpersonate::CCoImpersonate(bool)
0x180013a86  lea     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180013a8a  call    ?OpenUserToken@@YAKAEAPEAXPEA_N@Z; OpenUserToken(void * &,bool *)
0x180013a8f  lea     rcx, [rbp+57h+var_98]; this
0x180013a93  mov     ebx, eax
0x180013a95  call    ??1CCoImpersonate@@QEAA@XZ; CCoImpersonate::~CCoImpersonate(void)
0x180013a9a  test    ebx, ebx
0x180013a9c  setz    sil
0x180013aa0  jmp     loc_180013954
0x180013aa5  call    cs:__imp_GetLastError
0x180013aac  nop     dword ptr [rax+rax+00h]
0x180013ab1  mov     ebx, eax
0x180013ab3  jmp     loc_1800139E2
0x180013ab8  mov     eax, 0Eh
0x180013abd  jmp     short loc_180013A5B
0x180013abf  mov     edx, 48h ; 'H'; dwBytes
0x180013ac4  xor     ecx, ecx; uFlags
0x180013ac6  call    cs:__imp_GlobalAlloc
0x180013acd  nop     dword ptr [rax+rax+00h]
0x180013ad2  mov     rsi, rax
0x180013ad5  jmp     loc_18001389F
0x180013ada  mov     rcx, [rdi]; hMem
0x180013add  call    cs:__imp_GlobalFree
0x180013ae4  nop     dword ptr [rax+rax+00h]
0x180013ae9  jmp     loc_1800138B1
0x180013aee  mov     ebx, 5
0x180013af3  jmp     loc_180013A59
0x180013af8  mov     rax, [rax+28h]
0x180013afc  jmp     loc_180013949
0x180013b01  call    cs:__imp_GetLastError
0x180013b08  nop     dword ptr [rax+rax+00h]
0x180013b0d  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180013b14  mov     ebx, eax
0x180013b16  jz      loc_180013A44
0x180013b1c  lea     rcx, aNull; "(NULL)"
0x180013b23  xor     edx, edx; unsigned __int16
0x180013b25  mov     [rsp+100h+var_A8], rdx; void *
0x180013b2a  lea     r9, aGettokeninform; "GetTokenInformation failed with error %"...
0x180013b31  mov     [rsp+100h+var_B0], edx; unsigned int
0x180013b35  xor     r8d, r8d; int
0x180013b38  mov     [rsp+100h+var_B8], rcx; unsigned __int16 *
0x180013b3d  mov     [rsp+100h+var_C0], rcx; unsigned __int16 *
0x180013b42  mov     [rsp+100h+var_C8], rcx; unsigned __int16 *
0x180013b47  mov     [rsp+100h+var_D0], rcx; unsigned __int16 *
0x180013b4c  mov     [rsp+100h+var_D8], rcx; unsigned __int16 *
0x180013b51  lea     ecx, [rdx+9]; int
0x180013b54  mov     [rsp+100h+ReturnLength], rbx; unsigned __int16 *
0x180013b59  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180013b5e  jmp     loc_180013A44
0x180013b63  call    cs:__imp_GetLastError
0x180013b6a  nop     dword ptr [rax+rax+00h]
0x180013b6f  mov     ebx, eax
0x180013b71  jmp     loc_180013A44
```

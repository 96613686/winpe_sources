# CImpersonate::CImpersonate(bool)

- ea: `0x180064b4c`
- end: `0x180064f0f`
- name: `??0CImpersonate@@QEAA@_N@Z`
- size: `963`
- prototype: `CImpersonate *__fastcall(CImpersonate *this, char)`
- caller_count: `88`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001a2f8`
- `0x180056860`
- `0x1800569a0`
- `0x180056d60`
- `0x1800574e0`
- `0x1800575b0`
- `0x180057b50`
- `0x180057c20`
- `0x180058780`
- `0x180059360`
- `0x180064150`
- `0x180064a78`
- `0x1800659c0`
- `0x180066250`
- `0x1800683e0`
- `0x18006b1f0`
- `0x18008a3b8`
- `0x1800a86cc`
- `0x1800e798c`
- `0x1800f10b0`
- `0x1800f33ec`
- `0x18010c720`
- `0x18010c7b0`
- `0x18010dbe0`
- `0x18010ea00`
- `0x1801123bc`
- `0x180114f70`
- `0x180115bb0`
- `0x1801162b0`
- `0x180116380`
- `0x180118b10`
- `0x18011c3b0`
- `0x180129720`
- `0x18012c3e0`
- `0x1801344cc`
- `0x180134ac0`
- `0x180137b34`
- `0x1801389f0`
- `0x18013ae34`
- `0x180145390`
- `0x180145520`
- `0x1801559e0`
- `0x1801592e0`
- `0x180159610`
- `0x18015bc20`
- `0x18015c3f0`
- `0x18015cad0`
- `0x18015cd14`
- `0x18015d500`
- `0x18015e2d0`

## callees

- `0x180025a18`
- `0x180064b4c`
- `0x1800a9d48`
- `0x180157094`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180064c8c`
- `ADVAPI32!SetThreadToken` at `0x180064de9`
- `ADVAPI32!SetThreadToken` at `0x180064e92`
- `ADVAPI32!SetThreadToken` at `0x180064c8c`
- `ADVAPI32!SetThreadToken` at `0x180064de9`
- `ADVAPI32!SetThreadToken` at `0x180064e92`
- `ADVAPI32!OpenThreadToken` at `0x180064cdf`
- `ADVAPI32!OpenThreadToken` at `0x180064cdf`
- `ADVAPI32!OpenProcessToken` at `0x180064d17`
- `ADVAPI32!OpenProcessToken` at `0x180064d17`
- `KERNEL32!CloseHandle` at `0x180064dd6`
- `KERNEL32!CloseHandle` at `0x180064e00`
- `KERNEL32!CloseHandle` at `0x180064dd6`
- `KERNEL32!CloseHandle` at `0x180064e00`
- `KERNEL32!LeaveCriticalSection` at `0x180064bd6`
- `KERNEL32!LeaveCriticalSection` at `0x180064d66`
- `KERNEL32!LeaveCriticalSection` at `0x180064bd6`
- `KERNEL32!LeaveCriticalSection` at `0x180064d66`
- `KERNEL32!EnterCriticalSection` at `0x180064bbc`
- `KERNEL32!EnterCriticalSection` at `0x180064bbc`
- `KERNEL32!GetCurrentThread` at `0x180064cc5`
- `KERNEL32!GetCurrentThread` at `0x180064cc5`
- `KERNEL32!GetCurrentProcess` at `0x180064d01`
- `KERNEL32!GetCurrentProcess` at `0x180064d01`
- `KERNEL32!TlsSetValue` at `0x180064c46`
- `KERNEL32!TlsSetValue` at `0x180064da0`
- `KERNEL32!TlsSetValue` at `0x180064e49`
- `KERNEL32!TlsSetValue` at `0x180064c46`
- `KERNEL32!TlsSetValue` at `0x180064da0`
- `KERNEL32!TlsSetValue` at `0x180064e49`
- `KERNEL32!TlsGetValue` at `0x180064bde`
- `KERNEL32!TlsGetValue` at `0x180064bde`
- `KERNEL32!TlsAlloc` at `0x180064d4d`
- `KERNEL32!TlsAlloc` at `0x180064d4d`
- `KERNEL32!ExitProcess` at `0x180064d80`
- `KERNEL32!ExitProcess` at `0x180064d80`

## pseudocode

```c
CImpersonate *__fastcall CImpersonate::CImpersonate(CImpersonate *this, char a2)
{
  int v3; // ecx
  int v5; // eax
  int v6; // ebx
  DWORD v7; // esi
  unsigned int Value; // eax
  unsigned int v9; // r14d
  unsigned int v10; // ecx
  int v11; // ebp
  unsigned int v12; // r8d
  unsigned int v13; // ecx
  int v14; // ebx
  int v15; // ebx
  struct IUnknownVtbl *lpVtbl; // rdx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v20; // ebx
  unsigned int v21; // eax
  int v22; // ecx
  void *TokenHandle; // [rsp+90h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp+18h] BYREF

  *(_DWORD *)this = 0;
  *((_BYTE *)this + 4) = 0;
  v3 = dword_180306D40;
  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &hObject) )
    {
      v20 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v20;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v3 = dword_180306D40;
  }
  v5 = g_scServerContext;
  if ( g_scServerContext != 2 && !v3 )
  {
    *((_BYTE *)this + 4) = 0;
    return this;
  }
  *((_BYTE *)this + 4) = a2;
  if ( a2 )
  {
    *((_BYTE *)this + 4) = 0;
    v6 = 3 - (v5 != 3);
    EnterCriticalSection(&g_csImpersonationLock);
    v7 = g_dwImpersonationSlot;
    if ( g_dwImpersonationSlot == -1 )
    {
      g_dwImpersonationSlot = TlsAlloc();
      v7 = g_dwImpersonationSlot;
      if ( g_dwImpersonationSlot == -1 )
      {
        LeaveCriticalSection(&g_csImpersonationLock);
        if ( (unsigned int)(g_scServerContext - 2) <= 1 )
          ExitProcess(0xFFFFFFFF);
        return this;
      }
    }
    LeaveCriticalSection(&g_csImpersonationLock);
    Value = (unsigned int)TlsGetValue(v7);
    v9 = Value;
    v10 = Value >> 29;
    if ( Value >> 29 == 4 )
      return this;
    v11 = Value & 0x1FFFFFFF;
    if ( g_scServerContext == 3 && v6 == 2 )
      v6 = 3;
    v12 = Value;
    if ( v10 )
    {
      v13 = v10 - 1;
      if ( v13 )
      {
        if ( v13 == 2 )
          v6 = 3;
      }
      else
      {
        v6 = 1;
      }
    }
    else
    {
      v12 = v6 << 29;
      v11 = 0;
    }
    if ( !TlsSetValue(v7, (LPVOID)(v12 & 0xE0000000 | (unsigned __int64)((v11 + 1) & 0x1FFFFFFF))) )
    {
LABEL_35:
      ExitProcessIfNotClient();
      return this;
    }
    v14 = v6 - 1;
    if ( !v14 )
    {
      if ( !(unsigned int)OLE32::CoImpersonateClient() )
        goto LABEL_19;
      goto LABEL_34;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      lpVtbl = (struct IUnknownVtbl *)Token;
      if ( Token )
        goto LABEL_18;
      if ( g_scServerContext == 2 )
      {
        if ( !CMsiTransaction::m_pMsiTransaction )
          goto LABEL_34;
        lpVtbl = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
      }
      if ( lpVtbl )
        goto LABEL_18;
      if ( g_scServerContext != 2 )
        goto LABEL_20;
LABEL_34:
      TlsSetValue(v7, (LPVOID)v9);
      goto LABEL_35;
    }
    if ( v15 != 1 )
      goto LABEL_34;
    lpVtbl = (struct IUnknownVtbl *)*((_QWORD *)g_pCustomActionContext + 15);
    if ( (unsigned __int64)&lpVtbl[-1].Release + 7 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
LABEL_18:
      if ( SetThreadToken(0, lpVtbl) )
      {
LABEL_19:
        *((_BYTE *)this + 4) = 1;
LABEL_20:
        *(_DWORD *)this = v11;
        return this;
      }
      goto LABEL_34;
    }
    v21 = *((_DWORD *)g_pCustomActionContext + 25);
    if ( g_fWoW )
    {
      if ( v21 > 9 )
        goto LABEL_50;
      v22 = 642;
    }
    else
    {
      if ( v21 > 8 )
        goto LABEL_50;
      v22 = 321;
    }
    if ( _bittest(&v22, v21) )
    {
LABEL_47:
      TlsSetValue(v7, (LPVOID)v9);
      return this;
    }
LABEL_50:
    ExitProcessIfNotClient();
    goto LABEL_47;
  }
  return this;
}

```

## disassembly

```asm
0x180064b4c  mov     [rsp+arg_8], rbx
0x180064b51  push    rbp
0x180064b52  push    rsi
0x180064b53  push    rdi
0x180064b54  push    r12
0x180064b56  push    r14
0x180064b58  sub     rsp, 60h
0x180064b5c  mov     rdi, rcx
0x180064b5f  mov     dword ptr [rcx], 0
0x180064b65  mov     byte ptr [rcx+4], 0
0x180064b69  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180064b6d  mov     ecx, cs:dword_180306D40
0x180064b73  mov     sil, dl
0x180064b76  cmp     ecx, ebp
0x180064b78  jz      loc_180064CBD
0x180064b7e  mov     eax, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x180064b84  cmp     eax, 2
0x180064b87  jz      short loc_180064B91
0x180064b89  test    ecx, ecx
0x180064b8b  jz      loc_180064CA2
0x180064b91  mov     [rdi+4], sil
0x180064b95  test    sil, sil
0x180064b98  jz      loc_180064CA6
0x180064b9e  mov     r12d, 3
0x180064ba4  mov     byte ptr [rdi+4], 0
0x180064ba8  sub     eax, r12d
0x180064bab  lea     r14, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csImpersonationLock
0x180064bb2  neg     eax
0x180064bb4  mov     rcx, r14; lpCriticalSection
0x180064bb7  sbb     ebx, ebx
0x180064bb9  add     ebx, r12d
0x180064bbc  call    cs:__imp_EnterCriticalSection
0x180064bc2  mov     esi, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x180064bc8  or      ebp, 0FFFFFFFFh
0x180064bcb  cmp     esi, ebp
0x180064bcd  jz      loc_180064D4D
0x180064bd3  mov     rcx, r14; lpCriticalSection
0x180064bd6  call    cs:__imp_LeaveCriticalSection
0x180064bdc  mov     ecx, esi; dwTlsIndex
0x180064bde  call    cs:__imp_TlsGetValue
0x180064be4  mov     ecx, eax
0x180064be6  mov     r14, rax
0x180064be9  shr     ecx, 1Dh
0x180064bec  cmp     ecx, 4
0x180064bef  jz      loc_180064CA6
0x180064bf5  mov     ebp, r14d
0x180064bf8  mov     r9d, 1FFFFFFFh
0x180064bfe  and     ebp, r9d
0x180064c01  cmp     cs:?g_scServerContext@@3W4scEnum@@A, r12d; scEnum g_scServerContext
0x180064c08  jz      loc_180064EF1
0x180064c0e  mov     r8d, r14d
0x180064c11  test    ecx, ecx
0x180064c13  jz      loc_180064DB0
0x180064c19  sub     ecx, 1
0x180064c1c  jz      loc_180064F05
0x180064c22  sub     ecx, 1
0x180064c25  jz      short loc_180064C30
0x180064c27  cmp     ecx, 1
0x180064c2a  jz      loc_180064EFD
0x180064c30  mov     ecx, 0E0000000h
0x180064c35  lea     edx, [rbp+1]
0x180064c38  mov     eax, r8d
0x180064c3b  and     rdx, r9
0x180064c3e  and     rax, rcx
0x180064c41  mov     ecx, esi; dwTlsIndex
0x180064c43  or      rdx, rax; lpTlsValue
0x180064c46  call    cs:__imp_TlsSetValue
0x180064c4c  test    eax, eax
0x180064c4e  jz      loc_180064DA6
0x180064c54  sub     ebx, 1
0x180064c57  jz      loc_180064D87
0x180064c5d  sub     ebx, 1
0x180064c60  jnz     loc_180064E0B
0x180064c66  mov     rdx, cs:Token; Token
0x180064c6d  mov     eax, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x180064c73  test    rdx, rdx
0x180064c76  jnz     short loc_180064C8A
0x180064c78  cmp     eax, 2
0x180064c7b  jz      loc_180064E69
0x180064c81  test    rdx, rdx
0x180064c84  jz      loc_180064E54
0x180064c8a  xor     ecx, ecx; Thread
0x180064c8c  call    cs:__imp_SetThreadToken
0x180064c92  test    eax, eax
0x180064c94  jz      loc_180064D9B
0x180064c9a  mov     byte ptr [rdi+4], 1
0x180064c9e  mov     [rdi], ebp
0x180064ca0  jmp     short loc_180064CA6
0x180064ca2  mov     byte ptr [rdi+4], 0
0x180064ca6  mov     rbx, [rsp+88h+arg_8]
0x180064cae  mov     rax, rdi
0x180064cb1  add     rsp, 60h
0x180064cb5  pop     r14
0x180064cb7  pop     r12
0x180064cb9  pop     rdi
0x180064cba  pop     rsi
0x180064cbb  pop     rbp
0x180064cbc  retn
0x180064cbd  mov     [rsp+88h+TokenHandle], rbp
0x180064cc5  call    cs:__imp_GetCurrentThread
0x180064ccb  mov     edx, 4; DesiredAccess
0x180064cd0  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180064cd8  mov     rcx, rax; ThreadHandle
0x180064cdb  lea     r8d, [rdx-3]; OpenAsSelf
0x180064cdf  call    cs:__imp_OpenThreadToken
0x180064ce5  test    eax, eax
0x180064ce7  jnz     loc_180064E8E
0x180064ced  mov     [rsp+88h+TokenHandle], rbp
0x180064cf5  mov     [rsp+88h+hObject], 0
0x180064d01  call    cs:__imp_GetCurrentProcess
0x180064d07  lea     r8, [rsp+88h+hObject]; TokenHandle
0x180064d0f  mov     edx, 8; DesiredAccess
0x180064d14  mov     rcx, rax; ProcessHandle
0x180064d17  call    cs:__imp_OpenProcessToken
0x180064d1d  test    eax, eax
0x180064d1f  jnz     loc_180064DBE
0x180064d25  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x180064d2b  jnz     loc_180064EAA
0x180064d31  mov     rdx, [rsp+88h+TokenHandle]; Token
0x180064d39  cmp     rdx, rbp
0x180064d3c  jnz     loc_180064DE7
0x180064d42  mov     ecx, cs:dword_180306D40
0x180064d48  jmp     loc_180064B7E
0x180064d4d  call    cs:__imp_TlsAlloc
0x180064d53  mov     cs:?g_dwImpersonationSlot@@3KA, eax; ulong g_dwImpersonationSlot
0x180064d59  mov     esi, eax
0x180064d5b  cmp     eax, ebp
0x180064d5d  jnz     loc_180064BD3
0x180064d63  mov     rcx, r14; lpCriticalSection
0x180064d66  call    cs:__imp_LeaveCriticalSection
0x180064d6c  mov     eax, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x180064d72  add     eax, 0FFFFFFFEh
0x180064d75  cmp     eax, 1
0x180064d78  ja      loc_180064CA6
0x180064d7e  mov     ecx, ebp; uExitCode
0x180064d80  call    cs:__imp_ExitProcess
0x180064d87  mov     rax, cs:?CoImpersonateClient@OLE32@@3P6AJXZEA; long (*OLE32::CoImpersonateClient)(void)
0x180064d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d93  test    eax, eax
0x180064d95  jz      loc_180064C9A
0x180064d9b  mov     edx, r14d; lpTlsValue
0x180064d9e  mov     ecx, esi; dwTlsIndex
0x180064da0  call    cs:__imp_TlsSetValue
0x180064da6  call    ExitProcessIfNotClient
0x180064dab  jmp     loc_180064CA6
0x180064db0  mov     r8d, ebx
0x180064db3  shl     r8d, 1Dh
0x180064db7  xor     ebp, ebp
0x180064db9  jmp     loc_180064C30
0x180064dbe  mov     rcx, [rsp+88h+hObject]; void *
0x180064dc6  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x180064dcb  mov     rcx, [rsp+88h+hObject]; hObject
0x180064dd3  movzx   ebx, al
0x180064dd6  call    cs:__imp_CloseHandle
0x180064ddc  mov     cs:dword_180306D40, ebx
0x180064de2  jmp     loc_180064D31
0x180064de7  xor     ecx, ecx; Thread
0x180064de9  call    cs:__imp_SetThreadToken
0x180064def  test    eax, eax
0x180064df1  jnz     short loc_180064DF8
0x180064df3  call    ExitProcessIfNotClient
0x180064df8  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x180064e00  call    cs:__imp_CloseHandle
0x180064e06  jmp     loc_180064D42
0x180064e0b  cmp     ebx, 1
0x180064e0e  jnz     short loc_180064D9B
0x180064e10  mov     rcx, cs:?g_pCustomActionContext@@3PEAVCMsiCustomAction@@EA; CMsiCustomAction * g_pCustomActionContext
0x180064e17  mov     rdx, [rcx+78h]
0x180064e1b  lea     rax, [rdx-1]
0x180064e1f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180064e23  jbe     loc_180064C8A
0x180064e29  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x180064e30  mov     eax, [rcx+64h]
0x180064e33  jz      short loc_180064E82
0x180064e35  cmp     eax, 9
0x180064e38  ja      short loc_180064E62
0x180064e3a  mov     ecx, 282h
0x180064e3f  bt      ecx, eax
0x180064e42  jnb     short loc_180064E62
0x180064e44  mov     edx, r14d; lpTlsValue
0x180064e47  mov     ecx, esi; dwTlsIndex
0x180064e49  call    cs:__imp_TlsSetValue
0x180064e4f  jmp     loc_180064CA6
0x180064e54  cmp     eax, 2
0x180064e57  jz      loc_180064D9B
0x180064e5d  jmp     loc_180064C9E
0x180064e62  call    ExitProcessIfNotClient
0x180064e67  jmp     short loc_180064E44
0x180064e69  mov     rdx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x180064e70  test    rdx, rdx
0x180064e73  jz      loc_180064D9B
0x180064e79  mov     rdx, [rdx+28h]
0x180064e7d  jmp     loc_180064C81
0x180064e82  cmp     eax, 8
0x180064e85  ja      short loc_180064E62
0x180064e87  mov     ecx, 141h
0x180064e8c  jmp     short loc_180064E3F
0x180064e8e  xor     edx, edx; Token
0x180064e90  xor     ecx, ecx; Thread
0x180064e92  call    cs:__imp_SetThreadToken
0x180064e98  test    eax, eax
0x180064e9a  jnz     loc_180064CF5
0x180064ea0  call    ExitProcessIfNotClient
0x180064ea5  jmp     loc_180064CF5
0x180064eaa  lea     rax, aNull; "(NULL)"
0x180064eb1  xor     edx, edx; unsigned __int16
0x180064eb3  mov     [rsp+88h+var_30], rdx; void *
0x180064eb8  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x180064ebf  mov     [rsp+88h+var_38], edx; unsigned int
0x180064ec3  xor     r8d, r8d; int
0x180064ec6  mov     [rsp+88h+var_40], rax; unsigned __int16 *
0x180064ecb  mov     [rsp+88h+var_48], rax; unsigned __int16 *
0x180064ed0  lea     ecx, [rdx+9]; int
0x180064ed3  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x180064ed8  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x180064edd  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180064ee2  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x180064ee7  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180064eec  jmp     loc_180064D31
0x180064ef1  cmp     ebx, 2
0x180064ef4  cmovz   ebx, r12d
0x180064ef8  jmp     loc_180064C0E
0x180064efd  mov     ebx, r12d
0x180064f00  jmp     loc_180064C30
0x180064f05  mov     ebx, 1
0x180064f0a  jmp     loc_180064C30
```

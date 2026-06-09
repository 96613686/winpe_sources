# GrabMutex(ushort const *,ulong,void * &)

- ea: `0x18014d394`
- end: `0x18014d5e8`
- name: `?GrabMutex@@YAHPEBGKAEAPEAX@Z`
- size: `596`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18014d2d0`

## callees

- `0x1800141e0`
- `0x1800817f8`
- `0x180092280`
- `0x1800924b8`
- `0x1800d7428`
- `0x180122110`
- `0x18014d394`
- `0x18015c794`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x18014d45c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014d4a2`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014d4ee`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014d45c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014d4a2`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014d4ee`
- `KERNEL32!CreateMutexW` at `0x18014d53b`
- `KERNEL32!CreateMutexW` at `0x18014d53b`
- `KERNEL32!CloseHandle` at `0x18014d578`
- `KERNEL32!CloseHandle` at `0x18014d578`
- `KERNEL32!GetLastError` at `0x18014d589`
- `KERNEL32!GetLastError` at `0x18014d5a3`
- `KERNEL32!GetLastError` at `0x18014d589`
- `KERNEL32!GetLastError` at `0x18014d5a3`
- `KERNEL32!WaitForSingleObject` at `0x18014d557`
- `KERNEL32!WaitForSingleObject` at `0x18014d557`

## string_xrefs

- `0x18014d3d9`: `_MSIExecute`

## pseudocode

```c
__int64 __fastcall GrabMutex(const unsigned __int16 *a1, __int64 a2, void **a3)
{
  PSID *pSid; // rax
  PSID *v6; // rax
  PSID *v7; // rax
  void *v8; // r8
  struct _SECURITY_ATTRIBUTES *v9; // rax
  HANDLE MutexW; // rax
  DWORD v11; // eax
  DWORD LastError; // ebx
  _BYTE v13[32]; // [rsp+60h] [rbp-A0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp-80h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v15; // [rsp+88h] [rbp-78h] BYREF
  PSID v16[2]; // [rsp+90h] [rbp-70h] BYREF
  int v17; // [rsp+A0h] [rbp-60h]
  _BYTE v18[16]; // [rsp+A8h] [rbp-58h] BYREF
  int v19; // [rsp+B8h] [rbp-48h]
  _BYTE v20[16]; // [rsp+C0h] [rbp-40h] BYREF
  int v21; // [rsp+D0h] [rbp-30h]
  WCHAR Name[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v23[512]; // [rsp+F0h] [rbp-10h] BYREF

  wcscpy(Name, L"Global\\");
  memset_0(v23, 0, 0x1F8u);
  if ( (int)StringCchCatW(Name, 0x104u, L"_MSIExecute") < 0 )
    return 1627;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v15.Value = 0;
  *(_WORD *)&v15.Value[4] = 256;
  `vector constructor iterator'(v16, 0x18u, 3u, (void *(*)(void *))CSIDAccess::CSIDAccess);
  pSid = (PSID *)CSIDPointer::operator&(v16);
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, pSid)
    && (v6 = (PSID *)CSIDPointer::operator&(v18), AllocateAndInitializeSid(&v15, 1u, 0, 0, 0, 0, 0, 0, 0, 0, v6))
    && (v7 = (PSID *)CSIDPointer::operator&(v20),
        AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v7)) )
  {
    v17 = 0x10000000;
    v19 = 0x10000000;
    v21 = 0x10000000;
    CSecurityDescription::CSecurityDescription((CSecurityDescription *)v13, 0, v8, v16, 3);
    v9 = CSecurityDescription::SecurityAttributes((CSecurityDescription *)v13);
    MutexW = CreateMutexW(v9, 0, Name);
    *a3 = MutexW;
    if ( MutexW )
    {
      v11 = WaitForSingleObject(MutexW, 0xBB8u);
      LastError = v11;
      if ( v11 == -1 || v11 == 258 )
      {
        CloseHandle(*a3);
        *a3 = 0;
      }
      else
      {
        LastError = 0;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    CSecurityDescription::~CSecurityDescription((CSecurityDescription *)v13);
  }
  else
  {
    LastError = GetLastError();
  }
  `vector destructor iterator'(v16, 0x18u, 3u, (void (*)(void *))CSIDAccess::~CSIDAccess);
  return LastError;
}

```

## disassembly

```asm
0x18014d394  push    rbp
0x18014d396  push    rbx
0x18014d397  push    rsi
0x18014d398  push    rdi
0x18014d399  lea     rbp, [rsp-208h]
0x18014d3a1  sub     rsp, 308h
0x18014d3a8  mov     rax, cs:__security_cookie
0x18014d3af  xor     rax, rsp
0x18014d3b2  mov     [rbp+220h+var_30], rax
0x18014d3b9  movups  xmm0, xmmword ptr cs:aGlobal_1; "Global\\"
0x18014d3c0  mov     rdi, r8
0x18014d3c3  lea     rcx, [rbp+220h+var_230]; void *
0x18014d3c7  xor     edx, edx; Val
0x18014d3c9  mov     r8d, 1F8h; Size
0x18014d3cf  movdqu  xmmword ptr [rbp+220h+Name], xmm0
0x18014d3d4  call    memset_0
0x18014d3d9  lea     r8, aMsiexecute_0; "_MSIExecute"
0x18014d3e0  mov     edx, 104h; unsigned __int64
0x18014d3e5  lea     rcx, [rbp+220h+Name]; unsigned __int16 *
0x18014d3e9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18014d3ee  xor     esi, esi
0x18014d3f0  test    eax, eax
0x18014d3f2  jns     short loc_18014D3FE
0x18014d3f4  mov     eax, 65Bh
0x18014d3f9  jmp     loc_18014D5CC
0x18014d3fe  mov     edx, 18h; unsigned __int64
0x18014d403  mov     dword ptr [rbp+220h+pIdentifierAuthority.Value], esi
0x18014d406  lea     r9, ??0CSIDAccess@@QEAA@XZ; void *(*)(void *)
0x18014d40d  mov     word ptr [rbp+220h+pIdentifierAuthority.Value+4], 500h
0x18014d413  lea     rcx, [rbp+220h+var_290]; void *
0x18014d417  mov     dword ptr [rbp+220h+var_298.Value], esi
0x18014d41a  mov     word ptr [rbp+220h+var_298.Value+4], 100h
0x18014d420  lea     r8d, [rdx-15h]; unsigned __int64
0x18014d424  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18014d429  lea     rcx, [rbp+220h+var_290]
0x18014d42d  call    ??ICSIDPointer@@QEAAPEAPEAU_SID@@XZ; CSIDPointer::operator&(void)
0x18014d432  mov     [rsp+320h+pSid], rax; pSid
0x18014d437  lea     rcx, [rbp+220h+pIdentifierAuthority]; pIdentifierAuthority
0x18014d43b  mov     [rsp+320h+nSubAuthority7], esi; nSubAuthority7
0x18014d43f  xor     r9d, r9d; nSubAuthority1
0x18014d442  mov     [rsp+320h+nSubAuthority6], esi; nSubAuthority6
0x18014d446  mov     dl, 1; nSubAuthorityCount
0x18014d448  mov     [rsp+320h+nSubAuthority5], esi; nSubAuthority5
0x18014d44c  mov     [rsp+320h+nSubAuthority4], esi; nSubAuthority4
0x18014d450  mov     [rsp+320h+nSubAuthority3], esi; nSubAuthority3
0x18014d454  lea     r8d, [r9+12h]; nSubAuthority0
0x18014d458  mov     [rsp+320h+nSubAuthority2], esi; nSubAuthority2
0x18014d45c  call    cs:__imp_AllocateAndInitializeSid
0x18014d463  nop     dword ptr [rax+rax+00h]
0x18014d468  test    eax, eax
0x18014d46a  jz      loc_18014D5A3
0x18014d470  lea     rcx, [rbp+220h+var_278]
0x18014d474  call    ??ICSIDPointer@@QEAAPEAPEAU_SID@@XZ; CSIDPointer::operator&(void)
0x18014d479  mov     [rsp+320h+pSid], rax; pSid
0x18014d47e  lea     rcx, [rbp+220h+var_298]; pIdentifierAuthority
0x18014d482  mov     [rsp+320h+nSubAuthority7], esi; nSubAuthority7
0x18014d486  xor     r9d, r9d; nSubAuthority1
0x18014d489  mov     [rsp+320h+nSubAuthority6], esi; nSubAuthority6
0x18014d48d  xor     r8d, r8d; nSubAuthority0
0x18014d490  mov     [rsp+320h+nSubAuthority5], esi; nSubAuthority5
0x18014d494  mov     dl, 1; nSubAuthorityCount
0x18014d496  mov     [rsp+320h+nSubAuthority4], esi; nSubAuthority4
0x18014d49a  mov     [rsp+320h+nSubAuthority3], esi; nSubAuthority3
0x18014d49e  mov     [rsp+320h+nSubAuthority2], esi; nSubAuthority2
0x18014d4a2  call    cs:__imp_AllocateAndInitializeSid
0x18014d4a9  nop     dword ptr [rax+rax+00h]
0x18014d4ae  test    eax, eax
0x18014d4b0  jz      loc_18014D5A3
0x18014d4b6  lea     rcx, [rbp+220h+var_260]
0x18014d4ba  call    ??ICSIDPointer@@QEAAPEAPEAU_SID@@XZ; CSIDPointer::operator&(void)
0x18014d4bf  mov     [rsp+320h+pSid], rax; pSid
0x18014d4c4  lea     rcx, [rbp+220h+pIdentifierAuthority]; pIdentifierAuthority
0x18014d4c8  mov     [rsp+320h+nSubAuthority7], esi; nSubAuthority7
0x18014d4cc  mov     r9d, 220h; nSubAuthority1
0x18014d4d2  mov     [rsp+320h+nSubAuthority6], esi; nSubAuthority6
0x18014d4d6  mov     r8d, 20h ; ' '; nSubAuthority0
0x18014d4dc  mov     [rsp+320h+nSubAuthority5], esi; nSubAuthority5
0x18014d4e0  mov     dl, 2; nSubAuthorityCount
0x18014d4e2  mov     [rsp+320h+nSubAuthority4], esi; nSubAuthority4
0x18014d4e6  mov     [rsp+320h+nSubAuthority3], esi; nSubAuthority3
0x18014d4ea  mov     [rsp+320h+nSubAuthority2], esi; nSubAuthority2
0x18014d4ee  call    cs:__imp_AllocateAndInitializeSid
0x18014d4f5  nop     dword ptr [rax+rax+00h]
0x18014d4fa  test    eax, eax
0x18014d4fc  jz      loc_18014D5A3
0x18014d502  mov     eax, 10000000h
0x18014d507  mov     [rsp+320h+nSubAuthority2], 3; int
0x18014d50f  lea     r9, [rbp+220h+var_290]; struct CSIDAccess *
0x18014d513  mov     [rbp+220h+var_280], eax
0x18014d516  xor     edx, edx; void *
0x18014d518  mov     [rbp+220h+var_268], eax
0x18014d51b  lea     rcx, [rsp+320h+var_2C0]; this
0x18014d520  mov     [rbp+220h+var_250], eax
0x18014d523  call    ??0CSecurityDescription@@QEAA@PEAX0PEAUCSIDAccess@@H@Z; CSecurityDescription::CSecurityDescription(void *,void *,CSIDAccess *,int)
0x18014d528  lea     rcx, [rsp+320h+var_2C0]; this
0x18014d52d  call    ?SecurityAttributes@CSecurityDescription@@QEAAQEAU_SECURITY_ATTRIBUTES@@XZ; CSecurityDescription::SecurityAttributes(void)
0x18014d532  mov     rcx, rax; lpMutexAttributes
0x18014d535  lea     r8, [rbp+220h+Name]; lpName
0x18014d539  xor     edx, edx; bInitialOwner
0x18014d53b  call    cs:__imp_CreateMutexW
0x18014d542  nop     dword ptr [rax+rax+00h]
0x18014d547  mov     [rdi], rax
0x18014d54a  test    rax, rax
0x18014d54d  jz      short loc_18014D589
0x18014d54f  mov     edx, 0BB8h; dwMilliseconds
0x18014d554  mov     rcx, rax; hHandle
0x18014d557  call    cs:__imp_WaitForSingleObject
0x18014d55e  nop     dword ptr [rax+rax+00h]
0x18014d563  mov     ebx, eax
0x18014d565  cmp     eax, 0FFFFFFFFh
0x18014d568  jz      short loc_18014D575
0x18014d56a  cmp     eax, 102h
0x18014d56f  jz      short loc_18014D575
0x18014d571  mov     ebx, esi
0x18014d573  jmp     short loc_18014D597
0x18014d575  mov     rcx, [rdi]; hObject
0x18014d578  call    cs:__imp_CloseHandle
0x18014d57f  nop     dword ptr [rax+rax+00h]
0x18014d584  mov     [rdi], rsi
0x18014d587  jmp     short loc_18014D597
0x18014d589  call    cs:__imp_GetLastError
0x18014d590  nop     dword ptr [rax+rax+00h]
0x18014d595  mov     ebx, eax
0x18014d597  lea     rcx, [rsp+320h+var_2C0]; this
0x18014d59c  call    ??1CSecurityDescription@@QEAA@XZ; CSecurityDescription::~CSecurityDescription(void)
0x18014d5a1  jmp     short loc_18014D5B1
0x18014d5a3  call    cs:__imp_GetLastError
0x18014d5aa  nop     dword ptr [rax+rax+00h]
0x18014d5af  mov     ebx, eax
0x18014d5b1  mov     edx, 18h; unsigned __int64
0x18014d5b6  lea     r9, ??1CSIDAccess@@QEAA@XZ; void (*)(void *)
0x18014d5bd  lea     rcx, [rbp+220h+var_290]; void *
0x18014d5c1  lea     r8d, [rdx-15h]; unsigned __int64
0x18014d5c5  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18014d5ca  mov     eax, ebx
0x18014d5cc  mov     rcx, [rbp+220h+var_30]
0x18014d5d3  xor     rcx, rsp; StackCookie
0x18014d5d6  call    __security_check_cookie
0x18014d5db  add     rsp, 308h
0x18014d5e2  pop     rdi
0x18014d5e3  pop     rsi
0x18014d5e4  pop     rbx
0x18014d5e5  pop     rbp
0x18014d5e6  retn
```

# GrabMutex(ushort const *,ulong,void * &)

- ea: `0x180147e4c`
- end: `0x18014806f`
- name: `?GrabMutex@@YAHPEBGKAEAPEAX@Z`
- size: `547`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180147d88`

## callees

- `0x1800255e0`
- `0x18006c044`
- `0x18006c0cc`
- `0x18006c17c`
- `0x1800c9830`
- `0x180121310`
- `0x180147e4c`
- `0x180156d80`
- `0x18025ab2a`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x180147f14`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147f54`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147f9a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147f14`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147f54`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147f9a`
- `KERNEL32!CreateMutexW` at `0x180147fe1`
- `KERNEL32!CreateMutexW` at `0x180147fe1`
- `KERNEL32!CloseHandle` at `0x180148012`
- `KERNEL32!CloseHandle` at `0x180148012`
- `KERNEL32!GetLastError` at `0x18014801d`
- `KERNEL32!GetLastError` at `0x180148031`
- `KERNEL32!GetLastError` at `0x18014801d`
- `KERNEL32!GetLastError` at `0x180148031`
- `KERNEL32!WaitForSingleObject` at `0x180147ff7`
- `KERNEL32!WaitForSingleObject` at `0x180147ff7`

## string_xrefs

- `0x180147e91`: `_MSIExecute`

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
0x180147e4c  push    rbp
0x180147e4e  push    rbx
0x180147e4f  push    rsi
0x180147e50  push    rdi
0x180147e51  lea     rbp, [rsp-208h]
0x180147e59  sub     rsp, 308h
0x180147e60  mov     rax, cs:__security_cookie
0x180147e67  xor     rax, rsp
0x180147e6a  mov     [rbp+220h+var_30], rax
0x180147e71  movups  xmm0, xmmword ptr cs:aGlobal_1; "Global\\"
0x180147e78  mov     rdi, r8
0x180147e7b  lea     rcx, [rbp+220h+var_230]; void *
0x180147e7f  xor     edx, edx; Val
0x180147e81  mov     r8d, 1F8h; Size
0x180147e87  movdqu  xmmword ptr [rbp+220h+Name], xmm0
0x180147e8c  call    memset_0
0x180147e91  lea     r8, aMsiexecute_0; "_MSIExecute"
0x180147e98  mov     edx, 104h; unsigned __int64
0x180147e9d  lea     rcx, [rbp+220h+Name]; unsigned __int16 *
0x180147ea1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180147ea6  xor     esi, esi
0x180147ea8  test    eax, eax
0x180147eaa  jns     short loc_180147EB6
0x180147eac  mov     eax, 65Bh
0x180147eb1  jmp     loc_180148054
0x180147eb6  mov     edx, 18h; unsigned __int64
0x180147ebb  mov     dword ptr [rbp+220h+pIdentifierAuthority.Value], esi
0x180147ebe  lea     r9, ??0CSIDAccess@@QEAA@XZ; void *(*)(void *)
0x180147ec5  mov     word ptr [rbp+220h+pIdentifierAuthority.Value+4], 500h
0x180147ecb  lea     rcx, [rbp+220h+var_290]; void *
0x180147ecf  mov     dword ptr [rbp+220h+var_298.Value], esi
0x180147ed2  mov     word ptr [rbp+220h+var_298.Value+4], 100h
0x180147ed8  lea     r8d, [rdx-15h]; unsigned __int64
0x180147edc  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180147ee1  lea     rcx, [rbp+220h+var_290]
0x180147ee5  call    ??ICSIDPointer@@QEAAPEAPEAU_SID@@XZ; CSIDPointer::operator&(void)
0x180147eea  mov     [rsp+320h+pSid], rax; pSid
0x180147eef  lea     rcx, [rbp+220h+pIdentifierAuthority]; pIdentifierAuthority
0x180147ef3  mov     [rsp+320h+nSubAuthority7], esi; nSubAuthority7
0x180147ef7  xor     r9d, r9d; nSubAuthority1
0x180147efa  mov     [rsp+320h+nSubAuthority6], esi; nSubAuthority6
0x180147efe  mov     dl, 1; nSubAuthorityCount
0x180147f00  mov     [rsp+320h+nSubAuthority5], esi; nSubAuthority5
0x180147f04  mov     [rsp+320h+nSubAuthority4], esi; nSubAuthority4
0x180147f08  mov     [rsp+320h+nSubAuthority3], esi; nSubAuthority3
0x180147f0c  lea     r8d, [r9+12h]; nSubAuthority0
0x180147f10  mov     [rsp+320h+nSubAuthority2], esi; nSubAuthority2
0x180147f14  call    cs:__imp_AllocateAndInitializeSid
0x180147f1a  test    eax, eax
0x180147f1c  jz      loc_180148031
0x180147f22  lea     rcx, [rbp+220h+var_278]
0x180147f26  call    ??ICSIDPointer@@QEAAPEAPEAU_SID@@XZ; CSIDPointer::operator&(void)
0x180147f2b  mov     [rsp+320h+pSid], rax; pSid
0x180147f30  lea     rcx, [rbp+220h+var_298]; pIdentifierAuthority
0x180147f34  mov     [rsp+320h+nSubAuthority7], esi; nSubAuthority7
0x180147f38  xor     r9d, r9d; nSubAuthority1
0x180147f3b  mov     [rsp+320h+nSubAuthority6], esi; nSubAuthority6
0x180147f3f  xor     r8d, r8d; nSubAuthority0
0x180147f42  mov     [rsp+320h+nSubAuthority5], esi; nSubAuthority5
0x180147f46  mov     dl, 1; nSubAuthorityCount
0x180147f48  mov     [rsp+320h+nSubAuthority4], esi; nSubAuthority4
0x180147f4c  mov     [rsp+320h+nSubAuthority3], esi; nSubAuthority3
0x180147f50  mov     [rsp+320h+nSubAuthority2], esi; nSubAuthority2
0x180147f54  call    cs:__imp_AllocateAndInitializeSid
0x180147f5a  test    eax, eax
0x180147f5c  jz      loc_180148031
0x180147f62  lea     rcx, [rbp+220h+var_260]
0x180147f66  call    ??ICSIDPointer@@QEAAPEAPEAU_SID@@XZ; CSIDPointer::operator&(void)
0x180147f6b  mov     [rsp+320h+pSid], rax; pSid
0x180147f70  lea     rcx, [rbp+220h+pIdentifierAuthority]; pIdentifierAuthority
0x180147f74  mov     [rsp+320h+nSubAuthority7], esi; nSubAuthority7
0x180147f78  mov     r9d, 220h; nSubAuthority1
0x180147f7e  mov     [rsp+320h+nSubAuthority6], esi; nSubAuthority6
0x180147f82  mov     r8d, 20h ; ' '; nSubAuthority0
0x180147f88  mov     [rsp+320h+nSubAuthority5], esi; nSubAuthority5
0x180147f8c  mov     dl, 2; nSubAuthorityCount
0x180147f8e  mov     [rsp+320h+nSubAuthority4], esi; nSubAuthority4
0x180147f92  mov     [rsp+320h+nSubAuthority3], esi; nSubAuthority3
0x180147f96  mov     [rsp+320h+nSubAuthority2], esi; nSubAuthority2
0x180147f9a  call    cs:__imp_AllocateAndInitializeSid
0x180147fa0  test    eax, eax
0x180147fa2  jz      loc_180148031
0x180147fa8  mov     eax, 10000000h
0x180147fad  mov     [rsp+320h+nSubAuthority2], 3; int
0x180147fb5  lea     r9, [rbp+220h+var_290]; struct CSIDAccess *
0x180147fb9  mov     [rbp+220h+var_280], eax
0x180147fbc  xor     edx, edx; void *
0x180147fbe  mov     [rbp+220h+var_268], eax
0x180147fc1  lea     rcx, [rsp+320h+var_2C0]; this
0x180147fc6  mov     [rbp+220h+var_250], eax
0x180147fc9  call    ??0CSecurityDescription@@QEAA@PEAX0PEAUCSIDAccess@@H@Z; CSecurityDescription::CSecurityDescription(void *,void *,CSIDAccess *,int)
0x180147fce  lea     rcx, [rsp+320h+var_2C0]; this
0x180147fd3  call    ?SecurityAttributes@CSecurityDescription@@QEAAQEAU_SECURITY_ATTRIBUTES@@XZ; CSecurityDescription::SecurityAttributes(void)
0x180147fd8  mov     rcx, rax; lpMutexAttributes
0x180147fdb  lea     r8, [rbp+220h+Name]; lpName
0x180147fdf  xor     edx, edx; bInitialOwner
0x180147fe1  call    cs:__imp_CreateMutexW
0x180147fe7  mov     [rdi], rax
0x180147fea  test    rax, rax
0x180147fed  jz      short loc_18014801D
0x180147fef  mov     edx, 0BB8h; dwMilliseconds
0x180147ff4  mov     rcx, rax; hHandle
0x180147ff7  call    cs:__imp_WaitForSingleObject
0x180147ffd  mov     ebx, eax
0x180147fff  cmp     eax, 0FFFFFFFFh
0x180148002  jz      short loc_18014800F
0x180148004  cmp     eax, 102h
0x180148009  jz      short loc_18014800F
0x18014800b  mov     ebx, esi
0x18014800d  jmp     short loc_180148025
0x18014800f  mov     rcx, [rdi]; hObject
0x180148012  call    cs:__imp_CloseHandle
0x180148018  mov     [rdi], rsi
0x18014801b  jmp     short loc_180148025
0x18014801d  call    cs:__imp_GetLastError
0x180148023  mov     ebx, eax
0x180148025  lea     rcx, [rsp+320h+var_2C0]; this
0x18014802a  call    ??1CSecurityDescription@@QEAA@XZ; CSecurityDescription::~CSecurityDescription(void)
0x18014802f  jmp     short loc_180148039
0x180148031  call    cs:__imp_GetLastError
0x180148037  mov     ebx, eax
0x180148039  mov     edx, 18h; unsigned __int64
0x18014803e  lea     r9, ??1CSIDAccess@@QEAA@XZ; void (*)(void *)
0x180148045  lea     rcx, [rbp+220h+var_290]; void *
0x180148049  lea     r8d, [rdx-15h]; unsigned __int64
0x18014804d  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180148052  mov     eax, ebx
0x180148054  mov     rcx, [rbp+220h+var_30]
0x18014805b  xor     rcx, rsp; StackCookie
0x18014805e  call    __security_check_cookie
0x180148063  add     rsp, 308h
0x18014806a  pop     rdi
0x18014806b  pop     rsi
0x18014806c  pop     rbx
0x18014806d  pop     rbp
0x18014806e  retn
```

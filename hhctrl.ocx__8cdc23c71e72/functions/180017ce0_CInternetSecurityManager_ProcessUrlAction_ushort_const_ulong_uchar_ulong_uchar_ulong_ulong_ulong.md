# CInternetSecurityManager::ProcessUrlAction(ushort const *,ulong,uchar *,ulong,uchar *,ulong,ulong,ulong)

- ea: `0x180017ce0`
- end: `0x180017ecf`
- name: `?ProcessUrlAction@CInternetSecurityManager@@UEAAJPEBGKPEAEK1KKK@Z`
- size: `495`
- prototype: `__int64 __fastcall(CInternetSecurityManager *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001e30`
- `0x180002244`
- `0x1800022b4`
- `0x180003fc0`
- `0x180017ce0`
- `0x18001fff0`
- `0x180065230`
- `0x180068090`
- `0x180068a30`
- `0x18006ac20`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180017d38`
- `KERNEL32!LeaveCriticalSection` at `0x180017d38`
- `KERNEL32!EnterCriticalSection` at `0x180017d16`
- `KERNEL32!EnterCriticalSection` at `0x180017d16`
- `urlmon!CoInternetCreateSecurityManager` at `0x180017db4`
- `urlmon!CoInternetCreateSecurityManager` at `0x180017db4`

## pseudocode

```c
HRESULT __fastcall CInternetSecurityManager::ProcessUrlAction(
        CInternetSecurityManager *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9)
{
  char v9; // di
  HHUrlSecurityManager::InternalSecurityManager *v14; // rcx
  char v15; // al
  bool v16; // bl
  HRESULT result; // eax
  const char *v18; // rbx
  unsigned __int16 v19; // r8
  char *v20[9]; // [rsp+50h] [rbp-48h] BYREF

  v9 = 0;
  LODWORD(v20[0]) = 0;
  if ( byte_18008C3A9 )
  {
    v15 = byte_18008C3A8;
  }
  else
  {
    byte_18008C3A9 = 1;
    EnterCriticalSection(&CriticalSection);
    if ( !byte_18008C2E4 )
    {
      HHUrlSecurityManager::InternalSecurityManager::ReadRegistryData(v14);
      byte_18008C2E4 = 1;
    }
    LeaveCriticalSection(&CriticalSection);
    v15 = *(_DWORD *)&dword_18008C2E0 == 1;
    byte_18008C3A8 = *(_DWORD *)&dword_18008C2E0 == 1;
  }
  v16 = 1;
  if ( !v15 )
  {
    if ( g_fShortcutsAllowedInProcess != 1
      || (v20[0] = 0, CStr::operator=(v20, a2), v9 = 1, !(unsigned int)IsCompiledURL(v20[0])) )
    {
      v16 = 0;
    }
  }
  if ( (v9 & 1) != 0 )
    CWStr::~CWStr((CWStr *)v20);
  if ( v16 )
  {
    if ( *((_QWORD *)this + 3) )
      return (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int))(**((_QWORD **)this + 3) + 56LL))(
               *((_QWORD *)this + 3),
               a2,
               a3,
               a4,
               a5,
               a6,
               a7,
               a8 | 0x10000,
               a9);
    result = CoInternetCreateSecurityManager(0, (IInternetSecurityManager **)this + 3, 0);
    if ( result >= 0 )
      return (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int))(**((_QWORD **)this + 3) + 56LL))(
               *((_QWORD *)this + 3),
               a2,
               a3,
               a4,
               a5,
               a6,
               a7,
               a8 | 0x10000,
               a9);
  }
  else
  {
    if ( dword_18008C9C8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_18008C9C8);
      if ( dword_18008C9C8 == -1 )
      {
        HHEventManager::HHEventManager((HHEventManager *)qword_18008C9D0);
        atexit(CInternetSecurityManager::ProcessUrlAction_::_15_::_dynamic_atexit_destructor_for__eventMgr__);
        Init_thread_footer(&dword_18008C9C8);
      }
    }
    v18 = qword_18008C9F8;
    v20[0] = 0;
    CStr::operator=(v20, a2);
    HHEventManager::HHReportEvent((HHEventManager *)qword_18008C9D0, 0x770u, v19, v20[0], v18);
    CWStr::~CWStr((CWStr *)v20);
    return -2146697199;
  }
  return result;
}

```

## disassembly

```asm
0x180017ce0  push    rbx
0x180017ce2  push    rbp
0x180017ce3  push    rsi
0x180017ce4  push    rdi
0x180017ce5  push    r14
0x180017ce7  push    r15
0x180017ce9  sub     rsp, 68h
0x180017ced  xor     edi, edi
0x180017cef  mov     r14, r9
0x180017cf2  mov     dword ptr [rsp+98h+var_48], edi
0x180017cf6  mov     r15d, r8d
0x180017cf9  cmp     cs:byte_18008C3A9, dil
0x180017d00  mov     rsi, rdx
0x180017d03  mov     rbp, rcx
0x180017d06  jnz     short loc_180017D50
0x180017d08  lea     rcx, CriticalSection; lpCriticalSection
0x180017d0f  mov     cs:byte_18008C3A9, 1
0x180017d16  call    cs:__imp_EnterCriticalSection
0x180017d1c  cmp     cs:byte_18008C2E4, dil
0x180017d23  jnz     short loc_180017D31
0x180017d25  call    ?ReadRegistryData@InternalSecurityManager@HHUrlSecurityManager@@AEAAXXZ; HHUrlSecurityManager::InternalSecurityManager::ReadRegistryData(void)
0x180017d2a  mov     cs:byte_18008C2E4, 1
0x180017d31  lea     rcx, CriticalSection; lpCriticalSection
0x180017d38  call    cs:__imp_LeaveCriticalSection
0x180017d3e  cmp     cs:dword_18008C2E0, 1
0x180017d45  setz    al
0x180017d48  mov     cs:byte_18008C3A8, al
0x180017d4e  jmp     short loc_180017D56
0x180017d50  mov     al, cs:byte_18008C3A8
0x180017d56  test    al, al
0x180017d58  jnz     short loc_180017D8C
0x180017d5a  cmp     cs:?g_fShortcutsAllowedInProcess@@3HA, 1; int g_fShortcutsAllowedInProcess
0x180017d61  jnz     short loc_180017D88
0x180017d63  mov     rdx, rsi
0x180017d66  mov     [rsp+98h+var_48], rdi
0x180017d6b  lea     rcx, [rsp+98h+var_48]
0x180017d70  call    ??4CStr@@QEAAXPEBG@Z; CStr::operator=(ushort const *)
0x180017d75  mov     rcx, [rsp+98h+var_48]; char *
0x180017d7a  mov     edi, 1
0x180017d7f  call    ?IsCompiledURL@@YAHPEBD@Z; IsCompiledURL(char const *)
0x180017d84  test    eax, eax
0x180017d86  jnz     short loc_180017D8C
0x180017d88  xor     bl, bl
0x180017d8a  jmp     short loc_180017D8E
0x180017d8c  mov     bl, 1
0x180017d8e  test    dil, 1
0x180017d92  jz      short loc_180017D9E
0x180017d94  lea     rcx, [rsp+98h+var_48]; this
0x180017d99  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180017d9e  test    bl, bl
0x180017da0  jz      short loc_180017E1F
0x180017da2  lea     rbx, [rbp+18h]
0x180017da6  cmp     qword ptr [rbx], 0
0x180017daa  jnz     short loc_180017DC2
0x180017dac  xor     r8d, r8d; dwReserved
0x180017daf  mov     rdx, rbx; ppSM
0x180017db2  xor     ecx, ecx; pSP
0x180017db4  call    cs:__imp_CoInternetCreateSecurityManager
0x180017dba  test    eax, eax
0x180017dbc  js      loc_180017EC2
0x180017dc2  mov     edx, [rsp+98h+arg_40]
0x180017dc9  mov     r9, r14
0x180017dcc  mov     r8d, [rsp+98h+arg_38]
0x180017dd4  mov     rcx, [rbx]
0x180017dd7  bts     r8d, 10h
0x180017ddc  mov     [rsp+98h+var_58], edx
0x180017de0  mov     edx, [rsp+98h+arg_30]
0x180017de7  mov     [rsp+98h+var_60], r8d
0x180017dec  mov     r8d, r15d
0x180017def  mov     rax, [rcx]
0x180017df2  mov     [rsp+98h+var_68], edx
0x180017df6  mov     rdx, [rsp+98h+arg_28]
0x180017dfe  mov     [rsp+98h+var_70], rdx
0x180017e03  mov     edx, [rsp+98h+arg_20]
0x180017e0a  mov     rax, [rax+38h]
0x180017e0e  mov     dword ptr [rsp+98h+var_78], edx
0x180017e12  mov     rdx, rsi
0x180017e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e1a  jmp     loc_180017EC2
0x180017e1f  mov     ecx, cs:_tls_index
0x180017e25  mov     rax, gs:58h
0x180017e2e  mov     edx, 4
0x180017e33  mov     rax, [rax+rcx*8]
0x180017e37  mov     eax, [rdx+rax]
0x180017e3a  cmp     cs:dword_18008C9C8, eax
0x180017e40  jle     short loc_180017E7B
0x180017e42  lea     rcx, dword_18008C9C8
0x180017e49  call    _Init_thread_header
0x180017e4e  cmp     cs:dword_18008C9C8, 0FFFFFFFFh
0x180017e55  jnz     short loc_180017E7B
0x180017e57  lea     rcx, qword_18008C9D0; this
0x180017e5e  call    ??0HHEventManager@@QEAA@XZ; HHEventManager::HHEventManager(void)
0x180017e63  lea     rcx, _CInternetSecurityManager__ProcessUrlAction____15____dynamic_atexit_destructor_for__eventMgr__; void (__cdecl *)()
0x180017e6a  call    atexit
0x180017e6f  lea     rcx, dword_18008C9C8
0x180017e76  call    _Init_thread_footer
0x180017e7b  mov     rbx, cs:qword_18008C9F8
0x180017e82  lea     rcx, [rsp+98h+var_48]
0x180017e87  mov     rdx, rsi
0x180017e8a  mov     [rsp+98h+var_48], 0
0x180017e93  call    ??4CStr@@QEAAXPEBG@Z; CStr::operator=(ushort const *)
0x180017e98  mov     r9, [rsp+98h+var_48]; char *
0x180017e9d  lea     rcx, qword_18008C9D0; this
0x180017ea4  mov     edx, 770h; unsigned int
0x180017ea9  mov     [rsp+98h+var_78], rbx; char *
0x180017eae  call    ?HHReportEvent@HHEventManager@@QEAAXKGPEBD0@Z; HHEventManager::HHReportEvent(ulong,ushort,char const *,char const *)
0x180017eb3  lea     rcx, [rsp+98h+var_48]; this
0x180017eb8  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180017ebd  mov     eax, 800C0011h
0x180017ec2  add     rsp, 68h
0x180017ec6  pop     r15
0x180017ec8  pop     r14
0x180017eca  pop     rdi
0x180017ecb  pop     rsi
0x180017ecc  pop     rbp
0x180017ecd  pop     rbx
0x180017ece  retn
```

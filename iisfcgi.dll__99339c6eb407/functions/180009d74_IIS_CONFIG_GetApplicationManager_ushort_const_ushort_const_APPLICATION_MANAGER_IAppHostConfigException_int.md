# IIS_CONFIG::GetApplicationManager(ushort const *,ushort const *,APPLICATION_MANAGER * *,IAppHostConfigException * *,int *)

- ea: `0x180009d74`
- end: `0x180009eab`
- name: `?GetApplicationManager@IIS_CONFIG@@QEAAJPEBG0PEAPEAVAPPLICATION_MANAGER@@PEAPEAUIAppHostConfigException@@PEAH@Z`
- size: `311`
- prototype: `__int64 __fastcall(IIS_CONFIG *this, const unsigned __int16 *, const unsigned __int16 *, struct APPLICATION_MANAGER **, struct IAppHostConfigException **, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000d370`

## callees

- `0x180009cb0`
- `0x180009d74`
- `0x180009eb4`
- `0x18000edde`
- `0x18000ee10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009dfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009dfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e76`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009dd6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009dd6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009e81`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009e81`
- `iisutil!SAFE_snwprintf` at `0x180009e3a`
- `iisutil!SAFE_snwprintf` at `0x180009e3a`

## pseudocode

```c
__int64 __fastcall IIS_CONFIG::GetApplicationManager(
        IIS_CONFIG *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct APPLICATION_MANAGER **a4,
        struct IAppHostConfigException **a5,
        int *a6)
{
  int ApplicationManager; // ebx
  struct IAppHostConfigException *v11; // rax
  int v12; // r8d
  IIS_CONFIG_RECORD *Key; // rax
  _BYTE v15[32]; // [rsp+20h] [rbp-188h] BYREF
  unsigned __int16 *v16; // [rsp+40h] [rbp-168h]
  unsigned __int16 v17[128]; // [rsp+60h] [rbp-148h] BYREF

  memset_0(v17, 0, sizeof(v17));
  STRU::STRU((STRU *)v15, v17, 0x80u);
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1096));
  if ( *((_DWORD *)this + 284) )
  {
    ApplicationManager = -2147023901;
  }
  else
  {
    v11 = (struct IAppHostConfigException *)*((_QWORD *)this + 134);
    if ( v11 )
    {
      ApplicationManager = *((_DWORD *)this + 270);
      *a5 = v11;
    }
    else
    {
      ApplicationManager = SAFE_snwprintf((struct STRU *)v15, L"%s|%s", a2, a3);
      if ( ApplicationManager >= 0 )
      {
        Key = STATIC_WSTRING_HASH::FindKey(this, v16, v12);
        if ( Key )
        {
          *a6 = 1;
          ApplicationManager = IIS_CONFIG_RECORD::GetApplicationManager(Key, a4);
        }
        else
        {
          ApplicationManager = -2147023483;
        }
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1096));
  STRU::~STRU((STRU *)v15);
  return (unsigned int)ApplicationManager;
}

```

## disassembly

```asm
0x180009d74  push    rbx
0x180009d76  push    rbp
0x180009d77  push    rsi
0x180009d78  push    rdi
0x180009d79  push    r12
0x180009d7b  push    r14
0x180009d7d  push    r15
0x180009d7f  sub     rsp, 170h
0x180009d86  mov     rax, cs:__security_cookie
0x180009d8d  xor     rax, rsp
0x180009d90  mov     [rsp+1A8h+var_48], rax
0x180009d98  mov     rsi, [rsp+1A8h+arg_20]
0x180009da0  mov     r12, r8
0x180009da3  mov     r15, [rsp+1A8h+arg_28]
0x180009dab  mov     rbx, rdx
0x180009dae  mov     rdi, rcx
0x180009db1  xor     edx, edx; Val
0x180009db3  mov     r8d, 100h; Size
0x180009db9  lea     rcx, [rsp+1A8h+var_148]; void *
0x180009dbe  mov     r14, r9
0x180009dc1  call    memset_0
0x180009dc6  mov     r8d, 80h
0x180009dcc  lea     rdx, [rsp+1A8h+var_148]
0x180009dd1  lea     rcx, [rsp+1A8h+var_188]
0x180009dd6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009ddc  mov     qword ptr [r14], 0
0x180009de3  lea     rbp, [rdi+448h]
0x180009dea  mov     qword ptr [rsi], 0
0x180009df1  mov     rcx, rbp; lpCriticalSection
0x180009df4  mov     dword ptr [r15], 0
0x180009dfb  call    cs:__imp_EnterCriticalSection
0x180009e01  cmp     dword ptr [rdi+470h], 0
0x180009e08  jz      short loc_180009E11
0x180009e0a  mov     ebx, 800703E3h
0x180009e0f  jmp     short loc_180009E73
0x180009e11  mov     rax, [rdi+430h]
0x180009e18  test    rax, rax
0x180009e1b  jz      short loc_180009E28
0x180009e1d  mov     ebx, [rdi+438h]
0x180009e23  mov     [rsi], rax
0x180009e26  jmp     short loc_180009E73
0x180009e28  mov     r9, r12
0x180009e2b  lea     rdx, aSS_0; "%s|%s"
0x180009e32  mov     r8, rbx
0x180009e35  lea     rcx, [rsp+1A8h+var_188]
0x180009e3a  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180009e40  mov     ebx, eax
0x180009e42  test    eax, eax
0x180009e44  js      short loc_180009E73
0x180009e46  mov     rdx, [rsp+1A8h+var_168]; unsigned __int16 *
0x180009e4b  mov     rcx, rdi; this
0x180009e4e  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180009e53  test    rax, rax
0x180009e56  jz      short loc_180009E6E
0x180009e58  mov     rdx, r14; struct APPLICATION_MANAGER **
0x180009e5b  mov     dword ptr [r15], 1
0x180009e62  mov     rcx, rax; this
0x180009e65  call    ?GetApplicationManager@IIS_CONFIG_RECORD@@QEAAJPEAPEAVAPPLICATION_MANAGER@@@Z; IIS_CONFIG_RECORD::GetApplicationManager(APPLICATION_MANAGER * *)
0x180009e6a  mov     ebx, eax
0x180009e6c  jmp     short loc_180009E73
0x180009e6e  mov     ebx, 80070585h
0x180009e73  mov     rcx, rbp; lpCriticalSection
0x180009e76  call    cs:__imp_LeaveCriticalSection
0x180009e7c  lea     rcx, [rsp+1A8h+var_188]
0x180009e81  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009e87  mov     eax, ebx
0x180009e89  mov     rcx, [rsp+1A8h+var_48]
0x180009e91  xor     rcx, rsp; StackCookie
0x180009e94  call    __security_check_cookie
0x180009e99  add     rsp, 170h
0x180009ea0  pop     r15
0x180009ea2  pop     r14
0x180009ea4  pop     r12
0x180009ea6  pop     rdi
0x180009ea7  pop     rsi
0x180009ea8  pop     rbp
0x180009ea9  pop     rbx
0x180009eaa  retn
```

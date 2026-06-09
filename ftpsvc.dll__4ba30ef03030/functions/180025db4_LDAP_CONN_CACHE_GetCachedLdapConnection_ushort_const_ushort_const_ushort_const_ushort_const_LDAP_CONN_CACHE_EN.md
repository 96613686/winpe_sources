# LDAP_CONN_CACHE::GetCachedLdapConnection(ushort const *,ushort const *,ushort const *,ushort const *,LDAP_CONN_CACHE_ENTRY * *)

- ea: `0x180025db4`
- end: `0x180026037`
- name: `?GetCachedLdapConnection@LDAP_CONN_CACHE@@QEAAJPEBG000PEAPEAVLDAP_CONN_CACHE_ENTRY@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(LDAP_CONN_CACHE *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, wchar_t *String2, struct LDAP_CONN_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800061d0`

## callees

- `0x180001210`
- `0x180001250`
- `0x180025d14`
- `0x180025db4`
- `0x180026040`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025dfa`
- `msvcrt!_wcsicmp` at `0x180025e0e`
- `msvcrt!_wcsicmp` at `0x180025e22`
- `msvcrt!_wcsicmp` at `0x180025e3b`
- `msvcrt!_wcsicmp` at `0x180025f43`
- `msvcrt!_wcsicmp` at `0x180025f57`
- `msvcrt!_wcsicmp` at `0x180025f6b`
- `msvcrt!_wcsicmp` at `0x180025f84`
- `msvcrt!_wcsicmp` at `0x180025dfa`
- `msvcrt!_wcsicmp` at `0x180025e0e`
- `msvcrt!_wcsicmp` at `0x180025e22`
- `msvcrt!_wcsicmp` at `0x180025e3b`
- `msvcrt!_wcsicmp` at `0x180025f43`
- `msvcrt!_wcsicmp` at `0x180025f57`
- `msvcrt!_wcsicmp` at `0x180025f6b`
- `msvcrt!_wcsicmp` at `0x180025f84`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180025de4`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180025de4`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180025f2b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180025f2b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180025ff8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180025ff8`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180025e5b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180025e5b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025e99`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025ea7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025eb5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025ec3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025ed1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025e99`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025ea7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025eb5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025ec3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025ed1`

## pseudocode

```c
__int64 __fastcall LDAP_CONN_CACHE::GetCachedLdapConnection(
        LDAP_CONN_CACHE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        wchar_t *String2,
        struct LDAP_CONN_CACHE_ENTRY **a6)
{
  char *v10; // rbx
  int v11; // ebp
  CReaderWriterLock3 *v12; // r15
  LDAP_CONN_CACHE *i; // rdi
  int v14; // edi
  _DWORD *v15; // rax
  _DWORD *v16; // rbx
  LDAP_CONN_CACHE *j; // r14
  char *v18; // rbp
  LDAP_CONN_CACHE *v19; // rcx

  v10 = 0;
  v11 = 0;
  v12 = (LDAP_CONN_CACHE *)((char *)this + 16);
  CReaderWriterLock3::ReadLock((LDAP_CONN_CACHE *)((char *)this + 16));
  for ( i = *(LDAP_CONN_CACHE **)this; i != this; i = *(LDAP_CONN_CACHE **)i )
  {
    v10 = (char *)i - 8;
    if ( !_wcsicmp(*((const wchar_t **)i + 6), a2)
      && !_wcsicmp(*((const wchar_t **)v10 + 22), a3)
      && !_wcsicmp(*((const wchar_t **)v10 + 37), a4)
      && !_wcsicmp(*((const wchar_t **)v10 + 52), String2) )
    {
      v11 = 1;
      _InterlockedIncrement((volatile signed __int32 *)v10 + 1);
      break;
    }
  }
  CReaderWriterLock3::ReadUnlock(v12);
  v14 = 0;
  if ( v11 )
  {
    *a6 = (struct LDAP_CONN_CACHE_ENTRY *)v10;
  }
  else
  {
    v15 = operator new(0x338u);
    v16 = v15;
    if ( v15 )
    {
      v15[1] = 1;
      STRU::STRU(v15 + 6);
      STRU::STRU(v16 + 36);
      STRU::STRU(v16 + 66);
      STRU::STRU(v16 + 96);
      STRU::STRU(v16 + 126);
      *((_QWORD *)v16 + 102) = 0;
      *((_QWORD *)v16 + 2) = 0;
      *((_QWORD *)v16 + 1) = 0;
      *v16 = 1162036044;
    }
    else
    {
      v16 = 0;
    }
    if ( v16 )
    {
      v14 = LDAP_CONN_CACHE_ENTRY::Initialize((LDAP_CONN_CACHE_ENTRY *)v16, a2, a3, a4, String2);
      if ( v14 < 0 )
      {
        if ( _InterlockedExchangeAdd(v16 + 1, 0xFFFFFFFF) == 1 )
        {
          LDAP_CONN_CACHE_ENTRY::~LDAP_CONN_CACHE_ENTRY((LDAP_CONN_CACHE_ENTRY *)v16);
          operator delete(v16);
        }
      }
      else
      {
        CReaderWriterLock3::WriteLock(v12);
        for ( j = *(LDAP_CONN_CACHE **)this; ; j = *(LDAP_CONN_CACHE **)j )
        {
          if ( j == this )
          {
            v19 = *(LDAP_CONN_CACHE **)this;
            if ( *(LDAP_CONN_CACHE **)(*(_QWORD *)this + 8LL) != this )
              __fastfail(3u);
            *((_QWORD *)v16 + 1) = v19;
            *((_QWORD *)v16 + 2) = this;
            *((_QWORD *)v19 + 1) = v16 + 2;
            *(_QWORD *)this = v16 + 2;
            *a6 = (struct LDAP_CONN_CACHE_ENTRY *)v16;
            _InterlockedIncrement(v16 + 1);
            goto LABEL_31;
          }
          v18 = (char *)j - 8;
          if ( !_wcsicmp(*((const wchar_t **)j + 6), a2)
            && !_wcsicmp(*((const wchar_t **)v18 + 22), a3)
            && !_wcsicmp(*((const wchar_t **)v18 + 37), a4)
            && !_wcsicmp(*((const wchar_t **)v18 + 52), String2) )
          {
            break;
          }
        }
        _InterlockedIncrement((volatile signed __int32 *)v18 + 1);
        if ( _InterlockedExchangeAdd(v16 + 1, 0xFFFFFFFF) == 1 )
        {
          LDAP_CONN_CACHE_ENTRY::~LDAP_CONN_CACHE_ENTRY((LDAP_CONN_CACHE_ENTRY *)v16);
          operator delete(v16);
        }
        *a6 = (struct LDAP_CONN_CACHE_ENTRY *)v18;
LABEL_31:
        CReaderWriterLock3::WriteUnlock(v12);
      }
    }
    else
    {
      return (unsigned int)-2147024888;
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180025db4  mov     [rsp+arg_10], rbx
0x180025db9  mov     [rsp+arg_8], rdx
0x180025dbe  push    rbp
0x180025dbf  push    rsi
0x180025dc0  push    rdi
0x180025dc1  push    r12
0x180025dc3  push    r13
0x180025dc5  push    r14
0x180025dc7  push    r15
0x180025dc9  sub     rsp, 30h
0x180025dcd  mov     r12, r9
0x180025dd0  mov     r13, r8
0x180025dd3  mov     r14, rdx
0x180025dd6  mov     rsi, rcx
0x180025dd9  xor     ebx, ebx
0x180025ddb  xor     ebp, ebp
0x180025ddd  lea     r15, [rcx+10h]
0x180025de1  mov     rcx, r15
0x180025de4  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180025dea  mov     rdi, [rsi]
0x180025ded  jmp     short loc_180025E48
0x180025def  lea     rbx, [rdi-8]
0x180025df3  mov     rdx, r14; String2
0x180025df6  mov     rcx, [rbx+38h]; String1
0x180025dfa  call    cs:__imp__wcsicmp
0x180025e00  test    eax, eax
0x180025e02  jnz     short loc_180025E45
0x180025e04  mov     rdx, r13; String2
0x180025e07  mov     rcx, [rbx+0B0h]; String1
0x180025e0e  call    cs:__imp__wcsicmp
0x180025e14  test    eax, eax
0x180025e16  jnz     short loc_180025E45
0x180025e18  mov     rdx, r12; String2
0x180025e1b  mov     rcx, [rbx+128h]; String1
0x180025e22  call    cs:__imp__wcsicmp
0x180025e28  test    eax, eax
0x180025e2a  jnz     short loc_180025E45
0x180025e2c  mov     rdx, [rsp+68h+String2]; String2
0x180025e34  mov     rcx, [rbx+1A0h]; String1
0x180025e3b  call    cs:__imp__wcsicmp
0x180025e41  test    eax, eax
0x180025e43  jz      short loc_180025E4F
0x180025e45  mov     rdi, [rdi]
0x180025e48  cmp     rdi, rsi
0x180025e4b  jnz     short loc_180025DEF
0x180025e4d  jmp     short loc_180025E58
0x180025e4f  mov     ebp, 1
0x180025e54  lock inc dword ptr [rbx+4]
0x180025e58  mov     rcx, r15
0x180025e5b  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180025e61  xor     edi, edi
0x180025e63  test    ebp, ebp
0x180025e65  jz      short loc_180025E77
0x180025e67  mov     rax, [rsp+68h+arg_28]
0x180025e6f  mov     [rax], rbx
0x180025e72  jmp     loc_18002601D
0x180025e77  mov     ecx, 338h; Size
0x180025e7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025e81  mov     rbx, rax
0x180025e84  mov     [rsp+68h+arg_0], rax
0x180025e89  test    rax, rax
0x180025e8c  jz      short loc_180025EEE
0x180025e8e  mov     dword ptr [rax+4], 1
0x180025e95  lea     rcx, [rax+18h]
0x180025e99  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180025e9f  nop
0x180025ea0  lea     rcx, [rbx+90h]
0x180025ea7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180025ead  nop
0x180025eae  lea     rcx, [rbx+108h]
0x180025eb5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180025ebb  nop
0x180025ebc  lea     rcx, [rbx+180h]
0x180025ec3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180025ec9  nop
0x180025eca  lea     rcx, [rbx+1F8h]
0x180025ed1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180025ed7  mov     [rbx+330h], rdi
0x180025ede  mov     [rbx+10h], rdi
0x180025ee2  mov     [rbx+8], rdi
0x180025ee6  mov     dword ptr [rbx], 4543434Ch
0x180025eec  jmp     short loc_180025EF1
0x180025eee  mov     rbx, rdi
0x180025ef1  test    rbx, rbx
0x180025ef4  jnz     short loc_180025F00
0x180025ef6  mov     edi, 80070008h
0x180025efb  jmp     loc_18002601D
0x180025f00  mov     rax, [rsp+68h+String2]
0x180025f08  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x180025f0d  mov     r9, r12; unsigned __int16 *
0x180025f10  mov     r8, r13; unsigned __int16 *
0x180025f13  mov     rdx, r14; unsigned __int16 *
0x180025f16  mov     rcx, rbx; this
0x180025f19  call    ?Initialize@LDAP_CONN_CACHE_ENTRY@@QEAAJPEBG000@Z; LDAP_CONN_CACHE_ENTRY::Initialize(ushort const *,ushort const *,ushort const *,ushort const *)
0x180025f1e  mov     edi, eax
0x180025f20  test    eax, eax
0x180025f22  js      loc_180026000
0x180025f28  mov     rcx, r15
0x180025f2b  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180025f31  mov     r14, [rsi]
0x180025f34  jmp     short loc_180025F91
0x180025f36  lea     rbp, [r14-8]
0x180025f3a  mov     rdx, [rsp+68h+arg_8]; String2
0x180025f3f  mov     rcx, [rbp+38h]; String1
0x180025f43  call    cs:__imp__wcsicmp
0x180025f49  test    eax, eax
0x180025f4b  jnz     short loc_180025F8E
0x180025f4d  mov     rdx, r13; String2
0x180025f50  mov     rcx, [rbp+0B0h]; String1
0x180025f57  call    cs:__imp__wcsicmp
0x180025f5d  test    eax, eax
0x180025f5f  jnz     short loc_180025F8E
0x180025f61  mov     rdx, r12; String2
0x180025f64  mov     rcx, [rbp+128h]; String1
0x180025f6b  call    cs:__imp__wcsicmp
0x180025f71  test    eax, eax
0x180025f73  jnz     short loc_180025F8E
0x180025f75  mov     rdx, [rsp+68h+String2]; String2
0x180025f7d  mov     rcx, [rbp+1A0h]; String1
0x180025f84  call    cs:__imp__wcsicmp
0x180025f8a  test    eax, eax
0x180025f8c  jz      short loc_180025FA6
0x180025f8e  mov     r14, [r14]
0x180025f91  cmp     r14, rsi
0x180025f94  jnz     short loc_180025F36
0x180025f96  mov     rcx, [rsi]
0x180025f99  cmp     [rcx+8], rsi
0x180025f9d  jz      short loc_180025FD4
0x180025f9f  mov     ecx, 3
0x180025fa4  int     29h; Win8: RtlFailFast(ecx)
0x180025fa6  lock inc dword ptr [rbp+4]
0x180025faa  or      eax, 0FFFFFFFFh
0x180025fad  lock xadd [rbx+4], eax
0x180025fb2  cmp     eax, 1
0x180025fb5  jnz     short loc_180025FC7
0x180025fb7  mov     rcx, rbx; this
0x180025fba  call    ??1LDAP_CONN_CACHE_ENTRY@@QEAA@XZ; LDAP_CONN_CACHE_ENTRY::~LDAP_CONN_CACHE_ENTRY(void)
0x180025fbf  mov     rcx, rbx; Block
0x180025fc2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025fc7  mov     rax, [rsp+68h+arg_28]
0x180025fcf  mov     [rax], rbp
0x180025fd2  jmp     short loc_180025FF5
0x180025fd4  lea     rax, [rbx+8]
0x180025fd8  mov     [rax], rcx
0x180025fdb  mov     [rax+8], rsi
0x180025fdf  mov     [rcx+8], rax
0x180025fe3  mov     [rsi], rax
0x180025fe6  mov     rax, [rsp+68h+arg_28]
0x180025fee  mov     [rax], rbx
0x180025ff1  lock inc dword ptr [rbx+4]
0x180025ff5  mov     rcx, r15
0x180025ff8  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180025ffe  jmp     short loc_18002601D
0x180026000  or      eax, 0FFFFFFFFh
0x180026003  lock xadd [rbx+4], eax
0x180026008  cmp     eax, 1
0x18002600b  jnz     short loc_18002601D
0x18002600d  mov     rcx, rbx; this
0x180026010  call    ??1LDAP_CONN_CACHE_ENTRY@@QEAA@XZ; LDAP_CONN_CACHE_ENTRY::~LDAP_CONN_CACHE_ENTRY(void)
0x180026015  mov     rcx, rbx; Block
0x180026018  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002601d  mov     eax, edi
0x18002601f  mov     rbx, [rsp+68h+arg_10]
0x180026027  add     rsp, 30h
0x18002602b  pop     r15
0x18002602d  pop     r14
0x18002602f  pop     r13
0x180026031  pop     r12
0x180026033  pop     rdi
0x180026034  pop     rsi
0x180026035  pop     rbp
0x180026036  retn
```

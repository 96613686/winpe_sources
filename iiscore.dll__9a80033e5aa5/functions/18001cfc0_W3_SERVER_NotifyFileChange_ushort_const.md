# W3_SERVER::NotifyFileChange(ushort const *)

- ea: `0x18001cfc0`
- end: `0x18001d0f1`
- name: `?NotifyFileChange@W3_SERVER@@UEAAXPEBG@Z`
- size: `305`
- prototype: `void __fastcall(W3_SERVER *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180008930`
- `0x18000a340`
- `0x18001cfc0`
- `0x18001dbc0`
- `0x18003439a`
- `0x1800343f0`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18001d045`
- `msvcrt!_wcsupr` at `0x18001d045`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d0c7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d0c7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d03c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d072`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d088`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d03c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d072`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d088`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d029`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d029`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d01b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d01b`

## pseudocode

```c
void __fastcall W3_SERVER::NotifyFileChange(W3_SERVER *this, const unsigned __int16 *a2)
{
  wchar_t *Str; // rax
  const unsigned __int16 *v5; // rax
  const struct _GUID *v6; // rdx
  _QWORD v7[3]; // [rsp+20h] [rbp-E0h] BYREF
  int v8; // [rsp+38h] [rbp-C8h]
  _BYTE v9[64]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v10[256]; // [rsp+80h] [rbp-80h] BYREF

  if ( !*((_DWORD *)this + 5) )
  {
    memset_0(v10, 0, sizeof(v10));
    STRU::STRU((STRU *)v9, v10, 0x100u);
    if ( (int)STRU::Copy((STRU *)v9, a2) >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v9);
      _wcsupr(Str);
      if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(
                           ((unsigned __int64)this + 8) & -(__int64)(this != 0),
                           0,
                           4) )
      {
        v5 = STRU::QueryStr((STRU *)v9);
        IISGeneralEvents::FILE_CHANGE_NOTIFICATION::RaiseEvent(
          (struct IHttpTraceContext *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
          v6,
          v5);
      }
      v7[2] = 0;
      v7[0] = &FileChangeProvider::`vftable';
      v7[1] = STRU::QueryStr((STRU *)v9);
      v8 = 0;
      W3_SERVER::GlobalNotify((__int64)this, 0x80u, (__int64)v7);
    }
    STRU::~STRU((STRU *)v9);
  }
}

```

## disassembly

```asm
0x18001cfc0  mov     [rsp-8+arg_10], rbx
0x18001cfc5  mov     [rsp-8+arg_18], rdi
0x18001cfca  push    rbp
0x18001cfcb  lea     rbp, [rsp-190h]
0x18001cfd3  sub     rsp, 290h
0x18001cfda  mov     rax, cs:__security_cookie
0x18001cfe1  xor     rax, rsp
0x18001cfe4  mov     [rbp+190h+var_10], rax
0x18001cfeb  cmp     dword ptr [rcx+14h], 0
0x18001cfef  mov     rdi, rdx
0x18001cff2  mov     rbx, rcx
0x18001cff5  jnz     loc_18001D0CD
0x18001cffb  xor     edx, edx; Val
0x18001cffd  lea     rcx, [rbp+190h+var_210]; void *
0x18001d001  mov     r8d, 200h; Size
0x18001d007  call    memset_0
0x18001d00c  mov     r8d, 100h
0x18001d012  lea     rdx, [rbp+190h+var_210]
0x18001d016  lea     rcx, [rsp+290h+var_250]
0x18001d01b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001d021  mov     rdx, rdi
0x18001d024  lea     rcx, [rsp+290h+var_250]
0x18001d029  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001d02f  lea     rcx, [rsp+290h+var_250]
0x18001d034  test    eax, eax
0x18001d036  js      loc_18001D0C7
0x18001d03c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d042  mov     rcx, rax; String
0x18001d045  call    cs:__imp__wcsupr
0x18001d04b  lea     rcx, [rbx+8]
0x18001d04f  mov     rax, rbx
0x18001d052  neg     rax
0x18001d055  sbb     rdi, rdi
0x18001d058  xor     edx, edx
0x18001d05a  and     rdi, rcx
0x18001d05d  mov     rcx, rdi
0x18001d060  lea     r8d, [rdx+4]
0x18001d064  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18001d069  test    eax, eax
0x18001d06b  jz      short loc_18001D083
0x18001d06d  lea     rcx, [rsp+290h+var_250]
0x18001d072  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d078  mov     r8, rax; unsigned __int16 *
0x18001d07b  mov     rcx, rdi; struct IHttpTraceContext *
0x18001d07e  call    ?RaiseEvent@FILE_CHANGE_NOTIFICATION@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; IISGeneralEvents::FILE_CHANGE_NOTIFICATION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x18001d083  lea     rcx, [rsp+290h+var_250]
0x18001d088  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d08e  lea     rcx, ??_7FileChangeProvider@@6B@; const FileChangeProvider::`vftable'
0x18001d095  mov     [rsp+290h+var_260], 0
0x18001d09e  mov     [rsp+290h+var_270], rcx
0x18001d0a3  lea     r8, [rsp+290h+var_270]
0x18001d0a8  mov     rcx, rbx
0x18001d0ab  mov     [rsp+290h+var_268], rax
0x18001d0b0  mov     edx, 80h
0x18001d0b5  mov     [rsp+290h+var_258], 0
0x18001d0bd  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x18001d0c2  lea     rcx, [rsp+290h+var_250]
0x18001d0c7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001d0cd  mov     rcx, [rbp+190h+var_10]
0x18001d0d4  xor     rcx, rsp; StackCookie
0x18001d0d7  call    __security_check_cookie
0x18001d0dc  lea     r11, [rsp+290h+var_s0]
0x18001d0e4  mov     rbx, [r11+20h]
0x18001d0e8  mov     rdi, [r11+28h]
0x18001d0ec  mov     rsp, r11
0x18001d0ef  pop     rbp
0x18001d0f0  retn
```

# W3_SERVER::NotifyFileChange(ushort const *)

- ea: `0x18001e970`
- end: `0x18001eacc`
- name: `?NotifyFileChange@W3_SERVER@@UEAAXPEBG@Z`
- size: `348`
- prototype: `void __fastcall(W3_SERVER *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180009030`
- `0x18000ac10`
- `0x18001e970`
- `0x18001f5f0`
- `0x18003773a`
- `0x180037790`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18001ea07`
- `msvcrt!_wcsupr` at `0x18001ea07`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ea9b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ea9b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001e9f8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ea3a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ea56`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001e9f8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ea3a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ea56`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e9df`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e9df`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e9cb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e9cb`

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
0x18001e970  mov     [rsp-8+arg_10], rbx
0x18001e975  mov     [rsp-8+arg_18], rdi
0x18001e97a  push    rbp
0x18001e97b  lea     rbp, [rsp-190h]
0x18001e983  sub     rsp, 290h
0x18001e98a  mov     rax, cs:__security_cookie
0x18001e991  xor     rax, rsp
0x18001e994  mov     [rbp+190h+var_10], rax
0x18001e99b  cmp     dword ptr [rcx+14h], 0
0x18001e99f  mov     rdi, rdx
0x18001e9a2  mov     rbx, rcx
0x18001e9a5  jnz     loc_18001EAA7
0x18001e9ab  xor     edx, edx; Val
0x18001e9ad  lea     rcx, [rbp+190h+var_210]; void *
0x18001e9b1  mov     r8d, 200h; Size
0x18001e9b7  call    memset_0
0x18001e9bc  mov     r8d, 100h
0x18001e9c2  lea     rdx, [rbp+190h+var_210]
0x18001e9c6  lea     rcx, [rsp+290h+var_250]
0x18001e9cb  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001e9d2  nop     dword ptr [rax+rax+00h]
0x18001e9d7  mov     rdx, rdi
0x18001e9da  lea     rcx, [rsp+290h+var_250]
0x18001e9df  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001e9e6  nop     dword ptr [rax+rax+00h]
0x18001e9eb  lea     rcx, [rsp+290h+var_250]
0x18001e9f0  test    eax, eax
0x18001e9f2  js      loc_18001EA9B
0x18001e9f8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001e9ff  nop     dword ptr [rax+rax+00h]
0x18001ea04  mov     rcx, rax; String
0x18001ea07  call    cs:__imp__wcsupr
0x18001ea0e  nop     dword ptr [rax+rax+00h]
0x18001ea13  lea     rcx, [rbx+8]
0x18001ea17  mov     rax, rbx
0x18001ea1a  neg     rax
0x18001ea1d  sbb     rdi, rdi
0x18001ea20  xor     edx, edx
0x18001ea22  and     rdi, rcx
0x18001ea25  mov     rcx, rdi
0x18001ea28  lea     r8d, [rdx+4]
0x18001ea2c  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18001ea31  test    eax, eax
0x18001ea33  jz      short loc_18001EA51
0x18001ea35  lea     rcx, [rsp+290h+var_250]
0x18001ea3a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001ea41  nop     dword ptr [rax+rax+00h]
0x18001ea46  mov     r8, rax; unsigned __int16 *
0x18001ea49  mov     rcx, rdi; struct IHttpTraceContext *
0x18001ea4c  call    ?RaiseEvent@FILE_CHANGE_NOTIFICATION@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; IISGeneralEvents::FILE_CHANGE_NOTIFICATION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x18001ea51  lea     rcx, [rsp+290h+var_250]
0x18001ea56  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001ea5d  nop     dword ptr [rax+rax+00h]
0x18001ea62  lea     rcx, ??_7FileChangeProvider@@6B@; const FileChangeProvider::`vftable'
0x18001ea69  mov     [rsp+290h+var_260], 0
0x18001ea72  mov     [rsp+290h+var_270], rcx
0x18001ea77  lea     r8, [rsp+290h+var_270]
0x18001ea7c  mov     rcx, rbx
0x18001ea7f  mov     [rsp+290h+var_268], rax
0x18001ea84  mov     edx, 80h
0x18001ea89  mov     [rsp+290h+var_258], 0
0x18001ea91  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x18001ea96  lea     rcx, [rsp+290h+var_250]
0x18001ea9b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001eaa2  nop     dword ptr [rax+rax+00h]
0x18001eaa7  mov     rcx, [rbp+190h+var_10]
0x18001eaae  xor     rcx, rsp; StackCookie
0x18001eab1  call    __security_check_cookie
0x18001eab6  lea     r11, [rsp+290h+var_s0]
0x18001eabe  mov     rbx, [r11+20h]
0x18001eac2  mov     rdi, [r11+28h]
0x18001eac6  mov     rsp, r11
0x18001eac9  pop     rbp
0x18001eaca  retn
```

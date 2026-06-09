# W3_CONTEXT::SetScriptMap(IScriptMapInfo *)

- ea: `0x1800227e0`
- end: `0x180022a30`
- name: `?SetScriptMap@W3_CONTEXT@@UEAAXPEAVIScriptMapInfo@@@Z`
- size: `592`
- prototype: `void __fastcall(W3_CONTEXT *__hidden this, struct IScriptMapInfo *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180008930`
- `0x18000dae0`
- `0x180021e00`
- `0x1800227e0`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180022968`
- `msvcrt!_wcsupr` at `0x180022968`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800229ff`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800229ff`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180022984`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180022984`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002295f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180022991`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800229b8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002295f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180022991`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800229b8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002292a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002292a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002294c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002294c`

## pseudocode

```c
void __fastcall W3_CONTEXT::SetScriptMap(W3_CONTEXT *this, struct IScriptMapInfo *a2)
{
  char *v2; // r14
  struct IHttpTraceContext *v5; // rdi
  const unsigned __int16 *v6; // rbp
  const unsigned __int16 *v7; // r15
  const unsigned __int16 *v8; // r12
  __int64 v9; // rax
  const struct _GUID *v10; // rdx
  __int64 v11; // rcx
  const unsigned __int16 *v12; // r13
  const unsigned __int16 *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rbp
  wchar_t *Str; // rax
  const unsigned __int16 *v18; // rdi
  unsigned int CCH; // ebx
  wchar_t *v20; // rax
  const unsigned __int16 *matched; // rdi
  void (__fastcall *v22)(W3_CONTEXT *, const unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *v23; // rax
  _BYTE v24[64]; // [rsp+40h] [rbp-888h] BYREF
  unsigned __int16 v25[1024]; // [rsp+80h] [rbp-848h] BYREF

  v2 = (char *)this - 16;
  if ( *((_BYTE *)this + 9082) )
  {
    v5 = (struct IHttpTraceContext *)(((unsigned __int64)this - 8) & -(__int64)(this != (W3_CONTEXT *)16));
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v5, 0, 4) )
    {
      v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IScriptMapInfo *, _QWORD))(*(_QWORD *)a2 + 32LL))(
                                       a2,
                                       0);
      v7 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IScriptMapInfo *, _QWORD))(*(_QWORD *)a2 + 24LL))(
                                       a2,
                                       0);
      v8 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IScriptMapInfo *, _QWORD))(*(_QWORD *)a2 + 16LL))(
                                       a2,
                                       0);
      v9 = (*(__int64 (__fastcall **)(struct IScriptMapInfo *))(*(_QWORD *)a2 + 80LL))(a2);
      v11 = *((_QWORD *)this + 1126);
      v12 = (const unsigned __int16 *)v9;
      if ( v11 )
        v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 80LL))(v11);
      else
        v13 = &dword_180039134;
      IISGeneralEvents::HANDLER_CHANGED::RaiseEvent(v5, v10, v13, v12, v8, v7, v6);
    }
  }
  v14 = *(_QWORD *)this;
  *((_QWORD *)this + 1126) = a2;
  (*(void (__fastcall **)(W3_CONTEXT *, _QWORD))(v14 + 24))(this, 0);
  if ( !(*(unsigned int (__fastcall **)(struct IScriptMapInfo *))(*(_QWORD *)a2 + 64LL))(a2) )
  {
    memset_0(v25, 0, sizeof(v25));
    STRU::STRU((STRU *)v24, v25, 0x400u);
    v15 = *(_QWORD *)(*((_QWORD *)this + 4) + 40LL);
    v16 = *(const unsigned __int16 **)(v15 + 88);
    if ( (int)STRU::Copy((STRU *)v24, v16, *(unsigned __int16 *)(v15 + 68) >> 1) >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v24);
      _wcsupr(Str);
      v18 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(struct IScriptMapInfo *))a2)(a2);
      CCH = STRU::QueryCCH((STRU *)v24);
      v20 = STRU::QueryStr((STRU *)v24);
      matched = MatchPathInUrl(v20, CCH, v18);
      if ( matched )
      {
        v22 = *(void (__fastcall **)(W3_CONTEXT *, const unsigned __int16 *, _QWORD))(*(_QWORD *)this + 8LL);
        v23 = STRU::QueryStr((STRU *)v24);
        v22(this, v16, (unsigned int)(matched - v23));
        *((_BYTE *)this + 8085) = 0;
        *((_BYTE *)this + 9024) = 1;
      }
    }
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v2 + 376LL))(v2, 24);
    STRU::~STRU((STRU *)v24);
  }
}

```

## disassembly

```asm
0x1800227e0  mov     [rsp+arg_10], rbx
0x1800227e5  push    rbp
0x1800227e6  push    rsi
0x1800227e7  push    rdi
0x1800227e8  push    r12
0x1800227ea  push    r13
0x1800227ec  push    r14
0x1800227ee  push    r15
0x1800227f0  sub     rsp, 890h
0x1800227f7  mov     rax, cs:__security_cookie
0x1800227fe  xor     rax, rsp
0x180022801  mov     [rsp+8C8h+var_48], rax
0x180022809  lea     r14, [rcx-10h]
0x18002280d  mov     rbx, rdx
0x180022810  cmp     byte ptr [r14+238Ah], 0
0x180022818  mov     rsi, rcx
0x18002281b  jz      loc_1800228D3
0x180022821  lea     rdx, [rcx-8]
0x180022825  mov     rax, r14
0x180022828  neg     rax
0x18002282b  sbb     rdi, rdi
0x18002282e  and     rdi, rdx
0x180022831  xor     edx, edx
0x180022833  mov     rcx, rdi
0x180022836  lea     r8d, [rdx+4]
0x18002283a  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18002283f  test    eax, eax
0x180022841  jz      loc_1800228D3
0x180022847  mov     rax, [rbx]
0x18002284a  xor     edx, edx
0x18002284c  mov     rcx, rbx
0x18002284f  mov     rax, [rax+20h]
0x180022853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022858  mov     rcx, [rbx]
0x18002285b  mov     rbp, rax
0x18002285e  xor     edx, edx
0x180022860  mov     rax, [rcx+18h]
0x180022864  mov     rcx, rbx
0x180022867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002286c  mov     rcx, [rbx]
0x18002286f  mov     r15, rax
0x180022872  xor     edx, edx
0x180022874  mov     rax, [rcx+10h]
0x180022878  mov     rcx, rbx
0x18002287b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022880  mov     rcx, [rbx]
0x180022883  mov     r12, rax
0x180022886  mov     rax, [rcx+50h]
0x18002288a  mov     rcx, rbx
0x18002288d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022892  mov     rcx, [rsi+2330h]
0x180022899  mov     r13, rax
0x18002289c  test    rcx, rcx
0x18002289f  jz      short loc_1800228AF
0x1800228a1  mov     rdx, [rcx]
0x1800228a4  mov     rax, [rdx+50h]
0x1800228a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228ad  jmp     short loc_1800228B6
0x1800228af  lea     rax, dword_180039134
0x1800228b6  mov     [rsp+8C8h+var_898], rbp; unsigned __int16 *
0x1800228bb  mov     r9, r13; unsigned __int16 *
0x1800228be  mov     [rsp+8C8h+var_8A0], r15; unsigned __int16 *
0x1800228c3  mov     r8, rax; unsigned __int16 *
0x1800228c6  mov     rcx, rdi; struct IHttpTraceContext *
0x1800228c9  mov     [rsp+8C8h+var_8A8], r12; unsigned __int16 *
0x1800228ce  call    ?RaiseEvent@HANDLER_CHANGED@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2222@Z; IISGeneralEvents::HANDLER_CHANGED::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800228d3  mov     rax, [rsi]
0x1800228d6  xor     edx, edx
0x1800228d8  mov     rcx, rsi
0x1800228db  mov     [rsi+2330h], rbx
0x1800228e2  mov     rax, [rax+18h]
0x1800228e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228eb  mov     rax, [rbx]
0x1800228ee  mov     rcx, rbx
0x1800228f1  mov     rax, [rax+40h]
0x1800228f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228fa  test    eax, eax
0x1800228fc  jnz     loc_180022A05
0x180022902  xor     edx, edx; Val
0x180022904  lea     rcx, [rsp+8C8h+var_848]; void *
0x18002290c  mov     r8d, 800h; Size
0x180022912  call    memset_0
0x180022917  mov     r8d, 400h
0x18002291d  lea     rdx, [rsp+8C8h+var_848]
0x180022925  lea     rcx, [rsp+8C8h+var_888]
0x18002292a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022930  mov     rax, [rsi+20h]
0x180022934  mov     rcx, [rax+28h]
0x180022938  mov     rbp, [rcx+58h]
0x18002293c  movzx   r8d, word ptr [rcx+44h]
0x180022941  mov     rdx, rbp
0x180022944  shr     r8d, 1
0x180022947  lea     rcx, [rsp+8C8h+var_888]
0x18002294c  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180022952  test    eax, eax
0x180022954  js      loc_1800229E3
0x18002295a  lea     rcx, [rsp+8C8h+var_888]
0x18002295f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180022965  mov     rcx, rax; String
0x180022968  call    cs:__imp__wcsupr
0x18002296e  mov     rax, [rbx]
0x180022971  mov     rcx, rbx
0x180022974  mov     rax, [rax]
0x180022977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002297c  lea     rcx, [rsp+8C8h+var_888]
0x180022981  mov     rdi, rax
0x180022984  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002298a  lea     rcx, [rsp+8C8h+var_888]
0x18002298f  mov     ebx, eax
0x180022991  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180022997  mov     r8, rdi; unsigned __int16 *
0x18002299a  mov     edx, ebx; unsigned int
0x18002299c  mov     rcx, rax; String1
0x18002299f  call    ?MatchPathInUrl@@YAPEBGPEBGK0@Z; MatchPathInUrl(ushort const *,ulong,ushort const *)
0x1800229a4  mov     rdi, rax
0x1800229a7  test    rax, rax
0x1800229aa  jz      short loc_1800229E3
0x1800229ac  mov     rcx, [rsi]
0x1800229af  mov     rbx, [rcx+8]
0x1800229b3  lea     rcx, [rsp+8C8h+var_888]
0x1800229b8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800229be  mov     rdx, rbp
0x1800229c1  mov     rcx, rsi
0x1800229c4  sub     rdi, rax
0x1800229c7  mov     rax, rbx
0x1800229ca  sar     rdi, 1
0x1800229cd  mov     r8d, edi
0x1800229d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229d5  mov     byte ptr [rsi+1F95h], 0
0x1800229dc  mov     byte ptr [rsi+2340h], 1
0x1800229e3  mov     rax, [r14]
0x1800229e6  mov     edx, 18h
0x1800229eb  mov     rcx, r14
0x1800229ee  mov     rax, [rax+178h]
0x1800229f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229fa  lea     rcx, [rsp+8C8h+var_888]
0x1800229ff  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022a05  mov     rcx, [rsp+8C8h+var_48]
0x180022a0d  xor     rcx, rsp; StackCookie
0x180022a10  call    __security_check_cookie
0x180022a15  mov     rbx, [rsp+8C8h+arg_10]
0x180022a1d  add     rsp, 890h
0x180022a24  pop     r15
0x180022a26  pop     r14
0x180022a28  pop     r13
0x180022a2a  pop     r12
0x180022a2c  pop     rdi
0x180022a2d  pop     rsi
0x180022a2e  pop     rbp
0x180022a2f  retn
```

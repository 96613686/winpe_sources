# W3_CONTEXT::SetScriptMap(IScriptMapInfo *)

- ea: `0x180024480`
- end: `0x180024701`
- name: `?SetScriptMap@W3_CONTEXT@@UEAAXPEAVIScriptMapInfo@@@Z`
- size: `641`
- prototype: `void __fastcall(W3_CONTEXT *__hidden this, struct IScriptMapInfo *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180009030`
- `0x18000e660`
- `0x180023a7c`
- `0x180024480`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18002461a`
- `msvcrt!_wcsupr` at `0x18002461a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800246c9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800246c9`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002463c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002463c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002460b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002464f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002467c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002460b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002464f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002467c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800245ca`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800245ca`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800245f2`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800245f2`

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
  wchar_t *matched; // rdi
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
        v13 = &dword_18003C134;
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
0x180024480  mov     [rsp+arg_10], rbx
0x180024485  push    rbp
0x180024486  push    rsi
0x180024487  push    rdi
0x180024488  push    r12
0x18002448a  push    r13
0x18002448c  push    r14
0x18002448e  push    r15
0x180024490  sub     rsp, 890h
0x180024497  mov     rax, cs:__security_cookie
0x18002449e  xor     rax, rsp
0x1800244a1  mov     [rsp+8C8h+var_48], rax
0x1800244a9  lea     r14, [rcx-10h]
0x1800244ad  mov     rbx, rdx
0x1800244b0  cmp     byte ptr [r14+238Ah], 0
0x1800244b8  mov     rsi, rcx
0x1800244bb  jz      loc_180024573
0x1800244c1  lea     rdx, [rcx-8]
0x1800244c5  mov     rax, r14
0x1800244c8  neg     rax
0x1800244cb  sbb     rdi, rdi
0x1800244ce  and     rdi, rdx
0x1800244d1  xor     edx, edx
0x1800244d3  mov     rcx, rdi
0x1800244d6  lea     r8d, [rdx+4]
0x1800244da  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800244df  test    eax, eax
0x1800244e1  jz      loc_180024573
0x1800244e7  mov     rax, [rbx]
0x1800244ea  xor     edx, edx
0x1800244ec  mov     rcx, rbx
0x1800244ef  mov     rax, [rax+20h]
0x1800244f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244f8  mov     rcx, [rbx]
0x1800244fb  mov     rbp, rax
0x1800244fe  xor     edx, edx
0x180024500  mov     rax, [rcx+18h]
0x180024504  mov     rcx, rbx
0x180024507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002450c  mov     rcx, [rbx]
0x18002450f  mov     r15, rax
0x180024512  xor     edx, edx
0x180024514  mov     rax, [rcx+10h]
0x180024518  mov     rcx, rbx
0x18002451b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024520  mov     rcx, [rbx]
0x180024523  mov     r12, rax
0x180024526  mov     rax, [rcx+50h]
0x18002452a  mov     rcx, rbx
0x18002452d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024532  mov     rcx, [rsi+2330h]
0x180024539  mov     r13, rax
0x18002453c  test    rcx, rcx
0x18002453f  jz      short loc_18002454F
0x180024541  mov     rdx, [rcx]
0x180024544  mov     rax, [rdx+50h]
0x180024548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002454d  jmp     short loc_180024556
0x18002454f  lea     rax, dword_18003C134
0x180024556  mov     [rsp+8C8h+var_898], rbp; unsigned __int16 *
0x18002455b  mov     r9, r13; unsigned __int16 *
0x18002455e  mov     [rsp+8C8h+var_8A0], r15; unsigned __int16 *
0x180024563  mov     r8, rax; unsigned __int16 *
0x180024566  mov     rcx, rdi; struct IHttpTraceContext *
0x180024569  mov     [rsp+8C8h+var_8A8], r12; unsigned __int16 *
0x18002456e  call    ?RaiseEvent@HANDLER_CHANGED@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2222@Z; IISGeneralEvents::HANDLER_CHANGED::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180024573  mov     rax, [rsi]
0x180024576  xor     edx, edx
0x180024578  mov     rcx, rsi
0x18002457b  mov     [rsi+2330h], rbx
0x180024582  mov     rax, [rax+18h]
0x180024586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002458b  mov     rax, [rbx]
0x18002458e  mov     rcx, rbx
0x180024591  mov     rax, [rax+40h]
0x180024595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002459a  test    eax, eax
0x18002459c  jnz     loc_1800246D5
0x1800245a2  xor     edx, edx; Val
0x1800245a4  lea     rcx, [rsp+8C8h+var_848]; void *
0x1800245ac  mov     r8d, 800h; Size
0x1800245b2  call    memset_0
0x1800245b7  mov     r8d, 400h
0x1800245bd  lea     rdx, [rsp+8C8h+var_848]
0x1800245c5  lea     rcx, [rsp+8C8h+var_888]
0x1800245ca  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800245d1  nop     dword ptr [rax+rax+00h]
0x1800245d6  mov     rax, [rsi+20h]
0x1800245da  mov     rcx, [rax+28h]
0x1800245de  mov     rbp, [rcx+58h]
0x1800245e2  movzx   r8d, word ptr [rcx+44h]
0x1800245e7  mov     rdx, rbp
0x1800245ea  shr     r8d, 1
0x1800245ed  lea     rcx, [rsp+8C8h+var_888]
0x1800245f2  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800245f9  nop     dword ptr [rax+rax+00h]
0x1800245fe  test    eax, eax
0x180024600  js      loc_1800246AD
0x180024606  lea     rcx, [rsp+8C8h+var_888]
0x18002460b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180024612  nop     dword ptr [rax+rax+00h]
0x180024617  mov     rcx, rax; String
0x18002461a  call    cs:__imp__wcsupr
0x180024621  nop     dword ptr [rax+rax+00h]
0x180024626  mov     rax, [rbx]
0x180024629  mov     rcx, rbx
0x18002462c  mov     rax, [rax]
0x18002462f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024634  lea     rcx, [rsp+8C8h+var_888]
0x180024639  mov     rdi, rax
0x18002463c  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180024643  nop     dword ptr [rax+rax+00h]
0x180024648  lea     rcx, [rsp+8C8h+var_888]
0x18002464d  mov     ebx, eax
0x18002464f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180024656  nop     dword ptr [rax+rax+00h]
0x18002465b  mov     r8, rdi; unsigned __int16 *
0x18002465e  mov     edx, ebx; unsigned int
0x180024660  mov     rcx, rax; String1
0x180024663  call    ?MatchPathInUrl@@YAPEBGPEBGK0@Z; MatchPathInUrl(ushort const *,ulong,ushort const *)
0x180024668  mov     rdi, rax
0x18002466b  test    rax, rax
0x18002466e  jz      short loc_1800246AD
0x180024670  mov     rcx, [rsi]
0x180024673  mov     rbx, [rcx+8]
0x180024677  lea     rcx, [rsp+8C8h+var_888]
0x18002467c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180024683  nop     dword ptr [rax+rax+00h]
0x180024688  mov     rdx, rbp
0x18002468b  mov     rcx, rsi
0x18002468e  sub     rdi, rax
0x180024691  mov     rax, rbx
0x180024694  sar     rdi, 1
0x180024697  mov     r8d, edi
0x18002469a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002469f  mov     byte ptr [rsi+1F95h], 0
0x1800246a6  mov     byte ptr [rsi+2340h], 1
0x1800246ad  mov     rax, [r14]
0x1800246b0  mov     edx, 18h
0x1800246b5  mov     rcx, r14
0x1800246b8  mov     rax, [rax+178h]
0x1800246bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246c4  lea     rcx, [rsp+8C8h+var_888]
0x1800246c9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800246d0  nop     dword ptr [rax+rax+00h]
0x1800246d5  mov     rcx, [rsp+8C8h+var_48]
0x1800246dd  xor     rcx, rsp; StackCookie
0x1800246e0  call    __security_check_cookie
0x1800246e5  mov     rbx, [rsp+8C8h+arg_10]
0x1800246ed  add     rsp, 890h
0x1800246f4  pop     r15
0x1800246f6  pop     r14
0x1800246f8  pop     r13
0x1800246fa  pop     r12
0x1800246fc  pop     rdi
0x1800246fd  pop     rsi
0x1800246fe  pop     rbp
0x1800246ff  retn
```

# HTTP_LOG_HANDLER::GetCustomLogString(IHttpContext *,LOGGING *,STRA *)

- ea: `0x180003318`
- end: `0x180003508`
- name: `?GetCustomLogString@HTTP_LOG_HANDLER@@QEAAJPEAVIHttpContext@@PEAVLOGGING@@PEAVSTRA@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(HTTP_LOG_HANDLER *__hidden this, struct IHttpContext *, struct LOGGING *, struct STRA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001080`

## callees

- `0x180003318`
- `0x180005720`
- `0x180006010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x1800034d9`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800034d9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003364`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003364`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800033c6`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003458`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800033c6`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003458`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800033a1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800033a1`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x18000338a`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x1800034ce`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x18000338a`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x1800034ce`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x1800033af`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x1800033af`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x1800034b1`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x1800034b1`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800033d2`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800033ec`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000348c`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800034a2`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800033d2`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800033ec`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000348c`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800034a2`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_HANDLER::GetCustomLogString(
        HTTP_LOG_HANDLER *this,
        struct IHttpContext *a2,
        struct LOGGING *a3,
        struct STRA *a4)
{
  int v6; // ebx
  __int64 v8; // r15
  unsigned int i; // r14d
  __int64 v10; // rdi
  const unsigned __int16 *Str; // rax
  const char *v12; // rax
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // rax
  __int64 (__fastcall *v16)(__int64, char *, __int16 *); // rbx
  __int64 v17; // rdi
  char *v18; // rax
  __int64 v19; // rax
  const char *v20; // rdx
  __int16 v22; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v23[56]; // [rsp+28h] [rbp-D8h] BYREF
  char v24[256]; // [rsp+60h] [rbp-A0h] BYREF

  v22 = 0;
  v6 = 0;
  STRA::STRA((STRA *)v23, v24, 0xF5u);
  if ( *((_DWORD *)a3 + 28) )
  {
    v8 = *((_QWORD *)a3 + 13);
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_DWORD *)a3 + 28) )
        goto LABEL_22;
      STRA::Reset((STRA *)v23);
      v10 = 176LL * i;
      Str = STRU::QueryStr((STRU *)(v10 + v8 + 112));
      v6 = STRA::AppendW((STRA *)v23, Str);
      if ( v6 < 0 )
        goto LABEL_21;
      v12 = STRA::QueryStr((STRA *)(v10 + v8 + 56));
      v6 = STRA::Append(a4, v12);
      if ( v6 < 0 )
        goto LABEL_21;
      v6 = STRA::Append(a4, "\n");
      if ( v6 < 0 )
        goto LABEL_21;
      v13 = *(_DWORD *)(v10 + v8 + 168);
      if ( !v13 )
        break;
      v14 = v13 - 1;
      if ( !v14 )
      {
        v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
        v16 = *(__int64 (__fastcall **)(__int64, char *, __int16 *))(*(_QWORD *)v15 + 72LL);
LABEL_13:
        v17 = v15;
        v18 = STRA::QueryStr((STRA *)v23);
        v19 = v16(v17, v18, &v22);
        if ( !v19 || (v20 = (const char *)v19, !v22) )
          v20 = "-";
        v6 = STRA::Append(a4, v20);
        if ( v6 < 0 )
          goto LABEL_21;
        v6 = STRA::Append(a4, "\n");
        if ( v6 < 0 )
          goto LABEL_21;
        goto LABEL_18;
      }
      if ( v14 == 1 )
      {
        v6 = -2147024809;
LABEL_21:
        STRA::Reset(a4);
        goto LABEL_22;
      }
LABEL_18:
      if ( STRA::QueryCB(a4) > 0xF4 )
      {
        v6 = -2147024621;
        goto LABEL_21;
      }
    }
    v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v16 = *(__int64 (__fastcall **)(__int64, char *, __int16 *))(*(_QWORD *)v15 + 24LL);
    goto LABEL_13;
  }
LABEL_22:
  STRA::~STRA((STRA *)v23);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003318  mov     [rsp-8+arg_0], rbx
0x18000331d  push    rbp
0x18000331e  push    rsi
0x18000331f  push    rdi
0x180003320  push    r12
0x180003322  push    r13
0x180003324  push    r14
0x180003326  push    r15
0x180003328  lea     rbp, [rsp-70h]
0x18000332d  sub     rsp, 170h
0x180003334  mov     rax, cs:__security_cookie
0x18000333b  xor     rax, rsp
0x18000333e  mov     [rbp+0A0h+var_40], rax
0x180003342  mov     r13, r8
0x180003345  lea     rcx, [rsp+1A0h+var_178]
0x18000334a  mov     r12, rdx
0x18000334d  xor     edi, edi
0x18000334f  mov     r8d, 0F5h
0x180003355  mov     [rsp+1A0h+var_180], di
0x18000335a  lea     rdx, [rsp+1A0h+var_140]
0x18000335f  mov     ebx, edi
0x180003361  mov     rsi, r9
0x180003364  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000336a  cmp     [r13+70h], edi
0x18000336e  jz      loc_1800034D4
0x180003374  mov     r15, [r13+68h]
0x180003378  mov     r14d, edi
0x18000337b  cmp     r14d, [r13+70h]
0x18000337f  jnb     loc_1800034D4
0x180003385  lea     rcx, [rsp+1A0h+var_178]
0x18000338a  call    cs:__imp_?Reset@STRA@@QEAAXXZ; STRA::Reset(void)
0x180003390  mov     eax, r14d
0x180003393  lea     rcx, [r15+70h]
0x180003397  imul    rdi, rax, 0B0h
0x18000339e  add     rcx, rdi
0x1800033a1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800033a7  mov     rdx, rax
0x1800033aa  lea     rcx, [rsp+1A0h+var_178]
0x1800033af  call    cs:__imp_?AppendW@STRA@@QEAAJPEBG@Z; STRA::AppendW(ushort const *)
0x1800033b5  mov     ebx, eax
0x1800033b7  test    eax, eax
0x1800033b9  js      loc_1800034CB
0x1800033bf  lea     rcx, [r15+38h]
0x1800033c3  add     rcx, rdi
0x1800033c6  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800033cc  mov     rdx, rax
0x1800033cf  mov     rcx, rsi
0x1800033d2  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800033d8  mov     ebx, eax
0x1800033da  test    eax, eax
0x1800033dc  js      loc_1800034CB
0x1800033e2  lea     rdx, asc_180007E34; "\n"
0x1800033e9  mov     rcx, rsi
0x1800033ec  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800033f2  mov     ebx, eax
0x1800033f4  test    eax, eax
0x1800033f6  js      loc_1800034CB
0x1800033fc  mov     ecx, [rdi+r15+0A8h]
0x180003404  test    ecx, ecx
0x180003406  jz      short loc_180003439
0x180003408  sub     ecx, 1
0x18000340b  jz      short loc_180003420
0x18000340d  cmp     ecx, 1
0x180003410  jnz     loc_1800034AE
0x180003416  mov     ebx, 80070057h
0x18000341b  jmp     loc_1800034CB
0x180003420  mov     rax, [r12]
0x180003424  mov     rcx, r12
0x180003427  mov     rax, [rax+20h]
0x18000342b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003430  mov     rcx, [rax]
0x180003433  mov     rbx, [rcx+48h]
0x180003437  jmp     short loc_180003450
0x180003439  mov     rax, [r12]
0x18000343d  mov     rcx, r12
0x180003440  mov     rax, [rax+18h]
0x180003444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003449  mov     rcx, [rax]
0x18000344c  mov     rbx, [rcx+18h]
0x180003450  lea     rcx, [rsp+1A0h+var_178]
0x180003455  mov     rdi, rax
0x180003458  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000345e  lea     r8, [rsp+1A0h+var_180]
0x180003463  mov     rcx, rdi
0x180003466  mov     rdx, rax
0x180003469  mov     rax, rbx
0x18000346c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003471  xor     edi, edi
0x180003473  test    rax, rax
0x180003476  jz      short loc_180003482
0x180003478  mov     rdx, rax
0x18000347b  cmp     [rsp+1A0h+var_180], di
0x180003480  jnz     short loc_180003489
0x180003482  lea     rdx, asc_180007E38; "-"
0x180003489  mov     rcx, rsi
0x18000348c  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003492  mov     ebx, eax
0x180003494  test    eax, eax
0x180003496  js      short loc_1800034CB
0x180003498  lea     rdx, asc_180007E34; "\n"
0x18000349f  mov     rcx, rsi
0x1800034a2  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800034a8  mov     ebx, eax
0x1800034aa  test    eax, eax
0x1800034ac  js      short loc_1800034CB
0x1800034ae  mov     rcx, rsi
0x1800034b1  call    cs:__imp_?QueryCB@STRA@@QEBAKXZ; STRA::QueryCB(void)
0x1800034b7  cmp     eax, 0F4h
0x1800034bc  ja      short loc_1800034C6
0x1800034be  inc     r14d
0x1800034c1  jmp     loc_18000337B
0x1800034c6  mov     ebx, 80070113h
0x1800034cb  mov     rcx, rsi
0x1800034ce  call    cs:__imp_?Reset@STRA@@QEAAXXZ; STRA::Reset(void)
0x1800034d4  lea     rcx, [rsp+1A0h+var_178]
0x1800034d9  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800034df  mov     eax, ebx
0x1800034e1  mov     rcx, [rbp+0A0h+var_40]
0x1800034e5  xor     rcx, rsp; StackCookie
0x1800034e8  call    __security_check_cookie
0x1800034ed  mov     rbx, [rsp+1A0h+arg_0]
0x1800034f5  add     rsp, 170h
0x1800034fc  pop     r15
0x1800034fe  pop     r14
0x180003500  pop     r13
0x180003502  pop     r12
0x180003504  pop     rdi
0x180003505  pop     rsi
0x180003506  pop     rbp
0x180003507  retn
```

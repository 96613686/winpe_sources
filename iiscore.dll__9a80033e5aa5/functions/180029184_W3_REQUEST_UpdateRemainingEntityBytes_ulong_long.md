# W3_REQUEST::UpdateRemainingEntityBytes(ulong,long)

- ea: `0x180029184`
- end: `0x1800292d0`
- name: `?UpdateRemainingEntityBytes@W3_REQUEST@@QEAAXKJ@Z`
- size: `332`
- prototype: `void(W3_REQUEST *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x1800018d0`
- `0x180027770`

## callees

- `0x180008930`
- `0x180021a10`
- `0x180027c44`
- `0x180029184`
- `0x1800343f0`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180029268`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180029268`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180029244`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180029244`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180029235`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180029235`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180029220`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180029220`

## pseudocode

```c
void __fastcall W3_REQUEST::UpdateRemainingEntityBytes(W3_REQUEST *this, unsigned int a2, signed int a3)
{
  __int64 v5; // rcx
  _DWORD *v7; // rbx
  const char *Str; // rax
  unsigned int *v9; // rax
  int v10; // edx
  unsigned int v11; // ecx
  _BYTE v12[56]; // [rsp+20h] [rbp-58h] BYREF

  v5 = *((_QWORD *)this + 14);
  v7 = *(_DWORD **)(v5 + 392);
  if ( *(_BYTE *)(v5 + 9098) )
  {
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled((v5 + 8) & -(__int64)(v5 != 0), 0, 4) )
      IISGeneralEvents::GENERAL_READ_ENTITY_END::RaiseEvent(
        (struct IHttpTraceContext *)((*((_QWORD *)this + 14) + 8LL) & -(__int64)(*((_QWORD *)this + 14) != 0)),
        (const struct _GUID *)(*((_QWORD *)this + 14) + 8LL),
        a2,
        a3);
    if ( a3 >= 0
      && (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(
                         (*((_QWORD *)this + 14) + 8LL) & -(__int64)(*((_QWORD *)this + 14) != 0),
                         0,
                         5) )
    {
      STRA::STRA((STRA *)v12);
      if ( (int)STRA::Copy((STRA *)v12, *((const char **)this + 33), a2) >= 0 )
      {
        Str = STRA::QueryStr((STRA *)v12);
        IISGeneralEvents::GENERAL_REQUEST_ENTITY::RaiseEvent(
          (struct IHttpTraceContext *)((*((_QWORD *)this + 14) + 8LL) & -(__int64)(*((_QWORD *)this + 14) != 0)),
          (const struct _GUID *)(*((_QWORD *)this + 14) + 8LL),
          Str);
      }
      STRA::~STRA((STRA *)v12);
    }
  }
  *((_QWORD *)this + 33) = 0;
  v9 = v7 + 2362;
  v10 = v7[2363];
  if ( a3 == -2147024858 )
    goto LABEL_14;
  v11 = *v9;
  if ( a3 >= 0 )
  {
    v10 += a2;
    if ( v11 != -1 )
    {
      if ( v11 >= a2 )
      {
        v11 -= a2;
        goto LABEL_15;
      }
LABEL_14:
      v11 = 0;
    }
  }
LABEL_15:
  v7[2373] += a2;
  *v9 = v11;
  v7[2363] = v10;
}

```

## disassembly

```asm
0x180029184  mov     [rsp+arg_18], rbx
0x180029189  push    rbp
0x18002918a  push    rsi
0x18002918b  push    rdi
0x18002918c  sub     rsp, 60h
0x180029190  mov     rax, cs:__security_cookie
0x180029197  xor     rax, rsp
0x18002919a  mov     [rsp+78h+var_20], rax
0x18002919f  mov     rsi, rcx
0x1800291a2  mov     ebp, r8d
0x1800291a5  mov     rcx, [rcx+70h]
0x1800291a9  mov     edi, edx
0x1800291ab  cmp     byte ptr [rcx+238Ah], 0
0x1800291b2  mov     rbx, [rcx+188h]
0x1800291b9  jz      loc_18002926E
0x1800291bf  lea     rax, [rcx+8]
0x1800291c3  neg     rcx
0x1800291c6  sbb     rcx, rcx
0x1800291c9  xor     edx, edx
0x1800291cb  and     rcx, rax
0x1800291ce  lea     r8d, [rdx+4]
0x1800291d2  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800291d7  test    eax, eax
0x1800291d9  jz      short loc_1800291F7
0x1800291db  mov     rax, [rsi+70h]
0x1800291df  mov     r9d, ebp; unsigned int
0x1800291e2  mov     r8d, edi; unsigned int
0x1800291e5  lea     rdx, [rax+8]; struct _GUID *
0x1800291e9  neg     rax
0x1800291ec  sbb     rcx, rcx
0x1800291ef  and     rcx, rdx; struct IHttpTraceContext *
0x1800291f2  call    ?RaiseEvent@GENERAL_READ_ENTITY_END@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KK@Z; IISGeneralEvents::GENERAL_READ_ENTITY_END::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ulong)
0x1800291f7  test    ebp, ebp
0x1800291f9  js      short loc_18002926E
0x1800291fb  mov     rcx, [rsi+70h]
0x1800291ff  lea     rax, [rcx+8]
0x180029203  neg     rcx
0x180029206  sbb     rcx, rcx
0x180029209  xor     edx, edx
0x18002920b  and     rcx, rax
0x18002920e  lea     r8d, [rdx+5]
0x180029212  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180029217  test    eax, eax
0x180029219  jz      short loc_18002926E
0x18002921b  lea     rcx, [rsp+78h+var_58]
0x180029220  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180029226  mov     rdx, [rsi+108h]
0x18002922d  lea     rcx, [rsp+78h+var_58]
0x180029232  mov     r8d, edi
0x180029235  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18002923b  test    eax, eax
0x18002923d  js      short loc_180029263
0x18002923f  lea     rcx, [rsp+78h+var_58]
0x180029244  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002924a  mov     rcx, [rsi+70h]
0x18002924e  mov     r8, rax; char *
0x180029251  lea     rdx, [rcx+8]; struct _GUID *
0x180029255  neg     rcx
0x180029258  sbb     rcx, rcx
0x18002925b  and     rcx, rdx; struct IHttpTraceContext *
0x18002925e  call    ?RaiseEvent@GENERAL_REQUEST_ENTITY@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD@Z; IISGeneralEvents::GENERAL_REQUEST_ENTITY::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *)
0x180029263  lea     rcx, [rsp+78h+var_58]
0x180029268  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002926e  mov     qword ptr [rsi+108h], 0
0x180029279  lea     rax, [rbx+24E8h]
0x180029280  mov     edx, [rbx+24ECh]
0x180029286  cmp     ebp, 80070026h
0x18002928c  jz      short loc_1800292A3
0x18002928e  mov     ecx, [rax]
0x180029290  test    ebp, ebp
0x180029292  js      short loc_1800292A5
0x180029294  add     edx, edi
0x180029296  cmp     ecx, 0FFFFFFFFh
0x180029299  jz      short loc_1800292A5
0x18002929b  cmp     ecx, edi
0x18002929d  jb      short loc_1800292A3
0x18002929f  sub     ecx, edi
0x1800292a1  jmp     short loc_1800292A5
0x1800292a3  xor     ecx, ecx
0x1800292a5  add     [rbx+2514h], edi
0x1800292ab  mov     [rax], ecx
0x1800292ad  mov     [rbx+24ECh], edx
0x1800292b3  mov     rcx, [rsp+78h+var_20]
0x1800292b8  xor     rcx, rsp; StackCookie
0x1800292bb  call    __security_check_cookie
0x1800292c0  mov     rbx, [rsp+78h+arg_18]
0x1800292c8  add     rsp, 60h
0x1800292cc  pop     rdi
0x1800292cd  pop     rsi
0x1800292ce  pop     rbp
0x1800292cf  retn
```

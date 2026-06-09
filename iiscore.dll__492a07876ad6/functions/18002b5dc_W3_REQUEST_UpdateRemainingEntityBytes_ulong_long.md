# W3_REQUEST::UpdateRemainingEntityBytes(ulong,long)

- ea: `0x18002b5dc`
- end: `0x18002b745`
- name: `?UpdateRemainingEntityBytes@W3_REQUEST@@QEAAXKJ@Z`
- size: `361`
- prototype: `void(W3_REQUEST *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180001950`
- `0x180029930`

## callees

- `0x180009030`
- `0x18002368c`
- `0x180029e2c`
- `0x18002b5dc`
- `0x180037790`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b6d6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b6d6`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002b6ac`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002b6ac`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002b697`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002b697`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002b67c`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002b67c`

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
0x18002b5dc  mov     [rsp+arg_18], rbx
0x18002b5e1  push    rbp
0x18002b5e2  push    rsi
0x18002b5e3  push    rdi
0x18002b5e4  sub     rsp, 60h
0x18002b5e8  mov     rax, cs:__security_cookie
0x18002b5ef  xor     rax, rsp
0x18002b5f2  mov     [rsp+78h+var_20], rax
0x18002b5f7  mov     rsi, rcx
0x18002b5fa  mov     ebp, r8d
0x18002b5fd  mov     rcx, [rcx+70h]
0x18002b601  mov     edi, edx
0x18002b603  cmp     byte ptr [rcx+238Ah], 0
0x18002b60a  mov     rbx, [rcx+188h]
0x18002b611  jz      loc_18002B6E2
0x18002b617  lea     rax, [rcx+8]
0x18002b61b  neg     rcx
0x18002b61e  sbb     rcx, rcx
0x18002b621  xor     edx, edx
0x18002b623  and     rcx, rax
0x18002b626  lea     r8d, [rdx+4]
0x18002b62a  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18002b62f  test    eax, eax
0x18002b631  jz      short loc_18002B64F
0x18002b633  mov     rax, [rsi+70h]
0x18002b637  mov     r9d, ebp; unsigned int
0x18002b63a  mov     r8d, edi; unsigned int
0x18002b63d  lea     rdx, [rax+8]; struct _GUID *
0x18002b641  neg     rax
0x18002b644  sbb     rcx, rcx
0x18002b647  and     rcx, rdx; struct IHttpTraceContext *
0x18002b64a  call    ?RaiseEvent@GENERAL_READ_ENTITY_END@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KK@Z; IISGeneralEvents::GENERAL_READ_ENTITY_END::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ulong)
0x18002b64f  test    ebp, ebp
0x18002b651  js      loc_18002B6E2
0x18002b657  mov     rcx, [rsi+70h]
0x18002b65b  lea     rax, [rcx+8]
0x18002b65f  neg     rcx
0x18002b662  sbb     rcx, rcx
0x18002b665  xor     edx, edx
0x18002b667  and     rcx, rax
0x18002b66a  lea     r8d, [rdx+5]
0x18002b66e  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18002b673  test    eax, eax
0x18002b675  jz      short loc_18002B6E2
0x18002b677  lea     rcx, [rsp+78h+var_58]
0x18002b67c  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18002b683  nop     dword ptr [rax+rax+00h]
0x18002b688  mov     rdx, [rsi+108h]
0x18002b68f  lea     rcx, [rsp+78h+var_58]
0x18002b694  mov     r8d, edi
0x18002b697  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18002b69e  nop     dword ptr [rax+rax+00h]
0x18002b6a3  test    eax, eax
0x18002b6a5  js      short loc_18002B6D1
0x18002b6a7  lea     rcx, [rsp+78h+var_58]
0x18002b6ac  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002b6b3  nop     dword ptr [rax+rax+00h]
0x18002b6b8  mov     rcx, [rsi+70h]
0x18002b6bc  mov     r8, rax; char *
0x18002b6bf  lea     rdx, [rcx+8]; struct _GUID *
0x18002b6c3  neg     rcx
0x18002b6c6  sbb     rcx, rcx
0x18002b6c9  and     rcx, rdx; struct IHttpTraceContext *
0x18002b6cc  call    ?RaiseEvent@GENERAL_REQUEST_ENTITY@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD@Z; IISGeneralEvents::GENERAL_REQUEST_ENTITY::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *)
0x18002b6d1  lea     rcx, [rsp+78h+var_58]
0x18002b6d6  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002b6dd  nop     dword ptr [rax+rax+00h]
0x18002b6e2  mov     qword ptr [rsi+108h], 0
0x18002b6ed  lea     rax, [rbx+24E8h]
0x18002b6f4  mov     edx, [rbx+24ECh]
0x18002b6fa  cmp     ebp, 80070026h
0x18002b700  jz      short loc_18002B717
0x18002b702  mov     ecx, [rax]
0x18002b704  test    ebp, ebp
0x18002b706  js      short loc_18002B719
0x18002b708  add     edx, edi
0x18002b70a  cmp     ecx, 0FFFFFFFFh
0x18002b70d  jz      short loc_18002B719
0x18002b70f  cmp     ecx, edi
0x18002b711  jb      short loc_18002B717
0x18002b713  sub     ecx, edi
0x18002b715  jmp     short loc_18002B719
0x18002b717  xor     ecx, ecx
0x18002b719  add     [rbx+2514h], edi
0x18002b71f  mov     [rax], ecx
0x18002b721  mov     [rbx+24ECh], edx
0x18002b727  mov     rcx, [rsp+78h+var_20]
0x18002b72c  xor     rcx, rsp; StackCookie
0x18002b72f  call    __security_check_cookie
0x18002b734  mov     rbx, [rsp+78h+arg_18]
0x18002b73c  add     rsp, 60h
0x18002b740  pop     rdi
0x18002b741  pop     rsi
0x18002b742  pop     rbp
0x18002b743  retn
```

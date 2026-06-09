# W3_REQUEST::SetUrl(ushort const *,ulong,int)

- ea: `0x180028f38`
- end: `0x18002917c`
- name: `?SetUrl@W3_REQUEST@@QEAAJPEBGKH@Z`
- size: `580`
- prototype: `__int64 __fastcall(W3_REQUEST *__hidden this, const unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180022e60`

## callees

- `0x180008930`
- `0x180027f80`
- `0x1800289f8`
- `0x180028f38`
- `0x1800343f0`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180029005`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180029005`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029048`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029048`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180028fdf`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180028fdf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180028ff7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029021`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180028ff7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029021`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180029016`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180029058`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180029016`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180029058`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180028f86`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800290c8`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180028f86`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800290c8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180029107`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002913d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180029174`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180029107`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002913d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180029174`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002911f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002911f`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800290f6`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800290f6`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x180029112`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x180029112`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBGK@Z` at `0x1800290a4`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBGK@Z` at `0x1800290a4`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x1800290dc`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x1800290dc`

## pseudocode

```c
__int64 __fastcall W3_REQUEST::SetUrl(W3_REQUEST *this, const unsigned __int16 *a2, unsigned int a3, int a4)
{
  __int64 v4; // rbx
  int v8; // ebx
  __int64 v9; // rcx
  const unsigned __int16 *Str; // rdi
  const unsigned __int16 *v11; // rax
  const struct _GUID *v12; // rdx
  int v13; // eax
  __int64 v14; // rax
  const unsigned __int16 *i; // rdi
  __int64 v16; // rsi
  unsigned int v17; // r12d
  unsigned int CB; // ebx
  const char *v19; // rax
  _BYTE v21[56]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v22[56]; // [rsp+58h] [rbp-A8h] BYREF
  char v23[256]; // [rsp+90h] [rbp-70h] BYREF
  char v24[272]; // [rsp+190h] [rbp+90h] BYREF

  v4 = a3;
  STRA::STRA((STRA *)v22, v24, 0x104u);
  if ( !a2 )
  {
    v8 = -2147024809;
    goto LABEL_27;
  }
  if ( (_DWORD)v4 && *a2 != 47 )
  {
    v9 = *((_QWORD *)this + 14);
    if ( *(_BYTE *)(v9 + 9098)
      && (unsigned int)WWWServerTraceProvider::CheckTracingEnabled((v9 + 8) & -(__int64)(v9 != 0), 0, 4) )
    {
      if ( STRU::IsEmpty((W3_REQUEST *)((char *)this + 56)) )
        Str = *(const unsigned __int16 **)(*((_QWORD *)this + 5) + 88LL);
      else
        Str = STRU::QueryStr((W3_REQUEST *)((char *)this + 56));
      STRU::STRU((STRU *)v21);
      STRU::Copy((STRU *)v21, a2, v4);
      v11 = STRU::QueryStr((STRU *)v21);
      IISGeneralEvents::URL_CHANGED::RaiseEvent(
        (struct IHttpTraceContext *)((*((_QWORD *)this + 14) + 8LL) & -(__int64)(*((_QWORD *)this + 14) != 0)),
        v12,
        Str,
        v11);
      STRU::~STRU((STRU *)v21);
    }
    v13 = STRU::Copy((W3_REQUEST *)((char *)this + 56), a2, v4);
LABEL_26:
    v8 = v13;
    goto LABEL_27;
  }
  v14 = v4;
  for ( i = a2; ; ++i )
  {
    if ( !v14 )
    {
      i = 0;
      goto LABEL_19;
    }
    if ( *i == 63 )
      break;
    --v14;
  }
  if ( i )
  {
    v16 = i - a2;
    v17 = v4 - v16;
    goto LABEL_20;
  }
LABEL_19:
  v17 = 0;
  LODWORD(v16) = v4;
LABEL_20:
  v8 = STRA::CopyWToUTF8Escaped((STRA *)v22, a2, v16);
  if ( v8 >= 0 )
  {
    if ( i )
    {
      STRA::STRA((STRA *)v21, v23, 0x100u);
      v8 = STRA::CopyWToUTF8Unescaped((STRA *)v21, &a2[(unsigned int)v16], v17);
      if ( v8 < 0 || (v8 = STRA::Append((STRA *)v22, (const struct STRA *)v21), v8 < 0) )
      {
        STRA::~STRA((STRA *)v21);
        goto LABEL_27;
      }
      STRA::~STRA((STRA *)v21);
    }
    CB = STRA::QueryCB((STRA *)v22);
    v19 = STRA::QueryStr((STRA *)v22);
    v13 = W3_REQUEST::SetUrl(this, v19, CB, a4);
    goto LABEL_26;
  }
LABEL_27:
  STRA::~STRA((STRA *)v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180028f38  mov     [rsp-8+arg_18], rbx
0x180028f3d  push    rbp
0x180028f3e  push    rsi
0x180028f3f  push    rdi
0x180028f40  push    r12
0x180028f42  push    r13
0x180028f44  push    r14
0x180028f46  push    r15
0x180028f48  lea     rbp, [rsp-1B0h]
0x180028f50  sub     rsp, 2B0h
0x180028f57  mov     rax, cs:__security_cookie
0x180028f5e  xor     rax, rsp
0x180028f61  mov     [rbp+1E0h+var_40], rax
0x180028f68  mov     ebx, r8d
0x180028f6b  mov     r14, rdx
0x180028f6e  mov     r15, rcx
0x180028f71  lea     rdx, [rbp+1E0h+var_150]
0x180028f78  mov     r8d, 104h
0x180028f7e  lea     rcx, [rsp+2E0h+var_288]
0x180028f83  mov     r13d, r9d
0x180028f86  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180028f8c  test    r14, r14
0x180028f8f  jnz     short loc_180028F9B
0x180028f91  mov     ebx, 80070057h
0x180028f96  jmp     loc_180029138
0x180028f9b  test    ebx, ebx
0x180028f9d  jz      loc_180029063
0x180028fa3  cmp     word ptr [r14], 2Fh ; '/'
0x180028fa8  jz      loc_180029063
0x180028fae  mov     rcx, [r15+70h]
0x180028fb2  cmp     byte ptr [rcx+238Ah], 0
0x180028fb9  jz      loc_18002904E
0x180028fbf  lea     rax, [rcx+8]
0x180028fc3  neg     rcx
0x180028fc6  sbb     rcx, rcx
0x180028fc9  xor     edx, edx
0x180028fcb  and     rcx, rax
0x180028fce  lea     r8d, [rdx+4]
0x180028fd2  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180028fd7  test    eax, eax
0x180028fd9  jz      short loc_18002904E
0x180028fdb  lea     rcx, [r15+38h]
0x180028fdf  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180028fe5  test    al, al
0x180028fe7  jz      short loc_180028FF3
0x180028fe9  mov     rax, [r15+28h]
0x180028fed  mov     rdi, [rax+58h]
0x180028ff1  jmp     short loc_180029000
0x180028ff3  lea     rcx, [r15+38h]
0x180028ff7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180028ffd  mov     rdi, rax
0x180029000  lea     rcx, [rsp+2E0h+var_2C0]
0x180029005  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002900b  mov     r8d, ebx
0x18002900e  lea     rcx, [rsp+2E0h+var_2C0]
0x180029013  mov     rdx, r14
0x180029016  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002901c  lea     rcx, [rsp+2E0h+var_2C0]
0x180029021  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180029027  mov     rcx, [r15+70h]
0x18002902b  mov     r8, rdi; unsigned __int16 *
0x18002902e  lea     r9, [rcx+8]
0x180029032  neg     rcx
0x180029035  sbb     rcx, rcx
0x180029038  and     rcx, r9; struct IHttpTraceContext *
0x18002903b  mov     r9, rax; unsigned __int16 *
0x18002903e  call    ?RaiseEvent@URL_CHANGED@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2@Z; IISGeneralEvents::URL_CHANGED::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *)
0x180029043  lea     rcx, [rsp+2E0h+var_2C0]
0x180029048  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002904e  lea     rcx, [r15+38h]
0x180029052  mov     r8d, ebx
0x180029055  mov     rdx, r14
0x180029058  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002905e  jmp     loc_180029136
0x180029063  mov     rax, rbx
0x180029066  mov     rdi, r14
0x180029069  test    rax, rax
0x18002906c  jz      short loc_180029092
0x18002906e  cmp     word ptr [rdi], 3Fh ; '?'
0x180029072  jz      short loc_18002907D
0x180029074  add     rdi, 2
0x180029078  dec     rax
0x18002907b  jmp     short loc_180029069
0x18002907d  test    rdi, rdi
0x180029080  jz      short loc_180029094
0x180029082  mov     rsi, rdi
0x180029085  sub     rsi, r14
0x180029088  sar     rsi, 1
0x18002908b  sub     ebx, esi
0x18002908d  mov     r12d, ebx
0x180029090  jmp     short loc_180029099
0x180029092  xor     edi, edi
0x180029094  xor     r12d, r12d
0x180029097  mov     esi, ebx
0x180029099  mov     r8d, esi
0x18002909c  lea     rcx, [rsp+2E0h+var_288]
0x1800290a1  mov     rdx, r14
0x1800290a4  call    cs:__imp_?CopyWToUTF8Escaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Escaped(ushort const *,ulong)
0x1800290aa  mov     ebx, eax
0x1800290ac  test    eax, eax
0x1800290ae  js      loc_180029138
0x1800290b4  test    rdi, rdi
0x1800290b7  jz      short loc_18002910D
0x1800290b9  mov     r8d, 100h
0x1800290bf  lea     rdx, [rbp+1E0h+var_250]
0x1800290c3  lea     rcx, [rsp+2E0h+var_2C0]
0x1800290c8  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800290ce  mov     eax, esi
0x1800290d0  lea     rcx, [rsp+2E0h+var_2C0]
0x1800290d5  mov     r8d, r12d
0x1800290d8  lea     rdx, [r14+rax*2]
0x1800290dc  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Unescaped(ushort const *,ulong)
0x1800290e2  mov     ebx, eax
0x1800290e4  test    eax, eax
0x1800290e6  js      loc_18002916F
0x1800290ec  lea     rdx, [rsp+2E0h+var_2C0]
0x1800290f1  lea     rcx, [rsp+2E0h+var_288]
0x1800290f6  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x1800290fc  mov     ebx, eax
0x1800290fe  test    eax, eax
0x180029100  js      short loc_18002916F
0x180029102  lea     rcx, [rsp+2E0h+var_2C0]
0x180029107  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002910d  lea     rcx, [rsp+2E0h+var_288]
0x180029112  call    cs:__imp_?QueryCB@STRA@@QEBAKXZ; STRA::QueryCB(void)
0x180029118  lea     rcx, [rsp+2E0h+var_288]
0x18002911d  mov     ebx, eax
0x18002911f  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180029125  mov     r9d, r13d; int
0x180029128  mov     r8d, ebx; unsigned int
0x18002912b  mov     rdx, rax; char *
0x18002912e  mov     rcx, r15; this
0x180029131  call    ?SetUrl@W3_REQUEST@@QEAAJPEBDKH@Z; W3_REQUEST::SetUrl(char const *,ulong,int)
0x180029136  mov     ebx, eax
0x180029138  lea     rcx, [rsp+2E0h+var_288]
0x18002913d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180029143  mov     eax, ebx
0x180029145  mov     rcx, [rbp+1E0h+var_40]
0x18002914c  xor     rcx, rsp; StackCookie
0x18002914f  call    __security_check_cookie
0x180029154  mov     rbx, [rsp+2E0h+arg_18]
0x18002915c  add     rsp, 2B0h
0x180029163  pop     r15
0x180029165  pop     r14
0x180029167  pop     r13
0x180029169  pop     r12
0x18002916b  pop     rdi
0x18002916c  pop     rsi
0x18002916d  pop     rbp
0x18002916e  retn
0x18002916f  lea     rcx, [rsp+2E0h+var_2C0]
0x180029174  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002917a  jmp     short loc_180029138
```

# W3_REQUEST::SetUrl(ushort const *,ulong,int)

- ea: `0x18002b320`
- end: `0x18002b5d3`
- name: `?SetUrl@W3_REQUEST@@QEAAJPEBGKH@Z`
- size: `691`
- prototype: `__int64 __fastcall(W3_REQUEST *__hidden this, const unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024b70`

## callees

- `0x180009030`
- `0x18002a170`
- `0x18002ad04`
- `0x18002b320`
- `0x180037790`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18002b403`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002b403`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002b458`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002b458`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18002b3d1`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18002b3d1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002b3ef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002b42b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002b3ef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002b42b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002b41a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002b46e`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002b41a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002b46e`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002b36e`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002b4ea`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002b36e`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002b4ea`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b53f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b587`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b5c5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b53f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b587`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b5c5`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002b563`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002b563`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18002b524`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18002b524`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x18002b550`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x18002b550`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBGK@Z` at `0x18002b4c0`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBGK@Z` at `0x18002b4c0`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x18002b504`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x18002b504`

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
0x18002b320  mov     [rsp-8+arg_18], rbx
0x18002b325  push    rbp
0x18002b326  push    rsi
0x18002b327  push    rdi
0x18002b328  push    r12
0x18002b32a  push    r13
0x18002b32c  push    r14
0x18002b32e  push    r15
0x18002b330  lea     rbp, [rsp-1B0h]
0x18002b338  sub     rsp, 2B0h
0x18002b33f  mov     rax, cs:__security_cookie
0x18002b346  xor     rax, rsp
0x18002b349  mov     [rbp+1E0h+var_40], rax
0x18002b350  mov     ebx, r8d
0x18002b353  mov     r14, rdx
0x18002b356  mov     r15, rcx
0x18002b359  lea     rdx, [rbp+1E0h+var_150]
0x18002b360  mov     r8d, 104h
0x18002b366  lea     rcx, [rsp+2E0h+var_288]
0x18002b36b  mov     r13d, r9d
0x18002b36e  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002b375  nop     dword ptr [rax+rax+00h]
0x18002b37a  test    r14, r14
0x18002b37d  jnz     short loc_18002B389
0x18002b37f  mov     ebx, 80070057h
0x18002b384  jmp     loc_18002B582
0x18002b389  test    ebx, ebx
0x18002b38b  jz      loc_18002B47F
0x18002b391  cmp     word ptr [r14], 2Fh ; '/'
0x18002b396  jz      loc_18002B47F
0x18002b39c  mov     rcx, [r15+70h]
0x18002b3a0  cmp     byte ptr [rcx+238Ah], 0
0x18002b3a7  jz      loc_18002B464
0x18002b3ad  lea     rax, [rcx+8]
0x18002b3b1  neg     rcx
0x18002b3b4  sbb     rcx, rcx
0x18002b3b7  xor     edx, edx
0x18002b3b9  and     rcx, rax
0x18002b3bc  lea     r8d, [rdx+4]
0x18002b3c0  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18002b3c5  test    eax, eax
0x18002b3c7  jz      loc_18002B464
0x18002b3cd  lea     rcx, [r15+38h]
0x18002b3d1  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18002b3d8  nop     dword ptr [rax+rax+00h]
0x18002b3dd  test    al, al
0x18002b3df  jz      short loc_18002B3EB
0x18002b3e1  mov     rax, [r15+28h]
0x18002b3e5  mov     rdi, [rax+58h]
0x18002b3e9  jmp     short loc_18002B3FE
0x18002b3eb  lea     rcx, [r15+38h]
0x18002b3ef  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002b3f6  nop     dword ptr [rax+rax+00h]
0x18002b3fb  mov     rdi, rax
0x18002b3fe  lea     rcx, [rsp+2E0h+var_2C0]
0x18002b403  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002b40a  nop     dword ptr [rax+rax+00h]
0x18002b40f  mov     r8d, ebx
0x18002b412  lea     rcx, [rsp+2E0h+var_2C0]
0x18002b417  mov     rdx, r14
0x18002b41a  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002b421  nop     dword ptr [rax+rax+00h]
0x18002b426  lea     rcx, [rsp+2E0h+var_2C0]
0x18002b42b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002b432  nop     dword ptr [rax+rax+00h]
0x18002b437  mov     rcx, [r15+70h]
0x18002b43b  mov     r8, rdi; unsigned __int16 *
0x18002b43e  lea     r9, [rcx+8]
0x18002b442  neg     rcx
0x18002b445  sbb     rcx, rcx
0x18002b448  and     rcx, r9; struct IHttpTraceContext *
0x18002b44b  mov     r9, rax; unsigned __int16 *
0x18002b44e  call    ?RaiseEvent@URL_CHANGED@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2@Z; IISGeneralEvents::URL_CHANGED::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *)
0x18002b453  lea     rcx, [rsp+2E0h+var_2C0]
0x18002b458  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002b45f  nop     dword ptr [rax+rax+00h]
0x18002b464  lea     rcx, [r15+38h]
0x18002b468  mov     r8d, ebx
0x18002b46b  mov     rdx, r14
0x18002b46e  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002b475  nop     dword ptr [rax+rax+00h]
0x18002b47a  jmp     loc_18002B580
0x18002b47f  mov     rax, rbx
0x18002b482  mov     rdi, r14
0x18002b485  test    rax, rax
0x18002b488  jz      short loc_18002B4AE
0x18002b48a  cmp     word ptr [rdi], 3Fh ; '?'
0x18002b48e  jz      short loc_18002B499
0x18002b490  add     rdi, 2
0x18002b494  dec     rax
0x18002b497  jmp     short loc_18002B485
0x18002b499  test    rdi, rdi
0x18002b49c  jz      short loc_18002B4B0
0x18002b49e  mov     rsi, rdi
0x18002b4a1  sub     rsi, r14
0x18002b4a4  sar     rsi, 1
0x18002b4a7  sub     ebx, esi
0x18002b4a9  mov     r12d, ebx
0x18002b4ac  jmp     short loc_18002B4B5
0x18002b4ae  xor     edi, edi
0x18002b4b0  xor     r12d, r12d
0x18002b4b3  mov     esi, ebx
0x18002b4b5  mov     r8d, esi
0x18002b4b8  lea     rcx, [rsp+2E0h+var_288]
0x18002b4bd  mov     rdx, r14
0x18002b4c0  call    cs:__imp_?CopyWToUTF8Escaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Escaped(ushort const *,ulong)
0x18002b4c7  nop     dword ptr [rax+rax+00h]
0x18002b4cc  mov     ebx, eax
0x18002b4ce  test    eax, eax
0x18002b4d0  js      loc_18002B582
0x18002b4d6  test    rdi, rdi
0x18002b4d9  jz      short loc_18002B54B
0x18002b4db  mov     r8d, 100h
0x18002b4e1  lea     rdx, [rbp+1E0h+var_250]
0x18002b4e5  lea     rcx, [rsp+2E0h+var_2C0]
0x18002b4ea  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002b4f1  nop     dword ptr [rax+rax+00h]
0x18002b4f6  mov     eax, esi
0x18002b4f8  lea     rcx, [rsp+2E0h+var_2C0]
0x18002b4fd  mov     r8d, r12d
0x18002b500  lea     rdx, [r14+rax*2]
0x18002b504  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Unescaped(ushort const *,ulong)
0x18002b50b  nop     dword ptr [rax+rax+00h]
0x18002b510  mov     ebx, eax
0x18002b512  test    eax, eax
0x18002b514  js      loc_18002B5C0
0x18002b51a  lea     rdx, [rsp+2E0h+var_2C0]
0x18002b51f  lea     rcx, [rsp+2E0h+var_288]
0x18002b524  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x18002b52b  nop     dword ptr [rax+rax+00h]
0x18002b530  mov     ebx, eax
0x18002b532  test    eax, eax
0x18002b534  js      loc_18002B5C0
0x18002b53a  lea     rcx, [rsp+2E0h+var_2C0]
0x18002b53f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002b546  nop     dword ptr [rax+rax+00h]
0x18002b54b  lea     rcx, [rsp+2E0h+var_288]
0x18002b550  call    cs:__imp_?QueryCB@STRA@@QEBAKXZ; STRA::QueryCB(void)
0x18002b557  nop     dword ptr [rax+rax+00h]
0x18002b55c  lea     rcx, [rsp+2E0h+var_288]
0x18002b561  mov     ebx, eax
0x18002b563  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002b56a  nop     dword ptr [rax+rax+00h]
0x18002b56f  mov     r9d, r13d; int
0x18002b572  mov     r8d, ebx; unsigned int
0x18002b575  mov     rdx, rax; char *
0x18002b578  mov     rcx, r15; this
0x18002b57b  call    ?SetUrl@W3_REQUEST@@QEAAJPEBDKH@Z; W3_REQUEST::SetUrl(char const *,ulong,int)
0x18002b580  mov     ebx, eax
0x18002b582  lea     rcx, [rsp+2E0h+var_288]
0x18002b587  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002b58e  nop     dword ptr [rax+rax+00h]
0x18002b593  mov     eax, ebx
0x18002b595  mov     rcx, [rbp+1E0h+var_40]
0x18002b59c  xor     rcx, rsp; StackCookie
0x18002b59f  call    __security_check_cookie
0x18002b5a4  mov     rbx, [rsp+2E0h+arg_18]
0x18002b5ac  add     rsp, 2B0h
0x18002b5b3  pop     r15
0x18002b5b5  pop     r14
0x18002b5b7  pop     r13
0x18002b5b9  pop     r12
0x18002b5bb  pop     rdi
0x18002b5bc  pop     rsi
0x18002b5bd  pop     rbp
0x18002b5be  retn
0x18002b5c0  lea     rcx, [rsp+2E0h+var_2C0]
0x18002b5c5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002b5cc  nop     dword ptr [rax+rax+00h]
0x18002b5d1  jmp     short loc_18002B582
```

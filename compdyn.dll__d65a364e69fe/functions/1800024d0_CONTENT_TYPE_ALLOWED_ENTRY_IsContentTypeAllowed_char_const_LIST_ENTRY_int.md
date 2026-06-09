# CONTENT_TYPE_ALLOWED_ENTRY::IsContentTypeAllowed(char const *,_LIST_ENTRY *,int)

- ea: `0x1800024d0`
- end: `0x180002685`
- name: `?IsContentTypeAllowed@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDPEAU_LIST_ENTRY@@H@Z`
- size: `437`
- prototype: `__int64 __fastcall(const char *Str, struct _LIST_ENTRY *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001eb0`

## callees

- `0x1800024d0`
- `0x180004c10`
- `0x1800067f8`

## import_xrefs

- `msvcrt!strchr` at `0x180002533`
- `msvcrt!strchr` at `0x180002569`
- `msvcrt!strchr` at `0x180002533`
- `msvcrt!strchr` at `0x180002569`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180002553`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000267a`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180002553`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000267a`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x1800025ba`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x180002612`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x1800025ba`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x180002612`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800025f1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800025fc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000262b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002636`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005761`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000576c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800025f1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800025fc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000262b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002636`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005761`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000576c`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z` at `0x1800025cd`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z` at `0x1800056f3`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z` at `0x1800025cd`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z` at `0x1800056f3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800056ae`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800056c7`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180005720`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180005739`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800056ae`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800056c7`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180005720`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180005739`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000250c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002525`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000250c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002525`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002581`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002581`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800056a1`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800056bb`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180005713`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000572d`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800056a1`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800056bb`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180005713`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000572d`

## pseudocode

```c
__int64 __fastcall CONTENT_TYPE_ALLOWED_ENTRY::IsContentTypeAllowed(
        const char *Str,
        struct _LIST_ENTRY *a2,
        unsigned int a3)
{
  char *v6; // rax
  const char *v7; // rbx
  char *v8; // rax
  const char *v9; // rdx
  int v10; // eax
  struct _LIST_ENTRY *Flink; // rbx
  unsigned int v13; // ebx
  unsigned int v14; // ebp
  const char *v15; // rsi
  unsigned int v16; // edi
  const char *v17; // rax
  unsigned int CCH; // ebp
  const char *v19; // rsi
  unsigned int v20; // edi
  const char *v21; // rax
  int v22; // [rsp+20h] [rbp-F8h]
  _BYTE v23[56]; // [rsp+30h] [rbp-E8h] BYREF
  _BYTE v24[56]; // [rsp+68h] [rbp-B0h] BYREF
  char v25[32]; // [rsp+A0h] [rbp-78h] BYREF
  char v26[32]; // [rsp+C0h] [rbp-58h] BYREF

  STRA::STRA((STRA *)v24, v25, 0x20u);
  STRA::STRA((STRA *)v23, v26, 0x20u);
  v6 = strchr(Str, 47);
  v7 = v6;
  if ( v6
    && (int)STRA::Copy((STRA *)v24, Str, (_DWORD)v6 - (_DWORD)Str) >= 0
    && ((v8 = strchr(v7, 59), v9 = v7 + 1, v8)
      ? (v10 = STRA::Copy((STRA *)v23, v9, (_DWORD)v8 - (_DWORD)v7 - 1))
      : (v10 = STRA::Copy((STRA *)v23, v9)),
        v10 >= 0) )
  {
    Flink = a2->Flink;
    if ( a2->Flink == a2 )
    {
LABEL_11:
      STRA::~STRA((STRA *)v23);
      STRA::~STRA((STRA *)v24);
      return a3;
    }
    else
    {
      while ( 1 )
      {
        if ( STRA::Equals((STRA *)&Flink[1], "*")
          || STRA::EqualsNoCase((STRA *)&Flink[1], (const struct STRA *)v24)
          || HIDWORD(Flink[8].Flink)
          && (v14 = STRA::QueryCCH((STRA *)v24),
              v15 = STRA::QueryStr((STRA *)v24),
              v16 = STRA::QueryCCH((STRA *)&Flink[1]),
              v17 = STRA::QueryStr((STRA *)&Flink[1]),
              (unsigned int)CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(v17, v16, v15, v14, v22)) )
        {
          if ( STRA::Equals((STRA *)&Flink[4].Blink, "*") )
            break;
          if ( STRA::EqualsNoCase((STRA *)&Flink[4].Blink, (const struct STRA *)v23) )
            break;
          if ( LODWORD(Flink[8].Blink) )
          {
            CCH = STRA::QueryCCH((STRA *)v23);
            v19 = STRA::QueryStr((STRA *)v23);
            v20 = STRA::QueryCCH((STRA *)&Flink[4].Blink);
            v21 = STRA::QueryStr((STRA *)&Flink[4].Blink);
            if ( (unsigned int)CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(v21, v20, v19, CCH, v22) )
              break;
          }
        }
        Flink = Flink->Flink;
        if ( Flink == a2 )
          goto LABEL_11;
      }
      v13 = (unsigned int)Flink[8].Flink;
      STRA::~STRA((STRA *)v23);
      STRA::~STRA((STRA *)v24);
      return v13;
    }
  }
  else
  {
    STRA::~STRA((STRA *)v23);
    STRA::~STRA((STRA *)v24);
    return 0;
  }
}

```

## disassembly

```asm
0x1800024d0  push    rbx
0x1800024d2  push    rdi
0x1800024d3  push    r12
0x1800024d5  push    r15
0x1800024d7  sub     rsp, 0F8h
0x1800024de  mov     rax, cs:__security_cookie
0x1800024e5  xor     rax, rsp
0x1800024e8  mov     [rsp+118h+var_38], rax
0x1800024f0  mov     r12d, r8d
0x1800024f3  mov     r15, rdx
0x1800024f6  mov     rdi, rcx
0x1800024f9  lea     rdx, [rsp+118h+var_78]
0x180002501  mov     r8d, 20h ; ' '
0x180002507  lea     rcx, [rsp+118h+var_B0]
0x18000250c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002512  mov     r8d, 20h ; ' '
0x180002518  lea     rdx, [rsp+118h+var_58]
0x180002520  lea     rcx, [rsp+118h+var_E8]
0x180002525  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000252b  mov     edx, 2Fh ; '/'; Val
0x180002530  mov     rcx, rdi; Str
0x180002533  call    cs:__imp_strchr
0x180002539  mov     rbx, rax
0x18000253c  test    rax, rax
0x18000253f  jz      loc_18000575C
0x180002545  mov     r8d, ebx
0x180002548  lea     rcx, [rsp+118h+var_B0]
0x18000254d  sub     r8d, edi
0x180002550  mov     rdx, rdi
0x180002553  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180002559  test    eax, eax
0x18000255b  js      loc_18000575C
0x180002561  mov     edx, 3Bh ; ';'; Val
0x180002566  mov     rcx, rbx; Str
0x180002569  call    cs:__imp_strchr
0x18000256f  lea     rdx, [rbx+1]
0x180002573  lea     rcx, [rsp+118h+var_E8]
0x180002578  test    rax, rax
0x18000257b  jnz     loc_180002674
0x180002581  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180002587  test    eax, eax
0x180002589  js      loc_18000575C
0x18000258f  mov     rbx, [r15]
0x180002592  mov     [rsp+118h+arg_10], rbp
0x18000259a  mov     [rsp+118h+arg_18], rsi
0x1800025a2  mov     [rsp+118h+var_28], r14
0x1800025aa  cmp     rbx, r15
0x1800025ad  jz      short loc_1800025EC
0x1800025af  lea     rdx, asc_180009898; "*"
0x1800025b6  lea     rcx, [rbx+10h]
0x1800025ba  call    cs:__imp_?Equals@STRA@@QEBA_NPEBD@Z; STRA::Equals(char const *)
0x1800025c0  test    al, al
0x1800025c2  jnz     short loc_180002607
0x1800025c4  lea     rdx, [rsp+118h+var_B0]
0x1800025c9  lea     rcx, [rbx+10h]
0x1800025cd  call    cs:__imp_?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z; STRA::EqualsNoCase(STRA const &)
0x1800025d3  test    al, al
0x1800025d5  jnz     short loc_180002607
0x1800025d7  cmp     dword ptr [rbx+84h], 0
0x1800025de  jnz     loc_18000569C
0x1800025e4  mov     rbx, [rbx]
0x1800025e7  cmp     rbx, r15
0x1800025ea  jnz     short loc_1800025AF
0x1800025ec  lea     rcx, [rsp+118h+var_E8]
0x1800025f1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800025f7  lea     rcx, [rsp+118h+var_B0]
0x1800025fc  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002602  mov     eax, r12d
0x180002605  jmp     short loc_18000263E
0x180002607  lea     rdx, asc_180009898; "*"
0x18000260e  lea     rcx, [rbx+48h]
0x180002612  call    cs:__imp_?Equals@STRA@@QEBA_NPEBD@Z; STRA::Equals(char const *)
0x180002618  test    al, al
0x18000261a  jz      loc_1800056EA
0x180002620  mov     ebx, [rbx+80h]
0x180002626  lea     rcx, [rsp+118h+var_E8]
0x18000262b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002631  lea     rcx, [rsp+118h+var_B0]
0x180002636  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000263c  mov     eax, ebx
0x18000263e  mov     rsi, [rsp+118h+arg_18]
0x180002646  mov     rbp, [rsp+118h+arg_10]
0x18000264e  mov     r14, [rsp+118h+var_28]
0x180002656  mov     rcx, [rsp+118h+var_38]
0x18000265e  xor     rcx, rsp; StackCookie
0x180002661  call    __security_check_cookie
0x180002666  add     rsp, 0F8h
0x18000266d  pop     r15
0x18000266f  pop     r12
0x180002671  pop     rdi
0x180002672  pop     rbx
0x180002673  retn
0x180002674  sub     eax, ebx
0x180002676  lea     r8d, [rax-1]
0x18000267a  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180002680  jmp     loc_180002587
0x18000569c  lea     rcx, [rsp+118h+var_B0]
0x1800056a1  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800056a7  lea     rcx, [rsp+118h+var_B0]
0x1800056ac  mov     ebp, eax
0x1800056ae  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800056b4  lea     rcx, [rbx+10h]
0x1800056b8  mov     rsi, rax
0x1800056bb  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800056c1  lea     rcx, [rbx+10h]
0x1800056c5  mov     edi, eax
0x1800056c7  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800056cd  mov     r9d, ebp; unsigned int
0x1800056d0  mov     r8, rsi; char *
0x1800056d3  mov     rcx, rax; char *
0x1800056d6  mov     edx, edi; unsigned int
0x1800056d8  call    ?IsComplexMatch@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDK0KH@Z; CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(char const *,ulong,char const *,ulong,int)
0x1800056dd  test    eax, eax
0x1800056df  jz      loc_1800025E4
0x1800056e5  jmp     loc_180002607
0x1800056ea  lea     rdx, [rsp+118h+var_E8]
0x1800056ef  lea     rcx, [rbx+48h]
0x1800056f3  call    cs:__imp_?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z; STRA::EqualsNoCase(STRA const &)
0x1800056f9  test    al, al
0x1800056fb  jnz     loc_180002620
0x180005701  cmp     dword ptr [rbx+88h], 0
0x180005708  jz      loc_1800025E4
0x18000570e  lea     rcx, [rsp+118h+var_E8]
0x180005713  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180005719  lea     rcx, [rsp+118h+var_E8]
0x18000571e  mov     ebp, eax
0x180005720  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180005726  lea     rcx, [rbx+48h]
0x18000572a  mov     rsi, rax
0x18000572d  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180005733  lea     rcx, [rbx+48h]
0x180005737  mov     edi, eax
0x180005739  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000573f  mov     r9d, ebp; unsigned int
0x180005742  mov     r8, rsi; char *
0x180005745  mov     rcx, rax; char *
0x180005748  mov     edx, edi; unsigned int
0x18000574a  call    ?IsComplexMatch@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDK0KH@Z; CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(char const *,ulong,char const *,ulong,int)
0x18000574f  test    eax, eax
0x180005751  jnz     loc_180002620
0x180005757  jmp     loc_1800025E4
0x18000575c  lea     rcx, [rsp+118h+var_E8]
0x180005761  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180005767  lea     rcx, [rsp+118h+var_B0]
0x18000576c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180005772  xor     eax, eax
0x180005774  jmp     loc_180002656
```

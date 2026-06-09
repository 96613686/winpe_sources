# CONTENT_TYPE_ALLOWED_ENTRY::IsContentTypeAllowed(char const *,_LIST_ENTRY *,int)

- ea: `0x180001b00`
- end: `0x180001cc9`
- name: `?IsContentTypeAllowed@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDPEAU_LIST_ENTRY@@H@Z`
- size: `457`
- prototype: `__int64 __fastcall(const char *Str, struct _LIST_ENTRY *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001310`

## callees

- `0x180001b00`
- `0x180005f90`
- `0x1800084b0`

## import_xrefs

- `msvcrt!strchr` at `0x180001b63`
- `msvcrt!strchr` at `0x180001b99`
- `msvcrt!strchr` at `0x180001b63`
- `msvcrt!strchr` at `0x180001b99`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z` at `0x180001bfe`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z` at `0x180001c8a`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z` at `0x180001bfe`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z` at `0x180001c8a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001b3c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001b55`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001b3c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001b55`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001c22`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001c2d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001cb1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001cbc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006933`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000693e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001c22`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001c2d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001cb1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001cbc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006933`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000693e`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180006897`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800068b1`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800068e5`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800068ff`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180006897`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800068b1`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800068e5`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800068ff`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800068a4`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800068bd`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800068f2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000690b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800068a4`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800068bd`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800068f2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000690b`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x180001beb`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x180001c77`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x180001beb`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x180001c77`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180001bb1`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180001bb1`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180001b83`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180006886`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180001b83`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180006886`

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
  int v23; // [rsp+20h] [rbp-F8h]
  _BYTE v24[56]; // [rsp+30h] [rbp-E8h] BYREF
  _BYTE v25[56]; // [rsp+68h] [rbp-B0h] BYREF
  char v26[32]; // [rsp+A0h] [rbp-78h] BYREF
  char v27[32]; // [rsp+C0h] [rbp-58h] BYREF

  STRA::STRA((STRA *)v25, v26, 0x20u);
  STRA::STRA((STRA *)v24, v27, 0x20u);
  v6 = strchr(Str, 47);
  v7 = v6;
  if ( v6
    && (int)STRA::Copy((STRA *)v25, Str, (_DWORD)v6 - (_DWORD)Str) >= 0
    && ((v8 = strchr(v7, 59), v9 = v7 + 1, v8)
      ? (v10 = STRA::Copy((STRA *)v24, v9, (_DWORD)v8 - (_DWORD)v7 - 1))
      : (v10 = STRA::Copy((STRA *)v24, v9)),
        v10 >= 0) )
  {
    Flink = a2->Flink;
    if ( a2->Flink == a2 )
    {
LABEL_11:
      STRA::~STRA((STRA *)v24);
      STRA::~STRA((STRA *)v25);
      return a3;
    }
    else
    {
      while ( 1 )
      {
        if ( STRA::Equals((STRA *)&Flink[1], "*")
          || STRA::EqualsNoCase((STRA *)&Flink[1], (const struct STRA *)v25)
          || HIDWORD(Flink[8].Flink)
          && (v14 = STRA::QueryCCH((STRA *)v25),
              v15 = STRA::QueryStr((STRA *)v25),
              v16 = STRA::QueryCCH((STRA *)&Flink[1]),
              v17 = STRA::QueryStr((STRA *)&Flink[1]),
              (unsigned int)CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(v17, v16, v15, v14, v23)) )
        {
          if ( STRA::Equals((STRA *)&Flink[4].Blink, "*") )
            break;
          if ( STRA::EqualsNoCase((STRA *)&Flink[4].Blink, (const struct STRA *)v24) )
            break;
          if ( LODWORD(Flink[8].Blink) )
          {
            CCH = STRA::QueryCCH((STRA *)v24);
            v19 = STRA::QueryStr((STRA *)v24);
            v20 = STRA::QueryCCH((STRA *)&Flink[4].Blink);
            v21 = STRA::QueryStr((STRA *)&Flink[4].Blink);
            if ( (unsigned int)CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(v21, v20, v19, CCH, v23) )
              break;
          }
        }
        Flink = Flink->Flink;
        if ( Flink == a2 )
          goto LABEL_11;
      }
      v13 = (unsigned int)Flink[8].Flink;
      STRA::~STRA((STRA *)v24);
      STRA::~STRA((STRA *)v25);
      return v13;
    }
  }
  else
  {
    STRA::~STRA((STRA *)v24);
    STRA::~STRA((STRA *)v25);
    return 0;
  }
}

```

## disassembly

```asm
0x180001b00  push    rbx
0x180001b02  push    rdi
0x180001b03  push    r12
0x180001b05  push    r15
0x180001b07  sub     rsp, 0F8h
0x180001b0e  mov     rax, cs:__security_cookie
0x180001b15  xor     rax, rsp
0x180001b18  mov     [rsp+118h+var_38], rax
0x180001b20  mov     r12d, r8d
0x180001b23  mov     r15, rdx
0x180001b26  mov     rdi, rcx
0x180001b29  lea     rdx, [rsp+118h+var_78]
0x180001b31  mov     r8d, 20h ; ' '
0x180001b37  lea     rcx, [rsp+118h+var_B0]
0x180001b3c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180001b42  mov     r8d, 20h ; ' '
0x180001b48  lea     rdx, [rsp+118h+var_58]
0x180001b50  lea     rcx, [rsp+118h+var_E8]
0x180001b55  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180001b5b  mov     edx, 2Fh ; '/'; Val
0x180001b60  mov     rcx, rdi; Str
0x180001b63  call    cs:__imp_strchr
0x180001b69  mov     rbx, rax
0x180001b6c  test    rax, rax
0x180001b6f  jz      loc_18000692E
0x180001b75  mov     r8d, ebx
0x180001b78  lea     rcx, [rsp+118h+var_B0]
0x180001b7d  sub     r8d, edi
0x180001b80  mov     rdx, rdi
0x180001b83  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180001b89  test    eax, eax
0x180001b8b  js      loc_18000692E
0x180001b91  mov     edx, 3Bh ; ';'; Val
0x180001b96  mov     rcx, rbx; Str
0x180001b99  call    cs:__imp_strchr
0x180001b9f  lea     rdx, [rbx+1]
0x180001ba3  lea     rcx, [rsp+118h+var_E8]
0x180001ba8  test    rax, rax
0x180001bab  jnz     loc_180006880
0x180001bb1  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180001bb7  test    eax, eax
0x180001bb9  js      loc_18000692E
0x180001bbf  mov     rbx, [r15]
0x180001bc2  mov     [rsp+118h+arg_10], rbp
0x180001bca  mov     [rsp+118h+arg_18], rsi
0x180001bd2  mov     [rsp+118h+var_28], r14
0x180001bda  cmp     rbx, r15
0x180001bdd  jz      short loc_180001C1D
0x180001bdf  nop
0x180001be0  lea     rdx, asc_18000AA64; "*"
0x180001be7  lea     rcx, [rbx+10h]
0x180001beb  call    cs:__imp_?Equals@STRA@@QEBA_NPEBD@Z; STRA::Equals(char const *)
0x180001bf1  test    al, al
0x180001bf3  jnz     short loc_180001C6C
0x180001bf5  lea     rdx, [rsp+118h+var_B0]
0x180001bfa  lea     rcx, [rbx+10h]
0x180001bfe  call    cs:__imp_?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z; STRA::EqualsNoCase(STRA const &)
0x180001c04  test    al, al
0x180001c06  jnz     short loc_180001C6C
0x180001c08  cmp     dword ptr [rbx+84h], 0
0x180001c0f  jnz     loc_180006892
0x180001c15  mov     rbx, [rbx]
0x180001c18  cmp     rbx, r15
0x180001c1b  jnz     short loc_180001BE0
0x180001c1d  lea     rcx, [rsp+118h+var_E8]
0x180001c22  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001c28  lea     rcx, [rsp+118h+var_B0]
0x180001c2d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001c33  mov     eax, r12d
0x180001c36  mov     rsi, [rsp+118h+arg_18]
0x180001c3e  mov     rbp, [rsp+118h+arg_10]
0x180001c46  mov     r14, [rsp+118h+var_28]
0x180001c4e  mov     rcx, [rsp+118h+var_38]
0x180001c56  xor     rcx, rsp; StackCookie
0x180001c59  call    __security_check_cookie
0x180001c5e  add     rsp, 0F8h
0x180001c65  pop     r15
0x180001c67  pop     r12
0x180001c69  pop     rdi
0x180001c6a  pop     rbx
0x180001c6b  retn
0x180001c6c  lea     rdx, asc_18000AA64; "*"
0x180001c73  lea     rcx, [rbx+48h]
0x180001c77  call    cs:__imp_?Equals@STRA@@QEBA_NPEBD@Z; STRA::Equals(char const *)
0x180001c7d  test    al, al
0x180001c7f  jnz     short loc_180001CA6
0x180001c81  lea     rdx, [rsp+118h+var_E8]
0x180001c86  lea     rcx, [rbx+48h]
0x180001c8a  call    cs:__imp_?EqualsNoCase@STRA@@QEBA_NAEBV1@@Z; STRA::EqualsNoCase(STRA const &)
0x180001c90  test    al, al
0x180001c92  jnz     short loc_180001CA6
0x180001c94  cmp     dword ptr [rbx+88h], 0
0x180001c9b  jz      loc_180001C15
0x180001ca1  jmp     loc_1800068E0
0x180001ca6  mov     ebx, [rbx+80h]
0x180001cac  lea     rcx, [rsp+118h+var_E8]
0x180001cb1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001cb7  lea     rcx, [rsp+118h+var_B0]
0x180001cbc  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001cc2  mov     eax, ebx
0x180001cc4  jmp     loc_180001C36
0x180006880  sub     eax, ebx
0x180006882  lea     r8d, [rax-1]
0x180006886  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000688c  nop
0x18000688d  jmp     loc_180001BB7
0x180006892  lea     rcx, [rsp+118h+var_B0]
0x180006897  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18000689d  lea     rcx, [rsp+118h+var_B0]
0x1800068a2  mov     ebp, eax
0x1800068a4  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800068aa  lea     rcx, [rbx+10h]
0x1800068ae  mov     rsi, rax
0x1800068b1  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800068b7  lea     rcx, [rbx+10h]
0x1800068bb  mov     edi, eax
0x1800068bd  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800068c3  mov     r9d, ebp; unsigned int
0x1800068c6  mov     r8, rsi; char *
0x1800068c9  mov     rcx, rax; char *
0x1800068cc  mov     edx, edi; unsigned int
0x1800068ce  call    ?IsComplexMatch@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDK0KH@Z; CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(char const *,ulong,char const *,ulong,int)
0x1800068d3  test    eax, eax
0x1800068d5  jz      loc_180001C15
0x1800068db  jmp     loc_180001C6C
0x1800068e0  lea     rcx, [rsp+118h+var_E8]
0x1800068e5  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800068eb  lea     rcx, [rsp+118h+var_E8]
0x1800068f0  mov     ebp, eax
0x1800068f2  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800068f8  lea     rcx, [rbx+48h]
0x1800068fc  mov     rsi, rax
0x1800068ff  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180006905  lea     rcx, [rbx+48h]
0x180006909  mov     edi, eax
0x18000690b  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180006911  mov     r9d, ebp; unsigned int
0x180006914  mov     r8, rsi; char *
0x180006917  mov     rcx, rax; char *
0x18000691a  mov     edx, edi; unsigned int
0x18000691c  call    ?IsComplexMatch@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDK0KH@Z; CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(char const *,ulong,char const *,ulong,int)
0x180006921  test    eax, eax
0x180006923  jnz     loc_180001CA6
0x180006929  jmp     loc_180001C15
0x18000692e  lea     rcx, [rsp+118h+var_E8]
0x180006933  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006939  lea     rcx, [rsp+118h+var_B0]
0x18000693e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006944  xor     eax, eax
0x180006946  jmp     loc_180001C4E
```

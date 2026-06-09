# W3_REQUEST::SetHeader(_HTTP_HEADER_ID,char const *,ushort,int)

- ea: `0x18002a984`
- end: `0x18002ac4b`
- name: `?SetHeader@W3_REQUEST@@QEAAJW4_HTTP_HEADER_ID@@PEBDGH@Z`
- size: `711`
- prototype: `__int64 __fastcall(W3_REQUEST *this, enum _HTTP_HEADER_ID, const char *, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180024370`

## callees

- `0x1800126f0`
- `0x18001749c`
- `0x180017d40`
- `0x18002a984`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002a9d0`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002a9eb`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002a9d0`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002a9eb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002ab9b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002abac`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002abdf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002abf0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002ac05`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002ac16`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002ab9b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002abac`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002abdf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002abf0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002ac05`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002ac16`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002aa54`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002ab33`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002ab4b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002aa54`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002ab33`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002ab4b`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002aa26`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002aab1`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002aa26`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002aab1`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002ab14`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002ab5f`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002ab14`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002ab5f`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18002aad9`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18002aad9`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18002aaf9`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18002aaf9`

## pseudocode

```c
__int64 __fastcall W3_REQUEST::SetHeader(
        W3_REQUEST *this,
        enum _HTTP_HEADER_ID a2,
        const char *a3,
        unsigned __int16 a4,
        int a5)
{
  __int64 v6; // rsi
  unsigned int v8; // edi
  int v9; // ebx
  const char *String; // rax
  const char *v11; // r10
  __int64 v12; // r15
  __int64 v13; // rsi
  __int64 v14; // rdi
  const char *v15; // rdx
  char *Str; // rax
  STRA *v17; // rcx
  const char *v18; // rbx
  unsigned __int16 CCH; // ax
  __int64 v20; // rcx
  unsigned __int16 v21; // r13
  unsigned int v22; // r14d
  char *v23; // rax
  __int64 v25; // r10
  unsigned int v26; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v27[56]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v28[64]; // [rsp+60h] [rbp-A0h] BYREF
  char v29[256]; // [rsp+A0h] [rbp-60h] BYREF
  char v30[256]; // [rsp+1A0h] [rbp+A0h] BYREF

  v6 = a2;
  v8 = a4;
  STRA::STRA((STRA *)v27, v29, 0x100u);
  STRA::STRA((STRA *)v28, v30, 0x100u);
  if ( (unsigned int)v6 > 0x28 )
  {
    STRA::~STRA((STRA *)v28);
    STRA::~STRA((STRA *)v27);
    return 2147943813LL;
  }
  else
  {
    if ( !a3 && (_WORD)v8 )
    {
      v9 = -2147024809;
LABEL_19:
      STRA::~STRA((STRA *)v28);
      STRA::~STRA((STRA *)v27);
      return (unsigned int)v9;
    }
    ++*((_DWORD *)this + 12);
    v9 = STRA::Copy((STRA *)v28, a3, v8);
    if ( v9 < 0 )
      goto LABEL_19;
    if ( *(_BYTE *)(*((_QWORD *)this + 14) + 9098LL) )
    {
      STRA::QueryStr((STRA *)v28);
      String = REQUEST_HEADER_HASH::GetString(v6, &v26);
      W3_REQUEST::TraceSetHeader(this, String, v11, a5);
    }
    v12 = *((_QWORD *)this + 5);
    v13 = 2 * v6;
    v14 = v12 + 8 * v13;
    if ( a5 || (v15 = *(const char **)(v14 + 160)) == 0 )
    {
      Str = STRA::QueryStr((STRA *)v28);
      v17 = (STRA *)v28;
    }
    else
    {
      v9 = STRA::Copy((STRA *)v27, v15, *(unsigned __int16 *)(v12 + 8 * v13 + 152));
      if ( v9 < 0 )
        goto LABEL_19;
      v9 = STRA::Append((STRA *)v27, ",", 1u);
      if ( v9 < 0 )
        goto LABEL_19;
      v9 = STRA::Append((STRA *)v27, (const struct STRA *)v28);
      if ( v9 < 0 )
        goto LABEL_19;
      if ( STRA::QueryCCH((STRA *)v27) > 0xFFFF )
      {
        v9 = -2147024883;
        goto LABEL_19;
      }
      Str = STRA::QueryStr((STRA *)v27);
      v17 = (STRA *)v27;
    }
    v18 = Str;
    CCH = STRA::QueryCCH(v17);
    v20 = *((_QWORD *)this + 14);
    v21 = CCH;
    v22 = CCH + 1;
    v23 = (char *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 144LL))(v20, v22);
    if ( !v23 )
    {
      v9 = -2147024888;
      goto LABEL_19;
    }
    StringCchCopyA(v23, v22, v18);
    *(_QWORD *)(v14 + 160) = v25;
    *(_WORD *)(v12 + 8 * v13 + 152) = v21;
    STRA::~STRA((STRA *)v28);
    STRA::~STRA((STRA *)v27);
    return 0;
  }
}

```

## disassembly

```asm
0x18002a984  push    rbp
0x18002a986  push    rbx
0x18002a987  push    rsi
0x18002a988  push    rdi
0x18002a989  push    r12
0x18002a98b  push    r13
0x18002a98d  push    r14
0x18002a98f  push    r15
0x18002a991  lea     rbp, [rsp-1B8h]
0x18002a999  sub     rsp, 2B8h
0x18002a9a0  mov     rax, cs:__security_cookie
0x18002a9a7  xor     rax, rsp
0x18002a9aa  mov     [rbp+1F0h+var_50], rax
0x18002a9b1  mov     rbx, r8
0x18002a9b4  movsxd  rsi, edx
0x18002a9b7  mov     r14, rcx
0x18002a9ba  movzx   edi, r9w
0x18002a9be  mov     r15d, 100h
0x18002a9c4  lea     rdx, [rbp+1F0h+var_250]
0x18002a9c8  mov     r8d, r15d
0x18002a9cb  lea     rcx, [rsp+2F0h+var_2C8]
0x18002a9d0  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002a9d7  nop     dword ptr [rax+rax+00h]
0x18002a9dc  mov     r8d, r15d
0x18002a9df  lea     rdx, [rbp+1F0h+var_150]
0x18002a9e6  lea     rcx, [rsp+2F0h+var_290]
0x18002a9eb  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002a9f2  nop     dword ptr [rax+rax+00h]
0x18002a9f7  cmp     esi, 28h ; '('
0x18002a9fa  ja      loc_18002AC00
0x18002aa00  xor     r12d, r12d
0x18002aa03  test    rbx, rbx
0x18002aa06  jnz     short loc_18002AA17
0x18002aa08  test    di, di
0x18002aa0b  jz      short loc_18002AA17
0x18002aa0d  mov     ebx, 80070057h
0x18002aa12  jmp     loc_18002AB96
0x18002aa17  inc     dword ptr [r14+30h]
0x18002aa1b  lea     rcx, [rsp+2F0h+var_290]
0x18002aa20  mov     r8d, edi
0x18002aa23  mov     rdx, rbx
0x18002aa26  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18002aa2d  nop     dword ptr [rax+rax+00h]
0x18002aa32  mov     ebx, eax
0x18002aa34  test    eax, eax
0x18002aa36  js      loc_18002AB96
0x18002aa3c  mov     rax, [r14+70h]
0x18002aa40  mov     ebx, [rbp+1F0h+arg_20]
0x18002aa46  cmp     [rax+238Ah], r12b
0x18002aa4d  jz      short loc_18002AA80
0x18002aa4f  lea     rcx, [rsp+2F0h+var_290]
0x18002aa54  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002aa5b  nop     dword ptr [rax+rax+00h]
0x18002aa60  lea     rdx, [rsp+2F0h+var_2D0]; unsigned int *
0x18002aa65  mov     ecx, esi; unsigned int
0x18002aa67  mov     r10, rax
0x18002aa6a  call    ?GetString@REQUEST_HEADER_HASH@@SAPEADKPEAK@Z; REQUEST_HEADER_HASH::GetString(ulong,ulong *)
0x18002aa6f  mov     r8, r10; char *
0x18002aa72  mov     rdx, rax; char *
0x18002aa75  mov     rcx, r14; this
0x18002aa78  mov     r9d, ebx; int
0x18002aa7b  call    ?TraceSetHeader@W3_REQUEST@@AEAAXPEBD0H@Z; W3_REQUEST::TraceSetHeader(char const *,char const *,int)
0x18002aa80  mov     r15, [r14+28h]
0x18002aa84  add     rsi, rsi
0x18002aa87  lea     rdi, [r15+rsi*8]
0x18002aa8b  test    ebx, ebx
0x18002aa8d  jnz     loc_18002AB46
0x18002aa93  mov     rdx, [rdi+0A0h]
0x18002aa9a  test    rdx, rdx
0x18002aa9d  jz      loc_18002AB46
0x18002aaa3  movzx   r8d, word ptr [r15+rsi*8+98h]
0x18002aaac  lea     rcx, [rsp+2F0h+var_2C8]
0x18002aab1  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18002aab8  nop     dword ptr [rax+rax+00h]
0x18002aabd  mov     ebx, eax
0x18002aabf  test    eax, eax
0x18002aac1  js      loc_18002AB96
0x18002aac7  mov     r8d, 1
0x18002aacd  lea     rdx, asc_18003C188; ","
0x18002aad4  lea     rcx, [rsp+2F0h+var_2C8]
0x18002aad9  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18002aae0  nop     dword ptr [rax+rax+00h]
0x18002aae5  mov     ebx, eax
0x18002aae7  test    eax, eax
0x18002aae9  js      loc_18002AB96
0x18002aaef  lea     rdx, [rsp+2F0h+var_290]
0x18002aaf4  lea     rcx, [rsp+2F0h+var_2C8]
0x18002aaf9  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x18002ab00  nop     dword ptr [rax+rax+00h]
0x18002ab05  mov     ebx, eax
0x18002ab07  test    eax, eax
0x18002ab09  js      loc_18002AB96
0x18002ab0f  lea     rcx, [rsp+2F0h+var_2C8]
0x18002ab14  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002ab1b  nop     dword ptr [rax+rax+00h]
0x18002ab20  cmp     eax, 0FFFFh
0x18002ab25  jbe     short loc_18002AB2E
0x18002ab27  mov     ebx, 8007000Dh
0x18002ab2c  jmp     short loc_18002AB96
0x18002ab2e  lea     rcx, [rsp+2F0h+var_2C8]
0x18002ab33  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002ab3a  nop     dword ptr [rax+rax+00h]
0x18002ab3f  lea     rcx, [rsp+2F0h+var_2C8]
0x18002ab44  jmp     short loc_18002AB5C
0x18002ab46  lea     rcx, [rsp+2F0h+var_290]
0x18002ab4b  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002ab52  nop     dword ptr [rax+rax+00h]
0x18002ab57  lea     rcx, [rsp+2F0h+var_290]
0x18002ab5c  mov     rbx, rax
0x18002ab5f  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002ab66  nop     dword ptr [rax+rax+00h]
0x18002ab6b  mov     rcx, [r14+70h]
0x18002ab6f  movzx   r13d, ax
0x18002ab73  mov     rax, [rcx]
0x18002ab76  lea     r14d, [r13+1]
0x18002ab7a  mov     edx, r14d
0x18002ab7d  mov     rax, [rax+90h]
0x18002ab84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab89  mov     r10, rax
0x18002ab8c  test    rax, rax
0x18002ab8f  jnz     short loc_18002ABBC
0x18002ab91  mov     ebx, 80070008h
0x18002ab96  lea     rcx, [rsp+2F0h+var_290]
0x18002ab9b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002aba2  nop     dword ptr [rax+rax+00h]
0x18002aba7  lea     rcx, [rsp+2F0h+var_2C8]
0x18002abac  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002abb3  nop     dword ptr [rax+rax+00h]
0x18002abb8  mov     eax, ebx
0x18002abba  jmp     short loc_18002AC27
0x18002abbc  mov     edx, r14d; unsigned __int64
0x18002abbf  mov     r8, rbx; char *
0x18002abc2  mov     rcx, r10; char *
0x18002abc5  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002abca  lea     rcx, [rsp+2F0h+var_290]
0x18002abcf  mov     [rdi+0A0h], r10
0x18002abd6  mov     [r15+rsi*8+98h], r13w
0x18002abdf  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002abe6  nop     dword ptr [rax+rax+00h]
0x18002abeb  lea     rcx, [rsp+2F0h+var_2C8]
0x18002abf0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002abf7  nop     dword ptr [rax+rax+00h]
0x18002abfc  xor     eax, eax
0x18002abfe  jmp     short loc_18002AC27
0x18002ac00  lea     rcx, [rsp+2F0h+var_290]
0x18002ac05  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002ac0c  nop     dword ptr [rax+rax+00h]
0x18002ac11  lea     rcx, [rsp+2F0h+var_2C8]
0x18002ac16  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002ac1d  nop     dword ptr [rax+rax+00h]
0x18002ac22  mov     eax, 80070585h
0x18002ac27  mov     rcx, [rbp+1F0h+var_50]
0x18002ac2e  xor     rcx, rsp; StackCookie
0x18002ac31  call    __security_check_cookie
0x18002ac36  add     rsp, 2B8h
0x18002ac3d  pop     r15
0x18002ac3f  pop     r14
0x18002ac41  pop     r13
0x18002ac43  pop     r12
0x18002ac45  pop     rdi
0x18002ac46  pop     rsi
0x18002ac47  pop     rbx
0x18002ac48  pop     rbp
0x18002ac49  retn
```

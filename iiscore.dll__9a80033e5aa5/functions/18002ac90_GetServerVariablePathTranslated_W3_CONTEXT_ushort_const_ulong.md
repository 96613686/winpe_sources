# GetServerVariablePathTranslated(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x18002ac90`
- end: `0x18002aec8`
- name: `?GetServerVariablePathTranslated@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `568`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *this, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180002bf0`
- `0x18002ac90`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18002ad1d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002ad1d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002adb0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002adbb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae30`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae3b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae6e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae79`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002adb0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002adbb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae30`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae3b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae6e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae79`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002adfb`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002ae60`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002adfb`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002ae60`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002adcd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002adcd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ad43`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ad43`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002ad9f`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002ad9f`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002ae52`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002ae52`

## pseudocode

```c
__int64 __fastcall GetServerVariablePathTranslated(
        struct W3_CONTEXT *this,
        const unsigned __int16 **a2,
        unsigned int *a3)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rax
  unsigned int v9; // edi
  unsigned __int16 *Str; // rdx
  unsigned int v11; // edi
  int v12; // esi
  int v14; // edi
  unsigned int v15; // edx
  __int64 v16; // rax
  unsigned __int16 *v17; // rax
  const unsigned __int16 *v18; // rbx
  const unsigned __int16 *v19; // rax
  bool v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v22; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v23[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[56]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v25[256]; // [rsp+B0h] [rbp-50h] BYREF

  if ( (*(__int64 (__fastcall **)(struct W3_CONTEXT *))(*(_QWORD *)this + 192LL))(this)
    && (v6 = (*(__int64 (__fastcall **)(struct W3_CONTEXT *))(*(_QWORD *)this + 192LL))(this),
        (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6)) )
  {
    v7 = *(_QWORD *)(*((_QWORD *)this + 6) + 40LL);
    v21 = 0;
    STRU::STRU((STRU *)v24);
    memset_0(v25, 0, sizeof(v25));
    STRU::STRU((STRU *)v23, v25, 0x100u);
    v8 = *(_QWORD *)this;
    v20 = 0;
    (*(void (__fastcall **)(struct W3_CONTEXT *, unsigned int *))(v8 + 176))(this, &v21);
    v9 = *(unsigned __int16 *)(v7 + 68) >> 1;
    if ( v21 <= v9 )
    {
      v11 = v9 - v21;
      Str = (unsigned __int16 *)(*(_QWORD *)(v7 + 88) + 2LL * v21);
    }
    else
    {
      Str = (unsigned __int16 *)byte_18003C3C0;
      v11 = 0;
    }
    if ( Str[v11] )
    {
      v12 = STRU::Copy((STRU *)v24, Str, v11);
      if ( v12 < 0 )
      {
        STRU::~STRU((STRU *)v23);
        STRU::~STRU((STRU *)v24);
        return (unsigned int)v12;
      }
      Str = STRU::QueryStr((STRU *)v24);
    }
    v14 = W3_CONTEXT::MapPath(this, Str, v11, (struct STRU *)v23, &v20);
    if ( v14 < 0 )
      goto LABEL_13;
    v15 = 2 * STRU::QueryCCH((STRU *)v23) + 2;
    v16 = *(_QWORD *)this;
    v22 = v15;
    v17 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *))(v16 + 144))(this);
    v18 = v17;
    if ( !v17 )
    {
      v14 = -2147024888;
LABEL_13:
      STRU::~STRU((STRU *)v23);
      STRU::~STRU((STRU *)v24);
      return (unsigned int)v14;
    }
    STRU::CopyToBuffer((STRU *)v23, v17, &v22);
    *a2 = v18;
    *a3 = STRU::QueryCCH((STRU *)v23);
    STRU::~STRU((STRU *)v23);
    STRU::~STRU((STRU *)v24);
    return 0;
  }
  else
  {
    v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *, unsigned int *))(*(_QWORD *)this + 168LL))(
                                      this,
                                      a3);
    *a2 = v19;
    return v19 == 0 ? 0x80070008 : 0;
  }
}

```

## disassembly

```asm
0x18002ac90  push    rbp
0x18002ac92  push    rbx
0x18002ac93  push    rsi
0x18002ac94  push    rdi
0x18002ac95  push    r12
0x18002ac97  push    r14
0x18002ac99  push    r15
0x18002ac9b  lea     rbp, [rsp-1C0h]
0x18002aca3  sub     rsp, 2C0h
0x18002acaa  mov     rax, cs:__security_cookie
0x18002acb1  xor     rax, rsp
0x18002acb4  mov     [rbp+1F0h+var_40], rax
0x18002acbb  mov     rax, [rcx]
0x18002acbe  mov     r15, r8
0x18002acc1  mov     r14, rdx
0x18002acc4  mov     rbx, rcx
0x18002acc7  mov     rax, [rax+0C0h]
0x18002acce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acd3  xor     r12d, r12d
0x18002acd6  test    rax, rax
0x18002acd9  jz      loc_18002AE83
0x18002acdf  mov     rax, [rbx]
0x18002ace2  mov     rcx, rbx
0x18002ace5  mov     rax, [rax+0C0h]
0x18002acec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acf1  mov     rdx, rax
0x18002acf4  mov     rcx, [rax]
0x18002acf7  mov     rax, [rcx+28h]
0x18002acfb  mov     rcx, rdx
0x18002acfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad03  test    eax, eax
0x18002ad05  jz      loc_18002AE83
0x18002ad0b  mov     rax, [rbx+30h]
0x18002ad0f  lea     rcx, [rsp+2F0h+var_278]
0x18002ad14  mov     rsi, [rax+28h]
0x18002ad18  mov     [rsp+2F0h+var_2BC], r12d
0x18002ad1d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002ad23  xor     edx, edx; Val
0x18002ad25  lea     rcx, [rbp+1F0h+var_240]; void *
0x18002ad29  mov     r8d, 200h; Size
0x18002ad2f  call    memset_0
0x18002ad34  mov     r8d, 100h
0x18002ad3a  lea     rdx, [rbp+1F0h+var_240]
0x18002ad3e  lea     rcx, [rsp+2F0h+var_2B0]
0x18002ad43  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002ad49  mov     rax, [rbx]
0x18002ad4c  lea     rdx, [rsp+2F0h+var_2BC]
0x18002ad51  mov     rcx, rbx
0x18002ad54  mov     [rsp+2F0h+var_2C0], r12b
0x18002ad59  mov     rax, [rax+0B0h]
0x18002ad60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad65  movzx   eax, word ptr [rsi+44h]
0x18002ad69  mov     r8d, [rsp+2F0h+var_2BC]
0x18002ad6e  shr     eax, 1
0x18002ad70  mov     edi, eax
0x18002ad72  cmp     r8d, eax
0x18002ad75  jbe     short loc_18002AD83
0x18002ad77  lea     rdx, byte_18003C3C0
0x18002ad7e  mov     edi, r12d
0x18002ad81  jmp     short loc_18002AD8E
0x18002ad83  mov     rax, [rsi+58h]
0x18002ad87  sub     edi, r8d
0x18002ad8a  lea     rdx, [rax+r8*2]
0x18002ad8e  mov     eax, edi
0x18002ad90  cmp     [rdx+rax*2], r12w
0x18002ad95  jz      short loc_18002ADD6
0x18002ad97  mov     r8d, edi
0x18002ad9a  lea     rcx, [rsp+2F0h+var_278]
0x18002ad9f  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002ada5  mov     esi, eax
0x18002ada7  test    eax, eax
0x18002ada9  jns     short loc_18002ADC8
0x18002adab  lea     rcx, [rsp+2F0h+var_2B0]
0x18002adb0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002adb6  lea     rcx, [rsp+2F0h+var_278]
0x18002adbb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002adc1  mov     eax, esi
0x18002adc3  jmp     loc_18002AEA7
0x18002adc8  lea     rcx, [rsp+2F0h+var_278]
0x18002adcd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002add3  mov     rdx, rax; unsigned __int16 *
0x18002add6  lea     rax, [rsp+2F0h+var_2C0]
0x18002addb  mov     r8d, edi; unsigned int
0x18002adde  lea     r9, [rsp+2F0h+var_2B0]; struct STRU *
0x18002ade3  mov     [rsp+2F0h+var_2D0], rax; bool *
0x18002ade8  mov     rcx, rbx; this
0x18002adeb  call    ?MapPath@W3_CONTEXT@@QEAAJPEBGKPEAVSTRU@@PEA_N@Z; W3_CONTEXT::MapPath(ushort const *,ulong,STRU *,bool *)
0x18002adf0  mov     edi, eax
0x18002adf2  test    eax, eax
0x18002adf4  js      short loc_18002AE2B
0x18002adf6  lea     rcx, [rsp+2F0h+var_2B0]
0x18002adfb  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002ae01  mov     rcx, rbx
0x18002ae04  lea     edx, ds:2[rax*2]
0x18002ae0b  mov     rax, [rbx]
0x18002ae0e  mov     [rsp+2F0h+var_2B8], edx
0x18002ae12  mov     rax, [rax+90h]
0x18002ae19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae1e  mov     rbx, rax
0x18002ae21  test    rax, rax
0x18002ae24  jnz     short loc_18002AE45
0x18002ae26  mov     edi, 80070008h
0x18002ae2b  lea     rcx, [rsp+2F0h+var_2B0]
0x18002ae30  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002ae36  lea     rcx, [rsp+2F0h+var_278]
0x18002ae3b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002ae41  mov     eax, edi
0x18002ae43  jmp     short loc_18002AEA7
0x18002ae45  lea     r8, [rsp+2F0h+var_2B8]
0x18002ae4a  mov     rdx, rbx
0x18002ae4d  lea     rcx, [rsp+2F0h+var_2B0]
0x18002ae52  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18002ae58  lea     rcx, [rsp+2F0h+var_2B0]
0x18002ae5d  mov     [r14], rbx
0x18002ae60  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002ae66  lea     rcx, [rsp+2F0h+var_2B0]
0x18002ae6b  mov     [r15], eax
0x18002ae6e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002ae74  lea     rcx, [rsp+2F0h+var_278]
0x18002ae79  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002ae7f  xor     eax, eax
0x18002ae81  jmp     short loc_18002AEA7
0x18002ae83  mov     rax, [rbx]
0x18002ae86  mov     rdx, r15
0x18002ae89  mov     rcx, rbx
0x18002ae8c  mov     rax, [rax+0A8h]
0x18002ae93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae98  mov     [r14], rax
0x18002ae9b  neg     rax
0x18002ae9e  sbb     eax, eax
0x18002aea0  not     eax
0x18002aea2  and     eax, 80070008h
0x18002aea7  mov     rcx, [rbp+1F0h+var_40]
0x18002aeae  xor     rcx, rsp; StackCookie
0x18002aeb1  call    __security_check_cookie
0x18002aeb6  add     rsp, 2C0h
0x18002aebd  pop     r15
0x18002aebf  pop     r14
0x18002aec1  pop     r12
0x18002aec3  pop     rdi
0x18002aec4  pop     rsi
0x18002aec5  pop     rbx
0x18002aec6  pop     rbp
0x18002aec7  retn
```

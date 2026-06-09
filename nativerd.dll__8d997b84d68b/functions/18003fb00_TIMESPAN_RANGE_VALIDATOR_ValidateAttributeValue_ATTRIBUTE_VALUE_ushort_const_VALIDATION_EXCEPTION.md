# TIMESPAN_RANGE_VALIDATOR::ValidateAttributeValue(ATTRIBUTE_VALUE *,ushort const *,VALIDATION_EXCEPTION * *)

- ea: `0x18003fb00`
- end: `0x18003fdb5`
- name: `?ValidateAttributeValue@TIMESPAN_RANGE_VALIDATOR@@UEAAJPEAVATTRIBUTE_VALUE@@PEBGPEAPEAVVALIDATION_EXCEPTION@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(TIMESPAN_RANGE_VALIDATOR *__hidden this, struct ATTRIBUTE_VALUE *, const unsigned __int16 *, struct VALIDATION_EXCEPTION **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180019f88`
- `0x18001c250`
- `0x18001d2fc`
- `0x18002d45c`
- `0x18003c538`
- `0x18003fb00`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `msvcrt!_i64tow_s` at `0x18003fcff`
- `msvcrt!_i64tow_s` at `0x18003fcff`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003fd7c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003fd87`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003fd7c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003fd87`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003fd1d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003fd2c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003fd1d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003fd2c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003fb6a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003fb8b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003fb6a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003fb8b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003fc9d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003fc9d`

## pseudocode

```c
__int64 __fastcall TIMESPAN_RANGE_VALIDATOR::ValidateAttributeValue(
        TIMESPAN_RANGE_VALIDATOR *this,
        struct ATTRIBUTE_VALUE *a2,
        const unsigned __int16 *a3,
        struct VALIDATION_EXCEPTION **a4)
{
  __int64 v8; // rcx
  __int64 v9; // rdx
  int String; // edi
  VALIDATION_EXCEPTION *v11; // rax
  VALIDATION_EXCEPTION *v12; // rax
  VALIDATION_EXCEPTION *v13; // rbx
  BOOL v14; // r14d
  __int64 v16; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v18[56]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[56]; // [rsp+68h] [rbp-98h] BYREF
  va_list Arguments[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v21; // [rsp+B0h] [rbp-50h]
  __int64 v22; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v23[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v24[64]; // [rsp+150h] [rbp+50h] BYREF
  wchar_t Buffer[64]; // [rsp+1D0h] [rbp+D0h] BYREF

  v22 = 0;
  *(_OWORD *)Arguments = 0;
  v21 = 0;
  memset_0(v23, 0, sizeof(v23));
  STRU::STRU((STRU *)v19, v23, 0x40u);
  memset_0(v24, 0, sizeof(v24));
  STRU::STRU((STRU *)v18, v24, 0x40u);
  if ( !a2 || !a3 || !a4 )
  {
    String = -2147024809;
    goto LABEL_29;
  }
  v8 = **((_QWORD **)a2 + 1);
  if ( (*((_BYTE *)this + 44) & 2) != 0 )
  {
    if ( v8 == 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_14;
    if ( *((_DWORD *)this + 10) == 1 )
    {
      if ( (unsigned __int64)(v8 - 21474836470000000LL) < 0x989680 )
        goto LABEL_14;
    }
    else if ( *((_DWORD *)this + 10) == 2 && (unsigned __int64)(v8 - 1288490188200000000LL) < 0x23C34600 )
    {
      goto LABEL_14;
    }
  }
  v16 = 10000000LL * *((_QWORD *)this + 2);
  v17 = 10000000LL * *((_QWORD *)this + 3);
  v9 = v8 / 10000000;
  if ( (*((_BYTE *)this + 44) & 1) != 0 )
  {
    if ( v9 <= *((_QWORD *)this + 3) && v9 >= *((_QWORD *)this + 2) )
      goto LABEL_18;
  }
  else if ( v9 > *((_QWORD *)this + 3) || v9 < *((_QWORD *)this + 2) )
  {
    goto LABEL_18;
  }
  if ( !(v9 % *((_QWORD *)this + 4)) )
  {
LABEL_14:
    String = 0;
    goto LABEL_29;
  }
LABEL_18:
  v11 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
  if ( !v11 || (v12 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v11), (v13 = v12) == 0) )
  {
    String = -2147024888;
    goto LABEL_29;
  }
  String = STRU::Copy((VALIDATION_EXCEPTION *)((char *)v12 + 96), a3);
  if ( String >= 0 )
  {
    v14 = *((_DWORD *)this + 10) != 0;
    String = ((__int64 (__fastcall *)(__int64 *, bool, _QWORD, _BYTE *))TIMESPAN_PARSER::GetString)(
               &v16,
               *((_DWORD *)this + 10) != 0,
               0,
               v19);
    if ( String >= 0 )
    {
      String = TIMESPAN_PARSER::GetString(&v17, v14, 0, v18, v16);
      if ( String >= 0 )
      {
        if ( !_i64tow_s(*((_QWORD *)this + 4), Buffer, 0x40u, 10) )
        {
          Arguments[0] = (va_list)STRU::QueryStr((STRU *)v19);
          Arguments[1] = (va_list)STRU::QueryStr((STRU *)v18);
          *(_QWORD *)&v21 = Buffer;
          AdminFormatMessage(
            (*((_DWORD *)this + 11) & 1) != 0 ? -1073739056 : -1073739077,
            Arguments,
            (VALIDATION_EXCEPTION *)((char *)v13 + 208),
            0);
          *a4 = v13;
          goto LABEL_29;
        }
        String = -2147418113;
      }
    }
  }
  VALIDATION_EXCEPTION::DereferenceValidationException(v13);
LABEL_29:
  STRU::~STRU((STRU *)v18);
  STRU::~STRU((STRU *)v19);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18003fb00  mov     [rsp-8+arg_8], rbx
0x18003fb05  push    rbp
0x18003fb06  push    rsi
0x18003fb07  push    rdi
0x18003fb08  push    r14
0x18003fb0a  push    r15
0x18003fb0c  lea     rbp, [rsp-160h]
0x18003fb14  sub     rsp, 260h
0x18003fb1b  mov     rax, cs:__security_cookie
0x18003fb22  xor     rax, rsp
0x18003fb25  mov     [rbp+180h+var_30], rax
0x18003fb2c  xorps   xmm0, xmm0
0x18003fb2f  mov     rdi, r8
0x18003fb32  mov     rbx, rdx
0x18003fb35  mov     rsi, rcx
0x18003fb38  xor     eax, eax
0x18003fb3a  lea     rcx, [rbp+180h+var_1B0]; void *
0x18003fb3e  mov     r14d, 80h
0x18003fb44  mov     [rbp+180h+var_1C0], rax
0x18003fb48  mov     r8d, r14d; Size
0x18003fb4b  xor     edx, edx; Val
0x18003fb4d  mov     r15, r9
0x18003fb50  movups  xmmword ptr [rbp+180h+Arguments], xmm0
0x18003fb54  movups  [rbp+180h+var_1D0], xmm0
0x18003fb58  call    memset_0
0x18003fb5d  lea     r8d, [r14-40h]
0x18003fb61  lea     rdx, [rbp+180h+var_1B0]
0x18003fb65  lea     rcx, [rsp+280h+var_218]
0x18003fb6a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18003fb70  mov     r8d, r14d; Size
0x18003fb73  lea     rcx, [rbp+180h+var_130]; void *
0x18003fb77  xor     edx, edx; Val
0x18003fb79  call    memset_0
0x18003fb7e  lea     r8d, [r14-40h]
0x18003fb82  lea     rdx, [rbp+180h+var_130]
0x18003fb86  lea     rcx, [rsp+280h+var_250]
0x18003fb8b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18003fb91  test    rbx, rbx
0x18003fb94  jz      loc_18003FD72
0x18003fb9a  test    rdi, rdi
0x18003fb9d  jz      loc_18003FD72
0x18003fba3  test    r15, r15
0x18003fba6  jz      loc_18003FD72
0x18003fbac  test    byte ptr [rsi+2Ch], 2
0x18003fbb0  mov     rax, [rbx+8]
0x18003fbb4  mov     rcx, [rax]
0x18003fbb7  jz      short loc_18003FBE7
0x18003fbb9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003fbc3  cmp     rcx, rax
0x18003fbc6  jz      loc_18003FC4E
0x18003fbcc  cmp     dword ptr [rsi+28h], 1
0x18003fbd0  jnz     short loc_18003FC33
0x18003fbd2  mov     rax, 0FFB3B4C000989680h
0x18003fbdc  add     rax, rcx
0x18003fbdf  cmp     rax, 989680h
0x18003fbe5  jb      short loc_18003FC4E
0x18003fbe7  imul    rax, [rsi+10h], 989680h
0x18003fbef  mov     [rsp+280h+var_260], rax
0x18003fbf4  imul    rax, [rsi+18h], 989680h
0x18003fbfc  mov     [rsp+280h+var_258], rax
0x18003fc01  mov     rax, 0D6BF94D5E57A42BDh
0x18003fc0b  imul    rcx
0x18003fc0e  add     rdx, rcx
0x18003fc11  sar     rdx, 17h
0x18003fc15  mov     rax, rdx
0x18003fc18  shr     rax, 3Fh
0x18003fc1c  add     rdx, rax
0x18003fc1f  test    byte ptr [rsi+2Ch], 1
0x18003fc23  jnz     short loc_18003FC55
0x18003fc25  cmp     rdx, [rsi+18h]
0x18003fc29  jg      short loc_18003FC6F
0x18003fc2b  cmp     rdx, [rsi+10h]
0x18003fc2f  jge     short loc_18003FC61
0x18003fc31  jmp     short loc_18003FC6F
0x18003fc33  cmp     dword ptr [rsi+28h], 2
0x18003fc37  jnz     short loc_18003FBE7
0x18003fc39  mov     rax, 0EE1E5D0023C34600h
0x18003fc43  add     rax, rcx
0x18003fc46  cmp     rax, 23C34600h
0x18003fc4c  jnb     short loc_18003FBE7
0x18003fc4e  xor     edi, edi
0x18003fc50  jmp     loc_18003FD77
0x18003fc55  cmp     rdx, [rsi+18h]
0x18003fc59  jg      short loc_18003FC61
0x18003fc5b  cmp     rdx, [rsi+10h]
0x18003fc5f  jge     short loc_18003FC6F
0x18003fc61  mov     rax, rdx
0x18003fc64  cqo
0x18003fc66  idiv    qword ptr [rsi+20h]
0x18003fc6a  test    rdx, rdx
0x18003fc6d  jz      short loc_18003FC4E
0x18003fc6f  mov     ecx, 1E8h; Size
0x18003fc74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003fc79  test    rax, rax
0x18003fc7c  jz      loc_18003FD6B
0x18003fc82  mov     rcx, rax; this
0x18003fc85  call    ??0VALIDATION_EXCEPTION@@QEAA@XZ; VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(void)
0x18003fc8a  mov     rbx, rax
0x18003fc8d  test    rax, rax
0x18003fc90  jz      loc_18003FD6B
0x18003fc96  lea     rcx, [rax+60h]
0x18003fc9a  mov     rdx, rdi
0x18003fc9d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003fca3  mov     edi, eax
0x18003fca5  test    eax, eax
0x18003fca7  js      short loc_18003FD0E
0x18003fca9  xor     r14d, r14d
0x18003fcac  lea     r9, [rsp+280h+var_218]
0x18003fcb1  cmp     [rsi+28h], r14d
0x18003fcb5  lea     rcx, [rsp+280h+var_260]
0x18003fcba  setnz   r14b
0x18003fcbe  xor     r8d, r8d
0x18003fcc1  mov     edx, r14d
0x18003fcc4  call    ?GetString@TIMESPAN_PARSER@@QEAAJW4TIMESPAN_FORMAT@@HPEAVSTRU@@@Z; TIMESPAN_PARSER::GetString(TIMESPAN_FORMAT,int,STRU *)
0x18003fcc9  mov     edi, eax
0x18003fccb  test    eax, eax
0x18003fccd  js      short loc_18003FD0E
0x18003fccf  lea     r9, [rsp+280h+var_250]
0x18003fcd4  xor     r8d, r8d
0x18003fcd7  mov     edx, r14d
0x18003fcda  lea     rcx, [rsp+280h+var_258]
0x18003fcdf  call    ?GetString@TIMESPAN_PARSER@@QEAAJW4TIMESPAN_FORMAT@@HPEAVSTRU@@@Z; TIMESPAN_PARSER::GetString(TIMESPAN_FORMAT,int,STRU *)
0x18003fce4  mov     edi, eax
0x18003fce6  test    eax, eax
0x18003fce8  js      short loc_18003FD0E
0x18003fcea  mov     rcx, [rsi+20h]; Value
0x18003fcee  lea     rdx, [rbp+180h+Buffer]; Buffer
0x18003fcf5  mov     r9d, 0Ah; Radix
0x18003fcfb  lea     r8d, [r9+36h]; BufferCount
0x18003fcff  call    cs:__imp__i64tow_s
0x18003fd05  test    eax, eax
0x18003fd07  jz      short loc_18003FD18
0x18003fd09  mov     edi, 8000FFFFh
0x18003fd0e  mov     rcx, rbx; this
0x18003fd11  call    ?DereferenceValidationException@VALIDATION_EXCEPTION@@QEAAXXZ; VALIDATION_EXCEPTION::DereferenceValidationException(void)
0x18003fd16  jmp     short loc_18003FD77
0x18003fd18  lea     rcx, [rsp+280h+var_218]
0x18003fd1d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18003fd23  lea     rcx, [rsp+280h+var_250]
0x18003fd28  mov     [rbp+180h+Arguments], rax
0x18003fd2c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18003fd32  mov     [rbp+180h+Arguments+8], rax
0x18003fd36  lea     r8, [rbx+0D0h]; struct STRU *
0x18003fd3d  lea     rax, [rbp+180h+Buffer]
0x18003fd44  mov     qword ptr [rbp+180h+var_1D0], rax
0x18003fd48  lea     rdx, [rbp+180h+Arguments]; Arguments
0x18003fd4c  mov     eax, [rsi+2Ch]
0x18003fd4f  and     al, 1
0x18003fd51  neg     al
0x18003fd53  sbb     ecx, ecx
0x18003fd55  xor     r9d, r9d; struct SMALL_STRU *
0x18003fd58  and     ecx, 15h
0x18003fd5b  add     ecx, 0C0000ABBh; dwMessageId
0x18003fd61  call    ?AdminFormatMessage@@YAJKQEAPEBDPEAVSTRU@@PEAVSMALL_STRU@@@Z; AdminFormatMessage(ulong,char const * * const,STRU *,SMALL_STRU *)
0x18003fd66  mov     [r15], rbx
0x18003fd69  jmp     short loc_18003FD77
0x18003fd6b  mov     edi, 80070008h
0x18003fd70  jmp     short loc_18003FD77
0x18003fd72  mov     edi, 80070057h
0x18003fd77  lea     rcx, [rsp+280h+var_250]
0x18003fd7c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18003fd82  lea     rcx, [rsp+280h+var_218]
0x18003fd87  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18003fd8d  mov     eax, edi
0x18003fd8f  mov     rcx, [rbp+180h+var_30]
0x18003fd96  xor     rcx, rsp; StackCookie
0x18003fd99  call    __security_check_cookie
0x18003fd9e  mov     rbx, [rsp+280h+arg_8]
0x18003fda6  add     rsp, 260h
0x18003fdad  pop     r15
0x18003fdaf  pop     r14
0x18003fdb1  pop     rdi
0x18003fdb2  pop     rsi
0x18003fdb3  pop     rbp
0x18003fdb4  retn
```

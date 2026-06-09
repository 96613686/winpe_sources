# W3_REQUEST::GetHeader(char const *,ushort *)

- ea: `0x180010240`
- end: `0x180010419`
- name: `?GetHeader@W3_REQUEST@@QEBAPEBDPEBDPEAG@Z`
- size: `473`
- prototype: `const char *__fastcall(W3_REQUEST *__hidden this, const char *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180010230`
- `0x1800185e0`
- `0x180020860`

## callees

- `0x180010240`
- `0x180010420`
- `0x1800159e0`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180010323`
- `msvcrt!_stricmp` at `0x180010323`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180010290`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180010290`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800102d2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180010306`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800102d2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180010306`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180010359`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180010359`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800103b0`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800103b0`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180010377`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180010397`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180010377`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180010397`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x1800103ea`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x1800103ea`

## pseudocode

```c
const char *__fastcall W3_REQUEST::GetHeader(W3_REQUEST *this, const char *a2, unsigned __int16 *a3)
{
  __int64 v3; // r15
  enum _HTTP_HEADER_ID Index; // eax
  const char *Header; // rbx
  int v9; // r14d
  __int64 i; // rdi
  __int64 v12; // rax
  unsigned int CCH; // eax
  __int64 v14; // rcx
  char *v15; // rax
  unsigned int v16; // [rsp+20h] [rbp-79h] BYREF
  W3_REQUEST *v17; // [rsp+28h] [rbp-71h]
  _BYTE v18[64]; // [rsp+30h] [rbp-69h] BYREF
  char v19[64]; // [rsp+70h] [rbp-29h] BYREF

  v3 = *((_QWORD *)this + 5);
  v17 = this;
  v16 = 0;
  STRA::STRA((STRA *)v18, v19, 0x40u);
  if ( a2 )
  {
    Index = REQUEST_HEADER_HASH::GetIndex(a2);
    if ( Index != -1 )
    {
      Header = W3_REQUEST::QueryHeader(this, Index, a3);
LABEL_8:
      STRA::~STRA((STRA *)v18);
      return Header;
    }
    Header = 0;
    v9 = 0;
    for ( i = 0; (unsigned int)i < *(unsigned __int16 *)(v3 + 120); i = (unsigned int)(i + 1) )
    {
      if ( !_stricmp(a2, *(const char **)(*(_QWORD *)(v3 + 128) + 24 * i + 8)) )
      {
        if ( Header )
        {
          if ( !v9 && (int)STRA::Copy((STRA *)v18, Header, v16) < 0 )
            goto LABEL_9;
          v9 = 1;
          if ( (int)STRA::Append((STRA *)v18, ",", 1u) < 0
            || (int)STRA::Append(
                      (STRA *)v18,
                      *(const char **)(*(_QWORD *)(v3 + 128) + 24 * i + 16),
                      *(unsigned __int16 *)(*(_QWORD *)(v3 + 128) + 24 * i + 2)) < 0 )
          {
            goto LABEL_9;
          }
        }
        else
        {
          v12 = *(_QWORD *)(v3 + 128);
          Header = *(const char **)(v12 + 24 * i + 16);
          v16 = *(unsigned __int16 *)(v12 + 24 * i + 2);
        }
      }
    }
    if ( !v9 )
    {
LABEL_6:
      if ( a3 )
        *a3 = v16;
      goto LABEL_8;
    }
    CCH = STRA::QueryCCH((STRA *)v18);
    v14 = *((_QWORD *)v17 + 14);
    v16 = CCH + 1;
    v15 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 144LL))(v14);
    Header = v15;
    if ( v15 )
    {
      STRA::CopyToBuffer((STRA *)v18, v15, &v16);
      --v16;
      goto LABEL_6;
    }
  }
LABEL_9:
  STRA::~STRA((STRA *)v18);
  return 0;
}

```

## disassembly

```asm
0x180010240  mov     [rsp-8+arg_18], rbx
0x180010245  push    rbp
0x180010246  push    rsi
0x180010247  push    rdi
0x180010248  push    r12
0x18001024a  push    r13
0x18001024c  push    r14
0x18001024e  push    r15
0x180010250  lea     rbp, [rsp-27h]
0x180010255  sub     rsp, 0C0h
0x18001025c  mov     rax, cs:__security_cookie
0x180010263  xor     rax, rsp
0x180010266  mov     [rbp+57h+var_40], rax
0x18001026a  mov     r15, [rcx+28h]
0x18001026e  mov     rsi, r8
0x180010271  mov     r13, rdx
0x180010274  mov     [rbp+57h+var_C8], rcx
0x180010278  mov     r12, rcx
0x18001027b  mov     [rbp+57h+var_D0], 0
0x180010282  mov     r8d, 40h ; '@'
0x180010288  lea     rdx, [rbp+57h+var_80]
0x18001028c  lea     rcx, [rbp+57h+var_C0]
0x180010290  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180010296  test    r13, r13
0x180010299  jz      short loc_180010302
0x18001029b  mov     rcx, r13; char *
0x18001029e  call    ?GetIndex@REQUEST_HEADER_HASH@@SAKPEBD@Z; REQUEST_HEADER_HASH::GetIndex(char const *)
0x1800102a3  cmp     eax, 0FFFFFFFFh
0x1800102a6  jnz     loc_180010404
0x1800102ac  xor     ebx, ebx
0x1800102ae  xor     r14d, r14d
0x1800102b1  xor     edi, edi
0x1800102b3  movzx   eax, word ptr [r15+78h]
0x1800102b8  cmp     edi, eax
0x1800102ba  jb      short loc_180010310
0x1800102bc  test    r14d, r14d
0x1800102bf  jnz     loc_1800103AC
0x1800102c5  test    rsi, rsi
0x1800102c8  jnz     loc_1800103F8
0x1800102ce  lea     rcx, [rbp+57h+var_C0]
0x1800102d2  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800102d8  mov     rax, rbx
0x1800102db  mov     rcx, [rbp+57h+var_40]
0x1800102df  xor     rcx, rsp; StackCookie
0x1800102e2  call    __security_check_cookie
0x1800102e7  mov     rbx, [rsp+0F0h+arg_18]
0x1800102ef  add     rsp, 0C0h
0x1800102f6  pop     r15
0x1800102f8  pop     r14
0x1800102fa  pop     r13
0x1800102fc  pop     r12
0x1800102fe  pop     rdi
0x1800102ff  pop     rsi
0x180010300  pop     rbp
0x180010301  retn
0x180010302  lea     rcx, [rbp+57h+var_C0]
0x180010306  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001030c  xor     eax, eax
0x18001030e  jmp     short loc_1800102DB
0x180010310  mov     rdx, [r15+80h]
0x180010317  lea     r12, [rdi+rdi*2]
0x18001031b  mov     rcx, r13; String1
0x18001031e  mov     rdx, [rdx+r12*8+8]; String2
0x180010323  call    cs:__imp__stricmp
0x180010329  test    eax, eax
0x18001032b  jnz     short loc_1800103A5
0x18001032d  test    rbx, rbx
0x180010330  jnz     short loc_180010349
0x180010332  mov     rax, [r15+80h]
0x180010339  mov     rbx, [rax+r12*8+10h]
0x18001033e  movzx   eax, word ptr [rax+r12*8+2]
0x180010344  mov     [rbp+57h+var_D0], eax
0x180010347  jmp     short loc_1800103A5
0x180010349  test    r14d, r14d
0x18001034c  jnz     short loc_180010363
0x18001034e  mov     r8d, [rbp+57h+var_D0]
0x180010352  lea     rcx, [rbp+57h+var_C0]
0x180010356  mov     rdx, rbx
0x180010359  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18001035f  test    eax, eax
0x180010361  js      short loc_180010302
0x180010363  mov     r14d, 1
0x180010369  lea     rdx, asc_180039188; ","
0x180010370  mov     r8d, r14d
0x180010373  lea     rcx, [rbp+57h+var_C0]
0x180010377  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18001037d  test    eax, eax
0x18001037f  js      short loc_180010302
0x180010381  mov     rdx, [r15+80h]
0x180010388  lea     rcx, [rbp+57h+var_C0]
0x18001038c  movzx   r8d, word ptr [rdx+r12*8+2]
0x180010392  mov     rdx, [rdx+r12*8+10h]
0x180010397  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18001039d  test    eax, eax
0x18001039f  js      loc_180010302
0x1800103a5  inc     edi
0x1800103a7  jmp     loc_1800102B3
0x1800103ac  lea     rcx, [rbp+57h+var_C0]
0x1800103b0  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800103b6  mov     rcx, [rbp+57h+var_C8]
0x1800103ba  lea     edx, [rax+1]
0x1800103bd  mov     rcx, [rcx+70h]
0x1800103c1  mov     [rbp+57h+var_D0], edx
0x1800103c4  mov     rax, [rcx]
0x1800103c7  mov     rax, [rax+90h]
0x1800103ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103d3  mov     rbx, rax
0x1800103d6  test    rax, rax
0x1800103d9  jz      loc_180010302
0x1800103df  lea     r8, [rbp+57h+var_D0]
0x1800103e3  mov     rdx, rax
0x1800103e6  lea     rcx, [rbp+57h+var_C0]
0x1800103ea  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x1800103f0  dec     [rbp+57h+var_D0]
0x1800103f3  jmp     loc_1800102C5
0x1800103f8  movzx   ecx, word ptr [rbp+57h+var_D0]
0x1800103fc  mov     [rsi], cx
0x1800103ff  jmp     loc_1800102CE
0x180010404  mov     r8, rsi; unsigned __int16 *
0x180010407  mov     edx, eax; enum _HTTP_HEADER_ID
0x180010409  mov     rcx, r12; this
0x18001040c  call    ?QueryHeader@W3_REQUEST@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_REQUEST::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x180010411  mov     rbx, rax
0x180010414  jmp     loc_1800102CE
```

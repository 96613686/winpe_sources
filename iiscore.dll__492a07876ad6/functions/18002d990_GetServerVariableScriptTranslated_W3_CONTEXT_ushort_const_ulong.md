# GetServerVariableScriptTranslated(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x18002d990`
- end: `0x18002dae9`
- name: `?GetServerVariableScriptTranslated@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `345`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002d990`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18002dab6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002dab6`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002da39`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002da92`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002da39`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002da92`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002d9dd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002d9dd`
- `iisutil!MakePathCanonicalizationProof` at `0x18002da22`
- `iisutil!MakePathCanonicalizationProof` at `0x18002da22`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002da7e`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002da7e`

## pseudocode

```c
__int64 __fastcall GetServerVariableScriptTranslated(
        struct W3_CONTEXT *a1,
        const unsigned __int16 **a2,
        unsigned int *a3)
{
  const unsigned __int16 *v6; // rax
  int PathCanonicalizationProof; // ebx
  unsigned int v8; // edx
  __int64 v9; // rax
  unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // rbx
  unsigned int CCH; // eax
  unsigned int v14; // [rsp+20h] [rbp-168h] BYREF
  _BYTE v15[56]; // [rsp+28h] [rbp-160h] BYREF
  unsigned __int16 v16[128]; // [rsp+60h] [rbp-128h] BYREF

  memset_0(v16, 0, sizeof(v16));
  STRU::STRU((STRU *)v15, v16, 0x80u);
  if ( !(*(__int64 (__fastcall **)(struct W3_CONTEXT *, _QWORD))(*(_QWORD *)a1 + 184LL))(a1, 0) )
  {
    *a2 = &dword_18003C134;
    CCH = 0;
    goto LABEL_7;
  }
  v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *, _QWORD))(*(_QWORD *)a1 + 184LL))(a1, 0);
  PathCanonicalizationProof = MakePathCanonicalizationProof(v6, (struct STRU *)v15);
  if ( PathCanonicalizationProof >= 0 )
  {
    v8 = 2 * STRU::QueryCCH((STRU *)v15) + 2;
    v9 = *(_QWORD *)a1;
    v14 = v8;
    v10 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *))(v9 + 144))(a1);
    v11 = v10;
    if ( !v10 )
    {
      PathCanonicalizationProof = -2147024888;
      goto LABEL_8;
    }
    STRU::CopyToBuffer((STRU *)v15, v10, &v14);
    *a2 = v11;
    CCH = STRU::QueryCCH((STRU *)v15);
LABEL_7:
    *a3 = CCH;
    PathCanonicalizationProof = 0;
  }
LABEL_8:
  STRU::~STRU((STRU *)v15);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x18002d990  mov     [rsp+arg_18], rbx
0x18002d995  push    rsi
0x18002d996  push    rdi
0x18002d997  push    r14
0x18002d999  sub     rsp, 170h
0x18002d9a0  mov     rax, cs:__security_cookie
0x18002d9a7  xor     rax, rsp
0x18002d9aa  mov     [rsp+188h+var_28], rax
0x18002d9b2  mov     r14, r8
0x18002d9b5  mov     rsi, rdx
0x18002d9b8  mov     rdi, rcx
0x18002d9bb  xor     edx, edx; Val
0x18002d9bd  mov     r8d, 100h; Size
0x18002d9c3  lea     rcx, [rsp+188h+var_128]; void *
0x18002d9c8  call    memset_0
0x18002d9cd  mov     r8d, 80h
0x18002d9d3  lea     rdx, [rsp+188h+var_128]
0x18002d9d8  lea     rcx, [rsp+188h+var_160]
0x18002d9dd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002d9e4  nop     dword ptr [rax+rax+00h]
0x18002d9e9  mov     rax, [rdi]
0x18002d9ec  xor     edx, edx
0x18002d9ee  mov     rcx, rdi
0x18002d9f1  mov     rax, [rax+0B8h]
0x18002d9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9fd  test    rax, rax
0x18002da00  jz      loc_18002DAA0
0x18002da06  mov     rax, [rdi]
0x18002da09  xor     edx, edx
0x18002da0b  mov     rcx, rdi
0x18002da0e  mov     rax, [rax+0B8h]
0x18002da15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da1a  mov     rcx, rax
0x18002da1d  lea     rdx, [rsp+188h+var_160]
0x18002da22  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002da29  nop     dword ptr [rax+rax+00h]
0x18002da2e  mov     ebx, eax
0x18002da30  test    eax, eax
0x18002da32  js      short loc_18002DAB1
0x18002da34  lea     rcx, [rsp+188h+var_160]
0x18002da39  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002da40  nop     dword ptr [rax+rax+00h]
0x18002da45  mov     rcx, rdi
0x18002da48  lea     edx, ds:2[rax*2]
0x18002da4f  mov     rax, [rdi]
0x18002da52  mov     [rsp+188h+var_168], edx
0x18002da56  mov     rax, [rax+90h]
0x18002da5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da62  mov     rbx, rax
0x18002da65  test    rax, rax
0x18002da68  jnz     short loc_18002DA71
0x18002da6a  mov     ebx, 80070008h
0x18002da6f  jmp     short loc_18002DAB1
0x18002da71  lea     r8, [rsp+188h+var_168]
0x18002da76  mov     rdx, rbx
0x18002da79  lea     rcx, [rsp+188h+var_160]
0x18002da7e  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18002da85  nop     dword ptr [rax+rax+00h]
0x18002da8a  lea     rcx, [rsp+188h+var_160]
0x18002da8f  mov     [rsi], rbx
0x18002da92  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002da99  nop     dword ptr [rax+rax+00h]
0x18002da9e  jmp     short loc_18002DAAC
0x18002daa0  lea     rax, dword_18003C134
0x18002daa7  mov     [rsi], rax
0x18002daaa  xor     eax, eax
0x18002daac  mov     [r14], eax
0x18002daaf  xor     ebx, ebx
0x18002dab1  lea     rcx, [rsp+188h+var_160]
0x18002dab6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002dabd  nop     dword ptr [rax+rax+00h]
0x18002dac2  mov     eax, ebx
0x18002dac4  mov     rcx, [rsp+188h+var_28]
0x18002dacc  xor     rcx, rsp; StackCookie
0x18002dacf  call    __security_check_cookie
0x18002dad4  mov     rbx, [rsp+188h+arg_18]
0x18002dadc  add     rsp, 170h
0x18002dae3  pop     r14
0x18002dae5  pop     rdi
0x18002dae6  pop     rsi
0x18002dae7  retn
```

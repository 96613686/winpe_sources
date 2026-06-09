# GetServerVariableScriptTranslated(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x18002b310`
- end: `0x18002b444`
- name: `?GetServerVariableScriptTranslated@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `308`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002b310`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18002b418`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002b418`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002b3ad`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002b3fa`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002b3ad`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002b3fa`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002b35d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002b35d`
- `iisutil!MakePathCanonicalizationProof` at `0x18002b39c`
- `iisutil!MakePathCanonicalizationProof` at `0x18002b39c`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002b3ec`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002b3ec`

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
    *a2 = &dword_180039134;
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
0x18002b310  mov     [rsp+arg_18], rbx
0x18002b315  push    rsi
0x18002b316  push    rdi
0x18002b317  push    r14
0x18002b319  sub     rsp, 170h
0x18002b320  mov     rax, cs:__security_cookie
0x18002b327  xor     rax, rsp
0x18002b32a  mov     [rsp+188h+var_28], rax
0x18002b332  mov     r14, r8
0x18002b335  mov     rsi, rdx
0x18002b338  mov     rdi, rcx
0x18002b33b  xor     edx, edx; Val
0x18002b33d  mov     r8d, 100h; Size
0x18002b343  lea     rcx, [rsp+188h+var_128]; void *
0x18002b348  call    memset_0
0x18002b34d  mov     r8d, 80h
0x18002b353  lea     rdx, [rsp+188h+var_128]
0x18002b358  lea     rcx, [rsp+188h+var_160]
0x18002b35d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002b363  mov     rax, [rdi]
0x18002b366  xor     edx, edx
0x18002b368  mov     rcx, rdi
0x18002b36b  mov     rax, [rax+0B8h]
0x18002b372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b377  test    rax, rax
0x18002b37a  jz      loc_18002B402
0x18002b380  mov     rax, [rdi]
0x18002b383  xor     edx, edx
0x18002b385  mov     rcx, rdi
0x18002b388  mov     rax, [rax+0B8h]
0x18002b38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b394  mov     rcx, rax
0x18002b397  lea     rdx, [rsp+188h+var_160]
0x18002b39c  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002b3a2  mov     ebx, eax
0x18002b3a4  test    eax, eax
0x18002b3a6  js      short loc_18002B413
0x18002b3a8  lea     rcx, [rsp+188h+var_160]
0x18002b3ad  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002b3b3  mov     rcx, rdi
0x18002b3b6  lea     edx, ds:2[rax*2]
0x18002b3bd  mov     rax, [rdi]
0x18002b3c0  mov     [rsp+188h+var_168], edx
0x18002b3c4  mov     rax, [rax+90h]
0x18002b3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3d0  mov     rbx, rax
0x18002b3d3  test    rax, rax
0x18002b3d6  jnz     short loc_18002B3DF
0x18002b3d8  mov     ebx, 80070008h
0x18002b3dd  jmp     short loc_18002B413
0x18002b3df  lea     r8, [rsp+188h+var_168]
0x18002b3e4  mov     rdx, rbx
0x18002b3e7  lea     rcx, [rsp+188h+var_160]
0x18002b3ec  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18002b3f2  lea     rcx, [rsp+188h+var_160]
0x18002b3f7  mov     [rsi], rbx
0x18002b3fa  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002b400  jmp     short loc_18002B40E
0x18002b402  lea     rax, dword_180039134
0x18002b409  mov     [rsi], rax
0x18002b40c  xor     eax, eax
0x18002b40e  mov     [r14], eax
0x18002b411  xor     ebx, ebx
0x18002b413  lea     rcx, [rsp+188h+var_160]
0x18002b418  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002b41e  mov     eax, ebx
0x18002b420  mov     rcx, [rsp+188h+var_28]
0x18002b428  xor     rcx, rsp; StackCookie
0x18002b42b  call    __security_check_cookie
0x18002b430  mov     rbx, [rsp+188h+arg_18]
0x18002b438  add     rsp, 170h
0x18002b43f  pop     r14
0x18002b441  pop     rdi
0x18002b442  pop     rsi
0x18002b443  retn
```

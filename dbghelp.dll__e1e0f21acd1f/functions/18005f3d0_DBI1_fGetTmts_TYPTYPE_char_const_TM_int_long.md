# DBI1::fGetTmts(TYPTYPE *,char const *,TM * *,int,long &)

- ea: `0x18005f3d0`
- end: `0x18005f818`
- name: `?fGetTmts@DBI1@@AEAAHPEAUTYPTYPE@@PEBDPEAPEAVTM@@HAEAJ@Z`
- size: `1096`
- prototype: `__int64 __usercall@<rax>(DBI1 *__hidden this@<rcx>, struct TYPTYPE *@<rdx>, const char *@<r8>, struct TM **@<r9>, int, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x18006bef0`

## callees

- `0x180026980`
- `0x1800269f8`
- `0x180029c40`
- `0x18002c3e0`
- `0x180031a80`
- `0x180034890`
- `0x1800348d0`
- `0x180038b30`
- `0x180038b90`
- `0x18005b890`
- `0x18005e640`
- `0x18005f3d0`
- `0x180061470`
- `0x180169420`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005f581`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005f581`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DBI1::fGetTmts(DBI1 *this, struct TYPTYPE *a2, char *a3, struct TM **a4, int a5, int *a6)
{
  void **v8; // rcx
  unsigned int v9; // edi
  unsigned __int64 v10; // rax
  WCHAR *v11; // r15
  wchar_t *v12; // r12
  __int64 v13; // rax
  __int16 v14; // cx
  const wchar_t *v15; // rax
  wchar_t *v16; // r15
  const wchar_t *PDBMapping; // rax
  const wchar_t *v18; // rbx
  unsigned int v19; // r14d
  unsigned int v20; // r12d
  int LastErrorCurrentThread; // eax
  __int64 v22; // rax
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // kr00_8
  char *v25; // rax
  char *v26; // r12
  PSGSI1::EnumPubsByAddr *v27; // rbx
  char *v28; // rax
  struct TM *v29; // rdx
  struct TM **v30; // rsi
  PSGSI1::EnumPubsByAddr *v31; // rbx
  PSGSI1::EnumPubsByAddr *v32; // rcx
  unsigned int v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-ACh]
  wchar_t *v36; // [rsp+58h] [rbp-A8h]
  struct TM **v37; // [rsp+60h] [rbp-A0h]
  char *v38; // [rsp+68h] [rbp-98h]
  __int64 v39; // [rsp+70h] [rbp-90h]
  struct _GUID v40; // [rsp+80h] [rbp-80h] BYREF
  void **v41; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v42; // [rsp+98h] [rbp-68h]
  PSGSI1::EnumPubsByAddr *v43; // [rsp+A0h] [rbp-60h]
  WCHAR WideCharStr[268]; // [rsp+A8h] [rbp-58h] BYREF

  v39 = -2;
  v37 = a4;
  v38 = a3;
  v36 = (wchar_t *)this;
  v8 = &SafeStackAllocator<528>::`vftable';
  v41 = &SafeStackAllocator<528>::`vftable';
  v9 = 0;
  v43 = 0;
  v42 = 0;
  v10 = (2LL * *(unsigned __int16 *)a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( v10 > 0x210 )
  {
    v11 = (WCHAR *)SafeStackAllocator<528>::AllocInHeap(&v41);
    v10 = v42;
    v8 = v41;
  }
  else
  {
    v11 = WideCharStr;
    v42 = (2LL * *(unsigned __int16 *)a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  }
  if ( *v8 == SafeStackAllocator<528>::AllocBytes )
  {
    if ( 528 - v10 >= 0x208 )
    {
      v12 = (WCHAR *)((char *)WideCharStr + v10);
      v42 = v10 + 520;
      goto LABEL_10;
    }
    v13 = SafeStackAllocator<528>::AllocInHeap(&v41);
  }
  else
  {
    v13 = ((__int64 (__fastcall *)(void ***, __int64))*v8)(&v41, 520);
  }
  v12 = (wchar_t *)v13;
LABEL_10:
  if ( !v11
    || !v12
    || ((v14 = *((_WORD *)a2 + 1), v14 != 5397)
      ? ((v40 = 0, v40.Data1 = *((_DWORD *)a2 + 1), v14 == 5377) || v14 == 22
       ? (v35 = *((_DWORD *)a2 + 2))
       : (v35 = -1))
      : (v40 = *(struct _GUID *)((char *)a2 + 4), v35 = *((_DWORD *)a2 + 5)),
        v15 = (const wchar_t *)SZNameFromTSRecord(a2, v11, *(unsigned __int16 *)a2),
        (v16 = (wchar_t *)v15) == 0) )
  {
    *a6 = 2;
    PDB1::setOOMError(*((PDB1 **)this + 18));
    goto LABEL_44;
  }
  PDBMapping = PDB1::QueryPDBMapping(*((PDB1 **)this + 18), v15);
  v18 = PDBMapping;
  v19 = 1;
  if ( !PDBMapping )
  {
    v34 = 0;
    *v12 = 0;
    goto LABEL_23;
  }
  if ( !_wfullpath(v12, PDBMapping, 0x104u) )
  {
    *a6 = 3;
    PDB1::setLastError(*((PDB1 **)this + 18), 3, v18);
LABEL_44:
    v19 = 0;
    goto LABEL_45;
  }
  v34 = 1;
  v36 = v16;
  v16 = v12;
LABEL_23:
  if ( (unsigned int)DBI1::fFindTm(this, *((struct OTM **)this + 19), v16, &v40, v35, 0, v37, 0, a6) )
  {
LABEL_45:
    v9 = v19;
    goto LABEL_46;
  }
  if ( a5 )
  {
LABEL_46:
    v19 = v9;
    goto LABEL_47;
  }
  v20 = v34;
  if ( !(unsigned int)DBI1::fOpenTmts(this, v16, &v40, v35, v38, v37, &v34, v34, a6) )
  {
    if ( v20 && PDB1::FIsLinkerTempFile(v16) )
    {
      LastErrorCurrentThread = PDB1::QueryLastErrorCurrentThread(*((PDB1 **)this + 18), 0, 0);
      *a6 = LastErrorCurrentThread;
      PDB1::setLastError(*((PDB1 **)this + 18), LastErrorCurrentThread, v36);
    }
    goto LABEL_46;
  }
  v22 = -1;
  do
    ++v22;
  while ( v16[v22] );
  v36 = (wchar_t *)(v22 + 1);
  v24 = v22 + 1;
  v23 = 2 * (v22 + 1);
  if ( !is_mul_ok(v24, 2u) )
    v23 = -1;
  v25 = (char *)operator new[](v23, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v25;
  v27 = (PSGSI1::EnumPubsByAddr *)v25;
  v38 = v25;
  if ( !v25 )
    goto LABEL_37;
  memcpy_0(v25, v16, 2LL * (_QWORD)v36);
  v28 = (char *)operator new(0x48u, *((struct PDB1 **)this + 18));
  v36 = (wchar_t *)v28;
  if ( !v28 )
  {
    *((_QWORD *)this + 19) = 0;
LABEL_37:
    *a6 = 2;
    PDB1::setOOMError(*((PDB1 **)this + 18));
    v30 = v37;
    if ( *v37 )
      (*(void (__fastcall **)(struct TM *, __int64))(*(_QWORD *)*v37 + 24LL))(*v37, 1);
    *v30 = 0;
    v19 = 0;
    goto LABEL_40;
  }
  v29 = *v37;
  *(_QWORD *)v28 = *((_QWORD *)this + 19);
  *(struct _GUID *)(v28 + 8) = v40;
  v27 = 0;
  v38 = 0;
  *((_QWORD *)v28 + 3) = v26;
  *((_QWORD *)v28 + 4) = 0;
  *((_QWORD *)v28 + 5) = 0;
  *((_QWORD *)v28 + 6) = 0;
  *((_QWORD *)v28 + 7) = v29;
  *((_DWORD *)v28 + 16) = 0;
  *((_DWORD *)v28 + 17) = v34;
  *((_QWORD *)this + 19) = v28;
LABEL_40:
  if ( v27 )
    PSGSI1::EnumPubsByAddr::release(v27);
LABEL_47:
  v41 = &SafeStackAllocator<528>::`vftable';
  v31 = v43;
  while ( v31 )
  {
    v32 = v31;
    v31 = *(PSGSI1::EnumPubsByAddr **)v31;
    PSGSI1::EnumPubsByAddr::release(v32);
  }
  return v19;
}

```

## disassembly

```asm
0x18005f3d0  push    rbp
0x18005f3d2  push    rbx
0x18005f3d3  push    rsi
0x18005f3d4  push    rdi
0x18005f3d5  push    r12
0x18005f3d7  push    r13
0x18005f3d9  push    r14
0x18005f3db  push    r15
0x18005f3dd  lea     rbp, [rsp-1D8h]
0x18005f3e5  sub     rsp, 2D8h
0x18005f3ec  mov     [rsp+310h+var_2A0], 0FFFFFFFFFFFFFFFEh
0x18005f3f5  mov     rax, cs:__security_cookie
0x18005f3fc  xor     rax, rsp
0x18005f3ff  mov     [rbp+210h+var_50], rax
0x18005f406  mov     [rsp+310h+var_2B0], r9
0x18005f40b  mov     [rsp+310h+var_2A8], r8
0x18005f410  mov     rbx, rdx
0x18005f413  mov     rsi, rcx
0x18005f416  mov     [rsp+310h+var_2B8], rcx
0x18005f41b  mov     r13, [rbp+210h+arg_28]
0x18005f422  lea     rax, ??_7?$SafeStackAllocator@$0CBA@@@6B@; const SafeStackAllocator<528>::`vftable'
0x18005f429  mov     rcx, rax
0x18005f42c  mov     [rbp+210h+var_280], rax
0x18005f430  xor     edi, edi
0x18005f432  mov     [rbp+210h+var_270], rdi
0x18005f436  mov     [rbp+210h+var_278], rdi
0x18005f43a  movzx   eax, word ptr [rdx]
0x18005f43d  lea     rax, ds:7[rax*2]
0x18005f445  and     rax, 0FFFFFFFFFFFFFFF8h
0x18005f449  mov     r14d, 210h
0x18005f44f  cmp     rax, r14
0x18005f452  ja      short loc_18005F45E
0x18005f454  lea     r15, [rbp+210h+WideCharStr]
0x18005f458  mov     [rbp+210h+var_278], rax
0x18005f45c  jmp     short loc_18005F475
0x18005f45e  mov     rdx, rax
0x18005f461  lea     rcx, [rbp+210h+var_280]
0x18005f465  call    ?AllocInHeap@?$SafeStackAllocator@$0CBA@@@IEAAPEAX_K@Z; SafeStackAllocator<528>::AllocInHeap(unsigned __int64)
0x18005f46a  mov     r15, rax
0x18005f46d  mov     rax, [rbp+210h+var_278]
0x18005f471  mov     rcx, [rbp+210h+var_280]
0x18005f475  mov     r8, [rcx]
0x18005f478  lea     rcx, ?AllocBytes@?$SafeStackAllocator@$0CBA@@@UEAAPEAX_K@Z; SafeStackAllocator<528>::AllocBytes(unsigned __int64)
0x18005f47f  cmp     r8, rcx
0x18005f482  jnz     short loc_18005F4B3
0x18005f484  sub     r14, rax
0x18005f487  cmp     r14, 208h
0x18005f48e  jb      short loc_18005F4A3
0x18005f490  lea     r12, [rbp+210h+WideCharStr]
0x18005f494  add     r12, rax
0x18005f497  add     rax, 208h
0x18005f49d  mov     [rbp+210h+var_278], rax
0x18005f4a1  jmp     short loc_18005F4C8
0x18005f4a3  mov     edx, 208h
0x18005f4a8  lea     rcx, [rbp+210h+var_280]
0x18005f4ac  call    ?AllocInHeap@?$SafeStackAllocator@$0CBA@@@IEAAPEAX_K@Z; SafeStackAllocator<528>::AllocInHeap(unsigned __int64)
0x18005f4b1  jmp     short loc_18005F4C5
0x18005f4b3  mov     edx, 208h
0x18005f4b8  lea     rcx, [rbp+210h+var_280]
0x18005f4bc  mov     rax, r8
0x18005f4bf  call    cs:__guard_dispatch_icall_fptr
0x18005f4c5  mov     r12, rax
0x18005f4c8  test    r15, r15
0x18005f4cb  jz      loc_18005F7B1
0x18005f4d1  test    r12, r12
0x18005f4d4  jz      loc_18005F7B1
0x18005f4da  movzx   ecx, word ptr [rbx+2]
0x18005f4de  mov     eax, 1515h
0x18005f4e3  cmp     cx, ax
0x18005f4e6  jnz     short loc_18005F4FB
0x18005f4e8  movups  xmm0, xmmword ptr [rbx+4]
0x18005f4ec  movaps  xmmword ptr [rbp+210h+var_290.Data1], xmm0
0x18005f4f0  mov     r14d, [rbx+14h]
0x18005f4f4  mov     [rsp+310h+var_2BC], r14d
0x18005f4f9  jmp     short loc_18005F532
0x18005f4fb  xorps   xmm0, xmm0
0x18005f4fe  movups  xmmword ptr [rbp+210h+var_290.Data1], xmm0
0x18005f502  mov     eax, [rbx+4]
0x18005f505  mov     [rbp+210h+var_290.Data1], eax
0x18005f508  movaps  xmm0, xmmword ptr [rbp+210h+var_290.Data1]
0x18005f50c  movdqa  xmmword ptr [rbp+210h+var_290.Data1], xmm0
0x18005f511  mov     eax, 1501h
0x18005f516  cmp     cx, ax
0x18005f519  jz      short loc_18005F52B
0x18005f51b  cmp     cx, 16h
0x18005f51f  jz      short loc_18005F52B
0x18005f521  mov     [rsp+310h+var_2BC], 0FFFFFFFFh
0x18005f529  jmp     short loc_18005F532
0x18005f52b  mov     eax, [rbx+8]
0x18005f52e  mov     [rsp+310h+var_2BC], eax
0x18005f532  movzx   r8d, word ptr [rbx]; cchWideChar
0x18005f536  mov     rdx, r15; lpWideCharStr
0x18005f539  mov     rcx, rbx; struct TYPTYPE *
0x18005f53c  call    SZNameFromTSRecord
0x18005f541  mov     r15, rax
0x18005f544  test    rax, rax
0x18005f547  jz      loc_18005F7B1
0x18005f54d  mov     rdx, rax; wchar_t *
0x18005f550  mov     rcx, [rsi+90h]; this
0x18005f557  call    ?QueryPDBMapping@PDB1@@QEAAPEA_WPEB_W@Z; PDB1::QueryPDBMapping(wchar_t const *)
0x18005f55c  mov     rbx, rax
0x18005f55f  mov     r14d, 1
0x18005f565  test    rax, rax
0x18005f568  jnz     short loc_18005F575
0x18005f56a  mov     [rsp+310h+var_2C0], edi
0x18005f56e  mov     [r12], di
0x18005f573  jmp     short loc_18005F59D
0x18005f575  mov     r8d, 104h; BufferCount
0x18005f57b  mov     rdx, rbx; Path
0x18005f57e  mov     rcx, r12; Buffer
0x18005f581  call    cs:__imp__wfullpath
0x18005f587  test    rax, rax
0x18005f58a  jz      loc_18005F793
0x18005f590  mov     [rsp+310h+var_2C0], r14d
0x18005f595  mov     [rsp+310h+var_2B8], r15
0x18005f59a  mov     r15, r12
0x18005f59d  mov     [rsp+310h+var_2D0], r13; int *
0x18005f5a2  mov     [rsp+310h+var_2D8], 0; bool
0x18005f5a7  mov     rax, [rsp+310h+var_2B0]
0x18005f5ac  mov     [rsp+310h+var_2E0], rax; struct TM **
0x18005f5b1  mov     dword ptr [rsp+310h+var_2E8], edi; unsigned int
0x18005f5b5  mov     ebx, [rsp+310h+var_2BC]
0x18005f5b9  mov     dword ptr [rsp+310h+var_2F0], ebx; unsigned int
0x18005f5bd  lea     r9, [rbp+210h+var_290]; struct _GUID *
0x18005f5c1  mov     r8, r15; wchar_t *
0x18005f5c4  mov     rdx, [rsi+98h]; struct OTM *
0x18005f5cb  mov     rcx, rsi; this
0x18005f5ce  call    ?fFindTm@DBI1@@AEAAHPEAUOTM@@PEB_WAEBU_GUID@@KKPEAPEAVTM@@_NAEAJ@Z; DBI1::fFindTm(OTM *,wchar_t const *,_GUID const &,ulong,ulong,TM * *,bool,long &)
0x18005f5d3  test    eax, eax
0x18005f5d5  jnz     loc_18005F7C8
0x18005f5db  cmp     [rbp+210h+arg_20], eax
0x18005f5e1  jnz     loc_18005F7CB
0x18005f5e7  mov     [rsp+310h+var_2D0], r13; int *
0x18005f5ec  mov     r12d, [rsp+310h+var_2C0]
0x18005f5f1  mov     dword ptr [rsp+310h+var_2D8], r12d; int
0x18005f5f6  lea     rax, [rsp+310h+var_2C0]
0x18005f5fb  mov     [rsp+310h+var_2E0], rax; unsigned int *
0x18005f600  mov     rax, [rsp+310h+var_2B0]
0x18005f605  mov     [rsp+310h+var_2E8], rax; struct TM **
0x18005f60a  mov     rax, [rsp+310h+var_2A8]
0x18005f60f  mov     [rsp+310h+var_2F0], rax; char *
0x18005f614  mov     r9d, ebx; unsigned int
0x18005f617  lea     r8, [rbp+210h+var_290]; struct _GUID *
0x18005f61b  mov     rdx, r15; wchar_t *
0x18005f61e  mov     rcx, rsi; this
0x18005f621  call    ?fOpenTmts@DBI1@@AEAAHPEB_WAEBU_GUID@@KPEBDPEAPEAVTM@@AEAKHAEAJ@Z; DBI1::fOpenTmts(wchar_t const *,_GUID const &,ulong,char const *,TM * *,ulong &,int,long &)
0x18005f626  test    eax, eax
0x18005f628  jnz     short loc_18005F670
0x18005f62a  test    r12d, r12d
0x18005f62d  jz      loc_18005F7CB
0x18005f633  mov     rcx, r15; wchar_t *
0x18005f636  call    ?FIsLinkerTempFile@PDB1@@CA_NPEB_W@Z; PDB1::FIsLinkerTempFile(wchar_t const *)
0x18005f63b  test    al, al
0x18005f63d  jz      loc_18005F7CB
0x18005f643  xor     r8d, r8d; unsigned __int64
0x18005f646  xor     edx, edx; wchar_t *
0x18005f648  mov     rcx, [rsi+90h]; this
0x18005f64f  call    ?QueryLastErrorCurrentThread@PDB1@@UEAAJPEA_W_K@Z; PDB1::QueryLastErrorCurrentThread(wchar_t *,unsigned __int64)
0x18005f654  mov     [r13+0], eax
0x18005f658  mov     r8, [rsp+310h+var_2B8]; wchar_t *
0x18005f65d  mov     edx, eax; int
0x18005f65f  mov     rcx, [rsi+90h]; this
0x18005f666  call    ?setLastError@PDB1@@QEAAXJPEB_W@Z; PDB1::setLastError(long,wchar_t const *)
0x18005f66b  jmp     loc_18005F7CB
0x18005f670  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18005f677  mov     rax, r8
0x18005f67a  nop     word ptr [rax+rax+00h]
0x18005f680  lea     rax, [rax+1]
0x18005f684  cmp     word ptr [r15+rax*2], 0
0x18005f68a  jnz     short loc_18005F680
0x18005f68c  lea     rcx, [rax+1]
0x18005f690  mov     [rsp+310h+var_2B8], rcx
0x18005f695  mov     eax, 2
0x18005f69a  mul     rcx
0x18005f69d  cmovb   rax, r8
0x18005f6a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005f6a8  mov     rcx, rax; unsigned __int64
0x18005f6ab  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005f6b0  mov     r12, rax
0x18005f6b3  mov     rbx, rax
0x18005f6b6  mov     [rsp+310h+var_2A8], rax
0x18005f6bb  test    rax, rax
0x18005f6be  jz      loc_18005F74D
0x18005f6c4  mov     r8, [rsp+310h+var_2B8]
0x18005f6c9  add     r8, r8; Size
0x18005f6cc  mov     rdx, r15; Src
0x18005f6cf  mov     rcx, rax; void *
0x18005f6d2  call    memcpy_0
0x18005f6d7  mov     rdx, [rsi+90h]; struct PDB1 *
0x18005f6de  mov     ecx, 48h ; 'H'; unsigned __int64
0x18005f6e3  call    ??2@YAPEAX_KPEAVPDB1@@@Z; operator new(unsigned __int64,PDB1 *)
0x18005f6e8  mov     r8, rax
0x18005f6eb  mov     [rsp+310h+var_2B8], rax
0x18005f6f0  test    rax, rax
0x18005f6f3  jz      short loc_18005F746
0x18005f6f5  mov     rax, [rsp+310h+var_2B0]
0x18005f6fa  mov     rdx, [rax]
0x18005f6fd  mov     rcx, [rsi+98h]
0x18005f704  mov     [r8], rcx
0x18005f707  movups  xmm0, xmmword ptr [rbp+210h+var_290.Data1]
0x18005f70b  movups  xmmword ptr [r8+8], xmm0
0x18005f710  mov     rbx, rdi
0x18005f713  mov     [rsp+310h+var_2A8], rbx
0x18005f718  mov     [r8+18h], r12
0x18005f71c  mov     [r8+20h], rdi
0x18005f720  mov     [r8+28h], rdi
0x18005f724  mov     [r8+30h], rdi
0x18005f728  mov     [r8+38h], rdx
0x18005f72c  mov     [r8+40h], edi
0x18005f730  mov     eax, [rsp+310h+var_2C0]
0x18005f734  mov     [r8+44h], eax
0x18005f738  mov     [rsi+98h], r8
0x18005f73f  test    r8, r8
0x18005f742  jz      short loc_18005F74D
0x18005f744  jmp     short loc_18005F784
0x18005f746  mov     [rsi+98h], rdi
0x18005f74d  mov     dword ptr [r13+0], 2
0x18005f755  mov     rcx, [rsi+90h]; this
0x18005f75c  call    ?setOOMError@PDB1@@QEAAXXZ; PDB1::setOOMError(void)
0x18005f761  mov     rsi, [rsp+310h+var_2B0]
0x18005f766  mov     rcx, [rsi]
0x18005f769  test    rcx, rcx
0x18005f76c  jz      short loc_18005F77E
0x18005f76e  mov     rax, [rcx]
0x18005f771  mov     edx, r14d
0x18005f774  mov     rax, [rax+18h]
0x18005f778  call    cs:__guard_dispatch_icall_fptr
0x18005f77e  mov     [rsi], rdi
0x18005f781  mov     r14d, edi
0x18005f784  test    rbx, rbx
0x18005f787  jz      short loc_18005F7CE
0x18005f789  mov     rcx, rbx; this
0x18005f78c  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18005f791  jmp     short loc_18005F7CE
0x18005f793  mov     dword ptr [r13+0], 3
0x18005f79b  mov     r8, rbx; wchar_t *
0x18005f79e  mov     edx, 3; int
0x18005f7a3  mov     rcx, [rsi+90h]; this
0x18005f7aa  call    ?setLastError@PDB1@@QEAAXJPEB_W@Z; PDB1::setLastError(long,wchar_t const *)
0x18005f7af  jmp     short loc_18005F7C5
0x18005f7b1  mov     dword ptr [r13+0], 2
0x18005f7b9  mov     rcx, [rsi+90h]; this
0x18005f7c0  call    ?setOOMError@PDB1@@QEAAXXZ; PDB1::setOOMError(void)
0x18005f7c5  mov     r14d, edi
0x18005f7c8  mov     edi, r14d
0x18005f7cb  mov     r14d, edi
0x18005f7ce  lea     rax, ??_7?$SafeStackAllocator@$0CBA@@@6B@; const SafeStackAllocator<528>::`vftable'
0x18005f7d5  mov     [rbp+210h+var_280], rax
0x18005f7d9  mov     rbx, [rbp+210h+var_270]
0x18005f7dd  test    rbx, rbx
0x18005f7e0  jz      short loc_18005F7F2
0x18005f7e2  mov     rcx, rbx; this
0x18005f7e5  mov     rbx, [rbx]
0x18005f7e8  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18005f7ed  test    rbx, rbx
0x18005f7f0  jnz     short loc_18005F7E2
0x18005f7f2  mov     eax, r14d
0x18005f7f5  mov     rcx, [rbp+210h+var_50]
0x18005f7fc  xor     rcx, rsp; StackCookie
0x18005f7ff  call    __security_check_cookie
0x18005f804  add     rsp, 2D8h
0x18005f80b  pop     r15
0x18005f80d  pop     r14
0x18005f80f  pop     r13
0x18005f811  pop     r12
0x18005f813  pop     rdi
0x18005f814  pop     rsi
0x18005f815  pop     rbx
0x18005f816  pop     rbp
0x18005f817  retn
```

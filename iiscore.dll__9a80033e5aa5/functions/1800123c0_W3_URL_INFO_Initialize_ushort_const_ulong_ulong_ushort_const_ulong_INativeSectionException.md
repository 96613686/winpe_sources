# W3_URL_INFO::Initialize(ushort const *,ulong,ulong,ushort const *,ulong,INativeSectionException * *)

- ea: `0x1800123c0`
- end: `0x180012604`
- name: `?Initialize@W3_URL_INFO@@QEAAJPEBGKK0KPEAPEAVINativeSectionException@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(W3_URL_INFO *this, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002bf0`
- `0x180020e20`

## callees

- `0x1800123c0`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x1800124e7`
- `msvcrt!_wcsupr` at `0x1800124e7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012498`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012498`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800125f0`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800125f0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800124dd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001253a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012592`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800125e2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800124dd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001253a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012592`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800125e2`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180012575`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180012575`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800125d7`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800125d7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180012422`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180012422`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180012457`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180012470`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180012457`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180012470`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800124cd`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800124cd`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180012487`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180012487`

## pseudocode

```c
__int64 __fastcall W3_URL_INFO::Initialize(
        W3_URL_INFO *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        const unsigned __int16 *a5,
        unsigned int a6)
{
  const unsigned __int16 *v6; // rsi
  unsigned int CCH; // r14d
  int v12; // ebx
  unsigned __int16 *Str; // rax
  __int64 (__fastcall *v15)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD); // rbx
  unsigned __int16 *v16; // rax
  __int64 (__fastcall *v17)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD); // rbx
  unsigned __int16 *v18; // rax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[56]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v21[264]; // [rsp+70h] [rbp-90h] BYREF

  v6 = a5;
  memset_0(v21, 0, 0x208u);
  STRU::STRU((STRU *)v20, v21, 0x104u);
  if ( a5 && *a5 )
  {
    CCH = a6;
LABEL_4:
    *((_DWORD *)this + 6) = a4;
    v12 = STRU::Copy((W3_URL_INFO *)((char *)this + 32), L"MACHINE/WEBROOT/APPHOST/", 0x18u);
    if ( v12 >= 0 )
    {
      v12 = STRU::Copy((W3_URL_INFO *)((char *)this + 320), v6, CCH);
      if ( v12 >= 0 )
      {
        v12 = STRU::Append((W3_URL_INFO *)((char *)this + 32), (W3_URL_INFO *)((char *)this + 320));
        if ( v12 >= 0 )
        {
          v12 = STRU::Append((W3_URL_INFO *)((char *)this + 32), a2, a3);
          if ( v12 >= 0 )
          {
            Str = STRU::QueryStr((W3_URL_INFO *)((char *)this + 32));
            _wcsupr(Str + 24);
          }
        }
      }
    }
    goto LABEL_7;
  }
  v19 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)g_pW3Server + 187) + 56LL))(
          *((_QWORD *)g_pW3Server + 187),
          &v19);
  if ( v12 >= 0 )
  {
    a6 = 260;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)v19 + 24LL);
    v16 = STRU::QueryStr((STRU *)v20);
    v12 = v15(v19, a4, v16, &a6, 0);
    if ( v12 == -2147024774 )
    {
      v12 = STRU::Resize((STRU *)v20, 2 * a6);
      if ( v12 >= 0 )
      {
        v17 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)v19 + 24LL);
        v18 = STRU::QueryStr((STRU *)v20);
        v12 = v17(v19, a4, v18, &a6, 0);
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v12 >= 0 )
    {
      STRU::SyncWithBuffer((STRU *)v20);
      v6 = STRU::QueryStr((STRU *)v20);
      CCH = STRU::QueryCCH((STRU *)v20);
      a6 = CCH;
      goto LABEL_4;
    }
  }
LABEL_7:
  STRU::~STRU((STRU *)v20);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800123c0  push    rbp
0x1800123c2  push    rbx
0x1800123c3  push    rsi
0x1800123c4  push    rdi
0x1800123c5  push    r12
0x1800123c7  push    r13
0x1800123c9  push    r14
0x1800123cb  push    r15
0x1800123cd  lea     rbp, [rsp-198h]
0x1800123d5  sub     rsp, 298h
0x1800123dc  mov     rax, cs:__security_cookie
0x1800123e3  xor     rax, rsp
0x1800123e6  mov     [rbp+1D0h+var_50], rax
0x1800123ed  mov     rsi, [rbp+1D0h+arg_20]
0x1800123f4  mov     r13d, r8d
0x1800123f7  mov     r12, rdx
0x1800123fa  mov     rdi, rcx
0x1800123fd  xor     edx, edx; Val
0x1800123ff  lea     rcx, [rsp+2D0h+var_260]; void *
0x180012404  mov     r8d, 208h; Size
0x18001240a  mov     r15d, r9d
0x18001240d  call    memset_0
0x180012412  mov     r8d, 104h
0x180012418  lea     rdx, [rsp+2D0h+var_260]
0x18001241d  lea     rcx, [rsp+2D0h+var_298]
0x180012422  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180012428  test    rsi, rsi
0x18001242b  jz      loc_1800124EF
0x180012431  cmp     word ptr [rsi], 0
0x180012435  jz      loc_1800124EF
0x18001243b  mov     r14d, [rbp+1D0h+arg_28]
0x180012442  mov     r8d, 18h
0x180012448  mov     [rdi+18h], r15d
0x18001244c  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x180012453  lea     rcx, [rdi+20h]
0x180012457  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001245d  mov     ebx, eax
0x18001245f  test    eax, eax
0x180012461  js      short loc_180012493
0x180012463  mov     r8d, r14d
0x180012466  lea     rcx, [rdi+140h]
0x18001246d  mov     rdx, rsi
0x180012470  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180012476  mov     ebx, eax
0x180012478  test    eax, eax
0x18001247a  js      short loc_180012493
0x18001247c  lea     rdx, [rdi+140h]
0x180012483  lea     rcx, [rdi+20h]
0x180012487  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18001248d  mov     ebx, eax
0x18001248f  test    eax, eax
0x180012491  jns     short loc_1800124C3
0x180012493  lea     rcx, [rsp+2D0h+var_298]
0x180012498  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001249e  mov     eax, ebx
0x1800124a0  mov     rcx, [rbp+1D0h+var_50]
0x1800124a7  xor     rcx, rsp; StackCookie
0x1800124aa  call    __security_check_cookie
0x1800124af  add     rsp, 298h
0x1800124b6  pop     r15
0x1800124b8  pop     r14
0x1800124ba  pop     r13
0x1800124bc  pop     r12
0x1800124be  pop     rdi
0x1800124bf  pop     rsi
0x1800124c0  pop     rbx
0x1800124c1  pop     rbp
0x1800124c2  retn
0x1800124c3  mov     r8d, r13d
0x1800124c6  lea     rcx, [rdi+20h]
0x1800124ca  mov     rdx, r12
0x1800124cd  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x1800124d3  mov     ebx, eax
0x1800124d5  test    eax, eax
0x1800124d7  js      short loc_180012493
0x1800124d9  lea     rcx, [rdi+20h]
0x1800124dd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800124e3  lea     rcx, [rax+30h]; String
0x1800124e7  call    cs:__imp__wcsupr
0x1800124ed  jmp     short loc_180012493
0x1800124ef  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800124f6  lea     rdx, [rsp+2D0h+var_2A0]
0x1800124fb  xor     esi, esi
0x1800124fd  mov     [rsp+2D0h+var_2A0], rsi
0x180012502  mov     rcx, [rax+5D8h]
0x180012509  mov     rax, [rcx]
0x18001250c  mov     rax, [rax+38h]
0x180012510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012515  mov     ebx, eax
0x180012517  test    eax, eax
0x180012519  js      loc_180012493
0x18001251f  mov     rax, [rsp+2D0h+var_2A0]
0x180012524  mov     [rbp+1D0h+arg_28], 104h
0x18001252e  mov     rcx, [rax]
0x180012531  mov     rbx, [rcx+18h]
0x180012535  lea     rcx, [rsp+2D0h+var_298]
0x18001253a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180012540  mov     rcx, [rsp+2D0h+var_2A0]
0x180012545  lea     r9, [rbp+1D0h+arg_28]
0x18001254c  mov     r8, rax
0x18001254f  mov     [rsp+2D0h+var_2B0], rsi
0x180012554  mov     rax, rbx
0x180012557  mov     edx, r15d
0x18001255a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001255f  mov     ebx, eax
0x180012561  cmp     eax, 8007007Ah
0x180012566  jnz     short loc_1800125B9
0x180012568  mov     edx, [rbp+1D0h+arg_28]
0x18001256e  lea     rcx, [rsp+2D0h+var_298]
0x180012573  add     edx, edx
0x180012575  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18001257b  mov     ebx, eax
0x18001257d  test    eax, eax
0x18001257f  js      short loc_1800125B9
0x180012581  mov     rax, [rsp+2D0h+var_2A0]
0x180012586  mov     rcx, [rax]
0x180012589  mov     rbx, [rcx+18h]
0x18001258d  lea     rcx, [rsp+2D0h+var_298]
0x180012592  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180012598  mov     rcx, [rsp+2D0h+var_2A0]
0x18001259d  lea     r9, [rbp+1D0h+arg_28]
0x1800125a4  mov     r8, rax
0x1800125a7  mov     [rsp+2D0h+var_2B0], rsi
0x1800125ac  mov     rax, rbx
0x1800125af  mov     edx, r15d
0x1800125b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b7  mov     ebx, eax
0x1800125b9  mov     rcx, [rsp+2D0h+var_2A0]
0x1800125be  mov     rax, [rcx]
0x1800125c1  mov     rax, [rax+10h]
0x1800125c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ca  lea     rcx, [rsp+2D0h+var_298]
0x1800125cf  test    ebx, ebx
0x1800125d1  js      loc_180012498
0x1800125d7  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800125dd  lea     rcx, [rsp+2D0h+var_298]
0x1800125e2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800125e8  lea     rcx, [rsp+2D0h+var_298]
0x1800125ed  mov     rsi, rax
0x1800125f0  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800125f6  mov     r14d, eax
0x1800125f9  mov     [rbp+1D0h+arg_28], eax
0x1800125ff  jmp     loc_180012442
```

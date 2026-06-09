# W3_URL_INFO::Initialize(ushort const *,ulong,ulong,ushort const *,ulong,INativeSectionException * *)

- ea: `0x1800132e0`
- end: `0x180013579`
- name: `?Initialize@W3_URL_INFO@@QEAAJPEBGKK0KPEAPEAVINativeSectionException@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(W3_URL_INFO *this, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002db0`
- `0x180022a10`

## callees

- `0x1800132e0`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180013432`
- `msvcrt!_wcsupr` at `0x180013432`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800133d0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800133d0`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001355f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001355f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180013422`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001348b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800134ef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001354b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180013422`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001348b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800134ef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001354b`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800134cc`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800134cc`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001353a`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001353a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180013342`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180013342`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001337d`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001339c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001337d`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001339c`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18001340c`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18001340c`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800133b9`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800133b9`

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
0x1800132e0  push    rbp
0x1800132e2  push    rbx
0x1800132e3  push    rsi
0x1800132e4  push    rdi
0x1800132e5  push    r12
0x1800132e7  push    r13
0x1800132e9  push    r14
0x1800132eb  push    r15
0x1800132ed  lea     rbp, [rsp-198h]
0x1800132f5  sub     rsp, 298h
0x1800132fc  mov     rax, cs:__security_cookie
0x180013303  xor     rax, rsp
0x180013306  mov     [rbp+1D0h+var_50], rax
0x18001330d  mov     rsi, [rbp+1D0h+arg_20]
0x180013314  mov     r13d, r8d
0x180013317  mov     r12, rdx
0x18001331a  mov     rdi, rcx
0x18001331d  xor     edx, edx; Val
0x18001331f  lea     rcx, [rsp+2D0h+var_260]; void *
0x180013324  mov     r8d, 208h; Size
0x18001332a  mov     r15d, r9d
0x18001332d  call    memset_0
0x180013332  mov     r8d, 104h
0x180013338  lea     rdx, [rsp+2D0h+var_260]
0x18001333d  lea     rcx, [rsp+2D0h+var_298]
0x180013342  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180013349  nop     dword ptr [rax+rax+00h]
0x18001334e  test    rsi, rsi
0x180013351  jz      loc_180013440
0x180013357  cmp     word ptr [rsi], 0
0x18001335b  jz      loc_180013440
0x180013361  mov     r14d, [rbp+1D0h+arg_28]
0x180013368  mov     r8d, 18h
0x18001336e  mov     [rdi+18h], r15d
0x180013372  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x180013379  lea     rcx, [rdi+20h]
0x18001337d  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180013384  nop     dword ptr [rax+rax+00h]
0x180013389  mov     ebx, eax
0x18001338b  test    eax, eax
0x18001338d  js      short loc_1800133CB
0x18001338f  mov     r8d, r14d
0x180013392  lea     rcx, [rdi+140h]
0x180013399  mov     rdx, rsi
0x18001339c  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800133a3  nop     dword ptr [rax+rax+00h]
0x1800133a8  mov     ebx, eax
0x1800133aa  test    eax, eax
0x1800133ac  js      short loc_1800133CB
0x1800133ae  lea     rdx, [rdi+140h]
0x1800133b5  lea     rcx, [rdi+20h]
0x1800133b9  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x1800133c0  nop     dword ptr [rax+rax+00h]
0x1800133c5  mov     ebx, eax
0x1800133c7  test    eax, eax
0x1800133c9  jns     short loc_180013402
0x1800133cb  lea     rcx, [rsp+2D0h+var_298]
0x1800133d0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800133d7  nop     dword ptr [rax+rax+00h]
0x1800133dc  mov     eax, ebx
0x1800133de  mov     rcx, [rbp+1D0h+var_50]
0x1800133e5  xor     rcx, rsp; StackCookie
0x1800133e8  call    __security_check_cookie
0x1800133ed  add     rsp, 298h
0x1800133f4  pop     r15
0x1800133f6  pop     r14
0x1800133f8  pop     r13
0x1800133fa  pop     r12
0x1800133fc  pop     rdi
0x1800133fd  pop     rsi
0x1800133fe  pop     rbx
0x1800133ff  pop     rbp
0x180013400  retn
0x180013402  mov     r8d, r13d
0x180013405  lea     rcx, [rdi+20h]
0x180013409  mov     rdx, r12
0x18001340c  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180013413  nop     dword ptr [rax+rax+00h]
0x180013418  mov     ebx, eax
0x18001341a  test    eax, eax
0x18001341c  js      short loc_1800133CB
0x18001341e  lea     rcx, [rdi+20h]
0x180013422  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180013429  nop     dword ptr [rax+rax+00h]
0x18001342e  lea     rcx, [rax+30h]; String
0x180013432  call    cs:__imp__wcsupr
0x180013439  nop     dword ptr [rax+rax+00h]
0x18001343e  jmp     short loc_1800133CB
0x180013440  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180013447  lea     rdx, [rsp+2D0h+var_2A0]
0x18001344c  xor     esi, esi
0x18001344e  mov     [rsp+2D0h+var_2A0], rsi
0x180013453  mov     rcx, [rax+5D8h]
0x18001345a  mov     rax, [rcx]
0x18001345d  mov     rax, [rax+38h]
0x180013461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013466  mov     ebx, eax
0x180013468  test    eax, eax
0x18001346a  js      loc_1800133CB
0x180013470  mov     rax, [rsp+2D0h+var_2A0]
0x180013475  mov     [rbp+1D0h+arg_28], 104h
0x18001347f  mov     rcx, [rax]
0x180013482  mov     rbx, [rcx+18h]
0x180013486  lea     rcx, [rsp+2D0h+var_298]
0x18001348b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180013492  nop     dword ptr [rax+rax+00h]
0x180013497  mov     rcx, [rsp+2D0h+var_2A0]
0x18001349c  lea     r9, [rbp+1D0h+arg_28]
0x1800134a3  mov     r8, rax
0x1800134a6  mov     [rsp+2D0h+var_2B0], rsi
0x1800134ab  mov     rax, rbx
0x1800134ae  mov     edx, r15d
0x1800134b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134b6  mov     ebx, eax
0x1800134b8  cmp     eax, 8007007Ah
0x1800134bd  jnz     short loc_18001351C
0x1800134bf  mov     edx, [rbp+1D0h+arg_28]
0x1800134c5  lea     rcx, [rsp+2D0h+var_298]
0x1800134ca  add     edx, edx
0x1800134cc  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800134d3  nop     dword ptr [rax+rax+00h]
0x1800134d8  mov     ebx, eax
0x1800134da  test    eax, eax
0x1800134dc  js      short loc_18001351C
0x1800134de  mov     rax, [rsp+2D0h+var_2A0]
0x1800134e3  mov     rcx, [rax]
0x1800134e6  mov     rbx, [rcx+18h]
0x1800134ea  lea     rcx, [rsp+2D0h+var_298]
0x1800134ef  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800134f6  nop     dword ptr [rax+rax+00h]
0x1800134fb  mov     rcx, [rsp+2D0h+var_2A0]
0x180013500  lea     r9, [rbp+1D0h+arg_28]
0x180013507  mov     r8, rax
0x18001350a  mov     [rsp+2D0h+var_2B0], rsi
0x18001350f  mov     rax, rbx
0x180013512  mov     edx, r15d
0x180013515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001351a  mov     ebx, eax
0x18001351c  mov     rcx, [rsp+2D0h+var_2A0]
0x180013521  mov     rax, [rcx]
0x180013524  mov     rax, [rax+10h]
0x180013528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001352d  lea     rcx, [rsp+2D0h+var_298]
0x180013532  test    ebx, ebx
0x180013534  js      loc_1800133D0
0x18001353a  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180013541  nop     dword ptr [rax+rax+00h]
0x180013546  lea     rcx, [rsp+2D0h+var_298]
0x18001354b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180013552  nop     dword ptr [rax+rax+00h]
0x180013557  lea     rcx, [rsp+2D0h+var_298]
0x18001355c  mov     rsi, rax
0x18001355f  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180013566  nop     dword ptr [rax+rax+00h]
0x18001356b  mov     r14d, eax
0x18001356e  mov     [rbp+1D0h+arg_28], eax
0x180013574  jmp     loc_180013368
```

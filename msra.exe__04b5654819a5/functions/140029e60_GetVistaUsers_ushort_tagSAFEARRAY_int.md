# GetVistaUsers(ushort *,tagSAFEARRAY * *,int *)

- ea: `0x140029e60`
- end: `0x14002a16c`
- name: `?GetVistaUsers@@YAJPEAGPEAPEAUtagSAFEARRAY@@PEAH@Z`
- size: `780`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct tagSAFEARRAY **, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140031620`

## callees

- `0x140029e60`
- `0x140034ce4`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `ole32!MkParseDisplayName` at `0x14002a017`
- `ole32!MkParseDisplayName` at `0x14002a017`
- `ole32!CreateBindCtx` at `0x140029f37`
- `ole32!CreateBindCtx` at `0x140029f37`

## string_xrefs

- `0x14002a0c0`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140029e86`: `Session:Console!clsid:3C3A70A7-A468-49B9-8ADA-28E11FCCAD5D`

## pseudocode

```c
__int64 __fastcall GetVistaUsers(unsigned __int16 *a1, struct tagSAFEARRAY **a2, int *a3)
{
  HRESULT v6; // eax
  CEventLogger *v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // r9d
  LPBC ppbc; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  LPMONIKER ppmk; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pchEaten; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v16; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v17; // [rsp+68h] [rbp-98h]
  __int64 v18; // [rsp+78h] [rbp-88h]
  __int128 v19; // [rsp+80h] [rbp-80h] BYREF
  __int128 v20; // [rsp+90h] [rbp-70h]
  __int128 v21; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v22; // [rsp+B0h] [rbp-50h]
  __int128 *v23; // [rsp+C0h] [rbp-40h]
  OLECHAR szUserName[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v25; // [rsp+E0h] [rbp-20h]
  __int128 v26; // [rsp+F0h] [rbp-10h]
  __int128 v27; // [rsp+100h] [rbp+0h]
  __int128 v28; // [rsp+110h] [rbp+10h]
  __int128 v29; // [rsp+120h] [rbp+20h]
  _OWORD v30[2]; // [rsp+130h] [rbp+30h]

  *(_OWORD *)szUserName = *(_OWORD *)L"Session:Console!clsid:3C3A70A7-A468-49B9-8ADA-28E11FCCAD5D";
  v25 = *(_OWORD *)L"Console!clsid:3C3A70A7-A468-49B9-8ADA-28E11FCCAD5D";
  v26 = *(_OWORD *)L"clsid:3C3A70A7-A468-49B9-8ADA-28E11FCCAD5D";
  v27 = *(_OWORD *)L"3A70A7-A468-49B9-8ADA-28E11FCCAD5D";
  v28 = *(_OWORD *)L"468-49B9-8ADA-28E11FCCAD5D";
  v29 = *(_OWORD *)L"-8ADA-28E11FCCAD5D";
  v30[0] = *(_OWORD *)L"E11FCCAD5D";
  *(_QWORD *)((char *)v30 + 14) = *(_QWORD *)L"D5D";
  v16 = 0;
  ppbc = 0;
  v17 = 0;
  ppmk = 0;
  v13 = 0;
  v12 = 0;
  pchEaten = 0;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v6 = CreateBindCtx(0, &ppbc);
  v8 = v6;
  if ( v6 >= 0 )
  {
    *(_QWORD *)&v20 = &v16;
    v16 = 0xFFFFFFFF00000009uLL;
    v23 = 0;
    v21 = 0;
    v17 = 0x300000006uLL;
    LODWORD(v18) = 0;
    LODWORD(v19) = 0;
    *((_QWORD *)&v19 + 1) = a1;
    DWORD2(v20) = 0;
    v22 = 0;
    LODWORD(v21) = 40;
    v6 = ((__int64 (__fastcall *)(LPBC, __int128 *))ppbc->lpVtbl->GetBindOptions)(ppbc, &v21);
    v8 = v6;
    if ( v6 >= 0 )
    {
      v23 = &v19;
      v6 = ((__int64 (__fastcall *)(LPBC, __int128 *))ppbc->lpVtbl->SetBindOptions)(ppbc, &v21);
      v8 = v6;
      if ( v6 >= 0 )
      {
        v6 = MkParseDisplayName(ppbc, szUserName, &pchEaten, &ppmk);
        v8 = v6;
        if ( v6 >= 0 )
        {
          v6 = ((__int64 (__fastcall *)(LPMONIKER, LPBC, _QWORD, GUID *, __int64 *))ppmk->lpVtbl->BindToObject)(
                 ppmk,
                 ppbc,
                 0,
                 &IID_IClassFactory,
                 &v13);
          v8 = v6;
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v13 + 24LL))(
                   v13,
                   0,
                   &IID_IRASrv,
                   &v12);
            v8 = v6;
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(__int64, struct tagSAFEARRAY **, int *))(*(_QWORD *)v12 + 64LL))(
                     v12,
                     a2,
                     a3);
              v8 = v6;
              if ( v6 >= 0 )
                goto LABEL_16;
              v9 = 3447;
            }
            else
            {
              v9 = 3446;
            }
          }
          else
          {
            v9 = 3441;
          }
        }
        else
        {
          v9 = 3435;
        }
      }
      else
      {
        v9 = 3426;
      }
    }
    else
    {
      v9 = 3424;
    }
  }
  else
  {
    v9 = 3396;
  }
  CEventLogger::LogError(v7, &Recoverable_Error, L"base\\diagnosis\\ra\\ui\\commonfunc.cpp", v9, L"GetVistaUsers", v6);
LABEL_16:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( ppmk )
  {
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
    ppmk = 0;
  }
  if ( ppbc )
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  return v8;
}

```

## disassembly

```asm
0x140029e60  mov     [rsp-8+arg_18], rbx
0x140029e65  push    rbp
0x140029e66  push    rsi
0x140029e67  push    rdi
0x140029e68  push    r14
0x140029e6a  push    r15
0x140029e6c  lea     rbp, [rsp-60h]
0x140029e71  sub     rsp, 160h
0x140029e78  mov     rax, cs:__security_cookie
0x140029e7f  xor     rax, rsp
0x140029e82  mov     [rbp+80h+var_30], rax
0x140029e86  movaps  xmm0, xmmword ptr cs:aSessionConsole; "Session:Console!clsid:3C3A70A7-A468-49B"...
0x140029e8d  xor     r15d, r15d
0x140029e90  movaps  xmm1, xmmword ptr cs:aSessionConsole+10h; "Console!clsid:3C3A70A7-A468-49B9-8ADA-2"...
0x140029e97  xor     eax, eax
0x140029e99  movaps  xmmword ptr [rbp+80h+szUserName], xmm0
0x140029e9d  mov     rsi, rdx
0x140029ea0  movaps  xmm0, xmmword ptr cs:aSessionConsole+20h; "clsid:3C3A70A7-A468-49B9-8ADA-28E11FCCA"...
0x140029ea7  lea     rdx, [rsp+180h+ppbc]; ppbc
0x140029eac  movaps  [rbp+80h+var_A0], xmm1
0x140029eb0  mov     rdi, rcx
0x140029eb3  movaps  xmm1, xmmword ptr cs:aSessionConsole+30h; "3A70A7-A468-49B9-8ADA-28E11FCCAD5D"
0x140029eba  xor     ecx, ecx; reserved
0x140029ebc  movaps  [rbp+80h+var_90], xmm0
0x140029ec0  mov     r14, r8
0x140029ec3  movaps  xmm0, xmmword ptr cs:aSessionConsole+40h; "468-49B9-8ADA-28E11FCCAD5D"
0x140029eca  movaps  [rbp+80h+var_80], xmm1
0x140029ece  movaps  xmm1, xmmword ptr cs:aSessionConsole+50h; "-8ADA-28E11FCCAD5D"
0x140029ed5  movaps  [rbp+80h+var_70], xmm0
0x140029ed9  movaps  xmm0, xmmword ptr cs:aSessionConsole+60h; "E11FCCAD5D"
0x140029ee0  movaps  [rbp+80h+var_60], xmm1
0x140029ee4  movsd   xmm1, qword ptr cs:aSessionConsole+6Eh; "D5D"
0x140029eec  movaps  xmmword ptr [rbp+80h+var_50], xmm0
0x140029ef0  xorps   xmm0, xmm0
0x140029ef3  movsd   qword ptr [rbp+80h+var_50+0Eh], xmm1
0x140029ef8  xorps   xmm1, xmm1
0x140029efb  movups  [rsp+180h+var_128], xmm1
0x140029f00  mov     [rsp+180h+ppbc], r15
0x140029f05  movups  [rsp+180h+var_118], xmm1
0x140029f0a  mov     [rsp+180h+ppmk], r15
0x140029f0f  mov     [rsp+180h+var_140], r15
0x140029f14  mov     [rsp+180h+var_148], r15
0x140029f19  mov     [rsp+180h+pchEaten], r15d
0x140029f1e  movups  [rbp+80h+var_E0], xmm0
0x140029f22  mov     [rbp+80h+var_C0], rax
0x140029f26  movups  [rbp+80h+var_D0], xmm0
0x140029f2a  mov     [rsp+180h+var_108], rax
0x140029f2f  movups  [rbp+80h+var_100], xmm0
0x140029f33  movups  [rbp+80h+var_F0], xmm0
0x140029f37  call    cs:__imp_CreateBindCtx
0x140029f3e  nop     dword ptr [rax+rax+00h]
0x140029f43  mov     ebx, eax
0x140029f45  test    eax, eax
0x140029f47  jns     short loc_140029F54
0x140029f49  mov     r9d, 0D44h
0x140029f4f  jmp     loc_14002A0BC
0x140029f54  mov     rcx, [rsp+180h+ppbc]
0x140029f59  lea     rax, [rsp+180h+var_128]
0x140029f5e  mov     qword ptr [rbp+80h+var_F0], rax
0x140029f62  lea     rdx, [rbp+80h+var_E0]
0x140029f66  xor     eax, eax
0x140029f68  mov     dword ptr [rsp+180h+var_128], 9
0x140029f70  xorps   xmm0, xmm0
0x140029f73  mov     [rbp+80h+var_C0], rax
0x140029f77  movups  [rbp+80h+var_E0], xmm0
0x140029f7b  mov     dword ptr [rsp+180h+var_128+4], 0FFFFFFFFh
0x140029f83  mov     qword ptr [rsp+180h+var_128+8], r15
0x140029f88  mov     dword ptr [rsp+180h+var_118], 6
0x140029f90  mov     dword ptr [rsp+180h+var_118+4], 3
0x140029f98  mov     qword ptr [rsp+180h+var_118+8], r15
0x140029f9d  mov     dword ptr [rsp+180h+var_108], r15d
0x140029fa2  mov     dword ptr [rbp+80h+var_100], r15d
0x140029fa6  mov     qword ptr [rbp+80h+var_100+8], rdi
0x140029faa  mov     dword ptr [rbp+80h+var_F0+8], r15d
0x140029fae  movups  [rbp+80h+var_D0], xmm0
0x140029fb2  mov     dword ptr [rbp+80h+var_E0], 28h ; '('
0x140029fb9  mov     rax, [rcx]
0x140029fbc  mov     rax, [rax+38h]
0x140029fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029fc5  mov     ebx, eax
0x140029fc7  test    eax, eax
0x140029fc9  jns     short loc_140029FD6
0x140029fcb  mov     r9d, 0D60h
0x140029fd1  jmp     loc_14002A0BC
0x140029fd6  mov     rcx, [rsp+180h+ppbc]
0x140029fdb  lea     rax, [rbp+80h+var_100]
0x140029fdf  mov     [rbp+80h+var_C0], rax
0x140029fe3  lea     rdx, [rbp+80h+var_E0]
0x140029fe7  mov     rax, [rcx]
0x140029fea  mov     rax, [rax+30h]
0x140029fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029ff3  mov     ebx, eax
0x140029ff5  test    eax, eax
0x140029ff7  jns     short loc_14002A004
0x140029ff9  mov     r9d, 0D62h
0x140029fff  jmp     loc_14002A0BC
0x14002a004  mov     rcx, [rsp+180h+ppbc]; pbc
0x14002a009  lea     r9, [rsp+180h+ppmk]; ppmk
0x14002a00e  lea     r8, [rsp+180h+pchEaten]; pchEaten
0x14002a013  lea     rdx, [rbp+80h+szUserName]; szUserName
0x14002a017  call    cs:__imp_MkParseDisplayName
0x14002a01e  nop     dword ptr [rax+rax+00h]
0x14002a023  mov     ebx, eax
0x14002a025  test    eax, eax
0x14002a027  jns     short loc_14002A034
0x14002a029  mov     r9d, 0D6Bh
0x14002a02f  jmp     loc_14002A0BC
0x14002a034  mov     rcx, [rsp+180h+ppmk]
0x14002a039  lea     rdx, [rsp+180h+var_140]
0x14002a03e  mov     [rsp+180h+var_160], rdx
0x14002a043  lea     r9, IID_IClassFactory
0x14002a04a  mov     rdx, [rsp+180h+ppbc]
0x14002a04f  xor     r8d, r8d
0x14002a052  mov     rax, [rcx]
0x14002a055  mov     rax, [rax+40h]
0x14002a059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a05e  mov     ebx, eax
0x14002a060  test    eax, eax
0x14002a062  jns     short loc_14002A06C
0x14002a064  mov     r9d, 0D71h
0x14002a06a  jmp     short loc_14002A0BC
0x14002a06c  mov     rcx, [rsp+180h+var_140]
0x14002a071  lea     r9, [rsp+180h+var_148]
0x14002a076  lea     r8, IID_IRASrv
0x14002a07d  xor     edx, edx
0x14002a07f  mov     rax, [rcx]
0x14002a082  mov     rax, [rax+18h]
0x14002a086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a08b  mov     ebx, eax
0x14002a08d  test    eax, eax
0x14002a08f  jns     short loc_14002A099
0x14002a091  mov     r9d, 0D76h
0x14002a097  jmp     short loc_14002A0BC
0x14002a099  mov     rcx, [rsp+180h+var_148]
0x14002a09e  mov     r8, r14
0x14002a0a1  mov     rdx, rsi
0x14002a0a4  mov     rax, [rcx]
0x14002a0a7  mov     rax, [rax+40h]
0x14002a0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a0b0  mov     ebx, eax
0x14002a0b2  test    eax, eax
0x14002a0b4  jns     short loc_14002A0DF
0x14002a0b6  mov     r9d, 0D77h; unsigned int
0x14002a0bc  mov     [rsp+180h+var_158], eax; unsigned int
0x14002a0c0  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002a0c7  lea     rax, aGetvistausers; "GetVistaUsers"
0x14002a0ce  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002a0d5  mov     [rsp+180h+var_160], rax; unsigned __int16 *
0x14002a0da  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002a0df  mov     rcx, [rsp+180h+var_148]
0x14002a0e4  test    rcx, rcx
0x14002a0e7  jz      short loc_14002A0FA
0x14002a0e9  mov     rax, [rcx]
0x14002a0ec  mov     rax, [rax+10h]
0x14002a0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a0f5  mov     [rsp+180h+var_148], r15
0x14002a0fa  mov     rcx, [rsp+180h+var_140]
0x14002a0ff  test    rcx, rcx
0x14002a102  jz      short loc_14002A115
0x14002a104  mov     rax, [rcx]
0x14002a107  mov     rax, [rax+10h]
0x14002a10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a110  mov     [rsp+180h+var_140], r15
0x14002a115  mov     rcx, [rsp+180h+ppmk]
0x14002a11a  test    rcx, rcx
0x14002a11d  jz      short loc_14002A130
0x14002a11f  mov     rax, [rcx]
0x14002a122  mov     rax, [rax+10h]
0x14002a126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a12b  mov     [rsp+180h+ppmk], r15
0x14002a130  mov     rcx, [rsp+180h+ppbc]
0x14002a135  test    rcx, rcx
0x14002a138  jz      short loc_14002A146
0x14002a13a  mov     rax, [rcx]
0x14002a13d  mov     rax, [rax+10h]
0x14002a141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a146  mov     eax, ebx
0x14002a148  mov     rcx, [rbp+80h+var_30]
0x14002a14c  xor     rcx, rsp; StackCookie
0x14002a14f  call    __security_check_cookie
0x14002a154  mov     rbx, [rsp+180h+arg_18]
0x14002a15c  add     rsp, 160h
0x14002a163  pop     r15
0x14002a165  pop     r14
0x14002a167  pop     rdi
0x14002a168  pop     rsi
0x14002a169  pop     rbp
0x14002a16a  retn
```

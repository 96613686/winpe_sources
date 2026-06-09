# REDIRECTION_BLOB::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x18000304c`
- end: `0x18000352f`
- name: `?Initialize@REDIRECTION_BLOB@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `1251`
- prototype: `__int64 __fastcall(REDIRECTION_BLOB *this, __int64 (__fastcall ***)(struct IHttpContext *), struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180002758`

## callees

- `0x180002678`
- `0x18000304c`
- `0x180004010`

## import_xrefs

- `msvcrt!wcschr` at `0x180003339`
- `msvcrt!wcschr` at `0x180003339`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003269`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800034f2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003269`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800034f2`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180003322`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000351a`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180003322`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000351a`

## pseudocode

```c
__int64 __fastcall REDIRECTION_BLOB::Initialize(
        REDIRECTION_BLOB *this,
        __int64 (__fastcall ***a2)(struct IHttpContext *),
        struct INativeSectionException **a3)
{
  __int64 (__fastcall **v3)(struct IHttpContext *); // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v8)(_QWORD); // rax
  __int64 v9; // r14
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rax
  int v11; // ebx
  __int64 v13; // rcx
  wchar_t *v14; // rdx
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rcx
  unsigned int i; // esi
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rax
  unsigned __int64 v24; // rdx
  const unsigned __int16 *v25; // rdx
  __int64 v26; // rdx
  int v27; // eax
  __int64 v28; // [rsp+40h] [rbp-40h] BYREF
  __int64 v29; // [rsp+48h] [rbp-38h] BYREF
  __int64 v30; // [rsp+50h] [rbp-30h] BYREF
  __int64 v31; // [rsp+58h] [rbp-28h] BYREF
  wchar_t *Str; // [rsp+60h] [rbp-20h] BYREF
  __int64 v33; // [rsp+68h] [rbp-18h] BYREF
  const unsigned __int16 *v34; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int16 *v35; // [rsp+78h] [rbp-8h] BYREF
  unsigned int v36; // [rsp+B8h] [rbp+38h] BYREF
  int v37; // [rsp+C8h] [rbp+48h] BYREF

  v3 = *a2;
  v33 = 0;
  v28 = 0;
  v31 = 0;
  v6 = v3[20];
  v30 = 0;
  v29 = 0;
  Str = 0;
  v35 = 0;
  v34 = 0;
  v37 = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD))v6((struct IHttpContext *)a2);
  v9 = (**v8)(v8);
  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v11 = (**v10)(v10, &IID_INativeConfigurationSystem, &v33);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, __int64 *))(*(_QWORD *)v33 + 24LL))(
            v33,
            L"system.webServer/httpRedirect",
            v9,
            &v28,
            a3,
            &v29);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v28 + 72LL))(
              v28,
              L"enabled",
              (char *)this + 12,
              0,
              0);
      if ( v11 >= 0 )
      {
        if ( !*((_DWORD *)this + 3) )
        {
LABEL_5:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          v29 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          v28 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          return 0;
        }
        v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v28 + 72LL))(
                v28,
                L"exactDestination",
                (char *)this + 20,
                0,
                0);
        if ( v11 >= 0 )
        {
          v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v28 + 72LL))(
                  v28,
                  L"childOnly",
                  (char *)this + 24,
                  0,
                  0);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                    v28,
                    L"httpResponseStatus",
                    &v37,
                    0,
                    0);
            if ( v11 >= 0 )
            {
              v13 = v28;
              *((_WORD *)this + 4) = v37;
              v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
                      v13,
                      L"destination",
                      &Str,
                      0,
                      0);
              if ( v11 >= 0 )
              {
                v14 = Str;
                if ( *Str )
                {
                  *((_DWORD *)this + 7) = 0;
                  v11 = STRU::Copy((REDIRECTION_BLOB *)((char *)this + 32), v14);
                  if ( v11 < 0 )
                    goto LABEL_12;
                  while ( 1 )
                  {
                    v16 = *((_DWORD *)this + 20);
                    if ( v16 <= 1 )
                      break;
                    v15 = v16 - 1;
                    if ( *(_WORD *)(*((_QWORD *)this + 8) + 2 * v15) != 47 )
                      break;
                    STRU::SetLen((REDIRECTION_BLOB *)((char *)this + 32), v15);
                  }
                  *((_DWORD *)this + 4) = wcschr(Str, 0x24u) != 0;
                }
                else
                {
                  v17 = v28;
                  *((_DWORD *)this + 7) = 1;
                  v36 = 0;
                  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 40LL))(v17, &v31);
                  if ( v11 < 0 )
                    goto LABEL_12;
                  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 24LL))(v31, &v36);
                  if ( v11 < 0 )
                    goto LABEL_12;
                  for ( i = 0; i < v36; v30 = 0 )
                  {
                    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 32LL))(v31, i, &v30);
                    if ( v11 < 0 )
                      goto LABEL_12;
                    v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v30 + 64LL))(
                            v30,
                            L"wildcard",
                            &v35,
                            0,
                            0);
                    if ( v11 < 0 )
                      goto LABEL_12;
                    v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v30 + 64LL))(
                            v30,
                            L"destination",
                            &Str,
                            0,
                            0);
                    if ( v11 < 0 )
                      goto LABEL_12;
                    v11 = REDIRECTION_BLOB::AddWildcardEntry(this, v35, Str);
                    if ( v11 < 0 )
                      goto LABEL_12;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                    ++i;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                  v31 = 0;
                }
                v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v29 + 24LL))(v29, &v34);
                if ( v11 >= 0 )
                {
                  if ( !v34 )
                    goto LABEL_5;
                  v19 = (**a2)((struct IHttpContext *)a2);
                  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
                  v21 = -1;
                  v22 = v20;
                  v23 = -1;
                  do
                    ++v23;
                  while ( *(_WORD *)(v22 + 2 * v23) );
                  v24 = (unsigned int)(v23 + 24);
                  do
                    ++v21;
                  while ( v34[v21] );
                  if ( v21 > v24 )
                    v25 = &v34[v24];
                  else
                    v25 = (const unsigned __int16 *)&dword_180005D64;
                  v34 = v25;
                  v11 = STRU::Copy((REDIRECTION_BLOB *)((char *)this + 88), v25);
                  if ( v11 >= 0 )
                  {
                    while ( 1 )
                    {
                      v27 = *((_DWORD *)this + 34);
                      if ( !v27 )
                        break;
                      v26 = (unsigned int)(v27 - 1);
                      if ( *(_WORD *)(*((_QWORD *)this + 15) + 2 * v26) != 47 )
                        break;
                      STRU::SetLen((REDIRECTION_BLOB *)((char *)this + 88), v26);
                    }
                    goto LABEL_5;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_12:
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000304c  mov     [rsp-28h+arg_0], rbx
0x180003051  mov     [rsp-28h+arg_10], rsi
0x180003056  push    rbp
0x180003057  push    rdi
0x180003058  push    r12
0x18000305a  push    r14
0x18000305c  push    r15
0x18000305e  mov     rbp, rsp
0x180003061  sub     rsp, 80h
0x180003068  mov     rax, [rdx]
0x18000306b  xor     r12d, r12d
0x18000306e  mov     rdi, rcx
0x180003071  mov     [rbp+var_18], r12
0x180003075  mov     rcx, rdx
0x180003078  mov     [rbp+var_40], r12
0x18000307c  mov     rsi, r8
0x18000307f  mov     [rbp+var_28], r12
0x180003083  mov     rax, [rax+0A0h]
0x18000308a  mov     r15, rdx
0x18000308d  mov     [rbp+var_30], r12
0x180003091  mov     [rbp+var_38], r12
0x180003095  mov     [rbp+Str], r12
0x180003099  mov     [rbp+var_8], r12
0x18000309d  mov     [rbp+var_10], r12
0x1800030a1  mov     [rbp+arg_18], r12d
0x1800030a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030aa  mov     rdx, rax
0x1800030ad  mov     rcx, [rax]
0x1800030b0  mov     rax, [rcx]
0x1800030b3  mov     rcx, rdx
0x1800030b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030bb  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800030c2  mov     r14, rax
0x1800030c5  mov     rdx, [rcx]
0x1800030c8  mov     rax, [rdx+38h]
0x1800030cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d1  mov     r9, rax
0x1800030d4  lea     r8, [rbp+var_18]
0x1800030d8  lea     rdx, IID_INativeConfigurationSystem
0x1800030df  mov     rcx, [rax]
0x1800030e2  mov     rax, [rcx]
0x1800030e5  mov     rcx, r9
0x1800030e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ed  mov     ebx, eax
0x1800030ef  test    eax, eax
0x1800030f1  js      loc_180003279
0x1800030f7  mov     rcx, [rbp+var_18]
0x1800030fb  lea     rdx, [rbp+var_38]
0x1800030ff  mov     [rsp+80h+var_58], rdx
0x180003104  lea     r9, [rbp+var_40]
0x180003108  mov     r8, r14
0x18000310b  mov     [rsp+80h+var_60], rsi
0x180003110  lea     rdx, aSystemWebserve; "system.webServer/httpRedirect"
0x180003117  mov     rax, [rcx]
0x18000311a  mov     rax, [rax+18h]
0x18000311e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003123  mov     ebx, eax
0x180003125  test    eax, eax
0x180003127  js      loc_180003279
0x18000312d  mov     rcx, [rbp+var_40]
0x180003131  lea     r8, [rdi+0Ch]
0x180003135  xor     r9d, r9d
0x180003138  mov     [rsp+80h+var_60], r12
0x18000313d  lea     rdx, aEnabled; "enabled"
0x180003144  mov     rax, [rcx]
0x180003147  mov     rax, [rax+48h]
0x18000314b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003150  mov     ebx, eax
0x180003152  test    eax, eax
0x180003154  js      loc_180003279
0x18000315a  cmp     [rdi+0Ch], r12d
0x18000315e  jnz     short loc_18000319F
0x180003160  mov     rcx, [rbp+var_38]
0x180003164  mov     rax, [rcx]
0x180003167  mov     rax, [rax+10h]
0x18000316b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003170  mov     rcx, [rbp+var_40]
0x180003174  mov     [rbp+var_38], r12
0x180003178  mov     rax, [rcx]
0x18000317b  mov     rax, [rax+10h]
0x18000317f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003184  mov     rcx, [rbp+var_18]
0x180003188  mov     [rbp+var_40], r12
0x18000318c  mov     rax, [rcx]
0x18000318f  mov     rax, [rax+10h]
0x180003193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003198  xor     eax, eax
0x18000319a  jmp     loc_1800032F4
0x18000319f  mov     rcx, [rbp+var_40]
0x1800031a3  lea     r8, [rdi+14h]
0x1800031a7  xor     r9d, r9d
0x1800031aa  mov     [rsp+80h+var_60], r12
0x1800031af  lea     rdx, aExactdestinati; "exactDestination"
0x1800031b6  mov     rax, [rcx]
0x1800031b9  mov     rax, [rax+48h]
0x1800031bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c2  mov     ebx, eax
0x1800031c4  test    eax, eax
0x1800031c6  js      loc_180003279
0x1800031cc  mov     rcx, [rbp+var_40]
0x1800031d0  lea     r8, [rdi+18h]
0x1800031d4  xor     r9d, r9d
0x1800031d7  mov     [rsp+80h+var_60], r12
0x1800031dc  lea     rdx, aChildonly; "childOnly"
0x1800031e3  mov     rax, [rcx]
0x1800031e6  mov     rax, [rax+48h]
0x1800031ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ef  mov     ebx, eax
0x1800031f1  test    eax, eax
0x1800031f3  js      loc_180003279
0x1800031f9  mov     rcx, [rbp+var_40]
0x1800031fd  lea     r8, [rbp+arg_18]
0x180003201  xor     r9d, r9d
0x180003204  mov     [rsp+80h+var_60], r12
0x180003209  lea     rdx, aHttpresponsest; "httpResponseStatus"
0x180003210  mov     rax, [rcx]
0x180003213  mov     rax, [rax+30h]
0x180003217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000321c  mov     ebx, eax
0x18000321e  test    eax, eax
0x180003220  js      short loc_180003279
0x180003222  movzx   eax, word ptr [rbp+arg_18]
0x180003226  lea     r8, [rbp+Str]
0x18000322a  mov     rcx, [rbp+var_40]
0x18000322e  lea     rdx, aDestination; "destination"
0x180003235  mov     [rdi+8], ax
0x180003239  xor     r9d, r9d
0x18000323c  mov     [rsp+80h+var_60], r12
0x180003241  mov     rax, [rcx]
0x180003244  mov     rax, [rax+40h]
0x180003248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000324d  mov     ebx, eax
0x18000324f  test    eax, eax
0x180003251  js      short loc_180003279
0x180003253  mov     rdx, [rbp+Str]
0x180003257  cmp     [rdx], r12w
0x18000325b  jz      loc_180003350
0x180003261  lea     rcx, [rdi+20h]
0x180003265  mov     [rdi+1Ch], r12d
0x180003269  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000326f  mov     ebx, eax
0x180003271  test    eax, eax
0x180003273  jns     loc_180003328
0x180003279  mov     rcx, [rbp+var_30]
0x18000327d  test    rcx, rcx
0x180003280  jz      short loc_180003292
0x180003282  mov     rax, [rcx]
0x180003285  mov     rax, [rax+10h]
0x180003289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328e  mov     [rbp+var_30], r12
0x180003292  mov     rcx, [rbp+var_28]
0x180003296  test    rcx, rcx
0x180003299  jz      short loc_1800032AB
0x18000329b  mov     rax, [rcx]
0x18000329e  mov     rax, [rax+10h]
0x1800032a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a7  mov     [rbp+var_28], r12
0x1800032ab  mov     rcx, [rbp+var_40]
0x1800032af  test    rcx, rcx
0x1800032b2  jz      short loc_1800032C4
0x1800032b4  mov     rax, [rcx]
0x1800032b7  mov     rax, [rax+10h]
0x1800032bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c0  mov     [rbp+var_40], r12
0x1800032c4  mov     rcx, [rbp+var_38]
0x1800032c8  test    rcx, rcx
0x1800032cb  jz      short loc_1800032DD
0x1800032cd  mov     rax, [rcx]
0x1800032d0  mov     rax, [rax+10h]
0x1800032d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d9  mov     [rbp+var_38], r12
0x1800032dd  mov     rcx, [rbp+var_18]
0x1800032e1  test    rcx, rcx
0x1800032e4  jz      short loc_1800032F2
0x1800032e6  mov     rax, [rcx]
0x1800032e9  mov     rax, [rax+10h]
0x1800032ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f2  mov     eax, ebx
0x1800032f4  lea     r11, [rsp+80h+var_s0]
0x1800032fc  mov     rbx, [r11+30h]
0x180003300  mov     rsi, [r11+40h]
0x180003304  mov     rsp, r11
0x180003307  pop     r15
0x180003309  pop     r14
0x18000330b  pop     r12
0x18000330d  pop     rdi
0x18000330e  pop     rbp
0x18000330f  retn
0x180003310  lea     edx, [rax-1]
0x180003313  mov     rax, [rdi+40h]
0x180003317  cmp     word ptr [rax+rdx*2], 2Fh ; '/'
0x18000331c  jnz     short loc_180003330
0x18000331e  lea     rcx, [rdi+20h]
0x180003322  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180003328  mov     eax, [rdi+50h]
0x18000332b  cmp     eax, 1
0x18000332e  ja      short loc_180003310
0x180003330  mov     rcx, [rbp+Str]; Str
0x180003334  mov     edx, 24h ; '$'; Ch
0x180003339  call    cs:__imp_wcschr
0x18000333f  mov     ecx, r12d
0x180003342  test    rax, rax
0x180003345  setnz   cl
0x180003348  mov     [rdi+10h], ecx
0x18000334b  jmp     loc_18000346B
0x180003350  mov     rcx, [rbp+var_40]
0x180003354  lea     rdx, [rbp+var_28]
0x180003358  mov     dword ptr [rdi+1Ch], 1
0x18000335f  mov     [rbp+arg_8], r12d
0x180003363  mov     rax, [rcx]
0x180003366  mov     rax, [rax+28h]
0x18000336a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000336f  mov     ebx, eax
0x180003371  test    eax, eax
0x180003373  js      loc_180003279
0x180003379  mov     rcx, [rbp+var_28]
0x18000337d  lea     rdx, [rbp+arg_8]
0x180003381  mov     rax, [rcx]
0x180003384  mov     rax, [rax+18h]
0x180003388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000338d  mov     ebx, eax
0x18000338f  test    eax, eax
0x180003391  js      loc_180003279
0x180003397  mov     esi, r12d
0x18000339a  cmp     [rbp+arg_8], r12d
0x18000339e  jbe     loc_180003457
0x1800033a4  mov     rcx, [rbp+var_28]
0x1800033a8  lea     r8, [rbp+var_30]
0x1800033ac  mov     edx, esi
0x1800033ae  mov     rax, [rcx]
0x1800033b1  mov     rax, [rax+20h]
0x1800033b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ba  mov     ebx, eax
0x1800033bc  test    eax, eax
0x1800033be  js      loc_180003279
0x1800033c4  mov     rcx, [rbp+var_30]
0x1800033c8  lea     r8, [rbp+var_8]
0x1800033cc  xor     r9d, r9d
0x1800033cf  mov     [rsp+80h+var_60], r12
0x1800033d4  lea     rdx, aWildcard; "wildcard"
0x1800033db  mov     rax, [rcx]
0x1800033de  mov     rax, [rax+40h]
0x1800033e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e7  mov     ebx, eax
0x1800033e9  test    eax, eax
0x1800033eb  js      loc_180003279
0x1800033f1  mov     rcx, [rbp+var_30]
0x1800033f5  lea     r8, [rbp+Str]
0x1800033f9  xor     r9d, r9d
0x1800033fc  mov     [rsp+80h+var_60], r12
0x180003401  lea     rdx, aDestination; "destination"
0x180003408  mov     rax, [rcx]
0x18000340b  mov     rax, [rax+40h]
0x18000340f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003414  mov     ebx, eax
0x180003416  test    eax, eax
0x180003418  js      loc_180003279
0x18000341e  mov     r8, [rbp+Str]; unsigned __int16 *
0x180003422  mov     rcx, rdi; this
0x180003425  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x180003429  call    ?AddWildcardEntry@REDIRECTION_BLOB@@QEAAJPEBG0@Z; REDIRECTION_BLOB::AddWildcardEntry(ushort const *,ushort const *)
0x18000342e  mov     ebx, eax
0x180003430  test    eax, eax
0x180003432  js      loc_180003279
0x180003438  mov     rcx, [rbp+var_30]
0x18000343c  mov     rax, [rcx]
0x18000343f  mov     rax, [rax+10h]
0x180003443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003448  inc     esi
0x18000344a  mov     [rbp+var_30], r12
0x18000344e  cmp     esi, [rbp+arg_8]
0x180003451  jb      loc_1800033A4
0x180003457  mov     rcx, [rbp+var_28]
0x18000345b  mov     rax, [rcx]
0x18000345e  mov     rax, [rax+10h]
0x180003462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003467  mov     [rbp+var_28], r12
0x18000346b  mov     rcx, [rbp+var_38]
0x18000346f  lea     rdx, [rbp+var_10]
0x180003473  mov     rax, [rcx]
0x180003476  mov     rax, [rax+18h]
0x18000347a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000347f  mov     ebx, eax
0x180003481  test    eax, eax
0x180003483  js      loc_180003279
0x180003489  cmp     [rbp+var_10], r12
0x18000348d  jz      loc_180003160
0x180003493  mov     rax, [r15]
0x180003496  mov     rcx, r15
0x180003499  mov     rax, [rax]
0x18000349c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034a1  mov     rdx, rax
0x1800034a4  mov     rcx, [rax]
0x1800034a7  mov     rax, [rcx+8]
0x1800034ab  mov     rcx, rdx
0x1800034ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800034b7  mov     rdx, rax
0x1800034ba  mov     rax, rcx
0x1800034bd  inc     rax
  ... truncated ...
```

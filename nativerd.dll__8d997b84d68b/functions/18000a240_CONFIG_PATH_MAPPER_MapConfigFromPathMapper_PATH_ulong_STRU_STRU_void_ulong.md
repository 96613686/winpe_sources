# CONFIG_PATH_MAPPER::MapConfigFromPathMapper(PATH *,ulong,STRU *,STRU *,void * *,ulong *)

- ea: `0x18000a240`
- end: `0x18000a5a6`
- name: `?MapConfigFromPathMapper@CONFIG_PATH_MAPPER@@AEAAJPEAVPATH@@KPEAVSTRU@@1PEAPEAXPEAK@Z`
- size: `870`
- prototype: `int(CONFIG_PATH_MAPPER *__hidden this, struct PATH *, unsigned int, struct STRU *, struct STRU *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180008d00`

## callees

- `0x18000a240`
- `0x180016aa0`
- `0x180017a64`
- `0x180053a54`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a4e1`
- `msvcrt!_wcsicmp` at `0x18000a4e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a592`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a592`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a33c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a33c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a3d4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a482`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a54d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a3d4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a482`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a54d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a2ce`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a2ce`
- `iisutil!MakePathCanonicalizationProof` at `0x18000a559`
- `iisutil!MakePathCanonicalizationProof` at `0x18000a559`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a3bf`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a3dd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a3bf`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a3dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a44b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a456`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a587`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a44b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a456`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a587`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a51e`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a51e`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::MapConfigFromPathMapper(
        CONFIG_PATH_MAPPER *this,
        struct PATH *a2,
        unsigned int a3,
        struct STRU *a4,
        struct STRU *a5,
        void **a6,
        unsigned int *a7)
{
  __int64 v10; // r13
  int appended; // ebp
  OLECHAR *v12; // rsi
  wchar_t *v13; // rdi
  __int64 v14; // rcx
  unsigned int v16; // eax
  const OLECHAR *v17; // rax
  struct STRU *v18; // r13
  const OLECHAR *v19; // rax
  int v20; // eax
  int v21; // eax
  const unsigned __int16 *Str; // rax
  int v23; // eax
  HANDLE v24; // rcx
  const unsigned __int16 *v25; // rax
  BSTR bstrString; // [rsp+30h] [rbp-2C8h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-2C0h] BYREF
  struct STRU *v28; // [rsp+40h] [rbp-2B8h]
  const OLECHAR *v29; // [rsp+48h] [rbp-2B0h]
  void **v30; // [rsp+50h] [rbp-2A8h]
  _BYTE v31[56]; // [rsp+58h] [rbp-2A0h] BYREF
  unsigned __int16 v32[264]; // [rsp+90h] [rbp-268h] BYREF

  v28 = a5;
  v30 = a6;
  v10 = a3;
  bstrString = 0;
  appended = 0;
  hObject = 0;
  v12 = 0;
  v13 = 0;
  memset_0(v32, 0, 0x208u);
  STRU::STRU((STRU *)v31, v32, 0x104u);
  if ( *((_QWORD *)this + 22) && a4 )
  {
    v16 = *((_DWORD *)a2 + 6);
    if ( (unsigned int)v10 >= v16 )
    {
      appended = -2147024809;
      goto LABEL_2;
    }
    if ( *((_DWORD *)a2 + 7) != -1 || v16 == -1 )
    {
      appended = -2147024846;
      goto LABEL_2;
    }
    *(_WORD *)(*((_QWORD *)a2 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)a2 + 8 * v10)) = 0;
    v17 = (const OLECHAR *)*((_QWORD *)a2 + 1);
    *((_DWORD *)a2 + 7) = v10;
    v18 = v28;
    v29 = v17;
    if ( v28 )
    {
      Str = STRU::QueryStr(v28);
      appended = CONFIG_PATH_MAPPER::AppendFileName(a4, Str);
      if ( appended < 0 )
        goto LABEL_2;
      v17 = v29;
    }
    v12 = SysAllocString(v17);
    if ( v12 )
    {
      v19 = STRU::QueryStr(a4);
      v13 = SysAllocString(v19);
      if ( v13 )
      {
        v20 = *((_DWORD *)this + 46);
        if ( v20 )
        {
          if ( v20 != 1 )
          {
            appended = -2147024883;
            goto LABEL_2;
          }
          v21 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, wchar_t *, BSTR *, HANDLE *))(**((_QWORD **)this + 22)
                                                                                          + 24LL))(
                  *((_QWORD *)this + 22),
                  v12,
                  v13,
                  &bstrString,
                  &hObject);
        }
        else
        {
          v21 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, wchar_t *, BSTR *))(**((_QWORD **)this + 22) + 24LL))(
                  *((_QWORD *)this + 22),
                  v12,
                  v13,
                  &bstrString);
        }
        appended = v21;
        if ( v21 >= 0 )
        {
          if ( !bstrString )
          {
            appended = -2147024883;
LABEL_27:
            SysFreeString(v12);
            goto LABEL_5;
          }
          v23 = _wcsicmp(v13, bstrString);
          v24 = hObject;
          if ( v23 || hObject )
          {
            *a7 |= 0x800u;
            if ( v24 )
            {
              hObject = 0;
              *v30 = v24;
              *a7 |= 0x4000u;
            }
          }
          if ( !SysStringLen(bstrString) )
            *a7 |= 0x1000u;
          appended = ExpandEnvironmentVariables(bstrString, (struct STRU *)v31);
          if ( appended >= 0 )
          {
            v25 = STRU::QueryStr((STRU *)v31);
            appended = MakePathCanonicalizationProof(v25, a4);
            if ( appended >= 0 )
            {
              if ( v18 )
                appended = CONFIG_PATH_MAPPER::SplitPhysical(a4, v18);
            }
          }
        }
      }
      else
      {
        appended = -2147024888;
      }
    }
    else
    {
      appended = -2147024888;
    }
  }
LABEL_2:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v12 )
    goto LABEL_27;
LABEL_5:
  if ( v13 )
    SysFreeString(v13);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v14 = *((unsigned int *)a2 + 7);
  if ( (_DWORD)v14 != -1 )
  {
    if ( (_DWORD)v14 != *((_DWORD *)a2 + 6) - 1 )
      *(_WORD *)(*((_QWORD *)a2 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)a2 + 8 * v14)) = 47;
    *((_DWORD *)a2 + 7) = -1;
  }
  STRU::~STRU((STRU *)v31);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000a240  push    rbx
0x18000a242  push    rbp
0x18000a243  push    rsi
0x18000a244  push    rdi
0x18000a245  push    r12
0x18000a247  push    r13
0x18000a249  push    r14
0x18000a24b  push    r15
0x18000a24d  sub     rsp, 2B8h
0x18000a254  mov     rax, cs:__security_cookie
0x18000a25b  xor     rax, rsp
0x18000a25e  mov     [rsp+2F8h+var_58], rax
0x18000a266  mov     rax, [rsp+2F8h+arg_20]
0x18000a26e  mov     rbx, rdx
0x18000a271  mov     r15, [rsp+2F8h+arg_30]
0x18000a279  mov     r14, rcx
0x18000a27c  mov     [rsp+2F8h+var_2B8], rax
0x18000a281  lea     rcx, [rsp+2F8h+var_268]; void *
0x18000a289  mov     rax, [rsp+2F8h+arg_28]
0x18000a291  xor     edx, edx; Val
0x18000a293  mov     [rsp+2F8h+var_2A8], rax
0x18000a298  mov     r12, r9
0x18000a29b  xor     eax, eax
0x18000a29d  mov     r13d, r8d
0x18000a2a0  mov     r8d, 208h; Size
0x18000a2a6  mov     [rsp+2F8h+bstrString], rax
0x18000a2ab  mov     ebp, eax
0x18000a2ad  mov     [rsp+2F8h+hObject], rax
0x18000a2b2  mov     esi, eax
0x18000a2b4  mov     edi, eax
0x18000a2b6  call    memset_0
0x18000a2bb  mov     r8d, 104h
0x18000a2c1  lea     rdx, [rsp+2F8h+var_268]
0x18000a2c9  lea     rcx, [rsp+2F8h+var_2A0]
0x18000a2ce  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000a2d4  cmp     [r14+0B0h], rdi
0x18000a2db  jnz     loc_18000A368
0x18000a2e1  mov     rcx, [rsp+2F8h+bstrString]; bstrString
0x18000a2e6  test    rcx, rcx
0x18000a2e9  jnz     loc_18000A456
0x18000a2ef  test    rsi, rsi
0x18000a2f2  jnz     loc_18000A448
0x18000a2f8  test    rdi, rdi
0x18000a2fb  jnz     loc_18000A584
0x18000a301  mov     rcx, [rsp+2F8h+hObject]; hObject
0x18000a306  test    rcx, rcx
0x18000a309  jnz     loc_18000A592
0x18000a30f  mov     ecx, [rbx+1Ch]
0x18000a312  cmp     ecx, 0FFFFFFFFh
0x18000a315  jz      short loc_18000A337
0x18000a317  mov     eax, [rbx+18h]
0x18000a31a  dec     eax
0x18000a31c  cmp     ecx, eax
0x18000a31e  jz      short loc_18000A330
0x18000a320  mov     rax, [rbx]
0x18000a323  mov     edx, [rax+rcx*8]
0x18000a326  mov     rax, [rbx+8]
0x18000a32a  mov     word ptr [rax+rdx*2], 2Fh ; '/'
0x18000a330  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x18000a337  lea     rcx, [rsp+2F8h+var_2A0]
0x18000a33c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a342  mov     eax, ebp
0x18000a344  mov     rcx, [rsp+2F8h+var_58]
0x18000a34c  xor     rcx, rsp; StackCookie
0x18000a34f  call    __security_check_cookie
0x18000a354  add     rsp, 2B8h
0x18000a35b  pop     r15
0x18000a35d  pop     r14
0x18000a35f  pop     r13
0x18000a361  pop     r12
0x18000a363  pop     rdi
0x18000a364  pop     rsi
0x18000a365  pop     rbp
0x18000a366  pop     rbx
0x18000a367  retn
0x18000a368  test    r12, r12
0x18000a36b  jz      loc_18000A2E1
0x18000a371  mov     eax, [rbx+18h]
0x18000a374  cmp     r13d, eax
0x18000a377  jnb     loc_18000A475
0x18000a37d  cmp     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x18000a381  jnz     loc_18000A46B
0x18000a387  cmp     eax, 0FFFFFFFFh
0x18000a38a  jz      loc_18000A46B
0x18000a390  mov     rax, [rbx]
0x18000a393  mov     rcx, [rbx+8]
0x18000a397  mov     edx, [rax+r13*8]
0x18000a39b  xor     eax, eax
0x18000a39d  mov     [rcx+rdx*2], ax
0x18000a3a1  mov     rax, [rbx+8]
0x18000a3a5  mov     [rbx+1Ch], r13d
0x18000a3a9  mov     r13, [rsp+2F8h+var_2B8]
0x18000a3ae  mov     [rsp+2F8h+var_2B0], rax
0x18000a3b3  test    r13, r13
0x18000a3b6  jnz     loc_18000A47F
0x18000a3bc  mov     rcx, rax; psz
0x18000a3bf  call    cs:__imp_SysAllocString
0x18000a3c5  mov     rsi, rax
0x18000a3c8  test    rax, rax
0x18000a3cb  jz      loc_18000A4A7
0x18000a3d1  mov     rcx, r12
0x18000a3d4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a3da  mov     rcx, rax; psz
0x18000a3dd  call    cs:__imp_SysAllocString
0x18000a3e3  mov     rdi, rax
0x18000a3e6  test    rax, rax
0x18000a3e9  jz      loc_18000A4B1
0x18000a3ef  mov     eax, [r14+0B8h]
0x18000a3f6  test    eax, eax
0x18000a3f8  jz      loc_18000A4BB
0x18000a3fe  cmp     eax, 1
0x18000a401  jnz     short loc_18000A461
0x18000a403  mov     rcx, [r14+0B0h]
0x18000a40a  lea     rdx, [rsp+2F8h+hObject]
0x18000a40f  mov     [rsp+2F8h+var_2D8], rdx
0x18000a414  lea     r9, [rsp+2F8h+bstrString]
0x18000a419  mov     r8, rdi
0x18000a41c  mov     rdx, rsi
0x18000a41f  mov     rax, [rcx]
0x18000a422  mov     rax, [rax+18h]
0x18000a426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a42b  mov     ebp, eax
0x18000a42d  test    eax, eax
0x18000a42f  js      loc_18000A2E1
0x18000a435  mov     rdx, [rsp+2F8h+bstrString]; String2
0x18000a43a  test    rdx, rdx
0x18000a43d  jnz     loc_18000A4DE
0x18000a443  mov     ebp, 8007000Dh
0x18000a448  mov     rcx, rsi; bstrString
0x18000a44b  call    cs:__imp_SysFreeString
0x18000a451  jmp     loc_18000A2F8
0x18000a456  call    cs:__imp_SysFreeString
0x18000a45c  jmp     loc_18000A2EF
0x18000a461  mov     ebp, 8007000Dh
0x18000a466  jmp     loc_18000A2E1
0x18000a46b  mov     ebp, 80070032h
0x18000a470  jmp     loc_18000A2E1
0x18000a475  mov     ebp, 80070057h
0x18000a47a  jmp     loc_18000A2E1
0x18000a47f  mov     rcx, r13
0x18000a482  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a488  mov     rdx, rax; unsigned __int16 *
0x18000a48b  mov     rcx, r12; struct STRU *
0x18000a48e  call    ?AppendFileName@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@PEBG@Z; CONFIG_PATH_MAPPER::AppendFileName(STRU *,ushort const *)
0x18000a493  mov     ebp, eax
0x18000a495  test    eax, eax
0x18000a497  js      loc_18000A2E1
0x18000a49d  mov     rax, [rsp+2F8h+var_2B0]
0x18000a4a2  jmp     loc_18000A3BC
0x18000a4a7  mov     ebp, 80070008h
0x18000a4ac  jmp     loc_18000A2E1
0x18000a4b1  mov     ebp, 80070008h
0x18000a4b6  jmp     loc_18000A2E1
0x18000a4bb  mov     rcx, [r14+0B0h]
0x18000a4c2  lea     r9, [rsp+2F8h+bstrString]
0x18000a4c7  mov     r8, rdi
0x18000a4ca  mov     rdx, rsi
0x18000a4cd  mov     rax, [rcx]
0x18000a4d0  mov     rax, [rax+18h]
0x18000a4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4d9  jmp     loc_18000A42B
0x18000a4de  mov     rcx, rdi; String1
0x18000a4e1  call    cs:__imp__wcsicmp
0x18000a4e7  mov     rcx, [rsp+2F8h+hObject]
0x18000a4ec  test    eax, eax
0x18000a4ee  jnz     short loc_18000A4F5
0x18000a4f0  test    rcx, rcx
0x18000a4f3  jz      short loc_18000A519
0x18000a4f5  or      dword ptr [r15], 800h
0x18000a4fc  test    rcx, rcx
0x18000a4ff  jz      short loc_18000A519
0x18000a501  mov     rax, [rsp+2F8h+var_2A8]
0x18000a506  mov     [rsp+2F8h+hObject], 0
0x18000a50f  mov     [rax], rcx
0x18000a512  or      dword ptr [r15], 4000h
0x18000a519  mov     rcx, [rsp+2F8h+bstrString]; pbstr
0x18000a51e  call    cs:__imp_SysStringLen
0x18000a524  test    eax, eax
0x18000a526  jnz     short loc_18000A52F
0x18000a528  or      dword ptr [r15], 1000h
0x18000a52f  mov     rcx, [rsp+2F8h+bstrString]; lpSrc
0x18000a534  lea     rdx, [rsp+2F8h+var_2A0]; struct STRU *
0x18000a539  call    ?ExpandEnvironmentVariables@@YAJPEBGPEAVSTRU@@@Z; ExpandEnvironmentVariables(ushort const *,STRU *)
0x18000a53e  mov     ebp, eax
0x18000a540  test    eax, eax
0x18000a542  js      loc_18000A2E1
0x18000a548  lea     rcx, [rsp+2F8h+var_2A0]
0x18000a54d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a553  mov     rcx, rax
0x18000a556  mov     rdx, r12
0x18000a559  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18000a55f  mov     ebp, eax
0x18000a561  test    eax, eax
0x18000a563  js      loc_18000A2E1
0x18000a569  test    r13, r13
0x18000a56c  jz      loc_18000A2E1
0x18000a572  mov     rdx, r13; struct STRU *
0x18000a575  mov     rcx, r12; struct STRU *
0x18000a578  call    ?SplitPhysical@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@0@Z; CONFIG_PATH_MAPPER::SplitPhysical(STRU *,STRU *)
0x18000a57d  mov     ebp, eax
0x18000a57f  jmp     loc_18000A2E1
0x18000a584  mov     rcx, rdi; bstrString
0x18000a587  call    cs:__imp_SysFreeString
0x18000a58d  jmp     loc_18000A301
0x18000a592  call    cs:__imp_CloseHandle
0x18000a598  mov     [rsp+2F8h+hObject], 0
0x18000a5a1  jmp     loc_18000A30F
```

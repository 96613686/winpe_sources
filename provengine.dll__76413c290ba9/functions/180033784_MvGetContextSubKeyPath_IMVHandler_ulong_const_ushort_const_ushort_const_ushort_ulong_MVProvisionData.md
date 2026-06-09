# MvGetContextSubKeyPath(IMVHandler *,ulong const *,ushort const *,ushort const *,ushort *,ulong,_MVProvisionData *)

- ea: `0x180033784`
- end: `0x18003397b`
- name: `?MvGetContextSubKeyPath@@YAJPEAUIMVHandler@@PEBKPEBG2PEAGKPEAU_MVProvisionData@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(struct IMVHandler *, const unsigned int *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, struct _MVProvisionData *pv)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002fa98`
- `0x180034380`

## callees

- `0x180005598`
- `0x1800098dc`
- `0x180033560`
- `0x180033784`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033910`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033962`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033910`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033962`

## string_xrefs

- `0x1800337e6`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`
- `0x180033874`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`
- `0x1800338a5`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`
- `0x1800338e6`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MvGetContextSubKeyPath(
        struct IMVHandler *a1,
        const unsigned int *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        struct _MVProvisionData *pv)
{
  unsigned __int16 *v11; // rsi
  int v12; // eax
  unsigned int v13; // edi
  unsigned __int16 *v14; // rbx
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rax
  __int64 v17; // rbx
  int v18; // eax
  struct _MVProvisionData *v19; // rcx
  unsigned __int64 v20; // rdx
  int v21; // eax
  unsigned int v23; // eax
  unsigned int v24; // ebx
  int v25; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+40h]

  v11 = a5;
  *a5 = 0;
  a5 = 0;
  a6 = 0;
  if ( !pv )
  {
    a6 = 1;
LABEL_6:
    v13 = (*(__int64 (__fastcall **)(struct IMVHandler *, unsigned __int16 **, const unsigned int *))(*(_QWORD *)a1 + 88LL))(
            a1,
            &a5,
            a2);
    if ( (v13 & 0x80000000) == 0 )
    {
      v14 = a5;
LABEL_24:
      if ( a4 )
        v23 = StringCchPrintfW(v11, 0x104u, L"%s\\%s\\%s", a3, v14, a4);
      else
        v23 = StringCchPrintfW(v11, 0x104u, L"%s\\%s", a3, v14);
      v24 = v23;
      if ( a5 )
        CoTaskMemFree(a5);
      return v24;
    }
    goto LABEL_20;
  }
  v12 = (*(__int64 (__fastcall **)(struct IMVHandler *, struct _MVProvisionData *, unsigned int *))(*(_QWORD *)a1 + 120LL))(
          a1,
          pv,
          &a6);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
      (const char *)(unsigned int)v12,
      v25);
    goto LABEL_20;
  }
  if ( a6 )
    goto LABEL_6;
  v15 = 0x7FFFFFFF;
  v16 = L"Status";
  do
  {
    if ( !*v16 )
      break;
    ++v16;
    --v15;
  }
  while ( v15 );
  v13 = v15 == 0 ? 0x80070057 : 0;
  v17 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
  if ( !v15 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
      (const char *)v13,
      v25);
    goto LABEL_20;
  }
  pv = 0;
  v18 = CoAllocStringLen(
          (const unsigned __int16 *)v15,
          (0x7FFFFFFF - v15) & -(__int64)(v15 != 0),
          (unsigned __int16 **)&pv);
  v13 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
      (const char *)(unsigned int)v18,
      v25);
    v19 = pv;
    if ( !pv )
      goto LABEL_20;
LABEL_19:
    CoTaskMemFree(v19);
    goto LABEL_20;
  }
  v20 = v17 + 1;
  v14 = (unsigned __int16 *)pv;
  v21 = StringCchPrintfW((unsigned __int16 *)pv, v20, L"Status");
  v13 = v21;
  if ( v21 >= 0 )
  {
    a5 = v14;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x145,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
    (const char *)(unsigned int)v21,
    v25);
  if ( v14 )
  {
    v19 = (struct _MVProvisionData *)v14;
    goto LABEL_19;
  }
LABEL_20:
  if ( a5 )
    CoTaskMemFree(a5);
  return v13;
}

```

## disassembly

```asm
0x180033784  push    rbp
0x180033786  push    rbx
0x180033787  push    rsi
0x180033788  push    rdi
0x180033789  push    r12
0x18003378b  push    r13
0x18003378d  push    r14
0x18003378f  push    r15
0x180033791  mov     rbp, rsp
0x180033794  sub     rsp, 38h
0x180033798  mov     r14, r9
0x18003379b  mov     r12, r8
0x18003379e  mov     r15, rdx
0x1800337a1  mov     rbx, rcx
0x1800337a4  xor     r13d, r13d
0x1800337a7  mov     rsi, [rbp+arg_20]
0x1800337ab  mov     [rsi], r13w
0x1800337af  mov     [rbp+arg_20], r13
0x1800337b3  mov     [rbp+arg_28], r13d
0x1800337b7  mov     rdx, [rbp+pv]
0x1800337bb  test    rdx, rdx
0x1800337be  jnz     short loc_1800337C9
0x1800337c0  mov     [rbp+arg_28], 1
0x1800337c7  jmp     short loc_180033802
0x1800337c9  mov     rax, [rcx]
0x1800337cc  lea     r8, [rbp+arg_28]
0x1800337d0  mov     rax, [rax+78h]
0x1800337d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337d9  mov     edi, eax
0x1800337db  test    eax, eax
0x1800337dd  jns     short loc_1800337FC
0x1800337df  mov     rcx, [rbp+40h]; this
0x1800337e3  mov     r9d, eax; char *
0x1800337e6  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800337ed  mov     edx, 135h; void *
0x1800337f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800337f7  jmp     loc_180033907
0x1800337fc  cmp     [rbp+arg_28], r13d
0x180033800  jz      short loc_18003382B
0x180033802  mov     rax, [rbx]
0x180033805  mov     r8, r15
0x180033808  lea     rdx, [rbp+arg_20]
0x18003380c  mov     rcx, rbx
0x18003380f  mov     rax, [rax+58h]
0x180033813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033818  mov     edi, eax
0x18003381a  test    eax, eax
0x18003381c  js      loc_180033907
0x180033822  mov     rbx, [rbp+arg_20]
0x180033826  jmp     loc_18003391E
0x18003382b  mov     edx, 7FFFFFFFh
0x180033830  mov     ecx, edx
0x180033832  lea     rax, ?gc_szStatusFormat@@3QBGB; "Status"
0x180033839  cmp     [rax], r13w
0x18003383d  jz      short loc_180033849
0x18003383f  add     rax, 2
0x180033843  sub     rcx, 1; unsigned __int16 *
0x180033847  jnz     short loc_180033839
0x180033849  mov     rax, rcx
0x18003384c  neg     rax
0x18003384f  sbb     edi, edi
0x180033851  not     edi
0x180033853  and     edi, 80070057h
0x180033859  mov     rax, rcx
0x18003385c  sub     rdx, rcx
0x18003385f  neg     rax
0x180033862  sbb     rbx, rbx
0x180033865  and     rbx, rdx
0x180033868  test    rcx, rcx
0x18003386b  jnz     short loc_180033888
0x18003386d  mov     rcx, [rbp+40h]; this
0x180033871  mov     r9d, edi; char *
0x180033874  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003387b  mov     edx, 141h; void *
0x180033880  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033885  nop
0x180033886  jmp     short loc_180033907
0x180033888  mov     [rbp+pv], r13
0x18003388c  lea     r8, [rbp+pv]; unsigned __int16 **
0x180033890  mov     rdx, rbx; unsigned __int64
0x180033893  call    ?CoAllocStringLen@@YAJPEBG_KPEAPEAG@Z; CoAllocStringLen(ushort const *,unsigned __int64,ushort * *)
0x180033898  mov     edi, eax
0x18003389a  test    eax, eax
0x18003389c  jns     short loc_1800338C2
0x18003389e  mov     rcx, [rbp+40h]; this
0x1800338a2  mov     r9d, eax; char *
0x1800338a5  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800338ac  mov     edx, 143h; void *
0x1800338b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800338b6  nop
0x1800338b7  mov     rcx, [rbp+pv]
0x1800338bb  test    rcx, rcx
0x1800338be  jz      short loc_180033907
0x1800338c0  jmp     short loc_180033900
0x1800338c2  lea     rdx, [rbx+1]; unsigned __int64
0x1800338c6  lea     r8, ?gc_szStatusFormat@@3QBGB; "Status"
0x1800338cd  mov     rbx, [rbp+pv]
0x1800338d1  mov     rcx, rbx; unsigned __int16 *
0x1800338d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800338d9  mov     edi, eax
0x1800338db  test    eax, eax
0x1800338dd  jns     short loc_18003391A
0x1800338df  mov     rcx, [rbp+40h]; this
0x1800338e3  mov     r9d, eax; char *
0x1800338e6  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800338ed  mov     edx, 145h; void *
0x1800338f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800338f7  nop
0x1800338f8  test    rbx, rbx
0x1800338fb  jz      short loc_180033907
0x1800338fd  mov     rcx, rbx; pv
0x180033900  call    cs:__imp_CoTaskMemFree
0x180033906  nop
0x180033907  mov     rcx, [rbp+arg_20]; pv
0x18003390b  test    rcx, rcx
0x18003390e  jz      short loc_180033916
0x180033910  call    cs:__imp_CoTaskMemFree
0x180033916  mov     eax, edi
0x180033918  jmp     short loc_18003396A
0x18003391a  mov     [rbp+arg_20], rbx
0x18003391e  mov     r9, r12
0x180033921  mov     edx, 104h; unsigned __int64
0x180033926  mov     rcx, rsi; unsigned __int16 *
0x180033929  test    r14, r14
0x18003392c  jz      short loc_180033946
0x18003392e  mov     [rsp+38h+var_10], r14
0x180033933  mov     [rsp+38h+var_18], rbx
0x180033938  lea     r8, ?gc_szConcatThreePathsFormat@@3QBGB; "%s\\%s\\%s"
0x18003393f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033944  jmp     short loc_180033957
0x180033946  mov     [rsp+38h+var_18], rbx
0x18003394b  lea     r8, ?gc_szConcatTwoPathsFormat@@3QBGB; "%s\\%s"
0x180033952  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033957  mov     ebx, eax
0x180033959  mov     rcx, [rbp+arg_20]; pv
0x18003395d  test    rcx, rcx
0x180033960  jz      short loc_180033968
0x180033962  call    cs:__imp_CoTaskMemFree
0x180033968  mov     eax, ebx
0x18003396a  add     rsp, 38h
0x18003396e  pop     r15
0x180033970  pop     r14
0x180033972  pop     r13
0x180033974  pop     r12
0x180033976  pop     rdi
0x180033977  pop     rsi
0x180033978  pop     rbx
0x180033979  pop     rbp
0x18003397a  retn
```

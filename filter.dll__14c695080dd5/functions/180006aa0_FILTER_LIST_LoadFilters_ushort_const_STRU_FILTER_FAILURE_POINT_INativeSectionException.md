# FILTER_LIST::LoadFilters(ushort const *,STRU *,FILTER_FAILURE_POINT *,INativeSectionException * *)

- ea: `0x180006aa0`
- end: `0x180006dfb`
- name: `?LoadFilters@FILTER_LIST@@QEAAJPEBGPEAVSTRU@@PEAW4FILTER_FAILURE_POINT@@PEAPEAVINativeSectionException@@@Z`
- size: `859`
- prototype: `__int64 __fastcall(FILTER_LIST *this, const unsigned __int16 *, struct STRU *, enum FILTER_FAILURE_POINT *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180002fc0`

## callees

- `0x180006aa0`
- `0x180006e10`
- `0x180007490`
- `0x18000d010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006ce8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006ce8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006cd6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006cd6`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006d5e`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006d5e`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006d08`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006d08`

## string_xrefs

- `0x180006cbd`: `enableCache`

## pseudocode

```c
__int64 __fastcall FILTER_LIST::LoadFilters(
        FILTER_LIST *this,
        const unsigned __int16 *a2,
        struct STRU *a3,
        enum FILTER_FAILURE_POINT *a4,
        struct INativeSectionException **a5)
{
  __int64 v9; // rax
  __int64 (__fastcall *v10)(struct IHttpServer *); // rax
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rax
  int Filter; // edi
  unsigned int i; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  bool v17; // zf
  int v18; // edi
  const unsigned __int16 *Str; // rax
  unsigned int v20; // eax
  __int64 *v22; // [rsp+40h] [rbp-41h] BYREF
  __int64 *v23; // [rsp+48h] [rbp-39h] BYREF
  __int64 v24; // [rsp+50h] [rbp-31h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-29h] BYREF
  int v26; // [rsp+5Ch] [rbp-25h] BYREF
  int v27; // [rsp+60h] [rbp-21h] BYREF
  int v28; // [rsp+64h] [rbp-1Dh] BYREF
  __int64 v29; // [rsp+68h] [rbp-19h] BYREF
  __int64 v30; // [rsp+70h] [rbp-11h] BYREF
  const unsigned __int16 *v31; // [rsp+78h] [rbp-9h] BYREF
  const unsigned __int16 *v32; // [rsp+80h] [rbp-1h] BYREF

  v29 = 0;
  v24 = 0;
  v23 = 0;
  v9 = *(_QWORD *)g_pGlobalInfo;
  v22 = 0;
  v31 = 0;
  v30 = 0;
  v10 = *(__int64 (__fastcall **)(struct IHttpServer *))(v9 + 56);
  v26 = 0;
  v28 = 0;
  v25 = 0;
  v27 = 0;
  v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v10(g_pGlobalInfo);
  Filter = (**v11)(v11, &IID_INativeConfigurationSystem, &v29);
  if ( Filter < 0
    || (Filter = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v29 + 24LL))(
                   v29,
                   L"system.webServer/isapiFilters",
                   a2,
                   &v24,
                   a5,
                   0),
        Filter < 0)
    || (Filter = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v24 + 40LL))(v24, &v23),
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24),
        v24 = 0,
        Filter < 0)
    || (Filter = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v23 + 24))(v23, &v25), Filter < 0) )
  {
LABEL_20:
    v32 = a2 + 24;
    v20 = WIN32_FROM_HRESULT(Filter);
    EVENT_LOG::LogEvent((EVENT_LOG *)g_pEventLog, 0xC00008DC, 1u, &v32, v20);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
      v22 = 0;
    }
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
      v23 = 0;
    }
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v24 = 0;
    }
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    return (unsigned int)Filter;
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      v14 = *v23;
      if ( i >= v25 )
        break;
      Filter = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v14 + 32))(v23, i, &v22);
      if ( Filter < 0 )
        goto LABEL_20;
      Filter = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, int *, _QWORD, _QWORD))(*v22 + 72))(
                 v22,
                 L"enabled",
                 &v26,
                 0,
                 0);
      if ( Filter < 0 )
        goto LABEL_20;
      v15 = *v22;
      if ( v26 )
      {
        Filter = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(v15 + 64))(
                   v22,
                   L"path",
                   &v31,
                   0,
                   0);
        if ( Filter < 0 )
          goto LABEL_20;
        Filter = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *, _QWORD, _QWORD))(*v22 + 64))(
                   v22,
                   L"preCondition",
                   &v30,
                   0,
                   0);
        if ( Filter < 0 )
          goto LABEL_20;
        v16 = (*(__int64 (__fastcall **)(struct IHttpServer *, __int64, int *))(*(_QWORD *)g_pGlobalInfo + 176LL))(
                g_pGlobalInfo,
                v30,
                &v27);
        if ( v27 )
        {
          *(_DWORD *)a4 = 5;
          Filter = -2147024883;
          goto LABEL_20;
        }
        v17 = v16 == 0;
        v15 = *v22;
        if ( !v17 )
        {
          Filter = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, int *, _QWORD, _QWORD))(v15 + 72))(
                     v22,
                     L"enableCache",
                     &v28,
                     0,
                     0);
          if ( Filter < 0 )
            goto LABEL_20;
          Filter = STRU::Copy(a3, v31);
          if ( Filter < 0 )
            goto LABEL_20;
          v18 = v28;
          Str = STRU::QueryStr(a3);
          Filter = FILTER_LIST::LoadFilter(this, Str, v18, a4);
          if ( Filter < 0 )
            goto LABEL_20;
          STRU::Reset(a3);
          v15 = *v22;
        }
      }
      (*(void (**)(void))(v15 + 16))();
      v22 = 0;
    }
    (*(void (**)(void))(v14 + 16))();
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    return 0;
  }
}

```

## disassembly

```asm
0x180006aa0  push    rbp
0x180006aa2  push    rbx
0x180006aa3  push    rsi
0x180006aa4  push    rdi
0x180006aa5  push    r12
0x180006aa7  push    r13
0x180006aa9  push    r14
0x180006aab  push    r15
0x180006aad  lea     rbp, [rsp-17h]
0x180006ab2  sub     rsp, 98h
0x180006ab9  xor     r13d, r13d
0x180006abc  mov     r12, rcx
0x180006abf  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180006ac6  mov     r15, r9
0x180006ac9  mov     rsi, r8
0x180006acc  mov     [rbp+4Fh+var_68], r13
0x180006ad0  mov     r14, rdx
0x180006ad3  mov     [rbp+4Fh+var_80], r13
0x180006ad7  mov     [rbp+4Fh+var_88], r13
0x180006adb  mov     rax, [rcx]
0x180006ade  mov     [rbp+4Fh+var_90], r13
0x180006ae2  mov     [rbp+4Fh+var_58], r13
0x180006ae6  mov     [rbp+4Fh+var_60], r13
0x180006aea  mov     rax, [rax+38h]
0x180006aee  mov     [rbp+4Fh+var_74], r13d
0x180006af2  mov     [rbp+4Fh+var_6C], r13d
0x180006af6  mov     [rbp+4Fh+var_78], r13d
0x180006afa  mov     [rbp+4Fh+var_70], r13d
0x180006afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b03  mov     r9, rax
0x180006b06  lea     r8, [rbp+4Fh+var_68]
0x180006b0a  lea     rdx, IID_INativeConfigurationSystem
0x180006b11  mov     rcx, [rax]
0x180006b14  mov     rax, [rcx]
0x180006b17  mov     rcx, r9
0x180006b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b1f  mov     edi, eax
0x180006b21  test    eax, eax
0x180006b23  js      loc_180006D35
0x180006b29  mov     rcx, [rbp+4Fh+var_68]
0x180006b2d  lea     r9, [rbp+4Fh+var_80]
0x180006b31  mov     rdx, [rbp+4Fh+arg_20]
0x180006b35  mov     r8, r14
0x180006b38  mov     [rsp+0D0h+var_A8], r13
0x180006b3d  mov     [rsp+0D0h+var_B0], rdx
0x180006b42  lea     rdx, aSystemWebserve; "system.webServer/isapiFilters"
0x180006b49  mov     rax, [rcx]
0x180006b4c  mov     rax, [rax+18h]
0x180006b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b55  mov     edi, eax
0x180006b57  test    eax, eax
0x180006b59  js      loc_180006D35
0x180006b5f  mov     rcx, [rbp+4Fh+var_80]
0x180006b63  lea     rdx, [rbp+4Fh+var_88]
0x180006b67  mov     rax, [rcx]
0x180006b6a  mov     rax, [rax+28h]
0x180006b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b73  mov     rcx, [rbp+4Fh+var_80]
0x180006b77  mov     edi, eax
0x180006b79  mov     rax, [rcx]
0x180006b7c  mov     rax, [rax+10h]
0x180006b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b85  mov     [rbp+4Fh+var_80], r13
0x180006b89  test    edi, edi
0x180006b8b  js      loc_180006D35
0x180006b91  mov     rcx, [rbp+4Fh+var_88]
0x180006b95  lea     rdx, [rbp+4Fh+var_78]
0x180006b99  mov     rax, [rcx]
0x180006b9c  mov     rax, [rax+18h]
0x180006ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba5  mov     edi, eax
0x180006ba7  test    eax, eax
0x180006ba9  js      loc_180006D35
0x180006baf  mov     ebx, r13d
0x180006bb2  nop     dword ptr [rax+00h]
0x180006bb6  nop     word ptr [rax+rax+00000000h]
0x180006bc0  mov     rcx, [rbp+4Fh+var_88]
0x180006bc4  mov     rax, [rcx]
0x180006bc7  cmp     ebx, [rbp+4Fh+var_78]
0x180006bca  jnb     loc_180006DDA
0x180006bd0  mov     rax, [rax+20h]
0x180006bd4  lea     r8, [rbp+4Fh+var_90]
0x180006bd8  mov     edx, ebx
0x180006bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bdf  mov     edi, eax
0x180006be1  test    eax, eax
0x180006be3  js      loc_180006D35
0x180006be9  mov     rcx, [rbp+4Fh+var_90]
0x180006bed  lea     r8, [rbp+4Fh+var_74]
0x180006bf1  xor     r9d, r9d
0x180006bf4  mov     [rsp+0D0h+var_B0], r13
0x180006bf9  lea     rdx, aEnabled; "enabled"
0x180006c00  mov     rax, [rcx]
0x180006c03  mov     rax, [rax+48h]
0x180006c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c0c  mov     edi, eax
0x180006c0e  test    eax, eax
0x180006c10  js      loc_180006D35
0x180006c16  mov     rcx, [rbp+4Fh+var_90]
0x180006c1a  mov     rax, [rcx]
0x180006c1d  cmp     [rbp+4Fh+var_74], r13d
0x180006c21  jz      loc_180006D15
0x180006c27  mov     rax, [rax+40h]
0x180006c2b  lea     r8, [rbp+4Fh+var_58]
0x180006c2f  xor     r9d, r9d
0x180006c32  mov     [rsp+0D0h+var_B0], r13
0x180006c37  lea     rdx, aPath; "path"
0x180006c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c43  mov     edi, eax
0x180006c45  test    eax, eax
0x180006c47  js      loc_180006D35
0x180006c4d  mov     rcx, [rbp+4Fh+var_90]
0x180006c51  lea     r8, [rbp+4Fh+var_60]
0x180006c55  xor     r9d, r9d
0x180006c58  mov     [rsp+0D0h+var_B0], r13
0x180006c5d  lea     rdx, aPrecondition; "preCondition"
0x180006c64  mov     rax, [rcx]
0x180006c67  mov     rax, [rax+40h]
0x180006c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c70  mov     edi, eax
0x180006c72  test    eax, eax
0x180006c74  js      loc_180006D35
0x180006c7a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180006c81  lea     r8, [rbp+4Fh+var_70]
0x180006c85  mov     rdx, [rbp+4Fh+var_60]
0x180006c89  mov     rax, [rcx]
0x180006c8c  mov     rax, [rax+0B0h]
0x180006c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c98  cmp     [rbp+4Fh+var_70], r13d
0x180006c9c  jnz     loc_180006D29
0x180006ca2  mov     rcx, [rbp+4Fh+var_90]
0x180006ca6  test    eax, eax
0x180006ca8  mov     rax, [rcx]
0x180006cab  jz      short loc_180006D15
0x180006cad  mov     rax, [rax+48h]
0x180006cb1  lea     r8, [rbp+4Fh+var_6C]
0x180006cb5  xor     r9d, r9d
0x180006cb8  mov     [rsp+0D0h+var_B0], r13
0x180006cbd  lea     rdx, aEnablecache; "enableCache"
0x180006cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc9  mov     edi, eax
0x180006ccb  test    eax, eax
0x180006ccd  js      short loc_180006D35
0x180006ccf  mov     rdx, [rbp+4Fh+var_58]
0x180006cd3  mov     rcx, rsi
0x180006cd6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006cdc  mov     edi, eax
0x180006cde  test    eax, eax
0x180006ce0  js      short loc_180006D35
0x180006ce2  mov     edi, [rbp+4Fh+var_6C]
0x180006ce5  mov     rcx, rsi
0x180006ce8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006cee  mov     r9, r15; enum FILTER_FAILURE_POINT *
0x180006cf1  mov     r8d, edi; int
0x180006cf4  mov     rdx, rax; unsigned __int16 *
0x180006cf7  mov     rcx, r12; this
0x180006cfa  call    ?LoadFilter@FILTER_LIST@@AEAAJPEBGHPEAW4FILTER_FAILURE_POINT@@@Z; FILTER_LIST::LoadFilter(ushort const *,int,FILTER_FAILURE_POINT *)
0x180006cff  mov     edi, eax
0x180006d01  test    eax, eax
0x180006d03  js      short loc_180006D35
0x180006d05  mov     rcx, rsi
0x180006d08  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180006d0e  mov     rcx, [rbp+4Fh+var_90]
0x180006d12  mov     rax, [rcx]
0x180006d15  mov     rax, [rax+10h]
0x180006d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1e  inc     ebx
0x180006d20  mov     [rbp+4Fh+var_90], r13
0x180006d24  jmp     loc_180006BC0
0x180006d29  mov     dword ptr [r15], 5
0x180006d30  mov     edi, 8007000Dh
0x180006d35  lea     rax, [r14+30h]
0x180006d39  mov     ecx, edi; int
0x180006d3b  mov     [rbp+4Fh+var_50], rax
0x180006d3f  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180006d44  mov     rcx, cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_pEventLog
0x180006d4b  lea     r9, [rbp+4Fh+var_50]
0x180006d4f  mov     edx, 0C00008DCh
0x180006d54  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180006d58  mov     r8d, 1
0x180006d5e  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180006d64  mov     rcx, [rbp+4Fh+var_90]
0x180006d68  test    rcx, rcx
0x180006d6b  jz      short loc_180006D7D
0x180006d6d  mov     rax, [rcx]
0x180006d70  mov     rax, [rax+10h]
0x180006d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d79  mov     [rbp+4Fh+var_90], r13
0x180006d7d  mov     rcx, [rbp+4Fh+var_88]
0x180006d81  test    rcx, rcx
0x180006d84  jz      short loc_180006D96
0x180006d86  mov     rax, [rcx]
0x180006d89  mov     rax, [rax+10h]
0x180006d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d92  mov     [rbp+4Fh+var_88], r13
0x180006d96  mov     rcx, [rbp+4Fh+var_80]
0x180006d9a  test    rcx, rcx
0x180006d9d  jz      short loc_180006DAF
0x180006d9f  mov     rax, [rcx]
0x180006da2  mov     rax, [rax+10h]
0x180006da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dab  mov     [rbp+4Fh+var_80], r13
0x180006daf  mov     rcx, [rbp+4Fh+var_68]
0x180006db3  test    rcx, rcx
0x180006db6  jz      short loc_180006DC4
0x180006db8  mov     rax, [rcx]
0x180006dbb  mov     rax, [rax+10h]
0x180006dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc4  mov     eax, edi
0x180006dc6  add     rsp, 98h
0x180006dcd  pop     r15
0x180006dcf  pop     r14
0x180006dd1  pop     r13
0x180006dd3  pop     r12
0x180006dd5  pop     rdi
0x180006dd6  pop     rsi
0x180006dd7  pop     rbx
0x180006dd8  pop     rbp
0x180006dd9  retn
0x180006dda  mov     rax, [rax+10h]
0x180006dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006de3  mov     rcx, [rbp+4Fh+var_68]
0x180006de7  mov     [rbp+4Fh+var_88], r13
0x180006deb  mov     rax, [rcx]
0x180006dee  mov     rax, [rax+10h]
0x180006df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006df7  xor     eax, eax
0x180006df9  jmp     short loc_180006DC6
```

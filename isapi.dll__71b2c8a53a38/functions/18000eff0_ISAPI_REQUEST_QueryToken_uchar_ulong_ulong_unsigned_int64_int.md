# ISAPI_REQUEST::QueryToken(uchar *,ulong,ulong,unsigned __int64 *,int)

- ea: `0x18000eff0`
- end: `0x18000f23d`
- name: `?QueryToken@ISAPI_REQUEST@@UEAAJPEAEKKPEA_KH@Z`
- size: `589`
- prototype: `__int64 __usercall@<rax>(ISAPI_REQUEST *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int64 *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x18000d340`
- `0x18000d5b8`
- `0x18000eff0`
- `0x180012482`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f20e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f20e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f077`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f077`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f11e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f198`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f11e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f198`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000f04e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000f04e`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000f07f`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000f07f`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::QueryToken(
        ISAPI_REQUEST *this,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4,
        unsigned __int64 *a5,
        int a6)
{
  int v9; // eax
  int AppVrToken; // ebx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, struct INativeConfigurationSystem **); // rax
  int v12; // eax
  const unsigned __int16 *Str; // rbx
  __int64 v14; // rax
  const unsigned __int16 *v15; // rax
  void (*v16)(void); // rax
  const unsigned __int16 *v17; // rbx
  __int64 v18; // rax
  const unsigned __int16 *v19; // rax
  struct INativeConfigurationSystem *v21; // [rsp+30h] [rbp-D0h] BYREF
  struct INativeMappingExtension *v22; // [rsp+38h] [rbp-C8h] BYREF
  void *v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[56]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v25[264]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v25, 0, 0x208u);
  STRU::STRU((STRU *)v24, v25, 0x104u);
  v23 = 0;
  v21 = 0;
  if ( a6 )
    v9 = STRU::Copy((STRU *)v24, a2);
  else
    v9 = STRU::CopyA((STRU *)v24, (const char *)a2);
  AppVrToken = v9;
  if ( v9 >= 0 )
  {
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct INativeConfigurationSystem **))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
    v12 = (**v11)(v11, &IID_INativeConfigurationSystem, &v21);
    AppVrToken = v12;
    if ( a4 == 2 )
    {
      if ( v12 < 0 )
        goto LABEL_14;
      v22 = 0;
      AppVrToken = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, struct INativeMappingExtension **))(*(_QWORD *)v21 + 56LL))(
                     v21,
                     &v22);
      if ( AppVrToken < 0 )
      {
        (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v21 + 16LL))(v21);
        v21 = 0;
        goto LABEL_14;
      }
      Str = STRU::QueryStr((STRU *)v24);
      v14 = (***((__int64 (__fastcall ****)(_QWORD))this + 3))(*((_QWORD *)this + 3));
      v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      AppVrToken = ISAPI_REQUEST::GetAppVrToken(this, v22, v15, Str, &v23);
      (*(void (__fastcall **)(struct INativeMappingExtension *))(*(_QWORD *)v22 + 16LL))(v22);
      v22 = 0;
      v16 = *(void (**)(void))(*(_QWORD *)v21 + 16LL);
    }
    else
    {
      if ( v12 < 0 )
        goto LABEL_14;
      v17 = STRU::QueryStr((STRU *)v24);
      v18 = (***((__int64 (__fastcall ****)(_QWORD))this + 3))(*((_QWORD *)this + 3));
      v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      AppVrToken = ISAPI_REQUEST::GetAnonymousToken(this, v21, v19, v17, &v23);
      v16 = *(void (**)(void))(*(_QWORD *)v21 + 16LL);
    }
    v16();
    v21 = 0;
    if ( AppVrToken >= 0 )
    {
      AppVrToken = 0;
      *a5 = (unsigned __int64)v23;
    }
  }
LABEL_14:
  STRU::~STRU((STRU *)v24);
  return (unsigned int)AppVrToken;
}

```

## disassembly

```asm
0x18000eff0  mov     [rsp-8+arg_10], rbx
0x18000eff5  mov     [rsp-8+arg_18], rsi
0x18000effa  push    rbp
0x18000effb  push    rdi
0x18000effc  push    r14
0x18000effe  lea     rbp, [rsp-1A0h]
0x18000f006  sub     rsp, 2A0h
0x18000f00d  mov     rax, cs:__security_cookie
0x18000f014  xor     rax, rsp
0x18000f017  mov     [rbp+1B0h+var_20], rax
0x18000f01e  mov     rsi, [rbp+1B0h+arg_20]
0x18000f025  mov     rbx, rdx
0x18000f028  mov     r14, rcx
0x18000f02b  xor     edx, edx; Val
0x18000f02d  lea     rcx, [rbp+1B0h+var_230]; void *
0x18000f031  mov     r8d, 208h; Size
0x18000f037  mov     edi, r9d
0x18000f03a  call    memset_0
0x18000f03f  mov     r8d, 104h
0x18000f045  lea     rdx, [rbp+1B0h+var_230]
0x18000f049  lea     rcx, [rsp+2B0h+var_268]
0x18000f04e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000f054  cmp     [rbp+1B0h+arg_28], 0
0x18000f05b  lea     rcx, [rsp+2B0h+var_268]
0x18000f060  mov     [rsp+2B0h+var_270], 0
0x18000f069  mov     rdx, rbx
0x18000f06c  mov     [rsp+2B0h+var_280], 0
0x18000f075  jz      short loc_18000F07F
0x18000f077  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f07d  jmp     short loc_18000F085
0x18000f07f  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000f085  mov     ebx, eax
0x18000f087  test    eax, eax
0x18000f089  js      loc_18000F209
0x18000f08f  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000f096  mov     rax, [rcx]
0x18000f099  mov     rax, [rax+38h]
0x18000f09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0a2  mov     r9, rax
0x18000f0a5  lea     r8, [rsp+2B0h+var_280]
0x18000f0aa  lea     rdx, IID_INativeConfigurationSystem
0x18000f0b1  mov     rcx, [rax]
0x18000f0b4  mov     rax, [rcx]
0x18000f0b7  mov     rcx, r9
0x18000f0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0bf  mov     ebx, eax
0x18000f0c1  cmp     edi, 2
0x18000f0c4  jnz     loc_18000F18F
0x18000f0ca  test    eax, eax
0x18000f0cc  js      loc_18000F209
0x18000f0d2  mov     rcx, [rsp+2B0h+var_280]
0x18000f0d7  lea     rdx, [rsp+2B0h+var_278]
0x18000f0dc  mov     [rsp+2B0h+var_278], 0
0x18000f0e5  mov     rax, [rcx]
0x18000f0e8  mov     rax, [rax+38h]
0x18000f0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0f1  mov     ebx, eax
0x18000f0f3  test    eax, eax
0x18000f0f5  jns     short loc_18000F119
0x18000f0f7  mov     rdx, [rsp+2B0h+var_280]
0x18000f0fc  mov     rcx, [rdx]
0x18000f0ff  mov     rax, [rcx+10h]
0x18000f103  mov     rcx, rdx
0x18000f106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f10b  mov     [rsp+2B0h+var_280], 0
0x18000f114  jmp     loc_18000F209
0x18000f119  lea     rcx, [rsp+2B0h+var_268]
0x18000f11e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000f124  mov     rdx, [r14+18h]
0x18000f128  mov     rbx, rax
0x18000f12b  mov     rcx, [rdx]
0x18000f12e  mov     rax, [rcx]
0x18000f131  mov     rcx, rdx
0x18000f134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f139  mov     rcx, rax
0x18000f13c  mov     rdx, [rax]
0x18000f13f  mov     rax, [rdx+8]
0x18000f143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f148  mov     rdx, [rsp+2B0h+var_278]; struct INativeMappingExtension *
0x18000f14d  lea     rcx, [rsp+2B0h+var_270]
0x18000f152  mov     [rsp+2B0h+var_290], rcx; void **
0x18000f157  mov     r9, rbx; unsigned __int16 *
0x18000f15a  mov     rcx, r14; this
0x18000f15d  mov     r8, rax; unsigned __int16 *
0x18000f160  call    ?GetAppVrToken@ISAPI_REQUEST@@QEAAJPEAVINativeMappingExtension@@PEBG1PEAPEAX@Z; ISAPI_REQUEST::GetAppVrToken(INativeMappingExtension *,ushort const *,ushort const *,void * *)
0x18000f165  mov     rcx, [rsp+2B0h+var_278]
0x18000f16a  mov     ebx, eax
0x18000f16c  mov     rdx, [rcx]
0x18000f16f  mov     rax, [rdx+10h]
0x18000f173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f178  mov     rcx, [rsp+2B0h+var_280]
0x18000f17d  mov     [rsp+2B0h+var_278], 0
0x18000f186  mov     rdx, [rcx]
0x18000f189  mov     rax, [rdx+10h]
0x18000f18d  jmp     short loc_18000F1ED
0x18000f18f  lea     rcx, [rsp+2B0h+var_268]
0x18000f194  test    eax, eax
0x18000f196  js      short loc_18000F20E
0x18000f198  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000f19e  mov     rcx, [r14+18h]
0x18000f1a2  mov     rbx, rax
0x18000f1a5  mov     rdx, [rcx]
0x18000f1a8  mov     rax, [rdx]
0x18000f1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1b0  mov     rdx, rax
0x18000f1b3  mov     rcx, [rax]
0x18000f1b6  mov     rax, [rcx+8]
0x18000f1ba  mov     rcx, rdx
0x18000f1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1c2  mov     rdx, [rsp+2B0h+var_280]; struct INativeConfigurationSystem *
0x18000f1c7  lea     rcx, [rsp+2B0h+var_270]
0x18000f1cc  mov     [rsp+2B0h+var_290], rcx; void **
0x18000f1d1  mov     r9, rbx; unsigned __int16 *
0x18000f1d4  mov     rcx, r14; this
0x18000f1d7  mov     r8, rax; unsigned __int16 *
0x18000f1da  call    ?GetAnonymousToken@ISAPI_REQUEST@@QEAAJPEAVINativeConfigurationSystem@@PEBG1PEAPEAX@Z; ISAPI_REQUEST::GetAnonymousToken(INativeConfigurationSystem *,ushort const *,ushort const *,void * *)
0x18000f1df  mov     rcx, [rsp+2B0h+var_280]
0x18000f1e4  mov     ebx, eax
0x18000f1e6  mov     rax, [rcx]
0x18000f1e9  mov     rax, [rax+10h]
0x18000f1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1f2  mov     [rsp+2B0h+var_280], 0
0x18000f1fb  test    ebx, ebx
0x18000f1fd  js      short loc_18000F209
0x18000f1ff  mov     rax, [rsp+2B0h+var_270]
0x18000f204  xor     ebx, ebx
0x18000f206  mov     [rsi], rax
0x18000f209  lea     rcx, [rsp+2B0h+var_268]
0x18000f20e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f214  mov     eax, ebx
0x18000f216  mov     rcx, [rbp+1B0h+var_20]
0x18000f21d  xor     rcx, rsp; StackCookie
0x18000f220  call    __security_check_cookie
0x18000f225  lea     r11, [rsp+2B0h+var_10]
0x18000f22d  mov     rbx, [r11+30h]
0x18000f231  mov     rsi, [r11+38h]
0x18000f235  mov     rsp, r11
0x18000f238  pop     r14
0x18000f23a  pop     rdi
0x18000f23b  pop     rbp
0x18000f23c  retn
```

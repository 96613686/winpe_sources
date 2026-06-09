# IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_ const &,_STORE_DEPLOYMENT_METADATA_PROPERTY &)

- ea: `0x18010b978`
- end: `0x18010bb7b`
- name: `?CopyOut@Com@IsolationImplementation@@YAJAEBU_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_@Rtl@Isolation@Windows@@AEAU_STORE_DEPLOYMENT_METADATA_PROPERTY@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(IsolationImplementation::Com *__hidden this, const struct Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_ *, struct _STORE_DEPLOYMENT_METADATA_PROPERTY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010c0a0`

## callees

- `0x180014410`
- `0x1800148d8`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x1800194b0`
- `0x18010b978`
- `0x1801281c0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010ba0d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010ba83`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010bafa`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010ba0d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010ba83`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010bafa`

## string_xrefs

- `0x18010b9a8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumdeploymentmetadata.cpp`
- `0x18010ba16`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumdeploymentmetadata.cpp`
- `0x18010ba8f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumdeploymentmetadata.cpp`
- `0x18010bb06`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumdeploymentmetadata.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CopyOut(
        IsolationImplementation::Com *this,
        struct IMalloc **a2,
        struct _STORE_DEPLOYMENT_METADATA_PROPERTY *a3)
{
  int IMalloc; // eax
  unsigned __int16 **v6; // r8
  int v7; // r9d
  unsigned int v8; // edi
  __int64 v9; // rax
  __int64 *v10; // rbx
  int v11; // eax
  unsigned int v12; // edx
  unsigned int v13; // edi
  int v14; // edx
  __int64 v15; // rsi
  unsigned __int64 v16; // rdi
  struct IMalloc *v17; // rax
  struct IMalloc *v18; // r14
  __int64 v19; // rcx
  int v20; // edx
  __int128 v22; // [rsp+20h] [rbp-18h] BYREF
  __int64 *v23; // [rsp+80h] [rbp+48h] BYREF

  v23 = 0;
  IMalloc = IsolationImplementation::Com::GetIMalloc((IsolationImplementation::Com *)&v23, a2);
  v8 = IMalloc;
  if ( IMalloc < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumdeploymentmetadata.cpp",
      (const char *)0x12B,
      IMalloc,
      v7);
    if ( v23 )
    {
      v9 = *v23;
LABEL_28:
      (*(void (**)(void))(v9 + 16))();
      return v8;
    }
    return v8;
  }
  v10 = v23;
  v22 = 0;
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64 *))(*v23 + 8))(v23);
    *((_QWORD *)&v22 + 1) = v10;
  }
  v11 = IsolationImplementation::Com::CopyOut(
          (IsolationImplementation::Com *)((char *)this + 16),
          (const struct _LUNICODE_STRING *)&v22,
          v6);
  v13 = v11;
  if ( v11 < 0 )
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumdeploymentmetadata.cpp",
      (const char *)0x12F,
      v13,
      v22);
    v8 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v13, v14);
    v15 = *((_QWORD *)&v22 + 1);
    if ( !(_QWORD)v22 )
      goto LABEL_24;
LABEL_23:
    (*(void (__fastcall **)(__int64))(**((_QWORD **)&v22 + 1) + 40LL))(v15);
LABEL_24:
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_26;
  }
  v16 = *((_QWORD *)this + 5);
  if ( v16 > 0xFFFFFFFF )
  {
    if ( g_NTSTATUS_to_break_on_propagate == -1073741675 )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumdeploymentmetadata.cpp",
      (const char *)0x133,
      -1073741675,
      v22);
    v8 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)0xC0000095LL, v20);
LABEL_22:
    v15 = *((_QWORD *)&v22 + 1);
    if ( !(_QWORD)v22 )
      goto LABEL_24;
    goto LABEL_23;
  }
  v17 = (struct IMalloc *)IsolationImplementation::Com::CoTaskMemAlloc(
                            (IsolationImplementation::Com *)(unsigned int)v16,
                            v12);
  v18 = v17;
  if ( !v17 )
  {
    v8 = -2147024882;
    if ( g_HRESULT_to_break_on == -2147024882 )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"HR originated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumdeploymentmetadata.cpp",
      (const char *)0x134,
      -2147024882,
      v22);
    goto LABEL_22;
  }
  memmove(v17, *((const void **)this + 7), *((_QWORD *)this + 5));
  v19 = *((_QWORD *)&v22 + 1);
  a2[3] = (struct IMalloc *)(unsigned int)v16;
  a2[2] = (struct IMalloc *)v22;
  a2[4] = v18;
  *(_OWORD *)a2 = *(_OWORD *)this;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v8 = 0;
LABEL_26:
  if ( v10 )
  {
    v9 = *v10;
    goto LABEL_28;
  }
  return v8;
}

```

## disassembly

```asm
0x18010b978  push    rbp
0x18010b97a  push    rbx
0x18010b97b  push    rsi
0x18010b97c  push    rdi
0x18010b97d  push    r14
0x18010b97f  push    r15
0x18010b981  mov     rbp, rsp
0x18010b984  sub     rsp, 38h
0x18010b988  mov     rsi, rcx
0x18010b98b  mov     [rbp+arg_10], 0
0x18010b993  lea     rcx, [rbp+arg_10]; this
0x18010b997  mov     r15, rdx
0x18010b99a  call    ?GetIMalloc@Com@IsolationImplementation@@YAJPEAPEAUIMalloc@@@Z; IsolationImplementation::Com::GetIMalloc(IMalloc * *)
0x18010b99f  mov     edi, eax
0x18010b9a1  test    eax, eax
0x18010b9a3  jns     short loc_18010B9CE
0x18010b9a5  mov     r8d, eax; int
0x18010b9a8  lea     rcx, aOnecoreComNetf_29; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010b9af  mov     edx, 12Bh; char *
0x18010b9b4  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18010b9b9  mov     rcx, [rbp+arg_10]
0x18010b9bd  test    rcx, rcx
0x18010b9c0  jz      loc_18010BB6C
0x18010b9c6  mov     rax, [rcx]
0x18010b9c9  jmp     loc_18010BB63
0x18010b9ce  mov     rbx, [rbp+arg_10]
0x18010b9d2  xorps   xmm0, xmm0
0x18010b9d5  movdqu  [rbp+var_18], xmm0
0x18010b9da  test    rbx, rbx
0x18010b9dd  jz      short loc_18010B9F2
0x18010b9df  mov     rax, [rbx]
0x18010b9e2  mov     rcx, rbx
0x18010b9e5  mov     rax, [rax+8]
0x18010b9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b9ee  mov     qword ptr [rbp+var_18+8], rbx
0x18010b9f2  lea     rcx, [rsi+10h]; this
0x18010b9f6  lea     rdx, [rbp+var_18]; struct _LUNICODE_STRING *
0x18010b9fa  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUNICODE_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUNICODE_STRING const *,ushort * *)
0x18010b9ff  mov     edi, eax
0x18010ba01  test    eax, eax
0x18010ba03  jns     short loc_18010BA55
0x18010ba05  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18010ba0b  jnz     short loc_18010BA13
0x18010ba0d  call    cs:__imp_DebugBreak
0x18010ba13  mov     r9d, edi; int
0x18010ba16  lea     rdx, aOnecoreComNetf_29; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010ba1d  mov     r8d, 12Fh; char *
0x18010ba23  lea     rcx, aStatusPropagat; "Status propagated"
0x18010ba2a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18010ba2f  mov     ecx, edi; this
0x18010ba31  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18010ba36  mov     rdx, qword ptr [rbp+var_18]
0x18010ba3a  mov     edi, eax
0x18010ba3c  mov     rsi, qword ptr [rbp+var_18+8]
0x18010ba40  test    rdx, rdx
0x18010ba43  jz      loc_18010BB44
0x18010ba49  mov     rcx, [rsi]
0x18010ba4c  mov     rax, [rcx+28h]
0x18010ba50  jmp     loc_18010BB3C
0x18010ba55  mov     rdi, [rsi+28h]
0x18010ba59  mov     eax, 0FFFFFFFFh
0x18010ba5e  cmp     rdi, rax
0x18010ba61  ja      loc_18010BAED
0x18010ba67  mov     ecx, edi; this
0x18010ba69  call    ?CoTaskMemAlloc@Com@IsolationImplementation@@YAPEAXK@Z; IsolationImplementation::Com::CoTaskMemAlloc(ulong)
0x18010ba6e  mov     r14, rax
0x18010ba71  test    rax, rax
0x18010ba74  jnz     short loc_18010BAAA
0x18010ba76  mov     edi, 8007000Eh
0x18010ba7b  cmp     cs:?g_HRESULT_to_break_on@@3JA, edi; long g_HRESULT_to_break_on
0x18010ba81  jnz     short loc_18010BA89
0x18010ba83  call    cs:__imp_DebugBreak
0x18010ba89  mov     r9d, 8007000Eh; int
0x18010ba8f  lea     rdx, aOnecoreComNetf_29; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010ba96  mov     r8d, 134h; char *
0x18010ba9c  lea     rcx, aHrOriginated; "HR originated"
0x18010baa3  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18010baa8  jmp     short loc_18010BB28
0x18010baaa  mov     r8, [rsi+28h]; Size
0x18010baae  mov     rcx, r14; void *
0x18010bab1  mov     rdx, [rsi+38h]; Src
0x18010bab5  call    memmove
0x18010baba  mov     rcx, qword ptr [rbp+var_18+8]
0x18010babe  mov     eax, edi
0x18010bac0  mov     [r15+18h], rax
0x18010bac4  mov     rax, qword ptr [rbp+var_18]
0x18010bac8  mov     [r15+10h], rax
0x18010bacc  mov     [r15+20h], r14
0x18010bad0  movups  xmm0, xmmword ptr [rsi]
0x18010bad3  movdqu  xmmword ptr [r15], xmm0
0x18010bad8  test    rcx, rcx
0x18010badb  jz      short loc_18010BAE9
0x18010badd  mov     rax, [rcx]
0x18010bae0  mov     rax, [rax+10h]
0x18010bae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bae9  xor     edi, edi
0x18010baeb  jmp     short loc_18010BB58
0x18010baed  mov     edi, 0C0000095h
0x18010baf2  cmp     cs:g_NTSTATUS_to_break_on_propagate, edi
0x18010baf8  jnz     short loc_18010BB00
0x18010bafa  call    cs:__imp_DebugBreak
0x18010bb00  mov     r9d, 0C0000095h; int
0x18010bb06  lea     rdx, aOnecoreComNetf_29; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010bb0d  mov     r8d, 133h; char *
0x18010bb13  lea     rcx, aStatusPropagat; "Status propagated"
0x18010bb1a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18010bb1f  mov     ecx, edi; this
0x18010bb21  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18010bb26  mov     edi, eax
0x18010bb28  mov     rdx, qword ptr [rbp+var_18]
0x18010bb2c  mov     rsi, qword ptr [rbp+var_18+8]
0x18010bb30  test    rdx, rdx
0x18010bb33  jz      short loc_18010BB44
0x18010bb35  mov     rax, [rsi]
0x18010bb38  mov     rax, [rax+28h]
0x18010bb3c  mov     rcx, rsi
0x18010bb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bb44  test    rsi, rsi
0x18010bb47  jz      short loc_18010BB58
0x18010bb49  mov     rax, [rsi]
0x18010bb4c  mov     rcx, rsi
0x18010bb4f  mov     rax, [rax+10h]
0x18010bb53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bb58  test    rbx, rbx
0x18010bb5b  jz      short loc_18010BB6C
0x18010bb5d  mov     rax, [rbx]
0x18010bb60  mov     rcx, rbx
0x18010bb63  mov     rax, [rax+10h]
0x18010bb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bb6c  mov     eax, edi
0x18010bb6e  add     rsp, 38h
0x18010bb72  pop     r15
0x18010bb74  pop     r14
0x18010bb76  pop     rdi
0x18010bb77  pop     rsi
0x18010bb78  pop     rbx
0x18010bb79  pop     rbp
0x18010bb7a  retn
```

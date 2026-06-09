# StringCchCopyWithAlloc(ushort * *,int,int)

- ea: `0x18001223c`
- end: `0x180012351`
- name: `?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z`
- size: `277`
- prototype: `__int64 __fastcall(LPVOID *, const struct _EVENT_DESCRIPTOR *, UINT)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c998`
- `0x18000cb0c`
- `0x18000cc10`
- `0x18000ccd0`
- `0x18000cdf8`
- `0x18000ceb0`
- `0x18000da10`
- `0x18000e4d0`
- `0x18000e9b0`
- `0x180010718`
- `0x180011a04`

## callees

- `0x18001223c`
- `0x180014660`

## import_xrefs

- `USER32!LoadStringW` at `0x1800122e8`
- `USER32!LoadStringW` at `0x1800122e8`
- `KERNEL32!GetLastError` at `0x1800122f2`
- `KERNEL32!GetLastError` at `0x1800122f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001229b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001229b`

## string_xrefs

- `0x180012251`: `StringCchCopyWithAlloc`
- `0x1800122a9`: `StringCchCopyWithAlloc`
- `0x18001230f`: `StringCchCopyWithAlloc`

## pseudocode

```c
__int64 __fastcall StringCchCopyWithAlloc(LPVOID *a1, const struct _EVENT_DESCRIPTOR *a2, UINT a3)
{
  void *v6; // rcx
  unsigned __int16 *v7; // rax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  unsigned int v10; // edi
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx

  if ( !a1 )
  {
    CEventLogger::LogError(
      0,
      a2,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x2D5u,
      L"StringCchCopyWithAlloc",
      0x80070057);
    return 2147942487LL;
  }
  v6 = *a1;
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *a1 = 0;
  }
  v7 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
  *a1 = v7;
  if ( !v7 )
  {
    v10 = -2147024882;
    CEventLogger::LogError(
      v9,
      v8,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x2DCu,
      L"StringCchCopyWithAlloc",
      0x8007000E);
LABEL_11:
    if ( *a1 )
    {
      CoTaskMemFree(*a1);
      *a1 = 0;
    }
    return v10;
  }
  if ( !LoadStringW(hInstance, a3, v7, 1024) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CEventLogger::LogError(
      v13,
      v12,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x2E3u,
      L"StringCchCopyWithAlloc",
      LastError);
    v10 = -2147467259;
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x18001223c  mov     [rsp+arg_0], rbx
0x180012241  push    rdi
0x180012242  sub     rsp, 30h
0x180012246  mov     edi, r8d
0x180012249  mov     rbx, rcx
0x18001224c  test    rcx, rcx
0x18001224f  jnz     short loc_180012281
0x180012251  lea     rax, aStringcchcopyw; "StringCchCopyWithAlloc"
0x180012258  mov     [rsp+38h+var_10], 80070057h; unsigned int
0x180012260  mov     r9d, 2D5h; unsigned int
0x180012266  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18001226b  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180012272  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180012277  mov     eax, 80070057h
0x18001227c  jmp     loc_180012346
0x180012281  mov     rcx, [rcx]; pv
0x180012284  test    rcx, rcx
0x180012287  jz      short loc_180012296
0x180012289  call    cs:__imp_CoTaskMemFree
0x18001228f  mov     qword ptr [rbx], 0
0x180012296  mov     ecx, 800h; cb
0x18001229b  call    cs:__imp_CoTaskMemAlloc
0x1800122a1  mov     [rbx], rax
0x1800122a4  test    rax, rax
0x1800122a7  jnz     short loc_1800122D6
0x1800122a9  lea     rax, aStringcchcopyw; "StringCchCopyWithAlloc"
0x1800122b0  mov     [rsp+38h+var_10], 8007000Eh; unsigned int
0x1800122b8  mov     r9d, 2DCh; unsigned int
0x1800122be  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x1800122c3  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x1800122ca  mov     edi, 8007000Eh
0x1800122cf  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800122d4  jmp     short loc_18001232B
0x1800122d6  mov     rcx, cs:hInstance; hInstance
0x1800122dd  mov     r9d, 400h; cchBufferMax
0x1800122e3  mov     r8, rax; lpBuffer
0x1800122e6  mov     edx, edi; uID
0x1800122e8  call    cs:__imp_LoadStringW
0x1800122ee  test    eax, eax
0x1800122f0  jnz     short loc_180012342
0x1800122f2  call    cs:__imp_GetLastError
0x1800122f8  test    eax, eax
0x1800122fa  jle     short loc_180012304
0x1800122fc  movzx   eax, ax
0x1800122ff  or      eax, 80070000h
0x180012304  mov     [rsp+38h+var_10], eax; unsigned int
0x180012308  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18001230f  lea     rax, aStringcchcopyw; "StringCchCopyWithAlloc"
0x180012316  mov     r9d, 2E3h; unsigned int
0x18001231c  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x180012321  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180012326  mov     edi, 80004005h
0x18001232b  mov     rcx, [rbx]; pv
0x18001232e  test    rcx, rcx
0x180012331  jz      short loc_180012344
0x180012333  call    cs:__imp_CoTaskMemFree
0x180012339  mov     qword ptr [rbx], 0
0x180012340  jmp     short loc_180012344
0x180012342  xor     edi, edi
0x180012344  mov     eax, edi
0x180012346  mov     rbx, [rsp+38h+arg_0]
0x18001234b  add     rsp, 30h
0x18001234f  pop     rdi
0x180012350  retn
```

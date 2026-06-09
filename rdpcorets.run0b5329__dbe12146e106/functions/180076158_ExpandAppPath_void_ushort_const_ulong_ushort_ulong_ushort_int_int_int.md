# ExpandAppPath(void *,ushort const *,ulong,ushort *,ulong,ushort *,int,int *,int *)

- ea: `0x180076158`
- end: `0x18007634b`
- name: `?ExpandAppPath@@YAJPEAXPEBGKPEAGK2HPEAH3@Z`
- size: `499`
- prototype: `int(void *, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, int, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180076d08`

## callees

- `0x18000e420`
- `0x180075fb0`
- `0x180076158`
- `0x1800768e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007631b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007632a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007631b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007632a`
- `RDPBASE!TRC_TraceBufferW` at `0x18007630c`
- `RDPBASE!TRC_TraceBufferW` at `0x18007630c`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18007621e`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18007621e`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18007626f`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18007626f`

## string_xrefs

- `0x1800762fb`: `ExpandAppPath`
- `0x180076285`: `SHEvaluateSystemCommandTemplate hr[0x%x]`
- `0x1800762da`: `StringCchCopy Args hr[0x%x]`
- `0x1800762ad`: `StringCchCopy App hr[0x%x]`

## pseudocode

```c
__int64 __fastcall ExpandAppPath(
        void *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        int a7,
        int *a8,
        int *a9)
{
  int v9; // edi
  unsigned __int64 v10; // r12
  int v13; // eax
  unsigned __int16 *v14; // r14
  unsigned int v15; // r9d
  int v16; // eax
  signed int v17; // ebx
  signed int LastError; // eax
  const wchar_t *v19; // rax
  __int64 v20; // r8
  HRESULT v21; // eax
  int v22; // eax
  int v23; // eax
  signed int v25; // [rsp+38h] [rbp-18h]
  PWSTR ppszApplication; // [rsp+40h] [rbp-10h] BYREF
  PWSTR ppszParameters; // [rsp+48h] [rbp-8h] BYREF
  int v28; // [rsp+80h] [rbp+30h] BYREF
  int v29; // [rsp+84h] [rbp+34h]

  v29 = HIDWORD(a1);
  v9 = 0;
  v10 = a3;
  v28 = 0;
  ppszApplication = 0;
  ppszParameters = 0;
  v13 = IsAlias(a2);
  v14 = a6;
  if ( v13 )
  {
    v15 = a5;
    *a8 = 1;
    v16 = ExpandAlias(a2, v10, a4, v15, v14, &v28);
    v17 = v16;
    if ( v16 < 0 )
    {
      TRC_TraceBufferW(
        3,
        4096,
        687,
        L"ExpandAppPath",
        L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
        0,
        L"ExpandAlias hr[0x%x]",
        v16);
      goto LABEL_22;
    }
    v9 = v28;
    if ( !v28 )
      goto LABEL_8;
    *a9 = 1;
  }
  else
  {
    v17 = 0;
    *a8 = 0;
  }
  if ( v9 )
    goto LABEL_22;
LABEL_8:
  if ( !ExpandEnvironmentStringsForUserW(0, a2, a4, v10) )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    if ( v17 < 0 )
    {
      v25 = v17;
      v19 = L"ExpandEnvironmentStringsForUser hr[0x%x]";
      v20 = 710;
LABEL_21:
      TRC_TraceBufferW(
        3,
        4096,
        v20,
        L"ExpandAppPath",
        L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
        0,
        v19,
        v25);
      goto LABEL_22;
    }
  }
  if ( !a7 )
    goto LABEL_22;
  v21 = SHEvaluateSystemCommandTemplate(a4, &ppszApplication, 0, &ppszParameters);
  v17 = v21;
  if ( v21 < 0 )
  {
    v25 = v21;
    v20 = 721;
    v19 = L"SHEvaluateSystemCommandTemplate hr[0x%x]";
    goto LABEL_21;
  }
  v22 = StringCchCopyW(a4, v10, ppszApplication);
  v17 = v22;
  if ( v22 < 0 )
  {
    v25 = v22;
    v20 = 724;
    v19 = L"StringCchCopy App hr[0x%x]";
    goto LABEL_21;
  }
  if ( v14 )
  {
    v23 = StringCchCopyW(v14, a5, ppszParameters);
    v17 = v23;
    if ( v23 < 0 )
    {
      v25 = v23;
      v20 = 729;
      v19 = L"StringCchCopy Args hr[0x%x]";
      goto LABEL_21;
    }
  }
LABEL_22:
  if ( ppszApplication )
    CoTaskMemFree(ppszApplication);
  if ( ppszParameters )
    CoTaskMemFree(ppszParameters);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180076158  mov     [rsp-28h+arg_8], rbx
0x18007615d  mov     [rsp-28h+arg_10], rsi
0x180076162  mov     qword ptr [rsp-28h+arg_0], rcx
0x180076167  push    rbp
0x180076168  push    rdi
0x180076169  push    r12
0x18007616b  push    r14
0x18007616d  push    r15
0x18007616f  mov     rbp, rsp
0x180076172  sub     rsp, 50h
0x180076176  xor     edi, edi
0x180076178  mov     r12d, r8d
0x18007617b  mov     rcx, rdx; unsigned __int16 *
0x18007617e  mov     [rbp+arg_0], edi
0x180076181  mov     rsi, r9
0x180076184  mov     [rbp+ppszApplication], 0
0x18007618c  mov     r15, rdx
0x18007618f  mov     [rbp+ppszParameters], 0
0x180076197  call    ?IsAlias@@YAHPEBG@Z; IsAlias(ushort const *)
0x18007619c  mov     r14, [rbp+arg_28]
0x1800761a0  test    eax, eax
0x1800761a2  mov     rax, [rbp+arg_38]
0x1800761a6  jz      short loc_180076207
0x1800761a8  mov     r9d, [rbp+arg_20]; unsigned int
0x1800761ac  mov     r8, rsi; unsigned __int16 *
0x1800761af  mov     dword ptr [rax], 1
0x1800761b5  mov     edx, r12d; unsigned int
0x1800761b8  lea     rax, [rbp+arg_0]
0x1800761bc  mov     rcx, r15; unsigned __int16 *
0x1800761bf  mov     [rsp+50h+var_28], rax; int *
0x1800761c4  mov     [rsp+50h+var_30], r14; unsigned __int16 *
0x1800761c9  call    ?ExpandAlias@@YAJPEBGKPEAGK1PEAH@Z; ExpandAlias(ushort const *,ulong,ushort *,ulong,ushort *,int *)
0x1800761ce  mov     ebx, eax
0x1800761d0  test    eax, eax
0x1800761d2  jns     short loc_1800761F4
0x1800761d4  mov     [rsp+50h+var_18], eax
0x1800761d8  mov     r8d, 2AFh
0x1800761de  lea     rax, aExpandaliasHr0; "ExpandAlias hr[0x%x]"
0x1800761e5  mov     [rsp+50h+var_20], rax
0x1800761ea  mov     [rsp+50h+var_28], rdi
0x1800761ef  jmp     loc_1800762EF
0x1800761f4  mov     edi, [rbp+arg_0]
0x1800761f7  test    edi, edi
0x1800761f9  jz      short loc_180076213
0x1800761fb  mov     rax, [rbp+arg_40]
0x1800761ff  mov     dword ptr [rax], 1
0x180076205  jmp     short loc_18007620B
0x180076207  xor     ebx, ebx
0x180076209  mov     [rax], ebx
0x18007620b  test    edi, edi
0x18007620d  jnz     loc_180076312
0x180076213  mov     r9d, r12d; dwSize
0x180076216  mov     r8, rsi; lpDest
0x180076219  mov     rdx, r15; lpSrc
0x18007621c  xor     ecx, ecx; hToken
0x18007621e  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x180076224  test    eax, eax
0x180076226  jnz     short loc_180076257
0x180076228  call    cs:__imp_GetLastError
0x18007622e  mov     ebx, eax
0x180076230  test    eax, eax
0x180076232  jle     short loc_18007623D
0x180076234  movzx   ebx, ax
0x180076237  or      ebx, 80070000h
0x18007623d  test    ebx, ebx
0x18007623f  jns     short loc_180076257
0x180076241  mov     [rsp+50h+var_18], ebx
0x180076245  lea     rax, aExpandenvironm_0; "ExpandEnvironmentStringsForUser hr[0x%x"...
0x18007624c  mov     r8d, 2C6h
0x180076252  jmp     loc_1800762E1
0x180076257  cmp     [rbp+arg_30], 0
0x18007625b  jz      loc_180076312
0x180076261  lea     r9, [rbp+ppszParameters]; ppszParameters
0x180076265  xor     r8d, r8d; ppszCommandLine
0x180076268  lea     rdx, [rbp+ppszApplication]; ppszApplication
0x18007626c  mov     rcx, rsi; pszCmdTemplate
0x18007626f  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x180076275  mov     ebx, eax
0x180076277  test    eax, eax
0x180076279  jns     short loc_18007628E
0x18007627b  mov     [rsp+50h+var_18], eax
0x18007627f  mov     r8d, 2D1h
0x180076285  lea     rax, aShevaluatesyst_0; "SHEvaluateSystemCommandTemplate hr[0x%x"...
0x18007628c  jmp     short loc_1800762E1
0x18007628e  mov     r8, [rbp+ppszApplication]; unsigned __int16 *
0x180076292  mov     rdx, r12; unsigned __int64
0x180076295  mov     rcx, rsi; unsigned __int16 *
0x180076298  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007629d  mov     ebx, eax
0x18007629f  test    eax, eax
0x1800762a1  jns     short loc_1800762B6
0x1800762a3  mov     [rsp+50h+var_18], eax
0x1800762a7  mov     r8d, 2D4h
0x1800762ad  lea     rax, aStringcchcopyA; "StringCchCopy App hr[0x%x]"
0x1800762b4  jmp     short loc_1800762E1
0x1800762b6  test    r14, r14
0x1800762b9  jz      short loc_180076312
0x1800762bb  mov     edx, [rbp+arg_20]; unsigned __int64
0x1800762be  mov     rcx, r14; unsigned __int16 *
0x1800762c1  mov     r8, [rbp+ppszParameters]; unsigned __int16 *
0x1800762c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800762ca  mov     ebx, eax
0x1800762cc  test    eax, eax
0x1800762ce  jns     short loc_180076312
0x1800762d0  mov     [rsp+50h+var_18], eax
0x1800762d4  mov     r8d, 2D9h
0x1800762da  lea     rax, aStringcchcopyA_1; "StringCchCopy Args hr[0x%x]"
0x1800762e1  mov     [rsp+50h+var_20], rax
0x1800762e6  mov     [rsp+50h+var_28], 0
0x1800762ef  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x1800762f6  mov     edx, 1000h
0x1800762fb  lea     r9, aExpandapppath; "ExpandAppPath"
0x180076302  mov     [rsp+50h+var_30], rax
0x180076307  mov     ecx, 3
0x18007630c  call    cs:__imp_TRC_TraceBufferW
0x180076312  mov     rcx, [rbp+ppszApplication]; pv
0x180076316  test    rcx, rcx
0x180076319  jz      short loc_180076321
0x18007631b  call    cs:__imp_CoTaskMemFree
0x180076321  mov     rcx, [rbp+ppszParameters]; pv
0x180076325  test    rcx, rcx
0x180076328  jz      short loc_180076330
0x18007632a  call    cs:__imp_CoTaskMemFree
0x180076330  lea     r11, [rsp+50h+var_s0]
0x180076335  mov     eax, ebx
0x180076337  mov     rbx, [r11+38h]
0x18007633b  mov     rsi, [r11+40h]
0x18007633f  mov     rsp, r11
0x180076342  pop     r15
0x180076344  pop     r14
0x180076346  pop     r12
0x180076348  pop     rdi
0x180076349  pop     rbp
0x18007634a  retn
```

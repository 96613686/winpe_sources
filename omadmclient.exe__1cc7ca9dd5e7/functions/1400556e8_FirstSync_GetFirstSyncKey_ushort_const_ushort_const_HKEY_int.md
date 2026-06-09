# FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)

- ea: `0x1400556e8`
- end: `0x140055940`
- name: `?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z`
- size: `600`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, const unsigned __int16 *, HKEY *, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004f290`
- `0x140055948`
- `0x14005599c`
- `0x140055a68`
- `0x140055ba8`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000b0f4`
- `0x1400556e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140055811`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400558ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140055811`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400558ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005583e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400558bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005583e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400558bb`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140055769`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140055769`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1400557c4`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14005585e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x140055898`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1400557c4`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14005585e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x140055898`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14005579a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14005579a`

## pseudocode

```c
__int64 __fastcall FirstSync::GetFirstSyncKey(PCWSTR pszMore, PCWSTR a2, unsigned __int16 *a3, HKEY *a4)
{
  __int64 v7; // rdx
  int v8; // ebx
  char IsStateSeparationEnabled; // al
  LSTATUS v11; // eax
  HKEY v12; // rcx
  __int64 v13; // rdx
  LSTATUS v14; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v18; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  if ( !pszMore )
  {
    v7 = 367;
LABEL_3:
    v8 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)v8,
      phkResult);
    return (unsigned int)v8;
  }
  if ( !a3 )
  {
    v7 = 368;
    goto LABEL_3;
  }
  *(_QWORD *)a3 = 0;
  memset_0(pszPathOut, 0, 0x208u);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v8 = PathCchCombine(
         pszPathOut,
         0x104u,
         *(wchar_t **)((char *)off_14006AB10 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         pszMore);
  if ( v8 < 0 )
  {
    v7 = 373;
    goto LABEL_4;
  }
  v8 = PathCchAppend(pszPathOut, 0x104u, L"FirstSync");
  if ( v8 < 0 )
  {
    v7 = 374;
    goto LABEL_4;
  }
  if ( a2 )
  {
    hKey = 0;
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0x20019u, &hKey);
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_16;
    v8 = PathCchAppend(pszPathOut, 0x104u, L"\\");
    if ( v8 < 0 )
    {
      v13 = 386;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v8,
        phkResulta);
LABEL_16:
      v12 = hKey;
      goto LABEL_17;
    }
    v8 = PathCchAppend(pszPathOut, 0x104u, a2);
    if ( v8 < 0 )
    {
      v13 = 387;
      goto LABEL_21;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  v18 = 0;
  v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0x20019u, &v18);
  v8 = v14;
  if ( v14 > 0 )
    v8 = (unsigned __int16)v14 | 0x80070000;
  if ( v8 < 0 )
  {
    v12 = v18;
LABEL_17:
    if ( v12 )
      RegCloseKey(v12);
    return (unsigned int)v8;
  }
  *(_QWORD *)a3 = v18;
  return 0;
}

```

## disassembly

```asm
0x1400556e8  push    rbp
0x1400556ea  push    rbx
0x1400556eb  push    rsi
0x1400556ec  push    rdi
0x1400556ed  push    r15
0x1400556ef  lea     rbp, [rsp-160h]
0x1400556f7  sub     rsp, 260h
0x1400556fe  mov     rax, cs:__security_cookie
0x140055705  xor     rax, rsp
0x140055708  mov     [rbp+180h+var_30], rax
0x14005570f  mov     rdi, r8
0x140055712  mov     rsi, rdx
0x140055715  mov     rbx, rcx
0x140055718  test    rcx, rcx
0x14005571b  jnz     short loc_140055744
0x14005571d  mov     edx, 16Fh; void *
0x140055722  mov     ebx, 80070057h
0x140055727  mov     rcx, [rbp+188h]; this
0x14005572e  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x140055735  mov     r9d, ebx; char *
0x140055738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005573d  mov     eax, ebx
0x14005573f  jmp     loc_140055922
0x140055744  test    rdi, rdi
0x140055747  jnz     short loc_140055750
0x140055749  mov     edx, 170h
0x14005574e  jmp     short loc_140055722
0x140055750  mov     qword ptr [r8], 0
0x140055757  lea     rcx, [rsp+280h+pszPathOut]; void *
0x14005575c  mov     r8d, 208h; Size
0x140055762  xor     edx, edx; Val
0x140055764  call    memset_0
0x140055769  call    cs:__imp_RtlIsStateSeparationEnabled
0x140055770  nop     dword ptr [rax+rax+00h]
0x140055775  mov     r15d, 104h
0x14005577b  lea     rcx, [rsp+280h+pszPathOut]; pszPathOut
0x140055780  neg     al
0x140055782  mov     r9, rbx; pszMore
0x140055785  lea     rax, off_14006AB10; "Software\\Microsoft\\Enrollments\\"
0x14005578c  mov     edx, r15d; cchPathOut
0x14005578f  sbb     r8, r8
0x140055792  and     r8d, 8
0x140055796  mov     r8, [r8+rax]; pszPathIn
0x14005579a  call    cs:__imp_PathCchCombine
0x1400557a1  nop     dword ptr [rax+rax+00h]
0x1400557a6  mov     ebx, eax
0x1400557a8  test    eax, eax
0x1400557aa  jns     short loc_1400557B5
0x1400557ac  lea     edx, [r15+71h]
0x1400557b0  jmp     loc_140055727
0x1400557b5  lea     r8, pszMore; "FirstSync"
0x1400557bc  mov     rdx, r15; cchPath
0x1400557bf  lea     rcx, [rsp+280h+pszPathOut]; pszPath
0x1400557c4  call    cs:__imp_PathCchAppend
0x1400557cb  nop     dword ptr [rax+rax+00h]
0x1400557d0  mov     ebx, eax
0x1400557d2  test    eax, eax
0x1400557d4  jns     short loc_1400557E0
0x1400557d6  mov     edx, 176h
0x1400557db  jmp     loc_140055727
0x1400557e0  test    rsi, rsi
0x1400557e3  jz      loc_1400558C7
0x1400557e9  lea     rax, [rsp+280h+hKey]
0x1400557ee  mov     [rsp+280h+hKey], 0
0x1400557f7  mov     r9d, 20019h; samDesired
0x1400557fd  mov     qword ptr [rsp+280h+phkResult], rax; int
0x140055802  xor     r8d, r8d; ulOptions
0x140055805  lea     rdx, [rsp+280h+pszPathOut]; lpSubKey
0x14005580a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140055811  call    cs:__imp_RegOpenKeyExW
0x140055818  nop     dword ptr [rax+rax+00h]
0x14005581d  mov     ebx, eax
0x14005581f  test    eax, eax
0x140055821  jle     short loc_14005582C
0x140055823  movzx   ebx, ax
0x140055826  or      ebx, 80070000h
0x14005582c  test    ebx, ebx
0x14005582e  jns     short loc_14005584F
0x140055830  mov     rcx, [rsp+280h+hKey]; hKey
0x140055835  test    rcx, rcx
0x140055838  jz      loc_14005573D
0x14005583e  call    cs:__imp_RegCloseKey
0x140055845  nop     dword ptr [rax+rax+00h]
0x14005584a  jmp     loc_14005573D
0x14005584f  lea     r8, pszSrc; "\\"
0x140055856  mov     rdx, r15; cchPath
0x140055859  lea     rcx, [rsp+280h+pszPathOut]; pszPath
0x14005585e  call    cs:__imp_PathCchAppend
0x140055865  nop     dword ptr [rax+rax+00h]
0x14005586a  mov     ebx, eax
0x14005586c  test    eax, eax
0x14005586e  jns     short loc_14005588D
0x140055870  mov     edx, 182h; void *
0x140055875  mov     rcx, [rbp+188h]; this
0x14005587c  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x140055883  mov     r9d, ebx; char *
0x140055886  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005588b  jmp     short loc_140055830
0x14005588d  mov     r8, rsi; pszMore
0x140055890  lea     rcx, [rsp+280h+pszPathOut]; pszPath
0x140055895  mov     rdx, r15; cchPath
0x140055898  call    cs:__imp_PathCchAppend
0x14005589f  nop     dword ptr [rax+rax+00h]
0x1400558a4  mov     ebx, eax
0x1400558a6  test    eax, eax
0x1400558a8  jns     short loc_1400558B1
0x1400558aa  mov     edx, 183h
0x1400558af  jmp     short loc_140055875
0x1400558b1  mov     rcx, [rsp+280h+hKey]; hKey
0x1400558b6  test    rcx, rcx
0x1400558b9  jz      short loc_1400558C7
0x1400558bb  call    cs:__imp_RegCloseKey
0x1400558c2  nop     dword ptr [rax+rax+00h]
0x1400558c7  lea     rax, [rsp+280h+var_248]
0x1400558cc  mov     [rsp+280h+var_248], 0
0x1400558d5  mov     r9d, 20019h; samDesired
0x1400558db  mov     qword ptr [rsp+280h+phkResult], rax; phkResult
0x1400558e0  xor     r8d, r8d; ulOptions
0x1400558e3  lea     rdx, [rsp+280h+pszPathOut]; lpSubKey
0x1400558e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400558ef  call    cs:__imp_RegOpenKeyExW
0x1400558f6  nop     dword ptr [rax+rax+00h]
0x1400558fb  mov     ebx, eax
0x1400558fd  test    eax, eax
0x1400558ff  jle     short loc_14005590A
0x140055901  movzx   ebx, ax
0x140055904  or      ebx, 80070000h
0x14005590a  test    ebx, ebx
0x14005590c  jns     short loc_140055918
0x14005590e  mov     rcx, [rsp+280h+var_248]
0x140055913  jmp     loc_140055835
0x140055918  mov     rax, [rsp+280h+var_248]
0x14005591d  mov     [rdi], rax
0x140055920  xor     eax, eax
0x140055922  mov     rcx, [rbp+180h+var_30]
0x140055929  xor     rcx, rsp; StackCookie
0x14005592c  call    __security_check_cookie
0x140055931  add     rsp, 260h
0x140055938  pop     r15
0x14005593a  pop     rdi
0x14005593b  pop     rsi
0x14005593c  pop     rbx
0x14005593d  pop     rbp
0x14005593e  retn
```

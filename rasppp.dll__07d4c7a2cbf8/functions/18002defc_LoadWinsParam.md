# LoadWinsParam

- ea: `0x18002defc`
- end: `0x18002e124`
- name: `LoadWinsParam`
- size: `552`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002d904`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180014434`
- `0x18002a138`
- `0x18002defc`
- `0x18002e720`
- `0x180030da4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dfaa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dfaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dfb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dfb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e062`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e062`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e0e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e0e4`

## string_xrefs

- `0x18002e08c`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002e0a5`: `RegOpenKeyEx(%ws) failed and returned %d`

## pseudocode

```c
__int64 __fastcall LoadWinsParam(HKEY hKey, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  size_t v6; // rbx
  wchar_t *v7; // rsi
  DWORD LastError; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  HKEY hKeya; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKeya = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004C648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C648,
        L"LoadWinsParam");
  }
  else
  {
    TraceHlp("LoadWinsParam");
  }
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * v4) );
  v5 = (unsigned int)(v4 + 7);
  v6 = (unsigned int)v5;
  v7 = (wchar_t *)LocalAlloc(0x40u, 2 * v5);
  if ( v7 )
  {
    StringCchPrintfW(v7, v6, L"%s%s", L"Tcpip_", *(_QWORD *)(a2 + 8));
    v10 = RegOpenKeyExW(hKey, v7, 0, 0x20019u, &hKeya);
    v9 = v10;
    if ( v10 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( qword_18004C640 )
        {
          LOWORD(v13) = 0;
          FormatRRASErrorString(&v13, L"RegOpenKeyEx(%ws) failed and returned %d", v7, v10);
LABEL_11:
          ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C640, &v13);
        }
      }
      else
      {
        TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
      }
    }
    else
    {
      RegQueryValueWithAllocW(hKeya, L"NameServerList");
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004C640 )
        goto LABEL_19;
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"LocalAlloc failed and returned %d", LastError);
      goto LABEL_11;
    }
    TraceHlp("LocalAlloc failed and returned %d");
  }
LABEL_19:
  LocalFree(v7);
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v9 )
  {
    LocalFree(*(HLOCAL *)(a2 + 112));
    *(_QWORD *)(a2 + 112) = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18002defc  mov     [rsp-8+arg_10], rbx
0x18002df01  push    rbp
0x18002df02  push    rsi
0x18002df03  push    rdi
0x18002df04  push    r14
0x18002df06  push    r15
0x18002df08  lea     rbp, [rsp-750h]
0x18002df10  sub     rsp, 850h
0x18002df17  mov     rax, cs:__security_cookie
0x18002df1e  xor     rax, rsp
0x18002df21  mov     [rbp+770h+var_30], rax
0x18002df28  mov     rdi, rdx
0x18002df2b  mov     r14, rcx
0x18002df2e  xor     r15d, r15d
0x18002df31  lea     rcx, [rsp+870h+var_82C]; void *
0x18002df36  xor     edx, edx; Val
0x18002df38  mov     [rsp+870h+hKey], r15
0x18002df3d  mov     r8d, 7FCh; Size
0x18002df43  mov     [rsp+870h+var_830], r15d
0x18002df48  call    memset_0
0x18002df4d  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002df54  jz      short loc_18002DF7E
0x18002df56  mov     rdx, cs:qword_18004C648
0x18002df5d  test    rdx, rdx
0x18002df60  jz      short loc_18002DF8A
0x18002df62  mov     rcx, cs:gIphlpEtwContext
0x18002df69  lea     r8, aLoadwinsparam_0; "LoadWinsParam"
0x18002df70  mov     rax, cs:gIphlpTemplateFunc
0x18002df77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df7c  jmp     short loc_18002DF8A
0x18002df7e  lea     rcx, aLoadwinsparam; "LoadWinsParam"
0x18002df85  call    TraceHlp
0x18002df8a  mov     rcx, [rdi+8]
0x18002df8e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002df92  inc     rax
0x18002df95  cmp     [rcx+rax*2], r15w
0x18002df9a  jnz     short loc_18002DF92
0x18002df9c  add     eax, 7
0x18002df9f  mov     ecx, 40h ; '@'; uFlags
0x18002dfa4  mov     ebx, eax
0x18002dfa6  lea     rdx, [rax+rax]; uBytes
0x18002dfaa  call    cs:__imp_LocalAlloc
0x18002dfb0  mov     rsi, rax
0x18002dfb3  test    rax, rax
0x18002dfb6  jnz     short loc_18002E027
0x18002dfb8  call    cs:__imp_GetLastError
0x18002dfbe  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002dfc5  mov     ebx, eax
0x18002dfc7  jz      short loc_18002E014
0x18002dfc9  cmp     cs:qword_18004C640, r15
0x18002dfd0  jz      loc_18002E0D1
0x18002dfd6  mov     r8d, eax
0x18002dfd9  mov     word ptr [rsp+870h+var_830], r15w
0x18002dfdf  lea     rdx, aLocalallocFail_1; "LocalAlloc failed and returned %d"
0x18002dfe6  lea     rcx, [rsp+870h+var_830]
0x18002dfeb  call    FormatRRASErrorString
0x18002dff0  mov     rdx, cs:qword_18004C640
0x18002dff7  lea     r8, [rsp+870h+var_830]
0x18002dffc  mov     rcx, cs:gIphlpEtwContext
0x18002e003  mov     rax, cs:gIphlpTemplateFunc
0x18002e00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e00f  jmp     loc_18002E0D1
0x18002e014  mov     edx, eax
0x18002e016  lea     rcx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x18002e01d  call    TraceHlp
0x18002e022  jmp     loc_18002E0D1
0x18002e027  mov     rax, [rdi+8]
0x18002e02b  lea     r9, aTcpip; "Tcpip_"
0x18002e032  lea     r8, aSS_0; "%s%s"
0x18002e039  mov     [rsp+870h+phkResult], rax
0x18002e03e  mov     rdx, rbx; cchDest
0x18002e041  mov     rcx, rsi; pszDest
0x18002e044  call    StringCchPrintfW
0x18002e049  lea     rax, [rsp+870h+hKey]
0x18002e04e  mov     r9d, 20019h; samDesired
0x18002e054  xor     r8d, r8d; ulOptions
0x18002e057  mov     [rsp+870h+phkResult], rax; phkResult
0x18002e05c  mov     rdx, rsi; lpSubKey
0x18002e05f  mov     rcx, r14; hKey
0x18002e062  call    cs:__imp_RegOpenKeyExW
0x18002e068  mov     ebx, eax
0x18002e06a  test    eax, eax
0x18002e06c  jz      short loc_18002E0B6
0x18002e06e  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002e075  jz      short loc_18002E0A2
0x18002e077  cmp     cs:qword_18004C640, r15
0x18002e07e  jz      short loc_18002E0D1
0x18002e080  mov     r9d, eax
0x18002e083  mov     word ptr [rsp+870h+var_830], r15w
0x18002e089  mov     r8, rsi
0x18002e08c  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002e093  lea     rcx, [rsp+870h+var_830]
0x18002e098  call    FormatRRASErrorString
0x18002e09d  jmp     loc_18002DFF0
0x18002e0a2  mov     r8d, eax
0x18002e0a5  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002e0ac  mov     rdx, rsi
0x18002e0af  call    TraceHlp
0x18002e0b4  jmp     short loc_18002E0D1
0x18002e0b6  mov     rcx, [rsp+870h+hKey]; hKey
0x18002e0bb  lea     r9, [rdi+70h]
0x18002e0bf  mov     r8d, 7
0x18002e0c5  lea     rdx, aNameserverlist; "NameServerList"
0x18002e0cc  call    RegQueryValueWithAllocW
0x18002e0d1  mov     rcx, rsi; hMem
0x18002e0d4  call    cs:__imp_LocalFree
0x18002e0da  mov     rcx, [rsp+870h+hKey]; hKey
0x18002e0df  test    rcx, rcx
0x18002e0e2  jz      short loc_18002E0EA
0x18002e0e4  call    cs:__imp_RegCloseKey
0x18002e0ea  test    ebx, ebx
0x18002e0ec  jz      short loc_18002E0FC
0x18002e0ee  mov     rcx, [rdi+70h]; hMem
0x18002e0f2  call    cs:__imp_LocalFree
0x18002e0f8  mov     [rdi+70h], r15
0x18002e0fc  mov     eax, ebx
0x18002e0fe  mov     rcx, [rbp+770h+var_30]
0x18002e105  xor     rcx, rsp; StackCookie
0x18002e108  call    __security_check_cookie
0x18002e10d  mov     rbx, [rsp+870h+arg_10]
0x18002e115  add     rsp, 850h
0x18002e11c  pop     r15
0x18002e11e  pop     r14
0x18002e120  pop     rdi
0x18002e121  pop     rsi
0x18002e122  pop     rbp
0x18002e123  retn
```

# CRASHookPage::OnApply(void)

- ea: `0x18001e640`
- end: `0x18001ea4c`
- name: `?OnApply@CRASHookPage@@UEAAJXZ`
- size: `1036`
- prototype: `__int64 __fastcall(CRASHookPage *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180011940`
- `0x18001201c`
- `0x18001e640`
- `0x18002f382`
- `0x180030010`

## import_xrefs

- `RASAPI32!GetPersonalPhonebookPath` at `0x18001e84c`
- `RASAPI32!GetPersonalPhonebookPath` at `0x18001e84c`
- `rtutils!TracePrintfExA` at `0x18001e687`
- `rtutils!TracePrintfExA` at `0x18001e6cd`
- `rtutils!TracePrintfExA` at `0x18001e768`
- `rtutils!TracePrintfExA` at `0x18001e7b0`
- `rtutils!TracePrintfExA` at `0x18001e86a`
- `rtutils!TracePrintfExA` at `0x18001e8d9`
- `rtutils!TracePrintfExA` at `0x18001e90c`
- `rtutils!TracePrintfExA` at `0x18001e92e`
- `rtutils!TracePrintfExA` at `0x18001ea12`
- `rtutils!TracePrintfExA` at `0x18001e687`
- `rtutils!TracePrintfExA` at `0x18001e6cd`
- `rtutils!TracePrintfExA` at `0x18001e768`
- `rtutils!TracePrintfExA` at `0x18001e7b0`
- `rtutils!TracePrintfExA` at `0x18001e86a`
- `rtutils!TracePrintfExA` at `0x18001e8d9`
- `rtutils!TracePrintfExA` at `0x18001e90c`
- `rtutils!TracePrintfExA` at `0x18001e92e`
- `rtutils!TracePrintfExA` at `0x18001ea12`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e70a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e7df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e70a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e7df`

## string_xrefs

- `0x18001e7a7`: `CRASHookPage::OnApply:Since elevated IRasGcwLUA handle is not available, create an in-proc IRasGcwLUA handle`
- `0x18001e78d`: `CRASHookPage::OnApply:Failed to do CoCreateInstance for IID_IGlobalInterfaceTable. hr = %#x`
- `0x18001e861`: `CRASHookPage::OnApply:Failed to get the phone book Path.`
- `0x18001e7fd`: `CRASHookPage::OnApply:Failed to do CoCreateInstance for IRasGcwLUA. hr = %#x`
- `0x18001e903`: `CRASHookPage::OnApply:CreateRASEntry result. hr = %#x`
- `0x18001e996`: `CRASHookPage::OnApply:Unable to set the created connection name in the property bag. hr = %#x`
- `0x18001e925`: `CRASHookPage::OnApply:CreateRASEntry failed.`
- `0x18001ea06`: `CRASHookPage::OnApply:Unable to set the created c_szConnectionTesting in the property bag. hr = %#x`

## pseudocode

```c
__int64 __fastcall CRASHookPage::OnApply(CRASHookPage *this)
{
  DWORD v2; // ecx
  _QWORD *v3; // rsi
  __int64 result; // rax
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int v7; // r15d
  char *v8; // r14
  HRESULT v9; // eax
  unsigned int v10; // eax
  DWORD v11; // ecx
  __int64 v12; // r9
  int v13; // eax
  GUID *v14; // r9
  int v15; // eax
  LPVOID v16; // [rsp+60h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  *((_QWORD *)this + 9) = 0;
  v2 = g_dwTraceId;
  v16 = 0;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "CRASHookPage::OnApply.");
    v2 = g_dwTraceId;
  }
  v3 = (_QWORD *)((char *)this + 56);
  if ( *((_DWORD *)this + 20) )
  {
    *(_DWORD *)(*v3 + 4952LL) = 1;
    v2 = g_dwTraceId;
  }
  if ( !*(_DWORD *)(*v3 + 4952LL) )
  {
    if ( v2 != -1 )
      TracePrintfExA(v2, 0xCu, "CRASHookPage::OnApply: Graceful exit of OnApply as the data is not still valid.");
    return 0;
  }
  if ( *((_DWORD *)this + 12) )
  {
    ppv = 0;
    v5 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "CRASHookPage::OnApply:Failed to do CoCreateInstance for IID_IGlobalInterfaceTable. hr = %#x",
          (unsigned int)v5);
      return v6;
    }
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, LPVOID *))(*(_QWORD *)ppv + 40LL))(
           ppv,
           *((unsigned int *)this + 12),
           &IID_IRasGcwLUA,
           &v16);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( (v6 & 0x80000000) != 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "CRASHookPage::OnApply:Unable to set the get GetInterfaceFromGlobal for IRasGcwLUA. hr = %#x",
          v6);
      return v6;
    }
    v7 = 1;
    goto LABEL_25;
  }
  v7 = 0;
  if ( *((_QWORD *)this + 8) )
  {
    v16 = (LPVOID)*((_QWORD *)this + 8);
LABEL_25:
    v8 = (char *)this + 56;
    goto LABEL_26;
  }
  if ( v2 != -1 )
    TracePrintfExA(
      v2,
      0xCu,
      "CRASHookPage::OnApply:Since elevated IRasGcwLUA handle is not available, create an in-proc IRasGcwLUA handle");
  v8 = (char *)this + 56;
  v9 = CoCreateInstance(&CLSID_RasGcwLUA, 0, 0x401u, &IID_IRasGcwLUA, &v16);
  v6 = v9;
  if ( v9 < 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "CRASHookPage::OnApply:Failed to do CoCreateInstance for IRasGcwLUA. hr = %#x",
        (unsigned int)v9);
    return v6;
  }
  *((_QWORD *)this + 8) = v16;
LABEL_26:
  if ( *(_DWORD *)(*(_QWORD *)v8 + 8LL) )
  {
    memset_0((void *)(*(_QWORD *)v8 + 12LL), 0, 0x402u);
    if ( !*(_DWORD *)(*v3 + 2884LL) && !(unsigned int)GetPersonalPhonebookPath(0, *v3 + 12LL, 513) )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CRASHookPage::OnApply:Failed to get the phone book Path.");
      v6 = -2147024275;
LABEL_51:
      if ( v7 && v16 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
      return v6;
    }
  }
  result = IsValidRASConnectionName(
             0,
             (PCNZWCH)((*v3 + 12LL) & -(__int64)(*(_WORD *)(*v3 + 12LL) != 0)),
             (LPCWSTR)(*v3 + 1038LL));
  if ( !(_DWORD)result )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "CRASHookPage::OnApply: Entry:[%S],Pbk:[%S]",
        (const wchar_t *)(*v3 + 1038LL),
        (const wchar_t *)(*v3 + 12LL));
    v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 24LL))(v16, *v3);
    v11 = g_dwTraceId;
    v6 = v10;
    if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "CRASHookPage::OnApply:CreateRASEntry result. hr = %#x", v10);
      v11 = g_dwTraceId;
    }
    if ( (v6 & 0x80000000) == 0 )
    {
      v12 = *v3;
      *((_DWORD *)this + 18) = 1;
      if ( (*(_BYTE *)(v12 + 4) & 4) == 0 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, __int64, int))(**((_QWORD **)this + 4) + 40LL))(
                *((_QWORD *)this + 4),
                (char *)this + 8,
                L"ConnectionName",
                v12 + 1038,
                2);
        v6 = v13;
        if ( v13 >= 0 )
        {
          UpdateConnectionTestedProperty(
            *((_QWORD *)this + 4),
            (char *)this + 8,
            *(unsigned int *)(*v3 + 4LL),
            *(unsigned int *)(*v3 + 1812LL));
          v14 = &CLSID_RASCTITestingPage;
          if ( (*(_BYTE *)(*v3 + 4LL) & 2) == 0 )
            v14 = &CLSID_RASCTWTestingPage;
          v15 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, GUID *, int))(**((_QWORD **)this + 4) + 40LL))(
                  *((_QWORD *)this + 4),
                  (char *)this + 8,
                  L"ConnectionTesting",
                  v14,
                  2);
          v6 = v15;
          if ( v15 < 0 && g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "CRASHookPage::OnApply:Unable to set the created c_szConnectionTesting in the property bag. hr = %#x",
              (unsigned int)v15);
        }
        else if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "CRASHookPage::OnApply:Unable to set the created connection name in the property bag. hr = %#x",
            (unsigned int)v13);
        }
      }
    }
    else if ( v11 != -1 )
    {
      TracePrintfExA(v11, 0xCu, "CRASHookPage::OnApply:CreateRASEntry failed.");
    }
    goto LABEL_51;
  }
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001e640  mov     [rsp+arg_10], rbx
0x18001e645  mov     [rsp+arg_18], rbp
0x18001e64a  push    rsi
0x18001e64b  push    rdi
0x18001e64c  push    r13
0x18001e64e  push    r14
0x18001e650  push    r15
0x18001e652  sub     rsp, 30h
0x18001e656  mov     rdi, rcx
0x18001e659  mov     qword ptr [rcx+48h], 0
0x18001e661  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e667  or      r13d, 0FFFFFFFFh
0x18001e66b  mov     [rsp+58h+arg_0], 0
0x18001e674  mov     ebp, 0Ch
0x18001e679  cmp     ecx, r13d
0x18001e67c  jz      short loc_18001E693
0x18001e67e  lea     r8, aCrashookpageOn_19; "CRASHookPage::OnApply."
0x18001e685  mov     edx, ebp; dwFlags
0x18001e687  call    cs:__imp_TracePrintfExA
0x18001e68d  mov     ecx, cs:g_dwTraceId
0x18001e693  cmp     dword ptr [rdi+50h], 0
0x18001e697  lea     rsi, [rdi+38h]
0x18001e69b  mov     r14d, 1
0x18001e6a1  jz      short loc_18001E6B3
0x18001e6a3  mov     rax, [rsi]
0x18001e6a6  mov     [rax+1358h], r14d
0x18001e6ad  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e6b3  mov     rax, [rsi]
0x18001e6b6  cmp     dword ptr [rax+1358h], 0
0x18001e6bd  jnz     short loc_18001E6DA
0x18001e6bf  cmp     ecx, r13d
0x18001e6c2  jz      short loc_18001E6D3
0x18001e6c4  lea     r8, aCrashookpageOn_8; "CRASHookPage::OnApply: Graceful exit of"...
0x18001e6cb  mov     edx, ebp; dwFlags
0x18001e6cd  call    cs:__imp_TracePrintfExA
0x18001e6d3  xor     eax, eax
0x18001e6d5  jmp     loc_18001EA35
0x18001e6da  cmp     dword ptr [rdi+30h], 0
0x18001e6de  jz      loc_18001E796
0x18001e6e4  lea     rax, [rsp+58h+arg_8]
0x18001e6e9  mov     [rsp+58h+arg_8], 0
0x18001e6f2  lea     r9, IID_IGlobalInterfaceTable; riid
0x18001e6f9  mov     [rsp+58h+ppv], rax; ppv
0x18001e6fe  mov     r8d, r14d; dwClsContext
0x18001e701  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001e708  xor     edx, edx; pUnkOuter
0x18001e70a  call    cs:__imp_CoCreateInstance
0x18001e710  mov     ebx, eax
0x18001e712  test    eax, eax
0x18001e714  js      short loc_18001E77B
0x18001e716  mov     rcx, [rsp+58h+arg_8]
0x18001e71b  lea     r9, [rsp+58h+arg_0]
0x18001e720  mov     edx, [rdi+30h]
0x18001e723  lea     r8, IID_IRasGcwLUA
0x18001e72a  mov     rax, [rcx]
0x18001e72d  mov     rax, [rax+28h]
0x18001e731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e736  mov     rcx, [rsp+58h+arg_8]
0x18001e73b  mov     ebx, eax
0x18001e73d  mov     rax, [rcx]
0x18001e740  mov     rax, [rax+10h]
0x18001e744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e749  test    ebx, ebx
0x18001e74b  jns     short loc_18001E773
0x18001e74d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e753  cmp     ecx, r13d
0x18001e756  jz      loc_18001EA33
0x18001e75c  mov     r9d, ebx
0x18001e75f  lea     r8, aCrashookpageOn_4; "CRASHookPage::OnApply:Unable to set the"...
0x18001e766  mov     edx, ebp; dwFlags
0x18001e768  call    cs:__imp_TracePrintfExA
0x18001e76e  jmp     loc_18001EA33
0x18001e773  mov     r15d, r14d
0x18001e776  jmp     loc_18001E819
0x18001e77b  mov     ecx, cs:g_dwTraceId
0x18001e781  cmp     ecx, r13d
0x18001e784  jz      loc_18001EA33
0x18001e78a  mov     r9d, eax
0x18001e78d  lea     r8, aCrashookpageOn_14; "CRASHookPage::OnApply:Failed to do CoCr"...
0x18001e794  jmp     short loc_18001E766
0x18001e796  mov     rax, [rdi+40h]
0x18001e79a  xor     r15d, r15d
0x18001e79d  test    rax, rax
0x18001e7a0  jnz     short loc_18001E814
0x18001e7a2  cmp     ecx, r13d
0x18001e7a5  jz      short loc_18001E7BC
0x18001e7a7  lea     r8, aCrashookpageOn_7; "CRASHookPage::OnApply:Since elevated IR"...
0x18001e7ae  mov     edx, ebp; dwFlags
0x18001e7b0  call    cs:__imp_TracePrintfExA
0x18001e7b6  lea     r14, [rdi+38h]
0x18001e7ba  jmp     short loc_18001E7BF
0x18001e7bc  mov     r14, rsi
0x18001e7bf  lea     rax, [rsp+58h+arg_0]
0x18001e7c4  xor     edx, edx; pUnkOuter
0x18001e7c6  lea     r9, IID_IRasGcwLUA; riid
0x18001e7cd  mov     [rsp+58h+ppv], rax; ppv
0x18001e7d2  mov     r8d, 401h; dwClsContext
0x18001e7d8  lea     rcx, CLSID_RasGcwLUA; rclsid
0x18001e7df  call    cs:__imp_CoCreateInstance
0x18001e7e5  mov     ebx, eax
0x18001e7e7  test    eax, eax
0x18001e7e9  jns     short loc_18001E809
0x18001e7eb  mov     ecx, cs:g_dwTraceId
0x18001e7f1  cmp     ecx, r13d
0x18001e7f4  jz      loc_18001EA33
0x18001e7fa  mov     r9d, eax
0x18001e7fd  lea     r8, aCrashookpageOn_16; "CRASHookPage::OnApply:Failed to do CoCr"...
0x18001e804  jmp     loc_18001E766
0x18001e809  mov     rax, [rsp+58h+arg_0]
0x18001e80e  mov     [rdi+40h], rax
0x18001e812  jmp     short loc_18001E81C
0x18001e814  mov     [rsp+58h+arg_0], rax
0x18001e819  mov     r14, rsi
0x18001e81c  mov     rcx, [r14]
0x18001e81f  cmp     dword ptr [rcx+8], 0
0x18001e823  jz      short loc_18001E87A
0x18001e825  add     rcx, rbp; void *
0x18001e828  xor     edx, edx; Val
0x18001e82a  mov     r8d, 402h; Size
0x18001e830  call    memset_0
0x18001e835  mov     rdx, [rsi]
0x18001e838  cmp     dword ptr [rdx+0B44h], 0
0x18001e83f  jnz     short loc_18001E87A
0x18001e841  add     rdx, rbp
0x18001e844  xor     ecx, ecx
0x18001e846  mov     r8d, 201h
0x18001e84c  call    cs:__imp_GetPersonalPhonebookPath
0x18001e852  test    eax, eax
0x18001e854  jnz     short loc_18001E87A
0x18001e856  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e85c  cmp     ecx, r13d
0x18001e85f  jz      short loc_18001E870
0x18001e861  lea     r8, aCrashookpageOn_9; "CRASHookPage::OnApply:Failed to get the"...
0x18001e868  mov     edx, ebp; dwFlags
0x18001e86a  call    cs:__imp_TracePrintfExA
0x18001e870  mov     ebx, 8007026Dh
0x18001e875  jmp     loc_18001EA18
0x18001e87a  mov     r8, [rsi]
0x18001e87d  lea     rcx, [r8+0Ch]
0x18001e881  add     r8, 40Eh; LPCWSTR
0x18001e888  movzx   eax, word ptr [rcx]
0x18001e88b  neg     ax
0x18001e88e  sbb     rdx, rdx
0x18001e891  and     rdx, rcx; lpString2
0x18001e894  xor     ecx, ecx; hWnd
0x18001e896  call    IsValidRASConnectionName
0x18001e89b  test    eax, eax
0x18001e89d  jz      short loc_18001E8B2
0x18001e89f  jle     loc_18001EA35
0x18001e8a5  movzx   eax, ax
0x18001e8a8  or      eax, 80070000h
0x18001e8ad  jmp     loc_18001EA35
0x18001e8b2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e8b8  cmp     ecx, r13d
0x18001e8bb  jz      short loc_18001E8DF
0x18001e8bd  mov     r9, [rsi]
0x18001e8c0  lea     r8, aCrashookpageOn_20; "CRASHookPage::OnApply: Entry:[%S],Pbk:["...
0x18001e8c7  mov     edx, ebp; dwFlags
0x18001e8c9  lea     rax, [r9+0Ch]
0x18001e8cd  add     r9, 40Eh
0x18001e8d4  mov     [rsp+58h+ppv], rax
0x18001e8d9  call    cs:__imp_TracePrintfExA
0x18001e8df  mov     rcx, [rsp+58h+arg_0]
0x18001e8e4  mov     rdx, [rsi]
0x18001e8e7  mov     rax, [rcx]
0x18001e8ea  mov     rax, [rax+18h]
0x18001e8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8f3  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e8f9  mov     ebx, eax
0x18001e8fb  cmp     ecx, r13d
0x18001e8fe  jz      short loc_18001E918
0x18001e900  mov     r9d, eax
0x18001e903  lea     r8, aCrashookpageOn_17; "CRASHookPage::OnApply:CreateRASEntry re"...
0x18001e90a  mov     edx, ebp; dwFlags
0x18001e90c  call    cs:__imp_TracePrintfExA
0x18001e912  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e918  test    ebx, ebx
0x18001e91a  jns     short loc_18001E939
0x18001e91c  cmp     ecx, r13d
0x18001e91f  jz      loc_18001EA18
0x18001e925  lea     r8, aCrashookpageOn_1; "CRASHookPage::OnApply:CreateRASEntry fa"...
0x18001e92c  mov     edx, ebp; dwFlags
0x18001e92e  call    cs:__imp_TracePrintfExA
0x18001e934  jmp     loc_18001EA18
0x18001e939  mov     r9, [rsi]
0x18001e93c  mov     dword ptr [rdi+48h], 1
0x18001e943  test    byte ptr [r9+4], 4
0x18001e948  jnz     loc_18001EA18
0x18001e94e  mov     rcx, [rdi+20h]
0x18001e952  lea     rbp, [rdi+8]
0x18001e956  mov     r14d, 2
0x18001e95c  lea     r8, aConnectionname; "ConnectionName"
0x18001e963  add     r9, 40Eh
0x18001e96a  mov     dword ptr [rsp+58h+ppv], r14d
0x18001e96f  mov     rdx, rbp
0x18001e972  mov     rax, [rcx]
0x18001e975  mov     rax, [rax+28h]
0x18001e979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e97e  mov     ebx, eax
0x18001e980  test    eax, eax
0x18001e982  jns     short loc_18001E99F
0x18001e984  mov     ecx, cs:g_dwTraceId
0x18001e98a  cmp     ecx, r13d
0x18001e98d  jz      loc_18001EA18
0x18001e993  mov     r9d, eax
0x18001e996  lea     r8, aCrashookpageOn_2; "CRASHookPage::OnApply:Unable to set the"...
0x18001e99d  jmp     short loc_18001EA0D
0x18001e99f  mov     r8, [rsi]
0x18001e9a2  mov     rdx, rbp
0x18001e9a5  mov     rcx, [rdi+20h]
0x18001e9a9  mov     r9d, [r8+714h]
0x18001e9b0  mov     r8d, [r8+4]
0x18001e9b4  call    UpdateConnectionTestedProperty
0x18001e9b9  mov     rcx, [rdi+20h]
0x18001e9bd  lea     r8, aConnectiontest_2; "ConnectionTesting"
0x18001e9c4  mov     dword ptr [rsp+58h+ppv], r14d
0x18001e9c9  lea     r9, CLSID_RASCTITestingPage
0x18001e9d0  mov     rdx, rbp
0x18001e9d3  mov     rax, [rcx]
0x18001e9d6  mov     r10, [rax+28h]
0x18001e9da  mov     rax, [rsi]
0x18001e9dd  test    [rax+4], r14b
0x18001e9e1  mov     rax, r10
0x18001e9e4  jnz     short loc_18001E9ED
0x18001e9e6  lea     r9, CLSID_RASCTWTestingPage
0x18001e9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9f2  mov     ebx, eax
0x18001e9f4  test    eax, eax
0x18001e9f6  jns     short loc_18001EA18
0x18001e9f8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e9fe  cmp     ecx, r13d
0x18001ea01  jz      short loc_18001EA18
0x18001ea03  mov     r9d, eax
0x18001ea06  lea     r8, aCrashookpageOn_6; "CRASHookPage::OnApply:Unable to set the"...
0x18001ea0d  mov     edx, 0Ch; dwFlags
0x18001ea12  call    cs:__imp_TracePrintfExA
0x18001ea18  test    r15d, r15d
0x18001ea1b  jz      short loc_18001EA33
0x18001ea1d  mov     rcx, [rsp+58h+arg_0]
0x18001ea22  test    rcx, rcx
0x18001ea25  jz      short loc_18001EA33
0x18001ea27  mov     rax, [rcx]
0x18001ea2a  mov     rax, [rax+10h]
0x18001ea2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea33  mov     eax, ebx
0x18001ea35  mov     rbx, [rsp+58h+arg_10]
0x18001ea3a  mov     rbp, [rsp+58h+arg_18]
0x18001ea3f  add     rsp, 30h
0x18001ea43  pop     r15
0x18001ea45  pop     r14
0x18001ea47  pop     r13
0x18001ea49  pop     rdi
0x18001ea4a  pop     rsi
0x18001ea4b  retn
```

# CRemoteAssistanceApp::ShowUsage(void)

- ea: `0x14001756c`
- end: `0x140017879`
- name: `?ShowUsage@CRemoteAssistanceApp@@QEAAXXZ`
- size: `781`
- prototype: `void __fastcall(CRemoteAssistanceApp *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140012794`

## callees

- `0x140002463`
- `0x140007fc4`
- `0x14001756c`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140017844`
- `KERNEL32!HeapFree` at `0x140017844`
- `KERNEL32!GetProcessHeap` at `0x1400175b8`
- `KERNEL32!GetProcessHeap` at `0x140017830`
- `KERNEL32!GetProcessHeap` at `0x1400175b8`
- `KERNEL32!GetProcessHeap` at `0x140017830`
- `KERNEL32!HeapAlloc` at `0x1400175d2`
- `KERNEL32!HeapAlloc` at `0x1400175d2`
- `USER32!LoadStringW` at `0x14001763f`
- `USER32!LoadStringW` at `0x1400176b9`
- `USER32!LoadStringW` at `0x140017708`
- `USER32!LoadStringW` at `0x14001775a`
- `USER32!LoadStringW` at `0x1400177ac`
- `USER32!LoadStringW` at `0x14001763f`
- `USER32!LoadStringW` at `0x1400176b9`
- `USER32!LoadStringW` at `0x140017708`
- `USER32!LoadStringW` at `0x14001775a`
- `USER32!LoadStringW` at `0x1400177ac`
- `COMCTL32!__imp_TaskDialog` at `0x140017824`
- `COMCTL32!__imp_TaskDialog` at `0x140017824`

## pseudocode

```c
void __fastcall CRemoteAssistanceApp::ShowUsage(HINSTANCE *this)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // rax
  CEventLogger *v4; // rcx
  unsigned __int16 *pszContent; // rbx
  CEventLogger *v6; // rcx
  unsigned int v7; // r9d
  signed int v8; // eax
  CEventLogger *v9; // rcx
  signed int v10; // eax
  CEventLogger *v11; // rcx
  signed int v12; // eax
  CEventLogger *v13; // rcx
  signed int v14; // eax
  CEventLogger *v15; // rcx
  signed int v16; // eax
  CEventLogger *v17; // rcx
  HANDLE v18; // rax
  int pnButton[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[1024]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  pnButton[0] = 1;
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x3F40u);
  pszContent = v3;
  if ( !v3 )
  {
    CEventLogger::LogError(
      v4,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x3F3u,
      L"CRemoteAssistanceApp::ShowUsage",
      0x8007000E);
    return;
  }
  memset_0(v3, 0, 0x3F40u);
  if ( !LoadStringW(this[76], 0x258u, Buffer, 1024) )
  {
    v7 = 1021;
LABEL_5:
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      v7,
      L"CRemoteAssistanceApp::ShowUsage",
      0);
    goto LABEL_26;
  }
  v8 = StringCchCatW(pszContent, 0x1FA0u, Buffer);
  if ( v8 >= 0 )
  {
    if ( !LoadStringW(this[76], 0x259u, Buffer, 1024) )
    {
      v7 = 1032;
      goto LABEL_5;
    }
    v10 = StringCchCatW(pszContent, 0x1FA0u, Buffer);
    if ( v10 >= 0 )
    {
      if ( !LoadStringW(this[76], 0x25Bu, Buffer, 1024) )
      {
        v7 = 1043;
        goto LABEL_5;
      }
      v12 = StringCchCatW(pszContent, 0x1FA0u, Buffer);
      if ( v12 >= 0 )
      {
        if ( !LoadStringW(this[76], 0x25Cu, Buffer, 1024) )
        {
          v7 = 1054;
          goto LABEL_5;
        }
        v14 = StringCchCatW(pszContent, 0x1FA0u, Buffer);
        if ( v14 >= 0 )
        {
          if ( LoadStringW(this[76], 0x247u, Buffer, 1024) )
          {
            v16 = StringCchCatW(pszContent, 0x1FA0u, Buffer);
            if ( v16 >= 0 )
              TaskDialog(
                0,
                *((HINSTANCE *)_AtlModule + 76),
                (PCWSTR)0x25A,
                (PCWSTR)0x257,
                pszContent,
                1,
                (PCWSTR)0xFFFD,
                pnButton);
            else
              CEventLogger::LogError(
                v17,
                &Recoverable_Error,
                L"base\\diagnosis\\ra\\ui\\app.cpp",
                0x42Eu,
                L"CRemoteAssistanceApp::ShowUsage",
                v16);
            goto LABEL_26;
          }
          v7 = 1065;
          goto LABEL_5;
        }
        CEventLogger::LogError(
          v15,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\app.cpp",
          0x423u,
          L"CRemoteAssistanceApp::ShowUsage",
          v14);
      }
      else
      {
        CEventLogger::LogError(
          v13,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\app.cpp",
          0x418u,
          L"CRemoteAssistanceApp::ShowUsage",
          v12);
      }
    }
    else
    {
      CEventLogger::LogError(
        v11,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\app.cpp",
        0x40Du,
        L"CRemoteAssistanceApp::ShowUsage",
        v10);
    }
  }
  else
  {
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x402u,
      L"CRemoteAssistanceApp::ShowUsage",
      v8);
  }
LABEL_26:
  v18 = GetProcessHeap();
  HeapFree(v18, 0, pszContent);
}

```

## disassembly

```asm
0x14001756c  mov     [rsp-8+arg_8], rbx
0x140017571  mov     [rsp-8+arg_10], rdi
0x140017576  push    rbp
0x140017577  push    r14
0x140017579  push    r15
0x14001757b  lea     rbp, [rsp-760h]
0x140017583  sub     rsp, 860h
0x14001758a  mov     rax, cs:__security_cookie
0x140017591  xor     rax, rsp
0x140017594  mov     [rbp+770h+var_20], rax
0x14001759b  mov     rdi, rcx
0x14001759e  xor     edx, edx; Val
0x1400175a0  lea     rcx, [rsp+870h+Buffer]; void *
0x1400175a5  mov     r8d, 800h; Size
0x1400175ab  call    memset_0
0x1400175b0  mov     [rsp+870h+var_830], 1
0x1400175b8  call    cs:__imp_GetProcessHeap
0x1400175bf  nop     dword ptr [rax+rax+00h]
0x1400175c4  mov     r14d, 3F40h
0x1400175ca  xor     edx, edx; dwFlags
0x1400175cc  mov     rcx, rax; hHeap
0x1400175cf  mov     r8d, r14d; dwBytes
0x1400175d2  call    cs:__imp_HeapAlloc
0x1400175d9  nop     dword ptr [rax+rax+00h]
0x1400175de  mov     rbx, rax
0x1400175e1  test    rax, rax
0x1400175e4  jnz     short loc_140017618
0x1400175e6  lea     rax, aCremoteassista_0; "CRemoteAssistanceApp::ShowUsage"
0x1400175ed  mov     [rsp+870h+dwCommonButtons], 8007000Eh; unsigned int
0x1400175f5  mov     r9d, 3F3h; unsigned int
0x1400175fb  mov     [rsp+870h+pszContent], rax; unsigned __int16 *
0x140017600  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x140017607  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14001760e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140017613  jmp     loc_140017850
0x140017618  mov     r8, r14; Size
0x14001761b  xor     edx, edx; Val
0x14001761d  mov     rcx, rbx; void *
0x140017620  call    memset_0
0x140017625  mov     rcx, [rdi+260h]; hInstance
0x14001762c  lea     r8, [rsp+870h+Buffer]; lpBuffer
0x140017631  mov     r15d, 400h
0x140017637  mov     edx, 258h; uID
0x14001763c  mov     r9d, r15d; cchBufferMax
0x14001763f  call    cs:__imp_LoadStringW
0x140017646  nop     dword ptr [rax+rax+00h]
0x14001764b  test    eax, eax
0x14001764d  jnz     short loc_14001767F
0x14001764f  lea     r9d, [r15-3]; unsigned int
0x140017653  mov     [rsp+870h+dwCommonButtons], 0; unsigned int
0x14001765b  lea     rax, aCremoteassista_0; "CRemoteAssistanceApp::ShowUsage"
0x140017662  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x140017669  mov     [rsp+870h+pszContent], rax; unsigned __int16 *
0x14001766e  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140017675  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001767a  jmp     loc_140017830
0x14001767f  mov     r14d, 1FA0h
0x140017685  lea     r8, [rsp+870h+Buffer]; unsigned __int16 *
0x14001768a  mov     edx, r14d; unsigned __int64
0x14001768d  mov     rcx, rbx; unsigned __int16 *
0x140017690  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140017695  test    eax, eax
0x140017697  jns     short loc_1400176A5
0x140017699  mov     [rsp+870h+dwCommonButtons], eax
0x14001769d  mov     r9d, 402h
0x1400176a3  jmp     short loc_14001765B
0x1400176a5  mov     rcx, [rdi+260h]; hInstance
0x1400176ac  lea     r8, [rsp+870h+Buffer]; lpBuffer
0x1400176b1  mov     r9d, r15d; cchBufferMax
0x1400176b4  mov     edx, 259h; uID
0x1400176b9  call    cs:__imp_LoadStringW
0x1400176c0  nop     dword ptr [rax+rax+00h]
0x1400176c5  test    eax, eax
0x1400176c7  jnz     short loc_1400176D1
0x1400176c9  mov     r9d, 408h
0x1400176cf  jmp     short loc_140017653
0x1400176d1  lea     r8, [rsp+870h+Buffer]; unsigned __int16 *
0x1400176d6  mov     rdx, r14; unsigned __int64
0x1400176d9  mov     rcx, rbx; unsigned __int16 *
0x1400176dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400176e1  test    eax, eax
0x1400176e3  jns     short loc_1400176F4
0x1400176e5  mov     [rsp+870h+dwCommonButtons], eax
0x1400176e9  mov     r9d, 40Dh
0x1400176ef  jmp     loc_14001765B
0x1400176f4  mov     rcx, [rdi+260h]; hInstance
0x1400176fb  lea     r8, [rsp+870h+Buffer]; lpBuffer
0x140017700  mov     r9d, r15d; cchBufferMax
0x140017703  mov     edx, 25Bh; uID
0x140017708  call    cs:__imp_LoadStringW
0x14001770f  nop     dword ptr [rax+rax+00h]
0x140017714  test    eax, eax
0x140017716  jnz     short loc_140017723
0x140017718  mov     r9d, 413h
0x14001771e  jmp     loc_140017653
0x140017723  lea     r8, [rsp+870h+Buffer]; unsigned __int16 *
0x140017728  mov     rdx, r14; unsigned __int64
0x14001772b  mov     rcx, rbx; unsigned __int16 *
0x14001772e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140017733  test    eax, eax
0x140017735  jns     short loc_140017746
0x140017737  mov     [rsp+870h+dwCommonButtons], eax
0x14001773b  mov     r9d, 418h
0x140017741  jmp     loc_14001765B
0x140017746  mov     rcx, [rdi+260h]; hInstance
0x14001774d  lea     r8, [rsp+870h+Buffer]; lpBuffer
0x140017752  mov     r9d, r15d; cchBufferMax
0x140017755  mov     edx, 25Ch; uID
0x14001775a  call    cs:__imp_LoadStringW
0x140017761  nop     dword ptr [rax+rax+00h]
0x140017766  test    eax, eax
0x140017768  jnz     short loc_140017775
0x14001776a  mov     r9d, 41Eh
0x140017770  jmp     loc_140017653
0x140017775  lea     r8, [rsp+870h+Buffer]; unsigned __int16 *
0x14001777a  mov     rdx, r14; unsigned __int64
0x14001777d  mov     rcx, rbx; unsigned __int16 *
0x140017780  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140017785  test    eax, eax
0x140017787  jns     short loc_140017798
0x140017789  mov     [rsp+870h+dwCommonButtons], eax
0x14001778d  mov     r9d, 423h
0x140017793  jmp     loc_14001765B
0x140017798  mov     rcx, [rdi+260h]; hInstance
0x14001779f  lea     r8, [rsp+870h+Buffer]; lpBuffer
0x1400177a4  mov     r9d, r15d; cchBufferMax
0x1400177a7  mov     edx, 247h; uID
0x1400177ac  call    cs:__imp_LoadStringW
0x1400177b3  nop     dword ptr [rax+rax+00h]
0x1400177b8  test    eax, eax
0x1400177ba  jnz     short loc_1400177C7
0x1400177bc  mov     r9d, 429h
0x1400177c2  jmp     loc_140017653
0x1400177c7  lea     r8, [rsp+870h+Buffer]; unsigned __int16 *
0x1400177cc  mov     rdx, r14; unsigned __int64
0x1400177cf  mov     rcx, rbx; unsigned __int16 *
0x1400177d2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400177d7  test    eax, eax
0x1400177d9  jns     short loc_1400177EA
0x1400177db  mov     [rsp+870h+dwCommonButtons], eax
0x1400177df  mov     r9d, 42Eh
0x1400177e5  jmp     loc_14001765B
0x1400177ea  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400177f1  lea     rax, [rsp+870h+var_830]
0x1400177f6  mov     [rsp+870h+pnButton], rax; pnButton
0x1400177fb  mov     r9d, 257h; pszMainInstruction
0x140017801  mov     [rsp+870h+pszIcon], 0FFFDh; pszIcon
0x14001780a  xor     ecx, ecx; hwndOwner
0x14001780c  mov     [rsp+870h+dwCommonButtons], 1; dwCommonButtons
0x140017814  mov     rdx, [rdx+260h]; hInstance
0x14001781b  lea     r8d, [r9+3]; pszWindowTitle
0x14001781f  mov     [rsp+870h+pszContent], rbx; pszContent
0x140017824  call    cs:__imp_TaskDialog
0x14001782b  nop     dword ptr [rax+rax+00h]
0x140017830  call    cs:__imp_GetProcessHeap
0x140017837  nop     dword ptr [rax+rax+00h]
0x14001783c  mov     r8, rbx; lpMem
0x14001783f  xor     edx, edx; dwFlags
0x140017841  mov     rcx, rax; hHeap
0x140017844  call    cs:__imp_HeapFree
0x14001784b  nop     dword ptr [rax+rax+00h]
0x140017850  mov     rcx, [rbp+770h+var_20]
0x140017857  xor     rcx, rsp; StackCookie
0x14001785a  call    __security_check_cookie
0x14001785f  lea     r11, [rsp+870h+var_10]
0x140017867  mov     rbx, [r11+28h]
0x14001786b  mov     rdi, [r11+30h]
0x14001786f  mov     rsp, r11
0x140017872  pop     r15
0x140017874  pop     r14
0x140017876  pop     rbp
0x140017877  retn
```

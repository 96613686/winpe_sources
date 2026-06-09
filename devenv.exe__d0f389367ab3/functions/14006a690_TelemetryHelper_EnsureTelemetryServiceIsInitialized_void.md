# TelemetryHelper::EnsureTelemetryServiceIsInitialized(void)

- ea: `0x14006a690`
- end: `0x14006a8ec`
- name: `?EnsureTelemetryServiceIsInitialized@TelemetryHelper@@YAJXZ`
- size: `604`
- prototype: `__int64 __fastcall(TelemetryHelper *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14006a63c`
- `0x14006a8ec`
- `0x14006a920`

## callees

- `0x140001020`
- `0x140001040`
- `0x140033ab0`
- `0x14006a5e0`
- `0x14006a690`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14006a6ee`
- `KERNEL32!GetCurrentProcessId` at `0x14006a6ee`
- `ole32!CreateItemMoniker` at `0x14006a74a`
- `ole32!CreateItemMoniker` at `0x14006a74a`
- `ole32!GetRunningObjectTable` at `0x14006a6de`
- `ole32!GetRunningObjectTable` at `0x14006a6de`
- `OLEAUT32!__imp_SysAllocString` at `0x14006a729`
- `OLEAUT32!__imp_SysAllocString` at `0x14006a729`
- `OLEAUT32!__imp_SysFreeString` at `0x14006a755`
- `OLEAUT32!__imp_SysFreeString` at `0x14006a755`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TelemetryHelper::EnsureTelemetryServiceIsInitialized(TelemetryHelper *this)
{
  HRESULT RunningObjectTable; // ebx
  const OLECHAR *v2; // rax
  OLECHAR *v3; // rdi
  __int64 v5; // [rsp+28h] [rbp-E0h] BYREF
  LPMONIKER ppmk; // [rsp+30h] [rbp-D8h] BYREF
  LPRUNNINGOBJECTTABLE pprot; // [rsp+38h] [rbp-D0h] BYREF
  OLECHAR psz; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v9[206]; // [rsp+4Ah] [rbp-BEh] BYREF

  if ( qword_14009F168 )
    return 0;
  pprot = 0;
  ppmk = 0;
  v5 = 0;
  RunningObjectTable = GetRunningObjectTable(0, &pprot);
  if ( RunningObjectTable >= 0 )
  {
    GetCurrentProcessId();
    psz = 0;
    memset_0(v9, 0, 0xC6u);
    _snwprintf_s<100>(&psz, 0x64u, (wchar_t *)L"Microsoft Visual Studio Telemetry:%d");
    v2 = SysAllocString(&psz);
    v3 = (OLECHAR *)v2;
    if ( !v2 )
      ATL::AtlThrowImpl(-2147024882);
    RunningObjectTable = CreateItemMoniker(L"!", v2, &ppmk);
    SysFreeString(v3);
    if ( RunningObjectTable >= 0 )
    {
      RunningObjectTable = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, LPMONIKER, __int64 *))pprot->lpVtbl->GetObjectA)(
                             pprot,
                             ppmk,
                             &v5);
      if ( RunningObjectTable >= 0 )
      {
        RunningObjectTable = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v5)(
                               v5,
                               &GUID_5c7e7029_a00c_4f57_be15_6ac5d43e78cb,
                               &qword_14009F178);
        if ( RunningObjectTable >= 0 )
        {
          if ( qword_14009F178 )
          {
            RunningObjectTable = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)qword_14009F178 + 24LL))(
                                   qword_14009F178,
                                   &qword_14009F168);
            if ( RunningObjectTable >= 0 )
            {
              RunningObjectTable = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))qword_14009F168)(
                                     qword_14009F168,
                                     &GUID_a6635ecb_ba4f_4c03_8e2d_fe57c576646f,
                                     &qword_14009F170);
              if ( RunningObjectTable >= 0 )
              {
                RunningObjectTable = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))qword_14009F178)(
                                       qword_14009F178,
                                       &GUID_f5366c81_fba0_466a_89ce_bad636e9661c,
                                       &qword_14009F180);
                if ( RunningObjectTable >= 0 )
                {
                  RunningObjectTable = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))qword_14009F178)(
                                         qword_14009F178,
                                         &GUID_15c32802_6cc9_4581_a952_70febcc2190e,
                                         &qword_14009F188);
                  if ( RunningObjectTable >= 0 )
                  {
                    RunningObjectTable = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)qword_14009F180
                                                                                       + 88LL))(
                                           qword_14009F180,
                                           &qword_14009F190);
                    if ( RunningObjectTable >= 0 )
                    {
                      if ( v5 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
                      if ( ppmk )
                        ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
                      if ( pprot )
                        ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Release)(pprot);
                      return 0;
                    }
                  }
                }
              }
            }
          }
          else
          {
            RunningObjectTable = -2147467259;
          }
        }
      }
    }
  }
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( ppmk )
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
  if ( pprot )
    ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Release)(pprot);
  return (unsigned int)RunningObjectTable;
}

```

## disassembly

```asm
0x14006a690  mov     rax, rsp
0x14006a693  mov     [rax+8], rbx
0x14006a697  mov     [rax+10h], rsi
0x14006a69b  mov     [rax+18h], rdi
0x14006a69f  push    rbp
0x14006a6a0  lea     rbp, [rax-28h]
0x14006a6a4  sub     rsp, 120h
0x14006a6ab  mov     rax, cs:__security_cookie
0x14006a6b2  xor     rax, rsp
0x14006a6b5  mov     [rbp+20h+var_10], rax
0x14006a6b9  xor     esi, esi
0x14006a6bb  cmp     cs:qword_14009F168, rsi
0x14006a6c2  jnz     loc_14006A87F
0x14006a6c8  mov     [rsp+120h+pprot], rsi
0x14006a6cd  mov     [rsp+120h+ppmk], rsi
0x14006a6d2  mov     [rsp+120h+var_100], rsi
0x14006a6d7  lea     rdx, [rsp+120h+pprot]; pprot
0x14006a6dc  xor     ecx, ecx; reserved
0x14006a6de  call    cs:__imp_GetRunningObjectTable
0x14006a6e4  mov     ebx, eax
0x14006a6e6  test    eax, eax
0x14006a6e8  js      loc_14006A8AB
0x14006a6ee  call    cs:__imp_GetCurrentProcessId
0x14006a6f4  mov     ebx, eax
0x14006a6f6  mov     [rsp+120h+psz], si
0x14006a6fb  xor     edx, edx; Val
0x14006a6fd  mov     r8d, 0C6h; Size
0x14006a703  lea     rcx, [rsp+120h+var_DE]; void *
0x14006a708  call    memset_0
0x14006a70d  mov     r9d, ebx
0x14006a710  lea     r8, aMicrosoftVisua_0; "Microsoft Visual Studio Telemetry:%d"
0x14006a717  lea     edx, [rsi+64h]; MaxCount
0x14006a71a  lea     rcx, [rsp+120h+psz]; Buffer
0x14006a71f  call    ??$_snwprintf_s@$0GE@@@YAHAEAY0GE@G_KPEBGZZ; _snwprintf_s<100>(ushort (&)[100],unsigned __int64,ushort const *,...)
0x14006a724  lea     rcx, [rsp+120h+psz]; psz
0x14006a729  call    cs:__imp_SysAllocString
0x14006a72f  mov     rdi, rax
0x14006a732  test    rax, rax
0x14006a735  jz      loc_14006A8E1
0x14006a73b  lea     r8, [rsp+120h+ppmk]; ppmk
0x14006a740  mov     rdx, rax; lpszItem
0x14006a743  lea     rcx, szDelim; "!"
0x14006a74a  call    cs:__imp_CreateItemMoniker
0x14006a750  mov     ebx, eax
0x14006a752  mov     rcx, rdi; bstrString
0x14006a755  call    cs:__imp_SysFreeString
0x14006a75b  test    ebx, ebx
0x14006a75d  js      loc_14006A8AB
0x14006a763  mov     rcx, [rsp+120h+pprot]
0x14006a768  mov     rax, [rcx]
0x14006a76b  lea     r8, [rsp+120h+var_100]
0x14006a770  mov     rdx, [rsp+120h+ppmk]
0x14006a775  call    qword ptr [rax+30h]
0x14006a778  mov     ebx, eax
0x14006a77a  test    eax, eax
0x14006a77c  js      loc_14006A8AB
0x14006a782  mov     rcx, [rsp+120h+var_100]
0x14006a787  mov     rax, [rcx]
0x14006a78a  lea     r8, qword_14009F178
0x14006a791  lea     rdx, _GUID_5c7e7029_a00c_4f57_be15_6ac5d43e78cb
0x14006a798  call    qword ptr [rax]
0x14006a79a  mov     ebx, eax
0x14006a79c  test    eax, eax
0x14006a79e  js      loc_14006A8AB
0x14006a7a4  mov     rcx, cs:qword_14009F178
0x14006a7ab  test    rcx, rcx
0x14006a7ae  jz      loc_14006A8A6
0x14006a7b4  mov     rax, [rcx]
0x14006a7b7  lea     rdx, qword_14009F168
0x14006a7be  call    qword ptr [rax+18h]
0x14006a7c1  mov     ebx, eax
0x14006a7c3  test    eax, eax
0x14006a7c5  js      loc_14006A8AB
0x14006a7cb  mov     rcx, cs:qword_14009F168
0x14006a7d2  mov     rax, [rcx]
0x14006a7d5  lea     r8, qword_14009F170
0x14006a7dc  lea     rdx, _GUID_a6635ecb_ba4f_4c03_8e2d_fe57c576646f
0x14006a7e3  call    qword ptr [rax]
0x14006a7e5  mov     ebx, eax
0x14006a7e7  test    eax, eax
0x14006a7e9  js      loc_14006A8AB
0x14006a7ef  mov     rcx, cs:qword_14009F178
0x14006a7f6  mov     rax, [rcx]
0x14006a7f9  lea     r8, qword_14009F180
0x14006a800  lea     rdx, _GUID_f5366c81_fba0_466a_89ce_bad636e9661c
0x14006a807  call    qword ptr [rax]
0x14006a809  mov     ebx, eax
0x14006a80b  test    eax, eax
0x14006a80d  js      loc_14006A8AB
0x14006a813  mov     rcx, cs:qword_14009F178
0x14006a81a  mov     rax, [rcx]
0x14006a81d  lea     r8, qword_14009F188
0x14006a824  lea     rdx, _GUID_15c32802_6cc9_4581_a952_70febcc2190e
0x14006a82b  call    qword ptr [rax]
0x14006a82d  mov     ebx, eax
0x14006a82f  test    eax, eax
0x14006a831  js      short loc_14006A8AB
0x14006a833  mov     rcx, cs:qword_14009F180
0x14006a83a  mov     rax, [rcx]
0x14006a83d  lea     rdx, qword_14009F190
0x14006a844  call    qword ptr [rax+58h]
0x14006a847  mov     ebx, eax
0x14006a849  test    eax, eax
0x14006a84b  js      short loc_14006A8AB
0x14006a84d  mov     rcx, [rsp+120h+var_100]
0x14006a852  test    rcx, rcx
0x14006a855  jz      short loc_14006A85E
0x14006a857  mov     rax, [rcx]
0x14006a85a  call    qword ptr [rax+10h]
0x14006a85d  nop
0x14006a85e  mov     rcx, [rsp+120h+ppmk]
0x14006a863  test    rcx, rcx
0x14006a866  jz      short loc_14006A86F
0x14006a868  mov     rax, [rcx]
0x14006a86b  call    qword ptr [rax+10h]
0x14006a86e  nop
0x14006a86f  mov     rcx, [rsp+120h+pprot]
0x14006a874  test    rcx, rcx
0x14006a877  jz      short loc_14006A87F
0x14006a879  mov     rax, [rcx]
0x14006a87c  call    qword ptr [rax+10h]
0x14006a87f  xor     eax, eax
0x14006a881  mov     rcx, [rbp+20h+var_10]
0x14006a885  xor     rcx, rsp; StackCookie
0x14006a888  call    __security_check_cookie
0x14006a88d  lea     r11, [rsp+120h+var_s0]
0x14006a895  mov     rbx, [r11+10h]
0x14006a899  mov     rsi, [r11+18h]
0x14006a89d  mov     rdi, [r11+20h]
0x14006a8a1  mov     rsp, r11
0x14006a8a4  pop     rbp
0x14006a8a5  retn
0x14006a8a6  mov     ebx, 80004005h
0x14006a8ab  mov     rcx, [rsp+120h+var_100]
0x14006a8b0  test    rcx, rcx
0x14006a8b3  jz      short loc_14006A8BC
0x14006a8b5  mov     rax, [rcx]
0x14006a8b8  call    qword ptr [rax+10h]
0x14006a8bb  nop
0x14006a8bc  mov     rcx, [rsp+120h+ppmk]
0x14006a8c1  test    rcx, rcx
0x14006a8c4  jz      short loc_14006A8CD
0x14006a8c6  mov     rdx, [rcx]
0x14006a8c9  call    qword ptr [rdx+10h]
0x14006a8cc  nop
0x14006a8cd  mov     rcx, [rsp+120h+pprot]
0x14006a8d2  test    rcx, rcx
0x14006a8d5  jz      short loc_14006A8DD
0x14006a8d7  mov     rdx, [rcx]
0x14006a8da  call    qword ptr [rdx+10h]
0x14006a8dd  mov     eax, ebx
0x14006a8df  jmp     short loc_14006A881
0x14006a8e1  mov     ecx, 8007000Eh; int
0x14006a8e6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

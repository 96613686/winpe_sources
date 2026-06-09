# GetRASystemHealth(void *)

- ea: `0x140030cb0`
- end: `0x140030f69`
- name: `?GetRASystemHealth@@YAKPEAX@Z`
- size: `697`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140002463`
- `0x140030a44`
- `0x140030cb0`
- `0x140034ce4`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140030ef0`
- `KERNEL32!HeapFree` at `0x140030ef0`
- `KERNEL32!GetProcessHeap` at `0x140030edc`
- `KERNEL32!GetProcessHeap` at `0x140030edc`
- `ole32!CoTaskMemFree` at `0x140030f06`
- `ole32!CoTaskMemFree` at `0x140030f06`
- `ole32!CoUninitialize` at `0x140030f3f`
- `ole32!CoUninitialize` at `0x140030f3f`
- `ole32!CoCreateInstance` at `0x140030e38`
- `ole32!CoCreateInstance` at `0x140030e38`
- `ole32!CoInitializeEx` at `0x140030d59`
- `ole32!CoInitializeEx` at `0x140030d59`

## string_xrefs

- `0x140030dd1`: `UserSID`
- `0x140030e0b`: `%systemroot%\system32\msra.exe`

## pseudocode

```c
__int64 __fastcall GetRASystemHealth(_DWORD *Parameter)
{
  HRESULT ProcessSID; // eax
  int v4; // esi
  unsigned int v5; // r9d
  void *v6; // rbx
  HRESULT v7; // eax
  unsigned int v8; // r9d
  HANDLE ProcessHeap; // rax
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem[3]; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v14; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v15[34]; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v16; // [rsp+F0h] [rbp-10h]
  int v17; // [rsp+F8h] [rbp-8h]
  LPVOID v18; // [rsp+100h] [rbp+0h]
  LPVOID v19; // [rsp+108h] [rbp+8h]
  const wchar_t *v20; // [rsp+180h] [rbp+80h]
  int v21; // [rsp+188h] [rbp+88h]
  const wchar_t *v22; // [rsp+190h] [rbp+90h]

  v14 = 0;
  memset_0(v15, 0, 0x1A8u);
  ppv = 0;
  pv = 0;
  v10 = 2;
  *(_OWORD *)lpMem = 0;
  if ( !Parameter )
  {
    CEventLogger::LogError(
      (CEventLogger *)L"GetRASystemHealth",
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x297u,
      L"GetRASystemHealth",
      0x80070057);
    return 2147942487LL;
  }
  *Parameter = 1;
  ProcessSID = CoInitializeEx(0, 0);
  if ( ProcessSID < 0 )
  {
    v4 = 0;
    v5 = 671;
LABEL_5:
    CEventLogger::LogError(
      (CEventLogger *)L"GetRASystemHealth",
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      v5,
      L"GetRASystemHealth",
      ProcessSID);
    v6 = lpMem[1];
    goto LABEL_17;
  }
  v4 = 1;
  ProcessSID = GetProcessSID((struct tagOCTET_STRING *)lpMem);
  if ( ProcessSID < 0 )
  {
    v5 = 674;
    goto LABEL_5;
  }
  v6 = lpMem[1];
  v14 = L"DiagnosisType";
  v15[0] = 7;
  v16 = L"UserSID";
  v18 = lpMem[0];
  v15[2] = 1;
  v20 = L"AppID";
  v22 = L"%systemroot%\\system32\\msra.exe";
  v17 = 14;
  v19 = lpMem[1];
  v21 = 10;
  v7 = CoCreateInstance(&CLSID_RAHelper, 0, 1u, &GUID_c0b35746_ebf5_11d8_bbe9_505054503030, &ppv);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, const wchar_t **))(*(_QWORD *)ppv + 24LL))(ppv, 3, &v14);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID *, _QWORD, int *))(*(_QWORD *)ppv + 48LL))(
             ppv,
             0,
             &pv,
             0,
             &v10);
      if ( v7 >= 0 )
      {
        if ( v10 == 1 )
          *Parameter = 2;
        goto LABEL_17;
      }
      v8 = 703;
    }
    else
    {
      v8 = 698;
    }
  }
  else
  {
    v8 = 696;
  }
  CEventLogger::LogError(
    (CEventLogger *)L"GetRASystemHealth",
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
    v8,
    L"GetRASystemHealth",
    v7);
LABEL_17:
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v4 == 1 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x140030cb0  push    rbp
0x140030cb2  push    rbx
0x140030cb3  push    rsi
0x140030cb4  push    rdi
0x140030cb5  lea     rbp, [rsp-128h]
0x140030cbd  sub     rsp, 228h
0x140030cc4  mov     rax, cs:__security_cookie
0x140030ccb  xor     rax, rsp
0x140030cce  mov     [rbp+140h+var_30], rax
0x140030cd5  mov     rdi, rcx
0x140030cd8  mov     [rsp+240h+var_1E0], 0
0x140030ce1  lea     rcx, [rsp+240h+var_1D8]; void *
0x140030ce6  xor     edx, edx; Val
0x140030ce8  mov     r8d, 1A8h; Size
0x140030cee  call    memset_0
0x140030cf3  mov     [rsp+240h+var_208], 0
0x140030cfc  xorps   xmm0, xmm0
0x140030cff  mov     [rsp+240h+pv], 0
0x140030d08  mov     [rsp+240h+var_210], 2
0x140030d10  movups  xmmword ptr [rsp+240h+lpMem], xmm0
0x140030d15  test    rdi, rdi
0x140030d18  jnz     short loc_140030D4F
0x140030d1a  lea     rcx, aGetrasystemhea; "GetRASystemHealth"
0x140030d21  mov     ebx, 80070057h
0x140030d26  mov     [rsp+240h+var_218], ebx; unsigned int
0x140030d2a  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030d31  mov     r9d, 297h; unsigned int
0x140030d37  mov     [rsp+240h+ppv], rcx; unsigned __int16 *
0x140030d3c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030d43  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030d48  mov     eax, ebx
0x140030d4a  jmp     loc_140030F4D
0x140030d4f  xor     edx, edx; dwCoInit
0x140030d51  mov     dword ptr [rdi], 1
0x140030d57  xor     ecx, ecx; pvReserved
0x140030d59  call    cs:__imp_CoInitializeEx
0x140030d60  nop     dword ptr [rax+rax+00h]
0x140030d65  test    eax, eax
0x140030d67  jns     short loc_140030D9E
0x140030d69  xor     esi, esi
0x140030d6b  mov     r9d, 29Fh; unsigned int
0x140030d71  lea     rcx, aGetrasystemhea; "GetRASystemHealth"
0x140030d78  mov     [rsp+240h+var_218], eax; unsigned int
0x140030d7c  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030d83  mov     [rsp+240h+ppv], rcx; unsigned __int16 *
0x140030d88  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030d8f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030d94  mov     rbx, [rsp+240h+lpMem+8]
0x140030d99  jmp     loc_140030ED7
0x140030d9e  lea     rcx, [rsp+240h+lpMem]; struct tagOCTET_STRING *
0x140030da3  mov     esi, 1
0x140030da8  call    ?GetProcessSID@@YAJPEAUtagOCTET_STRING@@@Z; GetProcessSID(tagOCTET_STRING *)
0x140030dad  test    eax, eax
0x140030daf  jns     short loc_140030DB9
0x140030db1  mov     r9d, 2A2h
0x140030db7  jmp     short loc_140030D71
0x140030db9  mov     rbx, [rsp+240h+lpMem+8]
0x140030dbe  lea     rax, aDiagnosistype; "DiagnosisType"
0x140030dc5  mov     [rsp+240h+var_1E0], rax
0x140030dca  lea     r9, _GUID_c0b35746_ebf5_11d8_bbe9_505054503030; riid
0x140030dd1  lea     rax, aUsersid; "UserSID"
0x140030dd8  mov     [rsp+240h+var_1D8], 7
0x140030de0  mov     [rbp+140h+var_150], rax
0x140030de4  lea     rcx, CLSID_RAHelper; rclsid
0x140030deb  mov     rax, [rsp+240h+lpMem]
0x140030df0  xor     edx, edx; pUnkOuter
0x140030df2  mov     [rbp+140h+var_140], rax
0x140030df6  mov     r8d, esi; dwClsContext
0x140030df9  lea     rax, aAppid_0; "AppID"
0x140030e00  mov     [rsp+240h+var_1D0], esi
0x140030e04  mov     [rbp+140h+var_C0], rax
0x140030e0b  lea     rax, aSystemrootSyst; "%systemroot%\\system32\\msra.exe"
0x140030e12  mov     [rbp+140h+var_B0], rax
0x140030e19  lea     rax, [rsp+240h+var_208]
0x140030e1e  mov     [rsp+240h+ppv], rax; ppv
0x140030e23  mov     [rbp+140h+var_148], 0Eh
0x140030e2a  mov     [rbp+140h+var_138], rbx
0x140030e2e  mov     [rbp+140h+var_B8], 0Ah
0x140030e38  call    cs:__imp_CoCreateInstance
0x140030e3f  nop     dword ptr [rax+rax+00h]
0x140030e44  test    eax, eax
0x140030e46  jns     short loc_140030E73
0x140030e48  mov     r9d, 2B8h; unsigned int
0x140030e4e  lea     rcx, aGetrasystemhea; "GetRASystemHealth"
0x140030e55  mov     [rsp+240h+var_218], eax; unsigned int
0x140030e59  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030e60  mov     [rsp+240h+ppv], rcx; unsigned __int16 *
0x140030e65  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030e6c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030e71  jmp     short loc_140030ED7
0x140030e73  mov     rcx, [rsp+240h+var_208]
0x140030e78  lea     r8, [rsp+240h+var_1E0]
0x140030e7d  mov     edx, 3
0x140030e82  mov     rax, [rcx]
0x140030e85  mov     rax, [rax+18h]
0x140030e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030e8e  test    eax, eax
0x140030e90  jns     short loc_140030E9A
0x140030e92  mov     r9d, 2BAh
0x140030e98  jmp     short loc_140030E4E
0x140030e9a  mov     rcx, [rsp+240h+var_208]
0x140030e9f  lea     rdx, [rsp+240h+var_210]
0x140030ea4  mov     [rsp+240h+ppv], rdx
0x140030ea9  lea     r8, [rsp+240h+pv]
0x140030eae  xor     r9d, r9d
0x140030eb1  xor     edx, edx
0x140030eb3  mov     rax, [rcx]
0x140030eb6  mov     rax, [rax+30h]
0x140030eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030ebf  test    eax, eax
0x140030ec1  jns     short loc_140030ECB
0x140030ec3  mov     r9d, 2BFh
0x140030ec9  jmp     short loc_140030E4E
0x140030ecb  cmp     [rsp+240h+var_210], esi
0x140030ecf  jnz     short loc_140030ED7
0x140030ed1  mov     dword ptr [rdi], 2
0x140030ed7  test    rbx, rbx
0x140030eda  jz      short loc_140030EFC
0x140030edc  call    cs:__imp_GetProcessHeap
0x140030ee3  nop     dword ptr [rax+rax+00h]
0x140030ee8  mov     r8, rbx; lpMem
0x140030eeb  xor     edx, edx; dwFlags
0x140030eed  mov     rcx, rax; hHeap
0x140030ef0  call    cs:__imp_HeapFree
0x140030ef7  nop     dword ptr [rax+rax+00h]
0x140030efc  mov     rcx, [rsp+240h+pv]; pv
0x140030f01  test    rcx, rcx
0x140030f04  jz      short loc_140030F1B
0x140030f06  call    cs:__imp_CoTaskMemFree
0x140030f0d  nop     dword ptr [rax+rax+00h]
0x140030f12  mov     [rsp+240h+pv], 0
0x140030f1b  mov     rcx, [rsp+240h+var_208]
0x140030f20  test    rcx, rcx
0x140030f23  jz      short loc_140030F3A
0x140030f25  mov     rax, [rcx]
0x140030f28  mov     rax, [rax+10h]
0x140030f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030f31  mov     [rsp+240h+var_208], 0
0x140030f3a  cmp     esi, 1
0x140030f3d  jnz     short loc_140030F4B
0x140030f3f  call    cs:__imp_CoUninitialize
0x140030f46  nop     dword ptr [rax+rax+00h]
0x140030f4b  xor     eax, eax
0x140030f4d  mov     rcx, [rbp+140h+var_30]
0x140030f54  xor     rcx, rsp; StackCookie
0x140030f57  call    __security_check_cookie
0x140030f5c  add     rsp, 228h
0x140030f63  pop     rdi
0x140030f64  pop     rsi
0x140030f65  pop     rbx
0x140030f66  pop     rbp
0x140030f67  retn
```

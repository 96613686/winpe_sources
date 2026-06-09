# FindAndCreateWindowClass(HWND__ *,int,CLASS_ENUM,long,long,_GUID const &,void * *)

- ea: `0x18000bc30`
- end: `0x18000c139`
- name: `?FindAndCreateWindowClass@@YAJPEAUHWND__@@HW4CLASS_ENUM@@JJAEBU_GUID@@PEAPEAX@Z`
- size: `1289`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c370`
- `0x180045110`

## callees

- `0x18000baa0`
- `0x18000bc30`
- `0x18000c140`
- `0x18000c318`
- `0x18001bb6c`
- `0x18001e4c0`
- `0x180047c30`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000bf08`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000bf08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c10a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c10a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000be25`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000be25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c115`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c115`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18000bcc4`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18000bfed`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18000bcc4`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18000bfed`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c043`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c043`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf97`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bfa8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf97`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bfa8`
- `USER32!SendMessageTimeoutW` at `0x18000bd52`
- `USER32!SendMessageTimeoutW` at `0x18000bd52`
- `USER32!GetWindowThreadProcessId` at `0x18000be0b`
- `USER32!GetWindowThreadProcessId` at `0x18000be0b`
- `USER32!GetDesktopWindow` at `0x18000beb0`
- `USER32!GetDesktopWindow` at `0x18000beb0`
- `USER32!GetClassNameW` at `0x18000bf33`
- `USER32!GetClassNameW` at `0x18000c0b6`
- `USER32!GetClassNameW` at `0x18000bf33`
- `USER32!GetClassNameW` at `0x18000c0b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall FindAndCreateWindowClass(
        HWND a1,
        DWORD a2,
        int a3,
        int a4,
        unsigned int a5,
        struct _GUID *a6,
        void **a7)
{
  DWORD v8; // edi
  void **v10; // r14
  int ClassNameW; // eax
  int v12; // r15d
  ATOM AtomW; // r8
  int v14; // edx
  int i; // ecx
  __int64 v16; // rcx
  int *v17; // rax
  signed int v18; // ebx
  __int64 v19; // rdi
  HANDLE v21; // rsi
  int v22; // ebx
  int v23; // eax
  signed int LastError; // eax
  BSTR v25; // rsi
  unsigned __int16 *v26; // r14
  int v27; // eax
  WCHAR *v28; // rcx
  unsigned __int16 *ProviderInfo; // rax
  int v30; // r8d
  OLECHAR *v31; // rdi
  const WCHAR *v32; // rcx
  ATOM v33; // r8
  int v34; // edx
  int j; // eax
  __int64 v36; // rcx
  int *v37; // rax
  BOOL v38; // eax
  __int64 *v39; // rdx
  DWORD dwProcessId; // [rsp+40h] [rbp-C0h] BYREF
  ULONG_PTR dwResult; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h]
  int v43; // [rsp+58h] [rbp-A8h]
  void **v44; // [rsp+60h] [rbp-A0h]
  struct _GUID *v45; // [rsp+68h] [rbp-98h]
  WCHAR ClassName[64]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String[128]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v48[128]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR Buffer[256]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v43 = a4;
  v8 = a2;
  dwProcessId = a2;
  v45 = a6;
  v10 = a7;
  v44 = a7;
  String[0] = 0;
  if ( lpfnRealGetWindowClass )
    ClassNameW = ((__int64 (__fastcall *)(HWND, WCHAR *, __int64))lpfnRealGetWindowClass)(a1, String, 128);
  else
    ClassNameW = GetClassNameW(a1, String, 128);
  if ( ClassNameW )
  {
    v12 = 0;
    AtomW = GlobalFindAtomW(String);
    if ( AtomW )
    {
      v14 = 2;
      if ( !v8 )
        v14 = 32;
      for ( i = 0; i < v14; ++i )
      {
        if ( *((_WORD *)&rgAtomClasses + i) == AtomW )
        {
          v16 = i;
          _mm_lfence();
          if ( v8 )
            v17 = (int *)L"#";
          else
            v17 = dword_180054260;
          v12 = v17[v16];
          if ( v12 != -1 )
            goto LABEL_19;
          break;
        }
      }
    }
    v18 = 0;
    dwResult = 0;
    if ( !SendMessageTimeoutW(a1, 0x3Du, 0, -12, 2u, 0x4E20u, &dwResult) )
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError == 1460 )
      {
        v18 = -2146233083;
      }
      else if ( LastError > 0 )
      {
        v18 = (unsigned __int16)LastError | 0x80070000;
      }
      bstrString = 0;
      if ( LoadStringW(hinstResDll, 0x138Au, Buffer, 256) )
        bstrString = SysAllocString(Buffer);
      v25 = (BSTR)&qword_1800542E0;
      v26 = (unsigned __int16 *)&qword_1800542E0;
      if ( a1 )
      {
        v27 = GetClassNameW(a1, ClassName, 64);
        v28 = (WCHAR *)L"?";
        if ( v27 )
          v28 = ClassName;
        v26 = v48;
        if ( (int)StringCchPrintfW(v48, 0x80u, L"0x%08p (%s)", a1, v28) < 0 )
          v26 = (unsigned __int16 *)&qword_1800542E0;
      }
      ProviderInfo = GetProviderInfo(0);
      v31 = ProviderInfo;
      if ( (Microsoft_Windows_OLEACCEnableBits & 1) != 0 )
      {
        v39 = &qword_1800542E0;
        if ( ProviderInfo )
          v39 = (__int64 *)ProviderInfo;
        if ( bstrString )
          v25 = bstrString;
        McTemplateMofU0zqzzz(
          (_DWORD)bstrString,
          (_DWORD)v39,
          v30,
          (unsigned int)L"SendMessageTimeoutHelper",
          v18,
          (__int64)v25,
          (__int64)v26,
          (__int64)v39);
      }
      if ( v31 )
        SysFreeString(v31);
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      v10 = v44;
      v8 = dwProcessId;
    }
    if ( v18 < 0 )
    {
      Error::IAccessibleError(0, L"OleAcc: LookupWindowClass", v18, a1, 5002);
    }
    else if ( dwResult >= 0x10000 && dwResult - 0x10000 <= 0x1F )
    {
      v32 = off_180052380[dwResult - 0x10000];
      if ( v32 )
      {
        v33 = GlobalFindAtomW(v32);
        if ( v33 )
        {
          v34 = 2;
          if ( !v8 )
            v34 = 32;
          for ( j = 0; j < v34; ++j )
          {
            v36 = j;
            if ( *((_WORD *)&rgAtomClasses + j) == v33 )
            {
              _mm_lfence();
              if ( v8 )
                v37 = (int *)L"#";
              else
                v37 = dword_180054260;
              v12 = v37[v36];
              v38 = v12 != -1;
              goto LABEL_65;
            }
          }
        }
        v38 = 0;
LABEL_65:
        if ( v38 )
          goto LABEL_19;
      }
    }
  }
  if ( a3 == -1 )
  {
    *v10 = 0;
    return -2147467259;
  }
  v12 = a3;
LABEL_19:
  v19 = 40LL * v12;
  if ( *(_DWORD *)&algn_18004A398[v19] )
    return (*(__int64 (__fastcall **)(HWND, _QWORD, struct _GUID *, void **))((char *)&g_ClassInfo + v19))(
             a1,
             a5,
             v45,
             v10);
  if ( dword_180061968 )
  {
    if ( dword_180061968 == 1 )
      return (*(__int64 (__fastcall **)(HWND, _QWORD, struct _GUID *, void **))((char *)&g_ClassInfo + v19))(
               a1,
               a5,
               v45,
               v10);
  }
  else
  {
    dword_180061968 = 2;
  }
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(a1, &dwProcessId) )
    return -2147467259;
  v21 = OpenProcess(0x400u, 0, dwProcessId);
  if ( !v21 )
  {
    if ( a1 == GetDesktopWindow() )
    {
LABEL_33:
      v23 = 1;
      goto LABEL_29;
    }
    GetLastError();
    return -2147467259;
  }
  dwResult = 0;
  if ( !lpfnNtQueryInformationProcess )
  {
    CloseHandle(v21);
    goto LABEL_33;
  }
  v22 = lpfnNtQueryInformationProcess(v21, 26, &dwResult, 8u, 0);
  CloseHandle(v21);
  if ( (v22 & 0xC0000000) == 0xC0000000 || !dwResult )
    goto LABEL_33;
  v23 = 0;
LABEL_29:
  if ( v23 )
    return (*(__int64 (__fastcall **)(HWND, _QWORD, struct _GUID *, void **))((char *)&g_ClassInfo + v19))(
             a1,
             a5,
             v45,
             v10);
  return CreateRemoteProxy6432(a1, v43, v45, v10);
}

```

## disassembly

```asm
0x18000bc30  mov     [rsp-8+arg_8], rbx
0x18000bc35  push    rbp
0x18000bc36  push    rsi
0x18000bc37  push    rdi
0x18000bc38  push    r12
0x18000bc3a  push    r13
0x18000bc3c  push    r14
0x18000bc3e  push    r15
0x18000bc40  lea     rbp, [rsp-400h]
0x18000bc48  sub     rsp, 500h
0x18000bc4f  mov     rax, cs:__security_cookie
0x18000bc56  xor     rax, rsp
0x18000bc59  mov     [rbp+430h+var_40], rax
0x18000bc60  mov     [rsp+530h+var_4D8], r9d
0x18000bc65  mov     r13d, r8d
0x18000bc68  mov     edi, edx
0x18000bc6a  mov     [rsp+530h+dwProcessId], edx
0x18000bc6e  mov     r12, rcx
0x18000bc71  mov     rax, [rbp+430h+arg_28]
0x18000bc78  mov     [rsp+530h+var_4C8], rax
0x18000bc7d  mov     r14, [rbp+430h+arg_30]
0x18000bc84  mov     [rsp+530h+var_4D0], r14
0x18000bc89  xor     eax, eax
0x18000bc8b  mov     [rbp+430h+String], ax
0x18000bc8f  mov     rax, cs:?lpfnRealGetWindowClass@@3P6AIPEAUHWND__@@PEAGI@ZEA; uint (*lpfnRealGetWindowClass)(HWND__ *,ushort *,uint)
0x18000bc96  mov     r8d, 80h; nMaxCount
0x18000bc9c  lea     rdx, [rbp+430h+String]; lpClassName
0x18000bca0  test    rax, rax
0x18000bca3  jz      loc_18000C0B6
0x18000bca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcae  lea     rsi, __ImageBase
0x18000bcb5  test    eax, eax
0x18000bcb7  jz      loc_18000BD7A
0x18000bcbd  xor     r15d, r15d
0x18000bcc0  lea     rcx, [rbp+430h+String]; lpString
0x18000bcc4  call    cs:__imp_GlobalFindAtomW
0x18000bcca  movzx   r8d, ax
0x18000bcce  mov     eax, 20h ; ' '
0x18000bcd3  test    r8w, r8w
0x18000bcd7  jz      short loc_18000BD1F
0x18000bcd9  mov     edx, 2
0x18000bcde  test    edi, edi
0x18000bce0  cmovz   edx, eax
0x18000bce3  xor     ecx, ecx
0x18000bce5  cmp     ecx, edx
0x18000bce7  jge     short loc_18000BD1F
0x18000bce9  movsxd  rax, ecx
0x18000bcec  cmp     rva ?rgAtomClasses@@3PAGA[rsi+rax*2], r8w; ushort near * rgAtomClasses ...
0x18000bcf5  jz      short loc_18000BCFB
0x18000bcf7  inc     ecx
0x18000bcf9  jmp     short loc_18000BCE5
0x18000bcfb  lea     rcx, ds:0[rax*4]
0x18000bd03  lfence
0x18000bd06  test    edi, edi
0x18000bd08  jnz     loc_18000BEA4
0x18000bd0e  lea     rax, dword_180054260
0x18000bd15  mov     r15d, [rcx+rax]
0x18000bd19  cmp     r15d, 0FFFFFFFFh
0x18000bd1d  jnz     short loc_18000BD87
0x18000bd1f  xor     ebx, ebx
0x18000bd21  mov     [rsp+530h+dwResult], rbx
0x18000bd26  lea     rax, [rsp+530h+dwResult]
0x18000bd2b  mov     [rsp+530h+lpdwResult], rax; lpdwResult
0x18000bd30  mov     [rsp+530h+uTimeout], 4E20h; uTimeout
0x18000bd38  mov     [rsp+530h+fuFlags], 2; fuFlags
0x18000bd40  mov     r9, 0FFFFFFFFFFFFFFF4h; lParam
0x18000bd47  xor     r8d, r8d; wParam
0x18000bd4a  mov     edx, 3Dh ; '='; Msg
0x18000bd4f  mov     rcx, r12; hWnd
0x18000bd52  call    cs:__imp_SendMessageTimeoutW
0x18000bd58  test    rax, rax
0x18000bd5b  jz      loc_18000BEC6
0x18000bd61  test    ebx, ebx
0x18000bd63  js      loc_18000C053
0x18000bd69  mov     rax, [rsp+530h+dwResult]
0x18000bd6e  cmp     rax, 10000h
0x18000bd74  jnb     loc_18000BFCC
0x18000bd7a  cmp     r13d, 0FFFFFFFFh
0x18000bd7e  jz      loc_18000C02B
0x18000bd84  mov     r15d, r13d
0x18000bd87  movsxd  rax, r15d
0x18000bd8a  lea     rcx, [rax+rax*4]
0x18000bd8e  lea     rdi, ds:0[rcx*8]
0x18000bd96  cmp     dword ptr [rdi+rsi+4A398h], 0
0x18000bd9e  jz      short loc_18000BDE8
0x18000bda0  mov     r9, r14
0x18000bda3  mov     r8, [rsp+530h+var_4C8]
0x18000bda8  mov     edx, [rbp+430h+arg_20]
0x18000bdae  mov     rcx, r12
0x18000bdb1  mov     rax, [rdi+rsi+4A390h]
0x18000bdb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdbe  mov     rcx, [rbp+430h+var_40]
0x18000bdc5  xor     rcx, rsp; StackCookie
0x18000bdc8  call    __security_check_cookie
0x18000bdcd  mov     rbx, [rsp+530h+arg_8]
0x18000bdd5  add     rsp, 500h
0x18000bddc  pop     r15
0x18000bdde  pop     r14
0x18000bde0  pop     r13
0x18000bde2  pop     r12
0x18000bde4  pop     rdi
0x18000bde5  pop     rsi
0x18000bde6  pop     rbp
0x18000bde7  retn
0x18000bde8  mov     eax, cs:dword_180061968
0x18000bdee  test    eax, eax
0x18000bdf0  jz      loc_18000C0FB
0x18000bdf6  cmp     eax, 1
0x18000bdf9  jz      short loc_18000BDA0
0x18000bdfb  mov     [rsp+530h+dwProcessId], 0
0x18000be03  lea     rdx, [rsp+530h+dwProcessId]; lpdwProcessId
0x18000be08  mov     rcx, r12; hWnd
0x18000be0b  call    cs:__imp_GetWindowThreadProcessId
0x18000be11  test    eax, eax
0x18000be13  jz      loc_18000C032
0x18000be19  mov     r8d, [rsp+530h+dwProcessId]; dwProcessId
0x18000be1e  xor     edx, edx; bInheritHandle
0x18000be20  mov     ecx, 400h; dwDesiredAccess
0x18000be25  call    cs:__imp_OpenProcess
0x18000be2b  mov     rsi, rax
0x18000be2e  test    rax, rax
0x18000be31  jz      short loc_18000BEB0
0x18000be33  mov     [rsp+530h+dwResult], 0
0x18000be3c  mov     rax, cs:?lpfnNtQueryInformationProcess@@3P6AJPEAXH0KPEAK@ZEA; long (*lpfnNtQueryInformationProcess)(void *,int,void *,ulong,ulong *)
0x18000be43  mov     rcx, rsi; hObject
0x18000be46  test    rax, rax
0x18000be49  jz      loc_18000C115
0x18000be4f  mov     qword ptr [rsp+530h+fuFlags], 0
0x18000be58  mov     r9d, 8
0x18000be5e  lea     r8, [rsp+530h+dwResult]
0x18000be63  mov     edx, 1Ah
0x18000be68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be6d  mov     ebx, eax
0x18000be6f  mov     rcx, rsi; hObject
0x18000be72  call    cs:__imp_CloseHandle
0x18000be78  and     ebx, 0C0000000h
0x18000be7e  cmp     ebx, 0C0000000h
0x18000be84  jz      short loc_18000BEBF
0x18000be86  cmp     [rsp+530h+dwResult], 0
0x18000be8c  jz      short loc_18000BEBF
0x18000be8e  xor     eax, eax
0x18000be90  test    eax, eax
0x18000be92  jz      loc_18000C120
0x18000be98  lea     rsi, __ImageBase
0x18000be9f  jmp     loc_18000BDA0
0x18000bea4  lea     rax, ?g_WindowClassMap@@3PAW4CLASS_ENUM@@A; "#"
0x18000beab  jmp     loc_18000BD15
0x18000beb0  call    cs:__imp_GetDesktopWindow
0x18000beb6  cmp     r12, rax
0x18000beb9  jnz     loc_18000C10A
0x18000bebf  mov     eax, 1
0x18000bec4  jmp     short loc_18000BE90
0x18000bec6  call    cs:__imp_GetLastError
0x18000becc  mov     ebx, eax
0x18000bece  cmp     eax, 5B4h
0x18000bed3  jz      loc_18000C0AC
0x18000bed9  test    eax, eax
0x18000bedb  jle     short loc_18000BEE6
0x18000bedd  movzx   ebx, ax
0x18000bee0  or      ebx, 80070000h
0x18000bee6  mov     [rsp+530h+bstrString], 0
0x18000beef  mov     r9d, 100h; cchBufferMax
0x18000bef5  lea     r8, [rbp+430h+Buffer]; lpBuffer
0x18000befc  mov     edx, 138Ah; uID
0x18000bf01  mov     rcx, cs:?hinstResDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000bf08  call    cs:__imp_LoadStringW
0x18000bf0e  test    eax, eax
0x18000bf10  jnz     loc_18000C03C
0x18000bf16  lea     rsi, qword_1800542E0
0x18000bf1d  mov     r14, rsi
0x18000bf20  test    r12, r12
0x18000bf23  jz      short loc_18000BF78
0x18000bf25  mov     r8d, 40h ; '@'; nMaxCount
0x18000bf2b  lea     rdx, [rsp+530h+ClassName]; lpClassName
0x18000bf30  mov     rcx, r12; hWnd
0x18000bf33  call    cs:__imp_GetClassNameW
0x18000bf39  lea     rcx, asc_180054300; "?"
0x18000bf40  lea     rdx, [rsp+530h+ClassName]
0x18000bf45  test    eax, eax
0x18000bf47  cmovnz  rcx, rdx
0x18000bf4b  mov     qword ptr [rsp+530h+fuFlags], rcx
0x18000bf50  mov     r9, r12
0x18000bf53  lea     r8, a0x08pS; "0x%08p (%s)"
0x18000bf5a  mov     edx, 80h; unsigned __int64
0x18000bf5f  lea     rcx, [rbp+430h+var_340]; unsigned __int16 *
0x18000bf66  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bf6b  lea     r14, [rbp+430h+var_340]
0x18000bf72  test    eax, eax
0x18000bf74  cmovs   r14, rsi
0x18000bf78  xor     ecx, ecx; struct IUnknown *
0x18000bf7a  call    ?GetProviderInfo@@YAPEAGPEAUIUnknown@@@Z; GetProviderInfo(IUnknown *)
0x18000bf7f  mov     rdi, rax
0x18000bf82  test    byte ptr cs:Microsoft_Windows_OLEACCEnableBits, 1
0x18000bf89  jnz     loc_18000C0C1
0x18000bf8f  test    rdi, rdi
0x18000bf92  jz      short loc_18000BF9E
0x18000bf94  mov     rcx, rdi; bstrString
0x18000bf97  call    cs:__imp_SysFreeString
0x18000bf9d  nop
0x18000bf9e  mov     rcx, [rsp+530h+bstrString]; bstrString
0x18000bfa3  test    rcx, rcx
0x18000bfa6  jz      short loc_18000BFB7
0x18000bfa8  call    cs:__imp_SysFreeString
0x18000bfae  mov     [rsp+530h+bstrString], 0
0x18000bfb7  lea     rsi, __ImageBase
0x18000bfbe  mov     r14, [rsp+530h+var_4D0]
0x18000bfc3  mov     edi, [rsp+530h+dwProcessId]
0x18000bfc7  jmp     loc_18000BD61
0x18000bfcc  add     rax, 0FFFFFFFFFFFF0000h
0x18000bfd2  cmp     rax, 1Fh
0x18000bfd6  ja      loc_18000BD7A
0x18000bfdc  mov     rcx, ds:rva off_180052380[rsi+rax*8]; lpString
0x18000bfe4  test    rcx, rcx
0x18000bfe7  jz      loc_18000BD7A
0x18000bfed  call    cs:__imp_GlobalFindAtomW
0x18000bff3  movzx   r8d, ax
0x18000bff7  test    ax, ax
0x18000bffa  jz      loc_18000C09F
0x18000c000  mov     edx, 2
0x18000c005  test    edi, edi
0x18000c007  mov     eax, 20h ; ' '
0x18000c00c  cmovz   edx, eax
0x18000c00f  xor     eax, eax
0x18000c011  cmp     eax, edx
0x18000c013  jge     loc_18000C09F
0x18000c019  movsxd  rcx, eax
0x18000c01c  cmp     rva ?rgAtomClasses@@3PAGA[rsi+rcx*2], r8w; ushort near * rgAtomClasses ...
0x18000c025  jz      short loc_18000C074
0x18000c027  inc     eax
0x18000c029  jmp     short loc_18000C011
0x18000c02b  mov     qword ptr [r14], 0
0x18000c032  mov     eax, 80004005h
0x18000c037  jmp     loc_18000BDBE
0x18000c03c  lea     rcx, [rbp+430h+Buffer]; psz
0x18000c043  call    cs:__imp_SysAllocString
0x18000c049  mov     [rsp+530h+bstrString], rax
0x18000c04e  jmp     loc_18000BF16
0x18000c053  mov     [rsp+530h+fuFlags], 138Ah; int
0x18000c05b  mov     r9, r12; HWND
0x18000c05e  mov     r8d, ebx; int
0x18000c061  lea     rdx, aOleaccLookupwi; "OleAcc: LookupWindowClass"
0x18000c068  xor     ecx, ecx; struct IUnknown *
0x18000c06a  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z; Error::IAccessibleError(IUnknown *,ushort const *,long,HWND__ *,int)
0x18000c06f  jmp     loc_18000BD7A
0x18000c074  lfence
0x18000c077  test    edi, edi
0x18000c079  jnz     short loc_18000C0A3
0x18000c07b  lea     rax, dword_180054260
0x18000c082  lea     rax, [rax+rcx*4]
0x18000c086  mov     r15d, [rax]
0x18000c089  xor     eax, eax
0x18000c08b  cmp     r15d, 0FFFFFFFFh
0x18000c08f  setnz   al
0x18000c092  test    eax, eax
0x18000c094  jnz     loc_18000BD87
0x18000c09a  jmp     loc_18000BD7A
0x18000c09f  xor     eax, eax
0x18000c0a1  jmp     short loc_18000C092
0x18000c0a3  lea     rax, ?g_WindowClassMap@@3PAW4CLASS_ENUM@@A; "#"
0x18000c0aa  jmp     short loc_18000C082
0x18000c0ac  mov     ebx, 80131505h
0x18000c0b1  jmp     loc_18000BEE6
0x18000c0b6  call    cs:__imp_GetClassNameW
0x18000c0bc  jmp     loc_18000BCAE
0x18000c0c1  mov     rdx, rsi
0x18000c0c4  test    rdi, rdi
0x18000c0c7  cmovnz  rdx, rdi
0x18000c0cb  mov     rcx, [rsp+530h+bstrString]
0x18000c0d0  test    rcx, rcx
0x18000c0d3  cmovnz  rsi, rcx
0x18000c0d7  mov     [rsp+530h+var_4F8], rdx
0x18000c0dc  mov     [rsp+530h+lpdwResult], r14
0x18000c0e1  mov     qword ptr [rsp+530h+uTimeout], rsi
0x18000c0e6  mov     [rsp+530h+fuFlags], ebx
0x18000c0ea  lea     r9, aSendmessagetim_0; "SendMessageTimeoutHelper"
0x18000c0f1  call    McTemplateMofU0zqzzz
0x18000c0f6  jmp     loc_18000BF8F
0x18000c0fb  mov     cs:dword_180061968, 2
0x18000c105  jmp     loc_18000BDFB
0x18000c10a  call    cs:__imp_GetLastError
0x18000c110  jmp     loc_18000C032
0x18000c115  call    cs:__imp_CloseHandle
0x18000c11b  jmp     loc_18000BEBF
0x18000c120  mov     r9, r14; void **
0x18000c123  mov     r8, [rsp+530h+var_4C8]; struct _GUID *
0x18000c128  mov     edx, [rsp+530h+var_4D8]; int
0x18000c12c  mov     rcx, r12; HWND
0x18000c12f  call    ?CreateRemoteProxy6432@@YAJPEAUHWND__@@JAEBU_GUID@@PEAPEAX@Z; CreateRemoteProxy6432(HWND__ *,long,_GUID const &,void * *)
0x18000c134  jmp     loc_18000BDBE
```

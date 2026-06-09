# CAsyncHttp::AsyncHttpThreadEntry(ulong *)

- ea: `0x1800a6330`
- end: `0x1800a673b`
- name: `?AsyncHttpThreadEntry@CAsyncHttp@@CAKPEAK@Z`
- size: `1035`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180012cd0`
- `0x1800a6330`
- `0x1800a6c88`
- `0x1800cb1a4`
- `0x1800cb1c8`
- `0x1800cc9ba`

## import_xrefs

- `MSOERT2!__imp_InternetReadIntoBSTR` at `0x1800a6607`
- `MSOERT2!__imp_InternetReadIntoBSTR` at `0x1800a6607`
- `KERNEL32!WaitForSingleObject` at `0x1800a64fa`
- `KERNEL32!WaitForSingleObject` at `0x1800a663c`
- `KERNEL32!WaitForSingleObject` at `0x1800a64fa`
- `KERNEL32!WaitForSingleObject` at `0x1800a663c`
- `KERNEL32!GetTickCount` at `0x1800a651a`
- `KERNEL32!GetTickCount` at `0x1800a656b`
- `KERNEL32!GetTickCount` at `0x1800a651a`
- `KERNEL32!GetTickCount` at `0x1800a656b`
- `KERNEL32!GetLastError` at `0x1800a64bb`
- `KERNEL32!GetLastError` at `0x1800a65b5`
- `KERNEL32!GetLastError` at `0x1800a64bb`
- `KERNEL32!GetLastError` at `0x1800a65b5`
- `KERNEL32!SetEvent` at `0x1800a6469`
- `KERNEL32!SetEvent` at `0x1800a6469`
- `KERNEL32!WaitForMultipleObjects` at `0x1800a6723`
- `KERNEL32!WaitForMultipleObjects` at `0x1800a6723`
- `USER32!PostMessageA` at `0x1800a64ed`
- `USER32!PostMessageA` at `0x1800a65e4`
- `USER32!PostMessageA` at `0x1800a65f9`
- `USER32!PostMessageA` at `0x1800a6623`
- `USER32!PostMessageA` at `0x1800a66f9`
- `USER32!PostMessageA` at `0x1800a64ed`
- `USER32!PostMessageA` at `0x1800a65e4`
- `USER32!PostMessageA` at `0x1800a65f9`
- `USER32!PostMessageA` at `0x1800a6623`
- `USER32!PostMessageA` at `0x1800a66f9`
- `ole32!CoInitialize` at `0x1800a6421`
- `ole32!CoInitialize` at `0x1800a6421`
- `ole32!CoUninitialize` at `0x1800a6729`
- `ole32!CoUninitialize` at `0x1800a6729`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a66c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a66c9`
- `WININET!HttpOpenRequestA` at `0x1800a64b2`
- `WININET!HttpOpenRequestA` at `0x1800a64b2`
- `WININET!HttpSendRequestA` at `0x1800a65ab`
- `WININET!HttpSendRequestA` at `0x1800a65ab`
- `WININET!InternetSetOptionA` at `0x1800a652f`
- `WININET!InternetSetOptionA` at `0x1800a6548`
- `WININET!InternetSetOptionA` at `0x1800a6561`
- `WININET!InternetSetOptionA` at `0x1800a652f`
- `WININET!InternetSetOptionA` at `0x1800a6548`
- `WININET!InternetSetOptionA` at `0x1800a6561`
- `WININET!InternetCloseHandle` at `0x1800a66b5`
- `WININET!InternetCloseHandle` at `0x1800a66b5`

## pseudocode

```c
void __fastcall __noreturn CAsyncHttp::AsyncHttpThreadEntry(LPVOID lpThreadParameter)
{
  const CHAR *v2; // rdi
  const CHAR *v3; // r15
  _BYTE *v4; // r12
  bool v5; // zf
  int v6; // esi
  int v7; // eax
  void *v8; // r14
  HRESULT v9; // r13d
  int v10; // ecx
  void *v11; // rcx
  void *v12; // r14
  int v13; // esi
  int v14; // ebx
  signed int v15; // edi
  HWND v16; // r15
  int v17; // r12d
  __int64 v18; // r8
  __int64 v19; // rax
  signed int v20; // eax
  void *v21; // rcx
  WPARAM v22; // r8
  BSTR v23; // r9
  DWORD Buffer; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+44h] [rbp-BCh]
  unsigned int LastError; // [rsp+48h] [rbp-B8h] BYREF
  HWND hWnd; // [rsp+50h] [rbp-B0h]
  BOOL v28; // [rsp+58h] [rbp-A8h]
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hHandle; // [rsp+68h] [rbp-98h]
  HINTERNET hConnect[2]; // [rsp+70h] [rbp-90h] BYREF
  void *v32; // [rsp+80h] [rbp-80h]
  _BYTE v33[8]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v34[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF

  CLoadLibrary_FreeLibraryAndExitThread_Pair::CLoadLibrary_FreeLibraryAndExitThread_Pair((CLoadLibrary_FreeLibraryAndExitThread_Pair *)v33);
  bstrString = 0;
  v35 = 0;
  Buffer = 0;
  memset(v34, 0, sizeof(v34));
  memset_0(v36, 0, sizeof(v36));
  hConnect[0] = *((HINTERNET *)lpThreadParameter + 4);
  if ( hConnect[0]
    && (hWnd = (HWND)*((_QWORD *)lpThreadParameter + 5)) != 0
    && (v2 = (const CHAR *)*((_QWORD *)lpThreadParameter + 6)) != 0
    && (v3 = (const CHAR *)*((_QWORD *)lpThreadParameter + 7)) != 0
    && (v4 = (_BYTE *)*((_QWORD *)lpThreadParameter + 8)) != 0
    && *((_QWORD *)lpThreadParameter + 1)
    && (v32 = (void *)*((_QWORD *)lpThreadParameter + 3)) != 0 )
  {
    v5 = *((_DWORD *)lpThreadParameter + 18) == 0;
    v6 = *((_DWORD *)lpThreadParameter + 19);
    hHandle = (HANDLE)*((_QWORD *)lpThreadParameter + 2);
    v7 = 60;
    if ( !v5 )
      v7 = *((_DWORD *)lpThreadParameter + 18);
    Buffer = 1000 * v7;
    if ( v6 )
      StringCchCopyA(v36, 0x400u, *((const char **)lpThreadParameter + 10));
    v8 = hConnect[0];
    v9 = CoInitialize(0);
    v10 = v9;
  }
  else
  {
    v9 = 0;
    hConnect[0] = 0;
    v8 = 0;
    hWnd = 0;
    v2 = 0;
    hHandle = 0;
    v3 = 0;
    v32 = 0;
    v4 = 0;
    v6 = 0;
    v10 = -2147024809;
  }
  *(_DWORD *)lpThreadParameter = v10;
  v11 = (void *)*((_QWORD *)lpThreadParameter + 1);
  if ( v11 )
    SetEvent(v11);
  if ( *(int *)lpThreadParameter < 0 )
LABEL_65:
    CLoadLibrary_FreeLibraryAndExitThread_Pair::ExitThread_DWORD((CLoadLibrary_FreeLibraryAndExitThread_Pair *)v33, 0);
  v25 = 0;
  v12 = HttpOpenRequestA(v8, "POST", v2, "HTTP/1.0", 0, 0, v6 != 0 ? 79692288 : 71303680, 0);
  LastError = GetLastError();
  v13 = 1;
  v14 = LastError;
  v15 = -2146644969;
  if ( v12 )
  {
    PostMessageA(hWnd, 0x401u, 5u, 5);
    if ( !WaitForSingleObject(hHandle, 0) )
    {
      v16 = hWnd;
      v17 = 1;
      v9 = -2146644969;
LABEL_38:
      if ( WaitForSingleObject(hHandle, 0) )
      {
        v13 = v17;
        v15 = v9;
        if ( !v17 )
        {
          if ( !bstrString )
          {
            if ( v9 < 0 )
            {
LABEL_51:
              v21 = hConnect[0];
              if ( v12 )
                v21 = v12;
              CAsyncHttp::FillErrorResult(v21, &LastError, (struct tagIXPRESULTW *)v34);
              v14 = LastError;
              goto LABEL_54;
            }
            if ( v14 > 0 )
              v20 = (unsigned __int16)v14 | 0x80070000;
            else
              v20 = v14;
            if ( v20 >= 0 )
              v14 = 232;
            LastError = v14;
            if ( v14 > 0 )
              v15 = (unsigned __int16)v14 | 0x80070000;
            else
              v15 = v14;
          }
          if ( v15 < 0 )
            goto LABEL_51;
        }
      }
LABEL_54:
      if ( v12 )
        InternetCloseHandle(v12);
      if ( v15 < 0 && bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( !v13 )
      {
        if ( v15 >= 0 )
        {
          v23 = bstrString;
          v22 = 0;
        }
        else
        {
          v22 = (unsigned int)v14;
          v23 = (BSTR)v34;
        }
        PostMessageA(v16, 0x402u, v22, (LPARAM)v23);
        hConnect[0] = v32;
        hConnect[1] = hHandle;
        WaitForMultipleObjects(2u, hConnect, 0, Buffer);
      }
      CoUninitialize();
      goto LABEL_65;
    }
    v28 = 0;
    GetTickCount();
    if ( InternetSetOptionA(v12, 2u, &Buffer, 4u)
      && InternetSetOptionA(v12, 5u, &Buffer, 4u)
      && InternetSetOptionA(v12, 6u, &Buffer, 4u) )
    {
      GetTickCount();
      v18 = -1;
      if ( v4 )
      {
        v19 = -1;
        do
          ++v19;
        while ( v4[v19] );
      }
      else
      {
        LODWORD(v19) = 0;
      }
      if ( v3 )
      {
        do
          ++v18;
        while ( v3[v18] );
      }
      else
      {
        LODWORD(v18) = 0;
      }
      v28 = HttpSendRequestA(v12, v3, v18, v4, v19);
    }
    v14 = GetLastError();
    v16 = hWnd;
    LastError = v14;
    if ( v28 )
    {
      PostMessageA(hWnd, 0x401u, 6u, 6);
      PostMessageA(v16, 0x401u, 7u, 7);
      v9 = InternetReadIntoBSTR(v12, &bstrString);
      if ( v9 >= 0 )
        PostMessageA(v16, 0x401u, 8u, 8);
    }
  }
  else
  {
    v16 = hWnd;
  }
  v17 = v25;
  goto LABEL_38;
}

```

## disassembly

```asm
0x1800a6330  push    rbp
0x1800a6332  push    rbx
0x1800a6333  push    rsi
0x1800a6334  push    rdi
0x1800a6335  push    r12
0x1800a6337  push    r13
0x1800a6339  push    r14
0x1800a633b  push    r15
0x1800a633d  lea     rbp, [rsp-3D8h]
0x1800a6345  sub     rsp, 4D8h
0x1800a634c  mov     rax, cs:__security_cookie
0x1800a6353  xor     rax, rsp
0x1800a6356  mov     [rbp+410h+var_50], rax
0x1800a635d  mov     rbx, rcx
0x1800a6360  lea     rcx, [rbp+410h+var_488]; this
0x1800a6364  call    ??0CLoadLibrary_FreeLibraryAndExitThread_Pair@@QEAA@XZ; CLoadLibrary_FreeLibraryAndExitThread_Pair::CLoadLibrary_FreeLibraryAndExitThread_Pair(void)
0x1800a6369  xorps   xmm0, xmm0
0x1800a636c  mov     [rsp+510h+bstrString], 0
0x1800a6375  xor     eax, eax
0x1800a6377  lea     rcx, [rbp+410h+var_450]; void *
0x1800a637b  mov     r13d, 400h
0x1800a6381  mov     [rbp+410h+var_460], rax
0x1800a6385  mov     r8d, r13d; Size
0x1800a6388  mov     [rsp+510h+Buffer], eax
0x1800a638c  xor     edx, edx; Val
0x1800a638e  movups  [rbp+410h+var_480], xmm0
0x1800a6392  movups  [rbp+410h+var_470], xmm0
0x1800a6396  call    memset_0
0x1800a639b  mov     rax, [rbx+20h]
0x1800a639f  xor     edx, edx
0x1800a63a1  mov     [rsp+510h+hConnect], rax
0x1800a63a6  test    rax, rax
0x1800a63a9  jz      loc_1800A6435
0x1800a63af  mov     r14, [rbx+28h]
0x1800a63b3  mov     [rsp+510h+hWnd], r14
0x1800a63b8  test    r14, r14
0x1800a63bb  jz      short loc_1800A6435
0x1800a63bd  mov     rdi, [rbx+30h]
0x1800a63c1  test    rdi, rdi
0x1800a63c4  jz      short loc_1800A6435
0x1800a63c6  mov     r15, [rbx+38h]
0x1800a63ca  test    r15, r15
0x1800a63cd  jz      short loc_1800A6435
0x1800a63cf  mov     r12, [rbx+40h]
0x1800a63d3  test    r12, r12
0x1800a63d6  jz      short loc_1800A6435
0x1800a63d8  cmp     [rbx+8], rdx
0x1800a63dc  jz      short loc_1800A6435
0x1800a63de  mov     rax, [rbx+18h]
0x1800a63e2  mov     [rbp+410h+var_490], rax
0x1800a63e6  test    rax, rax
0x1800a63e9  jz      short loc_1800A6435
0x1800a63eb  mov     rax, [rbx+10h]
0x1800a63ef  cmp     [rbx+48h], edx
0x1800a63f2  mov     esi, [rbx+4Ch]
0x1800a63f5  mov     [rsp+510h+hHandle], rax
0x1800a63fa  lea     eax, [rdx+3Ch]
0x1800a63fd  cmovnz  eax, [rbx+48h]
0x1800a6401  imul    eax, 3E8h
0x1800a6407  mov     [rsp+510h+Buffer], eax
0x1800a640b  test    esi, esi
0x1800a640d  jz      short loc_1800A641F
0x1800a640f  mov     r8, [rbx+50h]; char *
0x1800a6413  lea     rcx, [rbp+410h+var_450]; char *
0x1800a6417  mov     edx, r13d; unsigned __int64
0x1800a641a  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800a641f  xor     ecx, ecx; pvReserved
0x1800a6421  call    cs:__imp_CoInitialize
0x1800a6427  mov     r14, [rsp+510h+hConnect]
0x1800a642c  xor     edx, edx
0x1800a642e  mov     r13d, eax
0x1800a6431  mov     ecx, eax
0x1800a6433  jmp     short loc_1800A645E
0x1800a6435  mov     r13d, edx
0x1800a6438  mov     [rsp+510h+hConnect], rdx
0x1800a643d  mov     r14, rdx
0x1800a6440  mov     [rsp+510h+hWnd], rdx
0x1800a6445  mov     rdi, rdx
0x1800a6448  mov     [rsp+510h+hHandle], rdx
0x1800a644d  mov     r15, rdx
0x1800a6450  mov     [rbp+410h+var_490], rdx
0x1800a6454  mov     r12, rdx
0x1800a6457  mov     esi, edx
0x1800a6459  mov     ecx, 80070057h
0x1800a645e  mov     [rbx], ecx
0x1800a6460  mov     rcx, [rbx+8]; hEvent
0x1800a6464  test    rcx, rcx
0x1800a6467  jz      short loc_1800A6471
0x1800a6469  call    cs:__imp_SetEvent
0x1800a646f  xor     edx, edx
0x1800a6471  cmp     [rbx], edx
0x1800a6473  jl      loc_1800A672F
0x1800a6479  mov     [rsp+510h+dwContext], rdx; dwContext
0x1800a647e  lea     r9, szVersion; "HTTP/1.0"
0x1800a6485  mov     [rsp+510h+var_4CC], edx
0x1800a6489  neg     esi
0x1800a648b  mov     r8, rdi; lpszObjectName
0x1800a648e  mov     rcx, r14; hConnect
0x1800a6491  sbb     eax, eax
0x1800a6493  and     eax, 800000h
0x1800a6498  add     eax, 4400200h
0x1800a649d  mov     [rsp+510h+dwFlags], eax; dwFlags
0x1800a64a1  mov     [rsp+510h+lplpszAcceptTypes], rdx; lplpszAcceptTypes
0x1800a64a6  mov     [rsp+510h+lpszReferrer], rdx; lpszReferrer
0x1800a64ab  lea     rdx, aPost; "POST"
0x1800a64b2  call    cs:__imp_HttpOpenRequestA
0x1800a64b8  mov     r14, rax
0x1800a64bb  call    cs:__imp_GetLastError
0x1800a64c1  mov     [rsp+510h+var_4C8], eax
0x1800a64c5  mov     esi, 1
0x1800a64ca  mov     ebx, eax
0x1800a64cc  mov     edi, 800CCC17h
0x1800a64d1  test    r14, r14
0x1800a64d4  jz      loc_1800A662B
0x1800a64da  mov     rcx, [rsp+510h+hWnd]; hWnd
0x1800a64df  lea     eax, [rsi+4]
0x1800a64e2  mov     r9d, eax; lParam
0x1800a64e5  mov     r8d, eax; wParam
0x1800a64e8  mov     edx, 401h; Msg
0x1800a64ed  call    cs:__imp_PostMessageA
0x1800a64f3  mov     rcx, [rsp+510h+hHandle]; hHandle
0x1800a64f8  xor     edx, edx; dwMilliseconds
0x1800a64fa  call    cs:__imp_WaitForSingleObject
0x1800a6500  test    eax, eax
0x1800a6502  jnz     short loc_1800A6514
0x1800a6504  mov     r15, [rsp+510h+hWnd]
0x1800a6509  mov     r12d, esi
0x1800a650c  mov     r13d, edi
0x1800a650f  jmp     loc_1800A6635
0x1800a6514  xor     ebx, ebx
0x1800a6516  mov     [rsp+510h+var_4B8], ebx
0x1800a651a  call    cs:__imp_GetTickCount
0x1800a6520  lea     r9d, [rbx+4]; dwBufferLength
0x1800a6524  mov     rcx, r14; hInternet
0x1800a6527  lea     r8, [rsp+510h+Buffer]; lpBuffer
0x1800a652c  lea     edx, [rbx+2]; dwOption
0x1800a652f  call    cs:__imp_InternetSetOptionA
0x1800a6535  test    eax, eax
0x1800a6537  jz      short loc_1800A65B5
0x1800a6539  lea     r9d, [rbx+4]; dwBufferLength
0x1800a653d  mov     rcx, r14; hInternet
0x1800a6540  lea     r8, [rsp+510h+Buffer]; lpBuffer
0x1800a6545  lea     edx, [rbx+5]; dwOption
0x1800a6548  call    cs:__imp_InternetSetOptionA
0x1800a654e  test    eax, eax
0x1800a6550  jz      short loc_1800A65B5
0x1800a6552  lea     r9d, [rbx+4]; dwBufferLength
0x1800a6556  mov     rcx, r14; hInternet
0x1800a6559  lea     r8, [rsp+510h+Buffer]; lpBuffer
0x1800a655e  lea     edx, [rbx+6]; dwOption
0x1800a6561  call    cs:__imp_InternetSetOptionA
0x1800a6567  test    eax, eax
0x1800a6569  jz      short loc_1800A65B5
0x1800a656b  call    cs:__imp_GetTickCount
0x1800a6571  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a6575  test    r12, r12
0x1800a6578  jz      short loc_1800A6588
0x1800a657a  mov     rax, r8
0x1800a657d  inc     rax
0x1800a6580  cmp     [r12+rax], bl
0x1800a6584  jnz     short loc_1800A657D
0x1800a6586  jmp     short loc_1800A658B
0x1800a6588  mov     rax, rbx
0x1800a658b  test    r15, r15
0x1800a658e  jz      short loc_1800A659B
0x1800a6590  inc     r8
0x1800a6593  cmp     [r15+r8], bl
0x1800a6597  jnz     short loc_1800A6590
0x1800a6599  jmp     short loc_1800A659E
0x1800a659b  mov     r8, rbx; dwHeadersLength
0x1800a659e  mov     r9, r12; lpOptional
0x1800a65a1  mov     dword ptr [rsp+510h+lpszReferrer], eax; dwOptionalLength
0x1800a65a5  mov     rdx, r15; lpszHeaders
0x1800a65a8  mov     rcx, r14; hRequest
0x1800a65ab  call    cs:__imp_HttpSendRequestA
0x1800a65b1  mov     [rsp+510h+var_4B8], eax
0x1800a65b5  call    cs:__imp_GetLastError
0x1800a65bb  cmp     [rsp+510h+var_4B8], 0
0x1800a65c0  mov     ebx, eax
0x1800a65c2  mov     r15, [rsp+510h+hWnd]
0x1800a65c7  mov     [rsp+510h+var_4C8], eax
0x1800a65cb  jz      short loc_1800A6630
0x1800a65cd  mov     eax, 6
0x1800a65d2  mov     r12d, 401h
0x1800a65d8  mov     r9d, eax; lParam
0x1800a65db  mov     r8d, eax; wParam
0x1800a65de  mov     edx, r12d; Msg
0x1800a65e1  mov     rcx, r15; hWnd
0x1800a65e4  call    cs:__imp_PostMessageA
0x1800a65ea  mov     r8d, 7; wParam
0x1800a65f0  mov     edx, r12d; Msg
0x1800a65f3  mov     r9d, r8d; lParam
0x1800a65f6  mov     rcx, r15; hWnd
0x1800a65f9  call    cs:__imp_PostMessageA
0x1800a65ff  lea     rdx, [rsp+510h+bstrString]
0x1800a6604  mov     rcx, r14
0x1800a6607  call    cs:__imp_InternetReadIntoBSTR
0x1800a660d  mov     r13d, eax
0x1800a6610  test    eax, eax
0x1800a6612  js      short loc_1800A6630
0x1800a6614  mov     r8d, 8; wParam
0x1800a661a  mov     edx, r12d; Msg
0x1800a661d  mov     r9d, r8d; lParam
0x1800a6620  mov     rcx, r15; hWnd
0x1800a6623  call    cs:__imp_PostMessageA
0x1800a6629  jmp     short loc_1800A6630
0x1800a662b  mov     r15, [rsp+510h+hWnd]
0x1800a6630  mov     r12d, [rsp+510h+var_4CC]
0x1800a6635  mov     rcx, [rsp+510h+hHandle]; hHandle
0x1800a663a  xor     edx, edx; dwMilliseconds
0x1800a663c  call    cs:__imp_WaitForSingleObject
0x1800a6642  test    eax, eax
0x1800a6644  jz      short loc_1800A66AD
0x1800a6646  mov     esi, r12d
0x1800a6649  mov     edi, r13d
0x1800a664c  test    r12d, r12d
0x1800a664f  jnz     short loc_1800A66AD
0x1800a6651  cmp     [rsp+510h+bstrString], 0
0x1800a6657  jnz     short loc_1800A668B
0x1800a6659  test    r13d, r13d
0x1800a665c  js      short loc_1800A668F
0x1800a665e  mov     edx, 80070000h
0x1800a6663  test    ebx, ebx
0x1800a6665  jg      short loc_1800A666B
0x1800a6667  mov     eax, ebx
0x1800a6669  jmp     short loc_1800A6670
0x1800a666b  movzx   eax, bx
0x1800a666e  or      eax, edx
0x1800a6670  test    eax, eax
0x1800a6672  mov     ecx, 0E8h
0x1800a6677  cmovns  ebx, ecx
0x1800a667a  mov     [rsp+510h+var_4C8], ebx
0x1800a667e  test    ebx, ebx
0x1800a6680  jg      short loc_1800A6686
0x1800a6682  mov     edi, ebx
0x1800a6684  jmp     short loc_1800A668B
0x1800a6686  movzx   edi, bx
0x1800a6689  or      edi, edx
0x1800a668b  test    edi, edi
0x1800a668d  jns     short loc_1800A66AD
0x1800a668f  mov     rcx, [rsp+510h+hConnect]
0x1800a6694  lea     r8, [rbp+410h+var_480]; struct tagIXPRESULTW *
0x1800a6698  test    r14, r14
0x1800a669b  lea     rdx, [rsp+510h+var_4C8]; unsigned int *
0x1800a66a0  cmovnz  rcx, r14; hRequest
0x1800a66a4  call    ?FillErrorResult@CAsyncHttp@@CAXPEAXPEAKPEAUtagIXPRESULTW@@@Z; CAsyncHttp::FillErrorResult(void *,ulong *,tagIXPRESULTW *)
0x1800a66a9  mov     ebx, [rsp+510h+var_4C8]
0x1800a66ad  test    r14, r14
0x1800a66b0  jz      short loc_1800A66BB
0x1800a66b2  mov     rcx, r14; hInternet
0x1800a66b5  call    cs:__imp_InternetCloseHandle
0x1800a66bb  test    edi, edi
0x1800a66bd  jns     short loc_1800A66D8
0x1800a66bf  mov     rcx, [rsp+510h+bstrString]; bstrString
0x1800a66c4  test    rcx, rcx
0x1800a66c7  jz      short loc_1800A66D8
0x1800a66c9  call    cs:__imp_SysFreeString
0x1800a66cf  mov     [rsp+510h+bstrString], 0
0x1800a66d8  test    esi, esi
0x1800a66da  jnz     short loc_1800A6729
0x1800a66dc  test    edi, edi
0x1800a66de  jns     short loc_1800A66E9
0x1800a66e0  mov     r8d, ebx
0x1800a66e3  lea     r9, [rbp+410h+var_480]
0x1800a66e7  jmp     short loc_1800A66F1
0x1800a66e9  mov     r9, [rsp+510h+bstrString]; lParam
0x1800a66ee  xor     r8d, r8d; wParam
0x1800a66f1  mov     edx, 402h; Msg
0x1800a66f6  mov     rcx, r15; hWnd
0x1800a66f9  call    cs:__imp_PostMessageA
0x1800a66ff  mov     rax, [rbp+410h+var_490]
0x1800a6703  lea     rdx, [rsp+510h+hConnect]; lpHandles
0x1800a6708  mov     r9d, [rsp+510h+Buffer]; dwMilliseconds
0x1800a670d  xor     r8d, r8d; bWaitAll
0x1800a6710  mov     [rsp+510h+hConnect], rax
0x1800a6715  mov     rax, [rsp+510h+hHandle]
0x1800a671a  mov     [rsp+510h+var_498], rax
0x1800a671f  lea     ecx, [r8+2]; nCount
0x1800a6723  call    cs:__imp_WaitForMultipleObjects
0x1800a6729  call    cs:__imp_CoUninitialize
0x1800a672f  xor     edx, edx; unsigned int
0x1800a6731  lea     rcx, [rbp+410h+var_488]; this
0x1800a6735  call    ?ExitThread_DWORD@CLoadLibrary_FreeLibraryAndExitThread_Pair@@QEAAXK@Z; CLoadLibrary_FreeLibraryAndExitThread_Pair::ExitThread_DWORD(ulong)
```

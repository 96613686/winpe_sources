# CCancelRpc::Init(void)

- ea: `0x180015ad0`
- end: `0x180015f8a`
- name: `?Init@CCancelRpc@@QEAAXXZ`
- size: `1210`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004330`

## callees

- `0x180003426`
- `0x1800049ac`
- `0x18000b95c`
- `0x18000c39c`
- `0x18000ca5c`
- `0x18000d650`
- `0x1800159a0`
- `0x180015ad0`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x180015efd`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180015efd`
- `KERNEL32!CloseHandle` at `0x180015b8b`
- `KERNEL32!CloseHandle` at `0x180015b8b`
- `KERNEL32!SetEvent` at `0x180015ef2`
- `KERNEL32!SetEvent` at `0x180015ef2`
- `KERNEL32!CreateThread` at `0x180015e1c`
- `KERNEL32!CreateThread` at `0x180015e1c`
- `KERNEL32!ResetEvent` at `0x180015c94`
- `KERNEL32!ResetEvent` at `0x180015c94`
- `KERNEL32!CreateEventW` at `0x180015ba2`
- `KERNEL32!CreateEventW` at `0x180015c20`
- `KERNEL32!CreateEventW` at `0x180015d11`
- `KERNEL32!CreateEventW` at `0x180015ba2`
- `KERNEL32!CreateEventW` at `0x180015c20`
- `KERNEL32!CreateEventW` at `0x180015d11`
- `KERNEL32!FreeLibrary` at `0x180015e3a`
- `KERNEL32!FreeLibrary` at `0x180015e3a`
- `KERNEL32!LeaveCriticalSection` at `0x180015afa`
- `KERNEL32!LeaveCriticalSection` at `0x180015f20`
- `KERNEL32!LeaveCriticalSection` at `0x180015afa`
- `KERNEL32!LeaveCriticalSection` at `0x180015f20`
- `KERNEL32!WaitForSingleObject` at `0x180015b19`
- `KERNEL32!WaitForSingleObject` at `0x180015ead`
- `KERNEL32!WaitForSingleObject` at `0x180015b19`
- `KERNEL32!WaitForSingleObject` at `0x180015ead`
- `KERNEL32!GetLastError` at `0x180015b23`
- `KERNEL32!GetLastError` at `0x180015bb1`
- `KERNEL32!GetLastError` at `0x180015c2f`
- `KERNEL32!GetLastError` at `0x180015c9e`
- `KERNEL32!GetLastError` at `0x180015d20`
- `KERNEL32!GetLastError` at `0x180015e2b`
- `KERNEL32!GetLastError` at `0x180015b23`
- `KERNEL32!GetLastError` at `0x180015bb1`
- `KERNEL32!GetLastError` at `0x180015c2f`
- `KERNEL32!GetLastError` at `0x180015c9e`
- `KERNEL32!GetLastError` at `0x180015d20`
- `KERNEL32!GetLastError` at `0x180015e2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CCancelRpc::Init(CCriticalSection *lpCriticalSection)
{
  HANDLE v2; // rcx
  DWORD LastError; // eax
  unsigned int v4; // ebx
  HANDLE v5; // rcx
  HANDLE EventW; // rax
  DWORD v7; // eax
  unsigned int v8; // ebx
  HANDLE v9; // rax
  DWORD v10; // eax
  unsigned int v11; // ebx
  DWORD v12; // eax
  unsigned int v13; // ebx
  HANDLE v14; // rax
  DWORD v15; // eax
  unsigned int v16; // ebx
  LONG v17; // eax
  HANDLE v18; // rax
  DWORD v19; // edi
  DWORD v20; // eax
  DWORD ThreadId; // [rsp+30h] [rbp-128h] BYREF
  CCriticalSection *v22; // [rsp+38h] [rbp-120h]
  _BYTE v23[24]; // [rsp+40h] [rbp-118h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+58h] [rbp-100h] BYREF
  _BYTE v25[32]; // [rsp+78h] [rbp-E0h] BYREF
  _BYTE v26[32]; // [rsp+98h] [rbp-C0h] BYREF
  _BYTE v27[32]; // [rsp+B8h] [rbp-A0h] BYREF
  _BYTE v28[32]; // [rsp+D8h] [rbp-80h] BYREF
  _BYTE v29[32]; // [rsp+F8h] [rbp-60h] BYREF
  _BYTE v30[64]; // [rsp+118h] [rbp-40h] BYREF
  _BYTE v32[8]; // [rsp+168h] [rbp+10h] BYREF
  unsigned int v33; // [rsp+170h] [rbp+18h] BYREF
  unsigned int v34; // [rsp+178h] [rbp+20h] BYREF

  v22 = lpCriticalSection;
  CCriticalSection::Lock(lpCriticalSection);
  if ( (int)++*((_DWORD *)lpCriticalSection + 31) <= 1 )
  {
    try
    {
      v2 = (HANDLE)*((_QWORD *)lpCriticalSection + 13);
      if ( v2 )
      {
        if ( WaitForSingleObject(v2, 0xFFFFFFFF) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 22),
              12,
              WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids,
              LastError);
          bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v4);
          throw (bad_win32_error *)pExceptionObject;
        }
        v5 = (HANDLE)*((_QWORD *)lpCriticalSection + 13);
        *((_QWORD *)lpCriticalSection + 13) = 0;
        CloseHandle(v5);
      }
      if ( !*((_QWORD *)lpCriticalSection + 11) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)lpCriticalSection + 11) = EventW;
        if ( !EventW )
        {
          v7 = GetLastError();
          v8 = v7;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 13, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids, v7);
          bad_win32_error::bad_win32_error((bad_win32_error *)v25, v8);
          throw (bad_win32_error *)v25;
        }
      }
      v9 = (HANDLE)*((_QWORD *)lpCriticalSection + 12);
      if ( !v9 )
      {
        v9 = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)lpCriticalSection + 12) = v9;
        if ( !v9 )
        {
          v10 = GetLastError();
          v11 = v10;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 14, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids, v10);
          bad_win32_error::bad_win32_error((bad_win32_error *)v26, v11);
          throw (bad_win32_error *)v26;
        }
      }
      if ( !ResetEvent(v9) )
      {
        v12 = GetLastError();
        v13 = v12;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 15, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids, v12);
        bad_win32_error::bad_win32_error((bad_win32_error *)v27, v13);
        throw (bad_win32_error *)v27;
      }
      if ( !*((_QWORD *)lpCriticalSection + 14) )
      {
        v14 = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)lpCriticalSection + 14) = v14;
        if ( !v14 )
        {
          v15 = GetLastError();
          v16 = v15;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 16, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids, v15);
          bad_win32_error::bad_win32_error((bad_win32_error *)v28, v16);
          throw (bad_win32_error *)v28;
        }
      }
      wcscpy((wchar_t *)v32, L"\x05");
      v33 = 4;
      v34 = 4;
      *((_DWORD *)lpCriticalSection + 32) = 5;
      GetFalconKeyValue(L"RpcCancelTimeout", &v34, (char *)lpCriticalSection + 128, &v33, (const wchar_t *)v32);
      v17 = *((_DWORD *)lpCriticalSection + 32);
      if ( !v17 )
        v17 = 5;
      *((_DWORD *)lpCriticalSection + 32) = 60000 * v17;
      *((_QWORD *)lpCriticalSection + 17) = GetLibraryReference();
      ThreadId = 0;
      v18 = CreateThread(0, 0, CCancelRpc::CancelThread, lpCriticalSection, 0, &ThreadId);
      *((_QWORD *)lpCriticalSection + 13) = v18;
      if ( !v18 )
      {
        v19 = GetLastError();
        FreeLibrary(*((HMODULE *)lpCriticalSection + 17));
        *((_QWORD *)lpCriticalSection + 17) = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 17, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids, v19);
        bad_win32_error::bad_win32_error((bad_win32_error *)v29, v19);
        throw (bad_win32_error *)v29;
      }
      v20 = WaitForSingleObject(*((HANDLE *)lpCriticalSection + 14), 0x2710u);
      if ( v20 == 258 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 18, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids);
        SetEvent(*((HANDLE *)lpCriticalSection + 12));
        exception::exception((exception *)v23);
        throw (exception *)v23;
      }
      if ( v20 || *((int *)lpCriticalSection + 30) < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            19,
            WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids,
            *((unsigned int *)lpCriticalSection + 30));
        bad_win32_error::bad_win32_error((bad_win32_error *)v30, *((_DWORD *)lpCriticalSection + 30));
        throw (bad_hresult *)v30;
      }
    }
    catch ( exception )
    {
      --*((_DWORD *)lpCriticalSection + 31);
      throw;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  }
}

```

## disassembly

```asm
0x180015ad0  mov     [rsp+arg_0], rcx
0x180015ad5  push    rbx
0x180015ad6  push    rdi
0x180015ad7  push    r15
0x180015ad9  sub     rsp, 140h
0x180015ae0  mov     rbx, rcx
0x180015ae3  mov     [rsp+158h+var_120], rcx
0x180015ae8  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180015aed  nop
0x180015aee  inc     dword ptr [rbx+7Ch]
0x180015af1  cmp     dword ptr [rbx+7Ch], 1
0x180015af5  jle     short loc_180015B0D
0x180015af7  mov     rcx, rbx; lpCriticalSection
0x180015afa  call    cs:__imp_LeaveCriticalSection
0x180015b00  nop
0x180015b01  add     rsp, 140h
0x180015b08  pop     r15
0x180015b0a  pop     rdi
0x180015b0b  pop     rbx
0x180015b0c  retn
0x180015b0d  mov     rcx, [rbx+68h]; hHandle
0x180015b11  test    rcx, rcx
0x180015b14  jz      short loc_180015B91
0x180015b16  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180015b19  call    cs:__imp_WaitForSingleObject
0x180015b1f  test    eax, eax
0x180015b21  jz      short loc_180015B7F
0x180015b23  call    cs:__imp_GetLastError
0x180015b29  mov     ebx, eax
0x180015b2b  lea     rdx, WPP_GLOBAL_Control
0x180015b32  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b39  cmp     rcx, rdx
0x180015b3c  jz      short loc_180015B62
0x180015b3e  test    byte ptr [rcx+0BCh], 1
0x180015b45  jz      short loc_180015B62
0x180015b47  mov     edx, 0Ch
0x180015b4c  mov     r9d, eax
0x180015b4f  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015b56  mov     rcx, [rcx+0B0h]
0x180015b5d  call    WPP_SF_d
0x180015b62  mov     edx, ebx; unsigned int
0x180015b64  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180015b69  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180015b6e  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180015b75  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180015b7a  call    _CxxThrowException_0
0x180015b7f  mov     rcx, [rbx+68h]; hObject
0x180015b83  mov     qword ptr [rbx+68h], 0
0x180015b8b  call    cs:__imp_CloseHandle
0x180015b91  cmp     qword ptr [rbx+58h], 0
0x180015b96  jnz     short loc_180015C0D
0x180015b98  xor     r9d, r9d; lpName
0x180015b9b  xor     r8d, r8d; bInitialState
0x180015b9e  xor     edx, edx; bManualReset
0x180015ba0  xor     ecx, ecx; lpEventAttributes
0x180015ba2  call    cs:__imp_CreateEventW
0x180015ba8  mov     [rbx+58h], rax
0x180015bac  test    rax, rax
0x180015baf  jnz     short loc_180015C0D
0x180015bb1  call    cs:__imp_GetLastError
0x180015bb7  mov     ebx, eax
0x180015bb9  lea     rdx, WPP_GLOBAL_Control
0x180015bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bc7  cmp     rcx, rdx
0x180015bca  jz      short loc_180015BF0
0x180015bcc  test    byte ptr [rcx+0BCh], 1
0x180015bd3  jz      short loc_180015BF0
0x180015bd5  mov     edx, 0Dh
0x180015bda  mov     r9d, eax
0x180015bdd  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015be4  mov     rcx, [rcx+0B0h]
0x180015beb  call    WPP_SF_d
0x180015bf0  mov     edx, ebx; unsigned int
0x180015bf2  lea     rcx, [rsp+158h+var_E0]; this
0x180015bf7  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180015bfc  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180015c03  lea     rcx, [rsp+158h+var_E0]; pExceptionObject
0x180015c08  call    _CxxThrowException_0
0x180015c0d  mov     rax, [rbx+60h]
0x180015c11  test    rax, rax
0x180015c14  jnz     short loc_180015C91
0x180015c16  xor     r9d, r9d; lpName
0x180015c19  xor     r8d, r8d; bInitialState
0x180015c1c  xor     edx, edx; bManualReset
0x180015c1e  xor     ecx, ecx; lpEventAttributes
0x180015c20  call    cs:__imp_CreateEventW
0x180015c26  mov     [rbx+60h], rax
0x180015c2a  test    rax, rax
0x180015c2d  jnz     short loc_180015C91
0x180015c2f  call    cs:__imp_GetLastError
0x180015c35  mov     ebx, eax
0x180015c37  lea     rdx, WPP_GLOBAL_Control
0x180015c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c45  cmp     rcx, rdx
0x180015c48  jz      short loc_180015C6E
0x180015c4a  test    byte ptr [rcx+0BCh], 1
0x180015c51  jz      short loc_180015C6E
0x180015c53  mov     edx, 0Eh
0x180015c58  mov     r9d, eax
0x180015c5b  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015c62  mov     rcx, [rcx+0B0h]
0x180015c69  call    WPP_SF_d
0x180015c6e  mov     edx, ebx; unsigned int
0x180015c70  lea     rcx, [rsp+158h+var_C0]; this
0x180015c78  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180015c7d  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180015c84  lea     rcx, [rsp+158h+var_C0]; pExceptionObject
0x180015c8c  call    _CxxThrowException_0
0x180015c91  mov     rcx, rax; hEvent
0x180015c94  call    cs:__imp_ResetEvent
0x180015c9a  test    eax, eax
0x180015c9c  jnz     short loc_180015D00
0x180015c9e  call    cs:__imp_GetLastError
0x180015ca4  mov     ebx, eax
0x180015ca6  lea     rdx, WPP_GLOBAL_Control
0x180015cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180015cb4  cmp     rcx, rdx
0x180015cb7  jz      short loc_180015CDD
0x180015cb9  test    byte ptr [rcx+0BCh], 1
0x180015cc0  jz      short loc_180015CDD
0x180015cc2  mov     edx, 0Fh
0x180015cc7  mov     r9d, eax
0x180015cca  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015cd1  mov     rcx, [rcx+0B0h]
0x180015cd8  call    WPP_SF_d
0x180015cdd  mov     edx, ebx; unsigned int
0x180015cdf  lea     rcx, [rsp+158h+var_A0]; this
0x180015ce7  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180015cec  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180015cf3  lea     rcx, [rsp+158h+var_A0]; pExceptionObject
0x180015cfb  call    _CxxThrowException_0
0x180015d00  cmp     qword ptr [rbx+70h], 0
0x180015d05  jnz     short loc_180015D82
0x180015d07  xor     r9d, r9d; lpName
0x180015d0a  xor     r8d, r8d; bInitialState
0x180015d0d  xor     edx, edx; bManualReset
0x180015d0f  xor     ecx, ecx; lpEventAttributes
0x180015d11  call    cs:__imp_CreateEventW
0x180015d17  mov     [rbx+70h], rax
0x180015d1b  test    rax, rax
0x180015d1e  jnz     short loc_180015D82
0x180015d20  call    cs:__imp_GetLastError
0x180015d26  mov     ebx, eax
0x180015d28  lea     rdx, WPP_GLOBAL_Control
0x180015d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d36  cmp     rcx, rdx
0x180015d39  jz      short loc_180015D5F
0x180015d3b  test    byte ptr [rcx+0BCh], 1
0x180015d42  jz      short loc_180015D5F
0x180015d44  mov     edx, 10h
0x180015d49  mov     r9d, eax
0x180015d4c  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015d53  mov     rcx, [rcx+0B0h]
0x180015d5a  call    WPP_SF_d
0x180015d5f  mov     edx, ebx; unsigned int
0x180015d61  lea     rcx, [rsp+158h+var_80]; this
0x180015d69  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180015d6e  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180015d75  lea     rcx, [rsp+158h+var_80]; pExceptionObject
0x180015d7d  call    _CxxThrowException_0
0x180015d82  mov     r15d, 5
0x180015d88  mov     dword ptr [rsp+158h+arg_8], r15d
0x180015d90  lea     eax, [r15-1]
0x180015d94  mov     [rsp+158h+arg_10], eax
0x180015d9b  mov     [rsp+158h+arg_18], eax
0x180015da2  lea     rdi, [rbx+80h]
0x180015da9  mov     [rdi], r15d
0x180015dac  lea     rax, [rsp+158h+arg_8]
0x180015db4  mov     qword ptr [rsp+158h+dwCreationFlags], rax; wchar_t *
0x180015db9  lea     r9, [rsp+158h+arg_10]; unsigned int *
0x180015dc1  mov     r8, rdi; void *
0x180015dc4  lea     rdx, [rsp+158h+arg_18]; unsigned int *
0x180015dcc  lea     rcx, aRpccanceltimeo_0; "RpcCancelTimeout"
0x180015dd3  call    ?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180015dd8  mov     eax, [rdi]
0x180015dda  test    eax, eax
0x180015ddc  cmovz   eax, r15d
0x180015de0  imul    eax, 0EA60h
0x180015de6  mov     [rdi], eax
0x180015de8  call    ?GetLibraryReference@@YAPEAUHINSTANCE__@@XZ; GetLibraryReference(void)
0x180015ded  mov     [rbx+88h], rax
0x180015df4  mov     [rsp+158h+ThreadId], 0
0x180015dfc  lea     rax, [rsp+158h+ThreadId]
0x180015e01  mov     [rsp+158h+lpThreadId], rax; lpThreadId
0x180015e06  mov     [rsp+158h+dwCreationFlags], 0; dwCreationFlags
0x180015e0e  mov     r9, rbx; lpParameter
0x180015e11  lea     r8, ?CancelThread@CCancelRpc@@CAKPEAX@Z; lpStartAddress
0x180015e18  xor     edx, edx; dwStackSize
0x180015e1a  xor     ecx, ecx; lpThreadAttributes
0x180015e1c  call    cs:__imp_CreateThread
0x180015e22  mov     [rbx+68h], rax
0x180015e26  test    rax, rax
0x180015e29  jnz     short loc_180015EA4
0x180015e2b  call    cs:__imp_GetLastError
0x180015e31  mov     edi, eax
0x180015e33  mov     rcx, [rbx+88h]; hLibModule
0x180015e3a  call    cs:__imp_FreeLibrary
0x180015e40  mov     qword ptr [rbx+88h], 0
0x180015e4b  lea     rdx, WPP_GLOBAL_Control
0x180015e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e59  cmp     rcx, rdx
0x180015e5c  jz      short loc_180015E81
0x180015e5e  test    byte ptr [rcx+0BCh], 1
0x180015e65  jz      short loc_180015E81
0x180015e67  lea     edx, [r15+0Ch]
0x180015e6b  mov     r9d, edi
0x180015e6e  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015e75  mov     rcx, [rcx+0B0h]
0x180015e7c  call    WPP_SF_d
0x180015e81  mov     edx, edi; unsigned int
0x180015e83  lea     rcx, [rsp+158h+var_60]; this
0x180015e8b  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180015e90  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180015e97  lea     rcx, [rsp+158h+var_60]; pExceptionObject
0x180015e9f  call    _CxxThrowException_0
0x180015ea4  mov     edx, 2710h; dwMilliseconds
0x180015ea9  mov     rcx, [rbx+70h]; hHandle
0x180015ead  call    cs:__imp_WaitForSingleObject
0x180015eb3  cmp     eax, 102h
0x180015eb8  jnz     short loc_180015F14
0x180015eba  lea     rdx, WPP_GLOBAL_Control
0x180015ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ec8  cmp     rcx, rdx
0x180015ecb  jz      short loc_180015EEE
0x180015ecd  test    byte ptr [rcx+0BCh], 1
0x180015ed4  jz      short loc_180015EEE
0x180015ed6  mov     edx, 12h
0x180015edb  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015ee2  mov     rcx, [rcx+0B0h]
0x180015ee9  call    WPP_SF_
0x180015eee  mov     rcx, [rbx+60h]; hEvent
0x180015ef2  call    cs:__imp_SetEvent
0x180015ef8  lea     rcx, [rsp+158h+var_118]
0x180015efd  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180015f03  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180015f0a  lea     rcx, [rsp+158h+var_118]; pExceptionObject
0x180015f0f  call    _CxxThrowException_0
0x180015f14  test    eax, eax
0x180015f16  jnz     short loc_180015F2C
0x180015f18  cmp     [rbx+78h], eax
0x180015f1b  jl      short loc_180015F2C
0x180015f1d  mov     rcx, rbx; lpCriticalSection
0x180015f20  call    cs:__imp_LeaveCriticalSection
0x180015f26  nop
0x180015f27  jmp     loc_180015B01
0x180015f2c  lea     rdx, WPP_GLOBAL_Control
0x180015f33  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f3a  cmp     rcx, rdx
0x180015f3d  jz      short loc_180015F64
0x180015f3f  test    byte ptr [rcx+0BCh], 1
0x180015f46  jz      short loc_180015F64
0x180015f48  mov     edx, 13h
0x180015f4d  mov     r9d, [rbx+78h]
0x180015f51  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015f58  mov     rcx, [rcx+0B0h]
0x180015f5f  call    WPP_SF_d
0x180015f64  mov     edx, [rbx+78h]; unsigned int
0x180015f67  lea     rcx, [rsp+158h+var_40]; this
0x180015f6f  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180015f74  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180015f7b  lea     rcx, [rsp+158h+var_40]; pExceptionObject
0x180015f83  call    _CxxThrowException_0
```

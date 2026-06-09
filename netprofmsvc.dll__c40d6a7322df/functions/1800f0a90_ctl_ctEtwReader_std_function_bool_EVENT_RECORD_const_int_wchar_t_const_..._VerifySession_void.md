# ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::VerifySession(void)

- ea: `0x1800f0a90`
- end: `0x1800f0c80`
- name: `?VerifySession@?$ctEtwReader@V?$function@$$A6A_NPEBU_EVENT_RECORD@@@Z@std@@P6AHPEB_WZZ@ctl@@AEAAXXZ`
- size: `496`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18009bb90`
- `0x1800eb9c4`

## callees

- `0x18008e7a8`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800a9744`
- `0x1800ea3a0`
- `0x1800ea964`
- `0x1800f0a90`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f0add`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f0add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0b66`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800f0b3e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800f0b3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f0bef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f0bef`

## string_xrefs

- `0x1800f0b88`: `ctEtwReader`
- `0x1800f0b4b`: `	ctEtwReader::VerifySession - the ProcessTrace worker thread exited with error 0x%x\n`
- `0x1800f0b70`: `	ctEtwReader::VerifySession - the ProcessTrace worker thread exited, but GetExitCodeThread failed with error 0x%x\n`
- `0x1800f0b7f`: `GetExitCodeThread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::VerifySession(
        __int64 a1)
{
  void *v2; // rcx
  const wchar_t *v3; // r8
  DWORD v4; // edx
  __int64 LastError; // rbx
  __int64 v6; // rax
  bool v7; // [rsp+20h] [rbp-69h]
  void **pExceptionObject; // [rsp+30h] [rbp-59h] BYREF
  __int128 v9; // [rsp+38h] [rbp-51h]
  __int64 v10; // [rsp+48h] [rbp-41h]
  __int128 v11; // [rsp+50h] [rbp-39h]
  __int64 v12; // [rsp+60h] [rbp-29h]
  int v13; // [rsp+68h] [rbp-21h]
  __int16 v14; // [rsp+6Ch] [rbp-1Dh]
  char v15; // [rsp+6Eh] [rbp-1Bh]
  DWORD ExitCode[4]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v17[3]; // [rsp+80h] [rbp-9h] BYREF
  __int64 v18; // [rsp+98h] [rbp+Fh]
  __int128 v19; // [rsp+A0h] [rbp+17h]
  __int64 v20; // [rsp+B0h] [rbp+27h]
  int v21; // [rsp+B8h] [rbp+2Fh]
  __int16 v22; // [rsp+BCh] [rbp+33h]
  char v23; // [rsp+BEh] [rbp+35h]

  if ( *(_QWORD *)(a1 + 168) != -1 )
  {
    v2 = *(void **)(a1 + 176);
    if ( v2 )
    {
      if ( !WaitForSingleObject(v2, 0) )
      {
        ExitCode[0] = 0;
        memset_0(v17, 0, 0x40u);
        std::exception::exception((std::exception *)v17, (const char *const)&Src);
        v17[0] = &ctl::ctException::`vftable';
        v18 = 0;
        v19 = 0;
        v20 = 0;
        v21 = 0;
        v22 = 0;
        v23 = 0;
        if ( GetExitCodeThread(*(HANDLE *)(a1 + 176), ExitCode) )
        {
          (*(void (**)(const wchar_t *, ...))a1)(
            L"\tctEtwReader::VerifySession - the ProcessTrace worker thread exited with error 0x%x\n",
            ExitCode[0]);
          v3 = L"ProcessTrace";
          v4 = ExitCode[0];
        }
        else
        {
          LastError = GetLastError();
          (*(void (**)(const wchar_t *, ...))a1)(
            L"\tctEtwReader::VerifySession - the ProcessTrace worker thread exited, but GetExitCodeThread failed with error 0x%x\n",
            LastError);
          v3 = L"GetExitCodeThread";
          v4 = LastError;
        }
        v6 = ctl::ctException::ctException((ctl::ctException *)&pExceptionObject, v4, v3, L"ctEtwReader", v7);
        v18 = *(_QWORD *)(v6 + 24);
        v19 = *(_OWORD *)(v6 + 32);
        v20 = *(_QWORD *)(v6 + 48);
        v21 = *(_DWORD *)(v6 + 56);
        v22 = *(_WORD *)(v6 + 60);
        v23 = *(_BYTE *)(v6 + 62);
        *(_WORD *)(v6 + 60) = 0;
        *(_BYTE *)(v6 + 62) = 0;
        *(_QWORD *)(v6 + 48) = 0;
        ctl::ctException::~ctException((ctl::ctException *)&pExceptionObject);
        CloseHandle(*(HANDLE *)(a1 + 176));
        *(_QWORD *)(a1 + 176) = 0;
        v9 = 0;
        pExceptionObject = &ctl::ctException::`vftable';
        v10 = v18;
        v11 = v19;
        v12 = v20;
        v13 = v21;
        v14 = v22;
        v15 = v23;
        v22 = 0;
        v23 = 0;
        v20 = 0;
        throw (ctl::ctException *)&pExceptionObject;
      }
    }
  }
}

```

## disassembly

```asm
0x1800f0a90  mov     [rsp-8+arg_8], rbx
0x1800f0a95  mov     [rsp-8+arg_10], rsi
0x1800f0a9a  push    rbp
0x1800f0a9b  push    rdi
0x1800f0a9c  push    r14
0x1800f0a9e  lea     rbp, [rsp-47h]
0x1800f0aa3  sub     rsp, 0D0h
0x1800f0aaa  mov     rax, cs:__security_cookie
0x1800f0ab1  xor     rax, rsp
0x1800f0ab4  mov     [rbp+57h+var_20], rax
0x1800f0ab8  mov     rdi, rcx
0x1800f0abb  cmp     qword ptr [rcx+0A8h], 0FFFFFFFFFFFFFFFFh
0x1800f0ac3  jz      loc_1800F0C5C
0x1800f0ac9  mov     rcx, [rcx+0B0h]; hHandle
0x1800f0ad0  xor     esi, esi
0x1800f0ad2  test    rcx, rcx
0x1800f0ad5  jz      loc_1800F0C5C
0x1800f0adb  xor     edx, edx; dwMilliseconds
0x1800f0add  call    cs:__imp_WaitForSingleObject
0x1800f0ae3  test    eax, eax
0x1800f0ae5  jnz     loc_1800F0C5C
0x1800f0aeb  mov     [rbp+57h+ExitCode], esi
0x1800f0aee  xor     edx, edx; Val
0x1800f0af0  lea     r8d, [rsi+40h]; Size
0x1800f0af4  lea     rcx, [rbp+57h+var_60]; void *
0x1800f0af8  call    memset_0
0x1800f0afd  lea     rdx, Src; char *
0x1800f0b04  lea     rcx, [rbp+57h+var_60]; this
0x1800f0b08  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x1800f0b0d  lea     r14, ??_7ctException@ctl@@6B@; const ctl::ctException::`vftable'
0x1800f0b14  mov     [rbp+57h+var_60], r14
0x1800f0b18  mov     [rbp+57h+var_48], rsi
0x1800f0b1c  xorps   xmm0, xmm0
0x1800f0b1f  movdqa  [rbp+57h+var_40], xmm0
0x1800f0b24  mov     [rbp+57h+var_30], rsi
0x1800f0b28  mov     [rbp+57h+var_28], esi
0x1800f0b2b  mov     [rbp+57h+var_24], si
0x1800f0b2f  mov     [rbp+57h+var_22], sil
0x1800f0b33  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x1800f0b37  mov     rcx, [rdi+0B0h]; hThread
0x1800f0b3e  call    cs:__imp_GetExitCodeThread
0x1800f0b44  test    eax, eax
0x1800f0b46  jz      short loc_1800F0B66
0x1800f0b48  mov     edx, [rbp+57h+ExitCode]
0x1800f0b4b  lea     rcx, aCtetwreaderVer; "\tctEtwReader::VerifySession - the Proc"...
0x1800f0b52  mov     rax, [rdi]
0x1800f0b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0b5a  lea     r8, aProcesstrace_0; "ProcessTrace"
0x1800f0b61  mov     edx, [rbp+57h+ExitCode]
0x1800f0b64  jmp     short loc_1800F0B88
0x1800f0b66  call    cs:__imp_GetLastError
0x1800f0b6c  mov     ebx, eax
0x1800f0b6e  mov     edx, eax
0x1800f0b70  lea     rcx, aCtetwreaderVer_0; "\tctEtwReader::VerifySession - the Proc"...
0x1800f0b77  mov     rax, [rdi]
0x1800f0b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0b7f  lea     r8, aGetexitcodethr; "GetExitCodeThread"
0x1800f0b86  mov     edx, ebx; unsigned int
0x1800f0b88  lea     r9, aCtetwreader; "ctEtwReader"
0x1800f0b8f  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f0b93  call    ??0ctException@ctl@@QEAA@KPEB_W0_N@Z; ctl::ctException::ctException(ulong,wchar_t const *,wchar_t const *,bool)
0x1800f0b98  mov     rcx, [rax+18h]
0x1800f0b9c  mov     [rbp+57h+var_48], rcx
0x1800f0ba0  mov     rcx, [rax+20h]
0x1800f0ba4  mov     qword ptr [rbp+57h+var_40], rcx
0x1800f0ba8  mov     rcx, [rax+28h]
0x1800f0bac  mov     qword ptr [rbp+57h+var_40+8], rcx
0x1800f0bb0  mov     rcx, [rax+30h]
0x1800f0bb4  mov     [rbp+57h+var_30], rcx
0x1800f0bb8  mov     ecx, [rax+38h]
0x1800f0bbb  mov     [rbp+57h+var_28], ecx
0x1800f0bbe  mov     cl, [rax+3Ch]
0x1800f0bc1  mov     rdx, rax
0x1800f0bc4  mov     byte ptr [rbp+57h+var_24], cl
0x1800f0bc7  mov     al, [rax+3Dh]
0x1800f0bca  mov     byte ptr [rbp+57h+var_24+1], al
0x1800f0bcd  mov     al, [rdx+3Eh]
0x1800f0bd0  mov     [rbp+57h+var_22], al
0x1800f0bd3  mov     [rdx+3Ch], si
0x1800f0bd7  mov     [rdx+3Eh], sil
0x1800f0bdb  mov     [rdx+30h], rsi
0x1800f0bdf  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f0be3  call    ??1ctException@ctl@@UEAA@XZ; ctl::ctException::~ctException(void)
0x1800f0be8  mov     rcx, [rdi+0B0h]; hObject
0x1800f0bef  call    cs:__imp_CloseHandle
0x1800f0bf5  mov     [rdi+0B0h], rsi
0x1800f0bfc  xorps   xmm0, xmm0
0x1800f0bff  movups  [rbp+57h+var_A8], xmm0
0x1800f0c03  mov     [rbp+57h+pExceptionObject], r14
0x1800f0c07  mov     rax, [rbp+57h+var_48]
0x1800f0c0b  mov     [rbp+57h+var_98], rax
0x1800f0c0f  mov     rax, qword ptr [rbp+57h+var_40]
0x1800f0c13  mov     qword ptr [rbp+57h+var_90], rax
0x1800f0c17  mov     rax, qword ptr [rbp+57h+var_40+8]
0x1800f0c1b  mov     qword ptr [rbp+57h+var_90+8], rax
0x1800f0c1f  mov     rax, [rbp+57h+var_30]
0x1800f0c23  mov     [rbp+57h+var_80], rax
0x1800f0c27  mov     eax, [rbp+57h+var_28]
0x1800f0c2a  mov     [rbp+57h+var_78], eax
0x1800f0c2d  mov     al, byte ptr [rbp+57h+var_24]
0x1800f0c30  mov     byte ptr [rbp+57h+var_74], al
0x1800f0c33  mov     al, byte ptr [rbp+57h+var_24+1]
0x1800f0c36  mov     byte ptr [rbp+57h+var_74+1], al
0x1800f0c39  mov     al, [rbp+57h+var_22]
0x1800f0c3c  mov     [rbp+57h+var_72], al
0x1800f0c3f  mov     [rbp+57h+var_24], si
0x1800f0c43  mov     [rbp+57h+var_22], sil
0x1800f0c47  mov     [rbp+57h+var_30], rsi
0x1800f0c4b  lea     rdx, _TI2?AVctException@ctl@@; pThrowInfo
0x1800f0c52  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f0c56  call    _CxxThrowException_0
0x1800f0c5c  mov     rcx, [rbp+57h+var_20]
0x1800f0c60  xor     rcx, rsp; StackCookie
0x1800f0c63  call    __security_check_cookie
0x1800f0c68  lea     r11, [rsp+0E0h+var_10]
0x1800f0c70  mov     rbx, [r11+28h]
0x1800f0c74  mov     rsi, [r11+30h]
0x1800f0c78  mov     rsp, r11
0x1800f0c7b  pop     r14
0x1800f0c7d  pop     rdi
0x1800f0c7e  pop     rbp
0x1800f0c7f  retn
```

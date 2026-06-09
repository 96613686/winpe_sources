# CCscWmiAsyncThread::_ThreadProc(void *)

- ea: `0x180026a90`
- end: `0x180026d61`
- name: `?_ThreadProc@CCscWmiAsyncThread@@CAKPEAX@Z`
- size: `721`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009864`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x180016280`
- `0x180026a5c`
- `0x180026a90`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180026b4e`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180026b97`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180026be3`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180026b4e`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180026b97`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180026be3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180026b0d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180026b0d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180026ce8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180026ce8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180026d21`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180026d21`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180026ab6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180026ab6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180026d44`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180026d44`

## pseudocode

```c
__int64 __fastcall CCscWmiAsyncThread::_ThreadProc(PVOID Parameter)
{
  HMODULE v1; // r14
  UstVarLib *v3; // rcx
  int Error; // eax
  HRESULT InterfaceAndReleaseStream; // ebx
  HRESULT v6; // eax
  IStream *v7; // rcx
  IStream *v8; // rcx
  IStream *v9; // rcx
  unsigned int v10; // r15d
  LPVOID v12; // [rsp+70h] [rbp+30h] BYREF
  LPVOID v13; // [rsp+78h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+40h] BYREF

  v1 = (HMODULE)*((_QWORD *)Parameter + 4);
  *((_QWORD *)Parameter + 4) = 0;
  if ( ImpersonateLoggedOnUser(*((HANDLE *)Parameter + 5))
    || (Error = UstVarLib::ResultFromLastError(v3), InterfaceAndReleaseStream = Error, Error >= 0) )
  {
    v6 = CoInitializeEx(0, 0);
    InterfaceAndReleaseStream = v6;
    if ( v6 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          17,
          WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids,
          (unsigned int)v6);
    }
    else
    {
      InterfaceAndReleaseStream = *((_DWORD *)Parameter + 20);
      ppv = 0;
      if ( InterfaceAndReleaseStream >= 0 )
      {
        v7 = (IStream *)*((_QWORD *)Parameter + 9);
        if ( v7 )
        {
          InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                        v7,
                                        &GUID_9556dc99_828c_11cf_a37e_00aa003240c7,
                                        &ppv);
          if ( InterfaceAndReleaseStream >= 0 )
          {
            *((_QWORD *)Parameter + 9) = 0;
            InterfaceAndReleaseStream = *((_DWORD *)Parameter + 26);
            v13 = 0;
            if ( InterfaceAndReleaseStream >= 0 )
            {
              v8 = (IStream *)*((_QWORD *)Parameter + 12);
              if ( v8 )
              {
                InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                              v8,
                                              &GUID_44aca674_e8fc_11d0_a07c_00c04fb68820,
                                              &v13);
                if ( InterfaceAndReleaseStream >= 0 )
                {
                  *((_QWORD *)Parameter + 12) = 0;
                  InterfaceAndReleaseStream = *((_DWORD *)Parameter + 32);
                  v12 = 0;
                  if ( InterfaceAndReleaseStream >= 0 )
                  {
                    v9 = (IStream *)*((_QWORD *)Parameter + 15);
                    if ( v9 )
                    {
                      InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                                    v9,
                                                    &GUID_7c857801_7381_11cf_884d_00aa004b2e24,
                                                    &v12);
                      if ( InterfaceAndReleaseStream >= 0 )
                      {
                        *((_QWORD *)Parameter + 15) = 0;
                        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                        {
                          WPP_SF_(
                            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                            15,
                            WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids);
                        }
                        InterfaceAndReleaseStream = CCscWmiAsyncThread::_SignalThreadIsRunning((CCscWmiAsyncThread *)Parameter);
                        if ( InterfaceAndReleaseStream >= 0 )
                        {
                          v10 = (*(__int64 (__fastcall **)(PVOID, LPVOID, LPVOID, LPVOID, _QWORD, _QWORD))(*(_QWORD *)Parameter + 8LL))(
                                  Parameter,
                                  ppv,
                                  v13,
                                  v12,
                                  *((_QWORD *)Parameter + 18),
                                  *((_QWORD *)Parameter + 14));
                          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                          {
                            WPP_SF_(
                              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                              16,
                              WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids);
                          }
                          (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v12 + 32LL))(
                            v12,
                            0,
                            v10,
                            0,
                            0);
                        }
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
                      }
                    }
                    else
                    {
                      InterfaceAndReleaseStream = -2147467259;
                    }
                  }
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
                }
              }
              else
              {
                InterfaceAndReleaseStream = -2147467259;
              }
            }
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
        else
        {
          InterfaceAndReleaseStream = -2147467259;
        }
      }
      CoUninitialize();
    }
    RevertToSelf();
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      18,
      WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids,
      (unsigned int)Error);
  }
  *((_DWORD *)Parameter + 14) = InterfaceAndReleaseStream;
  CCscWmiAsyncThread::_SignalThreadIsRunning((CCscWmiAsyncThread *)Parameter);
  CRefCounted::ReleaseReference((CRefCounted *)Parameter);
  if ( v1 )
    FreeLibraryAndExitThread(v1, 0);
  return 0;
}

```

## disassembly

```asm
0x180026a90  mov     [rsp-28h+arg_18], rbx
0x180026a95  push    rbp
0x180026a96  push    rsi
0x180026a97  push    rdi
0x180026a98  push    r14
0x180026a9a  push    r15
0x180026a9c  mov     rbp, rsp
0x180026a9f  sub     rsp, 40h
0x180026aa3  mov     r14, [rcx+20h]
0x180026aa7  mov     rdi, rcx
0x180026aaa  mov     qword ptr [rcx+20h], 0
0x180026ab2  mov     rcx, [rcx+28h]; hToken
0x180026ab6  call    cs:__imp_ImpersonateLoggedOnUser
0x180026abc  test    eax, eax
0x180026abe  jnz     short loc_180026B09
0x180026ac0  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x180026ac5  mov     ebx, eax
0x180026ac7  test    eax, eax
0x180026ac9  jns     short loc_180026B09
0x180026acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ad2  lea     rsi, WPP_GLOBAL_Control
0x180026ad9  cmp     rcx, rsi
0x180026adc  jz      loc_180026D27
0x180026ae2  test    byte ptr [rcx+1Ch], 2
0x180026ae6  jz      loc_180026D27
0x180026aec  mov     rcx, [rcx+10h]
0x180026af0  lea     r8, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids
0x180026af7  mov     edx, 12h
0x180026afc  mov     r9d, eax
0x180026aff  call    WPP_SF_d
0x180026b04  jmp     loc_180026D27
0x180026b09  xor     edx, edx; dwCoInit
0x180026b0b  xor     ecx, ecx; pvReserved
0x180026b0d  call    cs:__imp_CoInitializeEx
0x180026b13  mov     ebx, eax
0x180026b15  test    eax, eax
0x180026b17  js      loc_180026CF0
0x180026b1d  mov     ebx, [rdi+50h]
0x180026b20  mov     [rbp+ppv], 0
0x180026b28  test    ebx, ebx
0x180026b2a  js      loc_180026CE8
0x180026b30  mov     rcx, [rdi+48h]; pStm
0x180026b34  test    rcx, rcx
0x180026b37  jnz     short loc_180026B43
0x180026b39  mov     ebx, 80004005h
0x180026b3e  jmp     loc_180026CE8
0x180026b43  lea     r8, [rbp+ppv]; ppv
0x180026b47  lea     rdx, _GUID_9556dc99_828c_11cf_a37e_00aa003240c7; iid
0x180026b4e  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180026b54  mov     ebx, eax
0x180026b56  test    eax, eax
0x180026b58  js      loc_180026CE8
0x180026b5e  mov     qword ptr [rdi+48h], 0
0x180026b66  mov     ebx, [rdi+68h]
0x180026b69  mov     [rbp+arg_8], 0
0x180026b71  test    ebx, ebx
0x180026b73  js      loc_180026CD8
0x180026b79  mov     rcx, [rdi+60h]; pStm
0x180026b7d  test    rcx, rcx
0x180026b80  jnz     short loc_180026B8C
0x180026b82  mov     ebx, 80004005h
0x180026b87  jmp     loc_180026CD8
0x180026b8c  lea     r8, [rbp+arg_8]; ppv
0x180026b90  lea     rdx, _GUID_44aca674_e8fc_11d0_a07c_00c04fb68820; iid
0x180026b97  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180026b9d  mov     ebx, eax
0x180026b9f  test    eax, eax
0x180026ba1  js      loc_180026CD8
0x180026ba7  mov     qword ptr [rdi+60h], 0
0x180026baf  mov     ebx, [rdi+80h]
0x180026bb5  mov     [rbp+arg_0], 0
0x180026bbd  test    ebx, ebx
0x180026bbf  js      loc_180026CC8
0x180026bc5  mov     rcx, [rdi+78h]; pStm
0x180026bc9  test    rcx, rcx
0x180026bcc  jnz     short loc_180026BD8
0x180026bce  mov     ebx, 80004005h
0x180026bd3  jmp     loc_180026CC8
0x180026bd8  lea     r8, [rbp+arg_0]; ppv
0x180026bdc  lea     rdx, _GUID_7c857801_7381_11cf_884d_00aa004b2e24; iid
0x180026be3  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180026be9  mov     ebx, eax
0x180026beb  test    eax, eax
0x180026bed  js      loc_180026CC8
0x180026bf3  mov     qword ptr [rdi+78h], 0
0x180026bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c02  lea     rsi, WPP_GLOBAL_Control
0x180026c09  cmp     rcx, rsi
0x180026c0c  jz      short loc_180026C2C
0x180026c0e  test    dword ptr [rcx+1Ch], 4000000h
0x180026c15  jz      short loc_180026C2C
0x180026c17  mov     rcx, [rcx+10h]
0x180026c1b  lea     r8, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids
0x180026c22  mov     edx, 0Fh
0x180026c27  call    WPP_SF_
0x180026c2c  mov     rcx, rdi; this
0x180026c2f  call    ?_SignalThreadIsRunning@CCscWmiAsyncThread@@AEAAJXZ; CCscWmiAsyncThread::_SignalThreadIsRunning(void)
0x180026c34  mov     ebx, eax
0x180026c36  test    eax, eax
0x180026c38  js      short loc_180026CB8
0x180026c3a  mov     rcx, [rdi+70h]
0x180026c3e  mov     rax, [rdi]
0x180026c41  mov     r9, [rbp+arg_0]
0x180026c45  mov     r8, [rbp+arg_8]
0x180026c49  mov     rdx, [rbp+ppv]
0x180026c4d  mov     rax, [rax+8]
0x180026c51  mov     [rsp+40h+var_18], rcx
0x180026c56  mov     rcx, [rdi+90h]
0x180026c5d  mov     [rsp+40h+var_20], rcx
0x180026c62  mov     rcx, rdi
0x180026c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c6a  mov     r15d, eax
0x180026c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c74  cmp     rcx, rsi
0x180026c77  jz      short loc_180026C97
0x180026c79  test    dword ptr [rcx+1Ch], 4000000h
0x180026c80  jz      short loc_180026C97
0x180026c82  mov     rcx, [rcx+10h]
0x180026c86  lea     r8, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids
0x180026c8d  mov     edx, 10h
0x180026c92  call    WPP_SF_
0x180026c97  mov     rcx, [rbp+arg_0]
0x180026c9b  xor     r9d, r9d
0x180026c9e  mov     r8d, r15d
0x180026ca1  mov     [rsp+40h+var_20], 0
0x180026caa  xor     edx, edx
0x180026cac  mov     rax, [rcx]
0x180026caf  mov     rax, [rax+20h]
0x180026cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cb8  mov     rcx, [rbp+arg_0]
0x180026cbc  mov     rax, [rcx]
0x180026cbf  mov     rax, [rax+10h]
0x180026cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cc8  mov     rcx, [rbp+arg_8]
0x180026ccc  mov     rax, [rcx]
0x180026ccf  mov     rax, [rax+10h]
0x180026cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cd8  mov     rcx, [rbp+ppv]
0x180026cdc  mov     rax, [rcx]
0x180026cdf  mov     rax, [rax+10h]
0x180026ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ce8  call    cs:__imp_CoUninitialize
0x180026cee  jmp     short loc_180026D21
0x180026cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180026cf7  lea     rsi, WPP_GLOBAL_Control
0x180026cfe  cmp     rcx, rsi
0x180026d01  jz      short loc_180026D21
0x180026d03  test    byte ptr [rcx+1Ch], 2
0x180026d07  jz      short loc_180026D21
0x180026d09  mov     rcx, [rcx+10h]
0x180026d0d  lea     r8, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids
0x180026d14  mov     edx, 11h
0x180026d19  mov     r9d, eax
0x180026d1c  call    WPP_SF_d
0x180026d21  call    cs:__imp_RevertToSelf
0x180026d27  mov     rcx, rdi; this
0x180026d2a  mov     [rdi+38h], ebx
0x180026d2d  call    ?_SignalThreadIsRunning@CCscWmiAsyncThread@@AEAAJXZ; CCscWmiAsyncThread::_SignalThreadIsRunning(void)
0x180026d32  mov     rcx, rdi; this
0x180026d35  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x180026d3a  test    r14, r14
0x180026d3d  jz      short loc_180026D4B
0x180026d3f  xor     edx, edx; dwExitCode
0x180026d41  mov     rcx, r14; hLibModule
0x180026d44  call    cs:__imp_FreeLibraryAndExitThread
0x180026d4a  int     3; Trap to Debugger
0x180026d4b  mov     rbx, [rsp+40h+arg_18]
0x180026d53  xor     eax, eax
0x180026d55  add     rsp, 40h
0x180026d59  pop     r15
0x180026d5b  pop     r14
0x180026d5d  pop     rdi
0x180026d5e  pop     rsi
0x180026d5f  pop     rbp
0x180026d60  retn
```

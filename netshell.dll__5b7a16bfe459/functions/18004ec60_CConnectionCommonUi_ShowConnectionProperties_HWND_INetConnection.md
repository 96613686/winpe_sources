# CConnectionCommonUi::ShowConnectionProperties(HWND__ *,INetConnection *)

- ea: `0x18004ec60`
- end: `0x18004ee0d`
- name: `?ShowConnectionProperties@CConnectionCommonUi@@UEAAJPEAUHWND__@@PEAUINetConnection@@@Z`
- size: `429`
- prototype: `int(CConnectionCommonUi *__hidden this, HWND, struct INetConnection *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180002010`
- `0x180019898`
- `0x18001e5b0`
- `0x180034ba0`
- `0x18004ec60`
- `0x18004ef34`
- `0x180060b3c`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18004edad`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18004edad`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004ed6a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004ed6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004edd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004edd3`
- `ole32!CoWaitForMultipleHandles` at `0x18004ed98`
- `ole32!CoWaitForMultipleHandles` at `0x18004ed98`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x18004ecf5`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x18004ecf5`

## pseudocode

```c
HRESULT __fastcall CConnectionCommonUi::ShowConnectionProperties(CConnectionCommonUi *this, HWND a2, IUnknown *a3)
{
  HRESULT result; // eax
  _QWORD *v7; // rax
  void *v8; // rbx
  DWORD Win32Error; // eax
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  LPSTREAM ppStm; // [rsp+38h] [rbp-8h] BYREF
  DWORD ExitCode; // [rsp+60h] [rbp+20h] BYREF
  INITCOMMONCONTROLSEX picce; // [rsp+78h] [rbp+38h] BYREF

  result = 0;
  ExitCode = 0;
  if ( !*((_QWORD *)this + 9) )
  {
    picce.dwSize = 8;
    picce.dwICC = 512;
    result = HrCreateInstanceBase(
               &CLSID_ConnectionManager,
               0x404u,
               &GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e,
               (void **)this + 9);
    if ( result >= 0 )
    {
      if ( !InitCommonControlsEx(&picce) )
        return -2147024894;
      result = CChooseConnectionDlg::HrLoadImageList((struct _IMAGELIST **)this + 10);
    }
  }
  ExitCode = result;
  if ( result >= 0 )
  {
    ppStm = 0;
    result = CoMarshalInterThreadInterfaceInStream(&IID_INetConnection, a3, &ppStm);
    ExitCode = result;
    if ( result >= 0 )
    {
      v7 = MemAlloc(0x18u);
      v8 = v7;
      if ( !v7 )
      {
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppStm + 16LL))(ppStm);
        return -2147024882;
      }
      *v7 = a2;
      v7[1] = ppStm;
      *((_DWORD *)v7 + 4) = *((_DWORD *)this + 16);
      pHandles = CreateThread(0, 0, ShowPropertiesDialogThreadProc, v7, 0, 0);
      if ( pHandles )
      {
        picce.dwSize = 0;
        ExitCode = CoWaitForMultipleHandles(1u, 0xFFFFFFFF, 1u, &pHandles, (LPDWORD)&picce);
        if ( (ExitCode & 0x80000000) == 0 )
        {
          if ( !GetExitCodeThread(pHandles, &ExitCode) )
          {
            Win32Error = HrFromLastWin32Error();
            goto LABEL_16;
          }
          if ( ExitCode == 259 )
          {
            Win32Error = -2147467259;
LABEL_16:
            ExitCode = Win32Error;
          }
        }
        CloseHandle(pHandles);
        return ExitCode;
      }
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppStm + 16LL))(ppStm);
      operator delete(v8);
      return -2147467259;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004ec60  mov     [rsp-18h+arg_8], rbx
0x18004ec65  push    rbp
0x18004ec66  push    rsi
0x18004ec67  push    rdi
0x18004ec68  mov     rbp, rsp
0x18004ec6b  sub     rsp, 40h
0x18004ec6f  xor     eax, eax
0x18004ec71  mov     [rbp+ExitCode], 0
0x18004ec78  lea     r9, [rcx+48h]; void **
0x18004ec7c  mov     rbx, r8
0x18004ec7f  mov     rsi, rdx
0x18004ec82  mov     rdi, rcx
0x18004ec85  cmp     [r9], rax
0x18004ec88  jnz     short loc_18004ECD4
0x18004ec8a  lea     r8, _GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e; struct _GUID *
0x18004ec91  mov     [rbp+picce.dwSize], 8
0x18004ec98  mov     edx, 404h; unsigned int
0x18004ec9d  mov     [rbp+picce.dwICC], 200h
0x18004eca4  lea     rcx, CLSID_ConnectionManager; struct _GUID *
0x18004ecab  call    ?HrCreateInstanceBase@@YAJAEBU_GUID@@K0PEAPEAX@Z; HrCreateInstanceBase(_GUID const &,ulong,_GUID const &,void * *)
0x18004ecb0  test    eax, eax
0x18004ecb2  js      short loc_18004ECD4
0x18004ecb4  lea     rcx, [rbp+picce]; picce
0x18004ecb8  call    InitCommonControlsEx
0x18004ecbd  test    eax, eax
0x18004ecbf  jnz     short loc_18004ECCB
0x18004ecc1  mov     eax, 80070002h
0x18004ecc6  jmp     loc_18004EE00
0x18004eccb  lea     rcx, [rdi+50h]; struct _IMAGELIST **
0x18004eccf  call    ?HrLoadImageList@CChooseConnectionDlg@@SAJPEAPEAU_IMAGELIST@@@Z; CChooseConnectionDlg::HrLoadImageList(_IMAGELIST * *)
0x18004ecd4  mov     [rbp+ExitCode], eax
0x18004ecd7  test    eax, eax
0x18004ecd9  js      loc_18004EE00
0x18004ecdf  lea     r8, [rbp+ppStm]; ppStm
0x18004ece3  mov     [rbp+ppStm], 0
0x18004eceb  mov     rdx, rbx; pUnk
0x18004ecee  lea     rcx, IID_INetConnection; riid
0x18004ecf5  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18004ecfb  mov     [rbp+ExitCode], eax
0x18004ecfe  test    eax, eax
0x18004ed00  js      loc_18004EE00
0x18004ed06  mov     ecx, 18h; unsigned __int64
0x18004ed0b  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18004ed10  mov     rbx, rax
0x18004ed13  test    rax, rax
0x18004ed16  jnz     short loc_18004ED32
0x18004ed18  mov     rcx, [rbp+ppStm]
0x18004ed1c  mov     rax, [rcx]
0x18004ed1f  mov     rax, [rax+10h]
0x18004ed23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed28  mov     eax, 8007000Eh
0x18004ed2d  jmp     loc_18004EE00
0x18004ed32  mov     [rax], rsi
0x18004ed35  lea     r8, ?ShowPropertiesDialogThreadProc@@YAKPEAX@Z; lpStartAddress
0x18004ed3c  mov     rax, [rbp+ppStm]
0x18004ed40  mov     r9, rbx; lpParameter
0x18004ed43  mov     [rbx+8], rax
0x18004ed47  xor     edx, edx; dwStackSize
0x18004ed49  mov     eax, [rdi+40h]
0x18004ed4c  xor     ecx, ecx; lpThreadAttributes
0x18004ed4e  mov     [rbx+10h], eax
0x18004ed51  mov     [rsp+40h+lpThreadId], 0; lpThreadId
0x18004ed5a  mov     [rbp+pHandles], 0
0x18004ed62  mov     [rsp+40h+dwCreationFlags], 0; dwCreationFlags
0x18004ed6a  call    cs:__imp_CreateThread
0x18004ed70  mov     [rbp+pHandles], rax
0x18004ed74  test    rax, rax
0x18004ed77  jz      short loc_18004EDDE
0x18004ed79  mov     ecx, 1; dwFlags
0x18004ed7e  mov     [rbp+picce.dwSize], 0
0x18004ed85  lea     rax, [rbp+picce]
0x18004ed89  mov     r8d, ecx; cHandles
0x18004ed8c  lea     r9, [rbp+pHandles]; pHandles
0x18004ed90  mov     qword ptr [rsp+40h+dwCreationFlags], rax; lpdwindex
0x18004ed95  or      edx, 0FFFFFFFFh; dwTimeout
0x18004ed98  call    cs:__imp_CoWaitForMultipleHandles
0x18004ed9e  mov     [rbp+ExitCode], eax
0x18004eda1  test    eax, eax
0x18004eda3  js      short loc_18004EDCF
0x18004eda5  mov     rcx, [rbp+pHandles]; hThread
0x18004eda9  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18004edad  call    cs:__imp_GetExitCodeThread
0x18004edb3  test    eax, eax
0x18004edb5  jz      short loc_18004EDC7
0x18004edb7  cmp     [rbp+ExitCode], 103h
0x18004edbe  jnz     short loc_18004EDCF
0x18004edc0  mov     eax, 80004005h
0x18004edc5  jmp     short loc_18004EDCC
0x18004edc7  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18004edcc  mov     [rbp+ExitCode], eax
0x18004edcf  mov     rcx, [rbp+pHandles]; hObject
0x18004edd3  call    cs:__imp_CloseHandle
0x18004edd9  mov     eax, [rbp+ExitCode]
0x18004eddc  jmp     short loc_18004EE00
0x18004edde  mov     rcx, [rbp+ppStm]
0x18004ede2  mov     rax, [rcx]
0x18004ede5  mov     rax, [rax+10h]
0x18004ede9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edee  mov     edx, 18h; unsigned __int64
0x18004edf3  mov     rcx, rbx; void *
0x18004edf6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004edfb  mov     eax, 80004005h
0x18004ee00  mov     rbx, [rsp+40h+arg_8]
0x18004ee05  add     rsp, 40h
0x18004ee09  pop     rdi
0x18004ee0a  pop     rsi
0x18004ee0b  pop     rbp
0x18004ee0c  retn
```

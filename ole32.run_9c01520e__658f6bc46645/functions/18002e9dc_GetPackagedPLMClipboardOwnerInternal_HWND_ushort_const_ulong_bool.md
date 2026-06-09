# GetPackagedPLMClipboardOwnerInternal(HWND__ *,ushort const * *,ulong *,bool *)

- ea: `0x18002e9dc`
- end: `0x18002ec13`
- name: `?GetPackagedPLMClipboardOwnerInternal@@YAJPEAUHWND__@@PEAPEBGPEAKPEA_N@Z`
- size: `567`
- prototype: `HRESULT __fastcall(HWND__ *hWndClipboardOwner, const wchar_t **ppszPackageFullName, unsigned int *ppid, bool *pIsPLMManaged)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019864`
- `0x18008c2a0`

## callees

- `0x18001c778`
- `0x18002e9dc`
- `0x18002ec1c`
- `0x180041e3c`
- `0x180047484`
- `0x18008a880`

## import_xrefs

- `KERNELBASE!GetPackageFullName` at `0x18002eb5c`
- `KERNELBASE!GetPackageFullName` at `0x18002eb5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eabc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eabc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebbe`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ea88`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ea88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eaab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ebb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eaab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ebb0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002ea5e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002ea5e`
- `USER32!GetWindowThreadProcessId` at `0x18002ea40`
- `USER32!GetWindowThreadProcessId` at `0x18002ea40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002eb15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002eb15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eb77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eb77`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002eb32`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002eb32`

## pseudocode

```c
__int64 __fastcall GetPackagedPLMClipboardOwnerInternal(
        HWND__ *hWndClipboardOwner,
        wchar_t **ppszPackageFullName,
        unsigned int *ppid,
        bool *pIsPLMManaged)
{
  HRESULT Policy; // ebx
  DWORD v5; // r15d
  AppModelPolicy_PolicyValue v6; // edi
  HWND__ *v9; // rsi
  int ClipboardOwnerWindowProperty; // eax
  HANDLE v11; // rax
  AppModelPolicy_Type v12; // edx
  signed int LastError; // eax
  bool v14; // zf
  wchar_t *v15; // rax
  wchar_t *v16; // rsi
  LONG PackageFullName; // edi
  signed int v18; // eax
  HANDLE hProcess; // [rsp+20h] [rbp-10h]
  void *token; // [rsp+78h] [rbp+48h] BYREF
  AppModelPolicy_PolicyValue lifecyclePolicy; // [rsp+80h] [rbp+50h] BYREF
  bool *len; // [rsp+88h] [rbp+58h] BYREF

  len = pIsPLMManaged;
  Policy = 0;
  v5 = 0;
  *ppszPackageFullName = 0;
  v6 = AppModelPolicy_LifecycleManager_Unmanaged;
  LODWORD(token) = 0;
  lifecyclePolicy = AppModelPolicy_LifecycleManager_Unmanaged;
  *pIsPLMManaged = 0;
  v9 = hWndClipboardOwner;
  if ( ppid )
    *ppid = 0;
  if ( !hWndClipboardOwner
    || (ClipboardOwnerWindowProperty = GetClipboardOwnerWindowProperty(
                                         hWndClipboardOwner,
                                         (const wchar_t **)ppszPackageFullName,
                                         (unsigned int *)&token),
        v5 = (unsigned int)token,
        Policy = ClipboardOwnerWindowProperty,
        ClipboardOwnerWindowProperty >= 0) )
  {
    if ( GetWindowThreadProcessId(v9, 0) )
    {
      v11 = OpenProcess(0x400u, 0, v5);
      hProcess = v11;
      if ( v11 )
      {
        token = 0;
        if ( OpenProcessToken(v11, 8u, &token) )
        {
          Policy = AppModelPolicy_GetPolicy(token, v12, &lifecyclePolicy);
          CloseHandle(token);
          v6 = lifecyclePolicy;
        }
        else
        {
          LastError = GetLastError();
          Policy = LastError;
          if ( LastError > 0 )
            Policy = (unsigned __int16)LastError | 0x80070000;
          OleInternalOriginateError(Policy, 0x135u);
        }
        if ( Policy >= 0 && v6 == AppModelPolicy_LifecycleManager_ManagedByPLM )
        {
          v14 = *ppszPackageFullName == 0;
          *len = 1;
          if ( v14 )
          {
            LODWORD(len) = 127;
            v15 = (wchar_t *)CoTaskMemAlloc(0xFEu);
            v16 = v15;
            if ( v15 )
            {
              memset_0(v15, 0, 2LL * (unsigned int)len);
              PackageFullName = GetPackageFullName(hProcess, (UINT32 *)&len, v16);
              if ( PackageFullName )
              {
                CoTaskMemFree(v16);
                if ( PackageFullName != 15700 )
                {
                  if ( PackageFullName > 0 )
                    Policy = (unsigned __int16)PackageFullName | 0x80070000;
                  else
                    Policy = PackageFullName;
                  OleInternalOriginateError(Policy, 0x136u);
                }
              }
              else
              {
                *ppszPackageFullName = v16;
              }
            }
            else
            {
              Policy = -2147024882;
              RoOriginateError(2147942414LL, 0);
            }
            v9 = hWndClipboardOwner;
          }
        }
        CloseHandle(hProcess);
      }
      else
      {
        v18 = GetLastError();
        Policy = v18;
        if ( v18 > 0 )
          Policy = (unsigned __int16)v18 | 0x80070000;
        OleInternalOriginateError(Policy, 0x137u);
      }
    }
  }
  if ( ppid && Policy >= 0 )
    *ppid = v5;
  OleClipboardTracing::GetPackagedPLMClipboardOwnerInternalEtw(Policy, v9, (const wchar_t **)ppszPackageFullName, ppid);
  return (unsigned int)Policy;
}

```

## disassembly

```asm
0x18002e9dc  mov     [rsp-38h+len], pIsPLMManaged
0x18002e9e1  mov     [rsp-38h+arg_0], hWndClipboardOwner
0x18002e9e6  push    rbp
0x18002e9e7  push    rbx
0x18002e9e8  push    rsi
0x18002e9e9  push    rdi
0x18002e9ea  push    r13
0x18002e9ec  push    r14
0x18002e9ee  push    r15
0x18002e9f0  mov     rbp, rsp
0x18002e9f3  sub     rsp, 30h
0x18002e9f7  xor     ebx, ebx
0x18002e9f9  xor     r15d, r15d
0x18002e9fc  and     [ppszPackageFullName], rbx
0x18002e9ff  mov     edi, 10000h
0x18002ea04  mov     dword ptr [rbp+token], r15d
0x18002ea08  mov     r14, ppid
0x18002ea0b  mov     [rbp+lifecyclePolicy], edi
0x18002ea0e  mov     r13, ppszPackageFullName
0x18002ea11  mov     [pIsPLMManaged], bl
0x18002ea14  mov     rsi, hWndClipboardOwner
0x18002ea17  test    ppid, ppid
0x18002ea1a  jz      short loc_18002EA1F
0x18002ea1c  and     [ppid], ebx
0x18002ea1f  test    rsi, rsi
0x18002ea22  jz      short loc_18002EA3B
0x18002ea24  lea     ppid, [rbp+token]; pdwProcessId
0x18002ea28  call    ?GetClipboardOwnerWindowProperty@@YAJPEAUHWND__@@PEAPEBGPEAK@Z; GetClipboardOwnerWindowProperty(HWND__ *,ushort const * *,ulong *)
0x18002ea2d  mov     r15d, dword ptr [rbp+token]
0x18002ea31  mov     ebx, eax
0x18002ea33  test    eax, eax
0x18002ea35  js      loc_18002EBE5
0x18002ea3b  xor     edx, edx; lpdwProcessId
0x18002ea3d  mov     hWndClipboardOwner, rsi; hWnd
0x18002ea40  call    cs:__imp_GetWindowThreadProcessId
0x18002ea47  nop     dword ptr [rax+rax+00h]
0x18002ea4c  test    eax, eax
0x18002ea4e  jz      loc_18002EBE5
0x18002ea54  mov     r8d, r15d; dwProcessId
0x18002ea57  xor     edx, edx; bInheritHandle
0x18002ea59  mov     ecx, 400h; dwDesiredAccess
0x18002ea5e  call    cs:__imp_OpenProcess
0x18002ea65  nop     dword ptr [rax+rax+00h]
0x18002ea6a  mov     [rbp+hProcess], rax
0x18002ea6e  test    rax, rax
0x18002ea71  jz      loc_18002EBBE
0x18002ea77  and     [rbp+token], 0
0x18002ea7c  lea     ppid, [rbp+token]; TokenHandle
0x18002ea80  mov     edx, 8; DesiredAccess
0x18002ea85  mov     hWndClipboardOwner, rax; ProcessHandle
0x18002ea88  call    cs:__imp_OpenProcessToken
0x18002ea8f  nop     dword ptr [rax+rax+00h]
0x18002ea94  test    eax, eax
0x18002ea96  jz      short loc_18002EABC
0x18002ea98  mov     hWndClipboardOwner, [rbp+token]; token
0x18002ea9c  lea     ppid, [rbp+lifecyclePolicy]; token
0x18002eaa0  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x18002eaa5  mov     hWndClipboardOwner, [rbp+token]; hObject
0x18002eaa9  mov     ebx, eax
0x18002eaab  call    cs:__imp_CloseHandle
0x18002eab2  nop     dword ptr [rax+rax+00h]
0x18002eab7  mov     edi, [rbp+lifecyclePolicy]
0x18002eaba  jmp     short loc_18002EAE3
0x18002eabc  call    cs:__imp_GetLastError
0x18002eac3  nop     dword ptr [rax+rax+00h]
0x18002eac8  mov     ebx, eax
0x18002eaca  test    eax, eax
0x18002eacc  jle     short loc_18002EAD7
0x18002eace  movzx   ebx, ax
0x18002ead1  or      ebx, 80070000h
0x18002ead7  mov     edx, 135h; messageID
0x18002eadc  mov     ecx, ebx; hr
0x18002eade  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18002eae3  test    ebx, ebx
0x18002eae5  js      loc_18002EBAC
0x18002eaeb  cmp     edi, 10001h
0x18002eaf1  jnz     loc_18002EBAC
0x18002eaf7  cmp     qword ptr [r13+0], 0
0x18002eafc  mov     rax, [rbp+len]
0x18002eb00  mov     byte ptr [rax], 1
0x18002eb03  jnz     loc_18002EBAC
0x18002eb09  mov     ecx, 0FEh; cb
0x18002eb0e  mov     dword ptr [rbp+len], 7Fh
0x18002eb15  call    cs:__imp_CoTaskMemAlloc
0x18002eb1c  nop     dword ptr [rax+rax+00h]
0x18002eb21  mov     rsi, rax
0x18002eb24  test    rax, rax
0x18002eb27  jnz     short loc_18002EB40
0x18002eb29  mov     ebx, 8007000Eh
0x18002eb2e  xor     edx, edx
0x18002eb30  mov     ecx, ebx
0x18002eb32  call    cs:__imp_RoOriginateError
0x18002eb39  nop     dword ptr [rax+rax+00h]
0x18002eb3e  jmp     short loc_18002EBA8
0x18002eb40  mov     r8d, dword ptr [rbp+len]
0x18002eb44  xor     edx, edx; Val
0x18002eb46  add     ppid, ppid; Size
0x18002eb49  mov     hWndClipboardOwner, rsi; void *
0x18002eb4c  call    memset_0
0x18002eb51  mov     hWndClipboardOwner, [rbp+hProcess]; hProcess
0x18002eb55  lea     ppszPackageFullName, [rbp+len]; packageFullNameLength
0x18002eb59  mov     ppid, rsi; packageFullName
0x18002eb5c  call    cs:__imp_GetPackageFullName
0x18002eb63  nop     dword ptr [rax+rax+00h]
0x18002eb68  mov     edi, eax
0x18002eb6a  test    eax, eax
0x18002eb6c  jnz     short loc_18002EB74
0x18002eb6e  mov     [r13+0], rsi
0x18002eb72  jmp     short loc_18002EBA8
0x18002eb74  mov     hWndClipboardOwner, rsi; pv
0x18002eb77  call    cs:__imp_CoTaskMemFree
0x18002eb7e  nop     dword ptr [rax+rax+00h]
0x18002eb83  cmp     edi, 3D54h
0x18002eb89  jz      short loc_18002EBA8
0x18002eb8b  test    edi, edi
0x18002eb8d  jg      short loc_18002EB93
0x18002eb8f  mov     ebx, edi
0x18002eb91  jmp     short loc_18002EB9C
0x18002eb93  movzx   ebx, di
0x18002eb96  or      ebx, 80070000h
0x18002eb9c  mov     edx, 136h; messageID
0x18002eba1  mov     ecx, ebx; hr
0x18002eba3  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18002eba8  mov     rsi, [rbp+arg_0]
0x18002ebac  mov     hWndClipboardOwner, [rbp+hProcess]; hObject
0x18002ebb0  call    cs:__imp_CloseHandle
0x18002ebb7  nop     dword ptr [rax+rax+00h]
0x18002ebbc  jmp     short loc_18002EBE5
0x18002ebbe  call    cs:__imp_GetLastError
0x18002ebc5  nop     dword ptr [rax+rax+00h]
0x18002ebca  mov     ebx, eax
0x18002ebcc  test    eax, eax
0x18002ebce  jle     short loc_18002EBD9
0x18002ebd0  movzx   ebx, ax
0x18002ebd3  or      ebx, 80070000h
0x18002ebd9  mov     edx, 137h; messageID
0x18002ebde  mov     ecx, ebx; hr
0x18002ebe0  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18002ebe5  test    r14, r14
0x18002ebe8  jz      short loc_18002EBF1
0x18002ebea  test    ebx, ebx
0x18002ebec  js      short loc_18002EBF1
0x18002ebee  mov     [r14], r15d
0x18002ebf1  mov     pIsPLMManaged, r14; ppid
0x18002ebf4  mov     ppid, r13; ppszPackageFullName
0x18002ebf7  mov     ppszPackageFullName, rsi; hWndClipboardOwner
0x18002ebfa  mov     ecx, ebx; hr
0x18002ebfc  call    ?GetPackagedPLMClipboardOwnerInternalEtw@OleClipboardTracing@@SAXJPEAUHWND__@@PEAPEBGPEAK@Z; OleClipboardTracing::GetPackagedPLMClipboardOwnerInternalEtw(long,HWND__ *,ushort const * *,ulong *)
0x18002ec01  mov     eax, ebx
0x18002ec03  add     rsp, 30h
0x18002ec07  pop     r15
0x18002ec09  pop     r14
0x18002ec0b  pop     r13
0x18002ec0d  pop     rdi
0x18002ec0e  pop     rsi
0x18002ec0f  pop     rbx
0x18002ec10  pop     rbp
0x18002ec11  retn
```

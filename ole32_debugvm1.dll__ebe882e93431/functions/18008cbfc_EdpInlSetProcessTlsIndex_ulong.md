# EdpInlSetProcessTlsIndex(ulong *)

- ea: `0x18008cbfc`
- end: `0x18008ccd7`
- name: `?EdpInlSetProcessTlsIndex@@YAJPEAK@Z`
- size: `219`
- prototype: `HRESULT __fastcall(unsigned int *TlsIndex)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800405d4`

## callees

- `0x180053014`
- `0x18008cb44`
- `0x18008cbfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cc47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cc47`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18008cc3a`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18008cc3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008cc6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008cc6a`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18008ccba`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18008ccba`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EdpSetCredServiceInfo` at `0x18008cc8e`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EdpSetCredServiceInfo` at `0x18008cc8e`

## pseudocode

```c
__int64 __fastcall EdpInlSetProcessTlsIndex(unsigned int *TlsIndex)
{
  int ProcessTlsIndex; // ebx
  DWORD v3; // edi
  signed int LastError; // eax
  void *v5; // rcx
  _EDP_CRED_SVC_INFO EdpCredSvcInfo; // [rsp+30h] [rbp-98h] BYREF

  memset_0(&EdpCredSvcInfo, 0, sizeof(EdpCredSvcInfo));
  if ( TlsIndex )
  {
    *TlsIndex = -1;
    v3 = TlsAlloc();
    if ( v3 != -1 )
    {
      EdpCredSvcInfo.cbSize = 136;
      EdpCredSvcInfo.eInfoType = EdpCredSvcInfo_SetProcessTlsIndex;
      EdpCredSvcInfo.DplUserCredentialInfo.DplUserId = __PAIR64__(v3, GetCurrentProcessId());
      ProcessTlsIndex = EdpSetCredServiceInfo((unsigned int)EdpCredSvcInfo.eInfoType, 0, 0, 0, &EdpCredSvcInfo);
      if ( ProcessTlsIndex >= 0 )
      {
        ProcessTlsIndex = EdpInlGetProcessTlsIndex(v5, TlsIndex);
        if ( ProcessTlsIndex >= 0 )
        {
          if ( *TlsIndex == -1 )
          {
            ProcessTlsIndex = -2147418113;
          }
          else if ( v3 == *TlsIndex )
          {
            return (unsigned int)ProcessTlsIndex;
          }
        }
      }
      TlsFree(v3);
      return (unsigned int)ProcessTlsIndex;
    }
    LastError = GetLastError();
    ProcessTlsIndex = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)ProcessTlsIndex;
}

```

## disassembly

```asm
0x18008cbfc  mov     [rsp+arg_0], rbx
0x18008cc01  mov     [rsp+arg_8], rsi
0x18008cc06  push    rdi
0x18008cc07  sub     rsp, 0C0h
0x18008cc0e  mov     rsi, TlsIndex
0x18008cc11  mov     ebx, 88h
0x18008cc16  mov     r8d, ebx; Size
0x18008cc19  lea     TlsIndex, [rsp+0C8h+EdpCredSvcInfo]; void *
0x18008cc1e  xor     edx, edx; Val
0x18008cc20  call    memset_0
0x18008cc25  test    rsi, rsi
0x18008cc28  jnz     short loc_18008CC34
0x18008cc2a  mov     ebx, 80004003h
0x18008cc2f  jmp     loc_18008CCC0
0x18008cc34  mov     dword ptr [rsi], 0FFFFFFFFh
0x18008cc3a  call    cs:__imp_TlsAlloc
0x18008cc40  mov     edi, eax
0x18008cc42  cmp     eax, 0FFFFFFFFh
0x18008cc45  jnz     short loc_18008CC5E
0x18008cc47  call    cs:__imp_GetLastError
0x18008cc4d  mov     ebx, eax
0x18008cc4f  test    eax, eax
0x18008cc51  jle     short loc_18008CCC0
0x18008cc53  movzx   ebx, ax
0x18008cc56  or      ebx, 80070000h
0x18008cc5c  jmp     short loc_18008CCC0
0x18008cc5e  mov     [rsp+0C8h+EdpCredSvcInfo.cbSize], ebx
0x18008cc62  mov     [rsp+0C8h+EdpCredSvcInfo.eInfoType], 7
0x18008cc6a  call    cs:__imp_GetCurrentProcessId
0x18008cc70  mov     ecx, [rsp+0C8h+EdpCredSvcInfo.eInfoType]
0x18008cc74  xor     r9d, r9d
0x18008cc77  mov     dword ptr [rsp+0C8h+EdpCredSvcInfo.___u2], eax
0x18008cc7b  xor     r8d, r8d
0x18008cc7e  lea     rax, [rsp+0C8h+EdpCredSvcInfo]
0x18008cc83  mov     dword ptr [rsp+0C8h+EdpCredSvcInfo.___u2+4], edi
0x18008cc87  xor     edx, edx
0x18008cc89  mov     [rsp+0C8h+var_A8], rax
0x18008cc8e  call    cs:__imp_EdpSetCredServiceInfo
0x18008cc94  mov     ebx, eax
0x18008cc96  test    eax, eax
0x18008cc98  js      short loc_18008CCB8
0x18008cc9a  mov     rdx, rsi; hProcess
0x18008cc9d  call    ?EdpInlGetProcessTlsIndex@@YAJPEAXPEAK@Z; EdpInlGetProcessTlsIndex(void *,ulong *)
0x18008cca2  mov     ebx, eax
0x18008cca4  test    eax, eax
0x18008cca6  js      short loc_18008CCB8
0x18008cca8  cmp     dword ptr [rsi], 0FFFFFFFFh
0x18008ccab  jnz     short loc_18008CCB4
0x18008ccad  mov     ebx, 8000FFFFh
0x18008ccb2  jmp     short loc_18008CCB8
0x18008ccb4  cmp     edi, [rsi]
0x18008ccb6  jz      short loc_18008CCC0
0x18008ccb8  mov     ecx, edi; dwTlsIndex
0x18008ccba  call    cs:__imp_TlsFree
0x18008ccc0  lea     r11, [rsp+0C8h+var_8]
0x18008ccc8  mov     eax, ebx
0x18008ccca  mov     rbx, [r11+10h]
0x18008ccce  mov     rsi, [r11+18h]
0x18008ccd2  mov     rsp, r11
0x18008ccd5  pop     rdi
0x18008ccd6  retn
```

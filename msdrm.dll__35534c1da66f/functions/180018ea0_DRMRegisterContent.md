# DRMRegisterContent

- ea: `0x180018ea0`
- end: `0x180018fbe`
- name: `DRMRegisterContent`
- size: `286`
- prototype: `HRESULT __stdcall(BOOL fRegister)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180017358`
- `0x180018a00`
- `0x180018ea0`
- `0x180037b58`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018eda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018eda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f86`

## pseudocode

```c
HRESULT __stdcall DRMRegisterContent(BOOL fRegister)
{
  HRESULT v2; // edi
  DWORD CurrentProcessId; // esi
  struct _SECURITY_ATTRIBUTES *v4; // rdx
  signed int LastError; // eax
  unsigned __int16 v7[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = 0;
  memset_0(v7, 0, 0x208u);
  CurrentProcessId = GetCurrentProcessId();
  if ( fRegister )
  {
    if ( _InterlockedIncrement(&dword_1800856AC) == 1 )
    {
      v2 = DisablePrintScreen(1);
      if ( v2 >= 0 )
      {
        v2 = StringCchPrintfW(v7, 0x104u, L"DRMRegisterContent_%lu", CurrentProcessId);
        if ( v2 >= 0 )
        {
          g_hDRMRegisterContentEvent = DRMOS::CreateEventA(0, v4, 0, (DRMOS *)v7);
          if ( !g_hDRMRegisterContentEvent )
          {
            LastError = GetLastError();
            v2 = LastError;
            if ( LastError > 0 )
              return (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
  else if ( _InterlockedExchangeAdd(&dword_1800856AC, 0xFFFFFFFF) == 1 )
  {
    v2 = DisablePrintScreen(0);
    if ( v2 >= 0 )
    {
      if ( g_hDRMRegisterContentEvent )
      {
        CloseHandle(g_hDRMRegisterContentEvent);
        g_hDRMRegisterContentEvent = 0;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180018ea0  mov     [rsp+arg_0], rbx
0x180018ea5  mov     [rsp+arg_8], rsi
0x180018eaa  push    rdi
0x180018eab  sub     rsp, 240h
0x180018eb2  mov     rax, cs:__security_cookie
0x180018eb9  xor     rax, rsp
0x180018ebc  mov     [rsp+248h+var_18], rax
0x180018ec4  mov     ebx, ecx
0x180018ec6  xor     edx, edx; Val
0x180018ec8  lea     rcx, [rsp+248h+var_228]; void *
0x180018ecd  mov     r8d, 208h; Size
0x180018ed3  xor     edi, edi
0x180018ed5  call    memset_0
0x180018eda  call    cs:__imp_GetCurrentProcessId
0x180018ee0  mov     esi, eax
0x180018ee2  test    ebx, ebx
0x180018ee4  jz      short loc_180018F5D
0x180018ee6  lea     ecx, [rdi+1]; int
0x180018ee9  mov     eax, ecx
0x180018eeb  lock xadd cs:dword_1800856AC, eax
0x180018ef3  add     eax, ecx
0x180018ef5  cmp     eax, ecx
0x180018ef7  jnz     loc_180018F97
0x180018efd  call    ?DisablePrintScreen@@YAJH@Z; DisablePrintScreen(int)
0x180018f02  mov     edi, eax
0x180018f04  test    eax, eax
0x180018f06  js      loc_180018F97
0x180018f0c  mov     r9d, esi
0x180018f0f  lea     r8, ?g_wszDRMRegisterContentEventName@@3QBGB; "DRMRegisterContent_%lu"
0x180018f16  mov     edx, 104h; unsigned __int64
0x180018f1b  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x180018f20  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018f25  mov     edi, eax
0x180018f27  test    eax, eax
0x180018f29  js      short loc_180018F97
0x180018f2b  lea     r9, [rsp+248h+var_228]; int
0x180018f30  xor     r8d, r8d; int
0x180018f33  xor     ecx, ecx; lpEventAttributes
0x180018f35  call    ?CreateEventA@DRMOS@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; DRMOS::CreateEventA(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x180018f3a  mov     cs:?g_hDRMRegisterContentEvent@@3PEAXEA, rax; void * g_hDRMRegisterContentEvent
0x180018f41  test    rax, rax
0x180018f44  jnz     short loc_180018F97
0x180018f46  call    cs:__imp_GetLastError
0x180018f4c  mov     edi, eax
0x180018f4e  test    eax, eax
0x180018f50  jle     short loc_180018F97
0x180018f52  movzx   edi, ax
0x180018f55  or      edi, 80070000h
0x180018f5b  jmp     short loc_180018F97
0x180018f5d  or      eax, 0FFFFFFFFh
0x180018f60  lock xadd cs:dword_1800856AC, eax
0x180018f68  cmp     eax, 1
0x180018f6b  jnz     short loc_180018F97
0x180018f6d  xor     ecx, ecx; int
0x180018f6f  call    ?DisablePrintScreen@@YAJH@Z; DisablePrintScreen(int)
0x180018f74  mov     edi, eax
0x180018f76  test    eax, eax
0x180018f78  js      short loc_180018F97
0x180018f7a  mov     rcx, cs:?g_hDRMRegisterContentEvent@@3PEAXEA; hObject
0x180018f81  test    rcx, rcx
0x180018f84  jz      short loc_180018F97
0x180018f86  call    cs:__imp_CloseHandle
0x180018f8c  mov     cs:?g_hDRMRegisterContentEvent@@3PEAXEA, 0; void * g_hDRMRegisterContentEvent
0x180018f97  mov     eax, edi
0x180018f99  mov     rcx, [rsp+248h+var_18]
0x180018fa1  xor     rcx, rsp; StackCookie
0x180018fa4  call    __security_check_cookie
0x180018fa9  lea     r11, [rsp+248h+var_8]
0x180018fb1  mov     rbx, [r11+10h]
0x180018fb5  mov     rsi, [r11+18h]
0x180018fb9  mov     rsp, r11
0x180018fbc  pop     rdi
0x180018fbd  retn
```

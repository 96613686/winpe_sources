# CompareStringInternal(ushort const *,int,ushort const *,int,ulong,COMPARE_STR_RESULT *)

- ea: `0x18001b65c`
- end: `0x18001b803`
- name: `?CompareStringInternal@@YAJPEBGH0HKPEAW4COMPARE_STR_RESULT@@@Z`
- size: `423`
- prototype: `__int64 __usercall@<rax>(LPCWCH lpString1@<rcx>, int@<edx>, const unsigned __int16 *@<r8>, int@<r9d>, unsigned int, enum COMPARE_STR_RESULT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180044870`
- `0x180046728`

## callees

- `0x18001b65c`
- `0x180027448`
- `0x1800274cc`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b777`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18001b76b`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18001b76b`

## string_xrefs

- `0x18001b714`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18001b70d`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18001b69d`: `CompareStringInternal`
- `0x18001b78b`: `CompareStringInternal`
- `0x18001b77f`: `CompareStringEx`

## pseudocode

```c
__int64 __fastcall CompareStringInternal(
        LPCWCH lpString1,
        __int64 a2,
        const unsigned __int16 *lpString2,
        __int64 a4,
        unsigned int a5,
        enum COMPARE_STR_RESULT *a6)
{
  DWORD LastError; // ebx
  __int64 v7; // r8
  unsigned int v8; // eax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  char v13[16]; // [rsp+50h] [rbp-48h] BYREF
  const wchar_t *v14; // [rsp+60h] [rbp-38h]
  __int64 v15; // [rsp+68h] [rbp-30h]
  const wchar_t *v16; // [rsp+70h] [rbp-28h]
  __int64 v17; // [rsp+78h] [rbp-20h]

  if ( !a6 )
  {
    LastError = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CompareStringInternal", L"result");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v14 = L"CompareStringInternal";
      v15 = 44;
      v16 = L"result";
      v17 = 14;
      v8 = McGenEventWrite_EventWriteTransfer(
             &UserDeviceRegistrationEventProvider_Context,
             NullOrEmptyParameterFailureEvent,
             v7,
             3,
             v13);
      if ( v8 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v8);
    }
    return LastError;
  }
  *(_DWORD *)a6 = 0;
  v9 = CompareStringEx(&LocaleName, 1u, lpString1, -1, lpString2, -1, 0, 0, 0);
  if ( v9 )
  {
    LastError = 0;
    v10 = v9 - 1;
    if ( !v10 )
    {
      *(_DWORD *)a6 = 1;
      return LastError;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      *(_DWORD *)a6 = 2;
      return LastError;
    }
    if ( v11 == 1 )
    {
      *(_DWORD *)a6 = 3;
      return LastError;
    }
    LOWORD(LastError) = 1359;
    return (unsigned __int16)LastError | 0x80070000;
  }
  LastError = GetLastError();
  if ( !LastError )
    LastError = 1359;
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"CompareStringInternal",
    L"CompareStringEx",
    LastError);
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x18001b65c  mov     [rsp+arg_8], rbx
0x18001b661  mov     [rsp+arg_18], rbp
0x18001b666  push    rdi
0x18001b667  sub     rsp, 90h
0x18001b66e  mov     rax, cs:__security_cookie
0x18001b675  xor     rax, rsp
0x18001b678  mov     [rsp+98h+var_18], rax
0x18001b680  mov     rdi, [rsp+98h+arg_28]
0x18001b688  test    rdi, rdi
0x18001b68b  jnz     loc_18001B72C
0x18001b691  lea     rbp, aResult; "result"
0x18001b698  mov     ebx, 80070057h
0x18001b69d  lea     rdi, aComparestringi; "CompareStringInternal"
0x18001b6a4  mov     r8, rbp
0x18001b6a7  mov     rdx, rdi
0x18001b6aa  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001b6b1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001b6b6  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18001b6bd  jz      loc_18001B7DC
0x18001b6c3  lea     rax, [rsp+98h+var_48]
0x18001b6c8  mov     [rsp+98h+var_38], rdi
0x18001b6cd  mov     r9d, 3
0x18001b6d3  mov     [rsp+98h+lpString2], rax
0x18001b6d8  lea     rdx, NullOrEmptyParameterFailureEvent
0x18001b6df  mov     [rsp+98h+var_30], 2Ch ; ','
0x18001b6e8  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18001b6ef  mov     [rsp+98h+var_28], rbp
0x18001b6f4  mov     [rsp+98h+var_20], 0Eh
0x18001b6fd  call    McGenEventWrite_EventWriteTransfer
0x18001b702  test    eax, eax
0x18001b704  jz      loc_18001B7DC
0x18001b70a  mov     r9d, eax
0x18001b70d  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18001b714  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18001b71b  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18001b722  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001b727  jmp     loc_18001B7DC
0x18001b72c  mov     [rsp+98h+lParam], 0; lParam
0x18001b735  or      r9d, 0FFFFFFFFh; cchCount1
0x18001b739  mov     [rsp+98h+lpReserved], 0; lpReserved
0x18001b742  mov     [rsp+98h+lpVersionInformation], 0; lpVersionInformation
0x18001b74b  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x18001b750  lea     ebp, [r9+2]
0x18001b754  mov     [rsp+98h+lpString2], r8; lpString2
0x18001b759  mov     r8, rcx; lpString1
0x18001b75c  mov     dword ptr [rdi], 0
0x18001b762  mov     edx, ebp; dwCmpFlags
0x18001b764  lea     rcx, LocaleName; lpLocaleName
0x18001b76b  call    cs:__imp_CompareStringEx
0x18001b771  mov     ecx, eax
0x18001b773  test    eax, eax
0x18001b775  jnz     short loc_18001B7AC
0x18001b777  call    cs:__imp_GetLastError
0x18001b77d  mov     ebx, eax
0x18001b77f  lea     r8, aComparestringe; "CompareStringEx"
0x18001b786  mov     eax, 54Fh
0x18001b78b  lea     rdx, aComparestringi; "CompareStringInternal"
0x18001b792  test    ebx, ebx
0x18001b794  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18001b79b  cmovz   ebx, eax
0x18001b79e  mov     r9d, ebx
0x18001b7a1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001b7a6  test    ebx, ebx
0x18001b7a8  jg      short loc_18001B7BF
0x18001b7aa  jmp     short loc_18001B7DC
0x18001b7ac  xor     ebx, ebx
0x18001b7ae  sub     ecx, ebp
0x18001b7b0  jz      short loc_18001B7DA
0x18001b7b2  sub     ecx, ebp
0x18001b7b4  jz      short loc_18001B7D2
0x18001b7b6  cmp     ecx, ebp
0x18001b7b8  jz      short loc_18001B7CA
0x18001b7ba  mov     ebx, 54Fh
0x18001b7bf  movzx   ebx, bx
0x18001b7c2  or      ebx, 80070000h
0x18001b7c8  jmp     short loc_18001B7DC
0x18001b7ca  mov     dword ptr [rdi], 3
0x18001b7d0  jmp     short loc_18001B7DC
0x18001b7d2  mov     dword ptr [rdi], 2
0x18001b7d8  jmp     short loc_18001B7DC
0x18001b7da  mov     [rdi], ebp
0x18001b7dc  mov     eax, ebx
0x18001b7de  mov     rcx, [rsp+98h+var_18]
0x18001b7e6  xor     rcx, rsp; StackCookie
0x18001b7e9  call    __security_check_cookie
0x18001b7ee  lea     r11, [rsp+98h+var_8]
0x18001b7f6  mov     rbx, [r11+18h]
0x18001b7fa  mov     rbp, [r11+28h]
0x18001b7fe  mov     rsp, r11
0x18001b801  pop     rdi
0x18001b802  retn
```

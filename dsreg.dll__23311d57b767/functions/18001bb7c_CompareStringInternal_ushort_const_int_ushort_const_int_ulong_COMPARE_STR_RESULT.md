# CompareStringInternal(ushort const *,int,ushort const *,int,ulong,COMPARE_STR_RESULT *)

- ea: `0x18001bb7c`
- end: `0x18001bd29`
- name: `?CompareStringInternal@@YAJPEBGH0HKPEAW4COMPARE_STR_RESULT@@@Z`
- size: `429`
- prototype: `__int64 __usercall@<rax>(LPCWCH lpString1@<rcx>, int cchCount1@<edx>, LPCWCH lpString2@<r8>, int@<r9d>, DWORD dwCmpFlags, enum COMPARE_STR_RESULT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18008c9b0`
- `0x1800945a8`

## callees

- `0x1800084f4`
- `0x18000cbd8`
- `0x18001bb7c`
- `0x180044300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcd2`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18001bbe7`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18001bbe7`

## string_xrefs

- `0x18001bc47`: `CompareStringInternal`
- `0x18001bce6`: `CompareStringInternal`
- `0x18001bcda`: `CompareStringEx`
- `0x18001bcba`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18001bcb3`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall CompareStringInternal(
        LPCWCH lpString1,
        int cchCount1,
        LPCWCH lpString2,
        int a4,
        DWORD dwCmpFlags,
        enum COMPARE_STR_RESULT *a6)
{
  int v6; // ecx
  DWORD LastError; // ebx
  int v8; // ecx
  int v9; // ecx
  __int64 v11; // r8
  unsigned int v12; // eax
  char v13[16]; // [rsp+50h] [rbp-58h] BYREF
  const wchar_t *v14; // [rsp+60h] [rbp-48h]
  __int64 v15; // [rsp+68h] [rbp-40h]
  const wchar_t *v16; // [rsp+70h] [rbp-38h]
  __int64 v17; // [rsp+78h] [rbp-30h]

  if ( a6 )
  {
    *(_DWORD *)a6 = 0;
    v6 = CompareStringEx(&cchOriginalDestLength, dwCmpFlags, lpString1, cchCount1, lpString2, a4, 0, 0, 0);
    if ( v6 )
    {
      LastError = 0;
      v8 = v6 - 1;
      if ( !v8 )
      {
        *(_DWORD *)a6 = 1;
        return LastError;
      }
      v9 = v8 - 1;
      if ( !v9 )
      {
        *(_DWORD *)a6 = 2;
        return LastError;
      }
      if ( v9 == 1 )
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
  }
  else
  {
    LastError = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CompareStringInternal", L"result");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v14 = L"CompareStringInternal";
      v15 = 44;
      v16 = L"result";
      v17 = 14;
      v12 = McGenEventWrite_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              NullOrEmptyParameterFailureEvent,
              v11,
              3,
              v13);
      if ( v12 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v12);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18001bb7c  mov     r11, rsp
0x18001bb7f  push    rbx
0x18001bb80  push    rbp
0x18001bb81  push    rdi
0x18001bb82  sub     rsp, 90h
0x18001bb89  mov     rax, cs:__security_cookie
0x18001bb90  xor     rax, rsp
0x18001bb93  mov     [rsp+0A8h+var_28], rax
0x18001bb9b  mov     rdi, [rsp+0A8h+arg_28]
0x18001bba3  test    rdi, rdi
0x18001bba6  jz      loc_18001BC3B
0x18001bbac  mov     qword ptr [r11-68h], 0
0x18001bbb4  mov     qword ptr [r11-70h], 0
0x18001bbbc  mov     qword ptr [r11-78h], 0
0x18001bbc4  mov     [r11-80h], r9d
0x18001bbc8  mov     r9d, edx; cchCount1
0x18001bbcb  mov     edx, [rsp+0A8h+dwCmpFlags]; dwCmpFlags
0x18001bbd2  mov     [rsp+0A8h+lpString2], r8; lpString2
0x18001bbd7  mov     r8, rcx; lpString1
0x18001bbda  lea     rcx, cchOriginalDestLength; lpLocaleName
0x18001bbe1  mov     dword ptr [rdi], 0
0x18001bbe7  call    cs:__imp_CompareStringEx
0x18001bbed  mov     ecx, eax
0x18001bbef  test    eax, eax
0x18001bbf1  jz      loc_18001BCD2
0x18001bbf7  xor     ebx, ebx
0x18001bbf9  sub     ecx, 1
0x18001bbfc  jz      short loc_18001BC33
0x18001bbfe  sub     ecx, 1
0x18001bc01  jz      loc_18001BD1E
0x18001bc07  cmp     ecx, 1
0x18001bc0a  jnz     loc_18001BD0B
0x18001bc10  mov     dword ptr [rdi], 3
0x18001bc16  mov     eax, ebx
0x18001bc18  mov     rcx, [rsp+0A8h+var_28]
0x18001bc20  xor     rcx, rsp; StackCookie
0x18001bc23  call    __security_check_cookie
0x18001bc28  add     rsp, 90h
0x18001bc2f  pop     rdi
0x18001bc30  pop     rbp
0x18001bc31  pop     rbx
0x18001bc32  retn
0x18001bc33  mov     dword ptr [rdi], 1
0x18001bc39  jmp     short loc_18001BC16
0x18001bc3b  lea     rbp, aResult_0; "result"
0x18001bc42  mov     ebx, 80070057h
0x18001bc47  lea     rdi, aComparestringi; "CompareStringInternal"
0x18001bc4e  mov     r8, rbp
0x18001bc51  mov     rdx, rdi
0x18001bc54  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18001bc5b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001bc60  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18001bc67  jz      short loc_18001BC16
0x18001bc69  lea     rax, [rsp+0A8h+var_58]
0x18001bc6e  mov     [rsp+0A8h+var_48], rdi
0x18001bc73  mov     r9d, 3
0x18001bc79  mov     [rsp+0A8h+lpString2], rax
0x18001bc7e  lea     rdx, NullOrEmptyParameterFailureEvent
0x18001bc85  mov     [rsp+0A8h+var_40], 2Ch ; ','
0x18001bc8e  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18001bc95  mov     [rsp+0A8h+var_38], rbp
0x18001bc9a  mov     [rsp+0A8h+var_30], 0Eh
0x18001bca3  call    McGenEventWrite_EventWriteTransfer
0x18001bca8  test    eax, eax
0x18001bcaa  jz      loc_18001BC16
0x18001bcb0  mov     r9d, eax
0x18001bcb3  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18001bcba  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18001bcc1  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001bcc8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001bccd  jmp     loc_18001BC16
0x18001bcd2  call    cs:__imp_GetLastError
0x18001bcd8  mov     ebx, eax
0x18001bcda  lea     r8, aComparestringe; "CompareStringEx"
0x18001bce1  mov     eax, 54Fh
0x18001bce6  lea     rdx, aComparestringi; "CompareStringInternal"
0x18001bced  test    ebx, ebx
0x18001bcef  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001bcf6  cmovz   ebx, eax
0x18001bcf9  mov     r9d, ebx
0x18001bcfc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001bd01  test    ebx, ebx
0x18001bd03  jle     loc_18001BC16
0x18001bd09  jmp     short loc_18001BD10
0x18001bd0b  mov     ebx, 54Fh
0x18001bd10  movzx   ebx, bx
0x18001bd13  or      ebx, 80070000h
0x18001bd19  jmp     loc_18001BC16
0x18001bd1e  mov     dword ptr [rdi], 2
0x18001bd24  jmp     loc_18001BC16
```

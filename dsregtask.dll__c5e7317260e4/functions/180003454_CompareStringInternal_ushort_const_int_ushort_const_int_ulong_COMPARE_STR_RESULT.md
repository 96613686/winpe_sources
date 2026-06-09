# CompareStringInternal(ushort const *,int,ushort const *,int,ulong,COMPARE_STR_RESULT *)

- ea: `0x180003454`
- end: `0x18000356b`
- name: `?CompareStringInternal@@YAJPEBGH0HKPEAW4COMPARE_STR_RESULT@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(LPCWCH lpString1, __int64, const unsigned __int16 *, __int64, unsigned int, enum COMPARE_STR_RESULT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800035d8`

## callees

- `0x180003000`
- `0x1800030ec`
- `0x180003454`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034f2`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800034e6`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800034e6`

## string_xrefs

- `0x1800034ab`: `DeviceUpdate`
- `0x180003477`: `CompareStringInternal`
- `0x180003491`: `CompareStringInternal`
- `0x180003506`: `CompareStringInternal`
- `0x1800034fa`: `CompareStringEx`

## pseudocode

```c
__int64 __fastcall CompareStringInternal(
        LPCWCH lpString1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        enum COMPARE_STR_RESULT *a6)
{
  DWORD LastError; // ebx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx

  if ( !a6 )
  {
    LastError = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CompareStringInternal", L"result");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CompareStringInternal", L"result");
    return LastError;
  }
  *(_DWORD *)a6 = 0;
  v7 = CompareStringEx(&LocaleName, 1u, lpString1, -1, L"DeviceUpdate", -1, 0, 0, 0);
  if ( v7 )
  {
    LastError = 0;
    v8 = v7 - 1;
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
  return LastError;
}

```

## disassembly

```asm
0x180003454  mov     [rsp+arg_0], rbx
0x180003459  push    rdi
0x18000345a  sub     rsp, 50h
0x18000345e  mov     rdi, [rsp+58h+arg_28]
0x180003466  test    rdi, rdi
0x180003469  jnz     short loc_1800034A2
0x18000346b  lea     r8, aResult; "result"
0x180003472  mov     ebx, 80070057h
0x180003477  lea     rdx, aComparestringi; "CompareStringInternal"
0x18000347e  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180003485  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000348a  lea     rdx, aResult; "result"
0x180003491  lea     rcx, aComparestringi; "CompareStringInternal"
0x180003498  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000349d  jmp     loc_18000355E
0x1800034a2  mov     [rsp+58h+lParam], 0; lParam
0x1800034ab  lea     rax, String2; "DeviceUpdate"
0x1800034b2  or      r9d, 0FFFFFFFFh; cchCount1
0x1800034b6  mov     [rsp+58h+lpReserved], 0; lpReserved
0x1800034bf  mov     [rsp+58h+lpVersionInformation], 0; lpVersionInformation
0x1800034c8  mov     r8, rcx; lpString1
0x1800034cb  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x1800034d0  lea     rcx, LocaleName; lpLocaleName
0x1800034d7  mov     dword ptr [rdi], 0
0x1800034dd  lea     edx, [r9+2]; dwCmpFlags
0x1800034e1  mov     [rsp+58h+lpString2], rax; lpString2
0x1800034e6  call    cs:__imp_CompareStringEx
0x1800034ec  mov     ecx, eax
0x1800034ee  test    eax, eax
0x1800034f0  jnz     short loc_180003527
0x1800034f2  call    cs:__imp_GetLastError
0x1800034f8  mov     ebx, eax
0x1800034fa  lea     r8, aComparestringe; "CompareStringEx"
0x180003501  mov     eax, 54Fh
0x180003506  lea     rdx, aComparestringi; "CompareStringInternal"
0x18000350d  test    ebx, ebx
0x18000350f  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180003516  cmovz   ebx, eax
0x180003519  mov     r9d, ebx
0x18000351c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180003521  test    ebx, ebx
0x180003523  jle     short loc_18000355E
0x180003525  jmp     short loc_18000353D
0x180003527  xor     ebx, ebx
0x180003529  sub     ecx, 1
0x18000352c  jz      short loc_180003558
0x18000352e  sub     ecx, 1
0x180003531  jz      short loc_180003550
0x180003533  cmp     ecx, 1
0x180003536  jz      short loc_180003548
0x180003538  mov     ebx, 54Fh
0x18000353d  movzx   ebx, bx
0x180003540  or      ebx, 80070000h
0x180003546  jmp     short loc_18000355E
0x180003548  mov     dword ptr [rdi], 3
0x18000354e  jmp     short loc_18000355E
0x180003550  mov     dword ptr [rdi], 2
0x180003556  jmp     short loc_18000355E
0x180003558  mov     dword ptr [rdi], 1
0x18000355e  mov     eax, ebx
0x180003560  mov     rbx, [rsp+58h+arg_0]
0x180003565  add     rsp, 50h
0x180003569  pop     rdi
0x18000356a  retn
```

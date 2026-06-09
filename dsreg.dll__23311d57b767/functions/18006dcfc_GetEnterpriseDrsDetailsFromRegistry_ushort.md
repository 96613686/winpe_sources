# GetEnterpriseDrsDetailsFromRegistry(ushort * *)

- ea: `0x18006dcfc`
- end: `0x18006de9b`
- name: `?GetEnterpriseDrsDetailsFromRegistry@@YAJPEAPEAG@Z`
- size: `415`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006d100`

## callees

- `0x180006750`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x18000ddf0`
- `0x180012948`
- `0x1800307c4`
- `0x18006dcfc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006dd80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006dd80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006de58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006de58`

## string_xrefs

- `0x18006de2d`: `CopyStringW`
- `0x18006dd8c`: `RegOpenKeyExW`
- `0x18006dd0e`: `GetEnterpriseDrsDetailsFromRegistry`
- `0x18006ddfe`: `%s: enterpriseDrsName NOT found in registry.`

## pseudocode

```c
__int64 __fastcall GetEnterpriseDrsDetailsFromRegistry(unsigned __int16 **a1)
{
  unsigned __int16 *v2; // rsi
  int v3; // edi
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned __int64 v7; // rdx
  int v8; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *Source; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  Source = 0;
  v2 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v4 = 0;
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ", 0, 0x20019u, &hKey);
    v3 = v5;
    if ( v5 )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"GetEnterpriseDrsDetailsFromRegistry",
        L"RegOpenKeyExW",
        v5);
    }
    else
    {
      v6 = RegReadStringValue(
             hKey,
             0,
             L"EnterpriseDrsName",
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ",
             2u,
             &Source);
      v3 = v6;
      if ( v6 )
      {
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"GetEnterpriseDrsDetailsFromRegistry",
          L"GetStringFromRegKey",
          v6);
        v2 = Source;
      }
      else
      {
        v2 = Source;
        if ( Source )
        {
          v7 = -1;
          do
            ++v7;
          while ( Source[v7] );
          v8 = CopyStringW(Source, v7, a1);
          v4 = v8;
          if ( v8 < 0 )
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"GetEnterpriseDrsDetailsFromRegistry",
              L"CopyStringW",
              (unsigned int)v8);
        }
        else
        {
          v4 = 1;
          Logger::TraceInformation(
            L"%s: enterpriseDrsName NOT found in registry.",
            L"GetEnterpriseDrsDetailsFromRegistry");
        }
      }
    }
  }
  else
  {
    v3 = 0;
    v4 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"GetEnterpriseDrsDetailsFromRegistry",
      L"ppszEnterpriseDrsName");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetEnterpriseDrsDetailsFromRegistry", L"ppszEnterpriseDrsName");
  }
  SafeFree(v2);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    else
      v4 = v3;
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"GetEnterpriseDrsDetailsFromRegistry", v4);
  return v4;
}

```

## disassembly

```asm
0x18006dcfc  mov     [rsp+arg_10], rbx
0x18006dd01  push    rbp
0x18006dd02  push    rsi
0x18006dd03  push    rdi
0x18006dd04  push    r14
0x18006dd06  push    r15
0x18006dd08  sub     rsp, 30h
0x18006dd0c  xor     ebp, ebp
0x18006dd0e  lea     r15, aGetenterprised; "GetEnterpriseDrsDetailsFromRegistry"
0x18006dd15  mov     [rsp+58h+hKey], rbp
0x18006dd1a  mov     r14, rcx
0x18006dd1d  mov     [rsp+58h+Source], rbp
0x18006dd22  mov     esi, ebp
0x18006dd24  test    rcx, rcx
0x18006dd27  jnz     short loc_18006DD5A
0x18006dd29  lea     r8, aPpszenterprise; "ppszEnterpriseDrsName"
0x18006dd30  mov     rdx, r15
0x18006dd33  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18006dd3a  mov     edi, ebp
0x18006dd3c  mov     ebx, 80070057h
0x18006dd41  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006dd46  lea     rdx, aPpszenterprise; "ppszEnterpriseDrsName"
0x18006dd4d  mov     rcx, r15; unsigned __int16 *
0x18006dd50  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18006dd55  jmp     loc_18006DE46
0x18006dd5a  mov     [rcx], rbp
0x18006dd5d  lea     rax, [rsp+58h+hKey]
0x18006dd62  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006dd69  mov     [rsp+58h+phkResult], rax; phkResult
0x18006dd6e  mov     r9d, 20019h; samDesired
0x18006dd74  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006dd7b  xor     r8d, r8d; ulOptions
0x18006dd7e  mov     ebx, ebp
0x18006dd80  call    cs:__imp_RegOpenKeyExW
0x18006dd86  mov     edi, eax
0x18006dd88  test    eax, eax
0x18006dd8a  jz      short loc_18006DD9F
0x18006dd8c  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x18006dd93  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18006dd9a  jmp     loc_18006DE3B
0x18006dd9f  mov     rcx, [rsp+58h+hKey]; hkey
0x18006dda4  lea     rax, [rsp+58h+Source]
0x18006dda9  mov     [rsp+58h+var_30], rax; unsigned __int16 **
0x18006ddae  lea     r9, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006ddb5  lea     r8, aEnterprisedrsn; "EnterpriseDrsName"
0x18006ddbc  mov     dword ptr [rsp+58h+phkResult], 2; dwFlags
0x18006ddc4  xor     edx, edx; lpSubKey
0x18006ddc6  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18006ddcb  mov     edi, eax
0x18006ddcd  test    eax, eax
0x18006ddcf  jz      short loc_18006DDF1
0x18006ddd1  mov     r9d, eax
0x18006ddd4  lea     r8, aGetstringfromr; "GetStringFromRegKey"
0x18006dddb  mov     rdx, r15
0x18006ddde  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18006dde5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006ddea  mov     rsi, [rsp+58h+Source]
0x18006ddef  jmp     short loc_18006DE46
0x18006ddf1  mov     rsi, [rsp+58h+Source]
0x18006ddf6  test    rsi, rsi
0x18006ddf9  jnz     short loc_18006DE0F
0x18006ddfb  mov     rdx, r15
0x18006ddfe  lea     rcx, aSEnterprisedrs; "%s: enterpriseDrsName NOT found in regi"...
0x18006de05  lea     ebx, [rsi+1]
0x18006de08  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18006de0d  jmp     short loc_18006DE46
0x18006de0f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006de13  inc     rdx; unsigned __int64
0x18006de16  cmp     [rsi+rdx*2], bp
0x18006de1a  jnz     short loc_18006DE13
0x18006de1c  mov     r8, r14; unsigned __int16 **
0x18006de1f  mov     rcx, rsi; Source
0x18006de22  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x18006de27  mov     ebx, eax
0x18006de29  test    eax, eax
0x18006de2b  jns     short loc_18006DE46
0x18006de2d  lea     r8, aCopystringw; "CopyStringW"
0x18006de34  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006de3b  mov     r9d, eax
0x18006de3e  mov     rdx, r15
0x18006de41  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006de46  mov     rcx, rsi; lpMem
0x18006de49  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18006de4e  mov     rcx, [rsp+58h+hKey]; hKey
0x18006de53  test    rcx, rcx
0x18006de56  jz      short loc_18006DE63
0x18006de58  call    cs:__imp_RegCloseKey
0x18006de5e  mov     [rsp+58h+hKey], rbp
0x18006de63  test    edi, edi
0x18006de65  jz      short loc_18006DE76
0x18006de67  jg      short loc_18006DE6D
0x18006de69  mov     ebx, edi
0x18006de6b  jmp     short loc_18006DE76
0x18006de6d  movzx   ebx, di
0x18006de70  or      ebx, 80070000h
0x18006de76  mov     r8d, ebx
0x18006de79  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18006de80  mov     rdx, r15
0x18006de83  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18006de88  mov     eax, ebx
0x18006de8a  mov     rbx, [rsp+58h+arg_10]
0x18006de8f  add     rsp, 30h
0x18006de93  pop     r15
0x18006de95  pop     r14
0x18006de97  pop     rdi
0x18006de98  pop     rsi
0x18006de99  pop     rbp
0x18006de9a  retn
```

# OmaDmCloseSession

- ea: `0x180015bb0`
- end: `0x180015d2e`
- name: `OmaDmCloseSession`
- size: `382`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019684`
- `0x18001e698`

## callees

- `0x1800031b0`
- `0x18000e004`
- `0x18000ef50`
- `0x180014514`
- `0x180014570`
- `0x180014698`
- `0x180015bb0`
- `0x180016a10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180015c81`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180015ca8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180015c81`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180015ca8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ce5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ce5`
- `DMCmnUtils!CopyString` at `0x180015c63`
- `DMCmnUtils!CopyString` at `0x180015c63`

## pseudocode

```c
__int64 __fastcall OmaDmCloseSession(LPCWSTR lpSubKey, __int64 a2, __int64 a3)
{
  int v4; // ebx
  wchar_t *v5; // rax
  wchar_t *v6; // rax
  __int64 v7; // rcx
  wchar_t *Str; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+38h] [rbp-30h] BYREF
  const wchar_t *v11; // [rsp+48h] [rbp-20h]
  __int64 v12; // [rsp+50h] [rbp-18h]

  Str = 0;
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
  {
    v11 = L"OmaDmCloseSession";
    v12 = 36;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADMAPI_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)FunctionEntryPointEvent,
      a3,
      2u,
      &v10);
  }
  if ( !lpSubKey )
  {
    v4 = 0;
    goto LABEL_16;
  }
  if ( !(unsigned int)IsValidInitiationID(lpSubKey) )
    goto LABEL_6;
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_OMADMAPI_PROVIDER_Context, OmaDmCloseSessionEvent, lpSubKey);
  v4 = CopyString(lpSubKey, 0xFFFFFFFF, &Str);
  if ( v4 >= 0 )
  {
    v5 = wcsrchr(Str, 0x5Cu);
    if ( !v5 || v5 == Str || (*v5 = 0, (v6 = wcsrchr(Str, 0x5Cu)) == 0) || v6 == Str )
    {
LABEL_6:
      v4 = -2147024809;
      goto LABEL_16;
    }
    v4 = OmaDmCloseSession_Impl(lpSubKey);
    if ( v4 >= 0 )
      v4 = OmaDmDeleteSessionPolicy(lpSubKey);
  }
LABEL_16:
  LocalFree(Str);
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v7, FunctionReturnValueEvent, L"OmaDmCloseSession", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015bb0  mov     r11, rsp
0x180015bb3  mov     [r11+10h], rbx
0x180015bb7  mov     [r11+18h], rsi
0x180015bbb  push    rdi
0x180015bbc  sub     rsp, 60h
0x180015bc0  mov     rax, cs:__security_cookie
0x180015bc7  xor     rax, rsp
0x180015bca  mov     [rsp+68h+var_10], rax
0x180015bcf  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180015bd6  lea     rsi, aOmadmclosesess_1; "OmaDmCloseSession"
0x180015bdd  mov     rdi, rcx
0x180015be0  mov     qword ptr [r11-38h], 0
0x180015be8  jz      short loc_180015C17
0x180015bea  lea     rax, [r11-30h]
0x180015bee  mov     [r11-20h], rsi
0x180015bf2  mov     r9d, 2
0x180015bf8  mov     [r11-48h], rax
0x180015bfc  lea     rdx, FunctionEntryPointEvent
0x180015c03  mov     qword ptr [r11-18h], 24h ; '$'
0x180015c0b  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x180015c12  call    McGenEventWrite_EventWriteTransfer
0x180015c17  test    rdi, rdi
0x180015c1a  jnz     short loc_180015C23
0x180015c1c  xor     ebx, ebx
0x180015c1e  jmp     loc_180015CE0
0x180015c23  mov     rcx, rdi
0x180015c26  call    IsValidInitiationID
0x180015c2b  test    eax, eax
0x180015c2d  jnz     short loc_180015C39
0x180015c2f  mov     ebx, 80070057h
0x180015c34  jmp     loc_180015CE0
0x180015c39  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 2
0x180015c40  jz      short loc_180015C58
0x180015c42  mov     r8, rdi
0x180015c45  lea     rdx, OmaDmCloseSessionEvent
0x180015c4c  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x180015c53  call    McTemplateU0z_EventWriteTransfer
0x180015c58  lea     r8, [rsp+68h+Str]
0x180015c5d  or      edx, 0FFFFFFFFh
0x180015c60  mov     rcx, rdi
0x180015c63  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180015c6a  nop     dword ptr [rax+rax+00h]
0x180015c6f  mov     ebx, eax
0x180015c71  test    eax, eax
0x180015c73  js      short loc_180015CE0
0x180015c75  mov     rcx, [rsp+68h+Str]; Str
0x180015c7a  mov     ebx, 5Ch ; '\'
0x180015c7f  mov     edx, ebx; Ch
0x180015c81  call    cs:__imp_wcsrchr
0x180015c88  nop     dword ptr [rax+rax+00h]
0x180015c8d  mov     rcx, rax
0x180015c90  test    rax, rax
0x180015c93  jz      short loc_180015C2F
0x180015c95  cmp     rax, [rsp+68h+Str]
0x180015c9a  jz      short loc_180015C2F
0x180015c9c  xor     eax, eax
0x180015c9e  mov     edx, ebx; Ch
0x180015ca0  mov     [rcx], ax
0x180015ca3  mov     rcx, [rsp+68h+Str]; Str
0x180015ca8  call    cs:__imp_wcsrchr
0x180015caf  nop     dword ptr [rax+rax+00h]
0x180015cb4  test    rax, rax
0x180015cb7  jz      loc_180015C2F
0x180015cbd  cmp     rax, [rsp+68h+Str]
0x180015cc2  jz      loc_180015C2F
0x180015cc8  mov     rcx, rdi; lpSubKey
0x180015ccb  call    ?OmaDmCloseSession_Impl@@YAJPEBG@Z; OmaDmCloseSession_Impl(ushort const *)
0x180015cd0  mov     ebx, eax
0x180015cd2  test    eax, eax
0x180015cd4  js      short loc_180015CE0
0x180015cd6  mov     rcx, rdi
0x180015cd9  call    OmaDmDeleteSessionPolicy
0x180015cde  mov     ebx, eax
0x180015ce0  mov     rcx, [rsp+68h+Str]; hMem
0x180015ce5  call    cs:__imp_LocalFree
0x180015cec  nop     dword ptr [rax+rax+00h]
0x180015cf1  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180015cf8  jz      short loc_180015D0C
0x180015cfa  mov     r9d, ebx
0x180015cfd  lea     rdx, FunctionReturnValueEvent
0x180015d04  mov     r8, rsi
0x180015d07  call    McTemplateU0zq_EventWriteTransfer
0x180015d0c  mov     eax, ebx
0x180015d0e  mov     rcx, [rsp+68h+var_10]
0x180015d13  xor     rcx, rsp; StackCookie
0x180015d16  call    __security_check_cookie
0x180015d1b  lea     r11, [rsp+68h+var_8]
0x180015d20  mov     rbx, [r11+18h]
0x180015d24  mov     rsi, [r11+20h]
0x180015d28  mov     rsp, r11
0x180015d2b  pop     rdi
0x180015d2c  retn
```

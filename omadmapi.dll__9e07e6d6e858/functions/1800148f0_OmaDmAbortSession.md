# OmaDmAbortSession

- ea: `0x1800148f0`
- end: `0x180014a50`
- name: `OmaDmAbortSession`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180016160`

## callees

- `0x1800031b0`
- `0x18000e004`
- `0x180014514`
- `0x180014570`
- `0x180014698`
- `0x1800148f0`
- `0x180014a60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800149b9`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800149e0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800149b9`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800149e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a07`
- `DMCmnUtils!CopyString` at `0x18001499b`
- `DMCmnUtils!CopyString` at `0x18001499b`

## pseudocode

```c
__int64 __fastcall OmaDmAbortSession(const unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  char v3; // al
  int v5; // ebx
  wchar_t *v6; // rax
  wchar_t *v7; // rax
  __int64 v8; // rcx
  wchar_t *Str; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+38h] [rbp-30h] BYREF
  const wchar_t *v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-18h]

  v3 = Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits;
  Str = 0;
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
  {
    v12 = L"OmaDmAbortSession";
    v13 = 36;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADMAPI_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)FunctionEntryPointEvent,
      a3,
      2u,
      &v11);
    v3 = Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits;
  }
  if ( (v3 & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_OMADMAPI_PROVIDER_Context, OmaDmAbortSessionEvent, a1);
  if ( !a1 )
  {
LABEL_13:
    v5 = OmaDmAbortSession_Impl(a1);
    goto LABEL_14;
  }
  if ( !(unsigned int)IsValidInitiationID(a1) )
  {
LABEL_7:
    v5 = -2147024809;
    goto LABEL_14;
  }
  v5 = CopyString(a1, 0xFFFFFFFF, &Str);
  if ( v5 >= 0 )
  {
    v6 = wcsrchr(Str, 0x5Cu);
    if ( !v6 )
      goto LABEL_7;
    if ( v6 == Str )
      goto LABEL_7;
    *v6 = 0;
    v7 = wcsrchr(Str, 0x5Cu);
    if ( !v7 || v7 == Str )
      goto LABEL_7;
    goto LABEL_13;
  }
LABEL_14:
  LocalFree(Str);
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v8, FunctionReturnValueEvent, L"OmaDmAbortSession", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800148f0  mov     r11, rsp
0x1800148f3  mov     [r11+10h], rbx
0x1800148f7  mov     [r11+18h], rsi
0x1800148fb  push    rdi
0x1800148fc  sub     rsp, 60h
0x180014900  mov     rax, cs:__security_cookie
0x180014907  xor     rax, rsp
0x18001490a  mov     [rsp+68h+var_10], rax
0x18001490f  mov     eax, cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits
0x180014915  lea     rsi, aOmadmabortsess_1; "OmaDmAbortSession"
0x18001491c  mov     qword ptr [r11-38h], 0
0x180014924  mov     rdi, rcx
0x180014927  test    al, 1
0x180014929  jz      short loc_18001495E
0x18001492b  lea     rax, [r11-30h]
0x18001492f  mov     [r11-20h], rsi
0x180014933  mov     r9d, 2
0x180014939  mov     [r11-48h], rax
0x18001493d  lea     rdx, FunctionEntryPointEvent
0x180014944  mov     qword ptr [r11-18h], 24h ; '$'
0x18001494c  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x180014953  call    McGenEventWrite_EventWriteTransfer
0x180014958  mov     eax, cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits
0x18001495e  test    al, 2
0x180014960  jz      short loc_180014978
0x180014962  mov     r8, rdi
0x180014965  lea     rdx, OmaDmAbortSessionEvent
0x18001496c  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x180014973  call    McTemplateU0z_EventWriteTransfer
0x180014978  test    rdi, rdi
0x18001497b  jz      short loc_1800149F8
0x18001497d  mov     rcx, rdi
0x180014980  call    IsValidInitiationID
0x180014985  test    eax, eax
0x180014987  jnz     short loc_180014990
0x180014989  mov     ebx, 80070057h
0x18001498e  jmp     short loc_180014A02
0x180014990  lea     r8, [rsp+68h+Str]
0x180014995  or      edx, 0FFFFFFFFh
0x180014998  mov     rcx, rdi
0x18001499b  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800149a2  nop     dword ptr [rax+rax+00h]
0x1800149a7  mov     ebx, eax
0x1800149a9  test    eax, eax
0x1800149ab  js      short loc_180014A02
0x1800149ad  mov     rcx, [rsp+68h+Str]; Str
0x1800149b2  mov     ebx, 5Ch ; '\'
0x1800149b7  mov     edx, ebx; Ch
0x1800149b9  call    cs:__imp_wcsrchr
0x1800149c0  nop     dword ptr [rax+rax+00h]
0x1800149c5  mov     rcx, rax
0x1800149c8  test    rax, rax
0x1800149cb  jz      short loc_180014989
0x1800149cd  cmp     rax, [rsp+68h+Str]
0x1800149d2  jz      short loc_180014989
0x1800149d4  xor     eax, eax
0x1800149d6  mov     edx, ebx; Ch
0x1800149d8  mov     [rcx], ax
0x1800149db  mov     rcx, [rsp+68h+Str]; Str
0x1800149e0  call    cs:__imp_wcsrchr
0x1800149e7  nop     dword ptr [rax+rax+00h]
0x1800149ec  test    rax, rax
0x1800149ef  jz      short loc_180014989
0x1800149f1  cmp     rax, [rsp+68h+Str]
0x1800149f6  jz      short loc_180014989
0x1800149f8  mov     rcx, rdi
0x1800149fb  call    OmaDmAbortSession_Impl
0x180014a00  mov     ebx, eax
0x180014a02  mov     rcx, [rsp+68h+Str]; hMem
0x180014a07  call    cs:__imp_LocalFree
0x180014a0e  nop     dword ptr [rax+rax+00h]
0x180014a13  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180014a1a  jz      short loc_180014A2E
0x180014a1c  mov     r9d, ebx
0x180014a1f  lea     rdx, FunctionReturnValueEvent
0x180014a26  mov     r8, rsi
0x180014a29  call    McTemplateU0zq_EventWriteTransfer
0x180014a2e  mov     eax, ebx
0x180014a30  mov     rcx, [rsp+68h+var_10]
0x180014a35  xor     rcx, rsp; StackCookie
0x180014a38  call    __security_check_cookie
0x180014a3d  lea     r11, [rsp+68h+var_8]
0x180014a42  mov     rbx, [r11+18h]
0x180014a46  mov     rsi, [r11+20h]
0x180014a4a  mov     rsp, r11
0x180014a4d  pop     rdi
0x180014a4e  retn
```

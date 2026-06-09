# Microsoft::InformationProtection::HrFindServiceLocation(ulong,uint,ushort * *)

- ea: `0x18005aadc`
- end: `0x18005ac38`
- name: `?HrFindServiceLocation@InformationProtection@Microsoft@@YAJKIPEAPEAG@Z`
- size: `348`
- prototype: `__int64 __fastcall(DRMHSESSION hClient, UINT uServiceType, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005ad7c`
- `0x18005b2e0`

## callees

- `0x180015438`
- `0x18001c1c0`
- `0x18005a9cc`
- `0x18005aadc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ab7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ab7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ab6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ab6c`

## string_xrefs

- `0x18005abc4`: `Microsoft::InformationProtection::HrFindServiceLocation`
- `0x18005abe2`: `Microsoft::InformationProtection::HrFindServiceLocation`
- `0x18005ac0d`: `Microsoft::InformationProtection::HrFindServiceLocation`

## pseudocode

```c
__int64 __fastcall Microsoft::InformationProtection::HrFindServiceLocation(
        DRMHSESSION hClient,
        UINT uServiceType,
        WCHAR **a3,
        unsigned __int16 **a4)
{
  HRESULT v7; // eax
  int v8; // ebx
  __int64 v9; // r8
  unsigned __int64 v10; // rax
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *wszServiceURL; // rax
  Microsoft::InformationProtection *v15; // rcx
  UINT puServiceURLLength; // [rsp+88h] [rbp+20h] BYREF

  puServiceURLLength = 0;
  if ( !hClient || !a3 )
  {
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S Exited with hr = 0x%x",
      "Microsoft::InformationProtection::HrFindServiceLocation",
      2147942487LL,
      a4);
    return 2147942487LL;
  }
  v7 = DRMGetServiceLocation(hClient, uServiceType, 2u, 0, &puServiceURLLength, 0);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 41;
LABEL_11:
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
      "Microsoft::InformationProtection::HrFindServiceLocation",
      v9,
      (unsigned int)v7);
    goto LABEL_14;
  }
  v10 = puServiceURLLength + 1LL;
  if ( v10 > 0xFFFFFFFF )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0xFFFFFFFFLL);
  if ( !is_mul_ok(2u, v10) )
  {
    try
    {
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(2LL * (unsigned int)v10);
    }
    catch ( ... )
    {
      Microsoft::InformationProtection::HandleException(v15);
    }
  }
  v11 = 2 * v10;
  ProcessHeap = GetProcessHeap();
  wszServiceURL = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v11);
  *a3 = wszServiceURL;
  if ( wszServiceURL )
  {
    v7 = DRMGetServiceLocation(hClient, uServiceType, 2u, 0, &puServiceURLLength, wszServiceURL);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 52;
      goto LABEL_11;
    }
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_14:
  if ( v8 < 0 )
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
      "Microsoft::InformationProtection::HrFindServiceLocation",
      59,
      (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005aadc  mov     rax, rsp
0x18005aadf  push    rbx
0x18005aae0  push    rsi
0x18005aae1  push    rdi
0x18005aae2  push    r14
0x18005aae4  sub     rsp, 48h
0x18005aae8  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18005aaf0  mov     rsi, r8
0x18005aaf3  mov     r14d, edx
0x18005aaf6  mov     edi, ecx
0x18005aaf8  mov     dword ptr [rax+20h], 0
0x18005aaff  test    ecx, ecx
0x18005ab01  jz      loc_18005ABDA
0x18005ab07  test    r8, r8
0x18005ab0a  jz      loc_18005ABDA
0x18005ab10  mov     qword ptr [rax-40h], 0
0x18005ab18  lea     rax, [rax+20h]
0x18005ab1c  mov     [rsp+68h+puServiceURLLength], rax; puServiceURLLength
0x18005ab21  xor     r9d, r9d; wszIssuanceLicense
0x18005ab24  lea     r8d, [r9+2]; uServiceLocation
0x18005ab28  call    DRMGetServiceLocation
0x18005ab2d  mov     ebx, eax
0x18005ab2f  test    eax, eax
0x18005ab31  jns     short loc_18005AB3E
0x18005ab33  mov     r8d, 29h ; ')'
0x18005ab39  jmp     loc_18005ABC1
0x18005ab3e  mov     eax, [rsp+68h+arg_18]
0x18005ab45  inc     rax
0x18005ab48  mov     ecx, 0FFFFFFFFh
0x18005ab4d  cmp     rax, rcx
0x18005ab50  ja      loc_18005AC31
0x18005ab56  mov     ecx, eax
0x18005ab58  add     rcx, rcx
0x18005ab5b  mov     rax, rcx
0x18005ab5e  shr     rax, 20h
0x18005ab62  test    eax, eax
0x18005ab64  jnz     loc_18005AC2C
0x18005ab6a  mov     ebx, ecx
0x18005ab6c  call    cs:__imp_GetProcessHeap
0x18005ab72  mov     r8d, ebx; dwBytes
0x18005ab75  mov     edx, 8; dwFlags
0x18005ab7a  mov     rcx, rax; hHeap
0x18005ab7d  call    cs:__imp_HeapAlloc
0x18005ab83  mov     [rsi], rax
0x18005ab86  test    rax, rax
0x18005ab89  jnz     short loc_18005AB92
0x18005ab8b  mov     ebx, 8007000Eh
0x18005ab90  jmp     short loc_18005ABD8
0x18005ab92  mov     [rsp+68h+wszServiceURL], rax; wszServiceURL
0x18005ab97  lea     rax, [rsp+68h+arg_18]
0x18005ab9f  mov     [rsp+68h+puServiceURLLength], rax; puServiceURLLength
0x18005aba4  xor     r9d, r9d; wszIssuanceLicense
0x18005aba7  lea     r8d, [r9+2]; uServiceLocation
0x18005abab  mov     edx, r14d; uServiceType
0x18005abae  mov     ecx, edi; hClient
0x18005abb0  call    DRMGetServiceLocation
0x18005abb5  mov     ebx, eax
0x18005abb7  test    eax, eax
0x18005abb9  jns     short loc_18005ABD8
0x18005abbb  mov     r8d, 34h ; '4'
0x18005abc1  mov     r9d, eax
0x18005abc4  lea     rdx, aMicrosoftInfor_28; "Microsoft::InformationProtection::HrFin"...
0x18005abcb  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x18005abd2  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005abd7  nop
0x18005abd8  jmp     short loc_18005AC00
0x18005abda  mov     ebx, 80070057h
0x18005abdf  mov     r8d, ebx
0x18005abe2  lea     rdx, aMicrosoftInfor_28; "Microsoft::InformationProtection::HrFin"...
0x18005abe9  lea     rcx, aSExitedWithHr0; "%S Exited with hr = 0x%x"
0x18005abf0  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005abf5  mov     eax, ebx
0x18005abf7  jmp     short loc_18005AC22
0x18005abf9  mov     ebx, [rsp+68h+arg_18]
0x18005ac00  test    ebx, ebx
0x18005ac02  jns     short loc_18005AC20
0x18005ac04  mov     r9d, ebx
0x18005ac07  mov     r8d, 3Bh ; ';'
0x18005ac0d  lea     rdx, aMicrosoftInfor_28; "Microsoft::InformationProtection::HrFin"...
0x18005ac14  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x18005ac1b  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005ac20  mov     eax, ebx
0x18005ac22  add     rsp, 48h
0x18005ac26  pop     r14
0x18005ac28  pop     rdi
0x18005ac29  pop     rsi
0x18005ac2a  pop     rbx
0x18005ac2b  retn
0x18005ac2c  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18005ac31  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```

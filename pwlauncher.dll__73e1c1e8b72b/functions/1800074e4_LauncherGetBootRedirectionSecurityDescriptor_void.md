# LauncherGetBootRedirectionSecurityDescriptor(void * *)

- ea: `0x1800074e4`
- end: `0x1800075f4`
- name: `?LauncherGetBootRedirectionSecurityDescriptor@@YAHPEAPEAX@Z`
- size: `272`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *SecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005c98`

## callees

- `0x180005528`
- `0x1800074e4`
- `0x180008ac8`
- `0x180008cf0`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180007535`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180007535`
- `KERNEL32!GetLastError` at `0x180007541`
- `KERNEL32!GetLastError` at `0x1800075a2`
- `KERNEL32!GetLastError` at `0x180007541`
- `KERNEL32!GetLastError` at `0x1800075a2`
- `KERNEL32!SetLastError` at `0x18000758a`
- `KERNEL32!SetLastError` at `0x18000758a`

## string_xrefs

- `0x180007566`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall LauncherGetBootRedirectionSecurityDescriptor(PSECURITY_DESCRIPTOR *SecurityDescriptor)
{
  unsigned int v2; // ebx
  DWORD LastError; // eax
  DWORD v4; // edi
  int v5; // r8d
  int v6; // r9d
  const char *v7; // rcx
  char v9; // [rsp+30h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:BAD:P(A;;0xd01301bf;;;BA)(A;;0x1200a9;;;SY)(A;;0x1200a9;;;BU)S:(AU;SAFA;DCLCRPCRSDWDWO;;;WD)",
         1u,
         SecurityDescriptor,
         0) )
  {
    v4 = 0;
    v2 = 1;
  }
  else
  {
    v2 = 0;
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        164,
        LastError);
  }
  SetLastError(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v9 = GetLastError();
    v7 = "Success";
    if ( !v2 )
      v7 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v5, v6, 171, (__int64)v7, v9);
  }
  return v2;
}

```

## disassembly

```asm
0x1800074e4  mov     [rsp+arg_0], rbx
0x1800074e9  mov     [rsp+arg_8], rsi
0x1800074ee  push    rdi
0x1800074ef  sub     rsp, 40h
0x1800074f3  mov     rbx, rcx
0x1800074f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074fd  lea     rsi, WPP_GLOBAL_Control
0x180007504  cmp     rcx, rsi
0x180007507  jz      short loc_180007524
0x180007509  test    byte ptr [rcx+1Ch], 8
0x18000750d  jz      short loc_180007524
0x18000750f  mov     rcx, [rcx+10h]
0x180007513  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x18000751a  mov     edx, 33h ; '3'
0x18000751f  call    WPP_SF_
0x180007524  xor     r9d, r9d; SecurityDescriptorSize
0x180007527  lea     rcx, StringSecurityDescriptor; "O:BAD:P(A;;0xd01301bf;;;BA)(A;;0x1200a9"...
0x18000752e  mov     r8, rbx; SecurityDescriptor
0x180007531  lea     edx, [r9+1]; StringSDRevision
0x180007535  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000753b  test    eax, eax
0x18000753d  jnz     short loc_180007583
0x18000753f  xor     ebx, ebx
0x180007541  call    cs:__imp_GetLastError
0x180007547  mov     edi, eax
0x180007549  mov     rcx, cs:WPP_GLOBAL_Control
0x180007550  cmp     rcx, rsi
0x180007553  jz      short loc_180007588
0x180007555  test    byte ptr [rcx+1Ch], 1
0x180007559  jz      short loc_180007588
0x18000755b  mov     rcx, [rcx+10h]
0x18000755f  lea     edx, [rbx+34h]
0x180007562  mov     dword ptr [rsp+48h+var_20], eax
0x180007566  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x18000756d  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180007574  mov     [rsp+48h+var_28], 2A4h
0x18000757c  call    WPP_SF_sdD
0x180007581  jmp     short loc_180007588
0x180007583  xor     edi, edi
0x180007585  lea     ebx, [rdi+1]
0x180007588  mov     ecx, edi; dwErrCode
0x18000758a  call    cs:__imp_SetLastError
0x180007590  mov     rax, cs:WPP_GLOBAL_Control
0x180007597  cmp     rax, rsi
0x18000759a  jz      short loc_1800075E2
0x18000759c  test    byte ptr [rax+1Ch], 4
0x1800075a0  jz      short loc_1800075E2
0x1800075a2  call    cs:__imp_GetLastError
0x1800075a8  lea     rdx, aFailure; "Failure"
0x1800075af  mov     dword ptr [rsp+48h+var_18], eax
0x1800075b3  test    ebx, ebx
0x1800075b5  lea     rcx, aSuccess; "Success"
0x1800075bc  cmovz   rcx, rdx
0x1800075c0  mov     edx, 35h ; '5'
0x1800075c5  mov     [rsp+48h+var_20], rcx
0x1800075ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075d1  mov     [rsp+48h+var_28], 2ABh
0x1800075d9  mov     rcx, [rcx+10h]
0x1800075dd  call    WPP_SF_sdsd
0x1800075e2  mov     rsi, [rsp+48h+arg_8]
0x1800075e7  mov     eax, ebx
0x1800075e9  mov     rbx, [rsp+48h+arg_0]
0x1800075ee  add     rsp, 40h
0x1800075f2  pop     rdi
0x1800075f3  retn
```

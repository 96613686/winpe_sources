# ProvWriteAndTrackLockScreenText(ushort const *)

- ea: `0x180029f08`
- end: `0x18002a16a`
- name: `?ProvWriteAndTrackLockScreenText@@YAJPEBG@Z`
- size: `610`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017d8c`

## callees

- `0x180007674`
- `0x18001434c`
- `0x180017914`
- `0x180029f08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180029fc5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a066`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180029fc5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029ff6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a097`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a116`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a125`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029ff6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a097`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a116`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a125`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a01e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a0bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a0f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a01e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a0bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a0f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
__int64 __fastcall ProvWriteAndTrackLockScreenText(BYTE *lpData)
{
  BYTE *v2; // rax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  unsigned __int64 v5; // rbx
  char IsStateSeparationEnabled; // al
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v13; // rdx
  int dwOptions; // [rsp+20h] [rbp-30h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-30h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int Data; // [rsp+70h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+30h] BYREF

  if ( !lpData )
  {
    v4 = -2147024809;
LABEL_32:
    v13 = 20;
    goto LABEL_33;
  }
  v2 = lpData;
  v3 = 0x7FFFFFFF;
  do
  {
    if ( !*(_WORD *)v2 )
      break;
    v2 += 2;
    --v3;
  }
  while ( v3 );
  v4 = v3 == 0 ? 0x80070057 : 0;
  if ( !v3 )
    goto LABEL_32;
  v5 = (2 * (0x7FFFFFFF - v3)) & -(__int64)(v3 != 0);
  if ( !v5 )
    return 0;
  if ( v5 <= 0xFFFFFFFF )
  {
    hKey = 0;
    IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
    v7 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\";
    if ( !IsStateSeparationEnabled )
      v7 = L"SOFTWARE\\Microsoft\\Provisioning\\";
    v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    if ( v8 )
    {
      v9 = 34;
LABEL_12:
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\admin\\prov\\lib\\lockscreenstatus.cpp",
             (const char *)v8,
             dwOptionsa);
LABEL_13:
      if ( hKey )
        RegCloseKey(hKey);
      return v4;
    }
    v8 = RegSetValueExW(hKey, L"LostModeMessage", 0, 1u, lpData, v5);
    if ( v8 )
    {
      v9 = 37;
      goto LABEL_12;
    }
    phkResult = 0;
    v10 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\LostMode",
            0,
            0,
            0,
            0x20006u,
            0,
            &phkResult,
            0);
    if ( v10 )
    {
      v11 = 42;
      goto LABEL_19;
    }
    v10 = RegSetValueExW(phkResult, L"LostModeMessage", 0, 1u, lpData, v5);
    if ( v10 )
    {
      v11 = 45;
      goto LABEL_19;
    }
    Data = 1;
    v10 = RegSetValueExW(phkResult, L"EnableLostMode", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v10 )
    {
      v11 = 49;
LABEL_19:
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"onecoreuap\\admin\\prov\\lib\\lockscreenstatus.cpp",
             (const char *)v10,
             dwOptionsb);
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_13;
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  v4 = -2147024362;
  v13 = 28;
LABEL_33:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\admin\\prov\\lib\\lockscreenstatus.cpp",
    (const char *)v4,
    dwOptions);
  return v4;
}

```

## disassembly

```asm
0x180029f08  mov     [rsp-18h+arg_18], rbx
0x180029f0d  push    rbp
0x180029f0e  push    rsi
0x180029f0f  push    rdi
0x180029f10  mov     rbp, rsp
0x180029f13  sub     rsp, 50h
0x180029f17  xor     esi, esi
0x180029f19  mov     rdi, rcx
0x180029f1c  test    rcx, rcx
0x180029f1f  jz      loc_18002A13B
0x180029f25  mov     r8d, 7FFFFFFFh
0x180029f2b  mov     rax, rcx
0x180029f2e  mov     edx, r8d
0x180029f31  cmp     [rax], si
0x180029f34  jz      short loc_180029F40
0x180029f36  add     rax, 2
0x180029f3a  sub     rdx, 1
0x180029f3e  jnz     short loc_180029F31
0x180029f40  mov     rax, rdx
0x180029f43  neg     rax
0x180029f46  sbb     ebx, ebx
0x180029f48  not     ebx
0x180029f4a  and     ebx, 80070057h
0x180029f50  test    rdx, rdx
0x180029f53  jz      loc_18002A140
0x180029f59  sub     r8, rdx
0x180029f5c  add     r8, r8
0x180029f5f  neg     rdx
0x180029f62  sbb     rbx, rbx
0x180029f65  and     rbx, r8
0x180029f68  jz      loc_18002A12B
0x180029f6e  mov     eax, 0FFFFFFFFh
0x180029f73  cmp     rbx, rax
0x180029f76  ja      loc_18002A12F
0x180029f7c  mov     [rbp+hKey], rsi
0x180029f80  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180029f85  mov     [rsp+50h+lpdwDisposition], rsi; lpdwDisposition
0x180029f8a  lea     rcx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Provisioning\\"
0x180029f91  test    al, al
0x180029f93  lea     rdx, aOsdataSoftware_5; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x180029f9a  lea     rax, [rbp+hKey]
0x180029f9e  mov     [rsp+50h+phkResult], rax; phkResult
0x180029fa3  cmovz   rdx, rcx; lpSubKey
0x180029fa7  mov     [rsp+50h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180029fac  xor     r9d, r9d; lpClass
0x180029faf  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x180029fb7  xor     r8d, r8d; Reserved
0x180029fba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029fc1  mov     [rsp+50h+dwOptions], esi; unsigned int
0x180029fc5  call    cs:__imp_RegCreateKeyExW
0x180029fcb  test    eax, eax
0x180029fcd  jz      short loc_18002A001
0x180029fcf  mov     edx, 22h ; '"'; void *
0x180029fd4  mov     rcx, [rbp+18h]; this
0x180029fd8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x180029fdf  mov     r9d, eax; char *
0x180029fe2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180029fe7  mov     ebx, eax
0x180029fe9  mov     rcx, [rbp+hKey]; hKey
0x180029fed  test    rcx, rcx
0x180029ff0  jz      loc_18002A158
0x180029ff6  call    cs:__imp_RegCloseKey
0x180029ffc  jmp     loc_18002A158
0x18002a001  mov     rcx, [rbp+hKey]; hKey
0x18002a005  lea     rdx, aLostmodemessag; "LostModeMessage"
0x18002a00c  mov     [rsp+50h+samDesired], ebx; cbData
0x18002a010  mov     r9d, 1; dwType
0x18002a016  xor     r8d, r8d; Reserved
0x18002a019  mov     qword ptr [rsp+50h+dwOptions], rdi; lpData
0x18002a01e  call    cs:__imp_RegSetValueExW
0x18002a024  test    eax, eax
0x18002a026  jz      short loc_18002A02F
0x18002a028  mov     edx, 25h ; '%'
0x18002a02d  jmp     short loc_180029FD4
0x18002a02f  mov     [rsp+50h+lpdwDisposition], rsi; lpdwDisposition
0x18002a034  lea     rax, [rbp+arg_10]
0x18002a038  mov     [rsp+50h+phkResult], rax; phkResult
0x18002a03d  lea     rdx, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002a044  mov     [rsp+50h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002a049  xor     r9d, r9d; lpClass
0x18002a04c  mov     [rsp+50h+samDesired], 20006h; samDesired
0x18002a054  xor     r8d, r8d; Reserved
0x18002a057  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a05e  mov     [rsp+50h+dwOptions], esi; unsigned int
0x18002a062  mov     [rbp+arg_10], rsi
0x18002a066  call    cs:__imp_RegCreateKeyExW
0x18002a06c  test    eax, eax
0x18002a06e  jz      short loc_18002A0A2
0x18002a070  mov     edx, 2Ah ; '*'; void *
0x18002a075  mov     rcx, [rbp+18h]; this
0x18002a079  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x18002a080  mov     r9d, eax; char *
0x18002a083  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002a088  mov     rcx, [rbp+arg_10]; hKey
0x18002a08c  mov     ebx, eax
0x18002a08e  test    rcx, rcx
0x18002a091  jz      loc_180029FE9
0x18002a097  call    cs:__imp_RegCloseKey
0x18002a09d  jmp     loc_180029FE9
0x18002a0a2  mov     rcx, [rbp+arg_10]; hKey
0x18002a0a6  lea     rdx, aLostmodemessag; "LostModeMessage"
0x18002a0ad  mov     [rsp+50h+samDesired], ebx; cbData
0x18002a0b1  mov     r9d, 1; dwType
0x18002a0b7  xor     r8d, r8d; Reserved
0x18002a0ba  mov     qword ptr [rsp+50h+dwOptions], rdi; lpData
0x18002a0bf  call    cs:__imp_RegSetValueExW
0x18002a0c5  test    eax, eax
0x18002a0c7  jz      short loc_18002A0D0
0x18002a0c9  mov     edx, 2Dh ; '-'
0x18002a0ce  jmp     short loc_18002A075
0x18002a0d0  mov     rcx, [rbp+arg_10]; hKey
0x18002a0d4  lea     rax, [rbp+Data]
0x18002a0d8  mov     r9d, 4; dwType
0x18002a0de  mov     [rbp+Data], 1
0x18002a0e5  mov     [rsp+50h+samDesired], r9d; cbData
0x18002a0ea  lea     rdx, aEnablelostmode; "EnableLostMode"
0x18002a0f1  xor     r8d, r8d; Reserved
0x18002a0f4  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18002a0f9  call    cs:__imp_RegSetValueExW
0x18002a0ff  test    eax, eax
0x18002a101  jz      short loc_18002A10D
0x18002a103  mov     edx, 31h ; '1'
0x18002a108  jmp     loc_18002A075
0x18002a10d  mov     rcx, [rbp+arg_10]; hKey
0x18002a111  test    rcx, rcx
0x18002a114  jz      short loc_18002A11C
0x18002a116  call    cs:__imp_RegCloseKey
0x18002a11c  mov     rcx, [rbp+hKey]; hKey
0x18002a120  test    rcx, rcx
0x18002a123  jz      short loc_18002A12B
0x18002a125  call    cs:__imp_RegCloseKey
0x18002a12b  xor     eax, eax
0x18002a12d  jmp     short loc_18002A15A
0x18002a12f  mov     ebx, 80070216h
0x18002a134  mov     edx, 1Ch
0x18002a139  jmp     short loc_18002A145
0x18002a13b  mov     ebx, 80070057h
0x18002a140  mov     edx, 14h; void *
0x18002a145  mov     rcx, [rbp+18h]; this
0x18002a149  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x18002a150  mov     r9d, ebx; char *
0x18002a153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a158  mov     eax, ebx
0x18002a15a  mov     rbx, [rsp+50h+arg_18]
0x18002a162  add     rsp, 50h
0x18002a166  pop     rdi
0x18002a167  pop     rsi
0x18002a168  pop     rbp
0x18002a169  retn
```

# NgcUtils::IsVsmAvailable(void)

- ea: `0x18001c324`
- end: `0x18001c519`
- name: `?IsVsmAvailable@NgcUtils@@YA_NXZ`
- size: `501`
- prototype: `char __fastcall(NgcUtils *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c1f8`

## callees

- `0x18000247c`
- `0x1800024a8`
- `0x180006330`
- `0x18001aa20`
- `0x18001c324`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c429`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c479`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c429`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c479`
- `ntdll!NtQuerySystemInformation` at `0x18001c377`
- `ntdll!NtQuerySystemInformation` at `0x18001c377`

## string_xrefs

- `0x18001c446`: `EnableVirtualizationBasedSecurity`
- `0x18001c385`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

## pseudocode

```c
char __fastcall NgcUtils::IsVsmAvailable(NgcUtils *this)
{
  NTSTATUS v1; // eax
  int v2; // ebx
  int v3; // ebx
  int pdwType; // [rsp+20h] [rbp-69h]
  int pvData; // [rsp+40h] [rbp-49h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-45h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp-41h] BYREF
  int v9; // [rsp+4Ch] [rbp-3Dh] BYREF
  int v10; // [rsp+50h] [rbp-39h] BYREF
  int v11; // [rsp+54h] [rbp-35h] BYREF
  __int64 v12; // [rsp+58h] [rbp-31h] BYREF
  __int128 SystemInformation; // [rsp+60h] [rbp-29h] BYREF
  int *v14; // [rsp+90h] [rbp+7h]
  __int64 v15; // [rsp+98h] [rbp+Fh]
  int *v16; // [rsp+A0h] [rbp+17h]
  __int64 v17; // [rsp+A8h] [rbp+1Fh]
  int *v18; // [rsp+B0h] [rbp+27h]
  __int64 v19; // [rsp+B8h] [rbp+2Fh]
  __int64 *v20; // [rsp+C0h] [rbp+37h]
  __int64 v21; // [rsp+C8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( !byte_1800316C4 )
  {
    ReturnLength = 0;
    SystemInformation = 0;
    v1 = NtQuerySystemInformation(SystemRegistryQuotaInformation|0x80, &SystemInformation, 0x10u, &ReturnLength);
    if ( v1 < 0 )
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
        (const char *)(unsigned int)v1,
        pdwType);
    if ( (SystemInformation & 0x21) != 0x21 )
      byte_1800312BC = 0;
    if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x800000000000LL) )
    {
      v9 = (unsigned __int8)byte_1800312BC;
      v12 = 0x1000000;
      pvData = 0;
      v2 = 0;
      pcbData = 4;
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
              L"LaunchUserOOBE",
              0x10u,
              0,
              &pvData,
              &pcbData) )
        LOBYTE(v2) = pvData == 1;
      v10 = v2;
      v3 = 0;
      pvData = 0;
      pcbData = 4;
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard",
              L"EnableVirtualizationBasedSecurity",
              0x10u,
              0,
              &pvData,
              &pcbData) )
        LOBYTE(v3) = pvData == 1;
      v11 = v3;
      v20 = &v12;
      v21 = 8;
      v18 = &v9;
      v19 = 4;
      v16 = &v10;
      v17 = 4;
      v14 = &v11;
      v15 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180031038, &unk_180029B98);
    }
    byte_1800316C4 = 1;
  }
  return byte_1800312BC;
}

```

## disassembly

```asm
0x18001c324  mov     [rsp-8+arg_0], rbx
0x18001c329  mov     [rsp-8+arg_8], rsi
0x18001c32e  push    rbp
0x18001c32f  lea     rbp, [rsp-57h]
0x18001c334  sub     rsp, 0E0h
0x18001c33b  mov     rax, cs:__security_cookie
0x18001c342  xor     rax, rsp
0x18001c345  mov     [rbp+57h+var_10], rax
0x18001c349  cmp     cs:byte_1800316C4, 0
0x18001c350  jnz     loc_18001C4F2
0x18001c356  xorps   xmm0, xmm0
0x18001c359  mov     [rbp+57h+ReturnLength], 0
0x18001c360  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x18001c364  mov     r8d, 10h; SystemInformationLength
0x18001c36a  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x18001c36e  mov     ecx, 0A5h; SystemInformationClass
0x18001c373  movups  [rbp+57h+SystemInformation], xmm0
0x18001c377  call    cs:__imp_NtQuerySystemInformation
0x18001c37d  test    eax, eax
0x18001c37f  jns     short loc_18001C399
0x18001c381  mov     rcx, [rbp+5Fh]; this
0x18001c385  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001c38c  mov     r9d, eax; char *
0x18001c38f  mov     edx, 0E5h; void *
0x18001c394  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18001c399  mov     al, byte ptr [rbp+57h+SystemInformation]
0x18001c39c  and     al, 21h
0x18001c39e  cmp     al, 21h ; '!'
0x18001c3a0  jz      short loc_18001C3A9
0x18001c3a2  mov     cs:byte_1800312BC, 0
0x18001c3a9  mov     eax, cs:dword_180031038
0x18001c3af  cmp     eax, 5
0x18001c3b2  jbe     loc_18001C4EB
0x18001c3b8  mov     rdx, 800000000000h
0x18001c3c2  lea     rcx, dword_180031038
0x18001c3c9  call    _tlgKeywordOn
0x18001c3ce  test    al, al
0x18001c3d0  jz      loc_18001C4EB
0x18001c3d6  movzx   eax, cs:byte_1800312BC
0x18001c3dd  lea     r8, aLaunchuseroobe; "LaunchUserOOBE"
0x18001c3e4  mov     [rbp+57h+var_94], eax
0x18001c3e7  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001c3ee  lea     rax, [rbp+57h+var_9C]
0x18001c3f2  mov     [rbp+57h+var_88], 1000000h
0x18001c3fa  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18001c3ff  mov     esi, 4
0x18001c404  lea     rax, [rbp+57h+var_A0]
0x18001c408  mov     [rbp+57h+var_A0], 0
0x18001c40f  mov     [rsp+0E0h+pvData], rax; pvData
0x18001c414  xor     ebx, ebx
0x18001c416  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001c41d  mov     [rsp+0E0h+pdwType], rbx; pdwType
0x18001c422  lea     r9d, [rsi+0Ch]; dwFlags
0x18001c426  mov     [rbp+57h+var_9C], esi
0x18001c429  call    cs:__imp_RegGetValueW
0x18001c42f  test    eax, eax
0x18001c431  jnz     short loc_18001C43A
0x18001c433  cmp     [rbp+57h+var_A0], 1
0x18001c437  setz    bl
0x18001c43a  mov     [rbp+57h+var_90], ebx
0x18001c43d  lea     rax, [rbp+57h+var_9C]
0x18001c441  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18001c446  lea     r8, aEnablevirtuali; "EnableVirtualizationBasedSecurity"
0x18001c44d  xor     ebx, ebx
0x18001c44f  mov     [rbp+57h+var_A0], 0
0x18001c456  lea     rax, [rbp+57h+var_A0]
0x18001c45a  mov     [rbp+57h+var_9C], esi
0x18001c45d  mov     [rsp+0E0h+pvData], rax; pvData
0x18001c462  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x18001c469  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001c470  mov     [rsp+0E0h+pdwType], rbx; pdwType
0x18001c475  lea     r9d, [rbx+10h]; dwFlags
0x18001c479  call    cs:__imp_RegGetValueW
0x18001c47f  test    eax, eax
0x18001c481  jnz     short loc_18001C48A
0x18001c483  cmp     [rbp+57h+var_A0], 1
0x18001c487  setz    bl
0x18001c48a  lea     rax, [rbp+57h+var_88]
0x18001c48e  mov     [rbp+57h+var_8C], ebx
0x18001c491  mov     [rbp+57h+var_20], rax
0x18001c495  lea     rdx, unk_180029B98
0x18001c49c  lea     rax, [rbp+57h+var_94]
0x18001c4a0  mov     [rbp+57h+var_18], 8
0x18001c4a8  mov     [rbp+57h+var_30], rax
0x18001c4ac  lea     rcx, dword_180031038
0x18001c4b3  lea     rax, [rbp+57h+var_90]
0x18001c4b7  mov     [rbp+57h+var_28], rsi
0x18001c4bb  mov     [rbp+57h+var_40], rax
0x18001c4bf  xor     r9d, r9d
0x18001c4c2  lea     rax, [rbp+57h+var_8C]
0x18001c4c6  mov     [rbp+57h+var_38], rsi
0x18001c4ca  mov     [rbp+57h+var_50], rax
0x18001c4ce  xor     r8d, r8d
0x18001c4d1  lea     rax, [rbp+57h+var_70]
0x18001c4d5  mov     [rbp+57h+var_48], rsi
0x18001c4d9  mov     [rsp+0E0h+pvData], rax
0x18001c4de  mov     dword ptr [rsp+0E0h+pdwType], 6
0x18001c4e6  call    _tlgWriteTransfer_EventWriteTransfer
0x18001c4eb  mov     cs:byte_1800316C4, 1
0x18001c4f2  mov     al, cs:byte_1800312BC
0x18001c4f8  mov     rcx, [rbp+57h+var_10]
0x18001c4fc  xor     rcx, rsp; StackCookie
0x18001c4ff  call    __security_check_cookie
0x18001c504  lea     r11, [rsp+0E0h+var_s0]
0x18001c50c  mov     rbx, [r11+10h]
0x18001c510  mov     rsi, [r11+18h]
0x18001c514  mov     rsp, r11
0x18001c517  pop     rbp
0x18001c518  retn
```

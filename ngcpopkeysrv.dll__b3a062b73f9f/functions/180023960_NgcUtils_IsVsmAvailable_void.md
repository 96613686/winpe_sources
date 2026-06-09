# NgcUtils::IsVsmAvailable(void)

- ea: `0x180023960`
- end: `0x180023b55`
- name: `?IsVsmAvailable@NgcUtils@@YA_NXZ`
- size: `501`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023838`

## callees

- `0x18000121c`
- `0x180001248`
- `0x180004de0`
- `0x180022e94`
- `0x180023960`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800239b3`
- `ntdll!NtQuerySystemInformation` at `0x1800239b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023a65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023ab5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023a65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023ab5`

## string_xrefs

- `0x180023a82`: `EnableVirtualizationBasedSecurity`
- `0x1800239c1`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

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
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+70h] [rbp-19h] BYREF
  int *v15; // [rsp+90h] [rbp+7h]
  __int64 v16; // [rsp+98h] [rbp+Fh]
  int *v17; // [rsp+A0h] [rbp+17h]
  __int64 v18; // [rsp+A8h] [rbp+1Fh]
  int *v19; // [rsp+B0h] [rbp+27h]
  __int64 v20; // [rsp+B8h] [rbp+2Fh]
  __int64 *v21; // [rsp+C0h] [rbp+37h]
  __int64 v22; // [rsp+C8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( !byte_180037964 )
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
      byte_180037490 = 0;
    if ( (unsigned int)dword_180037000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180037000, 0x800000000000LL) )
    {
      v9 = (unsigned __int8)byte_180037490;
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
      v21 = &v12;
      v22 = 8;
      v19 = &v9;
      v20 = 4;
      v17 = &v10;
      v18 = 4;
      v15 = &v11;
      v16 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180037000, (unsigned __int8 *)byte_18002F1E5, 0, 0, 6u, &v14);
    }
    byte_180037964 = 1;
  }
  return byte_180037490;
}

```

## disassembly

```asm
0x180023960  mov     [rsp-8+arg_0], rbx
0x180023965  mov     [rsp-8+arg_8], rsi
0x18002396a  push    rbp
0x18002396b  lea     rbp, [rsp-57h]
0x180023970  sub     rsp, 0E0h
0x180023977  mov     rax, cs:__security_cookie
0x18002397e  xor     rax, rsp
0x180023981  mov     [rbp+57h+var_10], rax
0x180023985  cmp     cs:byte_180037964, 0
0x18002398c  jnz     loc_180023B2E
0x180023992  xorps   xmm0, xmm0
0x180023995  mov     [rbp+57h+ReturnLength], 0
0x18002399c  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x1800239a0  mov     r8d, 10h; SystemInformationLength
0x1800239a6  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x1800239aa  mov     ecx, 0A5h; SystemInformationClass
0x1800239af  movups  [rbp+57h+SystemInformation], xmm0
0x1800239b3  call    cs:__imp_NtQuerySystemInformation
0x1800239b9  test    eax, eax
0x1800239bb  jns     short loc_1800239D5
0x1800239bd  mov     rcx, [rbp+5Fh]; this
0x1800239c1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800239c8  mov     r9d, eax; char *
0x1800239cb  mov     edx, 0E5h; void *
0x1800239d0  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800239d5  mov     al, byte ptr [rbp+57h+SystemInformation]
0x1800239d8  and     al, 21h
0x1800239da  cmp     al, 21h ; '!'
0x1800239dc  jz      short loc_1800239E5
0x1800239de  mov     cs:byte_180037490, 0
0x1800239e5  mov     eax, cs:dword_180037000
0x1800239eb  cmp     eax, 5
0x1800239ee  jbe     loc_180023B27
0x1800239f4  mov     rdx, 800000000000h
0x1800239fe  lea     rcx, dword_180037000
0x180023a05  call    _tlgKeywordOn
0x180023a0a  test    al, al
0x180023a0c  jz      loc_180023B27
0x180023a12  movzx   eax, cs:byte_180037490
0x180023a19  lea     r8, aLaunchuseroobe; "LaunchUserOOBE"
0x180023a20  mov     [rbp+57h+var_94], eax
0x180023a23  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180023a2a  lea     rax, [rbp+57h+var_9C]
0x180023a2e  mov     [rbp+57h+var_88], 1000000h
0x180023a36  mov     [rsp+0E0h+pcbData], rax; pcbData
0x180023a3b  mov     esi, 4
0x180023a40  lea     rax, [rbp+57h+var_A0]
0x180023a44  mov     [rbp+57h+var_A0], 0
0x180023a4b  mov     [rsp+0E0h+pvData], rax; pvData
0x180023a50  xor     ebx, ebx
0x180023a52  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180023a59  mov     [rsp+0E0h+pdwType], rbx; pdwType
0x180023a5e  lea     r9d, [rsi+0Ch]; dwFlags
0x180023a62  mov     [rbp+57h+var_9C], esi
0x180023a65  call    cs:__imp_RegGetValueW
0x180023a6b  test    eax, eax
0x180023a6d  jnz     short loc_180023A76
0x180023a6f  cmp     [rbp+57h+var_A0], 1
0x180023a73  setz    bl
0x180023a76  mov     [rbp+57h+var_90], ebx
0x180023a79  lea     rax, [rbp+57h+var_9C]
0x180023a7d  mov     [rsp+0E0h+pcbData], rax; pcbData
0x180023a82  lea     r8, aEnablevirtuali; "EnableVirtualizationBasedSecurity"
0x180023a89  xor     ebx, ebx
0x180023a8b  mov     [rbp+57h+var_A0], 0
0x180023a92  lea     rax, [rbp+57h+var_A0]
0x180023a96  mov     [rbp+57h+var_9C], esi
0x180023a99  mov     [rsp+0E0h+pvData], rax; pvData
0x180023a9e  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x180023aa5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180023aac  mov     [rsp+0E0h+pdwType], rbx; pdwType
0x180023ab1  lea     r9d, [rbx+10h]; dwFlags
0x180023ab5  call    cs:__imp_RegGetValueW
0x180023abb  test    eax, eax
0x180023abd  jnz     short loc_180023AC6
0x180023abf  cmp     [rbp+57h+var_A0], 1
0x180023ac3  setz    bl
0x180023ac6  lea     rax, [rbp+57h+var_88]
0x180023aca  mov     [rbp+57h+var_8C], ebx
0x180023acd  mov     [rbp+57h+var_20], rax
0x180023ad1  lea     rdx, byte_18002F1E5
0x180023ad8  lea     rax, [rbp+57h+var_94]
0x180023adc  mov     [rbp+57h+var_18], 8
0x180023ae4  mov     [rbp+57h+var_30], rax
0x180023ae8  lea     rcx, dword_180037000
0x180023aef  lea     rax, [rbp+57h+var_90]
0x180023af3  mov     [rbp+57h+var_28], rsi
0x180023af7  mov     [rbp+57h+var_40], rax
0x180023afb  xor     r9d, r9d
0x180023afe  lea     rax, [rbp+57h+var_8C]
0x180023b02  mov     [rbp+57h+var_38], rsi
0x180023b06  mov     [rbp+57h+var_50], rax
0x180023b0a  xor     r8d, r8d
0x180023b0d  lea     rax, [rbp+57h+var_70]
0x180023b11  mov     [rbp+57h+var_48], rsi
0x180023b15  mov     [rsp+0E0h+pvData], rax
0x180023b1a  mov     dword ptr [rsp+0E0h+pdwType], 6
0x180023b22  call    _tlgWriteTransfer_EventWriteTransfer
0x180023b27  mov     cs:byte_180037964, 1
0x180023b2e  mov     al, cs:byte_180037490
0x180023b34  mov     rcx, [rbp+57h+var_10]
0x180023b38  xor     rcx, rsp; StackCookie
0x180023b3b  call    __security_check_cookie
0x180023b40  lea     r11, [rsp+0E0h+var_s0]
0x180023b48  mov     rbx, [r11+10h]
0x180023b4c  mov     rsi, [r11+18h]
0x180023b50  mov     rsp, r11
0x180023b53  pop     rbp
0x180023b54  retn
```

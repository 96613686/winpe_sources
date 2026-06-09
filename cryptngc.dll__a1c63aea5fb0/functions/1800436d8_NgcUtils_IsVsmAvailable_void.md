# NgcUtils::IsVsmAvailable(void)

- ea: `0x1800436d8`
- end: `0x1800438cd`
- name: `?IsVsmAvailable@NgcUtils@@YA_NXZ`
- size: `501`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004367c`

## callees

- `0x18000fc20`
- `0x18001c630`
- `0x180042330`
- `0x1800436d8`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800437dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004382d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800437dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004382d`
- `ntdll!NtQuerySystemInformation` at `0x18004372b`
- `ntdll!NtQuerySystemInformation` at `0x18004372b`

## string_xrefs

- `0x180043739`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x1800437fa`: `EnableVirtualizationBasedSecurity`

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

  if ( !byte_18006EEA8 )
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
      byte_18006E3E8 = 0;
    if ( (unsigned int)dword_18006E000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18006E000, 0x800000000000LL) )
    {
      v9 = (unsigned __int8)byte_18006E3E8;
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
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)&dword_1800636B4,
        0,
        0,
        6u,
        &v14);
    }
    byte_18006EEA8 = 1;
  }
  return byte_18006E3E8;
}

```

## disassembly

```asm
0x1800436d8  mov     [rsp-8+arg_0], rbx
0x1800436dd  mov     [rsp-8+arg_8], rsi
0x1800436e2  push    rbp
0x1800436e3  lea     rbp, [rsp-57h]
0x1800436e8  sub     rsp, 0E0h
0x1800436ef  mov     rax, cs:__security_cookie
0x1800436f6  xor     rax, rsp
0x1800436f9  mov     [rbp+57h+var_10], rax
0x1800436fd  cmp     cs:byte_18006EEA8, 0
0x180043704  jnz     loc_1800438A6
0x18004370a  xorps   xmm0, xmm0
0x18004370d  mov     [rbp+57h+ReturnLength], 0
0x180043714  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x180043718  mov     r8d, 10h; SystemInformationLength
0x18004371e  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x180043722  mov     ecx, 0A5h; SystemInformationClass
0x180043727  movups  [rbp+57h+SystemInformation], xmm0
0x18004372b  call    cs:__imp_NtQuerySystemInformation
0x180043731  test    eax, eax
0x180043733  jns     short loc_18004374D
0x180043735  mov     rcx, [rbp+5Fh]; this
0x180043739  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180043740  mov     r9d, eax; char *
0x180043743  mov     edx, 0E5h; void *
0x180043748  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18004374d  mov     al, byte ptr [rbp+57h+SystemInformation]
0x180043750  and     al, 21h
0x180043752  cmp     al, 21h ; '!'
0x180043754  jz      short loc_18004375D
0x180043756  mov     cs:byte_18006E3E8, 0
0x18004375d  mov     eax, cs:dword_18006E000
0x180043763  cmp     eax, 5
0x180043766  jbe     loc_18004389F
0x18004376c  mov     rdx, 800000000000h
0x180043776  lea     rcx, dword_18006E000
0x18004377d  call    _tlgKeywordOn
0x180043782  test    al, al
0x180043784  jz      loc_18004389F
0x18004378a  movzx   eax, cs:byte_18006E3E8
0x180043791  lea     r8, aLaunchuseroobe; "LaunchUserOOBE"
0x180043798  mov     [rbp+57h+var_94], eax
0x18004379b  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800437a2  lea     rax, [rbp+57h+var_9C]
0x1800437a6  mov     [rbp+57h+var_88], 1000000h
0x1800437ae  mov     [rsp+0E0h+pcbData], rax; pcbData
0x1800437b3  mov     esi, 4
0x1800437b8  lea     rax, [rbp+57h+var_A0]
0x1800437bc  mov     [rbp+57h+var_A0], 0
0x1800437c3  mov     [rsp+0E0h+pvData], rax; pvData
0x1800437c8  xor     ebx, ebx
0x1800437ca  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800437d1  mov     [rsp+0E0h+pdwType], rbx; pdwType
0x1800437d6  lea     r9d, [rsi+0Ch]; dwFlags
0x1800437da  mov     [rbp+57h+var_9C], esi
0x1800437dd  call    cs:__imp_RegGetValueW
0x1800437e3  test    eax, eax
0x1800437e5  jnz     short loc_1800437EE
0x1800437e7  cmp     [rbp+57h+var_A0], 1
0x1800437eb  setz    bl
0x1800437ee  mov     [rbp+57h+var_90], ebx
0x1800437f1  lea     rax, [rbp+57h+var_9C]
0x1800437f5  mov     [rsp+0E0h+pcbData], rax; pcbData
0x1800437fa  lea     r8, aEnablevirtuali; "EnableVirtualizationBasedSecurity"
0x180043801  xor     ebx, ebx
0x180043803  mov     [rbp+57h+var_A0], 0
0x18004380a  lea     rax, [rbp+57h+var_A0]
0x18004380e  mov     [rbp+57h+var_9C], esi
0x180043811  mov     [rsp+0E0h+pvData], rax; pvData
0x180043816  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x18004381d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180043824  mov     [rsp+0E0h+pdwType], rbx; pdwType
0x180043829  lea     r9d, [rbx+10h]; dwFlags
0x18004382d  call    cs:__imp_RegGetValueW
0x180043833  test    eax, eax
0x180043835  jnz     short loc_18004383E
0x180043837  cmp     [rbp+57h+var_A0], 1
0x18004383b  setz    bl
0x18004383e  lea     rax, [rbp+57h+var_88]
0x180043842  mov     [rbp+57h+var_8C], ebx
0x180043845  mov     [rbp+57h+var_20], rax
0x180043849  lea     rdx, dword_1800636B4
0x180043850  lea     rax, [rbp+57h+var_94]
0x180043854  mov     [rbp+57h+var_18], 8
0x18004385c  mov     [rbp+57h+var_30], rax
0x180043860  lea     rcx, dword_18006E000
0x180043867  lea     rax, [rbp+57h+var_90]
0x18004386b  mov     [rbp+57h+var_28], rsi
0x18004386f  mov     [rbp+57h+var_40], rax
0x180043873  xor     r9d, r9d
0x180043876  lea     rax, [rbp+57h+var_8C]
0x18004387a  mov     [rbp+57h+var_38], rsi
0x18004387e  mov     [rbp+57h+var_50], rax
0x180043882  xor     r8d, r8d
0x180043885  lea     rax, [rbp+57h+var_70]
0x180043889  mov     [rbp+57h+var_48], rsi
0x18004388d  mov     [rsp+0E0h+pvData], rax
0x180043892  mov     dword ptr [rsp+0E0h+pdwType], 6
0x18004389a  call    _tlgWriteTransfer_EventWriteTransfer
0x18004389f  mov     cs:byte_18006EEA8, 1
0x1800438a6  mov     al, cs:byte_18006E3E8
0x1800438ac  mov     rcx, [rbp+57h+var_10]
0x1800438b0  xor     rcx, rsp; StackCookie
0x1800438b3  call    __security_check_cookie
0x1800438b8  lea     r11, [rsp+0E0h+var_s0]
0x1800438c0  mov     rbx, [r11+10h]
0x1800438c4  mov     rsi, [r11+18h]
0x1800438c8  mov     rsp, r11
0x1800438cb  pop     rbp
0x1800438cc  retn
```

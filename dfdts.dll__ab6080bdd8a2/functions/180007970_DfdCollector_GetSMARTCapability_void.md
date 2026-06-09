# DfdCollector::GetSMARTCapability(void)

- ea: `0x180007970`
- end: `0x180007bb7`
- name: `?GetSMARTCapability@DfdCollector@@AEAAKXZ`
- size: `583`
- prototype: `__int64 __fastcall(DfdCollector *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180002450`

## callees

- `0x180002c90`
- `0x1800039fc`
- `0x180003aac`
- `0x180003edc`
- `0x1800040b8`
- `0x180007970`
- `0x180008370`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x180007b21`
- `ntdll!WinSqmAddToStream` at `0x180007b21`
- `KERNEL32!GetLastError` at `0x1800079c6`
- `KERNEL32!GetLastError` at `0x180007b65`
- `KERNEL32!GetLastError` at `0x1800079c6`
- `KERNEL32!GetLastError` at `0x180007b65`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180007b49`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180007b49`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1800079b7`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1800079b7`

## pseudocode

```c
__int64 __fastcall DfdCollector::GetSMARTCapability(DfdCollector *this)
{
  HDEVINFO ClassDevsW; // r14
  DWORD LastError; // eax
  DWORD v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  DWORD i; // esi
  unsigned int v8; // eax
  const wchar_t *HardwareId; // rax
  _BYTE v11[548]; // [rsp+20h] [rbp-E0h] BYREF
  int v12; // [rsp+244h] [rbp+144h]
  int v13; // [rsp+248h] [rbp+148h]
  int v14; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v15; // [rsp+2B8h] [rbp+1B8h]
  __int128 v16; // [rsp+2C8h] [rbp+1C8h]
  __int64 v17; // [rsp+2D8h] [rbp+1D8h]

  ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVINTERFACE_DISK, 0, 0, 0x12u);
  if ( ClassDevsW == (HDEVINFO)-1LL )
  {
    LastError = GetLastError();
    v4 = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 10;
      goto LABEL_22;
    }
    return v4;
  }
  for ( i = 0; ; ++i )
  {
    DiskContext::DiskContext((DiskContext *)v11, ClassDevsW, 0);
    v8 = DiskContext::Set((__int64)v11, 2, i);
    if ( v8 )
      break;
    *((_DWORD *)this + 10) = v12;
    *((_DWORD *)this + 11) = v13;
    HardwareId = DiskContext::GetHardwareId((DiskContext *)v11);
    *((_QWORD *)this + 4) = HardwareId;
    if ( !HardwareId )
    {
      *((_QWORD *)this + 4) = L"Unknown";
      HardwareId = L"Unknown";
    }
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    if ( !HardwareId || !*HardwareId )
      HardwareId = L"(null)";
    *(_QWORD *)&v15 = HardwareId;
    v14 = 2;
    LODWORD(v16) = *((_DWORD *)this + 10);
    DWORD2(v15) = 1;
    LODWORD(v17) = *((_DWORD *)this + 11);
    DWORD2(v16) = 1;
    WinSqmAddToStream(*((_QWORD *)this + 2), 913, 3, &v14);
LABEL_17:
    DiskContext::~DiskContext((DiskContext *)v11);
  }
  if ( v8 != 259 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids, v8);
    goto LABEL_17;
  }
  v4 = 0;
  DiskContext::~DiskContext((DiskContext *)v11);
  if ( !SetupDiDestroyDeviceInfoList(ClassDevsW)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    v6 = 12;
    v5 = WPP_GLOBAL_Control;
LABEL_22:
    WPP_SF_d(v5[2], v6, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids, LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x180007970  mov     [rsp-8+arg_8], rbx
0x180007975  mov     [rsp-8+arg_10], rsi
0x18000797a  push    rbp
0x18000797b  push    rdi
0x18000797c  push    r13
0x18000797e  push    r14
0x180007980  push    r15
0x180007982  lea     rbp, [rsp-1F0h]
0x18000798a  sub     rsp, 2F0h
0x180007991  mov     rax, cs:__security_cookie
0x180007998  xor     rax, rsp
0x18000799b  mov     [rbp+210h+var_30], rax
0x1800079a2  mov     rbx, rcx
0x1800079a5  mov     r9d, 12h; Flags
0x1800079ab  xor     r8d, r8d; hwndParent
0x1800079ae  xor     edx, edx; Enumerator
0x1800079b0  lea     rcx, GUID_DEVINTERFACE_DISK; ClassGuid
0x1800079b7  call    cs:__imp_SetupDiGetClassDevsW
0x1800079bd  mov     r14, rax
0x1800079c0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800079c4  jnz     short loc_1800079F8
0x1800079c6  call    cs:__imp_GetLastError
0x1800079cc  mov     ebx, eax
0x1800079ce  lea     rdi, WPP_GLOBAL_Control
0x1800079d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079dc  cmp     rcx, rdi
0x1800079df  jz      loc_180007B8A
0x1800079e5  test    byte ptr [rcx+1Ch], 1
0x1800079e9  jz      loc_180007B8A
0x1800079ef  lea     edx, [r14+0Bh]
0x1800079f3  jmp     loc_180007B77
0x1800079f8  xor     r15d, r15d
0x1800079fb  mov     esi, r15d
0x1800079fe  lea     rdi, WPP_GLOBAL_Control
0x180007a05  lea     r13, aUnknown; "Unknown"
0x180007a0c  xor     r8d, r8d; unsigned int
0x180007a0f  mov     rdx, r14; void *
0x180007a12  lea     rcx, [rsp+310h+var_2F0]; this
0x180007a17  call    ??0DiskContext@@QEAA@PEAXK@Z; DiskContext::DiskContext(void *,ulong)
0x180007a1c  nop
0x180007a1d  mov     r8d, esi
0x180007a20  mov     edx, 2
0x180007a25  lea     rcx, [rsp+310h+var_2F0]
0x180007a2a  call    ?Set@DiskContext@@QEAAKW4DFD_IDENTITY@@K@Z; DiskContext::Set(DFD_IDENTITY,ulong)
0x180007a2f  test    eax, eax
0x180007a31  jz      short loc_180007A75
0x180007a33  cmp     eax, 103h
0x180007a38  jz      loc_180007B39
0x180007a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a45  cmp     rcx, rdi
0x180007a48  jz      loc_180007B28
0x180007a4e  test    byte ptr [rcx+1Ch], 1
0x180007a52  jz      loc_180007B28
0x180007a58  mov     edx, 0Bh
0x180007a5d  mov     r9d, eax
0x180007a60  lea     r8, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids
0x180007a67  mov     rcx, [rcx+10h]
0x180007a6b  call    WPP_SF_d
0x180007a70  jmp     loc_180007B28
0x180007a75  mov     eax, [rbp+210h+var_CC]
0x180007a7b  mov     [rbx+28h], eax
0x180007a7e  mov     eax, [rbp+210h+var_C8]
0x180007a84  mov     [rbx+2Ch], eax
0x180007a87  lea     rcx, [rsp+310h+var_2F0]; this
0x180007a8c  call    ?GetHardwareId@DiskContext@@QEAAPEAGXZ; DiskContext::GetHardwareId(void)
0x180007a91  mov     [rbx+20h], rax
0x180007a95  test    rax, rax
0x180007a98  jnz     short loc_180007AA1
0x180007a9a  mov     [rbx+20h], r13
0x180007a9e  mov     rax, r13
0x180007aa1  mov     [rbp+210h+var_60], r15d
0x180007aa8  xorps   xmm0, xmm0
0x180007aab  xor     ecx, ecx
0x180007aad  movups  [rbp+210h+var_58], xmm0
0x180007ab4  movups  [rbp+210h+var_48], xmm0
0x180007abb  mov     [rbp+210h+var_38], rcx
0x180007ac2  test    rax, rax
0x180007ac5  jz      short loc_180007ACD
0x180007ac7  cmp     [rax], r15w
0x180007acb  jnz     short loc_180007AD4
0x180007acd  lea     rax, aNull; "(null)"
0x180007ad4  mov     qword ptr [rbp+210h+var_58], rax
0x180007adb  mov     [rbp+210h+var_60], 2
0x180007ae5  mov     eax, [rbx+28h]
0x180007ae8  mov     dword ptr [rbp+210h+var_48], eax
0x180007aee  mov     dword ptr [rbp+210h+var_58+8], 1
0x180007af8  mov     eax, [rbx+2Ch]
0x180007afb  mov     dword ptr [rbp+210h+var_38], eax
0x180007b01  mov     dword ptr [rbp+210h+var_48+8], 1
0x180007b0b  lea     r9, [rbp+210h+var_60]
0x180007b12  mov     edx, 391h
0x180007b17  mov     r8d, 3
0x180007b1d  mov     rcx, [rbx+10h]
0x180007b21  call    cs:__imp_WinSqmAddToStream
0x180007b27  nop
0x180007b28  lea     rcx, [rsp+310h+var_2F0]; this
0x180007b2d  call    ??1DiskContext@@QEAA@XZ; DiskContext::~DiskContext(void)
0x180007b32  inc     esi
0x180007b34  jmp     loc_180007A0C
0x180007b39  mov     ebx, r15d
0x180007b3c  lea     rcx, [rsp+310h+var_2F0]; this
0x180007b41  call    ??1DiskContext@@QEAA@XZ; DiskContext::~DiskContext(void)
0x180007b46  mov     rcx, r14; DeviceInfoSet
0x180007b49  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180007b4f  test    eax, eax
0x180007b51  jnz     short loc_180007B8A
0x180007b53  mov     rax, cs:WPP_GLOBAL_Control
0x180007b5a  cmp     rax, rdi
0x180007b5d  jz      short loc_180007B8A
0x180007b5f  test    byte ptr [rax+1Ch], 2
0x180007b63  jz      short loc_180007B8A
0x180007b65  call    cs:__imp_GetLastError
0x180007b6b  mov     edx, 0Ch
0x180007b70  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b77  mov     r9d, eax
0x180007b7a  lea     r8, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids
0x180007b81  mov     rcx, [rcx+10h]
0x180007b85  call    WPP_SF_d
0x180007b8a  mov     eax, ebx
0x180007b8c  mov     rcx, [rbp+210h+var_30]
0x180007b93  xor     rcx, rsp; StackCookie
0x180007b96  call    __security_check_cookie
0x180007b9b  lea     r11, [rsp+310h+var_20]
0x180007ba3  mov     rbx, [r11+38h]
0x180007ba7  mov     rsi, [r11+40h]
0x180007bab  mov     rsp, r11
0x180007bae  pop     r15
0x180007bb0  pop     r14
0x180007bb2  pop     r13
0x180007bb4  pop     rdi
0x180007bb5  pop     rbp
0x180007bb6  retn
```

# KpsCheckDomainJoinedMachine(void)

- ea: `0x18002c99c`
- end: `0x18002cb87`
- name: `?KpsCheckDomainJoinedMachine@@YAKXZ`
- size: `491`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002cf60`

## callees

- `0x18001ada8`
- `0x18001ae0c`
- `0x18001ae38`
- `0x18002c99c`
- `0x180031040`

## import_xrefs

- `ADVAPI32!LsaOpenPolicy` at `0x18002ca1f`
- `ADVAPI32!LsaOpenPolicy` at `0x18002ca1f`
- `ADVAPI32!LsaClose` at `0x18002cb30`
- `ADVAPI32!LsaClose` at `0x18002cb30`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18002ca59`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18002ca59`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18002ca79`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18002ca79`
- `ADVAPI32!LsaFreeMemory` at `0x18002cb1b`
- `ADVAPI32!LsaFreeMemory` at `0x18002cb1b`

## pseudocode

```c
__int64 KpsCheckDomainJoinedMachine(void)
{
  unsigned int v0; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  int v6; // [rsp+38h] [rbp-19h] BYREF
  PVOID Buffer; // [rsp+40h] [rbp-11h] BYREF
  PVOID PolicyHandle; // [rsp+48h] [rbp-9h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-1h] BYREF
  _BYTE v10[16]; // [rsp+80h] [rbp+2Fh] BYREF
  int *v11; // [rsp+90h] [rbp+3Fh]
  int v12; // [rsp+98h] [rbp+47h]
  int v13; // [rsp+9Ch] [rbp+4Bh]

  PolicyHandle = 0;
  Buffer = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v0 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    v2 = 21;
LABEL_8:
    WPP_SF_D(v1[2], v2, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v0);
LABEL_9:
    v0 = LsaNtStatusToWinError(v0);
    goto LABEL_20;
  }
  v0 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &Buffer);
  if ( v0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    v2 = 22;
    goto LABEL_8;
  }
  if ( !*((_QWORD *)Buffer + 2) )
  {
    v0 = 50;
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 1) != 0 )
    {
      v13 = 0;
      v11 = &v6;
      v6 = 50;
      v12 = 4;
      McGenEventWrite_EventWriteTransfer(v3, MachineNotDomainJoined, v4, 2, v10);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, 50);
  }
LABEL_20:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids);
  return v0;
}

```

## disassembly

```asm
0x18002c99c  mov     rax, rsp
0x18002c99f  mov     [rax+8], rbx
0x18002c9a3  mov     [rax+10h], rsi
0x18002c9a7  mov     [rax+18h], r15
0x18002c9ab  push    rbp
0x18002c9ac  lea     rbp, [rax-5Fh]
0x18002c9b0  sub     rsp, 0A0h
0x18002c9b7  mov     rax, cs:__security_cookie
0x18002c9be  xor     rax, rsp
0x18002c9c1  mov     [rbp+57h+var_8], rax
0x18002c9c5  and     [rbp+57h+PolicyHandle], 0
0x18002c9ca  and     [rbp+57h+Buffer], 0
0x18002c9cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c9d6  lea     rsi, WPP_GLOBAL_Control
0x18002c9dd  lea     r15, WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids
0x18002c9e4  cmp     rcx, rsi
0x18002c9e7  jz      short loc_18002CA00
0x18002c9e9  test    byte ptr [rcx+1Ch], 20h
0x18002c9ed  jz      short loc_18002CA00
0x18002c9ef  mov     rcx, [rcx+10h]
0x18002c9f3  mov     edx, 14h
0x18002c9f8  mov     r8, r15
0x18002c9fb  call    WPP_SF_
0x18002ca00  xorps   xmm0, xmm0
0x18002ca03  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002ca07  mov     r8d, 1; DesiredAccess
0x18002ca0d  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002ca11  xor     ecx, ecx; SystemName
0x18002ca13  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002ca17  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002ca1b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ca1f  call    cs:__imp_LsaOpenPolicy
0x18002ca26  nop     dword ptr [rax+rax+00h]
0x18002ca2b  mov     ebx, eax
0x18002ca2d  test    eax, eax
0x18002ca2f  jz      short loc_18002CA6C
0x18002ca31  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca38  cmp     rcx, rsi
0x18002ca3b  jz      short loc_18002CA57
0x18002ca3d  test    byte ptr [rcx+1Ch], 1
0x18002ca41  jz      short loc_18002CA57
0x18002ca43  mov     edx, 15h
0x18002ca48  mov     rcx, [rcx+10h]
0x18002ca4c  mov     r9d, ebx
0x18002ca4f  mov     r8, r15
0x18002ca52  call    WPP_SF_D
0x18002ca57  mov     ecx, ebx; Status
0x18002ca59  call    cs:__imp_LsaNtStatusToWinError
0x18002ca60  nop     dword ptr [rax+rax+00h]
0x18002ca65  mov     ebx, eax
0x18002ca67  jmp     loc_18002CB12
0x18002ca6c  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002ca70  lea     r8, [rbp+57h+Buffer]; Buffer
0x18002ca74  mov     edx, 3; InformationClass
0x18002ca79  call    cs:__imp_LsaQueryInformationPolicy
0x18002ca80  nop     dword ptr [rax+rax+00h]
0x18002ca85  mov     ebx, eax
0x18002ca87  test    eax, eax
0x18002ca89  jz      short loc_18002CAA4
0x18002ca8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca92  cmp     rcx, rsi
0x18002ca95  jz      short loc_18002CA57
0x18002ca97  test    byte ptr [rcx+1Ch], 1
0x18002ca9b  jz      short loc_18002CA57
0x18002ca9d  mov     edx, 16h
0x18002caa2  jmp     short loc_18002CA48
0x18002caa4  mov     rax, [rbp+57h+Buffer]
0x18002caa8  cmp     qword ptr [rax+10h], 0
0x18002caad  jnz     short loc_18002CB12
0x18002caaf  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 1
0x18002cab6  mov     ebx, 32h ; '2'
0x18002cabb  jz      short loc_18002CAEC
0x18002cabd  and     [rbp+57h+var_C], 0
0x18002cac1  lea     rax, [rbp+57h+var_70]
0x18002cac5  mov     [rbp+57h+var_18], rax
0x18002cac9  lea     r9d, [rbx-30h]
0x18002cacd  lea     rax, [rbp+57h+var_28]
0x18002cad1  mov     [rbp+57h+var_70], ebx
0x18002cad4  lea     rdx, MachineNotDomainJoined
0x18002cadb  mov     [rsp+0A0h+var_80], rax
0x18002cae0  mov     [rbp+57h+var_10], 4
0x18002cae7  call    McGenEventWrite_EventWriteTransfer
0x18002caec  mov     rcx, cs:WPP_GLOBAL_Control
0x18002caf3  cmp     rcx, rsi
0x18002caf6  jz      short loc_18002CB12
0x18002caf8  test    byte ptr [rcx+1Ch], 1
0x18002cafc  jz      short loc_18002CB12
0x18002cafe  mov     rcx, [rcx+10h]
0x18002cb02  mov     edx, 17h
0x18002cb07  mov     r9d, ebx
0x18002cb0a  mov     r8, r15
0x18002cb0d  call    WPP_SF_D
0x18002cb12  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18002cb16  test    rcx, rcx
0x18002cb19  jz      short loc_18002CB27
0x18002cb1b  call    cs:__imp_LsaFreeMemory
0x18002cb22  nop     dword ptr [rax+rax+00h]
0x18002cb27  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18002cb2b  test    rcx, rcx
0x18002cb2e  jz      short loc_18002CB3C
0x18002cb30  call    cs:__imp_LsaClose
0x18002cb37  nop     dword ptr [rax+rax+00h]
0x18002cb3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb43  cmp     rcx, rsi
0x18002cb46  jz      short loc_18002CB5F
0x18002cb48  test    byte ptr [rcx+1Ch], 20h
0x18002cb4c  jz      short loc_18002CB5F
0x18002cb4e  mov     rcx, [rcx+10h]
0x18002cb52  mov     edx, 18h
0x18002cb57  mov     r8, r15
0x18002cb5a  call    WPP_SF_
0x18002cb5f  mov     eax, ebx
0x18002cb61  mov     rcx, [rbp+57h+var_8]
0x18002cb65  xor     rcx, rsp; StackCookie
0x18002cb68  call    __security_check_cookie
0x18002cb6d  lea     r11, [rsp+0A0h+var_s0]
0x18002cb75  mov     rbx, [r11+10h]
0x18002cb79  mov     rsi, [r11+18h]
0x18002cb7d  mov     r15, [r11+20h]
0x18002cb81  mov     rsp, r11
0x18002cb84  pop     rbp
0x18002cb85  retn
```

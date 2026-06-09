# utils::CMachine::IsDomainJoined(void)

- ea: `0x18000ec5c`
- end: `0x18000ee17`
- name: `?IsDomainJoined@CMachine@utils@@SA_NXZ`
- size: `443`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c6bc`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180005528`
- `0x18000b9d0`
- `0x18000ec5c`

## import_xrefs

- `ADVAPI32!LsaOpenPolicy` at `0x18000ec90`
- `ADVAPI32!LsaOpenPolicy` at `0x18000ec90`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18000ecb5`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18000ecb5`
- `ADVAPI32!LsaClose` at `0x18000ed2d`
- `ADVAPI32!LsaClose` at `0x18000eda8`
- `ADVAPI32!LsaClose` at `0x18000ed2d`
- `ADVAPI32!LsaClose` at `0x18000eda8`
- `ADVAPI32!LsaFreeMemory` at `0x18000ed1b`
- `ADVAPI32!LsaFreeMemory` at `0x18000ed1b`

## pseudocode

```c
bool utils::CMachine::IsDomainJoined(void)
{
  NTSTATUS v0; // eax
  NTSTATUS v1; // ebx
  NTSTATUS v2; // ebx
  PVOID v3; // rcx
  __int64 v4; // rax
  bool v5; // bl
  const wchar_t *v6; // r9
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  char pExceptionObject; // [rsp+70h] [rbp+10h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp+18h] BYREF
  PVOID Buffer; // [rsp+80h] [rbp+20h] BYREF

  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v0 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  v1 = v0;
  if ( v0 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_ac7c82a58f1534def749feb208b2f783_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\creator\\lib\\utils\\cmachine.cpp",
        177,
        v0);
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v1 | 0x10000000);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  Buffer = 0;
  v2 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
  if ( v2 < 0 )
  {
    LsaClose(PolicyHandle);
    PolicyHandle = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_ac7c82a58f1534def749feb208b2f783_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\creator\\lib\\utils\\cmachine.cpp",
        187,
        v2);
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v2 | 0x10000000);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  v3 = Buffer;
  v4 = *((_QWORD *)Buffer + 8);
  v5 = v4 != 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v6 = L"Yes";
    if ( !v4 )
      v6 = L"No";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_ac7c82a58f1534def749feb208b2f783_Traceguids, v6);
    v3 = Buffer;
  }
  LsaFreeMemory(v3);
  Buffer = 0;
  LsaClose(PolicyHandle);
  return v5;
}

```

## disassembly

```asm
0x18000ec5c  mov     [rsp-8+arg_18], rbx
0x18000ec61  push    rbp
0x18000ec62  mov     rbp, rsp
0x18000ec65  sub     rsp, 60h
0x18000ec69  xorps   xmm0, xmm0
0x18000ec6c  mov     [rbp+PolicyHandle], 0
0x18000ec74  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18000ec78  mov     r8d, 1; DesiredAccess
0x18000ec7e  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18000ec82  xor     ecx, ecx; SystemName
0x18000ec84  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000ec88  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000ec8c  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ec90  call    cs:__imp_LsaOpenPolicy
0x18000ec96  mov     ebx, eax
0x18000ec98  test    eax, eax
0x18000ec9a  js      loc_18000ED43
0x18000eca0  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18000eca4  lea     r8, [rbp+Buffer]; Buffer
0x18000eca8  mov     edx, 0Ch; InformationClass
0x18000ecad  mov     [rbp+Buffer], 0
0x18000ecb5  call    cs:__imp_LsaQueryInformationPolicy
0x18000ecbb  mov     ebx, eax
0x18000ecbd  test    eax, eax
0x18000ecbf  js      loc_18000EDA4
0x18000ecc5  mov     rcx, [rbp+Buffer]
0x18000ecc9  mov     rax, [rcx+40h]
0x18000eccd  test    rax, rax
0x18000ecd0  setnz   bl
0x18000ecd3  mov     r10, cs:WPP_GLOBAL_Control
0x18000ecda  lea     rdx, WPP_GLOBAL_Control
0x18000ece1  cmp     r10, rdx
0x18000ece4  jz      short loc_18000ED1B
0x18000ece6  test    byte ptr [r10+1Ch], 4
0x18000eceb  jz      short loc_18000ED1B
0x18000eced  test    rax, rax
0x18000ecf0  lea     rcx, aNo_0; "No"
0x18000ecf7  lea     r9, aYes; "Yes"
0x18000ecfe  mov     edx, 19h
0x18000ed03  cmovz   r9, rcx
0x18000ed07  lea     r8, WPP_ac7c82a58f1534def749feb208b2f783_Traceguids
0x18000ed0e  mov     rcx, [r10+10h]
0x18000ed12  call    WPP_SF_S
0x18000ed17  mov     rcx, [rbp+Buffer]; Buffer
0x18000ed1b  call    cs:__imp_LsaFreeMemory
0x18000ed21  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18000ed25  mov     [rbp+Buffer], 0
0x18000ed2d  call    cs:__imp_LsaClose
0x18000ed33  mov     al, bl
0x18000ed35  mov     rbx, [rsp+60h+arg_18]
0x18000ed3d  add     rsp, 60h
0x18000ed41  pop     rbp
0x18000ed42  retn
0x18000ed43  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed4a  lea     rdx, WPP_GLOBAL_Control
0x18000ed51  cmp     rcx, rdx
0x18000ed54  jz      short loc_18000ED84
0x18000ed56  test    byte ptr [rcx+1Ch], 1
0x18000ed5a  jz      short loc_18000ED84
0x18000ed5c  mov     rcx, [rcx+10h]
0x18000ed60  lea     r9, aDriversWdmUsbp_10; "drivers\\wdm\\usbpw\\creator\\lib\\util"...
0x18000ed67  mov     edx, 17h
0x18000ed6c  mov     [rsp+60h+var_38], ebx
0x18000ed70  lea     r8, WPP_ac7c82a58f1534def749feb208b2f783_Traceguids
0x18000ed77  mov     [rsp+60h+var_40], 0B1h
0x18000ed7f  call    WPP_SF_sdD
0x18000ed84  bts     ebx, 1Ch
0x18000ed88  lea     rcx, [rbp+pExceptionObject]; this
0x18000ed8c  mov     edx, ebx; int
0x18000ed8e  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000ed93  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000ed9a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ed9e  call    _CxxThrowException_0
0x18000eda4  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18000eda8  call    cs:__imp_LsaClose
0x18000edae  mov     [rbp+PolicyHandle], 0
0x18000edb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edbd  lea     rdx, WPP_GLOBAL_Control
0x18000edc4  cmp     rcx, rdx
0x18000edc7  jz      short loc_18000EDF7
0x18000edc9  test    byte ptr [rcx+1Ch], 1
0x18000edcd  jz      short loc_18000EDF7
0x18000edcf  mov     rcx, [rcx+10h]
0x18000edd3  lea     r9, aDriversWdmUsbp_10; "drivers\\wdm\\usbpw\\creator\\lib\\util"...
0x18000edda  mov     edx, 18h
0x18000eddf  mov     [rsp+60h+var_38], ebx
0x18000ede3  lea     r8, WPP_ac7c82a58f1534def749feb208b2f783_Traceguids
0x18000edea  mov     [rsp+60h+var_40], 0BBh
0x18000edf2  call    WPP_SF_sdD
0x18000edf7  bts     ebx, 1Ch
0x18000edfb  lea     rcx, [rbp+pExceptionObject]; this
0x18000edff  mov     edx, ebx; int
0x18000ee01  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000ee06  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000ee0d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ee11  call    _CxxThrowException_0
```

# CscSeCreateSecurityDescriptor

- ea: `0x1400173e8`
- end: `0x140017643`
- name: `CscSeCreateSecurityDescriptor`
- size: `603`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140059edc`

## callees

- `0x1400173e8`
- `0x140018930`
- `0x140018fd0`
- `0x140019284`
- `0x14002f010`
- `0x14005f554`
- `0x14005f67c`
- `0x14008da04`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001755d`
- `ntoskrnl!ExAllocatePool2` at `0x14001755d`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400174f5`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400174f5`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001751d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001751d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400174cf`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400174cf`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140017543`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14001758c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140017543`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14001758c`

## pseudocode

```c
__int64 __fastcall CscSeCreateSecurityDescriptor(_QWORD *a1)
{
  void *v2; // rsi
  int v3; // eax
  PSID v4; // r14
  NTSTATUS v5; // ebx
  int v6; // eax
  struct _ACL *v7; // r15
  void *Pool2; // rax
  ULONG BufferLength; // [rsp+30h] [rbp-49h] BYREF
  PACL Dacl; // [rsp+38h] [rbp-41h] BYREF
  PSID Owner; // [rsp+40h] [rbp-39h] BYREF
  void *v13; // [rsp+48h] [rbp-31h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v15; // [rsp+70h] [rbp-9h]
  _OWORD v16[3]; // [rsp+78h] [rbp-1h] BYREF

  Owner = 0;
  v2 = 0;
  v15 = 0;
  v13 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  Dacl = 0;
  BufferLength = 0;
  memset(v16, 0, sizeof(v16));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids, 0);
  v3 = CscSeCreateSid(&Owner, 0);
  v4 = Owner;
  v5 = v3;
  if ( v3 >= 0 )
  {
    *(_QWORD *)&v16[0] = Owner;
    DWORD2(v16[0]) = 2032127;
    v6 = CscSeCreateAcl(&Dacl, v16);
    v7 = Dacl;
    v5 = v6;
    if ( v6 >= 0 )
    {
      v5 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( v5 >= 0 )
      {
        v5 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, v4, 0);
        if ( v5 >= 0 )
        {
          v5 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v7, 0);
          if ( v5 >= 0 )
          {
            BufferLength = 0;
            RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
            Pool2 = (void *)ExAllocatePool2(258, BufferLength, 557871939);
            v13 = Pool2;
            v2 = Pool2;
            if ( Pool2 )
              v5 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, Pool2, &BufferLength);
            else
              v5 = -1073741670;
          }
        }
      }
    }
    if ( v7 )
      CscSeDestroySid(&Dacl);
  }
  if ( v4 )
    CscSeDestroySid(&Owner);
  if ( v5 < 0 && v2 )
  {
    CscSeDestroySecurityDescriptor(&v13);
    v2 = v13;
  }
  *a1 = v2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400173e8  mov     [rsp-8+arg_8], rbx
0x1400173ed  mov     [rsp-8+arg_10], rsi
0x1400173f2  push    rbp
0x1400173f3  push    rdi
0x1400173f4  push    r12
0x1400173f6  push    r14
0x1400173f8  push    r15
0x1400173fa  lea     rbp, [rsp-37h]
0x1400173ff  sub     rsp, 0B0h
0x140017406  mov     rax, cs:__security_cookie
0x14001740d  xor     rax, rsp
0x140017410  mov     [rbp+57h+var_28], rax
0x140017414  xorps   xmm0, xmm0
0x140017417  mov     [rbp+57h+Owner], 0
0x14001741f  xor     eax, eax
0x140017421  mov     r12, rcx
0x140017424  xor     esi, esi
0x140017426  mov     [rbp+57h+var_60], rax
0x14001742a  mov     [rbp+57h+var_88], rsi
0x14001742e  movups  [rbp+57h+SecurityDescriptor], xmm0
0x140017432  mov     [rbp+57h+Dacl], rax
0x140017436  movups  [rbp+57h+var_70], xmm0
0x14001743a  mov     [rbp+57h+BufferLength], eax
0x14001743d  movups  [rbp+57h+var_58], xmm0
0x140017441  movups  [rbp+57h+var_48], xmm0
0x140017445  movups  [rbp+57h+var_38], xmm0
0x140017449  mov     rcx, cs:WPP_GLOBAL_Control
0x140017450  lea     r15, WPP_GLOBAL_Control
0x140017457  cmp     rcx, r15
0x14001745a  jz      short loc_14001747B
0x14001745c  test    dword ptr [rcx+2Ch], 40000h
0x140017463  jz      short loc_14001747B
0x140017465  mov     rcx, [rcx+18h]
0x140017469  lea     edx, [rax+14h]
0x14001746c  xor     r9d, r9d
0x14001746f  lea     r8, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids
0x140017476  call    WPP_SF_d
0x14001747b  xor     edx, edx
0x14001747d  lea     rcx, [rbp+57h+Owner]
0x140017481  call    CscSeCreateSid
0x140017486  mov     r14, [rbp+57h+Owner]
0x14001748a  mov     ebx, eax
0x14001748c  test    eax, eax
0x14001748e  jns     short loc_14001749A
0x140017490  mov     edi, 239h
0x140017495  jmp     loc_1400175BB
0x14001749a  lea     rdx, [rbp+57h+var_58]
0x14001749e  mov     qword ptr [rbp+57h+var_58], r14
0x1400174a2  lea     rcx, [rbp+57h+Dacl]
0x1400174a6  mov     dword ptr [rbp+57h+var_58+8], 1F01FFh
0x1400174ad  call    CscSeCreateAcl
0x1400174b2  mov     r15, [rbp+57h+Dacl]
0x1400174b6  mov     ebx, eax
0x1400174b8  test    eax, eax
0x1400174ba  jns     short loc_1400174C6
0x1400174bc  mov     edi, 255h
0x1400174c1  jmp     loc_1400175A6
0x1400174c6  mov     edx, 1; Revision
0x1400174cb  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400174cf  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400174d6  nop     dword ptr [rax+rax+00h]
0x1400174db  mov     ebx, eax
0x1400174dd  test    eax, eax
0x1400174df  jns     short loc_1400174EB
0x1400174e1  mov     edi, 260h
0x1400174e6  jmp     loc_1400175A6
0x1400174eb  xor     r8d, r8d; OwnerDefaulted
0x1400174ee  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400174f2  mov     rdx, r14; Owner
0x1400174f5  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1400174fc  nop     dword ptr [rax+rax+00h]
0x140017501  mov     ebx, eax
0x140017503  test    eax, eax
0x140017505  jns     short loc_140017511
0x140017507  mov     edi, 26Ah
0x14001750c  jmp     loc_1400175A6
0x140017511  xor     r9d, r9d; DaclDefaulted
0x140017514  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140017518  mov     r8, r15; Dacl
0x14001751b  mov     dl, 1; DaclPresent
0x14001751d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140017524  nop     dword ptr [rax+rax+00h]
0x140017529  mov     ebx, eax
0x14001752b  test    eax, eax
0x14001752d  jns     short loc_140017536
0x14001752f  mov     edi, 275h
0x140017534  jmp     short loc_1400175A6
0x140017536  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x14001753a  mov     [rbp+57h+BufferLength], esi
0x14001753d  xor     edx, edx; SelfRelativeSecurityDescriptor
0x14001753f  lea     rcx, [rbp+57h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140017543  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14001754a  nop     dword ptr [rax+rax+00h]
0x14001754f  mov     edx, [rbp+57h+BufferLength]
0x140017552  mov     ecx, 102h
0x140017557  mov     r8d, 21407343h
0x14001755d  call    cs:__imp_ExAllocatePool2
0x140017564  nop     dword ptr [rax+rax+00h]
0x140017569  mov     [rbp+57h+var_88], rax
0x14001756d  mov     rsi, rax
0x140017570  test    rax, rax
0x140017573  jnz     short loc_140017581
0x140017575  mov     ebx, 0C000009Ah
0x14001757a  mov     edi, 28Dh
0x14001757f  jmp     short loc_1400175A6
0x140017581  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x140017585  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x140017588  lea     rcx, [rbp+57h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14001758c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140017593  nop     dword ptr [rax+rax+00h]
0x140017598  mov     ebx, eax
0x14001759a  xor     edi, edi
0x14001759c  test    ebx, ebx
0x14001759e  mov     eax, 297h
0x1400175a3  cmovs   edi, eax
0x1400175a6  test    r15, r15
0x1400175a9  jz      short loc_1400175B4
0x1400175ab  lea     rcx, [rbp+57h+Dacl]
0x1400175af  call    CscSeDestroySid
0x1400175b4  lea     r15, WPP_GLOBAL_Control
0x1400175bb  test    r14, r14
0x1400175be  jz      short loc_1400175C9
0x1400175c0  lea     rcx, [rbp+57h+Owner]
0x1400175c4  call    CscSeDestroySid
0x1400175c9  test    ebx, ebx
0x1400175cb  jns     short loc_1400175DF
0x1400175cd  test    rsi, rsi
0x1400175d0  jz      short loc_1400175DF
0x1400175d2  lea     rcx, [rbp+57h+var_88]
0x1400175d6  call    CscSeDestroySecurityDescriptor
0x1400175db  mov     rsi, [rbp+57h+var_88]
0x1400175df  mov     [r12], rsi
0x1400175e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175ea  cmp     rcx, r15
0x1400175ed  jz      short loc_140017618
0x1400175ef  test    dword ptr [rcx+2Ch], 40000h
0x1400175f6  jz      short loc_140017618
0x1400175f8  mov     rcx, [rcx+18h]
0x1400175fc  lea     r8, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids
0x140017603  mov     edx, 15h
0x140017608  mov     [rsp+0D0h+var_A8], edi
0x14001760c  mov     r9, rsi
0x14001760f  mov     [rsp+0D0h+var_B0], ebx
0x140017613  call    WPP_SF_qDD
0x140017618  mov     eax, ebx
0x14001761a  mov     rcx, [rbp+57h+var_28]
0x14001761e  xor     rcx, rsp; StackCookie
0x140017621  call    __security_check_cookie
0x140017626  lea     r11, [rsp+0D0h+var_20]
0x14001762e  mov     rbx, [r11+38h]
0x140017632  mov     rsi, [r11+40h]
0x140017636  mov     rsp, r11
0x140017639  pop     r15
0x14001763b  pop     r14
0x14001763d  pop     r12
0x14001763f  pop     rdi
0x140017640  pop     rbp
0x140017641  retn
```

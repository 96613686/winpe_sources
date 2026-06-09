# NbtCreateSmbDevice

- ea: `0x140045254`
- end: `0x140045524`
- name: `NbtCreateSmbDevice`
- size: `720`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140053828`

## callees

- `0x140015340`
- `0x14001aa0c`
- `0x140030f40`
- `0x1400400a4`
- `0x140040294`
- `0x140045254`
- `0x14004c1a4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400452cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400452ed`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400452cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400452ed`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400454f7`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400454f7`
- `ntoskrnl!KeStackAttachProcess` at `0x14004531e`
- `ntoskrnl!KeStackAttachProcess` at `0x14004531e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140045302`
- `ntoskrnl!PsGetCurrentProcess` at `0x140045302`

## pseudocode

```c
__int64 NbtCreateSmbDevice()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  char v3; // di
  int v4; // eax
  unsigned int v5; // ebx
  int AddressObjects; // eax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v10; // [rsp+40h] [rbp-39h] BYREF
  UNICODE_STRING v11; // [rsp+48h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-21h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+68h] [rbp-11h] BYREF

  v10 = 0;
  DestinationString = 0;
  v11 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( (BYTE3(xmmword_140038420) & 1) != 0 )
    WPP_SF_(1048, 49, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids);
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Netbt_Smb_Bind");
  DestinationString.MaximumLength = 46;
  RtlInitUnicodeString(&v11, L"\\Device\\NetbiosSmb");
  v11.MaximumLength = 38;
  if ( (PRKPROCESS)PsGetCurrentProcess(v1, v0, v2) == NbtFspProcess )
  {
    v3 = 0;
  }
  else
  {
    KeStackAttachProcess(NbtFspProcess, &ApcState);
    v3 = 1;
  }
  v4 = NbtCreateDeviceObject(&DestinationString, &v11, 0, (PDEVICE_OBJECT *)&v10, 1);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (BYTE3(xmmword_140038420) & 1) == 0 )
      goto LABEL_22;
    WPP_SF_d(1048, 53, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids, (unsigned int)v4);
    if ( (BYTE3(xmmword_140038420) & 1) == 0 )
      goto LABEL_22;
    v8 = 54;
LABEL_21:
    WPP_SF_d(1048, v8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids, v5);
    goto LABEL_22;
  }
  *(_WORD *)(v10 + 872) = dword_14003969C;
  *(_WORD *)(v10 + 876) = HIWORD(dword_14003969C);
  *(_WORD *)(v10 + 874) = 0;
  *(_OWORD *)(v10 + 878) = *(_OWORD *)"*SMBSERVER      ";
  AddressObjects = NbtCreateAddressObjects(2130706433, 0, v10);
  v5 = AddressObjects;
  *(_DWORD *)(v10 + 496) = 2130706432;
  if ( AddressObjects < 0 )
  {
    if ( (BYTE3(xmmword_140038420) & 1) == 0 )
      goto LABEL_22;
    WPP_SF_d(1048, 51, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids, (unsigned int)AddressObjects);
    if ( (BYTE3(xmmword_140038420) & 1) == 0 )
      goto LABEL_22;
    v8 = 52;
    goto LABEL_21;
  }
  if ( *(_QWORD *)(v10 + 624) )
  {
    NbtSetTcpInfo(*(PFILE_OBJECT *)(v10 + 640));
    NbtSetTcpInfo(*(PFILE_OBJECT *)(v10 + 640));
  }
  v7 = *(_QWORD *)(v10 + 616);
  if ( v7 && *(_QWORD *)(v7 + 32) )
  {
    NbtSetTcpInfo(*(PFILE_OBJECT *)(v7 + 48));
    NbtSetTcpInfo(*(PFILE_OBJECT *)(*(_QWORD *)(v10 + 616) + 48LL));
  }
  if ( (BYTE3(xmmword_140038420) & 1) != 0 )
    WPP_SF_(1048, 50, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids);
LABEL_22:
  if ( v3 )
    KeUnstackDetachProcess(&ApcState);
  return v10;
}

```

## disassembly

```asm
0x140045254  push    rbp
0x140045256  push    rbx
0x140045257  push    rsi
0x140045258  push    rdi
0x140045259  push    r12
0x14004525b  push    r15
0x14004525d  lea     rbp, [rsp-2Fh]
0x140045262  sub     rsp, 0A8h
0x140045269  mov     rax, cs:__security_cookie
0x140045270  xor     rax, rsp
0x140045273  mov     [rbp+57h+var_38], rax
0x140045277  xorps   xmm0, xmm0
0x14004527a  mov     [rbp+57h+var_90], 0
0x140045282  xorps   xmm1, xmm1
0x140045285  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140045289  movups  xmmword ptr [rbp+57h+var_88.Length], xmm1
0x14004528d  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x140045291  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x140045295  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x140045299  mov     esi, 1
0x14004529e  lea     r12, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x1400452a5  test    byte ptr cs:xmmword_140038420+3, sil
0x1400452ac  mov     r15d, 418h
0x1400452b2  jz      short loc_1400452C2
0x1400452b4  lea     edx, [rsi+30h]
0x1400452b7  mov     ecx, r15d
0x1400452ba  mov     r8, r12
0x1400452bd  call    WPP_SF_
0x1400452c2  lea     rdx, aDeviceNetbtSmb; "\\Device\\Netbt_Smb_Bind"
0x1400452c9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400452cd  call    cs:__imp_RtlInitUnicodeString
0x1400452d4  nop     dword ptr [rax+rax+00h]
0x1400452d9  mov     eax, 2Eh ; '.'
0x1400452de  lea     rdx, aDeviceNetbioss; "\\Device\\NetbiosSmb"
0x1400452e5  lea     rcx, [rbp+57h+var_88]; DestinationString
0x1400452e9  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x1400452ed  call    cs:__imp_RtlInitUnicodeString
0x1400452f4  nop     dword ptr [rax+rax+00h]
0x1400452f9  mov     eax, 26h ; '&'
0x1400452fe  mov     [rbp+57h+var_88.MaximumLength], ax
0x140045302  call    cs:__imp_PsGetCurrentProcess
0x140045309  nop     dword ptr [rax+rax+00h]
0x14004530e  mov     rcx, cs:NbtFspProcess; PROCESS
0x140045315  cmp     rax, rcx
0x140045318  jz      short loc_14004532F
0x14004531a  lea     rdx, [rbp+57h+ApcState]; ApcState
0x14004531e  call    cs:__imp_KeStackAttachProcess
0x140045325  nop     dword ptr [rax+rax+00h]
0x14004532a  mov     dil, sil
0x14004532d  jmp     short loc_140045332
0x14004532f  xor     dil, dil
0x140045332  lea     rax, NBT_DEVICE_CLASS_GUID
0x140045339  xor     r8d, r8d
0x14004533c  mov     [rsp+0D0h+var_A0], rax
0x140045341  lea     r9, [rbp+57h+var_90]
0x140045345  lea     rax, NBT_DEVICE_OBJECT_SDDL
0x14004534c  mov     [rsp+0D0h+var_A8], rax
0x140045351  lea     rdx, [rbp+57h+var_88]; PCUNICODE_STRING
0x140045355  lea     rcx, [rbp+57h+DestinationString]; SourceString
0x140045359  mov     [rsp+0D0h+var_B0], esi; int
0x14004535d  call    NbtCreateDeviceObject
0x140045362  mov     ebx, eax
0x140045364  test    eax, eax
0x140045366  js      loc_1400454B6
0x14004536c  mov     rax, [rbp+57h+var_90]
0x140045370  xor     edx, edx
0x140045372  movzx   ecx, word ptr cs:dword_14003969C
0x140045379  mov     [rax+368h], cx
0x140045380  mov     rcx, [rbp+57h+var_90]
0x140045384  movzx   eax, word ptr cs:dword_14003969C+2
0x14004538b  mov     [rcx+36Ch], ax
0x140045392  xor     ecx, ecx
0x140045394  mov     rax, [rbp+57h+var_90]
0x140045398  mov     [rax+36Ah], cx
0x14004539f  mov     ecx, 7F000001h
0x1400453a4  mov     rax, [rbp+57h+var_90]
0x1400453a8  movups  xmm0, xmmword ptr cs:aSmbserver; "*SMBSERVER      "
0x1400453af  movdqu  xmmword ptr [rax+36Eh], xmm0
0x1400453b7  mov     r8, [rbp+57h+var_90]
0x1400453bb  call    NbtCreateAddressObjects
0x1400453c0  mov     rcx, [rbp+57h+var_90]
0x1400453c4  mov     ebx, eax
0x1400453c6  mov     dword ptr [rcx+1F0h], 7F000000h
0x1400453d0  test    eax, eax
0x1400453d2  js      loc_14004548A
0x1400453d8  mov     rcx, [rbp+57h+var_90]
0x1400453dc  mov     ebx, 200h
0x1400453e1  cmp     qword ptr [rcx+270h], 0
0x1400453e9  jz      short loc_140045421
0x1400453eb  mov     rcx, [rcx+280h]; FileObject
0x1400453f2  mov     r9d, esi
0x1400453f5  mov     r8d, ebx
0x1400453f8  mov     edx, 18h
0x1400453fd  call    NbtSetTcpInfo
0x140045402  mov     rcx, [rbp+57h+var_90]
0x140045406  mov     r8d, ebx
0x140045409  mov     edx, 19h
0x14004540e  mov     r9d, [rcx+2BCh]
0x140045415  mov     rcx, [rcx+280h]; FileObject
0x14004541c  call    NbtSetTcpInfo
0x140045421  mov     rax, [rbp+57h+var_90]
0x140045425  mov     rcx, [rax+268h]
0x14004542c  test    rcx, rcx
0x14004542f  jz      short loc_14004546F
0x140045431  cmp     qword ptr [rcx+20h], 0
0x140045436  jz      short loc_14004546F
0x140045438  mov     rcx, [rcx+30h]; FileObject
0x14004543c  mov     r9d, esi
0x14004543f  mov     r8d, ebx
0x140045442  mov     edx, 18h
0x140045447  call    NbtSetTcpInfo
0x14004544c  mov     r9, [rbp+57h+var_90]
0x140045450  mov     r8d, ebx
0x140045453  mov     edx, 19h
0x140045458  mov     rcx, [r9+268h]
0x14004545f  mov     r9d, [r9+2BCh]
0x140045466  mov     rcx, [rcx+30h]; FileObject
0x14004546a  call    NbtSetTcpInfo
0x14004546f  test    byte ptr cs:xmmword_140038420+3, sil
0x140045476  jz      short loc_1400454EE
0x140045478  mov     edx, 32h ; '2'
0x14004547d  mov     ecx, r15d
0x140045480  mov     r8, r12
0x140045483  call    WPP_SF_
0x140045488  jmp     short loc_1400454EE
0x14004548a  test    byte ptr cs:xmmword_140038420+3, sil
0x140045491  jz      short loc_1400454EE
0x140045493  mov     edx, 33h ; '3'
0x140045498  mov     ecx, r15d
0x14004549b  mov     r9d, ebx
0x14004549e  mov     r8, r12
0x1400454a1  call    WPP_SF_d
0x1400454a6  test    byte ptr cs:xmmword_140038420+3, sil
0x1400454ad  jz      short loc_1400454EE
0x1400454af  mov     edx, 34h ; '4'
0x1400454b4  jmp     short loc_1400454E0
0x1400454b6  test    byte ptr cs:xmmword_140038420+3, sil
0x1400454bd  jz      short loc_1400454EE
0x1400454bf  mov     edx, 35h ; '5'
0x1400454c4  mov     ecx, r15d
0x1400454c7  mov     r9d, ebx
0x1400454ca  mov     r8, r12
0x1400454cd  call    WPP_SF_d
0x1400454d2  test    byte ptr cs:xmmword_140038420+3, sil
0x1400454d9  jz      short loc_1400454EE
0x1400454db  mov     edx, 36h ; '6'
0x1400454e0  mov     r9d, ebx
0x1400454e3  mov     r8, r12
0x1400454e6  mov     ecx, r15d
0x1400454e9  call    WPP_SF_d
0x1400454ee  test    dil, dil
0x1400454f1  jz      short loc_140045503
0x1400454f3  lea     rcx, [rbp+57h+ApcState]; ApcState
0x1400454f7  call    cs:__imp_KeUnstackDetachProcess
0x1400454fe  nop     dword ptr [rax+rax+00h]
0x140045503  mov     rax, [rbp+57h+var_90]
0x140045507  mov     rcx, [rbp+57h+var_38]
0x14004550b  xor     rcx, rsp; StackCookie
0x14004550e  call    __security_check_cookie
0x140045513  add     rsp, 0A8h
0x14004551a  pop     r15
0x14004551c  pop     r12
0x14004551e  pop     rdi
0x14004551f  pop     rsi
0x140045520  pop     rbx
0x140045521  pop     rbp
0x140045522  retn
```

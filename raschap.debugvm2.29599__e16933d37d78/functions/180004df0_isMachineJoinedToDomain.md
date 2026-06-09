# isMachineJoinedToDomain

- ea: `0x180004df0`
- end: `0x180004f3d`
- name: `isMachineJoinedToDomain`
- size: `333`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001260`
- `0x180002040`
- `0x180003530`
- `0x1800038d0`
- `0x180004f50`
- `0x180005df0`

## callees

- `0x180003bd0`
- `0x180004df0`
- `0x180006a20`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x180004e45`
- `netutils!NetApiBufferFree` at `0x180004e45`
- `wkscli!NetGetJoinInformation` at `0x180004e16`
- `wkscli!NetGetJoinInformation` at `0x180004e16`

## pseudocode

```c
__int64 isMachineJoinedToDomain()
{
  unsigned int v0; // ebx
  DWORD JoinInformation; // eax
  _NETSETUP_JOIN_STATUS v2; // r9d
  _QWORD *v3; // rcx
  _QWORD *v5; // rcx
  USHORT v6; // dx
  USHORT v7; // dx
  _QWORD *v8; // rcx
  USHORT v9; // dx
  _NETSETUP_JOIN_STATUS BufferType; // [rsp+30h] [rbp+8h] BYREF
  LPWSTR NameBuffer; // [rsp+38h] [rbp+10h] BYREF

  NameBuffer = 0;
  BufferType = NetSetupUnknownStatus;
  v0 = 1;
  JoinInformation = NetGetJoinInformation(0, &NameBuffer, &BufferType);
  if ( JoinInformation )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_5;
    v6 = 10;
    v2 = JoinInformation;
LABEL_10:
    WPP_SF_d(v5[2], v6, (const GUID *)WPP_a4d11cea5dd4349ec5b90c3f916b9bf6_Traceguids, v2);
    goto LABEL_5;
  }
  v2 = BufferType;
  if ( BufferType != NetSetupWorkgroupName )
  {
    if ( BufferType )
    {
      if ( BufferType == NetSetupUnjoined )
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_4;
        v7 = 12;
        goto LABEL_9;
      }
      if ( BufferType != NetSetupDomainName )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_5;
        v6 = 15;
        goto LABEL_10;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_5;
      v9 = 14;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_5;
      v9 = 11;
    }
    WPP_SF_(v8[2], v9, (const GUID *)WPP_a4d11cea5dd4349ec5b90c3f916b9bf6_Traceguids);
    goto LABEL_5;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v7 = 13;
LABEL_9:
    WPP_SF_(v3[2], v7, (const GUID *)WPP_a4d11cea5dd4349ec5b90c3f916b9bf6_Traceguids);
  }
LABEL_4:
  v0 = 0;
LABEL_5:
  NetApiBufferFree(NameBuffer);
  return v0;
}

```

## disassembly

```asm
0x180004df0  mov     [rsp+arg_10], rbx
0x180004df5  push    rdi
0x180004df6  sub     rsp, 20h
0x180004dfa  xor     edi, edi
0x180004dfc  lea     r8, [rsp+28h+BufferType]; BufferType
0x180004e01  lea     rdx, [rsp+28h+NameBuffer]; lpNameBuffer
0x180004e06  mov     [rsp+28h+NameBuffer], rdi
0x180004e0b  xor     ecx, ecx; lpServer
0x180004e0d  mov     [rsp+28h+BufferType], edi
0x180004e11  mov     ebx, 1
0x180004e16  call    cs:__imp_NetGetJoinInformation
0x180004e1c  test    eax, eax
0x180004e1e  jnz     short loc_180004E58
0x180004e20  mov     r9d, [rsp+28h+BufferType]
0x180004e25  cmp     r9d, 2
0x180004e29  jnz     short loc_180004EA3
0x180004e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e32  lea     rdx, WPP_GLOBAL_Control
0x180004e39  cmp     rcx, rdx
0x180004e3c  jnz     short loc_180004E75
0x180004e3e  mov     ebx, edi
0x180004e40  mov     rcx, [rsp+28h+NameBuffer]; Buffer
0x180004e45  call    cs:__imp_NetApiBufferFree
0x180004e4b  mov     eax, ebx
0x180004e4d  mov     rbx, [rsp+28h+arg_10]
0x180004e52  add     rsp, 20h
0x180004e56  pop     rdi
0x180004e57  retn
0x180004e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e5f  lea     rdx, WPP_GLOBAL_Control
0x180004e66  cmp     rcx, rdx
0x180004e69  jz      short loc_180004E40
0x180004e6b  mov     edx, 0Ah
0x180004e70  mov     r9d, eax
0x180004e73  jmp     short loc_180004E91
0x180004e75  mov     edx, 0Dh
0x180004e7a  mov     rcx, [rcx+10h]
0x180004e7e  lea     r8, WPP_a4d11cea5dd4349ec5b90c3f916b9bf6_Traceguids
0x180004e85  call    WPP_SF_
0x180004e8a  jmp     short loc_180004E3E
0x180004e8c  mov     edx, 0Fh
0x180004e91  mov     rcx, [rcx+10h]
0x180004e95  lea     r8, WPP_a4d11cea5dd4349ec5b90c3f916b9bf6_Traceguids
0x180004e9c  call    WPP_SF_d
0x180004ea1  jmp     short loc_180004E40
0x180004ea3  mov     ecx, r9d
0x180004ea6  test    r9d, r9d
0x180004ea9  jz      short loc_180004F0C
0x180004eab  sub     ecx, ebx
0x180004ead  jz      short loc_180004EEB
0x180004eaf  cmp     ecx, 2
0x180004eb2  jz      short loc_180004ECD
0x180004eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ebb  lea     rdx, WPP_GLOBAL_Control
0x180004ec2  cmp     rcx, rdx
0x180004ec5  jz      loc_180004E40
0x180004ecb  jmp     short loc_180004E8C
0x180004ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ed4  lea     rdx, WPP_GLOBAL_Control
0x180004edb  cmp     rcx, rdx
0x180004ede  jz      loc_180004E40
0x180004ee4  mov     edx, 0Eh
0x180004ee9  jmp     short loc_180004F28
0x180004eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ef2  lea     rdx, WPP_GLOBAL_Control
0x180004ef9  cmp     rcx, rdx
0x180004efc  jz      loc_180004E3E
0x180004f02  mov     edx, 0Ch
0x180004f07  jmp     loc_180004E7A
0x180004f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f13  lea     rdx, WPP_GLOBAL_Control
0x180004f1a  cmp     rcx, rdx
0x180004f1d  jz      loc_180004E40
0x180004f23  mov     edx, 0Bh
0x180004f28  mov     rcx, [rcx+10h]
0x180004f2c  lea     r8, WPP_a4d11cea5dd4349ec5b90c3f916b9bf6_Traceguids
0x180004f33  call    WPP_SF_
0x180004f38  jmp     loc_180004E40
```

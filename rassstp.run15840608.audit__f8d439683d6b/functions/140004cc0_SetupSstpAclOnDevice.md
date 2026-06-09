# SetupSstpAclOnDevice

- ea: `0x140004cc0`
- end: `0x140004fc4`
- name: `SetupSstpAclOnDevice`
- size: `772`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000e0ec`

## callees

- `0x140002bd8`
- `0x140002c08`
- `0x140004cc0`
- `0x140005e10`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140004e33`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140004e33`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140004ee7`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140004ee7`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140004e79`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140004e79`
- `ntoskrnl!ZwSetSecurityObject` at `0x140004f2d`
- `ntoskrnl!ZwSetSecurityObject` at `0x140004f2d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140004dd5`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140004dd5`
- `ntoskrnl!ZwClose` at `0x140004f70`
- `ntoskrnl!ZwClose` at `0x140004f70`

## pseudocode

```c
__int64 __fastcall SetupSstpAclOnDevice(PVOID Object)
{
  unsigned int v2; // ebx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v4; // rdx
  PDEVICE_OBJECT v5; // rcx
  HANDLE Handle; // [rsp+40h] [rbp-79h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-71h] BYREF
  __int64 v9; // [rsp+68h] [rbp-51h]
  _ACL Dacl; // [rsp+70h] [rbp-49h] BYREF
  int v11; // [rsp+78h] [rbp-41h]
  int v12; // [rsp+7Ch] [rbp-3Dh]
  int v13; // [rsp+80h] [rbp-39h]
  int v14; // [rsp+84h] [rbp-35h]
  int v15; // [rsp+88h] [rbp-31h]
  int v16; // [rsp+8Ch] [rbp-2Dh]
  int v17; // [rsp+90h] [rbp-29h]
  int v18; // [rsp+94h] [rbp-25h]
  int v19; // [rsp+98h] [rbp-21h]
  int v20; // [rsp+9Ch] [rbp-1Dh]
  int v21; // [rsp+A0h] [rbp-19h]
  int v22; // [rsp+A4h] [rbp-15h]
  int v23; // [rsp+A8h] [rbp-11h]
  int v24; // [rsp+ACh] [rbp-Dh]
  int v25; // [rsp+B0h] [rbp-9h]
  int v26; // [rsp+B4h] [rbp-5h]
  int v27; // [rsp+B8h] [rbp-1h]
  int v28; // [rsp+BCh] [rbp+3h]
  int v29; // [rsp+C0h] [rbp+7h]
  int v30; // [rsp+C4h] [rbp+Bh]

  *(_DWORD *)&Dacl.AclRevision = 5767170;
  *(_DWORD *)&Dacl.AceCount = 2;
  v11 = 2621440;
  v9 = 0;
  v12 = 0x10000000;
  v13 = 1537;
  v14 = 83886080;
  v15 = 80;
  v16 = -859265410;
  v17 = 799518250;
  v18 = -503583807;
  v19 = -1066671174;
  v20 = -1356082982;
  v21 = 2621440;
  v22 = 0x10000000;
  v23 = 1537;
  v24 = 83886080;
  v25 = 80;
  v26 = -118600422;
  v27 = 305252471;
  v28 = -2038250239;
  v29 = -1580777525;
  v30 = -742434506;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  Handle = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids);
  v2 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( !v2 )
  {
    v2 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Dacl, 0);
    if ( v2 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v2;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
        goto LABEL_32;
      v4 = 12;
    }
    else if ( RtlValidSecurityDescriptor(SecurityDescriptor) )
    {
      WORD1(SecurityDescriptor[0]) |= 0x1000u;
      v2 = ObOpenObjectByPointer(Object, 0x200u, 0, 0x40000u, 0, 0, &Handle);
      if ( !v2 )
      {
        v2 = ZwSetSecurityObject(Handle, 4u, SecurityDescriptor);
        if ( v2
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids);
        }
        ZwClose(Handle);
        goto LABEL_32;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v2;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
        goto LABEL_32;
      v4 = 14;
    }
    else
    {
      v2 = -1073741703;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v2;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
        goto LABEL_32;
      v4 = 13;
    }
    AttachedDevice = v5->AttachedDevice;
    goto LABEL_9;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v4 = 11;
LABEL_9:
    WPP_SF_d(AttachedDevice, v4, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids);
  }
LABEL_32:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x140004cc0  push    rbp
0x140004cc2  push    rbx
0x140004cc3  push    rsi
0x140004cc4  push    rdi
0x140004cc5  push    r12
0x140004cc7  push    r15
0x140004cc9  lea     rbp, [rsp-2Fh]
0x140004cce  sub     rsp, 0E8h
0x140004cd5  mov     rax, cs:__security_cookie
0x140004cdc  xor     rax, rsp
0x140004cdf  mov     [rbp+57h+var_40], rax
0x140004ce3  xor     esi, esi
0x140004ce5  mov     dword ptr [rbp+57h+Dacl.AclRevision], 580002h
0x140004cec  xorps   xmm0, xmm0
0x140004cef  mov     dword ptr [rbp+57h+Dacl.AceCount], 2
0x140004cf6  xor     eax, eax
0x140004cf8  mov     [rbp+57h+var_98], 280000h
0x140004cff  mov     [rbp+57h+var_A8], rax
0x140004d03  mov     rdi, rcx
0x140004d06  mov     [rbp+57h+var_94], 10000000h
0x140004d0d  mov     [rbp+57h+var_90], 601h
0x140004d14  mov     [rbp+57h+var_8C], 5000000h
0x140004d1b  mov     [rbp+57h+var_88], 50h ; 'P'
0x140004d22  mov     [rbp+57h+var_84], 0CCC8A67Eh
0x140004d29  mov     [rbp+57h+var_80], 2FA7AE2Ah
0x140004d30  mov     [rbp+57h+var_7C], 0E1FBEBC1h
0x140004d37  mov     [rbp+57h+var_78], 0C06BE3BAh
0x140004d3e  mov     [rbp+57h+var_74], 0AF2BD0DAh
0x140004d45  mov     [rbp+57h+var_70], 280000h
0x140004d4c  mov     [rbp+57h+var_6C], 10000000h
0x140004d53  mov     [rbp+57h+var_68], 601h
0x140004d5a  mov     [rbp+57h+var_64], 5000000h
0x140004d61  mov     [rbp+57h+var_60], 50h ; 'P'
0x140004d68  mov     [rbp+57h+var_5C], 0F8EE4D1Ah
0x140004d6f  mov     [rbp+57h+var_58], 1231C877h
0x140004d76  mov     [rbp+57h+var_54], 8682C501h
0x140004d7d  mov     [rbp+57h+var_50], 0A1C73FCBh
0x140004d84  mov     [rbp+57h+var_4C], 0D3BF5936h
0x140004d8b  movups  [rbp+57h+SecurityDescriptor], xmm0
0x140004d8f  mov     [rbp+57h+var_D0], rsi
0x140004d93  movups  [rbp+57h+var_B8], xmm0
0x140004d97  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d9e  lea     r15, WPP_GLOBAL_Control
0x140004da5  lea     r12, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids
0x140004dac  cmp     rcx, r15
0x140004daf  jz      short loc_140004DCC
0x140004db1  mov     eax, [rcx+2Ch]
0x140004db4  and     eax, 81h
0x140004db9  cmp     al, 81h
0x140004dbb  jnz     short loc_140004DCC
0x140004dbd  mov     rcx, [rcx+18h]
0x140004dc1  lea     edx, [rsi+0Ah]
0x140004dc4  mov     r8, r12
0x140004dc7  call    WPP_SF_
0x140004dcc  mov     edx, 1; Revision
0x140004dd1  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140004dd5  call    cs:__imp_RtlCreateSecurityDescriptor
0x140004ddc  nop     dword ptr [rax+rax+00h]
0x140004de1  mov     ebx, eax
0x140004de3  test    eax, eax
0x140004de5  jz      short loc_140004E26
0x140004de7  mov     rax, cs:WPP_GLOBAL_Control
0x140004dee  cmp     rax, r15
0x140004df1  jz      loc_140004FA5
0x140004df7  mov     ecx, [rax+2Ch]
0x140004dfa  test    cl, 1
0x140004dfd  jz      loc_140004F7C
0x140004e03  cmp     byte ptr [rax+29h], 1
0x140004e07  jb      loc_140004F7C
0x140004e0d  mov     rcx, [rax+18h]
0x140004e11  mov     edx, 0Bh
0x140004e16  mov     r8, r12
0x140004e19  mov     r9d, ebx
0x140004e1c  call    WPP_SF_d
0x140004e21  jmp     loc_140004F7C
0x140004e26  xor     r9d, r9d; DaclDefaulted
0x140004e29  lea     r8, [rbp+57h+Dacl]; Dacl
0x140004e2d  mov     dl, 1; DaclPresent
0x140004e2f  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140004e33  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140004e3a  nop     dword ptr [rax+rax+00h]
0x140004e3f  mov     ebx, eax
0x140004e41  test    eax, eax
0x140004e43  jz      short loc_140004E75
0x140004e45  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e4c  cmp     rcx, r15
0x140004e4f  jz      loc_140004FA5
0x140004e55  mov     eax, [rcx+2Ch]
0x140004e58  test    al, 1
0x140004e5a  jz      loc_140004F7C
0x140004e60  cmp     byte ptr [rcx+29h], 1
0x140004e64  jb      loc_140004F7C
0x140004e6a  mov     edx, 0Ch
0x140004e6f  mov     rcx, [rcx+18h]
0x140004e73  jmp     short loc_140004E16
0x140004e75  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140004e79  call    cs:__imp_RtlValidSecurityDescriptor
0x140004e80  nop     dword ptr [rax+rax+00h]
0x140004e85  test    al, al
0x140004e87  jnz     short loc_140004EBA
0x140004e89  mov     ebx, 0C0000079h
0x140004e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e95  cmp     rcx, r15
0x140004e98  jz      loc_140004FA5
0x140004e9e  mov     eax, [rcx+2Ch]
0x140004ea1  test    al, 1
0x140004ea3  jz      loc_140004F7C
0x140004ea9  cmp     byte ptr [rcx+29h], 1
0x140004ead  jb      loc_140004F7C
0x140004eb3  mov     edx, 0Dh
0x140004eb8  jmp     short loc_140004E6F
0x140004eba  mov     eax, 1000h
0x140004ebf  mov     r9d, 40000h; DesiredAccess
0x140004ec5  or      word ptr [rbp+57h+SecurityDescriptor+2], ax
0x140004ec9  xor     r8d, r8d; PassedAccessState
0x140004ecc  lea     rax, [rbp+57h+var_D0]
0x140004ed0  mov     edx, 200h; HandleAttributes
0x140004ed5  mov     [rsp+110h+Handle], rax; Handle
0x140004eda  mov     rcx, rdi; Object
0x140004edd  mov     [rsp+110h+AccessMode], sil; AccessMode
0x140004ee2  mov     [rsp+110h+ObjectType], rsi; ObjectType
0x140004ee7  call    cs:__imp_ObOpenObjectByPointer
0x140004eee  nop     dword ptr [rax+rax+00h]
0x140004ef3  mov     ebx, eax
0x140004ef5  test    eax, eax
0x140004ef7  jz      short loc_140004F20
0x140004ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f00  cmp     rcx, r15
0x140004f03  jz      loc_140004FA5
0x140004f09  mov     eax, [rcx+2Ch]
0x140004f0c  test    al, 1
0x140004f0e  jz      short loc_140004F7C
0x140004f10  cmp     byte ptr [rcx+29h], 1
0x140004f14  jb      short loc_140004F7C
0x140004f16  mov     edx, 0Eh
0x140004f1b  jmp     loc_140004E6F
0x140004f20  mov     rcx, [rbp+57h+var_D0]; Handle
0x140004f24  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140004f28  mov     edx, 4; SecurityInformation
0x140004f2d  call    cs:__imp_ZwSetSecurityObject
0x140004f34  nop     dword ptr [rax+rax+00h]
0x140004f39  mov     ebx, eax
0x140004f3b  test    eax, eax
0x140004f3d  jz      short loc_140004F6C
0x140004f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f46  cmp     rcx, r15
0x140004f49  jz      short loc_140004F6C
0x140004f4b  mov     eax, [rcx+2Ch]
0x140004f4e  test    al, 1
0x140004f50  jz      short loc_140004F6C
0x140004f52  cmp     byte ptr [rcx+29h], 1
0x140004f56  jb      short loc_140004F6C
0x140004f58  mov     rcx, [rcx+18h]
0x140004f5c  mov     edx, 0Fh
0x140004f61  mov     r9d, ebx
0x140004f64  mov     r8, r12
0x140004f67  call    WPP_SF_d
0x140004f6c  mov     rcx, [rbp+57h+var_D0]; Handle
0x140004f70  call    cs:__imp_ZwClose
0x140004f77  nop     dword ptr [rax+rax+00h]
0x140004f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f83  cmp     rcx, r15
0x140004f86  jz      short loc_140004FA5
0x140004f88  mov     eax, [rcx+2Ch]
0x140004f8b  and     eax, 81h
0x140004f90  cmp     al, 81h
0x140004f92  jnz     short loc_140004FA5
0x140004f94  mov     rcx, [rcx+18h]
0x140004f98  mov     edx, 10h
0x140004f9d  mov     r8, r12
0x140004fa0  call    WPP_SF_
0x140004fa5  mov     eax, ebx
0x140004fa7  mov     rcx, [rbp+57h+var_40]
0x140004fab  xor     rcx, rsp; StackCookie
0x140004fae  call    __security_check_cookie
0x140004fb3  add     rsp, 0E8h
0x140004fba  pop     r15
0x140004fbc  pop     r12
0x140004fbe  pop     rdi
0x140004fbf  pop     rsi
0x140004fc0  pop     rbx
0x140004fc1  pop     rbp
0x140004fc2  retn
```

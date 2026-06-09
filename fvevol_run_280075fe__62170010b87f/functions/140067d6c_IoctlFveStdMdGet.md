# IoctlFveStdMdGet

- ea: `0x140067d6c`
- end: `0x14006822d`
- name: `IoctlFveStdMdGet`
- size: `1217`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x140068a40`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140016568`
- `0x140017e84`
- `0x140017fbc`
- `0x140021a00`
- `0x140021d00`
- `0x140065b08`
- `0x140067d6c`
- `0x14006b294`
- `0x140089574`
- `0x14008e180`
- `0x14008e6a0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140067e73`
- `ntoskrnl!ProbeForRead` at `0x140067e73`
- `ntoskrnl!ProbeForWrite` at `0x140068074`
- `ntoskrnl!ProbeForWrite` at `0x140068074`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006819f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400681c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006819f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400681c4`
- `ntoskrnl!ExAllocatePool2` at `0x140067e8d`
- `ntoskrnl!ExAllocatePool2` at `0x140067e8d`

## pseudocode

```c
__int64 __fastcall IoctlFveStdMdGet(void *a1, __int64 a2)
{
  char *v4; // r15
  __int64 v5; // rax
  volatile void *v6; // r12
  SIZE_T v7; // rdi
  int Request; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  char *Pool2; // rax
  _OWORD *v12; // r12
  _OWORD *v13; // rdi
  unsigned int *v14; // rdi
  int v16; // [rsp+20h] [rbp-E8h]
  char *v17; // [rsp+28h] [rbp-E0h]
  PVOID P; // [rsp+30h] [rbp-D8h] BYREF
  volatile void *Address; // [rsp+38h] [rbp-D0h]
  UNICODE_STRING SourceString[12]; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int Length; // [rsp+118h] [rbp+10h]
  unsigned int v23; // [rsp+120h] [rbp+18h]
  void *Src; // [rsp+128h] [rbp+20h] BYREF

  P = 0;
  v4 = 0;
  Src = 0;
  memset(SourceString, 0, 0x90u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 167, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
  }
  v5 = *(_QWORD *)(a2 + 184);
  v6 = *(volatile void **)(v5 + 32);
  v7 = *(unsigned int *)(v5 + 16);
  v23 = *(_DWORD *)(v5 + 16);
  Address = *(volatile void **)(a2 + 112);
  Length = *(_DWORD *)(v5 + 8);
  Request = FveKickAllSystemsGo(a1);
  if ( Request >= 0 )
  {
    if ( *(_BYTE *)(a2 + 64) )
      ProbeForRead(v6, v7, 4u);
    Pool2 = (char *)ExAllocatePool2(256, v7, 809850438);
    v4 = Pool2;
    v17 = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, (const void *)v6, v7);
    }
    else
    {
      Request = -1073741670;
      v16 = -1073741670;
    }
    if ( Request >= 0 )
    {
      Request = FveValidateStandaloneMetadataGetRequest(v4, v23);
      if ( Request >= 0 )
      {
        Request = FveVolumeInitInfo(a1, SourceString);
        if ( Request >= 0 )
        {
          Request = FveFsCreateSystemVolumeInformationFolder(SourceString);
          if ( Request >= 0 )
          {
            Request = FveReadStandaloneMetadata(SourceString, (GUID *)(v4 + 8), &P);
            if ( Request >= 0 )
            {
              Request = FveCreateStandaloneMetadataGetResponseFromDataSet(
                          v4 + 8,
                          *((_QWORD *)P + 2),
                          (char *)P + 24,
                          &Src,
                          v16,
                          v17);
              if ( Request >= 0 )
              {
                v12 = Address;
                if ( *(_BYTE *)(a2 + 64) )
                  ProbeForWrite(Address, Length, 8u);
                v13 = Src;
                if ( Length >= *(_DWORD *)Src )
                {
                  v14 = (unsigned int *)Src;
                  memmove(v12, Src, *(unsigned int *)Src);
                  *(_QWORD *)(a2 + 56) = *v14;
                }
                else if ( Length < 0x40 )
                {
                  Request = -1073741789;
                }
                else
                {
                  *v12 = *(_OWORD *)Src;
                  v12[1] = v13[1];
                  v12[2] = v13[2];
                  v12[3] = v13[3];
                  *(_QWORD *)(a2 + 56) = 64;
                }
              }
              else
              {
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v10 = 175;
                  goto LABEL_10;
                }
              }
            }
            else
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v10 = 174;
                goto LABEL_10;
              }
            }
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v10 = 173;
              goto LABEL_10;
            }
          }
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v10 = 172;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v10 = 171;
          goto LABEL_10;
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v10 = 170;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v10 = 168;
LABEL_10:
      WPP_SF_d(v9->AttachedDevice, v10, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)Request);
    }
  }
  if ( v4 )
    ExFreePoolWithTag(v4, 0x30455646u);
  FveVolumeCleanupInfo(SourceString);
  if ( P )
    ExFreePoolWithTag(P, 0x30455646u);
  if ( Src )
    FveLibClientFree(Src, *(unsigned int *)Src);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      178,
      WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
      (unsigned int)Request);
  }
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x140067d6c  mov     rax, rsp
0x140067d6f  mov     [rax+8], rcx
0x140067d73  push    rbx
0x140067d74  push    rdi
0x140067d75  push    r12
0x140067d77  push    r13
0x140067d79  push    r14
0x140067d7b  push    r15
0x140067d7d  sub     rsp, 0D8h
0x140067d84  mov     r13, rdx
0x140067d87  mov     rbx, rcx
0x140067d8a  mov     [rsp+108h+P], 0
0x140067d93  xor     r15d, r15d
0x140067d96  mov     [rsp+108h+var_E0], r15
0x140067d9b  mov     [rax+20h], r15
0x140067d9f  xor     edx, edx; Val
0x140067da1  mov     r8d, 90h; Size
0x140067da7  lea     rcx, [rsp+108h+SourceString]; void *
0x140067dac  call    memset
0x140067db1  lea     r14, WPP_GLOBAL_Control
0x140067db8  mov     rcx, cs:WPP_GLOBAL_Control
0x140067dbf  cmp     rcx, r14
0x140067dc2  jz      short loc_140067DE6
0x140067dc4  mov     eax, [rcx+2Ch]
0x140067dc7  test    al, 10h
0x140067dc9  jz      short loc_140067DE6
0x140067dcb  cmp     byte ptr [rcx+29h], 5
0x140067dcf  jb      short loc_140067DE6
0x140067dd1  mov     edx, 0A7h
0x140067dd6  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067ddd  mov     rcx, [rcx+18h]
0x140067de1  call    WPP_SF_
0x140067de6  mov     rax, [r13+0B8h]
0x140067ded  mov     r12, [rax+20h]
0x140067df1  mov     edi, [rax+10h]
0x140067df4  mov     [rsp+108h+arg_10], edi
0x140067dfb  mov     rcx, [r13+70h]
0x140067dff  mov     [rsp+108h+Address], rcx
0x140067e04  mov     eax, [rax+8]
0x140067e07  mov     dword ptr [rsp+108h+Length], eax
0x140067e0e  xor     edx, edx
0x140067e10  mov     rcx, rbx
0x140067e13  call    FveKickAllSystemsGo
0x140067e18  mov     ebx, eax
0x140067e1a  test    eax, eax
0x140067e1c  jns     short loc_140067E60
0x140067e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140067e25  cmp     rcx, r14
0x140067e28  jz      loc_140068192
0x140067e2e  mov     eax, [rcx+2Ch]
0x140067e31  test    al, 10h
0x140067e33  jz      loc_140068192
0x140067e39  cmp     byte ptr [rcx+29h], 2
0x140067e3d  jb      loc_140068192
0x140067e43  mov     edx, 0A8h
0x140067e48  mov     r9d, ebx
0x140067e4b  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067e52  mov     rcx, [rcx+18h]
0x140067e56  call    WPP_SF_d
0x140067e5b  jmp     loc_140068192
0x140067e60  cmp     byte ptr [r13+40h], 0
0x140067e65  jz      short loc_140067E7F
0x140067e67  mov     rdx, rdi; Length
0x140067e6a  mov     r8d, 4; Alignment
0x140067e70  mov     rcx, r12; Address
0x140067e73  call    cs:__imp_ProbeForRead
0x140067e7a  nop     dword ptr [rax+rax+00h]
0x140067e7f  mov     r8d, 30455646h
0x140067e85  mov     rdx, rdi
0x140067e88  mov     ecx, 100h
0x140067e8d  call    cs:__imp_ExAllocatePool2
0x140067e94  nop     dword ptr [rax+rax+00h]
0x140067e99  mov     r15, rax
0x140067e9c  mov     [rsp+108h+var_E0], rax
0x140067ea1  test    rax, rax
0x140067ea4  jnz     short loc_140067EB1
0x140067ea6  mov     ebx, 0C000009Ah
0x140067eab  mov     [rsp+108h+var_E8], ebx
0x140067eaf  jmp     short loc_140067EC0
0x140067eb1  mov     r8, rdi; Size
0x140067eb4  mov     rdx, r12; Src
0x140067eb7  mov     rcx, r15; void *
0x140067eba  call    memmove
0x140067ebf  nop
0x140067ec0  test    ebx, ebx
0x140067ec2  jns     short loc_140067EF3
0x140067ec4  mov     rcx, cs:WPP_GLOBAL_Control
0x140067ecb  cmp     rcx, r14
0x140067ece  jz      loc_140068192
0x140067ed4  mov     eax, [rcx+2Ch]
0x140067ed7  test    al, 10h
0x140067ed9  jz      loc_140068192
0x140067edf  cmp     byte ptr [rcx+29h], 2
0x140067ee3  jb      loc_140068192
0x140067ee9  mov     edx, 0AAh
0x140067eee  jmp     loc_140067E48
0x140067ef3  mov     edx, [rsp+108h+arg_10]
0x140067efa  mov     rcx, r15
0x140067efd  call    FveValidateStandaloneMetadataGetRequest
0x140067f02  mov     ebx, eax
0x140067f04  test    eax, eax
0x140067f06  jns     short loc_140067F37
0x140067f08  mov     rcx, cs:WPP_GLOBAL_Control
0x140067f0f  cmp     rcx, r14
0x140067f12  jz      loc_140068192
0x140067f18  mov     eax, [rcx+2Ch]
0x140067f1b  test    al, 10h
0x140067f1d  jz      loc_140068192
0x140067f23  cmp     byte ptr [rcx+29h], 2
0x140067f27  jb      loc_140068192
0x140067f2d  mov     edx, 0ABh
0x140067f32  jmp     loc_140067E48
0x140067f37  lea     rdx, [rsp+108h+SourceString]
0x140067f3c  mov     rcx, [rsp+108h+arg_0]
0x140067f44  call    FveVolumeInitInfo
0x140067f49  mov     ebx, eax
0x140067f4b  test    eax, eax
0x140067f4d  jns     short loc_140067F7E
0x140067f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140067f56  cmp     rcx, r14
0x140067f59  jz      loc_140068192
0x140067f5f  mov     eax, [rcx+2Ch]
0x140067f62  test    al, 10h
0x140067f64  jz      loc_140068192
0x140067f6a  cmp     byte ptr [rcx+29h], 2
0x140067f6e  jb      loc_140068192
0x140067f74  mov     edx, 0ACh
0x140067f79  jmp     loc_140067E48
0x140067f7e  lea     rcx, [rsp+108h+SourceString]; SourceString
0x140067f83  call    FveFsCreateSystemVolumeInformationFolder
0x140067f88  mov     ebx, eax
0x140067f8a  test    eax, eax
0x140067f8c  jns     short loc_140067FBD
0x140067f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140067f95  cmp     rcx, r14
0x140067f98  jz      loc_140068192
0x140067f9e  mov     eax, [rcx+2Ch]
0x140067fa1  test    al, 10h
0x140067fa3  jz      loc_140068192
0x140067fa9  cmp     byte ptr [rcx+29h], 2
0x140067fad  jb      loc_140068192
0x140067fb3  mov     edx, 0ADh
0x140067fb8  jmp     loc_140067E48
0x140067fbd  lea     r8, [rsp+108h+P]; P
0x140067fc2  lea     rdx, [r15+8]; Guid
0x140067fc6  lea     rcx, [rsp+108h+SourceString]; SourceString
0x140067fcb  call    FveReadStandaloneMetadata
0x140067fd0  mov     ebx, eax
0x140067fd2  test    eax, eax
0x140067fd4  jns     short loc_140068005
0x140067fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140067fdd  cmp     rcx, r14
0x140067fe0  jz      loc_140068192
0x140067fe6  mov     eax, [rcx+2Ch]
0x140067fe9  test    al, 10h
0x140067feb  jz      loc_140068192
0x140067ff1  cmp     byte ptr [rcx+29h], 2
0x140067ff5  jb      loc_140068192
0x140067ffb  mov     edx, 0AEh
0x140068000  jmp     loc_140067E48
0x140068005  mov     rdx, [rsp+108h+P]
0x14006800a  lea     r8, [rdx+18h]
0x14006800e  lea     r9, [rsp+108h+Src]
0x140068016  mov     rdx, [rdx+10h]
0x14006801a  lea     rcx, [r15+8]
0x14006801e  call    FveCreateStandaloneMetadataGetResponseFromDataSet
0x140068023  mov     ebx, eax
0x140068025  test    eax, eax
0x140068027  jns     short loc_140068058
0x140068029  mov     rcx, cs:WPP_GLOBAL_Control
0x140068030  cmp     rcx, r14
0x140068033  jz      loc_140068192
0x140068039  mov     eax, [rcx+2Ch]
0x14006803c  test    al, 10h
0x14006803e  jz      loc_140068192
0x140068044  cmp     byte ptr [rcx+29h], 2
0x140068048  jb      loc_140068192
0x14006804e  mov     edx, 0AFh
0x140068053  jmp     loc_140067E48
0x140068058  mov     r12, [rsp+108h+Address]
0x14006805d  cmp     byte ptr [r13+40h], 0
0x140068062  jz      short loc_140068080
0x140068064  mov     edx, dword ptr [rsp+108h+Length]; Length
0x14006806b  mov     r8d, 8; Alignment
0x140068071  mov     rcx, r12; Address
0x140068074  call    cs:__imp_ProbeForWrite
0x14006807b  nop     dword ptr [rax+rax+00h]
0x140068080  mov     rdi, [rsp+108h+Src]
0x140068088  mov     eax, [rdi]
0x14006808a  mov     ecx, dword ptr [rsp+108h+Length]
0x140068091  cmp     ecx, eax
0x140068093  jnb     short loc_1400680DB
0x140068095  cmp     ecx, 40h ; '@'
0x140068098  jb      short loc_1400680CD
0x14006809a  movups  xmm0, xmmword ptr [rdi]
0x14006809d  movups  xmmword ptr [r12], xmm0
0x1400680a2  movups  xmm1, xmmword ptr [rdi+10h]
0x1400680a6  movups  xmmword ptr [r12+10h], xmm1
0x1400680ac  movups  xmm0, xmmword ptr [rdi+20h]
0x1400680b0  movups  xmmword ptr [r12+20h], xmm0
0x1400680b6  movups  xmm1, xmmword ptr [rdi+30h]
0x1400680ba  movups  xmmword ptr [r12+30h], xmm1
0x1400680c0  mov     qword ptr [r13+38h], 40h ; '@'
0x1400680c8  jmp     loc_140068192
0x1400680cd  mov     ebx, 0C0000023h
0x1400680d2  mov     [rsp+108h+var_E8], ebx
0x1400680d6  jmp     loc_140068192
0x1400680db  mov     r8, rax; Size
0x1400680de  mov     rdi, [rsp+108h+Src]
0x1400680e6  mov     rdx, rdi; Src
0x1400680e9  mov     rcx, r12; void *
0x1400680ec  call    memmove
0x1400680f1  mov     eax, [rdi]
0x1400680f3  mov     [r13+38h], rax
0x1400680f7  jmp     loc_140068192
0x1400680fc  mov     ebx, eax
0x1400680fe  mov     [rsp+108h+var_E8], eax
0x140068102  lea     rax, WPP_GLOBAL_Control
0x140068109  mov     rcx, cs:WPP_GLOBAL_Control
0x140068110  cmp     rcx, rax
0x140068113  jz      short loc_14006813A
0x140068115  mov     eax, [rcx+2Ch]
0x140068118  test    al, 10h
0x14006811a  jz      short loc_14006813A
0x14006811c  cmp     byte ptr [rcx+29h], 2
0x140068120  jb      short loc_14006813A
0x140068122  mov     edx, 0B0h
0x140068127  mov     r9d, ebx
0x14006812a  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140068131  mov     rcx, [rcx+18h]
0x140068135  call    WPP_SF_d
0x14006813a  lea     r14, WPP_GLOBAL_Control
0x140068141  mov     r15, [rsp+108h+var_E0]
0x140068146  jmp     short loc_140068192
0x140068148  mov     ebx, eax
0x14006814a  mov     [rsp+108h+var_E8], eax
0x14006814e  lea     rax, WPP_GLOBAL_Control
0x140068155  mov     rcx, cs:WPP_GLOBAL_Control
0x14006815c  cmp     rcx, rax
0x14006815f  jz      short loc_140068186
0x140068161  mov     eax, [rcx+2Ch]
0x140068164  test    al, 10h
0x140068166  jz      short loc_140068186
0x140068168  cmp     byte ptr [rcx+29h], 2
0x14006816c  jb      short loc_140068186
0x14006816e  mov     edx, 0A9h
0x140068173  mov     r9d, ebx
0x140068176  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x14006817d  mov     rcx, [rcx+18h]
0x140068181  call    WPP_SF_d
0x140068186  lea     r14, WPP_GLOBAL_Control
0x14006818d  mov     r15, [rsp+108h+var_E0]
0x140068192  test    r15, r15
0x140068195  jz      short loc_1400681AB
0x140068197  mov     edx, 30455646h; Tag
0x14006819c  mov     rcx, r15; P
0x14006819f  call    cs:__imp_ExFreePoolWithTag
0x1400681a6  nop     dword ptr [rax+rax+00h]
0x1400681ab  lea     rcx, [rsp+108h+SourceString]; void *
0x1400681b0  call    FveVolumeCleanupInfo
0x1400681b5  mov     rcx, [rsp+108h+P]; P
0x1400681ba  test    rcx, rcx
0x1400681bd  jz      short loc_1400681D0
0x1400681bf  mov     edx, 30455646h; Tag
0x1400681c4  call    cs:__imp_ExFreePoolWithTag
0x1400681cb  nop     dword ptr [rax+rax+00h]
0x1400681d0  mov     rdi, [rsp+108h+Src]
0x1400681d8  test    rdi, rdi
0x1400681db  jz      short loc_1400681E7
0x1400681dd  mov     edx, [rdi]
0x1400681df  mov     rcx, rdi
0x1400681e2  call    FveLibClientFree
0x1400681e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400681ee  cmp     rcx, r14
0x1400681f1  jz      short loc_140068218
0x1400681f3  mov     eax, [rcx+2Ch]
0x1400681f6  test    al, 10h
0x1400681f8  jz      short loc_140068218
0x1400681fa  cmp     byte ptr [rcx+29h], 5
0x1400681fe  jb      short loc_140068218
0x140068200  mov     edx, 0B2h
0x140068205  mov     r9d, ebx
0x140068208  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x14006820f  mov     rcx, [rcx+18h]
0x140068213  call    WPP_SF_d
0x140068218  mov     eax, ebx
0x14006821a  add     rsp, 0D8h
0x140068221  pop     r15
0x140068223  pop     r14
0x140068225  pop     r13
0x140068227  pop     r12
0x140068229  pop     rdi
0x14006822a  pop     rbx
0x14006822b  retn
```

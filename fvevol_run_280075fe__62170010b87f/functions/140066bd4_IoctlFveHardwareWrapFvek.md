# IoctlFveHardwareWrapFvek

- ea: `0x140066bd4`
- end: `0x140067226`
- name: `IoctlFveHardwareWrapFvek`
- size: `1618`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x140068a40`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x14000110c`
- `0x140005e50`
- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x140016394`
- `0x1400218c0`
- `0x140021a00`
- `0x140066bd4`
- `0x140089574`
- `0x1400c7558`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140066cf4`
- `ntoskrnl!ProbeForRead` at `0x140066cf4`
- `ntoskrnl!ProbeForWrite` at `0x140066ee8`
- `ntoskrnl!ProbeForWrite` at `0x140066ee8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067101`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067101`
- `ntoskrnl!ExAllocatePool2` at `0x140066d0e`
- `ntoskrnl!ExAllocatePool2` at `0x140066d0e`

## string_xrefs

- `0x140067086`: `ReadInputBufferException`
- `0x140066d45`: `FailedToReadInputBuffer`
- `0x140066feb`: `WriteOutputBufferException`
- `0x140066f57`: `FailedToWriteOutputBuffer`

## pseudocode

```c
__int64 __fastcall IoctlFveHardwareWrapFvek(void *a1, __int64 a2)
{
  __int64 v4; // rax
  volatile void *v5; // r12
  _BYTE *v6; // r13
  int v7; // ebx
  const wchar_t *v8; // r14
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  _BYTE *Pool2; // rax
  unsigned int v12; // r12d
  unsigned __int16 *v13; // r8
  __int64 v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // r9d
  __int64 v17; // r12
  __int64 v18; // rcx
  _BYTE *v19; // rax
  unsigned int Length; // [rsp+30h] [rbp-B8h]
  char Length_4; // [rsp+34h] [rbp-B4h] BYREF
  int v23; // [rsp+38h] [rbp-B0h] BYREF
  void *Src; // [rsp+40h] [rbp-A8h] BYREF
  unsigned int v25; // [rsp+48h] [rbp-A0h]
  int v26; // [rsp+4Ch] [rbp-9Ch]
  volatile void *Address; // [rsp+50h] [rbp-98h]
  void *v28; // [rsp+58h] [rbp-90h]
  __int64 v29; // [rsp+60h] [rbp-88h] BYREF
  void *v30; // [rsp+68h] [rbp-80h]
  char v31[32]; // [rsp+70h] [rbp-78h] BYREF
  __int64 *v32; // [rsp+90h] [rbp-58h]
  __int64 v33; // [rsp+98h] [rbp-50h]
  int *v34; // [rsp+A0h] [rbp-48h]
  __int64 v35; // [rsp+A8h] [rbp-40h]
  char v36[16]; // [rsp+B0h] [rbp-38h] BYREF

  v29 = a2;
  v30 = a1;
  Src = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 147, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
  }
  v4 = *(_QWORD *)(a2 + 184);
  v5 = *(volatile void **)(v4 + 32);
  Length = *(_DWORD *)(v4 + 16);
  v23 = Length;
  Address = *(volatile void **)(a2 + 112);
  v25 = *(_DWORD *)(v4 + 8);
  v6 = 0;
  v28 = 0;
  Src = 0;
  Length_4 = 0;
  v7 = FveKickAllSystemsGo(a1);
  if ( v7 < 0 )
  {
    v8 = L"IoctlKickAllSystemsGo";
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_52;
    }
    v10 = 148;
LABEL_10:
    WPP_SF_d(v9->AttachedDevice, v10, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)v7);
LABEL_52:
    v12 = Length;
    goto LABEL_53;
  }
  if ( *(_BYTE *)(a2 + 64) )
    ProbeForRead(v5, Length, 1u);
  Pool2 = (_BYTE *)ExAllocatePool2(64, Length, 809850438);
  v6 = Pool2;
  v28 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, (const void *)v5, Length);
  }
  else
  {
    v7 = -1073741670;
    v26 = -1073741670;
  }
  if ( v7 < 0 )
  {
    v8 = L"FailedToReadInputBuffer";
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_52;
    }
    v10 = 150;
    goto LABEL_10;
  }
  v12 = Length;
  if ( (int)FveIsValidWrapKeyRequest(v6, Length, &Length_4) >= 0 && Length_4 )
  {
    v13 = (unsigned __int16 *)&v6[*((unsigned __int16 *)v6 + 1)];
    v14 = *v13;
    if ( Length == v14 + 8 )
    {
      v7 = FveIceHwWrapFvek(v30, *((unsigned int *)v6 + 1), v13, &Src);
      if ( v7 >= 0 )
      {
        v8 = L"NA";
        v15 = *(unsigned __int16 *)Src;
        v16 = v25;
        if ( v25 < v15 )
        {
          v7 = -1073741789;
          v8 = L"OutputBufferToSmall";
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              154,
              WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
              v25,
              v15);
            v16 = v25;
          }
        }
        v17 = v29;
        if ( *(_BYTE *)(v29 + 64) )
          ProbeForWrite(Address, v16, 1u);
        if ( v7 != -1073741789 )
        {
          memmove((void *)Address, Src, *(unsigned __int16 *)Src);
          *(_QWORD *)(v17 + 56) = *(unsigned __int16 *)Src;
          v7 = 0;
          v8 = L"SuccessfulHwWrap";
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 157, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
          }
          goto LABEL_52;
        }
        if ( v25 >= 8 )
        {
          *(_WORD *)Address = *(_WORD *)Src;
          *(_QWORD *)(v17 + 56) = 2;
          v7 = 0;
          v26 = 0;
        }
        v12 = Length;
      }
      else
      {
        v8 = L"FveIceHwWrapFvek";
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            153,
            WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
            (unsigned int)v7);
        }
      }
    }
    else
    {
      v7 = -1073741811;
      v8 = L"InvalidInputBufferLength";
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          152,
          WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
          Length,
          v14 + 8);
      }
    }
  }
  else
  {
    v7 = -1073741811;
    v8 = L"InputRequestIsInvalid";
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 151, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
    }
  }
LABEL_53:
  if ( v6 )
  {
    v18 = v12;
    v19 = v6;
    if ( v12 )
    {
      do
      {
        *v19++ = 0;
        --v18;
      }
      while ( v18 );
    }
    ExFreePoolWithTag(v6, 0x30455646u);
  }
  if ( Src )
  {
    FveDatumFree(Src);
    Src = 0;
  }
  if ( (unsigned int)dword_140045040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
  {
    v29 = 0x1000000;
    v32 = &v29;
    v33 = 8;
    v23 = v7;
    v34 = &v23;
    v35 = 4;
    tlgCreate1Sz_wchar_t(v36, v8);
    tlgWriteTransfer_EtwWriteTransfer(&dword_140045040, &unk_14003C328, 0, 0, 5, v31);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140066bd4  mov     [rsp+arg_10], rbx
0x140066bd9  mov     [rsp+arg_18], r12
0x140066bde  push    r13
0x140066be0  push    r14
0x140066be2  push    r15
0x140066be4  sub     rsp, 0D0h
0x140066beb  mov     rax, cs:__security_cookie
0x140066bf2  xor     rax, rsp
0x140066bf5  mov     [rsp+0E8h+var_28], rax
0x140066bfd  mov     r14, rdx
0x140066c00  mov     [rsp+0E8h+var_88], rdx
0x140066c05  mov     rbx, rcx
0x140066c08  mov     [rsp+0E8h+var_80], rcx
0x140066c0d  mov     [rsp+0E8h+Src], 0
0x140066c16  lea     r15, WPP_GLOBAL_Control
0x140066c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140066c24  cmp     rcx, r15
0x140066c27  jz      short loc_140066C4B
0x140066c29  mov     eax, [rcx+2Ch]
0x140066c2c  test    al, 10h
0x140066c2e  jz      short loc_140066C4B
0x140066c30  cmp     byte ptr [rcx+29h], 5
0x140066c34  jb      short loc_140066C4B
0x140066c36  mov     edx, 93h
0x140066c3b  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140066c42  mov     rcx, [rcx+18h]
0x140066c46  call    WPP_SF_
0x140066c4b  mov     rax, [r14+0B8h]
0x140066c52  mov     r12, [rax+20h]
0x140066c56  mov     ecx, [rax+10h]
0x140066c59  mov     dword ptr [rsp+0E8h+Length], ecx
0x140066c5d  mov     [rsp+0E8h+var_B0], ecx
0x140066c61  mov     rcx, [r14+70h]
0x140066c65  mov     [rsp+0E8h+Address], rcx
0x140066c6a  mov     ecx, [rax+8]
0x140066c6d  mov     dword ptr [rsp+0E8h+var_A0], ecx
0x140066c71  xor     r13d, r13d
0x140066c74  mov     [rsp+0E8h+var_90], r13
0x140066c79  mov     [rsp+0E8h+Src], r13
0x140066c7e  mov     byte ptr [rsp+0E8h+Length+4], r13b
0x140066c83  xor     edx, edx
0x140066c85  mov     rcx, rbx
0x140066c88  call    FveKickAllSystemsGo
0x140066c8d  mov     ebx, eax
0x140066c8f  test    eax, eax
0x140066c91  jns     short loc_140066CDC
0x140066c93  lea     r14, aIoctlkickallsy; "IoctlKickAllSystemsGo"
0x140066c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140066ca1  cmp     rcx, r15
0x140066ca4  jz      loc_1400670D8
0x140066caa  mov     eax, [rcx+2Ch]
0x140066cad  test    al, 10h
0x140066caf  jz      loc_1400670D8
0x140066cb5  cmp     byte ptr [rcx+29h], 2
0x140066cb9  jb      loc_1400670D8
0x140066cbf  mov     edx, 94h
0x140066cc4  mov     r9d, ebx
0x140066cc7  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140066cce  mov     rcx, [rcx+18h]
0x140066cd2  call    WPP_SF_d
0x140066cd7  jmp     loc_1400670D8
0x140066cdc  cmp     byte ptr [r14+40h], 0
0x140066ce1  mov     r14d, dword ptr [rsp+0E8h+Length]
0x140066ce6  jz      short loc_140066D00
0x140066ce8  mov     edx, r14d; Length
0x140066ceb  mov     r8d, 1; Alignment
0x140066cf1  mov     rcx, r12; Address
0x140066cf4  call    cs:__imp_ProbeForRead
0x140066cfb  nop     dword ptr [rax+rax+00h]
0x140066d00  mov     r8d, 30455646h
0x140066d06  mov     rdx, r14
0x140066d09  mov     ecx, 40h ; '@'
0x140066d0e  call    cs:__imp_ExAllocatePool2
0x140066d15  nop     dword ptr [rax+rax+00h]
0x140066d1a  mov     r13, rax
0x140066d1d  mov     [rsp+0E8h+var_90], rax
0x140066d22  test    rax, rax
0x140066d25  jnz     short loc_140066D32
0x140066d27  mov     ebx, 0C000009Ah
0x140066d2c  mov     dword ptr [rsp+0E8h+var_A0+4], ebx
0x140066d30  jmp     short loc_140066D41
0x140066d32  mov     r8, r14; Size
0x140066d35  mov     rdx, r12; Src
0x140066d38  mov     rcx, r13; void *
0x140066d3b  call    memmove
0x140066d40  nop
0x140066d41  test    ebx, ebx
0x140066d43  jns     short loc_140066D7B
0x140066d45  lea     r14, aFailedtoreadin; "FailedToReadInputBuffer"
0x140066d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140066d53  cmp     rcx, r15
0x140066d56  jz      loc_1400670D8
0x140066d5c  mov     eax, [rcx+2Ch]
0x140066d5f  test    al, 10h
0x140066d61  jz      loc_1400670D8
0x140066d67  cmp     byte ptr [rcx+29h], 2
0x140066d6b  jb      loc_1400670D8
0x140066d71  mov     edx, 96h
0x140066d76  jmp     loc_140066CC4
0x140066d7b  lea     r8, [rsp+0E8h+Length+4]
0x140066d80  mov     r12d, dword ptr [rsp+0E8h+Length]
0x140066d85  mov     edx, r12d
0x140066d88  mov     rcx, r13
0x140066d8b  call    FveIsValidWrapKeyRequest
0x140066d90  test    eax, eax
0x140066d92  js      loc_140067040
0x140066d98  cmp     byte ptr [rsp+0E8h+Length+4], 0
0x140066d9d  jz      loc_140067040
0x140066da3  movzx   r8d, word ptr [r13+2]
0x140066da8  add     r8, r13
0x140066dab  movzx   edx, word ptr [r8]
0x140066daf  lea     rcx, [rdx+8]
0x140066db3  cmp     r12, rcx
0x140066db6  jz      short loc_140066E0D
0x140066db8  mov     ebx, 0C000000Dh
0x140066dbd  lea     r14, aInvalidinputbu; "InvalidInputBufferLength"
0x140066dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140066dcb  cmp     rcx, r15
0x140066dce  jz      loc_1400670DD
0x140066dd4  mov     eax, [rcx+2Ch]
0x140066dd7  test    al, 10h
0x140066dd9  jz      loc_1400670DD
0x140066ddf  cmp     byte ptr [rcx+29h], 2
0x140066de3  jb      loc_1400670DD
0x140066de9  lea     eax, [rdx+8]
0x140066dec  mov     edx, 98h
0x140066df1  mov     [rsp+0E8h+var_C8], eax
0x140066df5  mov     r9d, r12d
0x140066df8  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140066dff  mov     rcx, [rcx+18h]
0x140066e03  call    WPP_SF_Dd
0x140066e08  jmp     loc_1400670DD
0x140066e0d  lea     r9, [rsp+0E8h+Src]
0x140066e12  mov     edx, [r13+4]
0x140066e16  mov     rcx, [rsp+0E8h+var_80]
0x140066e1b  call    FveIceHwWrapFvek
0x140066e20  mov     ebx, eax
0x140066e22  test    eax, eax
0x140066e24  jns     short loc_140066E6F
0x140066e26  lea     r14, aFveicehwwrapfv; "FveIceHwWrapFvek"
0x140066e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140066e34  cmp     rcx, r15
0x140066e37  jz      loc_1400670DD
0x140066e3d  mov     eax, [rcx+2Ch]
0x140066e40  test    al, 10h
0x140066e42  jz      loc_1400670DD
0x140066e48  cmp     byte ptr [rcx+29h], 2
0x140066e4c  jb      loc_1400670DD
0x140066e52  mov     edx, 99h
0x140066e57  mov     r9d, ebx
0x140066e5a  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140066e61  mov     rcx, [rcx+18h]
0x140066e65  call    WPP_SF_d
0x140066e6a  jmp     loc_1400670DD
0x140066e6f  lea     r14, aNa; "NA"
0x140066e76  mov     rax, [rsp+0E8h+Src]
0x140066e7b  movzx   r8d, word ptr [rax]
0x140066e7f  mov     r9d, dword ptr [rsp+0E8h+var_A0]
0x140066e84  cmp     r9d, r8d
0x140066e87  jnb     short loc_140066ECD
0x140066e89  mov     ebx, 0C0000023h
0x140066e8e  lea     r14, aOutputbufferto; "OutputBufferToSmall"
0x140066e95  mov     rcx, cs:WPP_GLOBAL_Control
0x140066e9c  cmp     rcx, r15
0x140066e9f  jz      short loc_140066ECD
0x140066ea1  mov     eax, [rcx+2Ch]
0x140066ea4  test    al, 10h
0x140066ea6  jz      short loc_140066ECD
0x140066ea8  cmp     byte ptr [rcx+29h], 2
0x140066eac  jb      short loc_140066ECD
0x140066eae  mov     edx, 9Ah
0x140066eb3  mov     [rsp+0E8h+var_C8], r8d
0x140066eb8  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140066ebf  mov     rcx, [rcx+18h]
0x140066ec3  call    WPP_SF_Dd
0x140066ec8  mov     r9d, dword ptr [rsp+0E8h+var_A0]
0x140066ecd  mov     r12, [rsp+0E8h+var_88]
0x140066ed2  cmp     byte ptr [r12+40h], 0
0x140066ed8  jz      short loc_140066EF4
0x140066eda  mov     edx, r9d; Length
0x140066edd  mov     r8d, 1; Alignment
0x140066ee3  mov     rcx, [rsp+0E8h+Address]; Address
0x140066ee8  call    cs:__imp_ProbeForWrite
0x140066eef  nop     dword ptr [rax+rax+00h]
0x140066ef4  cmp     ebx, 0C0000023h
0x140066efa  jnz     short loc_140066F2C
0x140066efc  cmp     dword ptr [rsp+0E8h+var_A0], 8
0x140066f01  jb      short loc_140066F22
0x140066f03  mov     rax, [rsp+0E8h+Src]
0x140066f08  movzx   ecx, word ptr [rax]
0x140066f0b  mov     rax, [rsp+0E8h+Address]
0x140066f10  mov     [rax], cx
0x140066f13  mov     qword ptr [r12+38h], 2
0x140066f1c  xor     ebx, ebx
0x140066f1e  mov     dword ptr [rsp+0E8h+var_A0+4], ebx
0x140066f22  mov     r12d, dword ptr [rsp+0E8h+Length]
0x140066f27  jmp     loc_1400670DD
0x140066f2c  test    ebx, ebx
0x140066f2e  js      short loc_140066F53
0x140066f30  mov     rcx, [rsp+0E8h+Src]
0x140066f35  movzx   r8d, word ptr [rcx]; Size
0x140066f39  mov     rdx, rcx; Src
0x140066f3c  mov     rcx, [rsp+0E8h+Address]; void *
0x140066f41  call    memmove
0x140066f46  mov     rax, [rsp+0E8h+Src]
0x140066f4b  movzx   ecx, word ptr [rax]
0x140066f4e  mov     [r12+38h], rcx
0x140066f53  test    ebx, ebx
0x140066f55  jns     short loc_140066F9D
0x140066f57  lea     r14, aFailedtowriteo; "FailedToWriteOutputBuffer"
0x140066f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140066f65  cmp     rcx, r15
0x140066f68  jz      short loc_140066F8F
0x140066f6a  mov     eax, [rcx+2Ch]
0x140066f6d  test    al, 10h
0x140066f6f  jz      short loc_140066F8F
0x140066f71  cmp     byte ptr [rcx+29h], 2
0x140066f75  jb      short loc_140066F8F
0x140066f77  mov     edx, 9Ch
0x140066f7c  mov     r9d, ebx
0x140066f7f  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140066f86  mov     rcx, [rcx+18h]
0x140066f8a  call    WPP_SF_d
0x140066f8f  mov     qword ptr [r12+38h], 0
0x140066f98  jmp     loc_1400670D8
0x140066f9d  xor     ebx, ebx
0x140066f9f  lea     r14, aSuccessfulhwwr; "SuccessfulHwWrap"
0x140066fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x140066fad  cmp     rcx, r15
0x140066fb0  jz      loc_1400670D8
0x140066fb6  mov     eax, [rcx+2Ch]
0x140066fb9  test    al, 10h
0x140066fbb  jz      loc_1400670D8
0x140066fc1  cmp     byte ptr [rcx+29h], 4
0x140066fc5  jb      loc_1400670D8
0x140066fcb  mov     edx, 9Dh
0x140066fd0  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140066fd7  mov     rcx, [rcx+18h]
0x140066fdb  call    WPP_SF_
0x140066fe0  jmp     loc_1400670D8
0x140066fe5  mov     ebx, eax
0x140066fe7  mov     dword ptr [rsp+0E8h+var_A0+4], eax
0x140066feb  lea     r14, aWriteoutputbuf; "WriteOutputBufferException"
0x140066ff2  lea     rax, WPP_GLOBAL_Control
0x140066ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x140067000  cmp     rcx, rax
0x140067003  jz      short loc_14006702A
0x140067005  mov     eax, [rcx+2Ch]
0x140067008  test    al, 10h
0x14006700a  jz      short loc_14006702A
0x14006700c  cmp     byte ptr [rcx+29h], 2
0x140067010  jb      short loc_14006702A
0x140067012  mov     edx, 9Bh
0x140067017  mov     r9d, ebx
0x14006701a  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067021  mov     rcx, [rcx+18h]
0x140067025  call    WPP_SF_d
0x14006702a  lea     r15, WPP_GLOBAL_Control
0x140067031  mov     r13, [rsp+0E8h+var_90]
0x140067036  mov     r12d, [rsp+0E8h+var_B0]
0x14006703b  jmp     loc_1400670DD
0x140067040  mov     ebx, 0C000000Dh
0x140067045  lea     r14, aInputrequestis; "InputRequestIsInvalid"
0x14006704c  mov     rcx, cs:WPP_GLOBAL_Control
0x140067053  cmp     rcx, r15
0x140067056  jz      loc_1400670DD
0x14006705c  mov     eax, [rcx+2Ch]
0x14006705f  test    al, 10h
0x140067061  jz      short loc_1400670DD
0x140067063  cmp     byte ptr [rcx+29h], 2
0x140067067  jb      short loc_1400670DD
0x140067069  mov     edx, 97h
0x14006706e  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067075  mov     rcx, [rcx+18h]
0x140067079  call    WPP_SF_
0x14006707e  jmp     short loc_1400670DD
0x140067080  mov     ebx, eax
0x140067082  mov     dword ptr [rsp+0E8h+var_A0+4], eax
0x140067086  lea     r14, aReadinputbuffe; "ReadInputBufferException"
0x14006708d  lea     rax, WPP_GLOBAL_Control
0x140067094  mov     rcx, cs:WPP_GLOBAL_Control
0x14006709b  cmp     rcx, rax
0x14006709e  jz      short loc_1400670C5
0x1400670a0  mov     eax, [rcx+2Ch]
0x1400670a3  test    al, 10h
0x1400670a5  jz      short loc_1400670C5
0x1400670a7  cmp     byte ptr [rcx+29h], 2
0x1400670ab  jb      short loc_1400670C5
0x1400670ad  mov     edx, 95h
0x1400670b2  mov     r9d, ebx
0x1400670b5  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x1400670bc  mov     rcx, [rcx+18h]
0x1400670c0  call    WPP_SF_d
0x1400670c5  lea     r15, WPP_GLOBAL_Control
0x1400670cc  mov     r13, [rsp+0E8h+var_90]
0x1400670d1  mov     r12d, [rsp+0E8h+var_B0]
0x1400670d6  jmp     short loc_1400670DD
0x1400670d8  mov     r12d, dword ptr [rsp+0E8h+Length]
0x1400670dd  test    r13, r13
0x1400670e0  jz      short loc_14006710D
  ... truncated ...
```

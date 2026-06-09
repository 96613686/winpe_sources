# IoctlFveHardwareWrapFvek

- ea: `0x140068c64`
- end: `0x1400692b6`
- name: `IoctlFveHardwareWrapFvek`
- size: `1618`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x14006aad0`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140001114`
- `0x140005e60`
- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x140016d4c`
- `0x140022bf0`
- `0x140022d40`
- `0x140068c64`
- `0x14008b614`
- `0x1400cb034`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140068d84`
- `ntoskrnl!ProbeForRead` at `0x140068d84`
- `ntoskrnl!ProbeForWrite` at `0x140068f78`
- `ntoskrnl!ProbeForWrite` at `0x140068f78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069191`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069191`
- `ntoskrnl!ExAllocatePool2` at `0x140068d9e`
- `ntoskrnl!ExAllocatePool2` at `0x140068d9e`

## string_xrefs

- `0x140069116`: `ReadInputBufferException`
- `0x140068dd5`: `FailedToReadInputBuffer`
- `0x14006907b`: `WriteOutputBufferException`
- `0x140068fe7`: `FailedToWriteOutputBuffer`

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
  SIZE_T Length; // [rsp+30h] [rbp-B8h] BYREF
  int v22; // [rsp+38h] [rbp-B0h] BYREF
  void *Src; // [rsp+40h] [rbp-A8h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-A0h]
  int v25; // [rsp+4Ch] [rbp-9Ch]
  volatile void *Address; // [rsp+50h] [rbp-98h]
  void *v27; // [rsp+58h] [rbp-90h]
  __int64 v28; // [rsp+60h] [rbp-88h] BYREF
  void *v29; // [rsp+68h] [rbp-80h]
  char v30[32]; // [rsp+70h] [rbp-78h] BYREF
  __int64 *v31; // [rsp+90h] [rbp-58h]
  __int64 v32; // [rsp+98h] [rbp-50h]
  int *v33; // [rsp+A0h] [rbp-48h]
  __int64 v34; // [rsp+A8h] [rbp-40h]
  char v35[16]; // [rsp+B0h] [rbp-38h] BYREF

  v28 = a2;
  v29 = a1;
  Src = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 147, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
  }
  v4 = *(_QWORD *)(a2 + 184);
  v5 = *(volatile void **)(v4 + 32);
  LODWORD(Length) = *(_DWORD *)(v4 + 16);
  v22 = *(_DWORD *)(v4 + 16);
  Address = *(volatile void **)(a2 + 112);
  v24 = *(_DWORD *)(v4 + 8);
  v6 = 0;
  v27 = 0;
  Src = 0;
  BYTE4(Length) = 0;
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
    WPP_SF_d(v9->AttachedDevice, v10, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, (unsigned int)v7);
LABEL_52:
    v12 = Length;
    goto LABEL_53;
  }
  if ( *(_BYTE *)(a2 + 64) )
    ProbeForRead(v5, (unsigned int)Length, 1u);
  Pool2 = (_BYTE *)ExAllocatePool2(64, (unsigned int)Length, 809850438);
  v6 = Pool2;
  v27 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, (const void *)v5, (unsigned int)Length);
  }
  else
  {
    v7 = -1073741670;
    v25 = -1073741670;
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
  if ( (int)FveIsValidWrapKeyRequest(v6, (unsigned int)Length, (char *)&Length + 4) >= 0 && BYTE4(Length) )
  {
    v13 = (unsigned __int16 *)&v6[*((unsigned __int16 *)v6 + 1)];
    v14 = *v13;
    if ( (unsigned int)Length == v14 + 8 )
    {
      v7 = FveIceHwWrapFvek(v29, *((unsigned int *)v6 + 1), v13, &Src);
      if ( v7 >= 0 )
      {
        v8 = L"NA";
        v15 = *(unsigned __int16 *)Src;
        v16 = v24;
        if ( v24 < v15 )
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
              WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
              v24,
              v15);
            v16 = v24;
          }
        }
        v17 = v28;
        if ( *(_BYTE *)(v28 + 64) )
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
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 157, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
          }
          goto LABEL_52;
        }
        if ( v24 >= 8 )
        {
          *(_WORD *)Address = *(_WORD *)Src;
          *(_QWORD *)(v17 + 56) = 2;
          v7 = 0;
          v25 = 0;
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
            WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
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
          WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
          (unsigned int)Length,
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
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 151, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
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
  if ( (unsigned int)dword_140046040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140046040, 0x400000000000LL) )
  {
    v28 = 0x1000000;
    v31 = &v28;
    v32 = 8;
    v22 = v7;
    v33 = &v22;
    v34 = 4;
    tlgCreate1Sz_wchar_t(v35, v8);
    tlgWriteTransfer_EtwWriteTransfer(&dword_140046040, &unk_14003D3A8, 0, 0, 5, v30, Length, v22, Src);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140068c64  mov     [rsp+arg_10], rbx
0x140068c69  mov     [rsp+arg_18], r12
0x140068c6e  push    r13
0x140068c70  push    r14
0x140068c72  push    r15
0x140068c74  sub     rsp, 0D0h
0x140068c7b  mov     rax, cs:__security_cookie
0x140068c82  xor     rax, rsp
0x140068c85  mov     [rsp+0E8h+var_28], rax
0x140068c8d  mov     r14, rdx
0x140068c90  mov     [rsp+0E8h+var_88], rdx
0x140068c95  mov     rbx, rcx
0x140068c98  mov     [rsp+0E8h+var_80], rcx
0x140068c9d  mov     [rsp+0E8h+Src], 0
0x140068ca6  lea     r15, WPP_GLOBAL_Control
0x140068cad  mov     rcx, cs:WPP_GLOBAL_Control
0x140068cb4  cmp     rcx, r15
0x140068cb7  jz      short loc_140068CDB
0x140068cb9  mov     eax, [rcx+2Ch]
0x140068cbc  test    al, 10h
0x140068cbe  jz      short loc_140068CDB
0x140068cc0  cmp     byte ptr [rcx+29h], 5
0x140068cc4  jb      short loc_140068CDB
0x140068cc6  mov     edx, 93h
0x140068ccb  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140068cd2  mov     rcx, [rcx+18h]
0x140068cd6  call    WPP_SF_
0x140068cdb  mov     rax, [r14+0B8h]
0x140068ce2  mov     r12, [rax+20h]
0x140068ce6  mov     ecx, [rax+10h]
0x140068ce9  mov     dword ptr [rsp+0E8h+Length], ecx
0x140068ced  mov     [rsp+0E8h+var_B0], ecx
0x140068cf1  mov     rcx, [r14+70h]
0x140068cf5  mov     [rsp+0E8h+Address], rcx
0x140068cfa  mov     ecx, [rax+8]
0x140068cfd  mov     dword ptr [rsp+0E8h+var_A0], ecx
0x140068d01  xor     r13d, r13d
0x140068d04  mov     [rsp+0E8h+var_90], r13
0x140068d09  mov     [rsp+0E8h+Src], r13
0x140068d0e  mov     byte ptr [rsp+0E8h+Length+4], r13b
0x140068d13  xor     edx, edx
0x140068d15  mov     rcx, rbx
0x140068d18  call    FveKickAllSystemsGo
0x140068d1d  mov     ebx, eax
0x140068d1f  test    eax, eax
0x140068d21  jns     short loc_140068D6C
0x140068d23  lea     r14, aIoctlkickallsy; "IoctlKickAllSystemsGo"
0x140068d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140068d31  cmp     rcx, r15
0x140068d34  jz      loc_140069168
0x140068d3a  mov     eax, [rcx+2Ch]
0x140068d3d  test    al, 10h
0x140068d3f  jz      loc_140069168
0x140068d45  cmp     byte ptr [rcx+29h], 2
0x140068d49  jb      loc_140069168
0x140068d4f  mov     edx, 94h
0x140068d54  mov     r9d, ebx
0x140068d57  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140068d5e  mov     rcx, [rcx+18h]
0x140068d62  call    WPP_SF_d
0x140068d67  jmp     loc_140069168
0x140068d6c  cmp     byte ptr [r14+40h], 0
0x140068d71  mov     r14d, dword ptr [rsp+0E8h+Length]
0x140068d76  jz      short loc_140068D90
0x140068d78  mov     edx, r14d; Length
0x140068d7b  mov     r8d, 1; Alignment
0x140068d81  mov     rcx, r12; Address
0x140068d84  call    cs:__imp_ProbeForRead
0x140068d8b  nop     dword ptr [rax+rax+00h]
0x140068d90  mov     r8d, 30455646h
0x140068d96  mov     rdx, r14
0x140068d99  mov     ecx, 40h ; '@'
0x140068d9e  call    cs:__imp_ExAllocatePool2
0x140068da5  nop     dword ptr [rax+rax+00h]
0x140068daa  mov     r13, rax
0x140068dad  mov     [rsp+0E8h+var_90], rax
0x140068db2  test    rax, rax
0x140068db5  jnz     short loc_140068DC2
0x140068db7  mov     ebx, 0C000009Ah
0x140068dbc  mov     dword ptr [rsp+0E8h+var_A0+4], ebx
0x140068dc0  jmp     short loc_140068DD1
0x140068dc2  mov     r8, r14; Size
0x140068dc5  mov     rdx, r12; Src
0x140068dc8  mov     rcx, r13; void *
0x140068dcb  call    memmove
0x140068dd0  nop
0x140068dd1  test    ebx, ebx
0x140068dd3  jns     short loc_140068E0B
0x140068dd5  lea     r14, aFailedtoreadin; "FailedToReadInputBuffer"
0x140068ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x140068de3  cmp     rcx, r15
0x140068de6  jz      loc_140069168
0x140068dec  mov     eax, [rcx+2Ch]
0x140068def  test    al, 10h
0x140068df1  jz      loc_140069168
0x140068df7  cmp     byte ptr [rcx+29h], 2
0x140068dfb  jb      loc_140069168
0x140068e01  mov     edx, 96h
0x140068e06  jmp     loc_140068D54
0x140068e0b  lea     r8, [rsp+0E8h+Length+4]
0x140068e10  mov     r12d, dword ptr [rsp+0E8h+Length]
0x140068e15  mov     edx, r12d
0x140068e18  mov     rcx, r13
0x140068e1b  call    FveIsValidWrapKeyRequest
0x140068e20  test    eax, eax
0x140068e22  js      loc_1400690D0
0x140068e28  cmp     byte ptr [rsp+0E8h+Length+4], 0
0x140068e2d  jz      loc_1400690D0
0x140068e33  movzx   r8d, word ptr [r13+2]
0x140068e38  add     r8, r13
0x140068e3b  movzx   edx, word ptr [r8]
0x140068e3f  lea     rcx, [rdx+8]
0x140068e43  cmp     r12, rcx
0x140068e46  jz      short loc_140068E9D
0x140068e48  mov     ebx, 0C000000Dh
0x140068e4d  lea     r14, aInvalidinputbu; "InvalidInputBufferLength"
0x140068e54  mov     rcx, cs:WPP_GLOBAL_Control
0x140068e5b  cmp     rcx, r15
0x140068e5e  jz      loc_14006916D
0x140068e64  mov     eax, [rcx+2Ch]
0x140068e67  test    al, 10h
0x140068e69  jz      loc_14006916D
0x140068e6f  cmp     byte ptr [rcx+29h], 2
0x140068e73  jb      loc_14006916D
0x140068e79  lea     eax, [rdx+8]
0x140068e7c  mov     edx, 98h
0x140068e81  mov     [rsp+0E8h+var_C8], eax
0x140068e85  mov     r9d, r12d
0x140068e88  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140068e8f  mov     rcx, [rcx+18h]
0x140068e93  call    WPP_SF_Dd
0x140068e98  jmp     loc_14006916D
0x140068e9d  lea     r9, [rsp+0E8h+Src]
0x140068ea2  mov     edx, [r13+4]
0x140068ea6  mov     rcx, [rsp+0E8h+var_80]
0x140068eab  call    FveIceHwWrapFvek
0x140068eb0  mov     ebx, eax
0x140068eb2  test    eax, eax
0x140068eb4  jns     short loc_140068EFF
0x140068eb6  lea     r14, aFveicehwwrapfv; "FveIceHwWrapFvek"
0x140068ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ec4  cmp     rcx, r15
0x140068ec7  jz      loc_14006916D
0x140068ecd  mov     eax, [rcx+2Ch]
0x140068ed0  test    al, 10h
0x140068ed2  jz      loc_14006916D
0x140068ed8  cmp     byte ptr [rcx+29h], 2
0x140068edc  jb      loc_14006916D
0x140068ee2  mov     edx, 99h
0x140068ee7  mov     r9d, ebx
0x140068eea  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140068ef1  mov     rcx, [rcx+18h]
0x140068ef5  call    WPP_SF_d
0x140068efa  jmp     loc_14006916D
0x140068eff  lea     r14, aNa; "NA"
0x140068f06  mov     rax, [rsp+0E8h+Src]
0x140068f0b  movzx   r8d, word ptr [rax]
0x140068f0f  mov     r9d, dword ptr [rsp+0E8h+var_A0]
0x140068f14  cmp     r9d, r8d
0x140068f17  jnb     short loc_140068F5D
0x140068f19  mov     ebx, 0C0000023h
0x140068f1e  lea     r14, aOutputbufferto; "OutputBufferToSmall"
0x140068f25  mov     rcx, cs:WPP_GLOBAL_Control
0x140068f2c  cmp     rcx, r15
0x140068f2f  jz      short loc_140068F5D
0x140068f31  mov     eax, [rcx+2Ch]
0x140068f34  test    al, 10h
0x140068f36  jz      short loc_140068F5D
0x140068f38  cmp     byte ptr [rcx+29h], 2
0x140068f3c  jb      short loc_140068F5D
0x140068f3e  mov     edx, 9Ah
0x140068f43  mov     [rsp+0E8h+var_C8], r8d
0x140068f48  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140068f4f  mov     rcx, [rcx+18h]
0x140068f53  call    WPP_SF_Dd
0x140068f58  mov     r9d, dword ptr [rsp+0E8h+var_A0]
0x140068f5d  mov     r12, [rsp+0E8h+var_88]
0x140068f62  cmp     byte ptr [r12+40h], 0
0x140068f68  jz      short loc_140068F84
0x140068f6a  mov     edx, r9d; Length
0x140068f6d  mov     r8d, 1; Alignment
0x140068f73  mov     rcx, [rsp+0E8h+Address]; Address
0x140068f78  call    cs:__imp_ProbeForWrite
0x140068f7f  nop     dword ptr [rax+rax+00h]
0x140068f84  cmp     ebx, 0C0000023h
0x140068f8a  jnz     short loc_140068FBC
0x140068f8c  cmp     dword ptr [rsp+0E8h+var_A0], 8
0x140068f91  jb      short loc_140068FB2
0x140068f93  mov     rax, [rsp+0E8h+Src]
0x140068f98  movzx   ecx, word ptr [rax]
0x140068f9b  mov     rax, [rsp+0E8h+Address]
0x140068fa0  mov     [rax], cx
0x140068fa3  mov     qword ptr [r12+38h], 2
0x140068fac  xor     ebx, ebx
0x140068fae  mov     dword ptr [rsp+0E8h+var_A0+4], ebx
0x140068fb2  mov     r12d, dword ptr [rsp+0E8h+Length]
0x140068fb7  jmp     loc_14006916D
0x140068fbc  test    ebx, ebx
0x140068fbe  js      short loc_140068FE3
0x140068fc0  mov     rcx, [rsp+0E8h+Src]
0x140068fc5  movzx   r8d, word ptr [rcx]; Size
0x140068fc9  mov     rdx, rcx; Src
0x140068fcc  mov     rcx, [rsp+0E8h+Address]; void *
0x140068fd1  call    memmove
0x140068fd6  mov     rax, [rsp+0E8h+Src]
0x140068fdb  movzx   ecx, word ptr [rax]
0x140068fde  mov     [r12+38h], rcx
0x140068fe3  test    ebx, ebx
0x140068fe5  jns     short loc_14006902D
0x140068fe7  lea     r14, aFailedtowriteo; "FailedToWriteOutputBuffer"
0x140068fee  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ff5  cmp     rcx, r15
0x140068ff8  jz      short loc_14006901F
0x140068ffa  mov     eax, [rcx+2Ch]
0x140068ffd  test    al, 10h
0x140068fff  jz      short loc_14006901F
0x140069001  cmp     byte ptr [rcx+29h], 2
0x140069005  jb      short loc_14006901F
0x140069007  mov     edx, 9Ch
0x14006900c  mov     r9d, ebx
0x14006900f  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140069016  mov     rcx, [rcx+18h]
0x14006901a  call    WPP_SF_d
0x14006901f  mov     qword ptr [r12+38h], 0
0x140069028  jmp     loc_140069168
0x14006902d  xor     ebx, ebx
0x14006902f  lea     r14, aSuccessfulhwwr; "SuccessfulHwWrap"
0x140069036  mov     rcx, cs:WPP_GLOBAL_Control
0x14006903d  cmp     rcx, r15
0x140069040  jz      loc_140069168
0x140069046  mov     eax, [rcx+2Ch]
0x140069049  test    al, 10h
0x14006904b  jz      loc_140069168
0x140069051  cmp     byte ptr [rcx+29h], 4
0x140069055  jb      loc_140069168
0x14006905b  mov     edx, 9Dh
0x140069060  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140069067  mov     rcx, [rcx+18h]
0x14006906b  call    WPP_SF_
0x140069070  jmp     loc_140069168
0x140069075  mov     ebx, eax
0x140069077  mov     dword ptr [rsp+0E8h+var_A0+4], eax
0x14006907b  lea     r14, aWriteoutputbuf; "WriteOutputBufferException"
0x140069082  lea     rax, WPP_GLOBAL_Control
0x140069089  mov     rcx, cs:WPP_GLOBAL_Control
0x140069090  cmp     rcx, rax
0x140069093  jz      short loc_1400690BA
0x140069095  mov     eax, [rcx+2Ch]
0x140069098  test    al, 10h
0x14006909a  jz      short loc_1400690BA
0x14006909c  cmp     byte ptr [rcx+29h], 2
0x1400690a0  jb      short loc_1400690BA
0x1400690a2  mov     edx, 9Bh
0x1400690a7  mov     r9d, ebx
0x1400690aa  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x1400690b1  mov     rcx, [rcx+18h]
0x1400690b5  call    WPP_SF_d
0x1400690ba  lea     r15, WPP_GLOBAL_Control
0x1400690c1  mov     r13, [rsp+0E8h+var_90]
0x1400690c6  mov     r12d, [rsp+0E8h+var_B0]
0x1400690cb  jmp     loc_14006916D
0x1400690d0  mov     ebx, 0C000000Dh
0x1400690d5  lea     r14, aInputrequestis; "InputRequestIsInvalid"
0x1400690dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400690e3  cmp     rcx, r15
0x1400690e6  jz      loc_14006916D
0x1400690ec  mov     eax, [rcx+2Ch]
0x1400690ef  test    al, 10h
0x1400690f1  jz      short loc_14006916D
0x1400690f3  cmp     byte ptr [rcx+29h], 2
0x1400690f7  jb      short loc_14006916D
0x1400690f9  mov     edx, 97h
0x1400690fe  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140069105  mov     rcx, [rcx+18h]
0x140069109  call    WPP_SF_
0x14006910e  jmp     short loc_14006916D
0x140069110  mov     ebx, eax
0x140069112  mov     dword ptr [rsp+0E8h+var_A0+4], eax
0x140069116  lea     r14, aReadinputbuffe; "ReadInputBufferException"
0x14006911d  lea     rax, WPP_GLOBAL_Control
0x140069124  mov     rcx, cs:WPP_GLOBAL_Control
0x14006912b  cmp     rcx, rax
0x14006912e  jz      short loc_140069155
0x140069130  mov     eax, [rcx+2Ch]
0x140069133  test    al, 10h
0x140069135  jz      short loc_140069155
0x140069137  cmp     byte ptr [rcx+29h], 2
0x14006913b  jb      short loc_140069155
0x14006913d  mov     edx, 95h
0x140069142  mov     r9d, ebx
0x140069145  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006914c  mov     rcx, [rcx+18h]
0x140069150  call    WPP_SF_d
0x140069155  lea     r15, WPP_GLOBAL_Control
0x14006915c  mov     r13, [rsp+0E8h+var_90]
0x140069161  mov     r12d, [rsp+0E8h+var_B0]
0x140069166  jmp     short loc_14006916D
0x140069168  mov     r12d, dword ptr [rsp+0E8h+Length]
0x14006916d  test    r13, r13
0x140069170  jz      short loc_14006919D
  ... truncated ...
```

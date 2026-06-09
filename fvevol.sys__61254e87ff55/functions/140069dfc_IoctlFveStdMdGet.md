# IoctlFveStdMdGet

- ea: `0x140069dfc`
- end: `0x14006a2bd`
- name: `IoctlFveStdMdGet`
- size: `1217`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x14006aad0`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140016f20`
- `0x140018894`
- `0x1400189cc`
- `0x140022d40`
- `0x140023040`
- `0x140067b98`
- `0x140069dfc`
- `0x14006d324`
- `0x14008b614`
- `0x140090230`
- `0x140090750`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140069f03`
- `ntoskrnl!ProbeForRead` at `0x140069f03`
- `ntoskrnl!ProbeForWrite` at `0x14006a104`
- `ntoskrnl!ProbeForWrite` at `0x14006a104`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a22f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a254`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a22f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a254`
- `ntoskrnl!ExAllocatePool2` at `0x140069f1d`
- `ntoskrnl!ExAllocatePool2` at `0x140069f1d`

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
  _OWORD *v12; // rdi
  unsigned int *v13; // rdi
  int v15; // [rsp+20h] [rbp-E8h]
  char *v16; // [rsp+28h] [rbp-E0h]
  _OWORD *Address; // [rsp+38h] [rbp-D0h]
  UNICODE_STRING SourceString[12]; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int Length; // [rsp+118h] [rbp+10h]
  unsigned int v21; // [rsp+120h] [rbp+18h]
  void *Src; // [rsp+128h] [rbp+20h] BYREF

  v4 = 0;
  Src = 0;
  memset(SourceString, 0, 0x90u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 167, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
  }
  v5 = *(_QWORD *)(a2 + 184);
  v6 = *(volatile void **)(v5 + 32);
  v7 = *(unsigned int *)(v5 + 16);
  v21 = *(_DWORD *)(v5 + 16);
  Address = *(_OWORD **)(a2 + 112);
  Length = *(_DWORD *)(v5 + 8);
  Request = FveKickAllSystemsGo(a1);
  if ( Request >= 0 )
  {
    if ( *(_BYTE *)(a2 + 64) )
      ProbeForRead(v6, v7, 4u);
    Pool2 = (char *)ExAllocatePool2(256, v7, 809850438);
    v4 = Pool2;
    v16 = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, (const void *)v6, v7);
    }
    else
    {
      Request = -1073741670;
      v15 = -1073741670;
    }
    if ( Request >= 0 )
    {
      Request = FveValidateStandaloneMetadataGetRequest(v4, v21);
      if ( Request >= 0 )
      {
        Request = FveVolumeInitInfo(a1, SourceString);
        if ( Request >= 0 )
        {
          Request = FveFsCreateSystemVolumeInformationFolder(SourceString);
          if ( Request >= 0 )
          {
            Request = FveReadStandaloneMetadata(SourceString, (GUID *)(v4 + 8));
            if ( Request >= 0 )
            {
              Request = FveCreateStandaloneMetadataGetResponseFromDataSet(v4 + 8, MEMORY[0x10], 24, &Src, v15, v16);
              if ( Request >= 0 )
              {
                if ( *(_BYTE *)(a2 + 64) )
                  ProbeForWrite(Address, Length, 8u);
                v12 = Src;
                if ( Length >= *(_DWORD *)Src )
                {
                  v13 = (unsigned int *)Src;
                  memmove(Address, Src, *(unsigned int *)Src);
                  *(_QWORD *)(a2 + 56) = *v13;
                }
                else if ( Length < 0x40 )
                {
                  Request = -1073741789;
                }
                else
                {
                  *Address = *(_OWORD *)Src;
                  Address[1] = v12[1];
                  Address[2] = v12[2];
                  Address[3] = v12[3];
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
      WPP_SF_d(v9->AttachedDevice, v10, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, (unsigned int)Request);
    }
  }
  if ( v4 )
    ExFreePoolWithTag(v4, 0x30455646u);
  FveVolumeCleanupInfo(SourceString);
  if ( Src )
    FveLibClientFree(Src, *(unsigned int *)Src);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      178,
      WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
      (unsigned int)Request);
  }
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x140069dfc  mov     rax, rsp
0x140069dff  mov     [rax+8], rcx
0x140069e03  push    rbx
0x140069e04  push    rdi
0x140069e05  push    r12
0x140069e07  push    r13
0x140069e09  push    r14
0x140069e0b  push    r15
0x140069e0d  sub     rsp, 0D8h
0x140069e14  mov     r13, rdx
0x140069e17  mov     rbx, rcx
0x140069e1a  mov     [rsp+108h+P], 0
0x140069e23  xor     r15d, r15d
0x140069e26  mov     [rsp+108h+var_E0], r15
0x140069e2b  mov     [rax+20h], r15
0x140069e2f  xor     edx, edx; Val
0x140069e31  mov     r8d, 90h; Size
0x140069e37  lea     rcx, [rsp+108h+SourceString]; void *
0x140069e3c  call    memset
0x140069e41  lea     r14, WPP_GLOBAL_Control
0x140069e48  mov     rcx, cs:WPP_GLOBAL_Control
0x140069e4f  cmp     rcx, r14
0x140069e52  jz      short loc_140069E76
0x140069e54  mov     eax, [rcx+2Ch]
0x140069e57  test    al, 10h
0x140069e59  jz      short loc_140069E76
0x140069e5b  cmp     byte ptr [rcx+29h], 5
0x140069e5f  jb      short loc_140069E76
0x140069e61  mov     edx, 0A7h
0x140069e66  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140069e6d  mov     rcx, [rcx+18h]
0x140069e71  call    WPP_SF_
0x140069e76  mov     rax, [r13+0B8h]
0x140069e7d  mov     r12, [rax+20h]
0x140069e81  mov     edi, [rax+10h]
0x140069e84  mov     [rsp+108h+arg_10], edi
0x140069e8b  mov     rcx, [r13+70h]
0x140069e8f  mov     [rsp+108h+Address], rcx
0x140069e94  mov     eax, [rax+8]
0x140069e97  mov     dword ptr [rsp+108h+Length], eax
0x140069e9e  xor     edx, edx
0x140069ea0  mov     rcx, rbx
0x140069ea3  call    FveKickAllSystemsGo
0x140069ea8  mov     ebx, eax
0x140069eaa  test    eax, eax
0x140069eac  jns     short loc_140069EF0
0x140069eae  mov     rcx, cs:WPP_GLOBAL_Control
0x140069eb5  cmp     rcx, r14
0x140069eb8  jz      loc_14006A222
0x140069ebe  mov     eax, [rcx+2Ch]
0x140069ec1  test    al, 10h
0x140069ec3  jz      loc_14006A222
0x140069ec9  cmp     byte ptr [rcx+29h], 2
0x140069ecd  jb      loc_14006A222
0x140069ed3  mov     edx, 0A8h
0x140069ed8  mov     r9d, ebx
0x140069edb  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140069ee2  mov     rcx, [rcx+18h]
0x140069ee6  call    WPP_SF_d
0x140069eeb  jmp     loc_14006A222
0x140069ef0  cmp     byte ptr [r13+40h], 0
0x140069ef5  jz      short loc_140069F0F
0x140069ef7  mov     rdx, rdi; Length
0x140069efa  mov     r8d, 4; Alignment
0x140069f00  mov     rcx, r12; Address
0x140069f03  call    cs:__imp_ProbeForRead
0x140069f0a  nop     dword ptr [rax+rax+00h]
0x140069f0f  mov     r8d, 30455646h
0x140069f15  mov     rdx, rdi
0x140069f18  mov     ecx, 100h
0x140069f1d  call    cs:__imp_ExAllocatePool2
0x140069f24  nop     dword ptr [rax+rax+00h]
0x140069f29  mov     r15, rax
0x140069f2c  mov     [rsp+108h+var_E0], rax
0x140069f31  test    rax, rax
0x140069f34  jnz     short loc_140069F41
0x140069f36  mov     ebx, 0C000009Ah
0x140069f3b  mov     [rsp+108h+var_E8], ebx
0x140069f3f  jmp     short loc_140069F50
0x140069f41  mov     r8, rdi; Size
0x140069f44  mov     rdx, r12; Src
0x140069f47  mov     rcx, r15; void *
0x140069f4a  call    memmove
0x140069f4f  nop
0x140069f50  test    ebx, ebx
0x140069f52  jns     short loc_140069F83
0x140069f54  mov     rcx, cs:WPP_GLOBAL_Control
0x140069f5b  cmp     rcx, r14
0x140069f5e  jz      loc_14006A222
0x140069f64  mov     eax, [rcx+2Ch]
0x140069f67  test    al, 10h
0x140069f69  jz      loc_14006A222
0x140069f6f  cmp     byte ptr [rcx+29h], 2
0x140069f73  jb      loc_14006A222
0x140069f79  mov     edx, 0AAh
0x140069f7e  jmp     loc_140069ED8
0x140069f83  mov     edx, [rsp+108h+arg_10]
0x140069f8a  mov     rcx, r15
0x140069f8d  call    FveValidateStandaloneMetadataGetRequest
0x140069f92  mov     ebx, eax
0x140069f94  test    eax, eax
0x140069f96  jns     short loc_140069FC7
0x140069f98  mov     rcx, cs:WPP_GLOBAL_Control
0x140069f9f  cmp     rcx, r14
0x140069fa2  jz      loc_14006A222
0x140069fa8  mov     eax, [rcx+2Ch]
0x140069fab  test    al, 10h
0x140069fad  jz      loc_14006A222
0x140069fb3  cmp     byte ptr [rcx+29h], 2
0x140069fb7  jb      loc_14006A222
0x140069fbd  mov     edx, 0ABh
0x140069fc2  jmp     loc_140069ED8
0x140069fc7  lea     rdx, [rsp+108h+SourceString]
0x140069fcc  mov     rcx, [rsp+108h+arg_0]
0x140069fd4  call    FveVolumeInitInfo
0x140069fd9  mov     ebx, eax
0x140069fdb  test    eax, eax
0x140069fdd  jns     short loc_14006A00E
0x140069fdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140069fe6  cmp     rcx, r14
0x140069fe9  jz      loc_14006A222
0x140069fef  mov     eax, [rcx+2Ch]
0x140069ff2  test    al, 10h
0x140069ff4  jz      loc_14006A222
0x140069ffa  cmp     byte ptr [rcx+29h], 2
0x140069ffe  jb      loc_14006A222
0x14006a004  mov     edx, 0ACh
0x14006a009  jmp     loc_140069ED8
0x14006a00e  lea     rcx, [rsp+108h+SourceString]; SourceString
0x14006a013  call    FveFsCreateSystemVolumeInformationFolder
0x14006a018  mov     ebx, eax
0x14006a01a  test    eax, eax
0x14006a01c  jns     short loc_14006A04D
0x14006a01e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a025  cmp     rcx, r14
0x14006a028  jz      loc_14006A222
0x14006a02e  mov     eax, [rcx+2Ch]
0x14006a031  test    al, 10h
0x14006a033  jz      loc_14006A222
0x14006a039  cmp     byte ptr [rcx+29h], 2
0x14006a03d  jb      loc_14006A222
0x14006a043  mov     edx, 0ADh
0x14006a048  jmp     loc_140069ED8
0x14006a04d  lea     r8, [rsp+108h+P]
0x14006a052  lea     rdx, [r15+8]; Guid
0x14006a056  lea     rcx, [rsp+108h+SourceString]; SourceString
0x14006a05b  call    FveReadStandaloneMetadata
0x14006a060  mov     ebx, eax
0x14006a062  test    eax, eax
0x14006a064  jns     short loc_14006A095
0x14006a066  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a06d  cmp     rcx, r14
0x14006a070  jz      loc_14006A222
0x14006a076  mov     eax, [rcx+2Ch]
0x14006a079  test    al, 10h
0x14006a07b  jz      loc_14006A222
0x14006a081  cmp     byte ptr [rcx+29h], 2
0x14006a085  jb      loc_14006A222
0x14006a08b  mov     edx, 0AEh
0x14006a090  jmp     loc_140069ED8
0x14006a095  mov     rcx, [rsp+108h+P]
0x14006a09a  lea     r8, [rcx+18h]
0x14006a09e  lea     r9, [rsp+108h+Src]
0x14006a0a6  mov     rdx, [rcx+10h]
0x14006a0aa  lea     rcx, [r15+8]
0x14006a0ae  call    FveCreateStandaloneMetadataGetResponseFromDataSet
0x14006a0b3  mov     ebx, eax
0x14006a0b5  test    eax, eax
0x14006a0b7  jns     short loc_14006A0E8
0x14006a0b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a0c0  cmp     rcx, r14
0x14006a0c3  jz      loc_14006A222
0x14006a0c9  mov     eax, [rcx+2Ch]
0x14006a0cc  test    al, 10h
0x14006a0ce  jz      loc_14006A222
0x14006a0d4  cmp     byte ptr [rcx+29h], 2
0x14006a0d8  jb      loc_14006A222
0x14006a0de  mov     edx, 0AFh
0x14006a0e3  jmp     loc_140069ED8
0x14006a0e8  mov     r12, [rsp+108h+Address]
0x14006a0ed  cmp     byte ptr [r13+40h], 0
0x14006a0f2  jz      short loc_14006A110
0x14006a0f4  mov     edx, dword ptr [rsp+108h+Length]; Length
0x14006a0fb  mov     r8d, 8; Alignment
0x14006a101  mov     rcx, r12; Address
0x14006a104  call    cs:__imp_ProbeForWrite
0x14006a10b  nop     dword ptr [rax+rax+00h]
0x14006a110  mov     rdi, [rsp+108h+Src]
0x14006a118  mov     eax, [rdi]
0x14006a11a  mov     ecx, dword ptr [rsp+108h+Length]
0x14006a121  cmp     ecx, eax
0x14006a123  jnb     short loc_14006A16B
0x14006a125  cmp     ecx, 40h ; '@'
0x14006a128  jb      short loc_14006A15D
0x14006a12a  movups  xmm0, xmmword ptr [rdi]
0x14006a12d  movups  xmmword ptr [r12], xmm0
0x14006a132  movups  xmm1, xmmword ptr [rdi+10h]
0x14006a136  movups  xmmword ptr [r12+10h], xmm1
0x14006a13c  movups  xmm0, xmmword ptr [rdi+20h]
0x14006a140  movups  xmmword ptr [r12+20h], xmm0
0x14006a146  movups  xmm1, xmmword ptr [rdi+30h]
0x14006a14a  movups  xmmword ptr [r12+30h], xmm1
0x14006a150  mov     qword ptr [r13+38h], 40h ; '@'
0x14006a158  jmp     loc_14006A222
0x14006a15d  mov     ebx, 0C0000023h
0x14006a162  mov     [rsp+108h+var_E8], ebx
0x14006a166  jmp     loc_14006A222
0x14006a16b  mov     r8, rax; Size
0x14006a16e  mov     rdi, [rsp+108h+Src]
0x14006a176  mov     rdx, rdi; Src
0x14006a179  mov     rcx, r12; void *
0x14006a17c  call    memmove
0x14006a181  mov     eax, [rdi]
0x14006a183  mov     [r13+38h], rax
0x14006a187  jmp     loc_14006A222
0x14006a18c  mov     ebx, eax
0x14006a18e  mov     [rsp+108h+var_E8], eax
0x14006a192  lea     rax, WPP_GLOBAL_Control
0x14006a199  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a1a0  cmp     rcx, rax
0x14006a1a3  jz      short loc_14006A1CA
0x14006a1a5  mov     eax, [rcx+2Ch]
0x14006a1a8  test    al, 10h
0x14006a1aa  jz      short loc_14006A1CA
0x14006a1ac  cmp     byte ptr [rcx+29h], 2
0x14006a1b0  jb      short loc_14006A1CA
0x14006a1b2  mov     edx, 0B0h
0x14006a1b7  mov     r9d, ebx
0x14006a1ba  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006a1c1  mov     rcx, [rcx+18h]
0x14006a1c5  call    WPP_SF_d
0x14006a1ca  lea     r14, WPP_GLOBAL_Control
0x14006a1d1  mov     r15, [rsp+108h+var_E0]
0x14006a1d6  jmp     short loc_14006A222
0x14006a1d8  mov     ebx, eax
0x14006a1da  mov     [rsp+108h+var_E8], eax
0x14006a1de  lea     rax, WPP_GLOBAL_Control
0x14006a1e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a1ec  cmp     rcx, rax
0x14006a1ef  jz      short loc_14006A216
0x14006a1f1  mov     eax, [rcx+2Ch]
0x14006a1f4  test    al, 10h
0x14006a1f6  jz      short loc_14006A216
0x14006a1f8  cmp     byte ptr [rcx+29h], 2
0x14006a1fc  jb      short loc_14006A216
0x14006a1fe  mov     edx, 0A9h
0x14006a203  mov     r9d, ebx
0x14006a206  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006a20d  mov     rcx, [rcx+18h]
0x14006a211  call    WPP_SF_d
0x14006a216  lea     r14, WPP_GLOBAL_Control
0x14006a21d  mov     r15, [rsp+108h+var_E0]
0x14006a222  test    r15, r15
0x14006a225  jz      short loc_14006A23B
0x14006a227  mov     edx, 30455646h; Tag
0x14006a22c  mov     rcx, r15; P
0x14006a22f  call    cs:__imp_ExFreePoolWithTag
0x14006a236  nop     dword ptr [rax+rax+00h]
0x14006a23b  lea     rcx, [rsp+108h+SourceString]; void *
0x14006a240  call    FveVolumeCleanupInfo
0x14006a245  mov     rcx, [rsp+108h+P]; P
0x14006a24a  test    rcx, rcx
0x14006a24d  jz      short loc_14006A260
0x14006a24f  mov     edx, 30455646h; Tag
0x14006a254  call    cs:__imp_ExFreePoolWithTag
0x14006a25b  nop     dword ptr [rax+rax+00h]
0x14006a260  mov     rdi, [rsp+108h+Src]
0x14006a268  test    rdi, rdi
0x14006a26b  jz      short loc_14006A277
0x14006a26d  mov     edx, [rdi]
0x14006a26f  mov     rcx, rdi
0x14006a272  call    FveLibClientFree
0x14006a277  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a27e  cmp     rcx, r14
0x14006a281  jz      short loc_14006A2A8
0x14006a283  mov     eax, [rcx+2Ch]
0x14006a286  test    al, 10h
0x14006a288  jz      short loc_14006A2A8
0x14006a28a  cmp     byte ptr [rcx+29h], 5
0x14006a28e  jb      short loc_14006A2A8
0x14006a290  mov     edx, 0B2h
0x14006a295  mov     r9d, ebx
0x14006a298  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006a29f  mov     rcx, [rcx+18h]
0x14006a2a3  call    WPP_SF_d
0x14006a2a8  mov     eax, ebx
0x14006a2aa  add     rsp, 0D8h
0x14006a2b1  pop     r15
0x14006a2b3  pop     r14
0x14006a2b5  pop     r13
0x14006a2b7  pop     r12
0x14006a2b9  pop     rdi
0x14006a2ba  pop     rbx
0x14006a2bb  retn
```

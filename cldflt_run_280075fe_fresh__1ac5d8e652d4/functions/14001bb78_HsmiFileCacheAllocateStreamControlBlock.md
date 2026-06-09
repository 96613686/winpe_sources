# HsmiFileCacheAllocateStreamControlBlock

- ea: `0x14001bb78`
- end: `0x14001bdb0`
- name: `HsmiFileCacheAllocateStreamControlBlock`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001b590`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14000d908`
- `0x14001bb78`
- `0x14001c788`
- `0x14001c7f4`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14001bcd1`
- `ntoskrnl!ObfReferenceObject` at `0x14001bcd1`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001bc79`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001bc8f`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001bc79`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001bc8f`
- `ntoskrnl!ExAllocatePool2` at `0x14001bc0b`
- `ntoskrnl!ExAllocatePool2` at `0x14001bc0b`

## pseudocode

```c
__int64 __fastcall HsmiFileCacheAllocateStreamControlBlock(
        __int64 a1,
        unsigned int a2,
        void *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7)
{
  __int64 v8; // rbp
  __int64 Pool2; // rax
  __int64 v11; // r14
  unsigned int v12; // esi
  __int64 v13; // rdi
  char v14; // al
  __int64 v15; // rdx
  __int64 v16; // r8

  v8 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_Dqi(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, a2, a3, a4);
  }
  *a7 = 0;
  if ( !(_DWORD)v8 || (((_DWORD)v8 - 1) & (unsigned int)v8) != 0 )
  {
    v12 = -1073741811;
    HsmDbgBreakOnStatus(3221225485LL);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v12;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_DLd(WPP_GLOBAL_Control->AttachedDevice, v15, v16, (unsigned int)v8, v8);
  }
  else
  {
    Pool2 = ExAllocatePool2(64, 312, 1666216776);
    v11 = Pool2;
    if ( Pool2 )
    {
      v13 = Pool2 + 48;
      v12 = 0;
      ExInitializeResourceLite((PERESOURCE)(Pool2 + 48));
      ExInitializeResourceLite((PERESOURCE)(v11 + 152));
      *(_QWORD *)(v11 + 280) = a1;
      *(_QWORD *)(v11 + 296) = a5;
      *(_QWORD *)(v11 + 304) = HsmiBitmapNORMALVerifyBitmapPages;
      *(_QWORD *)(v11 + 288) = a3;
      ObfReferenceObject(a3);
      v14 = *(_BYTE *)(v11 + 7) & 0xF;
      *(_QWORD *)(v11 + 16) = v11 + 152;
      *(_DWORD *)v11 = 20450561;
      *(_BYTE *)(v11 + 7) = v14 | 0x10;
      *(_BYTE *)(v11 + 5) = 0;
      *(_QWORD *)(v11 + 8) = v13;
      *(_QWORD *)(v11 + 32) = a4;
      *(_DWORD *)(v11 + 40) = -1;
      *(_QWORD *)(v11 + 24) = -v8 & (v8 + a4 - 1);
      *(_DWORD *)(v11 + 44) = 0x7FFFFFFF;
      *a7 = v11;
    }
    else
    {
      v12 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v12;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
          312,
          -1073741670);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, *a7, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x14001bb78  mov     [rsp+arg_0], rcx
0x14001bb7d  push    rbx
0x14001bb7e  push    rbp
0x14001bb7f  push    rsi
0x14001bb80  push    rdi
0x14001bb81  push    r12
0x14001bb83  push    r13
0x14001bb85  push    r14
0x14001bb87  push    r15
0x14001bb89  sub     rsp, 38h
0x14001bb8d  mov     r12, r9
0x14001bb90  mov     ebp, edx
0x14001bb92  mov     r13, r8
0x14001bb95  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb9c  lea     rbx, WPP_GLOBAL_Control
0x14001bba3  cmp     rcx, rbx
0x14001bba6  jz      short loc_14001BBD7
0x14001bba8  mov     eax, [rcx+2Ch]
0x14001bbab  test    al, 8
0x14001bbad  jz      short loc_14001BBD7
0x14001bbaf  cmp     byte ptr [rcx+29h], 5
0x14001bbb3  jb      short loc_14001BBD7
0x14001bbb5  mov     rcx, [rcx+18h]
0x14001bbb9  mov     edx, 17h
0x14001bbbe  mov     [rsp+78h+var_50], r9
0x14001bbc3  mov     r9d, ebp
0x14001bbc6  mov     [rsp+78h+var_58], r8
0x14001bbcb  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bbd2  call    WPP_SF_Dqi
0x14001bbd7  mov     r15, [rsp+78h+arg_30]
0x14001bbdf  mov     qword ptr [r15], 0
0x14001bbe6  test    ebp, ebp
0x14001bbe8  jz      loc_14001BD31
0x14001bbee  lea     eax, [rbp-1]
0x14001bbf1  test    ebp, eax
0x14001bbf3  jnz     loc_14001BD31
0x14001bbf9  mov     edi, 138h
0x14001bbfe  mov     r8d, 63507348h
0x14001bc04  mov     edx, edi
0x14001bc06  mov     ecx, 40h ; '@'
0x14001bc0b  call    cs:__imp_ExAllocatePool2
0x14001bc12  nop     dword ptr [rax+rax+00h]
0x14001bc17  mov     r14, rax
0x14001bc1a  test    rax, rax
0x14001bc1d  jnz     short loc_14001BC70
0x14001bc1f  mov     esi, 0C000009Ah
0x14001bc24  mov     ecx, esi
0x14001bc26  call    HsmDbgBreakOnStatus
0x14001bc2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc32  cmp     rcx, rbx
0x14001bc35  jz      loc_14001BD9C
0x14001bc3b  mov     eax, [rcx+2Ch]
0x14001bc3e  test    al, 8
0x14001bc40  jz      loc_14001BD66
0x14001bc46  cmp     byte ptr [rcx+29h], 2
0x14001bc4a  jb      loc_14001BD66
0x14001bc50  mov     rcx, [rcx+18h]
0x14001bc54  lea     edx, [r14+19h]
0x14001bc58  mov     r9d, edi
0x14001bc5b  mov     dword ptr [rsp+78h+var_58], esi
0x14001bc5f  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bc66  call    WPP_SF_Dd
0x14001bc6b  jmp     loc_14001BD66
0x14001bc70  lea     rdi, [rax+30h]
0x14001bc74  xor     esi, esi
0x14001bc76  mov     rcx, rdi; Resource
0x14001bc79  call    cs:__imp_ExInitializeResourceLite
0x14001bc80  nop     dword ptr [rax+rax+00h]
0x14001bc85  lea     rbx, [r14+98h]
0x14001bc8c  mov     rcx, rbx; Resource
0x14001bc8f  call    cs:__imp_ExInitializeResourceLite
0x14001bc96  nop     dword ptr [rax+rax+00h]
0x14001bc9b  mov     rax, [rsp+78h+arg_0]
0x14001bca3  mov     rcx, r13; Object
0x14001bca6  mov     [r14+118h], rax
0x14001bcad  mov     rax, [rsp+78h+arg_20]
0x14001bcb5  mov     [r14+128h], rax
0x14001bcbc  lea     rax, HsmiBitmapNORMALVerifyBitmapPages
0x14001bcc3  mov     [r14+130h], rax
0x14001bcca  mov     [r14+120h], r13
0x14001bcd1  call    cs:__imp_ObfReferenceObject
0x14001bcd8  nop     dword ptr [rax+rax+00h]
0x14001bcdd  mov     al, [r14+7]
0x14001bce1  mov     rcx, rbp
0x14001bce4  and     al, 0Fh
0x14001bce6  mov     [r14+10h], rbx
0x14001bcea  or      al, 10h
0x14001bcec  mov     dword ptr [r14], 1380D01h
0x14001bcf3  mov     [r14+7], al
0x14001bcf7  lea     rbx, WPP_GLOBAL_Control
0x14001bcfe  lea     rax, [r12-1]
0x14001bd03  mov     [r14+5], sil
0x14001bd07  add     rax, rbp
0x14001bd0a  mov     [r14+8], rdi
0x14001bd0e  neg     rcx
0x14001bd11  mov     [r14+20h], r12
0x14001bd15  and     rax, rcx
0x14001bd18  mov     dword ptr [r14+28h], 0FFFFFFFFh
0x14001bd20  mov     [r14+18h], rax
0x14001bd24  mov     dword ptr [r14+2Ch], 7FFFFFFFh
0x14001bd2c  mov     [r15], r14
0x14001bd2f  jmp     short loc_14001BD66
0x14001bd31  mov     esi, 0C000000Dh
0x14001bd36  mov     ecx, esi
0x14001bd38  call    HsmDbgBreakOnStatus
0x14001bd3d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd44  cmp     rcx, rbx
0x14001bd47  jz      short loc_14001BD9C
0x14001bd49  mov     eax, [rcx+2Ch]
0x14001bd4c  test    al, 8
0x14001bd4e  jz      short loc_14001BD66
0x14001bd50  cmp     byte ptr [rcx+29h], 2
0x14001bd54  jb      short loc_14001BD66
0x14001bd56  mov     rcx, [rcx+18h]
0x14001bd5a  mov     r9d, ebp
0x14001bd5d  mov     dword ptr [rsp+78h+var_58], ebp
0x14001bd61  call    WPP_SF_DLd
0x14001bd66  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd6d  cmp     rcx, rbx
0x14001bd70  jz      short loc_14001BD9C
0x14001bd72  mov     edx, [rcx+2Ch]
0x14001bd75  test    dl, 8
0x14001bd78  jz      short loc_14001BD9C
0x14001bd7a  cmp     byte ptr [rcx+29h], 5
0x14001bd7e  jb      short loc_14001BD9C
0x14001bd80  mov     r9, [r15]
0x14001bd83  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bd8a  mov     rcx, [rcx+18h]
0x14001bd8e  mov     edx, 1Ah
0x14001bd93  mov     dword ptr [rsp+78h+var_58], esi
0x14001bd97  call    WPP_SF_qd
0x14001bd9c  mov     eax, esi
0x14001bd9e  add     rsp, 38h
0x14001bda2  pop     r15
0x14001bda4  pop     r14
0x14001bda6  pop     r13
0x14001bda8  pop     r12
0x14001bdaa  pop     rdi
0x14001bdab  pop     rsi
0x14001bdac  pop     rbp
0x14001bdad  pop     rbx
0x14001bdae  retn
```

# HsmiFileCacheAllocateStreamControlBlock

- ea: `0x14001bbf8`
- end: `0x14001be30`
- name: `HsmiFileCacheAllocateStreamControlBlock`
- size: `568`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, __int64, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001b610`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14000d908`
- `0x14001bbf8`
- `0x14001c808`
- `0x14001c874`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14001bd51`
- `ntoskrnl!ObfReferenceObject` at `0x14001bd51`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001bcf9`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001bd0f`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001bcf9`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001bd0f`
- `ntoskrnl!ExAllocatePool2` at `0x14001bc8b`
- `ntoskrnl!ExAllocatePool2` at `0x14001bc8b`

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
    HsmDbgBreakOnStatus(-1073741811);
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
      HsmDbgBreakOnStatus(-1073741670);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v12;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids);
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
0x14001bbf8  mov     [rsp+arg_0], rcx
0x14001bbfd  push    rbx
0x14001bbfe  push    rbp
0x14001bbff  push    rsi
0x14001bc00  push    rdi
0x14001bc01  push    r12
0x14001bc03  push    r13
0x14001bc05  push    r14
0x14001bc07  push    r15
0x14001bc09  sub     rsp, 38h
0x14001bc0d  mov     r12, r9
0x14001bc10  mov     ebp, edx
0x14001bc12  mov     r13, r8
0x14001bc15  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc1c  lea     rbx, WPP_GLOBAL_Control
0x14001bc23  cmp     rcx, rbx
0x14001bc26  jz      short loc_14001BC57
0x14001bc28  mov     eax, [rcx+2Ch]
0x14001bc2b  test    al, 8
0x14001bc2d  jz      short loc_14001BC57
0x14001bc2f  cmp     byte ptr [rcx+29h], 5
0x14001bc33  jb      short loc_14001BC57
0x14001bc35  mov     rcx, [rcx+18h]
0x14001bc39  mov     edx, 17h
0x14001bc3e  mov     [rsp+78h+var_50], r9
0x14001bc43  mov     r9d, ebp
0x14001bc46  mov     [rsp+78h+var_58], r8
0x14001bc4b  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bc52  call    WPP_SF_Dqi
0x14001bc57  mov     r15, [rsp+78h+arg_30]
0x14001bc5f  mov     qword ptr [r15], 0
0x14001bc66  test    ebp, ebp
0x14001bc68  jz      loc_14001BDB1
0x14001bc6e  lea     eax, [rbp-1]
0x14001bc71  test    ebp, eax
0x14001bc73  jnz     loc_14001BDB1
0x14001bc79  mov     edi, 138h
0x14001bc7e  mov     r8d, 63507348h
0x14001bc84  mov     edx, edi
0x14001bc86  mov     ecx, 40h ; '@'
0x14001bc8b  call    cs:__imp_ExAllocatePool2
0x14001bc92  nop     dword ptr [rax+rax+00h]
0x14001bc97  mov     r14, rax
0x14001bc9a  test    rax, rax
0x14001bc9d  jnz     short loc_14001BCF0
0x14001bc9f  mov     esi, 0C000009Ah
0x14001bca4  mov     ecx, esi
0x14001bca6  call    HsmDbgBreakOnStatus
0x14001bcab  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bcb2  cmp     rcx, rbx
0x14001bcb5  jz      loc_14001BE1C
0x14001bcbb  mov     eax, [rcx+2Ch]
0x14001bcbe  test    al, 8
0x14001bcc0  jz      loc_14001BDE6
0x14001bcc6  cmp     byte ptr [rcx+29h], 2
0x14001bcca  jb      loc_14001BDE6
0x14001bcd0  mov     rcx, [rcx+18h]
0x14001bcd4  lea     edx, [r14+19h]
0x14001bcd8  mov     r9d, edi
0x14001bcdb  mov     dword ptr [rsp+78h+var_58], esi
0x14001bcdf  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bce6  call    WPP_SF_Dd
0x14001bceb  jmp     loc_14001BDE6
0x14001bcf0  lea     rdi, [rax+30h]
0x14001bcf4  xor     esi, esi
0x14001bcf6  mov     rcx, rdi; Resource
0x14001bcf9  call    cs:__imp_ExInitializeResourceLite
0x14001bd00  nop     dword ptr [rax+rax+00h]
0x14001bd05  lea     rbx, [r14+98h]
0x14001bd0c  mov     rcx, rbx; Resource
0x14001bd0f  call    cs:__imp_ExInitializeResourceLite
0x14001bd16  nop     dword ptr [rax+rax+00h]
0x14001bd1b  mov     rax, [rsp+78h+arg_0]
0x14001bd23  mov     rcx, r13; Object
0x14001bd26  mov     [r14+118h], rax
0x14001bd2d  mov     rax, [rsp+78h+arg_20]
0x14001bd35  mov     [r14+128h], rax
0x14001bd3c  lea     rax, HsmiBitmapNORMALVerifyBitmapPages
0x14001bd43  mov     [r14+130h], rax
0x14001bd4a  mov     [r14+120h], r13
0x14001bd51  call    cs:__imp_ObfReferenceObject
0x14001bd58  nop     dword ptr [rax+rax+00h]
0x14001bd5d  mov     al, [r14+7]
0x14001bd61  mov     rcx, rbp
0x14001bd64  and     al, 0Fh
0x14001bd66  mov     [r14+10h], rbx
0x14001bd6a  or      al, 10h
0x14001bd6c  mov     dword ptr [r14], 1380D01h
0x14001bd73  mov     [r14+7], al
0x14001bd77  lea     rbx, WPP_GLOBAL_Control
0x14001bd7e  lea     rax, [r12-1]
0x14001bd83  mov     [r14+5], sil
0x14001bd87  add     rax, rbp
0x14001bd8a  mov     [r14+8], rdi
0x14001bd8e  neg     rcx
0x14001bd91  mov     [r14+20h], r12
0x14001bd95  and     rax, rcx
0x14001bd98  mov     dword ptr [r14+28h], 0FFFFFFFFh
0x14001bda0  mov     [r14+18h], rax
0x14001bda4  mov     dword ptr [r14+2Ch], 7FFFFFFFh
0x14001bdac  mov     [r15], r14
0x14001bdaf  jmp     short loc_14001BDE6
0x14001bdb1  mov     esi, 0C000000Dh
0x14001bdb6  mov     ecx, esi
0x14001bdb8  call    HsmDbgBreakOnStatus
0x14001bdbd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bdc4  cmp     rcx, rbx
0x14001bdc7  jz      short loc_14001BE1C
0x14001bdc9  mov     eax, [rcx+2Ch]
0x14001bdcc  test    al, 8
0x14001bdce  jz      short loc_14001BDE6
0x14001bdd0  cmp     byte ptr [rcx+29h], 2
0x14001bdd4  jb      short loc_14001BDE6
0x14001bdd6  mov     rcx, [rcx+18h]
0x14001bdda  mov     r9d, ebp
0x14001bddd  mov     dword ptr [rsp+78h+var_58], ebp
0x14001bde1  call    WPP_SF_DLd
0x14001bde6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bded  cmp     rcx, rbx
0x14001bdf0  jz      short loc_14001BE1C
0x14001bdf2  mov     edx, [rcx+2Ch]
0x14001bdf5  test    dl, 8
0x14001bdf8  jz      short loc_14001BE1C
0x14001bdfa  cmp     byte ptr [rcx+29h], 5
0x14001bdfe  jb      short loc_14001BE1C
0x14001be00  mov     r9, [r15]
0x14001be03  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001be0a  mov     rcx, [rcx+18h]
0x14001be0e  mov     edx, 1Ah
0x14001be13  mov     dword ptr [rsp+78h+var_58], esi
0x14001be17  call    WPP_SF_qd
0x14001be1c  mov     eax, esi
0x14001be1e  add     rsp, 38h
0x14001be22  pop     r15
0x14001be24  pop     r14
0x14001be26  pop     r13
0x14001be28  pop     r12
0x14001be2a  pop     rdi
0x14001be2b  pop     rsi
0x14001be2c  pop     rbp
0x14001be2d  pop     rbx
0x14001be2e  retn
```

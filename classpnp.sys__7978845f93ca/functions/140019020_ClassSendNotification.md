# ClassSendNotification

- ea: `0x140019020`
- end: `0x140019129`
- name: `ClassSendNotification`
- size: `265`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, const GUID *Guid, ULONG ExtraDataSize, PVOID ExtraData)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400084b0`
- `0x140016ea0`
- `0x140021ba4`
- `0x140021c78`

## callees

- `0x140019020`
- `0x14001fbf4`
- `0x14003e640`

## import_xrefs

- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x1400190bf`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x1400190bf`
- `ntoskrnl!ExAllocatePool2` at `0x14001905e`
- `ntoskrnl!ExAllocatePool2` at `0x14001905e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400190d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400190d0`

## pseudocode

```c
void __stdcall ClassSendNotification(
        PFUNCTIONAL_DEVICE_EXTENSION FdoExtension,
        const GUID *Guid,
        ULONG ExtraDataSize,
        PVOID ExtraData)
{
  ULONG v8; // edi
  __int64 Pool2; // rax
  void *v10; // rbx

  v8 = ExtraDataSize + 39;
  if ( ExtraDataSize >= 0xFFFFFFD9 )
  {
    v8 = -1;
  }
  else if ( v8 <= 0xFFFF )
  {
    Pool2 = ExAllocatePool2(64, v8, 1867408211);
    v10 = (void *)Pool2;
    if ( Pool2 )
    {
      *(_WORD *)Pool2 = 1;
      *(_WORD *)(Pool2 + 2) = v8;
      *(_QWORD *)(Pool2 + 24) = 0;
      *(_DWORD *)(Pool2 + 32) = -1;
      *(GUID *)(Pool2 + 4) = *Guid;
      if ( ExtraData )
      {
        if ( ExtraDataSize )
          memmove((void *)(Pool2 + 36), ExtraData, ExtraDataSize);
      }
      IoReportTargetDeviceChangeAsynchronous(FdoExtension->LowerPdo, v10, 0, 0);
      ExFreePoolWithTag(v10, 0);
    }
    return;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v8);
  }
}

```

## disassembly

```asm
0x140019020  push    rbx
0x140019022  push    rbp
0x140019023  push    rsi
0x140019024  push    rdi
0x140019025  push    r14
0x140019027  push    r15
0x140019029  sub     rsp, 28h
0x14001902d  mov     esi, r8d
0x140019030  mov     rbp, r9
0x140019033  mov     r14, rdx
0x140019036  mov     r15, rcx
0x140019039  lea     edi, [rsi+27h]
0x14001903c  cmp     edi, 27h ; '''
0x14001903f  jb      loc_1400190DE
0x140019045  cmp     edi, 0FFFFh
0x14001904b  ja      loc_1400190E1
0x140019051  mov     edx, edi
0x140019053  mov     ecx, 40h ; '@'
0x140019058  mov     r8d, 6F4E6353h
0x14001905e  call    cs:__imp_ExAllocatePool2
0x140019065  nop     dword ptr [rax+rax+00h]
0x14001906a  mov     rbx, rax
0x14001906d  test    rax, rax
0x140019070  jz      loc_14001911B
0x140019076  mov     word ptr [rax], 1
0x14001907b  mov     [rax+2], di
0x14001907f  mov     qword ptr [rax+18h], 0
0x140019087  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x14001908e  movups  xmm0, xmmword ptr [r14]
0x140019092  movdqu  xmmword ptr [rax+4], xmm0
0x140019097  test    rbp, rbp
0x14001909a  jz      short loc_1400190AF
0x14001909c  test    esi, esi
0x14001909e  jz      short loc_1400190AF
0x1400190a0  mov     r8d, esi; Size
0x1400190a3  lea     rcx, [rax+24h]; void *
0x1400190a7  mov     rdx, rbp; Src
0x1400190aa  call    memmove
0x1400190af  mov     rcx, [r15+200h]; PhysicalDeviceObject
0x1400190b6  xor     r9d, r9d; Context
0x1400190b9  xor     r8d, r8d; Callback
0x1400190bc  mov     rdx, rbx; NotificationStructure
0x1400190bf  call    cs:__imp_IoReportTargetDeviceChangeAsynchronous
0x1400190c6  nop     dword ptr [rax+rax+00h]
0x1400190cb  xor     edx, edx; Tag
0x1400190cd  mov     rcx, rbx; P
0x1400190d0  call    cs:__imp_ExFreePoolWithTag
0x1400190d7  nop     dword ptr [rax+rax+00h]
0x1400190dc  jmp     short loc_14001911B
0x1400190de  or      edi, 0FFFFFFFFh
0x1400190e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400190e8  lea     rax, WPP_GLOBAL_Control
0x1400190ef  cmp     rcx, rax
0x1400190f2  jz      short loc_14001911B
0x1400190f4  test    dword ptr [rcx+2Ch], 1000h
0x1400190fb  jz      short loc_14001911B
0x1400190fd  cmp     byte ptr [rcx+29h], 3
0x140019101  jb      short loc_14001911B
0x140019103  mov     rcx, [rcx+18h]
0x140019107  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x14001910e  mov     edx, 0Bh
0x140019113  mov     r9d, edi
0x140019116  call    WPP_SF_d
0x14001911b  add     rsp, 28h
0x14001911f  pop     r15
0x140019121  pop     r14
0x140019123  pop     rdi
0x140019124  pop     rsi
0x140019125  pop     rbp
0x140019126  pop     rbx
0x140019127  retn
```

# CscDiffTransferOpenHandle

- ea: `0x14000a884`
- end: `0x14000aae7`
- name: `CscDiffTransferOpenHandle`
- size: `611`
- prototype: `__int64 __fastcall(__int64, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x14006c560`
- `0x14008b1ec`

## callees

- `0x14000a884`
- `0x14000b5a0`
- `0x14000b9d0`
- `0x1400169d4`
- `0x140016a04`
- `0x1400190ec`
- `0x14001b710`
- `0x140061104`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000aa5b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000aa5b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000aa0e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000aa0e`
- `ntoskrnl!ZwClose` at `0x14000aa46`
- `ntoskrnl!ZwClose` at `0x14000aa46`

## pseudocode

```c
__int64 __fastcall CscDiffTransferOpenHandle(__int64 a1, struct _LIST_ENTRY *a2)
{
  int v2; // ebx
  int v3; // r14d
  __int64 v6; // rdi
  __int16 v7; // r15
  struct _LIST_ENTRY v9; // [rsp+70h] [rbp-10h] BYREF
  struct _LIST_ENTRY Handle; // [rsp+C0h] [rbp+40h] BYREF

  v2 = 0;
  v9.Flink = (struct _LIST_ENTRY *)2228256;
  Handle.Flink = 0;
  v3 = 0;
  Handle.Blink = 0;
  v9.Blink = (struct _LIST_ENTRY *)L":CscBitmapStream";
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_c950bf81be4d382ffece536fe43e6690_Traceguids, a1);
  v6 = *(_QWORD *)(a1 + 392);
  v7 = *(_WORD *)(a1 + 388);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_c950bf81be4d382ffece536fe43e6690_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_e97202f6601e396a8249708b9471af4e_Traceguids, a1, v6, a2);
    }
  }
  if ( (unsigned __int16)(v7 - 1) <= 1u && !*(_QWORD *)(v6 + 24) )
  {
    v2 = CscStorepLowIoCreateFilePoster(&Handle, a2, &v9, 2032127, 0, 128, 7, 3, 98, 0, 0, 0, 0);
    if ( v2 >= 0 )
    {
      v2 = ObReferenceObjectByHandle(Handle.Flink, 0x1F01FFu, 0, 0, (PVOID *)&Handle.Blink, 0);
      if ( v2 >= 0 )
      {
        v2 = CscStorepLowIoDisableImplicitTimeUpdates(Handle.Flink);
        if ( v2 >= 0 )
        {
          *(struct _LIST_ENTRY *)(v6 + 24) = Handle;
          goto LABEL_25;
        }
        v3 = 1437;
      }
      else
      {
        v3 = 1430;
      }
    }
    else
    {
      v3 = 1417;
    }
    if ( Handle.Flink )
      ZwClose(Handle.Flink);
    if ( Handle.Blink )
      ObfDereferenceObject(Handle.Blink);
    if ( v7 == 1 )
      CscBitmappSetDiffTransferType(a1, 2);
  }
LABEL_25:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      29,
      WPP_e97202f6601e396a8249708b9471af4e_Traceguids,
      (unsigned int)v2,
      v3);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000a884  mov     [rsp-28h+arg_0], rbx
0x14000a889  mov     [rsp-28h+arg_8], rsi
0x14000a88e  push    rbp
0x14000a88f  push    rdi
0x14000a890  push    r12
0x14000a892  push    r14
0x14000a894  push    r15
0x14000a896  mov     rbp, rsp
0x14000a899  sub     rsp, 80h
0x14000a8a0  xor     ebx, ebx
0x14000a8a2  mov     [rbp+var_10], 220020h
0x14000a8aa  lea     rax, aCscbitmapstrea; ":CscBitmapStream"
0x14000a8b1  mov     [rbp+Handle], rbx
0x14000a8b5  xor     r14d, r14d
0x14000a8b8  mov     [rbp+arg_18], rbx
0x14000a8bc  mov     [rbp+var_8], rax
0x14000a8c0  mov     r12, rdx
0x14000a8c3  mov     rsi, rcx
0x14000a8c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a8cd  lea     rdx, WPP_GLOBAL_Control
0x14000a8d4  cmp     rcx, rdx
0x14000a8d7  jz      short loc_14000A8FF
0x14000a8d9  test    dword ptr [rcx+2Ch], 40000h
0x14000a8e0  jz      short loc_14000A8FF
0x14000a8e2  mov     rcx, [rcx+18h]
0x14000a8e6  lea     edx, [rbx+0Ah]
0x14000a8e9  mov     r9, rsi
0x14000a8ec  lea     r8, WPP_c950bf81be4d382ffece536fe43e6690_Traceguids
0x14000a8f3  call    WPP_SF_q
0x14000a8f8  lea     rdx, WPP_GLOBAL_Control
0x14000a8ff  mov     rdi, [rsi+188h]
0x14000a906  movzx   r15d, word ptr [rsi+184h]
0x14000a90e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a915  cmp     rcx, rdx
0x14000a918  jz      short loc_14000A976
0x14000a91a  test    dword ptr [rcx+2Ch], 40000h
0x14000a921  jz      short loc_14000A93F
0x14000a923  mov     rcx, [rcx+18h]
0x14000a927  lea     r8, WPP_c950bf81be4d382ffece536fe43e6690_Traceguids
0x14000a92e  mov     edx, 0Bh
0x14000a933  call    WPP_SF_
0x14000a938  lea     rdx, WPP_GLOBAL_Control
0x14000a93f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a946  cmp     rcx, rdx
0x14000a949  jz      short loc_14000A976
0x14000a94b  test    dword ptr [rcx+2Ch], 40000h
0x14000a952  jz      short loc_14000A976
0x14000a954  mov     rcx, [rcx+18h]
0x14000a958  lea     r8, WPP_e97202f6601e396a8249708b9471af4e_Traceguids
0x14000a95f  mov     edx, 1Ch
0x14000a964  mov     [rsp+80h+HandleInformation], r12
0x14000a969  mov     r9, rsi
0x14000a96c  mov     [rsp+80h+Object], rdi
0x14000a971  call    WPP_SF_qqq
0x14000a976  mov     ecx, 1
0x14000a97b  movzx   eax, r15w
0x14000a97f  sub     ax, cx
0x14000a982  cmp     ax, cx
0x14000a985  ja      loc_14000AA8F
0x14000a98b  cmp     [rdi+18h], rbx
0x14000a98f  jnz     loc_14000AA8F
0x14000a995  mov     [rsp+80h+var_20], rbx
0x14000a99a  lea     r8, [rbp+var_10]
0x14000a99e  mov     [rsp+80h+var_28], rbx
0x14000a9a3  lea     rcx, [rbp+Handle]
0x14000a9a7  mov     [rsp+80h+var_30], ebx
0x14000a9ab  mov     r9d, 1F01FFh
0x14000a9b1  mov     [rsp+80h+var_38], rbx
0x14000a9b6  mov     rdx, r12
0x14000a9b9  mov     [rsp+80h+var_40], 62h ; 'b'
0x14000a9c1  mov     [rsp+80h+var_48], 3
0x14000a9c9  mov     [rsp+80h+var_50], 7
0x14000a9d1  mov     dword ptr [rsp+80h+HandleInformation], 80h
0x14000a9d9  mov     [rsp+80h+Object], rbx
0x14000a9de  call    CscStorepLowIoCreateFilePoster
0x14000a9e3  mov     ebx, eax
0x14000a9e5  test    eax, eax
0x14000a9e7  jns     short loc_14000A9F1
0x14000a9e9  mov     r14d, 589h
0x14000a9ef  jmp     short loc_14000AA3D
0x14000a9f1  mov     rcx, [rbp+Handle]; Handle
0x14000a9f5  lea     rax, [rbp+arg_18]
0x14000a9f9  mov     [rsp+80h+HandleInformation], r14; HandleInformation
0x14000a9fe  xor     r9d, r9d; AccessMode
0x14000aa01  xor     r8d, r8d; ObjectType
0x14000aa04  mov     [rsp+80h+Object], rax; Object
0x14000aa09  mov     edx, 1F01FFh; DesiredAccess
0x14000aa0e  call    cs:__imp_ObReferenceObjectByHandle
0x14000aa15  nop     dword ptr [rax+rax+00h]
0x14000aa1a  mov     ebx, eax
0x14000aa1c  test    eax, eax
0x14000aa1e  jns     short loc_14000AA28
0x14000aa20  mov     r14d, 596h
0x14000aa26  jmp     short loc_14000AA3D
0x14000aa28  mov     rcx, [rbp+Handle]
0x14000aa2c  call    CscStorepLowIoDisableImplicitTimeUpdates
0x14000aa31  mov     ebx, eax
0x14000aa33  test    eax, eax
0x14000aa35  jns     short loc_14000AA7F
0x14000aa37  mov     r14d, 59Dh
0x14000aa3d  mov     rcx, [rbp+Handle]; Handle
0x14000aa41  test    rcx, rcx
0x14000aa44  jz      short loc_14000AA52
0x14000aa46  call    cs:__imp_ZwClose
0x14000aa4d  nop     dword ptr [rax+rax+00h]
0x14000aa52  mov     rcx, [rbp+arg_18]; Object
0x14000aa56  test    rcx, rcx
0x14000aa59  jz      short loc_14000AA67
0x14000aa5b  call    cs:__imp_ObfDereferenceObject
0x14000aa62  nop     dword ptr [rax+rax+00h]
0x14000aa67  mov     eax, 1
0x14000aa6c  cmp     ax, r15w
0x14000aa70  jnz     short loc_14000AA8F
0x14000aa72  lea     edx, [rax+1]
0x14000aa75  mov     rcx, rsi
0x14000aa78  call    CscBitmappSetDiffTransferType
0x14000aa7d  jmp     short loc_14000AA8F
0x14000aa7f  mov     rax, [rbp+arg_18]
0x14000aa83  mov     [rdi+20h], rax
0x14000aa87  mov     rax, [rbp+Handle]
0x14000aa8b  mov     [rdi+18h], rax
0x14000aa8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa96  lea     rax, WPP_GLOBAL_Control
0x14000aa9d  cmp     rcx, rax
0x14000aaa0  jz      short loc_14000AAC8
0x14000aaa2  test    dword ptr [rcx+2Ch], 40000h
0x14000aaa9  jz      short loc_14000AAC8
0x14000aaab  mov     rcx, [rcx+18h]
0x14000aaaf  lea     r8, WPP_e97202f6601e396a8249708b9471af4e_Traceguids
0x14000aab6  mov     edx, 1Dh
0x14000aabb  mov     dword ptr [rsp+80h+Object], r14d
0x14000aac0  mov     r9d, ebx
0x14000aac3  call    WPP_SF_Dd
0x14000aac8  lea     r11, [rsp+80h+var_s0]
0x14000aad0  mov     eax, ebx
0x14000aad2  mov     rbx, [r11+30h]
0x14000aad6  mov     rsi, [r11+38h]
0x14000aada  mov     rsp, r11
0x14000aadd  pop     r15
0x14000aadf  pop     r14
0x14000aae1  pop     r12
0x14000aae3  pop     rdi
0x14000aae4  pop     rbp
0x14000aae5  retn
```

# MountMgrKeepLinksWhenOffline

- ea: `0x14000c9f8`
- end: `0x14000caf9`
- name: `MountMgrKeepLinksWhenOffline`
- size: `257`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x14000c9f8`
- `0x140010970`

## pseudocode

```c
__int64 __fastcall MountMgrKeepLinksWhenOffline(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v4; // r8
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  _WORD *v7; // r9
  int v8; // ecx
  int DeviceInfo; // ebx
  __int64 v11; // r8
  __int128 v12; // [rsp+20h] [rbp-18h] BYREF
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  v12 = 0;
  v13 = 0;
  v4 = *(unsigned int *)(v2 + 16);
  if ( (unsigned int)v4 < 4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v6 = 289;
LABEL_9:
    WPP_SF_L(v5->AttachedDevice, v6, v4, 3221225485LL);
    return 3221225485LL;
  }
  v7 = *(_WORD **)(a2 + 24);
  v8 = (unsigned __int16)*v7;
  if ( (unsigned int)v4 < v8 + 2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v6 = 290;
    goto LABEL_9;
  }
  WORD1(v12) = *v7;
  LOWORD(v12) = v8;
  *((_QWORD *)&v12 + 1) = v7 + 1;
  DeviceInfo = FindDeviceInfo(a1, &v12, v4, &v13);
  if ( DeviceInfo >= 0 )
  {
    *(_BYTE *)(v13 + 130) = 1;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 291, v11, (unsigned int)DeviceInfo);
    return (unsigned int)DeviceInfo;
  }
}

```

## disassembly

```asm
0x14000c9f8  push    rbx
0x14000c9fa  sub     rsp, 30h
0x14000c9fe  mov     rax, [rdx+0B8h]
0x14000ca05  xorps   xmm0, xmm0
0x14000ca08  movups  [rsp+38h+var_18], xmm0
0x14000ca0d  mov     r10, rcx
0x14000ca10  mov     [rsp+38h+arg_8], 0
0x14000ca19  mov     r8d, [rax+10h]
0x14000ca1d  cmp     r8d, 4
0x14000ca21  jnb     short loc_14000CA44
0x14000ca23  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ca2a  lea     rax, WPP_GLOBAL_Control
0x14000ca31  cmp     rcx, rax
0x14000ca34  jz      short loc_14000CA82
0x14000ca36  mov     eax, [rcx+2Ch]
0x14000ca39  test    al, 1
0x14000ca3b  jz      short loc_14000CA82
0x14000ca3d  mov     edx, 121h
0x14000ca42  jmp     short loc_14000CA73
0x14000ca44  mov     r9, [rdx+18h]
0x14000ca48  movzx   ecx, word ptr [r9]
0x14000ca4c  lea     eax, [rcx+2]
0x14000ca4f  cmp     r8d, eax
0x14000ca52  jnb     short loc_14000CA89
0x14000ca54  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ca5b  lea     rax, WPP_GLOBAL_Control
0x14000ca62  cmp     rcx, rax
0x14000ca65  jz      short loc_14000CA82
0x14000ca67  mov     eax, [rcx+2Ch]
0x14000ca6a  test    al, 1
0x14000ca6c  jz      short loc_14000CA82
0x14000ca6e  mov     edx, 122h
0x14000ca73  mov     rcx, [rcx+18h]
0x14000ca77  mov     r9d, 0C000000Dh
0x14000ca7d  call    WPP_SF_L
0x14000ca82  mov     eax, 0C000000Dh
0x14000ca87  jmp     short loc_14000CAF2
0x14000ca89  lea     rax, [r9+2]
0x14000ca8d  mov     word ptr [rsp+38h+var_18+2], cx
0x14000ca92  mov     word ptr [rsp+38h+var_18], cx
0x14000ca97  lea     r9, [rsp+38h+arg_8]
0x14000ca9c  mov     rcx, r10
0x14000ca9f  mov     qword ptr [rsp+38h+var_18+8], rax
0x14000caa4  lea     rdx, [rsp+38h+var_18]
0x14000caa9  call    FindDeviceInfo
0x14000caae  mov     ebx, eax
0x14000cab0  test    eax, eax
0x14000cab2  jns     short loc_14000CAE4
0x14000cab4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cabb  lea     rax, WPP_GLOBAL_Control
0x14000cac2  cmp     rcx, rax
0x14000cac5  jz      short loc_14000CAE0
0x14000cac7  mov     edx, [rcx+2Ch]
0x14000caca  test    dl, 1
0x14000cacd  jz      short loc_14000CAE0
0x14000cacf  mov     rcx, [rcx+18h]
0x14000cad3  mov     edx, 123h
0x14000cad8  mov     r9d, ebx
0x14000cadb  call    WPP_SF_L
0x14000cae0  mov     eax, ebx
0x14000cae2  jmp     short loc_14000CAF2
0x14000cae4  mov     rax, [rsp+38h+arg_8]
0x14000cae9  mov     byte ptr [rax+82h], 1
0x14000caf0  xor     eax, eax
0x14000caf2  add     rsp, 30h
0x14000caf6  pop     rbx
0x14000caf7  retn
```

# MountMgrPrepareVolumeDelete

- ea: `0x14000cb00`
- end: `0x14000cc29`
- name: `MountMgrPrepareVolumeDelete`
- size: `297`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x14000cb00`
- `0x140010970`

## pseudocode

```c
__int64 __fastcall MountMgrPrepareVolumeDelete(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // r8
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  _WORD *v7; // r9
  int v8; // ecx
  int DeviceInfo; // edi
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
    v6 = 222;
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
    v6 = 223;
    goto LABEL_9;
  }
  WORD1(v12) = *v7;
  LOWORD(v12) = v8;
  *((_QWORD *)&v12 + 1) = v7 + 1;
  DeviceInfo = FindDeviceInfo(a1, &v12, v4, &v13);
  if ( DeviceInfo >= 0 )
  {
    if ( *(_DWORD *)(v2 + 24) == 7192652 )
    {
      *(_BYTE *)(v13 + 135) = 1;
    }
    else if ( *(_DWORD *)(v2 + 24) == 7192656 )
    {
      *(_BYTE *)(v13 + 135) = 0;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 224, v11, (unsigned int)DeviceInfo);
  }
  return (unsigned int)DeviceInfo;
}

```

## disassembly

```asm
0x14000cb00  mov     [rsp+arg_0], rbx
0x14000cb05  push    rdi
0x14000cb06  sub     rsp, 30h
0x14000cb0a  mov     rbx, [rdx+0B8h]
0x14000cb11  xorps   xmm0, xmm0
0x14000cb14  movups  [rsp+38h+var_18], xmm0
0x14000cb19  mov     r10, rcx
0x14000cb1c  mov     [rsp+38h+arg_8], 0
0x14000cb25  mov     r8d, [rbx+10h]
0x14000cb29  cmp     r8d, 4
0x14000cb2d  jnb     short loc_14000CB50
0x14000cb2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb36  lea     rax, WPP_GLOBAL_Control
0x14000cb3d  cmp     rcx, rax
0x14000cb40  jz      short loc_14000CB8E
0x14000cb42  mov     eax, [rcx+2Ch]
0x14000cb45  test    al, 1
0x14000cb47  jz      short loc_14000CB8E
0x14000cb49  mov     edx, 0DEh
0x14000cb4e  jmp     short loc_14000CB7F
0x14000cb50  mov     r9, [rdx+18h]
0x14000cb54  movzx   ecx, word ptr [r9]
0x14000cb58  lea     eax, [rcx+2]
0x14000cb5b  cmp     r8d, eax
0x14000cb5e  jnb     short loc_14000CB98
0x14000cb60  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb67  lea     rax, WPP_GLOBAL_Control
0x14000cb6e  cmp     rcx, rax
0x14000cb71  jz      short loc_14000CB8E
0x14000cb73  mov     eax, [rcx+2Ch]
0x14000cb76  test    al, 1
0x14000cb78  jz      short loc_14000CB8E
0x14000cb7a  mov     edx, 0DFh
0x14000cb7f  mov     rcx, [rcx+18h]
0x14000cb83  mov     r9d, 0C000000Dh
0x14000cb89  call    WPP_SF_L
0x14000cb8e  mov     eax, 0C000000Dh
0x14000cb93  jmp     loc_14000CC1D
0x14000cb98  lea     rax, [r9+2]
0x14000cb9c  mov     word ptr [rsp+38h+var_18+2], cx
0x14000cba1  mov     word ptr [rsp+38h+var_18], cx
0x14000cba6  lea     r9, [rsp+38h+arg_8]
0x14000cbab  mov     rcx, r10
0x14000cbae  mov     qword ptr [rsp+38h+var_18+8], rax
0x14000cbb3  lea     rdx, [rsp+38h+var_18]
0x14000cbb8  call    FindDeviceInfo
0x14000cbbd  mov     edi, eax
0x14000cbbf  test    eax, eax
0x14000cbc1  jns     short loc_14000CBF1
0x14000cbc3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cbca  lea     rax, WPP_GLOBAL_Control
0x14000cbd1  cmp     rcx, rax
0x14000cbd4  jz      short loc_14000CC1B
0x14000cbd6  mov     edx, [rcx+2Ch]
0x14000cbd9  test    dl, 1
0x14000cbdc  jz      short loc_14000CC1B
0x14000cbde  mov     rcx, [rcx+18h]
0x14000cbe2  mov     edx, 0E0h
0x14000cbe7  mov     r9d, edi
0x14000cbea  call    WPP_SF_L
0x14000cbef  jmp     short loc_14000CC1B
0x14000cbf1  mov     ecx, [rbx+18h]
0x14000cbf4  sub     ecx, 6DC04Ch
0x14000cbfa  jz      short loc_14000CC0F
0x14000cbfc  cmp     ecx, 4
0x14000cbff  jnz     short loc_14000CC1B
0x14000cc01  mov     rax, [rsp+38h+arg_8]
0x14000cc06  mov     byte ptr [rax+87h], 0
0x14000cc0d  jmp     short loc_14000CC1B
0x14000cc0f  mov     rax, [rsp+38h+arg_8]
0x14000cc14  mov     byte ptr [rax+87h], 1
0x14000cc1b  mov     eax, edi
0x14000cc1d  mov     rbx, [rsp+38h+arg_0]
0x14000cc22  add     rsp, 30h
0x14000cc26  pop     rdi
0x14000cc27  retn
```

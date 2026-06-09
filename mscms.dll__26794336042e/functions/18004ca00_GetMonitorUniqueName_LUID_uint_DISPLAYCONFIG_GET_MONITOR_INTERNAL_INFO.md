# GetMonitorUniqueName(_LUID,uint,_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO &)

- ea: `0x18004ca00`
- end: `0x18004cbbb`
- name: `?GetMonitorUniqueName@@YAJU_LUID@@IAEAU_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO@@@Z`
- size: `443`
- prototype: `int(struct _LUID, unsigned int, struct _DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000d950`
- `0x18000dc90`

## callees

- `0x18002e614`
- `0x18002ea60`
- `0x18004ca00`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x18004caf7`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x18004caf7`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18004cb7c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18004cb7c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18004ca3c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18004ca3c`

## pseudocode

```c
__int64 __fastcall GetMonitorUniqueName(struct _LUID a1, int a2, struct _LUID *a3)
{
  DISPLAYCONFIG_MODE_INFO *modeInfoArray; // rbp
  DISPLAYCONFIG_PATH_INFO *v7; // rsi
  LONG DisplayConfigBufferSizes; // eax
  signed int v9; // edi
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rax
  DISPLAYCONFIG_PATH_INFO *v12; // rax
  LONG v13; // eax
  int v14; // r10d
  int v15; // edx
  __int64 v16; // rcx
  LONG DeviceInfo; // eax
  UINT32 numModeInfoArrayElements[14]; // [rsp+30h] [rbp-38h] BYREF
  LONG HighPart; // [rsp+74h] [rbp+Ch]
  UINT32 numPathArrayElements; // [rsp+88h] [rbp+20h] BYREF

  HighPart = a1.HighPart;
  numPathArrayElements = 0;
  numModeInfoArrayElements[0] = 0;
  modeInfoArray = 0;
  v7 = 0;
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, numModeInfoArrayElements);
  v9 = DisplayConfigBufferSizes;
  if ( DisplayConfigBufferSizes > 0 )
    v9 = (unsigned __int16)DisplayConfigBufferSizes | 0x80070000;
  if ( v9 >= 0 )
  {
    if ( !numPathArrayElements || !numModeInfoArrayElements[0] )
      goto LABEL_25;
    v10 = (unsigned __int64)numModeInfoArrayElements[0] << 6;
    if ( !is_mul_ok(numModeInfoArrayElements[0], 0x40u) )
      v10 = -1;
    modeInfoArray = (DISPLAYCONFIG_MODE_INFO *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
    if ( !modeInfoArray )
      goto LABEL_9;
    v11 = 72LL * numPathArrayElements;
    if ( !is_mul_ok(numPathArrayElements, 0x48u) )
      v11 = -1;
    v12 = (DISPLAYCONFIG_PATH_INFO *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v12;
    if ( !v12 )
    {
LABEL_9:
      v9 = -2147024882;
      goto LABEL_26;
    }
    v13 = QueryDisplayConfig(2u, &numPathArrayElements, v12, numModeInfoArrayElements, modeInfoArray, 0);
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    if ( v9 >= 0 )
    {
      v14 = 0;
      v15 = 0;
      v16 = 0;
      if ( numPathArrayElements )
      {
        do
        {
          if ( v7[v16].targetInfo.adapterId.LowPart == a1.LowPart
            && v7[v16].targetInfo.adapterId.HighPart == HighPart
            && v7[v16].sourceInfo.id == a2 )
          {
            v14 = v16;
            ++v15;
          }
          v16 = (unsigned int)(v16 + 1);
        }
        while ( (unsigned int)v16 < numPathArrayElements );
        if ( v15 == 1 )
        {
          a3->LowPart = -7;
          a3->HighPart = 944;
          a3[1] = a1;
          a3[2].LowPart = v7[v14].targetInfo.id;
          DeviceInfo = DisplayConfigGetDeviceInfo((DISPLAYCONFIG_DEVICE_INFO_HEADER *)a3);
          v9 = DeviceInfo;
          if ( DeviceInfo > 0 )
            v9 = (unsigned __int16)DeviceInfo | 0x80070000;
          goto LABEL_26;
        }
      }
LABEL_25:
      v9 = -2147467260;
    }
  }
LABEL_26:
  operator delete(v7);
  operator delete(modeInfoArray);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004ca00  mov     rax, rsp
0x18004ca03  mov     [rax+10h], rbx
0x18004ca07  mov     [rax+8], rcx
0x18004ca0b  push    rbp
0x18004ca0c  push    rsi
0x18004ca0d  push    rdi
0x18004ca0e  push    r14
0x18004ca10  push    r15
0x18004ca12  sub     rsp, 40h
0x18004ca16  mov     r14, r8
0x18004ca19  mov     dword ptr [rax+20h], 0
0x18004ca20  mov     r15d, edx
0x18004ca23  mov     dword ptr [rax-38h], 0
0x18004ca2a  mov     rbx, rcx
0x18004ca2d  lea     r8, [rax-38h]; numModeInfoArrayElements
0x18004ca31  xor     ebp, ebp
0x18004ca33  lea     rdx, [rax+20h]; numPathArrayElements
0x18004ca37  xor     esi, esi
0x18004ca39  lea     ecx, [rbp+2]; flags
0x18004ca3c  call    cs:__imp_GetDisplayConfigBufferSizes
0x18004ca42  mov     edi, eax
0x18004ca44  test    eax, eax
0x18004ca46  jle     short loc_18004CA51
0x18004ca48  movzx   edi, ax
0x18004ca4b  or      edi, 80070000h
0x18004ca51  test    edi, edi
0x18004ca53  js      loc_18004CB98
0x18004ca59  cmp     [rsp+68h+numPathArrayElements], 1
0x18004ca61  jb      loc_18004CB93
0x18004ca67  cmp     [rsp+68h+numModeInfoArrayElements], 1
0x18004ca6c  jb      loc_18004CB93
0x18004ca72  mov     ecx, [rsp+68h+numModeInfoArrayElements]
0x18004ca76  mov     eax, 40h ; '@'
0x18004ca7b  mul     rcx
0x18004ca7e  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18004ca85  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004ca8c  cmovb   rax, rdi
0x18004ca90  mov     rcx, rax; unsigned __int64
0x18004ca93  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004ca98  mov     rbp, rax
0x18004ca9b  test    rax, rax
0x18004ca9e  jnz     short loc_18004CAAA
0x18004caa0  mov     edi, 8007000Eh
0x18004caa5  jmp     loc_18004CB98
0x18004caaa  mov     ecx, [rsp+68h+numPathArrayElements]
0x18004cab1  mov     eax, 48h ; 'H'
0x18004cab6  mul     rcx
0x18004cab9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004cac0  cmovb   rax, rdi
0x18004cac4  mov     rcx, rax; unsigned __int64
0x18004cac7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004cacc  mov     rsi, rax
0x18004cacf  test    rax, rax
0x18004cad2  jz      short loc_18004CAA0
0x18004cad4  mov     [rsp+68h+currentTopologyId], 0; currentTopologyId
0x18004cadd  lea     r9, [rsp+68h+numModeInfoArrayElements]; numModeInfoArrayElements
0x18004cae2  mov     r8, rax; pathArray
0x18004cae5  mov     [rsp+68h+modeInfoArray], rbp; modeInfoArray
0x18004caea  lea     rdx, [rsp+68h+numPathArrayElements]; numPathArrayElements
0x18004caf2  mov     ecx, 2; flags
0x18004caf7  call    cs:__imp_QueryDisplayConfig
0x18004cafd  mov     edi, eax
0x18004caff  test    eax, eax
0x18004cb01  jle     short loc_18004CB0C
0x18004cb03  movzx   edi, ax
0x18004cb06  or      edi, 80070000h
0x18004cb0c  test    edi, edi
0x18004cb0e  js      loc_18004CB98
0x18004cb14  mov     r9d, [rsp+68h+numPathArrayElements]
0x18004cb1c  xor     r10d, r10d
0x18004cb1f  xor     edx, edx
0x18004cb21  xor     ecx, ecx
0x18004cb23  test    r9d, r9d
0x18004cb26  jz      short loc_18004CB93
0x18004cb28  mov     r11d, [rsp+68h+arg_4]
0x18004cb2d  lea     r8, [rcx+rcx*8]
0x18004cb31  cmp     [rsi+r8*8+14h], ebx
0x18004cb36  jnz     short loc_18004CB4B
0x18004cb38  cmp     [rsi+r8*8+18h], r11d
0x18004cb3d  jnz     short loc_18004CB4B
0x18004cb3f  cmp     [rsi+r8*8+8], r15d
0x18004cb44  jnz     short loc_18004CB4B
0x18004cb46  mov     r10d, ecx
0x18004cb49  inc     edx
0x18004cb4b  inc     ecx
0x18004cb4d  cmp     ecx, r9d
0x18004cb50  jb      short loc_18004CB2D
0x18004cb52  cmp     edx, 1
0x18004cb55  jnz     short loc_18004CB93
0x18004cb57  mov     eax, r10d
0x18004cb5a  mov     dword ptr [r14], 0FFFFFFF9h
0x18004cb61  mov     dword ptr [r14+4], 3B0h
0x18004cb69  mov     [r14+8], rbx
0x18004cb6d  lea     rcx, [rax+rax*8]
0x18004cb71  mov     eax, [rsi+rcx*8+1Ch]
0x18004cb75  mov     rcx, r14; requestPacket
0x18004cb78  mov     [r14+10h], eax
0x18004cb7c  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18004cb82  mov     edi, eax
0x18004cb84  test    eax, eax
0x18004cb86  jle     short loc_18004CB98
0x18004cb88  movzx   edi, ax
0x18004cb8b  or      edi, 80070000h
0x18004cb91  jmp     short loc_18004CB98
0x18004cb93  mov     edi, 80004004h
0x18004cb98  mov     rcx, rsi; void *
0x18004cb9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004cba0  mov     rcx, rbp; void *
0x18004cba3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004cba8  mov     rbx, [rsp+68h+arg_8]
0x18004cbad  mov     eax, edi
0x18004cbaf  add     rsp, 40h
0x18004cbb3  pop     r15
0x18004cbb5  pop     r14
0x18004cbb7  pop     rdi
0x18004cbb8  pop     rsi
0x18004cbb9  pop     rbp
0x18004cbba  retn
```

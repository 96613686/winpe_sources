# DiscpGetTargetMappingsForMPIO

- ea: `0x18001b0b0`
- end: `0x18001b428`
- name: `DiscpGetTargetMappingsForMPIO`
- size: `888`
- prototype: `__int64 __fastcall(unsigned int *, __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ae70`
- `0x180017274`

## callees

- `0x18001b0b0`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x18001b3b9`
- `ISCSIUM!DiscpAllocMemory` at `0x18001b3b9`
- `ISCSIUM!DiscpCopyString` at `0x18001b1bc`
- `ISCSIUM!DiscpCopyString` at `0x18001b1bc`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b22b`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b3e2`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b3ec`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b3f6`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b400`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b22b`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b3e2`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b3ec`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b3f6`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b400`
- `ISCSIUM!DiscpParseAllData` at `0x18001b155`
- `ISCSIUM!DiscpParseAllData` at `0x18001b155`
- `ISCSIUM!DiscpGetStringFromDataBlock` at `0x18001b27e`
- `ISCSIUM!DiscpGetStringFromDataBlock` at `0x18001b27e`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001b2a7`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001b2a7`
- `ISCSIUM!DiscpQueryAllData` at `0x18001b124`
- `ISCSIUM!DiscpQueryAllData` at `0x18001b124`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18001b215`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18001b215`

## pseudocode

```c
__int64 __fastcall DiscpGetTargetMappingsForMPIO(unsigned int *a1, __int64 *a2)
{
  CONFIGRET StringFromDataBlock; // ebx
  __int64 v3; // rdi
  unsigned int v4; // r14d
  unsigned int v5; // r15d
  WCHAR *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  int v9; // r8d
  unsigned __int8 *v10; // rdx
  unsigned int v11; // ecx
  unsigned int v12; // r12d
  int v13; // esi
  unsigned int v14; // eax
  int v15; // r13d
  unsigned __int8 *v16; // rcx
  int v17; // r11d
  int v18; // r10d
  int v19; // r9d
  __int64 v20; // rcx
  unsigned int v22; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int8 *v23; // [rsp+38h] [rbp-41h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-35h] BYREF
  DEVNODE pdnDevInst; // [rsp+48h] [rbp-31h] BYREF
  DEVINSTID_W pDeviceID; // [rsp+50h] [rbp-29h] BYREF
  int v28; // [rsp+58h] [rbp-21h] BYREF
  __int64 v29; // [rsp+60h] [rbp-19h] BYREF
  __int64 v30; // [rsp+68h] [rbp-11h] BYREF
  __int64 v31; // [rsp+70h] [rbp-9h] BYREF
  __int64 v32; // [rsp+78h] [rbp-1h] BYREF
  __int64 v33; // [rsp+80h] [rbp+7h] BYREF
  __int64 v34[9]; // [rsp+88h] [rbp+Fh] BYREF
  unsigned __int8 v37; // [rsp+F0h] [rbp+77h]
  unsigned int v38; // [rsp+F8h] [rbp+7Fh] BYREF

  *a1 = 0;
  *a2 = 0;
  v32 = 0;
  v25 = 0;
  v29 = 0;
  v30 = 0;
  v24 = 0;
  v31 = 0;
  v23 = 0;
  v38 = 0;
  pDeviceID = 0;
  pdnDevInst = 0;
  v28 = 0;
  v22 = 0;
  v34[0] = 0;
  v33 = 0;
  StringFromDataBlock = DiscpQueryAllData(MPIO_GET_DESCRIPTOR_GUID, 0, &v32, &v25);
  if ( StringFromDataBlock )
  {
    if ( StringFromDataBlock == 4200 )
      return 0;
    return StringFromDataBlock;
  }
  StringFromDataBlock = DiscpParseAllData(v32, v25, &v24, &v29, &v30, &v31);
  if ( StringFromDataBlock )
    goto LABEL_40;
  v3 = 0;
  while ( 1 )
  {
    v4 = 0;
    v5 = 0;
    if ( v24 )
      break;
LABEL_33:
    StringFromDataBlock = 0;
LABEL_34:
    if ( v3 )
    {
      *a1 = v4;
      *a2 = v3;
      goto LABEL_39;
    }
    if ( !v4 )
      goto LABEL_39;
    v3 = DiscpAllocMemory(28 * v4);
    if ( !v3 )
    {
      StringFromDataBlock = 8;
      goto LABEL_39;
    }
  }
  while ( 1 )
  {
    if ( v3 )
    {
      pDeviceID = 0;
      v22 = 2 * **(unsigned __int16 **)(v29 + 8LL * v5) + 2;
      v33 = *(_QWORD *)(v29 + 8LL * v5);
      StringFromDataBlock = DiscpCopyString(&pDeviceID, &v28, &v33, v22, &v22);
      if ( StringFromDataBlock )
        goto LABEL_32;
      v6 = pDeviceID;
      v7 = -1;
      do
        ++v7;
      while ( pDeviceID[v7] );
      v22 = v7;
      if ( (_DWORD)v7 )
      {
        v8 = (unsigned int)v7;
        v9 = v7;
        while ( pDeviceID[v8] != 95 )
        {
          v8 = (unsigned int)(v7 - 1);
          v22 = v8;
          LODWORD(v7) = v7 - 1;
          v9 = v8;
          if ( !(_DWORD)v8 )
            goto LABEL_15;
        }
        pDeviceID[v9] = 0;
        v6 = pDeviceID;
      }
LABEL_15:
      StringFromDataBlock = CM_Locate_DevNodeW(&pdnDevInst, v6, 0);
      if ( StringFromDataBlock )
        StringFromDataBlock = 87;
      DiscpFreeMemory(pDeviceID);
    }
    if ( !StringFromDataBlock )
    {
      StringFromDataBlock = -268500967;
      v10 = *(unsigned __int8 **)(v30 + 8LL * v5);
      v23 = v10;
      v11 = *(_DWORD *)(v31 + 4LL * v5);
      v38 = v11;
      if ( v11 < 4 )
        goto LABEL_39;
      v12 = *(_DWORD *)v10;
      v23 = v10 + 4;
      v38 = v11 - 4;
      StringFromDataBlock = DiscpGetStringFromDataBlock(v34, &v22, &v23, &v38);
      if ( StringFromDataBlock )
        goto LABEL_39;
      v13 = 0;
      if ( v12 )
        break;
    }
LABEL_32:
    if ( ++v5 >= v24 )
      goto LABEL_33;
  }
  while ( 1 )
  {
    StringFromDataBlock = DiscpPadDataBlock(8, &v23, &v38);
    if ( StringFromDataBlock )
      break;
    v14 = v38;
    if ( !v38 )
      goto LABEL_34;
    v15 = *v23;
    v16 = ++v23;
    --v38;
    if ( v14 == 1 )
      goto LABEL_34;
    v37 = *v16;
    v23 = v16 + 1;
    v38 = v14 - 2;
    if ( v14 == 2 )
      goto LABEL_34;
    v17 = v16[1];
    v38 = v14 - 3;
    v23 = v16 + 2;
    if ( v14 == 3 )
      goto LABEL_34;
    v18 = v16[2];
    v38 = v14 - 4;
    v23 = v16 + 3;
    if ( v14 - 4 < 4 )
      goto LABEL_34;
    v19 = *(_DWORD *)(v16 + 3);
    v23 = v16 + 7;
    v38 = v14 - 8;
    if ( v14 - 8 < 0x34 )
      goto LABEL_34;
    v23 = v16 + 59;
    v38 = v14 - 60;
    if ( v3 )
    {
      v20 = 28LL * v4;
      *(_DWORD *)(v20 + v3) = pdnDevInst;
      *(_DWORD *)(v20 + v3 + 8) = v37;
      *(_DWORD *)(v20 + v3 + 4) = v15;
      *(_DWORD *)(v20 + v3 + 12) = v17;
      *(_DWORD *)(v20 + v3 + 16) = v18;
      *(_DWORD *)(v20 + v3 + 24) = v19;
    }
    ++v4;
    if ( ++v13 >= v12 )
      goto LABEL_32;
  }
LABEL_39:
  DiscpFreeMemory(v29);
  DiscpFreeMemory(v30);
  DiscpFreeMemory(v31);
LABEL_40:
  DiscpFreeMemory(v32);
  return StringFromDataBlock;
}

```

## disassembly

```asm
0x18001b0b0  mov     [rsp-8+arg_8], rdx
0x18001b0b5  mov     [rsp-8+arg_0], rcx
0x18001b0ba  push    rbp
0x18001b0bb  push    rbx
0x18001b0bc  push    rsi
0x18001b0bd  push    rdi
0x18001b0be  push    r12
0x18001b0c0  push    r13
0x18001b0c2  push    r14
0x18001b0c4  push    r15
0x18001b0c6  lea     rbp, [rsp-1Fh]
0x18001b0cb  sub     rsp, 98h
0x18001b0d2  xor     r13d, r13d
0x18001b0d5  lea     r9, [rbp+57h+var_8C]
0x18001b0d9  mov     [rcx], r13d
0x18001b0dc  lea     r8, [rbp+57h+var_58]
0x18001b0e0  mov     [rdx], r13
0x18001b0e3  lea     rcx, MPIO_GET_DESCRIPTOR_GUID
0x18001b0ea  xor     edx, edx
0x18001b0ec  mov     [rbp+57h+var_58], r13
0x18001b0f0  mov     [rbp+57h+var_8C], r13d
0x18001b0f4  mov     [rbp+57h+var_70], r13
0x18001b0f8  mov     [rbp+57h+var_68], r13
0x18001b0fc  mov     [rbp+57h+var_90], r13d
0x18001b100  mov     [rbp+57h+var_60], r13
0x18001b104  mov     [rbp+57h+var_98], r13
0x18001b108  mov     [rbp+57h+arg_18], r13d
0x18001b10c  mov     [rbp+57h+pDeviceID], r13
0x18001b110  mov     [rbp+57h+pdnDevInst], r13d
0x18001b114  mov     [rbp+57h+var_78], r13d
0x18001b118  mov     [rbp+57h+var_A0], r13d
0x18001b11c  mov     [rbp+57h+var_48], r13
0x18001b120  mov     [rbp+57h+var_50], r13
0x18001b124  call    cs:__imp_DiscpQueryAllData
0x18001b12a  mov     ebx, eax
0x18001b12c  test    eax, eax
0x18001b12e  jnz     loc_18001B408
0x18001b134  mov     edx, [rbp+57h+var_8C]
0x18001b137  lea     rax, [rbp+57h+var_60]
0x18001b13b  mov     rcx, [rbp+57h+var_58]
0x18001b13f  lea     r9, [rbp+57h+var_70]
0x18001b143  mov     [rsp+0D0h+var_A8], rax
0x18001b148  lea     r8, [rbp+57h+var_90]
0x18001b14c  lea     rax, [rbp+57h+var_68]
0x18001b150  mov     [rsp+0D0h+var_B0], rax
0x18001b155  call    cs:__imp_DiscpParseAllData
0x18001b15b  mov     ebx, eax
0x18001b15d  test    eax, eax
0x18001b15f  jnz     loc_18001B3FC
0x18001b165  mov     edi, r13d
0x18001b168  mov     r14d, r13d
0x18001b16b  mov     r15d, r13d
0x18001b16e  cmp     [rbp+57h+var_90], r13d
0x18001b172  jbe     loc_18001B3A3
0x18001b178  mov     esi, r15d
0x18001b17b  test    rdi, rdi
0x18001b17e  jz      loc_18001B231
0x18001b184  mov     rdx, [rbp+57h+var_70]
0x18001b188  lea     r8, [rbp+57h+var_50]
0x18001b18c  mov     [rbp+57h+pDeviceID], r13
0x18001b190  mov     rax, [rdx+rsi*8]
0x18001b194  movzx   ecx, word ptr [rax]
0x18001b197  lea     r9d, ds:2[rcx*2]
0x18001b19f  mov     [rbp+57h+var_A0], r9d
0x18001b1a3  lea     rcx, [rbp+57h+pDeviceID]
0x18001b1a7  mov     rax, [rdx+rsi*8]
0x18001b1ab  lea     rdx, [rbp+57h+var_78]
0x18001b1af  mov     [rbp+57h+var_50], rax
0x18001b1b3  lea     rax, [rbp+57h+var_A0]
0x18001b1b7  mov     [rsp+0D0h+var_B0], rax
0x18001b1bc  call    cs:__imp_DiscpCopyString
0x18001b1c2  mov     ebx, eax
0x18001b1c4  test    eax, eax
0x18001b1c6  jnz     loc_18001B396
0x18001b1cc  mov     rdx, [rbp+57h+pDeviceID]
0x18001b1d0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001b1d4  inc     rcx
0x18001b1d7  cmp     [rdx+rcx*2], r13w
0x18001b1dc  jnz     short loc_18001B1D4
0x18001b1de  mov     [rbp+57h+var_A0], ecx
0x18001b1e1  test    ecx, ecx
0x18001b1e3  jz      short loc_18001B20E
0x18001b1e5  mov     eax, ecx
0x18001b1e7  mov     r8d, ecx
0x18001b1ea  cmp     word ptr [rdx+rax*2], 5Fh ; '_'
0x18001b1ef  mov     r9d, r8d
0x18001b1f2  jz      short loc_18001B205
0x18001b1f4  lea     eax, [rcx-1]
0x18001b1f7  mov     [rbp+57h+var_A0], eax
0x18001b1fa  mov     ecx, eax
0x18001b1fc  mov     r8d, eax
0x18001b1ff  test    eax, eax
0x18001b201  jnz     short loc_18001B1EA
0x18001b203  jmp     short loc_18001B20E
0x18001b205  mov     [rdx+r9*2], r13w
0x18001b20a  mov     rdx, [rbp+57h+pDeviceID]; pDeviceID
0x18001b20e  xor     r8d, r8d; ulFlags
0x18001b211  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x18001b215  call    cs:__imp_CM_Locate_DevNodeW
0x18001b21b  mov     rcx, [rbp+57h+pDeviceID]
0x18001b21f  mov     ebx, eax
0x18001b221  test    ebx, ebx
0x18001b223  mov     eax, 57h ; 'W'
0x18001b228  cmovnz  ebx, eax
0x18001b22b  call    cs:__imp_DiscpFreeMemory
0x18001b231  test    ebx, ebx
0x18001b233  jnz     loc_18001B396
0x18001b239  mov     rax, [rbp+57h+var_68]
0x18001b23d  mov     ebx, 0EFFF0019h
0x18001b242  mov     rdx, [rax+rsi*8]
0x18001b246  mov     rax, [rbp+57h+var_60]
0x18001b24a  mov     [rbp+57h+var_98], rdx
0x18001b24e  mov     ecx, [rax+rsi*4]
0x18001b251  mov     [rbp+57h+arg_18], ecx
0x18001b254  cmp     ecx, 4
0x18001b257  jb      loc_18001B3DE
0x18001b25d  mov     r12d, [rdx]
0x18001b260  lea     rax, [rdx+4]
0x18001b264  mov     [rbp+57h+var_98], rax
0x18001b268  lea     r9, [rbp+57h+arg_18]
0x18001b26c  lea     eax, [rcx-4]
0x18001b26f  lea     rcx, [rbp+57h+var_48]
0x18001b273  mov     [rbp+57h+arg_18], eax
0x18001b276  lea     r8, [rbp+57h+var_98]
0x18001b27a  lea     rdx, [rbp+57h+var_A0]
0x18001b27e  call    cs:__imp_DiscpGetStringFromDataBlock
0x18001b284  mov     ebx, eax
0x18001b286  test    eax, eax
0x18001b288  jnz     loc_18001B3DE
0x18001b28e  mov     esi, r13d
0x18001b291  test    r12d, r12d
0x18001b294  jz      loc_18001B396
0x18001b29a  lea     r8, [rbp+57h+arg_18]
0x18001b29e  mov     ecx, 8
0x18001b2a3  lea     rdx, [rbp+57h+var_98]
0x18001b2a7  call    cs:__imp_DiscpPadDataBlock
0x18001b2ad  mov     ebx, eax
0x18001b2af  test    eax, eax
0x18001b2b1  jnz     loc_18001B3DE
0x18001b2b7  mov     eax, [rbp+57h+arg_18]
0x18001b2ba  cmp     eax, 1
0x18001b2bd  jb      loc_18001B3AB
0x18001b2c3  mov     rcx, [rbp+57h+var_98]
0x18001b2c7  movzx   r13d, byte ptr [rcx]
0x18001b2cb  inc     rcx
0x18001b2ce  dec     eax
0x18001b2d0  mov     [rbp+57h+var_98], rcx
0x18001b2d4  mov     [rbp+57h+arg_18], eax
0x18001b2d7  mov     edx, eax
0x18001b2d9  cmp     eax, 1
0x18001b2dc  jb      loc_18001B3A8
0x18001b2e2  mov     al, [rcx]
0x18001b2e4  lea     r8, [rcx+1]
0x18001b2e8  mov     [rbp+57h+arg_10], al
0x18001b2eb  lea     eax, [rdx-1]
0x18001b2ee  mov     [rbp+57h+var_98], r8
0x18001b2f2  mov     [rbp+57h+arg_18], eax
0x18001b2f5  cmp     eax, 1
0x18001b2f8  jb      loc_18001B3A8
0x18001b2fe  movzx   r11d, byte ptr [r8]
0x18001b302  lea     eax, [rdx-2]
0x18001b305  mov     [rbp+57h+arg_18], eax
0x18001b308  lea     r8, [rcx+2]
0x18001b30c  mov     [rbp+57h+var_98], r8
0x18001b310  cmp     eax, 1
0x18001b313  jb      loc_18001B3A8
0x18001b319  movzx   r10d, byte ptr [r8]
0x18001b31d  lea     eax, [rdx-3]
0x18001b320  mov     [rbp+57h+arg_18], eax
0x18001b323  lea     r8, [rcx+3]
0x18001b327  mov     [rbp+57h+var_98], r8
0x18001b32b  cmp     eax, 4
0x18001b32e  jb      short loc_18001B3A8
0x18001b330  mov     r9d, [r8]
0x18001b333  lea     rax, [rcx+7]
0x18001b337  mov     [rbp+57h+var_98], rax
0x18001b33b  lea     eax, [rdx-7]
0x18001b33e  mov     [rbp+57h+arg_18], eax
0x18001b341  cmp     eax, 34h ; '4'
0x18001b344  jb      short loc_18001B3A8
0x18001b346  lea     rax, [rcx+3Bh]
0x18001b34a  mov     [rbp+57h+var_98], rax
0x18001b34e  lea     eax, [rdx-3Bh]
0x18001b351  mov     [rbp+57h+arg_18], eax
0x18001b354  test    rdi, rdi
0x18001b357  jz      short loc_18001B382
0x18001b359  mov     eax, r14d
0x18001b35c  imul    rcx, rax, 1Ch
0x18001b360  mov     eax, [rbp+57h+pdnDevInst]
0x18001b363  mov     [rcx+rdi], eax
0x18001b366  movzx   eax, [rbp+57h+arg_10]
0x18001b36a  mov     [rcx+rdi+8], eax
0x18001b36e  mov     [rcx+rdi+4], r13d
0x18001b373  mov     [rcx+rdi+0Ch], r11d
0x18001b378  mov     [rcx+rdi+10h], r10d
0x18001b37d  mov     [rcx+rdi+18h], r9d
0x18001b382  inc     r14d
0x18001b385  inc     esi
0x18001b387  mov     r13d, 0
0x18001b38d  cmp     esi, r12d
0x18001b390  jb      loc_18001B29A
0x18001b396  inc     r15d
0x18001b399  cmp     r15d, [rbp+57h+var_90]
0x18001b39d  jb      loc_18001B178
0x18001b3a3  mov     ebx, r13d
0x18001b3a6  jmp     short loc_18001B3AB
0x18001b3a8  xor     r13d, r13d
0x18001b3ab  test    rdi, rdi
0x18001b3ae  jnz     short loc_18001B3D0
0x18001b3b0  test    r14d, r14d
0x18001b3b3  jz      short loc_18001B3DE
0x18001b3b5  imul    ecx, r14d, 1Ch
0x18001b3b9  call    cs:__imp_DiscpAllocMemory
0x18001b3bf  mov     rdi, rax
0x18001b3c2  test    rax, rax
0x18001b3c5  jnz     loc_18001B168
0x18001b3cb  lea     ebx, [rax+8]
0x18001b3ce  jmp     short loc_18001B3DE
0x18001b3d0  mov     rax, [rbp+57h+arg_0]
0x18001b3d4  mov     [rax], r14d
0x18001b3d7  mov     rax, [rbp+57h+arg_8]
0x18001b3db  mov     [rax], rdi
0x18001b3de  mov     rcx, [rbp+57h+var_70]
0x18001b3e2  call    cs:__imp_DiscpFreeMemory
0x18001b3e8  mov     rcx, [rbp+57h+var_68]
0x18001b3ec  call    cs:__imp_DiscpFreeMemory
0x18001b3f2  mov     rcx, [rbp+57h+var_60]
0x18001b3f6  call    cs:__imp_DiscpFreeMemory
0x18001b3fc  mov     rcx, [rbp+57h+var_58]
0x18001b400  call    cs:__imp_DiscpFreeMemory
0x18001b406  jmp     short loc_18001B412
0x18001b408  cmp     ebx, 1068h
0x18001b40e  cmovz   ebx, r13d
0x18001b412  mov     eax, ebx
0x18001b414  add     rsp, 98h
0x18001b41b  pop     r15
0x18001b41d  pop     r14
0x18001b41f  pop     r13
0x18001b421  pop     r12
0x18001b423  pop     rdi
0x18001b424  pop     rsi
0x18001b425  pop     rbx
0x18001b426  pop     rbp
0x18001b427  retn
```

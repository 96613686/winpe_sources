# DiskFdoProcessError

- ea: `0x140001ec0`
- end: `0x1400022a4`
- name: `DiskFdoProcessError`
- size: `996`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140001ec0`
- `0x140002940`
- `0x140003230`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x140002225`
- `ntoskrnl!IoQueueWorkItem` at `0x140002225`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000219e`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000219e`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400021f3`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400021f3`
- `ntoskrnl!IoAllocateWorkItem` at `0x140002204`
- `ntoskrnl!IoAllocateWorkItem` at `0x140002204`

## pseudocode

```c
void __fastcall DiskFdoProcessError(PDEVICE_OBJECT DeviceObject, __int64 a2, _DWORD *a3, _BYTE *a4)
{
  PVOID DeviceExtension; // rbp
  char v5; // r11
  unsigned __int8 v6; // r10
  _BYTE *v7; // rax
  bool v8; // zf
  char *v13; // rsi
  int v14; // ecx
  char v15; // r9
  char v16; // r8
  char v17; // r11
  _BYTE *v18; // rdx
  _BYTE *v19; // rcx
  char *v20; // r11
  unsigned int v21; // ecx
  unsigned __int64 v22; // rdx
  char v23; // al
  char v24; // cl
  char v25; // cl
  __int64 SrbScsiData; // rax
  __int64 v27; // rbx
  _DWORD *ErrorLogEntry; // rax
  struct _IO_WORKITEM *WorkItem; // rax
  bool v30; // al
  char v31; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v32[7]; // [rsp+31h] [rbp-47h] BYREF
  _BYTE *v33; // [rsp+38h] [rbp-40h] BYREF
  __int128 v34; // [rsp+40h] [rbp-38h] BYREF

  DeviceExtension = DeviceObject->DeviceExtension;
  v5 = 0;
  v6 = 0;
  v31 = 0;
  v7 = 0;
  v32[0] = 0;
  v8 = *(_BYTE *)(a2 + 2) == 40;
  v33 = 0;
  v34 = 0;
  if ( v8 )
  {
    if ( *(_DWORD *)(a2 + 20)
      || !*(_DWORD *)(a2 + 56)
      || (SrbScsiData = GetSrbScsiData(a2, 0, 0, (unsigned int)&v31, (__int64)&v33, (__int64)v32),
          v5 = v31,
          v13 = (char *)SrbScsiData,
          v6 = v32[0],
          v8 = SrbScsiData == 0,
          v7 = v33,
          v8) )
    {
      v13 = (char *)&v34;
    }
  }
  else
  {
    v5 = *(_BYTE *)(a2 + 4);
    v13 = (char *)(a2 + 72);
    v6 = *(_BYTE *)(a2 + 11);
    v7 = *(_BYTE **)(a2 + 32);
  }
  if ( *a3 == -1073741764 && v13 && ((*v13 - 8) & 0x5D) == 0 )
  {
    *a4 = 1;
    ++*((_DWORD *)DeviceExtension + 149);
    return;
  }
  v14 = *(_BYTE *)(a2 + 3) & 0x3F;
  if ( v14 == 4 && v5 == 8 )
  {
    ResetBus(DeviceObject);
    ++*((_DWORD *)DeviceExtension + 149);
    return;
  }
  if ( *(char *)(a2 + 3) >= 0 || !v7 || !v13 )
  {
    if ( v14 == 4 )
    {
      if ( v5 != 24 )
        return;
      goto LABEL_28;
    }
    switch ( *(_BYTE *)(a2 + 3) & 0x3F )
    {
      case 7:
      case 8:
      case 9:
      case 0xA:
      case 0xB:
      case 0xF:
      case 0x11:
      case 0x13:
      case 0x16:
      case 0x20:
      case 0x21:
        goto LABEL_28;
      default:
        return;
    }
    return;
  }
  if ( !v6 )
    return;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = &v7[v6];
  v19 = v7 + 8;
  if ( (unsigned __int8)((*v7 & 0x7F) - 114) <= 1u )
  {
    if ( v19 <= v18 )
    {
      v16 = v7[2];
      v15 = v7[1] & 0xF;
      v17 = v7[3];
LABEL_17:
      v23 = 1;
      goto LABEL_18;
    }
  }
  else if ( v19 <= v18 )
  {
    v20 = v7 + 13;
    v15 = v7[2] & 0xF;
    v21 = v6;
    if ( (unsigned int)(unsigned __int8)v7[7] + 8 <= v6 )
      v21 = (unsigned __int8)v7[7] + 8;
    v22 = (unsigned __int64)&v7[v21];
    if ( (unsigned __int64)v20 <= v22 )
      v16 = v7[12];
    if ( (unsigned __int64)(v7 + 14) > v22 )
      v17 = 0;
    else
      v17 = *v20;
    goto LABEL_17;
  }
  v23 = 0;
LABEL_18:
  if ( !v23 )
    return;
  if ( v15 != 2 )
  {
    if ( v15 != 1 && v15 != 3 && v15 != 4 )
    {
      if ( v15 != 5 )
      {
        if ( v15 != 6 )
          return;
        goto LABEL_28;
      }
      if ( v16 == 36 )
      {
        v24 = *v13;
        if ( (*v13 == 42 || v24 == -118) && (v13[1] & 8) != 0 )
        {
          v27 = *((_QWORD *)DeviceExtension + 12);
          if ( *(_DWORD *)(v27 + 520) == 1 )
          {
            ErrorLogEntry = IoAllocateErrorLogEntry(*((PVOID *)DeviceExtension + 1), 0x40u);
            if ( ErrorLogEntry )
            {
              ErrorLogEntry[5] = *a3;
              ErrorLogEntry[3] = -2147221372;
              *((_QWORD *)ErrorLogEntry + 3) = 0;
              *ErrorLogEntry = 1048591;
              ErrorLogEntry[4] = 0;
              ErrorLogEntry[10] = *(unsigned __int8 *)(v27 + 12);
              ErrorLogEntry[11] = *(unsigned __int8 *)(v27 + 13);
              ErrorLogEntry[12] = *(unsigned __int8 *)(v27 + 14);
              ErrorLogEntry[13] = *(unsigned __int8 *)(v27 + 15);
              IoWriteErrorLogEntry(ErrorLogEntry);
            }
          }
          else
          {
            WorkItem = IoAllocateWorkItem(DeviceObject);
            if ( WorkItem )
              IoQueueWorkItem(WorkItem, DisableWriteCache, CriticalWorkQueue, WorkItem);
          }
          *((_DWORD *)DeviceExtension + 219) |= 0x80u;
          v30 = (*((_WORD *)DeviceExtension + 320) & 1) != 0
             && *((_BYTE *)DeviceExtension + 876) >= 0
             && (*((_WORD *)DeviceExtension + 320) & 0x10) == 0;
          *((_BYTE *)DeviceExtension + 643) = v30;
          v13[1] &= ~8u;
          *a4 = 1;
        }
        else if ( v24 == 26 )
        {
          v25 = v13[2];
          if ( (v25 & 0x3F) == 0x3F )
          {
            v13[2] = v25 & 0xC0 | 8;
            *a4 = 1;
          }
        }
      }
      return;
    }
LABEL_28:
    if ( (DeviceObject->Characteristics & 1) != 0 )
      DeviceObject->Flags |= 2u;
    return;
  }
  if ( v16 != 4 )
  {
    if ( v16 != 58 )
      return;
    goto LABEL_28;
  }
  if ( !v17 || v17 == 1 || v17 == 3 )
    goto LABEL_28;
}

```

## disassembly

```asm
0x140001ec0  mov     [rsp+arg_10], rbx
0x140001ec5  push    rbp
0x140001ec6  push    rsi
0x140001ec7  push    rdi
0x140001ec8  push    r14
0x140001eca  push    r15
0x140001ecc  sub     rsp, 50h
0x140001ed0  mov     rbp, [rcx+40h]
0x140001ed4  xor     r11b, r11b
0x140001ed7  xor     r10b, r10b
0x140001eda  mov     [rsp+78h+var_48], r11b
0x140001edf  xor     eax, eax
0x140001ee1  mov     [rsp+78h+var_47], r10b
0x140001ee6  cmp     byte ptr [rdx+2], 28h ; '('
0x140001eea  xorps   xmm0, xmm0
0x140001eed  mov     r15, r9
0x140001ef0  mov     [rsp+78h+var_40], rax
0x140001ef5  mov     r14, r8
0x140001ef8  mov     rbx, rdx
0x140001efb  mov     rdi, rcx
0x140001efe  movups  [rsp+78h+var_38], xmm0
0x140001f03  jz      loc_1400020CC
0x140001f09  movzx   r11d, byte ptr [rdx+4]
0x140001f0e  lea     rsi, [rdx+48h]
0x140001f12  movzx   r10d, byte ptr [rdx+0Bh]
0x140001f17  mov     rax, [rdx+20h]
0x140001f1b  cmp     dword ptr [r14], 0C000003Ch
0x140001f22  jz      loc_140002123
0x140001f28  movzx   edx, byte ptr [rbx+3]
0x140001f2c  mov     ecx, edx
0x140001f2e  and     ecx, 0FFFFFF3Fh
0x140001f34  cmp     ecx, 4
0x140001f37  jz      loc_140002009
0x140001f3d  test    dl, dl
0x140001f3f  jns     loc_140002027
0x140001f45  test    rax, rax
0x140001f48  jz      loc_140002027
0x140001f4e  test    rsi, rsi
0x140001f51  jz      loc_140002027
0x140001f57  test    rax, rax
0x140001f5a  jz      def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x140001f60  test    r10b, r10b
0x140001f63  jz      def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x140001f69  movzx   ecx, byte ptr [rax]
0x140001f6c  xor     r9b, r9b
0x140001f6f  and     cl, 7Fh
0x140001f72  movzx   edx, r10b
0x140001f76  sub     cl, 72h ; 'r'
0x140001f79  xor     r8b, r8b
0x140001f7c  xor     r11b, r11b
0x140001f7f  add     rdx, rax
0x140001f82  cmp     cl, 1
0x140001f85  lea     rcx, [rax+8]
0x140001f89  jbe     loc_140002152
0x140001f8f  cmp     rcx, rdx
0x140001f92  ja      loc_140002023
0x140001f98  movzx   edx, byte ptr [rax+7]
0x140001f9c  lea     r11, [rax+0Dh]
0x140001fa0  movzx   r9d, byte ptr [rax+2]
0x140001fa5  add     edx, 8
0x140001fa8  and     r9b, 0Fh
0x140001fac  movzx   ecx, r10b
0x140001fb0  cmp     edx, ecx
0x140001fb2  cmovbe  ecx, edx
0x140001fb5  mov     edx, ecx
0x140001fb7  add     rdx, rax
0x140001fba  cmp     r11, rdx
0x140001fbd  ja      short loc_140001FC4
0x140001fbf  movzx   r8d, byte ptr [rax+0Ch]
0x140001fc4  add     rax, 0Eh
0x140001fc8  cmp     rax, rdx
0x140001fcb  ja      loc_14000214A
0x140001fd1  movzx   r11d, byte ptr [r11]
0x140001fd5  mov     al, 1
0x140001fd7  test    al, al
0x140001fd9  jz      short def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x140001fdb  movzx   ecx, r9b
0x140001fdf  cmp     ecx, 2
0x140001fe2  jnz     short loc_14000203F
0x140001fe4  cmp     r8b, 4
0x140001fe8  jz      loc_140002280
0x140001fee  cmp     r8b, 3Ah ; ':'
0x140001ff2  jz      short loc_140002032; jumptable 00000001400020C6 cases 7-11,15,17,19,22,32,33
0x140001ff4  mov     rbx, [rsp+78h+arg_10]; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x140001ffc  add     rsp, 50h
0x140002000  pop     r15
0x140002002  pop     r14
0x140002004  pop     rdi
0x140002005  pop     rsi
0x140002006  pop     rbp
0x140002007  retn
0x140002009  cmp     r11b, 8
0x14000200d  jnz     loc_140001F3D
0x140002013  mov     rcx, rdi; DeviceObject
0x140002016  call    ResetBus
0x14000201b  inc     dword ptr [rbp+254h]
0x140002021  jmp     short def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x140002023  xor     al, al
0x140002025  jmp     short loc_140001FD7
0x140002027  cmp     ecx, 4
0x14000202a  jnz     short loc_14000209E
0x14000202c  cmp     r11b, 18h
0x140002030  jnz     short def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x140002032  mov     eax, [rdi+34h]; jumptable 00000001400020C6 cases 7-11,15,17,19,22,32,33
0x140002035  test    al, 1
0x140002037  jz      short def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x140002039  or      dword ptr [rdi+30h], 2
0x14000203d  jmp     short def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x14000203f  sub     ecx, 1
0x140002042  jz      short loc_140002032; jumptable 00000001400020C6 cases 7-11,15,17,19,22,32,33
0x140002044  sub     ecx, 2
0x140002047  jz      short loc_140002032; jumptable 00000001400020C6 cases 7-11,15,17,19,22,32,33
0x140002049  sub     ecx, 1
0x14000204c  jz      short loc_140002032; jumptable 00000001400020C6 cases 7-11,15,17,19,22,32,33
0x14000204e  sub     ecx, 1
0x140002051  jnz     loc_140002173
0x140002057  cmp     r8b, 24h ; '$'
0x14000205b  jnz     short def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x14000205d  movzx   ecx, byte ptr [rsi]
0x140002060  cmp     cl, 2Ah ; '*'
0x140002063  jz      loc_140002181
0x140002069  cmp     cl, 8Ah
0x14000206c  jz      loc_140002181
0x140002072  cmp     cl, 1Ah
0x140002075  jnz     def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x14000207b  movzx   ecx, byte ptr [rsi+2]
0x14000207f  movzx   eax, cl
0x140002082  and     al, 3Fh
0x140002084  cmp     al, 3Fh ; '?'
0x140002086  jnz     def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x14000208c  and     cl, 0C8h
0x14000208f  or      cl, 8
0x140002092  mov     [rsi+2], cl
0x140002095  mov     byte ptr [r15], 1
0x140002099  jmp     def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x14000209e  add     ecx, 0FFFFFFF9h; switch 27 cases
0x1400020a1  cmp     ecx, 1Ah
0x1400020a4  ja      def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x1400020aa  movsxd  rax, ecx
0x1400020ad  lea     rdx, cs:140000000h
0x1400020b4  movzx   eax, ds:(byte_140008B18 - 140000000h)[rdx+rax]
0x1400020bc  mov     ecx, ds:(jpt_1400020C6 - 140000000h)[rdx+rax*4]
0x1400020c3  add     rcx, rdx
0x1400020c6  jmp     rcx; switch jump
0x1400020cc  cmp     [rdx+14h], eax
0x1400020cf  jnz     short loc_140002119
0x1400020d1  cmp     [rdx+38h], eax
0x1400020d4  jbe     short loc_140002119
0x1400020d6  lea     rax, [rsp+78h+var_47]
0x1400020db  xor     r8d, r8d
0x1400020de  mov     [rsp+78h+var_50], rax
0x1400020e3  lea     r9, [rsp+78h+var_48]
0x1400020e8  lea     rax, [rsp+78h+var_40]
0x1400020ed  xor     edx, edx
0x1400020ef  mov     rcx, rbx
0x1400020f2  mov     [rsp+78h+var_58], rax
0x1400020f7  call    GetSrbScsiData
0x1400020fc  movzx   r11d, [rsp+78h+var_48]
0x140002102  mov     rsi, rax
0x140002105  movzx   r10d, [rsp+78h+var_47]
0x14000210b  test    rax, rax
0x14000210e  mov     rax, [rsp+78h+var_40]
0x140002113  jnz     loc_140001F1B
0x140002119  lea     rsi, [rsp+78h+var_38]
0x14000211e  jmp     loc_140001F1B
0x140002123  test    rsi, rsi
0x140002126  jz      loc_140001F28
0x14000212c  movzx   ecx, byte ptr [rsi]
0x14000212f  sub     cl, 8
0x140002132  test    cl, 5Dh
0x140002135  jnz     loc_140001F28
0x14000213b  mov     byte ptr [r15], 1
0x14000213f  inc     dword ptr [rbp+254h]
0x140002145  jmp     def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x14000214a  xor     r11b, r11b
0x14000214d  jmp     loc_140001FD5
0x140002152  cmp     rcx, rdx
0x140002155  ja      loc_140002023
0x14000215b  movzx   r9d, byte ptr [rax+1]
0x140002160  movzx   r8d, byte ptr [rax+2]
0x140002165  and     r9b, 0Fh
0x140002169  movzx   r11d, byte ptr [rax+3]
0x14000216e  jmp     loc_140001FD5
0x140002173  cmp     ecx, 1
0x140002176  jz      loc_140002032; jumptable 00000001400020C6 cases 7-11,15,17,19,22,32,33
0x14000217c  jmp     def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x140002181  test    byte ptr [rsi+1], 8
0x140002185  jz      loc_140002072
0x14000218b  mov     rbx, [rbp+60h]
0x14000218f  cmp     dword ptr [rbx+208h], 1
0x140002196  jnz     short loc_140002201
0x140002198  mov     rcx, [rbp+8]; IoObject
0x14000219c  mov     dl, 40h ; '@'; EntrySize
0x14000219e  call    cs:__imp_IoAllocateErrorLogEntry
0x1400021a5  nop     dword ptr [rax+rax+00h]
0x1400021aa  mov     rdx, rax
0x1400021ad  test    rax, rax
0x1400021b0  jz      short loc_140002231
0x1400021b2  mov     ecx, [r14]
0x1400021b5  mov     [rax+14h], ecx
0x1400021b8  mov     dword ptr [rax+0Ch], 80040084h
0x1400021bf  mov     qword ptr [rax+18h], 0
0x1400021c7  mov     dword ptr [rax], 10000Fh
0x1400021cd  mov     dword ptr [rax+10h], 0
0x1400021d4  movzx   ecx, byte ptr [rbx+0Ch]
0x1400021d8  mov     [rax+28h], ecx
0x1400021db  mov     rcx, rdx; ElEntry
0x1400021de  movzx   eax, byte ptr [rbx+0Dh]
0x1400021e2  mov     [rdx+2Ch], eax
0x1400021e5  movzx   eax, byte ptr [rbx+0Eh]
0x1400021e9  mov     [rdx+30h], eax
0x1400021ec  movzx   eax, byte ptr [rbx+0Fh]
0x1400021f0  mov     [rdx+34h], eax
0x1400021f3  call    cs:__imp_IoWriteErrorLogEntry
0x1400021fa  nop     dword ptr [rax+rax+00h]
0x1400021ff  jmp     short loc_140002231
0x140002201  mov     rcx, rdi; DeviceObject
0x140002204  call    cs:__imp_IoAllocateWorkItem
0x14000220b  nop     dword ptr [rax+rax+00h]
0x140002210  test    rax, rax
0x140002213  jz      short loc_140002231
0x140002215  mov     r9, rax; Context
0x140002218  lea     rdx, DisableWriteCache; WorkerRoutine
0x14000221f  xor     r8d, r8d; QueueType
0x140002222  mov     rcx, rax; IoWorkItem
0x140002225  call    cs:__imp_IoQueueWorkItem
0x14000222c  nop     dword ptr [rax+rax+00h]
0x140002231  or      dword ptr [rbp+36Ch], 80h
0x14000223b  movzx   eax, word ptr [rbp+280h]
0x140002242  test    al, 1
0x140002244  jz      short loc_14000226B
0x140002246  movzx   eax, word ptr [rbp+280h]
0x14000224d  mov     ecx, 4
0x140002252  bt      ax, cx
0x140002256  setnb   cl
0x140002259  test    byte ptr [rbp+36Ch], 80h
0x140002260  setz    al
0x140002263  test    cl, al
0x140002265  jz      short loc_14000226B
0x140002267  mov     al, 1
0x140002269  jmp     short loc_14000226D
0x14000226b  xor     al, al
0x14000226d  mov     [rbp+283h], al
0x140002273  and     byte ptr [rsi+1], 0F7h
0x140002277  mov     byte ptr [r15], 1
0x14000227b  jmp     def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
0x140002280  movzx   ecx, r11b
0x140002284  test    r11b, r11b
0x140002287  jz      loc_140002032; jumptable 00000001400020C6 cases 7-11,15,17,19,22,32,33
0x14000228d  sub     ecx, 1
0x140002290  jz      loc_140002032; jumptable 00000001400020C6 cases 7-11,15,17,19,22,32,33
0x140002296  cmp     ecx, 2
0x140002299  jz      loc_140002032; jumptable 00000001400020C6 cases 7-11,15,17,19,22,32,33
0x14000229f  jmp     def_1400020C6; jumptable 00000001400020C6 default case, cases 12-14,16,18,20,21,23-31
```

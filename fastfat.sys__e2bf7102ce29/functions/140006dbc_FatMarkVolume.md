# FatMarkVolume

- ea: `0x140006dbc`
- end: `0x140007314`
- name: `FatMarkVolume`
- size: `1368`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400019b8`
- `0x140005a94`
- `0x140006918`
- `0x140006c70`
- `0x14002c234`
- `0x14003960c`
- `0x14003dba0`
- `0x14003f104`
- `0x14003f1bc`
- `0x140040674`
- `0x140046cb0`
- `0x1400498f0`

## callees

- `0x140005924`
- `0x140006dbc`
- `0x14000c380`
- `0x140022870`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400071ef`
- `ntoskrnl!KeInitializeEvent` at `0x1400071ef`
- `ntoskrnl!IofCallDriver` at `0x140007277`
- `ntoskrnl!IofCallDriver` at `0x140007277`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000729c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000729c`
- `ntoskrnl!IoFreeMdl` at `0x1400072ca`
- `ntoskrnl!IoFreeMdl` at `0x14000d38e`
- `ntoskrnl!IoFreeMdl` at `0x1400072ca`
- `ntoskrnl!IoFreeMdl` at `0x14000d38e`
- `ntoskrnl!CcPinRead` at `0x140007134`
- `ntoskrnl!CcPinRead` at `0x140007134`
- `ntoskrnl!IoFreeIrp` at `0x1400072e5`
- `ntoskrnl!IoFreeIrp` at `0x14000d3a6`
- `ntoskrnl!IoFreeIrp` at `0x1400072e5`
- `ntoskrnl!IoFreeIrp` at `0x14000d3a6`
- `ntoskrnl!MmUnlockPages` at `0x1400072ba`
- `ntoskrnl!MmUnlockPages` at `0x14000d37e`
- `ntoskrnl!MmUnlockPages` at `0x1400072ba`
- `ntoskrnl!MmUnlockPages` at `0x14000d37e`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14000721e`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14000721e`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140006eca`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140006eca`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140006f7c`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140006f7c`
- `ntoskrnl!CcUnpinData` at `0x1400072fb`
- `ntoskrnl!CcUnpinData` at `0x14000d3bc`
- `ntoskrnl!CcUnpinData` at `0x1400072fb`
- `ntoskrnl!CcUnpinData` at `0x14000d3bc`
- `ntoskrnl!ExRaiseStatus` at `0x140007105`
- `ntoskrnl!ExRaiseStatus` at `0x140007105`

## pseudocode

```c
void __fastcall FatMarkVolume(__int64 a1, __int64 a2, int a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  IRP *v7; // r15
  unsigned __int64 v8; // rbx
  char v9; // r13
  __int64 v10; // rax
  __int64 v11; // rax
  UCHAR v12; // r12
  char *ErrorLogEntry; // rax
  _WORD *v14; // r14
  unsigned int i; // r13d
  __int64 v16; // r9
  __int64 v17; // rax
  char v18; // cl
  int v19; // ecx
  ULONG v20; // ebx
  int v21; // ecx
  __int64 v22; // r8
  __int64 v23; // rcx
  char *v24; // r14
  char *v25; // rcx
  char v26; // al
  char v27; // al
  char v28; // al
  char *v29; // rcx
  PIRP v30; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _MDL *MdlAddress; // rcx
  struct _MDL *Next; // rbx
  unsigned int v34; // [rsp+3Ch] [rbp-8Ch]
  int v35; // [rsp+40h] [rbp-88h]
  union _LARGE_INTEGER FileOffset; // [rsp+48h] [rbp-80h] BYREF
  PVOID Buffer; // [rsp+50h] [rbp-78h] BYREF
  PVOID Bcb; // [rsp+58h] [rbp-70h] BYREF
  unsigned int v39; // [rsp+60h] [rbp-68h]
  PIRP v40; // [rsp+68h] [rbp-60h]
  struct _KEVENT Event; // [rsp+70h] [rbp-58h] BYREF
  char v43; // [rsp+D8h] [rbp+10h]
  char v45; // [rsp+E8h] [rbp+20h]

  Buffer = 0;
  Bcb = 0;
  memset(&Event, 0, sizeof(Event));
  FileOffset.QuadPart = 0;
  if ( (*(_DWORD *)(a2 + 200) & 0x4000) != 0 )
    return;
  if ( *(_BYTE *)(a2 + 376) == 12 )
    return;
  v5 = *(_QWORD *)(a2 + 728);
  if ( !v5 )
    return;
  v6 = *(_QWORD *)(v5 + 40);
  if ( !v6 || !*(_QWORD *)(v6 + 8) )
    return;
  v7 = 0;
  v40 = 0;
  v43 = 0;
  v34 = 0;
  v45 = 0;
  if ( a3 == 2 || a3 == 1 && (*(_DWORD *)(a2 + 200) & 0x10) != 0 )
  {
    v8 = *(unsigned __int16 *)(*(_QWORD *)(a2 + 192) + 6LL);
    v35 = 0;
    v9 = 0;
    v10 = *(_QWORD *)(a1 + 40);
    if ( v10 )
    {
      v11 = *(_QWORD *)(v10 + 184);
      if ( v11 )
      {
        if ( *(_BYTE *)v11 == 13 )
        {
          v9 = 1;
          v35 = *(_DWORD *)(v11 + 24);
        }
      }
    }
    v12 = v8 + 58;
    if ( (unsigned __int8)(v8 + 58) > 0xF0u )
      v12 = -16;
    ErrorLogEntry = (char *)IoAllocateErrorLogEntry((PVOID)(a2 - 416), v12);
    v14 = ErrorLogEntry;
    if ( ErrorLogEntry )
    {
      *((_DWORD *)ErrorLogEntry + 3) = -2147221339;
      *((_DWORD *)ErrorLogEntry + 5) = *(_DWORD *)(a1 + 72);
      *ErrorLogEntry = *(_BYTE *)(a1 + 64);
      ErrorLogEntry[1] = 0;
      *((_WORD *)ErrorLogEntry + 1) = 12;
      *((_DWORD *)ErrorLogEntry + 10) = a3;
      *((_DWORD *)ErrorLogEntry + 11) = v9 != 0 ? v35 : 0;
      *((_DWORD *)ErrorLogEntry + 12) = *(_DWORD *)(*(_QWORD *)(a2 + 192) + 24LL);
      *((_DWORD *)ErrorLogEntry + 1) = 3670017;
      *((_WORD *)ErrorLogEntry + 28) = 0;
      if ( v8 >= (unsigned __int64)v12 - 58 )
        LOWORD(v8) = v12 - 58;
      if ( (_WORD)v8 )
      {
        memmove(ErrorLogEntry + 56, (const void *)(*(_QWORD *)(a2 + 192) + 32LL), (unsigned __int16)v8);
        v14[((unsigned __int64)(unsigned __int16)v8 >> 1) + 28] = 0;
      }
      IoWriteErrorLogEntry(v14);
    }
  }
  for ( i = 0; i < 2 && (i != 1 || *(_BYTE *)(a2 + 376) == 32 && !a3 && !v43 && *(_WORD *)(a2 + 332)); ++i )
  {
    v17 = 0;
    FileOffset.QuadPart = 0;
    v18 = *(_BYTE *)(a2 + 376);
    if ( v18 == 12 )
    {
      v19 = *(unsigned __int16 *)(a2 + 302);
      v20 = *(unsigned __int16 *)(a2 + 288);
      if ( (_WORD)v19 )
        v21 = v20 * v19;
      else
        v21 = *(_DWORD *)(a2 + 316) * v20;
      LODWORD(v22) = v21 + v20 * *(unsigned __int16 *)(a2 + 292);
    }
    else
    {
      v22 = *(unsigned __int16 *)(a2 + 288);
      v20 = *(unsigned __int16 *)(a2 + 288);
      if ( v18 == 32 && !a3 )
      {
        v23 = *(unsigned __int16 *)(a2 + 332);
        if ( (_WORD)v23 == 1 )
        {
          v43 = 1;
          v34 = *(unsigned __int16 *)(a2 + 288);
          v39 = v34;
          v20 = 2 * v22;
          LODWORD(v22) = 2 * v22;
        }
        else if ( i == 1 )
        {
          v43 = 1;
          v34 = 0;
          v39 = 0;
          v17 = v23 * v22;
          FileOffset.QuadPart = v23 * v22;
        }
      }
    }
    if ( ((v17 ^ ((unsigned int)v22 + v17 - 1)) & 0xFFFFFFFFFFFC0000uLL) != 0 )
    {
      *(_DWORD *)(a1 + 72) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
    CcPinRead(*(PFILE_OBJECT *)(a2 + 728), &FileOffset, v22, 1u, &Bcb, &Buffer);
    if ( i )
      goto LABEL_56;
    v24 = (char *)Buffer;
    if ( !FatIsBootSectorFat((char *)Buffer) )
    {
      v45 = 1;
      goto LABEL_61;
    }
    v25 = v24 + 65;
    if ( *(_BYTE *)(a2 + 376) != 32 )
      v25 = v24 + 37;
    v26 = *v25;
    if ( !a3 )
    {
      v27 = v26 & 0xFE;
LABEL_55:
      *v25 = v27;
      goto LABEL_56;
    }
    v28 = v26 | 1;
    *v25 = v28;
    if ( a3 == 2 )
    {
      v27 = v28 | 2;
      goto LABEL_55;
    }
LABEL_56:
    if ( v43 )
    {
      v29 = (char *)Buffer;
      *(_DWORD *)((char *)Buffer + v34) = 1096897106;
      *(_DWORD *)&v29[v34 + 484] = 1631679090;
      *(_DWORD *)&v29[v34 + 488] = *(_DWORD *)(a2 + 368);
      *(_DWORD *)&v29[v34 + 492] = *(_DWORD *)(a2 + 760);
      *(_DWORD *)&v29[v34 + 508] = -1437270016;
    }
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v30 = IoBuildAsynchronousFsdRequest(4u, *(PDEVICE_OBJECT *)(a2 + 136), Buffer, v20, &FileOffset, 0);
    v7 = v30;
    v40 = v30;
    if ( v30 )
    {
      v30->Tail.Overlay.CurrentStackLocation[-1].Flags |= 4u;
      CurrentStackLocation = v30->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&FatCallSelfCompletionRoutine;
      CurrentStackLocation[-1].Context = &Event;
      CurrentStackLocation[-1].Control = 0;
      CurrentStackLocation[-1].Control = 64;
      CurrentStackLocation[-1].Control = -64;
      CurrentStackLocation[-1].Control = -32;
      if ( IofCallDriver(*(PDEVICE_OBJECT *)(a2 + 136), v30) == 259 )
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    }
LABEL_61:
    if ( v7 )
    {
      MdlAddress = v7->MdlAddress;
      if ( MdlAddress )
      {
        do
        {
          Next = MdlAddress->Next;
          MmUnlockPages(MdlAddress);
          IoFreeMdl(v7->MdlAddress);
          v7->MdlAddress = Next;
          MdlAddress = Next;
        }
        while ( Next );
      }
      IoFreeIrp(v7);
    }
    if ( Bcb )
    {
      CcUnpinData(Bcb);
      Bcb = 0;
    }
  }
  if ( !v45 )
  {
    v16 = 4026531841LL;
    if ( a3 != 1 )
      v16 = 4026531840LL;
    FatSetFatEntry(a1, a2, 1, v16);
  }
}

```

## disassembly

```asm
0x140006dbc  mov     r11, rsp
0x140006dbf  mov     [r11+18h], r8d
0x140006dc3  mov     [r11+8], rcx
0x140006dc7  push    rbx
0x140006dc8  push    rsi
0x140006dc9  push    rdi
0x140006dca  push    r12
0x140006dcc  push    r13
0x140006dce  push    r14
0x140006dd0  push    r15
0x140006dd2  sub     rsp, 90h
0x140006dd9  mov     rdi, rdx
0x140006ddc  mov     rdx, rcx
0x140006ddf  xor     r12d, r12d
0x140006de2  mov     [r11-78h], r12
0x140006de6  mov     [r11-70h], r12
0x140006dea  xorps   xmm0, xmm0
0x140006ded  xor     eax, eax
0x140006def  movups  xmmword ptr [rsp+0C8h+Event.Header], xmm0
0x140006df4  mov     [r11-48h], rax
0x140006df8  mov     [r11-80h], r12
0x140006dfc  mov     eax, [rdi+0C8h]
0x140006e02  bt      eax, 0Eh
0x140006e06  jb      loc_140006FF6
0x140006e0c  cmp     byte ptr [rdi+178h], 0Ch
0x140006e13  jz      loc_140006FF6
0x140006e19  mov     rax, [rdi+2D8h]
0x140006e20  test    rax, rax
0x140006e23  jz      loc_140006FF6
0x140006e29  mov     rcx, [rax+28h]
0x140006e2d  test    rcx, rcx
0x140006e30  jz      loc_140006FF6
0x140006e36  cmp     [rcx+8], r12
0x140006e3a  jz      loc_140006FF6
0x140006e40  mov     r15d, r12d
0x140006e43  mov     [r11-60h], r12
0x140006e47  mov     [r11+10h], r12b
0x140006e4b  mov     [rsp+0C8h+var_8C], r12d
0x140006e50  mov     [r11+20h], r12b
0x140006e54  lea     esi, [r12+1]
0x140006e59  cmp     r8d, 2
0x140006e5d  jz      short loc_140006E76
0x140006e5f  cmp     r8d, esi
0x140006e62  jnz     loc_140006F8D
0x140006e68  mov     eax, [rdi+0C8h]
0x140006e6e  test    al, 10h
0x140006e70  jz      loc_140006F8D
0x140006e76  mov     rax, [rdi+0C0h]
0x140006e7d  movzx   ebx, word ptr [rax+6]
0x140006e81  mov     [rsp+0C8h+var_88], r12d
0x140006e86  mov     r13b, r12b
0x140006e89  mov     rax, [rdx+28h]
0x140006e8d  test    rax, rax
0x140006e90  jz      short loc_140006EAD
0x140006e92  mov     rax, [rax+0B8h]
0x140006e99  test    rax, rax
0x140006e9c  jz      short loc_140006EAD
0x140006e9e  cmp     byte ptr [rax], 0Dh
0x140006ea1  jnz     short loc_140006EAD
0x140006ea3  mov     r13b, sil
0x140006ea6  mov     eax, [rax+18h]
0x140006ea9  mov     [rsp+0C8h+var_88], eax
0x140006ead  lea     eax, [rbx+3Ah]
0x140006eb0  movzx   r12d, al
0x140006eb4  mov     eax, 0F0h
0x140006eb9  cmp     r12b, al
0x140006ebc  cmova   r12d, eax
0x140006ec0  lea     rcx, [rdi-1A0h]; IoObject
0x140006ec7  mov     dl, r12b; EntrySize
0x140006eca  call    cs:__imp_IoAllocateErrorLogEntry
0x140006ed1  nop     dword ptr [rax+rax+00h]
0x140006ed6  mov     r14, rax
0x140006ed9  xor     edx, edx
0x140006edb  test    rax, rax
0x140006ede  jz      loc_140006F8A
0x140006ee4  mov     dword ptr [rax+0Ch], 800400A5h
0x140006eeb  mov     rcx, [rsp+0C8h+arg_0]
0x140006ef3  mov     eax, [rcx+48h]
0x140006ef6  mov     [r14+14h], eax
0x140006efa  mov     al, [rcx+40h]
0x140006efd  mov     [r14], al
0x140006f00  mov     [r14+1], dl
0x140006f04  mov     word ptr [r14+2], 0Ch
0x140006f0b  mov     eax, [rsp+0C8h+arg_10]
0x140006f12  mov     [r14+28h], eax
0x140006f16  neg     r13b
0x140006f19  sbb     eax, eax
0x140006f1b  and     eax, [rsp+0C8h+var_88]
0x140006f1f  mov     [r14+2Ch], eax
0x140006f23  mov     rax, [rdi+0C0h]
0x140006f2a  mov     ecx, [rax+18h]
0x140006f2d  mov     [r14+30h], ecx
0x140006f31  mov     dword ptr [r14+4], 380001h
0x140006f39  mov     [r14+38h], dx
0x140006f3e  movzx   ecx, r12b
0x140006f42  add     rcx, 0FFFFFFFFFFFFFFC6h
0x140006f46  cmp     rbx, rcx
0x140006f49  jb      short loc_140006F4E
0x140006f4b  movzx   ebx, cx
0x140006f4e  xor     r12d, r12d
0x140006f51  test    bx, bx
0x140006f54  jz      short loc_140006F79
0x140006f56  movzx   ebx, bx
0x140006f59  mov     rdx, [rdi+0C0h]
0x140006f60  add     rdx, 20h ; ' '; Src
0x140006f64  mov     r8d, ebx; Size
0x140006f67  lea     rcx, [r14+38h]; void *
0x140006f6b  call    memmove
0x140006f70  shr     rbx, 1
0x140006f73  mov     [r14+rbx*2+38h], r12w
0x140006f79  mov     rcx, r14; ElEntry
0x140006f7c  call    cs:__imp_IoWriteErrorLogEntry
0x140006f83  nop     dword ptr [rax+rax+00h]
0x140006f88  jmp     short loc_140006F8D
0x140006f8a  xor     r12d, r12d
0x140006f8d  mov     r13d, r12d
0x140006f90  mov     r12d, [rsp+0C8h+arg_10]
0x140006f98  cmp     r13d, 2
0x140006f9c  jnb     short loc_140006FC8
0x140006f9e  cmp     r13d, esi
0x140006fa1  jnz     short loc_14000700A
0x140006fa3  cmp     byte ptr [rdi+178h], 20h ; ' '
0x140006faa  jnz     short loc_140006FC8
0x140006fac  xor     r14d, r14d
0x140006faf  test    r12d, r12d
0x140006fb2  jnz     short loc_140006FC8
0x140006fb4  cmp     [rsp+0C8h+arg_8], r14b
0x140006fbc  jnz     short loc_140006FC8
0x140006fbe  cmp     [rdi+14Ch], r14w
0x140006fc6  jnz     short loc_14000700D
0x140006fc8  cmp     [rsp+0C8h+arg_18], 0
0x140006fd0  jnz     short loc_140006FF6
0x140006fd2  mov     r8d, esi
0x140006fd5  mov     rdx, rdi
0x140006fd8  mov     rcx, [rsp+0C8h+arg_0]
0x140006fe0  cmp     r12d, esi
0x140006fe3  mov     r9d, 0F0000001h
0x140006fe9  jz      short loc_140006FF1
0x140006feb  mov     r9d, 0F0000000h
0x140006ff1  call    FatSetFatEntry
0x140006ff6  add     rsp, 90h
0x140006ffd  pop     r15
0x140006fff  pop     r14
0x140007001  pop     r13
0x140007003  pop     r12
0x140007005  pop     rdi
0x140007006  pop     rsi
0x140007007  pop     rbx
0x140007008  retn
0x14000700a  xor     r14d, r14d
0x14000700d  mov     [rsp+0C8h+var_94], r14d
0x140007012  mov     [rsp+0C8h+var_90], r14d
0x140007017  mov     rax, r14
0x14000701a  mov     qword ptr [rsp+0C8h+FileOffset], rax
0x14000701f  mov     cl, [rdi+178h]
0x140007025  cmp     cl, 0Ch
0x140007028  jnz     short loc_140007061
0x14000702a  movzx   ecx, word ptr [rdi+12Eh]
0x140007031  movzx   ebx, word ptr [rdi+120h]
0x140007038  test    cx, cx
0x14000703b  jnz     short loc_140007048
0x14000703d  mov     ecx, ebx
0x14000703f  imul    ecx, [rdi+13Ch]
0x140007046  jmp     short loc_14000704B
0x140007048  imul    ecx, ebx
0x14000704b  movzx   r8d, word ptr [rdi+124h]
0x140007053  imul    r8d, ebx
0x140007057  add     r8d, ecx
0x14000705a  mov     [rsp+0C8h+var_94], r8d
0x14000705f  jmp     short loc_1400070AD
0x140007061  movzx   r8d, word ptr [rdi+120h]; Length
0x140007069  mov     [rsp+0C8h+var_94], r8d
0x14000706e  mov     ebx, r8d
0x140007071  mov     [rsp+0C8h+var_90], ebx
0x140007075  cmp     cl, 20h ; ' '
0x140007078  jnz     short loc_1400070DD
0x14000707a  test    r12d, r12d
0x14000707d  jnz     short loc_1400070DD
0x14000707f  movzx   ecx, word ptr [rdi+14Ch]
0x140007086  cmp     cx, si
0x140007089  jnz     short loc_1400070B3
0x14000708b  mov     [rsp+0C8h+arg_8], sil
0x140007093  mov     [rsp+0C8h+var_98], sil
0x140007098  mov     [rsp+0C8h+var_8C], r8d
0x14000709d  mov     [rsp+0C8h+var_68], r8d
0x1400070a2  lea     ebx, [r8+r8]
0x1400070a6  mov     r8d, ebx
0x1400070a9  mov     [rsp+0C8h+var_94], ebx
0x1400070ad  mov     [rsp+0C8h+var_90], ebx
0x1400070b1  jmp     short loc_1400070DD
0x1400070b3  cmp     r13d, esi
0x1400070b6  jnz     short loc_1400070DD
0x1400070b8  mov     al, sil
0x1400070bb  mov     [rsp+0C8h+arg_8], al
0x1400070c2  mov     [rsp+0C8h+var_98], al
0x1400070c6  mov     eax, r14d
0x1400070c9  mov     [rsp+0C8h+var_8C], eax
0x1400070cd  mov     [rsp+0C8h+var_68], eax
0x1400070d1  mov     rax, r8
0x1400070d4  imul    rax, rcx
0x1400070d8  mov     qword ptr [rsp+0C8h+FileOffset], rax
0x1400070dd  mov     ecx, r8d
0x1400070e0  lea     rdx, [rax-1]
0x1400070e4  add     rdx, rcx
0x1400070e7  xor     rdx, rax
0x1400070ea  test    rdx, 0FFFFFFFFFFFC0000h
0x1400070f1  jz      short loc_140007111
0x1400070f3  mov     eax, 0C0000102h
0x1400070f8  mov     rcx, [rsp+0C8h+arg_0]
0x140007100  mov     [rcx+48h], eax
0x140007103  mov     ecx, eax; Status
0x140007105  call    cs:__imp_ExRaiseStatus
0x140007111  lea     rax, [rsp+0C8h+var_78]
0x140007116  mov     [rsp+0C8h+Buffer], rax; Buffer
0x14000711b  lea     rax, [rsp+0C8h+var_70]
0x140007120  mov     [rsp+0C8h+Bcb], rax; Bcb
0x140007125  mov     r9d, esi; Flags
0x140007128  lea     rdx, [rsp+0C8h+FileOffset]; FileOffset
0x14000712d  mov     rcx, [rdi+2D8h]; FileObject
0x140007134  call    cs:__imp_CcPinRead
0x14000713b  nop     dword ptr [rax+rax+00h]
0x140007140  test    r13d, r13d
0x140007143  jnz     short loc_140007198
0x140007145  mov     r14, [rsp+0C8h+var_78]
0x14000714a  mov     rcx, r14
0x14000714d  call    FatIsBootSectorFat
0x140007152  test    al, al
0x140007154  jnz     short loc_14000716C
0x140007156  mov     al, sil
0x140007159  mov     [rsp+0C8h+arg_18], al
0x140007160  mov     [rsp+0C8h+var_97], al
0x140007164  xor     r12d, r12d
0x140007167  jmp     loc_1400072A9
0x14000716c  cmp     byte ptr [rdi+178h], 20h ; ' '
0x140007173  lea     rcx, [r14+41h]
0x140007177  jz      short loc_14000717D
0x140007179  lea     rcx, [r14+25h]
0x14000717d  mov     al, [rcx]
0x14000717f  test    r12d, r12d
0x140007182  jnz     short loc_140007188
0x140007184  and     al, 0FEh
0x140007186  jmp     short loc_140007196
0x140007188  or      al, sil
0x14000718b  mov     [rcx], al
0x14000718d  cmp     r12d, 2
0x140007191  jnz     short loc_140007198
0x140007193  or      al, r12b
0x140007196  mov     [rcx], al
0x140007198  xor     r12d, r12d
0x14000719b  cmp     [rsp+0C8h+arg_8], r12b
0x1400071a3  jz      short loc_1400071E5
0x1400071a5  mov     edx, [rsp+0C8h+var_8C]
0x1400071a9  mov     rcx, [rsp+0C8h+var_78]
0x1400071ae  mov     dword ptr [rdx+rcx], 41615252h
0x1400071b5  mov     dword ptr [rdx+rcx+1E4h], 61417272h
0x1400071c0  mov     eax, [rdi+170h]
0x1400071c6  mov     [rdx+rcx+1E8h], eax
0x1400071cd  mov     eax, [rdi+2F8h]
0x1400071d3  mov     [rdx+rcx+1ECh], eax
0x1400071da  mov     dword ptr [rdx+rcx+1FCh], 0AA550000h
0x1400071e5  xor     r8d, r8d; State
0x1400071e8  xor     edx, edx; Type
0x1400071ea  lea     rcx, [rsp+0C8h+Event]; Event
0x1400071ef  call    cs:__imp_KeInitializeEvent
0x1400071f6  nop     dword ptr [rax+rax+00h]
0x1400071fb  mov     [rsp+0C8h+Buffer], r12; IoStatusBlock
0x140007200  lea     rax, [rsp+0C8h+FileOffset]
0x140007205  mov     [rsp+0C8h+Bcb], rax; StartingOffset
0x14000720a  mov     r9d, ebx; Length
0x14000720d  mov     r8, [rsp+0C8h+var_78]; Buffer
0x140007212  mov     rdx, [rdi+88h]; DeviceObject
0x140007219  mov     ecx, 4; MajorFunction
0x14000721e  call    cs:__imp_IoBuildAsynchronousFsdRequest
0x140007225  nop     dword ptr [rax+rax+00h]
0x14000722a  mov     r15, rax
0x14000722d  mov     [rsp+0C8h+var_60], rax
0x140007232  test    rax, rax
0x140007235  jz      short loc_1400072A9
0x140007237  mov     rcx, [rax+0B8h]
0x14000723e  or      byte ptr [rcx-46h], 4
0x140007242  mov     rcx, [rax+0B8h]
0x140007249  lea     rax, FatCallSelfCompletionRoutine
0x140007250  mov     [rcx-10h], rax
0x140007254  lea     rax, [rsp+0C8h+Event]
0x140007259  mov     [rcx-8], rax
0x14000725d  mov     [rcx-45h], r12b
0x140007261  mov     byte ptr [rcx-45h], 40h ; '@'
0x140007265  mov     byte ptr [rcx-45h], 0C0h
0x140007269  mov     byte ptr [rcx-45h], 0E0h
0x14000726d  mov     rdx, r15; Irp
0x140007270  mov     rcx, [rdi+88h]; DeviceObject
0x140007277  call    cs:__imp_IofCallDriver
0x14000727e  nop     dword ptr [rax+rax+00h]
0x140007283  cmp     eax, 103h
0x140007288  jnz     short loc_1400072A9
0x14000728a  mov     [rsp+0C8h+Bcb], r12; Timeout
0x14000728f  xor     r9d, r9d; Alertable
0x140007292  xor     r8d, r8d; WaitMode
0x140007295  xor     edx, edx; WaitReason
0x140007297  lea     rcx, [rsp+0C8h+Event]; Object
  ... truncated ...
```

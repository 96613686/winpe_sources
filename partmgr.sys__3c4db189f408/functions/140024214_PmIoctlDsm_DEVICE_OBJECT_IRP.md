# PmIoctlDsm(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140024214`
- end: `0x1400242ea`
- name: `?PmIoctlDsm@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400068b0`

## callees

- `0x14000b204`
- `0x14001ed38`
- `0x140024214`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002426e`
- `ntoskrnl!IofCompleteRequest` at `0x14002426e`

## pseudocode

```c
__int64 __fastcall PmIoctlDsm(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  unsigned int Options; // r10d
  struct _IRP *MasterIrp; // r9
  unsigned int v7; // ebx
  ULONG Flags; // r11d
  unsigned int *v9; // rsi
  unsigned int v10; // ebx
  unsigned int v12; // eax
  unsigned int v13; // edx
  unsigned int IrpCount; // r8d
  unsigned int v15; // eax
  unsigned int MdlAddress_high; // ecx
  unsigned int v17; // ecx
  bool v18; // zf
  unsigned int v19; // edx
  bool v20; // cf

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options < 0x1C )
  {
    v10 = -1073741820;
    goto LABEL_5;
  }
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v7 = 0;
  Flags = MasterIrp->Flags;
  v9 = (unsigned int *)&MasterIrp->MdlAddress + 1;
  if ( !Flags )
    goto LABEL_17;
  v7 = *v9 + Flags;
  if ( v7 >= *v9 )
  {
    if ( *v9 < 0x1C || v7 > Options )
      goto LABEL_19;
LABEL_17:
    IrpCount = MasterIrp->AssociatedIrp.IrpCount;
    v13 = 0;
    if ( !IrpCount )
      goto LABEL_21;
    if ( ((__int64)MasterIrp->MdlAddress & 1) == 0 )
    {
      v12 = *(&MasterIrp->Flags + 1);
      v13 = v12 + IrpCount;
      if ( v12 + IrpCount < v12 )
        goto LABEL_4;
      if ( v12 && (IrpCount & 0xF) == 0 && v12 >= 0x1C && v13 <= Options && (((_BYTE)MasterIrp + (_BYTE)v12) & 7) == 0 )
      {
LABEL_21:
        if ( Flags && IrpCount )
        {
          v15 = *(&MasterIrp->Flags + 1);
          MdlAddress_high = HIDWORD(MasterIrp->MdlAddress);
          if ( MdlAddress_high >= v15 )
          {
            if ( v13 > MdlAddress_high )
              goto LABEL_19;
          }
          else if ( v7 > v15 )
          {
            goto LABEL_19;
          }
        }
        if ( *(_DWORD *)(&MasterIrp->Size + 1) != -2147483620 )
          return (unsigned int)PmIoctlRedirect(a1, a2);
        if ( *(_DWORD *)&MasterIrp->Type != 28 || Flags || *v9 )
          goto LABEL_19;
        v17 = *(&MasterIrp->Flags + 1);
        if ( ((__int64)MasterIrp->MdlAddress & 1) != 0 )
        {
          if ( v17 )
            goto LABEL_19;
          v18 = IrpCount == 0;
        }
        else
        {
          if ( v17 < 0x1C
            || v17 > Options
            || (v17 & 7) != 0
            || IrpCount < 0x10
            || IrpCount > Options - v17
            || (IrpCount & 0xF) != 0 )
          {
            goto LABEL_19;
          }
          v18 = IrpCount == 16;
        }
        if ( v18 )
        {
          v19 = *v9;
          v20 = v17 < *v9;
          if ( v17 > *v9 )
          {
            if ( v19 > v17 )
              goto LABEL_19;
            v20 = 0;
          }
          if ( !v20 || v17 + IrpCount <= v19 )
          {
            if ( CurrentStackLocation->Parameters.Read.Length >= 0x38 )
              v10 = PmIoctlDsmConversionQuery(a1, a2);
            else
              v10 = -1073741789;
            goto LABEL_5;
          }
        }
      }
    }
LABEL_19:
    v10 = -1073741811;
    goto LABEL_5;
  }
LABEL_4:
  v10 = -1073741675;
LABEL_5:
  a2->IoStatus.Status = v10;
  IofCompleteRequest(a2, 0);
  return v10;
}

```

## disassembly

```asm
0x140024214  push    rbx
0x140024216  push    rbp
0x140024217  push    rsi
0x140024218  push    rdi
0x140024219  push    r13
0x14002421b  push    r14
0x14002421d  push    r15
0x14002421f  sub     rsp, 40h
0x140024223  mov     r13, [rdx+0B8h]
0x14002422a  xor     ebp, ebp
0x14002422c  mov     rdi, rdx
0x14002422f  mov     r14, rcx
0x140024232  mov     r10d, [r13+10h]
0x140024236  cmp     r10d, 1Ch
0x14002423a  jb      loc_1400242CC
0x140024240  mov     r9, [rdx+18h]
0x140024244  xor     ebx, ebx
0x140024246  mov     r11d, [r9+10h]
0x14002424a  lea     rsi, [r9+0Ch]
0x14002424e  test    r11d, r11d
0x140024251  jz      loc_140028238
0x140024257  mov     eax, [rsi]
0x140024259  lea     ebx, [rax+r11]
0x14002425d  cmp     ebx, eax
0x14002425f  jnb     short loc_1400242D3
0x140024261  mov     ebx, 0C0000095h
0x140024266  xor     edx, edx; PriorityBoost
0x140024268  mov     [rdi+30h], ebx
0x14002426b  mov     rcx, rdi; Irp
0x14002426e  call    cs:__imp_IofCompleteRequest
0x140024275  nop     dword ptr [rax+rax+00h]
0x14002427a  mov     eax, ebx
0x14002427c  add     rsp, 40h
0x140024280  pop     r15
0x140024282  pop     r14
0x140024284  pop     r13
0x140024286  pop     rdi
0x140024287  pop     rsi
0x140024288  pop     rbp
0x140024289  pop     rbx
0x14002428a  retn
0x14002428c  mov     eax, [r9+14h]
0x140024290  lea     edx, [rax+r8]
0x140024294  cmp     edx, eax
0x140024296  jb      short loc_140024261
0x140024298  test    eax, eax
0x14002429a  jz      loc_14002824F
0x1400242a0  test    r8b, 0Fh
0x1400242a4  jnz     loc_14002824F
0x1400242aa  cmp     eax, 1Ch
0x1400242ad  jb      loc_14002824F
0x1400242b3  cmp     edx, r10d
0x1400242b6  ja      loc_14002824F
0x1400242bc  add     al, r9b
0x1400242bf  test    al, 7
0x1400242c1  jz      loc_140028259
0x1400242c7  jmp     loc_14002824F
0x1400242cc  mov     ebx, 0C0000004h
0x1400242d1  jmp     short loc_140024266
0x1400242d3  cmp     eax, 1Ch
0x1400242d6  jb      loc_14002824F
0x1400242dc  cmp     ebx, r10d
0x1400242df  ja      loc_14002824F
0x1400242e5  jmp     loc_140028238
0x140028238  mov     r8d, [r9+18h]
0x14002823c  xor     edx, edx
0x14002823e  test    r8d, r8d
0x140028241  jz      short loc_140028259
0x140028243  mov     eax, [r9+8]
0x140028247  test    al, 1
0x140028249  jz      loc_14002428C
0x14002824f  mov     ebx, 0C000000Dh
0x140028254  jmp     loc_140024266
0x140028259  test    r11d, r11d
0x14002825c  jz      short loc_140028279
0x14002825e  test    r8d, r8d
0x140028261  jz      short loc_140028279
0x140028263  mov     eax, [r9+14h]
0x140028267  mov     ecx, [r9+0Ch]
0x14002826b  cmp     ecx, eax
0x14002826d  jnb     short loc_140028275
0x14002826f  cmp     ebx, eax
0x140028271  ja      short loc_14002824F
0x140028273  jmp     short loc_140028279
0x140028275  cmp     edx, ecx
0x140028277  ja      short loc_14002824F
0x140028279  cmp     dword ptr [r9+4], 8000001Ch
0x140028281  jz      short loc_140028295
0x140028283  mov     rdx, rdi; struct _IRP *
0x140028286  mov     rcx, r14; struct _DEVICE_OBJECT *
0x140028289  call    ?PmIoctlRedirect@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlRedirect(_DEVICE_OBJECT *,_IRP *)
0x14002828e  mov     ebx, eax
0x140028290  jmp     loc_14002427A
0x140028295  cmp     dword ptr [r9], 1Ch
0x140028299  jnz     short loc_14002824F
0x14002829b  test    r11d, r11d
0x14002829e  jnz     short loc_14002824F
0x1400282a0  cmp     [rsi], ebp
0x1400282a2  jnz     short loc_14002824F
0x1400282a4  mov     eax, [r9+8]
0x1400282a8  mov     ecx, [r9+14h]
0x1400282ac  mov     r9b, 1
0x1400282af  test    r9b, al
0x1400282b2  jnz     short loc_1400282E5
0x1400282b4  cmp     ecx, 1Ch
0x1400282b7  jb      short loc_14002824F
0x1400282b9  cmp     ecx, r10d
0x1400282bc  ja      short loc_14002824F
0x1400282be  test    cl, 7
0x1400282c1  jnz     short loc_14002824F
0x1400282c3  cmp     r8d, 10h
0x1400282c7  jb      short loc_14002824F
0x1400282c9  sub     r10d, ecx
0x1400282cc  cmp     r8d, r10d
0x1400282cf  ja      loc_14002824F
0x1400282d5  test    r8b, 0Fh
0x1400282d9  jnz     loc_14002824F
0x1400282df  cmp     r8d, 10h
0x1400282e3  jmp     short loc_1400282F0
0x1400282e5  test    ecx, ecx
0x1400282e7  jnz     loc_14002824F
0x1400282ed  test    r8d, r8d
0x1400282f0  jnz     loc_14002824F
0x1400282f6  mov     edx, [rsi]
0x1400282f8  cmp     ecx, edx
0x1400282fa  jbe     short loc_14002830A
0x1400282fc  lea     eax, [rdx+r11]
0x140028300  cmp     eax, ecx
0x140028302  ja      loc_14002824F
0x140028308  cmp     ecx, edx
0x14002830a  jnb     short loc_140028318
0x14002830c  lea     eax, [rcx+r8]
0x140028310  cmp     eax, edx
0x140028312  ja      loc_14002824F
0x140028318  cmp     dword ptr [r13+8], 38h ; '8'
0x14002831d  jnb     short loc_140028329
0x14002831f  mov     ebx, 0C0000023h
0x140028324  jmp     loc_140024266
0x140028329  mov     rdx, rdi; struct _IRP *
0x14002832c  mov     rcx, r14; struct _DEVICE_OBJECT *
0x14002832f  call    ?PmIoctlDsmConversionQuery@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlDsmConversionQuery(_DEVICE_OBJECT *,_IRP *)
0x140028334  mov     ebx, eax
0x140028336  jmp     loc_140024266
```

# sub_1408DFCD8

- ea: `0x1408dfcd8`
- end: `0x1408e0140`
- name: `sub_1408DFCD8`
- size: `1128`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1408dc4f0`

## callees

- `0x140227210`
- `0x1402b1240`
- `0x1402f8270`
- `0x1403f2da0`
- `0x140461498`
- `0x14051e400`
- `0x1405df6dc`
- `0x1408d13b4`
- `0x1408d3130`
- `0x1408d4784`
- `0x1408dcc90`
- `0x1408dcf08`
- `0x1408dd45c`
- `0x1408dfcd8`
- `0x1408e1ba8`
- `0x1408e2114`
- `0x1408e2680`
- `0x1408e26c8`
- `0x140bae8e0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x1408dfd53`
- `msrpc!MesDecodeBufferHandleCreate` at `0x1408dfd53`
- `msrpc!RpcExceptionFilter` at `0x140b429ca`
- `msrpc!RpcExceptionFilter` at `0x140b429ca`
- `msrpc!MesHandleFree` at `0x1408dfeba`
- `msrpc!MesHandleFree` at `0x1408dfeba`
- `msrpc!NdrMesTypeDecode3` at `0x1408dfd95`
- `msrpc!NdrMesTypeDecode3` at `0x1408dfd95`

## pseudocode

```c
__int64 __fastcall sub_1408DFCD8(PIRP Irp, __int64 a2, int a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  _QWORD *FsContext2; // rsi
  struct _IRP *MasterIrp; // rcx
  int v7; // edi
  __int64 v8; // r8
  int v9; // r9d
  _WORD *v10; // r14
  __int64 v11; // rax
  int v12; // ecx
  int v13; // r8d
  int v15; // ecx
  int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rax
  _QWORD *v19; // r14
  __int64 v20; // r8
  PVOID v21; // r8
  PVOID *v22; // rcx
  __int64 v23; // rax
  _QWORD *v24; // rcx
  _QWORD *v25; // r14
  PVOID P; // [rsp+30h] [rbp-78h] BYREF
  PVOID v27; // [rsp+38h] [rbp-70h] BYREF
  PVOID v28; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v29[12]; // [rsp+48h] [rbp-60h] BYREF
  char v30; // [rsp+B8h] [rbp+10h]
  int v31; // [rsp+C8h] [rbp+20h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v29[1] = CurrentStackLocation;
  FsContext2 = CurrentStackLocation->FileObject->FsContext2;
  v29[2] = FsContext2;
  v29[0] = 0;
  P = 0;
  v28 = 0;
  v27 = 0;
  v31 = 0;
  v30 = 0;
  if ( (byte_140EDA02C & 0x40) != 0 )
    sub_14051E400((_DWORD)Irp, (unsigned int)qword_1400153A0, a3, FsContext2[1], FsContext2[2]);
  v29[3] = &Irp->AssociatedIrp;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( !MasterIrp )
  {
    v7 = -1073741811;
    goto LABEL_52;
  }
  v7 = MesDecodeBufferHandleCreate(MasterIrp, CurrentStackLocation->Parameters.Create.Options, v29);
  if ( v7 < 0 )
    goto LABEL_17;
  NdrMesTypeDecode3(v29[0], "TP 3\a", &off_140B78E48, &off_140E0A520, 2, &P);
  if ( P )
  {
    if ( *(_QWORD *)P )
    {
      v8 = *((_QWORD *)P + 3);
      if ( (v8 || !*((_DWORD *)P + 4)) && (*((_DWORD *)P + 4) || !v8) )
      {
        v7 = sub_1408D4784(*((_QWORD *)P + 3));
        if ( v7 < 0 )
          goto LABEL_17;
        sub_1408E1BA8();
        if ( !(unsigned __int8)sub_1408E2114(FsContext2) || (FsContext2[8] & 8) != 0 )
        {
          v7 = -1073741637;
        }
        else
        {
          LOBYTE(v9) = 1;
          v7 = sub_1408D13B4(FsContext2[10], *(_QWORD *)P, *((_QWORD *)P + 1), v9, (__int64)&v27, (__int64)&v31);
          if ( v7 >= 0 )
          {
            if ( (byte_140EDA02C & 0x40) != 0 )
              sub_1405DF6DC(v15, (unsigned int)qword_14002DB48, v16, FsContext2[1], FsContext2[2], (__int64)v27);
            v17 = FsContext2[15];
            if ( v17 )
              *(_DWORD *)(v17 + 48) |= v31;
            v18 = sub_1408E2680(FsContext2, v27);
            v19 = (_QWORD *)v18;
            v28 = (PVOID)v18;
            if ( v18 )
            {
              v7 = sub_1408E26C8(
                     *(_QWORD *)(v18 + 24),
                     *(unsigned int *)(v18 + 32),
                     *((_QWORD *)P + 3),
                     *((unsigned int *)P + 4));
LABEL_35:
              ExReleaseResourceLite(&stru_140F81740);
              KeLeaveCriticalRegion();
              if ( v7 < 0 )
                goto LABEL_52;
              v20 = *((_QWORD *)P + 3);
              if ( v20 )
                v7 = sub_1408D3130(v19[2], 3, v20, *((unsigned int *)P + 4));
              if ( v7 < 0 )
                goto LABEL_52;
              sub_1408E1BA8();
              v21 = P;
              LOBYTE(v21) = *((_BYTE *)P + 32);
              v7 = sub_1408DCC90(FsContext2, v28, v21);
              goto LABEL_12;
            }
            v7 = sub_1408DCF08(v27, *((_QWORD *)P + 3), *((unsigned int *)P + 4), &v28);
            if ( v7 >= 0 )
            {
              v22 = (PVOID *)FsContext2[24];
              if ( *v22 != FsContext2 + 23 )
                goto LABEL_44;
              v30 = 1;
              v19 = v28;
              *(_QWORD *)v28 = FsContext2 + 23;
              v19[1] = v22;
              *v22 = v19;
              FsContext2[24] = v19;
              goto LABEL_35;
            }
          }
        }
LABEL_12:
        ExReleaseResourceLite(&stru_140F81740);
        KeLeaveCriticalRegion();
        if ( v7 < 0 )
          goto LABEL_52;
        v10 = v27;
        v7 = sub_1403F2DA0(Irp->AssociatedIrp.MasterIrp, CurrentStackLocation->Parameters.Read.Length, v27);
        if ( v7 >= 0 )
        {
          v11 = -1;
          do
            ++v11;
          while ( v10[v11] );
          Irp->IoStatus.Information = 2 * v11 + 2;
        }
        goto LABEL_17;
      }
    }
  }
  v7 = -1073741811;
LABEL_17:
  if ( v7 >= 0 )
    goto LABEL_18;
LABEL_52:
  v25 = v28;
  if ( v28 && v30 )
  {
    sub_1408E1BA8();
    v23 = *v25;
    if ( *(_QWORD **)(*v25 + 8LL) == v25 )
    {
      v24 = (_QWORD *)v25[1];
      if ( (_QWORD *)*v24 == v25 )
      {
        *v24 = v23;
        *(_QWORD *)(v23 + 8) = v24;
        ExReleaseResourceLite(&stru_140F81740);
        KeLeaveCriticalRegion();
        sub_1408DD45C(v25);
        goto LABEL_18;
      }
    }
LABEL_44:
    __fastfail(3u);
  }
LABEL_18:
  if ( P )
    ExFreePoolWithTag(P, 0x6370726Bu);
  if ( v27 )
    ExFreePoolWithTag(v27, 0);
  if ( v29[0] )
    MesHandleFree();
  Irp->IoStatus.Status = v7;
  IofCompleteRequest(Irp, 0);
  if ( (byte_140EDA02C & 0x40) != 0 )
    sub_140461498(v12, (unsigned int)qword_14002D4E0, v13, FsContext2[1], FsContext2[2], v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1408dfcd8  mov     r11, rsp
0x1408dfcdb  mov     [r11+8], rcx
0x1408dfcdf  push    rbx
0x1408dfce0  push    rsi
0x1408dfce1  push    rdi
0x1408dfce2  push    r12
0x1408dfce4  push    r13
0x1408dfce6  push    r14
0x1408dfce8  push    r15
0x1408dfcea  sub     rsp, 70h
0x1408dfcee  mov     r15, rcx
0x1408dfcf1  mov     r13, [rcx+0B8h]
0x1408dfcf8  mov     [rsp+0A8h+var_58], r13
0x1408dfcfd  mov     rax, [r13+30h]
0x1408dfd01  mov     rsi, [rax+20h]
0x1408dfd05  mov     [rsp+0A8h+var_50], rsi
0x1408dfd0a  xor     ebx, ebx
0x1408dfd0c  mov     [r11-60h], rbx
0x1408dfd10  mov     [r11-78h], rbx
0x1408dfd14  mov     [r11-68h], rbx
0x1408dfd18  mov     [r11-70h], rbx
0x1408dfd1c  mov     [r11+20h], ebx
0x1408dfd20  mov     [rsp+0A8h+arg_8], bl
0x1408dfd27  test    cs:byte_140EDA02C, 40h
0x1408dfd2e  jnz     loc_1408E005A
0x1408dfd34  lea     r12, [r15+18h]
0x1408dfd38  mov     [rsp+0A8h+var_48], r12
0x1408dfd3d  mov     rcx, [r12]
0x1408dfd41  test    rcx, rcx
0x1408dfd44  jz      loc_1408E00D4
0x1408dfd4a  lea     r8, [rsp+0A8h+var_60]
0x1408dfd4f  mov     edx, [r13+10h]
0x1408dfd53  call    cs:MesDecodeBufferHandleCreate
0x1408dfd5a  nop     dword ptr [rax+rax+00h]
0x1408dfd5f  mov     edi, eax
0x1408dfd61  test    eax, eax
0x1408dfd63  js      loc_1408DFE80
0x1408dfd69  lea     rax, [rsp+0A8h+P]
0x1408dfd6e  mov     [rsp+0A8h+var_80], rax
0x1408dfd73  mov     dword ptr [rsp+0A8h+var_88], 2
0x1408dfd7b  lea     r9, off_140E0A520
0x1408dfd82  lea     r8, off_140B78E48
0x1408dfd89  lea     rdx, aTp3_0; "TP 3\a"
0x1408dfd90  mov     rcx, [rsp+0A8h+var_60]
0x1408dfd95  call    cs:NdrMesTypeDecode3
0x1408dfd9c  nop     dword ptr [rax+rax+00h]
0x1408dfda1  jmp     short loc_1408DFDCE
0x1408dfda3  mov     edi, eax
0x1408dfda5  mov     [rsp+0A8h+P], 0
0x1408dfdae  xor     ebx, ebx
0x1408dfdb0  mov     r15, [rsp+0A8h+arg_0]
0x1408dfdb8  mov     [rsp+0A8h+arg_8], bl
0x1408dfdbf  mov     r13, [rsp+0A8h+var_58]
0x1408dfdc4  mov     rsi, [rsp+0A8h+var_50]
0x1408dfdc9  mov     r12, [rsp+0A8h+var_48]
0x1408dfdce  test    edi, edi
0x1408dfdd0  js      loc_1408E00D9
0x1408dfdd6  mov     rcx, [rsp+0A8h+P]
0x1408dfddb  test    rcx, rcx
0x1408dfdde  jz      loc_1408DFFF9
0x1408dfde4  cmp     [rcx], rbx
0x1408dfde7  jz      loc_1408DFFF9
0x1408dfded  mov     r8, [rcx+18h]
0x1408dfdf1  test    r8, r8
0x1408dfdf4  jz      loc_1408DFFF0
0x1408dfdfa  mov     rax, [rsp+0A8h+P]
0x1408dfdff  mov     edx, [rax+10h]
0x1408dfe02  test    edx, edx
0x1408dfe04  jz      loc_1408E004F
0x1408dfe0a  mov     rcx, r8
0x1408dfe0d  call    sub_1408D4784
0x1408dfe12  mov     edi, eax
0x1408dfe14  test    eax, eax
0x1408dfe16  js      short loc_1408DFE80
0x1408dfe18  call    sub_1408E1BA8
0x1408dfe1d  mov     rcx, rsi
0x1408dfe20  call    sub_1408E2114
0x1408dfe25  test    al, al
0x1408dfe27  jnz     loc_1408DFEF4
0x1408dfe2d  mov     edi, 0C00000BBh
0x1408dfe32  lea     rcx, stru_140F81740; Resource
0x1408dfe39  call    ExReleaseResourceLite
0x1408dfe3e  call    KeLeaveCriticalRegion
0x1408dfe43  test    edi, edi
0x1408dfe45  js      loc_1408E00D9
0x1408dfe4b  mov     edx, [r13+8]
0x1408dfe4f  mov     r14, [rsp+0A8h+var_70]
0x1408dfe54  mov     r8, r14
0x1408dfe57  mov     rcx, [r12]
0x1408dfe5b  call    sub_1403F2DA0
0x1408dfe60  mov     edi, eax
0x1408dfe62  test    eax, eax
0x1408dfe64  js      short loc_1408DFE80
0x1408dfe66  or      rax, 0FFFFFFFFFFFFFFFFh
0x1408dfe6a  inc     rax
0x1408dfe6d  cmp     [r14+rax*2], bx
0x1408dfe72  jnz     short loc_1408DFE6A
0x1408dfe74  lea     rax, ds:2[rax*2]
0x1408dfe7c  mov     [r15+38h], rax
0x1408dfe80  test    edi, edi
0x1408dfe82  js      loc_1408E00D9
0x1408dfe88  mov     rcx, [rsp+0A8h+P]; P
0x1408dfe8d  test    rcx, rcx
0x1408dfe90  jz      short loc_1408DFE9C
0x1408dfe92  mov     edx, 6370726Bh; Tag
0x1408dfe97  call    ExFreePoolWithTag
0x1408dfe9c  mov     r14, [rsp+0A8h+var_70]
0x1408dfea1  test    r14, r14
0x1408dfea4  jz      short loc_1408DFEB0
0x1408dfea6  xor     edx, edx; Tag
0x1408dfea8  mov     rcx, r14; P
0x1408dfeab  call    ExFreePoolWithTag
0x1408dfeb0  mov     rcx, [rsp+0A8h+var_60]
0x1408dfeb5  test    rcx, rcx
0x1408dfeb8  jz      short loc_1408DFEC6
0x1408dfeba  call    cs:MesHandleFree
0x1408dfec1  nop     dword ptr [rax+rax+00h]
0x1408dfec6  mov     [r15+30h], edi
0x1408dfeca  xor     edx, edx; PriorityBoost
0x1408dfecc  mov     rcx, r15; Irp
0x1408dfecf  call    IofCompleteRequest
0x1408dfed4  test    cs:byte_140EDA02C, 40h
0x1408dfedb  jnz     loc_1408E011E
0x1408dfee1  mov     eax, edi
0x1408dfee3  add     rsp, 70h
0x1408dfee7  pop     r15
0x1408dfee9  pop     r14
0x1408dfeeb  pop     r13
0x1408dfeed  pop     r12
0x1408dfeef  pop     rdi
0x1408dfef0  pop     rsi
0x1408dfef1  pop     rbx
0x1408dfef2  retn
0x1408dfef4  mov     eax, [rsi+40h]
0x1408dfef7  test    al, 8
0x1408dfef9  jnz     loc_1408DFE2D
0x1408dfeff  lea     rax, [rsp+0A8h+arg_18]
0x1408dff07  mov     [rsp+0A8h+var_80], rax
0x1408dff0c  lea     rax, [rsp+0A8h+var_70]
0x1408dff11  mov     [rsp+0A8h+var_88], rax
0x1408dff16  mov     r9b, 1
0x1408dff19  mov     rdx, [rsp+0A8h+P]
0x1408dff1e  mov     r8, [rdx+8]
0x1408dff22  mov     rdx, [rdx]
0x1408dff25  mov     rcx, [rsi+50h]
0x1408dff29  call    sub_1408D13B4
0x1408dff2e  mov     edi, eax
0x1408dff30  test    eax, eax
0x1408dff32  js      loc_1408DFE32
0x1408dff38  test    cs:byte_140EDA02C, 40h
0x1408dff3f  jnz     loc_1408E00F6
0x1408dff45  mov     rcx, [rsi+78h]
0x1408dff49  test    rcx, rcx
0x1408dff4c  jnz     loc_1408E0040
0x1408dff52  mov     rdx, [rsp+0A8h+var_70]
0x1408dff57  mov     rcx, rsi
0x1408dff5a  call    sub_1408E2680
0x1408dff5f  mov     r14, rax
0x1408dff62  mov     [rsp+0A8h+var_68], rax
0x1408dff67  test    rax, rax
0x1408dff6a  jz      loc_1408E0003
0x1408dff70  mov     r8, [rsp+0A8h+P]
0x1408dff75  mov     r9d, [r8+10h]
0x1408dff79  mov     r8, [r8+18h]
0x1408dff7d  mov     edx, [rax+20h]
0x1408dff80  mov     rcx, [rax+18h]
0x1408dff84  call    sub_1408E26C8
0x1408dff89  mov     edi, eax
0x1408dff8b  lea     rcx, stru_140F81740; Resource
0x1408dff92  call    ExReleaseResourceLite
0x1408dff97  call    KeLeaveCriticalRegion
0x1408dff9c  test    edi, edi
0x1408dff9e  js      loc_1408E00D9
0x1408dffa4  mov     rcx, [rsp+0A8h+P]
0x1408dffa9  mov     r8, [rcx+18h]
0x1408dffad  test    r8, r8
0x1408dffb0  jz      short loc_1408DFFC6
0x1408dffb2  mov     r9d, [rcx+10h]
0x1408dffb6  mov     edx, 3
0x1408dffbb  mov     rcx, [r14+10h]
0x1408dffbf  call    sub_1408D3130
0x1408dffc4  mov     edi, eax
0x1408dffc6  test    edi, edi
0x1408dffc8  js      loc_1408E00D9
0x1408dffce  call    sub_1408E1BA8
0x1408dffd3  mov     r8, [rsp+0A8h+P]
0x1408dffd8  mov     r8b, [r8+20h]
0x1408dffdc  mov     rdx, [rsp+0A8h+var_68]
0x1408dffe1  mov     rcx, rsi
0x1408dffe4  call    sub_1408DCC90
0x1408dffe9  mov     edi, eax
0x1408dffeb  jmp     loc_1408DFE32
0x1408dfff0  cmp     [rcx+10h], ebx
0x1408dfff3  jz      loc_1408DFDFA
0x1408dfff9  mov     edi, 0C000000Dh
0x1408dfffe  jmp     loc_1408DFE80
0x1408e0003  lea     r9, [rsp+0A8h+var_68]
0x1408e0008  mov     rdx, [rsp+0A8h+P]
0x1408e000d  mov     r8d, [rdx+10h]
0x1408e0011  mov     rdx, [rdx+18h]
0x1408e0015  mov     rcx, [rsp+0A8h+var_70]
0x1408e001a  call    sub_1408DCF08
0x1408e001f  mov     edi, eax
0x1408e0021  test    eax, eax
0x1408e0023  js      loc_1408DFE32
0x1408e0029  lea     rax, [rsi+0B8h]
0x1408e0030  mov     rcx, [rax+8]
0x1408e0034  cmp     [rcx], rax
0x1408e0037  jz      short loc_1408E0078
0x1408e0039  mov     ecx, 3
0x1408e003e  int     29h; Win8: RtlFailFast(ecx)
0x1408e0040  mov     eax, [rsp+0A8h+arg_18]
0x1408e0047  or      [rcx+30h], eax
0x1408e004a  jmp     loc_1408DFF52
0x1408e004f  test    r8, r8
0x1408e0052  jz      loc_1408DFE0A
0x1408e0058  jmp     short loc_1408DFFF9
0x1408e005a  mov     rax, [rsi+10h]
0x1408e005e  mov     [rsp+0A8h+var_88], rax
0x1408e0063  mov     r9, [rsi+8]
0x1408e0067  lea     rdx, qword_1400153A0
0x1408e006e  call    sub_14051E400
0x1408e0073  jmp     loc_1408DFD34
0x1408e0078  mov     [rsp+0A8h+arg_8], 1
0x1408e0080  mov     r14, [rsp+0A8h+var_68]
0x1408e0085  mov     [r14], rax
0x1408e0088  mov     [r14+8], rcx
0x1408e008c  mov     [rcx], r14
0x1408e008f  mov     [rax+8], r14
0x1408e0093  jmp     loc_1408DFF8B
0x1408e0098  call    sub_1408E1BA8
0x1408e009d  mov     rax, [r14]
0x1408e00a0  cmp     [rax+8], r14
0x1408e00a4  jnz     short loc_1408E0039
0x1408e00a6  mov     rcx, [r14+8]
0x1408e00aa  cmp     [rcx], r14
0x1408e00ad  jnz     short loc_1408E0039
0x1408e00af  mov     [rcx], rax
0x1408e00b2  mov     [rax+8], rcx
0x1408e00b6  lea     rcx, stru_140F81740; Resource
0x1408e00bd  call    ExReleaseResourceLite
0x1408e00c2  call    KeLeaveCriticalRegion
0x1408e00c7  mov     rcx, r14; P
0x1408e00ca  call    sub_1408DD45C
0x1408e00cf  jmp     loc_1408DFE88
0x1408e00d4  mov     edi, 0C000000Dh
0x1408e00d9  mov     r14, [rsp+0A8h+var_68]
0x1408e00de  test    r14, r14
0x1408e00e1  jz      loc_1408DFE88
0x1408e00e7  cmp     [rsp+0A8h+arg_8], bl
0x1408e00ee  jz      loc_1408DFE88
0x1408e00f4  jmp     short loc_1408E0098
0x1408e00f6  mov     rax, [rsp+0A8h+var_70]
0x1408e00fb  mov     [rsp+0A8h+var_80], rax
0x1408e0100  mov     rax, [rsi+10h]
0x1408e0104  mov     [rsp+0A8h+var_88], rax
0x1408e0109  mov     r9, [rsi+8]
0x1408e010d  lea     rdx, qword_14002DB48
0x1408e0114  call    sub_1405DF6DC
0x1408e0119  jmp     loc_1408DFF45
0x1408e011e  mov     dword ptr [rsp+0A8h+var_80], edi
0x1408e0122  mov     rax, [rsi+10h]
0x1408e0126  mov     [rsp+0A8h+var_88], rax
0x1408e012b  mov     r9, [rsi+8]
0x1408e012f  lea     rdx, qword_14002D4E0
0x1408e0136  call    sub_140461498
0x1408e013b  jmp     loc_1408DFEE1
0x140b429bc  push    rbp
0x140b429be  sub     rsp, 30h
0x140b429c2  mov     rbp, rdx
0x140b429c5  mov     rcx, [rcx]
0x140b429c8  mov     ecx, [rcx]; ExceptionCode
0x140b429ca  call    cs:RpcExceptionFilter
0x140b429d1  nop     dword ptr [rax+rax+00h]
0x140b429d6  nop
0x140b429d7  add     rsp, 30h
0x140b429db  pop     rbp
0x140b429dc  retn
```

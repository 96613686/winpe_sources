# sub_1408DAFC8

- ea: `0x1408dafc8`
- end: `0x1408db32c`
- name: `sub_1408DAFC8`
- size: `868`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1408ceed0`

## callees

- `0x1402b1240`
- `0x1406daa70`
- `0x1408b55e4`
- `0x1408c85dc`
- `0x1408c8790`
- `0x1408ccf80`
- `0x1408cdbc8`
- `0x1408d2954`
- `0x1408d3e24`
- `0x1408dafc8`
- `0x1408db718`
- `0x1409e6124`
- `0x140bae8e0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x1408db026`
- `msrpc!MesDecodeBufferHandleCreate` at `0x1408db026`
- `msrpc!RpcExceptionFilter` at `0x140b42952`
- `msrpc!RpcExceptionFilter` at `0x140b42952`
- `msrpc!MesHandleFree` at `0x1408db271`
- `msrpc!MesHandleFree` at `0x1408db271`
- `msrpc!NdrMesTypeDecode3` at `0x1408db06b`
- `msrpc!NdrMesTypeDecode3` at `0x1408db06b`

## pseudocode

```c
__int64 __fastcall sub_1408DAFC8(PIRP Irp)
{
  struct _IRP *MasterIrp; // rcx
  NTSTATUS v3; // edi
  __int64 v4; // r11
  unsigned int v5; // r13d
  char v6; // dl
  char v7; // di
  unsigned int v8; // r8d
  __int64 v9; // r9
  int v10; // eax
  __int64 i; // r12
  __int64 v12; // rsi
  __int64 v13; // rcx
  int v14; // edx
  __int64 v15; // r8
  __int64 v17; // [rsp+50h] [rbp-68h] BYREF
  PVOID v18; // [rsp+58h] [rbp-60h] BYREF
  _QWORD v19[11]; // [rsp+60h] [rbp-58h] BYREF
  PVOID P; // [rsp+C8h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+D0h] [rbp+18h] BYREF
  HANDLE v22; // [rsp+D8h] [rbp+20h] BYREF

  v17 = 0;
  Handle = 0;
  v22 = 0;
  P = 0;
  v18 = 0;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( !MasterIrp )
    goto LABEL_28;
  v3 = MesDecodeBufferHandleCreate(MasterIrp, Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options, &v17);
  if ( v3 < 0 )
    goto LABEL_29;
  NdrMesTypeDecode3(v17, "TP 3\a", &off_140004F60, &off_140E0A510, 2, &P);
  if ( !P
    || !*((_QWORD *)P + 1)
    || !*((_QWORD *)P + 3)
    || !*((_DWORD *)P + 4)
    || (v5 = sub_1408CDBC8(*(unsigned int *)P)) == 0 )
  {
LABEL_28:
    v3 = -1073741811;
    goto LABEL_29;
  }
  Handle = 0;
  v3 = sub_1408CCF80(*(__int64 *)&qword_140E4C568, v4, v5, 7, 0, (__int64)&Handle);
  if ( v3 < 0 )
    goto LABEL_29;
  v6 = 0;
  v7 = 0;
  v8 = *((_DWORD *)P + 4);
  if ( v8 )
  {
    v9 = 0;
    do
    {
      v10 = *(_DWORD *)(*((_QWORD *)P + 3) + 48 * v9 + 20);
      if ( !v10 )
        v6 = 1;
      if ( v10 == 1 )
        v7 = 1;
      v9 = (unsigned int)(v9 + 1);
    }
    while ( (unsigned int)v9 < v8 );
  }
  if ( v6 && !(unsigned __int8)sub_1408DB718(2u) )
    goto LABEL_43;
  if ( v7 )
  {
    if ( (unsigned __int8)sub_1408DB718(0x100u) )
    {
      v3 = sub_1408B55E4(1, *((_QWORD *)P + 1), v5, 7, 1, 0, (__int64)&v22);
      if ( v3 < 0 )
        goto LABEL_29;
      goto LABEL_19;
    }
LABEL_43:
    v3 = -1073741790;
    goto LABEL_29;
  }
LABEL_19:
  v3 = sub_1408C8790(&v18);
  if ( v3 >= 0 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)P + 4); i = (unsigned int)(i + 1) )
    {
      v12 = *((_QWORD *)P + 3) + 48 * i;
      v13 = *(_QWORD *)(v12 + 40);
      v14 = *(_DWORD *)(v12 + 32);
      v15 = *(_QWORD *)(v12 + 24);
      if ( *(_DWORD *)(v12 + 20) )
      {
        v3 = sub_1408D2954(qword_140E4C568, (_DWORD)v22, v15, v12, v14, v13, *(_DWORD *)(v12 + 36));
        if ( v3 >= 0 )
        {
          v19[0] = 0;
          v19[1] = *(_QWORD *)(v12 + 24);
          v19[2] = v12;
          sub_1409E6124(*((_QWORD *)P + 1), v5, 4, (unsigned int)v19, 1);
        }
      }
      else
      {
        v3 = sub_1408D3E24(
               *(_QWORD *)&qword_140E4C568,
               *((_QWORD *)P + 1),
               v5,
               Handle,
               v15,
               v12,
               v14,
               v13,
               *(_DWORD *)(v12 + 36),
               0);
      }
      if ( v3 == -1073741275 )
        v3 = *(_DWORD *)(v12 + 32) != 0 ? 0xC0000225 : 0;
      if ( v3 < 0 )
        break;
    }
  }
LABEL_29:
  if ( Handle )
    ZwClose(Handle);
  if ( v22 )
    ZwClose(v22);
  if ( P )
    ExFreePoolWithTag(P, 0x6370726Bu);
  if ( v17 )
    MesHandleFree();
  if ( v18 )
    sub_1408C85DC(v18);
  Irp->IoStatus.Status = v3;
  IofCompleteRequest(Irp, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1408dafc8  mov     rax, rsp
0x1408dafcb  mov     [rax+8], rcx
0x1408dafcf  push    rsi
0x1408dafd0  push    rdi
0x1408dafd1  push    r12
0x1408dafd3  push    r13
0x1408dafd5  push    r14
0x1408dafd7  push    r15
0x1408dafd9  sub     rsp, 88h
0x1408dafe0  mov     r14, rcx
0x1408dafe3  mov     qword ptr [rax-68h], 0
0x1408dafeb  mov     qword ptr [rax+18h], 0
0x1408daff3  mov     qword ptr [rax+20h], 0
0x1408daffb  mov     qword ptr [rax+10h], 0
0x1408db003  mov     qword ptr [rax-60h], 0
0x1408db00b  mov     rcx, [rcx+18h]
0x1408db00f  test    rcx, rcx
0x1408db012  jz      loc_1408DB225
0x1408db018  mov     rdx, [r14+0B8h]
0x1408db01f  lea     r8, [rax-68h]
0x1408db023  mov     edx, [rdx+10h]
0x1408db026  call    cs:MesDecodeBufferHandleCreate
0x1408db02d  nop     dword ptr [rax+rax+00h]
0x1408db032  mov     edi, eax
0x1408db034  test    eax, eax
0x1408db036  js      loc_1408DB22A
0x1408db03c  lea     rax, [rsp+0B8h+P]
0x1408db044  mov     [rsp+0B8h+var_90], rax
0x1408db049  mov     dword ptr [rsp+0B8h+var_98], 2
0x1408db051  lea     r9, off_140E0A510
0x1408db058  lea     r8, off_140004F60
0x1408db05f  lea     rdx, aTp3; "TP 3\a"
0x1408db066  mov     rcx, [rsp+0B8h+var_68]
0x1408db06b  call    cs:NdrMesTypeDecode3
0x1408db072  nop     dword ptr [rax+rax+00h]
0x1408db077  jmp     short loc_1408DB08F
0x1408db079  mov     edi, eax
0x1408db07b  mov     [rsp+0B8h+P], 0
0x1408db087  mov     r14, [rsp+0B8h+arg_0]
0x1408db08f  test    edi, edi
0x1408db091  js      loc_1408DB22A
0x1408db097  mov     r10, [rsp+0B8h+P]
0x1408db09f  test    r10, r10
0x1408db0a2  jz      loc_1408DB225
0x1408db0a8  mov     r11, [r10+8]
0x1408db0ac  test    r11, r11
0x1408db0af  jz      loc_1408DB225
0x1408db0b5  cmp     qword ptr [r10+18h], 0
0x1408db0ba  jz      loc_1408DB225
0x1408db0c0  cmp     dword ptr [r10+10h], 0
0x1408db0c5  jz      loc_1408DB225
0x1408db0cb  mov     ecx, [r10]
0x1408db0ce  call    sub_1408CDBC8
0x1408db0d3  mov     r13d, eax
0x1408db0d6  test    eax, eax
0x1408db0d8  jz      loc_1408DB225
0x1408db0de  mov     [rsp+0B8h+Handle], 0
0x1408db0ea  lea     rax, [rsp+0B8h+Handle]
0x1408db0f2  mov     [rsp+0B8h+var_90], rax
0x1408db0f7  mov     byte ptr [rsp+0B8h+var_98], 0
0x1408db0fc  mov     esi, 7
0x1408db101  mov     r9d, esi
0x1408db104  mov     r8d, r13d
0x1408db107  mov     rdx, r11
0x1408db10a  mov     rcx, cs:qword_140E4C568
0x1408db111  call    sub_1408CCF80
0x1408db116  mov     edi, eax
0x1408db118  test    eax, eax
0x1408db11a  js      loc_1408DB22A
0x1408db120  xor     dl, dl
0x1408db122  xor     dil, dil
0x1408db125  mov     rax, [rsp+0B8h+P]
0x1408db12d  mov     r8d, [rax+10h]
0x1408db131  lea     r15d, [rsi-6]
0x1408db135  test    r8d, r8d
0x1408db138  jz      short loc_1408DB169
0x1408db13a  xor     r9d, r9d
0x1408db13d  mov     r10, [rax+18h]
0x1408db141  lea     rcx, [r9+r9*2]
0x1408db145  add     rcx, rcx
0x1408db148  mov     eax, [r10+rcx*8+14h]
0x1408db14d  movzx   edx, dl
0x1408db150  test    eax, eax
0x1408db152  cmovz   edx, r15d
0x1408db156  movzx   edi, dil
0x1408db15a  cmp     eax, r15d
0x1408db15d  cmovz   edi, r15d
0x1408db161  add     r9d, r15d
0x1408db164  cmp     r9d, r8d
0x1408db167  jb      short loc_1408DB141
0x1408db169  test    dl, dl
0x1408db16b  jz      short loc_1408DB17F
0x1408db16d  mov     ecx, 2; DesiredAccess
0x1408db172  call    sub_1408DB718
0x1408db177  test    al, al
0x1408db179  jz      loc_1408DB318
0x1408db17f  test    dil, dil
0x1408db182  jnz     loc_1408DB2BD
0x1408db188  lea     rcx, [rsp+0B8h+var_60]
0x1408db18d  call    sub_1408C8790
0x1408db192  mov     edi, eax
0x1408db194  test    eax, eax
0x1408db196  js      loc_1408DB22A
0x1408db19c  xor     r12d, r12d
0x1408db19f  mov     r10, [rsp+0B8h+P]
0x1408db1a7  cmp     r12d, [r10+10h]
0x1408db1ab  jnb     short loc_1408DB22A
0x1408db1ad  lea     rsi, [r12+r12*2]
0x1408db1b1  shl     rsi, 4
0x1408db1b5  add     rsi, [r10+18h]
0x1408db1b9  mov     eax, [rsi+24h]
0x1408db1bc  mov     rcx, [rsi+28h]
0x1408db1c0  mov     edx, [rsi+20h]
0x1408db1c3  mov     r8, [rsi+18h]
0x1408db1c7  cmp     dword ptr [rsi+14h], 0
0x1408db1cb  jnz     loc_140B5690E
0x1408db1d1  mov     [rsp+0B8h+var_70], 0
0x1408db1d9  mov     [rsp+0B8h+var_78], eax
0x1408db1dd  mov     [rsp+0B8h+var_80], rcx
0x1408db1e2  mov     dword ptr [rsp+0B8h+var_88], edx
0x1408db1e6  mov     [rsp+0B8h+var_90], rsi
0x1408db1eb  mov     [rsp+0B8h+var_98], r8
0x1408db1f0  mov     r9, [rsp+0B8h+Handle]
0x1408db1f8  mov     r8d, r13d
0x1408db1fb  mov     rdx, [r10+8]
0x1408db1ff  mov     rcx, cs:qword_140E4C568
0x1408db206  call    sub_1408D3E24
0x1408db20b  mov     edi, eax
0x1408db20d  cmp     edi, 0C0000225h
0x1408db213  jz      loc_1408DB2AF
0x1408db219  test    edi, edi
0x1408db21b  js      short loc_1408DB22A
0x1408db21d  add     r12d, r15d
0x1408db220  jmp     loc_1408DB19F
0x1408db225  mov     edi, 0C000000Dh
0x1408db22a  mov     rcx, [rsp+0B8h+Handle]; Handle
0x1408db232  test    rcx, rcx
0x1408db235  jz      short loc_1408DB23C
0x1408db237  call    ZwClose
0x1408db23c  mov     rcx, [rsp+0B8h+arg_18]; Handle
0x1408db244  test    rcx, rcx
0x1408db247  jnz     loc_1408DB322
0x1408db24d  mov     r10, [rsp+0B8h+P]
0x1408db255  test    r10, r10
0x1408db258  jz      short loc_1408DB267
0x1408db25a  mov     edx, 6370726Bh; Tag
0x1408db25f  mov     rcx, r10; P
0x1408db262  call    ExFreePoolWithTag
0x1408db267  mov     rcx, [rsp+0B8h+var_68]
0x1408db26c  test    rcx, rcx
0x1408db26f  jz      short loc_1408DB27D
0x1408db271  call    cs:MesHandleFree
0x1408db278  nop     dword ptr [rax+rax+00h]
0x1408db27d  mov     rcx, [rsp+0B8h+var_60]; P
0x1408db282  test    rcx, rcx
0x1408db285  jz      short loc_1408DB28C
0x1408db287  call    sub_1408C85DC
0x1408db28c  mov     [r14+30h], edi
0x1408db290  xor     edx, edx; PriorityBoost
0x1408db292  mov     rcx, r14; Irp
0x1408db295  call    IofCompleteRequest
0x1408db29a  mov     eax, edi
0x1408db29c  add     rsp, 88h
0x1408db2a3  pop     r15
0x1408db2a5  pop     r14
0x1408db2a7  pop     r13
0x1408db2a9  pop     r12
0x1408db2ab  pop     rdi
0x1408db2ac  pop     rsi
0x1408db2ad  retn
0x1408db2af  mov     eax, [rsi+20h]
0x1408db2b2  neg     eax
0x1408db2b4  sbb     ecx, ecx
0x1408db2b6  and     edi, ecx
0x1408db2b8  jmp     loc_1408DB219
0x1408db2bd  mov     ecx, 100h; DesiredAccess
0x1408db2c2  call    sub_1408DB718
0x1408db2c7  test    al, al
0x1408db2c9  jz      short loc_1408DB318
0x1408db2cb  test    dil, dil
0x1408db2ce  jz      loc_1408DB188
0x1408db2d4  lea     rax, [rsp+0B8h+arg_18]
0x1408db2dc  mov     [rsp+0B8h+var_88], rax
0x1408db2e1  mov     [rsp+0B8h+var_90], 0
0x1408db2ea  mov     byte ptr [rsp+0B8h+var_98], r15b
0x1408db2ef  mov     r9d, esi
0x1408db2f2  mov     r8d, r13d
0x1408db2f5  mov     rdx, [rsp+0B8h+P]
0x1408db2fd  mov     rdx, [rdx+8]
0x1408db301  mov     ecx, r15d
0x1408db304  call    sub_1408B55E4
0x1408db309  mov     edi, eax
0x1408db30b  test    eax, eax
0x1408db30d  js      loc_1408DB22A
0x1408db313  jmp     loc_1408DB188
0x1408db318  mov     edi, 0C0000022h
0x1408db31d  jmp     loc_1408DB22A
0x1408db322  call    ZwClose
0x1408db327  jmp     loc_1408DB24D
0x140b42944  push    rbp
0x140b42946  sub     rsp, 50h
0x140b4294a  mov     rbp, rdx
0x140b4294d  mov     rcx, [rcx]
0x140b42950  mov     ecx, [rcx]; ExceptionCode
0x140b42952  call    cs:RpcExceptionFilter
0x140b42959  nop     dword ptr [rax+rax+00h]
0x140b4295e  nop
0x140b4295f  add     rsp, 50h
0x140b42963  pop     rbp
0x140b42964  retn
0x140b5690e  mov     dword ptr [rsp+0B8h+var_88], eax
0x140b56912  mov     [rsp+0B8h+var_90], rcx
0x140b56917  mov     dword ptr [rsp+0B8h+var_98], edx
0x140b5691b  mov     r9, rsi
0x140b5691e  mov     rdx, [rsp+0B8h+arg_18]
0x140b56926  mov     rcx, cs:qword_140E4C568
0x140b5692d  call    sub_1408D2954
0x140b56932  mov     edi, eax
0x140b56934  test    eax, eax
0x140b56936  js      loc_1408DB20D
0x140b5693c  mov     [rsp+0B8h+var_58], 0
0x140b56945  mov     rax, [rsi+18h]
0x140b56949  mov     [rsp+0B8h+var_50], rax
0x140b5694e  mov     [rsp+0B8h+var_48], rsi
0x140b56953  mov     dword ptr [rsp+0B8h+var_98], r15d
0x140b56958  lea     r9, [rsp+0B8h+var_58]
0x140b5695d  mov     r8d, 4
0x140b56963  mov     edx, r13d
0x140b56966  mov     rcx, [rsp+0B8h+P]
0x140b5696e  mov     rcx, [rcx+8]
0x140b56972  call    sub_1409E6124
0x140b56977  nop
0x140b56978  jmp     loc_1408DB20D
```

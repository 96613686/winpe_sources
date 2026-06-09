# PiDqIrpPropertySet

- ea: `0x14090fda8`
- end: `0x14091010c`
- name: `PiDqIrpPropertySet`
- size: `868`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140903cb0`

## callees

- `0x1402c0a40`
- `0x1406dd5c0`
- `0x1408ea4f4`
- `0x1408fd47c`
- `0x1408fd630`
- `0x140901d60`
- `0x1409029a8`
- `0x140907734`
- `0x140908c04`
- `0x14090fda8`
- `0x1409104f8`
- `0x1409e89b4`
- `0x140bb19f0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x14090fe06`
- `msrpc!MesDecodeBufferHandleCreate` at `0x14090fe06`
- `msrpc!RpcExceptionFilter` at `0x140b44712`
- `msrpc!RpcExceptionFilter` at `0x140b44712`
- `msrpc!MesHandleFree` at `0x140910051`
- `msrpc!MesHandleFree` at `0x140910051`
- `msrpc!NdrMesTypeDecode3` at `0x14090fe4b`
- `msrpc!NdrMesTypeDecode3` at `0x14090fe4b`

## pseudocode

```c
__int64 __fastcall PiDqIrpPropertySet(PIRP Irp)
{
  struct _IRP *MasterIrp; // rcx
  NTSTATUS v3; // edi
  __int64 v4; // r11
  unsigned int PnpObjectType; // r13d
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
  NdrMesTypeDecode3(v17, "TP 3\a", &off_140004F50, &off_140E0A510, 2, &P);
  if ( !P
    || !*((_QWORD *)P + 1)
    || !*((_QWORD *)P + 3)
    || !*((_DWORD *)P + 4)
    || (PnpObjectType = PiDqGetPnpObjectType(*(unsigned int *)P)) == 0 )
  {
LABEL_28:
    v3 = -1073741811;
    goto LABEL_29;
  }
  Handle = 0;
  v3 = PnpOpenObjectRegKey(*(__int64 *)&PiPnpRtlCtx, v4, PnpObjectType, 7, 0, (__int64)&Handle);
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
  if ( v6 && !(unsigned __int8)PiAuDoesClientHaveAccess(2u) )
    goto LABEL_43;
  if ( v7 )
  {
    if ( (unsigned __int8)PiAuDoesClientHaveAccess(0x100u) )
    {
      v3 = PiDqOpenObjectRegKey(1, *((_QWORD *)P + 1), PnpObjectType, 7, 1, 0, (__int64)&v22);
      if ( v3 < 0 )
        goto LABEL_29;
      goto LABEL_19;
    }
LABEL_43:
    v3 = -1073741790;
    goto LABEL_29;
  }
LABEL_19:
  v3 = PiPnpRtlBeginOperation(&v18);
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
        v3 = PnpSetGenericStoreProperty(PiPnpRtlCtx, (_DWORD)v22, v15, v12, v14, v13, *(_DWORD *)(v12 + 36));
        if ( v3 >= 0 )
        {
          v19[0] = 0;
          v19[1] = *(_QWORD *)(v12 + 24);
          v19[2] = v12;
          PiPnpRtlObjectEventWorker(*((_QWORD *)P + 1), PnpObjectType, 4, (__int64)v19, 1u);
        }
      }
      else
      {
        v3 = PiPnpRtlSetObjectProperty(
               *(_QWORD *)&PiPnpRtlCtx,
               *((_QWORD *)P + 1),
               PnpObjectType,
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
    PiPnpRtlEndOperation(v18);
  Irp->IoStatus.Status = v3;
  IofCompleteRequest(Irp, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14090fda8  mov     rax, rsp
0x14090fdab  mov     [rax+8], rcx
0x14090fdaf  push    rsi
0x14090fdb0  push    rdi
0x14090fdb1  push    r12
0x14090fdb3  push    r13
0x14090fdb5  push    r14
0x14090fdb7  push    r15
0x14090fdb9  sub     rsp, 88h
0x14090fdc0  mov     r14, rcx
0x14090fdc3  mov     qword ptr [rax-68h], 0
0x14090fdcb  mov     qword ptr [rax+18h], 0
0x14090fdd3  mov     qword ptr [rax+20h], 0
0x14090fddb  mov     qword ptr [rax+10h], 0
0x14090fde3  mov     qword ptr [rax-60h], 0
0x14090fdeb  mov     rcx, [rcx+18h]
0x14090fdef  test    rcx, rcx
0x14090fdf2  jz      loc_140910005
0x14090fdf8  mov     rdx, [r14+0B8h]
0x14090fdff  lea     r8, [rax-68h]
0x14090fe03  mov     edx, [rdx+10h]
0x14090fe06  call    cs:__imp_MesDecodeBufferHandleCreate
0x14090fe0d  nop     dword ptr [rax+rax+00h]
0x14090fe12  mov     edi, eax
0x14090fe14  test    eax, eax
0x14090fe16  js      loc_14091000A
0x14090fe1c  lea     rax, [rsp+0B8h+P]
0x14090fe24  mov     [rsp+0B8h+var_90], rax
0x14090fe29  mov     dword ptr [rsp+0B8h+var_98], 2
0x14090fe31  lea     r9, off_140E0A510
0x14090fe38  lea     r8, off_140004F50
0x14090fe3f  lea     rdx, aTp3; "TP 3\a"
0x14090fe46  mov     rcx, [rsp+0B8h+var_68]
0x14090fe4b  call    cs:__imp_NdrMesTypeDecode3
0x14090fe52  nop     dword ptr [rax+rax+00h]
0x14090fe57  jmp     short loc_14090FE6F
0x14090fe59  mov     edi, eax
0x14090fe5b  mov     [rsp+0B8h+P], 0
0x14090fe67  mov     r14, [rsp+0B8h+arg_0]
0x14090fe6f  test    edi, edi
0x14090fe71  js      loc_14091000A
0x14090fe77  mov     r10, [rsp+0B8h+P]
0x14090fe7f  test    r10, r10
0x14090fe82  jz      loc_140910005
0x14090fe88  mov     r11, [r10+8]
0x14090fe8c  test    r11, r11
0x14090fe8f  jz      loc_140910005
0x14090fe95  cmp     qword ptr [r10+18h], 0
0x14090fe9a  jz      loc_140910005
0x14090fea0  cmp     dword ptr [r10+10h], 0
0x14090fea5  jz      loc_140910005
0x14090feab  mov     ecx, [r10]
0x14090feae  call    PiDqGetPnpObjectType
0x14090feb3  mov     r13d, eax
0x14090feb6  test    eax, eax
0x14090feb8  jz      loc_140910005
0x14090febe  mov     [rsp+0B8h+Handle], 0
0x14090feca  lea     rax, [rsp+0B8h+Handle]
0x14090fed2  mov     [rsp+0B8h+var_90], rax
0x14090fed7  mov     byte ptr [rsp+0B8h+var_98], 0
0x14090fedc  mov     esi, 7
0x14090fee1  mov     r9d, esi
0x14090fee4  mov     r8d, r13d
0x14090fee7  mov     rdx, r11
0x14090feea  mov     rcx, cs:PiPnpRtlCtx
0x14090fef1  call    _PnpOpenObjectRegKey
0x14090fef6  mov     edi, eax
0x14090fef8  test    eax, eax
0x14090fefa  js      loc_14091000A
0x14090ff00  xor     dl, dl
0x14090ff02  xor     dil, dil
0x14090ff05  mov     rax, [rsp+0B8h+P]
0x14090ff0d  mov     r8d, [rax+10h]
0x14090ff11  lea     r15d, [rsi-6]
0x14090ff15  test    r8d, r8d
0x14090ff18  jz      short loc_14090FF49
0x14090ff1a  xor     r9d, r9d
0x14090ff1d  mov     r10, [rax+18h]
0x14090ff21  lea     rcx, [r9+r9*2]
0x14090ff25  add     rcx, rcx
0x14090ff28  mov     eax, [r10+rcx*8+14h]
0x14090ff2d  movzx   edx, dl
0x14090ff30  test    eax, eax
0x14090ff32  cmovz   edx, r15d
0x14090ff36  movzx   edi, dil
0x14090ff3a  cmp     eax, r15d
0x14090ff3d  cmovz   edi, r15d
0x14090ff41  add     r9d, r15d
0x14090ff44  cmp     r9d, r8d
0x14090ff47  jb      short loc_14090FF21
0x14090ff49  test    dl, dl
0x14090ff4b  jz      short loc_14090FF5F
0x14090ff4d  mov     ecx, 2; DesiredAccess
0x14090ff52  call    PiAuDoesClientHaveAccess
0x14090ff57  test    al, al
0x14090ff59  jz      loc_1409100F8
0x14090ff5f  test    dil, dil
0x14090ff62  jnz     loc_14091009D
0x14090ff68  lea     rcx, [rsp+0B8h+var_60]
0x14090ff6d  call    PiPnpRtlBeginOperation
0x14090ff72  mov     edi, eax
0x14090ff74  test    eax, eax
0x14090ff76  js      loc_14091000A
0x14090ff7c  xor     r12d, r12d
0x14090ff7f  mov     r10, [rsp+0B8h+P]
0x14090ff87  cmp     r12d, [r10+10h]
0x14090ff8b  jnb     short loc_14091000A
0x14090ff8d  lea     rsi, [r12+r12*2]
0x14090ff91  shl     rsi, 4
0x14090ff95  add     rsi, [r10+18h]
0x14090ff99  mov     eax, [rsi+24h]
0x14090ff9c  mov     rcx, [rsi+28h]
0x14090ffa0  mov     edx, [rsi+20h]
0x14090ffa3  mov     r8, [rsi+18h]
0x14090ffa7  cmp     dword ptr [rsi+14h], 0
0x14090ffab  jnz     loc_140B5B380
0x14090ffb1  mov     [rsp+0B8h+var_70], 0
0x14090ffb9  mov     [rsp+0B8h+var_78], eax
0x14090ffbd  mov     [rsp+0B8h+var_80], rcx
0x14090ffc2  mov     dword ptr [rsp+0B8h+var_88], edx
0x14090ffc6  mov     [rsp+0B8h+var_90], rsi
0x14090ffcb  mov     [rsp+0B8h+var_98], r8
0x14090ffd0  mov     r9, [rsp+0B8h+Handle]
0x14090ffd8  mov     r8d, r13d
0x14090ffdb  mov     rdx, [r10+8]
0x14090ffdf  mov     rcx, cs:PiPnpRtlCtx
0x14090ffe6  call    PiPnpRtlSetObjectProperty
0x14090ffeb  mov     edi, eax
0x14090ffed  cmp     edi, 0C0000225h
0x14090fff3  jz      loc_14091008F
0x14090fff9  test    edi, edi
0x14090fffb  js      short loc_14091000A
0x14090fffd  add     r12d, r15d
0x140910000  jmp     loc_14090FF7F
0x140910005  mov     edi, 0C000000Dh
0x14091000a  mov     rcx, [rsp+0B8h+Handle]; Handle
0x140910012  test    rcx, rcx
0x140910015  jz      short loc_14091001C
0x140910017  call    ZwClose
0x14091001c  mov     rcx, [rsp+0B8h+arg_18]; Handle
0x140910024  test    rcx, rcx
0x140910027  jnz     loc_140910102
0x14091002d  mov     r10, [rsp+0B8h+P]
0x140910035  test    r10, r10
0x140910038  jz      short loc_140910047
0x14091003a  mov     edx, 6370726Bh; Tag
0x14091003f  mov     rcx, r10; P
0x140910042  call    ExFreePoolWithTag
0x140910047  mov     rcx, [rsp+0B8h+var_68]
0x14091004c  test    rcx, rcx
0x14091004f  jz      short loc_14091005D
0x140910051  call    cs:__imp_MesHandleFree
0x140910058  nop     dword ptr [rax+rax+00h]
0x14091005d  mov     rcx, [rsp+0B8h+var_60]; P
0x140910062  test    rcx, rcx
0x140910065  jz      short loc_14091006C
0x140910067  call    PiPnpRtlEndOperation
0x14091006c  mov     [r14+30h], edi
0x140910070  xor     edx, edx; PriorityBoost
0x140910072  mov     rcx, r14; Irp
0x140910075  call    IofCompleteRequest
0x14091007a  mov     eax, edi
0x14091007c  add     rsp, 88h
0x140910083  pop     r15
0x140910085  pop     r14
0x140910087  pop     r13
0x140910089  pop     r12
0x14091008b  pop     rdi
0x14091008c  pop     rsi
0x14091008d  retn
0x14091008f  mov     eax, [rsi+20h]
0x140910092  neg     eax
0x140910094  sbb     ecx, ecx
0x140910096  and     edi, ecx
0x140910098  jmp     loc_14090FFF9
0x14091009d  mov     ecx, 100h; DesiredAccess
0x1409100a2  call    PiAuDoesClientHaveAccess
0x1409100a7  test    al, al
0x1409100a9  jz      short loc_1409100F8
0x1409100ab  test    dil, dil
0x1409100ae  jz      loc_14090FF68
0x1409100b4  lea     rax, [rsp+0B8h+arg_18]
0x1409100bc  mov     [rsp+0B8h+var_88], rax
0x1409100c1  mov     [rsp+0B8h+var_90], 0
0x1409100ca  mov     byte ptr [rsp+0B8h+var_98], r15b
0x1409100cf  mov     r9d, esi
0x1409100d2  mov     r8d, r13d
0x1409100d5  mov     rdx, [rsp+0B8h+P]
0x1409100dd  mov     rdx, [rdx+8]
0x1409100e1  mov     ecx, r15d
0x1409100e4  call    PiDqOpenObjectRegKey
0x1409100e9  mov     edi, eax
0x1409100eb  test    eax, eax
0x1409100ed  js      loc_14091000A
0x1409100f3  jmp     loc_14090FF68
0x1409100f8  mov     edi, 0C0000022h
0x1409100fd  jmp     loc_14091000A
0x140910102  call    ZwClose
0x140910107  jmp     loc_14091002D
0x140b44704  push    rbp
0x140b44706  sub     rsp, 50h
0x140b4470a  mov     rbp, rdx
0x140b4470d  mov     rcx, [rcx]
0x140b44710  mov     ecx, [rcx]; ExceptionCode
0x140b44712  call    cs:__imp_RpcExceptionFilter
0x140b44719  nop     dword ptr [rax+rax+00h]
0x140b4471e  nop
0x140b4471f  add     rsp, 50h
0x140b44723  pop     rbp
0x140b44724  retn
0x140b5b380  mov     dword ptr [rsp+0B8h+var_88], eax
0x140b5b384  mov     [rsp+0B8h+var_90], rcx
0x140b5b389  mov     dword ptr [rsp+0B8h+var_98], edx
0x140b5b38d  mov     r9, rsi
0x140b5b390  mov     rdx, [rsp+0B8h+arg_18]
0x140b5b398  mov     rcx, cs:PiPnpRtlCtx
0x140b5b39f  call    _PnpSetGenericStoreProperty
0x140b5b3a4  mov     edi, eax
0x140b5b3a6  test    eax, eax
0x140b5b3a8  js      loc_14090FFED
0x140b5b3ae  mov     [rsp+0B8h+var_58], 0
0x140b5b3b7  mov     rax, [rsi+18h]
0x140b5b3bb  mov     [rsp+0B8h+var_50], rax
0x140b5b3c0  mov     [rsp+0B8h+var_48], rsi
0x140b5b3c5  mov     dword ptr [rsp+0B8h+var_98], r15d
0x140b5b3ca  lea     r9, [rsp+0B8h+var_58]
0x140b5b3cf  mov     r8d, 4
0x140b5b3d5  mov     edx, r13d
0x140b5b3d8  mov     rcx, [rsp+0B8h+P]
0x140b5b3e0  mov     rcx, [rcx+8]
0x140b5b3e4  call    PiPnpRtlObjectEventWorker
0x140b5b3e9  nop
0x140b5b3ea  jmp     loc_14090FFED
```

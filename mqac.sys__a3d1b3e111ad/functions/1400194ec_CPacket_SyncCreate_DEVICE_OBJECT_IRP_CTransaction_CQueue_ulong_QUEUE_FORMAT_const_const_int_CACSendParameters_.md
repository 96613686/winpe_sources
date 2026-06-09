# CPacket::SyncCreate(_DEVICE_OBJECT *,_IRP *,CTransaction *,CQueue *,ulong,QUEUE_FORMAT const * const,int,CACSendParameters const *,ACSendParametersPointerContents const *,CQueue *,bool,CPacket * *)

- ea: `0x1400194ec`
- end: `0x1400195a6`
- name: `?SyncCreate@CPacket@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAVCTransaction@@PEAVCQueue@@KQEBUQUEUE_FORMAT@@HPEBVCACSendParameters@@PEBUACSendParametersPointerContents@@3_NPEAPEAV1@@Z`
- size: `186`
- prototype: `__int64 __usercall@<rax>(struct _DEVICE_OBJECT *@<rcx>, struct _IRP *@<rdx>, struct CTransaction *@<r8>, struct CQueue *@<r9>, unsigned int, const struct QUEUE_FORMAT *const, int, const struct CACSendParameters *, const struct ACSendParametersPointerContents *, struct CQueue *, bool, struct CPacket **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000dc20`
- `0x14001cd90`

## callees

- `0x140011d68`
- `0x1400126fc`
- `0x140012754`
- `0x140015084`
- `0x1400194ec`

## pseudocode

```c
__int64 __fastcall CPacket::SyncCreate(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        struct CTransaction *a3,
        struct CQueue *a4,
        unsigned int a5,
        const struct QUEUE_FORMAT *a6,
        int a7,
        const struct CACSendParameters *a8,
        const struct ACSendParametersPointerContents *a9,
        struct CQueue *a10,
        char a11,
        struct CPacket **a12)
{
  __int64 result; // rax
  struct CPacket *v15; // rbx

  result = CPacket::Create(a12, a1, a2, a7, a8, a9, a4, a5, a6, a11);
  if ( (int)result >= 0 )
  {
    v15 = *a12;
    if ( CIrp2Pkt::SafeAttachPacket(a2, *a12) )
    {
      CBaseObject::AddRef(v15);
      *((_QWORD *)v15 + 4) = a10;
      result = 0;
      *((_QWORD *)v15 + 5) = a3;
    }
    else
    {
      CBaseObject::Release(v15);
      result = 3221225626LL;
      *a12 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400194ec  mov     r11, rsp
0x1400194ef  push    rbx
0x1400194f0  push    rbp
0x1400194f1  push    rsi
0x1400194f2  push    rdi
0x1400194f3  sub     rsp, 58h
0x1400194f7  mov     al, [rsp+78h+arg_50]
0x1400194fe  mov     rbp, r8
0x140019501  mov     rdi, [rsp+78h+arg_58]
0x140019509  mov     rsi, rdx
0x14001950c  mov     [rsp+78h+var_30], al; bool
0x140019510  mov     r8, rdx; struct _IRP *
0x140019513  mov     rax, [rsp+78h+arg_28]
0x14001951b  mov     rdx, rcx; struct _DEVICE_OBJECT *
0x14001951e  mov     [r11-38h], rax
0x140019522  mov     rcx, rdi; struct CPacket **
0x140019525  mov     eax, [rsp+78h+arg_20]
0x14001952c  mov     [rsp+78h+var_40], eax; unsigned int
0x140019530  mov     rax, [rsp+78h+arg_40]
0x140019538  mov     [r11-48h], r9
0x14001953c  mov     r9d, [rsp+78h+arg_30]; int
0x140019544  mov     [r11-50h], rax
0x140019548  mov     rax, [rsp+78h+arg_38]
0x140019550  mov     [r11-58h], rax
0x140019554  call    ?Create@CPacket@@CAJPEAPEAV1@PEAU_DEVICE_OBJECT@@PEAU_IRP@@HPEBVCACSendParameters@@PEBUACSendParametersPointerContents@@PEBVCQueue@@KQEBUQUEUE_FORMAT@@_N@Z; CPacket::Create(CPacket * *,_DEVICE_OBJECT *,_IRP *,int,CACSendParameters const *,ACSendParametersPointerContents const *,CQueue const *,ulong,QUEUE_FORMAT const * const,bool)
0x140019559  test    eax, eax
0x14001955b  js      short loc_14001959C
0x14001955d  mov     rbx, [rdi]
0x140019560  mov     rcx, rsi; struct _IRP *
0x140019563  mov     rdx, rbx; struct CPacket *
0x140019566  call    ?SafeAttachPacket@CIrp2Pkt@@SA_NPEAU_IRP@@PEAVCPacket@@@Z; CIrp2Pkt::SafeAttachPacket(_IRP *,CPacket *)
0x14001956b  mov     rcx, rbx; this
0x14001956e  test    al, al
0x140019570  jnz     short loc_140019585
0x140019572  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140019577  mov     eax, 0C000009Ah
0x14001957c  mov     qword ptr [rdi], 0
0x140019583  jmp     short loc_14001959C
0x140019585  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x14001958a  mov     rax, [rsp+78h+arg_48]
0x140019592  mov     [rbx+20h], rax
0x140019596  xor     eax, eax
0x140019598  mov     [rbx+28h], rbp
0x14001959c  add     rsp, 58h
0x1400195a0  pop     rdi
0x1400195a1  pop     rsi
0x1400195a2  pop     rbp
0x1400195a3  pop     rbx
0x1400195a4  retn
```

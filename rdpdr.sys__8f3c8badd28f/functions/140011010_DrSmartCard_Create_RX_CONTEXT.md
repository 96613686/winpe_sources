# DrSmartCard::Create(_RX_CONTEXT *)

- ea: `0x140011010`
- end: `0x140011162`
- name: `?Create@DrSmartCard@@UEAAJPEAU_RX_CONTEXT@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(DrSmartCard *__hidden this, struct _RX_CONTEXT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140001660`
- `0x1400016a0`
- `0x140001830`
- `0x140001890`
- `0x140003940`
- `0x140011010`
- `0x140016420`
- `0x14002b530`
- `0x14002b698`

## import_xrefs

- `rdbss!RxCreateNetFobx` at `0x140011095`
- `rdbss!RxCreateNetFobx` at `0x140011095`

## pseudocode

```c
__int64 __fastcall DrSmartCard::Create(DrSmartCard *this, struct _RX_CONTEXT *a2)
{
  int *v2; // rbx
  PMRX_SRV_OPEN pRelevantSrvOpen; // r14
  struct _RX_CONTEXT *v6; // rdx
  DrDevice *v7; // rcx
  int Security; // edi
  struct _MRX_FOBX_ *NetFobx; // rax
  unsigned __int64 v10; // rdx
  void *v11; // rax
  __int64 v12; // rcx
  PMRX_FOBX pFobx; // rcx
  RefCount *v15; // [rsp+50h] [rbp+8h] BYREF
  DrSmartCard *v16; // [rsp+58h] [rbp+10h] BYREF
  int *v17; // [rsp+60h] [rbp+18h] BYREF

  v2 = (int *)*((_QWORD *)this + 4);
  pRelevantSrvOpen = a2->pRelevantSrvOpen;
  v17 = v2;
  if ( v2 )
    RefCount::AddRef((RefCount *)v2);
  v15 = 0;
  v16 = this;
  RefCount::AddRef(this);
  Security = DrDevice::VerifyCreateSecurity(v7, v6, v2[282]);
  if ( (Security & 0xC0000000) != 0xC0000000 )
  {
    if ( Security >= 0 )
    {
      LODWORD(pRelevantSrvOpen->Key) |= 3u;
      NetFobx = RxCreateNetFobx(a2, a2->pRelevantSrvOpen);
      a2->pFobx = NetFobx;
      if ( NetFobx )
      {
        RefCount::AddRef(this);
        a2->pFobx->UnicodeQueryTemplate.Buffer = (wchar_t *)this;
        v11 = TopObj::operator new(0xD8u, v10);
        if ( v11 )
          v11 = (void *)DrFile::DrFile(v11, &v16, 1);
        SmartPtr<VirtualChannel>::operator=(&v15, v11);
        if ( v15 )
        {
          Security = 0;
          RefCount::AddRef(v15);
          *(_QWORD *)&a2->pFobx->OffsetOfNextEaToReturn = v12;
          _InterlockedIncrement((volatile signed __int32 *)this + 16);
          DrDevice::FinishCreate(this, a2);
LABEL_14:
          SmartPtr<DrFile>::~SmartPtr<DrFile>(&v16);
          SmartPtr<DrFile>::~SmartPtr<DrFile>(&v15);
          SmartPtr<DrFile>::~SmartPtr<DrFile>(&v17);
          return (unsigned int)Security;
        }
      }
      Security = -1073741670;
    }
    pFobx = a2->pFobx;
    if ( pFobx )
    {
      RefCount::Release((RefCount *)pFobx->UnicodeQueryTemplate.Buffer);
      a2->pFobx->UnicodeQueryTemplate.Buffer = 0;
    }
    goto LABEL_14;
  }
  RefCount::Release(this);
  RefCount::Release((RefCount *)v2);
  return (unsigned int)Security;
}

```

## disassembly

```asm
0x140011010  push    rbx
0x140011012  push    rbp
0x140011013  push    rsi
0x140011014  push    rdi
0x140011015  push    r14
0x140011017  sub     rsp, 20h
0x14001101b  mov     rbx, [rcx+20h]
0x14001101f  mov     rsi, rdx
0x140011022  mov     r14, [rdx+48h]
0x140011026  mov     rbp, rcx
0x140011029  mov     [rsp+48h+arg_10], rbx
0x14001102e  test    rbx, rbx
0x140011031  jz      short loc_14001103B
0x140011033  mov     rcx, rbx; this
0x140011036  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001103b  mov     rcx, rbp; this
0x14001103e  mov     [rsp+48h+arg_0], 0
0x140011047  mov     [rsp+48h+arg_8], rbp
0x14001104c  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140011051  mov     r8d, [rbx+468h]; unsigned int
0x140011058  call    ?VerifyCreateSecurity@DrDevice@@IEAAJPEAU_RX_CONTEXT@@K@Z; DrDevice::VerifyCreateSecurity(_RX_CONTEXT *,ulong)
0x14001105d  mov     ecx, eax
0x14001105f  mov     edi, eax
0x140011061  mov     eax, 0C0000000h
0x140011066  and     ecx, eax
0x140011068  cmp     ecx, eax
0x14001106a  jnz     short loc_140011081
0x14001106c  mov     rcx, rbp; this
0x14001106f  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140011074  mov     rcx, rbx; this
0x140011077  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14001107c  jmp     loc_140011154
0x140011081  test    edi, edi
0x140011083  js      loc_140011118
0x140011089  or      dword ptr [r14+48h], 3
0x14001108e  mov     rcx, rsi; RxContext
0x140011091  mov     rdx, [rsi+48h]; MrxSrvOpen
0x140011095  call    cs:__imp_RxCreateNetFobx
0x14001109c  nop     dword ptr [rax+rax+00h]
0x1400110a1  mov     [rsi+40h], rax
0x1400110a5  test    rax, rax
0x1400110a8  jz      short loc_140011113
0x1400110aa  mov     rcx, rbp; this
0x1400110ad  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400110b2  mov     rax, [rsi+40h]
0x1400110b6  mov     ecx, 0D8h; unsigned __int64
0x1400110bb  mov     [rax+38h], rbp
0x1400110bf  call    ??2TopObj@@SAPEAX_K0@Z; TopObj::operator new(unsigned __int64,unsigned __int64)
0x1400110c4  test    rax, rax
0x1400110c7  jz      short loc_1400110DC
0x1400110c9  mov     r8d, 1
0x1400110cf  lea     rdx, [rsp+48h+arg_8]
0x1400110d4  mov     rcx, rax
0x1400110d7  call    ??0DrFile@@QEAA@AEAV?$SmartPtr@VDrDevice@@@@K@Z; DrFile::DrFile(SmartPtr<DrDevice> &,ulong)
0x1400110dc  mov     rdx, rax
0x1400110df  lea     rcx, [rsp+48h+arg_0]
0x1400110e4  call    ??4?$SmartPtr@VVirtualChannel@@@@QEAAAEAV0@PEAVVirtualChannel@@@Z; SmartPtr<VirtualChannel>::operator=(VirtualChannel *)
0x1400110e9  mov     rcx, [rsp+48h+arg_0]; this
0x1400110ee  test    rcx, rcx
0x1400110f1  jz      short loc_140011113
0x1400110f3  xor     edi, edi
0x1400110f5  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400110fa  mov     rax, [rsi+40h]
0x1400110fe  mov     [rax+40h], rcx
0x140011102  lock inc dword ptr [rbp+40h]
0x140011106  mov     rdx, rsi; struct _RX_CONTEXT *
0x140011109  mov     rcx, rbp; this
0x14001110c  call    ?FinishCreate@DrDevice@@IEAAXPEAU_RX_CONTEXT@@@Z; DrDevice::FinishCreate(_RX_CONTEXT *)
0x140011111  jmp     short loc_140011136
0x140011113  mov     edi, 0C000009Ah
0x140011118  mov     rcx, [rsi+40h]
0x14001111c  test    rcx, rcx
0x14001111f  jz      short loc_140011136
0x140011121  mov     rcx, [rcx+38h]; this
0x140011125  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14001112a  mov     rax, [rsi+40h]
0x14001112e  mov     qword ptr [rax+38h], 0
0x140011136  lea     rcx, [rsp+48h+arg_8]
0x14001113b  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140011140  lea     rcx, [rsp+48h+arg_0]
0x140011145  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001114a  lea     rcx, [rsp+48h+arg_10]
0x14001114f  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140011154  mov     eax, edi
0x140011156  add     rsp, 20h
0x14001115a  pop     r14
0x14001115c  pop     rdi
0x14001115d  pop     rsi
0x14001115e  pop     rbp
0x14001115f  pop     rbx
0x140011160  retn
```

# DrDevice::FinishCreate(_RX_CONTEXT *)

- ea: `0x14002b530`
- end: `0x14002b68f`
- name: `?FinishCreate@DrDevice@@IEAAXPEAU_RX_CONTEXT@@@Z`
- size: `351`
- prototype: `void(DrDevice *__hidden this, struct _RX_CONTEXT *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140011010`
- `0x14002b120`

## callees

- `0x140001660`
- `0x140001890`
- `0x1400068c0`
- `0x14002b530`

## import_xrefs

- `rdbss!RxInferFileType` at `0x14002b636`
- `rdbss!RxInferFileType` at `0x14002b636`
- `rdbss!RxFinishFcbInitialization` at `0x14002b66c`
- `rdbss!RxFinishFcbInitialization` at `0x14002b66c`

## pseudocode

```c
void __fastcall DrDevice::FinishCreate(DrDevice *this, struct _RX_CONTEXT *a2)
{
  unsigned __int16 *v2; // rbx
  PMRX_FCB pFcb; // rsi
  RX_FILE_TYPE v5; // eax
  unsigned __int16 NodeTypeCode; // ax
  __int64 v7; // [rsp+20h] [rbp-49h] BYREF
  __int64 v8; // [rsp+28h] [rbp-41h] BYREF
  __int64 v9; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int64 v10; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int64 v11; // [rsp+40h] [rbp-29h] BYREF
  _BYTE InitPacket[80]; // [rsp+50h] [rbp-19h] BYREF
  int v13; // [rsp+D0h] [rbp+67h] BYREF
  int v14; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v15; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v16; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = (unsigned __int16 *)*((_QWORD *)this + 4);
  pFcb = a2->pFcb;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  memset(InitPacket, 0, sizeof(InitPacket));
  if ( v2 )
    RefCount::AddRef((RefCount *)v2);
  *(_DWORD *)InitPacket = 0;
  *(_QWORD *)&InitPacket[8] = &v13;
  *(_QWORD *)&InitPacket[16] = &v14;
  *(_QWORD *)&InitPacket[24] = &v15;
  *(_QWORD *)&InitPacket[32] = &v16;
  *(_QWORD *)&InitPacket[40] = &v7;
  *(_QWORD *)&InitPacket[48] = &v8;
  *(_QWORD *)&InitPacket[56] = &v9;
  *(_QWORD *)&InitPacket[64] = &v10;
  *(_QWORD *)&InitPacket[72] = &v11;
  v15 = 0;
  v16 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = (((__int64)(((v2[566] << 16) | v2[567]) - 65549) >> 63) & 0x8000000080000000uLL) + 0x7FFFFFFFFFFFFFFFLL;
  v11 = v10;
  v5 = RxInferFileType(a2);
  if ( v5 )
  {
    NodeTypeCode = v5 - 5088;
  }
  else
  {
    NodeTypeCode = pFcb->Header.NodeTypeCode;
    if ( pFcb->Header.NodeTypeCode == -5088 )
      NodeTypeCode = -5086;
  }
  RxFinishFcbInitialization(pFcb, (RX_FILE_TYPE)NodeTypeCode, (PFCB_INIT_PACKET)InitPacket);
  RefCount::Release((RefCount *)v2);
}

```

## disassembly

```asm
0x14002b530  push    rbp
0x14002b532  push    rbx
0x14002b533  push    rsi
0x14002b534  push    rdi
0x14002b535  push    r14
0x14002b537  lea     rbp, [rsp-37h]
0x14002b53c  sub     rsp, 0A0h
0x14002b543  mov     rbx, [rcx+20h]
0x14002b547  xor     r14d, r14d
0x14002b54a  mov     rsi, [rdx+38h]
0x14002b54e  lea     rcx, [rbp+57h+InitPacket]; void *
0x14002b552  mov     rdi, rdx
0x14002b555  mov     [rbp+57h+arg_0], r14d
0x14002b559  xor     edx, edx; Val
0x14002b55b  mov     [rbp+57h+arg_8], r14d
0x14002b55f  mov     r8d, 50h ; 'P'; Size
0x14002b565  mov     [rbp+57h+arg_10], r14
0x14002b569  mov     [rbp+57h+arg_18], r14
0x14002b56d  mov     [rbp+57h+var_A0], r14
0x14002b571  mov     [rbp+57h+var_98], r14
0x14002b575  mov     [rbp+57h+var_90], r14
0x14002b579  mov     [rbp+57h+var_88], r14
0x14002b57d  mov     [rbp+57h+var_80], r14
0x14002b581  call    memset
0x14002b586  test    rbx, rbx
0x14002b589  jz      short loc_14002B593
0x14002b58b  mov     rcx, rbx; this
0x14002b58e  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14002b593  mov     dword ptr [rbp+57h+InitPacket.pAttributes], r14d
0x14002b597  lea     rax, [rbp+57h+arg_0]
0x14002b59b  mov     [rbp+57h+InitPacket.pNumLinks], rax
0x14002b59f  lea     rax, [rbp+57h+arg_8]
0x14002b5a3  mov     [rbp+57h+InitPacket.pCreationTime], rax
0x14002b5a7  lea     rax, [rbp+57h+arg_10]
0x14002b5ab  mov     [rbp+57h+InitPacket.pLastAccessTime], rax
0x14002b5af  lea     rax, [rbp+57h+arg_18]
0x14002b5b3  mov     [rbp+57h+InitPacket.pLastWriteTime], rax
0x14002b5b7  lea     rax, [rbp+57h+var_A0]
0x14002b5bb  mov     [rbp+57h+InitPacket.pLastChangeTime], rax
0x14002b5bf  lea     rax, [rbp+57h+var_98]
0x14002b5c3  mov     [rbp+57h+InitPacket.pAllocationSize], rax
0x14002b5c7  lea     rax, [rbp+57h+var_90]
0x14002b5cb  mov     [rbp+57h+InitPacket.pFileSize], rax
0x14002b5cf  lea     rax, [rbp+57h+var_88]
0x14002b5d3  mov     [rbp+57h+InitPacket.pValidDataLength], rax
0x14002b5d7  lea     rax, [rbp+57h+var_80]
0x14002b5db  mov     [rbp+57h+var_28], rax
0x14002b5df  mov     [rbp+57h+arg_10], r14
0x14002b5e3  mov     [rbp+57h+arg_18], r14
0x14002b5e7  mov     [rbp+57h+var_A0], r14
0x14002b5eb  mov     [rbp+57h+var_98], r14
0x14002b5ef  mov     [rbp+57h+var_90], r14
0x14002b5f3  movzx   ecx, word ptr [rbx+46Ch]
0x14002b5fa  movzx   eax, word ptr [rbx+46Eh]
0x14002b601  shl     ecx, 10h
0x14002b604  or      eax, ecx
0x14002b606  mov     rcx, 8000000080000000h
0x14002b610  sub     eax, 1000Dh
0x14002b615  cdqe
0x14002b617  sar     rax, 3Fh
0x14002b61b  and     rax, rcx
0x14002b61e  mov     rcx, 7FFFFFFFFFFFFFFFh
0x14002b628  add     rax, rcx
0x14002b62b  mov     rcx, rdi; RxContext
0x14002b62e  mov     [rbp+57h+var_88], rax
0x14002b632  mov     [rbp+57h+var_80], rax
0x14002b636  call    cs:__imp_RxInferFileType
0x14002b63d  nop     dword ptr [rax+rax+00h]
0x14002b642  test    eax, eax
0x14002b644  jnz     short loc_14002B65A
0x14002b646  movzx   eax, word ptr [rsi]
0x14002b649  mov     ecx, 0EC20h
0x14002b64e  cmp     cx, ax
0x14002b651  jnz     short loc_14002B662
0x14002b653  mov     eax, 0EC22h
0x14002b658  jmp     short loc_14002B662
0x14002b65a  mov     ecx, 13E0h
0x14002b65f  sub     ax, cx
0x14002b662  movzx   edx, ax; FileType
0x14002b665  lea     r8, [rbp+57h+InitPacket]; InitPacket
0x14002b669  mov     rcx, rsi; Fcb
0x14002b66c  call    cs:__imp_RxFinishFcbInitialization
0x14002b673  nop     dword ptr [rax+rax+00h]
0x14002b678  mov     rcx, rbx; this
0x14002b67b  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002b680  add     rsp, 0A0h
0x14002b687  pop     r14
0x14002b689  pop     rdi
0x14002b68a  pop     rsi
0x14002b68b  pop     rbx
0x14002b68c  pop     rbp
0x14002b68d  retn
```

# CDescriptor::Copy(CDescriptor *)

- ea: `0x18000a484`
- end: `0x18000a57e`
- name: `?Copy@CDescriptor@@QEAAXPEAV1@@Z`
- size: `250`
- prototype: `void __fastcall(CDescriptor *__hidden this, struct CDescriptor *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800085b0`
- `0x18000a060`
- `0x18000bbc4`

## callees

- `0x1800019a0`
- `0x18000a2a4`
- `0x18000a484`
- `0x18000c14c`
- `0x18000c290`
- `0x18000c3f0`
- `0x18000c494`

## pseudocode

```c
void __fastcall CDescriptor::Copy(CDescriptor *this, struct CDescriptor *a2)
{
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *(_OWORD *)((char *)this + 12) = *(_OWORD *)((char *)a2 + 12);
  *(_OWORD *)((char *)this + 28) = *(_OWORD *)((char *)a2 + 28);
  *(_QWORD *)((char *)this + 44) = *(_QWORD *)((char *)a2 + 44);
  *(_QWORD *)((char *)this + 52) = *(_QWORD *)((char *)a2 + 52);
  *(_QWORD *)this = *(_QWORD *)a2;
  *((_QWORD *)this + 12) = *((_QWORD *)a2 + 12);
  v4 = (void *)*((_QWORD *)this + 8);
  if ( v4 )
    operator delete(v4);
  *((_DWORD *)this + 2) &= ~4u;
  *((_QWORD *)this + 8) = 0;
  if ( (*((_BYTE *)a2 + 8) & 4) != 0 )
    CDescriptor::SetName(this, *((unsigned __int16 **)a2 + 8));
  v5 = (void *)*((_QWORD *)this + 9);
  if ( v5 )
    operator delete(v5);
  *((_DWORD *)this + 2) &= ~8u;
  *((_QWORD *)this + 9) = 0;
  if ( (*((_BYTE *)a2 + 8) & 8) != 0 )
    CDescriptor::SetCategory(this, *((unsigned __int16 **)a2 + 9));
  v6 = (void *)*((_QWORD *)this + 10);
  if ( v6 )
    operator delete(v6);
  *((_DWORD *)this + 2) &= ~0x10u;
  *((_QWORD *)this + 10) = 0;
  if ( (*((_BYTE *)a2 + 8) & 0x10) != 0 )
    CDescriptor::SetFileName(this, *((unsigned __int16 **)a2 + 10));
  CDescriptor::ClearIStream(this);
  if ( (*((_DWORD *)a2 + 2) & 0x800) != 0 )
  {
    CDescriptor::SetIStream(this, *((struct IStream **)a2 + 13));
    *((_QWORD *)this + 14) = *((_QWORD *)a2 + 14);
  }
}

```

## disassembly

```asm
0x18000a484  mov     [rsp+arg_0], rbx
0x18000a489  push    rdi
0x18000a48a  sub     rsp, 20h
0x18000a48e  mov     eax, [rdx+8]
0x18000a491  mov     rbx, rcx
0x18000a494  mov     [rcx+8], eax
0x18000a497  mov     rdi, rdx
0x18000a49a  movups  xmm0, xmmword ptr [rdx+0Ch]
0x18000a49e  movdqu  xmmword ptr [rcx+0Ch], xmm0
0x18000a4a3  movups  xmm1, xmmword ptr [rdx+1Ch]
0x18000a4a7  movdqu  xmmword ptr [rcx+1Ch], xmm1
0x18000a4ac  mov     rax, [rdx+2Ch]
0x18000a4b0  mov     [rcx+2Ch], rax
0x18000a4b4  mov     rax, [rdx+34h]
0x18000a4b8  mov     [rcx+34h], rax
0x18000a4bc  mov     rax, [rdx]
0x18000a4bf  mov     [rcx], rax
0x18000a4c2  mov     rax, [rdx+60h]
0x18000a4c6  mov     [rcx+60h], rax
0x18000a4ca  mov     rcx, [rcx+40h]; void *
0x18000a4ce  test    rcx, rcx
0x18000a4d1  jz      short loc_18000A4D8
0x18000a4d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a4d8  and     dword ptr [rbx+8], 0FFFFFFFBh
0x18000a4dc  mov     qword ptr [rbx+40h], 0
0x18000a4e4  test    byte ptr [rdi+8], 4
0x18000a4e8  jz      short loc_18000A4F6
0x18000a4ea  mov     rdx, [rdi+40h]; unsigned __int16 *
0x18000a4ee  mov     rcx, rbx; this
0x18000a4f1  call    ?SetName@CDescriptor@@QEAAXPEAG@Z; CDescriptor::SetName(ushort *)
0x18000a4f6  mov     rcx, [rbx+48h]; void *
0x18000a4fa  test    rcx, rcx
0x18000a4fd  jz      short loc_18000A504
0x18000a4ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a504  and     dword ptr [rbx+8], 0FFFFFFF7h
0x18000a508  mov     qword ptr [rbx+48h], 0
0x18000a510  test    byte ptr [rdi+8], 8
0x18000a514  jz      short loc_18000A522
0x18000a516  mov     rdx, [rdi+48h]; unsigned __int16 *
0x18000a51a  mov     rcx, rbx; this
0x18000a51d  call    ?SetCategory@CDescriptor@@QEAAXPEAG@Z; CDescriptor::SetCategory(ushort *)
0x18000a522  mov     rcx, [rbx+50h]; void *
0x18000a526  test    rcx, rcx
0x18000a529  jz      short loc_18000A530
0x18000a52b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a530  and     dword ptr [rbx+8], 0FFFFFFEFh
0x18000a534  mov     qword ptr [rbx+50h], 0
0x18000a53c  test    byte ptr [rdi+8], 10h
0x18000a540  jz      short loc_18000A54E
0x18000a542  mov     rdx, [rdi+50h]; unsigned __int16 *
0x18000a546  mov     rcx, rbx; this
0x18000a549  call    ?SetFileName@CDescriptor@@QEAAJPEAG@Z; CDescriptor::SetFileName(ushort *)
0x18000a54e  mov     rcx, rbx; this
0x18000a551  call    ?ClearIStream@CDescriptor@@QEAAXXZ; CDescriptor::ClearIStream(void)
0x18000a556  test    dword ptr [rdi+8], 800h
0x18000a55d  jz      short loc_18000A573
0x18000a55f  mov     rdx, [rdi+68h]; struct IStream *
0x18000a563  mov     rcx, rbx; this
0x18000a566  call    ?SetIStream@CDescriptor@@QEAAXPEAUIStream@@@Z; CDescriptor::SetIStream(IStream *)
0x18000a56b  mov     rax, [rdi+70h]
0x18000a56f  mov     [rbx+70h], rax
0x18000a573  mov     rbx, [rsp+28h+arg_0]
0x18000a578  add     rsp, 20h
0x18000a57c  pop     rdi
0x18000a57d  retn
```

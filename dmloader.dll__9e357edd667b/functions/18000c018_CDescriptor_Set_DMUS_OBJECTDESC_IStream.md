# CDescriptor::Set(_DMUS_OBJECTDESC *,IStream *)

- ea: `0x18000c018`
- end: `0x18000c146`
- name: `?Set@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@PEAUIStream@@@Z`
- size: `302`
- prototype: `void __fastcall(CDescriptor *__hidden this, struct _DMUS_OBJECTDESC *, struct IStream *)`
- caller_count: `10`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800080f0`
- `0x180008710`
- `0x180008bc0`
- `0x180008e90`
- `0x180009b20`
- `0x18000ae74`
- `0x18000b45c`
- `0x18000b668`
- `0x18000b81c`
- `0x18000bbc4`

## callees

- `0x1800019a0`
- `0x18000a2a4`
- `0x18000c018`
- `0x18000c14c`
- `0x18000c290`
- `0x18000c3f0`
- `0x18000c494`

## pseudocode

```c
void __fastcall CDescriptor::Set(CDescriptor *this, struct _DMUS_OBJECTDESC *a2, struct IStream *a3)
{
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 12) = *(_OWORD *)((char *)a2 + 8);
  *(_OWORD *)((char *)this + 28) = *(_OWORD *)((char *)a2 + 24);
  *(_QWORD *)((char *)this + 44) = *((_QWORD *)a2 + 5);
  *(_QWORD *)((char *)this + 52) = *((_QWORD *)a2 + 6);
  *(_QWORD *)this = *((_QWORD *)a2 + 104);
  *((_QWORD *)this + 12) = *((_QWORD *)a2 + 105);
  v6 = (void *)*((_QWORD *)this + 8);
  if ( v6 )
    operator delete(v6);
  *((_DWORD *)this + 2) &= ~4u;
  *((_QWORD *)this + 8) = 0;
  if ( (*((_BYTE *)a2 + 4) & 4) != 0 )
  {
    *((_WORD *)a2 + 91) = 0;
    CDescriptor::SetName(this, (unsigned __int16 *)a2 + 28);
  }
  v7 = (void *)*((_QWORD *)this + 9);
  if ( v7 )
    operator delete(v7);
  *((_DWORD *)this + 2) &= ~8u;
  *((_QWORD *)this + 9) = 0;
  if ( (*((_BYTE *)a2 + 4) & 8) != 0 )
  {
    *((_WORD *)a2 + 155) = 0;
    CDescriptor::SetCategory(this, (unsigned __int16 *)a2 + 92);
  }
  v8 = (void *)*((_QWORD *)this + 10);
  if ( v8 )
    operator delete(v8);
  *((_DWORD *)this + 2) &= ~0x10u;
  *((_QWORD *)this + 10) = 0;
  if ( (*((_BYTE *)a2 + 4) & 0x10) != 0 )
  {
    *((_WORD *)a2 + 415) = 0;
    CDescriptor::SetFileName(this, (unsigned __int16 *)a2 + 156);
  }
  CDescriptor::ClearIStream(this);
  if ( (*((_DWORD *)a2 + 1) & 0x800) != 0 )
  {
    CDescriptor::SetIStream(this, *((struct IStream **)a2 + 106));
    *((_QWORD *)this + 14) = a3;
  }
}

```

## disassembly

```asm
0x18000c018  mov     [rsp+arg_0], rbx
0x18000c01d  mov     [rsp+arg_8], rsi
0x18000c022  push    rdi
0x18000c023  sub     rsp, 20h
0x18000c027  mov     eax, [rdx+4]
0x18000c02a  mov     rbx, rcx
0x18000c02d  mov     [rcx+8], eax
0x18000c030  mov     rsi, r8
0x18000c033  movups  xmm0, xmmword ptr [rdx+8]
0x18000c037  mov     rdi, rdx
0x18000c03a  movdqu  xmmword ptr [rcx+0Ch], xmm0
0x18000c03f  movups  xmm1, xmmword ptr [rdx+18h]
0x18000c043  movdqu  xmmword ptr [rcx+1Ch], xmm1
0x18000c048  mov     rax, [rdx+28h]
0x18000c04c  mov     [rcx+2Ch], rax
0x18000c050  mov     rax, [rdx+30h]
0x18000c054  mov     [rcx+34h], rax
0x18000c058  mov     rax, [rdx+340h]
0x18000c05f  mov     [rcx], rax
0x18000c062  mov     rax, [rdx+348h]
0x18000c069  mov     [rcx+60h], rax
0x18000c06d  mov     rcx, [rcx+40h]; void *
0x18000c071  test    rcx, rcx
0x18000c074  jz      short loc_18000C07B
0x18000c076  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c07b  and     dword ptr [rbx+8], 0FFFFFFFBh
0x18000c07f  mov     qword ptr [rbx+40h], 0
0x18000c087  test    byte ptr [rdi+4], 4
0x18000c08b  jz      short loc_18000C0A2
0x18000c08d  xor     eax, eax
0x18000c08f  lea     rdx, [rdi+38h]; unsigned __int16 *
0x18000c093  mov     rcx, rbx; this
0x18000c096  mov     [rdi+0B6h], ax
0x18000c09d  call    ?SetName@CDescriptor@@QEAAXPEAG@Z; CDescriptor::SetName(ushort *)
0x18000c0a2  mov     rcx, [rbx+48h]; void *
0x18000c0a6  test    rcx, rcx
0x18000c0a9  jz      short loc_18000C0B0
0x18000c0ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c0b0  and     dword ptr [rbx+8], 0FFFFFFF7h
0x18000c0b4  mov     qword ptr [rbx+48h], 0
0x18000c0bc  test    byte ptr [rdi+4], 8
0x18000c0c0  jz      short loc_18000C0DA
0x18000c0c2  xor     eax, eax
0x18000c0c4  lea     rdx, [rdi+0B8h]; unsigned __int16 *
0x18000c0cb  mov     rcx, rbx; this
0x18000c0ce  mov     [rdi+136h], ax
0x18000c0d5  call    ?SetCategory@CDescriptor@@QEAAXPEAG@Z; CDescriptor::SetCategory(ushort *)
0x18000c0da  mov     rcx, [rbx+50h]; void *
0x18000c0de  test    rcx, rcx
0x18000c0e1  jz      short loc_18000C0E8
0x18000c0e3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c0e8  and     dword ptr [rbx+8], 0FFFFFFEFh
0x18000c0ec  mov     qword ptr [rbx+50h], 0
0x18000c0f4  test    byte ptr [rdi+4], 10h
0x18000c0f8  jz      short loc_18000C112
0x18000c0fa  xor     eax, eax
0x18000c0fc  lea     rdx, [rdi+138h]; unsigned __int16 *
0x18000c103  mov     rcx, rbx; this
0x18000c106  mov     [rdi+33Eh], ax
0x18000c10d  call    ?SetFileName@CDescriptor@@QEAAJPEAG@Z; CDescriptor::SetFileName(ushort *)
0x18000c112  mov     rcx, rbx; this
0x18000c115  call    ?ClearIStream@CDescriptor@@QEAAXXZ; CDescriptor::ClearIStream(void)
0x18000c11a  test    dword ptr [rdi+4], 800h
0x18000c121  jz      short loc_18000C136
0x18000c123  mov     rdx, [rdi+350h]; struct IStream *
0x18000c12a  mov     rcx, rbx; this
0x18000c12d  call    ?SetIStream@CDescriptor@@QEAAXPEAUIStream@@@Z; CDescriptor::SetIStream(IStream *)
0x18000c132  mov     [rbx+70h], rsi
0x18000c136  mov     rbx, [rsp+28h+arg_0]
0x18000c13b  mov     rsi, [rsp+28h+arg_8]
0x18000c140  add     rsp, 20h
0x18000c144  pop     rdi
0x18000c145  retn
```

# CDescriptor::Merge(CDescriptor *)

- ea: `0x18000b358`
- end: `0x18000b454`
- name: `?Merge@CDescriptor@@QEAAXPEAV1@@Z`
- size: `252`
- prototype: `void __fastcall(CDescriptor *__hidden this, struct CDescriptor *)`
- caller_count: `7`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008e90`
- `0x180009b20`
- `0x18000ae74`
- `0x18000b45c`
- `0x18000b668`
- `0x18000b81c`
- `0x18000bbc4`

## callees

- `0x18000b358`
- `0x18000c14c`
- `0x18000c290`
- `0x18000c3f0`
- `0x18000c494`

## pseudocode

```c
void __fastcall CDescriptor::Merge(CDescriptor *this, struct CDescriptor *a2)
{
  _DWORD *v2; // rbx
  __int64 v5; // rcx
  __int64 v6; // rax

  v2 = (_DWORD *)((char *)this + 8);
  if ( (*((_BYTE *)a2 + 8) & 1) != 0 )
  {
    *v2 |= 1u;
    *(_OWORD *)((char *)this + 12) = *(_OWORD *)((char *)a2 + 12);
  }
  if ( (*((_BYTE *)a2 + 8) & 2) != 0 )
  {
    *v2 |= 2u;
    *(_OWORD *)((char *)this + 28) = *(_OWORD *)((char *)a2 + 28);
  }
  if ( (*((_BYTE *)a2 + 8) & 4) != 0 )
  {
    *v2 |= 4u;
    CDescriptor::SetName(this, *((unsigned __int16 **)a2 + 8));
  }
  if ( (*((_BYTE *)a2 + 8) & 8) != 0 )
  {
    *v2 |= 8u;
    CDescriptor::SetCategory(this, *((unsigned __int16 **)a2 + 9));
  }
  if ( *((char *)a2 + 8) < 0 )
  {
    *v2 |= 0x80u;
    *(_QWORD *)((char *)this + 52) = *(_QWORD *)((char *)a2 + 52);
  }
  if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 )
  {
    *v2 |= 0x100u;
    *(_QWORD *)((char *)this + 44) = *(_QWORD *)((char *)a2 + 44);
  }
  if ( (*((_BYTE *)a2 + 8) & 0x10) != 0
    && (*(_BYTE *)v2 & 0x10) == 0
    && (int)CDescriptor::SetFileName(this, *((unsigned __int16 **)a2 + 10)) >= 0 )
  {
    *v2 |= *((_DWORD *)a2 + 2) & 0x70;
  }
  if ( (*((_DWORD *)a2 + 2) & 0x400) != 0 )
  {
    v5 = *((_QWORD *)a2 + 12);
    *((_QWORD *)this + 12) = v5;
    v6 = *(_QWORD *)a2;
    *(_QWORD *)this = *(_QWORD *)a2;
    if ( v6 && v5 )
      *v2 |= 0x400u;
    else
      *v2 &= ~0x400u;
  }
  if ( (*((_DWORD *)a2 + 2) & 0x800) != 0 )
    CDescriptor::SetIStream(this, *((struct IStream **)a2 + 13));
}

```

## disassembly

```asm
0x18000b358  mov     [rsp+arg_0], rbx
0x18000b35d  mov     [rsp+arg_8], rsi
0x18000b362  push    rdi
0x18000b363  sub     rsp, 20h
0x18000b367  test    byte ptr [rdx+8], 1
0x18000b36b  lea     rbx, [rcx+8]
0x18000b36f  mov     rdi, rdx
0x18000b372  mov     rsi, rcx
0x18000b375  jz      short loc_18000B383
0x18000b377  or      dword ptr [rbx], 1
0x18000b37a  movups  xmm0, xmmword ptr [rdx+0Ch]
0x18000b37e  movdqu  xmmword ptr [rcx+0Ch], xmm0
0x18000b383  test    byte ptr [rdx+8], 2
0x18000b387  jz      short loc_18000B395
0x18000b389  or      dword ptr [rbx], 2
0x18000b38c  movups  xmm0, xmmword ptr [rdx+1Ch]
0x18000b390  movdqu  xmmword ptr [rcx+1Ch], xmm0
0x18000b395  test    byte ptr [rdx+8], 4
0x18000b399  jz      short loc_18000B3A7
0x18000b39b  or      dword ptr [rbx], 4
0x18000b39e  mov     rdx, [rdx+40h]; unsigned __int16 *
0x18000b3a2  call    ?SetName@CDescriptor@@QEAAXPEAG@Z; CDescriptor::SetName(ushort *)
0x18000b3a7  test    byte ptr [rdi+8], 8
0x18000b3ab  jz      short loc_18000B3BC
0x18000b3ad  or      dword ptr [rbx], 8
0x18000b3b0  mov     rcx, rsi; this
0x18000b3b3  mov     rdx, [rdi+48h]; unsigned __int16 *
0x18000b3b7  call    ?SetCategory@CDescriptor@@QEAAXPEAG@Z; CDescriptor::SetCategory(ushort *)
0x18000b3bc  test    byte ptr [rdi+8], 80h
0x18000b3c0  jz      short loc_18000B3CE
0x18000b3c2  bts     dword ptr [rbx], 7
0x18000b3c6  mov     rax, [rdi+34h]
0x18000b3ca  mov     [rsi+34h], rax
0x18000b3ce  mov     eax, 100h
0x18000b3d3  test    [rdi+8], eax
0x18000b3d6  jz      short loc_18000B3E2
0x18000b3d8  or      [rbx], eax
0x18000b3da  mov     rax, [rdi+2Ch]
0x18000b3de  mov     [rsi+2Ch], rax
0x18000b3e2  test    byte ptr [rdi+8], 10h
0x18000b3e6  jz      short loc_18000B405
0x18000b3e8  test    byte ptr [rbx], 10h
0x18000b3eb  jnz     short loc_18000B405
0x18000b3ed  mov     rdx, [rdi+50h]; unsigned __int16 *
0x18000b3f1  mov     rcx, rsi; this
0x18000b3f4  call    ?SetFileName@CDescriptor@@QEAAJPEAG@Z; CDescriptor::SetFileName(ushort *)
0x18000b3f9  test    eax, eax
0x18000b3fb  js      short loc_18000B405
0x18000b3fd  mov     eax, [rdi+8]
0x18000b400  and     eax, 70h
0x18000b403  or      [rbx], eax
0x18000b405  mov     edx, 400h
0x18000b40a  test    [rdi+8], edx
0x18000b40d  jz      short loc_18000B42F
0x18000b40f  mov     rcx, [rdi+60h]
0x18000b413  mov     [rsi+60h], rcx
0x18000b417  mov     rax, [rdi]
0x18000b41a  mov     [rsi], rax
0x18000b41d  test    rax, rax
0x18000b420  jz      short loc_18000B42B
0x18000b422  test    rcx, rcx
0x18000b425  jz      short loc_18000B42B
0x18000b427  or      [rbx], edx
0x18000b429  jmp     short loc_18000B42F
0x18000b42b  btr     dword ptr [rbx], 0Ah
0x18000b42f  test    dword ptr [rdi+8], 800h
0x18000b436  jz      short loc_18000B444
0x18000b438  mov     rdx, [rdi+68h]; struct IStream *
0x18000b43c  mov     rcx, rsi; this
0x18000b43f  call    ?SetIStream@CDescriptor@@QEAAXPEAUIStream@@@Z; CDescriptor::SetIStream(IStream *)
0x18000b444  mov     rbx, [rsp+28h+arg_0]
0x18000b449  mov     rsi, [rsp+28h+arg_8]
0x18000b44e  add     rsp, 20h
0x18000b452  pop     rdi
0x18000b453  retn
```

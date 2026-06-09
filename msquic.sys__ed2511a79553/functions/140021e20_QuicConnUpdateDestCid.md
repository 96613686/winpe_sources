# QuicConnUpdateDestCid

- ea: `0x140021e20`
- end: `0x140021faa`
- name: `QuicConnUpdateDestCid`
- size: `394`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140012630`
- `0x140042e10`

## callees

- `0x14001c664`
- `0x140021e20`
- `0x140021fb0`
- `0x14003c9e0`
- `0x14003cb00`
- `0x140040c0c`
- `0x1400427e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021eee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021eee`

## pseudocode

```c
char __fastcall QuicConnUpdateDestCid(__int64 a1, __int64 a2)
{
  __int64 *v2; // rsi
  __int64 v4; // rbx
  char v7; // r12
  const void **v8; // r14
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // [rsp+20h] [rbp-28h]

  v2 = (__int64 *)(a1 + 1288);
  v4 = *(_QWORD *)(a1 + 1288);
  if ( v4 == a1 + 1288 )
  {
    QuicConnTransportError(a1, 1);
    return 0;
  }
  v7 = *(_BYTE *)(v4 + 33);
  v8 = (const void **)(a2 + 72);
  if ( *(_BYTE *)(a2 + 87) != v7 || memcmp(*v8, (const void *)(v4 + 48), *(unsigned __int8 *)(v4 + 33)) )
  {
    if ( (byte_14005C48A & 4) != 0 )
      McTemplateU0pxubr2_EtwWriteTransfer(
        a1,
        (const EVENT_DESCRIPTOR *)QuicConnDestCidRemoved,
        a1,
        *(_QWORD *)(v4 + 40),
        v7,
        v4 + 48);
    if ( *(_BYTE *)(a2 + 87) > *(_BYTE *)(v4 + 33) )
    {
      v11 = *(_QWORD *)v4;
      v12 = *(_QWORD **)(v4 + 8);
      *v12 = *(_QWORD *)v4;
      *(_QWORD *)(v11 + 8) = v12;
      ExFreePoolWithTag((PVOID)v4, 0x45306351u);
      LOBYTE(v13) = *(_BYTE *)(a2 + 87);
      v14 = QuicCidNewDestination(v13, *v8);
      v4 = v14;
      if ( !v14 )
      {
        --*(_BYTE *)(a1 + 272);
        *(_QWORD *)(a1 + 464) = 0;
        QuicConnTryClose(a1, 18, -1073741801, "Out of memory", 0xDu);
        return 0;
      }
      *(_QWORD *)(a1 + 464) = v14;
      *(_BYTE *)(v14 + 32) |= 8u;
      v15 = *v2;
      *(_QWORD *)v4 = *v2;
      *(_QWORD *)(v4 + 8) = v2;
      *(_QWORD *)(v15 + 8) = v4;
      *v2 = v4;
    }
    else
    {
      *(_BYTE *)(v4 + 32) &= ~1u;
      v9 = *(unsigned __int8 *)(a2 + 87);
      *(_BYTE *)(v4 + 33) = v9;
      memmove((void *)(v4 + 48), *v8, v9);
    }
    if ( byte_14005C48A < 0 )
    {
      LOBYTE(v16) = *(_BYTE *)(v4 + 33);
      McTemplateU0pxubr2_EtwWriteTransfer(
        v10,
        (const EVENT_DESCRIPTOR *)QuicConnDestCidAdded,
        a1,
        *(_QWORD *)(v4 + 40),
        v16,
        v4 + 48);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140021e20  mov     rax, rsp
0x140021e23  mov     [rax+8], rbx
0x140021e27  mov     [rax+10h], rbp
0x140021e2b  mov     [rax+18h], rsi
0x140021e2f  mov     [rax+20h], rdi
0x140021e33  push    r12
0x140021e35  push    r14
0x140021e37  push    r15
0x140021e39  sub     rsp, 30h
0x140021e3d  lea     rsi, [rcx+508h]
0x140021e44  mov     rbp, rdx
0x140021e47  mov     rbx, [rsi]
0x140021e4a  mov     rdi, rcx
0x140021e4d  cmp     rbx, rsi
0x140021e50  jnz     short loc_140021E63
0x140021e52  mov     edx, 1
0x140021e57  call    QuicConnTransportError
0x140021e5c  xor     al, al
0x140021e5e  jmp     loc_140021F8A
0x140021e63  movzx   r12d, byte ptr [rbx+21h]
0x140021e68  lea     r15, [rbx+30h]
0x140021e6c  lea     r14, [rdx+48h]
0x140021e70  cmp     [rdx+57h], r12b
0x140021e74  jnz     short loc_140021E8C
0x140021e76  mov     rcx, [r14]; Buf1
0x140021e79  mov     r8d, r12d; Size
0x140021e7c  mov     rdx, r15; Buf2
0x140021e7f  call    memcmp
0x140021e84  test    eax, eax
0x140021e86  jz      loc_140021F88
0x140021e8c  test    cs:byte_14005C48A, 4
0x140021e93  jz      short loc_140021EB2
0x140021e95  mov     r9, [rbx+28h]
0x140021e99  lea     rdx, QuicConnDestCidRemoved
0x140021ea0  mov     [rsp+48h+var_20], r15
0x140021ea5  mov     r8, rdi
0x140021ea8  mov     byte ptr [rsp+48h+var_28], r12b
0x140021ead  call    McTemplateU0pxubr2_EtwWriteTransfer
0x140021eb2  mov     al, [rbx+21h]
0x140021eb5  cmp     [rbp+57h], al
0x140021eb8  ja      short loc_140021ED8
0x140021eba  and     byte ptr [rbx+20h], 0FEh
0x140021ebe  mov     rcx, r15; void *
0x140021ec1  movzx   eax, byte ptr [rbp+57h]
0x140021ec5  mov     [rbx+21h], al
0x140021ec8  mov     r8d, eax; Size
0x140021ecb  mov     rdx, [r14]; Src
0x140021ece  call    memmove
0x140021ed3  jmp     loc_140021F5B
0x140021ed8  mov     rdx, [rbx]
0x140021edb  mov     rcx, rbx; P
0x140021ede  mov     rax, [rbx+8]
0x140021ee2  mov     [rax], rdx
0x140021ee5  mov     [rdx+8], rax
0x140021ee9  mov     edx, 45306351h; Tag
0x140021eee  call    cs:__imp_ExFreePoolWithTag
0x140021ef5  nop     dword ptr [rax+rax+00h]
0x140021efa  mov     rdx, [r14]
0x140021efd  mov     cl, [rbp+57h]
0x140021f00  call    QuicCidNewDestination
0x140021f05  mov     rbx, rax
0x140021f08  test    rax, rax
0x140021f0b  jnz     short loc_140021F3F
0x140021f0d  dec     byte ptr [rdi+110h]
0x140021f13  lea     r9, aOutOfMemory; "Out of memory"
0x140021f1a  and     [rdi+1D0h], rax
0x140021f21  lea     edx, [rax+12h]
0x140021f24  mov     r8, 0FFFFFFFFC0000017h
0x140021f2b  mov     word ptr [rsp+48h+var_28], 0Dh
0x140021f32  mov     rcx, rdi
0x140021f35  call    QuicConnTryClose
0x140021f3a  jmp     loc_140021E5C
0x140021f3f  mov     [rdi+1D0h], rbx
0x140021f46  or      byte ptr [rax+20h], 8
0x140021f4a  mov     rax, [rsi]
0x140021f4d  mov     [rbx], rax
0x140021f50  mov     [rbx+8], rsi
0x140021f54  mov     [rax+8], rbx
0x140021f58  mov     [rsi], rbx
0x140021f5b  mov     al, cs:byte_14005C48A
0x140021f61  test    al, al
0x140021f63  jns     short loc_140021F88
0x140021f65  mov     r9, [rbx+28h]
0x140021f69  lea     rax, [rbx+30h]
0x140021f6d  mov     [rsp+48h+var_20], rax
0x140021f72  lea     rdx, QuicConnDestCidAdded
0x140021f79  mov     al, [rbx+21h]
0x140021f7c  mov     r8, rdi
0x140021f7f  mov     byte ptr [rsp+48h+var_28], al
0x140021f83  call    McTemplateU0pxubr2_EtwWriteTransfer
0x140021f88  mov     al, 1
0x140021f8a  mov     rbx, [rsp+48h+arg_0]
0x140021f8f  mov     rbp, [rsp+48h+arg_8]
0x140021f94  mov     rsi, [rsp+48h+arg_10]
0x140021f99  mov     rdi, [rsp+48h+arg_18]
0x140021f9e  add     rsp, 30h
0x140021fa2  pop     r15
0x140021fa4  pop     r14
0x140021fa6  pop     r12
0x140021fa8  retn
```

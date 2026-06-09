# CComponentData::CreateComponent(IComponent * *)

- ea: `0x180005a10`
- end: `0x180005a9c`
- name: `?CreateComponent@CComponentData@@UEAAJPEAPEAUIComponent@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, struct IComponent **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002928`
- `0x180004f34`
- `0x180005a10`
- `0x18001b700`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CComponentData::CreateComponent(CComponentData *this, struct IComponent **a2)
{
  CSnapin *v4; // rax
  struct IComponent *v5; // rax
  struct IComponent *v6; // rbx
  unsigned int v7; // esi
  __int64 v8; // rdx

  v4 = (CSnapin *)operator new(0x680u);
  if ( !v4 )
  {
    *a2 = 0;
    return (unsigned int)-2147024882;
  }
  v5 = (struct IComponent *)CSnapin::CSnapin(v4, (CComponentData *)((char *)this - 8));
  *a2 = v5;
  v6 = v5;
  if ( !v5 )
    return (unsigned int)-2147024882;
  v7 = 0;
  ((void (__fastcall *)(struct IComponent *))v5->lpVtbl->AddRef)(v5);
  *((_QWORD *)this + 8) = v6;
  v8 = *((_QWORD *)this + 7);
  if ( v8 )
    CDLink::LinkAfter((CDLink *)&v6[7], (struct CDLink *)(v8 + 56));
  else
    *((_QWORD *)this + 7) = v6;
  return v7;
}

```

## disassembly

```asm
0x180005a10  mov     [rsp+arg_0], rbx
0x180005a15  mov     [rsp+arg_8], rsi
0x180005a1a  push    rdi
0x180005a1b  sub     rsp, 20h
0x180005a1f  mov     rdi, rcx
0x180005a22  mov     rsi, rdx
0x180005a25  mov     ecx, 680h; Size
0x180005a2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005a2f  test    rax, rax
0x180005a32  jz      short loc_180005A7E
0x180005a34  lea     rdx, [rdi-8]; struct CComponentData *
0x180005a38  mov     rcx, rax; this
0x180005a3b  call    ??0CSnapin@@QEAA@PEAVCComponentData@@@Z; CSnapin::CSnapin(CComponentData *)
0x180005a40  mov     [rsi], rax
0x180005a43  mov     rbx, rax
0x180005a46  test    rax, rax
0x180005a49  jz      short loc_180005A85
0x180005a4b  mov     rcx, [rax]
0x180005a4e  xor     esi, esi
0x180005a50  mov     rax, [rcx+8]
0x180005a54  mov     rcx, rbx
0x180005a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a5c  mov     [rdi+40h], rbx
0x180005a60  mov     rdx, [rdi+38h]
0x180005a64  test    rdx, rdx
0x180005a67  jnz     short loc_180005A6F
0x180005a69  mov     [rdi+38h], rbx
0x180005a6d  jmp     short loc_180005A8A
0x180005a6f  add     rdx, 38h ; '8'; struct CDLink *
0x180005a73  lea     rcx, [rbx+38h]; this
0x180005a77  call    ?LinkAfter@CDLink@@QEAAXPEAV1@@Z; CDLink::LinkAfter(CDLink *)
0x180005a7c  jmp     short loc_180005A8A
0x180005a7e  mov     qword ptr [rsi], 0
0x180005a85  mov     esi, 8007000Eh
0x180005a8a  mov     rbx, [rsp+28h+arg_0]
0x180005a8f  mov     eax, esi
0x180005a91  mov     rsi, [rsp+28h+arg_8]
0x180005a96  add     rsp, 20h
0x180005a9a  pop     rdi
0x180005a9b  retn
```

# IASRemoteServer::IASRemoteServer(RemoteServerConfig const &,_RadiusRemoteServerEntry *)

- ea: `0x18001d4d0`
- end: `0x18001d5c9`
- name: `??0IASRemoteServer@@QEAA@AEBURemoteServerConfig@@PEAU_RadiusRemoteServerEntry@@@Z`
- size: `249`
- prototype: `IASRemoteServer *__fastcall(IASRemoteServer *__hidden this, const struct RemoteServerConfig *, struct _RadiusRemoteServerEntry *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001debc`

## callees

- `0x180014478`
- `0x18001b0ec`
- `0x18001c46c`
- `0x18001d4d0`
- `0x180020a98`
- `0x18002abe4`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x18001d57a`
- `WS2_32!__imp_ntohs` at `0x18001d594`
- `WS2_32!__imp_ntohs` at `0x18001d57a`
- `WS2_32!__imp_ntohs` at `0x18001d594`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
IASRemoteServer *__fastcall IASRemoteServer::IASRemoteServer(
        IASRemoteServer *this,
        const struct RemoteServerConfig *a2,
        struct _RadiusRemoteServerEntry *a3)
{
  struct sockaddr *v6; // rsi
  ADDRESS_FAMILY sa_family; // di
  struct _IASATTRIBUTE *v8; // rbx
  int v9; // eax
  bool v10; // r8
  struct _IASATTRIBUTE *v12; // [rsp+58h] [rbp+10h] BYREF

  RemoteServer::RemoteServer(this, a2);
  *(_QWORD *)this = &IASRemoteServer::`vftable';
  *((_QWORD *)this + 57) = (char *)this + 480;
  *((_QWORD *)this + 58) = (char *)this + 480;
  *((_DWORD *)this + 118) = 1;
  *((_BYTE *)this + 476) = 0;
  *((_QWORD *)this + 62) = a3;
  v6 = (struct sockaddr *)*((_QWORD *)a2 + 2);
  sa_family = v6->sa_family;
  IASTL::IASAttribute::_alloc((IASTL::IASAttribute *)&v12);
  v8 = v12;
  *((_DWORD *)v12 + 2) = 4157;
  v9 = 4;
  if ( sa_family != 2 )
    v9 = 10;
  *((_DWORD *)v8 + 4) = v9;
  IASTL::IASAttribute::setSockAddress((IASTL::IASAttribute *)&v12, v6);
  IASTL::IASAttributeVector::push_back((IASRemoteServer *)((char *)this + 456), v8, v10);
  if ( *((_QWORD *)this + 62) )
  {
    *(_DWORD *)(*((_QWORD *)this + 62) + 132LL) = ntohs(*((_WORD *)a2 + 20));
    *(_DWORD *)(*((_QWORD *)this + 62) + 180LL) = ntohs(*((_WORD *)a2 + 21));
  }
  IASTL::IASAttribute::_release((IASTL::IASAttribute *)&v12);
  return this;
}

```

## disassembly

```asm
0x18001d4d0  mov     [rsp+arg_10], rbx
0x18001d4d5  mov     [rsp+arg_0], rcx
0x18001d4da  push    rbp
0x18001d4db  push    rsi
0x18001d4dc  push    rdi
0x18001d4dd  push    r14
0x18001d4df  push    r15
0x18001d4e1  sub     rsp, 20h
0x18001d4e5  mov     rbx, r8
0x18001d4e8  mov     rbp, rdx
0x18001d4eb  mov     r15, rcx
0x18001d4ee  call    ??0RemoteServer@@QEAA@AEBURemoteServerConfig@@@Z; RemoteServer::RemoteServer(RemoteServerConfig const &)
0x18001d4f3  nop
0x18001d4f4  lea     rax, ??_7IASRemoteServer@@6B@; const IASRemoteServer::`vftable'
0x18001d4fb  mov     [r15], rax
0x18001d4fe  lea     r14, [r15+1C8h]
0x18001d505  lea     rax, [r14+18h]
0x18001d509  mov     [r14], rax
0x18001d50c  mov     [r14+8], rax
0x18001d510  mov     dword ptr [r14+10h], 1
0x18001d518  mov     byte ptr [r14+14h], 0
0x18001d51d  mov     [r15+1F0h], rbx
0x18001d524  mov     rsi, [rbp+10h]
0x18001d528  movzx   edi, word ptr [rsi]
0x18001d52b  lea     rcx, [rsp+48h+arg_8]; this
0x18001d530  call    ?_alloc@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::_alloc(void)
0x18001d535  nop
0x18001d536  mov     rbx, [rsp+48h+arg_8]
0x18001d53b  mov     dword ptr [rbx+8], 103Dh
0x18001d542  mov     eax, 4
0x18001d547  lea     ecx, [rax+6]
0x18001d54a  cmp     di, 2
0x18001d54e  cmovnz  eax, ecx
0x18001d551  mov     [rbx+10h], eax
0x18001d554  mov     rdx, rsi; struct sockaddr *
0x18001d557  lea     rcx, [rsp+48h+arg_8]; this
0x18001d55c  call    ?setSockAddress@IASAttribute@IASTL@@QEAAXQEAUsockaddr@@@Z; IASTL::IASAttribute::setSockAddress(sockaddr * const)
0x18001d561  mov     rdx, rbx; struct _IASATTRIBUTE *
0x18001d564  mov     rcx, r14; this
0x18001d567  call    ?push_back@IASAttributeVector@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttributeVector::push_back(_IASATTRIBUTE *,bool)
0x18001d56c  cmp     qword ptr [r15+1F0h], 0
0x18001d574  jz      short loc_18001D5AA
0x18001d576  movzx   ecx, word ptr [rbp+28h]; netshort
0x18001d57a  call    cs:__imp_ntohs
0x18001d580  movzx   ecx, ax
0x18001d583  mov     rax, [r15+1F0h]
0x18001d58a  mov     [rax+84h], ecx
0x18001d590  movzx   ecx, word ptr [rbp+2Ah]; netshort
0x18001d594  call    cs:__imp_ntohs
0x18001d59a  movzx   ecx, ax
0x18001d59d  mov     rax, [r15+1F0h]
0x18001d5a4  mov     [rax+0B4h], ecx
0x18001d5aa  lea     rcx, [rsp+48h+arg_8]; this
0x18001d5af  call    ?_release@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::_release(void)
0x18001d5b4  nop
0x18001d5b5  mov     rax, r15
0x18001d5b8  mov     rbx, [rsp+48h+arg_10]
0x18001d5bd  add     rsp, 20h
0x18001d5c1  pop     r15
0x18001d5c3  pop     r14
0x18001d5c5  pop     rdi
0x18001d5c6  pop     rsi
0x18001d5c7  pop     rbp
0x18001d5c8  retn
```

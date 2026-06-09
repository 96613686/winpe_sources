# CKsProxy::NotifyDisplayChangedEvent(void)

- ea: `0x180023b4c`
- end: `0x180023d35`
- name: `?NotifyDisplayChangedEvent@CKsProxy@@QEAAJXZ`
- size: `489`
- prototype: `__int64 __fastcall(CKsProxy *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x18002bd20`

## callees

- `0x180002b58`
- `0x18001f1c4`
- `0x18001ffb0`
- `0x180022494`
- `0x180022e7c`
- `0x180023b4c`
- `0x180025860`
- `0x180025a74`
- `0x18003f33c`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180023c10`
- `ole32!CoTaskMemAlloc` at `0x180023c10`

## pseudocode

```c
__int64 __fastcall CKsProxy::NotifyDisplayChangedEvent(CKsProxy *this)
{
  enum _PinDirection v2; // edx
  int ConnectedPins; // eax
  struct IPin **v4; // r13
  int v5; // r14d
  __int64 v6; // rsi
  void *v7; // rax
  __int64 v8; // r15
  __int64 i; // r14
  struct IPin *v10; // r9
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 j; // rbx
  unsigned int v15; // [rsp+50h] [rbp+8h] BYREF
  struct IPin **v16; // [rsp+58h] [rbp+10h] BYREF

  v16 = 0;
  v15 = 0;
  if ( !this->m_lInProgress )
  {
    CKsProxy::IncrementInProgressCount(this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x1Fu,
        &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
        this->m_lInProgress);
    ConnectedPins = CKsProxy::GetConnectedPins(this, v2, &v16, &v15);
    v4 = v16;
    v5 = ConnectedPins;
    if ( ConnectedPins < 0 )
      goto LABEL_21;
    v6 = v15;
    if ( !v15 )
      goto LABEL_21;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x21u, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids, v15);
    v7 = CoTaskMemAlloc((unsigned int)(8 * v6));
    v8 = (__int64)v7;
    if ( v7 )
    {
      memset_0(v7, 0, (unsigned int)(8 * v6));
      for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
      {
        v10 = v4[i];
        *(_QWORD *)(v8 + 8 * i) = v10;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids, v10);
      }
      v5 = CBaseFilter::NotifyEvent(this, 22, v8, v6);
      if ( v5 >= 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_19;
        v12 = 36;
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_19;
        v12 = 35;
      }
      WPP_SF_(v11[2], v12, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids);
    }
LABEL_19:
    for ( j = 0; (unsigned int)j < (unsigned int)v6; j = (unsigned int)(j + 1) )
      v4[j]->Release(v4[j]);
LABEL_21:
    operator delete(v4);
    return (unsigned int)v5;
  }
  CKsProxy::IncrementInProgressCount(this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x20u,
      &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
      this->m_lInProgress);
  return 0;
}

```

## disassembly

```asm
0x180023b4c  mov     rax, rsp
0x180023b4f  mov     [rax+18h], rbx
0x180023b53  mov     [rax+20h], rsi
0x180023b57  push    rdi
0x180023b58  push    r12
0x180023b5a  push    r13
0x180023b5c  push    r14
0x180023b5e  push    r15
0x180023b60  sub     rsp, 20h
0x180023b64  xor     r15d, r15d
0x180023b67  mov     rbx, rcx
0x180023b6a  mov     [rax+10h], r15
0x180023b6e  mov     [rax+8], r15d
0x180023b72  cmp     [rcx+290h], r15d
0x180023b79  jnz     loc_180023CE6
0x180023b7f  call    ?IncrementInProgressCount@CKsProxy@@QEAAXXZ; CKsProxy::IncrementInProgressCount(void)
0x180023b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b8b  lea     rdi, WPP_GLOBAL_Control
0x180023b92  cmp     rcx, rdi
0x180023b95  jz      short loc_180023BB2
0x180023b97  mov     r9d, [rbx+290h]
0x180023b9e  lea     edx, [r15+1Fh]
0x180023ba2  mov     rcx, [rcx+10h]
0x180023ba6  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x180023bad  call    WPP_SF_d
0x180023bb2  lea     r9, [rsp+48h+arg_0]; unsigned int *
0x180023bb7  mov     rcx, rbx; this
0x180023bba  lea     r8, [rsp+48h+arg_8]; struct IPin ***
0x180023bbf  call    ?GetConnectedPins@CKsProxy@@QEAAJW4_PinDirection@@PEAPEAPEAUIPin@@PEAK@Z; CKsProxy::GetConnectedPins(_PinDirection,IPin * * *,ulong *)
0x180023bc4  mov     r13, [rsp+48h+arg_8]
0x180023bc9  mov     r14d, eax
0x180023bcc  test    eax, eax
0x180023bce  js      loc_180023CD9
0x180023bd4  mov     esi, [rsp+48h+arg_0]
0x180023bd8  test    esi, esi
0x180023bda  jz      loc_180023CD9
0x180023be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180023be7  cmp     rcx, rdi
0x180023bea  jz      short loc_180023C04
0x180023bec  mov     rcx, [rcx+10h]
0x180023bf0  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x180023bf7  mov     edx, 21h ; '!'
0x180023bfc  mov     r9d, esi
0x180023bff  call    WPP_SF_d
0x180023c04  lea     eax, ds:0[rsi*8]
0x180023c0b  mov     ecx, eax; cb
0x180023c0d  mov     r12d, eax
0x180023c10  call    cs:__imp_CoTaskMemAlloc
0x180023c17  nop     dword ptr [rax+rax+00h]
0x180023c1c  mov     r15, rax
0x180023c1f  test    rax, rax
0x180023c22  jz      loc_180023CBC
0x180023c28  mov     r8d, r12d; Size
0x180023c2b  xor     edx, edx; Val
0x180023c2d  mov     rcx, rax; void *
0x180023c30  call    memset_0
0x180023c35  xor     r14d, r14d
0x180023c38  test    esi, esi
0x180023c3a  jz      short loc_180023C6E
0x180023c3c  mov     r9, [r13+r14*8+0]
0x180023c41  mov     [r15+r14*8], r9
0x180023c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c4c  cmp     rcx, rdi
0x180023c4f  jz      short loc_180023C66
0x180023c51  mov     rcx, [rcx+10h]
0x180023c55  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x180023c5c  mov     edx, 22h ; '"'
0x180023c61  call    WPP_SF_q
0x180023c66  inc     r14d
0x180023c69  cmp     r14d, esi
0x180023c6c  jb      short loc_180023C3C
0x180023c6e  mov     r9, rsi; __int64
0x180023c71  mov     r8, r15; __int64
0x180023c74  mov     edx, 16h; int
0x180023c79  mov     rcx, rbx; this
0x180023c7c  call    ?NotifyEvent@CBaseFilter@@QEAAJJ_J0@Z; CBaseFilter::NotifyEvent(long,__int64,__int64)
0x180023c81  mov     r14d, eax
0x180023c84  test    eax, eax
0x180023c86  jns     short loc_180023C9B
0x180023c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c8f  cmp     rcx, rdi
0x180023c92  jz      short loc_180023CBC
0x180023c94  mov     edx, 23h ; '#'
0x180023c99  jmp     short loc_180023CAC
0x180023c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ca2  cmp     rcx, rdi
0x180023ca5  jz      short loc_180023CBC
0x180023ca7  mov     edx, 24h ; '$'
0x180023cac  mov     rcx, [rcx+10h]
0x180023cb0  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x180023cb7  call    WPP_SF_
0x180023cbc  xor     ebx, ebx
0x180023cbe  test    esi, esi
0x180023cc0  jz      short loc_180023CD9
0x180023cc2  mov     rcx, [r13+rbx*8+0]
0x180023cc7  mov     rax, [rcx]
0x180023cca  mov     rax, [rax+10h]
0x180023cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cd3  inc     ebx
0x180023cd5  cmp     ebx, esi
0x180023cd7  jb      short loc_180023CC2
0x180023cd9  mov     rcx, r13; void *
0x180023cdc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023ce1  mov     eax, r14d
0x180023ce4  jmp     short loc_180023D1C
0x180023ce6  call    ?IncrementInProgressCount@CKsProxy@@QEAAXXZ; CKsProxy::IncrementInProgressCount(void)
0x180023ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x180023cf2  lea     rdi, WPP_GLOBAL_Control
0x180023cf9  cmp     rcx, rdi
0x180023cfc  jz      short loc_180023D1A
0x180023cfe  mov     r9d, [rbx+290h]
0x180023d05  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x180023d0c  mov     rcx, [rcx+10h]
0x180023d10  mov     edx, 20h ; ' '
0x180023d15  call    WPP_SF_d
0x180023d1a  xor     eax, eax
0x180023d1c  mov     rbx, [rsp+48h+arg_10]
0x180023d21  mov     rsi, [rsp+48h+arg_18]
0x180023d26  add     rsp, 20h
0x180023d2a  pop     r15
0x180023d2c  pop     r14
0x180023d2e  pop     r13
0x180023d30  pop     r12
0x180023d32  pop     rdi
0x180023d33  retn
```

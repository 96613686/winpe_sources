# RxCancelNotifyChangeDirectoryRequestsForLogicalView

- ea: `0x140017c28`
- end: `0x140017dc6`
- name: `RxCancelNotifyChangeDirectoryRequestsForLogicalView`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14004f55c`

## callees

- `0x140016890`
- `0x140016e20`
- `0x140017c28`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140017d3e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140017d3e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140017c83`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140017c83`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017d54`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017d54`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017c6c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017c6c`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall RxCancelNotifyChangeDirectoryRequestsForLogicalView(struct _LIST_ENTRY *a1)
{
  unsigned int v1; // esi
  __int64 v3; // rdi
  LIST_ENTRY *v4; // r14
  KIRQL v5; // r12
  struct _LIST_ENTRY *Flink; // rdx
  LIST_ENTRY *v7; // r8
  LIST_ENTRY *v8; // rcx
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY **p_Flink; // rax
  PDEVICE_OBJECT *result; // rax
  __int64 v12; // [rsp+20h] [rbp-58h] BYREF
  struct _LIST_ENTRY *v13; // [rsp+28h] [rbp-50h]

  v1 = 0;
  v13 = (struct _LIST_ENTRY *)&v12;
  v12 = (__int64)&v12;
  v3 = 0;
  do
  {
    v4 = &RxActiveContexts + 12 * v3;
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v4[8]);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&v4[4]);
    Flink = v4->Flink;
    if ( v4->Flink != v4 )
    {
      do
      {
        v7 = Flink->Flink;
        if ( LOBYTE(Flink[1].Blink) == 12 && BYTE1(Flink[1].Blink) == 2 )
        {
          if ( Flink[3].Flink )
          {
            _m_prefetchw(&Flink[7].Blink);
            if ( (_InterlockedXor((volatile signed __int32 *)&Flink[7].Blink, 0) & 2) == 0
              && (!a1 || Flink[6].Blink == a1) )
            {
              _InterlockedOr((volatile signed __int32 *)&Flink[7].Blink, 2u);
              v8 = Flink->Flink;
              if ( Flink->Flink->Blink != Flink
                || (Blink = Flink->Blink, Blink->Flink != Flink)
                || (Blink->Flink = v8, v8->Blink = Blink, p_Flink = &v13->Flink, (__int64 *)v13->Flink != &v12) )
              {
                __fastfail(3u);
              }
              Flink->Blink = v13;
              Flink->Flink = (struct _LIST_ENTRY *)&v12;
              *p_Flink = Flink;
              v13 = Flink;
              _InterlockedIncrement((volatile signed __int32 *)&Flink[-1].Blink + 1);
              ++v1;
            }
          }
        }
        Flink = v7;
      }
      while ( v7 != &RxActiveContexts + 12 * v3 );
    }
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&v4[4]);
    KeReleaseSpinLock((PKSPIN_LOCK)&v4[8], v5);
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (unsigned int)v3 < 0x40 );
  RxpCancelRxContextList(&v12);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)result & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      return (PDEVICE_OBJECT *)WPP_SF_d(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 12,
                                 &WPP_cfd2e4d29c7e3fd7560d67a28dd6957d_Traceguids,
                                 v1);
  }
  return result;
}

```

## disassembly

```asm
0x140017c28  mov     r11, rsp
0x140017c2b  push    rbx
0x140017c2c  push    rbp
0x140017c2d  push    rsi
0x140017c2e  push    rdi
0x140017c2f  push    r12
0x140017c31  push    r13
0x140017c33  push    r14
0x140017c35  push    r15
0x140017c37  sub     rsp, 38h
0x140017c3b  lea     rax, [r11-58h]
0x140017c3f  xor     esi, esi
0x140017c41  mov     [r11-50h], rax
0x140017c45  lea     r13, RxActiveContexts
0x140017c4c  lea     rax, [r11-58h]
0x140017c50  mov     rbp, rcx
0x140017c53  mov     [r11-58h], rax
0x140017c57  xor     edi, edi
0x140017c59  lea     rbx, [rdi+rdi*2]
0x140017c5d  shl     rbx, 6
0x140017c61  lea     r14, [rbx+r13]
0x140017c65  lea     rcx, [r14+80h]; SpinLock
0x140017c6c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017c73  nop     dword ptr [rax+rax+00h]
0x140017c78  lea     r15, [rbx+r13]
0x140017c7c  mov     r12b, al
0x140017c7f  lea     rcx, [r15+40h]; SpinLock
0x140017c83  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140017c8a  nop     dword ptr [rax+rax+00h]
0x140017c8f  lea     r9, [rbx+r13]
0x140017c93  mov     rdx, [r9]
0x140017c96  cmp     rdx, r9
0x140017c99  jz      loc_140017D3A
0x140017c9f  cmp     byte ptr [rdx+18h], 0Ch
0x140017ca3  mov     r8, [rdx]
0x140017ca6  jnz     loc_140017D2E
0x140017cac  cmp     byte ptr [rdx+19h], 2
0x140017cb0  jnz     short loc_140017D2E
0x140017cb2  cmp     qword ptr [rdx+30h], 0
0x140017cb7  jz      short loc_140017D2E
0x140017cb9  prefetchw byte ptr [rdx+78h]
0x140017cbd  mov     eax, [rdx+78h]
0x140017cc0  mov     ecx, eax
0x140017cc2  xor     ecx, 0
0x140017cc5  lock cmpxchg [rdx+78h], ecx
0x140017cca  jnz     short loc_140017CC0
0x140017ccc  test    al, 2
0x140017cce  jnz     short loc_140017D2E
0x140017cd0  test    rbp, rbp
0x140017cd3  jz      short loc_140017CDB
0x140017cd5  cmp     [rdx+68h], rbp
0x140017cd9  jnz     short loc_140017D2E
0x140017cdb  lock or dword ptr [rdx+78h], 2
0x140017ce0  mov     rcx, [rdx]
0x140017ce3  cmp     [rcx+8], rdx
0x140017ce7  jnz     loc_140017DBF
0x140017ced  mov     rax, [rdx+8]
0x140017cf1  cmp     [rax], rdx
0x140017cf4  jnz     loc_140017DBF
0x140017cfa  mov     [rax], rcx
0x140017cfd  mov     [rcx+8], rax
0x140017d01  lea     rcx, [rsp+78h+var_58]
0x140017d06  mov     rax, [rsp+78h+var_50]
0x140017d0b  cmp     [rax], rcx
0x140017d0e  jnz     loc_140017DBF
0x140017d14  mov     [rdx+8], rax
0x140017d18  lea     rcx, [rsp+78h+var_58]
0x140017d1d  mov     [rdx], rcx
0x140017d20  mov     [rax], rdx
0x140017d23  mov     [rsp+78h+var_50], rdx
0x140017d28  lock inc dword ptr [rdx-4]
0x140017d2c  inc     esi
0x140017d2e  mov     rdx, r8
0x140017d31  cmp     r8, r9
0x140017d34  jnz     loc_140017C9F
0x140017d3a  lea     rcx, [r15+40h]; SpinLock
0x140017d3e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140017d45  nop     dword ptr [rax+rax+00h]
0x140017d4a  mov     dl, r12b; NewIrql
0x140017d4d  lea     rcx, [r14+80h]; SpinLock
0x140017d54  call    cs:__imp_KeReleaseSpinLock
0x140017d5b  nop     dword ptr [rax+rax+00h]
0x140017d60  inc     edi
0x140017d62  cmp     edi, 40h ; '@'
0x140017d65  jb      loc_140017C59
0x140017d6b  lea     rcx, [rsp+78h+var_58]
0x140017d70  call    RxpCancelRxContextList
0x140017d75  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d7c  lea     rax, WPP_GLOBAL_Control
0x140017d83  cmp     rcx, rax
0x140017d86  jz      short loc_140017DAD
0x140017d88  mov     eax, [rcx+2Ch]
0x140017d8b  test    al, 2
0x140017d8d  jz      short loc_140017DAD
0x140017d8f  cmp     byte ptr [rcx+29h], 2
0x140017d93  jb      short loc_140017DAD
0x140017d95  mov     rcx, [rcx+18h]
0x140017d99  lea     r8, WPP_cfd2e4d29c7e3fd7560d67a28dd6957d_Traceguids
0x140017da0  mov     edx, 0Ch
0x140017da5  mov     r9d, esi
0x140017da8  call    WPP_SF_d
0x140017dad  add     rsp, 38h
0x140017db1  pop     r15
0x140017db3  pop     r14
0x140017db5  pop     r13
0x140017db7  pop     r12
0x140017db9  pop     rdi
0x140017dba  pop     rsi
0x140017dbb  pop     rbp
0x140017dbc  pop     rbx
0x140017dbd  retn
0x140017dbf  mov     ecx, 3
0x140017dc4  int     29h; Win8: RtlFailFast(ecx)
```

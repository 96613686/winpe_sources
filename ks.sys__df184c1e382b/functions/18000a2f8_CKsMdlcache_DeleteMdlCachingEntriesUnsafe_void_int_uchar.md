# CKsMdlcache::DeleteMdlCachingEntriesUnsafe(void *,int,uchar &)

- ea: `0x18000a2f8`
- end: `0x18000a55a`
- name: `?DeleteMdlCachingEntriesUnsafe@CKsMdlcache@@QEAAJPEAXHAEAE@Z`
- size: `610`
- prototype: `__int64 __fastcall(CKsMdlcache *this, struct _LIST_ENTRY *, int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000a270`

## callees

- `0x18000a2f8`
- `0x18000a560`
- `0x1800159b0`
- `0x1800186f0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000a53f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000a53f`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000a50e`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000a50e`
- `ntoskrnl!KeClearEvent` at `0x18000a34c`
- `ntoskrnl!KeClearEvent` at `0x18000a34c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000a52f`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000a52f`

## pseudocode

```c
__int64 __fastcall CKsMdlcache::DeleteMdlCachingEntriesUnsafe(
        CKsMdlcache *this,
        struct _LIST_ENTRY *a2,
        int a3,
        unsigned __int8 *a4)
{
  struct _LIST_ENTRY *v5; // r13
  struct _LIST_ENTRY *v6; // rbx
  struct _LIST_ENTRY *v7; // rax
  unsigned int v9; // r15d
  struct _LIST_ENTRY *v10; // rsi
  bool v11; // bp
  int v12; // r12d
  int Flink; // edx
  KIRQL v15; // al
  struct _LIST_ENTRY *v16; // [rsp+80h] [rbp+8h] BYREF
  struct _LIST_ENTRY *v17; // [rsp+88h] [rbp+10h]
  unsigned __int8 *v18; // [rsp+98h] [rbp+20h]

  v18 = a4;
  v17 = a2;
  v5 = (struct _LIST_ENTRY *)((char *)this + 64);
  v6 = (struct _LIST_ENTRY *)*((_QWORD *)this + 8);
  v16 = v6;
  v7 = a2;
  if ( !a3 && !*((_DWORD *)this + 26) )
    return 0;
  v9 = 0;
  if ( !a3 )
  {
    if ( v6 != v5 )
      goto LABEL_6;
    return v9;
  }
  if ( v6 == v5 )
    goto LABEL_35;
  KeClearEvent((PRKEVENT)((char *)this + 112));
  v7 = v17;
  a4 = v18;
  do
  {
LABEL_6:
    v10 = v6 - 5;
    v11 = 0;
    v12 = 0;
    if ( v7 && v7 != v10->Blink )
      goto LABEL_10;
    Flink = (int)v10[1].Flink;
    switch ( Flink )
    {
      case 0:
LABEL_8:
        v11 = 1;
        break;
      case 1:
        if ( a3 )
        {
          v12 = CKsMdlcache::MdlCacheCancelCachedEntry(this, (struct _KSPMDLCACHED_STREAM_POINTER *)&v6[-5], a4);
          v11 = v12 >= 0;
        }
        else
        {
          LODWORD(v10[1].Flink) = 2;
        }
        break;
      case 2:
        if ( a3 )
        {
          v12 = CKsMdlcache::MdlCacheCancelCachedEntry(this, (struct _KSPMDLCACHED_STREAM_POINTER *)&v6[-5], a4);
          if ( v12 >= 0 )
            goto LABEL_8;
        }
        else
        {
          v12 = -1073740024;
        }
        break;
      default:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(Flink) = 5;
          WPP_RECORDER_SF_qd(
            WPP_GLOBAL_Control->DeviceExtension,
            Flink,
            0,
            18,
            (__int64)WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids,
            (char)this,
            (char)v10[1].Flink);
        }
        break;
    }
    if ( v17 )
      break;
LABEL_10:
    if ( (v9 & 0x80000000) == 0 )
      v9 = v12;
    if ( v11 )
    {
      CKsMdlcache::MdlCacheDeleteCachedEntry(this, (struct _KSPMDLCACHED_STREAM_POINTER *)&v6[-5], 1u, a4, &v16);
      v6 = v16;
    }
    else
    {
      v6 = v6->Flink;
      v16 = v6;
    }
    v7 = v17;
    a4 = v18;
  }
  while ( v6 != v5 );
  if ( !a3 )
    return v9;
  a4 = v18;
LABEL_35:
  if ( *((_DWORD *)this + 22) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)this + 10, *a4);
    KeWaitForSingleObject((char *)this + 112, Executive, 0, 0, 0);
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 10);
    *v18 = v15;
  }
  return v9;
}

```

## disassembly

```asm
0x18000a2f8  mov     r11, rsp
0x18000a2fb  mov     [r11+18h], rbx
0x18000a2ff  mov     [r11+20h], r9
0x18000a303  mov     [r11+10h], rdx
0x18000a307  push    rbp
0x18000a308  push    rsi
0x18000a309  push    rdi
0x18000a30a  push    r12
0x18000a30c  push    r13
0x18000a30e  push    r14
0x18000a310  push    r15
0x18000a312  sub     rsp, 40h
0x18000a316  mov     r14d, r8d
0x18000a319  lea     r13, [rcx+40h]
0x18000a31d  mov     rbx, [r13+0]
0x18000a321  xor     r8d, r8d
0x18000a324  mov     [r11+8], rbx
0x18000a328  mov     rax, rdx
0x18000a32b  mov     rdi, rcx
0x18000a32e  test    r14d, r14d
0x18000a331  jz      loc_18000A427
0x18000a337  mov     r15d, r8d
0x18000a33a  test    r14d, r14d
0x18000a33d  jz      short loc_18000A36D
0x18000a33f  cmp     rbx, r13
0x18000a342  jz      loc_18000A4FD
0x18000a348  add     rcx, 70h ; 'p'; Event
0x18000a34c  call    cs:__imp_KeClearEvent
0x18000a353  nop     dword ptr [rax+rax+00h]
0x18000a358  mov     rax, [rsp+78h+arg_8]
0x18000a360  xor     r8d, r8d
0x18000a363  mov     r9, [rsp+78h+arg_18]; unsigned __int8 *
0x18000a36b  jmp     short loc_18000A372
0x18000a36d  cmp     rbx, r13
0x18000a370  jz      short loc_18000A3EF
0x18000a372  lea     rsi, [rbx-50h]
0x18000a376  mov     bpl, r8b
0x18000a379  mov     r12d, r8d
0x18000a37c  test    rax, rax
0x18000a37f  jnz     loc_18000A418
0x18000a385  mov     edx, [rsi+10h]
0x18000a388  mov     ecx, edx
0x18000a38a  test    edx, edx
0x18000a38c  jnz     loc_18000A435
0x18000a392  mov     bpl, 1
0x18000a395  cmp     [rsp+78h+arg_8], r8
0x18000a39d  jnz     short loc_18000A3E6
0x18000a39f  test    r15d, r15d
0x18000a3a2  cmovns  r15d, r12d
0x18000a3a6  test    bpl, bpl
0x18000a3a9  jz      short loc_18000A40B
0x18000a3ab  lea     rax, [rsp+78h+arg_0]
0x18000a3b3  mov     r8b, 1; unsigned __int8
0x18000a3b6  mov     rdx, rsi; struct _KSPMDLCACHED_STREAM_POINTER *
0x18000a3b9  mov     [rsp+78h+Timeout], rax; struct _LIST_ENTRY **
0x18000a3be  mov     rcx, rdi; this
0x18000a3c1  call    ?MdlCacheDeleteCachedEntry@CKsMdlcache@@QEAAXPEAU_KSPMDLCACHED_STREAM_POINTER@@EAEAEPEAPEAU_LIST_ENTRY@@@Z; CKsMdlcache::MdlCacheDeleteCachedEntry(_KSPMDLCACHED_STREAM_POINTER *,uchar,uchar &,_LIST_ENTRY * *)
0x18000a3c6  mov     rbx, [rsp+78h+arg_0]
0x18000a3ce  xor     r8d, r8d
0x18000a3d1  mov     rax, [rsp+78h+arg_8]
0x18000a3d9  mov     r9, [rsp+78h+arg_18]
0x18000a3e1  cmp     rbx, r13
0x18000a3e4  jnz     short loc_18000A372
0x18000a3e6  test    r14d, r14d
0x18000a3e9  jnz     loc_18000A4F5
0x18000a3ef  mov     eax, r15d
0x18000a3f2  mov     rbx, [rsp+78h+arg_10]
0x18000a3fa  add     rsp, 40h
0x18000a3fe  pop     r15
0x18000a400  pop     r14
0x18000a402  pop     r13
0x18000a404  pop     r12
0x18000a406  pop     rdi
0x18000a407  pop     rsi
0x18000a408  pop     rbp
0x18000a409  retn
0x18000a40b  mov     rbx, [rbx]
0x18000a40e  mov     [rsp+78h+arg_0], rbx
0x18000a416  jmp     short loc_18000A3D1
0x18000a418  cmp     rax, [rsi+8]
0x18000a41c  jz      loc_18000A385
0x18000a422  jmp     loc_18000A39F
0x18000a427  cmp     [rcx+68h], r8d
0x18000a42b  jnz     loc_18000A337
0x18000a431  xor     eax, eax
0x18000a433  jmp     short loc_18000A3F2
0x18000a435  sub     ecx, 1
0x18000a438  jz      loc_18000A4E4
0x18000a43e  cmp     ecx, 1
0x18000a441  jz      short loc_18000A4B3
0x18000a443  lea     rax, WPP_RECORDER_INITIALIZED
0x18000a44a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000a451  jz      loc_18000A395
0x18000a457  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a45e  cmp     [rcx+48h], r8w
0x18000a463  jz      loc_18000A395
0x18000a469  mov     rcx, [rcx+40h]
0x18000a46d  lea     rax, WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids
0x18000a474  mov     [rsp+78h+var_48], edx
0x18000a478  mov     r9d, 12h
0x18000a47e  mov     [rsp+78h+var_50], rdi
0x18000a483  mov     dl, 5
0x18000a485  mov     [rsp+78h+Timeout], rax
0x18000a48a  call    WPP_RECORDER_SF_qd
0x18000a48f  jmp     short loc_18000A4AB
0x18000a491  mov     r8, r9; unsigned __int8 *
0x18000a494  mov     rdx, rsi; struct _KSPMDLCACHED_STREAM_POINTER *
0x18000a497  mov     rcx, rdi; this
0x18000a49a  call    ?MdlCacheCancelCachedEntry@CKsMdlcache@@QEAAJPEAU_KSPMDLCACHED_STREAM_POINTER@@AEAE@Z; CKsMdlcache::MdlCacheCancelCachedEntry(_KSPMDLCACHED_STREAM_POINTER *,uchar &)
0x18000a49f  mov     ebp, eax
0x18000a4a1  mov     r12d, eax
0x18000a4a4  shr     ebp, 1Fh
0x18000a4a7  xor     bpl, 1
0x18000a4ab  xor     r8d, r8d
0x18000a4ae  jmp     loc_18000A395
0x18000a4b3  test    r14d, r14d
0x18000a4b6  jnz     short loc_18000A4C3
0x18000a4b8  mov     r12d, 0C0000708h
0x18000a4be  jmp     loc_18000A395
0x18000a4c3  mov     r8, r9; unsigned __int8 *
0x18000a4c6  mov     rdx, rsi; struct _KSPMDLCACHED_STREAM_POINTER *
0x18000a4c9  mov     rcx, rdi; this
0x18000a4cc  call    ?MdlCacheCancelCachedEntry@CKsMdlcache@@QEAAJPEAU_KSPMDLCACHED_STREAM_POINTER@@AEAE@Z; CKsMdlcache::MdlCacheCancelCachedEntry(_KSPMDLCACHED_STREAM_POINTER *,uchar &)
0x18000a4d1  xor     r8d, r8d
0x18000a4d4  mov     r12d, eax
0x18000a4d7  test    eax, eax
0x18000a4d9  js      loc_18000A395
0x18000a4df  jmp     loc_18000A392
0x18000a4e4  test    r14d, r14d
0x18000a4e7  jnz     short loc_18000A491
0x18000a4e9  mov     dword ptr [rsi+10h], 2
0x18000a4f0  jmp     loc_18000A395
0x18000a4f5  mov     r9, [rsp+78h+arg_18]
0x18000a4fd  cmp     [rdi+58h], r8d
0x18000a501  jz      loc_18000A3EF
0x18000a507  mov     dl, [r9]; NewIrql
0x18000a50a  lea     rcx, [rdi+50h]; SpinLock
0x18000a50e  call    cs:__imp_KeReleaseSpinLock
0x18000a515  nop     dword ptr [rax+rax+00h]
0x18000a51a  lea     rcx, [rdi+70h]; Object
0x18000a51e  mov     [rsp+78h+Timeout], 0; Timeout
0x18000a527  xor     r9d, r9d; Alertable
0x18000a52a  xor     r8d, r8d; WaitMode
0x18000a52d  xor     edx, edx; WaitReason
0x18000a52f  call    cs:__imp_KeWaitForSingleObject
0x18000a536  nop     dword ptr [rax+rax+00h]
0x18000a53b  lea     rcx, [rdi+50h]; SpinLock
0x18000a53f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000a546  nop     dword ptr [rax+rax+00h]
0x18000a54b  mov     rcx, [rsp+78h+arg_18]
0x18000a553  mov     [rcx], al
0x18000a555  jmp     loc_18000A3EF
```

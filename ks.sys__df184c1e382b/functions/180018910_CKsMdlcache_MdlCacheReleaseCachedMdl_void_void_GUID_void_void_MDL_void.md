# CKsMdlcache::MdlCacheReleaseCachedMdl(void *,void (*)(_GUID,void *,void *),_MDL *,void *)

- ea: `0x180018910`
- end: `0x180018a7c`
- name: `?MdlCacheReleaseCachedMdl@CKsMdlcache@@UEAAJPEAXP6AXU_GUID@@00@ZPEAU_MDL@@0@Z`
- size: `364`
- prototype: `__int64 __fastcall(CKsMdlcache *this, void *, void (*)(struct _GUID *__struct_ptr, void *, void *), struct _MDL *, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000a560`
- `0x18000dddc`
- `0x1800159b0`
- `0x180018910`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180018a14`
- `ntoskrnl!ObfDereferenceObject` at `0x180018a14`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001898a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001898a`
- `ntoskrnl!KeReleaseSpinLock` at `0x180018a55`
- `ntoskrnl!KeReleaseSpinLock` at `0x180018a55`
- `ntoskrnl!KeReadStateEvent` at `0x18001899d`
- `ntoskrnl!KeReadStateEvent` at `0x18001899d`

## pseudocode

```c
__int64 __fastcall CKsMdlcache::MdlCacheReleaseCachedMdl(
        CKsMdlcache *this,
        void *a2,
        void (*a3)(struct _GUID *__struct_ptr, void *, void *),
        struct _MDL *a4,
        _DWORD *a5)
{
  unsigned int v6; // esi
  KIRQL v7; // r12
  LONG StateEvent; // eax
  int v9; // r8d
  unsigned __int8 *v10; // r9
  int v11; // edx
  LONG v12; // r14d
  unsigned __int8 v13; // bp
  void *v14; // rcx
  char v16; // [rsp+28h] [rbp-60h]

  if ( a2 && a5 )
  {
    v6 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      v16 = (char)a2;
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        20,
        (__int64)WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids,
        v16);
    }
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 10);
    StateEvent = KeReadStateEvent((PRKEVENT)((char *)this + 112));
    v11 = *(a5 - 14);
    v12 = StateEvent;
    v13 = StateEvent == 0;
    if ( v11 )
    {
      if ( v11 != 1 )
      {
        if ( v11 != 2 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v11) = 2;
            WPP_RECORDER_SF_qd(
              WPP_GLOBAL_Control->DeviceExtension,
              v11,
              v9,
              21,
              (__int64)WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids,
              (char)this,
              *(a5 - 14));
          }
          goto LABEL_15;
        }
LABEL_12:
        if ( !*((_QWORD *)a5 - 1) )
          CKsMdlcache::MdlCacheDeleteCachedEntry(this, (struct _KSPMDLCACHED_STREAM_POINTER *)(a5 - 18), v13, v10, 0);
        goto LABEL_15;
      }
      v14 = (void *)*((_QWORD *)a5 - 5);
      *((_QWORD *)a5 - 6) = 0;
      *((_QWORD *)a5 - 4) = 0;
      ObfDereferenceObject(v14);
      *((_QWORD *)a5 - 5) = 0;
      *(a5 - 14) = 0;
      if ( !v12 )
        goto LABEL_12;
    }
    else
    {
      v6 = -1073741436;
    }
LABEL_15:
    KeReleaseSpinLock((PKSPIN_LOCK)this + 10, v7);
    return v6;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180018910  push    rbx
0x180018912  push    rbp
0x180018913  push    rsi
0x180018914  push    rdi
0x180018915  push    r12
0x180018917  push    r13
0x180018919  push    r14
0x18001891b  push    r15
0x18001891d  sub     rsp, 48h
0x180018921  xor     r13d, r13d
0x180018924  mov     rdi, rcx
0x180018927  test    rdx, rdx
0x18001892a  jz      loc_180018A65
0x180018930  mov     rbx, [rsp+88h+arg_20]
0x180018938  test    rbx, rbx
0x18001893b  jz      loc_180018A65
0x180018941  mov     esi, r13d
0x180018944  lea     rax, WPP_RECORDER_INITIALIZED
0x18001894b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180018952  lea     r8, WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids
0x180018959  jz      short loc_180018986
0x18001895b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018962  cmp     [rcx+48h], r13w
0x180018967  jz      short loc_180018986
0x180018969  mov     rcx, [rcx+40h]
0x18001896d  lea     r9d, [r13+14h]
0x180018971  mov     [rsp+88h+var_60], rdx
0x180018976  mov     dl, 5
0x180018978  mov     [rsp+88h+var_68], r8
0x18001897d  lea     r8d, [r13+1]
0x180018981  call    WPP_RECORDER_SF_q
0x180018986  lea     rcx, [rdi+50h]; SpinLock
0x18001898a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180018991  nop     dword ptr [rax+rax+00h]
0x180018996  lea     rcx, [rdi+70h]; Event
0x18001899a  mov     r12b, al
0x18001899d  call    cs:__imp_KeReadStateEvent
0x1800189a4  nop     dword ptr [rax+rax+00h]
0x1800189a9  mov     edx, [rbx-38h]
0x1800189ac  test    eax, eax
0x1800189ae  mov     r14d, eax
0x1800189b1  mov     ecx, edx
0x1800189b3  setz    bpl
0x1800189b7  test    edx, edx
0x1800189b9  jz      loc_180018A49
0x1800189bf  sub     ecx, 1
0x1800189c2  jz      short loc_180018A08
0x1800189c4  cmp     ecx, 1
0x1800189c7  jz      short loc_180018A2D
0x1800189c9  lea     rax, WPP_RECORDER_INITIALIZED
0x1800189d0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800189d7  jz      short loc_180018A4E
0x1800189d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189e0  lea     rax, WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids
0x1800189e7  mov     [rsp+88h+var_58], edx
0x1800189eb  mov     r9d, 15h
0x1800189f1  mov     [rsp+88h+var_60], rdi
0x1800189f6  mov     dl, 2
0x1800189f8  mov     [rsp+88h+var_68], rax
0x1800189fd  mov     rcx, [rcx+40h]
0x180018a01  call    WPP_RECORDER_SF_qd
0x180018a06  jmp     short loc_180018A4E
0x180018a08  mov     rcx, [rbx-28h]; Object
0x180018a0c  mov     [rbx-30h], r13
0x180018a10  mov     [rbx-20h], r13
0x180018a14  call    cs:__imp_ObfDereferenceObject
0x180018a1b  nop     dword ptr [rax+rax+00h]
0x180018a20  mov     [rbx-28h], r13
0x180018a24  mov     [rbx-38h], r13d
0x180018a28  test    r14d, r14d
0x180018a2b  jnz     short loc_180018A4E
0x180018a2d  cmp     [rbx-8], r13
0x180018a31  jnz     short loc_180018A4E
0x180018a33  mov     r8b, bpl; unsigned __int8
0x180018a36  mov     [rsp+88h+var_68], r13; struct _LIST_ENTRY **
0x180018a3b  lea     rdx, [rbx-48h]; struct _KSPMDLCACHED_STREAM_POINTER *
0x180018a3f  mov     rcx, rdi; this
0x180018a42  call    ?MdlCacheDeleteCachedEntry@CKsMdlcache@@QEAAXPEAU_KSPMDLCACHED_STREAM_POINTER@@EAEAEPEAPEAU_LIST_ENTRY@@@Z; CKsMdlcache::MdlCacheDeleteCachedEntry(_KSPMDLCACHED_STREAM_POINTER *,uchar,uchar &,_LIST_ENTRY * *)
0x180018a47  jmp     short loc_180018A4E
0x180018a49  mov     esi, 0C0000184h
0x180018a4e  mov     dl, r12b; NewIrql
0x180018a51  lea     rcx, [rdi+50h]; SpinLock
0x180018a55  call    cs:__imp_KeReleaseSpinLock
0x180018a5c  nop     dword ptr [rax+rax+00h]
0x180018a61  mov     eax, esi
0x180018a63  jmp     short loc_180018A6A
0x180018a65  mov     eax, 0C000000Dh
0x180018a6a  add     rsp, 48h
0x180018a6e  pop     r15
0x180018a70  pop     r14
0x180018a72  pop     r13
0x180018a74  pop     r12
0x180018a76  pop     rdi
0x180018a77  pop     rsi
0x180018a78  pop     rbp
0x180018a79  pop     rbx
0x180018a7a  retn
```

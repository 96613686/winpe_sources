# CKsMdlcache::MdlCacheReleaseCachedMdl(void *,void (*)(_GUID,void *,void *),_MDL *,void *)

- ea: `0x1800188c0`
- end: `0x180018a2c`
- name: `?MdlCacheReleaseCachedMdl@CKsMdlcache@@UEAAJPEAXP6AXU_GUID@@00@ZPEAU_MDL@@0@Z`
- size: `364`
- prototype: `__int64 __usercall@<rax>(CKsMdlcache *__hidden this@<rcx>, void *@<rdx>, void (*)(struct _GUID *__struct_ptr, void *, void *)@<r8>, struct _MDL *@<r9>, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000a560`
- `0x18000dddc`
- `0x180015960`
- `0x1800188c0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1800189c4`
- `ntoskrnl!ObfDereferenceObject` at `0x1800189c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001893a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001893a`
- `ntoskrnl!KeReleaseSpinLock` at `0x180018a05`
- `ntoskrnl!KeReleaseSpinLock` at `0x180018a05`
- `ntoskrnl!KeReadStateEvent` at `0x18001894d`
- `ntoskrnl!KeReadStateEvent` at `0x18001894d`

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
0x1800188c0  push    rbx
0x1800188c2  push    rbp
0x1800188c3  push    rsi
0x1800188c4  push    rdi
0x1800188c5  push    r12
0x1800188c7  push    r13
0x1800188c9  push    r14
0x1800188cb  push    r15
0x1800188cd  sub     rsp, 48h
0x1800188d1  xor     r13d, r13d
0x1800188d4  mov     rdi, rcx
0x1800188d7  test    rdx, rdx
0x1800188da  jz      loc_180018A15
0x1800188e0  mov     rbx, [rsp+88h+arg_20]
0x1800188e8  test    rbx, rbx
0x1800188eb  jz      loc_180018A15
0x1800188f1  mov     esi, r13d
0x1800188f4  lea     rax, WPP_RECORDER_INITIALIZED
0x1800188fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180018902  lea     r8, WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids
0x180018909  jz      short loc_180018936
0x18001890b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018912  cmp     [rcx+48h], r13w
0x180018917  jz      short loc_180018936
0x180018919  mov     rcx, [rcx+40h]
0x18001891d  lea     r9d, [r13+14h]
0x180018921  mov     [rsp+88h+var_60], rdx
0x180018926  mov     dl, 5
0x180018928  mov     [rsp+88h+var_68], r8
0x18001892d  lea     r8d, [r13+1]
0x180018931  call    WPP_RECORDER_SF_q
0x180018936  lea     rcx, [rdi+50h]; SpinLock
0x18001893a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180018941  nop     dword ptr [rax+rax+00h]
0x180018946  lea     rcx, [rdi+70h]; Event
0x18001894a  mov     r12b, al
0x18001894d  call    cs:__imp_KeReadStateEvent
0x180018954  nop     dword ptr [rax+rax+00h]
0x180018959  mov     edx, [rbx-38h]
0x18001895c  test    eax, eax
0x18001895e  mov     r14d, eax
0x180018961  mov     ecx, edx
0x180018963  setz    bpl
0x180018967  test    edx, edx
0x180018969  jz      loc_1800189F9
0x18001896f  sub     ecx, 1
0x180018972  jz      short loc_1800189B8
0x180018974  cmp     ecx, 1
0x180018977  jz      short loc_1800189DD
0x180018979  lea     rax, WPP_RECORDER_INITIALIZED
0x180018980  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180018987  jz      short loc_1800189FE
0x180018989  mov     rcx, cs:WPP_GLOBAL_Control
0x180018990  lea     rax, WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids
0x180018997  mov     [rsp+88h+var_58], edx
0x18001899b  mov     r9d, 15h
0x1800189a1  mov     [rsp+88h+var_60], rdi
0x1800189a6  mov     dl, 2
0x1800189a8  mov     [rsp+88h+var_68], rax
0x1800189ad  mov     rcx, [rcx+40h]
0x1800189b1  call    WPP_RECORDER_SF_qd
0x1800189b6  jmp     short loc_1800189FE
0x1800189b8  mov     rcx, [rbx-28h]; Object
0x1800189bc  mov     [rbx-30h], r13
0x1800189c0  mov     [rbx-20h], r13
0x1800189c4  call    cs:__imp_ObfDereferenceObject
0x1800189cb  nop     dword ptr [rax+rax+00h]
0x1800189d0  mov     [rbx-28h], r13
0x1800189d4  mov     [rbx-38h], r13d
0x1800189d8  test    r14d, r14d
0x1800189db  jnz     short loc_1800189FE
0x1800189dd  cmp     [rbx-8], r13
0x1800189e1  jnz     short loc_1800189FE
0x1800189e3  mov     r8b, bpl; unsigned __int8
0x1800189e6  mov     [rsp+88h+var_68], r13; struct _LIST_ENTRY **
0x1800189eb  lea     rdx, [rbx-48h]; struct _KSPMDLCACHED_STREAM_POINTER *
0x1800189ef  mov     rcx, rdi; this
0x1800189f2  call    ?MdlCacheDeleteCachedEntry@CKsMdlcache@@QEAAXPEAU_KSPMDLCACHED_STREAM_POINTER@@EAEAEPEAPEAU_LIST_ENTRY@@@Z; CKsMdlcache::MdlCacheDeleteCachedEntry(_KSPMDLCACHED_STREAM_POINTER *,uchar,uchar &,_LIST_ENTRY * *)
0x1800189f7  jmp     short loc_1800189FE
0x1800189f9  mov     esi, 0C0000184h
0x1800189fe  mov     dl, r12b; NewIrql
0x180018a01  lea     rcx, [rdi+50h]; SpinLock
0x180018a05  call    cs:__imp_KeReleaseSpinLock
0x180018a0c  nop     dword ptr [rax+rax+00h]
0x180018a11  mov     eax, esi
0x180018a13  jmp     short loc_180018A1A
0x180018a15  mov     eax, 0C000000Dh
0x180018a1a  add     rsp, 48h
0x180018a1e  pop     r15
0x180018a20  pop     r14
0x180018a22  pop     r13
0x180018a24  pop     r12
0x180018a26  pop     rdi
0x180018a27  pop     rsi
0x180018a28  pop     rbp
0x180018a29  pop     rbx
0x180018a2a  retn
```

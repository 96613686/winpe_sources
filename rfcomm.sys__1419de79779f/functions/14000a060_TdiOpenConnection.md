# TdiOpenConnection

- ea: `0x14000a060`
- end: `0x14000a376`
- name: `TdiOpenConnection`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007d40`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140007488`
- `0x14000a060`
- `0x14001e74c`
- `0x14001e8f4`
- `0x14001ee30`
- `0x140034048`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000a1a6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000a1a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a2ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a2ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a31a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a31a`
- `ntoskrnl!ExAllocatePool2` at `0x14000a0db`
- `ntoskrnl!ExAllocatePool2` at `0x14000a0db`
- `ntoskrnl!ObfReferenceObject` at `0x14000a124`
- `ntoskrnl!ObfReferenceObject` at `0x14000a124`

## string_xrefs

- `0x14000a25b`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiOpenConnection(
        __int64 a1,
        __int64 a2,
        void *a3,
        int a4,
        __int64 *a5,
        __int64 a6,
        unsigned __int16 a7)
{
  unsigned int v11; // ebx
  __int64 Pool2; // rax
  __int64 v13; // rdi
  struct _KPROCESS *v14; // rcx
  int v15; // edx
  bool v16; // cl
  bool v17; // al
  __int64 *v18; // rcx
  bool v20; // [rsp+30h] [rbp-48h] BYREF

  v20 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      61,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  if ( a7 >= 8u )
  {
    Pool2 = ExAllocatePool2(64, 832, 1313039954);
    v13 = Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)(Pool2 + 16) = 1313754947;
      TdiConnStateLocked(Pool2, 0);
      *(_QWORD *)(v13 + 328) = a6;
      *(_QWORD *)(v13 + 72) = a2;
      *(_QWORD *)(v13 + 88) = a3;
      ObfReferenceObject(a3);
      v14 = *(struct _KPROCESS **)(v13 + 88);
      *(_DWORD *)(v13 + 824) = a4;
      if ( (int)QueryIsAppContainer(v14, &v20) >= 0 )
      {
        v16 = v20;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            19,
            62,
            (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
        v16 = 1;
      }
      v17 = !*(_BYTE *)(*(_QWORD *)(a1 + 80) + 48LL) && v16;
      *(_BYTE *)(v13 + 828) = v17;
      *(_WORD *)(v13 + 829) = 256;
      *(_BYTE *)(v13 + 820) = 0;
      KeInitializeSpinLock((PKSPIN_LOCK)(v13 + 48));
      IrpList_InitEx(v13 + 344, v13 + 360);
      IrpList_InitEx(v13 + 400, v13 + 416);
      IrpList_InitEx(v13 + 456, v13 + 472);
      IrpList_InitEx(v13 + 568, v13 + 584);
      IrpList_InitEx(v13 + 512, v13 + 528);
      IrpList_InitEx(v13 + 680, v13 + 696);
      IrpList_InitEx(v13 + 736, v13 + 752);
      IrpList_InitEx(v13 + 624, v13 + 640);
      *(_QWORD *)(v13 + 800) = v13 + 792;
      *(_QWORD *)(v13 + 792) = v13 + 792;
      *(_QWORD *)(v13 + 288) = v13 + 280;
      *(_QWORD *)(v13 + 280) = v13 + 280;
      *(_QWORD *)(v13 + 304) = v13 + 296;
      *(_QWORD *)(v13 + 296) = v13 + 296;
      *(_QWORD *)(v13 + 320) = v13 + 312;
      *(_QWORD *)(v13 + 312) = v13 + 312;
      RefObj_InitEx(
        v13 + 24,
        (unsigned int)FreeConnObject,
        1414090313,
        1598,
        (__int64)"onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
      *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
      RefObj_AddRefEx(a1 + 24, 1313754947, 1602, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
      *(_QWORD *)(v13 + 64) = a1;
      RefObj_AddRefEx(v13 + 24, 541672532, 1605, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
      v18 = *(__int64 **)(a1 + 104);
      if ( *v18 != a1 + 96 )
        __fastfail(3u);
      *(_QWORD *)(v13 + 8) = v18;
      v11 = 0;
      *(_QWORD *)v13 = a1 + 96;
      *v18 = v13;
      *(_QWORD *)(a1 + 104) = v13;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 48), *(_BYTE *)(a1 + 56));
      *(_QWORD *)(v13 + 336) = 0;
      *a5 = v13;
    }
    else
    {
      v11 = -1073741670;
    }
  }
  else
  {
    v11 = -2147483628;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      63,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      v11);
  return v11;
}

```

## disassembly

```asm
0x14000a060  push    rbx
0x14000a062  push    rbp
0x14000a063  push    rsi
0x14000a064  push    rdi
0x14000a065  push    r12
0x14000a067  push    r13
0x14000a069  push    r14
0x14000a06b  sub     rsp, 40h
0x14000a06f  mov     ebp, r9d
0x14000a072  mov     [rsp+78h+var_48], 0
0x14000a077  mov     rbx, r8
0x14000a07a  mov     r14, rdx
0x14000a07d  mov     rsi, rcx
0x14000a080  lea     r12, WPP_RECORDER_INITIALIZED
0x14000a087  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a08e  lea     r13, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000a095  jz      short loc_14000A0B6
0x14000a097  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a09e  mov     r9d, 3Dh ; '='
0x14000a0a4  mov     [rsp+78h+var_58], r13
0x14000a0a9  mov     rcx, [rcx+40h]
0x14000a0ad  lea     r8d, [r9-2Eh]
0x14000a0b1  call    WPP_RECORDER_SF_
0x14000a0b6  cmp     [rsp+78h+arg_30], 8
0x14000a0bf  jnb     short loc_14000A0CB
0x14000a0c1  mov     ebx, 80000014h
0x14000a0c6  jmp     loc_14000A338
0x14000a0cb  mov     edx, 340h
0x14000a0d0  mov     ecx, 40h ; '@'
0x14000a0d5  mov     r8d, 4E436652h
0x14000a0db  call    cs:__imp_ExAllocatePool2
0x14000a0e2  nop     dword ptr [rax+rax+00h]
0x14000a0e7  mov     rdi, rax
0x14000a0ea  test    rax, rax
0x14000a0ed  jnz     short loc_14000A0F9
0x14000a0ef  mov     ebx, 0C000009Ah
0x14000a0f4  jmp     loc_14000A338
0x14000a0f9  xor     edx, edx
0x14000a0fb  mov     dword ptr [rax+10h], 4E4E4F43h
0x14000a102  mov     rcx, rdi
0x14000a105  call    TdiConnStateLocked
0x14000a10a  mov     rax, [rsp+78h+arg_28]
0x14000a112  mov     rcx, rbx; Object
0x14000a115  mov     [rdi+148h], rax
0x14000a11c  mov     [rdi+48h], r14
0x14000a120  mov     [rdi+58h], rbx
0x14000a124  call    cs:__imp_ObfReferenceObject
0x14000a12b  nop     dword ptr [rax+rax+00h]
0x14000a130  mov     rcx, [rdi+58h]
0x14000a134  lea     rdx, [rsp+78h+var_48]
0x14000a139  mov     [rdi+338h], ebp
0x14000a13f  call    QueryIsAppContainer
0x14000a144  test    eax, eax
0x14000a146  jns     short loc_14000A174
0x14000a148  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a14f  jz      short loc_14000A170
0x14000a151  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a158  mov     r9d, 3Eh ; '>'
0x14000a15e  mov     [rsp+78h+var_58], r13
0x14000a163  mov     rcx, [rcx+40h]
0x14000a167  lea     r8d, [r9-2Bh]
0x14000a16b  call    WPP_RECORDER_SF_
0x14000a170  mov     cl, 1
0x14000a172  jmp     short loc_14000A178
0x14000a174  mov     cl, [rsp+78h+var_48]
0x14000a178  mov     rax, [rsi+50h]
0x14000a17c  cmp     byte ptr [rax+30h], 0
0x14000a180  jnz     short loc_14000A18A
0x14000a182  test    cl, cl
0x14000a184  jz      short loc_14000A18A
0x14000a186  mov     al, 1
0x14000a188  jmp     short loc_14000A18C
0x14000a18a  xor     al, al
0x14000a18c  lea     rcx, [rdi+30h]; SpinLock
0x14000a190  mov     [rdi+33Ch], al
0x14000a196  mov     word ptr [rdi+33Dh], 100h
0x14000a19f  mov     byte ptr [rdi+334h], 0
0x14000a1a6  call    cs:__imp_KeInitializeSpinLock
0x14000a1ad  nop     dword ptr [rax+rax+00h]
0x14000a1b2  lea     rdx, [rdi+168h]
0x14000a1b9  lea     rcx, [rdi+158h]
0x14000a1c0  call    IrpList_InitEx
0x14000a1c5  lea     rdx, [rdi+1A0h]
0x14000a1cc  lea     rcx, [rdi+190h]
0x14000a1d3  call    IrpList_InitEx
0x14000a1d8  lea     rdx, [rdi+1D8h]
0x14000a1df  lea     rcx, [rdi+1C8h]
0x14000a1e6  call    IrpList_InitEx
0x14000a1eb  lea     rdx, [rdi+248h]
0x14000a1f2  lea     rcx, [rdi+238h]
0x14000a1f9  call    IrpList_InitEx
0x14000a1fe  lea     rdx, [rdi+210h]
0x14000a205  lea     rcx, [rdi+200h]
0x14000a20c  call    IrpList_InitEx
0x14000a211  lea     rdx, [rdi+2B8h]
0x14000a218  lea     rcx, [rdi+2A8h]
0x14000a21f  call    IrpList_InitEx
0x14000a224  lea     rdx, [rdi+2F0h]
0x14000a22b  lea     rcx, [rdi+2E0h]
0x14000a232  call    IrpList_InitEx
0x14000a237  lea     rdx, [rdi+280h]
0x14000a23e  lea     rcx, [rdi+270h]
0x14000a245  call    IrpList_InitEx
0x14000a24a  lea     rax, [rdi+318h]
0x14000a251  mov     r9d, 63Eh
0x14000a257  mov     [rax+8], rax
0x14000a25b  lea     r14, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000a262  mov     [rax], rax
0x14000a265  lea     rdx, FreeConnObject
0x14000a26c  lea     rax, [rdi+118h]
0x14000a273  mov     [rsp+78h+var_58], r14
0x14000a278  mov     [rax+8], rax
0x14000a27c  lea     rcx, [rdi+18h]
0x14000a280  mov     [rax], rax
0x14000a283  mov     r8d, 54494E49h
0x14000a289  lea     rax, [rdi+128h]
0x14000a290  mov     [rax+8], rax
0x14000a294  mov     [rax], rax
0x14000a297  lea     rax, [rdi+138h]
0x14000a29e  mov     [rax+8], rax
0x14000a2a2  mov     [rax], rax
0x14000a2a5  call    RefObj_InitEx
0x14000a2aa  lea     rcx, [rsi+30h]; SpinLock
0x14000a2ae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a2b5  nop     dword ptr [rax+rax+00h]
0x14000a2ba  lea     rcx, [rsi+18h]
0x14000a2be  mov     r9, r14
0x14000a2c1  mov     edx, 4E4E4F43h
0x14000a2c6  mov     [rsi+38h], al
0x14000a2c9  mov     r8d, 642h
0x14000a2cf  call    RefObj_AddRefEx
0x14000a2d4  mov     r9, r14
0x14000a2d7  mov     [rdi+40h], rsi
0x14000a2db  mov     edx, 20494454h
0x14000a2e0  lea     rcx, [rdi+18h]
0x14000a2e4  mov     r8d, 645h
0x14000a2ea  call    RefObj_AddRefEx
0x14000a2ef  lea     rax, [rsi+60h]
0x14000a2f3  mov     rcx, [rax+8]
0x14000a2f7  cmp     [rcx], rax
0x14000a2fa  jz      short loc_14000A303
0x14000a2fc  mov     ecx, 3
0x14000a301  int     29h; Win8: RtlFailFast(ecx)
0x14000a303  mov     [rdi+8], rcx
0x14000a307  xor     ebx, ebx
0x14000a309  mov     [rdi], rax
0x14000a30c  mov     [rcx], rdi
0x14000a30f  lea     rcx, [rsi+30h]; SpinLock
0x14000a313  mov     [rax+8], rdi
0x14000a317  mov     dl, [rsi+38h]; NewIrql
0x14000a31a  call    cs:__imp_KeReleaseSpinLock
0x14000a321  nop     dword ptr [rax+rax+00h]
0x14000a326  mov     rax, [rsp+78h+arg_20]
0x14000a32e  mov     [rdi+150h], rbx
0x14000a335  mov     [rax], rdi
0x14000a338  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a33f  jz      short loc_14000A364
0x14000a341  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a348  mov     r9d, 3Fh ; '?'
0x14000a34e  mov     [rsp+78h+var_50], ebx
0x14000a352  mov     [rsp+78h+var_58], r13
0x14000a357  mov     rcx, [rcx+40h]
0x14000a35b  lea     r8d, [r9-30h]
0x14000a35f  call    WPP_RECORDER_SF_d
0x14000a364  mov     eax, ebx
0x14000a366  add     rsp, 40h
0x14000a36a  pop     r14
0x14000a36c  pop     r13
0x14000a36e  pop     r12
0x14000a370  pop     rdi
0x14000a371  pop     rsi
0x14000a372  pop     rbp
0x14000a373  pop     rbx
0x14000a374  retn
```

# ClRegisterSapComplete

- ea: `0x140006860`
- end: `0x140006a4a`
- name: `ClRegisterSapComplete`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400060f0`

## callees

- `0x140006430`
- `0x140006860`
- `0x14000a290`
- `0x14000a68c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400069de`
- `ntoskrnl!KeSetEvent` at `0x1400069de`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000691f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000698b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400069ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000691f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000698b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400069ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400068c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006935`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400069bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400068c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006935`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400069bb`
- `NDIS!NdisClCloseAddressFamily` at `0x14000699b`
- `NDIS!NdisClCloseAddressFamily` at `0x14000699b`

## pseudocode

```c
void __fastcall ClRegisterSapComplete(int a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  KIRQL v8; // al
  unsigned int v9; // edx
  KSPIN_LOCK *v10; // rcx
  KIRQL *v11; // rsi
  KSPIN_LOCK v12; // rcx
  __int64 **v13; // rax
  __int64 **v14; // rcx
  NDIS_STATUS v15; // eax
  KIRQL v16; // al
  bool v17; // zf

  v4 = a2[4];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, a2, a1);
  }
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a2 + 11);
  v9 = a2[3] & 0xFFFFFFDF;
  *((_BYTE *)a2 + 96) = v8;
  v10 = (KSPIN_LOCK *)(a2 + 11);
  if ( a1 )
  {
    *((_DWORD *)a2 + 6) = v9 & 0xFFFFFF75 | 0x88;
    KeReleaseSpinLock(v10, v8);
    v11 = (KIRQL *)(v4 + 512);
    *(_BYTE *)(v4 + 512) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 504));
    v12 = *a2;
    if ( *(__int64 **)(*a2 + 8) != a2
      || (v13 = (__int64 **)a2[1], *v13 != a2)
      || (*v13 = (__int64 *)v12,
          *(_QWORD *)(v12 + 8) = v13,
          v14 = *(__int64 ***)(v4 + 248),
          *v14 != (__int64 *)(v4 + 240)) )
    {
      __fastfail(3u);
    }
    a2[1] = (__int64)v14;
    *a2 = v4 + 240;
    *v14 = a2;
    *(_QWORD *)(v4 + 248) = a2;
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 504), *v11);
    v15 = NdisClCloseAddressFamily((NDIS_HANDLE)a2[7]);
    if ( v15 != 259 )
      ClCloseAfComplete(v15, a2);
  }
  else
  {
    a2[8] = a4;
    *((_DWORD *)a2 + 6) = v9 | 0x40;
    KeReleaseSpinLock(v10, v8);
    v11 = (KIRQL *)(v4 + 512);
  }
  v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 504));
  v17 = (*(_DWORD *)(v4 + 448))-- == 1;
  *v11 = v16;
  if ( v17 )
    KeSetEvent((PRKEVENT)(v4 + 456), 0, 0);
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 504), *v11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
  }
}

```

## disassembly

```asm
0x140006860  mov     [rsp+arg_8], rbx
0x140006865  mov     [rsp+arg_10], rbp
0x14000686a  push    rsi
0x14000686b  push    rdi
0x14000686c  push    r13
0x14000686e  push    r14
0x140006870  push    r15
0x140006872  sub     rsp, 30h
0x140006876  mov     rdi, [rdx+20h]
0x14000687a  mov     r15, r9
0x14000687d  mov     rbx, rdx
0x140006880  mov     r14d, ecx
0x140006883  mov     rcx, cs:WPP_GLOBAL_Control
0x14000688a  lea     r13, WPP_GLOBAL_Control
0x140006891  cmp     rcx, r13
0x140006894  jz      short loc_1400068C2
0x140006896  test    dword ptr [rcx+2Ch], 8000h
0x14000689d  jz      short loc_1400068C2
0x14000689f  cmp     byte ptr [rcx+29h], 5
0x1400068a3  jb      short loc_1400068C2
0x1400068a5  mov     rcx, [rcx+18h]
0x1400068a9  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x1400068b0  mov     edx, 15h
0x1400068b5  mov     [rsp+58h+var_38], r14d
0x1400068ba  mov     r9, rbx
0x1400068bd  call    WPP_SF_qD
0x1400068c2  lea     rsi, [rbx+58h]
0x1400068c6  mov     rcx, rsi; SpinLock
0x1400068c9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400068d0  nop     dword ptr [rax+rax+00h]
0x1400068d5  mov     edx, [rbx+18h]
0x1400068d8  lea     rbp, [rdi+1F8h]
0x1400068df  and     edx, 0FFFFFFDFh
0x1400068e2  mov     [rbx+60h], al
0x1400068e5  mov     rcx, rsi; SpinLock
0x1400068e8  test    r14d, r14d
0x1400068eb  jnz     short loc_140006911
0x1400068ed  or      edx, 40h
0x1400068f0  mov     [rbx+40h], r15
0x1400068f4  mov     [rbx+18h], edx
0x1400068f7  mov     dl, al; NewIrql
0x1400068f9  call    cs:__imp_KeReleaseSpinLock
0x140006900  nop     dword ptr [rax+rax+00h]
0x140006905  lea     rsi, [rdi+200h]
0x14000690c  jmp     loc_1400069B8
0x140006911  and     edx, 0FFFFFFFDh
0x140006914  or      edx, 88h
0x14000691a  mov     [rbx+18h], edx
0x14000691d  mov     dl, al; NewIrql
0x14000691f  call    cs:__imp_KeReleaseSpinLock
0x140006926  nop     dword ptr [rax+rax+00h]
0x14000692b  mov     rcx, rbp; SpinLock
0x14000692e  lea     rsi, [rdi+200h]
0x140006935  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000693c  nop     dword ptr [rax+rax+00h]
0x140006941  mov     [rsi], al
0x140006943  mov     rcx, [rbx]
0x140006946  cmp     [rcx+8], rbx
0x14000694a  jnz     loc_140006A43
0x140006950  mov     rax, [rbx+8]
0x140006954  cmp     [rax], rbx
0x140006957  jnz     loc_140006A43
0x14000695d  mov     [rax], rcx
0x140006960  mov     [rcx+8], rax
0x140006964  lea     rax, [rdi+0F0h]
0x14000696b  mov     rcx, [rax+8]
0x14000696f  cmp     [rcx], rax
0x140006972  jnz     loc_140006A43
0x140006978  mov     [rbx+8], rcx
0x14000697c  mov     [rbx], rax
0x14000697f  mov     [rcx], rbx
0x140006982  mov     rcx, rbp; SpinLock
0x140006985  mov     [rax+8], rbx
0x140006989  mov     dl, [rsi]; NewIrql
0x14000698b  call    cs:__imp_KeReleaseSpinLock
0x140006992  nop     dword ptr [rax+rax+00h]
0x140006997  mov     rcx, [rbx+38h]; NdisAfHandle
0x14000699b  call    cs:__imp_NdisClCloseAddressFamily
0x1400069a2  nop     dword ptr [rax+rax+00h]
0x1400069a7  cmp     eax, 103h
0x1400069ac  jz      short loc_1400069B8
0x1400069ae  mov     rdx, rbx
0x1400069b1  mov     ecx, eax
0x1400069b3  call    ClCloseAfComplete
0x1400069b8  mov     rcx, rbp; SpinLock
0x1400069bb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400069c2  nop     dword ptr [rax+rax+00h]
0x1400069c7  add     dword ptr [rdi+1C0h], 0FFFFFFFFh
0x1400069ce  mov     [rsi], al
0x1400069d0  jnz     short loc_1400069EA
0x1400069d2  lea     rcx, [rdi+1C8h]; Event
0x1400069d9  xor     r8d, r8d; Wait
0x1400069dc  xor     edx, edx; Increment
0x1400069de  call    cs:__imp_KeSetEvent
0x1400069e5  nop     dword ptr [rax+rax+00h]
0x1400069ea  mov     dl, [rsi]; NewIrql
0x1400069ec  mov     rcx, rbp; SpinLock
0x1400069ef  call    cs:__imp_KeReleaseSpinLock
0x1400069f6  nop     dword ptr [rax+rax+00h]
0x1400069fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a02  cmp     rcx, r13
0x140006a05  jz      short loc_140006A2B
0x140006a07  test    dword ptr [rcx+2Ch], 8000h
0x140006a0e  jz      short loc_140006A2B
0x140006a10  cmp     byte ptr [rcx+29h], 5
0x140006a14  jb      short loc_140006A2B
0x140006a16  mov     rcx, [rcx+18h]
0x140006a1a  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140006a21  mov     edx, 16h
0x140006a26  call    WPP_SF_
0x140006a2b  mov     rbx, [rsp+58h+arg_8]
0x140006a30  mov     rbp, [rsp+58h+arg_10]
0x140006a35  add     rsp, 30h
0x140006a39  pop     r15
0x140006a3b  pop     r14
0x140006a3d  pop     r13
0x140006a3f  pop     rdi
0x140006a40  pop     rsi
0x140006a41  retn
0x140006a43  mov     ecx, 3
0x140006a48  int     29h; Win8: RtlFailFast(ecx)
```

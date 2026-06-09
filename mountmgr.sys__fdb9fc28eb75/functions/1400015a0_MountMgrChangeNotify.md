# MountMgrChangeNotify

- ea: `0x1400015a0`
- end: `0x14000172a`
- name: `MountMgrChangeNotify`
- size: `394`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400147a0`

## callees

- `0x1400015a0`
- `0x140001ae0`

## import_xrefs

- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140001626`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140001626`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000163d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400016ce`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000163d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400016ce`

## pseudocode

```c
__int64 __fastcall MountMgrChangeNotify(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  _DWORD *v6; // rax
  int v7; // ecx
  __int64 v9; // r8
  __int64 v10; // rdi
  _QWORD *v11; // rcx
  KIRQL Irql; // [rsp+38h] [rbp+10h] BYREF

  v3 = *(_QWORD *)(a2 + 184);
  Irql = 0;
  if ( *(_DWORD *)(v3 + 16) < 4u || *(_DWORD *)(v3 + 8) < 4u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 356, a3, 3221225485LL);
    return 3221225485LL;
  }
  else
  {
    v6 = *(_DWORD **)(a2 + 24);
    v7 = *(_DWORD *)(a1 + 168);
    if ( *v6 == v7 )
    {
      IoAcquireCancelSpinLock(&Irql);
      if ( *(_BYTE *)(a2 + 68) )
      {
        IoReleaseCancelSpinLock(Irql);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 358, v9, 3221225760LL);
        }
        return 3221225760LL;
      }
      else
      {
        v10 = a1 + 152;
        v11 = *(_QWORD **)(v10 + 8);
        if ( *v11 != v10 )
          __fastfail(3u);
        *(_QWORD *)(a2 + 176) = v11;
        *(_QWORD *)(a2 + 168) = v10;
        *v11 = a2 + 168;
        *(_QWORD *)(v10 + 8) = a2 + 168;
        *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
        _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)&MountMgrCancel);
        IoReleaseCancelSpinLock(Irql);
        return 259;
      }
    }
    else
    {
      *v6 = v7;
      *(_QWORD *)(a2 + 56) = 4;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 357, a3, 0);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1400015a0  mov     [rsp+arg_0], rbx
0x1400015a5  push    rdi
0x1400015a6  sub     rsp, 20h
0x1400015aa  mov     rax, [rdx+0B8h]
0x1400015b1  mov     rbx, rdx
0x1400015b4  mov     [rsp+28h+Irql], 0
0x1400015b9  mov     rdi, rcx
0x1400015bc  cmp     dword ptr [rax+10h], 4
0x1400015c0  jb      loc_1400016EB
0x1400015c6  cmp     dword ptr [rax+8], 4
0x1400015ca  jb      loc_1400016EB
0x1400015d0  mov     rax, [rdx+18h]
0x1400015d4  mov     ecx, [rcx+0A8h]
0x1400015da  cmp     [rax], ecx
0x1400015dc  jz      short loc_140001621
0x1400015de  mov     [rax], ecx
0x1400015e0  mov     qword ptr [rdx+38h], 4
0x1400015e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015ef  lea     rax, WPP_GLOBAL_Control
0x1400015f6  cmp     rcx, rax
0x1400015f9  jz      short loc_140001613
0x1400015fb  mov     eax, [rcx+2Ch]
0x1400015fe  test    al, 1
0x140001600  jz      short loc_140001613
0x140001602  mov     rcx, [rcx+18h]
0x140001606  mov     edx, 165h
0x14000160b  xor     r9d, r9d
0x14000160e  call    WPP_SF_L
0x140001613  xor     eax, eax
0x140001615  mov     rbx, [rsp+28h+arg_0]
0x14000161a  add     rsp, 20h
0x14000161e  pop     rdi
0x14000161f  retn
0x140001621  lea     rcx, [rsp+28h+Irql]; Irql
0x140001626  call    cs:__imp_IoAcquireCancelSpinLock
0x14000162d  nop     dword ptr [rax+rax+00h]
0x140001632  cmp     byte ptr [rbx+44h], 0
0x140001636  jz      short loc_140001687
0x140001638  movzx   ecx, [rsp+28h+Irql]; Irql
0x14000163d  call    cs:__imp_IoReleaseCancelSpinLock
0x140001644  nop     dword ptr [rax+rax+00h]
0x140001649  mov     rcx, cs:WPP_GLOBAL_Control
0x140001650  lea     rax, WPP_GLOBAL_Control
0x140001657  cmp     rcx, rax
0x14000165a  jz      short loc_14000167D
0x14000165c  mov     eax, [rcx+2Ch]
0x14000165f  test    al, 1
0x140001661  jz      short loc_14000167D
0x140001663  cmp     byte ptr [rcx+29h], 1
0x140001667  jb      short loc_14000167D
0x140001669  mov     rcx, [rcx+18h]
0x14000166d  mov     edx, 166h
0x140001672  mov     r9d, 0C0000120h
0x140001678  call    WPP_SF_L
0x14000167d  mov     eax, 0C0000120h
0x140001682  jmp     loc_14000171E
0x140001687  add     rdi, 98h
0x14000168e  mov     rcx, [rdi+8]
0x140001692  cmp     [rcx], rdi
0x140001695  jz      short loc_14000169E
0x140001697  mov     ecx, 3
0x14000169c  int     29h; Win8: RtlFailFast(ecx)
0x14000169e  lea     rax, [rbx+0A8h]
0x1400016a5  mov     [rax+8], rcx
0x1400016a9  mov     [rax], rdi
0x1400016ac  mov     [rcx], rax
0x1400016af  mov     [rdi+8], rax
0x1400016b3  mov     rax, [rbx+0B8h]
0x1400016ba  or      byte ptr [rax+3], 1
0x1400016be  lea     rax, MountMgrCancel
0x1400016c5  xchg    rax, [rbx+68h]
0x1400016c9  movzx   ecx, [rsp+28h+Irql]; Irql
0x1400016ce  call    cs:__imp_IoReleaseCancelSpinLock
0x1400016d5  nop     dword ptr [rax+rax+00h]
0x1400016da  mov     eax, 103h
0x1400016df  mov     rbx, [rsp+28h+arg_0]
0x1400016e4  add     rsp, 20h
0x1400016e8  pop     rdi
0x1400016e9  retn
0x1400016eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400016f2  lea     rax, WPP_GLOBAL_Control
0x1400016f9  cmp     rcx, rax
0x1400016fc  jz      short loc_140001719
0x1400016fe  mov     eax, [rcx+2Ch]
0x140001701  test    al, 1
0x140001703  jz      short loc_140001719
0x140001705  mov     rcx, [rcx+18h]
0x140001709  mov     edx, 164h
0x14000170e  mov     r9d, 0C000000Dh
0x140001714  call    WPP_SF_L
0x140001719  mov     eax, 0C000000Dh
0x14000171e  mov     rbx, [rsp+28h+arg_0]
0x140001723  add     rsp, 20h
0x140001727  pop     rdi
0x140001728  retn
```

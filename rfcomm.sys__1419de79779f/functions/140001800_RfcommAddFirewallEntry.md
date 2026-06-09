# RfcommAddFirewallEntry

- ea: `0x140001800`
- end: `0x140001951`
- name: `RfcommAddFirewallEntry`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002ac8`

## callees

- `0x140001800`
- `0x140002e20`
- `0x140003cb4`
- `0x1400048b0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001820`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001820`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001935`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001935`
- `ntoskrnl!ExAllocatePool2` at `0x140001856`
- `ntoskrnl!ExAllocatePool2` at `0x140001856`

## pseudocode

```c
__int64 __fastcall RfcommAddFirewallEntry(__int64 a1, __int64 a2, __int64 a3)
{
  KSPIN_LOCK *v3; // rbp
  unsigned __int64 *v7; // rdi
  KIRQL v8; // r14
  __int64 v9; // rcx
  int v10; // edx
  __int64 Pool2; // rax
  unsigned __int64 *v12; // rcx
  unsigned int v13; // ebx
  unsigned __int64 **v14; // rax

  v3 = (KSPIN_LOCK *)(a1 + 368);
  v7 = (unsigned __int64 *)(a1 + 384);
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 368));
  if ( RfcommFindFirewallEntry(v9, v7, a3) )
  {
    v13 = -1073741514;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        19,
        53,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
        -1073741514);
  }
  else
  {
    Pool2 = ExAllocatePool2(64, 48, 1835230802);
    v12 = (unsigned __int64 *)Pool2;
    if ( Pool2 )
    {
      *(_OWORD *)(Pool2 + 24) = *(_OWORD *)a3;
      *(_BYTE *)(Pool2 + 40) = *(_BYTE *)(a3 + 16);
      *(_QWORD *)(Pool2 + 16) = a2;
      v14 = *(unsigned __int64 ***)(a1 + 392);
      if ( *v14 != v7 )
        __fastfail(3u);
      *v12 = (unsigned __int64)v7;
      v13 = 0;
      v12[1] = (unsigned __int64)v14;
      *v14 = v12;
      *(_QWORD *)(a1 + 392) = v12;
      ++*(_DWORD *)(a1 + 376);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dq(
          WPP_GLOBAL_Control->DeviceExtension,
          *(_DWORD *)(a1 + 376),
          19,
          52,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          *(_DWORD *)(a1 + 376),
          (char)v12);
    }
    else
    {
      v13 = -1073741670;
    }
  }
  KeReleaseSpinLock(v3, v8);
  return v13;
}

```

## disassembly

```asm
0x140001800  push    rbx
0x140001802  push    rbp
0x140001803  push    rsi
0x140001804  push    rdi
0x140001805  push    r14
0x140001807  push    r15
0x140001809  sub     rsp, 48h
0x14000180d  lea     rbp, [rcx+170h]
0x140001814  mov     rsi, rcx
0x140001817  mov     rcx, rbp; SpinLock
0x14000181a  mov     rbx, r8
0x14000181d  mov     r15, rdx
0x140001820  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001827  nop     dword ptr [rax+rax+00h]
0x14000182c  lea     rdi, [rsi+180h]
0x140001833  mov     r8, rbx
0x140001836  mov     rdx, rdi
0x140001839  mov     r14b, al
0x14000183c  call    RfcommFindFirewallEntry
0x140001841  test    rax, rax
0x140001844  jnz     loc_1400018F0
0x14000184a  lea     edx, [rax+30h]
0x14000184d  mov     r8d, 6D636652h
0x140001853  lea     ecx, [rax+40h]
0x140001856  call    cs:__imp_ExAllocatePool2
0x14000185d  nop     dword ptr [rax+rax+00h]
0x140001862  mov     rcx, rax
0x140001865  test    rax, rax
0x140001868  jnz     short loc_140001874
0x14000186a  mov     ebx, 0C000009Ah
0x14000186f  jmp     loc_14000192F
0x140001874  movups  xmm0, xmmword ptr [rbx]
0x140001877  movups  xmmword ptr [rax+18h], xmm0
0x14000187b  mov     al, [rbx+10h]
0x14000187e  mov     [rcx+28h], al
0x140001881  mov     [rcx+10h], r15
0x140001885  mov     rax, [rdi+8]
0x140001889  cmp     [rax], rdi
0x14000188c  jz      short loc_140001895
0x14000188e  mov     ecx, 3
0x140001893  int     29h; Win8: RtlFailFast(ecx)
0x140001895  mov     [rcx], rdi
0x140001898  xor     ebx, ebx
0x14000189a  mov     [rcx+8], rax
0x14000189e  mov     [rax], rcx
0x1400018a1  mov     [rdi+8], rcx
0x1400018a5  inc     dword ptr [rsi+178h]
0x1400018ab  mov     edx, [rsi+178h]
0x1400018b1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400018b8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400018bf  jz      short loc_14000192F
0x1400018c1  mov     [rsp+78h+var_48], rcx
0x1400018c6  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x1400018cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018d4  lea     r9d, [rbx+34h]
0x1400018d8  mov     [rsp+78h+var_50], edx
0x1400018dc  lea     r8d, [rbx+13h]
0x1400018e0  mov     [rsp+78h+var_58], rax
0x1400018e5  mov     rcx, [rcx+40h]
0x1400018e9  call    WPP_RECORDER_SF_dq
0x1400018ee  jmp     short loc_14000192F
0x1400018f0  mov     ebx, 0C0000136h
0x1400018f5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400018fc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001903  jz      short loc_14000192F
0x140001905  mov     rcx, cs:WPP_GLOBAL_Control
0x14000190c  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140001913  mov     r9d, 35h ; '5'
0x140001919  mov     [rsp+78h+var_50], ebx
0x14000191d  mov     [rsp+78h+var_58], rax
0x140001922  mov     rcx, [rcx+40h]
0x140001926  lea     r8d, [r9-22h]
0x14000192a  call    WPP_RECORDER_SF_d
0x14000192f  mov     dl, r14b; NewIrql
0x140001932  mov     rcx, rbp; SpinLock
0x140001935  call    cs:__imp_KeReleaseSpinLock
0x14000193c  nop     dword ptr [rax+rax+00h]
0x140001941  mov     eax, ebx
0x140001943  add     rsp, 48h
0x140001947  pop     r15
0x140001949  pop     r14
0x14000194b  pop     rdi
0x14000194c  pop     rsi
0x14000194d  pop     rbp
0x14000194e  pop     rbx
0x14000194f  retn
```

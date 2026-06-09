# DrGetConnectionInfo

- ea: `0x140019f18`
- end: `0x14001a294`
- name: `DrGetConnectionInfo`
- size: `892`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002acc0`

## callees

- `0x14000327c`
- `0x1400064b0`
- `0x140011bfc`
- `0x140011ce4`
- `0x1400189b8`
- `0x140019f18`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001a061`
- `ntoskrnl!ExAllocatePool2` at `0x14001a061`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a277`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a277`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a129`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a129`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a233`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a233`
- `ntoskrnl!ProbeForWrite` at `0x140019fdd`
- `ntoskrnl!ProbeForWrite` at `0x140019ff2`
- `ntoskrnl!ProbeForWrite` at `0x140019fdd`
- `ntoskrnl!ProbeForWrite` at `0x140019ff2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001a14a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001a14a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a227`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a227`

## pseudocode

```c
__int64 __fastcall DrGetConnectionInfo(__int64 a1)
{
  _DWORD *v1; // r9
  char *v2; // r12
  SIZE_T v3; // r14
  __int64 v4; // r15
  __int64 v5; // rax
  __int64 v6; // r13
  unsigned int v7; // ecx
  char *v8; // rsi
  char *Pool2; // rax
  int v11; // edi
  char *v12; // r13
  _DWORD *v13; // rcx
  struct _RX_CONTEXT *v14; // rcx
  char v15; // [rsp+30h] [rbp-68h]
  struct _V_NET_ROOT *v16; // [rsp+40h] [rbp-58h]
  unsigned int v17; // [rsp+A0h] [rbp+8h] BYREF
  _DWORD *v18; // [rsp+A8h] [rbp+10h]
  char *v19; // [rsp+B0h] [rbp+18h] BYREF
  char *v20; // [rsp+B8h] [rbp+20h] BYREF

  v1 = *(_DWORD **)(a1 + 552);
  v18 = v1;
  v2 = *(char **)(a1 + 560);
  v3 = *(unsigned int *)(a1 + 572);
  v20 = v2;
  v19 = &v2[v3];
  if ( !(_DWORD)v3 )
  {
    v20 = 0;
    v19 = 0;
  }
  if ( !v1 || !v2 )
    return 3221225485LL;
  if ( (*(_BYTE *)(a1 + 540) & 3) != 3 )
    return 3221225488LL;
  v4 = a1 + 40;
  v5 = *(_QWORD *)(a1 + 40);
  if ( *(_QWORD *)(v5 + 8) )
    return 3221225488LL;
  v6 = *(_QWORD *)(a1 + 72);
  v7 = *(_DWORD *)(a1 + 568);
  v17 = v7;
  v8 = 0;
  v15 = 0;
  if ( *(_BYTE *)(v5 + 64) )
  {
    ProbeForWrite(v1, v7, 1u);
    ProbeForWrite(v2, v3, 1u);
    if ( (unsigned int)v3 > 0xA0000 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids,
          (unsigned int)v3);
      return 3221225485LL;
    }
    if ( (_DWORD)v3 )
    {
      Pool2 = (char *)ExAllocatePool2(64, v3, 1917088324);
      v8 = Pool2;
      if ( !Pool2 )
        return 3221225626LL;
      v20 = Pool2;
      v19 = &Pool2[v3];
    }
    v7 = v17;
    v1 = v18;
  }
  if ( v6 )
  {
    v16 = *(struct _V_NET_ROOT **)(v6 + 40);
    if ( *((_QWORD *)&v16->1 + 4) )
    {
      if ( v7 >= 0x18 )
      {
        v12 = (char *)(v1 + 2);
        v13 = v1 + 3;
        if ( *(_BYTE *)(*(_QWORD *)v4 + 64LL) )
          RtlWriteULongToUser(v13, 1);
        else
          *v13 = 1;
        if ( *(_BYTE *)(*(_QWORD *)v4 + 64LL) )
          RtlWriteULongToUser(v12 + 8, 0);
        else
          *((_DWORD *)v12 + 2) = 0;
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite(
          (PERESOURCE)((char *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[7].DpcData + 24),
          1u);
        v15 = 1;
        v17 = 0;
        if ( DrPackConnectEntry(v14, &v20, &v19, v16, &v17) )
        {
          if ( *(_BYTE *)(*(_QWORD *)v4 + 64LL) )
            RtlWriteULongToUser(v12 + 8, v17);
          else
            *((_DWORD *)v12 + 2) = v17;
          if ( *(_BYTE *)(*(_QWORD *)v4 + 64LL) )
            RtlWriteULongToUser(v18 + 2, 1);
          else
            v18[2] = 1;
          v11 = 0;
        }
        else
        {
          v11 = -1073741789;
        }
      }
      else
      {
        v11 = -1073741789;
      }
    }
    else
    {
      v11 = -2147483611;
    }
  }
  else
  {
    v11 = -1073741808;
  }
  if ( v15 )
  {
    ExReleaseResourceLite((PERESOURCE)((char *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[7].DpcData + 24));
    KeLeaveCriticalRegion();
  }
  if ( v8 )
  {
    if ( v11 >= 0 )
    {
      if ( *(_BYTE *)(*(_QWORD *)v4 + 64LL) )
        RtlCopyToUser(v2, v8, v3);
      else
        RtlCopyVolatileMemory(v2, v8, v3);
    }
    ExFreePoolWithTag(v8, 0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140019f18  mov     r11, rsp
0x140019f1b  push    rsi
0x140019f1c  push    rdi
0x140019f1d  push    r12
0x140019f1f  push    r13
0x140019f21  push    r14
0x140019f23  push    r15
0x140019f25  sub     rsp, 68h
0x140019f29  mov     r9, [rcx+228h]
0x140019f30  mov     [rsp+98h+arg_8], r9
0x140019f38  mov     r12, [rcx+230h]
0x140019f3f  mov     r14d, [rcx+23Ch]
0x140019f46  mov     [r11+20h], r12
0x140019f4a  lea     rax, [r14+r12]
0x140019f4e  mov     [r11+18h], rax
0x140019f52  test    r14d, r14d
0x140019f55  jnz     short loc_140019F67
0x140019f57  mov     qword ptr [r11+20h], 0
0x140019f5f  mov     qword ptr [r11+18h], 0
0x140019f67  test    r9, r9
0x140019f6a  jz      loc_14001A039
0x140019f70  test    r12, r12
0x140019f73  jz      loc_14001A039
0x140019f79  mov     eax, [rcx+21Ch]
0x140019f7f  and     eax, 3
0x140019f82  cmp     al, 3
0x140019f84  jnz     loc_14001A28A
0x140019f8a  lea     r15, [rcx+28h]
0x140019f8e  mov     rax, [r15]
0x140019f91  cmp     qword ptr [rax+8], 0
0x140019f96  jnz     loc_14001A28A
0x140019f9c  mov     [rsp+98h+var_50], r12
0x140019fa1  mov     [rsp+98h+var_48], r14
0x140019fa6  mov     [rsp+98h+var_40], r15
0x140019fab  mov     r13, [rcx+48h]
0x140019faf  mov     ecx, [rcx+238h]
0x140019fb5  mov     [rsp+98h+arg_0], ecx
0x140019fbc  xor     esi, esi
0x140019fbe  mov     [rsp+98h+var_60], rsi
0x140019fc3  mov     [rsp+98h+var_68], sil
0x140019fc8  cmp     [rax+40h], sil
0x140019fcc  jz      loc_14001A102
0x140019fd2  mov     edx, ecx; Length
0x140019fd4  lea     edi, [rsi+1]
0x140019fd7  mov     r8d, edi; Alignment
0x140019fda  mov     rcx, r9; Address
0x140019fdd  call    cs:__imp_ProbeForWrite
0x140019fe4  nop     dword ptr [rax+rax+00h]
0x140019fe9  mov     r8d, edi; Alignment
0x140019fec  mov     rdx, r14; Length
0x140019fef  mov     rcx, r12; Address
0x140019ff2  call    cs:__imp_ProbeForWrite
0x140019ff9  nop     dword ptr [rax+rax+00h]
0x140019ffe  nop
0x140019fff  cmp     r14d, 0A0000h
0x14001a006  jbe     short loc_14001A04E
0x14001a008  lea     rax, WPP_GLOBAL_Control
0x14001a00f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a016  cmp     rcx, rax
0x14001a019  jz      short loc_14001A039
0x14001a01b  cmp     byte ptr [rcx+29h], 2
0x14001a01f  jb      short loc_14001A039
0x14001a021  mov     edx, 27h ; '''
0x14001a026  mov     r9d, r14d
0x14001a029  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a030  mov     rcx, [rcx+18h]
0x14001a034  call    WPP_SF_d
0x14001a039  mov     eax, 0C000000Dh
0x14001a03e  add     rsp, 68h
0x14001a042  pop     r15
0x14001a044  pop     r14
0x14001a046  pop     r13
0x14001a048  pop     r12
0x14001a04a  pop     rdi
0x14001a04b  pop     rsi
0x14001a04c  retn
0x14001a04e  test    r14d, r14d
0x14001a051  jz      short loc_14001A095
0x14001a053  mov     r8d, 72447244h
0x14001a059  mov     rdx, r14
0x14001a05c  mov     ecx, 40h ; '@'
0x14001a061  call    cs:__imp_ExAllocatePool2
0x14001a068  nop     dword ptr [rax+rax+00h]
0x14001a06d  mov     rsi, rax
0x14001a070  mov     [rsp+98h+var_60], rax
0x14001a075  test    rax, rax
0x14001a078  jnz     short loc_14001A081
0x14001a07a  mov     eax, 0C000009Ah
0x14001a07f  jmp     short loc_14001A03E
0x14001a081  mov     [rsp+98h+arg_18], rax
0x14001a089  lea     rax, [r14+rax]
0x14001a08d  mov     [rsp+98h+arg_10], rax
0x14001a095  mov     ecx, [rsp+98h+arg_0]
0x14001a09c  mov     r9, [rsp+98h+arg_8]
0x14001a0a4  test    r13, r13
0x14001a0a7  jz      loc_14001A1E6
0x14001a0ad  mov     rax, [r13+28h]
0x14001a0b1  mov     [rsp+98h+var_58], rax
0x14001a0b6  cmp     qword ptr [rax+20h], 0
0x14001a0bb  jnz     short loc_14001A0CB
0x14001a0bd  mov     edi, 80000025h
0x14001a0c2  mov     [rsp+98h+var_64], edi
0x14001a0c6  jmp     loc_14001A20E
0x14001a0cb  cmp     ecx, 18h
0x14001a0ce  jnb     short loc_14001A0DE
0x14001a0d0  mov     edi, 0C0000023h
0x14001a0d5  mov     [rsp+98h+var_64], edi
0x14001a0d9  jmp     loc_14001A20E
0x14001a0de  lea     r13, [r9+8]
0x14001a0e2  lea     rcx, [r13+4]
0x14001a0e6  mov     rax, [r15]
0x14001a0e9  cmp     byte ptr [rax+40h], 0
0x14001a0ed  jz      short loc_14001A109
0x14001a0ef  mov     edx, edi
0x14001a0f1  call    RtlWriteULongToUser
0x14001a0f6  jmp     short loc_14001A10B
0x14001a0f8  mov     eax, 0C000000Dh
0x14001a0fd  jmp     loc_14001A03E
0x14001a102  mov     edi, 1
0x14001a107  jmp     short loc_14001A0A4
0x14001a109  mov     [rcx], edi
0x14001a10b  mov     rax, [r15]
0x14001a10e  cmp     byte ptr [rax+40h], 0
0x14001a112  jz      short loc_14001A121
0x14001a114  xor     edx, edx
0x14001a116  lea     rcx, [r13+8]
0x14001a11a  call    RtlWriteULongToUser
0x14001a11f  jmp     short loc_14001A129
0x14001a121  mov     dword ptr [r13+8], 0
0x14001a129  call    cs:__imp_KeEnterCriticalRegion
0x14001a130  nop     dword ptr [rax+rax+00h]
0x14001a135  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001a13c  mov     rcx, [rax+1F8h]
0x14001a143  add     rcx, 18h; Resource
0x14001a147  mov     dl, dil; Wait
0x14001a14a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001a151  nop     dword ptr [rax+rax+00h]
0x14001a156  mov     [rsp+98h+var_68], dil
0x14001a15b  mov     [rsp+98h+arg_0], 0
0x14001a166  lea     rax, [rsp+98h+arg_0]
0x14001a16e  mov     [rsp+98h+var_78], rax; unsigned int *
0x14001a173  mov     r9, [rsp+98h+var_58]; struct _V_NET_ROOT *
0x14001a178  lea     r8, [rsp+98h+arg_10]; char **
0x14001a180  lea     rdx, [rsp+98h+arg_18]; char **
0x14001a188  call    ?DrPackConnectEntry@@YAEPEAU_RX_CONTEXT@@PEAPEAD1PEAU_V_NET_ROOT@@PEAK@Z; DrPackConnectEntry(_RX_CONTEXT *,char * *,char * *,_V_NET_ROOT *,ulong *)
0x14001a18d  test    al, al
0x14001a18f  jz      short loc_14001A1DB
0x14001a191  mov     ecx, [rsp+98h+arg_0]
0x14001a198  mov     rax, [r15]
0x14001a19b  cmp     byte ptr [rax+40h], 0
0x14001a19f  jz      short loc_14001A1AE
0x14001a1a1  mov     edx, ecx
0x14001a1a3  lea     rcx, [r13+8]
0x14001a1a7  call    RtlWriteULongToUser
0x14001a1ac  jmp     short loc_14001A1B2
0x14001a1ae  mov     [r13+8], ecx
0x14001a1b2  mov     rax, [r15]
0x14001a1b5  mov     rcx, [rsp+98h+arg_8]
0x14001a1bd  cmp     byte ptr [rax+40h], 0
0x14001a1c1  jz      short loc_14001A1D0
0x14001a1c3  mov     edx, edi
0x14001a1c5  add     rcx, 8
0x14001a1c9  call    RtlWriteULongToUser
0x14001a1ce  jmp     short loc_14001A1D3
0x14001a1d0  mov     [rcx+8], edi
0x14001a1d3  xor     edi, edi
0x14001a1d5  mov     [rsp+98h+var_64], edi
0x14001a1d9  jmp     short loc_14001A20E
0x14001a1db  mov     edi, 0C0000023h
0x14001a1e0  mov     [rsp+98h+var_64], edi
0x14001a1e4  jmp     short loc_14001A20E
0x14001a1e6  mov     edi, 0C0000010h
0x14001a1eb  mov     [rsp+98h+var_64], edi
0x14001a1ef  jmp     short loc_14001A20E
0x14001a1f1  mov     edi, 0C000000Dh
0x14001a1f6  mov     [rsp+98h+var_64], edi
0x14001a1fa  mov     r12, [rsp+98h+var_50]
0x14001a1ff  mov     rsi, [rsp+98h+var_60]
0x14001a204  mov     r14, [rsp+98h+var_48]
0x14001a209  mov     r15, [rsp+98h+var_40]
0x14001a20e  cmp     [rsp+98h+var_68], 0
0x14001a213  jz      short loc_14001A23F
0x14001a215  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001a21c  mov     rcx, [rax+1F8h]
0x14001a223  add     rcx, 18h; Resource
0x14001a227  call    cs:__imp_ExReleaseResourceLite
0x14001a22e  nop     dword ptr [rax+rax+00h]
0x14001a233  call    cs:__imp_KeLeaveCriticalRegion
0x14001a23a  nop     dword ptr [rax+rax+00h]
0x14001a23f  test    rsi, rsi
0x14001a242  jz      short loc_14001A283
0x14001a244  test    edi, edi
0x14001a246  js      short loc_14001A272
0x14001a248  mov     rax, [r15]
0x14001a24b  mov     r8, r14; Size
0x14001a24e  mov     rdx, rsi; Src
0x14001a251  mov     rcx, r12; void *
0x14001a254  cmp     byte ptr [rax+40h], 0
0x14001a258  jz      short loc_14001A261
0x14001a25a  call    RtlCopyToUser
0x14001a25f  jmp     short loc_14001A266
0x14001a261  call    RtlCopyVolatileMemory
0x14001a266  jmp     short loc_14001A272
0x14001a268  mov     edi, 0C000000Dh
0x14001a26d  mov     rsi, [rsp+98h+var_60]
0x14001a272  xor     edx, edx; Tag
0x14001a274  mov     rcx, rsi; P
0x14001a277  call    cs:__imp_ExFreePoolWithTag
0x14001a27e  nop     dword ptr [rax+rax+00h]
0x14001a283  mov     eax, edi
0x14001a285  jmp     loc_14001A03E
0x14001a28a  mov     eax, 0C0000010h
0x14001a28f  jmp     loc_14001A03E
```

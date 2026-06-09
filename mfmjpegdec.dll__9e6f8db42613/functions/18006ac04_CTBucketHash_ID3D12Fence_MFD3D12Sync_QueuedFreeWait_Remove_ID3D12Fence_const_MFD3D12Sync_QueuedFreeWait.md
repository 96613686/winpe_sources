# CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Remove(ID3D12Fence * const &,MFD3D12Sync::QueuedFreeWait * &)

- ea: `0x18006ac04`
- end: `0x18006acb7`
- name: `?Remove@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@QEAAHAEBQEAUID3D12Fence@@AEAPEAVQueuedFreeWait@MFD3D12Sync@@@Z`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180069b14`

## callees

- `0x180068d80`
- `0x180068e34`
- `0x18006ac04`

## pseudocode

```c
__int64 __fastcall CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Remove(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // r8
  bool v5; // zf
  __int64 v6; // rdi
  int v7; // ebp
  unsigned int v8; // r14d
  __int64 v9; // rsi
  __int64 result; // rax
  _OWORD v11[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  v11[0] = 0;
  if ( !(unsigned int)CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Find(a1, a2, a3, v11) )
    return 0;
  v5 = *(_QWORD *)a1 == 0;
  v12 = 0;
  if ( v5 )
    return 0;
  v6 = *(_QWORD *)&v11[0];
  if ( !*(_QWORD *)&v11[0] )
    return 0;
  v7 = *(_DWORD *)(a1 + 8);
  v8 = **(_DWORD **)&v11[0];
  v9 = *((_QWORD *)&v11[0] + 1);
  CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::GetNext(a1, v11, &v12, v4);
  if ( v9 )
    *(_QWORD *)(v9 + 16) = *(_QWORD *)(v6 + 16);
  else
    *(_QWORD *)(*(_QWORD *)a1 + 8LL * (v8 % (v7 & 0x7FFFFFFFu))) = *(_QWORD *)(v6 + 16);
  --*(_DWORD *)(a1 + 12);
  *(_QWORD *)(v6 + 16) = *(_QWORD *)(a1 + 24);
  result = 1;
  *(_QWORD *)(a1 + 24) = v6;
  return result;
}

```

## disassembly

```asm
0x18006ac04  mov     rax, rsp
0x18006ac07  mov     [rax+8], rbx
0x18006ac0b  mov     [rax+10h], rbp
0x18006ac0f  push    rsi
0x18006ac10  push    rdi
0x18006ac11  push    r14
0x18006ac13  sub     rsp, 30h
0x18006ac17  xorps   xmm0, xmm0
0x18006ac1a  lea     r9, [rax-28h]
0x18006ac1e  movups  xmmword ptr [rax-28h], xmm0
0x18006ac22  mov     rbx, rcx
0x18006ac25  call    ?Find@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@QEAAHAEBQEAUID3D12Fence@@AEAPEAVQueuedFreeWait@MFD3D12Sync@@AEAU_POSITION@1@@Z; CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Find(ID3D12Fence * const &,MFD3D12Sync::QueuedFreeWait * &,CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::_POSITION &)
0x18006ac2a  test    eax, eax
0x18006ac2c  jz      short loc_18006ACA2
0x18006ac2e  cmp     qword ptr [rbx], 0
0x18006ac32  mov     [rsp+48h+arg_18], 0
0x18006ac3b  jz      short loc_18006ACA2
0x18006ac3d  mov     rdi, [rsp+48h+var_28]
0x18006ac42  test    rdi, rdi
0x18006ac45  jz      short loc_18006ACA2
0x18006ac47  mov     ebp, [rbx+8]
0x18006ac4a  lea     rdx, [rsp+48h+var_28]
0x18006ac4f  mov     r14d, [rdi]
0x18006ac52  mov     r9, r8
0x18006ac55  mov     rsi, [rsp+48h+var_20]
0x18006ac5a  lea     r8, [rsp+48h+arg_18]
0x18006ac5f  mov     rcx, rbx
0x18006ac62  call    ?GetNext@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@QEAAHAEAU_POSITION@1@AEAPEAUID3D12Fence@@AEAPEAVQueuedFreeWait@MFD3D12Sync@@@Z; CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::GetNext(CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::_POSITION &,ID3D12Fence * &,MFD3D12Sync::QueuedFreeWait * &)
0x18006ac67  test    rsi, rsi
0x18006ac6a  jz      short loc_18006AC76
0x18006ac6c  mov     rax, [rdi+10h]
0x18006ac70  mov     [rsi+10h], rax
0x18006ac74  jmp     short loc_18006AC8C
0x18006ac76  mov     rcx, [rbx]
0x18006ac79  xor     edx, edx
0x18006ac7b  mov     eax, r14d
0x18006ac7e  btr     ebp, 1Fh
0x18006ac82  div     ebp
0x18006ac84  mov     rax, [rdi+10h]
0x18006ac88  mov     [rcx+rdx*8], rax
0x18006ac8c  dec     dword ptr [rbx+0Ch]
0x18006ac8f  mov     rax, [rbx+18h]
0x18006ac93  mov     [rdi+10h], rax
0x18006ac97  mov     eax, 1
0x18006ac9c  mov     [rbx+18h], rdi
0x18006aca0  jmp     short loc_18006ACA4
0x18006aca2  xor     eax, eax
0x18006aca4  mov     rbx, [rsp+48h+arg_0]
0x18006aca9  mov     rbp, [rsp+48h+arg_8]
0x18006acae  add     rsp, 30h
0x18006acb2  pop     r14
0x18006acb4  pop     rdi
0x18006acb5  pop     rsi
0x18006acb6  retn
```

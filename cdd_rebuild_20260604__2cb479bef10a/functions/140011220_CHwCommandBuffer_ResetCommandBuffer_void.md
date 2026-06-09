# CHwCommandBuffer::ResetCommandBuffer(void)

- ea: `0x140011220`
- end: `0x1400112ea`
- name: `?ResetCommandBuffer@CHwCommandBuffer@@QEAAXXZ`
- size: `202`
- prototype: `void __fastcall(CHwCommandBuffer *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400111c0`
- `0x14002d4b4`
- `0x14002e61c`
- `0x14002ece0`

## callees

- `0x1400111a0`
- `0x140011220`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001125d`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001125d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001127b`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001127b`

## pseudocode

```c
void __fastcall CHwCommandBuffer::ResetCommandBuffer(CHwCommandBuffer *this)
{
  __int64 v1; // rsi
  _QWORD **v3; // rdi
  _QWORD *v4; // rcx
  __int64 v5; // rcx
  _QWORD *v6; // rax

  v1 = *((_QWORD *)this + 267);
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 524) = 0;
  *((_DWORD *)this + 525) = 257;
  if ( v1 )
  {
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v1);
    v3 = (_QWORD **)((char *)this + 2104);
    while ( 1 )
    {
      v4 = *v3;
      if ( *v3 == v3 )
        break;
      if ( (_QWORD **)v4[1] != v3 || (v6 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
        __fastfail(3u);
      *v3 = v6;
      v6[1] = v3;
      CddResidencyState::OnCommandBufferFlush((CddResidencyState *)&v4[-2 * *((unsigned int *)this + 2) - 6], this);
    }
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v1);
  }
  v5 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 4) = v5;
  *((_DWORD *)this + 530) = 0;
  *((_QWORD *)this + 3) = v5 + 0x10000;
}

```

## disassembly

```asm
0x140011220  mov     [rsp+arg_0], rbx
0x140011225  mov     [rsp+arg_8], rsi
0x14001122a  push    rdi
0x14001122b  sub     rsp, 20h
0x14001122f  mov     rsi, [rcx+858h]
0x140011236  mov     rbx, rcx
0x140011239  mov     qword ptr [rcx+28h], 0
0x140011241  mov     dword ptr [rcx+830h], 0
0x14001124b  mov     dword ptr [rcx+834h], 101h
0x140011255  test    rsi, rsi
0x140011258  jz      short loc_140011287
0x14001125a  mov     rcx, rsi
0x14001125d  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x140011264  nop     dword ptr [rax+rax+00h]
0x140011269  lea     rdi, [rbx+838h]
0x140011270  mov     rcx, [rdi]
0x140011273  cmp     rcx, rdi
0x140011276  jnz     short loc_1400112B5
0x140011278  mov     rcx, rsi
0x14001127b  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140011282  nop     dword ptr [rax+rax+00h]
0x140011287  mov     rcx, [rbx+10h]
0x14001128b  mov     rsi, [rsp+28h+arg_8]
0x140011290  mov     [rbx+20h], rcx
0x140011294  mov     dword ptr [rbx+848h], 0
0x14001129e  lea     rax, [rcx+10000h]
0x1400112a5  mov     [rbx+18h], rax
0x1400112a9  mov     rbx, [rsp+28h+arg_0]
0x1400112ae  add     rsp, 20h
0x1400112b2  pop     rdi
0x1400112b3  retn
0x1400112b5  cmp     [rcx+8], rdi
0x1400112b9  jnz     short loc_1400112E3
0x1400112bb  mov     rax, [rcx]
0x1400112be  cmp     [rax+8], rcx
0x1400112c2  jnz     short loc_1400112E3
0x1400112c4  mov     [rdi], rax
0x1400112c7  mov     rdx, rbx; struct CHwCommandBuffer *
0x1400112ca  mov     [rax+8], rdi
0x1400112ce  mov     eax, [rbx+8]
0x1400112d1  add     rax, 3
0x1400112d5  shl     rax, 4
0x1400112d9  sub     rcx, rax; this
0x1400112dc  call    ?OnCommandBufferFlush@CddResidencyState@@QEAAXPEAVCHwCommandBuffer@@@Z; CddResidencyState::OnCommandBufferFlush(CHwCommandBuffer *)
0x1400112e1  jmp     short loc_140011270
0x1400112e3  mov     ecx, 3
0x1400112e8  int     29h; Win8: RtlFailFast(ecx)
```

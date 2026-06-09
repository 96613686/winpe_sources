# CddBitmap::RemoveFromCddBitmapList(void)

- ea: `0x14000229c`
- end: `0x140002324`
- name: `?RemoveFromCddBitmapList@CddBitmap@@QEAAXXZ`
- size: `136`
- prototype: `void __fastcall(CddBitmap *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400015e0`
- `0x140003840`
- `0x140032000`

## callees

- `0x14000229c`
- `0x14000232c`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400022b7`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400022b7`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400022fd`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400022fd`

## pseudocode

```c
void __fastcall CddBitmap::RemoveFromCddBitmapList(CddBitmap *this)
{
  __int64 v2; // rdi
  _QWORD *v3; // rax
  __int64 v4; // rcx
  _QWORD *v5; // rdx

  v2 = *(_QWORD *)(*((_QWORD *)this + 1) + 7256LL);
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v2);
  v3 = (_QWORD *)((char *)this + 144);
  v4 = *((_QWORD *)this + 18);
  if ( v4 )
  {
    if ( *(_QWORD **)(v4 + 8) != v3 || (v5 = (_QWORD *)*((_QWORD *)this + 19), (_QWORD *)*v5 != v3) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    *v3 = 0;
    *((_QWORD *)this + 19) = 0;
  }
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v2);
  CddBitmap::RemoveFromCddBitmapOnCloseProcessList(this);
}

```

## disassembly

```asm
0x14000229c  mov     [rsp+arg_0], rbx
0x1400022a1  push    rdi
0x1400022a2  sub     rsp, 20h
0x1400022a6  mov     rax, [rcx+8]
0x1400022aa  mov     rbx, rcx
0x1400022ad  mov     rdi, [rax+1C58h]
0x1400022b4  mov     rcx, rdi
0x1400022b7  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x1400022be  nop     dword ptr [rax+rax+00h]
0x1400022c3  lea     rax, [rbx+90h]
0x1400022ca  mov     rcx, [rax]
0x1400022cd  test    rcx, rcx
0x1400022d0  jz      short loc_1400022FA
0x1400022d2  cmp     [rcx+8], rax
0x1400022d6  jnz     short loc_14000231D
0x1400022d8  mov     rdx, [rax+8]
0x1400022dc  cmp     [rdx], rax
0x1400022df  jnz     short loc_14000231D
0x1400022e1  mov     [rdx], rcx
0x1400022e4  mov     [rcx+8], rdx
0x1400022e8  mov     qword ptr [rax], 0
0x1400022ef  mov     qword ptr [rbx+98h], 0
0x1400022fa  mov     rcx, rdi
0x1400022fd  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140002304  nop     dword ptr [rax+rax+00h]
0x140002309  mov     rcx, rbx; this
0x14000230c  call    ?RemoveFromCddBitmapOnCloseProcessList@CddBitmap@@QEAAXXZ; CddBitmap::RemoveFromCddBitmapOnCloseProcessList(void)
0x140002311  mov     rbx, [rsp+28h+arg_0]
0x140002316  add     rsp, 20h
0x14000231a  pop     rdi
0x14000231b  retn
0x14000231d  mov     ecx, 3
0x140002322  int     29h; Win8: RtlFailFast(ecx)
```

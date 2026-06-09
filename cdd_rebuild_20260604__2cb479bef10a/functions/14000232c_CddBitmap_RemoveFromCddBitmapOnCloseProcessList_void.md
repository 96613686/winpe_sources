# CddBitmap::RemoveFromCddBitmapOnCloseProcessList(void)

- ea: `0x14000232c`
- end: `0x1400023ac`
- name: `?RemoveFromCddBitmapOnCloseProcessList@CddBitmap@@QEAAXXZ`
- size: `128`
- prototype: `void __fastcall(CddBitmap *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000229c`

## callees

- `0x14000232c`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140002347`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140002347`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000238d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000238d`

## pseudocode

```c
void __fastcall CddBitmap::RemoveFromCddBitmapOnCloseProcessList(CddBitmap *this)
{
  __int64 v2; // rbx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rcx

  v2 = *(_QWORD *)(*((_QWORD *)this + 1) + 7256LL);
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v2);
  v3 = (_QWORD *)((char *)this + 160);
  v4 = *((_QWORD *)this + 20);
  if ( v4 )
  {
    if ( *(_QWORD **)(v4 + 8) != v3 || (v5 = (_QWORD *)*((_QWORD *)this + 21), (_QWORD *)*v5 != v3) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    *v3 = 0;
    *((_QWORD *)this + 21) = 0;
  }
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v2);
}

```

## disassembly

```asm
0x14000232c  mov     [rsp+arg_0], rbx
0x140002331  push    rdi
0x140002332  sub     rsp, 20h
0x140002336  mov     rax, [rcx+8]
0x14000233a  mov     rdi, rcx
0x14000233d  mov     rbx, [rax+1C58h]
0x140002344  mov     rcx, rbx
0x140002347  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000234e  nop     dword ptr [rax+rax+00h]
0x140002353  lea     rax, [rdi+0A0h]
0x14000235a  mov     rdx, [rax]
0x14000235d  test    rdx, rdx
0x140002360  jz      short loc_14000238A
0x140002362  cmp     [rdx+8], rax
0x140002366  jnz     short loc_1400023A5
0x140002368  mov     rcx, [rax+8]
0x14000236c  cmp     [rcx], rax
0x14000236f  jnz     short loc_1400023A5
0x140002371  mov     [rcx], rdx
0x140002374  mov     [rdx+8], rcx
0x140002378  mov     qword ptr [rax], 0
0x14000237f  mov     qword ptr [rdi+0A8h], 0
0x14000238a  mov     rcx, rbx
0x14000238d  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140002394  nop     dword ptr [rax+rax+00h]
0x140002399  mov     rbx, [rsp+28h+arg_0]
0x14000239e  add     rsp, 20h
0x1400023a2  pop     rdi
0x1400023a3  retn
0x1400023a5  mov     ecx, 3
0x1400023aa  int     29h; Win8: RtlFailFast(ecx)
```

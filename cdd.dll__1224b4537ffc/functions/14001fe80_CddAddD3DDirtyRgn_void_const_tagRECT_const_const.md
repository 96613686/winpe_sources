# CddAddD3DDirtyRgn(void * const,tagRECT const * const)

- ea: `0x14001fe80`
- end: `0x14001ff6a`
- name: `?CddAddD3DDirtyRgn@@YAXQEAXQEBUtagRECT@@@Z`
- size: `234`
- prototype: `void __fastcall(_QWORD *, const struct tagRECT *const)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001fe80`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001fe97`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001fe97`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001ff52`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001ff52`
- `WIN32K!CddEngCombineRgn` at `0x14001feee`
- `WIN32K!CddEngCombineRgn` at `0x14001feee`
- `WIN32K!CddEngSetRectRgn` at `0x14001fec0`
- `WIN32K!CddEngSetRectRgn` at `0x14001ff31`
- `WIN32K!CddEngSetRectRgn` at `0x14001fec0`
- `WIN32K!CddEngSetRectRgn` at `0x14001ff31`

## pseudocode

```c
void __fastcall CddAddD3DDirtyRgn(_QWORD *a1, const struct tagRECT *const a2)
{
  __int64 *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx

  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(a1[360]);
  if ( a2 )
  {
    if ( (unsigned int)CddEngSetRectRgn(
                         a1[356],
                         (unsigned int)a2->left,
                         (unsigned int)a2->top,
                         (unsigned int)a2->right,
                         a2->bottom) )
    {
      v4 = a1 + 357;
      if ( (unsigned int)CddEngCombineRgn(a1 + 357, a1[359], a1[356], 2) )
      {
        v5 = *v4;
        *v4 = a1[359];
        a1[359] = v5;
      }
    }
  }
  else
  {
    CddEngSetRectRgn(a1[359], 0, 0, *((unsigned int *)a1 + 199), *((_DWORD *)a1 + 200));
  }
  v6 = a1[360];
  *((_BYTE *)a1 + 2713) = 1;
  *((_BYTE *)a1 + 2736) = 1;
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v6);
}

```

## disassembly

```asm
0x14001fe80  mov     [rsp+arg_0], rbx
0x14001fe85  push    rdi
0x14001fe86  sub     rsp, 30h
0x14001fe8a  mov     rbx, rcx
0x14001fe8d  mov     rdi, rdx
0x14001fe90  mov     rcx, [rcx+0B40h]
0x14001fe97  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001fe9e  nop     dword ptr [rax+rax+00h]
0x14001fea3  test    rdi, rdi
0x14001fea6  jz      short loc_14001FF14
0x14001fea8  mov     eax, [rdi+0Ch]
0x14001feab  mov     r9d, [rdi+8]
0x14001feaf  mov     r8d, [rdi+4]
0x14001feb3  mov     edx, [rdi]
0x14001feb5  mov     rcx, [rbx+0B20h]
0x14001febc  mov     [rsp+38h+var_18], eax
0x14001fec0  call    cs:__imp_CddEngSetRectRgn
0x14001fec7  nop     dword ptr [rax+rax+00h]
0x14001fecc  test    eax, eax
0x14001fece  jz      short loc_14001FF3D
0x14001fed0  mov     r8, [rbx+0B20h]
0x14001fed7  lea     rdi, [rbx+0B28h]
0x14001fede  mov     rdx, [rbx+0B38h]
0x14001fee5  mov     rcx, rdi
0x14001fee8  mov     r9d, 2
0x14001feee  call    cs:__imp_CddEngCombineRgn
0x14001fef5  nop     dword ptr [rax+rax+00h]
0x14001fefa  test    eax, eax
0x14001fefc  jz      short loc_14001FF3D
0x14001fefe  mov     rcx, [rdi]
0x14001ff01  mov     rax, [rbx+0B38h]
0x14001ff08  mov     [rdi], rax
0x14001ff0b  mov     [rbx+0B38h], rcx
0x14001ff12  jmp     short loc_14001FF3D
0x14001ff14  mov     eax, [rbx+320h]
0x14001ff1a  xor     r8d, r8d
0x14001ff1d  mov     r9d, [rbx+31Ch]
0x14001ff24  xor     edx, edx
0x14001ff26  mov     rcx, [rbx+0B38h]
0x14001ff2d  mov     [rsp+38h+var_18], eax
0x14001ff31  call    cs:__imp_CddEngSetRectRgn
0x14001ff38  nop     dword ptr [rax+rax+00h]
0x14001ff3d  mov     rcx, [rbx+0B40h]
0x14001ff44  mov     byte ptr [rbx+0A99h], 1
0x14001ff4b  mov     byte ptr [rbx+0AB0h], 1
0x14001ff52  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14001ff59  nop     dword ptr [rax+rax+00h]
0x14001ff5e  mov     rbx, [rsp+38h+arg_0]
0x14001ff63  add     rsp, 30h
0x14001ff67  pop     rdi
0x14001ff68  retn
```

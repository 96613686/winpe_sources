# COConnectionPoint::InternalEnumSinks(tagCONNECTDATA * *,ulong *)

- ea: `0x180028270`
- end: `0x18002838a`
- name: `?InternalEnumSinks@COConnectionPoint@@QEAAJPEAPEAUtagCONNECTDATA@@PEAK@Z`
- size: `282`
- prototype: `__int64 __fastcall(COConnectionPoint *__hidden this, struct tagCONNECTDATA **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001a308`

## callees

- `0x180008a14`
- `0x180028270`
- `0x18003099a`
- `0x180031010`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180028366`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180028366`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800282b2`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800282b2`

## pseudocode

```c
__int64 __fastcall COConnectionPoint::InternalEnumSinks(
        COConnectionPoint *this,
        struct tagCONNECTDATA **a2,
        unsigned int *a3)
{
  unsigned int v6; // edi
  unsigned __int64 v7; // rsi
  struct tagCONNECTDATA *v8; // rax
  struct tagCONNECTDATA *v9; // r13
  unsigned int v10; // r12d
  __int64 v11; // rcx
  IUnknown *v12; // rcx
  __int64 v13; // rbx
  __int64 v15; // [rsp+68h] [rbp+10h]

  if ( a2 && a3 )
  {
    v6 = 0;
    *a2 = 0;
    *a3 = 0;
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockSinkResource);
    v7 = *((unsigned int *)this + 11);
    if ( (_DWORD)v7 )
    {
      v8 = (struct tagCONNECTDATA *)operator new[](saturated_mul(v7, 0x10u));
      v9 = v8;
      if ( v8 )
      {
        memset_0(v8, 0, 16LL * (unsigned int)v7);
        v10 = 0;
        if ( *((_DWORD *)this + 12) )
        {
          do
          {
            if ( v6 >= (unsigned int)v7 )
              break;
            v11 = *((_QWORD *)this + 7);
            v15 = 16LL * v10;
            if ( *(_DWORD *)(v11 + v15 + 8) )
            {
              v12 = *(IUnknown **)(v11 + 16LL * v10);
              v13 = v6;
              v9[v6].pUnk = v12;
              ((void (__fastcall *)(IUnknown *))v12->lpVtbl->AddRef)(v12);
              ++v6;
              v9[v13].dwCookie = *(_DWORD *)(*((_QWORD *)this + 7) + v15 + 8);
            }
            ++v10;
          }
          while ( v10 < *((_DWORD *)this + 12) );
          v6 = 0;
        }
        *a2 = v9;
        *a3 = v7;
      }
      else
      {
        v6 = -2147024882;
      }
    }
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockSinkResource);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180028270  mov     [rsp+arg_0], rbx
0x180028275  push    rbp
0x180028276  push    rsi
0x180028277  push    rdi
0x180028278  push    r12
0x18002827a  push    r13
0x18002827c  push    r14
0x18002827e  push    r15
0x180028280  sub     rsp, 20h
0x180028284  mov     r14, r8
0x180028287  mov     r15, rdx
0x18002828a  mov     rbp, rcx
0x18002828d  test    rdx, rdx
0x180028290  jz      loc_18002836E
0x180028296  test    r8, r8
0x180028299  jz      loc_18002836E
0x18002829f  xor     edi, edi
0x1800282a1  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x1800282a8  mov     [rsp+58h+arg_18], edi
0x1800282ac  mov     [rdx], rdi
0x1800282af  mov     [r8], edi
0x1800282b2  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800282b8  mov     esi, [rbp+2Ch]
0x1800282bb  test    esi, esi
0x1800282bd  jz      loc_18002835F
0x1800282c3  lea     rcx, [rdi-1]
0x1800282c7  mov     ebx, esi
0x1800282c9  lea     eax, [rdi+10h]
0x1800282cc  mul     rsi
0x1800282cf  cmovb   rax, rcx
0x1800282d3  mov     rcx, rax; unsigned __int64
0x1800282d6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800282db  mov     r13, rax
0x1800282de  test    rax, rax
0x1800282e1  jnz     short loc_1800282EA
0x1800282e3  mov     edi, 8007000Eh
0x1800282e8  jmp     short loc_18002835F
0x1800282ea  shl     rbx, 4
0x1800282ee  xor     edx, edx; Val
0x1800282f0  mov     r8, rbx; Size
0x1800282f3  mov     rcx, r13; void *
0x1800282f6  call    memset_0
0x1800282fb  xor     r12d, r12d
0x1800282fe  cmp     [rbp+30h], edi
0x180028301  jbe     short loc_180028359
0x180028303  cmp     edi, esi
0x180028305  jnb     short loc_180028355
0x180028307  mov     rcx, [rbp+38h]
0x18002830b  mov     eax, r12d
0x18002830e  shl     rax, 4
0x180028312  mov     [rsp+58h+arg_8], rax
0x180028317  cmp     dword ptr [rcx+rax+8], 0
0x18002831c  jz      short loc_18002834C
0x18002831e  mov     rcx, [rcx+rax]
0x180028322  mov     ebx, edi
0x180028324  add     rbx, rbx
0x180028327  mov     [r13+rbx*8+0], rcx
0x18002832c  mov     rax, [rcx]
0x18002832f  mov     rax, [rax+8]
0x180028333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028338  mov     rax, [rbp+38h]
0x18002833c  inc     edi
0x18002833e  mov     rcx, [rsp+58h+arg_8]
0x180028343  mov     ecx, [rax+rcx+8]
0x180028347  mov     [r13+rbx*8+8], ecx
0x18002834c  inc     r12d
0x18002834f  cmp     r12d, [rbp+30h]
0x180028353  jb      short loc_180028303
0x180028355  mov     edi, [rsp+58h+arg_18]
0x180028359  mov     [r15], r13
0x18002835c  mov     [r14], esi
0x18002835f  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x180028366  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002836c  jmp     short loc_180028373
0x18002836e  mov     edi, 80070057h
0x180028373  mov     rbx, [rsp+58h+arg_0]
0x180028378  mov     eax, edi
0x18002837a  add     rsp, 20h
0x18002837e  pop     r15
0x180028380  pop     r14
0x180028382  pop     r13
0x180028384  pop     r12
0x180028386  pop     rdi
0x180028387  pop     rsi
0x180028388  pop     rbp
0x180028389  retn
```

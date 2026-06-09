# CddBitmapBase::AddCommandBufferReference(CHwCommandBuffer *,tagRECT const *,uint,tagPOINT const *)

- ea: `0x140014130`
- end: `0x140014179`
- name: `?AddCommandBufferReference@CddBitmapBase@@UEAAXPEAVCHwCommandBuffer@@PEBUtagRECT@@IPEBUtagPOINT@@@Z`
- size: `73`
- prototype: `void __fastcall(CddBitmapBase *__hidden this, struct CHwCommandBuffer *, const struct tagRECT *, unsigned int, const struct tagPOINT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140014130`

## pseudocode

```c
void __fastcall CddBitmapBase::AddCommandBufferReference(
        CddBitmapBase *this,
        struct CHwCommandBuffer *a2,
        const struct tagRECT *a3)
{
  __int64 v4; // rcx
  char *v5; // rax
  struct CHwCommandBuffer **v6; // r8
  struct CHwCommandBuffer *v7; // rdx

  v4 = *((unsigned int *)a2 + 2);
  if ( !*((_BYTE *)this + v4 + 44) )
  {
    v5 = (char *)a2 + 2104;
    v6 = (struct CHwCommandBuffer **)*((_QWORD *)a2 + 264);
    if ( *v6 != (struct CHwCommandBuffer *)((char *)a2 + 2104) )
      __fastfail(3u);
    v7 = (CddBitmapBase *)((char *)this + 16 * v4 + 96);
    *(_QWORD *)v7 = v5;
    *((_QWORD *)v7 + 1) = v6;
    *v6 = v7;
    *((_QWORD *)v5 + 1) = v7;
    *((_BYTE *)this + v4 + 44) = 1;
  }
}

```

## disassembly

```asm
0x140014130  mov     r9, rcx
0x140014133  mov     ecx, [rdx+8]
0x140014136  cmp     byte ptr [rcx+r9+2Ch], 0
0x14001413c  lea     r10, [rcx+r9]
0x140014140  jnz     short locret_140014170
0x140014142  lea     rax, [rdx+838h]
0x140014149  mov     r8, [rax+8]
0x14001414d  cmp     [r8], rax
0x140014150  jnz     short loc_140014172
0x140014152  lea     rdx, [rcx+6]
0x140014156  shl     rdx, 4
0x14001415a  add     rdx, r9
0x14001415d  mov     [rdx], rax
0x140014160  mov     [rdx+8], r8
0x140014164  mov     [r8], rdx
0x140014167  mov     [rax+8], rdx
0x14001416b  mov     byte ptr [r10+2Ch], 1
0x140014170  retn
0x140014172  mov     ecx, 3
0x140014177  int     29h; Win8: RtlFailFast(ecx)
```

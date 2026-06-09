# CSidCache::Add(void *,ushort const *)

- ea: `0x18001b3f8`
- end: `0x18001b4bd`
- name: `?Add@CSidCache@@QEAAJPEAXPEBG@Z`
- size: `197`
- prototype: `int(CSidCache *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000e208`
- `0x180019c40`

## callees

- `0x180002928`
- `0x180017d40`
- `0x18001b3f8`
- `0x18001b558`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSidCache::Add(CSidCache *this, void *a2, const unsigned __int16 *a3)
{
  struct CLruCacheItem *v5; // rax
  struct CLruCacheItem *v6; // rbx
  unsigned int v7; // edi

  v5 = (struct CLruCacheItem *)operator new(0x30u);
  v6 = v5;
  if ( v5 )
  {
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    *((_DWORD *)v5 + 6) = 0;
    *(_QWORD *)v5 = &CSidCacheItem::`vftable';
    *((_QWORD *)v5 + 4) = 0;
    *((_QWORD *)v5 + 5) = 0;
    CSidCacheItem::_Set(v5, a2, a3);
  }
  else
  {
    v6 = 0;
  }
  if ( v6 )
  {
    if ( *((_QWORD *)v6 + 4) )
    {
      return (unsigned int)CLruCache::Add((CLruCache *)&g_SidCache, v6);
    }
    else
    {
      v7 = -2147024882;
      (**(void (__fastcall ***)(struct CLruCacheItem *, __int64))v6)(v6, 1);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x18001b3f8  mov     [rsp+arg_8], rbx
0x18001b3fd  mov     [rsp+arg_10], rsi
0x18001b402  mov     [rsp+arg_0], rcx
0x18001b407  push    rdi
0x18001b408  sub     rsp, 20h
0x18001b40c  mov     rdi, r8
0x18001b40f  mov     rsi, rdx
0x18001b412  mov     ecx, 30h ; '0'; Size
0x18001b417  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b41c  mov     rbx, rax
0x18001b41f  mov     [rsp+28h+arg_0], rax
0x18001b424  test    rax, rax
0x18001b427  jz      short loc_18001B46B
0x18001b429  mov     qword ptr [rax+8], 0
0x18001b431  mov     qword ptr [rax+10h], 0
0x18001b439  mov     dword ptr [rax+18h], 0
0x18001b440  lea     rax, ??_7CSidCacheItem@@6B@; const CSidCacheItem::`vftable'
0x18001b447  mov     [rbx], rax
0x18001b44a  mov     qword ptr [rbx+20h], 0
0x18001b452  mov     qword ptr [rbx+28h], 0
0x18001b45a  mov     r8, rdi; unsigned __int16 *
0x18001b45d  mov     rdx, rsi; void *
0x18001b460  mov     rcx, rbx; this
0x18001b463  call    ?_Set@CSidCacheItem@@AEAAJPEAXPEBG@Z; CSidCacheItem::_Set(void *,ushort const *)
0x18001b468  nop
0x18001b469  jmp     short loc_18001B46D
0x18001b46b  xor     ebx, ebx
0x18001b46d  test    rbx, rbx
0x18001b470  jz      short loc_18001B4A6
0x18001b472  cmp     qword ptr [rbx+20h], 0
0x18001b477  jz      short loc_18001B48C
0x18001b479  mov     rdx, rbx; struct CLruCacheItem *
0x18001b47c  lea     rcx, ?g_SidCache@@3VCSidCache@@A; this
0x18001b483  call    ?Add@CLruCache@@UEAAJPEAVCLruCacheItem@@@Z; CLruCache::Add(CLruCacheItem *)
0x18001b488  mov     edi, eax
0x18001b48a  jmp     short loc_18001B4AB
0x18001b48c  mov     edi, 8007000Eh
0x18001b491  mov     rax, [rbx]
0x18001b494  mov     edx, 1
0x18001b499  mov     rcx, rbx
0x18001b49c  mov     rax, [rax]
0x18001b49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4a4  jmp     short loc_18001B4AB
0x18001b4a6  mov     edi, 8007000Eh
0x18001b4ab  mov     eax, edi
0x18001b4ad  mov     rbx, [rsp+28h+arg_8]
0x18001b4b2  mov     rsi, [rsp+28h+arg_10]
0x18001b4b7  add     rsp, 20h
0x18001b4bb  pop     rdi
0x18001b4bc  retn
```

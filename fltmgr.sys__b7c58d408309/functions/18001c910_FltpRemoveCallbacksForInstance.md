# FltpRemoveCallbacksForInstance

- ea: `0x18001c910`
- end: `0x18001c9fd`
- name: `FltpRemoveCallbacksForInstance`
- size: `237`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180063b40`

## callees

- `0x18001c910`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x18001c92d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18001c92d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001c977`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001c977`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x18001c93c`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x18001c93c`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x18001c96b`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x18001c96b`

## pseudocode

```c
void __fastcall FltpRemoveCallbacksForInstance(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 *v5; // rdx
  __int64 *v6; // rcx
  __int64 **v7; // r9
  int v8; // ecx
  int v9; // edx
  __int64 **v10; // r9
  __int64 *i; // rcx

  v1 = *(_QWORD *)(a1 + 64);
  v3 = qword_18003E9A0;
  KeEnterGuardedRegion();
  ExAcquireCacheAwarePushLockExclusive(v3);
  v4 = 0;
  do
  {
    v5 = *(__int64 **)(a1 + 8 * v4 + 304);
    if ( v5 && *v5 )
    {
      v6 = (__int64 *)*v5;
      if ( *(__int64 **)(*v5 + 8) != v5 || (v7 = (__int64 **)v5[1], *v7 != v5) )
        __fastfail(3u);
      *v7 = v6;
      v6[1] = (__int64)v7;
      v8 = v5[5] & 0x1B;
      *v5 = 0;
      if ( (_BYTE)v8 != 27 )
      {
        v9 = 27;
        v10 = (__int64 **)(v1 + 16 * (v4 + 20));
        for ( i = *v10; i != (__int64 *)v10; i = (__int64 *)*i )
          v9 &= *((_DWORD *)i + 10);
        *(_DWORD *)(v1 + 4 * v4 + 1120) = v9;
      }
    }
    v4 = (unsigned int)(v4 + 1);
  }
  while ( (unsigned int)v4 < 0x32 );
  ExReleaseCacheAwarePushLockExclusive(qword_18003E9A0);
  KeLeaveGuardedRegion();
}

```

## disassembly

```asm
0x18001c910  mov     [rsp+arg_0], rbx
0x18001c915  mov     [rsp+arg_8], rsi
0x18001c91a  push    rdi
0x18001c91b  sub     rsp, 20h
0x18001c91f  mov     rsi, [rcx+40h]
0x18001c923  mov     rdi, rcx
0x18001c926  mov     rbx, cs:qword_18003E9A0
0x18001c92d  call    cs:__imp_KeEnterGuardedRegion
0x18001c934  nop     dword ptr [rax+rax+00h]
0x18001c939  mov     rcx, rbx
0x18001c93c  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x18001c943  nop     dword ptr [rax+rax+00h]
0x18001c948  xor     eax, eax
0x18001c94a  nop     word ptr [rax+rax+00h]
0x18001c950  mov     rdx, [rdi+rax*8+130h]
0x18001c958  test    rdx, rdx
0x18001c95b  jnz     short loc_18001C994
0x18001c95d  inc     eax
0x18001c95f  cmp     eax, 32h ; '2'
0x18001c962  jb      short loc_18001C950
0x18001c964  mov     rcx, cs:qword_18003E9A0
0x18001c96b  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x18001c972  nop     dword ptr [rax+rax+00h]
0x18001c977  call    cs:__imp_KeLeaveGuardedRegion
0x18001c97e  nop     dword ptr [rax+rax+00h]
0x18001c983  mov     rbx, [rsp+28h+arg_0]
0x18001c988  mov     rsi, [rsp+28h+arg_8]
0x18001c98d  add     rsp, 20h
0x18001c991  pop     rdi
0x18001c992  retn
0x18001c994  mov     rcx, [rdx]
0x18001c997  test    rcx, rcx
0x18001c99a  jz      short loc_18001C95D
0x18001c99c  mov     rcx, [rdx]
0x18001c99f  cmp     [rcx+8], rdx
0x18001c9a3  jnz     short loc_18001C9F6
0x18001c9a5  mov     r9, [rdx+8]
0x18001c9a9  cmp     [r9], rdx
0x18001c9ac  jnz     short loc_18001C9F6
0x18001c9ae  mov     [r9], rcx
0x18001c9b1  mov     [rcx+8], r9
0x18001c9b5  mov     ecx, [rdx+28h]
0x18001c9b8  and     ecx, 1Bh
0x18001c9bb  mov     qword ptr [rdx], 0
0x18001c9c2  cmp     cl, 1Bh
0x18001c9c5  jz      short loc_18001C95D
0x18001c9c7  lea     r9, [rax+14h]
0x18001c9cb  mov     edx, 1Bh
0x18001c9d0  shl     r9, 4
0x18001c9d4  add     r9, rsi
0x18001c9d7  mov     rcx, [r9]
0x18001c9da  cmp     rcx, r9
0x18001c9dd  jz      short loc_18001C9EA
0x18001c9df  and     edx, [rcx+28h]
0x18001c9e2  mov     rcx, [rcx]
0x18001c9e5  cmp     rcx, r9
0x18001c9e8  jnz     short loc_18001C9DF
0x18001c9ea  mov     [rsi+rax*4+460h], edx
0x18001c9f1  jmp     loc_18001C95D
0x18001c9f6  mov     ecx, 3
0x18001c9fb  int     29h; Win8: RtlFailFast(ecx)
```

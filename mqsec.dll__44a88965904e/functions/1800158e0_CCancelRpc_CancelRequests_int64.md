# CCancelRpc::CancelRequests(__int64)

- ea: `0x1800158e0`
- end: `0x180015985`
- name: `?CancelRequests@CCancelRpc@@QEAAX_J@Z`
- size: `165`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180015f90`

## callees

- `0x18000b95c`
- `0x1800158e0`
- `0x1800160b0`

## import_xrefs

- `RPCRT4!RpcCancelThread` at `0x18001595c`
- `RPCRT4!RpcCancelThread` at `0x18001595c`
- `KERNEL32!LeaveCriticalSection` at `0x180015975`
- `KERNEL32!LeaveCriticalSection` at `0x180015975`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CCancelRpc::CancelRequests(CCriticalSection *lpCriticalSection, __int64 a2)
{
  __int64 v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 i; // rcx
  void *v8; // rbx

  CCriticalSection::Lock(lpCriticalSection);
  if ( *((_DWORD *)lpCriticalSection + 15) )
  {
    v4 = -1;
    do
    {
      v5 = v4;
      if ( v4 == -1 && *((_DWORD *)lpCriticalSection + 14) )
      {
        v6 = 0;
        do
        {
          v5 = *(_QWORD *)(*((_QWORD *)lpCriticalSection + 6) + 8 * v6);
          if ( v5 )
            break;
          v6 = (unsigned int)(v6 + 1);
        }
        while ( (unsigned int)v6 < *((_DWORD *)lpCriticalSection + 14) );
      }
      v4 = *(_QWORD *)v5;
      if ( !*(_QWORD *)v5 )
      {
        for ( i = (unsigned int)(*(_DWORD *)(v5 + 8) + 1);
              (unsigned int)i < *((_DWORD *)lpCriticalSection + 14);
              i = (unsigned int)(i + 1) )
        {
          v4 = *(_QWORD *)(*((_QWORD *)lpCriticalSection + 6) + 8 * i);
          if ( v4 )
            break;
        }
      }
      if ( *(_QWORD *)(v5 + 24) < a2 )
      {
        v8 = *(void **)(v5 + 16);
        RpcCancelThread(v8);
        CCancelRpc::Remove((LPCRITICAL_SECTION)lpCriticalSection, v8);
      }
    }
    while ( v4 );
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
}

```

## disassembly

```asm
0x1800158e0  push    rbx
0x1800158e2  push    rbp
0x1800158e3  push    rsi
0x1800158e4  push    rdi
0x1800158e5  sub     rsp, 28h
0x1800158e9  mov     rbp, rdx
0x1800158ec  mov     rdi, rcx
0x1800158ef  mov     [rsp+48h+arg_0], rcx
0x1800158f4  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x1800158f9  nop
0x1800158fa  cmp     dword ptr [rdi+3Ch], 0
0x1800158fe  jz      short loc_180015972
0x180015900  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180015904  mov     rbx, rsi
0x180015907  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001590b  jnz     short loc_180015929
0x18001590d  cmp     dword ptr [rdi+38h], 0
0x180015911  jbe     short loc_180015929
0x180015913  xor     ecx, ecx
0x180015915  mov     rdx, [rdi+30h]
0x180015919  mov     rbx, [rdx+rcx*8]
0x18001591d  test    rbx, rbx
0x180015920  jnz     short loc_180015929
0x180015922  inc     ecx
0x180015924  cmp     ecx, [rdi+38h]
0x180015927  jb      short loc_180015919
0x180015929  mov     rsi, [rbx]
0x18001592c  test    rsi, rsi
0x18001592f  jnz     short loc_18001594F
0x180015931  mov     ecx, [rbx+8]
0x180015934  inc     ecx
0x180015936  cmp     ecx, [rdi+38h]
0x180015939  jnb     short loc_18001594F
0x18001593b  mov     rdx, [rdi+30h]
0x18001593f  mov     rsi, [rdx+rcx*8]
0x180015943  test    rsi, rsi
0x180015946  jnz     short loc_18001594F
0x180015948  inc     ecx
0x18001594a  cmp     ecx, [rdi+38h]
0x18001594d  jb      short loc_18001593F
0x18001594f  cmp     [rbx+18h], rbp
0x180015953  jge     short loc_18001596D
0x180015955  mov     rbx, [rbx+10h]
0x180015959  mov     rcx, rbx; Thread
0x18001595c  call    cs:__imp_RpcCancelThread
0x180015962  mov     rdx, rbx; void *
0x180015965  mov     rcx, rdi; lpCriticalSection
0x180015968  call    ?Remove@CCancelRpc@@QEAAXPEAX@Z; CCancelRpc::Remove(void *)
0x18001596d  test    rsi, rsi
0x180015970  jnz     short loc_180015904
0x180015972  mov     rcx, rdi; lpCriticalSection
0x180015975  call    cs:__imp_LeaveCriticalSection
0x18001597b  nop
0x18001597c  add     rsp, 28h
0x180015980  pop     rdi
0x180015981  pop     rsi
0x180015982  pop     rbp
0x180015983  pop     rbx
0x180015984  retn
```

# CCancelRpc::Remove(void *)

- ea: `0x1800160b0`
- end: `0x180016128`
- name: `?Remove@CCancelRpc@@QEAAXPEAX@Z`
- size: `120`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800158e0`

## callees

- `0x180004808`
- `0x18000b95c`
- `0x1800160b0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180016116`
- `KERNEL32!LeaveCriticalSection` at `0x180016116`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CCancelRpc::Remove(CCriticalSection *lpCriticalSection, void *a2)
{
  __int64 v4; // r9
  void ***v5; // rdx
  void **i; // rcx

  CCriticalSection::Lock(lpCriticalSection);
  v4 = *((_QWORD *)lpCriticalSection + 6);
  if ( v4 )
  {
    v5 = (void ***)(v4 + 8LL * (((unsigned int)a2 >> 4) % *((_DWORD *)lpCriticalSection + 14)));
    for ( i = *v5; i; i = (void **)*i )
    {
      if ( i[2] == a2 )
      {
        *v5 = (void **)*i;
        *i = (void *)*((_QWORD *)lpCriticalSection + 8);
        *((_QWORD *)lpCriticalSection + 8) = i;
        if ( (*((_DWORD *)lpCriticalSection + 15))-- == 1 )
          CMap<void *,void *,__int64,__int64>::RemoveAll((char *)lpCriticalSection + 40);
        break;
      }
      v5 = (void ***)i;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
}

```

## disassembly

```asm
0x1800160b0  mov     [rsp+arg_8], rbx
0x1800160b5  push    rdi
0x1800160b6  sub     rsp, 20h
0x1800160ba  mov     rdi, rdx
0x1800160bd  mov     rbx, rcx
0x1800160c0  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x1800160c5  mov     r9, [rbx+30h]
0x1800160c9  test    r9, r9
0x1800160cc  jz      short loc_180016113
0x1800160ce  mov     eax, edi
0x1800160d0  shr     eax, 4
0x1800160d3  xor     edx, edx
0x1800160d5  div     dword ptr [rbx+38h]
0x1800160d8  lea     rdx, [r9+rdx*8]
0x1800160dc  mov     rcx, [rdx]
0x1800160df  test    rcx, rcx
0x1800160e2  jz      short loc_180016113
0x1800160e4  mov     rax, [rcx]
0x1800160e7  cmp     [rcx+10h], rdi
0x1800160eb  jz      short loc_1800160F5
0x1800160ed  mov     rdx, rcx
0x1800160f0  mov     rcx, rax
0x1800160f3  jmp     short loc_1800160DF
0x1800160f5  mov     [rdx], rax
0x1800160f8  mov     rax, [rbx+40h]
0x1800160fc  mov     [rcx], rax
0x1800160ff  mov     [rbx+40h], rcx
0x180016103  sub     dword ptr [rbx+3Ch], 1
0x180016107  jnz     short loc_180016113
0x180016109  lea     rcx, [rbx+28h]
0x18001610d  call    ?RemoveAll@?$CMap@PEAXPEAX_J_J@@QEAAXXZ; CMap<void *,void *,__int64,__int64>::RemoveAll(void)
0x180016112  nop
0x180016113  mov     rcx, rbx; lpCriticalSection
0x180016116  call    cs:__imp_LeaveCriticalSection
0x18001611c  nop
0x18001611d  mov     rbx, [rsp+28h+arg_8]
0x180016122  add     rsp, 20h
0x180016126  pop     rdi
0x180016127  retn
```

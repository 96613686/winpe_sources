# Dfdll::CArray<Dfdll::CBuffer<uint>,uint>::`scalar deleting destructor'(uint)

- ea: `0x180009030`
- end: `0x18000909a`
- name: `??_G?$CArray@V?$CBuffer@I@Dfdll@@I@Dfdll@@UEAAPEAXI@Z`
- size: `106`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180009030`
- `0x180012b30`

## pseudocode

```c
_QWORD *__fastcall Dfdll::CArray<Dfdll::CBuffer<unsigned int>,unsigned int>::`scalar deleting destructor'(
        _QWORD *a1,
        const struct std::nothrow_t *a2)
{
  char v2; // di
  void *v4; // rcx

  v2 = (char)a2;
  *a1 = &Dfdll::CArray<Dfdll::CBuffer<unsigned int>,unsigned int>::`vftable';
  a1[3] = &Dfdll::CBuffer<unsigned int>::`vftable';
  v4 = (void *)a1[4];
  if ( v4 )
    operator delete(v4, a2);
  a1[4] = 0;
  *((_DWORD *)a1 + 10) = 0;
  a1[3] = &Dfdll::CObject::`vftable';
  *a1 = &Dfdll::CObject::`vftable';
  if ( (v2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x30);
  return a1;
}

```

## disassembly

```asm
0x180009030  mov     [rsp+arg_0], rbx
0x180009035  push    rdi
0x180009036  sub     rsp, 20h
0x18000903a  mov     edi, edx
0x18000903c  mov     rbx, rcx
0x18000903f  lea     rax, ??_7?$CArray@V?$CBuffer@I@Dfdll@@I@Dfdll@@6B@; const Dfdll::CArray<Dfdll::CBuffer<uint>,uint>::`vftable'
0x180009046  mov     [rcx], rax
0x180009049  lea     rax, ??_7?$CBuffer@I@Dfdll@@6B@; const Dfdll::CBuffer<uint>::`vftable'
0x180009050  mov     [rcx+18h], rax
0x180009054  mov     rcx, [rcx+20h]; void *
0x180009058  test    rcx, rcx
0x18000905b  jz      short loc_180009062
0x18000905d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009062  and     qword ptr [rbx+20h], 0
0x180009067  and     dword ptr [rbx+28h], 0
0x18000906b  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180009072  mov     [rbx+18h], rax
0x180009076  mov     [rbx], rax
0x180009079  test    dil, 1
0x18000907d  jz      short loc_18000908C
0x18000907f  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180009084  mov     rcx, rbx; void *
0x180009087  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000908c  mov     rax, rbx
0x18000908f  mov     rbx, [rsp+28h+arg_0]
0x180009094  add     rsp, 20h
0x180009098  pop     rdi
0x180009099  retn
```

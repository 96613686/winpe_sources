# KpsIoLockedRef::RemoveRef(void)

- ea: `0x180024be0`
- end: `0x180024c8f`
- name: `?RemoveRef@KpsIoLockedRef@@QEAA_NXZ`
- size: `175`
- prototype: `char __fastcall(KpsIoLockedRef *this)`
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001e728`
- `0x18001e8e8`
- `0x18001eb40`
- `0x18001edec`
- `0x18001f048`
- `0x18001f390`
- `0x18001f5ec`
- `0x18001fd08`
- `0x180020038`
- `0x180020610`
- `0x180020750`
- `0x1800208d8`
- `0x180020d0c`
- `0x1800210f4`
- `0x1800215c0`
- `0x1800216f4`
- `0x180021b10`
- `0x1800225d0`
- `0x180022708`
- `0x180022a5c`

## callees

- `0x1800203ac`
- `0x180024be0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180024c5e`
- `ntdll!RtlLeaveCriticalSection` at `0x180024c5e`
- `ntdll!RtlEnterCriticalSection` at `0x180024c1c`
- `ntdll!RtlEnterCriticalSection` at `0x180024c1c`

## pseudocode

```c
char __fastcall KpsIoLockedRef::RemoveRef(KpsIoLockedRef *this)
{
  __int64 v1; // rdi
  char v2; // bl
  signed __int64 v3; // rax
  bool v4; // cc
  signed __int64 v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rdx

  v1 = *(_QWORD *)this;
  v2 = 0;
  if ( !*(_QWORD *)this )
    return 0;
  v3 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v1 + 344), 0xFFFFFFFFFFFFFFFFuLL);
  v4 = v3 <= 1;
  v5 = v3 - 1;
  if ( v4 )
  {
    if ( v5 )
      __fastfail(0xEu);
    KpsFreeKpsIo((struct _KPS_IO *)v1);
    return 1;
  }
  else
  {
    RtlEnterCriticalSection(&stru_18003AC20);
    v6 = (_QWORD *)(v1 + 40);
    v7 = *(_QWORD *)(v1 + 40);
    if ( v7 && *(_QWORD *)(v1 + 48) )
    {
      if ( *(_QWORD **)(v7 + 8) != v6 || (v8 = *(_QWORD **)(v1 + 48), (_QWORD *)*v8 != v6) )
        __fastfail(3u);
      *v8 = v7;
      *(_QWORD *)(v7 + 8) = v8;
      *v6 = 0;
      *(_QWORD *)(v1 + 48) = 0;
    }
    RtlLeaveCriticalSection(&stru_18003AC20);
  }
  return v2;
}

```

## disassembly

```asm
0x180024be0  mov     [rsp+arg_0], rbx
0x180024be5  push    rdi
0x180024be6  sub     rsp, 20h
0x180024bea  mov     rdi, [rcx]
0x180024bed  xor     ebx, ebx
0x180024bef  test    rdi, rdi
0x180024bf2  jz      loc_180024C81
0x180024bf8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024bfc  lock xadd [rdi+158h], rax
0x180024c05  sub     rax, 1
0x180024c09  jg      short loc_180024C15
0x180024c0b  test    rax, rax
0x180024c0e  jz      short loc_180024C6E
0x180024c10  lea     ecx, [rbx+0Eh]
0x180024c13  int     29h; Win8: RtlFailFast(ecx)
0x180024c15  lea     rcx, stru_18003AC20; CriticalSection
0x180024c1c  call    cs:__imp_RtlEnterCriticalSection
0x180024c23  nop     dword ptr [rax+rax+00h]
0x180024c28  lea     rax, [rdi+28h]
0x180024c2c  mov     rcx, [rax]
0x180024c2f  test    rcx, rcx
0x180024c32  jz      short loc_180024C57
0x180024c34  cmp     [rdi+30h], rbx
0x180024c38  jz      short loc_180024C57
0x180024c3a  cmp     [rcx+8], rax
0x180024c3e  jnz     short loc_180024C7A
0x180024c40  mov     rdx, [rax+8]
0x180024c44  cmp     [rdx], rax
0x180024c47  jnz     short loc_180024C7A
0x180024c49  mov     [rdx], rcx
0x180024c4c  mov     [rcx+8], rdx
0x180024c50  mov     [rax], rbx
0x180024c53  mov     [rdi+30h], rbx
0x180024c57  lea     rcx, stru_18003AC20; CriticalSection
0x180024c5e  call    cs:__imp_RtlLeaveCriticalSection
0x180024c65  nop     dword ptr [rax+rax+00h]
0x180024c6a  mov     al, bl
0x180024c6c  jmp     short loc_180024C83
0x180024c6e  mov     rcx, rdi; lpMem
0x180024c71  call    ?KpsFreeKpsIo@@YAXPEAU_KPS_IO@@@Z; KpsFreeKpsIo(_KPS_IO *)
0x180024c76  mov     bl, 1
0x180024c78  jmp     short loc_180024C6A
0x180024c7a  mov     ecx, 3
0x180024c7f  int     29h; Win8: RtlFailFast(ecx)
0x180024c81  xor     al, al
0x180024c83  mov     rbx, [rsp+28h+arg_0]
0x180024c88  add     rsp, 20h
0x180024c8c  pop     rdi
0x180024c8d  retn
```

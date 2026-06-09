# SetAppCompatStringPointer(unsigned __int64,char const *)

- ea: `0x18000efc0`
- end: `0x18000f02c`
- name: `?SetAppCompatStringPointer@@YAX_KPEBD@Z`
- size: `108`
- prototype: `void __fastcall(unsigned __int64, const char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180009084`
- `0x18000affc`
- `0x18000efc0`
- `0x18000f034`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SetAppCompatStringPointer(unsigned __int64 a1, const char *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rbp
  _Smtx_t *v6; // [rsp+20h] [rbp-38h] BYREF
  char v7; // [rsp+28h] [rbp-30h]

  SetAppCompatStringPointerInternal(a1, a2);
  std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(&v6, &qword_18001E7F8);
  v4 = qword_18001E858;
  v5 = qword_18001E860;
  while ( v4 != v5 )
  {
    (*(void (__fastcall **)(unsigned __int64, const char *))(*(_QWORD *)v4 + 88LL))(a1, a2);
    v4 += 8;
  }
  if ( v7 )
    Smtx_unlock_shared(v6);
}

```

## disassembly

```asm
0x18000efc0  push    rbx
0x18000efc2  push    rbp
0x18000efc3  push    rsi
0x18000efc4  push    rdi
0x18000efc5  sub     rsp, 38h
0x18000efc9  mov     rdi, rdx
0x18000efcc  mov     rsi, rcx
0x18000efcf  call    ?SetAppCompatStringPointerInternal@@YAX_KPEBD@Z; SetAppCompatStringPointerInternal(unsigned __int64,char const *)
0x18000efd4  nop
0x18000efd5  lea     rdx, qword_18001E7F8
0x18000efdc  lea     rcx, [rsp+58h+var_38]
0x18000efe1  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x18000efe6  mov     rbx, cs:qword_18001E858
0x18000efed  mov     rbp, cs:qword_18001E860
0x18000eff4  jmp     short loc_18000F00C
0x18000eff6  mov     rax, [rbx]
0x18000eff9  mov     rdx, rdi
0x18000effc  mov     rcx, rsi
0x18000efff  mov     rax, [rax+58h]
0x18000f003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f008  add     rbx, 8
0x18000f00c  cmp     rbx, rbp
0x18000f00f  jnz     short loc_18000EFF6
0x18000f011  cmp     [rsp+58h+var_30], 0
0x18000f016  jz      short loc_18000F023
0x18000f018  mov     rcx, [rsp+58h+var_38]; _Smtx_t *
0x18000f01d  call    _Smtx_unlock_shared
0x18000f022  nop
0x18000f023  add     rsp, 38h
0x18000f027  pop     rdi
0x18000f028  pop     rsi
0x18000f029  pop     rbp
0x18000f02a  pop     rbx
0x18000f02b  retn
```

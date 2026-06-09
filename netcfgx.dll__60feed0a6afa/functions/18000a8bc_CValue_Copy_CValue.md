# CValue::Copy(CValue *)

- ea: `0x18000a8bc`
- end: `0x18000a94b`
- name: `?Copy@CValue@@QEAAXPEAV1@@Z`
- size: `143`
- prototype: `void __fastcall(CValue *__hidden this, struct CValue *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008cc0`
- `0x180008f28`
- `0x18000994c`
- `0x18000af5c`

## callees

- `0x1800069b8`
- `0x180007d38`
- `0x18000a8bc`
- `0x18000a954`

## pseudocode

```c
void __fastcall CValue::Copy(CValue *this, struct CValue *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rcx
  unsigned __int16 *v7; // rax
  const unsigned __int16 *v8; // r8

  CValue::Destroy(this);
  *(_OWORD *)this = *(_OWORD *)a2;
  *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
  *((_QWORD *)this + 4) = *((_QWORD *)a2 + 4);
  if ( !*((_DWORD *)a2 + 2) )
  {
    v4 = *((_QWORD *)a2 + 4);
    if ( v4 )
    {
      v5 = -1;
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)(v4 + 2 * v6) );
      v7 = (unsigned __int16 *)MemAlloc(saturated_mul(v6 + 1, 2u));
      *((_QWORD *)this + 4) = v7;
      if ( v7 )
      {
        v8 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
        do
          ++v5;
        while ( v8[v5] );
        StringCchCopyW(v7, v5 + 1, v8);
      }
    }
  }
}

```

## disassembly

```asm
0x18000a8bc  push    rbx
0x18000a8be  push    rbp
0x18000a8bf  push    rsi
0x18000a8c0  push    rdi
0x18000a8c1  sub     rsp, 28h
0x18000a8c5  mov     rdi, rdx
0x18000a8c8  mov     rsi, rcx
0x18000a8cb  call    ?Destroy@CValue@@QEAAXXZ; CValue::Destroy(void)
0x18000a8d0  movups  xmm0, xmmword ptr [rdi]
0x18000a8d3  xor     ebp, ebp
0x18000a8d5  movups  xmmword ptr [rsi], xmm0
0x18000a8d8  movups  xmm1, xmmword ptr [rdi+10h]
0x18000a8dc  movups  xmmword ptr [rsi+10h], xmm1
0x18000a8e0  movsd   xmm0, qword ptr [rdi+20h]
0x18000a8e5  movsd   qword ptr [rsi+20h], xmm0
0x18000a8ea  cmp     [rdi+8], ebp
0x18000a8ed  jnz     short loc_18000A942
0x18000a8ef  mov     rax, [rdi+20h]
0x18000a8f3  test    rax, rax
0x18000a8f6  jz      short loc_18000A942
0x18000a8f8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a8fc  mov     rcx, rbx
0x18000a8ff  inc     rcx
0x18000a902  cmp     [rax+rcx*2], bp
0x18000a906  jnz     short loc_18000A8FF
0x18000a908  inc     rcx
0x18000a90b  mov     eax, 2
0x18000a910  mul     rcx
0x18000a913  cmovb   rax, rbx
0x18000a917  mov     rcx, rax; unsigned __int64
0x18000a91a  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000a91f  mov     [rsi+20h], rax
0x18000a923  test    rax, rax
0x18000a926  jz      short loc_18000A942
0x18000a928  mov     r8, [rdi+20h]; unsigned __int16 *
0x18000a92c  inc     rbx
0x18000a92f  cmp     [r8+rbx*2], bp
0x18000a934  jnz     short loc_18000A92C
0x18000a936  lea     rdx, [rbx+1]; unsigned __int64
0x18000a93a  mov     rcx, rax; unsigned __int16 *
0x18000a93d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a942  add     rsp, 28h
0x18000a946  pop     rdi
0x18000a947  pop     rsi
0x18000a948  pop     rbp
0x18000a949  pop     rbx
0x18000a94a  retn
```

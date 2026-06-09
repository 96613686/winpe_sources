# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180015958`
- end: `0x180015a57`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800151c8`

## callees

- `0x180015958`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180015a23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180015a23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800159d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800159d3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // r8
  __int64 v5; // rcx
  _WORD *v6; // rax
  unsigned int v7; // ecx
  unsigned __int64 v8; // rcx
  LPVOID v9; // rax

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = -1;
  if ( v4 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v5;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v5) );
      }
      else
      {
        v5 = 0;
      }
      *(_QWORD *)(a1 + 8) = v5;
    }
    else
    {
      v5 = *(_QWORD *)(a1 + 8);
    }
    v4 = (v5 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v4;
  }
  if ( !v4 )
  {
    if ( is_mul_ok(v2, 2u) )
    {
      v6 = CoTaskMemAlloc(2 * v2);
      if ( v6 )
      {
        *(_QWORD *)(a1 + 16) = v2;
        *(_QWORD *)a1 = v6;
        *v6 = 0;
        return 0;
      }
      return (unsigned int)-2147024882;
    }
    return (unsigned int)-2147024362;
  }
  v7 = 0;
  if ( v2 > v4 )
  {
    if ( is_mul_ok(v4, 2u) )
    {
      v8 = v4 + 2048;
      if ( v4 <= 0x800 )
        v8 = 2 * v4;
      if ( v2 <= v8 )
        v2 = v8;
      v9 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v2);
      if ( v9 )
      {
        *(_QWORD *)(a1 + 16) = v2;
        *(_QWORD *)a1 = v9;
        return 0;
      }
      return (unsigned int)-2147024882;
    }
    return (unsigned int)-2147024362;
  }
  return v7;
}

```

## disassembly

```asm
0x180015958  mov     [rsp+arg_0], rbx
0x18001595d  mov     [rsp+arg_10], rsi
0x180015962  push    rdi
0x180015963  sub     rsp, 20h
0x180015967  lea     rdi, [rdx+1]
0x18001596b  mov     rbx, rcx
0x18001596e  cmp     rdi, rdx
0x180015971  jb      loc_180015A40
0x180015977  mov     r8, [rcx+10h]
0x18001597b  xor     esi, esi
0x18001597d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180015981  cmp     r8, rcx
0x180015984  jnz     short loc_1800159BF
0x180015986  cmp     [rbx+8], rcx
0x18001598a  jnz     short loc_1800159A8
0x18001598c  mov     rax, [rbx]
0x18001598f  test    rax, rax
0x180015992  jz      short loc_18001599F
0x180015994  inc     rcx
0x180015997  cmp     [rax+rcx*2], si
0x18001599b  jnz     short loc_180015994
0x18001599d  jmp     short loc_1800159A2
0x18001599f  mov     rcx, rsi
0x1800159a2  mov     [rbx+8], rcx
0x1800159a6  jmp     short loc_1800159AC
0x1800159a8  mov     rcx, [rbx+8]
0x1800159ac  mov     rax, [rbx]
0x1800159af  inc     rcx
0x1800159b2  neg     rax
0x1800159b5  sbb     r8, r8
0x1800159b8  and     r8, rcx
0x1800159bb  mov     [rbx+10h], r8
0x1800159bf  test    r8, r8
0x1800159c2  jnz     short loc_1800159EA
0x1800159c4  lea     eax, [r8+2]
0x1800159c8  mul     rdi
0x1800159cb  test    rdx, rdx
0x1800159ce  jnz     short loc_180015A40
0x1800159d0  mov     rcx, rax; cb
0x1800159d3  call    cs:__imp_CoTaskMemAlloc
0x1800159d9  test    rax, rax
0x1800159dc  jz      short loc_180015A39
0x1800159de  mov     [rbx+10h], rdi
0x1800159e2  mov     [rbx], rax
0x1800159e5  mov     [rax], si
0x1800159e8  jmp     short loc_180015A35
0x1800159ea  mov     ecx, esi
0x1800159ec  cmp     rdi, r8
0x1800159ef  jbe     short loc_180015A45
0x1800159f1  mov     eax, 2
0x1800159f6  mul     r8
0x1800159f9  mov     r9, rax
0x1800159fc  test    rdx, rdx
0x1800159ff  jnz     short loc_180015A40
0x180015a01  sub     rax, r8
0x180015a04  lea     rcx, [r8+800h]
0x180015a0b  cmp     rax, 800h
0x180015a11  cmovbe  rcx, r9
0x180015a15  cmp     rdi, rcx
0x180015a18  cmovbe  rdi, rcx
0x180015a1c  mov     rcx, [rbx]; pv
0x180015a1f  lea     rdx, [rdi+rdi]; cb
0x180015a23  call    cs:__imp_CoTaskMemRealloc
0x180015a29  test    rax, rax
0x180015a2c  jz      short loc_180015A39
0x180015a2e  mov     [rbx+10h], rdi
0x180015a32  mov     [rbx], rax
0x180015a35  mov     ecx, esi
0x180015a37  jmp     short loc_180015A45
0x180015a39  mov     ecx, 8007000Eh
0x180015a3e  jmp     short loc_180015A45
0x180015a40  mov     ecx, 80070216h
0x180015a45  mov     rbx, [rsp+28h+arg_0]
0x180015a4a  mov     eax, ecx
0x180015a4c  mov     rsi, [rsp+28h+arg_10]
0x180015a51  add     rsp, 20h
0x180015a55  pop     rdi
0x180015a56  retn
```

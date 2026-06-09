# HeapBlockMap32::ResetWriteWatch(void)

- ea: `0x18013d870`
- end: `0x18013d983`
- name: `?ResetWriteWatch@HeapBlockMap32@@QEAAXXZ`
- size: `275`
- prototype: `void __fastcall(HeapBlockMap32 *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1801b269c`

## callees

- `0x18013d870`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x18013d917`
- `KERNEL32!ResetWriteWatch` at `0x18013d934`
- `KERNEL32!ResetWriteWatch` at `0x18013d957`
- `KERNEL32!ResetWriteWatch` at `0x18013d972`
- `KERNEL32!ResetWriteWatch` at `0x18013d917`
- `KERNEL32!ResetWriteWatch` at `0x18013d934`
- `KERNEL32!ResetWriteWatch` at `0x18013d957`
- `KERNEL32!ResetWriteWatch` at `0x18013d972`

## pseudocode

```c
void __fastcall HeapBlockMap32::ResetWriteWatch(HeapBlockMap32 *this)
{
  __int64 v2; // rax
  void *v3; // r15
  int v4; // ebp
  __int64 i; // r14
  __int64 v6; // rsi
  __int64 j; // rbx
  __int64 v8; // rdi

  v2 = 0;
  v3 = 0;
  v4 = 0;
  for ( i = 0; i != 4096; ++i )
  {
    v6 = *((_QWORD *)this + i + 1);
    if ( v6 )
    {
      for ( j = 0; j != 256; ++j )
      {
        v8 = *(_QWORD *)(v6 + 8 * j + 8);
        if ( !v8 || *(_BYTE *)(v8 + 24) == 2 )
        {
          if ( v2 )
          {
            ResetWriteWatch(v3, (unsigned int)(v4 << 12));
            v2 = 0;
          }
        }
        else if ( *(_QWORD *)(v8 + 16) == v2 )
        {
          ++v4;
        }
        else
        {
          if ( v2 )
            ResetWriteWatch(v3, (unsigned int)(v4 << 12));
          v3 = *(void **)(v8 + 8);
          v4 = 1;
          v2 = *(_QWORD *)(v8 + 16);
        }
      }
    }
    else if ( v2 )
    {
      ResetWriteWatch(v3, (unsigned int)(v4 << 12));
      v2 = 0;
    }
  }
  if ( v2 )
    ResetWriteWatch(v3, (unsigned int)(v4 << 12));
}

```

## disassembly

```asm
0x18013d870  mov     [rsp+arg_8], rbx
0x18013d875  mov     [rsp+arg_10], rbp
0x18013d87a  mov     [rsp+arg_0], rcx
0x18013d87f  push    rsi
0x18013d880  push    rdi
0x18013d881  push    r12
0x18013d883  push    r14
0x18013d885  push    r15
0x18013d887  sub     rsp, 20h
0x18013d88b  mov     r12, [rsp+48h+arg_0]
0x18013d890  xor     eax, eax
0x18013d892  xor     r15d, r15d
0x18013d895  xor     ebp, ebp
0x18013d897  xor     r14d, r14d
0x18013d89a  nop     word ptr [rax+rax+00h]
0x18013d8a0  mov     rsi, [r12+r14*8+8]
0x18013d8a5  test    rsi, rsi
0x18013d8a8  jnz     short loc_18013D8E0
0x18013d8aa  test    rax, rax
0x18013d8ad  jnz     loc_18013D94F
0x18013d8b3  inc     r14
0x18013d8b6  cmp     r14, 1000h
0x18013d8bd  jnz     short loc_18013D8A0
0x18013d8bf  test    rax, rax
0x18013d8c2  jnz     loc_18013D96A
0x18013d8c8  mov     rbx, [rsp+48h+arg_8]
0x18013d8cd  mov     rbp, [rsp+48h+arg_10]
0x18013d8d2  add     rsp, 20h
0x18013d8d6  pop     r15
0x18013d8d8  pop     r14
0x18013d8da  pop     r12
0x18013d8dc  pop     rdi
0x18013d8dd  pop     rsi
0x18013d8de  retn
0x18013d8e0  xor     ebx, ebx
0x18013d8e2  mov     rdi, [rsi+rbx*8+8]
0x18013d8e7  test    rdi, rdi
0x18013d8ea  jnz     short loc_18013D8FF
0x18013d8ec  test    rax, rax
0x18013d8ef  jnz     short loc_18013D90F
0x18013d8f1  inc     rbx
0x18013d8f4  cmp     rbx, 100h
0x18013d8fb  jnz     short loc_18013D8E2
0x18013d8fd  jmp     short loc_18013D8B3
0x18013d8ff  cmp     byte ptr [rdi+18h], 2
0x18013d903  jz      short loc_18013D8EC
0x18013d905  cmp     [rdi+10h], rax
0x18013d909  jnz     short loc_18013D927
0x18013d90b  inc     ebp
0x18013d90d  jmp     short loc_18013D8F1
0x18013d90f  mov     edx, ebp
0x18013d911  mov     rcx, r15; lpBaseAddress
0x18013d914  shl     edx, 0Ch; dwRegionSize
0x18013d917  call    cs:__imp_ResetWriteWatch
0x18013d91e  nop     dword ptr [rax+rax+00h]
0x18013d923  xor     eax, eax
0x18013d925  jmp     short loc_18013D8F1
0x18013d927  test    rax, rax
0x18013d92a  jz      short loc_18013D940
0x18013d92c  shl     ebp, 0Ch
0x18013d92f  mov     rcx, r15; lpBaseAddress
0x18013d932  mov     edx, ebp; dwRegionSize
0x18013d934  call    cs:__imp_ResetWriteWatch
0x18013d93b  nop     dword ptr [rax+rax+00h]
0x18013d940  mov     r15, [rdi+8]
0x18013d944  mov     ebp, 1
0x18013d949  mov     rax, [rdi+10h]
0x18013d94d  jmp     short loc_18013D8F1
0x18013d94f  mov     edx, ebp
0x18013d951  mov     rcx, r15; lpBaseAddress
0x18013d954  shl     edx, 0Ch; dwRegionSize
0x18013d957  call    cs:__imp_ResetWriteWatch
0x18013d95e  nop     dword ptr [rax+rax+00h]
0x18013d963  xor     eax, eax
0x18013d965  jmp     loc_18013D8B3
0x18013d96a  shl     ebp, 0Ch
0x18013d96d  mov     rcx, r15; lpBaseAddress
0x18013d970  mov     edx, ebp; dwRegionSize
0x18013d972  call    cs:__imp_ResetWriteWatch
0x18013d979  nop     dword ptr [rax+rax+00h]
0x18013d97e  jmp     loc_18013D8C8
```

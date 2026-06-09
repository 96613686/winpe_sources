# DiscpBuildProviderContext

- ea: `0x180014b08`
- end: `0x180014b6e`
- name: `DiscpBuildProviderContext`
- size: `102`
- prototype: `RPC_STATUS __fastcall(UUID *Uuid, __int64, __int64, unsigned int, __int64, UUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014888`

## callees

- `0x180001cfe`
- `0x180014b08`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180014b4e`
- `RPCRT4!UuidCreate` at `0x180014b4e`

## pseudocode

```c
RPC_STATUS __fastcall DiscpBuildProviderContext(
        UUID *Uuid,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        UUID *a6)
{
  unsigned int v10; // esi
  unsigned int v11; // esi
  RPC_STATUS result; // eax

  memset_0(Uuid, 0, 0x58u);
  Uuid[4].Data1 = a4;
  *(_QWORD *)&Uuid[1].Data1 = a2;
  *(_QWORD *)Uuid[1].Data4 = a3;
  v10 = a4 - 1;
  if ( !v10 || (v11 = v10 - 1) == 0 || v11 == 3 )
    *(_QWORD *)Uuid[4].Data4 = a5;
  result = UuidCreate(Uuid);
  if ( !result )
    *a6 = *Uuid;
  return result;
}

```

## disassembly

```asm
0x180014b08  push    rbx
0x180014b0a  push    rbp
0x180014b0b  push    rsi
0x180014b0c  push    rdi
0x180014b0d  sub     rsp, 28h
0x180014b11  mov     rbx, rdx
0x180014b14  mov     rdi, r8
0x180014b17  xor     edx, edx; Val
0x180014b19  mov     esi, r9d
0x180014b1c  mov     rbp, rcx
0x180014b1f  lea     r8d, [rdx+58h]; Size
0x180014b23  call    memset_0
0x180014b28  mov     [rbp+40h], esi
0x180014b2b  mov     [rbp+10h], rbx
0x180014b2f  mov     [rbp+18h], rdi
0x180014b33  sub     esi, 1
0x180014b36  jz      short loc_180014B42
0x180014b38  sub     esi, 1
0x180014b3b  jz      short loc_180014B42
0x180014b3d  cmp     esi, 3
0x180014b40  jnz     short loc_180014B4B
0x180014b42  mov     rax, [rsp+48h+arg_20]
0x180014b47  mov     [rbp+48h], rax
0x180014b4b  mov     rcx, rbp; Uuid
0x180014b4e  call    cs:__imp_UuidCreate
0x180014b54  test    eax, eax
0x180014b56  jnz     short loc_180014B65
0x180014b58  mov     rcx, [rsp+48h+arg_28]
0x180014b5d  movups  xmm0, xmmword ptr [rbp+0]
0x180014b61  movdqu  xmmword ptr [rcx], xmm0
0x180014b65  add     rsp, 28h
0x180014b69  pop     rdi
0x180014b6a  pop     rsi
0x180014b6b  pop     rbp
0x180014b6c  pop     rbx
0x180014b6d  retn
```

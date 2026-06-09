# EtwpInitializeCompression(_TRACELOG_CONTEXT *)

- ea: `0x180013084`
- end: `0x180013132`
- name: `?EtwpInitializeCompression@@YAKPEAU_TRACELOG_CONTEXT@@@Z`
- size: `174`
- prototype: `unsigned int __fastcall(struct _TRACELOG_CONTEXT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012958`
- `0x1800148b8`

## callees

- `0x180001eb2`
- `0x180001ee2`
- `0x180001ff0`
- `0x18000202c`
- `0x180013084`

## import_xrefs

- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x1800130b4`
- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x1800130b4`

## pseudocode

```c
ULONG __fastcall EtwpInitializeCompression(struct _TRACELOG_CONTEXT *a1)
{
  USHORT v2; // cx
  NTSTATUS CompressionWorkSpaceSize; // eax
  ULONG result; // eax
  unsigned int v5; // esi
  void *v6; // rax
  void *v7; // rbx
  void *v8; // rax
  unsigned __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  ULONG v10; // [rsp+38h] [rbp+10h] BYREF

  LODWORD(v9) = 0;
  v2 = *((_WORD *)a1 + 277);
  v10 = 0;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(v2, (PULONG)&v9, &v10);
  result = RtlNtStatusToDosError_0(CompressionWorkSpaceSize);
  if ( !result )
  {
    v5 = *((_DWORD *)a1 + 192);
    v6 = operator new(v5, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
      memset_0(v6, 0, v5);
    *((_QWORD *)a1 + 81) = v7;
    if ( v7 )
    {
      v8 = operator new[]((unsigned int)v9, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)a1 + 82) = v8;
      return v8 == 0 ? 8 : 0;
    }
    else
    {
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013084  mov     rax, rsp
0x180013087  mov     [rax+18h], rbx
0x18001308b  mov     [rax+20h], rsi
0x18001308f  push    rdi
0x180013090  sub     rsp, 20h
0x180013094  mov     rdi, rcx
0x180013097  mov     dword ptr [rax+8], 0
0x18001309e  movzx   ecx, word ptr [rcx+22Ah]; CompressionFormatAndEngine
0x1800130a5  lea     r8, [rax+10h]; CompressFragmentWorkSpaceSize
0x1800130a9  lea     rdx, [rax+8]; CompressBufferWorkSpaceSize
0x1800130ad  mov     dword ptr [rax+10h], 0
0x1800130b4  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x1800130ba  mov     ecx, eax; Status
0x1800130bc  call    RtlNtStatusToDosError_0
0x1800130c1  test    eax, eax
0x1800130c3  jnz     short loc_180013122
0x1800130c5  mov     esi, [rdi+300h]
0x1800130cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800130d2  mov     ecx, esi; unsigned __int64
0x1800130d4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800130d9  mov     rbx, rax
0x1800130dc  test    rax, rax
0x1800130df  jz      short loc_1800130EE
0x1800130e1  mov     r8d, esi; Size
0x1800130e4  xor     edx, edx; Val
0x1800130e6  mov     rcx, rax; void *
0x1800130e9  call    memset_0
0x1800130ee  mov     [rdi+288h], rbx
0x1800130f5  test    rbx, rbx
0x1800130f8  jz      short loc_18001311D
0x1800130fa  mov     ecx, dword ptr [rsp+28h+arg_0]; unsigned __int64
0x1800130fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013105  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001310a  mov     [rdi+290h], rax
0x180013111  neg     rax
0x180013114  sbb     eax, eax
0x180013116  not     eax
0x180013118  and     eax, 8
0x18001311b  jmp     short loc_180013122
0x18001311d  mov     eax, 8
0x180013122  mov     rbx, [rsp+28h+arg_10]
0x180013127  mov     rsi, [rsp+28h+arg_18]
0x18001312c  add     rsp, 20h
0x180013130  pop     rdi
0x180013131  retn
```

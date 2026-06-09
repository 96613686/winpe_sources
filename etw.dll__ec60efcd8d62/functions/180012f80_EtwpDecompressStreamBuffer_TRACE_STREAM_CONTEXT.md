# EtwpDecompressStreamBuffer(_TRACE_STREAM_CONTEXT *)

- ea: `0x180012f80`
- end: `0x18001307c`
- name: `?EtwpDecompressStreamBuffer@@YAEPEAU_TRACE_STREAM_CONTEXT@@@Z`
- size: `252`
- prototype: `unsigned __int8 __fastcall(struct _TRACE_STREAM_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010ed8`

## callees

- `0x180001ee2`
- `0x180012f80`

## import_xrefs

- `ntdll!RtlDecompressBufferEx` at `0x180012ffc`
- `ntdll!RtlDecompressBufferEx` at `0x180012ffc`

## pseudocode

```c
unsigned __int8 __fastcall EtwpDecompressStreamBuffer(struct _TRACE_STREAM_CONTEXT *a1)
{
  __int64 v1; // rbx
  __int64 v3; // rdi
  int v4; // ebp
  unsigned int v5; // r8d
  NTSTATUS v6; // eax
  __int64 v7; // rax
  unsigned int v9; // [rsp+70h] [rbp+8h] BYREF

  v1 = *((_QWORD *)a1 + 9);
  v3 = *((_QWORD *)a1 + 8);
  v9 = 0;
  v4 = *(_DWORD *)(v3 + 768);
  if ( (*(_BYTE *)(v1 + 52) & 0x40) == 0 )
    goto LABEL_7;
  v5 = *(_DWORD *)(v1 + 48);
  if ( v5 >= 0x48 && *(_DWORD *)v1 >= 0x48u )
  {
    v6 = RtlDecompressBufferEx(
           *(unsigned __int16 *)(v3 + 554),
           *(_QWORD *)(v3 + 648) + 72LL,
           v5 - 72,
           v1 + 72,
           *(_DWORD *)v1 - 72,
           &v9,
           *(_QWORD *)(v3 + 656));
    if ( !RtlNtStatusToDosError_0(v6) )
    {
      *(_WORD *)(v1 + 52) &= ~0x40u;
      if ( *(_DWORD *)(v1 + 48) == v9 + 72LL )
      {
        v7 = *(_QWORD *)(v3 + 648);
        *(_OWORD *)v7 = *(_OWORD *)v1;
        *(_OWORD *)(v7 + 16) = *(_OWORD *)(v1 + 16);
        *(_OWORD *)(v7 + 32) = *(_OWORD *)(v1 + 32);
        *(_OWORD *)(v7 + 48) = *(_OWORD *)(v1 + 48);
        *(_QWORD *)(v7 + 64) = *(_QWORD *)(v1 + 64);
        v1 = *(_QWORD *)(v3 + 648);
        *(_QWORD *)(v3 + 648) = *((_QWORD *)a1 + 9);
        *((_QWORD *)a1 + 9) = v1;
LABEL_7:
        *(_DWORD *)v1 = v4;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012f80  push    rbx
0x180012f82  push    rbp
0x180012f83  push    rsi
0x180012f84  push    rdi
0x180012f85  sub     rsp, 48h
0x180012f89  mov     rbx, [rcx+48h]
0x180012f8d  mov     rsi, rcx
0x180012f90  mov     rdi, [rcx+40h]
0x180012f94  mov     [rsp+68h+arg_0], 0
0x180012f9c  test    byte ptr [rbx+34h], 40h
0x180012fa0  mov     ebp, [rdi+300h]
0x180012fa6  jz      loc_18001306B
0x180012fac  mov     r8d, [rbx+30h]
0x180012fb0  cmp     r8d, 48h ; 'H'
0x180012fb4  jb      loc_180013078
0x180012fba  mov     ecx, [rbx]
0x180012fbc  cmp     ecx, 48h ; 'H'
0x180012fbf  jb      loc_180013078
0x180012fc5  mov     rax, [rdi+290h]
0x180012fcc  lea     r9, [rbx+48h]
0x180012fd0  mov     rdx, [rdi+288h]
0x180012fd7  add     ecx, 0FFFFFFB8h
0x180012fda  mov     [rsp+68h+var_38], rax
0x180012fdf  add     r8d, 0FFFFFFB8h
0x180012fe3  lea     rax, [rsp+68h+arg_0]
0x180012fe8  add     rdx, 48h ; 'H'
0x180012fec  mov     [rsp+68h+var_40], rax
0x180012ff1  mov     [rsp+68h+var_48], ecx
0x180012ff5  movzx   ecx, word ptr [rdi+22Ah]
0x180012ffc  call    cs:__imp_RtlDecompressBufferEx
0x180013002  mov     ecx, eax; Status
0x180013004  call    RtlNtStatusToDosError_0
0x180013009  test    eax, eax
0x18001300b  jnz     short loc_180013078
0x18001300d  mov     eax, 0FFBFh
0x180013012  and     [rbx+34h], ax
0x180013016  mov     ecx, [rsp+68h+arg_0]
0x18001301a  mov     eax, [rbx+30h]
0x18001301d  add     rcx, 48h ; 'H'
0x180013021  cmp     rax, rcx
0x180013024  jnz     short loc_180013078
0x180013026  movups  xmm0, xmmword ptr [rbx]
0x180013029  mov     rax, [rdi+288h]
0x180013030  movups  xmmword ptr [rax], xmm0
0x180013033  movups  xmm1, xmmword ptr [rbx+10h]
0x180013037  movups  xmmword ptr [rax+10h], xmm1
0x18001303b  movups  xmm0, xmmword ptr [rbx+20h]
0x18001303f  movups  xmmword ptr [rax+20h], xmm0
0x180013043  movups  xmm1, xmmword ptr [rbx+30h]
0x180013047  movups  xmmword ptr [rax+30h], xmm1
0x18001304b  movsd   xmm0, qword ptr [rbx+40h]
0x180013050  movsd   qword ptr [rax+40h], xmm0
0x180013055  mov     rax, [rsi+48h]
0x180013059  mov     rbx, [rdi+288h]
0x180013060  mov     [rdi+288h], rax
0x180013067  mov     [rsi+48h], rbx
0x18001306b  mov     [rbx], ebp
0x18001306d  mov     al, 1
0x18001306f  add     rsp, 48h
0x180013073  pop     rdi
0x180013074  pop     rsi
0x180013075  pop     rbp
0x180013076  pop     rbx
0x180013077  retn
0x180013078  xor     al, al
0x18001307a  jmp     short loc_18001306F
```

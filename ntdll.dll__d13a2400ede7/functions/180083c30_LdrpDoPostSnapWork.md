# LdrpDoPostSnapWork

- ea: `0x180083c30`
- end: `0x180083d1c`
- name: `LdrpDoPostSnapWork`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800b6f08`

## callees

- `0x18001eb80`
- `0x180083bf0`
- `0x180083c30`
- `0x180083d30`
- `0x1800eac88`
- `0x18015f4e0`

## string_xrefs

- `0x180083d04`: `LdrpDoPostSnapWork:Unable to unsuppress the export suppressed functions that are imported in the DLL based at 0x%p.Status = 0x%x\n`

## pseudocode

```c
__int64 __fastcall LdrpDoPostSnapWork(__int64 a1)
{
  __int64 v1; // rsi
  int v2; // ebx
  __int64 result; // rax
  _QWORD *v5; // rax
  int v6; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v2 = 0;
  v6 = 0;
  if ( !*(_QWORD *)(a1 + 112)
    || (result = ZwProtectVirtualMemory(-1, a1 + 112, a1 + 120, *(unsigned int *)(a1 + 144), &v6),
        v2 = result,
        (int)result >= 0) )
  {
    v5 = *(_QWORD **)(a1 + 160);
    if ( v5 && *v5 != *(_QWORD *)(a1 + 152) )
      __fastfail(0x13u);
    if ( *(_WORD *)(v1 + 110) || (result = LdrpHandleTlsData(v1), v2 = result, (int)result >= 0) )
    {
      if ( (unsigned int)LdrControlFlowGuardEnforcedWithExportSuppression() )
      {
        v2 = LdrpUnsuppressAddressTakenIat(*(_QWORD *)(v1 + 48), 0, 0);
        if ( v2 < 0 )
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrsnap.c",
            590,
            (int)"LdrpDoPostSnapWork",
            0,
            "LdrpDoPostSnapWork:Unable to unsuppress the export suppressed functions that are imported in the DLL based a"
            "t 0x%p.Status = 0x%x\n",
            *(_QWORD *)(v1 + 48));
      }
      return (unsigned int)v2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180083c30  mov     [rsp+arg_8], rbx
0x180083c35  mov     [rsp+arg_10], rsi
0x180083c3a  push    rdi
0x180083c3b  sub     rsp, 40h
0x180083c3f  mov     rsi, [rcx+38h]
0x180083c43  lea     rdx, [rcx+70h]
0x180083c47  xor     ebx, ebx
0x180083c49  mov     [rsp+48h+arg_0], 0
0x180083c51  mov     rdi, rcx
0x180083c54  cmp     [rdx], rbx
0x180083c57  jz      short loc_180083C80
0x180083c59  mov     r9d, [rcx+90h]
0x180083c60  lea     r8, [rcx+78h]
0x180083c64  lea     rax, [rsp+48h+arg_0]
0x180083c69  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180083c70  mov     [rsp+48h+Format], rax
0x180083c75  call    ZwProtectVirtualMemory
0x180083c7a  mov     ebx, eax
0x180083c7c  test    eax, eax
0x180083c7e  js      short loc_180083CAA
0x180083c80  mov     rax, [rdi+0A0h]
0x180083c87  test    rax, rax
0x180083c8a  jz      short loc_180083CBB
0x180083c8c  mov     rax, [rax]
0x180083c8f  cmp     rax, [rdi+98h]
0x180083c96  jz      short loc_180083CBB
0x180083c98  mov     ecx, 13h
0x180083c9d  int     29h; Win8: RtlFailFast(ecx)
0x180083c9f  call    LdrControlFlowGuardEnforcedWithExportSuppression
0x180083ca4  test    eax, eax
0x180083ca6  jnz     short loc_180083CD2
0x180083ca8  mov     eax, ebx
0x180083caa  mov     rbx, [rsp+48h+arg_8]
0x180083caf  mov     rsi, [rsp+48h+arg_10]
0x180083cb4  add     rsp, 40h
0x180083cb8  pop     rdi
0x180083cb9  retn
0x180083cbb  cmp     word ptr [rsi+6Eh], 0
0x180083cc0  jnz     short loc_180083C9F
0x180083cc2  mov     rcx, rsi
0x180083cc5  call    LdrpHandleTlsData
0x180083cca  mov     ebx, eax
0x180083ccc  test    eax, eax
0x180083cce  jns     short loc_180083C9F
0x180083cd0  jmp     short loc_180083CAA
0x180083cd2  mov     rcx, [rsi+30h]
0x180083cd6  xor     r8d, r8d
0x180083cd9  xor     edx, edx
0x180083cdb  call    LdrpUnsuppressAddressTakenIat
0x180083ce0  mov     ebx, eax
0x180083ce2  test    eax, eax
0x180083ce4  jns     short loc_180083CA8
0x180083ce6  mov     [rsp+48h+var_18], eax
0x180083cea  lea     r8, aLdrpdopostsnap_0; "LdrpDoPostSnapWork"
0x180083cf1  mov     rax, [rsi+30h]
0x180083cf5  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x180083cfc  mov     qword ptr [rsp+48h+ArgList], rax; ArgList
0x180083d01  xor     r9d, r9d; int
0x180083d04  lea     rax, aLdrpdopostsnap; "LdrpDoPostSnapWork:Unable to unsuppress"...
0x180083d0b  mov     edx, 24Eh; int
0x180083d10  mov     [rsp+48h+Format], rax; Format
0x180083d15  call    LdrpLogInternal
0x180083d1a  jmp     short loc_180083CA8
```

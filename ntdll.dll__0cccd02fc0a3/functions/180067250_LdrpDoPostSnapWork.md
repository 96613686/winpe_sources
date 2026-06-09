# LdrpDoPostSnapWork

- ea: `0x180067250`
- end: `0x18006733c`
- name: `LdrpDoPostSnapWork`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800ac3d0`

## callees

- `0x18001eb80`
- `0x180067210`
- `0x180067250`
- `0x180067350`
- `0x1800ea628`
- `0x18015ecd0`

## string_xrefs

- `0x180067324`: `LdrpDoPostSnapWork:Unable to unsuppress the export suppressed functions that are imported in the DLL based at 0x%p.Status = 0x%x\n`

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
0x180067250  mov     [rsp+arg_8], rbx
0x180067255  mov     [rsp+arg_10], rsi
0x18006725a  push    rdi
0x18006725b  sub     rsp, 40h
0x18006725f  mov     rsi, [rcx+38h]
0x180067263  lea     rdx, [rcx+70h]
0x180067267  xor     ebx, ebx
0x180067269  mov     [rsp+48h+arg_0], 0
0x180067271  mov     rdi, rcx
0x180067274  cmp     [rdx], rbx
0x180067277  jz      short loc_1800672A0
0x180067279  mov     r9d, [rcx+90h]
0x180067280  lea     r8, [rcx+78h]
0x180067284  lea     rax, [rsp+48h+arg_0]
0x180067289  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180067290  mov     [rsp+48h+Format], rax
0x180067295  call    ZwProtectVirtualMemory
0x18006729a  mov     ebx, eax
0x18006729c  test    eax, eax
0x18006729e  js      short loc_1800672CA
0x1800672a0  mov     rax, [rdi+0A0h]
0x1800672a7  test    rax, rax
0x1800672aa  jz      short loc_1800672DB
0x1800672ac  mov     rax, [rax]
0x1800672af  cmp     rax, [rdi+98h]
0x1800672b6  jz      short loc_1800672DB
0x1800672b8  mov     ecx, 13h
0x1800672bd  int     29h; Win8: RtlFailFast(ecx)
0x1800672bf  call    LdrControlFlowGuardEnforcedWithExportSuppression
0x1800672c4  test    eax, eax
0x1800672c6  jnz     short loc_1800672F2
0x1800672c8  mov     eax, ebx
0x1800672ca  mov     rbx, [rsp+48h+arg_8]
0x1800672cf  mov     rsi, [rsp+48h+arg_10]
0x1800672d4  add     rsp, 40h
0x1800672d8  pop     rdi
0x1800672d9  retn
0x1800672db  cmp     word ptr [rsi+6Eh], 0
0x1800672e0  jnz     short loc_1800672BF
0x1800672e2  mov     rcx, rsi
0x1800672e5  call    LdrpHandleTlsData
0x1800672ea  mov     ebx, eax
0x1800672ec  test    eax, eax
0x1800672ee  jns     short loc_1800672BF
0x1800672f0  jmp     short loc_1800672CA
0x1800672f2  mov     rcx, [rsi+30h]
0x1800672f6  xor     r8d, r8d
0x1800672f9  xor     edx, edx
0x1800672fb  call    LdrpUnsuppressAddressTakenIat
0x180067300  mov     ebx, eax
0x180067302  test    eax, eax
0x180067304  jns     short loc_1800672C8
0x180067306  mov     [rsp+48h+var_18], eax
0x18006730a  lea     r8, aLdrpdopostsnap_0; "LdrpDoPostSnapWork"
0x180067311  mov     rax, [rsi+30h]
0x180067315  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x18006731c  mov     qword ptr [rsp+48h+ArgList], rax; ArgList
0x180067321  xor     r9d, r9d; int
0x180067324  lea     rax, aLdrpdopostsnap; "LdrpDoPostSnapWork:Unable to unsuppress"...
0x18006732b  mov     edx, 24Eh; int
0x180067330  mov     [rsp+48h+Format], rax; Format
0x180067335  call    LdrpLogInternal
0x18006733a  jmp     short loc_1800672C8
```

# LdrpPrepareModuleForExecution

- ea: `0x180025fb4`
- end: `0x180026105`
- name: `LdrpPrepareModuleForExecution`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024990`
- `0x180050718`

## callees

- `0x18001eb80`
- `0x180025f78`
- `0x180025fb4`
- `0x1800694f0`
- `0x180069950`
- `0x1800e1a08`
- `0x1800e634c`
- `0x180104ca4`
- `0x180105f20`

## string_xrefs

- `0x180026090`: `Failed to load for appcompat reasons\n`

## pseudocode

```c
__int64 __fastcall LdrpPrepareModuleForExecution(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  char v9; // [rsp+28h] [rbp-10h]
  char v10; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  if ( (void *)qword_1801C4930 == NtCurrentTeb()->ClientId.UniqueThread )
    return v2;
  switch ( *(_DWORD *)(*(_QWORD *)(a1 + 152) + 56LL) )
  {
    case 5:
      LdrpCondenseGraph(*(_QWORD *)(a1 + 152));
LABEL_4:
      if ( (*(_DWORD *)(a1 + 104) & 0x20) == 0 && (unsigned int)NtCurrentTeb()->SubProcessTag )
        LdrpAddNodeServiceTag(*(_QWORD *)(a1 + 152));
      v2 = LdrpNotifyLoadOfGraph(*(_QWORD *)(a1 + 152));
      if ( (v2 & 0x80000000) != 0 )
        return v2;
      v2 = LdrpDynamicShimModule(*(_QWORD *)(a1 + 152));
      if ( (v2 & 0x80000000) != 0 )
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrsnap.c",
          2644,
          (int)"LdrpPrepareModuleForExecution",
          1,
          "Failed to load for appcompat reasons\n",
          v9);
        return v2;
      }
LABEL_10:
      v6 = *(_QWORD *)(a1 + 176);
      if ( v6 && (*(_BYTE *)(v6 + 32) & 1) == 0 )
      {
        LdrpAcquireLoaderLock();
        v7 = *(_QWORD *)(a1 + 152);
        v10 = 0;
        v2 = LdrpInitializeGraphRecurse(v7, a2, &v10);
        LdrpReleaseLoaderLock(v8, 2, v2);
      }
      return v2;
    case 6:
      goto LABEL_4;
    case 7:
      goto LABEL_10;
  }
  if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 152) + 56LL) - 8) >= 2 )
    return (unsigned int)-1073741595;
  return v2;
}

```

## disassembly

```asm
0x180025fb4  mov     [rsp+arg_0], rbx
0x180025fb9  mov     [rsp+arg_8], rsi
0x180025fbe  push    rdi
0x180025fbf  sub     rsp, 30h
0x180025fc3  mov     rax, gs:30h
0x180025fcc  xor     ebx, ebx
0x180025fce  mov     rsi, rdx
0x180025fd1  mov     rdi, rcx
0x180025fd4  mov     r8, [rax+48h]
0x180025fd8  cmp     cs:qword_1801C4930, r8
0x180025fdf  jz      short loc_18002602A
0x180025fe1  mov     rax, [rcx+98h]
0x180025fe8  mov     r8d, [rax+38h]
0x180025fec  sub     r8d, 5
0x180025ff0  jz      loc_1800260F4
0x180025ff6  sub     r8d, 1
0x180025ffa  jnz     loc_1800260BF
0x180026000  mov     eax, [rdi+68h]
0x180026003  test    al, 20h
0x180026005  jnz     short loc_180026018
0x180026007  mov     rdx, gs:1720h
0x180026010  test    edx, edx
0x180026012  jnz     loc_1800260E3
0x180026018  mov     rcx, [rdi+98h]
0x18002601f  call    LdrpNotifyLoadOfGraph
0x180026024  mov     ebx, eax
0x180026026  test    eax, eax
0x180026028  jns     short loc_18002603D
0x18002602a  mov     rsi, [rsp+38h+arg_8]
0x18002602f  mov     eax, ebx
0x180026031  mov     rbx, [rsp+38h+arg_0]
0x180026036  add     rsp, 30h
0x18002603a  pop     rdi
0x18002603b  retn
0x18002603d  mov     rcx, [rdi+98h]
0x180026044  call    LdrpDynamicShimModule
0x180026049  mov     ebx, eax
0x18002604b  test    eax, eax
0x18002604d  js      short loc_180026090
0x18002604f  mov     rax, [rdi+0B0h]
0x180026056  test    rax, rax
0x180026059  jz      short loc_18002602A
0x18002605b  test    byte ptr [rax+20h], 1
0x18002605f  jnz     short loc_18002602A
0x180026061  call    LdrpAcquireLoaderLock
0x180026066  mov     rcx, [rdi+98h]
0x18002606d  lea     r8, [rsp+38h+arg_10]
0x180026072  mov     rdx, rsi
0x180026075  mov     [rsp+38h+arg_10], 0
0x18002607a  call    LdrpInitializeGraphRecurse
0x18002607f  mov     r8d, eax
0x180026082  mov     edx, 2
0x180026087  mov     ebx, eax
0x180026089  call    LdrpReleaseLoaderLock
0x18002608e  jmp     short loc_18002602A
0x180026090  lea     rax, aFailedToLoadFo; "Failed to load for appcompat reasons\n"
0x180026097  mov     r9d, 1; int
0x18002609d  lea     r8, aLdrppreparemod; "LdrpPrepareModuleForExecution"
0x1800260a4  mov     [rsp+38h+Format], rax; Format
0x1800260a9  mov     edx, 0A54h; int
0x1800260ae  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800260b5  call    LdrpLogInternal
0x1800260ba  jmp     loc_18002602A
0x1800260bf  sub     r8d, 1
0x1800260c3  jz      short loc_18002604F
0x1800260c5  sub     r8d, 1
0x1800260c9  jz      loc_18002602A
0x1800260cf  cmp     r8d, 1
0x1800260d3  jz      loc_18002602A
0x1800260d9  mov     ebx, 0C00000E5h
0x1800260de  jmp     loc_18002602A
0x1800260e3  mov     rcx, [rdi+98h]
0x1800260ea  call    LdrpAddNodeServiceTag
0x1800260ef  jmp     loc_180026018
0x1800260f4  mov     rcx, [rcx+98h]
0x1800260fb  call    LdrpCondenseGraph
0x180026100  jmp     loc_180026000
```

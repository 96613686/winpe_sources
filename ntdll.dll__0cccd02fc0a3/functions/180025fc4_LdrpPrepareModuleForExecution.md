# LdrpPrepareModuleForExecution

- ea: `0x180025fc4`
- end: `0x180026115`
- name: `LdrpPrepareModuleForExecution`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800249a0`
- `0x1800d6508`

## callees

- `0x18001eb80`
- `0x180025f88`
- `0x180025fc4`
- `0x18004c8f0`
- `0x18004cd50`
- `0x1800e13f8`
- `0x1800e5fcc`
- `0x180103f24`
- `0x1801050f0`

## string_xrefs

- `0x1800260a0`: `Failed to load for appcompat reasons\n`

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
  if ( (void *)qword_1801C4900 == NtCurrentTeb()->ClientId.UniqueThread )
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
0x180025fc4  mov     [rsp+arg_0], rbx
0x180025fc9  mov     [rsp+arg_8], rsi
0x180025fce  push    rdi
0x180025fcf  sub     rsp, 30h
0x180025fd3  mov     rax, gs:30h
0x180025fdc  xor     ebx, ebx
0x180025fde  mov     rsi, rdx
0x180025fe1  mov     rdi, rcx
0x180025fe4  mov     r8, [rax+48h]
0x180025fe8  cmp     cs:qword_1801C4900, r8
0x180025fef  jz      short loc_18002603A
0x180025ff1  mov     rax, [rcx+98h]
0x180025ff8  mov     r8d, [rax+38h]
0x180025ffc  sub     r8d, 5
0x180026000  jz      loc_180026104
0x180026006  sub     r8d, 1
0x18002600a  jnz     loc_1800260CF
0x180026010  mov     eax, [rdi+68h]
0x180026013  test    al, 20h
0x180026015  jnz     short loc_180026028
0x180026017  mov     rdx, gs:1720h
0x180026020  test    edx, edx
0x180026022  jnz     loc_1800260F3
0x180026028  mov     rcx, [rdi+98h]
0x18002602f  call    LdrpNotifyLoadOfGraph
0x180026034  mov     ebx, eax
0x180026036  test    eax, eax
0x180026038  jns     short loc_18002604D
0x18002603a  mov     rsi, [rsp+38h+arg_8]
0x18002603f  mov     eax, ebx
0x180026041  mov     rbx, [rsp+38h+arg_0]
0x180026046  add     rsp, 30h
0x18002604a  pop     rdi
0x18002604b  retn
0x18002604d  mov     rcx, [rdi+98h]
0x180026054  call    LdrpDynamicShimModule
0x180026059  mov     ebx, eax
0x18002605b  test    eax, eax
0x18002605d  js      short loc_1800260A0
0x18002605f  mov     rax, [rdi+0B0h]
0x180026066  test    rax, rax
0x180026069  jz      short loc_18002603A
0x18002606b  test    byte ptr [rax+20h], 1
0x18002606f  jnz     short loc_18002603A
0x180026071  call    LdrpAcquireLoaderLock
0x180026076  mov     rcx, [rdi+98h]
0x18002607d  lea     r8, [rsp+38h+arg_10]
0x180026082  mov     rdx, rsi
0x180026085  mov     [rsp+38h+arg_10], 0
0x18002608a  call    LdrpInitializeGraphRecurse
0x18002608f  mov     r8d, eax
0x180026092  mov     edx, 2
0x180026097  mov     ebx, eax
0x180026099  call    LdrpReleaseLoaderLock
0x18002609e  jmp     short loc_18002603A
0x1800260a0  lea     rax, aFailedToLoadFo; "Failed to load for appcompat reasons\n"
0x1800260a7  mov     r9d, 1; int
0x1800260ad  lea     r8, aLdrppreparemod; "LdrpPrepareModuleForExecution"
0x1800260b4  mov     [rsp+38h+Format], rax; Format
0x1800260b9  mov     edx, 0A54h; int
0x1800260be  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800260c5  call    LdrpLogInternal
0x1800260ca  jmp     loc_18002603A
0x1800260cf  sub     r8d, 1
0x1800260d3  jz      short loc_18002605F
0x1800260d5  sub     r8d, 1
0x1800260d9  jz      loc_18002603A
0x1800260df  cmp     r8d, 1
0x1800260e3  jz      loc_18002603A
0x1800260e9  mov     ebx, 0C00000E5h
0x1800260ee  jmp     loc_18002603A
0x1800260f3  mov     rcx, [rdi+98h]
0x1800260fa  call    LdrpAddNodeServiceTag
0x1800260ff  jmp     loc_180026028
0x180026104  mov     rcx, [rcx+98h]
0x18002610b  call    LdrpCondenseGraph
0x180026110  jmp     loc_180026010
```

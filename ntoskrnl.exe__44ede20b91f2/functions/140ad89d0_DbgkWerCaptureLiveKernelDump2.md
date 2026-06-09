# DbgkWerCaptureLiveKernelDump2

- ea: `0x140ad89d0`
- end: `0x140ad8c49`
- name: `DbgkWerCaptureLiveKernelDump2`
- size: `633`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140607d30`
- `0x140ad8950`

## callees

- `0x14020fe90`
- `0x140224f70`
- `0x1402f8270`
- `0x14074daac`
- `0x14074dd94`
- `0x14074ddb4`
- `0x140ad89d0`
- `0x140ad8c50`
- `0x140bae410`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x140ad8bc3`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x140ad8bc3`

## string_xrefs

- `0x140ad8bd7`: `DBGK: DbgkWerCaptureLiveKernelDump: WerLiveKernelCreateReport failed, status 0x%x.\n\n`

## pseudocode

```c
__int64 __fastcall DbgkWerCaptureLiveKernelDump2(
        _WORD *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  char v7; // di
  unsigned int v13; // ebx
  __int64 Pool2; // rsi
  __int64 v15; // rdx
  _WORD *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  _WORD *v19; // r8
  _WORD *v20; // rcx
  int v21; // eax
  int v22; // ecx
  unsigned int v23; // ecx
  int v24; // eax
  unsigned int v25; // eax
  char v26[4]; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v27; // [rsp+24h] [rbp-54h] BYREF
  _QWORD v28[10]; // [rsp+28h] [rbp-50h] BYREF

  v7 = 1;
  v26[0] = 1;
  v27 = 0;
  v28[0] = 0;
  if ( KeGetCurrentIrql() )
  {
    DbgPrintEx(5u, 1u, "DBGK: DbgkWerCaptureLiveKernelDump2: called at IRQL > PASSIVE_LEVEL\n");
    return 3221225800LL;
  }
  if ( !byte_140E4BD60 )
  {
    DbgPrintEx(5u, 1u, "DBGK: DbgkWerCaptureLiveKernelDump2: called before initialization.\n");
    return 3221225635LL;
  }
  if ( (unsigned __int8)sub_140AD8C50() )
  {
    DbgPrintEx(5u, 1u, "DBGK: Full Live Kernel Dumps are disabled. Failing request.\n");
    return 3221227524LL;
  }
  if ( !a7 )
  {
    DbgPrintEx(5u, 1u, "DBGK: DbgkWerCaptureLiveKernelDump2: Called without dump control.\n");
    return 3221225485LL;
  }
  KeEnterCriticalRegion();
  if ( _InterlockedExchange(&dword_140F85D94, 1) != 1 )
  {
    Pool2 = ExAllocatePool2(256, 176, 1466393156);
    if ( !Pool2 )
    {
      v13 = -1073741670;
LABEL_36:
      _InterlockedExchange(&dword_140F85D94, 0);
      goto LABEL_37;
    }
    if ( a1 )
    {
      v15 = 16;
      v16 = a1;
      v17 = 16;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v17;
      }
      while ( v17 );
      v13 = v17 == 0 ? 0xC000000D : 0;
      if ( !v17 )
        goto LABEL_35;
      v18 = 2147483646;
      v19 = (_WORD *)Pool2;
      do
      {
        if ( !v18 )
          break;
        if ( !*a1 )
          break;
        *v19++ = *a1++;
        --v18;
        --v15;
      }
      while ( v15 );
      v20 = v19 - 1;
      v13 = v15 == 0 ? 0x80000005 : 0;
      if ( v15 )
        v20 = v19;
      *v20 = 0;
      if ( v15 )
      {
        v21 = dword_140F85D98;
        if ( (*(_BYTE *)(a7 + 24) & 2) != 0 )
          v21 = 1;
        v27 = v21;
        v22 = *(_DWORD *)(Pool2 + 104);
        *(_QWORD *)(Pool2 + 56) = a5;
        v23 = v22 & 0xFFFFFFFD;
        *(_QWORD *)(Pool2 + 64) = a6;
        *(_DWORD *)(Pool2 + 32) = a2;
        *(_QWORD *)(Pool2 + 40) = a3;
        *(_QWORD *)(Pool2 + 48) = a4;
        *(_QWORD *)(Pool2 + 72) = a7;
        if ( (*(_DWORD *)(a7 + 24) & 8) == 0 )
          v23 |= 2u;
        *(_DWORD *)(Pool2 + 104) = v23;
        v28[0] = 0;
        v24 = WerLiveKernelCreateReport(Pool2, &v27, v28);
        v13 = v24;
        if ( v24 < 0 )
        {
          DbgPrintEx(
            5u,
            0,
            "DBGK: DbgkWerCaptureLiveKernelDump: WerLiveKernelCreateReport failed, status 0x%x.\n\n",
            v24);
LABEL_35:
          sub_14074DAAC(Pool2);
          sub_14074DD94(Pool2);
          goto LABEL_36;
        }
        v25 = sub_14074DDB4(Pool2, v27, v28[0], v26);
        v7 = v26[0];
        v13 = v25;
      }
      if ( !v7 )
        goto LABEL_37;
      goto LABEL_35;
    }
    v13 = -1073741811;
    goto LABEL_35;
  }
  v13 = -1073741267;
LABEL_37:
  KeLeaveCriticalRegion();
  return v13;
}

```

## disassembly

```asm
0x140ad89d0  push    rbx
0x140ad89d2  push    rbp
0x140ad89d3  push    rsi
0x140ad89d4  push    rdi
0x140ad89d5  push    r12
0x140ad89d7  push    r13
0x140ad89d9  push    r14
0x140ad89db  push    r15
0x140ad89dd  sub     rsp, 38h
0x140ad89e1  xor     ebx, ebx
0x140ad89e3  mov     edi, 1
0x140ad89e8  mov     [rsp+78h+var_58], dil
0x140ad89ed  mov     r15, r9
0x140ad89f0  mov     [rsp+78h+var_54], ebx
0x140ad89f4  mov     r12, r8
0x140ad89f7  mov     [rsp+78h+var_50], rbx
0x140ad89fc  mov     r13d, edx
0x140ad89ff  mov     r14, rcx
0x140ad8a02  mov     rax, cr8
0x140ad8a06  test    al, al
0x140ad8a08  jz      short loc_140AD8A25
0x140ad8a0a  lea     r8, aDbgkDbgkwercap; "DBGK: DbgkWerCaptureLiveKernelDump2: ca"...
0x140ad8a11  mov     edx, edi; Level
0x140ad8a13  lea     ecx, [rdi+4]; ComponentId
0x140ad8a16  call    DbgPrintEx
0x140ad8a1b  mov     eax, 0C0000148h
0x140ad8a20  jmp     loc_140AD8C37
0x140ad8a25  cmp     cs:byte_140E4BD60, bl
0x140ad8a2b  jnz     short loc_140AD8A4A
0x140ad8a2d  lea     r8, aDbgkDbgkwercap_0; "DBGK: DbgkWerCaptureLiveKernelDump2: ca"...
0x140ad8a34  mov     edx, edi; Level
0x140ad8a36  mov     ecx, 5; ComponentId
0x140ad8a3b  call    DbgPrintEx
0x140ad8a40  mov     eax, 0C00000A3h
0x140ad8a45  jmp     loc_140AD8C37
0x140ad8a4a  call    sub_140AD8C50
0x140ad8a4f  test    al, al
0x140ad8a51  jz      short loc_140AD8A70
0x140ad8a53  lea     r8, aDbgkFullLiveKe_0; "DBGK: Full Live Kernel Dumps are disabl"...
0x140ad8a5a  mov     edx, edi; Level
0x140ad8a5c  mov     ecx, 5; ComponentId
0x140ad8a61  call    DbgPrintEx
0x140ad8a66  mov     eax, 0C0000804h
0x140ad8a6b  jmp     loc_140AD8C37
0x140ad8a70  mov     rbp, [rsp+78h+arg_30]
0x140ad8a78  test    rbp, rbp
0x140ad8a7b  jnz     short loc_140AD8A98
0x140ad8a7d  lea     r8, aDbgkDbgkwercap_1; "DBGK: DbgkWerCaptureLiveKernelDump2: Ca"...
0x140ad8a84  mov     edx, edi; Level
0x140ad8a86  lea     ecx, [rbp+5]; ComponentId
0x140ad8a89  call    DbgPrintEx
0x140ad8a8e  mov     eax, 0C000000Dh
0x140ad8a93  jmp     loc_140AD8C37
0x140ad8a98  call    KeEnterCriticalRegion
0x140ad8a9d  mov     eax, edi
0x140ad8a9f  xchg    eax, cs:dword_140F85D94
0x140ad8aa5  cmp     eax, edi
0x140ad8aa7  jnz     short loc_140AD8AB3
0x140ad8aa9  mov     ebx, 0C000022Dh
0x140ad8aae  jmp     loc_140AD8C30
0x140ad8ab3  mov     edx, 0B0h
0x140ad8ab8  mov     r8d, 57676244h
0x140ad8abe  lea     ecx, [rdx+50h]
0x140ad8ac1  call    ExAllocatePool2
0x140ad8ac6  xor     r9d, r9d
0x140ad8ac9  mov     rsi, rax
0x140ad8acc  test    rax, rax
0x140ad8acf  jnz     short loc_140AD8ADB
0x140ad8ad1  mov     ebx, 0C000009Ah
0x140ad8ad6  jmp     loc_140AD8C27
0x140ad8adb  test    r14, r14
0x140ad8ade  jz      loc_140AD8C0F
0x140ad8ae4  mov     edx, 10h
0x140ad8ae9  mov     rax, r14
0x140ad8aec  mov     ecx, edx
0x140ad8aee  cmp     [rax], r9w
0x140ad8af2  jz      short loc_140AD8AFD
0x140ad8af4  add     rax, 2
0x140ad8af8  sub     rcx, rdi
0x140ad8afb  jnz     short loc_140AD8AEE
0x140ad8afd  mov     rax, rcx
0x140ad8b00  neg     rax
0x140ad8b03  sbb     ebx, ebx
0x140ad8b05  not     ebx
0x140ad8b07  and     ebx, 0C000000Dh
0x140ad8b0d  test    rcx, rcx
0x140ad8b10  jz      loc_140AD8C14
0x140ad8b16  mov     eax, 7FFFFFFEh
0x140ad8b1b  mov     r8, rsi
0x140ad8b1e  test    rax, rax
0x140ad8b21  jz      short loc_140AD8B40
0x140ad8b23  movzx   ecx, word ptr [r14]
0x140ad8b27  test    cx, cx
0x140ad8b2a  jz      short loc_140AD8B40
0x140ad8b2c  mov     [r8], cx
0x140ad8b30  add     r14, 2
0x140ad8b34  add     r8, 2
0x140ad8b38  sub     rax, rdi
0x140ad8b3b  sub     rdx, rdi
0x140ad8b3e  jnz     short loc_140AD8B1E
0x140ad8b40  mov     rax, rdx
0x140ad8b43  lea     rcx, [r8-2]
0x140ad8b47  neg     rax
0x140ad8b4a  sbb     ebx, ebx
0x140ad8b4c  not     ebx
0x140ad8b4e  and     ebx, 80000005h
0x140ad8b54  test    rdx, rdx
0x140ad8b57  cmovnz  rcx, r8
0x140ad8b5b  mov     [rcx], r9w
0x140ad8b5f  jz      loc_140AD8C08
0x140ad8b65  test    byte ptr [rbp+18h], 2
0x140ad8b69  mov     eax, cs:dword_140F85D98
0x140ad8b6f  cmovnz  eax, edi
0x140ad8b72  mov     [rsp+78h+var_54], eax
0x140ad8b76  mov     rax, [rsp+78h+arg_20]
0x140ad8b7e  mov     ecx, [rsi+68h]
0x140ad8b81  mov     [rsi+38h], rax
0x140ad8b85  and     ecx, 0FFFFFFFDh
0x140ad8b88  mov     rax, [rsp+78h+arg_28]
0x140ad8b90  mov     [rsi+40h], rax
0x140ad8b94  mov     [rsi+20h], r13d
0x140ad8b98  mov     [rsi+28h], r12
0x140ad8b9c  mov     [rsi+30h], r15
0x140ad8ba0  mov     [rsi+48h], rbp
0x140ad8ba4  mov     eax, [rbp+18h]
0x140ad8ba7  test    al, 8
0x140ad8ba9  jnz     short loc_140AD8BAE
0x140ad8bab  or      ecx, 2
0x140ad8bae  mov     [rsi+68h], ecx
0x140ad8bb1  lea     r8, [rsp+78h+var_50]
0x140ad8bb6  mov     rcx, rsi
0x140ad8bb9  mov     [rsp+78h+var_50], r9
0x140ad8bbe  lea     rdx, [rsp+78h+var_54]
0x140ad8bc3  call    cs:WerLiveKernelCreateReport
0x140ad8bca  nop     dword ptr [rax+rax+00h]
0x140ad8bcf  mov     ebx, eax
0x140ad8bd1  test    eax, eax
0x140ad8bd3  jns     short loc_140AD8BEB
0x140ad8bd5  xor     edx, edx; Level
0x140ad8bd7  lea     r8, aDbgkDbgkwercap_2; "DBGK: DbgkWerCaptureLiveKernelDump: Wer"...
0x140ad8bde  mov     r9d, eax
0x140ad8be1  lea     ecx, [rdx+5]; ComponentId
0x140ad8be4  call    DbgPrintEx
0x140ad8be9  jmp     short loc_140AD8C14
0x140ad8beb  mov     r8, [rsp+78h+var_50]
0x140ad8bf0  lea     r9, [rsp+78h+var_58]
0x140ad8bf5  mov     edx, [rsp+78h+var_54]
0x140ad8bf9  mov     rcx, rsi
0x140ad8bfc  call    sub_14074DDB4
0x140ad8c01  mov     dil, [rsp+78h+var_58]
0x140ad8c06  mov     ebx, eax
0x140ad8c08  test    dil, dil
0x140ad8c0b  jnz     short loc_140AD8C14
0x140ad8c0d  jmp     short loc_140AD8C30
0x140ad8c0f  mov     ebx, 0C000000Dh
0x140ad8c14  mov     rcx, rsi
0x140ad8c17  call    sub_14074DAAC
0x140ad8c1c  mov     rcx, rsi
0x140ad8c1f  call    sub_14074DD94
0x140ad8c24  xor     r9d, r9d
0x140ad8c27  mov     eax, r9d
0x140ad8c2a  xchg    eax, cs:dword_140F85D94
0x140ad8c30  call    KeLeaveCriticalRegion
0x140ad8c35  mov     eax, ebx
0x140ad8c37  add     rsp, 38h
0x140ad8c3b  pop     r15
0x140ad8c3d  pop     r14
0x140ad8c3f  pop     r13
0x140ad8c41  pop     r12
0x140ad8c43  pop     rdi
0x140ad8c44  pop     rsi
0x140ad8c45  pop     rbp
0x140ad8c46  pop     rbx
0x140ad8c47  retn
```

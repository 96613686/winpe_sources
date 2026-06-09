# CcRegistryChangeCallback

- ea: `0x1404c3200`
- end: `0x1404c33bb`
- name: `CcRegistryChangeCallback`
- size: `443`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14020fe90`
- `0x1404c3200`
- `0x1405b76fc`
- `0x1406daa70`
- `0x1406dccf0`
- `0x1406e8590`
- `0x140bae8e0`

## string_xrefs

- `0x1404c3224`: `CcRegistryChangeCallback: Something of interest changed (callback:%c), under:"%wZ"\n`
- `0x1404c32f8`: `CcRegistryChangeCallback: Watch queued "%wZ"\n`
- `0x1404c337e`: `CcRegistryChangeCallback: Failed Watch request, status=0x%08x "%wZ"\n`
- `0x1404c326e`: `CcRegistryChangeCallback: Processed "%wZ", TickDiff=%I64d\n`
- `0x1404c3340`: `CcRegistryChangeCallback: Failed to open Key, status=0x%08x "%wZ\n`
- `0x14071b718`: `CcRegistryChangeCallback: Watch queued "%wZ" (for Immediate Processing)\n`

## pseudocode

```c
void __fastcall CcRegistryChangeCallback(_QWORD *P)
{
  char *v1; // rdi
  _QWORD *v2; // rbx
  __int64 v3; // rsi
  __int64 v4; // rbp
  __int64 v5; // rdx
  __int64 v6; // r8
  void *v7; // rcx
  NTSTATUS v8; // edi
  int v9; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF

  v1 = (char *)(P + 7);
  IoStatusBlock = 0;
  v2 = P;
  v3 = MEMORY[0xFFFFF78000000320];
  v4 = P[6];
  DbgPrintEx(
    0x7Fu,
    2u,
    "CcRegistryChangeCallback: Something of interest changed (callback:%c), under:\"%wZ\"\n",
    *((_BYTE *)P + 72) != 0 ? 70 : 84,
    P + 7);
  if ( !*((_BYTE *)v2 + 72) )
  {
    guard_dispatch_icall_no_overrides(v2, v5, v6);
    v2[6] = v3;
    DbgPrintEx(0x7Fu, 2u, "CcRegistryChangeCallback: Processed \"%wZ\", TickDiff=%I64d\n", v1, v3 - v4);
  }
  *((_BYTE *)v2 + 72) = 0;
  if ( v2[4] || (v9 = CcOpenRegistryPath(v1, v2 + 4), v9 >= 0) )
  {
    if ( v2 )
    {
      v7 = (void *)v2[4];
      if ( v7 )
      {
        v8 = ZwNotifyChangeKey(v7, 0, (PIO_APC_ROUTINE)v2, (PVOID)1, &IoStatusBlock, 5u, 1u, 0, 0, 1u);
        if ( v8 == 259 )
        {
          DbgPrintEx(0x7Fu, 2u, "CcRegistryChangeCallback: Watch queued \"%wZ\"\n", v2 + 7);
        }
        else if ( v8 >= 0 )
        {
          DbgPrintEx(0x7Fu, 2u, "CcRegistryChangeCallback: Watch queued \"%wZ\" (for Immediate Processing)\n", v2 + 7);
        }
        else
        {
          ZwClose((HANDLE)v2[4]);
          v2[4] = 0;
          *((_BYTE *)v2 + 72) = 1;
          DbgPrintEx(
            0x7Fu,
            0,
            "CcRegistryChangeCallback: Failed Watch request, status=0x%08x \"%wZ\"\n",
            (unsigned int)v8,
            v2 + 7);
        }
      }
    }
  }
  else
  {
    DbgPrintEx(0x7Fu, 0, "CcRegistryChangeCallback: Failed to open Key, status=0x%08x \"%wZ\n", (unsigned int)v9, v1);
    ExFreePoolWithTag(v2, 0x52576343u);
    v2 = 0;
  }
  if ( !CcRegistryWatchInitComplete && v2 && !*((_BYTE *)v2 + 72) )
    CcRegistryWatchInitComplete = 1;
}

```

## disassembly

```asm
0x1404c3200  push    rbx
0x1404c3202  push    rbp
0x1404c3203  push    rsi
0x1404c3204  push    rdi
0x1404c3205  push    r15
0x1404c3207  sub     rsp, 60h
0x1404c320b  lea     rdi, [rcx+38h]
0x1404c320f  xorps   xmm0, xmm0
0x1404c3212  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x1404c3217  mov     edx, 2; Level
0x1404c321c  mov     [rsp+88h+IoStatusBlock], rdi
0x1404c3221  mov     rbx, rcx
0x1404c3224  lea     r8, aCcregistrychan_2; "CcRegistryChangeCallback: Something of "...
0x1404c322b  mov     rsi, 0FFFFF78000000320h
0x1404c3235  lea     r15d, [rdx+7Dh]
0x1404c3239  mov     rsi, [rsi]
0x1404c323c  mov     al, [rcx+48h]
0x1404c323f  mov     rbp, [rcx+30h]
0x1404c3243  neg     al
0x1404c3245  mov     ecx, r15d; ComponentId
0x1404c3248  sbb     r9d, r9d
0x1404c324b  and     r9d, 0FFFFFFF2h
0x1404c324f  add     r9d, 54h ; 'T'
0x1404c3253  call    DbgPrintEx
0x1404c3258  cmp     byte ptr [rbx+48h], 0
0x1404c325c  jnz     short loc_1404C328C
0x1404c325e  mov     rax, [rbx+28h]
0x1404c3262  mov     rcx, rbx
0x1404c3265  call    _guard_dispatch_icall_no_overrides
0x1404c326a  mov     [rbx+30h], rsi
0x1404c326e  lea     r8, aCcregistrychan; "CcRegistryChangeCallback: Processed \"%"...
0x1404c3275  sub     rsi, rbp
0x1404c3278  lea     edx, [r15-7Dh]; Level
0x1404c327c  mov     r9, rdi
0x1404c327f  mov     [rsp+88h+IoStatusBlock], rsi
0x1404c3284  mov     ecx, r15d; ComponentId
0x1404c3287  call    DbgPrintEx
0x1404c328c  lea     rdx, [rbx+20h]
0x1404c3290  mov     byte ptr [rbx+48h], 0
0x1404c3294  cmp     qword ptr [rdx], 0
0x1404c3298  mov     ebp, 1
0x1404c329d  jz      loc_1404C3328
0x1404c32a3  test    rbx, rbx
0x1404c32a6  jz      short loc_1404C330F
0x1404c32a8  mov     rcx, [rbx+20h]; KeyHandle
0x1404c32ac  test    rcx, rcx
0x1404c32af  jz      short loc_1404C330F
0x1404c32b1  mov     [rsp+88h+Asynchronous], bpl; Asynchronous
0x1404c32b6  lea     rax, [rsp+88h+var_38]
0x1404c32bb  mov     [rsp+88h+BufferSize], 0; BufferSize
0x1404c32c3  mov     r9, rbp; ApcContext
0x1404c32c6  mov     [rsp+88h+Buffer], 0; Buffer
0x1404c32cf  mov     r8, rbx; ApcRoutine
0x1404c32d2  mov     [rsp+88h+WatchTree], bpl; WatchTree
0x1404c32d7  xor     edx, edx; Event
0x1404c32d9  mov     [rsp+88h+CompletionFilter], 5; CompletionFilter
0x1404c32e1  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x1404c32e6  call    ZwNotifyChangeKey
0x1404c32eb  lea     rsi, [rbx+38h]
0x1404c32ef  mov     edi, eax
0x1404c32f1  cmp     eax, 103h
0x1404c32f6  jnz     short loc_1404C3362
0x1404c32f8  lea     r8, aCcregistrychan_0; "CcRegistryChangeCallback: Watch queued "...
0x1404c32ff  mov     r9, rsi
0x1404c3302  mov     edx, 2; Level
0x1404c3307  mov     ecx, r15d; ComponentId
0x1404c330a  call    DbgPrintEx
0x1404c330f  cmp     cs:CcRegistryWatchInitComplete, 0
0x1404c3316  jz      loc_1404C339D
0x1404c331c  add     rsp, 60h
0x1404c3320  pop     r15
0x1404c3322  pop     rdi
0x1404c3323  pop     rsi
0x1404c3324  pop     rbp
0x1404c3325  pop     rbx
0x1404c3326  retn
0x1404c3328  mov     rcx, rdi
0x1404c332b  call    CcOpenRegistryPath
0x1404c3330  test    eax, eax
0x1404c3332  jns     loc_1404C32A3
0x1404c3338  mov     r9d, eax
0x1404c333b  mov     [rsp+88h+IoStatusBlock], rdi
0x1404c3340  lea     r8, aCcregistrychan_1; "CcRegistryChangeCallback: Failed to ope"...
0x1404c3347  xor     edx, edx; Level
0x1404c3349  mov     ecx, r15d; ComponentId
0x1404c334c  call    DbgPrintEx
0x1404c3351  mov     edx, 52576343h; Tag
0x1404c3356  mov     rcx, rbx; P
0x1404c3359  call    ExFreePoolWithTag
0x1404c335e  xor     ebx, ebx
0x1404c3360  jmp     short loc_1404C330F
0x1404c3362  test    edi, edi
0x1404c3364  jns     loc_14071B718
0x1404c336a  mov     rcx, [rbx+20h]; Handle
0x1404c336e  call    ZwClose
0x1404c3373  mov     r9d, edi
0x1404c3376  mov     qword ptr [rbx+20h], 0
0x1404c337e  lea     r8, aCcregistrychan_4; "CcRegistryChangeCallback: Failed Watch "...
0x1404c3385  mov     [rbx+48h], bpl
0x1404c3389  xor     edx, edx; Level
0x1404c338b  mov     [rsp+88h+IoStatusBlock], rsi
0x1404c3390  mov     ecx, r15d; ComponentId
0x1404c3393  call    DbgPrintEx
0x1404c3398  jmp     loc_1404C330F
0x1404c339d  test    rbx, rbx
0x1404c33a0  jz      loc_1404C331C
0x1404c33a6  cmp     byte ptr [rbx+48h], 0
0x1404c33aa  jnz     loc_1404C331C
0x1404c33b0  mov     cs:CcRegistryWatchInitComplete, ebp
0x1404c33b6  jmp     loc_1404C331C
0x14071b718  lea     r8, aCcregistrychan_3; "CcRegistryChangeCallback: Watch queued "...
0x14071b71f  jmp     loc_1404C32FF
```

# CcRegistryChangeCallback

- ea: `0x1404d2b80`
- end: `0x1404d2d3b`
- name: `CcRegistryChangeCallback`
- size: `443`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1402a2f90`
- `0x1404d2b80`
- `0x1405be3ec`
- `0x1406dd5c0`
- `0x1406df840`
- `0x1406eb0e0`
- `0x140bb19f0`

## string_xrefs

- `0x1404d2bee`: `CcRegistryChangeCallback: Processed "%wZ", TickDiff=%I64d\n`
- `0x1404d2cc0`: `CcRegistryChangeCallback: Failed to open Key, status=0x%08x "%wZ\n`
- `0x1404d2ba4`: `CcRegistryChangeCallback: Something of interest changed (callback:%c), under:"%wZ"\n`
- `0x14071f924`: `CcRegistryChangeCallback: Watch queued "%wZ" (for Immediate Processing)\n`
- `0x1404d2c78`: `CcRegistryChangeCallback: Watch queued "%wZ"\n`
- `0x1404d2cfe`: `CcRegistryChangeCallback: Failed Watch request, status=0x%08x "%wZ"\n`

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
0x1404d2b80  push    rbx
0x1404d2b82  push    rbp
0x1404d2b83  push    rsi
0x1404d2b84  push    rdi
0x1404d2b85  push    r15
0x1404d2b87  sub     rsp, 60h
0x1404d2b8b  lea     rdi, [rcx+38h]
0x1404d2b8f  xorps   xmm0, xmm0
0x1404d2b92  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x1404d2b97  mov     edx, 2; Level
0x1404d2b9c  mov     [rsp+88h+IoStatusBlock], rdi
0x1404d2ba1  mov     rbx, rcx
0x1404d2ba4  lea     r8, aCcregistrychan_2; "CcRegistryChangeCallback: Something of "...
0x1404d2bab  mov     rsi, 0FFFFF78000000320h
0x1404d2bb5  lea     r15d, [rdx+7Dh]
0x1404d2bb9  mov     rsi, [rsi]
0x1404d2bbc  mov     al, [rcx+48h]
0x1404d2bbf  mov     rbp, [rcx+30h]
0x1404d2bc3  neg     al
0x1404d2bc5  mov     ecx, r15d; ComponentId
0x1404d2bc8  sbb     r9d, r9d
0x1404d2bcb  and     r9d, 0FFFFFFF2h
0x1404d2bcf  add     r9d, 54h ; 'T'
0x1404d2bd3  call    DbgPrintEx
0x1404d2bd8  cmp     byte ptr [rbx+48h], 0
0x1404d2bdc  jnz     short loc_1404D2C0C
0x1404d2bde  mov     rax, [rbx+28h]
0x1404d2be2  mov     rcx, rbx
0x1404d2be5  call    _guard_dispatch_icall_no_overrides
0x1404d2bea  mov     [rbx+30h], rsi
0x1404d2bee  lea     r8, aCcregistrychan; "CcRegistryChangeCallback: Processed \"%"...
0x1404d2bf5  sub     rsi, rbp
0x1404d2bf8  lea     edx, [r15-7Dh]; Level
0x1404d2bfc  mov     r9, rdi
0x1404d2bff  mov     [rsp+88h+IoStatusBlock], rsi
0x1404d2c04  mov     ecx, r15d; ComponentId
0x1404d2c07  call    DbgPrintEx
0x1404d2c0c  lea     rdx, [rbx+20h]
0x1404d2c10  mov     byte ptr [rbx+48h], 0
0x1404d2c14  cmp     qword ptr [rdx], 0
0x1404d2c18  mov     ebp, 1
0x1404d2c1d  jz      loc_1404D2CA8
0x1404d2c23  test    rbx, rbx
0x1404d2c26  jz      short loc_1404D2C8F
0x1404d2c28  mov     rcx, [rbx+20h]; KeyHandle
0x1404d2c2c  test    rcx, rcx
0x1404d2c2f  jz      short loc_1404D2C8F
0x1404d2c31  mov     [rsp+88h+Asynchronous], bpl; Asynchronous
0x1404d2c36  lea     rax, [rsp+88h+var_38]
0x1404d2c3b  mov     [rsp+88h+BufferSize], 0; BufferSize
0x1404d2c43  mov     r9, rbp; ApcContext
0x1404d2c46  mov     [rsp+88h+Buffer], 0; Buffer
0x1404d2c4f  mov     r8, rbx; ApcRoutine
0x1404d2c52  mov     [rsp+88h+WatchTree], bpl; WatchTree
0x1404d2c57  xor     edx, edx; Event
0x1404d2c59  mov     [rsp+88h+CompletionFilter], 5; CompletionFilter
0x1404d2c61  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x1404d2c66  call    ZwNotifyChangeKey
0x1404d2c6b  lea     rsi, [rbx+38h]
0x1404d2c6f  mov     edi, eax
0x1404d2c71  cmp     eax, 103h
0x1404d2c76  jnz     short loc_1404D2CE2
0x1404d2c78  lea     r8, aCcregistrychan_0; "CcRegistryChangeCallback: Watch queued "...
0x1404d2c7f  mov     r9, rsi
0x1404d2c82  mov     edx, 2; Level
0x1404d2c87  mov     ecx, r15d; ComponentId
0x1404d2c8a  call    DbgPrintEx
0x1404d2c8f  cmp     cs:CcRegistryWatchInitComplete, 0
0x1404d2c96  jz      loc_1404D2D1D
0x1404d2c9c  add     rsp, 60h
0x1404d2ca0  pop     r15
0x1404d2ca2  pop     rdi
0x1404d2ca3  pop     rsi
0x1404d2ca4  pop     rbp
0x1404d2ca5  pop     rbx
0x1404d2ca6  retn
0x1404d2ca8  mov     rcx, rdi
0x1404d2cab  call    CcOpenRegistryPath
0x1404d2cb0  test    eax, eax
0x1404d2cb2  jns     loc_1404D2C23
0x1404d2cb8  mov     r9d, eax
0x1404d2cbb  mov     [rsp+88h+IoStatusBlock], rdi
0x1404d2cc0  lea     r8, aCcregistrychan_1; "CcRegistryChangeCallback: Failed to ope"...
0x1404d2cc7  xor     edx, edx; Level
0x1404d2cc9  mov     ecx, r15d; ComponentId
0x1404d2ccc  call    DbgPrintEx
0x1404d2cd1  mov     edx, 52576343h; Tag
0x1404d2cd6  mov     rcx, rbx; P
0x1404d2cd9  call    ExFreePoolWithTag
0x1404d2cde  xor     ebx, ebx
0x1404d2ce0  jmp     short loc_1404D2C8F
0x1404d2ce2  test    edi, edi
0x1404d2ce4  jns     loc_14071F924
0x1404d2cea  mov     rcx, [rbx+20h]; Handle
0x1404d2cee  call    ZwClose
0x1404d2cf3  mov     r9d, edi
0x1404d2cf6  mov     qword ptr [rbx+20h], 0
0x1404d2cfe  lea     r8, aCcregistrychan_4; "CcRegistryChangeCallback: Failed Watch "...
0x1404d2d05  mov     [rbx+48h], bpl
0x1404d2d09  xor     edx, edx; Level
0x1404d2d0b  mov     [rsp+88h+IoStatusBlock], rsi
0x1404d2d10  mov     ecx, r15d; ComponentId
0x1404d2d13  call    DbgPrintEx
0x1404d2d18  jmp     loc_1404D2C8F
0x1404d2d1d  test    rbx, rbx
0x1404d2d20  jz      loc_1404D2C9C
0x1404d2d26  cmp     byte ptr [rbx+48h], 0
0x1404d2d2a  jnz     loc_1404D2C9C
0x1404d2d30  mov     cs:CcRegistryWatchInitComplete, ebp
0x1404d2d36  jmp     loc_1404D2C9C
0x14071f924  lea     r8, aCcregistrychan_3; "CcRegistryChangeCallback: Watch queued "...
0x14071f92b  jmp     loc_1404D2C7F
```

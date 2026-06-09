# TxfAddLogContainerForLFFInRecovery

- ea: `0x14010229c`
- end: `0x1401024f7`
- name: `TxfAddLogContainerForLFFInRecovery`
- size: `603`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1401d8340`

## callees

- `0x140010be0`
- `0x140010c54`
- `0x140010e5c`
- `0x1400291f0`
- `0x140029d80`
- `0x140059250`
- `0x14010229c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1401023f3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401023f3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140102405`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140102405`
- `ntoskrnl!ExUuidCreate` at `0x14010233c`
- `ntoskrnl!ExUuidCreate` at `0x14010233c`
- `ntoskrnl!RtlStringFromGUID` at `0x1401023b2`
- `ntoskrnl!RtlStringFromGUID` at `0x1401023b2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010239e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010239e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14010246a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c4efd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14010246a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c4efd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140102453`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010247b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c4ee5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c4f10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140102453`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010247b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c4ee5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c4f10`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140102303`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401023dd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140102303`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401023dd`
- `ntoskrnl!KeDelayExecutionThread` at `0x140102370`
- `ntoskrnl!KeDelayExecutionThread` at `0x140102370`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsAddLogContainer` at `0x14010242b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsAddLogContainer` at `0x14010242b`

## pseudocode

```c
__int64 __fastcall TxfAddLogContainerForLFFInRecovery(__int64 a1, __int64 a2)
{
  char *PoolWithTag; // rsi
  struct _UNICODE_STRING *v5; // r12
  struct _UNICODE_STRING *v6; // r13
  unsigned int v7; // edi
  SIZE_T v8; // rdx
  void *v9; // rcx
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp-68h] BYREF
  char *v12; // [rsp+38h] [rbp-60h]
  char *v13; // [rsp+40h] [rbp-58h]
  __int64 v14; // [rsp+48h] [rbp-50h]
  __int64 v15; // [rsp+50h] [rbp-48h]
  UUID Uuid; // [rsp+58h] [rbp-40h] BYREF

  v14 = a1;
  v15 = a2;
  Uuid = 0;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x30u, 0x31667854u);
  *(_OWORD *)PoolWithTag = 0;
  *((_OWORD *)PoolWithTag + 1) = 0;
  *((_OWORD *)PoolWithTag + 2) = 0;
  v5 = (struct _UNICODE_STRING *)(PoolWithTag + 16);
  v13 = PoolWithTag + 16;
  v6 = (struct _UNICODE_STRING *)(PoolWithTag + 32);
  v12 = PoolWithTag + 32;
  while ( 1 )
  {
    v7 = ExUuidCreate(&Uuid);
    if ( v7 != -1073741267 )
      break;
    Interval.QuadPart = -10000000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  if ( !v7 || v7 == 1073872982 )
  {
    RtlInitUnicodeString((PUNICODE_STRING)PoolWithTag, L"%BLF%\\$");
    RtlStringFromGUID(&Uuid, v5);
    v8 = (unsigned __int16)(*(_WORD *)PoolWithTag + v5->Length);
    *((_WORD *)PoolWithTag + 17) = v8;
    *((_QWORD *)PoolWithTag + 5) = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v8, 0x31667854u);
    RtlCopyUnicodeString(v6, (PCUNICODE_STRING)PoolWithTag);
    RtlAppendUnicodeStringToString(v6, v5);
    NtfsPurgeFileRecordCache(a1);
    *(_DWORD *)(a1 + 4) |= 0x200u;
    v7 = ClfsAddLogContainer(*(PLOG_FILE_OBJECT *)(a2 + 496), 0, v6);
    *(_DWORD *)(a1 + 4) &= ~0x200u;
  }
  if ( PoolWithTag )
  {
    v9 = (void *)*((_QWORD *)PoolWithTag + 5);
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
    if ( *((_QWORD *)PoolWithTag + 3) )
      RtlFreeUnicodeString(v5);
    ExFreePoolWithTag(PoolWithTag, 0);
  }
  if ( v7 )
  {
    if ( TxfRmInForcedRecovery(a2) )
      _InterlockedOr((volatile signed __int32 *)(a2 + 136), 0x1000000u);
    TxfHardErrorFcn(a1, a2, v7, 0x318C21u);
  }
  return v7;
}

```

## disassembly

```asm
0x14010229c  mov     r11, rsp
0x14010229f  mov     [r11+18h], rsi
0x1401022a3  push    rdi
0x1401022a4  push    r12
0x1401022a6  push    r13
0x1401022a8  push    r14
0x1401022aa  push    r15
0x1401022ac  sub     rsp, 70h
0x1401022b0  mov     rax, cs:__security_cookie
0x1401022b7  xor     rax, rsp
0x1401022ba  mov     [rsp+98h+var_30], rax
0x1401022bf  mov     r14, rdx
0x1401022c2  mov     r15, rcx
0x1401022c5  mov     [rsp+98h+var_50], rcx
0x1401022ca  mov     [rsp+98h+var_48], rdx
0x1401022cf  mov     qword ptr [r11-70h], 0
0x1401022d7  mov     qword ptr [r11-58h], 0
0x1401022df  mov     qword ptr [r11-60h], 0
0x1401022e7  xorps   xmm0, xmm0
0x1401022ea  movups  xmmword ptr [rsp+98h+Uuid.Data1], xmm0
0x1401022ef  mov     ecx, cs:PoolType
0x1401022f5  or      ecx, 10h; PoolType
0x1401022f8  mov     edx, 30h ; '0'; NumberOfBytes
0x1401022fd  mov     r8d, 31667854h; Tag
0x140102303  call    cs:__imp_ExAllocatePoolWithTag
0x14010230a  nop     dword ptr [rax+rax+00h]
0x14010230f  mov     rsi, rax
0x140102312  mov     [rsp+98h+var_70], rax
0x140102317  xorps   xmm0, xmm0
0x14010231a  movups  xmmword ptr [rax], xmm0
0x14010231d  movups  xmmword ptr [rax+10h], xmm0
0x140102321  movups  xmmword ptr [rax+20h], xmm0
0x140102325  lea     r12, [rax+10h]
0x140102329  mov     [rsp+98h+var_58], r12
0x14010232e  lea     r13, [rax+20h]
0x140102332  mov     [rsp+98h+var_60], r13
0x140102337  lea     rcx, [rsp+98h+Uuid]; Uuid
0x14010233c  call    cs:__imp_ExUuidCreate
0x140102343  nop     dword ptr [rax+rax+00h]
0x140102348  mov     edi, eax
0x14010234a  mov     [rsp+98h+var_78], eax
0x14010234e  cmp     eax, 0C000022Dh
0x140102353  jnz     short loc_14010237C
0x140102355  mov     qword ptr [rsp+98h+Interval], 0
0x14010235e  mov     qword ptr [rsp+98h+Interval], 0FFFFFFFFFF676980h
0x140102367  lea     r8, [rsp+98h+Interval]; Interval
0x14010236c  xor     edx, edx; Alertable
0x14010236e  xor     ecx, ecx; WaitMode
0x140102370  call    cs:__imp_KeDelayExecutionThread
0x140102377  nop     dword ptr [rax+rax+00h]
0x14010237c  cmp     edi, 0C000022Dh
0x140102382  jz      short loc_140102337
0x140102384  test    edi, edi
0x140102386  jz      short loc_140102394
0x140102388  cmp     edi, 40020056h
0x14010238e  jnz     loc_140102443
0x140102394  lea     rdx, aBlf; "%BLF%\\$"
0x14010239b  mov     rcx, rsi; DestinationString
0x14010239e  call    cs:__imp_RtlInitUnicodeString
0x1401023a5  nop     dword ptr [rax+rax+00h]
0x1401023aa  mov     rdx, r12; GuidString
0x1401023ad  lea     rcx, [rsp+98h+Uuid]; Guid
0x1401023b2  call    cs:__imp_RtlStringFromGUID
0x1401023b9  nop     dword ptr [rax+rax+00h]
0x1401023be  movzx   ecx, word ptr [r12]
0x1401023c3  add     cx, [rsi]
0x1401023c6  movzx   edx, cx; NumberOfBytes
0x1401023c9  mov     [r13+2], dx
0x1401023ce  mov     ecx, cs:PoolType
0x1401023d4  or      ecx, 10h; PoolType
0x1401023d7  mov     r8d, 31667854h; Tag
0x1401023dd  call    cs:__imp_ExAllocatePoolWithTag
0x1401023e4  nop     dword ptr [rax+rax+00h]
0x1401023e9  mov     [r13+8], rax
0x1401023ed  mov     rdx, rsi; SourceString
0x1401023f0  mov     rcx, r13; DestinationString
0x1401023f3  call    cs:__imp_RtlCopyUnicodeString
0x1401023fa  nop     dword ptr [rax+rax+00h]
0x1401023ff  mov     rdx, r12; Source
0x140102402  mov     rcx, r13; Destination
0x140102405  call    cs:__imp_RtlAppendUnicodeStringToString
0x14010240c  nop     dword ptr [rax+rax+00h]
0x140102411  mov     rcx, r15
0x140102414  call    NtfsPurgeFileRecordCache
0x140102419  bts     dword ptr [r15+4], 9
0x14010241f  mov     r8, r13; puszContainerPath
0x140102422  xor     edx, edx; pcbContainer
0x140102424  mov     rcx, [r14+1F0h]; plfoLog
0x14010242b  call    cs:__imp_ClfsAddLogContainer
0x140102432  nop     dword ptr [rax+rax+00h]
0x140102437  mov     edi, eax
0x140102439  mov     [rsp+98h+var_78], eax
0x14010243d  btr     dword ptr [r15+4], 9
0x140102443  test    rsi, rsi
0x140102446  jz      short loc_140102487
0x140102448  mov     rcx, [r13+8]; P
0x14010244c  test    rcx, rcx
0x14010244f  jz      short loc_14010245F
0x140102451  xor     edx, edx; Tag
0x140102453  call    cs:__imp_ExFreePoolWithTag
0x14010245a  nop     dword ptr [rax+rax+00h]
0x14010245f  cmp     qword ptr [r12+8], 0
0x140102465  jz      short loc_140102476
0x140102467  mov     rcx, r12; UnicodeString
0x14010246a  call    cs:__imp_RtlFreeUnicodeString
0x140102471  nop     dword ptr [rax+rax+00h]
0x140102476  xor     edx, edx; Tag
0x140102478  mov     rcx, rsi; P
0x14010247b  call    cs:__imp_ExFreePoolWithTag
0x140102482  nop     dword ptr [rax+rax+00h]
0x140102487  jmp     short loc_1401024A1
0x140102489  mov     r8d, eax
0x14010248c  xor     edx, edx
0x14010248e  xor     ecx, ecx
0x140102490  call    NtfsProcessException
0x140102495  mov     edi, eax
0x140102497  mov     r15, [rsp+98h+var_50]
0x14010249c  mov     r14, [rsp+98h+var_48]
0x1401024a1  test    edi, edi
0x1401024a3  jz      short loc_1401024D1
0x1401024a5  mov     rcx, r14
0x1401024a8  call    TxfRmInForcedRecovery
0x1401024ad  test    al, al
0x1401024af  jz      short loc_1401024BD
0x1401024b1  lock or dword ptr [r14+88h], 1000000h
0x1401024bd  mov     r9d, 318C21h
0x1401024c3  mov     r8d, edi
0x1401024c6  mov     rdx, r14
0x1401024c9  mov     rcx, r15
0x1401024cc  call    TxfHardErrorFcn
0x1401024d1  mov     eax, edi
0x1401024d3  mov     rcx, [rsp+98h+var_30]
0x1401024d8  xor     rcx, rsp; StackCookie
0x1401024db  call    __security_check_cookie
0x1401024e0  mov     rsi, [rsp+98h+arg_10]
0x1401024e8  add     rsp, 70h
0x1401024ec  pop     r15
0x1401024ee  pop     r14
0x1401024f0  pop     r13
0x1401024f2  pop     r12
0x1401024f4  pop     rdi
0x1401024f5  retn
0x1402c4eb7  push    rbp
0x1402c4eb9  sub     rsp, 20h
0x1402c4ebd  mov     rbp, rdx
0x1402c4ec0  movzx   eax, cl
0x1402c4ec3  test    cl, cl
0x1402c4ec5  jz      short loc_1402C4ECD
0x1402c4ec7  mov     al, cs:NtfsStatusDebugFlags
0x1402c4ecd  cmp     qword ptr [rbp+28h], 0
0x1402c4ed2  jz      short loc_1402C4F1D
0x1402c4ed4  mov     rcx, [rbp+38h]
0x1402c4ed8  cmp     qword ptr [rcx+8], 0
0x1402c4edd  jz      short loc_1402C4EF2
0x1402c4edf  xor     edx, edx; Tag
0x1402c4ee1  mov     rcx, [rcx+8]; P
0x1402c4ee5  call    cs:__imp_ExFreePoolWithTag
0x1402c4eec  nop     dword ptr [rax+rax+00h]
0x1402c4ef1  nop
0x1402c4ef2  mov     rcx, [rbp+40h]; UnicodeString
0x1402c4ef6  cmp     qword ptr [rcx+8], 0
0x1402c4efb  jz      short loc_1402C4F0A
0x1402c4efd  call    cs:__imp_RtlFreeUnicodeString
0x1402c4f04  nop     dword ptr [rax+rax+00h]
0x1402c4f09  nop
0x1402c4f0a  xor     edx, edx; Tag
0x1402c4f0c  mov     rcx, [rbp+28h]; P
0x1402c4f10  call    cs:__imp_ExFreePoolWithTag
0x1402c4f17  nop     dword ptr [rax+rax+00h]
0x1402c4f1c  nop
0x1402c4f1d  add     rsp, 20h
0x1402c4f21  pop     rbp
0x1402c4f22  retn
0x1402c4f24  push    rbp
0x1402c4f26  sub     rsp, 20h
0x1402c4f2a  mov     rbp, rdx
0x1402c4f2d  mov     rdx, rcx
0x1402c4f30  xor     ecx, ecx; BugCheckParameter2
0x1402c4f32  call    NtfsExceptionFilter
0x1402c4f37  nop
0x1402c4f38  add     rsp, 20h
0x1402c4f3c  pop     rbp
0x1402c4f3d  retn
```

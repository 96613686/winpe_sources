# TxfAddLogContainerForLFFInRecovery

- ea: `0x1401022ec`
- end: `0x140102547`
- name: `TxfAddLogContainerForLFFInRecovery`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1401d8390`

## callees

- `0x140010be0`
- `0x140010c54`
- `0x140010e5c`
- `0x1400291f0`
- `0x140029d80`
- `0x1400592c0`
- `0x1401022ec`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140102443`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140102443`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140102455`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140102455`
- `ntoskrnl!ExUuidCreate` at `0x14010238c`
- `ntoskrnl!ExUuidCreate` at `0x14010238c`
- `ntoskrnl!RtlStringFromGUID` at `0x140102402`
- `ntoskrnl!RtlStringFromGUID` at `0x140102402`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401023ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401023ee`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401024ba`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c4f4d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401024ba`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c4f4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401024a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401024cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c4f35`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c4f60`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401024a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401024cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c4f35`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c4f60`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140102353`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14010242d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140102353`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14010242d`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401023c0`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401023c0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsAddLogContainer` at `0x14010247b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsAddLogContainer` at `0x14010247b`

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
    if ( (unsigned __int8)TxfRmInForcedRecovery(a2) )
      _InterlockedOr((volatile signed __int32 *)(a2 + 136), 0x1000000u);
    TxfHardErrorFcn(a1, a2, v7, 3247137);
  }
  return v7;
}

```

## disassembly

```asm
0x1401022ec  mov     r11, rsp
0x1401022ef  mov     [r11+18h], rsi
0x1401022f3  push    rdi
0x1401022f4  push    r12
0x1401022f6  push    r13
0x1401022f8  push    r14
0x1401022fa  push    r15
0x1401022fc  sub     rsp, 70h
0x140102300  mov     rax, cs:__security_cookie
0x140102307  xor     rax, rsp
0x14010230a  mov     [rsp+98h+var_30], rax
0x14010230f  mov     r14, rdx
0x140102312  mov     r15, rcx
0x140102315  mov     [rsp+98h+var_50], rcx
0x14010231a  mov     [rsp+98h+var_48], rdx
0x14010231f  mov     qword ptr [r11-70h], 0
0x140102327  mov     qword ptr [r11-58h], 0
0x14010232f  mov     qword ptr [r11-60h], 0
0x140102337  xorps   xmm0, xmm0
0x14010233a  movups  xmmword ptr [rsp+98h+Uuid.Data1], xmm0
0x14010233f  mov     ecx, cs:PoolType
0x140102345  or      ecx, 10h; PoolType
0x140102348  mov     edx, 30h ; '0'; NumberOfBytes
0x14010234d  mov     r8d, 31667854h; Tag
0x140102353  call    cs:__imp_ExAllocatePoolWithTag
0x14010235a  nop     dword ptr [rax+rax+00h]
0x14010235f  mov     rsi, rax
0x140102362  mov     [rsp+98h+var_70], rax
0x140102367  xorps   xmm0, xmm0
0x14010236a  movups  xmmword ptr [rax], xmm0
0x14010236d  movups  xmmword ptr [rax+10h], xmm0
0x140102371  movups  xmmword ptr [rax+20h], xmm0
0x140102375  lea     r12, [rax+10h]
0x140102379  mov     [rsp+98h+var_58], r12
0x14010237e  lea     r13, [rax+20h]
0x140102382  mov     [rsp+98h+var_60], r13
0x140102387  lea     rcx, [rsp+98h+Uuid]; Uuid
0x14010238c  call    cs:__imp_ExUuidCreate
0x140102393  nop     dword ptr [rax+rax+00h]
0x140102398  mov     edi, eax
0x14010239a  mov     [rsp+98h+var_78], eax
0x14010239e  cmp     eax, 0C000022Dh
0x1401023a3  jnz     short loc_1401023CC
0x1401023a5  mov     qword ptr [rsp+98h+Interval], 0
0x1401023ae  mov     qword ptr [rsp+98h+Interval], 0FFFFFFFFFF676980h
0x1401023b7  lea     r8, [rsp+98h+Interval]; Interval
0x1401023bc  xor     edx, edx; Alertable
0x1401023be  xor     ecx, ecx; WaitMode
0x1401023c0  call    cs:__imp_KeDelayExecutionThread
0x1401023c7  nop     dword ptr [rax+rax+00h]
0x1401023cc  cmp     edi, 0C000022Dh
0x1401023d2  jz      short loc_140102387
0x1401023d4  test    edi, edi
0x1401023d6  jz      short loc_1401023E4
0x1401023d8  cmp     edi, 40020056h
0x1401023de  jnz     loc_140102493
0x1401023e4  lea     rdx, aBlf; "%BLF%\\$"
0x1401023eb  mov     rcx, rsi; DestinationString
0x1401023ee  call    cs:__imp_RtlInitUnicodeString
0x1401023f5  nop     dword ptr [rax+rax+00h]
0x1401023fa  mov     rdx, r12; GuidString
0x1401023fd  lea     rcx, [rsp+98h+Uuid]; Guid
0x140102402  call    cs:__imp_RtlStringFromGUID
0x140102409  nop     dword ptr [rax+rax+00h]
0x14010240e  movzx   ecx, word ptr [r12]
0x140102413  add     cx, [rsi]
0x140102416  movzx   edx, cx; NumberOfBytes
0x140102419  mov     [r13+2], dx
0x14010241e  mov     ecx, cs:PoolType
0x140102424  or      ecx, 10h; PoolType
0x140102427  mov     r8d, 31667854h; Tag
0x14010242d  call    cs:__imp_ExAllocatePoolWithTag
0x140102434  nop     dword ptr [rax+rax+00h]
0x140102439  mov     [r13+8], rax
0x14010243d  mov     rdx, rsi; SourceString
0x140102440  mov     rcx, r13; DestinationString
0x140102443  call    cs:__imp_RtlCopyUnicodeString
0x14010244a  nop     dword ptr [rax+rax+00h]
0x14010244f  mov     rdx, r12; Source
0x140102452  mov     rcx, r13; Destination
0x140102455  call    cs:__imp_RtlAppendUnicodeStringToString
0x14010245c  nop     dword ptr [rax+rax+00h]
0x140102461  mov     rcx, r15
0x140102464  call    NtfsPurgeFileRecordCache
0x140102469  bts     dword ptr [r15+4], 9
0x14010246f  mov     r8, r13; puszContainerPath
0x140102472  xor     edx, edx; pcbContainer
0x140102474  mov     rcx, [r14+1F0h]; plfoLog
0x14010247b  call    cs:__imp_ClfsAddLogContainer
0x140102482  nop     dword ptr [rax+rax+00h]
0x140102487  mov     edi, eax
0x140102489  mov     [rsp+98h+var_78], eax
0x14010248d  btr     dword ptr [r15+4], 9
0x140102493  test    rsi, rsi
0x140102496  jz      short loc_1401024D7
0x140102498  mov     rcx, [r13+8]; P
0x14010249c  test    rcx, rcx
0x14010249f  jz      short loc_1401024AF
0x1401024a1  xor     edx, edx; Tag
0x1401024a3  call    cs:__imp_ExFreePoolWithTag
0x1401024aa  nop     dword ptr [rax+rax+00h]
0x1401024af  cmp     qword ptr [r12+8], 0
0x1401024b5  jz      short loc_1401024C6
0x1401024b7  mov     rcx, r12; UnicodeString
0x1401024ba  call    cs:__imp_RtlFreeUnicodeString
0x1401024c1  nop     dword ptr [rax+rax+00h]
0x1401024c6  xor     edx, edx; Tag
0x1401024c8  mov     rcx, rsi; P
0x1401024cb  call    cs:__imp_ExFreePoolWithTag
0x1401024d2  nop     dword ptr [rax+rax+00h]
0x1401024d7  jmp     short loc_1401024F1
0x1401024d9  mov     r8d, eax
0x1401024dc  xor     edx, edx
0x1401024de  xor     ecx, ecx
0x1401024e0  call    NtfsProcessException
0x1401024e5  mov     edi, eax
0x1401024e7  mov     r15, [rsp+98h+var_50]
0x1401024ec  mov     r14, [rsp+98h+var_48]
0x1401024f1  test    edi, edi
0x1401024f3  jz      short loc_140102521
0x1401024f5  mov     rcx, r14
0x1401024f8  call    TxfRmInForcedRecovery
0x1401024fd  test    al, al
0x1401024ff  jz      short loc_14010250D
0x140102501  lock or dword ptr [r14+88h], 1000000h
0x14010250d  mov     r9d, 318C21h
0x140102513  mov     r8d, edi
0x140102516  mov     rdx, r14
0x140102519  mov     rcx, r15
0x14010251c  call    TxfHardErrorFcn
0x140102521  mov     eax, edi
0x140102523  mov     rcx, [rsp+98h+var_30]
0x140102528  xor     rcx, rsp; StackCookie
0x14010252b  call    __security_check_cookie
0x140102530  mov     rsi, [rsp+98h+arg_10]
0x140102538  add     rsp, 70h
0x14010253c  pop     r15
0x14010253e  pop     r14
0x140102540  pop     r13
0x140102542  pop     r12
0x140102544  pop     rdi
0x140102545  retn
0x1402c4f07  push    rbp
0x1402c4f09  sub     rsp, 20h
0x1402c4f0d  mov     rbp, rdx
0x1402c4f10  movzx   eax, cl
0x1402c4f13  test    cl, cl
0x1402c4f15  jz      short loc_1402C4F1D
0x1402c4f17  mov     al, cs:NtfsStatusDebugFlags
0x1402c4f1d  cmp     qword ptr [rbp+28h], 0
0x1402c4f22  jz      short loc_1402C4F6D
0x1402c4f24  mov     rcx, [rbp+38h]
0x1402c4f28  cmp     qword ptr [rcx+8], 0
0x1402c4f2d  jz      short loc_1402C4F42
0x1402c4f2f  xor     edx, edx; Tag
0x1402c4f31  mov     rcx, [rcx+8]; P
0x1402c4f35  call    cs:__imp_ExFreePoolWithTag
0x1402c4f3c  nop     dword ptr [rax+rax+00h]
0x1402c4f41  nop
0x1402c4f42  mov     rcx, [rbp+40h]; UnicodeString
0x1402c4f46  cmp     qword ptr [rcx+8], 0
0x1402c4f4b  jz      short loc_1402C4F5A
0x1402c4f4d  call    cs:__imp_RtlFreeUnicodeString
0x1402c4f54  nop     dword ptr [rax+rax+00h]
0x1402c4f59  nop
0x1402c4f5a  xor     edx, edx; Tag
0x1402c4f5c  mov     rcx, [rbp+28h]; P
0x1402c4f60  call    cs:__imp_ExFreePoolWithTag
0x1402c4f67  nop     dword ptr [rax+rax+00h]
0x1402c4f6c  nop
0x1402c4f6d  add     rsp, 20h
0x1402c4f71  pop     rbp
0x1402c4f72  retn
0x1402c4f74  push    rbp
0x1402c4f76  sub     rsp, 20h
0x1402c4f7a  mov     rbp, rdx
0x1402c4f7d  mov     rdx, rcx
0x1402c4f80  xor     ecx, ecx; BugCheckParameter2
0x1402c4f82  call    NtfsExceptionFilter
0x1402c4f87  nop
0x1402c4f88  add     rsp, 20h
0x1402c4f8c  pop     rbp
0x1402c4f8d  retn
```

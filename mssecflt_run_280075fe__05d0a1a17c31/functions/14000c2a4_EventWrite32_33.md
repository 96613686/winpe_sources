# EventWrite32_33

- ea: `0x14000c2a4`
- end: `0x14000c513`
- name: `EventWrite32_33`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000a4a0`

## callees

- `0x140008714`
- `0x14000876c`
- `0x140009b80`
- `0x14000c2a4`
- `0x140011610`
- `0x140011650`
- `0x140011700`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!MmCopyMemory` at `0x14000c450`
- `ntoskrnl!MmCopyMemory` at `0x14000c450`
- `ntoskrnl!EtwWrite` at `0x14000c4b0`
- `ntoskrnl!EtwWrite` at `0x14000c4b0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c398`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c40e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c398`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c40e`

## pseudocode

```c
__int64 __fastcall EventWrite32_33(__int64 a1, int a2, int a3, const void *a4, SIZE_T NumberOfBytes, __int64 a6)
{
  unsigned int v6; // r14d
  SIZE_T v7; // r12
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rbx
  void *v12; // r15
  void *v13; // rdi
  PVOID PoolWithTag; // rax
  unsigned int v16; // eax
  PVOID v17; // rax
  int v18; // eax
  int v19; // esi
  int v20; // esi
  const EVENT_DESCRIPTOR *v21; // rdx
  __int64 v22; // [rsp+30h] [rbp-20h]
  size_t Size; // [rsp+38h] [rbp-18h] BYREF
  __int64 v24; // [rsp+40h] [rbp-10h] BYREF
  __int64 v25; // [rsp+90h] [rbp+40h] BYREF
  int v26; // [rsp+A0h] [rbp+50h] BYREF

  v26 = a3;
  v25 = a1;
  v6 = 0;
  v7 = (unsigned int)NumberOfBytes;
  v22 = a6;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(6);
  UserData = EtwDescriptorBuffer;
  Size = 0;
  v12 = 0;
  v13 = 0;
  v24 = 0;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v25;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[2] = &v26;
  EtwDescriptorBuffer[4] = &Size;
  EtwDescriptorBuffer[8] = (char *)&Size + 4;
  EtwDescriptorBuffer[5] = 4;
  EtwDescriptorBuffer[6] = 0;
  EtwDescriptorBuffer[7] = 0;
  EtwDescriptorBuffer[9] = 4;
  EtwDescriptorBuffer[10] = 0;
  EtwDescriptorBuffer[11] = 0;
  if ( _bittest64((const signed __int64 *)&xmmword_14001B740, 0x26u) )
  {
    if ( qword_140020008 )
      PoolWithTag = (PVOID)qword_140020008(256, v7, 1682203475);
    else
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, v7, 0x64446353u);
    v12 = PoolWithTag;
    if ( PoolWithTag )
    {
      LODWORD(Size) = v7;
      memset(PoolWithTag, 0, v7);
      memmove(v12, a4, (unsigned int)Size);
      v16 = Size;
      UserData[6] = v12;
      UserData[7] = v16;
    }
    else
    {
      v6 = -1073741670;
    }
    if ( qword_140020008 )
      v17 = (PVOID)qword_140020008(64, 4096, 1682203475);
    else
      v17 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x1000u, 0x64446353u);
    v13 = v17;
    if ( v17 )
    {
      memset(v17, 0, 0x1000u);
      MmCopyMemory(v13, v22, 4096, 2, &v24);
      v18 = v24;
      HIDWORD(Size) = v24;
      if ( (_DWORD)v24 )
      {
        UserData[10] = v13;
        *((_DWORD *)UserData + 22) = v18;
        *((_DWORD *)UserData + 23) = 0;
      }
    }
    else
    {
      v6 = -1073741670;
    }
  }
  v19 = a2 - 1;
  if ( !v19 )
  {
    v21 = &Event32;
    goto LABEL_23;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    v21 = (const EVENT_DESCRIPTOR *)Event33;
    goto LABEL_23;
  }
  if ( v20 == 1 )
  {
    v21 = (const EVENT_DESCRIPTOR *)Event59;
LABEL_23:
    v6 = EtwWrite(Microsoft_Windows_SECHandle, v21, 0, 6u, (PEVENT_DATA_DESCRIPTOR)UserData);
  }
  if ( v12 )
    SecFreePool(v12, 0x64446353u);
  if ( v13 )
    SecFreePool(v13, 0x64446353u);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v6;
}

```

## disassembly

```asm
0x14000c2a4  mov     [rsp-38h+arg_8], rbx
0x14000c2a9  mov     [rsp-38h+arg_10], r8d
0x14000c2ae  mov     [rsp-38h+arg_0], rcx
0x14000c2b3  push    rbp
0x14000c2b4  push    rsi
0x14000c2b5  push    rdi
0x14000c2b6  push    r12
0x14000c2b8  push    r13
0x14000c2ba  push    r14
0x14000c2bc  push    r15
0x14000c2be  mov     rbp, rsp
0x14000c2c1  sub     rsp, 50h
0x14000c2c5  mov     rax, cs:__security_cookie
0x14000c2cc  xor     rax, rsp
0x14000c2cf  mov     [rbp+var_8], rax
0x14000c2d3  mov     rax, [rbp+arg_28]
0x14000c2d7  xor     r14d, r14d
0x14000c2da  mov     r12d, dword ptr [rbp+NumberOfBytes]
0x14000c2de  mov     r13, r9
0x14000c2e1  mov     esi, edx
0x14000c2e3  mov     [rbp+var_20], rax
0x14000c2e7  lea     ecx, [r14+6]
0x14000c2eb  call    SecGetEtwDescriptorBuffer
0x14000c2f0  xor     edx, edx
0x14000c2f2  mov     rbx, rax
0x14000c2f5  mov     dword ptr [rbp+Size], edx
0x14000c2f8  mov     r15d, edx
0x14000c2fb  mov     dword ptr [rbp+Size+4], edx
0x14000c2fe  mov     edi, edx
0x14000c300  mov     [rbp+var_10], rdx
0x14000c304  test    rax, rax
0x14000c307  jnz     short loc_14000C313
0x14000c309  mov     eax, 0C000009Ah
0x14000c30e  jmp     loc_14000C4EE
0x14000c313  lea     rax, [rbp+arg_0]
0x14000c317  mov     qword ptr [rbx+8], 8
0x14000c31f  mov     [rbx], rax
0x14000c322  mov     r8d, 64446353h; Tag
0x14000c328  lea     rax, [rbp+arg_10]
0x14000c32c  mov     qword ptr [rbx+18h], 4
0x14000c334  mov     [rbx+10h], rax
0x14000c338  lea     rax, [rbp+Size]
0x14000c33c  mov     [rbx+20h], rax
0x14000c340  lea     rax, [rbp+Size+4]
0x14000c344  mov     [rbx+40h], rax
0x14000c348  mov     qword ptr [rbx+28h], 4
0x14000c350  mov     [rbx+30h], rdx
0x14000c354  mov     [rbx+38h], rdx
0x14000c358  mov     qword ptr [rbx+48h], 4
0x14000c360  mov     [rbx+50h], rdx
0x14000c364  mov     [rbx+58h], rdx
0x14000c368  bt      qword ptr cs:xmmword_14001B740, 26h ; '&'
0x14000c371  jnb     loc_14000C473
0x14000c377  mov     rax, cs:qword_140020008
0x14000c37e  mov     rdx, r12; NumberOfBytes
0x14000c381  test    rax, rax
0x14000c384  jz      short loc_14000C393
0x14000c386  mov     ecx, 100h
0x14000c38b  call    cs:__guard_dispatch_icall_fptr
0x14000c391  jmp     short loc_14000C3A4
0x14000c393  mov     ecx, 1; PoolType
0x14000c398  call    cs:__imp_ExAllocatePoolWithTag
0x14000c39f  nop     dword ptr [rax+rax+00h]
0x14000c3a4  mov     r15, rax
0x14000c3a7  test    rax, rax
0x14000c3aa  jnz     short loc_14000C3B4
0x14000c3ac  mov     r14d, 0C000009Ah
0x14000c3b2  jmp     short loc_14000C3E1
0x14000c3b4  mov     r8, r12; Size
0x14000c3b7  mov     dword ptr [rbp+Size], r12d
0x14000c3bb  xor     edx, edx; Val
0x14000c3bd  mov     rcx, r15; void *
0x14000c3c0  call    memset
0x14000c3c5  mov     r8d, dword ptr [rbp+Size]; Size
0x14000c3c9  mov     rdx, r13; Src
0x14000c3cc  mov     rcx, r15; void *
0x14000c3cf  call    memmove
0x14000c3d4  mov     eax, dword ptr [rbp+Size]
0x14000c3d7  mov     [rbx+30h], r15
0x14000c3db  mov     [rbx+38h], eax
0x14000c3de  mov     [rbx+3Ch], edi
0x14000c3e1  mov     rax, cs:qword_140020008
0x14000c3e8  mov     r12d, 1000h
0x14000c3ee  mov     r8d, 64446353h; Tag
0x14000c3f4  mov     edx, r12d; NumberOfBytes
0x14000c3f7  test    rax, rax
0x14000c3fa  jz      short loc_14000C409
0x14000c3fc  mov     ecx, 40h ; '@'
0x14000c401  call    cs:__guard_dispatch_icall_fptr
0x14000c407  jmp     short loc_14000C41A
0x14000c409  mov     ecx, 200h; PoolType
0x14000c40e  call    cs:__imp_ExAllocatePoolWithTag
0x14000c415  nop     dword ptr [rax+rax+00h]
0x14000c41a  mov     rdi, rax
0x14000c41d  test    rax, rax
0x14000c420  jnz     short loc_14000C42A
0x14000c422  mov     r14d, 0C000009Ah
0x14000c428  jmp     short loc_14000C473
0x14000c42a  mov     r8, r12; Size
0x14000c42d  xor     edx, edx; Val
0x14000c42f  mov     rcx, rdi; void *
0x14000c432  call    memset
0x14000c437  mov     rdx, [rbp+var_20]
0x14000c43b  lea     rax, [rbp+var_10]
0x14000c43f  mov     r9d, 2
0x14000c445  mov     [rsp+50h+UserData], rax
0x14000c44a  mov     r8, r12
0x14000c44d  mov     rcx, rdi
0x14000c450  call    cs:__imp_MmCopyMemory
0x14000c457  nop     dword ptr [rax+rax+00h]
0x14000c45c  mov     rax, [rbp+var_10]
0x14000c460  xor     edx, edx
0x14000c462  mov     dword ptr [rbp+Size+4], eax
0x14000c465  test    eax, eax
0x14000c467  jz      short loc_14000C473
0x14000c469  mov     [rbx+50h], rdi
0x14000c46d  mov     [rbx+58h], eax
0x14000c470  mov     [rbx+5Ch], edx
0x14000c473  sub     esi, 1
0x14000c476  jz      short loc_14000C494
0x14000c478  sub     esi, 1
0x14000c47b  jz      short loc_14000C48B
0x14000c47d  cmp     esi, 1
0x14000c480  jnz     short loc_14000C4BF
0x14000c482  lea     rdx, Event59
0x14000c489  jmp     short loc_14000C49B
0x14000c48b  lea     rdx, Event33
0x14000c492  jmp     short loc_14000C49B
0x14000c494  lea     rdx, Event32; EventDescriptor
0x14000c49b  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14000c4a2  mov     r9d, 6; UserDataCount
0x14000c4a8  xor     r8d, r8d; ActivityId
0x14000c4ab  mov     [rsp+50h+UserData], rbx; UserData
0x14000c4b0  call    cs:__imp_EtwWrite
0x14000c4b7  nop     dword ptr [rax+rax+00h]
0x14000c4bc  mov     r14d, eax
0x14000c4bf  test    r15, r15
0x14000c4c2  jz      short loc_14000C4D1
0x14000c4c4  mov     edx, 64446353h; Tag
0x14000c4c9  mov     rcx, r15; P
0x14000c4cc  call    SecFreePool
0x14000c4d1  test    rdi, rdi
0x14000c4d4  jz      short loc_14000C4E3
0x14000c4d6  mov     edx, 64446353h; Tag
0x14000c4db  mov     rcx, rdi; P
0x14000c4de  call    SecFreePool
0x14000c4e3  mov     rcx, rbx; ListEntry
0x14000c4e6  call    SecReleaseEtwDescriptorBuffer
0x14000c4eb  mov     eax, r14d
0x14000c4ee  mov     rcx, [rbp+var_8]
0x14000c4f2  xor     rcx, rsp; StackCookie
0x14000c4f5  call    __security_check_cookie
0x14000c4fa  mov     rbx, [rsp+50h+arg_8]
0x14000c502  add     rsp, 50h
0x14000c506  pop     r15
0x14000c508  pop     r14
0x14000c50a  pop     r13
0x14000c50c  pop     r12
0x14000c50e  pop     rdi
0x14000c50f  pop     rsi
0x14000c510  pop     rbp
0x14000c511  retn
```

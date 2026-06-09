# CompressedStreamDump::CompressedMemStream::AddMemoryRegion(_MINIDUMP_MEMORY_INFO &)

- ea: `0x18001db40`
- end: `0x18001dd22`
- name: `?AddMemoryRegion@CompressedMemStream@CompressedStreamDump@@QEAA_NAEAU_MINIDUMP_MEMORY_INFO@@@Z`
- size: `482`
- prototype: `bool __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this, struct _MINIDUMP_MEMORY_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d6f4`

## callees

- `0x180001710`
- `0x18001db40`
- `0x18001dd28`
- `0x18001df74`

## pseudocode

```c
bool __fastcall CompressedStreamDump::CompressedMemStream::AddMemoryRegion(
        CompressedStreamDump::CompressedMemStream *this,
        struct _MINIDUMP_MEMORY_INFO *a2)
{
  ULONG64 v4; // r12
  ULONG64 v5; // r13
  ULONG64 i; // r15
  ULONG64 v7; // rdx
  ULONG64 v8; // rdx
  ULONG64 v9; // r8
  unsigned int RegionSize; // r15d
  char *v11; // rdi
  __int64 v12; // rcx
  unsigned int v13; // edx
  ULONG64 BaseAddress; // rcx
  bool result; // al
  __int64 v16; // rax
  __int64 v17; // rax
  const std::bad_alloc *v18; // [rsp+28h] [rbp-70h] BYREF
  const std::exception *v19; // [rsp+30h] [rbp-68h] BYREF
  __int64 v20; // [rsp+38h] [rbp-60h] BYREF
  ULONG64 v21; // [rsp+40h] [rbp-58h]
  __int64 v22; // [rsp+48h] [rbp-50h]
  int v23; // [rsp+50h] [rbp-48h]
  int v24; // [rsp+54h] [rbp-44h]

  try
  {
    *((_QWORD *)this + 44) += a2->RegionSize;
    v4 = *((unsigned int *)this + 4);
    if ( a2->RegionSize <= v4 )
    {
      RegionSize = a2->RegionSize;
      v11 = (char *)this + 336;
      if ( *((_QWORD *)this + 39) == *((_QWORD *)this + 40)
        || RegionSize + *(_DWORD *)(*(_QWORD *)v11 + 8LL) > (unsigned int)v4 )
      {
        CompressedStreamDump::CompressedMemStream::AddNewBucket(this);
      }
      if ( *(_DWORD *)(*(_QWORD *)v11 + 32LL)
        && (v12 = *((_QWORD *)this + 11), *((_QWORD *)this + 10) != v12)
        && (v13 = *(_DWORD *)(v12 - 8), *(_QWORD *)(v12 - 24) + v13 == a2->BaseAddress)
        && RegionSize <= (unsigned int)v4 - v13 )
      {
        *(_DWORD *)(v12 - 8) = RegionSize + v13;
        *(_DWORD *)(*(_QWORD *)v11 + 8LL) += RegionSize;
      }
      else
      {
        BaseAddress = a2->BaseAddress;
        v22 = 0;
        v24 = 0;
        v20 = *((_QWORD *)this + 43);
        *((_QWORD *)this + 43) = v20 + 1;
        v21 = BaseAddress;
        v23 = RegionSize;
        CompressedStreamDump::CompressedMemStream::AppendMemoryRegion(this, (struct MemoryRegion *)&v20);
      }
    }
    else
    {
      v5 = a2->RegionSize / v4;
      for ( i = 0; i < v5; ++i )
      {
        v7 = a2->BaseAddress + i * v4;
        v22 = 0;
        v24 = 0;
        v20 = *((_QWORD *)this + 43);
        *((_QWORD *)this + 43) = v20 + 1;
        v21 = v7;
        v23 = v4;
        CompressedStreamDump::CompressedMemStream::AddNewBucket(this);
        CompressedStreamDump::CompressedMemStream::AppendMemoryRegion(this, (struct MemoryRegion *)&v20);
      }
      v8 = a2->RegionSize % v4;
      if ( (_DWORD)v8 )
      {
        v9 = v5 * v4 + a2->BaseAddress;
        v22 = 0;
        v24 = 0;
        v20 = *((_QWORD *)this + 43);
        *((_QWORD *)this + 43) = v20 + 1;
        v21 = v9;
        v23 = v8;
        CompressedStreamDump::CompressedMemStream::AddNewBucket(this);
        CompressedStreamDump::CompressedMemStream::AppendMemoryRegion(this, (struct MemoryRegion *)&v20);
      }
    }
    result = 1;
  }
  catch ( const std::bad_alloc *v18 )
  {
    v16 = (*(__int64 (__fastcall **)(const std::bad_alloc *))(*(_QWORD *)v18 + 8LL))(v18);
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"%s: memory allocation error: %s.\n",
      "AddMemoryRegion",
      v16);
    return 0;
  }
  catch ( const std::exception *v19 )
  {
    v17 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v19 + 8LL))(v19);
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"%s: standard exception: %s.\n",
      "AddMemoryRegion",
      v17);
    return 0;
  }
  catch ( ... )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"%s: unknown exception occured.\n",
      "AddMemoryRegion");
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001db40  push    rbx
0x18001db42  push    rdi
0x18001db43  push    r12
0x18001db45  push    r13
0x18001db47  push    r14
0x18001db49  push    r15
0x18001db4b  sub     rsp, 68h
0x18001db4f  mov     [rsp+98h+var_78], 0FFFFFFFFFFFFFFFEh
0x18001db58  mov     rax, cs:__security_cookie
0x18001db5f  xor     rax, rsp
0x18001db62  mov     [rsp+98h+var_40], rax
0x18001db67  mov     r14, rdx
0x18001db6a  mov     rbx, rcx
0x18001db6d  mov     rax, [rdx+18h]
0x18001db71  add     [rcx+160h], rax
0x18001db78  mov     r12d, [rcx+10h]
0x18001db7c  mov     edi, r12d
0x18001db7f  mov     rax, [rdx+18h]
0x18001db83  cmp     rax, r12
0x18001db86  jbe     loc_18001DC56
0x18001db8c  xor     edx, edx
0x18001db8e  div     rdi
0x18001db91  mov     r13, rax
0x18001db94  xor     r15d, r15d
0x18001db97  cmp     r15, r13
0x18001db9a  jnb     short loc_18001DBF1
0x18001db9c  mov     rdx, rdi
0x18001db9f  imul    rdx, r15
0x18001dba3  add     rdx, [r14]
0x18001dba6  mov     [rsp+98h+var_50], 0
0x18001dbaf  mov     [rsp+98h+var_44], 0
0x18001dbb7  mov     rax, [rbx+158h]
0x18001dbbe  mov     [rsp+98h+var_60], rax
0x18001dbc3  inc     rax
0x18001dbc6  mov     [rbx+158h], rax
0x18001dbcd  mov     [rsp+98h+var_58], rdx
0x18001dbd2  mov     [rsp+98h+var_48], r12d
0x18001dbd7  mov     rcx, rbx; this
0x18001dbda  call    ?AddNewBucket@CompressedMemStream@CompressedStreamDump@@AEAAXXZ; CompressedStreamDump::CompressedMemStream::AddNewBucket(void)
0x18001dbdf  lea     rdx, [rsp+98h+var_60]; struct MemoryRegion *
0x18001dbe4  mov     rcx, rbx; this
0x18001dbe7  call    ?AppendMemoryRegion@CompressedMemStream@CompressedStreamDump@@AEAAXAEAUMemoryRegion@@@Z; CompressedStreamDump::CompressedMemStream::AppendMemoryRegion(MemoryRegion &)
0x18001dbec  inc     r15
0x18001dbef  jmp     short loc_18001DB97
0x18001dbf1  xor     edx, edx
0x18001dbf3  mov     rax, [r14+18h]
0x18001dbf7  div     rdi
0x18001dbfa  test    edx, edx
0x18001dbfc  jz      loc_18001DCFE
0x18001dc02  imul    rdi, r13
0x18001dc06  mov     r8, [r14]
0x18001dc09  add     r8, rdi
0x18001dc0c  mov     [rsp+98h+var_50], 0
0x18001dc15  mov     [rsp+98h+var_44], 0
0x18001dc1d  mov     rax, [rbx+158h]
0x18001dc24  mov     [rsp+98h+var_60], rax
0x18001dc29  inc     rax
0x18001dc2c  mov     [rbx+158h], rax
0x18001dc33  mov     [rsp+98h+var_58], r8
0x18001dc38  mov     [rsp+98h+var_48], edx
0x18001dc3c  mov     rcx, rbx; this
0x18001dc3f  call    ?AddNewBucket@CompressedMemStream@CompressedStreamDump@@AEAAXXZ; CompressedStreamDump::CompressedMemStream::AddNewBucket(void)
0x18001dc44  lea     rdx, [rsp+98h+var_60]; struct MemoryRegion *
0x18001dc49  mov     rcx, rbx; this
0x18001dc4c  call    ?AppendMemoryRegion@CompressedMemStream@CompressedStreamDump@@AEAAXAEAUMemoryRegion@@@Z; CompressedStreamDump::CompressedMemStream::AppendMemoryRegion(MemoryRegion &)
0x18001dc51  jmp     loc_18001DCFE
0x18001dc56  mov     r15d, [rdx+18h]
0x18001dc5a  lea     rdi, [rcx+150h]
0x18001dc61  mov     rax, [rcx+140h]
0x18001dc68  cmp     [rcx+138h], rax
0x18001dc6f  jz      short loc_18001DC7F
0x18001dc71  mov     rax, [rdi]
0x18001dc74  mov     eax, [rax+8]
0x18001dc77  add     eax, r15d
0x18001dc7a  cmp     eax, r12d
0x18001dc7d  jbe     short loc_18001DC84
0x18001dc7f  call    ?AddNewBucket@CompressedMemStream@CompressedStreamDump@@AEAAXXZ; CompressedStreamDump::CompressedMemStream::AddNewBucket(void)
0x18001dc84  mov     rax, [rdi]
0x18001dc87  cmp     dword ptr [rax+20h], 0
0x18001dc8b  jbe     short loc_18001DCBD
0x18001dc8d  mov     rcx, [rbx+58h]
0x18001dc91  cmp     [rbx+50h], rcx
0x18001dc95  jz      short loc_18001DCBD
0x18001dc97  mov     edx, [rcx-8]
0x18001dc9a  mov     eax, edx
0x18001dc9c  add     rax, [rcx-18h]
0x18001dca0  cmp     rax, [r14]
0x18001dca3  jnz     short loc_18001DCBD
0x18001dca5  sub     r12d, edx
0x18001dca8  cmp     r15d, r12d
0x18001dcab  ja      short loc_18001DCBD
0x18001dcad  lea     eax, [r15+rdx]
0x18001dcb1  mov     [rcx-8], eax
0x18001dcb4  mov     rax, [rdi]
0x18001dcb7  add     [rax+8], r15d
0x18001dcbb  jmp     short loc_18001DCFE
0x18001dcbd  mov     rcx, [r14]
0x18001dcc0  mov     [rsp+98h+var_50], 0
0x18001dcc9  mov     [rsp+98h+var_44], 0
0x18001dcd1  mov     rax, [rbx+158h]
0x18001dcd8  mov     [rsp+98h+var_60], rax
0x18001dcdd  inc     rax
0x18001dce0  mov     [rbx+158h], rax
0x18001dce7  mov     [rsp+98h+var_58], rcx
0x18001dcec  mov     [rsp+98h+var_48], r15d
0x18001dcf1  lea     rdx, [rsp+98h+var_60]; struct MemoryRegion *
0x18001dcf6  mov     rcx, rbx; this
0x18001dcf9  call    ?AppendMemoryRegion@CompressedMemStream@CompressedStreamDump@@AEAAXAEAUMemoryRegion@@@Z; CompressedStreamDump::CompressedMemStream::AppendMemoryRegion(MemoryRegion &)
0x18001dcfe  mov     al, 1
0x18001dd00  jmp     short loc_18001DD04
0x18001dd02  xor     al, al
0x18001dd04  mov     rcx, [rsp+98h+var_40]
0x18001dd09  xor     rcx, rsp; StackCookie
0x18001dd0c  call    __security_check_cookie
0x18001dd11  add     rsp, 68h
0x18001dd15  pop     r15
0x18001dd17  pop     r14
0x18001dd19  pop     r13
0x18001dd1b  pop     r12
0x18001dd1d  pop     rdi
0x18001dd1e  pop     rbx
0x18001dd1f  retn
0x18001dd20  jmp     short loc_18001DD02
```

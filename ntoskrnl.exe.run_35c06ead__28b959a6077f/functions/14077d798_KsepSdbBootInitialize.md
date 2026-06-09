# KsepSdbBootInitialize

- ea: `0x14077d798`
- end: `0x14077d8af`
- name: `KsepSdbBootInitialize`
- size: `279`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140c6f5bc`

## callees

- `0x1404965f8`
- `0x1404a9424`
- `0x1404adb80`
- `0x1404df6b0`
- `0x1406f4480`
- `0x14077d798`
- `0x14097adb4`
- `0x14097b6b4`

## string_xrefs

- `0x14077d866`: `KSE: SdbInitDatabaseInMemory failed during boot!\n`
- `0x14077d874`: `KSE: SdbInitDatabaseInMemory failed during boot!\n`
- `0x14077d7f1`: `KSE: Failed to allocate memory for shim database during boot!\n`
- `0x14077d7ff`: `KSE: Failed to allocate memory for shim database during boot!\n`

## pseudocode

```c
__int64 __fastcall KsepSdbBootInitialize(void *Src, size_t Size, __int64 a3)
{
  size_t v4; // rsi
  void *Paged; // rax
  void *v7; // rbx
  unsigned int v8; // esi
  __int64 v9; // rcx
  __int64 inited; // rax
  __int64 v11; // rdx

  v4 = (unsigned int)Size;
  Paged = (void *)KsepPoolAllocatePaged((unsigned int)Size);
  v7 = Paged;
  if ( Paged )
  {
    memmove(Paged, Src, v4);
    inited = SdbInitDatabaseInMemory(v7, (unsigned int)v4);
    if ( inited )
    {
      *(_QWORD *)(a3 + 8) = v7;
      *(_QWORD *)a3 = inited;
      *(_DWORD *)(a3 + 48) = SdbGetDatabaseEdition(*(_QWORD *)(inited + 8));
      return 0;
    }
    else
    {
      v8 = -1073741823;
      v11 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u)
           + 1)
          & 0x3F;
      *(&AlpcpMessageLogLock.Timer.Period + 2 * v11) = -1073741823;
      *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v11) = 590002;
      if ( ((__int64)stru_140E4CF30.StackBase & 2) != 0 )
        KsepDebugPrint(1, "KSE: SdbInitDatabaseInMemory failed during boot!\n");
      KsepLogError(1, "KSE: SdbInitDatabaseInMemory failed during boot!\n");
      KsepPoolFreePaged(v7);
    }
  }
  else
  {
    v8 = -1073741670;
    v9 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u) + 1)
       & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v9) = -1073741670;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v9) = 589986;
    if ( ((__int64)stru_140E4CF30.StackBase & 2) != 0 )
      KsepDebugPrint(0, "KSE: Failed to allocate memory for shim database during boot!\n");
    KsepLogError(0, "KSE: Failed to allocate memory for shim database during boot!\n");
  }
  return v8;
}

```

## disassembly

```asm
0x14077d798  push    rbx
0x14077d79a  push    rbp
0x14077d79b  push    rsi
0x14077d79c  push    rdi
0x14077d79d  push    r14
0x14077d79f  sub     rsp, 20h
0x14077d7a3  mov     r14, rcx
0x14077d7a6  mov     esi, edx
0x14077d7a8  mov     ecx, edx
0x14077d7aa  mov     rdi, r8
0x14077d7ad  call    KsepPoolAllocatePaged
0x14077d7b2  mov     rbx, rax
0x14077d7b5  test    rax, rax
0x14077d7b8  jnz     short loc_14077D812
0x14077d7ba  lea     edi, [rax+1]
0x14077d7bd  mov     esi, 0C000009Ah
0x14077d7c2  mov     ecx, edi
0x14077d7c4  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, ecx
0x14077d7cc  add     ecx, edi
0x14077d7ce  lea     rax, AlpcpMessageLogLock.Timer.Processor
0x14077d7d5  and     ecx, 3Fh
0x14077d7d8  mov     dword ptr [rax+rcx*8+4], 0C000009Ah
0x14077d7e0  mov     dword ptr [rax+rcx*8], 900A2h
0x14077d7e7  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077d7ed  test    al, 2
0x14077d7ef  jz      short loc_14077D7FF
0x14077d7f1  lea     rdx, aKseFailedToAll; "KSE: Failed to allocate memory for shim"...
0x14077d7f8  xor     ecx, ecx
0x14077d7fa  call    KsepDebugPrint
0x14077d7ff  lea     rdx, aKseFailedToAll; "KSE: Failed to allocate memory for shim"...
0x14077d806  xor     ecx, ecx
0x14077d808  call    KsepLogError
0x14077d80d  jmp     loc_14077D8A1
0x14077d812  mov     r8, rsi; Size
0x14077d815  mov     rdx, r14; Src
0x14077d818  mov     rcx, rbx; void *
0x14077d81b  call    memmove
0x14077d820  mov     edx, esi
0x14077d822  mov     rcx, rbx
0x14077d825  call    SdbInitDatabaseInMemory
0x14077d82a  test    rax, rax
0x14077d82d  jnz     short loc_14077D88C
0x14077d82f  lea     edi, [rax+1]
0x14077d832  mov     esi, 0C0000001h
0x14077d837  mov     edx, edi
0x14077d839  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, edx
0x14077d841  add     edx, edi
0x14077d843  lea     rax, AlpcpMessageLogLock.Timer.Processor
0x14077d84a  and     edx, 3Fh
0x14077d84d  mov     dword ptr [rax+rdx*8+4], 0C0000001h
0x14077d855  mov     dword ptr [rax+rdx*8], 900B2h
0x14077d85c  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077d862  test    al, 2
0x14077d864  jz      short loc_14077D874
0x14077d866  lea     rdx, aKseSdbinitdata_0; "KSE: SdbInitDatabaseInMemory failed dur"...
0x14077d86d  mov     ecx, edi
0x14077d86f  call    KsepDebugPrint
0x14077d874  lea     rdx, aKseSdbinitdata_0; "KSE: SdbInitDatabaseInMemory failed dur"...
0x14077d87b  mov     ecx, edi
0x14077d87d  call    KsepLogError
0x14077d882  mov     rcx, rbx
0x14077d885  call    KsepPoolFreePaged
0x14077d88a  jmp     short loc_14077D8A1
0x14077d88c  mov     [rdi+8], rbx
0x14077d890  mov     [rdi], rax
0x14077d893  mov     rcx, [rax+8]
0x14077d897  call    SdbGetDatabaseEdition
0x14077d89c  mov     [rdi+30h], eax
0x14077d89f  xor     esi, esi
0x14077d8a1  mov     eax, esi
0x14077d8a3  add     rsp, 20h
0x14077d8a7  pop     r14
0x14077d8a9  pop     rdi
0x14077d8aa  pop     rsi
0x14077d8ab  pop     rbp
0x14077d8ac  pop     rbx
0x14077d8ad  retn
```

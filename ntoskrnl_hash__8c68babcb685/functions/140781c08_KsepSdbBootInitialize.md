# KsepSdbBootInitialize

- ea: `0x140781c08`
- end: `0x140781d1f`
- name: `KsepSdbBootInitialize`
- size: `279`
- prototype: `__int64 __fastcall(void *Src, size_t Size, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140c7486c`

## callees

- `0x1404a4304`
- `0x1404b8304`
- `0x1404bd2d0`
- `0x1404eef34`
- `0x1406f6f80`
- `0x140781c08`
- `0x1408c0be4`
- `0x1408c14e4`

## string_xrefs

- `0x140781cd6`: `KSE: SdbInitDatabaseInMemory failed during boot!\n`
- `0x140781ce4`: `KSE: SdbInitDatabaseInMemory failed during boot!\n`
- `0x140781c61`: `KSE: Failed to allocate memory for shim database during boot!\n`
- `0x140781c6f`: `KSE: Failed to allocate memory for shim database during boot!\n`

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
      v11 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
      KsepHistoryErrors[2 * v11 + 1] = -1073741823;
      KsepHistoryErrors[2 * v11] = 590002;
      if ( (KsepDebugFlag & 2) != 0 )
        KsepDebugPrint(1, "KSE: SdbInitDatabaseInMemory failed during boot!\n");
      KsepLogError(1, "KSE: SdbInitDatabaseInMemory failed during boot!\n");
      KsepPoolFreePaged(v7);
    }
  }
  else
  {
    v8 = -1073741670;
    v9 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v9 + 1] = -1073741670;
    KsepHistoryErrors[2 * v9] = 589986;
    if ( (KsepDebugFlag & 2) != 0 )
      KsepDebugPrint(0, "KSE: Failed to allocate memory for shim database during boot!\n");
    KsepLogError(0, "KSE: Failed to allocate memory for shim database during boot!\n");
  }
  return v8;
}

```

## disassembly

```asm
0x140781c08  push    rbx
0x140781c0a  push    rbp
0x140781c0b  push    rsi
0x140781c0c  push    rdi
0x140781c0d  push    r14
0x140781c0f  sub     rsp, 20h
0x140781c13  mov     r14, rcx
0x140781c16  mov     esi, edx
0x140781c18  mov     ecx, edx
0x140781c1a  mov     rdi, r8
0x140781c1d  call    KsepPoolAllocatePaged
0x140781c22  mov     rbx, rax
0x140781c25  test    rax, rax
0x140781c28  jnz     short loc_140781C82
0x140781c2a  lea     edi, [rax+1]
0x140781c2d  mov     esi, 0C000009Ah
0x140781c32  mov     ecx, edi
0x140781c34  lock xadd cs:KsepHistoryErrorsIndex, ecx
0x140781c3c  add     ecx, edi
0x140781c3e  lea     rax, KsepHistoryErrors
0x140781c45  and     ecx, 3Fh
0x140781c48  mov     dword ptr [rax+rcx*8+4], 0C000009Ah
0x140781c50  mov     dword ptr [rax+rcx*8], 900A2h
0x140781c57  mov     eax, cs:KsepDebugFlag
0x140781c5d  test    al, 2
0x140781c5f  jz      short loc_140781C6F
0x140781c61  lea     rdx, aKseFailedToAll; "KSE: Failed to allocate memory for shim"...
0x140781c68  xor     ecx, ecx
0x140781c6a  call    KsepDebugPrint
0x140781c6f  lea     rdx, aKseFailedToAll; "KSE: Failed to allocate memory for shim"...
0x140781c76  xor     ecx, ecx
0x140781c78  call    KsepLogError
0x140781c7d  jmp     loc_140781D11
0x140781c82  mov     r8, rsi; Size
0x140781c85  mov     rdx, r14; Src
0x140781c88  mov     rcx, rbx; void *
0x140781c8b  call    memmove
0x140781c90  mov     edx, esi
0x140781c92  mov     rcx, rbx
0x140781c95  call    SdbInitDatabaseInMemory
0x140781c9a  test    rax, rax
0x140781c9d  jnz     short loc_140781CFC
0x140781c9f  lea     edi, [rax+1]
0x140781ca2  mov     esi, 0C0000001h
0x140781ca7  mov     edx, edi
0x140781ca9  lock xadd cs:KsepHistoryErrorsIndex, edx
0x140781cb1  add     edx, edi
0x140781cb3  lea     rax, KsepHistoryErrors
0x140781cba  and     edx, 3Fh
0x140781cbd  mov     dword ptr [rax+rdx*8+4], 0C0000001h
0x140781cc5  mov     dword ptr [rax+rdx*8], 900B2h
0x140781ccc  mov     eax, cs:KsepDebugFlag
0x140781cd2  test    al, 2
0x140781cd4  jz      short loc_140781CE4
0x140781cd6  lea     rdx, aKseSdbinitdata_0; "KSE: SdbInitDatabaseInMemory failed dur"...
0x140781cdd  mov     ecx, edi
0x140781cdf  call    KsepDebugPrint
0x140781ce4  lea     rdx, aKseSdbinitdata_0; "KSE: SdbInitDatabaseInMemory failed dur"...
0x140781ceb  mov     ecx, edi
0x140781ced  call    KsepLogError
0x140781cf2  mov     rcx, rbx
0x140781cf5  call    KsepPoolFreePaged
0x140781cfa  jmp     short loc_140781D11
0x140781cfc  mov     [rdi+8], rbx
0x140781d00  mov     [rdi], rax
0x140781d03  mov     rcx, [rax+8]
0x140781d07  call    SdbGetDatabaseEdition
0x140781d0c  mov     [rdi+30h], eax
0x140781d0f  xor     esi, esi
0x140781d11  mov     eax, esi
0x140781d13  add     rsp, 20h
0x140781d17  pop     r14
0x140781d19  pop     rdi
0x140781d1a  pop     rsi
0x140781d1b  pop     rbp
0x140781d1c  pop     rbx
0x140781d1d  retn
```

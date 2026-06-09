# CreateLogMarshallingArea

- ea: `0x18000a7e0`
- end: `0x18000a941`
- name: `CreateLogMarshallingArea`
- size: `353`
- prototype: `BOOL __stdcall(HANDLE hLog, CLFS_BLOCK_ALLOCATION pfnAllocBuffer, CLFS_BLOCK_DEALLOCATION pfnFreeBuffer, PVOID pvBlockAllocContext, ULONG cbMarshallingBuffer, ULONG cMaxWriteBuffers, ULONG cMaxReadBuffers, PVOID *ppvMarshal)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000187c`
- `0x18000840c`
- `0x18000a7e0`
- `0x180010bdc`
- `0x180013058`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a84f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a91a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a84f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a91a`

## pseudocode

```c
BOOL __stdcall CreateLogMarshallingArea(
        HANDLE hLog,
        CLFS_BLOCK_ALLOCATION pfnAllocBuffer,
        CLFS_BLOCK_DEALLOCATION pfnFreeBuffer,
        PVOID pvBlockAllocContext,
        ULONG cbMarshallingBuffer,
        ULONG cMaxWriteBuffers,
        ULONG cMaxReadBuffers,
        PVOID *ppvMarshal)
{
  DWORD v10; // ecx
  CClfsMarshallingContext *v12; // rax
  volatile signed __int32 *v13; // rax
  CClfsMarshallingContext *v14; // rbx
  BOOL v15; // ebp
  DWORD v16; // esi

  if ( !cMaxReadBuffers && !cMaxWriteBuffers || !ppvMarshal )
    goto LABEL_8;
  if ( hLog == (HANDLE)-1LL )
  {
    v10 = 6;
LABEL_9:
    SetLastError(v10);
    return 0;
  }
  *ppvMarshal = 0;
  if ( pfnAllocBuffer )
  {
    if ( !pfnFreeBuffer )
    {
LABEL_8:
      v10 = 87;
      goto LABEL_9;
    }
  }
  else if ( pfnFreeBuffer )
  {
    goto LABEL_8;
  }
  if ( cbMarshallingBuffer < 0x200 )
  {
    v10 = 122;
    goto LABEL_9;
  }
  if ( (cbMarshallingBuffer & 0x1FF) != 0 )
  {
    v10 = 1784;
    goto LABEL_9;
  }
  v12 = (CClfsMarshallingContext *)operator new(0x170u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v12
    || (v13 = (volatile signed __int32 *)CClfsMarshallingContext::CClfsMarshallingContext(
                                           v12,
                                           cMaxReadBuffers,
                                           cMaxWriteBuffers),
        (v14 = (CClfsMarshallingContext *)v13) == 0) )
  {
    v10 = 14;
    goto LABEL_9;
  }
  v15 = 1;
  _InterlockedAdd(v13 + 27, 1u);
  v16 = CClfsMarshallingContext::Initialize(
          (CClfsMarshallingContext *)v13,
          hLog,
          pfnAllocBuffer,
          pfnFreeBuffer,
          pvBlockAllocContext,
          cbMarshallingBuffer,
          cMaxReadBuffers,
          cMaxWriteBuffers);
  if ( v16 )
  {
    v15 = 0;
    CClfsMarshallingContext::Release(v14);
    v14 = 0;
  }
  *ppvMarshal = v14;
  SetLastError(v16);
  return v15;
}

```

## disassembly

```asm
0x18000a7e0  mov     [rsp+arg_8], rbx
0x18000a7e5  mov     [rsp+arg_18], r9
0x18000a7ea  mov     [rsp+hSourceHandle], rcx
0x18000a7ef  push    rbp
0x18000a7f0  push    rsi
0x18000a7f1  push    rdi
0x18000a7f2  push    r12
0x18000a7f4  push    r13
0x18000a7f6  push    r14
0x18000a7f8  push    r15
0x18000a7fa  sub     rsp, 40h
0x18000a7fe  mov     r12d, [rsp+78h+cMaxReadBuffers]
0x18000a806  mov     r14, r8
0x18000a809  mov     r15d, [rsp+78h+cMaxWriteBuffers]
0x18000a811  mov     r13, rdx
0x18000a814  mov     rax, rcx
0x18000a817  test    r12d, r12d
0x18000a81a  jnz     short loc_18000A821
0x18000a81c  test    r15d, r15d
0x18000a81f  jz      short loc_18000A84A
0x18000a821  mov     rdi, [rsp+78h+ppvMarshal]
0x18000a829  test    rdi, rdi
0x18000a82c  jz      short loc_18000A84A
0x18000a82e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a832  jnz     short loc_18000A839
0x18000a834  lea     ecx, [rax+7]
0x18000a837  jmp     short loc_18000A84F
0x18000a839  mov     qword ptr [rdi], 0
0x18000a840  test    r13, r13
0x18000a843  jz      short loc_18000A876
0x18000a845  test    r14, r14
0x18000a848  jnz     short loc_18000A87B
0x18000a84a  mov     ecx, 57h ; 'W'; dwErrCode
0x18000a84f  call    cs:__imp_SetLastError
0x18000a856  nop     dword ptr [rax+rax+00h]
0x18000a85b  xor     eax, eax
0x18000a85d  mov     rbx, [rsp+78h+arg_8]
0x18000a865  add     rsp, 40h
0x18000a869  pop     r15
0x18000a86b  pop     r14
0x18000a86d  pop     r13
0x18000a86f  pop     r12
0x18000a871  pop     rdi
0x18000a872  pop     rsi
0x18000a873  pop     rbp
0x18000a874  retn
0x18000a876  test    r14, r14
0x18000a879  jnz     short loc_18000A84A
0x18000a87b  mov     esi, [rsp+78h+cbMarshallingBuffer]
0x18000a882  cmp     esi, 200h
0x18000a888  jb      loc_18000A937
0x18000a88e  test    esi, 1FFh
0x18000a894  jz      short loc_18000A89D
0x18000a896  mov     ecx, 6F8h
0x18000a89b  jmp     short loc_18000A84F
0x18000a89d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a8a4  mov     ecx, 170h; unsigned __int64
0x18000a8a9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a8ae  test    rax, rax
0x18000a8b1  jz      short loc_18000A92D
0x18000a8b3  mov     r8d, r15d; unsigned int
0x18000a8b6  mov     edx, r12d; unsigned int
0x18000a8b9  mov     rcx, rax; this
0x18000a8bc  call    ??0CClfsMarshallingContext@@QEAA@KK@Z; CClfsMarshallingContext::CClfsMarshallingContext(ulong,ulong)
0x18000a8c1  mov     rbx, rax
0x18000a8c4  test    rax, rax
0x18000a8c7  jz      short loc_18000A92D
0x18000a8c9  mov     ebp, 1
0x18000a8ce  lock add [rax+6Ch], ebp
0x18000a8d2  mov     rax, [rsp+78h+arg_18]
0x18000a8da  mov     r9, r14; void (*)(void *, void *)
0x18000a8dd  mov     rdx, [rsp+78h+hSourceHandle]; hSourceHandle
0x18000a8e5  mov     r8, r13; void *(*)(unsigned int, void *)
0x18000a8e8  mov     [rsp+78h+var_40], r15d; unsigned int
0x18000a8ed  mov     rcx, rbx; this
0x18000a8f0  mov     [rsp+78h+var_48], r12d; unsigned int
0x18000a8f5  mov     [rsp+78h+var_50], esi; unsigned int
0x18000a8f9  mov     [rsp+78h+var_58], rax; void *
0x18000a8fe  call    ?Initialize@CClfsMarshallingContext@@QEAAKPEAXP6APEAXK0@ZP6AX00@Z0KKK@Z; CClfsMarshallingContext::Initialize(void *,void * (*)(ulong,void *),void (*)(void *,void *),void *,ulong,ulong,ulong)
0x18000a903  mov     esi, eax
0x18000a905  test    eax, eax
0x18000a907  jz      short loc_18000A915
0x18000a909  mov     rcx, rbx; this
0x18000a90c  xor     ebp, ebp
0x18000a90e  call    ?Release@CClfsMarshallingContext@@QEAAKXZ; CClfsMarshallingContext::Release(void)
0x18000a913  xor     ebx, ebx
0x18000a915  mov     ecx, esi; dwErrCode
0x18000a917  mov     [rdi], rbx
0x18000a91a  call    cs:__imp_SetLastError
0x18000a921  nop     dword ptr [rax+rax+00h]
0x18000a926  mov     eax, ebp
0x18000a928  jmp     loc_18000A85D
0x18000a92d  mov     ecx, 0Eh
0x18000a932  jmp     loc_18000A84F
0x18000a937  mov     ecx, 7Ah ; 'z'
0x18000a93c  jmp     loc_18000A84F
```

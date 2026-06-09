# CMFMediaType<CMFSRWLock>::GetVideoFormat(void)

- ea: `0x180050c00`
- end: `0x180050cf8`
- name: `?GetVideoFormat@?$CMFMediaType@VCMFSRWLock@@@@UEAAPEBU_MFVIDEOFORMAT@@XZ`
- size: `248`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180050c00`
- `0x180050d00`
- `0x180120ecc`
- `0x180121581`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050cb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ced`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050cb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ced`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050c32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050c32`

## pseudocode

```c
__int64 __fastcall CMFMediaType<CMFSRWLock>::GetVideoFormat(__int64 a1)
{
  IMFMediaType *v1; // rdi
  __int64 v3; // rbp
  void *v4; // rax
  void *v5; // rsi
  MFVIDEOFORMAT *v6; // rcx
  UINT32 pcbSize; // [rsp+40h] [rbp+8h] BYREF
  MFVIDEOFORMAT *ppMFVF; // [rsp+48h] [rbp+10h] BYREF

  v1 = (IMFMediaType *)(a1 - 8);
  v3 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 - 8) + 224LL))(a1 - 8);
  if ( !*(_QWORD *)(a1 + 56) )
  {
    v4 = CoTaskMemAlloc(0x8B0u);
    v5 = v4;
    if ( !v4 )
      goto LABEL_11;
    memset_0(v4, 0, 0x8B0u);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 56), (signed __int64)v5, 0) )
      CoTaskMemFree(v5);
    _InterlockedExchange((volatile __int32 *)(a1 + 40), 1);
  }
  if ( !*(_DWORD *)(a1 + 40) )
  {
LABEL_10:
    v3 = *(_QWORD *)(a1 + 56);
    goto LABEL_11;
  }
  ppMFVF = 0;
  pcbSize = 0;
  if ( MFCreateMFVideoFormatFromMFMediaType(v1, &ppMFVF, &pcbSize) >= 0 )
  {
    if ( pcbSize > 0x8B0 )
    {
      CoTaskMemFree((LPVOID)ppMFVF);
      goto LABEL_11;
    }
    memcpy_0(*(void **)(a1 + 56), ppMFVF, pcbSize);
    v6 = ppMFVF;
    _InterlockedExchange((volatile __int32 *)(a1 + 40), 0);
    CoTaskMemFree((LPVOID)v6);
    goto LABEL_10;
  }
LABEL_11:
  v1->UnlockStore(v1);
  return v3;
}

```

## disassembly

```asm
0x180050c00  mov     [rsp+arg_10], rbx
0x180050c05  push    rbp
0x180050c06  push    rsi
0x180050c07  push    rdi
0x180050c08  sub     rsp, 20h
0x180050c0c  lea     rdi, [rcx-8]
0x180050c10  mov     rbx, rcx
0x180050c13  mov     rax, [rdi]
0x180050c16  mov     rcx, rdi
0x180050c19  xor     ebp, ebp
0x180050c1b  mov     rax, [rax+0E0h]
0x180050c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c27  cmp     [rbx+38h], rbp
0x180050c2b  jnz     short loc_180050C66
0x180050c2d  mov     ecx, 8B0h; cb
0x180050c32  call    cs:__imp_CoTaskMemAlloc
0x180050c38  mov     rsi, rax
0x180050c3b  test    rax, rax
0x180050c3e  jz      short loc_180050CBB
0x180050c40  xor     edx, edx; Val
0x180050c42  mov     r8d, 8B0h; Size
0x180050c48  mov     rcx, rax; void *
0x180050c4b  call    memset_0
0x180050c50  xor     eax, eax
0x180050c52  lock cmpxchg [rbx+38h], rsi
0x180050c58  jnz     loc_180050CEA
0x180050c5e  mov     eax, 1
0x180050c63  xchg    eax, [rbx+28h]
0x180050c66  cmp     [rbx+28h], ebp
0x180050c69  jz      short loc_180050CB7
0x180050c6b  lea     r8, [rsp+38h+pcbSize]; pcbSize
0x180050c70  mov     [rsp+38h+ppMFVF], rbp
0x180050c75  lea     rdx, [rsp+38h+ppMFVF]; ppMFVF
0x180050c7a  mov     [rsp+38h+pcbSize], ebp
0x180050c7e  mov     rcx, rdi; pMFType
0x180050c81  call    MFCreateMFVideoFormatFromMFMediaType
0x180050c86  test    eax, eax
0x180050c88  js      short loc_180050CBB
0x180050c8a  cmp     [rsp+38h+pcbSize], 8B0h
0x180050c92  ja      short loc_180050CDD
0x180050c94  mov     r8d, [rsp+38h+pcbSize]; Size
0x180050c99  mov     rdx, [rsp+38h+ppMFVF]; Src
0x180050c9e  mov     rcx, [rbx+38h]; void *
0x180050ca2  call    memcpy_0
0x180050ca7  mov     rcx, [rsp+38h+ppMFVF]; pv
0x180050cac  xor     eax, eax
0x180050cae  xchg    eax, [rbx+28h]
0x180050cb1  call    cs:__imp_CoTaskMemFree
0x180050cb7  mov     rbp, [rbx+38h]
0x180050cbb  mov     rdx, [rdi]
0x180050cbe  mov     rcx, rdi
0x180050cc1  mov     rax, [rdx+0E8h]
0x180050cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ccd  mov     rbx, [rsp+38h+arg_10]
0x180050cd2  mov     rax, rbp
0x180050cd5  add     rsp, 20h
0x180050cd9  pop     rdi
0x180050cda  pop     rsi
0x180050cdb  pop     rbp
0x180050cdc  retn
0x180050cdd  mov     rcx, [rsp+38h+ppMFVF]; pv
0x180050ce2  call    cs:__imp_CoTaskMemFree
0x180050ce8  jmp     short loc_180050CBB
0x180050cea  mov     rcx, rsi; pv
0x180050ced  call    cs:__imp_CoTaskMemFree
0x180050cf3  jmp     loc_180050C5E
```

# CStreamChunkList::GetFreeChunk(long *)

- ea: `0x180028cdc`
- end: `0x180028d35`
- name: `?GetFreeChunk@CStreamChunkList@@QEAAPEAUCStreamChunk@@PEAJ@Z`
- size: `89`
- prototype: `struct CStreamChunk *__fastcall(CStreamChunkList *__hidden this, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027ff4`

## callees

- `0x180028cdc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028d18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028d18`

## pseudocode

```c
struct CStreamChunk *__fastcall CStreamChunkList::GetFreeChunk(CStreamChunkList *this, int *a2)
{
  struct CStreamChunk *result; // rax
  __int64 v5; // rcx

  *a2 = 0;
  result = (struct CStreamChunk *)*((_QWORD *)this + 1);
  if ( result )
    goto LABEL_2;
  result = (struct CStreamChunk *)CoTaskMemAlloc(8LL * *(unsigned int *)this);
  *((_QWORD *)this + 1) = result;
  if ( result )
  {
    *((_BYTE *)this + 16) = 1;
LABEL_2:
    v5 = *((unsigned int *)this + 1);
    result = (struct CStreamChunk *)((char *)result + 8 * v5);
    *((_DWORD *)this + 1) = v5 + 1;
    return result;
  }
  *a2 = -1073741670;
  return result;
}

```

## disassembly

```asm
0x180028cdc  mov     [rsp+arg_0], rbx
0x180028ce1  push    rdi
0x180028ce2  sub     rsp, 20h
0x180028ce6  mov     dword ptr [rdx], 0
0x180028cec  mov     rdi, rdx
0x180028cef  mov     rax, [rcx+8]
0x180028cf3  mov     rbx, rcx
0x180028cf6  test    rax, rax
0x180028cf9  jz      short loc_180028D12
0x180028cfb  mov     ecx, [rbx+4]
0x180028cfe  lea     rax, [rax+rcx*8]
0x180028d02  inc     ecx
0x180028d04  mov     [rbx+4], ecx
0x180028d07  mov     rbx, [rsp+28h+arg_0]
0x180028d0c  add     rsp, 20h
0x180028d10  pop     rdi
0x180028d11  retn
0x180028d12  mov     ecx, [rcx]
0x180028d14  shl     rcx, 3; cb
0x180028d18  call    cs:__imp_CoTaskMemAlloc
0x180028d1e  mov     [rbx+8], rax
0x180028d22  test    rax, rax
0x180028d25  jnz     short loc_180028D2F
0x180028d27  mov     dword ptr [rdi], 0C000009Ah
0x180028d2d  jmp     short loc_180028D07
0x180028d2f  mov     byte ptr [rbx+10h], 1
0x180028d33  jmp     short loc_180028CFB
```

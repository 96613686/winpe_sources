# CString::operator=(ushort const *)

- ea: `0x180019fb0`
- end: `0x18001a03a`
- name: `??4CString@@QEAAAEAV0@PEBG@Z`
- size: `138`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001230c`
- `0x180012b10`
- `0x180013b8c`
- `0x180014220`
- `0x1800151c0`
- `0x180016470`
- `0x180018384`
- `0x1800184c0`
- `0x18001a040`
- `0x18001bec8`

## callees

- `0x180001534`
- `0x180006ec0`
- `0x180019e80`
- `0x180019fb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019fe8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019fe8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CString::operator=(__int64 a1, const unsigned __int16 *a2)
{
  HLOCAL *v4; // rdi
  CString::StringValue *v5; // rax

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 12LL), 0xFFFFFFFF) == 1 )
  {
    v4 = *(HLOCAL **)(a1 + 8);
    if ( v4 )
    {
      if ( *v4 )
        LocalFree(*v4);
      operator delete(v4);
    }
  }
  *(_QWORD *)(a1 + 8) = 0;
  v5 = (CString::StringValue *)operator new(0x18u);
  if ( v5 )
    v5 = (CString::StringValue *)CString::StringValue::StringValue(v5, a2);
  *(_QWORD *)(a1 + 8) = v5;
  return a1;
}

```

## disassembly

```asm
0x180019fb0  mov     [rsp+arg_8], rbx
0x180019fb5  mov     [rsp+arg_10], rsi
0x180019fba  push    rdi
0x180019fbb  sub     rsp, 20h
0x180019fbf  mov     rsi, rdx
0x180019fc2  mov     rbx, rcx
0x180019fc5  mov     r8, [rcx+8]
0x180019fc9  or      eax, 0FFFFFFFFh
0x180019fcc  lock xadd [r8+0Ch], eax
0x180019fd2  cmp     eax, 1
0x180019fd5  jnz     short loc_180019FFB
0x180019fd7  mov     rdi, [rcx+8]
0x180019fdb  test    rdi, rdi
0x180019fde  jz      short loc_180019FFB
0x180019fe0  mov     rcx, [rdi]; hMem
0x180019fe3  test    rcx, rcx
0x180019fe6  jz      short loc_180019FEE
0x180019fe8  call    cs:__imp_LocalFree
0x180019fee  mov     edx, 18h; unsigned __int64
0x180019ff3  mov     rcx, rdi; void *
0x180019ff6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019ffb  mov     qword ptr [rbx+8], 0
0x18001a003  mov     ecx, 18h; uBytes
0x18001a008  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a00d  mov     [rsp+28h+arg_0], rax
0x18001a012  test    rax, rax
0x18001a015  jz      short loc_18001A023
0x18001a017  mov     rdx, rsi; unsigned __int16 *
0x18001a01a  mov     rcx, rax; this
0x18001a01d  call    ??0StringValue@CString@@QEAA@PEBG@Z; CString::StringValue::StringValue(ushort const *)
0x18001a022  nop
0x18001a023  mov     [rbx+8], rax
0x18001a027  mov     rax, rbx
0x18001a02a  mov     rbx, [rsp+28h+arg_8]
0x18001a02f  mov     rsi, [rsp+28h+arg_10]
0x18001a034  add     rsp, 20h
0x18001a038  pop     rdi
0x18001a039  retn
```

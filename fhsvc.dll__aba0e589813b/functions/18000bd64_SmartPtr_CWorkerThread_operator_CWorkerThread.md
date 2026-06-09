# SmartPtr<CWorkerThread>::operator=(CWorkerThread *)

- ea: `0x18000bd64`
- end: `0x18000bdc6`
- name: `??4?$SmartPtr@VCWorkerThread@@@@QEAAAEAV0@PEAVCWorkerThread@@@Z`
- size: `98`
- prototype: `_QWORD *__fastcall(_QWORD *, CWorkerThread *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003f00`
- `0x180007330`

## callees

- `0x18000bd64`
- `0x18000cadc`
- `0x18000f11c`

## pseudocode

```c
_QWORD *__fastcall SmartPtr<CWorkerThread>::operator=(_QWORD *a1, CWorkerThread *a2)
{
  _DWORD *v4; // rax
  _QWORD *result; // rax
  __int64 v6; // [rsp+0h] [rbp-28h] BYREF

  if ( *a1 )
    SmartPtr<CWorkerThread>::RefCounter::Dec_nRefs();
  try
  {
    if ( a2 )
    {
      v4 = operator new(0x10u);
      if ( v4 )
      {
        *(_QWORD *)v4 = a2;
        v4[2] = 0;
      }
      *a1 = v4;
      if ( v4 )
        ++v4[2];
    }
    else
    {
      *a1 = 0;
    }
    result = a1;
  }
  catch ( ... )
  {
    CWorkerThread::`scalar deleting destructor'(a2, (unsigned int)&v6);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000bd64  mov     [rsp+arg_10], rbx
0x18000bd69  mov     [rsp+arg_8], rdx
0x18000bd6e  push    rdi
0x18000bd6f  sub     rsp, 20h
0x18000bd73  mov     rdi, rdx
0x18000bd76  mov     rbx, rcx
0x18000bd79  mov     rcx, [rcx]
0x18000bd7c  test    rcx, rcx
0x18000bd7f  jz      short loc_18000BD86
0x18000bd81  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCWorkerThread@@@@QEAAHXZ; SmartPtr<CWorkerThread>::RefCounter::Dec_nRefs(void)
0x18000bd86  test    rdi, rdi
0x18000bd89  jz      short loc_18000BDB1
0x18000bd8b  mov     ecx, 10h; Size
0x18000bd90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bd95  test    rax, rax
0x18000bd98  jz      short loc_18000BDA4
0x18000bd9a  mov     [rax], rdi
0x18000bd9d  mov     dword ptr [rax+8], 0
0x18000bda4  mov     [rbx], rax
0x18000bda7  test    rax, rax
0x18000bdaa  jz      short loc_18000BDB8
0x18000bdac  inc     dword ptr [rax+8]
0x18000bdaf  jmp     short loc_18000BDB8
0x18000bdb1  mov     qword ptr [rbx], 0
0x18000bdb8  mov     rax, rbx
0x18000bdbb  mov     rbx, [rsp+28h+arg_10]
0x18000bdc0  add     rsp, 20h
0x18000bdc4  pop     rdi
0x18000bdc5  retn
```

# CBuffer::GetReadPage(ulong,ulong *)

- ea: `0x180005c04`
- end: `0x180005ca1`
- name: `?GetReadPage@CBuffer@@QEAAPEAU_RECORDPAGE@@KPEAK@Z`
- size: `157`
- prototype: `struct _RECORDPAGE *__fastcall(CBuffer *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cec8`

## callees

- `0x180005c04`
- `0x18001266c`
- `0x180015010`

## pseudocode

```c
struct _RECORDPAGE *__fastcall CBuffer::GetReadPage(CBuffer *this, unsigned int a2, unsigned int *a3)
{
  __int64 v6; // rdi
  struct _RECORDPAGE *result; // rax
  int pExceptionObject; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_DWORD *)this + 10) )
  {
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  *a3 = 0;
  if ( *((_DWORD *)this + 16) )
    return 0;
  v6 = *((_QWORD *)this + 7);
  if ( !v6
    || (unsigned int)((__int64 (__fastcall *)(_QWORD, __int64, void *))lpCalcCRC)(
                       (unsigned int)(*((_DWORD *)this + 2) - 8),
                       v6 + 8,
                       pulCRCTable) != *(_DWORD *)(v6 + 4)
    || a2 > *(_DWORD *)(v6 + 8)
    || *(_DWORD *)v6 != 1146368594 )
  {
    return 0;
  }
  result = (struct _RECORDPAGE *)v6;
  *a3 = *((_DWORD *)this + 14) - *((_DWORD *)this + 6);
  return result;
}

```

## disassembly

```asm
0x180005c04  mov     [rsp+arg_8], rbx
0x180005c09  mov     [rsp+arg_10], rbp
0x180005c0e  push    rsi
0x180005c0f  push    rdi
0x180005c10  push    r14
0x180005c12  sub     rsp, 20h
0x180005c16  xor     eax, eax
0x180005c18  mov     rsi, r8
0x180005c1b  mov     ebp, edx
0x180005c1d  mov     rbx, rcx
0x180005c20  cmp     [rcx+28h], eax
0x180005c23  jz      short loc_180005C87
0x180005c25  mov     [r8], eax
0x180005c28  cmp     [rcx+40h], eax
0x180005c2b  jnz     short loc_180005C72
0x180005c2d  mov     rdi, [rcx+38h]
0x180005c31  test    rdi, rdi
0x180005c34  jz      short loc_180005C72
0x180005c36  mov     ecx, [rcx+8]
0x180005c39  lea     rdx, [rdi+8]
0x180005c3d  mov     r8, cs:?pulCRCTable@@3PEAKEA; ulong * pulCRCTable
0x180005c44  sub     ecx, 8
0x180005c47  mov     rax, cs:?lpCalcCRC@@3P6AKIPEAEPEAK@ZEA; ulong (*lpCalcCRC)(uint,uchar *,ulong *)
0x180005c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c53  cmp     eax, [rdi+4]
0x180005c56  jnz     short loc_180005C72
0x180005c58  cmp     ebp, [rdi+8]
0x180005c5b  ja      short loc_180005C72
0x180005c5d  cmp     dword ptr [rdi], 44543252h
0x180005c63  jnz     short loc_180005C72
0x180005c65  mov     ecx, [rbx+38h]
0x180005c68  mov     rax, rdi
0x180005c6b  sub     ecx, [rbx+18h]
0x180005c6e  mov     [rsi], ecx
0x180005c70  jmp     short loc_180005C74
0x180005c72  xor     eax, eax
0x180005c74  mov     rbx, [rsp+38h+arg_8]
0x180005c79  mov     rbp, [rsp+38h+arg_10]
0x180005c7e  add     rsp, 20h
0x180005c82  pop     r14
0x180005c84  pop     rdi
0x180005c85  pop     rsi
0x180005c86  retn
0x180005c87  lea     rdx, _TI1J; pThrowInfo
0x180005c8e  mov     [rsp+38h+pExceptionObject], 80070057h
0x180005c96  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180005c9b  call    _CxxThrowException_0
```

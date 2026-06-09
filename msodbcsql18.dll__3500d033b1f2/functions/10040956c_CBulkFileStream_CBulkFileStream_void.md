# CBulkFileStream::CBulkFileStream(void *)

- ea: `0x10040956c`
- end: `0x100409614`
- name: `??0CBulkFileStream@@AEAA@PEAX@Z`
- size: `168`
- prototype: `CBulkFileStream *__fastcall(CBulkFileStream *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x10040a6d0`

## callees

- `0x10040956c`
- `0x10054811c`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1004095ac`
- `KERNEL32!ReadFile` at `0x1004095ac`
- `KERNEL32!SetFilePointer` at `0x1004095c2`
- `KERNEL32!SetFilePointer` at `0x1004095c2`

## pseudocode

```c
CBulkFileStream *__fastcall CBulkFileStream::CBulkFileStream(CBulkFileStream *this, void *a2)
{
  int v2; // ebx
  void *v4; // rcx
  CBulkFileStream *result; // rax
  char v6; // [rsp+40h] [rbp+8h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp+10h] BYREF
  DWORD v8; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &CBulkFileStream::`vftable';
  _InterlockedAdd((volatile signed __int32 *)this + 4, 1u);
  v4 = (void *)*((_QWORD *)this + 1);
  v6 = 0;
  if ( !ReadFile(v4, &v6, 1u, &v8, 0) )
  {
    pExceptionObject = 0;
    throw (int *)&pExceptionObject;
  }
  if ( SetFilePointer(*((HANDLE *)this + 1), 0, 0, 0) )
  {
    pExceptionObject = 0;
    throw (int *)&pExceptionObject;
  }
  result = this;
  LOBYTE(v2) = (unsigned __int8)(v6 - 52) <= 5u;
  *((_DWORD *)this + 5) = v2;
  return result;
}

```

## disassembly

```asm
0x10040956c  mov     r11, rsp
0x10040956f  mov     [r11+20h], rbx
0x100409573  push    rdi
0x100409574  sub     rsp, 30h
0x100409578  xor     ebx, ebx
0x10040957a  mov     [rcx+8], rdx
0x10040957e  lea     rax, ??_7CBulkFileStream@@6B@; const CBulkFileStream::`vftable'
0x100409585  mov     [rcx+10h], rbx
0x100409589  mov     rdi, rcx
0x10040958c  mov     [rcx], rax
0x10040958f  lea     r8d, [rbx+1]; nNumberOfBytesToRead
0x100409593  lock add [rcx+10h], r8d
0x100409598  mov     rcx, [rcx+8]; hFile
0x10040959c  lea     r9, [r11+18h]; lpNumberOfBytesRead
0x1004095a0  lea     rdx, [r11+8]; lpBuffer
0x1004095a4  mov     [rsp+38h+arg_0], bl
0x1004095a8  mov     [r11-18h], rbx
0x1004095ac  call    cs:__imp_ReadFile
0x1004095b2  test    eax, eax
0x1004095b4  jz      short loc_1004095E8
0x1004095b6  mov     rcx, [rdi+8]; hFile
0x1004095ba  xor     r9d, r9d; dwMoveMethod
0x1004095bd  xor     r8d, r8d; lpDistanceToMoveHigh
0x1004095c0  xor     edx, edx; lDistanceToMove
0x1004095c2  call    cs:__imp_SetFilePointer
0x1004095c8  test    eax, eax
0x1004095ca  jnz     short loc_1004095FE
0x1004095cc  mov     al, [rsp+38h+arg_0]
0x1004095d0  sub     al, 34h ; '4'
0x1004095d2  cmp     al, 5
0x1004095d4  mov     rax, rdi
0x1004095d7  setbe   bl
0x1004095da  mov     [rdi+14h], ebx
0x1004095dd  mov     rbx, [rsp+38h+arg_18]
0x1004095e2  add     rsp, 30h
0x1004095e6  pop     rdi
0x1004095e7  retn
0x1004095e8  lea     rdx, _TI1H; pThrowInfo
0x1004095ef  mov     [rsp+38h+pExceptionObject], ebx
0x1004095f3  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1004095f8  call    _CxxThrowException_0
0x1004095fe  lea     rdx, _TI1H; pThrowInfo
0x100409605  mov     [rsp+38h+pExceptionObject], ebx
0x100409609  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x10040960e  call    _CxxThrowException_0
```

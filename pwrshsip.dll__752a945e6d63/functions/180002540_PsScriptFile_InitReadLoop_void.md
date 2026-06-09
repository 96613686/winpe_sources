# PsScriptFile::InitReadLoop(void)

- ea: `0x180002540`
- end: `0x18000259e`
- name: `?InitReadLoop@PsScriptFile@@UEAAKXZ`
- size: `94`
- prototype: `unsigned int __fastcall(PsScriptFile *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002540`
- `0x180004650`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x18000257c`
- `KERNEL32!SetFilePointerEx` at `0x18000257c`
- `KERNEL32!GetLastError` at `0x180002586`
- `KERNEL32!GetLastError` at `0x180002586`

## pseudocode

```c
DWORD __fastcall PsScriptFile::InitReadLoop(PsScriptFile *this)
{
  void *v2; // rcx
  DWORD result; // eax

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 == (void *)-1LL )
  {
    if ( !*((_QWORD *)this + 1) )
      return 6;
    goto LABEL_5;
  }
  if ( *((_QWORD *)this + 1) )
  {
LABEL_5:
    *((_QWORD *)this + 2) = 0;
    return SipFile::InitReadContentLoop(this);
  }
  if ( SetFilePointerEx(v2, 0, 0, 0) )
    return SipFile::InitReadContentLoop(this);
  result = GetLastError();
  if ( !result )
    return SipFile::InitReadContentLoop(this);
  return result;
}

```

## disassembly

```asm
0x180002540  push    rbx
0x180002542  sub     rsp, 20h
0x180002546  mov     rbx, rcx
0x180002549  mov     rcx, [rcx+20h]; hFile
0x18000254d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002551  jnz     short loc_180002563
0x180002553  cmp     qword ptr [rbx+8], 0
0x180002558  jnz     short loc_18000256A
0x18000255a  lea     eax, [rcx+7]
0x18000255d  add     rsp, 20h
0x180002561  pop     rbx
0x180002562  retn
0x180002563  cmp     qword ptr [rbx+8], 0
0x180002568  jz      short loc_180002574
0x18000256a  mov     qword ptr [rbx+10h], 0
0x180002572  jmp     short loc_180002590
0x180002574  xor     edx, edx; liDistanceToMove
0x180002576  xor     r9d, r9d; dwMoveMethod
0x180002579  xor     r8d, r8d; lpNewFilePointer
0x18000257c  call    cs:__imp_SetFilePointerEx
0x180002582  test    eax, eax
0x180002584  jnz     short loc_180002590
0x180002586  call    cs:__imp_GetLastError
0x18000258c  test    eax, eax
0x18000258e  jnz     short loc_180002598
0x180002590  mov     rcx, rbx; this
0x180002593  call    ?InitReadContentLoop@SipFile@@QEAAKXZ; SipFile::InitReadContentLoop(void)
0x180002598  add     rsp, 20h
0x18000259c  pop     rbx
0x18000259d  retn
```

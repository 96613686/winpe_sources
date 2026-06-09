# CVsActivityLogFile::FWriteFilePreserveCurrentPosition(ushort const *)

- ea: `0x1400649d0`
- end: `0x140064a77`
- name: `?FWriteFilePreserveCurrentPosition@CVsActivityLogFile@@QEAA_NPEBG@Z`
- size: `167`
- prototype: `bool __fastcall(CVsActivityLogFile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140064fc0`

## callees

- `0x140001020`
- `0x140064960`
- `0x1400649d0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x140064a0c`
- `KERNEL32!SetFilePointer` at `0x140064a40`
- `KERNEL32!SetFilePointer` at `0x140064a0c`
- `KERNEL32!SetFilePointer` at `0x140064a40`
- `KERNEL32!GetLastError` at `0x140064a19`
- `KERNEL32!GetLastError` at `0x140064a4b`
- `KERNEL32!GetLastError` at `0x140064a19`
- `KERNEL32!GetLastError` at `0x140064a4b`

## pseudocode

```c
char __fastcall CVsActivityLogFile::FWriteFilePreserveCurrentPosition(
        CVsActivityLogFile *this,
        const unsigned __int16 *a2)
{
  void *v4; // rcx
  char v5; // bl
  LONG v6; // esi
  LONG DistanceToMoveHigh; // [rsp+20h] [rbp-28h] BYREF

  v4 = (void *)*((_QWORD *)this + 4);
  if ( v4 == (void *)-1LL )
    return 0;
  v5 = 0;
  DistanceToMoveHigh = 0;
  v6 = SetFilePointer(v4, 0, &DistanceToMoveHigh, 1u);
  if ( v6 == -1 )
  {
    if ( GetLastError() )
      return 0;
  }
  if ( !CVsActivityLogFile::FWriteFile(this, a2) )
    return 0;
  if ( SetFilePointer(*((HANDLE *)this + 4), v6, &DistanceToMoveHigh, 0) != -1 || !GetLastError() )
    return 1;
  return v5;
}

```

## disassembly

```asm
0x1400649d0  mov     [rsp+arg_10], rbx
0x1400649d5  push    rbp
0x1400649d6  push    rsi
0x1400649d7  push    rdi
0x1400649d8  sub     rsp, 30h
0x1400649dc  mov     rax, cs:__security_cookie
0x1400649e3  xor     rax, rsp
0x1400649e6  mov     [rsp+48h+var_20], rax
0x1400649eb  mov     rdi, rcx
0x1400649ee  mov     rbp, rdx
0x1400649f1  mov     rcx, [rcx+20h]; hFile
0x1400649f5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400649f9  jz      short loc_140064A5B
0x1400649fb  xor     ebx, ebx
0x1400649fd  lea     r8, [rsp+48h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x140064a02  xor     edx, edx; lDistanceToMove
0x140064a04  mov     [rsp+48h+DistanceToMoveHigh], ebx
0x140064a08  lea     r9d, [rbx+1]; dwMoveMethod
0x140064a0c  call    cs:__imp_SetFilePointer
0x140064a12  mov     esi, eax
0x140064a14  cmp     eax, 0FFFFFFFFh
0x140064a17  jnz     short loc_140064A23
0x140064a19  call    cs:__imp_GetLastError
0x140064a1f  test    eax, eax
0x140064a21  jnz     short loc_140064A5B
0x140064a23  mov     rdx, rbp; unsigned __int16 *
0x140064a26  mov     rcx, rdi; this
0x140064a29  call    ?FWriteFile@CVsActivityLogFile@@QEAA_NPEBG@Z; CVsActivityLogFile::FWriteFile(ushort const *)
0x140064a2e  test    al, al
0x140064a30  jz      short loc_140064A5B
0x140064a32  mov     rcx, [rdi+20h]; hFile
0x140064a36  lea     r8, [rsp+48h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x140064a3b  xor     r9d, r9d; dwMoveMethod
0x140064a3e  mov     edx, esi; lDistanceToMove
0x140064a40  call    cs:__imp_SetFilePointer
0x140064a46  cmp     eax, 0FFFFFFFFh
0x140064a49  jnz     short loc_140064A55
0x140064a4b  call    cs:__imp_GetLastError
0x140064a51  test    eax, eax
0x140064a53  jnz     short loc_140064A57
0x140064a55  mov     bl, 1
0x140064a57  mov     al, bl
0x140064a59  jmp     short loc_140064A5D
0x140064a5b  xor     al, al
0x140064a5d  mov     rcx, [rsp+48h+var_20]
0x140064a62  xor     rcx, rsp; StackCookie
0x140064a65  call    __security_check_cookie
0x140064a6a  mov     rbx, [rsp+48h+arg_10]
0x140064a6f  add     rsp, 30h
0x140064a73  pop     rdi
0x140064a74  pop     rsi
0x140064a75  pop     rbp
0x140064a76  retn
```

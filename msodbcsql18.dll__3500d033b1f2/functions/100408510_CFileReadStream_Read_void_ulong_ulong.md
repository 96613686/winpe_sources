# CFileReadStream::Read(void *,ulong,ulong *)

- ea: `0x100408510`
- end: `0x10040859e`
- name: `?Read@CFileReadStream@@UEAAJPEAXKPEAK@Z`
- size: `142`
- prototype: `__int64 __fastcall(CFileReadStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x100408cc8`

## callees

- `0x100408510`
- `0x100546a24`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10040854c`
- `KERNEL32!GetLastError` at `0x10040854c`
- `KERNEL32!ReadFile` at `0x100408542`
- `KERNEL32!ReadFile` at `0x100408542`

## pseudocode

```c
__int64 __fastcall CFileReadStream::Read(CFileReadStream *this, void *a2, DWORD a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  void *v6; // rcx
  signed int LastError; // eax

  v4 = 0;
  if ( a4 && a2 )
  {
    *a4 = 0;
    v6 = (void *)*((_QWORD *)this + 2);
    if ( v6 == (void *)-1LL )
    {
      return (unsigned int)-2147221301;
    }
    else if ( ReadFile(v6, a2, a3, a4, 0) )
    {
      if ( !*a4 )
        return (unsigned int)-2147221300;
    }
    else
    {
      LastError = GetLastError();
      v4 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    return (unsigned int)bidTraceHR(0, 142345, 2147942487LL, a4);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x100408510  mov     [rsp+arg_0], rbx
0x100408515  push    rdi
0x100408516  sub     rsp, 30h
0x10040851a  xor     ebx, ebx
0x10040851c  mov     rdi, r9
0x10040851f  test    r9, r9
0x100408522  jz      short loc_10040856D
0x100408524  test    rdx, rdx
0x100408527  jz      short loc_10040856D
0x100408529  mov     [r9], ebx
0x10040852c  mov     rcx, [rcx+10h]; hFile
0x100408530  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x100408534  jnz     short loc_10040853D
0x100408536  mov     ebx, 800400CBh
0x10040853b  jmp     short loc_100408591
0x10040853d  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x100408542  call    cs:__imp_ReadFile
0x100408548  test    eax, eax
0x10040854a  jnz     short loc_100408562
0x10040854c  call    cs:__imp_GetLastError
0x100408552  movzx   ebx, ax
0x100408555  or      ebx, 80070000h
0x10040855b  test    eax, eax
0x10040855d  cmovle  ebx, eax
0x100408560  jmp     short loc_100408591
0x100408562  cmp     [rdi], ebx
0x100408564  jnz     short loc_100408591
0x100408566  mov     ebx, 800400CCh
0x10040856b  jmp     short loc_100408591
0x10040856d  test    byte ptr cs:_bidGblFlags, 2
0x100408574  jz      short loc_10040858C
0x100408576  mov     edx, 22C09h
0x10040857b  xor     ecx, ecx
0x10040857d  mov     r8d, 80070057h
0x100408583  call    _bidTraceHR
0x100408588  mov     ebx, eax
0x10040858a  jmp     short loc_100408591
0x10040858c  mov     ebx, 80070057h
0x100408591  mov     eax, ebx
0x100408593  mov     rbx, [rsp+38h+arg_0]
0x100408598  add     rsp, 30h
0x10040859c  pop     rdi
0x10040859d  retn
```

# Dfdll::CFile::Read(Dfdll::CBuffer<uchar> &,ulong &)

- ea: `0x18001138c`
- end: `0x18001140c`
- name: `?Read@CFile@Dfdll@@QEAAJAEAV?$CBuffer@E@2@AEAK@Z`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18001140c`

## callees

- `0x180001fc8`
- `0x18001138c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800113e0`
- `KERNEL32!GetLastError` at `0x1800113e0`
- `KERNEL32!ReadFile` at `0x1800113d6`
- `KERNEL32!ReadFile` at `0x1800113d6`

## pseudocode

```c
__int64 __fastcall Dfdll::CFile::Read(__int64 a1, LPVOID *a2, unsigned int *a3)
{
  void *v3; // rdi
  signed int v6; // ecx
  signed int LastError; // eax

  v3 = *(void **)(a1 + 8);
  if ( v3 == (void *)-1LL )
  {
    return (unsigned int)-2147024883;
  }
  else
  {
    v6 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)a2, *a3);
    if ( v6 >= 0 )
    {
      if ( ReadFile(v3, a2[1], *a3, a3, 0) )
        return 0;
      LastError = GetLastError();
      v6 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v6 = LastError;
      if ( v6 >= 0 )
        return 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001138c  mov     [rsp+arg_0], rbx
0x180011391  mov     [rsp+arg_8], rsi
0x180011396  push    rdi
0x180011397  sub     rsp, 30h
0x18001139b  mov     rdi, [rcx+8]
0x18001139f  mov     rbx, r8
0x1800113a2  mov     rsi, rdx
0x1800113a5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800113a9  jnz     short loc_1800113B2
0x1800113ab  mov     ecx, 8007000Dh
0x1800113b0  jmp     short loc_1800113FA
0x1800113b2  mov     edx, [r8]; unsigned int
0x1800113b5  mov     rcx, rsi; this
0x1800113b8  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x1800113bd  mov     ecx, eax
0x1800113bf  test    eax, eax
0x1800113c1  js      short loc_1800113FA
0x1800113c3  mov     r8d, [rbx]; nNumberOfBytesToRead
0x1800113c6  mov     r9, rbx; lpNumberOfBytesRead
0x1800113c9  mov     rdx, [rsi+8]; lpBuffer
0x1800113cd  mov     rcx, rdi; hFile
0x1800113d0  and     [rsp+38h+var_18], 0
0x1800113d6  call    cs:__imp_ReadFile
0x1800113dc  test    eax, eax
0x1800113de  jnz     short loc_1800113F8
0x1800113e0  call    cs:__imp_GetLastError
0x1800113e6  movzx   ecx, ax
0x1800113e9  or      ecx, 80070000h
0x1800113ef  test    eax, eax
0x1800113f1  cmovle  ecx, eax
0x1800113f4  test    ecx, ecx
0x1800113f6  js      short loc_1800113FA
0x1800113f8  xor     ecx, ecx
0x1800113fa  mov     rbx, [rsp+38h+arg_0]
0x1800113ff  mov     eax, ecx
0x180011401  mov     rsi, [rsp+38h+arg_8]
0x180011406  add     rsp, 30h
0x18001140a  pop     rdi
0x18001140b  retn
```

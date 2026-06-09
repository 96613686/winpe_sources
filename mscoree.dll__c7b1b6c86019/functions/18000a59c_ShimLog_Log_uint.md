# ShimLog::Log(uint,...)

- ea: `0x18000a59c`
- end: `0x18000a69c`
- name: `?Log@ShimLog@@QEAAXIZZ`
- size: `256`
- prototype: `void(ShimLog *__hidden this, unsigned int, ...)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180001ff0`
- `0x180009af4`
- `0x18002a43c`
- `0x18002adf4`
- `0x180030798`
- `0x1800313bc`

## callees

- `0x18000a59c`
- `0x18000dfa8`
- `0x18002a3b8`
- `0x180030758`
- `0x180041ac0`
- `0x180045030`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18000a672`
- `KERNEL32!WriteFile` at `0x18000a672`
- `USER32!LoadStringW` at `0x18000a615`
- `USER32!LoadStringW` at `0x18000a615`

## pseudocode

```c
void ShimLog::Log(HANDLE *this, UINT a2, ...)
{
  HINSTANCE ResourceInst; // rax
  int StringW; // eax
  __int64 v5; // r8
  __int64 NumberOfBytesWritten; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t v7[256]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Buffer[256]; // [rsp+248h] [rbp+140h] BYREF
  va_list ArgList; // [rsp+498h] [rbp+390h] BYREF

  va_start(ArgList, a2);
  if ( *((_DWORD *)this + 2) )
  {
    NumberOfBytesWritten = 0;
    memset_thunk_772440563353939046(v7, 0, 0x1FEu);
    ResourceInst = GetResourceInst();
    StringW = LoadStringW(ResourceInst, a2, Buffer, 255);
    if ( StringW )
    {
      if ( StringW != 255 )
      {
        vsnwprintf_s(v7, 0xFFu, 0xFEu, Buffer, ArgList);
        LODWORD(NumberOfBytesWritten) = 0;
        v5 = -1;
        do
          ++v5;
        while ( v7[v5] );
        WriteFile(this[2], v7, 2 * v5, (LPDWORD)&NumberOfBytesWritten, 0);
        ShimLog::LogNewline((ShimLog *)this);
      }
    }
  }
}

```

## disassembly

```asm
0x18000a59c  mov     rax, rsp
0x18000a59f  mov     [rax+10h], edx
0x18000a5a2  mov     [rax+18h], r8
0x18000a5a6  mov     [rax+20h], r9
0x18000a5aa  push    rbp
0x18000a5ab  push    rbx
0x18000a5ac  push    rdi
0x18000a5ad  push    r14
0x18000a5af  lea     rbp, [rax-378h]
0x18000a5b6  sub     rsp, 458h
0x18000a5bd  mov     rax, cs:__security_cookie
0x18000a5c4  xor     rax, rsp
0x18000a5c7  mov     [rbp+370h+var_30], rax
0x18000a5ce  xor     edi, edi
0x18000a5d0  mov     rbx, rcx
0x18000a5d3  cmp     [rcx+8], edi
0x18000a5d6  jz      loc_18000A680
0x18000a5dc  xor     edx, edx; Val
0x18000a5de  mov     [rsp+470h+NumberOfBytesWritten], rdi
0x18000a5e3  mov     r8d, 1FEh; Size
0x18000a5e9  lea     rcx, [rsp+470h+var_430]; void *
0x18000a5ee  lea     r14, [rbp+370h+ArgList]
0x18000a5f5  call    memset$thunk$772440563353939046
0x18000a5fa  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18000a5ff  mov     edx, [rbp+370h+uID]; uID
0x18000a605  lea     r8, [rbp+370h+Buffer]; lpBuffer
0x18000a60c  mov     rcx, rax; hInstance
0x18000a60f  mov     r9d, 0FFh; cchBufferMax
0x18000a615  call    cs:__imp_LoadStringW
0x18000a61b  test    eax, eax
0x18000a61d  jz      short loc_18000A680
0x18000a61f  cmp     eax, 0FFh
0x18000a624  jz      short loc_18000A680
0x18000a626  mov     edx, 0FFh; BufferCount
0x18000a62b  mov     [rsp+20h], r14; ArgList
0x18000a630  lea     r9, [rbp+370h+Buffer]; Format
0x18000a637  lea     rcx, [rsp+470h+var_430]; Buffer
0x18000a63c  lea     r8d, [rdx-1]; MaxCount
0x18000a640  call    _vsnwprintf_s
0x18000a645  lea     rax, [rsp+470h+var_430]
0x18000a64a  mov     dword ptr [rsp+470h+NumberOfBytesWritten], edi
0x18000a64e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a652  inc     r8
0x18000a655  cmp     [rax+r8*2], di
0x18000a65a  jnz     short loc_18000A652
0x18000a65c  mov     rcx, [rbx+10h]; hFile
0x18000a660  lea     r9, [rsp+470h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000a665  add     r8d, r8d; nNumberOfBytesToWrite
0x18000a668  mov     [rsp+20h], rdi; lpOverlapped
0x18000a66d  lea     rdx, [rsp+470h+var_430]; lpBuffer
0x18000a672  call    cs:__imp_WriteFile
0x18000a678  mov     rcx, rbx; this
0x18000a67b  call    ?LogNewline@ShimLog@@QEAAXXZ; ShimLog::LogNewline(void)
0x18000a680  mov     rcx, [rbp+370h+var_30]
0x18000a687  xor     rcx, rsp; StackCookie
0x18000a68a  call    __security_check_cookie
0x18000a68f  add     rsp, 458h
0x18000a696  pop     r14
0x18000a698  pop     rdi
0x18000a699  pop     rbx
0x18000a69a  pop     rbp
0x18000a69b  retn
```

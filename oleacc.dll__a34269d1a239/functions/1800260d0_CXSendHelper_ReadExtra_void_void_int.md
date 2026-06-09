# CXSendHelper::ReadExtra(void *,void *,int)

- ea: `0x1800260d0`
- end: `0x180026149`
- name: `?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z`
- size: `121`
- prototype: `__int64 __fastcall(CXSendHelper *this, char *, void *, int)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x18002473c`
- `0x1800248a0`
- `0x180024a04`
- `0x180024b44`
- `0x180024c84`
- `0x180024df4`
- `0x1800251d8`
- `0x180025320`
- `0x18002546c`
- `0x1800255d8`
- `0x180025744`
- `0x1800258b0`
- `0x180025a1c`
- `0x180025b50`
- `0x180025c84`
- `0x180025d84`

## callees

- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002610d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002610d`

## pseudocode

```c
__int64 __fastcall CXSendHelper::ReadExtra(CXSendHelper *this, char *a2, void *a3, int a4)
{
  if ( !*((_DWORD *)this + 7) )
    return 1;
  if ( a3 )
  {
    if ( ReadProcessMemory(*((HANDLE *)this + 2), a3, a2, *((unsigned int *)this + 7), 0) )
    {
      if ( a4 )
        *(_WORD *)&a2[*((unsigned int *)this + 7) - 2] = 0;
      return 1;
    }
  }
  else if ( a4 )
  {
    *(_WORD *)a2 = 0;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800260d0  mov     [rsp+arg_0], rbx
0x1800260d5  mov     [rsp+arg_8], rsi
0x1800260da  push    rdi
0x1800260db  sub     rsp, 30h
0x1800260df  cmp     dword ptr [rcx+1Ch], 0
0x1800260e3  mov     edi, r9d
0x1800260e6  mov     rax, r8
0x1800260e9  mov     rbx, rdx
0x1800260ec  mov     rsi, rcx
0x1800260ef  jz      short loc_180026125
0x1800260f1  test    rax, rax
0x1800260f4  jz      short loc_18002613A
0x1800260f6  mov     r9d, [rcx+1Ch]; nSize
0x1800260fa  mov     r8, rdx; lpBuffer
0x1800260fd  mov     rcx, [rcx+10h]; hProcess
0x180026101  mov     rdx, rax; lpBaseAddress
0x180026104  mov     [rsp+38h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18002610d  call    cs:__imp_ReadProcessMemory
0x180026113  test    eax, eax
0x180026115  jz      short loc_180026145
0x180026117  test    edi, edi
0x180026119  jz      short loc_180026125
0x18002611b  mov     ecx, [rsi+1Ch]
0x18002611e  xor     eax, eax
0x180026120  mov     [rcx+rbx-2], ax
0x180026125  mov     eax, 1
0x18002612a  mov     rbx, [rsp+38h+arg_0]
0x18002612f  mov     rsi, [rsp+38h+arg_8]
0x180026134  add     rsp, 30h
0x180026138  pop     rdi
0x180026139  retn
0x18002613a  test    edi, edi
0x18002613c  jz      short loc_180026145
0x18002613e  xor     eax, eax
0x180026140  mov     [rdx], ax
0x180026143  jmp     short loc_180026125
0x180026145  xor     eax, eax
0x180026147  jmp     short loc_18002612A
```

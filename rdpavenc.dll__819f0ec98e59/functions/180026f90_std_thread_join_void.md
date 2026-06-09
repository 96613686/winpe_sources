# std::thread::join(void)

- ea: `0x180026f90`
- end: `0x180027005`
- name: `?join@thread@std@@QEAAXXZ`
- size: `117`
- prototype: `void __fastcall(std::thread *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180026410`
- `0x18004c050`
- `0x18004c5f0`
- `0x180064d90`

## callees

- `0x180010bc8`
- `0x180026f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180026fba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180026fba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026fa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026fc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026fc8`

## pseudocode

```c
void __fastcall std::thread::join(std::thread *this)
{
  void *v2; // rdi

  if ( !*((_DWORD *)this + 2) )
    std::_Throw_Cpp_error(1);
  if ( *((_DWORD *)this + 2) == GetCurrentThreadId() )
    std::_Throw_Cpp_error(5);
  v2 = *(void **)this;
  if ( WaitForSingleObjectEx(*(HANDLE *)this, 0xFFFFFFFF, 0) == -1 || !CloseHandle(v2) )
    std::_Throw_Cpp_error(2);
  *(_OWORD *)this = 0;
}

```

## disassembly

```asm
0x180026f90  mov     [rsp+arg_0], rbx
0x180026f95  push    rdi
0x180026f96  sub     rsp, 20h
0x180026f9a  cmp     dword ptr [rcx+8], 0
0x180026f9e  mov     rbx, rcx
0x180026fa1  jz      short loc_180026FFA
0x180026fa3  call    cs:__imp_GetCurrentThreadId
0x180026fa9  cmp     [rbx+8], eax
0x180026fac  jz      short loc_180026FE4
0x180026fae  mov     rdi, [rbx]
0x180026fb1  xor     r8d, r8d; bAlertable
0x180026fb4  mov     rcx, rdi; hHandle
0x180026fb7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180026fba  call    cs:__imp_WaitForSingleObjectEx
0x180026fc0  cmp     eax, 0FFFFFFFFh
0x180026fc3  jz      short loc_180026FEF
0x180026fc5  mov     rcx, rdi; hObject
0x180026fc8  call    cs:__imp_CloseHandle
0x180026fce  test    eax, eax
0x180026fd0  jz      short loc_180026FEF
0x180026fd2  xorps   xmm0, xmm0
0x180026fd5  movdqu  xmmword ptr [rbx], xmm0
0x180026fd9  mov     rbx, [rsp+28h+arg_0]
0x180026fde  add     rsp, 20h
0x180026fe2  pop     rdi
0x180026fe3  retn
0x180026fe4  mov     ecx, 5; int
0x180026fe9  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180026fef  mov     ecx, 2; int
0x180026ff4  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180026ffa  mov     ecx, 1; int
0x180026fff  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

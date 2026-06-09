# __crt_win32_buffer<wchar_t,__crt_win32_buffer_no_resizing>::call_win32_function<_lambda_17b8e77e04f0039ff1429d79b8271fa1_>(_lambda_17b8e77e04f0039ff1429d79b8271fa1_ const &)

- ea: `0x14014704c`
- end: `0x1401470bd`
- name: `??$call_win32_function@V_lambda_17b8e77e04f0039ff1429d79b8271fa1_@@@?$__crt_win32_buffer@_WU__crt_win32_buffer_no_resizing@@@@QEAAHAEBV_lambda_17b8e77e04f0039ff1429d79b8271fa1_@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, LPCWSTR *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140146eb4`
- `0x14015a434`

## callees

- `0x14013fd08`
- `0x14013fd50`
- `0x14014704c`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x140147065`
- `KERNEL32!GetFullPathNameW` at `0x140147065`
- `KERNEL32!GetLastError` at `0x140147072`
- `KERNEL32!GetLastError` at `0x140147072`

## pseudocode

```c
__int64 __fastcall __crt_win32_buffer<wchar_t,__crt_win32_buffer_no_resizing>::call_win32_function<_lambda_17b8e77e04f0039ff1429d79b8271fa1_>(
        __int64 a1,
        LPCWSTR *a2)
{
  DWORD FullPathNameW; // eax
  DWORD LastError; // eax
  __int64 result; // rax

  FullPathNameW = GetFullPathNameW(*a2, *(_DWORD *)(a1 + 24), *(LPWSTR *)(a1 + 16), 0);
  if ( FullPathNameW )
  {
    if ( (unsigned __int64)FullPathNameW > *(_QWORD *)(a1 + 24) )
    {
      if ( *(_BYTE *)(a1 + 40) )
        *(_BYTE *)(a1 + 40) = 0;
      *(_DWORD *)sub_14013FD08() = 34;
      result = 34;
      *(_BYTE *)(a1 + 40) = 0;
      *(_QWORD *)(a1 + 24) = 0;
    }
    else
    {
      *(_QWORD *)(a1 + 32) = FullPathNameW;
      return 0;
    }
  }
  else
  {
    LastError = GetLastError();
    sub_14013FD50(LastError);
    return *(unsigned int *)sub_14013FD08();
  }
  return result;
}

```

## disassembly

```asm
0x14014704c  push    rbx
0x14014704e  sub     rsp, 20h
0x140147052  mov     r8, [rcx+10h]; lpBuffer
0x140147056  mov     rax, rdx
0x140147059  mov     edx, [rcx+18h]; nBufferLength
0x14014705c  mov     rbx, rcx
0x14014705f  xor     r9d, r9d; lpFilePart
0x140147062  mov     rcx, [rax]; lpFileName
0x140147065  call    cs:GetFullPathNameW
0x14014706b  mov     eax, eax
0x14014706d  test    rax, rax
0x140147070  jnz     short loc_140147088
0x140147072  call    cs:__imp_GetLastError
0x140147078  mov     ecx, eax
0x14014707a  call    sub_14013FD50
0x14014707f  call    sub_14013FD08
0x140147084  mov     eax, [rax]
0x140147086  jmp     short loc_1401470B7
0x140147088  cmp     rax, [rbx+18h]
0x14014708c  ja      short loc_140147096
0x14014708e  mov     [rbx+20h], rax
0x140147092  xor     eax, eax
0x140147094  jmp     short loc_1401470B7
0x140147096  cmp     byte ptr [rbx+28h], 0
0x14014709a  jz      short loc_1401470A0
0x14014709c  mov     byte ptr [rbx+28h], 0
0x1401470a0  call    sub_14013FD08
0x1401470a5  mov     ecx, 22h ; '"'
0x1401470aa  mov     [rax], ecx
0x1401470ac  mov     eax, ecx
0x1401470ae  mov     byte ptr [rbx+28h], 0
0x1401470b2  and     qword ptr [rbx+18h], 0
0x1401470b7  add     rsp, 20h
0x1401470bb  pop     rbx
0x1401470bc  retn
```

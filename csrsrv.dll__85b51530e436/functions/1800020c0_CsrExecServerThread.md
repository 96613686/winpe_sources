# CsrExecServerThread

- ea: `0x1800020c0`
- end: `0x1800021dc`
- name: `CsrExecServerThread`
- size: `284`
- prototype: `__int64 __fastcall(PVOID Reserved5, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800020c0`
- `0x180002f60`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800021ce`
- `ntdll!RtlFreeHeap` at `0x1800021ce`
- `ntdll!RtlCreateUserThread` at `0x180002145`
- `ntdll!RtlCreateUserThread` at `0x180002145`
- `ntdll!RtlEnterCriticalSection` at `0x1800020e7`
- `ntdll!RtlEnterCriticalSection` at `0x1800020e7`
- `ntdll!RtlLeaveCriticalSection` at `0x18000219c`
- `ntdll!RtlLeaveCriticalSection` at `0x18000219c`

## pseudocode

```c
__int64 __fastcall CsrExecServerThread(PVOID Reserved5, int a2)
{
  __int64 Thread; // rbx
  NTSTATUS v5; // esi
  __int128 v6; // xmm0
  __int64 v7; // rcx
  __int64 **v8; // rdx
  __int64 *v9; // rbx
  __int128 Reserved8[3]; // [rsp+50h] [rbp-38h] BYREF
  __int64 Reserved7; // [rsp+A0h] [rbp+18h] BYREF

  Reserved7 = 0;
  Reserved8[0] = 0;
  RtlEnterCriticalSection(&CsrProcessStructureLock);
  Thread = CsrAllocateThread(CsrRootProcess);
  if ( Thread )
  {
    v5 = RtlCreateUserThread((PVOID)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0, 0, 0, Reserved5, 0, &Reserved7, Reserved8);
    if ( v5 < 0 )
    {
      RtlFreeHeap(CsrHeap, 0, (PVOID)Thread);
    }
    else
    {
      *(_QWORD *)(Thread + 64) = Reserved7;
      v6 = Reserved8[0];
      v7 = CsrRootProcess + 32;
      *(_DWORD *)(Thread + 72) = a2;
      *(_OWORD *)(Thread + 40) = v6;
      v8 = *(__int64 ***)(v7 + 8);
      if ( *v8 != (__int64 *)v7 )
        __fastfail(3u);
      v9 = (__int64 *)(Thread + 8);
      *v9 = v7;
      v9[1] = (__int64)v8;
      *v8 = v9;
      *(_QWORD *)(v7 + 8) = v9;
    }
  }
  else
  {
    v5 = -1073741801;
  }
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800020c0  push    rbx
0x1800020c2  push    rbp
0x1800020c3  push    rsi
0x1800020c4  push    rdi
0x1800020c5  sub     rsp, 68h
0x1800020c9  mov     rsi, rcx
0x1800020cc  xorps   xmm0, xmm0
0x1800020cf  xor     ebp, ebp
0x1800020d1  lea     rcx, CsrProcessStructureLock; CriticalSection
0x1800020d8  mov     [rsp+88h+arg_10], rbp
0x1800020e0  mov     edi, edx
0x1800020e2  movups  [rsp+88h+var_38], xmm0
0x1800020e7  call    cs:__imp_RtlEnterCriticalSection
0x1800020ee  nop     dword ptr [rax+rax+00h]
0x1800020f3  mov     rcx, cs:CsrRootProcess
0x1800020fa  call    CsrAllocateThread
0x1800020ff  mov     rbx, rax
0x180002102  test    rax, rax
0x180002105  jz      loc_1800021BB
0x18000210b  lea     rax, [rsp+88h+var_38]
0x180002110  xor     r9d, r9d; Reserved2
0x180002113  mov     [rsp+88h+Reserved8], rax; Reserved8
0x180002118  xor     r8d, r8d; Reserved1
0x18000211b  lea     rax, [rsp+88h+arg_10]
0x180002123  xor     edx, edx; OutThreadHandle
0x180002125  mov     [rsp+88h+Reserved7], rax; Reserved7
0x18000212a  mov     rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x180002131  mov     [rsp+88h+Reserved6], rbp; Reserved6
0x180002136  mov     [rsp+88h+Reserved5], rsi; Reserved5
0x18000213b  mov     [rsp+88h+Reserved4], rbp; Reserved4
0x180002140  mov     [rsp+88h+Reserved3], rbp; Reserved3
0x180002145  call    cs:__imp_RtlCreateUserThread
0x18000214c  nop     dword ptr [rax+rax+00h]
0x180002151  mov     esi, eax
0x180002153  test    eax, eax
0x180002155  js      short loc_1800021C2
0x180002157  mov     rcx, [rsp+88h+arg_10]
0x18000215f  mov     [rbx+40h], rcx
0x180002163  movups  xmm0, [rsp+88h+var_38]
0x180002168  mov     rcx, cs:CsrRootProcess
0x18000216f  add     rcx, 20h ; ' '
0x180002173  mov     [rbx+48h], edi
0x180002176  movups  xmmword ptr [rbx+28h], xmm0
0x18000217a  mov     rdx, [rcx+8]
0x18000217e  cmp     [rdx], rcx
0x180002181  jnz     short loc_1800021B4
0x180002183  add     rbx, 8
0x180002187  mov     [rbx], rcx
0x18000218a  mov     [rbx+8], rdx
0x18000218e  mov     [rdx], rbx
0x180002191  mov     [rcx+8], rbx
0x180002195  lea     rcx, CsrProcessStructureLock; CriticalSection
0x18000219c  call    cs:__imp_RtlLeaveCriticalSection
0x1800021a3  nop     dword ptr [rax+rax+00h]
0x1800021a8  mov     eax, esi
0x1800021aa  add     rsp, 68h
0x1800021ae  pop     rdi
0x1800021af  pop     rsi
0x1800021b0  pop     rbp
0x1800021b1  pop     rbx
0x1800021b2  retn
0x1800021b4  mov     ecx, 3
0x1800021b9  int     29h; Win8: RtlFailFast(ecx)
0x1800021bb  mov     esi, 0C0000017h
0x1800021c0  jmp     short loc_180002195
0x1800021c2  mov     rcx, cs:CsrHeap; HeapHandle
0x1800021c9  mov     r8, rbx; BaseAddress
0x1800021cc  xor     edx, edx; Flags
0x1800021ce  call    cs:__imp_RtlFreeHeap
0x1800021d5  nop     dword ptr [rax+rax+00h]
0x1800021da  jmp     short loc_180002195
```

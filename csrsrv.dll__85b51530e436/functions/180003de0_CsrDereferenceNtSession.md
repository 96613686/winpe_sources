# CsrDereferenceNtSession

- ea: `0x180003de0`
- end: `0x180003e94`
- name: `CsrDereferenceNtSession`
- size: `180`
- prototype: `char __fastcall(volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800030a0`
- `0x180003c20`

## callees

- `0x180003de0`
- `0x180003ea0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180003e69`
- `ntdll!RtlEnterCriticalSection` at `0x180003e09`
- `ntdll!RtlEnterCriticalSection` at `0x180003e09`
- `ntdll!RtlLeaveCriticalSection` at `0x180003e44`
- `ntdll!RtlLeaveCriticalSection` at `0x180003e7c`
- `ntdll!RtlLeaveCriticalSection` at `0x180003e44`
- `ntdll!RtlLeaveCriticalSection` at `0x180003e7c`

## pseudocode

```c
char __fastcall CsrDereferenceNtSession(volatile signed __int32 *a1)
{
  signed __int32 v1; // eax
  signed __int32 v3; // eax
  int v4; // ett
  __int64 v5; // rax
  volatile signed __int32 **v6; // rdx
  __int64 v7; // rcx

  v1 = *((_DWORD *)a1 + 5);
  if ( v1 <= 1 || (v4 = *((_DWORD *)a1 + 5), v3 = _InterlockedCompareExchange(a1 + 5, v1 - 1, v1), v4 != v3) )
  {
    RtlEnterCriticalSection(&CsrNtSessionLock);
    if ( _InterlockedExchangeAdd(a1 + 5, 0xFFFFFFFF) == 1 )
    {
      v5 = *(_QWORD *)a1;
      if ( *(volatile signed __int32 **)(*(_QWORD *)a1 + 8LL) != a1
        || (v6 = (volatile signed __int32 **)*((_QWORD *)a1 + 1), *v6 != a1) )
      {
        __fastfail(3u);
      }
      *v6 = (volatile signed __int32 *)v5;
      *(_QWORD *)(v5 + 8) = v6;
      RtlLeaveCriticalSection(&CsrNtSessionLock);
      SmSessionComplete(v7, *((unsigned int *)a1 + 4));
      LOBYTE(v3) = RtlFreeHeap(CsrHeap, 0, (PVOID)a1);
    }
    else
    {
      LOBYTE(v3) = RtlLeaveCriticalSection(&CsrNtSessionLock);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180003de0  push    rbx
0x180003de2  sub     rsp, 20h
0x180003de6  mov     eax, [rcx+14h]
0x180003de9  mov     rbx, rcx
0x180003dec  cmp     eax, 1
0x180003def  jle     short loc_180003E02
0x180003df1  lea     ecx, [rax-1]
0x180003df4  lock cmpxchg [rbx+14h], ecx
0x180003df9  jnz     short loc_180003E02
0x180003dfb  add     rsp, 20h
0x180003dff  pop     rbx
0x180003e00  retn
0x180003e02  lea     rcx, CsrNtSessionLock; CriticalSection
0x180003e09  call    cs:__imp_RtlEnterCriticalSection
0x180003e10  nop     dword ptr [rax+rax+00h]
0x180003e15  mov     eax, 0FFFFFFFFh
0x180003e1a  lock xadd [rbx+14h], eax
0x180003e1f  cmp     eax, 1
0x180003e22  jnz     short loc_180003E75
0x180003e24  mov     rax, [rbx]
0x180003e27  cmp     [rax+8], rbx
0x180003e2b  jnz     short loc_180003E8D
0x180003e2d  mov     rdx, [rbx+8]
0x180003e31  cmp     [rdx], rbx
0x180003e34  jnz     short loc_180003E8D
0x180003e36  mov     [rdx], rax
0x180003e39  lea     rcx, CsrNtSessionLock; CriticalSection
0x180003e40  mov     [rax+8], rdx
0x180003e44  call    cs:__imp_RtlLeaveCriticalSection
0x180003e4b  nop     dword ptr [rax+rax+00h]
0x180003e50  mov     edx, [rbx+10h]
0x180003e53  call    SmSessionComplete
0x180003e58  mov     rcx, cs:CsrHeap
0x180003e5f  mov     r8, rbx
0x180003e62  xor     edx, edx
0x180003e64  add     rsp, 20h
0x180003e68  pop     rbx
0x180003e69  jmp     cs:__imp_RtlFreeHeap
0x180003e75  lea     rcx, CsrNtSessionLock; CriticalSection
0x180003e7c  call    cs:__imp_RtlLeaveCriticalSection
0x180003e83  nop     dword ptr [rax+rax+00h]
0x180003e88  jmp     loc_180003DFB
0x180003e8d  mov     ecx, 3
0x180003e92  int     29h; Win8: RtlFailFast(ecx)
```

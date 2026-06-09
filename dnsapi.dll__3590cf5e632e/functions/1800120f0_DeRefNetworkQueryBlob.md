# DeRefNetworkQueryBlob

- ea: `0x1800120f0`
- end: `0x1800121d2`
- name: `DeRefNetworkQueryBlob`
- size: `226`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011e3c`
- `0x1800317e0`

## callees

- `0x1800120f0`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001215c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001215c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001218a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001219f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001218a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001219f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012144`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001217c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012144`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001217c`

## pseudocode

```c
void __fastcall DeRefNetworkQueryBlob(char *lpMem)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v4; // rax

  if ( lpMem )
  {
    if ( (BYTE3(xmmword_1801119E0) & 4) != 0 )
      WPP_SF_d(1050, 13, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, *(unsigned int *)lpMem);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem, 0xFFFFFFFF) == 1 )
    {
      v2 = (void *)*((_QWORD *)lpMem + 1);
      if ( v2 )
      {
        ProcessHeap = g_hProcessHeap;
        if ( !g_hProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          g_hProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v2);
        *((_QWORD *)lpMem + 1) = 0;
      }
      DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 24));
      v4 = g_hProcessHeap;
      if ( !g_hProcessHeap )
      {
        v4 = GetProcessHeap();
        g_hProcessHeap = v4;
      }
      HeapFree(v4, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x1800120f0  test    rcx, rcx
0x1800120f3  jz      short locret_180012125
0x1800120f5  mov     [rsp+arg_0], rbx
0x1800120fa  push    rdi
0x1800120fb  sub     rsp, 20h
0x1800120ff  mov     rbx, rcx
0x180012102  test    byte ptr cs:xmmword_1801119E0+3, 4
0x180012109  jnz     loc_1800121B4
0x18001210f  or      eax, 0FFFFFFFFh
0x180012112  lock xadd [rbx], eax
0x180012116  cmp     eax, 1
0x180012119  jz      short loc_180012127
0x18001211b  mov     rbx, [rsp+28h+arg_0]
0x180012120  add     rsp, 20h
0x180012124  pop     rdi
0x180012125  retn
0x180012127  mov     rdi, [rbx+8]
0x18001212b  test    rdi, rdi
0x18001212e  jz      short loc_180012158
0x180012130  mov     rax, cs:g_hProcessHeap
0x180012137  test    rax, rax
0x18001213a  jz      short loc_18001219F
0x18001213c  mov     r8, rdi; lpMem
0x18001213f  xor     edx, edx; dwFlags
0x180012141  mov     rcx, rax; hHeap
0x180012144  call    cs:__imp_HeapFree
0x18001214b  nop     dword ptr [rax+rax+00h]
0x180012150  mov     qword ptr [rbx+8], 0
0x180012158  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001215c  call    cs:__imp_DeleteCriticalSection
0x180012163  nop     dword ptr [rax+rax+00h]
0x180012168  mov     rax, cs:g_hProcessHeap
0x18001216f  test    rax, rax
0x180012172  jz      short loc_18001218A
0x180012174  mov     r8, rbx; lpMem
0x180012177  xor     edx, edx; dwFlags
0x180012179  mov     rcx, rax; hHeap
0x18001217c  call    cs:__imp_HeapFree
0x180012183  nop     dword ptr [rax+rax+00h]
0x180012188  jmp     short loc_18001211B
0x18001218a  call    cs:__imp_GetProcessHeap
0x180012191  nop     dword ptr [rax+rax+00h]
0x180012196  mov     cs:g_hProcessHeap, rax
0x18001219d  jmp     short loc_180012174
0x18001219f  call    cs:__imp_GetProcessHeap
0x1800121a6  nop     dword ptr [rax+rax+00h]
0x1800121ab  mov     cs:g_hProcessHeap, rax
0x1800121b2  jmp     short loc_18001213C
0x1800121b4  mov     r9d, [rbx]
0x1800121b7  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x1800121be  mov     edx, 0Dh
0x1800121c3  mov     ecx, 41Ah
0x1800121c8  call    WPP_SF_d
0x1800121cd  jmp     loc_18001210F
```

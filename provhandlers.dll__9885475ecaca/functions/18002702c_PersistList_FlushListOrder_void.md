# PersistList::FlushListOrder(void)

- ea: `0x18002702c`
- end: `0x180027152`
- name: `?FlushListOrder@PersistList@@AEAAJXZ`
- size: `294`
- prototype: `__int64 __fastcall(PersistList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180028720`

## callees

- `0x18002702c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800270c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800270c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800270cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800270cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002708d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002708d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027056`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027056`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002711d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027132`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002711d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027064`
- `DMCmnUtils!CopyString` at `0x1800270dd`
- `DMCmnUtils!CopyString` at `0x1800270dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistList::FlushListOrder(PersistList *this)
{
  unsigned __int64 v1; // rbx
  HANDLE ProcessHeap; // rax
  void *v4; // r15
  signed int LastError; // eax
  int v6; // ebx
  unsigned __int16 **v7; // r14
  __int64 v8; // r12
  __int64 v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  const unsigned __int16 *v11; // rbx
  __int64 i; // rdi

  v1 = 8LL * *((unsigned int *)this + 4);
  if ( v1 > 0xFFFFFFFF )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v4 = ProcessHeap;
    if ( ProcessHeap )
    {
      v7 = (unsigned __int16 **)HeapAlloc(ProcessHeap, 8u, (unsigned int)v1);
      if ( v7 )
      {
        v8 = 0;
        if ( *((_DWORD *)this + 4) )
        {
          while ( 1 )
          {
            v9 = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v8);
            v10 = (struct _RTL_CRITICAL_SECTION *)(v9 + 32);
            EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 32));
            v11 = *(const unsigned __int16 **)(v9 + 24);
            LeaveCriticalSection(v10);
            v6 = CopyString(v11, 0xFFFFFFFF, &v7[v8]);
            if ( v6 < 0 )
              break;
            v8 = (unsigned int)(v8 + 1);
            if ( (unsigned int)v8 >= *((_DWORD *)this + 4) )
              goto LABEL_10;
          }
        }
        else
        {
LABEL_10:
          v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 4) + 24LL))(
                 *((_QWORD *)this + 4),
                 v7);
        }
        for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
          HeapFree(v4, 0, v7[i]);
        HeapFree(v4, 0, v7);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002702c  push    rbx
0x18002702e  push    rbp
0x18002702f  push    rsi
0x180027030  push    rdi
0x180027031  push    r12
0x180027033  push    r13
0x180027035  push    r14
0x180027037  push    r15
0x180027039  sub     rsp, 28h
0x18002703d  mov     ebx, [rcx+10h]
0x180027040  mov     r13d, 0FFFFFFFFh
0x180027046  shl     rbx, 3
0x18002704a  mov     rbp, rcx
0x18002704d  cmp     rbx, r13
0x180027050  ja      loc_18002713A
0x180027056  call    cs:__imp_GetProcessHeap
0x18002705c  mov     r15, rax
0x18002705f  test    rax, rax
0x180027062  jnz     short loc_180027082
0x180027064  call    cs:__imp_GetLastError
0x18002706a  mov     ebx, eax
0x18002706c  test    eax, eax
0x18002706e  jle     loc_18002713F
0x180027074  movzx   ebx, ax
0x180027077  or      ebx, 80070000h
0x18002707d  jmp     loc_18002713F
0x180027082  mov     r8d, ebx; dwBytes
0x180027085  mov     edx, 8; dwFlags
0x18002708a  mov     rcx, r15; hHeap
0x18002708d  call    cs:__imp_HeapAlloc
0x180027093  mov     r14, rax
0x180027096  test    rax, rax
0x180027099  jnz     short loc_1800270A5
0x18002709b  mov     ebx, 8007000Eh
0x1800270a0  jmp     loc_18002713F
0x1800270a5  mov     r8d, [rbp+10h]
0x1800270a9  xor     r12d, r12d
0x1800270ac  test    r8d, r8d
0x1800270af  jz      short loc_1800270F5
0x1800270b1  mov     rax, [rbp+8]
0x1800270b5  mov     rbx, [rax+r12*8]
0x1800270b9  lea     rdi, [rbx+20h]
0x1800270bd  mov     rcx, rdi; lpCriticalSection
0x1800270c0  call    cs:__imp_EnterCriticalSection
0x1800270c6  mov     rbx, [rbx+18h]
0x1800270ca  mov     rcx, rdi; lpCriticalSection
0x1800270cd  call    cs:__imp_LeaveCriticalSection
0x1800270d3  lea     r8, [r14+r12*8]
0x1800270d7  mov     edx, r13d
0x1800270da  mov     rcx, rbx
0x1800270dd  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800270e3  mov     ebx, eax
0x1800270e5  test    eax, eax
0x1800270e7  js      short loc_18002710A
0x1800270e9  mov     r8d, [rbp+10h]
0x1800270ed  inc     r12d
0x1800270f0  cmp     r12d, r8d
0x1800270f3  jb      short loc_1800270B1
0x1800270f5  mov     rcx, [rbp+20h]
0x1800270f9  mov     rdx, r14
0x1800270fc  mov     rax, [rcx]
0x1800270ff  mov     rax, [rax+18h]
0x180027103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027108  mov     ebx, eax
0x18002710a  xor     edi, edi
0x18002710c  mov     rsi, r14
0x18002710f  cmp     [rbp+10h], edi
0x180027112  jbe     short loc_18002712A
0x180027114  mov     r8, [rsi+rdi*8]; lpMem
0x180027118  xor     edx, edx; dwFlags
0x18002711a  mov     rcx, r15; hHeap
0x18002711d  call    cs:__imp_HeapFree
0x180027123  inc     edi
0x180027125  cmp     edi, [rbp+10h]
0x180027128  jb      short loc_180027114
0x18002712a  mov     r8, r14; lpMem
0x18002712d  xor     edx, edx; dwFlags
0x18002712f  mov     rcx, r15; hHeap
0x180027132  call    cs:__imp_HeapFree
0x180027138  jmp     short loc_18002713F
0x18002713a  mov     ebx, 80070216h
0x18002713f  mov     eax, ebx
0x180027141  add     rsp, 28h
0x180027145  pop     r15
0x180027147  pop     r14
0x180027149  pop     r13
0x18002714b  pop     r12
0x18002714d  pop     rdi
0x18002714e  pop     rsi
0x18002714f  pop     rbp
0x180027150  pop     rbx
0x180027151  retn
```

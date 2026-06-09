# PersistList::FlushListOrder(void)

- ea: `0x180014620`
- end: `0x180014746`
- name: `?FlushListOrder@PersistList@@AEAAJXZ`
- size: `294`
- prototype: `__int64 __fastcall(PersistList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800142a0`
- `0x180014f80`

## callees

- `0x180014620`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014711`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014726`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014711`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014726`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014681`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014681`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001464a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001464a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014658`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800146c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800146c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800146b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800146b4`
- `DMCmnUtils!CopyString` at `0x1800146d1`
- `DMCmnUtils!CopyString` at `0x1800146d1`

## pseudocode

```c
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
0x180014620  push    rbx
0x180014622  push    rbp
0x180014623  push    rsi
0x180014624  push    rdi
0x180014625  push    r12
0x180014627  push    r13
0x180014629  push    r14
0x18001462b  push    r15
0x18001462d  sub     rsp, 28h
0x180014631  mov     ebx, [rcx+10h]
0x180014634  mov     r13d, 0FFFFFFFFh
0x18001463a  shl     rbx, 3
0x18001463e  mov     rbp, rcx
0x180014641  cmp     rbx, r13
0x180014644  ja      loc_18001472E
0x18001464a  call    cs:__imp_GetProcessHeap
0x180014650  mov     r15, rax
0x180014653  test    rax, rax
0x180014656  jnz     short loc_180014676
0x180014658  call    cs:__imp_GetLastError
0x18001465e  mov     ebx, eax
0x180014660  test    eax, eax
0x180014662  jle     loc_180014733
0x180014668  movzx   ebx, ax
0x18001466b  or      ebx, 80070000h
0x180014671  jmp     loc_180014733
0x180014676  mov     r8d, ebx; dwBytes
0x180014679  mov     edx, 8; dwFlags
0x18001467e  mov     rcx, r15; hHeap
0x180014681  call    cs:__imp_HeapAlloc
0x180014687  mov     r14, rax
0x18001468a  test    rax, rax
0x18001468d  jnz     short loc_180014699
0x18001468f  mov     ebx, 8007000Eh
0x180014694  jmp     loc_180014733
0x180014699  mov     r8d, [rbp+10h]
0x18001469d  xor     r12d, r12d
0x1800146a0  test    r8d, r8d
0x1800146a3  jz      short loc_1800146E9
0x1800146a5  mov     rax, [rbp+8]
0x1800146a9  mov     rbx, [rax+r12*8]
0x1800146ad  lea     rdi, [rbx+20h]
0x1800146b1  mov     rcx, rdi; lpCriticalSection
0x1800146b4  call    cs:__imp_EnterCriticalSection
0x1800146ba  mov     rbx, [rbx+18h]
0x1800146be  mov     rcx, rdi; lpCriticalSection
0x1800146c1  call    cs:__imp_LeaveCriticalSection
0x1800146c7  lea     r8, [r14+r12*8]
0x1800146cb  mov     edx, r13d
0x1800146ce  mov     rcx, rbx
0x1800146d1  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800146d7  mov     ebx, eax
0x1800146d9  test    eax, eax
0x1800146db  js      short loc_1800146FE
0x1800146dd  mov     r8d, [rbp+10h]
0x1800146e1  inc     r12d
0x1800146e4  cmp     r12d, r8d
0x1800146e7  jb      short loc_1800146A5
0x1800146e9  mov     rcx, [rbp+20h]
0x1800146ed  mov     rdx, r14
0x1800146f0  mov     rax, [rcx]
0x1800146f3  mov     rax, [rax+18h]
0x1800146f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146fc  mov     ebx, eax
0x1800146fe  xor     edi, edi
0x180014700  mov     rsi, r14
0x180014703  cmp     [rbp+10h], edi
0x180014706  jbe     short loc_18001471E
0x180014708  mov     r8, [rsi+rdi*8]; lpMem
0x18001470c  xor     edx, edx; dwFlags
0x18001470e  mov     rcx, r15; hHeap
0x180014711  call    cs:__imp_HeapFree
0x180014717  inc     edi
0x180014719  cmp     edi, [rbp+10h]
0x18001471c  jb      short loc_180014708
0x18001471e  mov     r8, r14; lpMem
0x180014721  xor     edx, edx; dwFlags
0x180014723  mov     rcx, r15; hHeap
0x180014726  call    cs:__imp_HeapFree
0x18001472c  jmp     short loc_180014733
0x18001472e  mov     ebx, 80070216h
0x180014733  mov     eax, ebx
0x180014735  add     rsp, 28h
0x180014739  pop     r15
0x18001473b  pop     r14
0x18001473d  pop     r13
0x18001473f  pop     r12
0x180014741  pop     rdi
0x180014742  pop     rsi
0x180014743  pop     rbp
0x180014744  pop     rbx
0x180014745  retn
```

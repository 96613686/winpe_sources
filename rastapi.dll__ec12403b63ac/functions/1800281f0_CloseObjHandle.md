# CloseObjHandle

- ea: `0x1800281f0`
- end: `0x18002838f`
- name: `CloseObjHandle`
- size: `415`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x1800226f0`
- `0x180023610`
- `0x180023a14`
- `0x1800257e4`
- `0x180025e40`
- `0x18002619c`

## callees

- `0x1800281ac`
- `0x1800281f0`
- `0x180028db8`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028286`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028286`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028294`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028294`
- `rtutils!TracePrintfA` at `0x18002835c`
- `rtutils!TracePrintfA` at `0x18002835c`

## pseudocode

```c
__int64 __fastcall CloseObjHandle(unsigned int a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rbp
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  int v8; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v9[2044]; // [rsp+24h] [rbp-834h] BYREF

  v2 = a1 >> 1;
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  AcquireWriteLock(&CriticalSection);
  v3 = (unsigned __int16)v2;
  if ( (unsigned __int16)v2 < (unsigned int)dword_18003EBBC
    && (v4 = (struct _RTL_CRITICAL_SECTION *)((char *)lpMem + 72 * (unsigned __int16)v2),
        HIWORD(v2) == LOWORD(v4[1].LockSemaphore))
    && v4[1].OwningThread )
  {
    AcquireWriteLock(v4);
    v5 = (void *)*((_QWORD *)lpMem + 9 * (unsigned __int16)v2 + 7);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
    *((_QWORD *)lpMem + 9 * v3 + 7) = 0;
    *((_WORD *)lpMem + 36 * v3 + 32) = 0;
    *((_WORD *)lpMem + 36 * v3 + 33) = HIWORD(dword_18003EBB8);
    ++dword_18003EBC0;
    HIWORD(dword_18003EBB8) = v3;
    ReleaseWriteLock((struct _RTL_CRITICAL_SECTION *)((char *)lpMem + 72 * v3));
    ReleaseWriteLock(&CriticalSection);
    return 0;
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString((wchar_t *)&v8, L"CloseObjHandle: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "CloseObjHandle: Bad handle (0x%x)", a1);
    }
    ReleaseWriteLock(&CriticalSection);
    return 6;
  }
}

```

## disassembly

```asm
0x1800281f0  push    rbx
0x1800281f2  push    rbp
0x1800281f3  push    rsi
0x1800281f4  push    rdi
0x1800281f5  sub     rsp, 838h
0x1800281fc  mov     rax, cs:__security_cookie
0x180028203  xor     rax, rsp
0x180028206  mov     [rsp+858h+var_38], rax
0x18002820e  mov     ebx, ecx
0x180028210  mov     esi, ecx
0x180028212  xor     eax, eax
0x180028214  shr     ebx, 1
0x180028216  lea     rcx, [rsp+858h+var_834]; void *
0x18002821b  mov     [rsp+858h+var_838], eax
0x18002821f  xor     edx, edx; Val
0x180028221  mov     r8d, 7FCh; Size
0x180028227  call    memset_0
0x18002822c  lea     rcx, CriticalSection; lpCriticalSection
0x180028233  call    AcquireWriteLock
0x180028238  movzx   ebp, bx
0x18002823b  cmp     ebp, cs:dword_18003EBBC
0x180028241  jnb     loc_1800282F8
0x180028247  mov     rax, cs:lpMem
0x18002824e  lea     rdi, ds:0[rbp*8]
0x180028256  add     rdi, rbp
0x180028259  shr     ebx, 10h
0x18002825c  lea     rcx, [rax+rdi*8]; lpCriticalSection
0x180028260  cmp     bx, [rcx+40h]
0x180028264  jnz     loc_1800282F8
0x18002826a  cmp     qword ptr [rcx+38h], 0
0x18002826f  jz      loc_1800282F8
0x180028275  call    AcquireWriteLock
0x18002827a  mov     rax, cs:lpMem
0x180028281  mov     rbx, [rax+rdi*8+38h]
0x180028286  call    cs:__imp_GetProcessHeap
0x18002828c  mov     r8, rbx; lpMem
0x18002828f  xor     edx, edx; dwFlags
0x180028291  mov     rcx, rax; hHeap
0x180028294  call    cs:__imp_HeapFree
0x18002829a  mov     rax, cs:lpMem
0x1800282a1  xor     edx, edx
0x1800282a3  mov     qword ptr [rax+rdi*8+38h], 0
0x1800282ac  mov     rax, cs:lpMem
0x1800282b3  mov     [rax+rdi*8+40h], dx
0x1800282b8  movzx   eax, word ptr cs:dword_18003EBB8+2
0x1800282bf  mov     rdx, cs:lpMem
0x1800282c6  mov     [rdx+rdi*8+42h], ax
0x1800282cb  mov     rax, cs:lpMem
0x1800282d2  inc     cs:dword_18003EBC0
0x1800282d8  mov     word ptr cs:dword_18003EBB8+2, bp
0x1800282df  lea     rcx, [rax+rdi*8]
0x1800282e3  call    ReleaseWriteLock
0x1800282e8  lea     rcx, CriticalSection
0x1800282ef  call    ReleaseWriteLock
0x1800282f4  xor     eax, eax
0x1800282f6  jmp     short loc_180028373
0x1800282f8  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800282ff  jz      short loc_180028347
0x180028301  cmp     cs:qword_18003EC40, 0
0x180028309  jz      short loc_180028362
0x18002830b  xor     eax, eax
0x18002830d  lea     rdx, aCloseobjhandle; "CloseObjHandle: Bad handle (0x%x)"
0x180028314  mov     r8d, esi
0x180028317  mov     word ptr [rsp+858h+var_838], ax
0x18002831c  lea     rcx, [rsp+858h+var_838]
0x180028321  call    FormatRRASErrorString
0x180028326  mov     rdx, cs:qword_18003EC40
0x18002832d  lea     r8, [rsp+858h+var_838]
0x180028332  mov     rcx, cs:gNdpspEtwContext
0x180028339  mov     rax, cs:gNdpspTemplateFunc
0x180028340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028345  jmp     short loc_180028362
0x180028347  mov     ecx, cs:dwTraceId; dwTraceID
0x18002834d  cmp     ecx, 0FFFFFFFFh
0x180028350  jz      short loc_180028362
0x180028352  mov     r8d, esi
0x180028355  lea     rdx, aCloseobjhandle_0; "CloseObjHandle: Bad handle (0x%x)"
0x18002835c  call    cs:__imp_TracePrintfA
0x180028362  lea     rcx, CriticalSection
0x180028369  call    ReleaseWriteLock
0x18002836e  mov     eax, 6
0x180028373  mov     rcx, [rsp+858h+var_38]
0x18002837b  xor     rcx, rsp; StackCookie
0x18002837e  call    __security_check_cookie
0x180028383  add     rsp, 838h
0x18002838a  pop     rdi
0x18002838b  pop     rsi
0x18002838c  pop     rbp
0x18002838d  pop     rbx
0x18002838e  retn
```

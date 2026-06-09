# CaptureStack(long,uint)

- ea: `0x180167278`
- end: `0x18016730e`
- name: `?CaptureStack@@YAXJI@Z`
- size: `150`
- prototype: `void __fastcall(int, unsigned int)`
- caller_count: `67`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18011a720`
- `0x18011a850`
- `0x18011d394`
- `0x18011db00`
- `0x18011e500`
- `0x18011f190`
- `0x1801226e8`
- `0x1801227e0`
- `0x18012a85c`
- `0x18012cd9c`
- `0x18012cf34`
- `0x18012ec40`
- `0x1801367c0`
- `0x18013bb50`
- `0x18013cbd0`
- `0x18013ee90`
- `0x180141138`
- `0x1801415d8`
- `0x180145b4c`
- `0x180147a54`
- `0x18014fb80`
- `0x180152858`
- `0x180154068`
- `0x180158664`
- `0x18015efc8`
- `0x18015fd5c`
- `0x180165b38`
- `0x180165f80`
- `0x180166f0c`
- `0x180167110`
- `0x180167878`
- `0x18016d4b4`
- `0x18016daac`
- `0x180178c74`
- `0x180178df0`
- `0x18017a7a8`
- `0x18017dcf0`
- `0x18017de30`
- `0x180186b94`
- `0x1801881a0`
- `0x1801892b0`
- `0x18018a49c`
- `0x1801924e4`
- `0x1801936c0`
- `0x18019f66c`
- `0x1801ab344`
- `0x1801c7b18`
- `0x1801c85b0`
- `0x1801d01c4`
- `0x1801d308c`

## callees

- `0x180167278`
- `0x1801e90c0`
- `0x1802066a4`
- `0x180212f4c`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x1801672da`
- `ntdll!RtlCaptureStackBackTrace` at `0x1801672da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801672c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801672c0`

## pseudocode

```c
void __fastcall CaptureStack(int a1, const char *a2)
{
  int v2; // esi
  volatile int v4; // ecx
  __int64 v5; // rdx
  struct StackCaptureFrame near **v6; // rbx

  v2 = (int)a2;
  if ( !a1 )
  {
    FailAssert(0x7Bu, a2);
    __debugbreak();
  }
  EnsureStackCaptureRegisteredWithWER();
  do
  {
    v4 = g_nCurrentStackCaptureIndex;
    v5 = ((_BYTE)g_nCurrentStackCaptureIndex + 1) & 7;
  }
  while ( v4 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v5, g_nCurrentStackCaptureIndex) );
  v6 = &g_StackCaptureFrames + 10 * v5;
  *((_DWORD *)v6 + 16) = a1;
  *((_DWORD *)v6 + 17) = v2;
  *((_DWORD *)v6 + 18) = GetCurrentThreadId();
  *v6 = 0;
  if ( !RtlCaptureStackBackTrace(1u, 8u, (PVOID *)v6, 0) )
    memset_0(v6, 224, 0x40u);
}

```

## disassembly

```asm
0x180167278  push    rbx
0x18016727a  push    rbp
0x18016727b  push    rsi
0x18016727c  push    rdi
0x18016727d  sub     rsp, 28h
0x180167281  mov     esi, edx
0x180167283  mov     edi, ecx
0x180167285  test    ecx, ecx
0x180167287  jz      short loc_1801672EE
0x180167289  call    ?EnsureStackCaptureRegisteredWithWER@@YAXXZ; EnsureStackCaptureRegisteredWithWER(void)
0x18016728e  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x180167294  mov     eax, ecx
0x180167296  lea     edx, [rcx+1]
0x180167299  and     edx, 7
0x18016729c  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x1801672a4  cmp     ecx, eax
0x1801672a6  jnz     short loc_18016728E
0x1801672a8  lea     rbx, [rdx+rdx*4]
0x1801672ac  lea     rax, ?g_StackCaptureFrames@@3PAUStackCaptureFrame@@A; StackCaptureFrame near * g_StackCaptureFrames
0x1801672b3  shl     rbx, 4
0x1801672b7  add     rbx, rax
0x1801672ba  mov     [rbx+40h], edi
0x1801672bd  mov     [rbx+44h], esi
0x1801672c0  call    cs:__imp_GetCurrentThreadId
0x1801672c6  mov     [rbx+48h], eax
0x1801672c9  xor     r9d, r9d; BackTraceHash
0x1801672cc  xor     eax, eax
0x1801672ce  mov     r8, rbx; BackTrace
0x1801672d1  mov     [rbx], rax
0x1801672d4  lea     edx, [rax+8]; FramesToCapture
0x1801672d7  lea     ecx, [rax+1]; FramesToSkip
0x1801672da  call    cs:__imp_RtlCaptureStackBackTrace
0x1801672e0  test    ax, ax
0x1801672e3  jz      short loc_1801672F9
0x1801672e5  add     rsp, 28h
0x1801672e9  pop     rdi
0x1801672ea  pop     rsi
0x1801672eb  pop     rbp
0x1801672ec  pop     rbx
0x1801672ed  retn
0x1801672ee  mov     ecx, 7Bh ; '{'; unsigned int
0x1801672f3  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x1801672f8  int     3; Trap to Debugger
0x1801672f9  mov     edx, 0E0h; Val
0x1801672fe  mov     r8d, 40h ; '@'; Size
0x180167304  mov     rcx, rbx; void *
0x180167307  call    memset_0
0x18016730c  jmp     short loc_1801672E5
```

# DoStackCaptureInternal(uint,long)

- ea: `0x18019ea10`
- end: `0x18019eb2a`
- name: `?DoStackCaptureInternal@@YAXIJ@Z`
- size: `282`
- prototype: `void __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001fd58`

## callees

- `0x18019ea10`
- `0x18019eb30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019eb04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019eb04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019eaf0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019eaf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18019eaa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18019eaa0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18019eaaa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18019eaaa`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18019ead2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18019ead2`

## pseudocode

```c
void __fastcall DoStackCaptureInternal(__int64 a1, int a2)
{
  __int64 *i; // rcx
  volatile int v4; // ecx
  __int64 v5; // rdx
  _DWORD *v6; // rbx
  __int64 v7; // rdi
  char *v8; // rbx
  HANDLE ProcessHeap; // rax
  __m128i si128; // xmm0

  if ( a2 )
  {
    for ( i = &qword_1805DBF68;
          i != (__int64 *)((char *)&qword_1805DBF68 + 4 * (unsigned int)dword_1805DBF60);
          i = (__int64 *)((char *)i + 4) )
    {
      if ( a2 == *(_DWORD *)i )
        return;
    }
    if ( !_InterlockedCompareExchange(&dword_1805DBF98, 1, 0) )
    {
      ProcessHeap = GetProcessHeap();
      qword_1805DBF90 = HeapAlloc(ProcessHeap, 8u, 0x2800u);
    }
    if ( qword_1805DBF90 )
    {
      EnsureStackCaptureRegisteredWithWER();
      do
      {
        v4 = g_nCurrentStackCaptureIndex;
        v5 = (unsigned __int8)(g_nCurrentStackCaptureIndex + 1);
      }
      while ( v4 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v5, g_nCurrentStackCaptureIndex) );
      v6 = qword_1805DBF90;
      v7 = 5 * v5;
      *((_DWORD *)qword_1805DBF90 + 10 * v5) = a2;
      v6[2 * v7 + 1] = GetCurrentThreadId();
      v6[2 * v7 + 2] = GetTickCount();
      v8 = (char *)&v6[2 * v7];
      *((_OWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 4) = 0;
      if ( !RtlCaptureStackBackTrace(1u, 3u, (PVOID *)v8 + 2, 0) )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm_e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0);
        *((__m128i *)v8 + 1) = si128;
        *((_QWORD *)v8 + 4) = si128.m128i_i64[0];
      }
    }
  }
}

```

## disassembly

```asm
0x18019ea10  test    edx, edx
0x18019ea12  jz      locret_18019EAEF
0x18019ea18  mov     [rsp+arg_8], rbx
0x18019ea1d  mov     [rsp+arg_10], rbp
0x18019ea22  push    rsi
0x18019ea23  push    rdi
0x18019ea24  push    r14
0x18019ea26  sub     rsp, 20h
0x18019ea2a  mov     eax, cs:dword_1805DBF60
0x18019ea30  lea     rcx, qword_1805DBF68
0x18019ea37  mov     esi, edx
0x18019ea39  xor     ebp, ebp
0x18019ea3b  lea     rdx, [rcx+rax*4]
0x18019ea3f  cmp     rcx, rdx
0x18019ea42  jz      short loc_18019EA52
0x18019ea44  cmp     esi, [rcx]
0x18019ea46  jz      loc_18019EADD
0x18019ea4c  add     rcx, 4
0x18019ea50  jmp     short loc_18019EA3F
0x18019ea52  xor     eax, eax
0x18019ea54  lea     r14d, [rax+1]
0x18019ea58  lock cmpxchg cs:dword_1805DBF98, r14d
0x18019ea61  jz      loc_18019EAF0
0x18019ea67  mov     rax, cs:qword_1805DBF90
0x18019ea6e  test    rax, rax
0x18019ea71  jz      short loc_18019EADD
0x18019ea73  call    ?EnsureStackCaptureRegisteredWithWER@@YAXXZ; EnsureStackCaptureRegisteredWithWER(void)
0x18019ea78  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x18019ea7e  lea     eax, [rcx+1]
0x18019ea81  movzx   edx, al
0x18019ea84  mov     eax, ecx
0x18019ea86  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x18019ea8e  cmp     ecx, eax
0x18019ea90  jnz     short loc_18019EA78
0x18019ea92  mov     rbx, cs:qword_1805DBF90
0x18019ea99  lea     rdi, [rdx+rdx*4]
0x18019ea9d  mov     [rbx+rdi*8], esi
0x18019eaa0  call    cs:__imp_GetCurrentThreadId
0x18019eaa6  mov     [rbx+rdi*8+4], eax
0x18019eaaa  call    cs:__imp_GetTickCount
0x18019eab0  mov     [rbx+rdi*8+8], eax
0x18019eab4  xorps   xmm0, xmm0
0x18019eab7  lea     rbx, [rbx+rdi*8]
0x18019eabb  xor     r9d, r9d; BackTraceHash
0x18019eabe  xor     eax, eax
0x18019eac0  lea     r8, [rbx+10h]; BackTrace
0x18019eac4  movups  xmmword ptr [rbx+10h], xmm0
0x18019eac8  mov     ecx, r14d; FramesToSkip
0x18019eacb  mov     [rbx+20h], rax
0x18019eacf  lea     edx, [rax+3]; FramesToCapture
0x18019ead2  call    cs:__imp_RtlCaptureStackBackTrace
0x18019ead8  test    ax, ax
0x18019eadb  jz      short loc_18019EB16
0x18019eadd  mov     rbx, [rsp+38h+arg_8]
0x18019eae2  mov     rbp, [rsp+38h+arg_10]
0x18019eae7  add     rsp, 20h
0x18019eaeb  pop     r14
0x18019eaed  pop     rdi
0x18019eaee  pop     rsi
0x18019eaef  retn
0x18019eaf0  call    cs:__imp_GetProcessHeap
0x18019eaf6  mov     edx, 8; dwFlags
0x18019eafb  mov     r8d, 2800h; dwBytes
0x18019eb01  mov     rcx, rax; hHeap
0x18019eb04  call    cs:__imp_HeapAlloc
0x18019eb0a  mov     cs:qword_1805DBF90, rax
0x18019eb11  jmp     loc_18019EA67
0x18019eb16  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x18019eb1e  movups  xmmword ptr [rbx+10h], xmm0
0x18019eb22  movq    qword ptr [rbx+20h], xmm0
0x18019eb28  jmp     short loc_18019EADD
```

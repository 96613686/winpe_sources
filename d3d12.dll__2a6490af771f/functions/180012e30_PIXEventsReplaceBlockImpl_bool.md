# PIXEventsReplaceBlockImpl(bool)

- ea: `0x180012e30`
- end: `0x180012f54`
- name: `?PIXEventsReplaceBlockImpl@@YA_K_N@Z`
- size: `292`
- prototype: `unsigned __int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180010760`

## callees

- `0x1800027d0`
- `0x180011b3c`
- `0x180012878`
- `0x180012e30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012eae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012eae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012eb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012eb7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012e5a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012e8e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012f11`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012e5a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012e8e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012f11`

## pseudocode

```c
LARGE_INTEGER __fastcall PIXEventsReplaceBlockImpl(char a1)
{
  LARGE_INTEGER v1; // rbx
  unsigned int v3; // ecx
  LARGE_INTEGER *v4; // rdi
  LARGE_INTEGER v5; // rsi
  LARGE_INTEGER v6; // rax
  DWORD CurrentThreadId; // r15d
  DWORD CurrentProcessId; // r12d
  LARGE_INTEGER result; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp+38h] BYREF

  v1.QuadPart = 0;
  if ( a1 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v1 = PerformanceCount;
  }
  v4 = (LARGE_INTEGER *)PIXGetThreadInfo();
  v5 = *v4;
  PerformanceCount = v5;
  if ( v5.QuadPart )
  {
    if ( a1 )
    {
      v6 = v1;
    }
    else
    {
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v6 = PerformanceCount;
    }
    *(LARGE_INTEGER *)(v5.QuadPart + 40) = v6;
    PIXRecordTimingCaptureBlob(v3, (unsigned __int8 *)v5.QuadPart);
    v4[2].QuadPart = v5.QuadPart + 48;
  }
  else
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    if ( (int)PEvtAllocBlk(0, &PerformanceCount) < 0 )
    {
      v4->QuadPart = 0;
      result.QuadPart = 0;
      v4[1].QuadPart = 0;
      v4[2].QuadPart = -1;
      return result;
    }
    v5 = PerformanceCount;
    *v4 = PerformanceCount;
    v4[2].QuadPart = v5.QuadPart + 48;
    v4[1].QuadPart = v5.QuadPart + 15872;
    *(_QWORD *)(v5.QuadPart + 48) = 1048448;
    *(_DWORD *)(v5.QuadPart + 24) = CurrentThreadId;
    *(_DWORD *)(v5.QuadPart + 28) = CurrentProcessId;
  }
  *(_QWORD *)(v5.QuadPart + 40) = -1;
  if ( !a1 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v1 = PerformanceCount;
  }
  *(LARGE_INTEGER *)(v5.QuadPart + 32) = v1;
  return v1;
}

```

## disassembly

```asm
0x180012e30  mov     [rsp-28h+arg_0], rbx
0x180012e35  mov     [rsp-28h+arg_10], rsi
0x180012e3a  push    rbp
0x180012e3b  push    rdi
0x180012e3c  push    r12
0x180012e3e  push    r14
0x180012e40  push    r15
0x180012e42  mov     rbp, rsp
0x180012e45  sub     rsp, 20h
0x180012e49  xor     ebx, ebx
0x180012e4b  mov     r14b, cl
0x180012e4e  test    cl, cl
0x180012e50  jz      short loc_180012E64
0x180012e52  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180012e56  mov     qword ptr [rbp+PerformanceCount], rbx
0x180012e5a  call    cs:__imp_QueryPerformanceCounter
0x180012e60  mov     rbx, qword ptr [rbp+PerformanceCount]
0x180012e64  call    PIXGetThreadInfo
0x180012e69  mov     rdi, rax
0x180012e6c  mov     rsi, [rax]
0x180012e6f  mov     qword ptr [rbp+PerformanceCount], rsi
0x180012e73  test    rsi, rsi
0x180012e76  jz      short loc_180012EAE
0x180012e78  test    r14b, r14b
0x180012e7b  jz      short loc_180012E82
0x180012e7d  mov     rax, rbx
0x180012e80  jmp     short loc_180012E98
0x180012e82  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180012e86  mov     qword ptr [rbp+PerformanceCount], 0
0x180012e8e  call    cs:__imp_QueryPerformanceCounter
0x180012e94  mov     rax, qword ptr [rbp+PerformanceCount]
0x180012e98  mov     rdx, rsi; unsigned __int8 *
0x180012e9b  mov     [rsi+28h], rax
0x180012e9f  call    ?PIXRecordTimingCaptureBlob@@YAXIPEAE@Z; PIXRecordTimingCaptureBlob(uint,uchar *)
0x180012ea4  lea     rax, [rsi+30h]
0x180012ea8  mov     [rdi+10h], rax
0x180012eac  jmp     short loc_180012EF8
0x180012eae  call    cs:__imp_GetCurrentThreadId
0x180012eb4  mov     r15d, eax
0x180012eb7  call    cs:__imp_GetCurrentProcessId
0x180012ebd  lea     rdx, [rbp+PerformanceCount]
0x180012ec1  xor     ecx, ecx
0x180012ec3  mov     r12d, eax
0x180012ec6  call    ?PEvtAllocBlk@@YAJW4PIXEVT_BLOCK_TYPE@@PEAPEAUPEvtBlkHdr@@@Z; PEvtAllocBlk(PIXEVT_BLOCK_TYPE,PEvtBlkHdr * *)
0x180012ecb  test    eax, eax
0x180012ecd  js      short loc_180012F24
0x180012ecf  mov     rsi, qword ptr [rbp+PerformanceCount]
0x180012ed3  mov     [rdi], rsi
0x180012ed6  lea     rcx, [rsi+30h]
0x180012eda  mov     [rdi+10h], rcx
0x180012ede  lea     rax, [rsi+3E00h]
0x180012ee5  mov     [rdi+8], rax
0x180012ee9  mov     qword ptr [rcx], 0FFF80h
0x180012ef0  mov     [rsi+18h], r15d
0x180012ef4  mov     [rsi+1Ch], r12d
0x180012ef8  mov     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x180012f00  test    r14b, r14b
0x180012f03  jnz     short loc_180012F1B
0x180012f05  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180012f09  mov     qword ptr [rbp+PerformanceCount], 0
0x180012f11  call    cs:__imp_QueryPerformanceCounter
0x180012f17  mov     rbx, qword ptr [rbp+PerformanceCount]
0x180012f1b  mov     [rsi+20h], rbx
0x180012f1f  mov     rax, rbx
0x180012f22  jmp     short loc_180012F3D
0x180012f24  mov     qword ptr [rdi], 0
0x180012f2b  xor     eax, eax
0x180012f2d  mov     qword ptr [rdi+8], 0
0x180012f35  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x180012f3d  mov     rbx, [rsp+20h+arg_0]
0x180012f42  mov     rsi, [rsp+20h+arg_10]
0x180012f47  add     rsp, 20h
0x180012f4b  pop     r15
0x180012f4d  pop     r14
0x180012f4f  pop     r12
0x180012f51  pop     rdi
0x180012f52  pop     rbp
0x180012f53  retn
```

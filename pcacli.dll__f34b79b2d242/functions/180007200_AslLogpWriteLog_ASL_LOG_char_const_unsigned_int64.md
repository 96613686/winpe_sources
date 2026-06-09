# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x180007200`
- end: `0x1800075d7`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `983`
- prototype: `void(struct _ASL_LOG *, const char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180003110`
- `0x1800092ac`

## callees

- `0x180007200`
- `0x180008202`
- `0x18000826e`
- `0x18000827a`
- `0x180008ea8`
- `0x18000bfe6`
- `0x18000bff2`
- `0x18000bffe`
- `0x18000c030`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180007535`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180007535`
- `ntdll!RtlEnterCriticalSection` at `0x180007249`
- `ntdll!RtlEnterCriticalSection` at `0x1800074bf`
- `ntdll!RtlEnterCriticalSection` at `0x180007249`
- `ntdll!RtlEnterCriticalSection` at `0x1800074bf`
- `ntdll!RtlLeaveCriticalSection` at `0x180007433`
- `ntdll!RtlLeaveCriticalSection` at `0x1800075b6`
- `ntdll!RtlLeaveCriticalSection` at `0x180007433`
- `ntdll!RtlLeaveCriticalSection` at `0x1800075b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073a2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800073c2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800073c2`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18000747b`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18000747b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007464`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007464`

## pseudocode

```c
void __fastcall AslLogpWriteLog(struct _ASL_LOG *a1, const char *a2, size_t a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  DWORD v5; // r13d
  const char *v7; // r14
  size_t v8; // rbp
  size_t v9; // rcx
  size_t v10; // r14
  __int64 v11; // r9
  size_t v12; // r9
  size_t v13; // rdi
  size_t v14; // r10
  size_t v15; // rdx
  __int64 v16; // rax
  size_t v17; // rax
  size_t v18; // r8
  size_t v19; // rax
  size_t v20; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // rdi
  unsigned __int64 v23; // rax
  void *v24; // r8
  void *v25; // rcx
  SIZE_T v26; // rdi
  void *v27; // rax
  LPVOID v28; // rsi
  size_t v29; // rax
  size_t v30; // rcx
  size_t v31; // rax
  char *StdHandle; // rax
  __int64 v33; // rax
  int v34; // edi
  HANDLE FileW_0; // rbx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-68h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-60h] BYREF
  __int64 Buffer; // [rsp+58h] [rbp-50h] BYREF
  int v39; // [rsp+60h] [rbp-48h]
  char v40; // [rsp+64h] [rbp-44h]

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 104);
  v5 = a3;
  *(_QWORD *)(*(_QWORD *)a1 + 64LL) = 0;
  v7 = a2;
  v8 = a3;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
  v9 = *(unsigned int *)(*(_QWORD *)a1 + 76LL);
  if ( (_DWORD)v9 )
  {
    if ( v8 > v9 )
    {
      v10 = v8;
      v8 = (unsigned int)v9;
      v7 = &a2[v10 - v9];
    }
    v11 = *((unsigned int *)a1 + 38);
    if ( v11 + v8 > v9 )
    {
      v12 = v8 + v11 - v9;
      if ( v12 )
      {
        v13 = 0;
        v14 = *((_QWORD *)a1 + 19);
        do
        {
          if ( v13 >= v14 )
            break;
          v15 = v13 + *((_QWORD *)a1 + 23);
          v16 = 0;
          if ( v14 - v13 == 1 )
            goto LABEL_14;
          while ( *(_BYTE *)(v15 + v16) != 13 || *(_BYTE *)(v15 + v16 + 1) != 10 )
          {
            if ( ++v16 >= v14 - v13 - 1 )
              goto LABEL_14;
          }
          v17 = v16 + 2;
          if ( !v17 )
LABEL_14:
            v17 = v14 - v13;
          v13 += v17;
        }
        while ( v13 < v12 );
        v18 = *((_QWORD *)a1 + 20);
        if ( v13 >= v18 || v13 >= *((_QWORD *)a1 + 19) )
        {
          memset_0(*((void **)a1 + 23), 0, v18);
          *((_QWORD *)a1 + 22) = 0;
        }
        else
        {
          memmove_0(*((void **)a1 + 23), (const void *)(*((_QWORD *)a1 + 23) + v13), *((_QWORD *)a1 + 22) - v13);
          v19 = *((_QWORD *)a1 + 22) - v13;
          *((_QWORD *)a1 + 19) = v19;
          *((_QWORD *)a1 + 22) = v19;
        }
      }
    }
  }
  if ( v8 )
  {
    v20 = *((_QWORD *)a1 + 22);
    v21 = v20 + v8;
    if ( v20 + v8 >= v20 )
    {
      if ( v21 <= *((_QWORD *)a1 + 20) )
        goto LABEL_30;
      v22 = *((_QWORD *)a1 + 21) - 1LL;
      v23 = v22 + v21;
      if ( v22 + v21 >= v21 )
      {
        v24 = (void *)*((_QWORD *)a1 + 23);
        v25 = (void *)*((_QWORD *)a1 + 18);
        v26 = v23 & ~v22;
        if ( v24 )
        {
          v28 = HeapReAlloc(v25, 0, v24, v26);
        }
        else
        {
          v27 = HeapAlloc(v25, 0, v26);
          v28 = v27;
          if ( v27 )
            memset_0(v27, 0, v26);
        }
        if ( v28 )
        {
          *((_QWORD *)a1 + 23) = v28;
          *((_QWORD *)a1 + 20) = v26;
LABEL_30:
          memcpy_0((void *)(*((_QWORD *)a1 + 22) + *((_QWORD *)a1 + 23)), v7, v8);
          v29 = *((_QWORD *)a1 + 22);
          v30 = v29 + v8;
          if ( v29 + v8 < v29 )
          {
            *((_QWORD *)a1 + 22) = -1;
          }
          else
          {
            *((_QWORD *)a1 + 22) = v30;
            v31 = *((_QWORD *)a1 + 19);
            if ( v31 <= v30 )
              v31 = v30;
            *((_QWORD *)a1 + 19) = v31;
          }
        }
      }
    }
  }
  RtlLeaveCriticalSection(v3);
  *(_QWORD *)(*(_QWORD *)a1 + 64LL) = *((_QWORD *)a1 + 23);
  *(_DWORD *)(*(_QWORD *)a1 + 72LL) = *((_DWORD *)a1 + 38);
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 80LL) & 1) != 0 )
    OutputDebugStringA(a2);
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 80LL) & 0x100) != 0 )
  {
    StdHandle = (char *)GetStdHandle(0xFFFFFFF5);
    if ( (unsigned __int64)(StdHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      WriteFile_0(StdHandle, a2, v8, 0, 0);
  }
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 80LL) & 4) != 0 )
  {
    RtlEnterCriticalSection(v3);
    v33 = *(_QWORD *)a1;
    NumberOfBytesWritten = 0;
    v34 = *(_DWORD *)(v33 + 80);
    FileW_0 = CreateFileW_0((LPCWSTR)a1 + 96, 4u, 1u, 0, 4u, ~(v34 << 28) & 0x80000000, 0);
    if ( FileW_0 != (HANDLE)-1LL )
    {
      if ( (v34 & 0x20) != 0 )
      {
        Buffer = 0;
        v39 = 0;
        v40 = 0;
        SystemTime = 0;
        GetLocalTime(&SystemTime);
        if ( (int)RtlStringCchPrintfA(
                    (char *)&Buffer,
                    0xDu,
                    "%02d:%02d:%02d.%03d",
                    SystemTime.wHour,
                    SystemTime.wMinute,
                    SystemTime.wSecond,
                    SystemTime.wMilliseconds) >= 0 )
          WriteFile_0(FileW_0, &Buffer, 0xDu, &NumberOfBytesWritten, 0);
      }
      WriteFile_0(FileW_0, a2, v5, &NumberOfBytesWritten, 0);
      CloseHandle_0(FileW_0);
    }
    RtlLeaveCriticalSection(v3);
  }
}

```

## disassembly

```asm
0x180007200  push    rbx
0x180007202  push    rsi
0x180007203  push    rdi
0x180007204  push    r12
0x180007206  push    r13
0x180007208  push    r15
0x18000720a  sub     rsp, 78h
0x18000720e  mov     rax, cs:__security_cookie
0x180007215  xor     rax, rsp
0x180007218  mov     [rsp+0A8h+var_40], rax
0x18000721d  mov     rax, [rcx]
0x180007220  lea     r12, [rcx+68h]
0x180007224  mov     [rsp+0A8h+arg_18], rbp
0x18000722c  mov     rbx, rcx
0x18000722f  xor     esi, esi
0x180007231  mov     [rsp+0A8h+var_38], r14
0x180007236  mov     rcx, r12; CriticalSection
0x180007239  mov     r13, r8
0x18000723c  mov     [rax+40h], rsi
0x180007240  mov     r15, rdx
0x180007243  mov     r14, rdx
0x180007246  mov     rbp, r8
0x180007249  call    cs:__imp_RtlEnterCriticalSection
0x18000724f  mov     rax, [rbx]
0x180007252  mov     ecx, [rax+4Ch]
0x180007255  test    ecx, ecx
0x180007257  jz      loc_180007347
0x18000725d  cmp     rbp, rcx
0x180007260  jbe     short loc_18000726D
0x180007262  mov     r14, rbp
0x180007265  mov     ebp, ecx
0x180007267  sub     r14, rcx
0x18000726a  add     r14, r15
0x18000726d  mov     r9d, [rbx+98h]
0x180007274  lea     rax, [r9+rbp]
0x180007278  cmp     rax, rcx
0x18000727b  jbe     loc_180007347
0x180007281  sub     r9, rcx
0x180007284  add     r9, rbp
0x180007287  jz      loc_180007347
0x18000728d  mov     rdi, rsi
0x180007290  test    r9, r9
0x180007293  jz      short loc_1800072E9
0x180007295  mov     r10, [rbx+98h]
0x18000729c  nop     dword ptr [rax+00h]
0x1800072a0  cmp     rdi, r10
0x1800072a3  jnb     short loc_1800072E9
0x1800072a5  mov     rdx, [rbx+0B8h]
0x1800072ac  mov     r8, r10
0x1800072af  sub     r8, rdi
0x1800072b2  add     rdx, rdi
0x1800072b5  mov     rax, rsi
0x1800072b8  lea     rcx, [r8-1]
0x1800072bc  test    rcx, rcx
0x1800072bf  jz      short loc_1800072DE
0x1800072c1  cmp     byte ptr [rdx+rax], 0Dh
0x1800072c5  jnz     short loc_1800072CE
0x1800072c7  cmp     byte ptr [rdx+rax+1], 0Ah
0x1800072cc  jz      short loc_1800072D8
0x1800072ce  inc     rax
0x1800072d1  cmp     rax, rcx
0x1800072d4  jb      short loc_1800072C1
0x1800072d6  jmp     short loc_1800072DE
0x1800072d8  add     rax, 2
0x1800072dc  jnz     short loc_1800072E1
0x1800072de  mov     rax, r8
0x1800072e1  add     rdi, rax
0x1800072e4  cmp     rdi, r9
0x1800072e7  jb      short loc_1800072A0
0x1800072e9  mov     r8, [rbx+0A0h]; Size
0x1800072f0  cmp     rdi, r8
0x1800072f3  jnb     short loc_180007332
0x1800072f5  cmp     rdi, [rbx+98h]
0x1800072fc  jnb     short loc_180007332
0x1800072fe  mov     rcx, [rbx+0B8h]; void *
0x180007305  mov     r8, [rbx+0B0h]
0x18000730c  sub     r8, rdi; Size
0x18000730f  lea     rdx, [rcx+rdi]; Src
0x180007313  call    memmove_0
0x180007318  mov     rax, [rbx+0B0h]
0x18000731f  sub     rax, rdi
0x180007322  mov     [rbx+98h], rax
0x180007329  mov     [rbx+0B0h], rax
0x180007330  jmp     short loc_180007347
0x180007332  mov     rcx, [rbx+0B8h]; void *
0x180007339  xor     edx, edx; Val
0x18000733b  call    memset_0
0x180007340  mov     [rbx+0B0h], rsi
0x180007347  test    rbp, rbp
0x18000734a  jz      loc_180007430
0x180007350  mov     rax, [rbx+0B0h]
0x180007357  lea     rcx, [rax+rbp]
0x18000735b  cmp     rcx, rax
0x18000735e  jb      loc_180007430
0x180007364  cmp     rcx, [rbx+0A0h]
0x18000736b  jbe     short loc_1800073DE
0x18000736d  mov     rdi, [rbx+0A8h]
0x180007374  dec     rdi
0x180007377  lea     rax, [rdi+rcx]
0x18000737b  cmp     rax, rcx
0x18000737e  jb      loc_180007430
0x180007384  mov     r8, [rbx+0B8h]; lpMem
0x18000738b  not     rdi
0x18000738e  mov     rcx, [rbx+90h]; hHeap
0x180007395  and     rdi, rax
0x180007398  xor     edx, edx; dwFlags
0x18000739a  test    r8, r8
0x18000739d  jnz     short loc_1800073BF
0x18000739f  mov     r8, rdi; dwBytes
0x1800073a2  call    cs:__imp_HeapAlloc
0x1800073a8  mov     rsi, rax
0x1800073ab  test    rax, rax
0x1800073ae  jz      short loc_1800073CB
0x1800073b0  mov     r8, rdi; Size
0x1800073b3  xor     edx, edx; Val
0x1800073b5  mov     rcx, rax; void *
0x1800073b8  call    memset_0
0x1800073bd  jmp     short loc_1800073CB
0x1800073bf  mov     r9, rdi; dwBytes
0x1800073c2  call    cs:__imp_HeapReAlloc
0x1800073c8  mov     rsi, rax
0x1800073cb  test    rsi, rsi
0x1800073ce  jz      short loc_180007430
0x1800073d0  mov     [rbx+0B8h], rsi
0x1800073d7  mov     [rbx+0A0h], rdi
0x1800073de  mov     rcx, [rbx+0B8h]
0x1800073e5  mov     r8, rbp; Size
0x1800073e8  add     rcx, [rbx+0B0h]; void *
0x1800073ef  mov     rdx, r14; Src
0x1800073f2  call    memcpy_0
0x1800073f7  mov     rax, [rbx+0B0h]
0x1800073fe  lea     rcx, [rax+rbp]
0x180007402  cmp     rcx, rax
0x180007405  jb      short loc_180007425
0x180007407  mov     [rbx+0B0h], rcx
0x18000740e  mov     rax, [rbx+98h]
0x180007415  cmp     rax, rcx
0x180007418  cmovbe  rax, rcx
0x18000741c  mov     [rbx+98h], rax
0x180007423  jmp     short loc_180007430
0x180007425  mov     qword ptr [rbx+0B0h], 0FFFFFFFFFFFFFFFFh
0x180007430  mov     rcx, r12; CriticalSection
0x180007433  call    cs:__imp_RtlLeaveCriticalSection
0x180007439  mov     rax, [rbx+0B8h]
0x180007440  mov     rcx, [rbx]
0x180007443  mov     r14, [rsp+0A8h+var_38]
0x180007448  mov     [rcx+40h], rax
0x18000744c  mov     eax, [rbx+98h]
0x180007452  mov     rcx, [rbx]
0x180007455  mov     [rcx+48h], eax
0x180007458  mov     rax, [rbx]
0x18000745b  test    byte ptr [rax+50h], 1
0x18000745f  jz      short loc_18000746A
0x180007461  mov     rcx, r15; lpOutputString
0x180007464  call    cs:__imp_OutputDebugStringA
0x18000746a  mov     rax, [rbx]
0x18000746d  test    dword ptr [rax+50h], 100h
0x180007474  jz      short loc_1800074A5
0x180007476  mov     ecx, 0FFFFFFF5h; nStdHandle
0x18000747b  call    cs:__imp_GetStdHandle
0x180007481  xor     esi, esi
0x180007483  lea     rcx, [rax-1]
0x180007487  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000748b  ja      short loc_1800074A7
0x18000748d  mov     r8d, ebp; nNumberOfBytesToWrite
0x180007490  mov     [rsp+0A8h+lpOverlapped], rsi; lpOverlapped
0x180007495  xor     r9d, r9d; lpNumberOfBytesWritten
0x180007498  mov     rdx, r15; lpBuffer
0x18000749b  mov     rcx, rax; hFile
0x18000749e  call    WriteFile_0
0x1800074a3  jmp     short loc_1800074A7
0x1800074a5  xor     esi, esi
0x1800074a7  mov     rax, [rbx]
0x1800074aa  mov     rbp, [rsp+0A8h+arg_18]
0x1800074b2  test    byte ptr [rax+50h], 4
0x1800074b6  jz      loc_1800075BC
0x1800074bc  mov     rcx, r12; CriticalSection
0x1800074bf  call    cs:__imp_RtlEnterCriticalSection
0x1800074c5  mov     rax, [rbx]
0x1800074c8  lea     rcx, [rbx+0C0h]; lpFileName
0x1800074cf  mov     [rsp+0A8h+hTemplateFile], rsi; hTemplateFile
0x1800074d4  xor     r9d, r9d; lpSecurityAttributes
0x1800074d7  mov     edx, 4; dwDesiredAccess
0x1800074dc  mov     [rsp+0A8h+NumberOfBytesWritten], esi
0x1800074e0  mov     r8d, 1; dwShareMode
0x1800074e6  mov     edi, [rax+50h]
0x1800074e9  mov     eax, edi
0x1800074eb  shl     eax, 1Ch
0x1800074ee  not     eax
0x1800074f0  and     eax, 80000000h
0x1800074f5  mov     [rsp+0A8h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800074f9  mov     dword ptr [rsp+0A8h+lpOverlapped], 4; dwCreationDisposition
0x180007501  call    CreateFileW_0
0x180007506  mov     rbx, rax
0x180007509  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000750d  jz      loc_1800075B3
0x180007513  test    dil, 20h
0x180007517  jz      short loc_180007593
0x180007519  xor     eax, eax
0x18000751b  lea     rcx, [rsp+0A8h+SystemTime]; lpSystemTime
0x180007520  xorps   xmm0, xmm0
0x180007523  mov     [rsp+0A8h+Buffer], rax
0x180007528  mov     [rsp+0A8h+var_48], eax
0x18000752c  mov     [rsp+0A8h+var_44], al
0x180007530  movups  xmmword ptr [rsp+0A8h+SystemTime.wYear], xmm0
0x180007535  call    cs:__imp_GetLocalTime
0x18000753b  movzx   ecx, [rsp+0A8h+SystemTime.wSecond]
0x180007540  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x180007547  movzx   edx, [rsp+0A8h+SystemTime.wMinute]
0x18000754c  movzx   eax, [rsp+0A8h+SystemTime.wMilliseconds]
0x180007551  movzx   r9d, [rsp+0A8h+SystemTime.wHour]
0x180007557  mov     dword ptr [rsp+0A8h+hTemplateFile], eax
0x18000755b  mov     [rsp+0A8h+dwFlagsAndAttributes], ecx
0x18000755f  lea     rcx, [rsp+0A8h+Buffer]; char *
0x180007564  mov     dword ptr [rsp+0A8h+lpOverlapped], edx
0x180007568  mov     edx, 0Dh; unsigned __int64
0x18000756d  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007572  test    eax, eax
0x180007574  js      short loc_180007593
0x180007576  lea     r9, [rsp+0A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000757b  mov     [rsp+0A8h+lpOverlapped], rsi; lpOverlapped
0x180007580  mov     r8d, 0Dh; nNumberOfBytesToWrite
0x180007586  lea     rdx, [rsp+0A8h+Buffer]; lpBuffer
0x18000758b  mov     rcx, rbx; hFile
0x18000758e  call    WriteFile_0
0x180007593  mov     r8d, r13d; nNumberOfBytesToWrite
0x180007596  mov     [rsp+0A8h+lpOverlapped], rsi; lpOverlapped
0x18000759b  lea     r9, [rsp+0A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800075a0  mov     rdx, r15; lpBuffer
0x1800075a3  mov     rcx, rbx; hFile
0x1800075a6  call    WriteFile_0
0x1800075ab  mov     rcx, rbx; hObject
0x1800075ae  call    CloseHandle_0
0x1800075b3  mov     rcx, r12; CriticalSection
0x1800075b6  call    cs:__imp_RtlLeaveCriticalSection
0x1800075bc  mov     rcx, [rsp+0A8h+var_40]
0x1800075c1  xor     rcx, rsp; StackCookie
0x1800075c4  call    __security_check_cookie
0x1800075c9  add     rsp, 78h
0x1800075cd  pop     r15
0x1800075cf  pop     r13
0x1800075d1  pop     r12
0x1800075d3  pop     rdi
0x1800075d4  pop     rsi
0x1800075d5  pop     rbx
0x1800075d6  retn
```

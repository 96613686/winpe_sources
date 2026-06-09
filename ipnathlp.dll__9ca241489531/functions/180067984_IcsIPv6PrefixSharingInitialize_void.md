# IcsIPv6PrefixSharingInitialize(void)

- ea: `0x180067984`
- end: `0x180067af7`
- name: `?IcsIPv6PrefixSharingInitialize@@YAPEAXXZ`
- size: `371`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c140`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18004ed64`
- `0x180067984`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800679c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067a9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800679c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067a9a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800679d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800679d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067aa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067aa8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067a94`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067a94`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180067a36`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180067a36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a4d`
- `WINNSI!NsiConnectToServer` at `0x180067a3e`
- `WINNSI!NsiConnectToServer` at `0x180067a3e`

## pseudocode

```c
char *IcsIPv6PrefixSharingInitialize(void)
{
  HANDLE ProcessHeap; // rax
  unsigned int v1; // ebx
  char *v2; // rax
  char *v3; // rdi
  PVOID *v4; // rcx
  __int64 v5; // rax
  DWORD LastError; // eax
  HANDLE v7; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
  }
  ProcessHeap = GetProcessHeap();
  v1 = 8;
  v2 = (char *)HeapAlloc(ProcessHeap, 8u, 0x68u);
  v3 = v2;
  if ( v2 )
  {
    memset_0(v2, 0, 0x68u);
    InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 64));
    v5 = NsiConnectToServer(0);
    *((_QWORD *)v3 + 1) = v5;
    if ( v5 )
    {
      v1 = 0;
      *(_DWORD *)v3 = 1;
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, LastError);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !v1 )
        goto LABEL_19;
      DeleteCriticalSection((LPCRITICAL_SECTION)(v3 + 64));
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v3);
      v3 = 0;
    }
    goto LABEL_18;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, 8);
LABEL_18:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_19:
  if ( v4 != &WPP_GLOBAL_Control && *((char *)v4 + 28) < 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 88, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, v1);
  return v3;
}

```

## disassembly

```asm
0x180067984  push    rbx
0x180067986  push    rsi
0x180067987  push    rdi
0x180067988  push    r14
0x18006798a  sub     rsp, 28h
0x18006798e  mov     rcx, cs:WPP_GLOBAL_Control
0x180067995  lea     r14, WPP_GLOBAL_Control
0x18006799c  cmp     rcx, r14
0x18006799f  jz      short loc_1800679C2
0x1800679a1  test    byte ptr [rcx+1Ch], 80h
0x1800679a5  jz      short loc_1800679C2
0x1800679a7  cmp     byte ptr [rcx+19h], 6
0x1800679ab  jb      short loc_1800679C2
0x1800679ad  mov     rcx, [rcx+10h]
0x1800679b1  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x1800679b8  mov     edx, 55h ; 'U'
0x1800679bd  call    WPP_SF_
0x1800679c2  call    cs:__imp_GetProcessHeap
0x1800679c8  mov     esi, 68h ; 'h'
0x1800679cd  mov     rcx, rax; hHeap
0x1800679d0  mov     r8d, esi; dwBytes
0x1800679d3  lea     ebx, [rsi-60h]
0x1800679d6  mov     edx, ebx; dwFlags
0x1800679d8  call    cs:__imp_HeapAlloc
0x1800679de  mov     rdi, rax
0x1800679e1  test    rax, rax
0x1800679e4  jnz     short loc_180067A25
0x1800679e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800679ed  cmp     rcx, r14
0x1800679f0  jz      loc_180067AEA
0x1800679f6  test    byte ptr [rcx+1Ch], 80h
0x1800679fa  jz      loc_180067AC1
0x180067a00  cmp     byte ptr [rcx+19h], 2
0x180067a04  jb      loc_180067AC1
0x180067a0a  mov     rcx, [rcx+10h]
0x180067a0e  lea     edx, [rsi-12h]
0x180067a11  mov     r9d, ebx
0x180067a14  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x180067a1b  call    WPP_SF_d
0x180067a20  jmp     loc_180067ABA
0x180067a25  mov     r8, rsi; Size
0x180067a28  xor     edx, edx; Val
0x180067a2a  mov     rcx, rdi; void *
0x180067a2d  call    memset_0
0x180067a32  lea     rcx, [rdi+40h]; lpCriticalSection
0x180067a36  call    cs:__imp_InitializeCriticalSection
0x180067a3c  xor     ecx, ecx
0x180067a3e  call    cs:__imp_NsiConnectToServer
0x180067a44  mov     [rdi+8], rax
0x180067a48  test    rax, rax
0x180067a4b  jnz     short loc_180067AB2
0x180067a4d  call    cs:__imp_GetLastError
0x180067a53  mov     ebx, eax
0x180067a55  mov     rcx, cs:WPP_GLOBAL_Control
0x180067a5c  cmp     rcx, r14
0x180067a5f  jz      short loc_180067A8C
0x180067a61  test    byte ptr [rcx+1Ch], 80h
0x180067a65  jz      short loc_180067A8C
0x180067a67  cmp     byte ptr [rcx+19h], 2
0x180067a6b  jb      short loc_180067A8C
0x180067a6d  mov     rcx, [rcx+10h]
0x180067a71  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x180067a78  mov     edx, 57h ; 'W'
0x180067a7d  mov     r9d, eax
0x180067a80  call    WPP_SF_d
0x180067a85  mov     rcx, cs:WPP_GLOBAL_Control
0x180067a8c  test    ebx, ebx
0x180067a8e  jz      short loc_180067AC1
0x180067a90  lea     rcx, [rdi+40h]; lpCriticalSection
0x180067a94  call    cs:__imp_DeleteCriticalSection
0x180067a9a  call    cs:__imp_GetProcessHeap
0x180067aa0  mov     r8, rdi; lpMem
0x180067aa3  xor     edx, edx; dwFlags
0x180067aa5  mov     rcx, rax; hHeap
0x180067aa8  call    cs:__imp_HeapFree
0x180067aae  xor     edi, edi
0x180067ab0  jmp     short loc_180067ABA
0x180067ab2  xor     ebx, ebx
0x180067ab4  mov     dword ptr [rdi], 1
0x180067aba  mov     rcx, cs:WPP_GLOBAL_Control
0x180067ac1  cmp     rcx, r14
0x180067ac4  jz      short loc_180067AEA
0x180067ac6  test    byte ptr [rcx+1Ch], 80h
0x180067aca  jz      short loc_180067AEA
0x180067acc  cmp     byte ptr [rcx+19h], 6
0x180067ad0  jb      short loc_180067AEA
0x180067ad2  mov     rcx, [rcx+10h]
0x180067ad6  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x180067add  mov     edx, 58h ; 'X'
0x180067ae2  mov     r9d, ebx
0x180067ae5  call    WPP_SF_d
0x180067aea  mov     rax, rdi
0x180067aed  add     rsp, 28h
0x180067af1  pop     r14
0x180067af3  pop     rdi
0x180067af4  pop     rsi
0x180067af5  pop     rbx
0x180067af6  retn
```

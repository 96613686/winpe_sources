# IcsIPv6PrefixSharingInitialize(void)

- ea: `0x18006cad4`
- end: `0x18006cc78`
- name: `?IcsIPv6PrefixSharingInitialize@@YAPEAXXZ`
- size: `420`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ca50`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180052bf4`
- `0x18006cad4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006cb12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006cc0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006cb12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006cc0e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006cb2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006cb2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006cc22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006cc22`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006cc02`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006cc02`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006cb92`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006cb92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cbb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cbb5`
- `WINNSI!NsiConnectToServer` at `0x18006cba0`
- `WINNSI!NsiConnectToServer` at `0x18006cba0`

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
0x18006cad4  push    rbx
0x18006cad6  push    rsi
0x18006cad7  push    rdi
0x18006cad8  push    r14
0x18006cada  sub     rsp, 28h
0x18006cade  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cae5  lea     r14, WPP_GLOBAL_Control
0x18006caec  cmp     rcx, r14
0x18006caef  jz      short loc_18006CB12
0x18006caf1  test    byte ptr [rcx+1Ch], 80h
0x18006caf5  jz      short loc_18006CB12
0x18006caf7  cmp     byte ptr [rcx+19h], 6
0x18006cafb  jb      short loc_18006CB12
0x18006cafd  mov     rcx, [rcx+10h]
0x18006cb01  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18006cb08  mov     edx, 55h ; 'U'
0x18006cb0d  call    WPP_SF_
0x18006cb12  call    cs:__imp_GetProcessHeap
0x18006cb19  nop     dword ptr [rax+rax+00h]
0x18006cb1e  mov     esi, 68h ; 'h'
0x18006cb23  mov     rcx, rax; hHeap
0x18006cb26  mov     r8d, esi; dwBytes
0x18006cb29  lea     ebx, [rsi-60h]
0x18006cb2c  mov     edx, ebx; dwFlags
0x18006cb2e  call    cs:__imp_HeapAlloc
0x18006cb35  nop     dword ptr [rax+rax+00h]
0x18006cb3a  mov     rdi, rax
0x18006cb3d  test    rax, rax
0x18006cb40  jnz     short loc_18006CB81
0x18006cb42  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cb49  cmp     rcx, r14
0x18006cb4c  jz      loc_18006CC6A
0x18006cb52  test    byte ptr [rcx+1Ch], 80h
0x18006cb56  jz      loc_18006CC41
0x18006cb5c  cmp     byte ptr [rcx+19h], 2
0x18006cb60  jb      loc_18006CC41
0x18006cb66  mov     rcx, [rcx+10h]
0x18006cb6a  lea     edx, [rsi-12h]
0x18006cb6d  mov     r9d, ebx
0x18006cb70  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18006cb77  call    WPP_SF_d
0x18006cb7c  jmp     loc_18006CC3A
0x18006cb81  mov     r8, rsi; Size
0x18006cb84  xor     edx, edx; Val
0x18006cb86  mov     rcx, rdi; void *
0x18006cb89  call    memset_0
0x18006cb8e  lea     rcx, [rdi+40h]; lpCriticalSection
0x18006cb92  call    cs:__imp_InitializeCriticalSection
0x18006cb99  nop     dword ptr [rax+rax+00h]
0x18006cb9e  xor     ecx, ecx
0x18006cba0  call    cs:__imp_NsiConnectToServer
0x18006cba7  nop     dword ptr [rax+rax+00h]
0x18006cbac  mov     [rdi+8], rax
0x18006cbb0  test    rax, rax
0x18006cbb3  jnz     short loc_18006CC32
0x18006cbb5  call    cs:__imp_GetLastError
0x18006cbbc  nop     dword ptr [rax+rax+00h]
0x18006cbc1  mov     ebx, eax
0x18006cbc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cbca  cmp     rcx, r14
0x18006cbcd  jz      short loc_18006CBFA
0x18006cbcf  test    byte ptr [rcx+1Ch], 80h
0x18006cbd3  jz      short loc_18006CBFA
0x18006cbd5  cmp     byte ptr [rcx+19h], 2
0x18006cbd9  jb      short loc_18006CBFA
0x18006cbdb  mov     rcx, [rcx+10h]
0x18006cbdf  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18006cbe6  mov     edx, 57h ; 'W'
0x18006cbeb  mov     r9d, eax
0x18006cbee  call    WPP_SF_d
0x18006cbf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cbfa  test    ebx, ebx
0x18006cbfc  jz      short loc_18006CC41
0x18006cbfe  lea     rcx, [rdi+40h]; lpCriticalSection
0x18006cc02  call    cs:__imp_DeleteCriticalSection
0x18006cc09  nop     dword ptr [rax+rax+00h]
0x18006cc0e  call    cs:__imp_GetProcessHeap
0x18006cc15  nop     dword ptr [rax+rax+00h]
0x18006cc1a  mov     r8, rdi; lpMem
0x18006cc1d  xor     edx, edx; dwFlags
0x18006cc1f  mov     rcx, rax; hHeap
0x18006cc22  call    cs:__imp_HeapFree
0x18006cc29  nop     dword ptr [rax+rax+00h]
0x18006cc2e  xor     edi, edi
0x18006cc30  jmp     short loc_18006CC3A
0x18006cc32  xor     ebx, ebx
0x18006cc34  mov     dword ptr [rdi], 1
0x18006cc3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cc41  cmp     rcx, r14
0x18006cc44  jz      short loc_18006CC6A
0x18006cc46  test    byte ptr [rcx+1Ch], 80h
0x18006cc4a  jz      short loc_18006CC6A
0x18006cc4c  cmp     byte ptr [rcx+19h], 6
0x18006cc50  jb      short loc_18006CC6A
0x18006cc52  mov     rcx, [rcx+10h]
0x18006cc56  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18006cc5d  mov     edx, 58h ; 'X'
0x18006cc62  mov     r9d, ebx
0x18006cc65  call    WPP_SF_d
0x18006cc6a  mov     rax, rdi
0x18006cc6d  add     rsp, 28h
0x18006cc71  pop     r14
0x18006cc73  pop     rdi
0x18006cc74  pop     rsi
0x18006cc75  pop     rbx
0x18006cc76  retn
```

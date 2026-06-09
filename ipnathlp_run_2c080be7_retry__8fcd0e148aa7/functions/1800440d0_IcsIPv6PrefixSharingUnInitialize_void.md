# IcsIPv6PrefixSharingUnInitialize(void *)

- ea: `0x1800440d0`
- end: `0x18004420f`
- name: `?IcsIPv6PrefixSharingUnInitialize@@YAKPEAX@Z`
- size: `319`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000ca50`
- `0x18003ba60`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18000d590`
- `0x1800440d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800441b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800441b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800441c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800441c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044168`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044168`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004419a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004419a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800441a9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800441a9`
- `WINNSI!NsiDisconnectFromServer` at `0x18004417d`
- `WINNSI!NsiDisconnectFromServer` at `0x18004417d`

## pseudocode

```c
__int64 __fastcall IcsIPv6PrefixSharingUnInitialize(void *a1)
{
  struct _ICS_PS_CONTEXT *v1; // rbx
  unsigned int v2; // eax
  unsigned int v3; // edi
  PVOID *v4; // rcx
  __int64 v5; // rcx
  HANDLE ProcessHeap; // rax

  v1 = gPrefixSharingContext;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
  }
  v2 = IcsIPv6PrefixSharingDisable(v1);
  v3 = v2;
  if ( !v2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 64));
    v5 = *((_QWORD *)v1 + 1);
    if ( v5 )
    {
      NsiDisconnectFromServer(v5);
      *((_QWORD *)v1 + 1) = 0;
    }
    *(_DWORD *)v1 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 64));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 64));
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    goto LABEL_13;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, v2);
LABEL_13:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && *((char *)v4 + 28) < 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_(v4[2], 91, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x1800440d0  push    rbx
0x1800440d2  push    rsi
0x1800440d3  push    rdi
0x1800440d4  push    r14
0x1800440d6  sub     rsp, 28h
0x1800440da  mov     rbx, cs:?gPrefixSharingContext@@3PEAXEA; void * gPrefixSharingContext
0x1800440e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800440e8  lea     r14, WPP_GLOBAL_Control
0x1800440ef  cmp     rcx, r14
0x1800440f2  jz      short loc_180044115
0x1800440f4  test    byte ptr [rcx+1Ch], 80h
0x1800440f8  jz      short loc_180044115
0x1800440fa  cmp     byte ptr [rcx+19h], 6
0x1800440fe  jb      short loc_180044115
0x180044100  mov     rcx, [rcx+10h]
0x180044104  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18004410b  mov     edx, 59h ; 'Y'
0x180044110  call    WPP_SF_
0x180044115  mov     rcx, rbx; struct _ICS_PS_CONTEXT *
0x180044118  call    ?IcsIPv6PrefixSharingDisable@@YAKPEAX@Z; IcsIPv6PrefixSharingDisable(void *)
0x18004411d  mov     edi, eax
0x18004411f  test    eax, eax
0x180044121  jz      short loc_180044161
0x180044123  mov     rcx, cs:WPP_GLOBAL_Control
0x18004412a  cmp     rcx, r14
0x18004412d  jz      loc_180044202
0x180044133  test    byte ptr [rcx+1Ch], 80h
0x180044137  jz      loc_1800441DC
0x18004413d  cmp     byte ptr [rcx+19h], 2
0x180044141  jb      loc_1800441DC
0x180044147  mov     rcx, [rcx+10h]
0x18004414b  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x180044152  mov     edx, 5Ah ; 'Z'
0x180044157  mov     r9d, eax
0x18004415a  call    WPP_SF_d
0x18004415f  jmp     short loc_1800441D5
0x180044161  lea     rsi, [rbx+40h]
0x180044165  mov     rcx, rsi; lpCriticalSection
0x180044168  call    cs:__imp_EnterCriticalSection
0x18004416f  nop     dword ptr [rax+rax+00h]
0x180044174  mov     rcx, [rbx+8]
0x180044178  test    rcx, rcx
0x18004417b  jz      short loc_180044191
0x18004417d  call    cs:__imp_NsiDisconnectFromServer
0x180044184  nop     dword ptr [rax+rax+00h]
0x180044189  mov     qword ptr [rbx+8], 0
0x180044191  mov     rcx, rsi; lpCriticalSection
0x180044194  mov     dword ptr [rbx], 0
0x18004419a  call    cs:__imp_LeaveCriticalSection
0x1800441a1  nop     dword ptr [rax+rax+00h]
0x1800441a6  mov     rcx, rsi; lpCriticalSection
0x1800441a9  call    cs:__imp_DeleteCriticalSection
0x1800441b0  nop     dword ptr [rax+rax+00h]
0x1800441b5  call    cs:__imp_GetProcessHeap
0x1800441bc  nop     dword ptr [rax+rax+00h]
0x1800441c1  mov     r8, rbx; lpMem
0x1800441c4  xor     edx, edx; dwFlags
0x1800441c6  mov     rcx, rax; hHeap
0x1800441c9  call    cs:__imp_HeapFree
0x1800441d0  nop     dword ptr [rax+rax+00h]
0x1800441d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800441dc  cmp     rcx, r14
0x1800441df  jz      short loc_180044202
0x1800441e1  test    byte ptr [rcx+1Ch], 80h
0x1800441e5  jz      short loc_180044202
0x1800441e7  cmp     byte ptr [rcx+19h], 6
0x1800441eb  jb      short loc_180044202
0x1800441ed  mov     rcx, [rcx+10h]
0x1800441f1  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x1800441f8  mov     edx, 5Bh ; '['
0x1800441fd  call    WPP_SF_
0x180044202  mov     eax, edi
0x180044204  add     rsp, 28h
0x180044208  pop     r14
0x18004420a  pop     rdi
0x18004420b  pop     rsi
0x18004420c  pop     rbx
0x18004420d  retn
```

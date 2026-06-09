# IcsIPv6PrefixSharingUnInitialize(void *)

- ea: `0x180040a48`
- end: `0x180040b5a`
- name: `?IcsIPv6PrefixSharingUnInitialize@@YAKPEAX@Z`
- size: `274`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000c140`
- `0x180038be4`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18000cc20`
- `0x180040a48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040b0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040b0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040b1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040b1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040ad8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040ad8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040afe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040afe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180040b07`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180040b07`
- `WINNSI!NsiDisconnectFromServer` at `0x180040ae7`
- `WINNSI!NsiDisconnectFromServer` at `0x180040ae7`

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
0x180040a48  push    rbx
0x180040a4a  push    rsi
0x180040a4b  push    rdi
0x180040a4c  push    r14
0x180040a4e  sub     rsp, 28h
0x180040a52  mov     rbx, cs:?gPrefixSharingContext@@3PEAXEA; void * gPrefixSharingContext
0x180040a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a60  lea     r14, WPP_GLOBAL_Control
0x180040a67  cmp     rcx, r14
0x180040a6a  jz      short loc_180040A8D
0x180040a6c  test    byte ptr [rcx+1Ch], 80h
0x180040a70  jz      short loc_180040A8D
0x180040a72  cmp     byte ptr [rcx+19h], 6
0x180040a76  jb      short loc_180040A8D
0x180040a78  mov     rcx, [rcx+10h]
0x180040a7c  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x180040a83  mov     edx, 59h ; 'Y'
0x180040a88  call    WPP_SF_
0x180040a8d  mov     rcx, rbx; struct _ICS_PS_CONTEXT *
0x180040a90  call    ?IcsIPv6PrefixSharingDisable@@YAKPEAX@Z; IcsIPv6PrefixSharingDisable(void *)
0x180040a95  mov     edi, eax
0x180040a97  test    eax, eax
0x180040a99  jz      short loc_180040AD1
0x180040a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180040aa2  cmp     rcx, r14
0x180040aa5  jz      loc_180040B4E
0x180040aab  test    byte ptr [rcx+1Ch], 80h
0x180040aaf  jz      short loc_180040B28
0x180040ab1  cmp     byte ptr [rcx+19h], 2
0x180040ab5  jb      short loc_180040B28
0x180040ab7  mov     rcx, [rcx+10h]
0x180040abb  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x180040ac2  mov     edx, 5Ah ; 'Z'
0x180040ac7  mov     r9d, eax
0x180040aca  call    WPP_SF_d
0x180040acf  jmp     short loc_180040B21
0x180040ad1  lea     rsi, [rbx+40h]
0x180040ad5  mov     rcx, rsi; lpCriticalSection
0x180040ad8  call    cs:__imp_EnterCriticalSection
0x180040ade  mov     rcx, [rbx+8]
0x180040ae2  test    rcx, rcx
0x180040ae5  jz      short loc_180040AF5
0x180040ae7  call    cs:__imp_NsiDisconnectFromServer
0x180040aed  mov     qword ptr [rbx+8], 0
0x180040af5  mov     rcx, rsi; lpCriticalSection
0x180040af8  mov     dword ptr [rbx], 0
0x180040afe  call    cs:__imp_LeaveCriticalSection
0x180040b04  mov     rcx, rsi; lpCriticalSection
0x180040b07  call    cs:__imp_DeleteCriticalSection
0x180040b0d  call    cs:__imp_GetProcessHeap
0x180040b13  mov     r8, rbx; lpMem
0x180040b16  xor     edx, edx; dwFlags
0x180040b18  mov     rcx, rax; hHeap
0x180040b1b  call    cs:__imp_HeapFree
0x180040b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b28  cmp     rcx, r14
0x180040b2b  jz      short loc_180040B4E
0x180040b2d  test    byte ptr [rcx+1Ch], 80h
0x180040b31  jz      short loc_180040B4E
0x180040b33  cmp     byte ptr [rcx+19h], 6
0x180040b37  jb      short loc_180040B4E
0x180040b39  mov     rcx, [rcx+10h]
0x180040b3d  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x180040b44  mov     edx, 5Bh ; '['
0x180040b49  call    WPP_SF_
0x180040b4e  mov     eax, edi
0x180040b50  add     rsp, 28h
0x180040b54  pop     r14
0x180040b56  pop     rdi
0x180040b57  pop     rsi
0x180040b58  pop     rbx
0x180040b59  retn
```

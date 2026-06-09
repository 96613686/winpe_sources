# DnsCleanupTables(void)

- ea: `0x18003a30c`
- end: `0x18003a5b3`
- name: `?DnsCleanupTables@@YAXXZ`
- size: `679`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007fb4`
- `0x180063ce4`
- `0x180063f50`

## callees

- `0x18000c110`
- `0x18003a30c`
- `0x18008e908`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a463`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a499`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a52d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a561`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a463`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a499`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a52d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a561`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a474`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a474`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a430`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a4a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a53b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a56f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a430`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a4a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a53b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a56f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a374`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a556`
- `ntdll!RtlEnumerateGenericTable` at `0x18003a383`
- `ntdll!RtlEnumerateGenericTable` at `0x18003a4d2`
- `ntdll!RtlEnumerateGenericTable` at `0x18003a383`
- `ntdll!RtlEnumerateGenericTable` at `0x18003a4d2`
- `ntdll!RtlLookupElementGenericTable` at `0x18003a3c7`
- `ntdll!RtlLookupElementGenericTable` at `0x18003a50e`
- `ntdll!RtlLookupElementGenericTable` at `0x18003a3c7`
- `ntdll!RtlLookupElementGenericTable` at `0x18003a50e`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003a523`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003a523`

## pseudocode

```c
void DnsCleanupTables(void)
{
  _QWORD *v0; // r14
  __int64 v1; // rsi
  unsigned int v2; // r12d
  _QWORD *i; // rdi
  unsigned int v4; // ebp
  _QWORD *v5; // rax
  char *v6; // r15
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  HANDLE v11; // rax
  __int64 j; // rdi
  PVOID v13; // rax
  void *v14; // rbx
  HANDLE v15; // rax
  HANDLE v16; // rax
  __int128 Buffer; // [rsp+20h] [rbp-78h] BYREF
  __int128 v18; // [rsp+30h] [rbp-68h] BYREF
  __int64 v19; // [rsp+40h] [rbp-58h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
  }
  v0 = 0;
  v18 = 0;
  v19 = 0;
  v1 = 0;
  Buffer = 0;
  v2 = 0;
  EnterCriticalSection(&DnsTableLock);
  for ( i = RtlEnumerateGenericTable(&g_DnsTable, 1u); i; i = RtlEnumerateGenericTable(&g_DnsTable, 0) )
  {
    v4 = 0;
    while ( v4 < *((_DWORD *)i + 2) )
    {
      LODWORD(Buffer) = *(_DWORD *)(i[2] + 12LL * v4);
      *((_QWORD *)&Buffer + 1) = 0;
      v5 = RtlLookupElementGenericTable(&g_ReverseDnsTable, &Buffer);
      if ( v5 && v5[1] == *i )
      {
        ++v4;
      }
      else
      {
        v6 = (char *)i[2];
        if ( *((_DWORD *)i + 2) <= 1u )
        {
          *((_DWORD *)i + 2) = 0;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v6);
          i[2] = 0;
          break;
        }
        memcpy_0(&v6[12 * v4], &v6[12 * v4 + 12], 12LL * (*((_DWORD *)i + 2) + ~v4));
        --*((_DWORD *)i + 2);
        ++v4;
      }
    }
    if ( *((_DWORD *)i + 2) )
      continue;
    if ( v2 > (unsigned int)v1 )
    {
      v0[v1] = *i;
    }
    else
    {
      v8 = GetProcessHeap();
      v9 = HeapAlloc(v8, 8u, 40LL * (((int)v1 + 5) / 5u));
      v10 = v9;
      if ( !v9 )
        continue;
      if ( v0 )
      {
        memcpy_0(v9, v0, 8LL * (unsigned int)v1);
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v0);
      }
      v2 = 5 * (((int)v1 + 5) / 5u);
      v0 = v10;
      if ( (unsigned int)v1 >= v2 )
        continue;
      v10[v1] = *i;
    }
    v1 = (unsigned int)(v1 + 1);
  }
  for ( j = 0; (unsigned int)j < (unsigned int)v1; j = (unsigned int)(j + 1) )
  {
    *(_QWORD *)&v18 = v0[j];
    DWORD2(v18) = 0;
    v13 = RtlLookupElementGenericTable(&g_DnsTable, &v18);
    if ( v13 )
    {
      RtlDeleteElementGenericTable(&g_DnsTable, v13);
      v14 = (void *)v0[j];
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v14);
    }
    v0[j] = 0;
  }
  LeaveCriticalSection(&DnsTableLock);
  if ( v0 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v0);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
  }
}

```

## disassembly

```asm
0x18003a30c  push    rbx
0x18003a30e  push    rbp
0x18003a30f  push    rsi
0x18003a310  push    rdi
0x18003a311  push    r12
0x18003a313  push    r13
0x18003a315  push    r14
0x18003a317  push    r15
0x18003a319  sub     rsp, 58h
0x18003a31d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a324  lea     r15, WPP_GLOBAL_Control
0x18003a32b  cmp     rcx, r15
0x18003a32e  jz      short loc_18003A351
0x18003a330  test    byte ptr [rcx+1Ch], 10h
0x18003a334  jz      short loc_18003A351
0x18003a336  cmp     byte ptr [rcx+19h], 6
0x18003a33a  jb      short loc_18003A351
0x18003a33c  mov     rcx, [rcx+10h]
0x18003a340  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003a347  mov     edx, 40h ; '@'
0x18003a34c  call    WPP_SF_
0x18003a351  xorps   xmm0, xmm0
0x18003a354  lea     rcx, ?DnsTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a35b  xor     eax, eax
0x18003a35d  xor     r14d, r14d
0x18003a360  movups  [rsp+98h+var_68], xmm0
0x18003a365  mov     [rsp+98h+var_58], rax
0x18003a36a  xor     esi, esi
0x18003a36c  movups  [rsp+98h+Buffer], xmm0
0x18003a371  xor     r12d, r12d
0x18003a374  call    cs:__imp_EnterCriticalSection
0x18003a37a  mov     dl, 1; Restart
0x18003a37c  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003a383  call    cs:__imp_RtlEnumerateGenericTable
0x18003a389  mov     rdi, rax
0x18003a38c  test    rax, rax
0x18003a38f  jz      loc_18003A4EB
0x18003a395  xor     ebp, ebp
0x18003a397  cmp     ebp, [rdi+8]
0x18003a39a  jnb     loc_18003A43E
0x18003a3a0  mov     eax, ebp
0x18003a3a2  lea     rdx, [rsp+98h+Buffer]; Buffer
0x18003a3a7  lea     r13, [rax+rax*2]
0x18003a3ab  mov     rax, [rdi+10h]
0x18003a3af  mov     ecx, [rax+r13*4]
0x18003a3b3  mov     dword ptr [rsp+98h+Buffer], ecx
0x18003a3b7  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003a3be  mov     qword ptr [rsp+98h+Buffer+8], 0
0x18003a3c7  call    cs:__imp_RtlLookupElementGenericTable
0x18003a3cd  test    rax, rax
0x18003a3d0  jz      short loc_18003A3DF
0x18003a3d2  mov     rcx, [rdi]
0x18003a3d5  cmp     [rax+8], rcx
0x18003a3d9  jnz     short loc_18003A3DF
0x18003a3db  inc     ebp
0x18003a3dd  jmp     short loc_18003A397
0x18003a3df  cmp     dword ptr [rdi+8], 1
0x18003a3e3  mov     r15, [rdi+10h]
0x18003a3e7  jbe     short loc_18003A41B
0x18003a3e9  lea     ebx, [rbp+1]
0x18003a3ec  not     ebp
0x18003a3ee  add     ebp, [rdi+8]
0x18003a3f1  lea     rcx, [rbx+rbx*2]
0x18003a3f5  lea     rdx, [r15+rcx*4]; Src
0x18003a3f9  lea     rcx, [r15+r13*4]; void *
0x18003a3fd  lea     r8, ds:0[rbp*2]
0x18003a405  add     r8, rbp
0x18003a408  shl     r8, 2; Size
0x18003a40c  call    memcpy_0
0x18003a411  dec     dword ptr [rdi+8]
0x18003a414  mov     ebp, ebx
0x18003a416  jmp     loc_18003A397
0x18003a41b  mov     dword ptr [rdi+8], 0
0x18003a422  call    cs:__imp_GetProcessHeap
0x18003a428  mov     r8, r15; lpMem
0x18003a42b  xor     edx, edx; dwFlags
0x18003a42d  mov     rcx, rax; hHeap
0x18003a430  call    cs:__imp_HeapFree
0x18003a436  mov     qword ptr [rdi+10h], 0
0x18003a43e  cmp     dword ptr [rdi+8], 0
0x18003a442  jnz     loc_18003A4C9
0x18003a448  cmp     r12d, esi
0x18003a44b  ja      short loc_18003A4C0
0x18003a44d  lea     ecx, [rsi+5]
0x18003a450  mov     eax, 0CCCCCCCDh
0x18003a455  mul     ecx
0x18003a457  shr     edx, 2
0x18003a45a  lea     ebp, [rdx+rdx*4]
0x18003a45d  mov     ebx, ebp
0x18003a45f  shl     rbx, 3
0x18003a463  call    cs:__imp_GetProcessHeap
0x18003a469  mov     r8, rbx; dwBytes
0x18003a46c  mov     edx, 8; dwFlags
0x18003a471  mov     rcx, rax; hHeap
0x18003a474  call    cs:__imp_HeapAlloc
0x18003a47a  mov     rbx, rax
0x18003a47d  test    rax, rax
0x18003a480  jz      short loc_18003A4C9
0x18003a482  test    r14, r14
0x18003a485  jz      short loc_18003A4AD
0x18003a487  mov     r8d, esi
0x18003a48a  mov     rdx, r14; Src
0x18003a48d  shl     r8, 3; Size
0x18003a491  mov     rcx, rax; void *
0x18003a494  call    memcpy_0
0x18003a499  call    cs:__imp_GetProcessHeap
0x18003a49f  mov     r8, r14; lpMem
0x18003a4a2  xor     edx, edx; dwFlags
0x18003a4a4  mov     rcx, rax; hHeap
0x18003a4a7  call    cs:__imp_HeapFree
0x18003a4ad  mov     r12d, ebp
0x18003a4b0  mov     r14, rbx
0x18003a4b3  cmp     esi, ebp
0x18003a4b5  jnb     short loc_18003A4C9
0x18003a4b7  mov     rax, [rdi]
0x18003a4ba  mov     [rbx+rsi*8], rax
0x18003a4be  jmp     short loc_18003A4C7
0x18003a4c0  mov     rax, [rdi]
0x18003a4c3  mov     [r14+rsi*8], rax
0x18003a4c7  inc     esi
0x18003a4c9  xor     edx, edx; Restart
0x18003a4cb  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003a4d2  call    cs:__imp_RtlEnumerateGenericTable
0x18003a4d8  mov     rdi, rax
0x18003a4db  test    rax, rax
0x18003a4de  jnz     loc_18003A395
0x18003a4e4  lea     r15, WPP_GLOBAL_Control
0x18003a4eb  xor     edi, edi
0x18003a4ed  test    esi, esi
0x18003a4ef  jz      short loc_18003A54F
0x18003a4f1  mov     rax, [r14+rdi*8]
0x18003a4f5  lea     rdx, [rsp+98h+var_68]; Buffer
0x18003a4fa  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003a501  mov     qword ptr [rsp+98h+var_68], rax
0x18003a506  mov     dword ptr [rsp+98h+var_68+8], 0
0x18003a50e  call    cs:__imp_RtlLookupElementGenericTable
0x18003a514  test    rax, rax
0x18003a517  jz      short loc_18003A541
0x18003a519  mov     rdx, rax; Buffer
0x18003a51c  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003a523  call    cs:__imp_RtlDeleteElementGenericTable
0x18003a529  mov     rbx, [r14+rdi*8]
0x18003a52d  call    cs:__imp_GetProcessHeap
0x18003a533  mov     r8, rbx; lpMem
0x18003a536  xor     edx, edx; dwFlags
0x18003a538  mov     rcx, rax; hHeap
0x18003a53b  call    cs:__imp_HeapFree
0x18003a541  mov     qword ptr [r14+rdi*8], 0
0x18003a549  inc     edi
0x18003a54b  cmp     edi, esi
0x18003a54d  jb      short loc_18003A4F1
0x18003a54f  lea     rcx, ?DnsTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a556  call    cs:__imp_LeaveCriticalSection
0x18003a55c  test    r14, r14
0x18003a55f  jz      short loc_18003A575
0x18003a561  call    cs:__imp_GetProcessHeap
0x18003a567  mov     r8, r14; lpMem
0x18003a56a  xor     edx, edx; dwFlags
0x18003a56c  mov     rcx, rax; hHeap
0x18003a56f  call    cs:__imp_HeapFree
0x18003a575  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a57c  cmp     rcx, r15
0x18003a57f  jz      short loc_18003A5A2
0x18003a581  test    byte ptr [rcx+1Ch], 10h
0x18003a585  jz      short loc_18003A5A2
0x18003a587  cmp     byte ptr [rcx+19h], 6
0x18003a58b  jb      short loc_18003A5A2
0x18003a58d  mov     rcx, [rcx+10h]
0x18003a591  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003a598  mov     edx, 41h ; 'A'
0x18003a59d  call    WPP_SF_
0x18003a5a2  add     rsp, 58h
0x18003a5a6  pop     r15
0x18003a5a8  pop     r14
0x18003a5aa  pop     r13
0x18003a5ac  pop     r12
0x18003a5ae  pop     rdi
0x18003a5af  pop     rsi
0x18003a5b0  pop     rbp
0x18003a5b1  pop     rbx
0x18003a5b2  retn
```

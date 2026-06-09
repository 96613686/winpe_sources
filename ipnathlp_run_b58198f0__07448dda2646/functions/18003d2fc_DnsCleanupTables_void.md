# DnsCleanupTables(void)

- ea: `0x18003d2fc`
- end: `0x18003d60e`
- name: `?DnsCleanupTables@@YAXXZ`
- size: `786`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000843c`
- `0x180068b24`
- `0x180068dd0`

## callees

- `0x18000ca20`
- `0x18003d2fc`
- `0x180095b28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d424`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d475`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d4b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d569`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d5af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d424`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d475`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d4b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d569`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d5af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d48c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d48c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d438`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d4cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d57d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d5c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d438`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d4cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d57d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d5c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d364`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d364`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d59e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d59e`
- `ntdll!RtlEnumerateGenericTable` at `0x18003d379`
- `ntdll!RtlEnumerateGenericTable` at `0x18003d4fc`
- `ntdll!RtlEnumerateGenericTable` at `0x18003d379`
- `ntdll!RtlEnumerateGenericTable` at `0x18003d4fc`
- `ntdll!RtlLookupElementGenericTable` at `0x18003d3c3`
- `ntdll!RtlLookupElementGenericTable` at `0x18003d53e`
- `ntdll!RtlLookupElementGenericTable` at `0x18003d3c3`
- `ntdll!RtlLookupElementGenericTable` at `0x18003d53e`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003d559`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003d559`

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
0x18003d2fc  push    rbx
0x18003d2fe  push    rbp
0x18003d2ff  push    rsi
0x18003d300  push    rdi
0x18003d301  push    r12
0x18003d303  push    r13
0x18003d305  push    r14
0x18003d307  push    r15
0x18003d309  sub     rsp, 58h
0x18003d30d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d314  lea     r15, WPP_GLOBAL_Control
0x18003d31b  cmp     rcx, r15
0x18003d31e  jz      short loc_18003D341
0x18003d320  test    byte ptr [rcx+1Ch], 10h
0x18003d324  jz      short loc_18003D341
0x18003d326  cmp     byte ptr [rcx+19h], 6
0x18003d32a  jb      short loc_18003D341
0x18003d32c  mov     rcx, [rcx+10h]
0x18003d330  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003d337  mov     edx, 40h ; '@'
0x18003d33c  call    WPP_SF_
0x18003d341  xorps   xmm0, xmm0
0x18003d344  lea     rcx, ?DnsTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003d34b  xor     eax, eax
0x18003d34d  xor     r14d, r14d
0x18003d350  movups  [rsp+98h+var_68], xmm0
0x18003d355  mov     [rsp+98h+var_58], rax
0x18003d35a  xor     esi, esi
0x18003d35c  movups  [rsp+98h+Buffer], xmm0
0x18003d361  xor     r12d, r12d
0x18003d364  call    cs:__imp_EnterCriticalSection
0x18003d36b  nop     dword ptr [rax+rax+00h]
0x18003d370  mov     dl, 1; Restart
0x18003d372  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003d379  call    cs:__imp_RtlEnumerateGenericTable
0x18003d380  nop     dword ptr [rax+rax+00h]
0x18003d385  mov     rdi, rax
0x18003d388  test    rax, rax
0x18003d38b  jz      loc_18003D51B
0x18003d391  xor     ebp, ebp
0x18003d393  cmp     ebp, [rdi+8]
0x18003d396  jnb     loc_18003D44C
0x18003d39c  mov     eax, ebp
0x18003d39e  lea     rdx, [rsp+98h+Buffer]; Buffer
0x18003d3a3  lea     r13, [rax+rax*2]
0x18003d3a7  mov     rax, [rdi+10h]
0x18003d3ab  mov     ecx, [rax+r13*4]
0x18003d3af  mov     dword ptr [rsp+98h+Buffer], ecx
0x18003d3b3  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003d3ba  mov     qword ptr [rsp+98h+Buffer+8], 0
0x18003d3c3  call    cs:__imp_RtlLookupElementGenericTable
0x18003d3ca  nop     dword ptr [rax+rax+00h]
0x18003d3cf  test    rax, rax
0x18003d3d2  jz      short loc_18003D3E1
0x18003d3d4  mov     rcx, [rdi]
0x18003d3d7  cmp     [rax+8], rcx
0x18003d3db  jnz     short loc_18003D3E1
0x18003d3dd  inc     ebp
0x18003d3df  jmp     short loc_18003D393
0x18003d3e1  cmp     dword ptr [rdi+8], 1
0x18003d3e5  mov     r15, [rdi+10h]
0x18003d3e9  jbe     short loc_18003D41D
0x18003d3eb  lea     ebx, [rbp+1]
0x18003d3ee  not     ebp
0x18003d3f0  add     ebp, [rdi+8]
0x18003d3f3  lea     rcx, [rbx+rbx*2]
0x18003d3f7  lea     rdx, [r15+rcx*4]; Src
0x18003d3fb  lea     rcx, [r15+r13*4]; void *
0x18003d3ff  lea     r8, ds:0[rbp*2]
0x18003d407  add     r8, rbp
0x18003d40a  shl     r8, 2; Size
0x18003d40e  call    memcpy_0
0x18003d413  dec     dword ptr [rdi+8]
0x18003d416  mov     ebp, ebx
0x18003d418  jmp     loc_18003D393
0x18003d41d  mov     dword ptr [rdi+8], 0
0x18003d424  call    cs:__imp_GetProcessHeap
0x18003d42b  nop     dword ptr [rax+rax+00h]
0x18003d430  mov     r8, r15; lpMem
0x18003d433  xor     edx, edx; dwFlags
0x18003d435  mov     rcx, rax; hHeap
0x18003d438  call    cs:__imp_HeapFree
0x18003d43f  nop     dword ptr [rax+rax+00h]
0x18003d444  mov     qword ptr [rdi+10h], 0
0x18003d44c  cmp     dword ptr [rdi+8], 0
0x18003d450  jnz     loc_18003D4F3
0x18003d456  cmp     r12d, esi
0x18003d459  ja      loc_18003D4EA
0x18003d45f  lea     ecx, [rsi+5]
0x18003d462  mov     eax, 0CCCCCCCDh
0x18003d467  mul     ecx
0x18003d469  shr     edx, 2
0x18003d46c  lea     ebp, [rdx+rdx*4]
0x18003d46f  mov     ebx, ebp
0x18003d471  shl     rbx, 3
0x18003d475  call    cs:__imp_GetProcessHeap
0x18003d47c  nop     dword ptr [rax+rax+00h]
0x18003d481  mov     r8, rbx; dwBytes
0x18003d484  mov     edx, 8; dwFlags
0x18003d489  mov     rcx, rax; hHeap
0x18003d48c  call    cs:__imp_HeapAlloc
0x18003d493  nop     dword ptr [rax+rax+00h]
0x18003d498  mov     rbx, rax
0x18003d49b  test    rax, rax
0x18003d49e  jz      short loc_18003D4F3
0x18003d4a0  test    r14, r14
0x18003d4a3  jz      short loc_18003D4D7
0x18003d4a5  mov     r8d, esi
0x18003d4a8  mov     rdx, r14; Src
0x18003d4ab  shl     r8, 3; Size
0x18003d4af  mov     rcx, rax; void *
0x18003d4b2  call    memcpy_0
0x18003d4b7  call    cs:__imp_GetProcessHeap
0x18003d4be  nop     dword ptr [rax+rax+00h]
0x18003d4c3  mov     r8, r14; lpMem
0x18003d4c6  xor     edx, edx; dwFlags
0x18003d4c8  mov     rcx, rax; hHeap
0x18003d4cb  call    cs:__imp_HeapFree
0x18003d4d2  nop     dword ptr [rax+rax+00h]
0x18003d4d7  mov     r12d, ebp
0x18003d4da  mov     r14, rbx
0x18003d4dd  cmp     esi, ebp
0x18003d4df  jnb     short loc_18003D4F3
0x18003d4e1  mov     rax, [rdi]
0x18003d4e4  mov     [rbx+rsi*8], rax
0x18003d4e8  jmp     short loc_18003D4F1
0x18003d4ea  mov     rax, [rdi]
0x18003d4ed  mov     [r14+rsi*8], rax
0x18003d4f1  inc     esi
0x18003d4f3  xor     edx, edx; Restart
0x18003d4f5  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003d4fc  call    cs:__imp_RtlEnumerateGenericTable
0x18003d503  nop     dword ptr [rax+rax+00h]
0x18003d508  mov     rdi, rax
0x18003d50b  test    rax, rax
0x18003d50e  jnz     loc_18003D391
0x18003d514  lea     r15, WPP_GLOBAL_Control
0x18003d51b  xor     edi, edi
0x18003d51d  test    esi, esi
0x18003d51f  jz      short loc_18003D597
0x18003d521  mov     rax, [r14+rdi*8]
0x18003d525  lea     rdx, [rsp+98h+var_68]; Buffer
0x18003d52a  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003d531  mov     qword ptr [rsp+98h+var_68], rax
0x18003d536  mov     dword ptr [rsp+98h+var_68+8], 0
0x18003d53e  call    cs:__imp_RtlLookupElementGenericTable
0x18003d545  nop     dword ptr [rax+rax+00h]
0x18003d54a  test    rax, rax
0x18003d54d  jz      short loc_18003D589
0x18003d54f  mov     rdx, rax; Buffer
0x18003d552  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003d559  call    cs:__imp_RtlDeleteElementGenericTable
0x18003d560  nop     dword ptr [rax+rax+00h]
0x18003d565  mov     rbx, [r14+rdi*8]
0x18003d569  call    cs:__imp_GetProcessHeap
0x18003d570  nop     dword ptr [rax+rax+00h]
0x18003d575  mov     r8, rbx; lpMem
0x18003d578  xor     edx, edx; dwFlags
0x18003d57a  mov     rcx, rax; hHeap
0x18003d57d  call    cs:__imp_HeapFree
0x18003d584  nop     dword ptr [rax+rax+00h]
0x18003d589  mov     qword ptr [r14+rdi*8], 0
0x18003d591  inc     edi
0x18003d593  cmp     edi, esi
0x18003d595  jb      short loc_18003D521
0x18003d597  lea     rcx, ?DnsTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003d59e  call    cs:__imp_LeaveCriticalSection
0x18003d5a5  nop     dword ptr [rax+rax+00h]
0x18003d5aa  test    r14, r14
0x18003d5ad  jz      short loc_18003D5CF
0x18003d5af  call    cs:__imp_GetProcessHeap
0x18003d5b6  nop     dword ptr [rax+rax+00h]
0x18003d5bb  mov     r8, r14; lpMem
0x18003d5be  xor     edx, edx; dwFlags
0x18003d5c0  mov     rcx, rax; hHeap
0x18003d5c3  call    cs:__imp_HeapFree
0x18003d5ca  nop     dword ptr [rax+rax+00h]
0x18003d5cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d5d6  cmp     rcx, r15
0x18003d5d9  jz      short loc_18003D5FC
0x18003d5db  test    byte ptr [rcx+1Ch], 10h
0x18003d5df  jz      short loc_18003D5FC
0x18003d5e1  cmp     byte ptr [rcx+19h], 6
0x18003d5e5  jb      short loc_18003D5FC
0x18003d5e7  mov     rcx, [rcx+10h]
0x18003d5eb  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003d5f2  mov     edx, 41h ; 'A'
0x18003d5f7  call    WPP_SF_
0x18003d5fc  add     rsp, 58h
0x18003d600  pop     r15
0x18003d602  pop     r14
0x18003d604  pop     r13
0x18003d606  pop     r12
0x18003d608  pop     rdi
0x18003d609  pop     rsi
0x18003d60a  pop     rbp
0x18003d60b  pop     rbx
0x18003d60c  retn
```

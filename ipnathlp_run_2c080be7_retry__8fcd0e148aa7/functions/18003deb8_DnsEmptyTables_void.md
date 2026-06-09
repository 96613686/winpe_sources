# DnsEmptyTables(void)

- ea: `0x18003deb8`
- end: `0x18003e11c`
- name: `?DnsEmptyTables@@YAXXZ`
- size: `612`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002362c`
- `0x18002776c`
- `0x18003dbc4`
- `0x18004fc6c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18003deb8`
- `0x180069118`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e01e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e05b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e01e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e05b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e032`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e06f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e032`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e06f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003df09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003df09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e0d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e0d4`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003e004`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003e04f`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003e0bd`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003e004`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003e04f`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003e0bd`
- `ntdll!RtlGetElementGenericTable` at `0x18003df76`
- `ntdll!RtlGetElementGenericTable` at `0x18003e0a7`
- `ntdll!RtlGetElementGenericTable` at `0x18003df76`
- `ntdll!RtlGetElementGenericTable` at `0x18003e0a7`
- `ntdll!RtlNumberGenericTableElements` at `0x18003df1c`
- `ntdll!RtlNumberGenericTableElements` at `0x18003e08a`
- `ntdll!RtlNumberGenericTableElements` at `0x18003df1c`
- `ntdll!RtlNumberGenericTableElements` at `0x18003e08a`

## pseudocode

```c
void DnsEmptyTables(void)
{
  ULONG v0; // eax
  ULONG v1; // esi
  _QWORD *ElementGenericTable; // rax
  __int64 v3; // rbx
  _DWORD *v4; // r15
  void **v5; // r14
  unsigned int v6; // edx
  void *v7; // rdi
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v10; // rax
  ULONG v11; // ebx
  PVOID v12; // rax
  __int128 Buffer; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
  }
  Buffer = 0;
  EnterCriticalSection(&DnsTableLock);
  v0 = RtlNumberGenericTableElements(&g_DnsTable);
  v1 = v0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids, v0);
  }
  while ( v1 )
  {
    ElementGenericTable = RtlGetElementGenericTable(&g_DnsTable, --v1);
    v3 = 0;
    *((_QWORD *)&Buffer + 1) = 0;
    v4 = ElementGenericTable;
    v5 = (void **)(ElementGenericTable + 2);
    if ( *((_DWORD *)ElementGenericTable + 2) )
    {
      do
      {
        v6 = *((_DWORD *)*v5 + 3 * v3);
        LODWORD(Buffer) = v6;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_dDDDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned __int8)Buffer,
            BYTE2(v6),
            (unsigned int)v3,
            (unsigned __int8)Buffer,
            BYTE1(v6),
            BYTE2(v6),
            HIBYTE(v6));
        }
        RtlDeleteElementGenericTable(&g_ReverseDnsTable, &Buffer);
        v3 = (unsigned int)(v3 + 1);
      }
      while ( (unsigned int)v3 < v4[2] );
    }
    v7 = *(void **)v4;
    v8 = *v5;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    *v5 = 0;
    RtlDeleteElementGenericTable(&g_DnsTable, v4);
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v7);
  }
  v11 = RtlNumberGenericTableElements(&g_ReverseDnsTable);
  while ( v11 )
  {
    v12 = RtlGetElementGenericTable(&g_ReverseDnsTable, --v11);
    RtlDeleteElementGenericTable(&g_ReverseDnsTable, v12);
  }
  LeaveCriticalSection(&DnsTableLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
  }
}

```

## disassembly

```asm
0x18003deb8  push    rbx
0x18003deba  push    rsi
0x18003debb  push    rdi
0x18003debc  push    r13
0x18003debe  push    r14
0x18003dec0  push    r15
0x18003dec2  sub     rsp, 58h
0x18003dec6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003decd  lea     r13, WPP_GLOBAL_Control
0x18003ded4  cmp     rcx, r13
0x18003ded7  jz      short loc_18003DEFA
0x18003ded9  test    byte ptr [rcx+1Ch], 10h
0x18003dedd  jz      short loc_18003DEFA
0x18003dedf  cmp     byte ptr [rcx+19h], 6
0x18003dee3  jb      short loc_18003DEFA
0x18003dee5  mov     rcx, [rcx+10h]
0x18003dee9  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003def0  mov     edx, 10h
0x18003def5  call    WPP_SF_
0x18003defa  xorps   xmm0, xmm0
0x18003defd  lea     rcx, ?DnsTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003df04  movups  [rsp+88h+Buffer], xmm0
0x18003df09  call    cs:__imp_EnterCriticalSection
0x18003df10  nop     dword ptr [rax+rax+00h]
0x18003df15  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003df1c  call    cs:__imp_RtlNumberGenericTableElements
0x18003df23  nop     dword ptr [rax+rax+00h]
0x18003df28  mov     esi, eax
0x18003df2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df31  cmp     rcx, r13
0x18003df34  jz      loc_18003E07B
0x18003df3a  test    byte ptr [rcx+1Ch], 10h
0x18003df3e  jz      loc_18003E07B
0x18003df44  cmp     byte ptr [rcx+19h], 5
0x18003df48  jb      loc_18003E07B
0x18003df4e  mov     rcx, [rcx+10h]
0x18003df52  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003df59  mov     edx, 11h
0x18003df5e  mov     r9d, eax
0x18003df61  call    WPP_SF_d
0x18003df66  jmp     loc_18003E07B
0x18003df6b  dec     esi
0x18003df6d  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003df74  mov     edx, esi; I
0x18003df76  call    cs:__imp_RtlGetElementGenericTable
0x18003df7d  nop     dword ptr [rax+rax+00h]
0x18003df82  xor     ebx, ebx
0x18003df84  mov     qword ptr [rsp+88h+Buffer+8], 0
0x18003df8d  mov     r15, rax
0x18003df90  lea     r14, [rax+10h]
0x18003df94  cmp     [rax+8], ebx
0x18003df97  jbe     short loc_18003E018
0x18003df99  mov     rax, [r14]
0x18003df9c  lea     rcx, [rbx+rbx*2]
0x18003dfa0  mov     edx, [rax+rcx*4]
0x18003dfa3  mov     dword ptr [rsp+88h+Buffer], edx
0x18003dfa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dfae  cmp     rcx, r13
0x18003dfb1  jz      short loc_18003DFF8
0x18003dfb3  test    byte ptr [rcx+1Ch], 10h
0x18003dfb7  jz      short loc_18003DFF8
0x18003dfb9  cmp     byte ptr [rcx+19h], 5
0x18003dfbd  jb      short loc_18003DFF8
0x18003dfbf  mov     rcx, [rcx+10h]
0x18003dfc3  mov     eax, edx
0x18003dfc5  mov     r9d, edx
0x18003dfc8  shr     eax, 10h
0x18003dfcb  shr     r9d, 18h
0x18003dfcf  mov     [rsp+88h+var_50], r9d
0x18003dfd4  mov     r9d, ebx
0x18003dfd7  shr     edx, 8
0x18003dfda  movzx   r8d, al
0x18003dfde  movzx   eax, dl
0x18003dfe1  movzx   edx, byte ptr [rsp+88h+Buffer]
0x18003dfe6  mov     [rsp+88h+var_58], r8d
0x18003dfeb  mov     [rsp+88h+var_60], eax
0x18003dfef  mov     [rsp+88h+var_68], edx
0x18003dff3  call    WPP_SF_dDDDD
0x18003dff8  lea     rdx, [rsp+88h+Buffer]; Buffer
0x18003dffd  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003e004  call    cs:__imp_RtlDeleteElementGenericTable
0x18003e00b  nop     dword ptr [rax+rax+00h]
0x18003e010  inc     ebx
0x18003e012  cmp     ebx, [r15+8]
0x18003e016  jb      short loc_18003DF99
0x18003e018  mov     rdi, [r15]
0x18003e01b  mov     rbx, [r14]
0x18003e01e  call    cs:__imp_GetProcessHeap
0x18003e025  nop     dword ptr [rax+rax+00h]
0x18003e02a  mov     r8, rbx; lpMem
0x18003e02d  xor     edx, edx; dwFlags
0x18003e02f  mov     rcx, rax; hHeap
0x18003e032  call    cs:__imp_HeapFree
0x18003e039  nop     dword ptr [rax+rax+00h]
0x18003e03e  mov     rdx, r15; Buffer
0x18003e041  mov     qword ptr [r14], 0
0x18003e048  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003e04f  call    cs:__imp_RtlDeleteElementGenericTable
0x18003e056  nop     dword ptr [rax+rax+00h]
0x18003e05b  call    cs:__imp_GetProcessHeap
0x18003e062  nop     dword ptr [rax+rax+00h]
0x18003e067  mov     r8, rdi; lpMem
0x18003e06a  xor     edx, edx; dwFlags
0x18003e06c  mov     rcx, rax; hHeap
0x18003e06f  call    cs:__imp_HeapFree
0x18003e076  nop     dword ptr [rax+rax+00h]
0x18003e07b  test    esi, esi
0x18003e07d  jnz     loc_18003DF6B
0x18003e083  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003e08a  call    cs:__imp_RtlNumberGenericTableElements
0x18003e091  nop     dword ptr [rax+rax+00h]
0x18003e096  mov     ebx, eax
0x18003e098  test    eax, eax
0x18003e09a  jz      short loc_18003E0CD
0x18003e09c  dec     ebx
0x18003e09e  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003e0a5  mov     edx, ebx; I
0x18003e0a7  call    cs:__imp_RtlGetElementGenericTable
0x18003e0ae  nop     dword ptr [rax+rax+00h]
0x18003e0b3  mov     rdx, rax; Buffer
0x18003e0b6  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003e0bd  call    cs:__imp_RtlDeleteElementGenericTable
0x18003e0c4  nop     dword ptr [rax+rax+00h]
0x18003e0c9  test    ebx, ebx
0x18003e0cb  jnz     short loc_18003E09C
0x18003e0cd  lea     rcx, ?DnsTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003e0d4  call    cs:__imp_LeaveCriticalSection
0x18003e0db  nop     dword ptr [rax+rax+00h]
0x18003e0e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e0e7  cmp     rcx, r13
0x18003e0ea  jz      short loc_18003E10D
0x18003e0ec  test    byte ptr [rcx+1Ch], 10h
0x18003e0f0  jz      short loc_18003E10D
0x18003e0f2  cmp     byte ptr [rcx+19h], 6
0x18003e0f6  jb      short loc_18003E10D
0x18003e0f8  mov     rcx, [rcx+10h]
0x18003e0fc  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003e103  mov     edx, 13h
0x18003e108  call    WPP_SF_
0x18003e10d  add     rsp, 58h
0x18003e111  pop     r15
0x18003e113  pop     r14
0x18003e115  pop     r13
0x18003e117  pop     rdi
0x18003e118  pop     rsi
0x18003e119  pop     rbx
0x18003e11a  retn
```

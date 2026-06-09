# UpdateArpCache

- ea: `0x180033438`
- end: `0x18003364b`
- name: `UpdateArpCache`
- size: `531`
- prototype: `__int64 __usercall@<rax>(struct in_addr in@<ecx>, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180032b60`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000c180`
- `0x180033438`
- `0x1800cc982`

## import_xrefs

- `IPHLPAPI!CreateIpNetEntry` at `0x1800335a4`
- `IPHLPAPI!CreateIpNetEntry` at `0x1800335a4`
- `IPHLPAPI!DeleteIpNetEntry` at `0x1800335d5`
- `IPHLPAPI!DeleteIpNetEntry` at `0x1800335d5`
- `WS2_32!__imp_inet_ntoa` at `0x1800334eb`
- `WS2_32!__imp_inet_ntoa` at `0x1800334eb`
- `KERNEL32!HeapAlloc` at `0x18003352e`
- `KERNEL32!HeapAlloc` at `0x18003352e`
- `KERNEL32!EnterCriticalSection` at `0x180033474`
- `KERNEL32!EnterCriticalSection` at `0x180033474`
- `KERNEL32!LeaveCriticalSection` at `0x1800334bd`
- `KERNEL32!LeaveCriticalSection` at `0x1800334bd`
- `KERNEL32!HeapFree` at `0x180033623`
- `KERNEL32!HeapFree` at `0x180033623`

## pseudocode

```c
__int64 __fastcall UpdateArpCache(struct in_addr in, DWORD a2, const void *a3, unsigned int a4, int a5)
{
  IF_INDEX v5; // ebp
  size_t v6; // rsi
  int v7; // ebx
  DWORD IpNetEntry; // ebx
  unsigned int i; // ecx
  __int64 v13; // rdx
  char *v14; // rax
  MIB_IPNETROW_LH *v15; // rax
  MIB_IPNETROW_LH *v16; // rdi
  _QWORD *v17; // rcx
  __int64 v18; // rdx

  v5 = 0;
  v6 = a4;
  v7 = 0;
  if ( a4 > 8 )
    return 87;
  EnterCriticalSection(lpCriticalSection);
  for ( i = 0; i < (unsigned int)qword_1801556CC; ++i )
  {
    if ( v7 )
      break;
    v13 = *(__int64 *)((char *)&qword_1801556CC + 4) + dword_1801556D8 * i;
    if ( *(_DWORD *)(v13 + 16) == in )
    {
      v5 = *(_DWORD *)(v13 + 20);
      v7 = 1;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      v14 = inet_ntoa(in);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids, v14);
    }
    return 2;
  }
  v15 = (MIB_IPNETROW_LH *)HeapAlloc(gDhcpHeap, 8u, 0x18u);
  v16 = v15;
  if ( v15 )
  {
    v15->dwIndex = v5;
    v15->dwPhysAddrLen = v6;
    memcpy_0(v15->bPhysAddr, a3, v6);
    v16->dwAddr = a2;
    v16->dwType = 3;
    if ( a5 == 1 )
    {
      IpNetEntry = CreateIpNetEntry(v16);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_26;
      v18 = 24;
    }
    else
    {
      IpNetEntry = DeleteIpNetEntry(v16);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_26;
      v18 = 25;
    }
    WPP_SF_D(v17[2], v18, &WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids, IpNetEntry);
LABEL_26:
    HeapFree(gDhcpHeap, 0, v16);
    return IpNetEntry;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids);
  return 14;
}

```

## disassembly

```asm
0x180033438  mov     [rsp+arg_0], rbx
0x18003343d  mov     [rsp+arg_8], rbp
0x180033442  mov     [rsp+arg_10], rsi
0x180033447  push    rdi
0x180033448  push    r14
0x18003344a  push    r15
0x18003344c  sub     rsp, 20h
0x180033450  xor     ebp, ebp
0x180033452  mov     esi, r9d
0x180033455  xor     ebx, ebx
0x180033457  mov     r14, r8
0x18003345a  mov     r15d, edx
0x18003345d  mov     edi, ecx
0x18003345f  cmp     r9d, 8
0x180033463  jbe     short loc_18003346D
0x180033465  lea     ebx, [rbp+57h]
0x180033468  jmp     loc_18003362F
0x18003346d  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x180033474  call    cs:__imp_EnterCriticalSection
0x18003347b  nop     dword ptr [rax+rax+00h]
0x180033480  mov     r8, cs:qword_1801556CC
0x180033487  xor     ecx, ecx
0x180033489  test    r8d, r8d
0x18003348c  jz      short loc_1800334B6
0x18003348e  test    ebx, ebx
0x180033490  jnz     short loc_1800334B6
0x180033492  mov     edx, ecx
0x180033494  imul    edx, cs:dword_1801556D8
0x18003349b  add     rdx, cs:qword_1801556CC+4
0x1800334a2  cmp     [rdx+10h], edi
0x1800334a5  jnz     short loc_1800334AF
0x1800334a7  mov     ebp, [rdx+14h]
0x1800334aa  mov     ebx, 1
0x1800334af  inc     ecx
0x1800334b1  cmp     ecx, r8d
0x1800334b4  jb      short loc_18003348E
0x1800334b6  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x1800334bd  call    cs:__imp_LeaveCriticalSection
0x1800334c4  nop     dword ptr [rax+rax+00h]
0x1800334c9  test    ebx, ebx
0x1800334cb  jnz     short loc_18003351E
0x1800334cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334d4  lea     rax, WPP_GLOBAL_Control
0x1800334db  cmp     rcx, rax
0x1800334de  jz      short loc_180033514
0x1800334e0  test    dword ptr [rcx+1Ch], 8000h
0x1800334e7  jz      short loc_180033514
0x1800334e9  mov     ecx, edi; in
0x1800334eb  call    cs:__imp_inet_ntoa
0x1800334f2  nop     dword ptr [rax+rax+00h]
0x1800334f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334fe  lea     edx, [rbx+16h]
0x180033501  mov     r9, rax
0x180033504  lea     r8, WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids
0x18003350b  mov     rcx, [rcx+10h]
0x18003350f  call    WPP_SF_s
0x180033514  mov     ebx, 2
0x180033519  jmp     loc_18003362F
0x18003351e  mov     rcx, cs:gDhcpHeap; hHeap
0x180033525  mov     edx, 8; dwFlags
0x18003352a  lea     r8d, [rdx+10h]; dwBytes
0x18003352e  call    cs:__imp_HeapAlloc
0x180033535  nop     dword ptr [rax+rax+00h]
0x18003353a  mov     rdi, rax
0x18003353d  test    rax, rax
0x180033540  jnz     short loc_18003357B
0x180033542  mov     rcx, cs:WPP_GLOBAL_Control
0x180033549  lea     rax, WPP_GLOBAL_Control
0x180033550  cmp     rcx, rax
0x180033553  jz      short loc_180033571
0x180033555  test    dword ptr [rcx+1Ch], 8000h
0x18003355c  jz      short loc_180033571
0x18003355e  mov     rcx, [rcx+10h]
0x180033562  lea     edx, [rdi+17h]
0x180033565  lea     r8, WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids
0x18003356c  call    WPP_SF_
0x180033571  mov     ebx, 0Eh
0x180033576  jmp     loc_18003362F
0x18003357b  mov     r8, rsi; Size
0x18003357e  mov     [rax], ebp
0x180033580  lea     rcx, [rax+8]; void *
0x180033584  mov     [rax+4], esi
0x180033587  mov     rdx, r14; Src
0x18003358a  call    memcpy_0
0x18003358f  cmp     [rsp+38h+arg_20], 1
0x180033594  mov     rcx, rdi; pArpEntry
0x180033597  mov     [rdi+10h], r15d
0x18003359b  mov     dword ptr [rdi+14h], 3
0x1800335a2  jnz     short loc_1800335D5
0x1800335a4  call    cs:__imp_CreateIpNetEntry
0x1800335ab  nop     dword ptr [rax+rax+00h]
0x1800335b0  mov     ebx, eax
0x1800335b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800335b9  lea     rax, WPP_GLOBAL_Control
0x1800335c0  cmp     rcx, rax
0x1800335c3  jz      short loc_180033617
0x1800335c5  test    dword ptr [rcx+1Ch], 8000h
0x1800335cc  jz      short loc_180033617
0x1800335ce  mov     edx, 18h
0x1800335d3  jmp     short loc_180033604
0x1800335d5  call    cs:__imp_DeleteIpNetEntry
0x1800335dc  nop     dword ptr [rax+rax+00h]
0x1800335e1  mov     ebx, eax
0x1800335e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800335ea  lea     rax, WPP_GLOBAL_Control
0x1800335f1  cmp     rcx, rax
0x1800335f4  jz      short loc_180033617
0x1800335f6  test    dword ptr [rcx+1Ch], 8000h
0x1800335fd  jz      short loc_180033617
0x1800335ff  mov     edx, 19h
0x180033604  mov     rcx, [rcx+10h]
0x180033608  lea     r8, WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids
0x18003360f  mov     r9d, ebx
0x180033612  call    WPP_SF_D
0x180033617  mov     rcx, cs:gDhcpHeap; hHeap
0x18003361e  mov     r8, rdi; lpMem
0x180033621  xor     edx, edx; dwFlags
0x180033623  call    cs:__imp_HeapFree
0x18003362a  nop     dword ptr [rax+rax+00h]
0x18003362f  mov     rbp, [rsp+38h+arg_8]
0x180033634  mov     eax, ebx
0x180033636  mov     rbx, [rsp+38h+arg_0]
0x18003363b  mov     rsi, [rsp+38h+arg_10]
0x180033640  add     rsp, 20h
0x180033644  pop     r15
0x180033646  pop     r14
0x180033648  pop     rdi
0x180033649  retn
```

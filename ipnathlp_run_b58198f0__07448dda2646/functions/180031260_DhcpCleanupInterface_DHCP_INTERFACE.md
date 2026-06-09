# DhcpCleanupInterface(_DHCP_INTERFACE *)

- ea: `0x180031260`
- end: `0x1800313e4`
- name: `?DhcpCleanupInterface@@YAXPEAU_DHCP_INTERFACE@@@Z`
- size: `388`
- prototype: `void __fastcall(struct _DHCP_INTERFACE *lpMem)`
- caller_count: `21`
- callee_count: `3`
- tags: ``

## callers

- `0x1800027d0`
- `0x18000c930`
- `0x18002b3f0`
- `0x18002bd70`
- `0x18002f74c`
- `0x18002fa58`
- `0x180030e58`
- `0x180037ce0`
- `0x1800383d0`
- `0x180041c04`
- `0x180047a30`
- `0x18004898c`
- `0x1800492ec`
- `0x18005cd38`
- `0x18005cfd0`
- `0x18005d5c0`
- `0x18005d84c`
- `0x18005dc70`
- `0x18005dfc8`
- `0x18005e164`
- `0x180064384`

## callees

- `0x18000ca20`
- `0x180013720`
- `0x180031260`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800312e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031310`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031347`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003138c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800312e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031310`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031347`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003138c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800312f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031324`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003135b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800313a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800312f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031324`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003135b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800313a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031380`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031380`

## pseudocode

```c
void __fastcall DhcpCleanupInterface(struct _DHCP_INTERFACE *lpMem)
{
  __int64 v2; // rbx
  void *v3; // rsi
  HANDLE ProcessHeap; // rax
  void *v5; // rbx
  HANDLE v6; // rax
  void *v7; // rbx
  HANDLE v8; // rax
  HANDLE v9; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_ddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids,
      *((unsigned int *)lpMem + 15),
      *((_DWORD *)lpMem + 16),
      *((_DWORD *)lpMem + 19));
  }
  if ( *((_DWORD *)lpMem + 20) && *((_QWORD *)lpMem + 11) )
  {
    if ( !DhcpArpForDad )
    {
      v2 = 0;
      do
      {
        v3 = *(void **)(*((_QWORD *)lpMem + 11) + 80 * v2 + 72);
        if ( v3 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v3);
        }
        v2 = (unsigned int)(v2 + 1);
      }
      while ( (unsigned int)v2 < *((_DWORD *)lpMem + 20) );
    }
    v5 = (void *)*((_QWORD *)lpMem + 11);
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
    *((_QWORD *)lpMem + 11) = 0;
  }
  if ( *((_DWORD *)lpMem + 24) )
  {
    v7 = (void *)*((_QWORD *)lpMem + 13);
    if ( v7 )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v7);
      *((_QWORD *)lpMem + 13) = 0;
      *((_DWORD *)lpMem + 24) = 0;
    }
  }
  --DhcpInterfaceCount;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 16));
  v9 = GetProcessHeap();
  HeapFree(v9, 0, lpMem);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids);
  }
}

```

## disassembly

```asm
0x180031260  push    rbx
0x180031262  push    rsi
0x180031263  push    rdi
0x180031264  push    r14
0x180031266  sub     rsp, 38h
0x18003126a  mov     rdi, rcx
0x18003126d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031274  lea     r14, WPP_GLOBAL_Control
0x18003127b  cmp     rcx, r14
0x18003127e  jz      short loc_1800312B3
0x180031280  test    byte ptr [rcx+1Ch], 2
0x180031284  jz      short loc_1800312B3
0x180031286  cmp     byte ptr [rcx+19h], 6
0x18003128a  jb      short loc_1800312B3
0x18003128c  mov     eax, [rdi+4Ch]
0x18003128f  lea     r8, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids
0x180031296  mov     r9d, [rdi+3Ch]
0x18003129a  mov     edx, 2Ch ; ','
0x18003129f  mov     rcx, [rcx+10h]
0x1800312a3  mov     [rsp+58h+var_30], eax
0x1800312a7  mov     eax, [rdi+40h]
0x1800312aa  mov     [rsp+58h+var_38], eax
0x1800312ae  call    WPP_SF_ddD
0x1800312b3  mov     eax, [rdi+50h]
0x1800312b6  test    eax, eax
0x1800312b8  jz      short loc_180031338
0x1800312ba  cmp     qword ptr [rdi+58h], 0
0x1800312bf  jz      short loc_180031338
0x1800312c1  cmp     cs:?DhcpArpForDad@@3HA, 0; int DhcpArpForDad
0x1800312c8  jnz     short loc_18003130C
0x1800312ca  xor     ebx, ebx
0x1800312cc  test    eax, eax
0x1800312ce  jz      short loc_18003130C
0x1800312d0  mov     rax, [rdi+58h]
0x1800312d4  lea     rcx, [rbx+rbx*4]
0x1800312d8  add     rcx, rcx
0x1800312db  mov     rsi, [rax+rcx*8+48h]
0x1800312e0  test    rsi, rsi
0x1800312e3  jz      short loc_180031305
0x1800312e5  call    cs:__imp_GetProcessHeap
0x1800312ec  nop     dword ptr [rax+rax+00h]
0x1800312f1  mov     r8, rsi; lpMem
0x1800312f4  xor     edx, edx; dwFlags
0x1800312f6  mov     rcx, rax; hHeap
0x1800312f9  call    cs:__imp_HeapFree
0x180031300  nop     dword ptr [rax+rax+00h]
0x180031305  inc     ebx
0x180031307  cmp     ebx, [rdi+50h]
0x18003130a  jb      short loc_1800312D0
0x18003130c  mov     rbx, [rdi+58h]
0x180031310  call    cs:__imp_GetProcessHeap
0x180031317  nop     dword ptr [rax+rax+00h]
0x18003131c  mov     r8, rbx; lpMem
0x18003131f  xor     edx, edx; dwFlags
0x180031321  mov     rcx, rax; hHeap
0x180031324  call    cs:__imp_HeapFree
0x18003132b  nop     dword ptr [rax+rax+00h]
0x180031330  mov     qword ptr [rdi+58h], 0
0x180031338  cmp     dword ptr [rdi+60h], 0
0x18003133c  jbe     short loc_180031376
0x18003133e  mov     rbx, [rdi+68h]
0x180031342  test    rbx, rbx
0x180031345  jz      short loc_180031376
0x180031347  call    cs:__imp_GetProcessHeap
0x18003134e  nop     dword ptr [rax+rax+00h]
0x180031353  mov     r8, rbx; lpMem
0x180031356  xor     edx, edx; dwFlags
0x180031358  mov     rcx, rax; hHeap
0x18003135b  call    cs:__imp_HeapFree
0x180031362  nop     dword ptr [rax+rax+00h]
0x180031367  mov     qword ptr [rdi+68h], 0
0x18003136f  mov     dword ptr [rdi+60h], 0
0x180031376  dec     cs:?DhcpInterfaceCount@@3JA; long DhcpInterfaceCount
0x18003137c  lea     rcx, [rdi+10h]; lpCriticalSection
0x180031380  call    cs:__imp_DeleteCriticalSection
0x180031387  nop     dword ptr [rax+rax+00h]
0x18003138c  call    cs:__imp_GetProcessHeap
0x180031393  nop     dword ptr [rax+rax+00h]
0x180031398  mov     r8, rdi; lpMem
0x18003139b  xor     edx, edx; dwFlags
0x18003139d  mov     rcx, rax; hHeap
0x1800313a0  call    cs:__imp_HeapFree
0x1800313a7  nop     dword ptr [rax+rax+00h]
0x1800313ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313b3  cmp     rcx, r14
0x1800313b6  jz      short loc_1800313D9
0x1800313b8  test    byte ptr [rcx+1Ch], 2
0x1800313bc  jz      short loc_1800313D9
0x1800313be  cmp     byte ptr [rcx+19h], 6
0x1800313c2  jb      short loc_1800313D9
0x1800313c4  mov     rcx, [rcx+10h]
0x1800313c8  lea     r8, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids
0x1800313cf  mov     edx, 2Dh ; '-'
0x1800313d4  call    WPP_SF_
0x1800313d9  add     rsp, 38h
0x1800313dd  pop     r14
0x1800313df  pop     rdi
0x1800313e0  pop     rsi
0x1800313e1  pop     rbx
0x1800313e2  retn
```

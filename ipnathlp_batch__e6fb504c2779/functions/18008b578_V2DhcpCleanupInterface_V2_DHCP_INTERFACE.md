# V2DhcpCleanupInterface(_V2_DHCP_INTERFACE *)

- ea: `0x18008b578`
- end: `0x18008b715`
- name: `?V2DhcpCleanupInterface@@YAXPEAU_V2_DHCP_INTERFACE@@@Z`
- size: `413`
- prototype: `void __fastcall(struct _V2_DHCP_INTERFACE *lpMem)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180004070`
- `0x18000b500`
- `0x18000fec0`
- `0x18002b960`
- `0x18002c510`
- `0x18002cc50`
- `0x18002d8f4`
- `0x18002eb94`
- `0x1800394e8`
- `0x180041e00`
- `0x18004cb30`
- `0x18004d200`
- `0x18008b720`
- `0x18008bd10`
- `0x18008c4ec`
- `0x18008c5f0`
- `0x18008cad8`
- `0x18008d408`

## callees

- `0x18000ca20`
- `0x18008b578`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b64b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b67c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b6bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b64b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b67c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b6bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008b65f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008b690`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008b6d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008b65f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008b690`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008b6d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b6b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b6b1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008b5f7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008b5f7`

## pseudocode

```c
void __fastcall V2DhcpCleanupInterface(struct _V2_DHCP_INTERFACE *lpMem)
{
  PVOID *v2; // rcx
  __int64 v3; // rbx
  void *v4; // rsi
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax
  HANDLE v8; // rax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)lpMem + 17) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 4u )
      WPP_SF_(v2[2], 36, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids);
    SetEvent(*((HANDLE *)lpMem + 17));
  }
  else
  {
    if ( *((_DWORD *)lpMem + 32) && *((_QWORD *)lpMem + 18) )
    {
      if ( !V2DhcpArpForDad )
      {
        v3 = 0;
        do
        {
          v4 = *(void **)(*((_QWORD *)lpMem + 18) + 80 * v3 + 72);
          if ( v4 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v4);
          }
          v3 = (unsigned int)(v3 + 1);
        }
        while ( (unsigned int)v3 < *((_DWORD *)lpMem + 32) );
      }
      v6 = (void *)*((_QWORD *)lpMem + 18);
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v6);
      *((_QWORD *)lpMem + 18) = 0;
    }
    --V2DhcpInterfaceCount;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 16));
    v8 = GetProcessHeap();
    HeapFree(v8, 0, lpMem);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids);
  }
}

```

## disassembly

```asm
0x18008b578  push    rbx
0x18008b57a  push    rsi
0x18008b57b  push    rdi
0x18008b57c  push    r15
0x18008b57e  sub     rsp, 28h
0x18008b582  mov     rdi, rcx
0x18008b585  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b58c  lea     r15, WPP_GLOBAL_Control
0x18008b593  cmp     rcx, r15
0x18008b596  jz      short loc_18008B5C0
0x18008b598  test    byte ptr [rcx+1Ch], 2
0x18008b59c  jz      short loc_18008B5C0
0x18008b59e  cmp     byte ptr [rcx+19h], 6
0x18008b5a2  jb      short loc_18008B5C0
0x18008b5a4  mov     rcx, [rcx+10h]
0x18008b5a8  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x18008b5af  mov     edx, 23h ; '#'
0x18008b5b4  call    WPP_SF_
0x18008b5b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b5c0  cmp     qword ptr [rdi+88h], 0
0x18008b5c8  jz      short loc_18008B608
0x18008b5ca  cmp     rcx, r15
0x18008b5cd  jz      short loc_18008B5F0
0x18008b5cf  test    byte ptr [rcx+1Ch], 2
0x18008b5d3  jz      short loc_18008B5F0
0x18008b5d5  cmp     byte ptr [rcx+19h], 4
0x18008b5d9  jb      short loc_18008B5F0
0x18008b5db  mov     rcx, [rcx+10h]
0x18008b5df  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x18008b5e6  mov     edx, 24h ; '$'
0x18008b5eb  call    WPP_SF_
0x18008b5f0  mov     rcx, [rdi+88h]; hEvent
0x18008b5f7  call    cs:__imp_SetEvent
0x18008b5fe  nop     dword ptr [rax+rax+00h]
0x18008b603  jmp     loc_18008B6DD
0x18008b608  mov     eax, [rdi+80h]
0x18008b60e  test    eax, eax
0x18008b610  jz      loc_18008B6A7
0x18008b616  cmp     qword ptr [rdi+90h], 0
0x18008b61e  jz      loc_18008B6A7
0x18008b624  cmp     cs:?V2DhcpArpForDad@@3HA, 0; int V2DhcpArpForDad
0x18008b62b  jnz     short loc_18008B675
0x18008b62d  xor     ebx, ebx
0x18008b62f  test    eax, eax
0x18008b631  jz      short loc_18008B675
0x18008b633  mov     rax, [rdi+90h]
0x18008b63a  lea     rcx, [rbx+rbx*4]
0x18008b63e  add     rcx, rcx
0x18008b641  mov     rsi, [rax+rcx*8+48h]
0x18008b646  test    rsi, rsi
0x18008b649  jz      short loc_18008B66B
0x18008b64b  call    cs:__imp_GetProcessHeap
0x18008b652  nop     dword ptr [rax+rax+00h]
0x18008b657  mov     r8, rsi; lpMem
0x18008b65a  xor     edx, edx; dwFlags
0x18008b65c  mov     rcx, rax; hHeap
0x18008b65f  call    cs:__imp_HeapFree
0x18008b666  nop     dword ptr [rax+rax+00h]
0x18008b66b  inc     ebx
0x18008b66d  cmp     ebx, [rdi+80h]
0x18008b673  jb      short loc_18008B633
0x18008b675  mov     rbx, [rdi+90h]
0x18008b67c  call    cs:__imp_GetProcessHeap
0x18008b683  nop     dword ptr [rax+rax+00h]
0x18008b688  mov     r8, rbx; lpMem
0x18008b68b  xor     edx, edx; dwFlags
0x18008b68d  mov     rcx, rax; hHeap
0x18008b690  call    cs:__imp_HeapFree
0x18008b697  nop     dword ptr [rax+rax+00h]
0x18008b69c  mov     qword ptr [rdi+90h], 0
0x18008b6a7  dec     cs:?V2DhcpInterfaceCount@@3JA; long V2DhcpInterfaceCount
0x18008b6ad  lea     rcx, [rdi+10h]; lpCriticalSection
0x18008b6b1  call    cs:__imp_DeleteCriticalSection
0x18008b6b8  nop     dword ptr [rax+rax+00h]
0x18008b6bd  call    cs:__imp_GetProcessHeap
0x18008b6c4  nop     dword ptr [rax+rax+00h]
0x18008b6c9  mov     r8, rdi; lpMem
0x18008b6cc  xor     edx, edx; dwFlags
0x18008b6ce  mov     rcx, rax; hHeap
0x18008b6d1  call    cs:__imp_HeapFree
0x18008b6d8  nop     dword ptr [rax+rax+00h]
0x18008b6dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b6e4  cmp     rcx, r15
0x18008b6e7  jz      short loc_18008B70A
0x18008b6e9  test    byte ptr [rcx+1Ch], 2
0x18008b6ed  jz      short loc_18008B70A
0x18008b6ef  cmp     byte ptr [rcx+19h], 6
0x18008b6f3  jb      short loc_18008B70A
0x18008b6f5  mov     rcx, [rcx+10h]
0x18008b6f9  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x18008b700  mov     edx, 25h ; '%'
0x18008b705  call    WPP_SF_
0x18008b70a  add     rsp, 28h
0x18008b70e  pop     r15
0x18008b710  pop     rdi
0x18008b711  pop     rsi
0x18008b712  pop     rbx
0x18008b713  retn
```

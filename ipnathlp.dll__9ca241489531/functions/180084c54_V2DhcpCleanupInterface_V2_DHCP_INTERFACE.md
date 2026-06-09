# V2DhcpCleanupInterface(_V2_DHCP_INTERFACE *)

- ea: `0x180084c54`
- end: `0x180084db8`
- name: `?V2DhcpCleanupInterface@@YAXPEAU_V2_DHCP_INTERFACE@@@Z`
- size: `356`
- prototype: `void __fastcall(struct _V2_DHCP_INTERFACE *lpMem)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f10`
- `0x18000ad20`
- `0x18000f328`
- `0x18001f6c0`
- `0x180020210`
- `0x180020914`
- `0x180021500`
- `0x18002a53c`
- `0x180036868`
- `0x18003ea70`
- `0x180048ef4`
- `0x18004959c`
- `0x180084dc0`
- `0x180085330`
- `0x180085a7c`
- `0x180085b74`
- `0x180085ff4`
- `0x180086904`

## callees

- `0x18000c110`
- `0x180084c54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084d19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084d3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084d6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084d19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084d3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084d6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084d27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084d4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084d7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084d27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084d4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084d7b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180084d67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180084d67`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180084cd3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180084cd3`

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
0x180084c54  push    rbx
0x180084c56  push    rsi
0x180084c57  push    rdi
0x180084c58  push    r15
0x180084c5a  sub     rsp, 28h
0x180084c5e  mov     rdi, rcx
0x180084c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180084c68  lea     r15, WPP_GLOBAL_Control
0x180084c6f  cmp     rcx, r15
0x180084c72  jz      short loc_180084C9C
0x180084c74  test    byte ptr [rcx+1Ch], 2
0x180084c78  jz      short loc_180084C9C
0x180084c7a  cmp     byte ptr [rcx+19h], 6
0x180084c7e  jb      short loc_180084C9C
0x180084c80  mov     rcx, [rcx+10h]
0x180084c84  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x180084c8b  mov     edx, 23h ; '#'
0x180084c90  call    WPP_SF_
0x180084c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180084c9c  cmp     qword ptr [rdi+88h], 0
0x180084ca4  jz      short loc_180084CDE
0x180084ca6  cmp     rcx, r15
0x180084ca9  jz      short loc_180084CCC
0x180084cab  test    byte ptr [rcx+1Ch], 2
0x180084caf  jz      short loc_180084CCC
0x180084cb1  cmp     byte ptr [rcx+19h], 4
0x180084cb5  jb      short loc_180084CCC
0x180084cb7  mov     rcx, [rcx+10h]
0x180084cbb  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x180084cc2  mov     edx, 24h ; '$'
0x180084cc7  call    WPP_SF_
0x180084ccc  mov     rcx, [rdi+88h]; hEvent
0x180084cd3  call    cs:__imp_SetEvent
0x180084cd9  jmp     loc_180084D81
0x180084cde  mov     eax, [rdi+80h]
0x180084ce4  test    eax, eax
0x180084ce6  jz      short loc_180084D5D
0x180084ce8  cmp     qword ptr [rdi+90h], 0
0x180084cf0  jz      short loc_180084D5D
0x180084cf2  cmp     cs:?V2DhcpArpForDad@@3HA, 0; int V2DhcpArpForDad
0x180084cf9  jnz     short loc_180084D37
0x180084cfb  xor     ebx, ebx
0x180084cfd  test    eax, eax
0x180084cff  jz      short loc_180084D37
0x180084d01  mov     rax, [rdi+90h]
0x180084d08  lea     rcx, [rbx+rbx*4]
0x180084d0c  add     rcx, rcx
0x180084d0f  mov     rsi, [rax+rcx*8+48h]
0x180084d14  test    rsi, rsi
0x180084d17  jz      short loc_180084D2D
0x180084d19  call    cs:__imp_GetProcessHeap
0x180084d1f  mov     r8, rsi; lpMem
0x180084d22  xor     edx, edx; dwFlags
0x180084d24  mov     rcx, rax; hHeap
0x180084d27  call    cs:__imp_HeapFree
0x180084d2d  inc     ebx
0x180084d2f  cmp     ebx, [rdi+80h]
0x180084d35  jb      short loc_180084D01
0x180084d37  mov     rbx, [rdi+90h]
0x180084d3e  call    cs:__imp_GetProcessHeap
0x180084d44  mov     r8, rbx; lpMem
0x180084d47  xor     edx, edx; dwFlags
0x180084d49  mov     rcx, rax; hHeap
0x180084d4c  call    cs:__imp_HeapFree
0x180084d52  mov     qword ptr [rdi+90h], 0
0x180084d5d  dec     cs:?V2DhcpInterfaceCount@@3JA; long V2DhcpInterfaceCount
0x180084d63  lea     rcx, [rdi+10h]; lpCriticalSection
0x180084d67  call    cs:__imp_DeleteCriticalSection
0x180084d6d  call    cs:__imp_GetProcessHeap
0x180084d73  mov     r8, rdi; lpMem
0x180084d76  xor     edx, edx; dwFlags
0x180084d78  mov     rcx, rax; hHeap
0x180084d7b  call    cs:__imp_HeapFree
0x180084d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180084d88  cmp     rcx, r15
0x180084d8b  jz      short loc_180084DAE
0x180084d8d  test    byte ptr [rcx+1Ch], 2
0x180084d91  jz      short loc_180084DAE
0x180084d93  cmp     byte ptr [rcx+19h], 6
0x180084d97  jb      short loc_180084DAE
0x180084d99  mov     rcx, [rcx+10h]
0x180084d9d  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x180084da4  mov     edx, 25h ; '%'
0x180084da9  call    WPP_SF_
0x180084dae  add     rsp, 28h
0x180084db2  pop     r15
0x180084db4  pop     rdi
0x180084db5  pop     rsi
0x180084db6  pop     rbx
0x180084db7  retn
```

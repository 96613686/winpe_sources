# DhcpCleanupInterface(_DHCP_INTERFACE *)

- ea: `0x18002c9e4`
- end: `0x18002cb31`
- name: `?DhcpCleanupInterface@@YAXPEAU_DHCP_INTERFACE@@@Z`
- size: `333`
- prototype: `void __fastcall(struct _DHCP_INTERFACE *lpMem)`
- caller_count: `21`
- callee_count: `3`
- tags: ``

## callers

- `0x180002730`
- `0x18000c020`
- `0x18001f180`
- `0x18001fac0`
- `0x18002b064`
- `0x18002b350`
- `0x18002c60c`
- `0x180035220`
- `0x180035874`
- `0x18003e7dc`
- `0x180044020`
- `0x180044f28`
- `0x180045898`
- `0x1800587a8`
- `0x180058a10`
- `0x180058f80`
- `0x1800591d0`
- `0x1800595cc`
- `0x1800598f4`
- `0x180059a64`
- `0x18005f8d4`

## callees

- `0x18000c110`
- `0x1800127f8`
- `0x18002c9e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cab3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cae6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cab3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cae6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ca77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ca96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002caf4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ca77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ca96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002caf4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002cae0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002cae0`

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
0x18002c9e4  push    rbx
0x18002c9e6  push    rsi
0x18002c9e7  push    rdi
0x18002c9e8  push    r14
0x18002c9ea  sub     rsp, 38h
0x18002c9ee  mov     rdi, rcx
0x18002c9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c9f8  lea     r14, WPP_GLOBAL_Control
0x18002c9ff  cmp     rcx, r14
0x18002ca02  jz      short loc_18002CA37
0x18002ca04  test    byte ptr [rcx+1Ch], 2
0x18002ca08  jz      short loc_18002CA37
0x18002ca0a  cmp     byte ptr [rcx+19h], 6
0x18002ca0e  jb      short loc_18002CA37
0x18002ca10  mov     eax, [rdi+4Ch]
0x18002ca13  lea     r8, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids
0x18002ca1a  mov     r9d, [rdi+3Ch]
0x18002ca1e  mov     edx, 2Ch ; ','
0x18002ca23  mov     rcx, [rcx+10h]
0x18002ca27  mov     [rsp+58h+var_30], eax
0x18002ca2b  mov     eax, [rdi+40h]
0x18002ca2e  mov     [rsp+58h+var_38], eax
0x18002ca32  call    WPP_SF_ddD
0x18002ca37  mov     eax, [rdi+50h]
0x18002ca3a  test    eax, eax
0x18002ca3c  jz      short loc_18002CAA4
0x18002ca3e  cmp     qword ptr [rdi+58h], 0
0x18002ca43  jz      short loc_18002CAA4
0x18002ca45  cmp     cs:?DhcpArpForDad@@3HA, 0; int DhcpArpForDad
0x18002ca4c  jnz     short loc_18002CA84
0x18002ca4e  xor     ebx, ebx
0x18002ca50  test    eax, eax
0x18002ca52  jz      short loc_18002CA84
0x18002ca54  mov     rax, [rdi+58h]
0x18002ca58  lea     rcx, [rbx+rbx*4]
0x18002ca5c  add     rcx, rcx
0x18002ca5f  mov     rsi, [rax+rcx*8+48h]
0x18002ca64  test    rsi, rsi
0x18002ca67  jz      short loc_18002CA7D
0x18002ca69  call    cs:__imp_GetProcessHeap
0x18002ca6f  mov     r8, rsi; lpMem
0x18002ca72  xor     edx, edx; dwFlags
0x18002ca74  mov     rcx, rax; hHeap
0x18002ca77  call    cs:__imp_HeapFree
0x18002ca7d  inc     ebx
0x18002ca7f  cmp     ebx, [rdi+50h]
0x18002ca82  jb      short loc_18002CA54
0x18002ca84  mov     rbx, [rdi+58h]
0x18002ca88  call    cs:__imp_GetProcessHeap
0x18002ca8e  mov     r8, rbx; lpMem
0x18002ca91  xor     edx, edx; dwFlags
0x18002ca93  mov     rcx, rax; hHeap
0x18002ca96  call    cs:__imp_HeapFree
0x18002ca9c  mov     qword ptr [rdi+58h], 0
0x18002caa4  cmp     dword ptr [rdi+60h], 0
0x18002caa8  jbe     short loc_18002CAD6
0x18002caaa  mov     rbx, [rdi+68h]
0x18002caae  test    rbx, rbx
0x18002cab1  jz      short loc_18002CAD6
0x18002cab3  call    cs:__imp_GetProcessHeap
0x18002cab9  mov     r8, rbx; lpMem
0x18002cabc  xor     edx, edx; dwFlags
0x18002cabe  mov     rcx, rax; hHeap
0x18002cac1  call    cs:__imp_HeapFree
0x18002cac7  mov     qword ptr [rdi+68h], 0
0x18002cacf  mov     dword ptr [rdi+60h], 0
0x18002cad6  dec     cs:?DhcpInterfaceCount@@3JA; long DhcpInterfaceCount
0x18002cadc  lea     rcx, [rdi+10h]; lpCriticalSection
0x18002cae0  call    cs:__imp_DeleteCriticalSection
0x18002cae6  call    cs:__imp_GetProcessHeap
0x18002caec  mov     r8, rdi; lpMem
0x18002caef  xor     edx, edx; dwFlags
0x18002caf1  mov     rcx, rax; hHeap
0x18002caf4  call    cs:__imp_HeapFree
0x18002cafa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb01  cmp     rcx, r14
0x18002cb04  jz      short loc_18002CB27
0x18002cb06  test    byte ptr [rcx+1Ch], 2
0x18002cb0a  jz      short loc_18002CB27
0x18002cb0c  cmp     byte ptr [rcx+19h], 6
0x18002cb10  jb      short loc_18002CB27
0x18002cb12  mov     rcx, [rcx+10h]
0x18002cb16  lea     r8, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids
0x18002cb1d  mov     edx, 2Dh ; '-'
0x18002cb22  call    WPP_SF_
0x18002cb27  add     rsp, 38h
0x18002cb2b  pop     r14
0x18002cb2d  pop     rdi
0x18002cb2e  pop     rsi
0x18002cb2f  pop     rbx
0x18002cb30  retn
```

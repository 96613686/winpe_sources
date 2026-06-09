# DnsPurgeExpiredNames(DNS_ENTRY *)

- ea: `0x180039d28`
- end: `0x180039ee5`
- name: `?DnsPurgeExpiredNames@@YAPEAUDNS_ENTRY@@PEAU1@@Z`
- size: `445`
- prototype: `struct DNS_ENTRY *__fastcall(_DWORD *Buffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004b158`

## callees

- `0x180008248`
- `0x18000c110`
- `0x180039d28`
- `0x1800641cc`
- `0x18008e908`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039e6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039e9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039e6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039e9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180039d87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180039d87`
- `ntdll!RtlDeleteElementGenericTable` at `0x180039e14`
- `ntdll!RtlDeleteElementGenericTable` at `0x180039e86`
- `ntdll!RtlDeleteElementGenericTable` at `0x180039e14`
- `ntdll!RtlDeleteElementGenericTable` at `0x180039e86`

## pseudocode

```c
struct DNS_ENTRY *__fastcall DnsPurgeExpiredNames(_DWORD *Buffer)
{
  int v2; // ecx
  unsigned int v3; // ebx
  __int64 v4; // rbp
  int v5; // edx
  int v6; // r8d
  void *v7; // rdi
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v10; // rax
  __int128 Buffera; // [rsp+30h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
  }
  SystemTimeAsFileTime = 0;
  Buffera = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v2 = Buffer[2];
  v3 = 1;
  for ( *((_QWORD *)&Buffera + 1) = 0; v3 < v2 + 1; ++v3 )
  {
    v4 = v3 - 1;
    if ( (unsigned int)IsFileTimeExpired((struct _FILETIME *)(*((_QWORD *)Buffer + 2) + 4LL + 12 * v4)) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_LS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v5,
          v6,
          *(_DWORD *)(*((_QWORD *)Buffer + 2) + 12 * v4),
          *(_QWORD *)Buffer);
      }
      LODWORD(Buffera) = *(_DWORD *)(*((_QWORD *)Buffer + 2) + 12 * v4);
      RtlDeleteElementGenericTable(&g_ReverseDnsTable, &Buffera);
      memcpy_0(
        (void *)(*((_QWORD *)Buffer + 2) + 12 * v4),
        (const void *)(*((_QWORD *)Buffer + 2) + 12LL * v3),
        12LL * (Buffer[2] - v3));
      --Buffer[2];
      --v3;
    }
    v2 = Buffer[2];
  }
  if ( !v2 )
  {
    v7 = *(void **)Buffer;
    v8 = (void *)*((_QWORD *)Buffer + 2);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    *((_QWORD *)Buffer + 2) = 0;
    RtlDeleteElementGenericTable(&g_DnsTable, Buffer);
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v7);
    Buffer = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
  }
  return (struct DNS_ENTRY *)Buffer;
}

```

## disassembly

```asm
0x180039d28  mov     [rsp+arg_8], rbx
0x180039d2d  mov     [rsp+arg_10], rbp
0x180039d32  push    rsi
0x180039d33  push    rdi
0x180039d34  push    r12
0x180039d36  sub     rsp, 40h
0x180039d3a  mov     rsi, rcx
0x180039d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039d44  lea     r12, WPP_GLOBAL_Control
0x180039d4b  cmp     rcx, r12
0x180039d4e  jz      short loc_180039D71
0x180039d50  test    byte ptr [rcx+1Ch], 10h
0x180039d54  jz      short loc_180039D71
0x180039d56  cmp     byte ptr [rcx+19h], 6
0x180039d5a  jb      short loc_180039D71
0x180039d5c  mov     rcx, [rcx+10h]
0x180039d60  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x180039d67  mov     edx, 20h ; ' '
0x180039d6c  call    WPP_SF_
0x180039d71  xorps   xmm0, xmm0
0x180039d74  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180039d7d  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180039d82  movups  [rsp+58h+Buffer], xmm0
0x180039d87  call    cs:__imp_GetSystemTimeAsFileTime
0x180039d8d  mov     ecx, [rsi+8]
0x180039d90  mov     ebx, 1
0x180039d95  mov     qword ptr [rsp+58h+Buffer+8], 0
0x180039d9e  lea     eax, [rcx+1]
0x180039da1  cmp     eax, ebx
0x180039da3  jbe     loc_180039E55
0x180039da9  mov     rcx, [rsi+10h]
0x180039dad  lea     ebp, [rbx-1]
0x180039db0  add     rcx, 4
0x180039db4  lea     rdi, ds:0[rbp*2]
0x180039dbc  add     rdi, rbp
0x180039dbf  lea     rcx, [rcx+rdi*4]; struct _FILETIME *
0x180039dc3  call    ?IsFileTimeExpired@@YAHPEAU_FILETIME@@@Z; IsFileTimeExpired(_FILETIME *)
0x180039dc8  test    eax, eax
0x180039dca  jz      short loc_180039E45
0x180039dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180039dd3  cmp     rcx, r12
0x180039dd6  jz      short loc_180039DFD
0x180039dd8  test    byte ptr [rcx+1Ch], 10h
0x180039ddc  jz      short loc_180039DFD
0x180039dde  cmp     byte ptr [rcx+19h], 4
0x180039de2  jb      short loc_180039DFD
0x180039de4  mov     r9, [rsi+10h]
0x180039de8  mov     rax, [rsi]
0x180039deb  mov     rcx, [rcx+10h]
0x180039def  mov     [rsp+58h+var_38], rax
0x180039df4  mov     r9d, [r9+rdi*4]
0x180039df8  call    WPP_SF_LS
0x180039dfd  mov     rax, [rsi+10h]
0x180039e01  lea     rdx, [rsp+58h+Buffer]; Buffer
0x180039e06  mov     ecx, [rax+rdi*4]
0x180039e09  mov     dword ptr [rsp+58h+Buffer], ecx
0x180039e0d  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x180039e14  call    cs:__imp_RtlDeleteElementGenericTable
0x180039e1a  mov     r9, [rsi+10h]
0x180039e1e  mov     eax, ebp
0x180039e20  not     eax
0x180039e22  add     eax, [rsi+8]
0x180039e25  lea     r8, [rax+rax*2]
0x180039e29  mov     eax, ebx
0x180039e2b  shl     r8, 2; Size
0x180039e2f  lea     rcx, [rax+rax*2]
0x180039e33  lea     rdx, [r9+rcx*4]; Src
0x180039e37  lea     rcx, [r9+rdi*4]; void *
0x180039e3b  call    memcpy_0
0x180039e40  dec     dword ptr [rsi+8]
0x180039e43  mov     ebx, ebp
0x180039e45  mov     ecx, [rsi+8]
0x180039e48  inc     ebx
0x180039e4a  lea     eax, [rcx+1]
0x180039e4d  cmp     ebx, eax
0x180039e4f  jb      loc_180039DA9
0x180039e55  test    ecx, ecx
0x180039e57  jnz     short loc_180039EA2
0x180039e59  mov     rdi, [rsi]
0x180039e5c  mov     rbx, [rsi+10h]
0x180039e60  call    cs:__imp_GetProcessHeap
0x180039e66  mov     r8, rbx; lpMem
0x180039e69  xor     edx, edx; dwFlags
0x180039e6b  mov     rcx, rax; hHeap
0x180039e6e  call    cs:__imp_HeapFree
0x180039e74  mov     rdx, rsi; Buffer
0x180039e77  mov     qword ptr [rsi+10h], 0
0x180039e7f  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x180039e86  call    cs:__imp_RtlDeleteElementGenericTable
0x180039e8c  call    cs:__imp_GetProcessHeap
0x180039e92  mov     r8, rdi; lpMem
0x180039e95  xor     edx, edx; dwFlags
0x180039e97  mov     rcx, rax; hHeap
0x180039e9a  call    cs:__imp_HeapFree
0x180039ea0  xor     esi, esi
0x180039ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ea9  cmp     rcx, r12
0x180039eac  jz      short loc_180039ECF
0x180039eae  test    byte ptr [rcx+1Ch], 10h
0x180039eb2  jz      short loc_180039ECF
0x180039eb4  cmp     byte ptr [rcx+19h], 6
0x180039eb8  jb      short loc_180039ECF
0x180039eba  mov     rcx, [rcx+10h]
0x180039ebe  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x180039ec5  mov     edx, 22h ; '"'
0x180039eca  call    WPP_SF_
0x180039ecf  mov     rbx, [rsp+58h+arg_8]
0x180039ed4  mov     rax, rsi
0x180039ed7  mov     rbp, [rsp+58h+arg_10]
0x180039edc  add     rsp, 40h
0x180039ee0  pop     r12
0x180039ee2  pop     rdi
0x180039ee3  pop     rsi
0x180039ee4  retn
```

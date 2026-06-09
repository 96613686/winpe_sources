# DnsPurgeExpiredNames(DNS_ENTRY *)

- ea: `0x18003cc80`
- end: `0x18003ce68`
- name: `?DnsPurgeExpiredNames@@YAPEAUDNS_ENTRY@@PEAU1@@Z`
- size: `488`
- prototype: `struct DNS_ENTRY *__fastcall(_DWORD *Buffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004ee28`

## callees

- `0x180008700`
- `0x18000ca20`
- `0x18003cc80`
- `0x180069084`
- `0x180095b28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cdc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ce02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cdc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ce02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cdd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ce16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cdd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ce16`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ccdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ccdf`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003cd72`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003cdf6`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003cd72`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003cdf6`

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
0x18003cc80  mov     [rsp+arg_8], rbx
0x18003cc85  mov     [rsp+arg_10], rbp
0x18003cc8a  push    rsi
0x18003cc8b  push    rdi
0x18003cc8c  push    r12
0x18003cc8e  sub     rsp, 40h
0x18003cc92  mov     rsi, rcx
0x18003cc95  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc9c  lea     r12, WPP_GLOBAL_Control
0x18003cca3  cmp     rcx, r12
0x18003cca6  jz      short loc_18003CCC9
0x18003cca8  test    byte ptr [rcx+1Ch], 10h
0x18003ccac  jz      short loc_18003CCC9
0x18003ccae  cmp     byte ptr [rcx+19h], 6
0x18003ccb2  jb      short loc_18003CCC9
0x18003ccb4  mov     rcx, [rcx+10h]
0x18003ccb8  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003ccbf  mov     edx, 20h ; ' '
0x18003ccc4  call    WPP_SF_
0x18003ccc9  xorps   xmm0, xmm0
0x18003cccc  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003ccd5  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003ccda  movups  [rsp+58h+Buffer], xmm0
0x18003ccdf  call    cs:__imp_GetSystemTimeAsFileTime
0x18003cce6  nop     dword ptr [rax+rax+00h]
0x18003cceb  mov     ecx, [rsi+8]
0x18003ccee  mov     ebx, 1
0x18003ccf3  mov     qword ptr [rsp+58h+Buffer+8], 0
0x18003ccfc  lea     eax, [rcx+1]
0x18003ccff  cmp     eax, ebx
0x18003cd01  jbe     loc_18003CDB9
0x18003cd07  mov     rcx, [rsi+10h]
0x18003cd0b  lea     ebp, [rbx-1]
0x18003cd0e  add     rcx, 4
0x18003cd12  lea     rdi, ds:0[rbp*2]
0x18003cd1a  add     rdi, rbp
0x18003cd1d  lea     rcx, [rcx+rdi*4]; struct _FILETIME *
0x18003cd21  call    ?IsFileTimeExpired@@YAHPEAU_FILETIME@@@Z; IsFileTimeExpired(_FILETIME *)
0x18003cd26  test    eax, eax
0x18003cd28  jz      short loc_18003CDA9
0x18003cd2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd31  cmp     rcx, r12
0x18003cd34  jz      short loc_18003CD5B
0x18003cd36  test    byte ptr [rcx+1Ch], 10h
0x18003cd3a  jz      short loc_18003CD5B
0x18003cd3c  cmp     byte ptr [rcx+19h], 4
0x18003cd40  jb      short loc_18003CD5B
0x18003cd42  mov     r9, [rsi+10h]
0x18003cd46  mov     rax, [rsi]
0x18003cd49  mov     rcx, [rcx+10h]
0x18003cd4d  mov     [rsp+58h+var_38], rax
0x18003cd52  mov     r9d, [r9+rdi*4]
0x18003cd56  call    WPP_SF_LS
0x18003cd5b  mov     rax, [rsi+10h]
0x18003cd5f  lea     rdx, [rsp+58h+Buffer]; Buffer
0x18003cd64  mov     ecx, [rax+rdi*4]
0x18003cd67  mov     dword ptr [rsp+58h+Buffer], ecx
0x18003cd6b  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003cd72  call    cs:__imp_RtlDeleteElementGenericTable
0x18003cd79  nop     dword ptr [rax+rax+00h]
0x18003cd7e  mov     r9, [rsi+10h]
0x18003cd82  mov     eax, ebp
0x18003cd84  not     eax
0x18003cd86  add     eax, [rsi+8]
0x18003cd89  lea     r8, [rax+rax*2]
0x18003cd8d  mov     eax, ebx
0x18003cd8f  shl     r8, 2; Size
0x18003cd93  lea     rcx, [rax+rax*2]
0x18003cd97  lea     rdx, [r9+rcx*4]; Src
0x18003cd9b  lea     rcx, [r9+rdi*4]; void *
0x18003cd9f  call    memcpy_0
0x18003cda4  dec     dword ptr [rsi+8]
0x18003cda7  mov     ebx, ebp
0x18003cda9  mov     ecx, [rsi+8]
0x18003cdac  inc     ebx
0x18003cdae  lea     eax, [rcx+1]
0x18003cdb1  cmp     ebx, eax
0x18003cdb3  jb      loc_18003CD07
0x18003cdb9  test    ecx, ecx
0x18003cdbb  jnz     short loc_18003CE24
0x18003cdbd  mov     rdi, [rsi]
0x18003cdc0  mov     rbx, [rsi+10h]
0x18003cdc4  call    cs:__imp_GetProcessHeap
0x18003cdcb  nop     dword ptr [rax+rax+00h]
0x18003cdd0  mov     r8, rbx; lpMem
0x18003cdd3  xor     edx, edx; dwFlags
0x18003cdd5  mov     rcx, rax; hHeap
0x18003cdd8  call    cs:__imp_HeapFree
0x18003cddf  nop     dword ptr [rax+rax+00h]
0x18003cde4  mov     rdx, rsi; Buffer
0x18003cde7  mov     qword ptr [rsi+10h], 0
0x18003cdef  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003cdf6  call    cs:__imp_RtlDeleteElementGenericTable
0x18003cdfd  nop     dword ptr [rax+rax+00h]
0x18003ce02  call    cs:__imp_GetProcessHeap
0x18003ce09  nop     dword ptr [rax+rax+00h]
0x18003ce0e  mov     r8, rdi; lpMem
0x18003ce11  xor     edx, edx; dwFlags
0x18003ce13  mov     rcx, rax; hHeap
0x18003ce16  call    cs:__imp_HeapFree
0x18003ce1d  nop     dword ptr [rax+rax+00h]
0x18003ce22  xor     esi, esi
0x18003ce24  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ce2b  cmp     rcx, r12
0x18003ce2e  jz      short loc_18003CE51
0x18003ce30  test    byte ptr [rcx+1Ch], 10h
0x18003ce34  jz      short loc_18003CE51
0x18003ce36  cmp     byte ptr [rcx+19h], 6
0x18003ce3a  jb      short loc_18003CE51
0x18003ce3c  mov     rcx, [rcx+10h]
0x18003ce40  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003ce47  mov     edx, 22h ; '"'
0x18003ce4c  call    WPP_SF_
0x18003ce51  mov     rbx, [rsp+58h+arg_8]
0x18003ce56  mov     rax, rsi
0x18003ce59  mov     rbp, [rsp+58h+arg_10]
0x18003ce5e  add     rsp, 40h
0x18003ce62  pop     r12
0x18003ce64  pop     rdi
0x18003ce65  pop     rsi
0x18003ce66  retn
```

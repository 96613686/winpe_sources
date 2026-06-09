# Rnr_ThreadInit

- ea: `0x180004480`
- end: `0x180004550`
- name: `Rnr_ThreadInit`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003804`

## callees

- `0x180004480`
- `0x180005f78`
- `0x180022bd2`
- `0x180038104`
- `0x180038118`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000448c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800044ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000448c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800044ee`
- `ntdll!RtlAllocateHeap` at `0x1800044c4`
- `ntdll!RtlAllocateHeap` at `0x1800044c4`

## pseudocode

```c
__int64 Rnr_ThreadInit()
{
  PVOID Heap; // rax
  PVOID v1; // rbx

  if ( TlsGetValue(MSAFD_SockTlsSlot) || (unsigned int)MSAFD_SockThreadInitialize() )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_q(1025, 10, WPP_e936febbce6639b317d7e1b8ac52ecad_Traceguids, NtCurrentTeb());
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x470u);
    v1 = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, 0x470u);
      *((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9) = v1;
      return 1;
    }
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 11, WPP_e936febbce6639b317d7e1b8ac52ecad_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180004480  push    rbx
0x180004482  sub     rsp, 20h
0x180004486  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18000448c  call    cs:__imp_TlsGetValue
0x180004493  nop     dword ptr [rax+rax+00h]
0x180004498  test    rax, rax
0x18000449b  jnz     short loc_1800044A6
0x18000449d  call    MSAFD_SockThreadInitialize
0x1800044a2  test    eax, eax
0x1800044a4  jz      short loc_18000450A
0x1800044a6  test    byte ptr cs:xmmword_180063D60, 2
0x1800044ad  jnz     short loc_18000450E
0x1800044af  mov     rcx, gs:60h
0x1800044b8  xor     edx, edx; Flags
0x1800044ba  mov     r8d, 470h; Size
0x1800044c0  mov     rcx, [rcx+30h]; HeapHandle
0x1800044c4  call    cs:__imp_RtlAllocateHeap
0x1800044cb  nop     dword ptr [rax+rax+00h]
0x1800044d0  mov     rbx, rax
0x1800044d3  test    rax, rax
0x1800044d6  jz      short loc_18000452F
0x1800044d8  xor     edx, edx; Val
0x1800044da  mov     r8d, 470h; Size
0x1800044e0  mov     rcx, rax; void *
0x1800044e3  call    memset_0
0x1800044e8  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x1800044ee  call    cs:__imp_TlsGetValue
0x1800044f5  nop     dword ptr [rax+rax+00h]
0x1800044fa  mov     [rax+48h], rbx
0x1800044fe  mov     eax, 1
0x180004503  add     rsp, 20h
0x180004507  pop     rbx
0x180004508  retn
0x18000450a  xor     eax, eax
0x18000450c  jmp     short loc_180004503
0x18000450e  mov     r9, gs:30h
0x180004517  lea     r8, WPP_e936febbce6639b317d7e1b8ac52ecad_Traceguids
0x18000451e  mov     edx, 0Ah
0x180004523  mov     ecx, 401h
0x180004528  call    WPP_SF_q
0x18000452d  jmp     short loc_1800044AF
0x18000452f  test    byte ptr cs:xmmword_180063D60, 2
0x180004536  jz      short loc_18000450A
0x180004538  mov     edx, 0Bh
0x18000453d  lea     r8, WPP_e936febbce6639b317d7e1b8ac52ecad_Traceguids
0x180004544  mov     ecx, 401h
0x180004549  call    WPP_SF_
0x18000454e  jmp     short loc_18000450A
```

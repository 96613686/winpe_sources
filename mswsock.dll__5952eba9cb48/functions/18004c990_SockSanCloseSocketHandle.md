# SockSanCloseSocketHandle

- ea: `0x18004c990`
- end: `0x18004cb13`
- name: `SockSanCloseSocketHandle`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180008250`
- `0x1800248a0`
- `0x180038118`
- `0x18004c4b8`
- `0x18004c990`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004cab2`
- `ntdll!RtlFreeHeap` at `0x18004caca`
- `ntdll!RtlFreeHeap` at `0x18004cab2`
- `ntdll!RtlFreeHeap` at `0x18004caca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ca96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ca96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c9e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ca35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c9e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ca35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c9b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ca14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c9b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ca14`

## pseudocode

```c
__int64 __fastcall SockSanCloseSocketHandle(__int64 a1)
{
  __int64 v1; // rbx
  bool v2; // r15
  volatile signed __int32 *v3; // rdi
  char v4; // al
  char v5; // bp
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rbp

  if ( a1 )
  {
    v1 = *(_QWORD *)(a1 + 16);
    v2 = 0;
    v3 = *(volatile signed __int32 **)(v1 + 8);
    EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 48));
    v4 = *(_BYTE *)(v1 + 802);
    if ( (v4 & 1) != 0 )
    {
      v5 = 1;
      *(_BYTE *)(v1 + 802) = v4 & 0xFE;
    }
    else
    {
      v5 = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 48));
    if ( !v5 )
    {
      *(_QWORD *)(v1 + 112) = 4079088417LL;
      if ( _InterlockedIncrement((volatile signed __int32 *)(v1 + 888)) == 3
        && (EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 48)),
            v8 = *(_QWORD *)(v1 + 824),
            *(_QWORD *)(v1 + 824) = 0,
            LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 48)),
            v8) )
      {
        DoTPReuse(v1, v8);
      }
      else if ( _InterlockedIncrement((volatile signed __int32 *)(v1 + 832)) == 2 )
      {
        v2 = (unsigned __int8)SockSanCheckForConnectListReference(v1) == 0;
      }
    }
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(v3, 0xFFFFFFFF) == 1 )
        SockDestroySocket((__int64)v3, v6, v7);
    }
    else if ( _InterlockedExchange((volatile __int32 *)(v1 + 168), 3) == 4 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_q(1025, 11, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, v1);
      goto LABEL_15;
    }
    if ( v2 )
    {
LABEL_15:
      DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 48));
      RtlFreeHeap(SockPrivateHeap, 0, *(PVOID *)(v1 + 216));
      RtlFreeHeap(SockPrivateHeap, 0, (PVOID)v1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004c990  push    rbx
0x18004c992  push    rbp
0x18004c993  push    rsi
0x18004c994  push    rdi
0x18004c995  push    r14
0x18004c997  push    r15
0x18004c999  sub     rsp, 28h
0x18004c99d  test    rcx, rcx
0x18004c9a0  jz      loc_18004CAD6
0x18004c9a6  mov     rbx, [rcx+10h]
0x18004c9aa  xor     r15b, r15b
0x18004c9ad  mov     rdi, [rbx+8]
0x18004c9b1  lea     r14, [rbx+30h]
0x18004c9b5  mov     rcx, r14; lpCriticalSection
0x18004c9b8  call    cs:__imp_EnterCriticalSection
0x18004c9bf  nop     dword ptr [rax+rax+00h]
0x18004c9c4  mov     al, [rbx+322h]
0x18004c9ca  test    al, 1
0x18004c9cc  jnz     short loc_18004C9D3
0x18004c9ce  xor     bpl, bpl
0x18004c9d1  jmp     short loc_18004C9DE
0x18004c9d3  and     al, 0FEh
0x18004c9d5  mov     bpl, 1
0x18004c9d8  mov     [rbx+322h], al
0x18004c9de  mov     rcx, r14; lpCriticalSection
0x18004c9e1  call    cs:__imp_LeaveCriticalSection
0x18004c9e8  nop     dword ptr [rax+rax+00h]
0x18004c9ed  mov     esi, 3
0x18004c9f2  test    bpl, bpl
0x18004c9f5  jnz     short loc_18004CA75
0x18004c9f7  mov     eax, 0F321F321h
0x18004c9fc  mov     [rbx+70h], rax
0x18004ca00  lea     eax, [rsi-2]
0x18004ca03  lock xadd [rbx+378h], eax
0x18004ca0b  inc     eax
0x18004ca0d  cmp     eax, esi
0x18004ca0f  jnz     short loc_18004CA53
0x18004ca11  mov     rcx, r14; lpCriticalSection
0x18004ca14  call    cs:__imp_EnterCriticalSection
0x18004ca1b  nop     dword ptr [rax+rax+00h]
0x18004ca20  mov     rbp, [rbx+338h]
0x18004ca27  mov     rcx, r14; lpCriticalSection
0x18004ca2a  mov     qword ptr [rbx+338h], 0
0x18004ca35  call    cs:__imp_LeaveCriticalSection
0x18004ca3c  nop     dword ptr [rax+rax+00h]
0x18004ca41  test    rbp, rbp
0x18004ca44  jz      short loc_18004CA53
0x18004ca46  mov     rdx, rbp
0x18004ca49  mov     rcx, rbx
0x18004ca4c  call    DoTPReuse
0x18004ca51  jmp     short loc_18004CA75
0x18004ca53  mov     eax, 1
0x18004ca58  lock xadd [rbx+340h], eax
0x18004ca60  inc     eax
0x18004ca62  cmp     eax, 2
0x18004ca65  jnz     short loc_18004CA75
0x18004ca67  mov     rcx, rbx
0x18004ca6a  call    SockSanCheckForConnectListReference
0x18004ca6f  test    al, al
0x18004ca71  setz    r15b
0x18004ca75  test    rdi, rdi
0x18004ca78  jz      short loc_18004CAE6
0x18004ca7a  or      eax, 0FFFFFFFFh
0x18004ca7d  lock xadd [rdi], eax
0x18004ca81  cmp     eax, 1
0x18004ca84  jnz     short loc_18004CA8E
0x18004ca86  mov     rcx, rdi
0x18004ca89  call    SockDestroySocket
0x18004ca8e  test    r15b, r15b
0x18004ca91  jz      short loc_18004CAD6
0x18004ca93  mov     rcx, r14; lpCriticalSection
0x18004ca96  call    cs:__imp_DeleteCriticalSection
0x18004ca9d  nop     dword ptr [rax+rax+00h]
0x18004caa2  mov     r8, [rbx+0D8h]; P
0x18004caa9  xor     edx, edx; Flags
0x18004caab  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004cab2  call    cs:__imp_RtlFreeHeap
0x18004cab9  nop     dword ptr [rax+rax+00h]
0x18004cabe  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004cac5  mov     r8, rbx; P
0x18004cac8  xor     edx, edx; Flags
0x18004caca  call    cs:__imp_RtlFreeHeap
0x18004cad1  nop     dword ptr [rax+rax+00h]
0x18004cad6  xor     eax, eax
0x18004cad8  add     rsp, 28h
0x18004cadc  pop     r15
0x18004cade  pop     r14
0x18004cae0  pop     rdi
0x18004cae1  pop     rsi
0x18004cae2  pop     rbp
0x18004cae3  pop     rbx
0x18004cae4  retn
0x18004cae6  xchg    esi, [rbx+0A8h]
0x18004caec  cmp     esi, 4
0x18004caef  jnz     short loc_18004CA8E
0x18004caf1  test    byte ptr cs:xmmword_180063D60, 2
0x18004caf8  jz      short loc_18004CA93
0x18004cafa  lea     edx, [rsi+7]
0x18004cafd  mov     ecx, 401h
0x18004cb02  mov     r9, rbx
0x18004cb05  lea     r8, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids
0x18004cb0c  call    WPP_SF_q
0x18004cb11  jmp     short loc_18004CA93
```

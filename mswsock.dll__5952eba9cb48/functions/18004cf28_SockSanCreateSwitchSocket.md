# SockSanCreateSwitchSocket

- ea: `0x18004cf28`
- end: `0x18004d15c`
- name: `SockSanCreateSwitchSocket`
- size: `564`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004cb1c`
- `0x18004d924`
- `0x180051170`

## callees

- `0x180022bd2`
- `0x180038104`
- `0x180038118`
- `0x18004cf28`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004d023`
- `ntdll!RtlFreeHeap` at `0x18004d023`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18004d007`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18004d007`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d056`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d056`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d0fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d0fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d08b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d08b`

## pseudocode

```c
char *SockSanCreateSwitchSocket()
{
  char *v0; // rax
  char *v1; // rbx
  BOOL v3; // eax
  HANDLE v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rax
  _QWORD *v7; // rcx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  char v10; // al

  if ( (BYTE1(xmmword_180063D60) & 0x40) != 0 )
    WPP_SF_(1038, 36, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids);
  v0 = (char *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(SockPrivateHeap, 0, 952);
  v1 = v0;
  if ( !v0 )
    return 0;
  memset_0(v0, 0, 0x3B8u);
  *((_QWORD *)v1 + 13) = -1;
  v1[744] = 1;
  *((_WORD *)v1 + 420) = 1536;
  *((_DWORD *)v1 + 121) = 255;
  *((_DWORD *)v1 + 39) = -1;
  *((_DWORD *)v1 + 209) = 100664832;
  *((_DWORD *)v1 + 43) = 65;
  *((_QWORD *)v1 + 41) = v1 + 320;
  *((_QWORD *)v1 + 40) = v1 + 320;
  *((_QWORD *)v1 + 51) = v1 + 400;
  *((_QWORD *)v1 + 50) = v1 + 400;
  *((_QWORD *)v1 + 113) = v1 + 896;
  *((_QWORD *)v1 + 112) = v1 + 896;
  v3 = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v1 + 48), 0x3E8u);
  v4 = SockPrivateHeap;
  if ( !v3 )
  {
LABEL_6:
    RtlFreeHeap(v4, 0, v1);
    return 0;
  }
  v5 = ((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(SockPrivateHeap, 0, 48);
  *((_QWORD *)v1 + 27) = v5;
  if ( !v5 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 48));
    v4 = SockPrivateHeap;
    goto LABEL_6;
  }
  *(_QWORD *)(v5 + 16) = v1;
  v6 = *((_QWORD *)v1 + 27);
  *(_OWORD *)(v6 + 24) = 0;
  *(_DWORD *)(v6 + 40) = 0;
  EnterCriticalSection(&SockSanListCritSec);
  v7 = (_QWORD *)qword_1800646E8;
  if ( *(__int64 **)qword_1800646E8 != &SockSanOpenList
    || (++NumOpenSanSocks,
        *((_QWORD *)v1 + 11) = &SockSanOpenList,
        *((_QWORD *)v1 + 12) = v7,
        *v7 = v1 + 88,
        v8 = (_QWORD *)qword_180064718,
        qword_1800646E8 = (__int64)(v1 + 88),
        *(__int64 **)qword_180064718 != &SockSanRedirectorList) )
  {
    __fastfail(3u);
  }
  v9 = (_QWORD *)*((_QWORD *)v1 + 27);
  v9[1] = qword_180064718;
  *v9 = &SockSanRedirectorList;
  *v8 = v9;
  qword_180064718 = (__int64)v9;
  LeaveCriticalSection(&SockSanListCritSec);
  v10 = BYTE1(xmmword_180063D60);
  if ( (BYTE1(xmmword_180063D60) & 2) != 0 )
  {
    WPP_SF_q(1033, 37, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, v1);
    v10 = BYTE1(xmmword_180063D60);
  }
  if ( (v10 & 0x40) != 0 )
    WPP_SF_q(1038, 38, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18004cf28  mov     [rsp+arg_0], rbx
0x18004cf2d  push    rdi
0x18004cf2e  sub     rsp, 20h
0x18004cf32  test    byte ptr cs:xmmword_180063D60+1, 40h
0x18004cf39  jz      short loc_18004CF51
0x18004cf3b  mov     edx, 24h ; '$'
0x18004cf40  lea     r8, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids
0x18004cf47  mov     ecx, 40Eh
0x18004cf4c  call    WPP_SF_
0x18004cf51  mov     rcx, cs:SockPrivateHeap
0x18004cf58  mov     edi, 3B8h
0x18004cf5d  mov     rax, cs:SockAllocateHeapRoutine
0x18004cf64  mov     r8d, edi
0x18004cf67  xor     edx, edx
0x18004cf69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf6e  mov     rbx, rax
0x18004cf71  test    rax, rax
0x18004cf74  jnz     short loc_18004CF84
0x18004cf76  xor     eax, eax
0x18004cf78  mov     rbx, [rsp+28h+arg_0]
0x18004cf7d  add     rsp, 20h
0x18004cf81  pop     rdi
0x18004cf82  retn
0x18004cf84  mov     r8, rdi; Size
0x18004cf87  xor     edx, edx; Val
0x18004cf89  mov     rcx, rbx; void *
0x18004cf8c  call    memset_0
0x18004cf91  mov     qword ptr [rbx+68h], 0FFFFFFFFFFFFFFFFh
0x18004cf99  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004cf9d  mov     byte ptr [rbx+2E8h], 1
0x18004cfa4  mov     eax, 600h
0x18004cfa9  mov     [rbx+348h], ax
0x18004cfb0  mov     edx, 3E8h; dwSpinCount
0x18004cfb5  mov     dword ptr [rbx+1E4h], 0FFh
0x18004cfbf  lea     rax, [rbx+140h]
0x18004cfc6  mov     dword ptr [rbx+9Ch], 0FFFFFFFFh
0x18004cfd0  mov     dword ptr [rbx+344h], 6000600h
0x18004cfda  mov     dword ptr [rbx+0ACh], 41h ; 'A'
0x18004cfe4  mov     [rax+8], rax
0x18004cfe8  mov     [rax], rax
0x18004cfeb  lea     rax, [rbx+190h]
0x18004cff2  mov     [rax+8], rax
0x18004cff6  mov     [rax], rax
0x18004cff9  lea     rax, [rbx+380h]
0x18004d000  mov     [rax+8], rax
0x18004d004  mov     [rax], rax
0x18004d007  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18004d00e  nop     dword ptr [rax+rax+00h]
0x18004d013  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004d01a  xor     edx, edx; Flags
0x18004d01c  test    eax, eax
0x18004d01e  jnz     short loc_18004D034
0x18004d020  mov     r8, rbx; P
0x18004d023  call    cs:__imp_RtlFreeHeap
0x18004d02a  nop     dword ptr [rax+rax+00h]
0x18004d02f  jmp     loc_18004CF76
0x18004d034  mov     rax, cs:SockAllocateHeapRoutine
0x18004d03b  mov     r8d, 30h ; '0'
0x18004d041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d046  mov     [rbx+0D8h], rax
0x18004d04d  test    rax, rax
0x18004d050  jnz     short loc_18004D06D
0x18004d052  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004d056  call    cs:__imp_DeleteCriticalSection
0x18004d05d  nop     dword ptr [rax+rax+00h]
0x18004d062  mov     rcx, cs:SockPrivateHeap
0x18004d069  xor     edx, edx
0x18004d06b  jmp     short loc_18004D020
0x18004d06d  mov     [rax+10h], rbx
0x18004d071  xor     ecx, ecx
0x18004d073  mov     rax, [rbx+0D8h]
0x18004d07a  xorps   xmm0, xmm0
0x18004d07d  movups  xmmword ptr [rax+18h], xmm0
0x18004d081  mov     [rax+28h], ecx
0x18004d084  lea     rcx, SockSanListCritSec; lpCriticalSection
0x18004d08b  call    cs:__imp_EnterCriticalSection
0x18004d092  nop     dword ptr [rax+rax+00h]
0x18004d097  mov     rcx, cs:qword_1800646E8
0x18004d09e  lea     rdx, SockSanOpenList
0x18004d0a5  cmp     [rcx], rdx
0x18004d0a8  jnz     loc_18004D155
0x18004d0ae  inc     cs:NumOpenSanSocks
0x18004d0b4  lea     rax, [rbx+58h]
0x18004d0b8  mov     [rax], rdx
0x18004d0bb  lea     rdx, SockSanRedirectorList
0x18004d0c2  mov     [rax+8], rcx
0x18004d0c6  mov     [rcx], rax
0x18004d0c9  mov     rcx, cs:qword_180064718
0x18004d0d0  mov     cs:qword_1800646E8, rax
0x18004d0d7  cmp     [rcx], rdx
0x18004d0da  jnz     short loc_18004D155
0x18004d0dc  mov     rax, [rbx+0D8h]
0x18004d0e3  mov     [rax+8], rcx
0x18004d0e7  mov     [rax], rdx
0x18004d0ea  mov     [rcx], rax
0x18004d0ed  lea     rcx, SockSanListCritSec; lpCriticalSection
0x18004d0f4  mov     cs:qword_180064718, rax
0x18004d0fb  call    cs:__imp_LeaveCriticalSection
0x18004d102  nop     dword ptr [rax+rax+00h]
0x18004d107  mov     al, byte ptr cs:xmmword_180063D60+1
0x18004d10d  test    al, 2
0x18004d10f  jz      short loc_18004D130
0x18004d111  mov     edx, 25h ; '%'
0x18004d116  lea     r8, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids
0x18004d11d  mov     ecx, 409h
0x18004d122  mov     r9, rbx
0x18004d125  call    WPP_SF_q
0x18004d12a  mov     al, byte ptr cs:xmmword_180063D60+1
0x18004d130  test    al, 40h
0x18004d132  jz      short loc_18004D14D
0x18004d134  mov     edx, 26h ; '&'
0x18004d139  lea     r8, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids
0x18004d140  mov     ecx, 40Eh
0x18004d145  mov     r9, rbx
0x18004d148  call    WPP_SF_q
0x18004d14d  mov     rax, rbx
0x18004d150  jmp     loc_18004CF78
0x18004d155  mov     ecx, 3
0x18004d15a  int     29h; Win8: RtlFailFast(ecx)
```

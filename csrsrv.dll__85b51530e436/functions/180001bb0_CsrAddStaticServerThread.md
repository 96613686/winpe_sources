# CsrAddStaticServerThread

- ea: `0x180001bb0`
- end: `0x180001c44`
- name: `CsrAddStaticServerThread`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int128 *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001aa0`
- `0x180008540`
- `0x1800095c0`

## callees

- `0x180001bb0`
- `0x180002f60`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180001bc9`
- `ntdll!RtlEnterCriticalSection` at `0x180001bc9`
- `ntdll!RtlLeaveCriticalSection` at `0x180001c24`
- `ntdll!RtlLeaveCriticalSection` at `0x180001c24`

## pseudocode

```c
__int64 __fastcall CsrAddStaticServerThread(__int64 a1, __int128 *a2, int a3)
{
  __int64 Thread; // rax
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int128 v10; // xmm0
  __int64 **v11; // rdx
  __int64 *v12; // rax

  RtlEnterCriticalSection(&CsrProcessStructureLock);
  Thread = CsrAllocateThread(CsrRootProcess);
  v7 = Thread;
  if ( Thread )
  {
    v8 = CsrRootProcess;
    *(_QWORD *)(Thread + 64) = a1;
    v9 = v8 + 32;
    v10 = *a2;
    *(_DWORD *)(Thread + 72) = a3;
    *(_OWORD *)(Thread + 40) = v10;
    v11 = *(__int64 ***)(v9 + 8);
    if ( *v11 != (__int64 *)v9 )
      __fastfail(3u);
    v12 = (__int64 *)(Thread + 8);
    *v12 = v9;
    v12[1] = (__int64)v11;
    *v11 = v12;
    *(_QWORD *)(v9 + 8) = v12;
  }
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  return v7;
}

```

## disassembly

```asm
0x180001bb0  push    rbx
0x180001bb2  push    rbp
0x180001bb3  push    rsi
0x180001bb4  push    rdi
0x180001bb5  sub     rsp, 28h
0x180001bb9  mov     rbp, rcx
0x180001bbc  mov     edi, r8d
0x180001bbf  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180001bc6  mov     rsi, rdx
0x180001bc9  call    cs:__imp_RtlEnterCriticalSection
0x180001bd0  nop     dword ptr [rax+rax+00h]
0x180001bd5  mov     rcx, cs:CsrRootProcess
0x180001bdc  call    CsrAllocateThread
0x180001be1  mov     rbx, rax
0x180001be4  test    rax, rax
0x180001be7  jz      short loc_180001C1D
0x180001be9  mov     rcx, cs:CsrRootProcess
0x180001bf0  mov     [rax+40h], rbp
0x180001bf4  add     rcx, 20h ; ' '
0x180001bf8  movups  xmm0, xmmword ptr [rsi]
0x180001bfb  mov     [rax+48h], edi
0x180001bfe  movups  xmmword ptr [rax+28h], xmm0
0x180001c02  mov     rdx, [rcx+8]
0x180001c06  cmp     [rdx], rcx
0x180001c09  jnz     short loc_180001C3D
0x180001c0b  add     rax, 8
0x180001c0f  mov     [rax], rcx
0x180001c12  mov     [rax+8], rdx
0x180001c16  mov     [rdx], rax
0x180001c19  mov     [rcx+8], rax
0x180001c1d  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180001c24  call    cs:__imp_RtlLeaveCriticalSection
0x180001c2b  nop     dword ptr [rax+rax+00h]
0x180001c30  mov     rax, rbx
0x180001c33  add     rsp, 28h
0x180001c37  pop     rdi
0x180001c38  pop     rsi
0x180001c39  pop     rbp
0x180001c3a  pop     rbx
0x180001c3b  retn
0x180001c3d  mov     ecx, 3
0x180001c42  int     29h; Win8: RtlFailFast(ecx)
```

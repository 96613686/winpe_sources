# ClRtlDeleteHash

- ea: `0x1800a2ddc`
- end: `0x1800a2e59`
- name: `ClRtlDeleteHash`
- size: `125`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005c424`

## callees

- `0x1800a2ddc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a2e42`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a2e42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2e39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2e39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a2ded`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a2ded`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2e27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2e27`

## pseudocode

```c
void __fastcall ClRtlDeleteHash(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int i; // edi
  __int64 v3; // rsi
  _QWORD **v4; // r14
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rdx

  if ( lpCriticalSection )
  {
    EnterCriticalSection(lpCriticalSection);
    for ( i = 0; i < 0x10; ++i )
    {
      v3 = 32LL * i;
      v4 = (_QWORD **)((char *)&lpCriticalSection[2].SpinCount + v3);
      while ( 1 )
      {
        v5 = *v4;
        if ( *v4 == v4 )
          break;
        v6 = (ULONG_PTR *)((char *)&lpCriticalSection[2].SpinCount + v3);
        if ( (_QWORD *)v5[1] != v6 || (v7 = *v5, *(_QWORD **)(*v5 + 8LL) != v5) )
          __fastfail(3u);
        *v6 = v7;
        *(_QWORD *)(v7 + 8) = v6;
        LocalFree(v5);
      }
    }
    LeaveCriticalSection(lpCriticalSection);
    DeleteCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x1800a2ddc  test    rcx, rcx
0x1800a2ddf  jz      short locret_1800A2E51
0x1800a2de1  push    rbx
0x1800a2de2  push    rsi
0x1800a2de3  push    rdi
0x1800a2de4  push    r14
0x1800a2de6  sub     rsp, 28h
0x1800a2dea  mov     rbx, rcx
0x1800a2ded  call    cs:__imp_EnterCriticalSection
0x1800a2df3  xor     edi, edi
0x1800a2df5  mov     esi, edi
0x1800a2df7  lea     r14, [rbx+70h]
0x1800a2dfb  shl     rsi, 5
0x1800a2dff  add     r14, rsi
0x1800a2e02  mov     rcx, [r14]; hMem
0x1800a2e05  cmp     rcx, r14
0x1800a2e08  jz      short loc_1800A2E2F
0x1800a2e0a  lea     rax, [rbx+70h]
0x1800a2e0e  add     rax, rsi
0x1800a2e11  cmp     [rcx+8], rax
0x1800a2e15  jnz     short loc_1800A2E52
0x1800a2e17  mov     rdx, [rcx]
0x1800a2e1a  cmp     [rdx+8], rcx
0x1800a2e1e  jnz     short loc_1800A2E52
0x1800a2e20  mov     [rax], rdx
0x1800a2e23  mov     [rdx+8], rax
0x1800a2e27  call    cs:__imp_LocalFree
0x1800a2e2d  jmp     short loc_1800A2E02
0x1800a2e2f  inc     edi
0x1800a2e31  cmp     edi, 10h
0x1800a2e34  jb      short loc_1800A2DF5
0x1800a2e36  mov     rcx, rbx; lpCriticalSection
0x1800a2e39  call    cs:__imp_LeaveCriticalSection
0x1800a2e3f  mov     rcx, rbx; lpCriticalSection
0x1800a2e42  call    cs:__imp_DeleteCriticalSection
0x1800a2e48  add     rsp, 28h
0x1800a2e4c  pop     r14
0x1800a2e4e  pop     rdi
0x1800a2e4f  pop     rsi
0x1800a2e50  pop     rbx
0x1800a2e51  retn
0x1800a2e52  mov     ecx, 3
0x1800a2e57  int     29h; Win8: RtlFailFast(ecx)
```

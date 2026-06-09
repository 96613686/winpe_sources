# IndexHashCreate

- ea: `0x180042970`
- end: `0x180042a61`
- name: `IndexHashCreate`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x18000438c`
- `0x180006e40`
- `0x180007e38`
- `0x18000cde0`
- `0x180011500`
- `0x18001346a`
- `0x180039f34`
- `0x180042970`

## import_xrefs

- `ntdll!RtlCreateHashTable` at `0x1800429d2`
- `ntdll!RtlCreateHashTable` at `0x1800429d2`

## string_xrefs

- `0x1800429e8`: `RtlCreateHashTable`
- `0x180042a21`: `IndexHashCreate`

## pseudocode

```c
__int64 __fastcall IndexHashCreate(__int64 a1, _QWORD *a2)
{
  int v3; // esi
  __int64 v5; // rax
  _QWORD *v6; // rdi
  __int64 FastRWLock; // rbx
  __int64 v8; // rcx
  void *v10; // [rsp+60h] [rbp+8h] BYREF

  v10 = 0;
  v3 = 0;
  v5 = WfpPoolAllocNonPaged(0x48u);
  v6 = v10;
  FastRWLock = v5;
  if ( v5 )
    goto LABEL_5;
  memset_0(v10, 0, 0x48u);
  FastRWLock = WfpCreateFastRWLock(v6);
  if ( FastRWLock )
    goto LABEL_5;
  if ( (unsigned __int8)RtlCreateHashTable(v6 + 7, 0, 0) )
  {
    v6[6] = a1;
    v6[8] = 72;
    v6[8] = 4LL * *(unsigned __int16 *)v6[6] + 128;
    *a2 = v6;
    return FastRWLock;
  }
  v3 = 1;
  FastRWLock = WfpReportSysErrorAsNtStatus(v8, "RtlCreateHashTable", 3221225473LL);
  if ( FastRWLock )
  {
LABEL_5:
    if ( v3 )
      WfpCriticalSectionDestroy(v6);
    WfpMemFree(&v10);
    *a2 = 0;
    if ( FastRWLock )
      WfpReportError(FastRWLock, "IndexHashCreate");
  }
  return FastRWLock;
}

```

## disassembly

```asm
0x180042970  push    rbx
0x180042972  push    rbp
0x180042973  push    rsi
0x180042974  push    rdi
0x180042975  push    r14
0x180042977  push    r15
0x180042979  sub     rsp, 28h
0x18004297d  mov     rbp, rcx
0x180042980  mov     [rsp+58h+arg_0], 0
0x180042989  xor     esi, esi
0x18004298b  lea     r8, [rsp+58h+arg_0]
0x180042990  mov     r14, rdx
0x180042993  lea     r15d, [rsi+48h]
0x180042997  mov     ecx, r15d; dwBytes
0x18004299a  call    WfpPoolAllocNonPaged
0x18004299f  mov     rdi, [rsp+58h+arg_0]
0x1800429a4  mov     rbx, rax
0x1800429a7  test    rax, rax
0x1800429aa  jnz     short loc_1800429FF
0x1800429ac  mov     r8d, r15d; Size
0x1800429af  xor     edx, edx; Val
0x1800429b1  mov     rcx, rdi; void *
0x1800429b4  call    memset_0
0x1800429b9  mov     rcx, rdi
0x1800429bc  call    WfpCreateFastRWLock
0x1800429c1  mov     rbx, rax
0x1800429c4  test    rax, rax
0x1800429c7  jnz     short loc_1800429FF
0x1800429c9  lea     rcx, [rdi+38h]
0x1800429cd  xor     r8d, r8d
0x1800429d0  xor     edx, edx
0x1800429d2  call    cs:__imp_RtlCreateHashTable
0x1800429d9  nop     dword ptr [rax+rax+00h]
0x1800429de  test    al, al
0x1800429e0  jnz     short loc_180042A41
0x1800429e2  mov     r8d, 0C0000001h
0x1800429e8  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x1800429ef  lea     esi, [rbx+1]
0x1800429f2  call    WfpReportSysErrorAsNtStatus
0x1800429f7  mov     rbx, rax
0x1800429fa  test    rax, rax
0x1800429fd  jz      short loc_180042A30
0x1800429ff  test    esi, esi
0x180042a01  jz      short loc_180042A0B
0x180042a03  mov     rcx, rdi
0x180042a06  call    WfpCriticalSectionDestroy
0x180042a0b  lea     rcx, [rsp+58h+arg_0]
0x180042a10  call    WfpMemFree
0x180042a15  mov     qword ptr [r14], 0
0x180042a1c  test    rbx, rbx
0x180042a1f  jz      short loc_180042A30
0x180042a21  lea     rdx, aIndexhashcreat; "IndexHashCreate"
0x180042a28  mov     rcx, rbx
0x180042a2b  call    WfpReportError
0x180042a30  mov     rax, rbx
0x180042a33  add     rsp, 28h
0x180042a37  pop     r15
0x180042a39  pop     r14
0x180042a3b  pop     rdi
0x180042a3c  pop     rsi
0x180042a3d  pop     rbp
0x180042a3e  pop     rbx
0x180042a3f  retn
0x180042a41  mov     [rdi+30h], rbp
0x180042a45  mov     [rdi+40h], r15
0x180042a49  mov     rax, [rdi+30h]
0x180042a4d  movzx   ecx, word ptr [rax]
0x180042a50  lea     rcx, ds:80h[rcx*4]
0x180042a58  mov     [rdi+40h], rcx
0x180042a5c  mov     [r14], rdi
0x180042a5f  jmp     short loc_180042A30
```

# UninitAllocator

- ea: `0x1800029dc`
- end: `0x180002ac9`
- name: `UninitAllocator`
- size: `237`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800077c0`
- `0x180007c20`

## callees

- `0x1800029dc`
- `0x180007df8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002a1f`
- `KERNEL32!DeleteCriticalSection` at `0x180002a58`
- `KERNEL32!DeleteCriticalSection` at `0x180002a91`
- `KERNEL32!DeleteCriticalSection` at `0x180002a1f`
- `KERNEL32!DeleteCriticalSection` at `0x180002a58`
- `KERNEL32!DeleteCriticalSection` at `0x180002a91`
- `KERNEL32!LocalFree` at `0x1800029fe`
- `KERNEL32!LocalFree` at `0x180002a37`
- `KERNEL32!LocalFree` at `0x180002a70`
- `KERNEL32!LocalFree` at `0x1800029fe`
- `KERNEL32!LocalFree` at `0x180002a37`
- `KERNEL32!LocalFree` at `0x180002a70`

## pseudocode

```c
__int64 UninitAllocator()
{
  int v0; // ebx
  int v1; // edi
  int v2; // esi
  HLOCAL v3; // rcx
  HLOCAL v4; // rcx
  HLOCAL v5; // rcx

  v0 = 0;
  v1 = 0;
  v2 = 0;
  while ( 1 )
  {
    v3 = qword_18000E348;
    if ( !qword_18000E348 )
      break;
    qword_18000E348 = (HLOCAL)*((_QWORD *)qword_18000E348 + 2);
    LocalFree(v3);
    ++v0;
  }
  DeleteCriticalSection(&stru_18000E350);
  while ( 1 )
  {
    v4 = qword_18000E380;
    if ( !qword_18000E380 )
      break;
    qword_18000E380 = *(HLOCAL *)qword_18000E380;
    LocalFree(v4);
    ++v1;
  }
  DeleteCriticalSection(&stru_18000E388);
  while ( 1 )
  {
    v5 = qword_18000E318;
    if ( !qword_18000E318 )
      break;
    qword_18000E318 = *(HLOCAL *)qword_18000E318;
    LocalFree(v5);
    ++v2;
  }
  DeleteCriticalSection(&stru_18000E320);
  return TspLog(8, "UninitAllocator: exited(%d, %d, %d)", v0, v1, v2);
}

```

## disassembly

```asm
0x1800029dc  mov     [rsp+arg_0], rbx
0x1800029e1  mov     [rsp+arg_8], rsi
0x1800029e6  push    rdi
0x1800029e7  sub     rsp, 30h
0x1800029eb  xor     ebx, ebx
0x1800029ed  xor     edi, edi
0x1800029ef  xor     esi, esi
0x1800029f1  jmp     short loc_180002A0C
0x1800029f3  mov     rax, [rcx+10h]
0x1800029f7  mov     cs:qword_18000E348, rax
0x1800029fe  call    cs:__imp_LocalFree
0x180002a05  nop     dword ptr [rax+rax+00h]
0x180002a0a  inc     ebx
0x180002a0c  mov     rcx, cs:qword_18000E348; hMem
0x180002a13  test    rcx, rcx
0x180002a16  jnz     short loc_1800029F3
0x180002a18  lea     rcx, stru_18000E350; lpCriticalSection
0x180002a1f  call    cs:__imp_DeleteCriticalSection
0x180002a26  nop     dword ptr [rax+rax+00h]
0x180002a2b  jmp     short loc_180002A45
0x180002a2d  mov     rax, [rcx]
0x180002a30  mov     cs:qword_18000E380, rax
0x180002a37  call    cs:__imp_LocalFree
0x180002a3e  nop     dword ptr [rax+rax+00h]
0x180002a43  inc     edi
0x180002a45  mov     rcx, cs:qword_18000E380; hMem
0x180002a4c  test    rcx, rcx
0x180002a4f  jnz     short loc_180002A2D
0x180002a51  lea     rcx, stru_18000E388; lpCriticalSection
0x180002a58  call    cs:__imp_DeleteCriticalSection
0x180002a5f  nop     dword ptr [rax+rax+00h]
0x180002a64  jmp     short loc_180002A7E
0x180002a66  mov     rax, [rcx]
0x180002a69  mov     cs:qword_18000E318, rax
0x180002a70  call    cs:__imp_LocalFree
0x180002a77  nop     dword ptr [rax+rax+00h]
0x180002a7c  inc     esi
0x180002a7e  mov     rcx, cs:qword_18000E318; hMem
0x180002a85  test    rcx, rcx
0x180002a88  jnz     short loc_180002A66
0x180002a8a  lea     rcx, stru_18000E320; lpCriticalSection
0x180002a91  call    cs:__imp_DeleteCriticalSection
0x180002a98  nop     dword ptr [rax+rax+00h]
0x180002a9d  mov     r9d, edi
0x180002aa0  mov     [rsp+38h+var_18], esi
0x180002aa4  mov     r8d, ebx
0x180002aa7  lea     rdx, aUninitallocato; "UninitAllocator: exited(%d, %d, %d)"
0x180002aae  mov     ecx, 8
0x180002ab3  call    TspLog
0x180002ab8  mov     rbx, [rsp+38h+arg_0]
0x180002abd  mov     rsi, [rsp+38h+arg_8]
0x180002ac2  add     rsp, 30h
0x180002ac6  pop     rdi
0x180002ac7  retn
```

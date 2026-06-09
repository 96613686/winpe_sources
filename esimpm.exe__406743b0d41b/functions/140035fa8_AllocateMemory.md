# AllocateMemory

- ea: `0x140035fa8`
- end: `0x1400360b6`
- name: `AllocateMemory`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003574c`

## callees

- `0x140035fa8`
- `0x1400361e0`
- `0x140036300`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140036027`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140036027`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140035fbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140035fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035fca`

## string_xrefs

- `0x140036002`: `CreateTimer`
- `0x14003607b`: `CreateTimer`

## pseudocode

```c
__int64 __fastcall AllocateMemory(__int64 a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  HANDLE ProcessHeap; // rdi
  DWORD LastError; // eax
  int v6; // r8d
  LPVOID v7; // rax
  int v8; // r8d

  v3 = 0;
  ProcessHeap = GetProcessHeap();
  if ( ProcessHeap || (LastError = GetLastError(), (v3 = LastError) == 0) )
  {
    v7 = HeapAlloc(ProcessHeap, 8u, 0x40u);
    ProcessHeap = v7;
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sdqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v8, (unsigned int)"CreateTimer", 126, (char)v7, 64);
    }
    else
    {
      v3 = 14;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v8, (unsigned int)"CreateTimer", 126, 64);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v6, (unsigned int)"CreateTimer", 126, LastError);
  }
  *a2 = ProcessHeap;
  return v3;
}

```

## disassembly

```asm
0x140035fa8  mov     [rsp+arg_0], rbx
0x140035fad  mov     [rsp+arg_8], rsi
0x140035fb2  push    rdi
0x140035fb3  sub     rsp, 40h
0x140035fb7  mov     rsi, rdx
0x140035fba  xor     ebx, ebx
0x140035fbc  call    cs:__imp_GetProcessHeap
0x140035fc2  mov     rdi, rax
0x140035fc5  test    rax, rax
0x140035fc8  jnz     short loc_14003601B
0x140035fca  call    cs:__imp_GetLastError
0x140035fd0  mov     ebx, eax
0x140035fd2  test    eax, eax
0x140035fd4  jz      short loc_14003601B
0x140035fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140035fdd  lea     rdx, WPP_GLOBAL_Control
0x140035fe4  cmp     rcx, rdx
0x140035fe7  jz      loc_1400360A1
0x140035fed  test    byte ptr [rcx+1Ch], 4
0x140035ff1  jz      loc_1400360A1
0x140035ff7  lea     edx, [rdi+0Ah]
0x140035ffa  mov     dword ptr [rsp+48h+var_20], eax
0x140035ffe  mov     rcx, [rcx+10h]
0x140036002  lea     r9, aCreatetimer; "CreateTimer"
0x140036009  mov     [rsp+48h+var_28], 7Eh ; '~'
0x140036011  call    WPP_SF_sdd
0x140036016  jmp     loc_1400360A1
0x14003601b  mov     edx, 8; dwFlags
0x140036020  mov     rcx, rdi; hHeap
0x140036023  lea     r8d, [rdx+38h]; dwBytes
0x140036027  call    cs:__imp_HeapAlloc
0x14003602d  mov     rdi, rax
0x140036030  test    rax, rax
0x140036033  jnz     short loc_14003605E
0x140036035  lea     ebx, [rax+0Eh]
0x140036038  mov     rcx, cs:WPP_GLOBAL_Control
0x14003603f  lea     rdx, WPP_GLOBAL_Control
0x140036046  cmp     rcx, rdx
0x140036049  jz      short loc_1400360A1
0x14003604b  test    byte ptr [rcx+1Ch], 4
0x14003604f  jz      short loc_1400360A1
0x140036051  lea     edx, [rax+0Bh]
0x140036054  mov     dword ptr [rsp+48h+var_20], 40h ; '@'
0x14003605c  jmp     short loc_140035FFE
0x14003605e  mov     rcx, cs:WPP_GLOBAL_Control
0x140036065  lea     rdx, WPP_GLOBAL_Control
0x14003606c  cmp     rcx, rdx
0x14003606f  jz      short loc_1400360A1
0x140036071  test    byte ptr [rcx+1Ch], 2
0x140036075  jz      short loc_1400360A1
0x140036077  mov     rcx, [rcx+10h]
0x14003607b  lea     r9, aCreatetimer; "CreateTimer"
0x140036082  mov     [rsp+48h+var_18], 40h ; '@'
0x14003608a  mov     edx, 0Ch
0x14003608f  mov     [rsp+48h+var_20], rax
0x140036094  mov     [rsp+48h+var_28], 7Eh ; '~'
0x14003609c  call    WPP_SF_sdqd
0x1400360a1  mov     [rsi], rdi
0x1400360a4  mov     eax, ebx
0x1400360a6  mov     rbx, [rsp+48h+arg_0]
0x1400360ab  mov     rsi, [rsp+48h+arg_8]
0x1400360b0  add     rsp, 40h
0x1400360b4  pop     rdi
0x1400360b5  retn
```

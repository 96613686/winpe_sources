# RemoveFontResourceEntry

- ea: `0x18007e560`
- end: `0x18007e617`
- name: `RemoveFontResourceEntry`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18007e620`
- `0x18007e710`

## callees

- `0x18007e560`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e596`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e596`
- `GDI32!RemoveFontResourceW` at `0x18007e5cd`
- `GDI32!RemoveFontResourceW` at `0x18007e5cd`
- `ntdll!RtlFreeHeap` at `0x18007e5fe`
- `ntdll!RtlFreeHeap` at `0x18007e5fe`

## pseudocode

```c
void __fastcall RemoveFontResourceEntry(int a1, __int64 a2)
{
  int v4; // ebp
  _QWORD *v5; // rbx
  PVOID *v6; // rsi
  int v7; // eax
  int v9; // eax

  v4 = 1;
LABEL_2:
  v5 = pAFRTNodeList;
  v6 = &pAFRTNodeList;
  while ( v5 )
  {
    if ( (!a2 || *v5 && !(unsigned int)_o__wcsicmp(a2, *v5)) && a1 == *((_DWORD *)v5 + 4) )
    {
      v7 = *((_DWORD *)v5 + 5);
      if ( a2 )
      {
        v4 = 0;
        v9 = v7 - 1;
        *((_DWORD *)v5 + 5) = v9;
        if ( v9 )
          return;
      }
      else if ( v7 )
      {
        do
          RemoveFontResourceW((LPCWSTR)*v5);
        while ( (*((_DWORD *)v5 + 5))-- != 1 );
      }
      *v6 = (PVOID)v5[1];
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      if ( v4 )
        goto LABEL_2;
      return;
    }
    v6 = (PVOID *)(v5 + 1);
    v5 = (_QWORD *)MEMORY[8];
  }
}

```

## disassembly

```asm
0x18007e560  push    rbx
0x18007e562  push    rbp
0x18007e563  push    rsi
0x18007e564  push    rdi
0x18007e565  push    r14
0x18007e567  sub     rsp, 20h
0x18007e56b  mov     rdi, rdx
0x18007e56e  mov     r14d, ecx
0x18007e571  mov     ebp, 1
0x18007e576  mov     rbx, cs:pAFRTNodeList
0x18007e57d  lea     rsi, pAFRTNodeList
0x18007e584  jmp     short loc_18007E5B2
0x18007e586  test    rdi, rdi
0x18007e589  jz      short loc_18007E5A0
0x18007e58b  mov     rdx, [rbx]
0x18007e58e  test    rdx, rdx
0x18007e591  jz      short loc_18007E5A6
0x18007e593  mov     rcx, rdi
0x18007e596  call    cs:__imp__o__wcsicmp
0x18007e59c  test    eax, eax
0x18007e59e  jnz     short loc_18007E5A6
0x18007e5a0  cmp     r14d, [rbx+10h]
0x18007e5a4  jz      short loc_18007E5B9
0x18007e5a6  lea     rsi, [rbx+8]
0x18007e5aa  mov     rbx, ds:8
0x18007e5b2  test    rbx, rbx
0x18007e5b5  jnz     short loc_18007E586
0x18007e5b7  jmp     short loc_18007E60C
0x18007e5b9  test    rbx, rbx
0x18007e5bc  jz      short loc_18007E60C
0x18007e5be  mov     eax, [rbx+14h]
0x18007e5c1  test    rdi, rdi
0x18007e5c4  jnz     short loc_18007E5DB
0x18007e5c6  test    eax, eax
0x18007e5c8  jz      short loc_18007E5E5
0x18007e5ca  mov     rcx, [rbx]; lpFileName
0x18007e5cd  call    cs:__imp_RemoveFontResourceW
0x18007e5d3  sub     dword ptr [rbx+14h], 1
0x18007e5d7  jnz     short loc_18007E5CA
0x18007e5d9  jmp     short loc_18007E5E5
0x18007e5db  xor     ebp, ebp
0x18007e5dd  sub     eax, 1
0x18007e5e0  mov     [rbx+14h], eax
0x18007e5e3  jnz     short loc_18007E60C
0x18007e5e5  mov     rax, [rbx+8]
0x18007e5e9  mov     r8, rbx; P
0x18007e5ec  mov     [rsi], rax
0x18007e5ef  xor     edx, edx; Flags
0x18007e5f1  mov     rcx, gs:60h
0x18007e5fa  mov     rcx, [rcx+30h]; HeapHandle
0x18007e5fe  call    cs:__imp_RtlFreeHeap
0x18007e604  test    ebp, ebp
0x18007e606  jnz     loc_18007E576
0x18007e60c  add     rsp, 20h
0x18007e610  pop     r14
0x18007e612  pop     rdi
0x18007e613  pop     rsi
0x18007e614  pop     rbp
0x18007e615  pop     rbx
0x18007e616  retn
```

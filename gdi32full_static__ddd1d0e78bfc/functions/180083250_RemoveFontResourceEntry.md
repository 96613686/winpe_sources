# RemoveFontResourceEntry

- ea: `0x180083250`
- end: `0x18008331a`
- name: `RemoveFontResourceEntry`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180083320`
- `0x180083430`

## callees

- `0x180083250`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180083286`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180083286`
- `GDI32!RemoveFontResourceW` at `0x1800832c3`
- `GDI32!RemoveFontResourceW` at `0x1800832c3`
- `ntdll!RtlFreeHeap` at `0x1800832fa`
- `ntdll!RtlFreeHeap` at `0x1800832fa`

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
0x180083250  push    rbx
0x180083252  push    rbp
0x180083253  push    rsi
0x180083254  push    rdi
0x180083255  push    r14
0x180083257  sub     rsp, 20h
0x18008325b  mov     rdi, rdx
0x18008325e  mov     r14d, ecx
0x180083261  mov     ebp, 1
0x180083266  mov     rbx, cs:pAFRTNodeList
0x18008326d  lea     rsi, pAFRTNodeList
0x180083274  jmp     short loc_1800832A8
0x180083276  test    rdi, rdi
0x180083279  jz      short loc_180083296
0x18008327b  mov     rdx, [rbx]
0x18008327e  test    rdx, rdx
0x180083281  jz      short loc_18008329C
0x180083283  mov     rcx, rdi
0x180083286  call    cs:__imp__o__wcsicmp
0x18008328d  nop     dword ptr [rax+rax+00h]
0x180083292  test    eax, eax
0x180083294  jnz     short loc_18008329C
0x180083296  cmp     r14d, [rbx+10h]
0x18008329a  jz      short loc_1800832AF
0x18008329c  lea     rsi, [rbx+8]
0x1800832a0  mov     rbx, ds:8
0x1800832a8  test    rbx, rbx
0x1800832ab  jnz     short loc_180083276
0x1800832ad  jmp     short loc_18008330E
0x1800832af  test    rbx, rbx
0x1800832b2  jz      short loc_18008330E
0x1800832b4  mov     eax, [rbx+14h]
0x1800832b7  test    rdi, rdi
0x1800832ba  jnz     short loc_1800832D7
0x1800832bc  test    eax, eax
0x1800832be  jz      short loc_1800832E1
0x1800832c0  mov     rcx, [rbx]; lpFileName
0x1800832c3  call    cs:__imp_RemoveFontResourceW
0x1800832ca  nop     dword ptr [rax+rax+00h]
0x1800832cf  sub     dword ptr [rbx+14h], 1
0x1800832d3  jnz     short loc_1800832C0
0x1800832d5  jmp     short loc_1800832E1
0x1800832d7  xor     ebp, ebp
0x1800832d9  sub     eax, 1
0x1800832dc  mov     [rbx+14h], eax
0x1800832df  jnz     short loc_18008330E
0x1800832e1  mov     rax, [rbx+8]
0x1800832e5  mov     r8, rbx; P
0x1800832e8  mov     [rsi], rax
0x1800832eb  xor     edx, edx; Flags
0x1800832ed  mov     rcx, gs:60h
0x1800832f6  mov     rcx, [rcx+30h]; HeapHandle
0x1800832fa  call    cs:__imp_RtlFreeHeap
0x180083301  nop     dword ptr [rax+rax+00h]
0x180083306  test    ebp, ebp
0x180083308  jnz     loc_180083266
0x18008330e  add     rsp, 20h
0x180083312  pop     r14
0x180083314  pop     rdi
0x180083315  pop     rsi
0x180083316  pop     rbp
0x180083317  pop     rbx
0x180083318  retn
```

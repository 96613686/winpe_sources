# AllocateBuffer

- ea: `0x1800142b0`
- end: `0x18001443c`
- name: `AllocateBuffer`
- size: `396`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030d0`
- `0x180012330`

## callees

- `0x1800142b0`
- `0x180021b14`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014303`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143de`

## pseudocode

```c
__int64 __fastcall AllocateBuffer(unsigned int a1, _QWORD *a2, unsigned int *a3)
{
  unsigned int v5; // ebx
  DWORD LastError; // ebp
  _DWORD *v7; // rax
  _QWORD *v9; // rcx
  USHORT v10; // dx

  *a2 = 0;
  if ( ~a1 < 0x1C00 )
  {
    LastError = 632;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v10 = 10;
LABEL_12:
    WPP_SF_d(v9[2], v10, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, LastError);
    return LastError;
  }
  if ( a1 + 32 < a1 )
  {
    LastError = 534;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v10 = 11;
    goto LABEL_12;
  }
  v5 = a1 + 7168;
  if ( a1 + 7168 < a1 + 32 )
  {
    LastError = 534;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v10 = 12;
    goto LABEL_12;
  }
  LastError = 0;
  if ( v5 > *a3 )
  {
    v7 = LocalAlloc(0x40u, v5);
    *a2 = v7;
    if ( v7 )
    {
      v7[2] = 8;
      *a3 = v5;
      return LastError;
    }
    LastError = GetLastError();
    if ( LastError )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 13;
        goto LABEL_12;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800142b0  mov     [rsp+arg_8], rbp
0x1800142b5  mov     [rsp+arg_10], rsi
0x1800142ba  push    rdi
0x1800142bb  sub     rsp, 20h
0x1800142bf  mov     eax, ecx
0x1800142c1  mov     qword ptr [rdx], 0
0x1800142c8  not     eax
0x1800142ca  mov     rsi, r8
0x1800142cd  mov     rdi, rdx
0x1800142d0  cmp     eax, 1C00h
0x1800142d5  jb      short loc_18001433C
0x1800142d7  lea     eax, [rcx+20h]
0x1800142da  cmp     eax, ecx
0x1800142dc  jb      loc_180014381
0x1800142e2  mov     [rsp+28h+arg_0], rbx
0x1800142e7  lea     ebx, [rax+1BE0h]
0x1800142ed  cmp     ebx, eax
0x1800142ef  jb      loc_1800143A7
0x1800142f5  xor     ebp, ebp
0x1800142f7  cmp     ebx, [r8]
0x1800142fa  jbe     short loc_180014324
0x1800142fc  mov     edx, ebx; uBytes
0x1800142fe  mov     ecx, 40h ; '@'; uFlags
0x180014303  call    cs:__imp_LocalAlloc
0x18001430a  nop     dword ptr [rax+rax+00h]
0x18001430f  mov     [rdi], rax
0x180014312  test    rax, rax
0x180014315  jz      loc_1800143DE
0x18001431b  mov     dword ptr [rax+8], 8
0x180014322  mov     [rsi], ebx
0x180014324  mov     rbx, [rsp+28h+arg_0]
0x180014329  mov     rsi, [rsp+28h+arg_10]
0x18001432e  mov     eax, ebp
0x180014330  mov     rbp, [rsp+28h+arg_8]
0x180014335  add     rsp, 20h
0x180014339  pop     rdi
0x18001433a  retn
0x18001433c  mov     ebp, 278h
0x180014341  mov     rcx, cs:WPP_GLOBAL_Control
0x180014348  lea     rax, WPP_GLOBAL_Control
0x18001434f  cmp     rcx, rax
0x180014352  jz      short loc_180014329
0x180014354  test    byte ptr [rcx+1Ch], 40h
0x180014358  jz      short loc_180014329
0x18001435a  cmp     byte ptr [rcx+19h], 2
0x18001435e  jb      short loc_180014329
0x180014360  mov     edx, 0Ah
0x180014365  jmp     short loc_18001436C
0x180014367  mov     edx, 0Bh
0x18001436c  mov     rcx, [rcx+10h]
0x180014370  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180014377  mov     r9d, ebp
0x18001437a  call    WPP_SF_d
0x18001437f  jmp     short loc_180014329
0x180014381  mov     ebp, 216h
0x180014386  mov     rcx, cs:WPP_GLOBAL_Control
0x18001438d  lea     rax, WPP_GLOBAL_Control
0x180014394  cmp     rcx, rax
0x180014397  jz      short loc_180014329
0x180014399  test    byte ptr [rcx+1Ch], 40h
0x18001439d  jz      short loc_180014329
0x18001439f  cmp     byte ptr [rcx+19h], 2
0x1800143a3  jb      short loc_180014329
0x1800143a5  jmp     short loc_180014367
0x1800143a7  mov     ebp, 216h
0x1800143ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143b3  lea     rax, WPP_GLOBAL_Control
0x1800143ba  cmp     rcx, rax
0x1800143bd  jz      loc_180014324
0x1800143c3  test    byte ptr [rcx+1Ch], 40h
0x1800143c7  jz      loc_180014324
0x1800143cd  cmp     byte ptr [rcx+19h], 2
0x1800143d1  jb      loc_180014324
0x1800143d7  mov     edx, 0Ch
0x1800143dc  jmp     short loc_180014424
0x1800143de  call    cs:__imp_GetLastError
0x1800143e5  nop     dword ptr [rax+rax+00h]
0x1800143ea  mov     ebp, eax
0x1800143ec  test    eax, eax
0x1800143ee  jz      loc_180014324
0x1800143f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143fb  lea     rax, WPP_GLOBAL_Control
0x180014402  cmp     rcx, rax
0x180014405  jz      loc_180014324
0x18001440b  test    byte ptr [rcx+1Ch], 40h
0x18001440f  jz      loc_180014324
0x180014415  cmp     byte ptr [rcx+19h], 2
0x180014419  jb      loc_180014324
0x18001441f  mov     edx, 0Dh
0x180014424  mov     rcx, [rcx+10h]
0x180014428  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x18001442f  mov     r9d, ebp
0x180014432  call    WPP_SF_d
0x180014437  jmp     loc_180014324
```

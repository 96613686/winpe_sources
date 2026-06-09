# DoCreatePalette

- ea: `0x180146430`
- end: `0x18014655d`
- name: `DoCreatePalette`
- size: `301`
- prototype: `_BOOL8 __fastcall(__int64, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18013f9b0`

## callees

- `0x180146430`
- `0x1801740d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180146485`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180146485`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180146524`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180146524`
- `GDI32!CreatePalette` at `0x18014650a`
- `GDI32!CreatePalette` at `0x18014650a`

## pseudocode

```c
_BOOL8 __fastcall DoCreatePalette(__int64 a1, unsigned int a2, unsigned __int16 *a3)
{
  __int64 v5; // rbp
  LOGPALETTE *v6; // rax
  LOGPALETTE *v7; // rbx
  __int64 v8; // rdx

  if ( a2 == -2147483633 )
    return 1;
  if ( a2 >= *(_DWORD *)(a1 + 520) )
    return 0;
  v5 = a2;
  if ( *(_QWORD *)(*(_QWORD *)(a1 + 552) + 8LL * a2) )
    return 0;
  v6 = (LOGPALETTE *)LocalAlloc(0, 4LL * a3[1] + 12);
  v7 = v6;
  if ( !v6 )
    return 0;
  memmove_0(v6, a3, 4LL * a3[1] + 4);
  v8 = (unsigned __int16)(v7->palNumEntries + 2);
  v7->palNumEntries = v8;
  *((_BYTE *)&v7->palVersion + 4 * v8) = 0;
  *((_BYTE *)&v7->palVersion + 4 * v7->palNumEntries + 1) = 0;
  *((_BYTE *)&v7->palNumEntries + 4 * v7->palNumEntries) = 0;
  *((_BYTE *)&v7->palNumEntries + 4 * v7->palNumEntries + 1) = 0;
  *((_BYTE *)v7 + 4 * v7->palNumEntries - 4) = -1;
  *((_BYTE *)v7 + 4 * v7->palNumEntries - 3) = -1;
  *((_BYTE *)v7 + 4 * v7->palNumEntries - 2) = -1;
  *((_BYTE *)v7 + 4 * v7->palNumEntries - 1) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 552) + 8 * v5) = CreatePalette(v7);
  LocalFree(v7);
  return *(_QWORD *)(*(_QWORD *)(a1 + 552) + 8 * v5) != 0;
}

```

## disassembly

```asm
0x180146430  mov     [rsp+arg_0], rbx
0x180146435  mov     [rsp+arg_8], rbp
0x18014643a  mov     [rsp+arg_10], rsi
0x18014643f  push    rdi
0x180146440  sub     rsp, 20h
0x180146444  mov     rsi, r8
0x180146447  mov     rdi, rcx
0x18014644a  cmp     edx, 8000000Fh
0x180146450  jz      loc_180146542
0x180146456  cmp     edx, [rcx+208h]
0x18014645c  jnb     loc_18014653E
0x180146462  mov     rax, [rcx+228h]
0x180146469  mov     ebp, edx
0x18014646b  cmp     qword ptr [rax+rbp*8], 0
0x180146470  jnz     loc_18014653E
0x180146476  movzx   edx, word ptr [r8+2]
0x18014647b  xor     ecx, ecx; uFlags
0x18014647d  lea     rdx, ds:0Ch[rdx*4]; uBytes
0x180146485  call    cs:__imp_LocalAlloc
0x18014648c  nop     dword ptr [rax+rax+00h]
0x180146491  mov     rbx, rax
0x180146494  test    rax, rax
0x180146497  jz      loc_18014653E
0x18014649d  movzx   r8d, word ptr [rsi+2]
0x1801464a2  mov     rdx, rsi; Src
0x1801464a5  mov     rcx, rax; void *
0x1801464a8  lea     r8, ds:4[r8*4]; Size
0x1801464b0  call    memmove_0
0x1801464b5  movzx   ecx, word ptr [rbx+2]
0x1801464b9  add     cx, 2
0x1801464bd  movzx   edx, cx
0x1801464c0  mov     rcx, rbx; plpal
0x1801464c3  mov     [rbx+2], dx
0x1801464c7  mov     byte ptr [rbx+rdx*4], 0
0x1801464cb  movzx   eax, word ptr [rbx+2]
0x1801464cf  mov     byte ptr [rbx+rax*4+1], 0
0x1801464d4  movzx   eax, word ptr [rbx+2]
0x1801464d8  mov     byte ptr [rbx+rax*4+2], 0
0x1801464dd  movzx   eax, word ptr [rbx+2]
0x1801464e1  mov     byte ptr [rbx+rax*4+3], 0
0x1801464e6  movzx   eax, word ptr [rbx+2]
0x1801464ea  mov     byte ptr [rbx+rax*4-4], 0FFh
0x1801464ef  movzx   eax, word ptr [rbx+2]
0x1801464f3  mov     byte ptr [rbx+rax*4-3], 0FFh
0x1801464f8  movzx   eax, word ptr [rbx+2]
0x1801464fc  mov     byte ptr [rbx+rax*4-2], 0FFh
0x180146501  movzx   eax, word ptr [rbx+2]
0x180146505  mov     byte ptr [rbx+rax*4-1], 0
0x18014650a  call    cs:__imp_CreatePalette
0x180146511  nop     dword ptr [rax+rax+00h]
0x180146516  mov     rcx, [rdi+228h]
0x18014651d  mov     [rcx+rbp*8], rax
0x180146521  mov     rcx, rbx; hMem
0x180146524  call    cs:__imp_LocalFree
0x18014652b  nop     dword ptr [rax+rax+00h]
0x180146530  mov     rax, [rdi+228h]
0x180146537  cmp     qword ptr [rax+rbp*8], 0
0x18014653c  jnz     short loc_180146542
0x18014653e  xor     eax, eax
0x180146540  jmp     short loc_180146547
0x180146542  mov     eax, 1
0x180146547  mov     rbx, [rsp+28h+arg_0]
0x18014654c  mov     rbp, [rsp+28h+arg_8]
0x180146551  mov     rsi, [rsp+28h+arg_10]
0x180146556  add     rsp, 20h
0x18014655a  pop     rdi
0x18014655b  retn
```

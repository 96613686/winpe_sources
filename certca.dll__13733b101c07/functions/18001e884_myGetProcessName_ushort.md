# myGetProcessName(ushort * *)

- ea: `0x18001e884`
- end: `0x18001e95e`
- name: `?myGetProcessName@@YAJPEAPEAG@Z`
- size: `218`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d5d0`

## callees

- `0x180008400`
- `0x180013a86`
- `0x18001e884`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e912`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e912`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001e898`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001e898`

## pseudocode

```c
__int64 __fastcall myGetProcessName(unsigned __int16 **a1)
{
  LPWSTR CommandLineW; // rax
  const WCHAR *v3; // rdx
  WCHAR v4; // cx
  const WCHAR *v5; // rdi
  __int16 v6; // r8
  const WCHAR *v7; // rbx
  WCHAR v8; // cx
  unsigned __int64 v9; // rbx
  char *v10; // rsi
  unsigned int v11; // ebx
  size_t v12; // rbx

  *a1 = 0;
  CommandLineW = GetCommandLineW();
  v3 = &Class;
  if ( CommandLineW )
    v3 = CommandLineW;
  if ( *v3 == 34 )
    v4 = v3[1];
  else
    v4 = *v3;
  v5 = v3 + 1;
  if ( *v3 != 34 )
    v5 = v3;
  v6 = 34;
  if ( *v3 != 34 )
    v6 = 32;
  v7 = v5;
  if ( v4 )
  {
    v8 = *v5;
    do
    {
      if ( v6 == v8 )
        break;
      ++v7;
      if ( v8 == 92 )
        v5 = v7;
      v8 = *v7;
    }
    while ( *v7 );
  }
  v9 = (unsigned __int64)((char *)v7 - (char *)v5) >> 1;
  v10 = (char *)LocalAlloc(0, 2LL * (unsigned int)(v9 + 1));
  if ( v10 )
  {
    v12 = 2LL * (unsigned int)v9;
    memcpy_0(v10, v5, v12);
    *a1 = (unsigned __int16 *)v10;
    *(_WORD *)&v10[v12] = 0;
    return 0;
  }
  else
  {
    v11 = -2147024882;
    CSPrintErrorLineFile(0x3C401CAu, -2147024882);
  }
  return v11;
}

```

## disassembly

```asm
0x18001e884  push    rbx
0x18001e886  push    rsi
0x18001e887  push    rdi
0x18001e888  push    r14
0x18001e88a  sub     rsp, 28h
0x18001e88e  mov     r14, rcx
0x18001e891  mov     qword ptr [rcx], 0
0x18001e898  call    cs:__imp_GetCommandLineW
0x18001e89e  lea     rdx, Class
0x18001e8a5  mov     r9d, 22h ; '"'
0x18001e8ab  test    rax, rax
0x18001e8ae  cmovnz  rdx, rax
0x18001e8b2  cmp     r9w, [rdx]
0x18001e8b6  jnz     short loc_18001E8BE
0x18001e8b8  movzx   ecx, word ptr [rdx+2]
0x18001e8bc  jmp     short loc_18001E8C1
0x18001e8be  movzx   ecx, word ptr [rdx]
0x18001e8c1  mov     eax, 20h ; ' '
0x18001e8c6  lea     rdi, [rdx+2]
0x18001e8ca  cmovnz  rdi, rdx
0x18001e8ce  mov     r8d, r9d
0x18001e8d1  cmovnz  r8w, ax
0x18001e8d6  mov     rbx, rdi
0x18001e8d9  xor     eax, eax
0x18001e8db  cmp     ax, cx
0x18001e8de  jz      short loc_18001E904
0x18001e8e0  movzx   ecx, word ptr [rdi]
0x18001e8e3  cmp     r8w, cx
0x18001e8e7  jz      short loc_18001E904
0x18001e8e9  mov     eax, 5Ch ; '\'
0x18001e8ee  add     rbx, 2
0x18001e8f2  cmp     ax, cx
0x18001e8f5  jnz     short loc_18001E8FA
0x18001e8f7  mov     rdi, rbx
0x18001e8fa  movzx   ecx, word ptr [rbx]
0x18001e8fd  xor     eax, eax
0x18001e8ff  cmp     ax, cx
0x18001e902  jnz     short loc_18001E8E3
0x18001e904  sub     rbx, rdi
0x18001e907  xor     ecx, ecx; uFlags
0x18001e909  shr     rbx, 1
0x18001e90c  lea     edx, [rbx+1]
0x18001e90f  add     rdx, rdx; uBytes
0x18001e912  call    cs:__imp_LocalAlloc
0x18001e918  mov     rsi, rax
0x18001e91b  test    rax, rax
0x18001e91e  jnz     short loc_18001E933
0x18001e920  mov     ebx, 8007000Eh
0x18001e925  mov     ecx, 3C401CAh; unsigned int
0x18001e92a  mov     edx, ebx; int
0x18001e92c  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001e931  jmp     short loc_18001E952
0x18001e933  mov     eax, ebx
0x18001e935  mov     rdx, rdi; Src
0x18001e938  mov     rcx, rsi; void *
0x18001e93b  lea     rbx, [rax+rax]
0x18001e93f  mov     r8, rbx; Size
0x18001e942  call    memcpy_0
0x18001e947  xor     eax, eax
0x18001e949  mov     [r14], rsi
0x18001e94c  mov     [rbx+rsi], ax
0x18001e950  xor     ebx, ebx
0x18001e952  mov     eax, ebx
0x18001e954  add     rsp, 28h
0x18001e958  pop     r14
0x18001e95a  pop     rdi
0x18001e95b  pop     rsi
0x18001e95c  pop     rbx
0x18001e95d  retn
```

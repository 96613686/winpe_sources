# WppTraceIndent(char * *,_WppTraceIndentType)

- ea: `0x1800238a4`
- end: `0x180023a13`
- name: `?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z`
- size: `367`
- prototype: `char *__fastcall(__int64, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180023730`
- `0x180023a1c`
- `0x180023c10`
- `0x180023e20`

## callees

- `0x180023800`
- `0x1800238a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800238b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800238b8`

## pseudocode

```c
char *__fastcall WppTraceIndent(__int64 a1, unsigned int a2)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 v4; // rdx
  char *i; // rcx
  int v6; // ebx
  bool v7; // zf
  int v8; // edi
  int j; // esi
  unsigned __int64 v10; // rcx
  const char *v11; // r8
  char *result; // rax

  CurrentThreadId = GetCurrentThreadId();
  v6 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v6 = 0;
    `WppTraceIndent'::`2'::ThreadTable[0] = CurrentThreadId;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_180031724 = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || `WppTraceIndent'::`2'::ThreadTable[2 * `WppTraceIndent'::`2'::idxCurrentThread] != CurrentThreadId )
    {
      v4 = 0xFFFFFFFFLL;
      for ( i = 0; ; i = (char *)(unsigned int)((_DWORD)i + 1) )
      {
        v7 = (_DWORD)i == 32;
        if ( (unsigned int)i >= 0x20 )
          break;
        if ( `WppTraceIndent'::`2'::ThreadTable[2 * (int)i] == CurrentThreadId )
        {
          v6 = (int)i;
          `WppTraceIndent'::`2'::idxCurrentThread = (int)i;
          v7 = (_DWORD)i == 32;
          break;
        }
        if ( (_DWORD)v4 == -1 && !`WppTraceIndent'::`2'::ThreadTable[2 * (int)i] )
          v4 = (unsigned int)i;
      }
      if ( v7 )
      {
        if ( (_DWORD)v4 == -1 )
        {
          v6 = -2;
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
        }
        else
        {
          v6 = v4;
          `WppTraceIndent'::`2'::idxCurrentThread = v4;
          `WppTraceIndent'::`2'::ThreadTable[2 * (int)v4] = CurrentThreadId;
          `WppTraceIndent'::`2'::ThreadTable[2 * (int)v4 + 1] = 0;
        }
      }
    }
    if ( v6 < 0 )
    {
      v8 = 0;
      goto LABEL_23;
    }
  }
  if ( !a2 )
    ++`WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1];
  v8 = `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1];
LABEL_23:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    for ( j = 1; j <= v8; ++j )
    {
      if ( (unsigned int)StringCbCatA(i, v4, "..") )
        break;
    }
  }
  v10 = a2;
  if ( !a2 )
  {
    v11 = ">";
    goto LABEL_34;
  }
  v10 = a2 - 1;
  if ( a2 == 1 )
  {
    v11 = "<";
    goto LABEL_34;
  }
  if ( a2 == 2 )
  {
    v11 = " ";
LABEL_34:
    StringCbCatA((char *)v10, v4, v11);
  }
  if ( v6 >= 0 && a2 == 1 )
  {
    v7 = `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1]-- == 1;
    if ( v7 )
      `WppTraceIndent'::`2'::ThreadTable[2 * v6] = 0;
  }
  result = &`WppTraceIndent'::`2'::szIndentPrefix;
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  return result;
}

```

## disassembly

```asm
0x1800238a4  mov     [rsp+arg_8], rbx
0x1800238a9  mov     [rsp+arg_10], rbp
0x1800238ae  push    rsi
0x1800238af  push    rdi
0x1800238b0  push    r14
0x1800238b2  sub     rsp, 20h
0x1800238b6  mov     ebp, edx
0x1800238b8  call    cs:__imp_GetCurrentThreadId
0x1800238be  movsxd  rbx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800238c5  lea     r14, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x1800238cc  mov     r8d, eax
0x1800238cf  cmp     ebx, 0FFFFFFFFh
0x1800238d2  jnz     short loc_1800238EA
0x1800238d4  xor     ebx, ebx
0x1800238d6  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, eax; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x1800238dc  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800238e2  mov     cs:dword_180031724, ebx
0x1800238e8  jmp     short loc_180023954
0x1800238ea  cmp     ebx, 0FFFFFFFEh
0x1800238ed  jz      short loc_1800238F5
0x1800238ef  cmp     [r14+rbx*8], r8d
0x1800238f3  jz      short loc_180023950
0x1800238f5  or      edx, 0FFFFFFFFh; unsigned __int64
0x1800238f8  xor     ecx, ecx; char *
0x1800238fa  cmp     ecx, 20h ; ' '
0x1800238fd  jnb     short loc_180023924
0x1800238ff  movsxd  rax, ecx
0x180023902  cmp     [r14+rax*8], r8d
0x180023906  jz      short loc_180023919
0x180023908  cmp     edx, 0FFFFFFFFh
0x18002390b  jnz     short loc_180023915
0x18002390d  cmp     dword ptr [r14+rax*8], 0
0x180023912  cmovz   edx, ecx
0x180023915  inc     ecx
0x180023917  jmp     short loc_1800238FA
0x180023919  mov     ebx, ecx
0x18002391b  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180023921  cmp     ecx, 20h ; ' '
0x180023924  jnz     short loc_180023950
0x180023926  cmp     edx, 0FFFFFFFFh
0x180023929  jz      short loc_180023945
0x18002392b  movsxd  rax, edx
0x18002392e  mov     ebx, edx
0x180023930  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, edx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180023936  mov     [r14+rax*8], r8d
0x18002393a  mov     dword ptr [r14+rax*8+4], 0
0x180023943  jmp     short loc_180023950
0x180023945  mov     ebx, 0FFFFFFFEh
0x18002394a  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180023950  test    ebx, ebx
0x180023952  js      short loc_18002396E
0x180023954  movsxd  rax, ebx
0x180023957  test    ebp, ebp
0x180023959  jnz     short loc_180023967
0x18002395b  inc     dword ptr [r14+rax*8+4]
0x180023960  mov     edi, [r14+rax*8+4]
0x180023965  jmp     short loc_180023970
0x180023967  mov     edi, [r14+rax*8+4]
0x18002396c  jmp     short loc_180023970
0x18002396e  xor     edi, edi
0x180023970  mov     rax, cs:WPP_GLOBAL_Control
0x180023977  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18002397e  test    byte ptr [rax+1Ch], 2
0x180023982  jz      short loc_1800239A9
0x180023984  cmp     byte ptr [rax+19h], 5
0x180023988  jb      short loc_1800239A9
0x18002398a  mov     esi, 1
0x18002398f  cmp     edi, esi
0x180023991  jl      short loc_1800239A9
0x180023993  lea     r8, pszSrc; ".."
0x18002399a  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18002399f  test    eax, eax
0x1800239a1  jnz     short loc_1800239A9
0x1800239a3  inc     esi
0x1800239a5  cmp     esi, edi
0x1800239a7  jle     short loc_180023993
0x1800239a9  mov     ecx, ebp; char *
0x1800239ab  test    ebp, ebp
0x1800239ad  jz      short loc_1800239CB
0x1800239af  sub     ecx, 1
0x1800239b2  jz      short loc_1800239C2
0x1800239b4  cmp     ecx, 1
0x1800239b7  jnz     short loc_1800239D7
0x1800239b9  lea     r8, asc_180027F18; " "
0x1800239c0  jmp     short loc_1800239D2
0x1800239c2  lea     r8, asc_180027E38; "<"
0x1800239c9  jmp     short loc_1800239D2
0x1800239cb  lea     r8, asc_180027E34; ">"
0x1800239d2  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x1800239d7  test    ebx, ebx
0x1800239d9  js      short loc_1800239F2
0x1800239db  cmp     ebp, 1
0x1800239de  jnz     short loc_1800239F2
0x1800239e0  movsxd  rcx, ebx
0x1800239e3  sub     [r14+rcx*8+4], ebp
0x1800239e8  jnz     short loc_1800239F2
0x1800239ea  mov     dword ptr [r14+rcx*8], 0
0x1800239f2  mov     rbx, [rsp+38h+arg_8]
0x1800239f7  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x1800239fe  mov     rbp, [rsp+38h+arg_10]
0x180023a03  mov     cs:?WPP_pszIndent@@3PEADEA, rax; char * WPP_pszIndent
0x180023a0a  add     rsp, 20h
0x180023a0e  pop     r14
0x180023a10  pop     rdi
0x180023a11  pop     rsi
0x180023a12  retn
```

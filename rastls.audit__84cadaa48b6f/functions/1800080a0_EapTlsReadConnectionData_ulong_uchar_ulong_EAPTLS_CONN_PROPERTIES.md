# EapTlsReadConnectionData(ulong,uchar *,ulong,_EAPTLS_CONN_PROPERTIES * *)

- ea: `0x1800080a0`
- end: `0x180008232`
- name: `?EapTlsReadConnectionData@@YAKKPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z`
- size: `402`
- prototype: `unsigned int(unsigned int, unsigned __int8 *, unsigned int, struct _EAPTLS_CONN_PROPERTIES **)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x18001bc10`
- `0x1800239a0`
- `0x180052b78`
- `0x180052e60`
- `0x18005363c`
- `0x18005388c`
- `0x180061fc4`
- `0x1800624f4`
- `0x180070bf8`
- `0x180076a1c`

## callees

- `0x180005010`
- `0x1800080a0`
- `0x180008240`
- `0x180038e4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800080d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000819b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800080d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000819b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008218`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008218`

## pseudocode

```c
__int64 __fastcall EapTlsReadConnectionData(
        char a1,
        unsigned __int8 *a2,
        unsigned int a3,
        struct _EAPTLS_CONN_PROPERTIES **a4)
{
  size_t v4; // rdi
  unsigned int v8; // esi
  struct _EAPTLS_CONN_PROPERTIES *v9; // rax
  struct _EAPTLS_CONN_PROPERTIES *v10; // rbx
  DWORD LastError; // edi
  struct _EAPTLS_CONTROL_BLOCK *v12; // rcx
  __int64 v13; // rdx
  bool v14; // zf
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  struct _EAPTLS_CONN_PROPERTIES *v18; // rax

  v4 = a3;
  if ( a3 >= 0x28 && a2 )
  {
    v8 = a3 + 8;
    v9 = (struct _EAPTLS_CONN_PROPERTIES *)LocalAlloc(0x40u, a3 + 8);
    v10 = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v13 = 126;
LABEL_21:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, LastError);
        goto LABEL_27;
      }
      goto LABEL_27;
    }
    memcpy_0(v9, a2, v4);
    if ( !(unsigned int)IsEaptlsConnDataValid(v10, v4) )
    {
      LastError = 13;
      goto LABEL_27;
    }
    v14 = *(_DWORD *)v10 == 0;
    *((_DWORD *)v10 + 1) = v8;
    if ( v14 && *((_DWORD *)v10 + 3) )
    {
      v15 = -1;
      do
        v14 = *((_WORD *)v10 + v15++ + 19) == 0;
      while ( !v14 );
      *(_DWORD *)((char *)v10 + 2 * v15 + 38) = 1;
    }
    if ( *(_DWORD *)v10 != 2 )
    {
      v16 = *((_DWORD *)v10 + 2);
      *(_DWORD *)v10 = 2;
      if ( (v16 & 1) != 0 )
        *((_DWORD *)v10 + 2) = v16 | 0x10;
    }
    v17 = *((_DWORD *)v10 + 2);
    if ( (v17 & 0x20) != 0 )
      *((_DWORD *)v10 + 2) = v17 & 0xFFFFFDFF;
LABEL_26:
    LastError = 0;
    *a4 = v10;
    v10 = 0;
    goto LABEL_27;
  }
  v18 = (struct _EAPTLS_CONN_PROPERTIES *)LocalAlloc(0x40u, 0x30u);
  v10 = v18;
  if ( v18 )
  {
    *(_DWORD *)v18 = 2;
    *((_DWORD *)v18 + 1) = 48;
    if ( a1 < 0 )
      *((_DWORD *)v18 + 2) |= 0x15u;
    if ( (a1 & 1) != 0 )
    {
      *((_DWORD *)v18 + 2) |= 1u;
      *((_DWORD *)v18 + 2) |= 4u;
    }
    goto LABEL_26;
  }
  LastError = GetLastError();
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v13 = 125;
    goto LABEL_21;
  }
LABEL_27:
  LocalFree(v10);
  return LastError;
}

```

## disassembly

```asm
0x1800080a0  push    rbx
0x1800080a2  push    rbp
0x1800080a3  push    rsi
0x1800080a4  push    rdi
0x1800080a5  push    r14
0x1800080a7  sub     rsp, 20h
0x1800080ab  mov     edi, r8d
0x1800080ae  mov     r14, r9
0x1800080b1  mov     rbp, rdx
0x1800080b4  mov     esi, ecx
0x1800080b6  cmp     r8d, 28h ; '('
0x1800080ba  jb      loc_180008191
0x1800080c0  test    rdx, rdx
0x1800080c3  jz      loc_180008191
0x1800080c9  lea     esi, [rdi+8]
0x1800080cc  mov     ecx, 40h ; '@'; uFlags
0x1800080d1  mov     edx, esi; uBytes
0x1800080d3  call    cs:__imp_LocalAlloc
0x1800080da  nop     dword ptr [rax+rax+00h]
0x1800080df  mov     rbx, rax
0x1800080e2  test    rax, rax
0x1800080e5  jnz     short loc_180008116
0x1800080e7  call    cs:__imp_GetLastError
0x1800080ee  nop     dword ptr [rax+rax+00h]
0x1800080f3  mov     edi, eax
0x1800080f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080fc  lea     rax, WPP_GLOBAL_Control
0x180008103  cmp     rcx, rax
0x180008106  jz      loc_180008215
0x18000810c  mov     edx, 7Eh ; '~'
0x180008111  jmp     loc_1800081D5
0x180008116  mov     r8, rdi; Size
0x180008119  mov     rdx, rbp; Src
0x18000811c  mov     rcx, rbx; void *
0x18000811f  call    memcpy_0
0x180008124  mov     edx, edi; unsigned int
0x180008126  mov     rcx, rbx; struct _EAPTLS_CONN_PROPERTIES *
0x180008129  call    ?IsEaptlsConnDataValid@@YAHPEAU_EAPTLS_CONN_PROPERTIES@@K@Z; IsEaptlsConnDataValid(_EAPTLS_CONN_PROPERTIES *,ulong)
0x18000812e  test    eax, eax
0x180008130  jnz     short loc_18000813C
0x180008132  mov     edi, 0Dh
0x180008137  jmp     loc_180008215
0x18000813c  cmp     dword ptr [rbx], 0
0x18000813f  mov     [rbx+4], esi
0x180008142  jnz     short loc_180008165
0x180008144  cmp     dword ptr [rbx+0Ch], 0
0x180008148  jz      short loc_180008165
0x18000814a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008151  cmp     word ptr [rbx+rax*2+26h], 0
0x180008157  lea     rax, [rax+1]
0x18000815b  jnz     short loc_180008151
0x18000815d  mov     dword ptr [rbx+rax*2+26h], 1
0x180008165  cmp     dword ptr [rbx], 2
0x180008168  jz      short loc_18000817D
0x18000816a  mov     eax, [rbx+8]
0x18000816d  mov     dword ptr [rbx], 2
0x180008173  test    al, 1
0x180008175  jz      short loc_18000817D
0x180008177  or      eax, 10h
0x18000817a  mov     [rbx+8], eax
0x18000817d  mov     eax, [rbx+8]
0x180008180  test    al, 20h
0x180008182  jz      loc_18000820E
0x180008188  btr     eax, 9
0x18000818c  mov     [rbx+8], eax
0x18000818f  jmp     short loc_18000820E
0x180008191  mov     edx, 30h ; '0'; uBytes
0x180008196  mov     ecx, 40h ; '@'; uFlags
0x18000819b  call    cs:__imp_LocalAlloc
0x1800081a2  nop     dword ptr [rax+rax+00h]
0x1800081a7  mov     rbx, rax
0x1800081aa  test    rax, rax
0x1800081ad  jnz     short loc_1800081EA
0x1800081af  call    cs:__imp_GetLastError
0x1800081b6  nop     dword ptr [rax+rax+00h]
0x1800081bb  mov     edi, eax
0x1800081bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081c4  lea     rax, WPP_GLOBAL_Control
0x1800081cb  cmp     rcx, rax
0x1800081ce  jz      short loc_180008215
0x1800081d0  mov     edx, 7Dh ; '}'
0x1800081d5  mov     rcx, [rcx+10h]
0x1800081d9  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800081e0  mov     r9d, edi
0x1800081e3  call    WPP_SF_d
0x1800081e8  jmp     short loc_180008215
0x1800081ea  mov     dword ptr [rax], 2
0x1800081f0  mov     dword ptr [rax+4], 30h ; '0'
0x1800081f7  test    sil, sil
0x1800081fa  jns     short loc_180008200
0x1800081fc  or      dword ptr [rax+8], 15h
0x180008200  test    sil, 1
0x180008204  jz      short loc_18000820E
0x180008206  or      dword ptr [rax+8], 1
0x18000820a  or      dword ptr [rax+8], 4
0x18000820e  xor     edi, edi
0x180008210  mov     [r14], rbx
0x180008213  xor     ebx, ebx
0x180008215  mov     rcx, rbx; hMem
0x180008218  call    cs:__imp_LocalFree
0x18000821f  nop     dword ptr [rax+rax+00h]
0x180008224  mov     eax, edi
0x180008226  add     rsp, 20h
0x18000822a  pop     r14
0x18000822c  pop     rdi
0x18000822d  pop     rsi
0x18000822e  pop     rbp
0x18000822f  pop     rbx
0x180008230  retn
```

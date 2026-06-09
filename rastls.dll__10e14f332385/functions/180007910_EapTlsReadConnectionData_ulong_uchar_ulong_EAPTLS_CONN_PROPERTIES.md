# EapTlsReadConnectionData(ulong,uchar *,ulong,_EAPTLS_CONN_PROPERTIES * *)

- ea: `0x180007910`
- end: `0x180007a7f`
- name: `?EapTlsReadConnectionData@@YAKKPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(char, unsigned __int8 *, unsigned int, struct _EAPTLS_CONN_PROPERTIES **)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a300`
- `0x180023b60`
- `0x18004feb4`
- `0x180050150`
- `0x1800508cc`
- `0x180050b0c`
- `0x18005e7f0`
- `0x18005ecf4`
- `0x18006c46c`
- `0x180071b98`

## callees

- `0x180004bd0`
- `0x180007910`
- `0x180007a90`
- `0x18003623c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007943`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800079fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007943`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800079fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180007910  push    rbx
0x180007912  push    rbp
0x180007913  push    rsi
0x180007914  push    rdi
0x180007915  push    r14
0x180007917  sub     rsp, 20h
0x18000791b  mov     edi, r8d
0x18000791e  mov     r14, r9
0x180007921  mov     rbp, rdx
0x180007924  mov     esi, ecx
0x180007926  cmp     r8d, 28h ; '('
0x18000792a  jb      loc_1800079F1
0x180007930  test    rdx, rdx
0x180007933  jz      loc_1800079F1
0x180007939  lea     esi, [rdi+8]
0x18000793c  mov     ecx, 40h ; '@'; uFlags
0x180007941  mov     edx, esi; uBytes
0x180007943  call    cs:__imp_LocalAlloc
0x180007949  mov     rbx, rax
0x18000794c  test    rax, rax
0x18000794f  jnz     short loc_18000797A
0x180007951  call    cs:__imp_GetLastError
0x180007957  mov     edi, eax
0x180007959  mov     rcx, cs:WPP_GLOBAL_Control
0x180007960  lea     rax, WPP_GLOBAL_Control
0x180007967  cmp     rcx, rax
0x18000796a  jz      loc_180007A69
0x180007970  mov     edx, 7Eh ; '~'
0x180007975  jmp     loc_180007A29
0x18000797a  mov     r8, rdi; Size
0x18000797d  mov     rdx, rbp; Src
0x180007980  mov     rcx, rbx; void *
0x180007983  call    memcpy_0
0x180007988  mov     edx, edi; unsigned int
0x18000798a  mov     rcx, rbx; struct _EAPTLS_CONN_PROPERTIES *
0x18000798d  call    ?IsEaptlsConnDataValid@@YAHPEAU_EAPTLS_CONN_PROPERTIES@@K@Z; IsEaptlsConnDataValid(_EAPTLS_CONN_PROPERTIES *,ulong)
0x180007992  test    eax, eax
0x180007994  jnz     short loc_1800079A0
0x180007996  mov     edi, 0Dh
0x18000799b  jmp     loc_180007A69
0x1800079a0  cmp     dword ptr [rbx], 0
0x1800079a3  mov     [rbx+4], esi
0x1800079a6  jnz     short loc_1800079C9
0x1800079a8  cmp     dword ptr [rbx+0Ch], 0
0x1800079ac  jz      short loc_1800079C9
0x1800079ae  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800079b5  cmp     word ptr [rbx+rax*2+26h], 0
0x1800079bb  lea     rax, [rax+1]
0x1800079bf  jnz     short loc_1800079B5
0x1800079c1  mov     dword ptr [rbx+rax*2+26h], 1
0x1800079c9  cmp     dword ptr [rbx], 2
0x1800079cc  jz      short loc_1800079E1
0x1800079ce  mov     eax, [rbx+8]
0x1800079d1  mov     dword ptr [rbx], 2
0x1800079d7  test    al, 1
0x1800079d9  jz      short loc_1800079E1
0x1800079db  or      eax, 10h
0x1800079de  mov     [rbx+8], eax
0x1800079e1  mov     eax, [rbx+8]
0x1800079e4  test    al, 20h
0x1800079e6  jz      short loc_180007A62
0x1800079e8  btr     eax, 9
0x1800079ec  mov     [rbx+8], eax
0x1800079ef  jmp     short loc_180007A62
0x1800079f1  mov     edx, 30h ; '0'; uBytes
0x1800079f6  mov     ecx, 40h ; '@'; uFlags
0x1800079fb  call    cs:__imp_LocalAlloc
0x180007a01  mov     rbx, rax
0x180007a04  test    rax, rax
0x180007a07  jnz     short loc_180007A3E
0x180007a09  call    cs:__imp_GetLastError
0x180007a0f  mov     edi, eax
0x180007a11  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a18  lea     rax, WPP_GLOBAL_Control
0x180007a1f  cmp     rcx, rax
0x180007a22  jz      short loc_180007A69
0x180007a24  mov     edx, 7Dh ; '}'
0x180007a29  mov     rcx, [rcx+10h]
0x180007a2d  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180007a34  mov     r9d, edi
0x180007a37  call    WPP_SF_d
0x180007a3c  jmp     short loc_180007A69
0x180007a3e  mov     dword ptr [rax], 2
0x180007a44  mov     dword ptr [rax+4], 30h ; '0'
0x180007a4b  test    sil, sil
0x180007a4e  jns     short loc_180007A54
0x180007a50  or      dword ptr [rax+8], 15h
0x180007a54  test    sil, 1
0x180007a58  jz      short loc_180007A62
0x180007a5a  or      dword ptr [rax+8], 1
0x180007a5e  or      dword ptr [rax+8], 4
0x180007a62  xor     edi, edi
0x180007a64  mov     [r14], rbx
0x180007a67  xor     ebx, ebx
0x180007a69  mov     rcx, rbx; hMem
0x180007a6c  call    cs:__imp_LocalFree
0x180007a72  mov     eax, edi
0x180007a74  add     rsp, 20h
0x180007a78  pop     r14
0x180007a7a  pop     rdi
0x180007a7b  pop     rsi
0x180007a7c  pop     rbp
0x180007a7d  pop     rbx
0x180007a7e  retn
```

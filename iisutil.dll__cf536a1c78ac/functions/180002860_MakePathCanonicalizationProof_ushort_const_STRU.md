# MakePathCanonicalizationProof(ushort const *,STRU *)

- ea: `0x180002860`
- end: `0x180002aae`
- name: `?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z`
- size: `590`
- prototype: `signed int __fastcall(const unsigned __int16 *Src, void **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002d6c0`

## callees

- `0x1800026d0`
- `0x180002860`
- `0x180002da0`
- `0x18002e516`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a48`

## pseudocode

```c
signed int __fastcall MakePathCanonicalizationProof(const unsigned __int16 *Src, void **this)
{
  const unsigned __int16 *v3; // rbx
  unsigned int *v4; // rsi
  _WORD *v5; // rcx
  signed int result; // eax
  bool v7; // sf
  __int64 v8; // rbp
  __int64 v9; // rax
  bool v10; // zf
  unsigned int v11; // r14d
  _WORD *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // ecx
  unsigned __int16 v15; // ax
  __int64 v16; // rax
  __int64 v17; // rsi
  _WORD *v18; // rcx
  __int64 v19; // rsi
  signed int LastError; // eax
  unsigned __int64 v21; // rdx
  signed int v22; // eax

  v3 = Src;
  if ( *(_DWORD *)Src == 6029404 )
  {
    v15 = Src[2];
    if ( (v15 == 63 || v15 == 46) && Src[3] == 92 )
    {
      v16 = -1;
      do
        v10 = Src[++v16] == 0;
      while ( !v10 );
      v17 = (unsigned int)(2 * v16);
      if ( *((unsigned int *)this + 10) >= (unsigned __int64)(v17 + 2) )
        goto LABEL_19;
      if ( (unsigned __int64)(v17 + 128) > 0xFFFFFFFF )
        return -2147024362;
      if ( BUFFER::Resize((BUFFER *)this, v17 + 128) )
      {
LABEL_19:
        memcpy_0(this[4], v3, (unsigned int)v17);
        v18 = this[4];
        v19 = (unsigned int)v17 >> 1;
        *((_DWORD *)this + 12) = v19;
        v18[v19] = 0;
        v14 = 0;
      }
      else
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        if ( v14 < 0 )
          return v14;
      }
      *((_WORD *)this[4] + 2) = 63;
      return v14;
    }
    result = STRU::Copy((STRU *)this, L"\\\\?\\UNC\\");
    if ( result < 0 )
      return result;
    v4 = (unsigned int *)(this + 5);
    v3 += 2;
LABEL_8:
    v8 = (unsigned int)(2 * *((_DWORD *)this + 12));
    v9 = -1;
    do
      v10 = v3[++v9] == 0;
    while ( !v10 );
    v11 = 2 * v9;
    if ( *v4 < (unsigned __int64)(unsigned int)(2 * v9) + v8 + 2 )
    {
      v21 = v11 + v8 + 128;
      if ( v21 > 0xFFFFFFFF )
        return -2147024362;
      if ( !BUFFER::Resize((BUFFER *)this, v21) )
      {
        v22 = GetLastError();
        v14 = v22;
        if ( v22 > 0 )
          return (unsigned __int16)v22 | 0x80070000;
        return v14;
      }
    }
    memcpy_0((char *)this[4] + (unsigned int)v8, v3, v11);
    v12 = this[4];
    v13 = (v11 + (unsigned int)v8) >> 1;
    *((_DWORD *)this + 12) = v13;
    v12[v13] = 0;
    return 0;
  }
  v4 = (unsigned int *)(this + 5);
  if ( *((_DWORD *)this + 10) >= 0xAu || BUFFER::Resize((BUFFER *)this, 0x88u) )
  {
    *(_QWORD *)this[4] = 0x5C003F005C005CLL;
    v5 = this[4];
    *((_DWORD *)this + 12) = 4;
    v5[4] = 0;
    goto LABEL_8;
  }
  result = GetLastError();
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( !v7 )
    goto LABEL_8;
  return result;
}

```

## disassembly

```asm
0x180002860  mov     [rsp+arg_10], rbx
0x180002865  mov     [rsp+arg_18], rbp
0x18000286a  push    rsi
0x18000286b  push    rdi
0x18000286c  push    r14
0x18000286e  sub     rsp, 20h
0x180002872  cmp     word ptr [rcx], 5Ch ; '\'
0x180002876  mov     rdi, rdx
0x180002879  mov     rbx, rcx
0x18000287c  jz      loc_180002963
0x180002882  cmp     dword ptr [rdx+28h], 0Ah
0x180002886  lea     rsi, [rdx+28h]
0x18000288a  jb      short loc_1800028B0
0x18000288c  mov     rax, [rdi+20h]
0x180002890  mov     rcx, 5C003F005C005Ch
0x18000289a  mov     [rax], rcx
0x18000289d  xor     eax, eax
0x18000289f  mov     rcx, [rdi+20h]
0x1800028a3  mov     dword ptr [rdi+30h], 4
0x1800028aa  mov     [rcx+8], ax
0x1800028ae  jmp     short loc_1800028DD
0x1800028b0  mov     edx, 88h; unsigned int
0x1800028b5  mov     rcx, rdi; this
0x1800028b8  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800028bd  test    al, al
0x1800028bf  jnz     short loc_18000288C
0x1800028c1  call    cs:__imp_GetLastError
0x1800028c8  nop     dword ptr [rax+rax+00h]
0x1800028cd  test    eax, eax
0x1800028cf  jle     short loc_1800028DB
0x1800028d1  movzx   eax, ax
0x1800028d4  or      eax, 80070000h
0x1800028d9  test    eax, eax
0x1800028db  js      short loc_18000294F
0x1800028dd  mov     eax, [rdi+30h]
0x1800028e0  mov     [rsp+38h+arg_0], r12
0x1800028e5  mov     [rsp+38h+arg_8], r15
0x1800028ea  lea     ebp, [rax+rax]
0x1800028ed  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800028f4  cmp     word ptr [rbx+rax*2+2], 0
0x1800028fa  lea     rax, [rax+1]
0x1800028fe  jnz     short loc_1800028F4
0x180002900  lea     r14d, [rax+rax]
0x180002904  mov     r15d, ebp
0x180002907  mov     eax, [rsi]
0x180002909  lea     rcx, [rbp+2]
0x18000290d  mov     r12d, r14d
0x180002910  add     rcx, r12
0x180002913  cmp     rax, rcx
0x180002916  jb      loc_180002A24
0x18000291c  mov     rcx, [rdi+20h]
0x180002920  mov     r8, r12; Size
0x180002923  add     rcx, r15; void *
0x180002926  mov     rdx, rbx; Src
0x180002929  call    memcpy_0
0x18000292e  mov     rcx, [rdi+20h]
0x180002932  lea     edx, [r14+rbp]
0x180002936  shr     edx, 1
0x180002938  xor     eax, eax
0x18000293a  mov     [rdi+30h], edx
0x18000293d  mov     [rcx+rdx*2], ax
0x180002941  xor     ecx, ecx
0x180002943  mov     r15, [rsp+38h+arg_8]
0x180002948  mov     r12, [rsp+38h+arg_0]
0x18000294d  mov     eax, ecx
0x18000294f  mov     rbx, [rsp+38h+arg_10]
0x180002954  mov     rbp, [rsp+38h+arg_18]
0x180002959  add     rsp, 20h
0x18000295d  pop     r14
0x18000295f  pop     rdi
0x180002960  pop     rsi
0x180002961  retn
0x180002963  cmp     word ptr [rcx+2], 5Ch ; '\'
0x180002968  jnz     loc_180002882
0x18000296e  movzx   eax, word ptr [rcx+4]
0x180002972  cmp     ax, 3Fh ; '?'
0x180002976  jnz     loc_180002A6C
0x18000297c  cmp     word ptr [rcx+6], 5Ch ; '\'
0x180002981  jnz     loc_180002A76
0x180002987  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000298e  xchg    ax, ax
0x180002990  cmp     word ptr [rcx+rax*2+2], 0
0x180002996  lea     rax, [rax+1]
0x18000299a  jnz     short loc_180002990
0x18000299c  mov     ecx, [rdx+28h]
0x18000299f  lea     esi, [rax+rax]
0x1800029a2  lea     rax, [rsi+2]
0x1800029a6  mov     ebp, esi
0x1800029a8  cmp     rcx, rax
0x1800029ab  jb      short loc_1800029D1
0x1800029ad  mov     rcx, [rdi+20h]; void *
0x1800029b1  mov     r8, rbp; Size
0x1800029b4  mov     rdx, rbx; Src
0x1800029b7  call    memcpy_0
0x1800029bc  mov     rcx, [rdi+20h]
0x1800029c0  xor     eax, eax
0x1800029c2  shr     esi, 1
0x1800029c4  mov     edx, esi
0x1800029c6  mov     [rdi+30h], edx
0x1800029c9  mov     [rcx+rsi*2], ax
0x1800029cd  xor     ecx, ecx
0x1800029cf  jmp     short loc_180002A15
0x1800029d1  lea     rdx, [rsi+80h]; unsigned int
0x1800029d8  mov     eax, 0FFFFFFFFh
0x1800029dd  cmp     rdx, rax
0x1800029e0  ja      loc_180002AA4
0x1800029e6  mov     rcx, rdi; this
0x1800029e9  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800029ee  test    al, al
0x1800029f0  jnz     short loc_1800029AD
0x1800029f2  call    cs:__imp_GetLastError
0x1800029f9  nop     dword ptr [rax+rax+00h]
0x1800029fe  mov     ecx, eax
0x180002a00  test    eax, eax
0x180002a02  jle     short loc_180002A0D
0x180002a04  movzx   ecx, ax
0x180002a07  or      ecx, 80070000h
0x180002a0d  test    ecx, ecx
0x180002a0f  js      loc_18000294D
0x180002a15  mov     rax, [rdi+20h]
0x180002a19  mov     word ptr [rax+4], 3Fh ; '?'
0x180002a1f  jmp     loc_18000294D
0x180002a24  lea     rdx, [rbp+80h]
0x180002a2b  mov     eax, 0FFFFFFFFh
0x180002a30  add     rdx, r12; unsigned int
0x180002a33  cmp     rdx, rax
0x180002a36  ja      short loc_180002A9A
0x180002a38  mov     rcx, rdi; this
0x180002a3b  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180002a40  test    al, al
0x180002a42  jnz     loc_18000291C
0x180002a48  call    cs:__imp_GetLastError
0x180002a4f  nop     dword ptr [rax+rax+00h]
0x180002a54  mov     ecx, eax
0x180002a56  test    eax, eax
0x180002a58  jle     loc_180002943
0x180002a5e  movzx   ecx, ax
0x180002a61  or      ecx, 80070000h
0x180002a67  jmp     loc_180002943
0x180002a6c  cmp     ax, 2Eh ; '.'
0x180002a70  jz      loc_18000297C
0x180002a76  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x180002a7d  mov     rcx, rdi; this
0x180002a80  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002a85  test    eax, eax
0x180002a87  js      loc_18000294F
0x180002a8d  lea     rsi, [rdi+28h]
0x180002a91  add     rbx, 4
0x180002a95  jmp     loc_1800028DD
0x180002a9a  mov     ecx, 80070216h
0x180002a9f  jmp     loc_180002943
0x180002aa4  mov     ecx, 80070216h
0x180002aa9  jmp     loc_18000294D
```

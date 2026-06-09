# CPersistErrorCache::GetErrorDescription(long,ulong)

- ea: `0x180016764`
- end: `0x180016b57`
- name: `?GetErrorDescription@CPersistErrorCache@@AEAAPEAGJK@Z`
- size: `1011`
- prototype: `unsigned __int16 *(CPersistErrorCache *__hidden this, int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180016128`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x1800028b8`
- `0x180016764`
- `0x180016d94`
- `0x180016e0c`
- `0x180017244`
- `0x18001b008`
- `0x18002dca4`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001694a`
- `msvcrt!wcsstr` at `0x18001694a`

## pseudocode

```c
unsigned __int8 *__fastcall CPersistErrorCache::GetErrorDescription(CPersistErrorCache *this, unsigned int a2, UINT a3)
{
  UINT v3; // ebx
  CPersistErrorCache *v4; // r14
  unsigned __int8 *v5; // rsi
  unsigned int v6; // edx
  CPersistErrorCache *v7; // rcx
  unsigned __int8 *v8; // r15
  CPersistErrorCache *v9; // rcx
  wchar_t *v10; // r13
  unsigned int v11; // r12d
  __int64 v12; // rbx
  wchar_t *v13; // rax
  wchar_t *v14; // r14
  __int64 v15; // rcx
  __int64 v16; // r9
  int v17; // eax
  int v18; // r14d
  unsigned __int16 *v19; // r8
  __int64 v20; // rax
  unsigned int v21; // ebx
  unsigned int v23; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int8 *v24; // [rsp+38h] [rbp-50h]
  unsigned __int8 *v25; // [rsp+40h] [rbp-48h]
  unsigned int v27; // [rsp+A0h] [rbp+18h] BYREF
  unsigned int v28; // [rsp+A8h] [rbp+20h] BYREF

  v3 = a3;
  v4 = this;
  if ( !a3 )
  {
    switch ( a2 )
    {
      case 0x80040E00:
        v3 = 113;
        break;
      case 0x80040E21:
        v3 = 114;
        break;
      case 0x80040E55:
        v3 = 115;
        break;
      case 0x80040E5C:
        v3 = 116;
        break;
      case 0x80040E23:
        v3 = 117;
        break;
      case 0x80040E24:
        v3 = 118;
        break;
      case 0x80040E25:
        v3 = 119;
        break;
      case 0x80040E04:
        v3 = 120;
        break;
      case 0x80040E35:
        v3 = 121;
        break;
      case 0x80040E07:
        v3 = 122;
        break;
      case 0x80040E22:
        v3 = 123;
        break;
      case 0x80040E37:
        v3 = 124;
        break;
      case 0x80070057:
        v3 = 125;
        break;
      case 0x80004001:
        v3 = 127;
        break;
      case 0x80030103:
        v3 = 129;
        break;
      case 0x80030002:
        v3 = 130;
        break;
      case 0x40EC6u:
        v3 = 131;
        break;
      case 0x40EC0u:
        v3 = 132;
        break;
      case 0x80004005:
        v3 = 135;
        break;
      default:
        return 0;
    }
  }
  v24 = 0;
  v5 = MMMAlloc(0x800u, a2);
  v25 = v5;
  OnNullThrowOOM(v5);
  try
  {
    *((_WORD *)v5 + 1023) = 0;
    if ( !*((_DWORD *)v4 + 4) )
    {
      CPersistErrorCache::LoadDescription(v7, v3, (unsigned __int16 *)v5);
      return v5;
    }
    v8 = MMMAlloc(0x800u, v6);
    v24 = v8;
    OnNullThrowOOM(v8);
    CPersistErrorCache::LoadDescription(v9, v3, (unsigned __int16 *)v8);
    v27 = 0;
    v10 = (wchar_t *)v8;
    v11 = 0;
    v12 = -1;
    while ( v11 < *((_DWORD *)v4 + 4) )
    {
      v13 = wcsstr(v10, L"%p%");
      v14 = v13;
      if ( !v13 )
        break;
      v28 = v13 - v10;
      InsertString(&v28, &v27, v10, (unsigned __int16 *)v5);
      v10 = v14 + 3;
      LODWORD(v15) = v27;
      if ( v27 >= 0x3FF )
        break;
      v4 = this;
      v16 = *((_QWORD *)this + 3);
      if ( *(_WORD *)(v16 + 24LL * v11) == 19 )
      {
        v17 = StringCchPrintfW(
                (unsigned __int16 *)&v5[2 * v27],
                1024 - v27,
                L"%u",
                *(unsigned int *)(v16 + 24LL * v11 + 8));
        v18 = v17;
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049A18[0] )
            bidTraceW(off_1800491E8[0], 681984, off_180049A18[0], (unsigned int)v17, 666);
          ThrowHR(v18);
        }
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v5[2 * v15] );
        v27 = v15;
        v4 = this;
      }
      else
      {
        if ( *(_WORD *)(v16 + 24LL * v11) == 8 )
        {
          v19 = *(unsigned __int16 **)(v16 + 24LL * v11 + 8);
          if ( !v19 )
            goto LABEL_63;
          v20 = -1;
          do
            ++v20;
          while ( v19[v20] );
          v28 = v20;
        }
        else
        {
          v28 = 3;
          v19 = L"???";
        }
        InsertString(&v28, &v27, v19, (unsigned __int16 *)v5);
        LODWORD(v15) = v27;
      }
LABEL_63:
      if ( (unsigned int)v15 >= 0x3FF )
        goto LABEL_65;
      ++v11;
    }
    do
LABEL_65:
      ++v12;
    while ( v10[v12] );
    v28 = v12;
    InsertString(&v28, &v27, v10, (unsigned __int16 *)v5);
    *(_WORD *)&v5[2 * v27] = 0;
    operator delete(v8);
  }
  catch ( long v23 )
  {
    v27 = v23;
    operator delete(v25);
    if ( v24 )
      operator delete(v24);
    v21 = v27;
    if ( (v27 & 0x80000000) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049A10[0] )
          bidTraceW(off_1800491E8[0], 740352, off_180049A10[0], v27, 723);
      }
      ThrowHR(v21);
    }
    return v25;
  }
  return v5;
}

```

## disassembly

```asm
0x180016764  mov     [rsp+arg_0], rcx
0x180016769  push    rbx
0x18001676a  push    rsi
0x18001676b  push    rdi
0x18001676c  push    r12
0x18001676e  push    r13
0x180016770  push    r14
0x180016772  push    r15
0x180016774  sub     rsp, 50h
0x180016778  mov     ebx, r8d
0x18001677b  mov     r14, rcx
0x18001677e  xor     edi, edi
0x180016780  test    r8d, r8d
0x180016783  jnz     loc_1800168C4
0x180016789  cmp     edx, 80040E00h
0x18001678f  jnz     short loc_180016799
0x180016791  lea     ebx, [rdi+71h]
0x180016794  jmp     loc_1800168C4
0x180016799  cmp     edx, 80040E21h
0x18001679f  jnz     short loc_1800167AB
0x1800167a1  mov     ebx, 72h ; 'r'
0x1800167a6  jmp     loc_1800168C4
0x1800167ab  cmp     edx, 80040E55h
0x1800167b1  jnz     short loc_1800167BD
0x1800167b3  mov     ebx, 73h ; 's'
0x1800167b8  jmp     loc_1800168C4
0x1800167bd  cmp     edx, 80040E5Ch
0x1800167c3  jnz     short loc_1800167CF
0x1800167c5  mov     ebx, 74h ; 't'
0x1800167ca  jmp     loc_1800168C4
0x1800167cf  cmp     edx, 80040E23h
0x1800167d5  jnz     short loc_1800167E1
0x1800167d7  mov     ebx, 75h ; 'u'
0x1800167dc  jmp     loc_1800168C4
0x1800167e1  cmp     edx, 80040E24h
0x1800167e7  jnz     short loc_1800167F3
0x1800167e9  mov     ebx, 76h ; 'v'
0x1800167ee  jmp     loc_1800168C4
0x1800167f3  cmp     edx, 80040E25h
0x1800167f9  jnz     short loc_180016805
0x1800167fb  mov     ebx, 77h ; 'w'
0x180016800  jmp     loc_1800168C4
0x180016805  cmp     edx, 80040E04h
0x18001680b  jnz     short loc_180016817
0x18001680d  mov     ebx, 78h ; 'x'
0x180016812  jmp     loc_1800168C4
0x180016817  cmp     edx, 80040E35h
0x18001681d  jnz     short loc_180016829
0x18001681f  mov     ebx, 79h ; 'y'
0x180016824  jmp     loc_1800168C4
0x180016829  cmp     edx, 80040E07h
0x18001682f  jnz     short loc_18001683B
0x180016831  mov     ebx, 7Ah ; 'z'
0x180016836  jmp     loc_1800168C4
0x18001683b  cmp     edx, 80040E22h
0x180016841  jnz     short loc_18001684A
0x180016843  mov     ebx, 7Bh ; '{'
0x180016848  jmp     short loc_1800168C4
0x18001684a  cmp     edx, 80040E37h
0x180016850  jnz     short loc_180016859
0x180016852  mov     ebx, 7Ch ; '|'
0x180016857  jmp     short loc_1800168C4
0x180016859  cmp     edx, 80070057h
0x18001685f  jnz     short loc_180016868
0x180016861  mov     ebx, 7Dh ; '}'
0x180016866  jmp     short loc_1800168C4
0x180016868  cmp     edx, 80004001h
0x18001686e  jnz     short loc_180016877
0x180016870  mov     ebx, 7Fh
0x180016875  jmp     short loc_1800168C4
0x180016877  cmp     edx, 80030103h
0x18001687d  jnz     short loc_180016886
0x18001687f  mov     ebx, 81h
0x180016884  jmp     short loc_1800168C4
0x180016886  cmp     edx, 80030002h
0x18001688c  jnz     short loc_180016895
0x18001688e  mov     ebx, 82h
0x180016893  jmp     short loc_1800168C4
0x180016895  cmp     edx, 40EC6h
0x18001689b  jnz     short loc_1800168A4
0x18001689d  mov     ebx, 83h
0x1800168a2  jmp     short loc_1800168C4
0x1800168a4  cmp     edx, 40EC0h
0x1800168aa  jnz     short loc_1800168B3
0x1800168ac  mov     ebx, 84h
0x1800168b1  jmp     short loc_1800168C4
0x1800168b3  cmp     edx, 80004005h
0x1800168b9  jnz     loc_180016B44
0x1800168bf  mov     ebx, 87h
0x1800168c4  mov     [rsp+88h+var_50], rdi
0x1800168c9  mov     r15d, 800h
0x1800168cf  mov     ecx, r15d; unsigned int
0x1800168d2  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800168d7  mov     rsi, rax
0x1800168da  mov     [rsp+88h+var_48], rax
0x1800168df  mov     rcx, rax; void *
0x1800168e2  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800168e7  mov     [rsi+7FEh], di
0x1800168ee  cmp     [r14+10h], edi
0x1800168f2  jnz     short loc_180016903
0x1800168f4  mov     r8, rsi; unsigned __int16 *
0x1800168f7  mov     edx, ebx; unsigned int
0x1800168f9  call    ?LoadDescription@CPersistErrorCache@@AEAAXKPEAGK@Z; CPersistErrorCache::LoadDescription(ulong,ushort *,ulong)
0x1800168fe  jmp     loc_180016AED
0x180016903  mov     ecx, r15d; unsigned int
0x180016906  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001690b  mov     r15, rax
0x18001690e  mov     [rsp+88h+var_50], rax
0x180016913  mov     rcx, rax; void *
0x180016916  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18001691b  mov     r8, r15; unsigned __int16 *
0x18001691e  mov     edx, ebx; unsigned int
0x180016920  call    ?LoadDescription@CPersistErrorCache@@AEAAXKPEAGK@Z; CPersistErrorCache::LoadDescription(ulong,ushort *,ulong)
0x180016925  mov     [rsp+88h+arg_10], edi
0x18001692c  mov     r13, r15
0x18001692f  mov     r12d, edi
0x180016932  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016936  cmp     r12d, [r14+10h]
0x18001693a  jnb     loc_180016AAC
0x180016940  lea     rdx, aP; "%p%"
0x180016947  mov     rcx, r13; Str
0x18001694a  call    cs:__imp_wcsstr
0x180016951  nop     dword ptr [rax+rax+00h]
0x180016956  mov     r14, rax
0x180016959  test    rax, rax
0x18001695c  jz      loc_180016AAC
0x180016962  mov     rcx, rax
0x180016965  sub     rcx, r13
0x180016968  sar     rcx, 1
0x18001696b  mov     [rsp+88h+arg_18], ecx
0x180016972  mov     r9, rsi; unsigned __int16 *
0x180016975  mov     r8, r13; unsigned __int16 *
0x180016978  lea     rdx, [rsp+88h+arg_10]; unsigned int *
0x180016980  lea     rcx, [rsp+88h+arg_18]; unsigned int *
0x180016988  call    ?InsertString@@YAXPEAK0PEAG1@Z; InsertString(ulong *,ulong *,ushort *,ushort *)
0x18001698d  lea     r13, [r14+6]
0x180016991  mov     ecx, [rsp+88h+arg_10]
0x180016998  cmp     ecx, 3FFh
0x18001699e  jnb     loc_180016AAC
0x1800169a4  mov     eax, r12d
0x1800169a7  lea     r8, [rax+rax*2]
0x1800169ab  mov     r14, [rsp+88h+arg_0]
0x1800169b3  mov     r9, [r14+18h]
0x1800169b7  cmp     word ptr [r9+r8*8], 13h
0x1800169bd  jnz     loc_180016A43
0x1800169c3  mov     edx, 400h
0x1800169c8  sub     edx, ecx; unsigned __int64
0x1800169ca  lea     rcx, [rsi+rcx*2]; unsigned __int16 *
0x1800169ce  mov     r9d, [r9+r8*8+8]
0x1800169d3  lea     r8, aU; "%u"
0x1800169da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800169df  mov     r14d, eax
0x1800169e2  test    eax, eax
0x1800169e4  jns     short loc_180016A26
0x1800169e6  test    byte ptr cs:_bidGblFlags, 2
0x1800169ed  jz      short loc_180016A1E
0x1800169ef  mov     rcx, cs:off_180049A18; "<CPersistErrorCache::GetErrorDescriptio"...
0x1800169f6  test    rcx, rcx
0x1800169f9  jz      short loc_180016A1E
0x1800169fb  mov     [rsp+88h+var_68], 29Ah
0x180016a03  mov     r9d, eax
0x180016a06  mov     r8, cs:off_180049A18; "<CPersistErrorCache::GetErrorDescriptio"...
0x180016a0d  mov     edx, 0A6800h
0x180016a12  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180016a19  call    _bidTraceW
0x180016a1e  mov     ecx, r14d; int
0x180016a21  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016a26  mov     rcx, rbx
0x180016a29  inc     rcx
0x180016a2c  cmp     [rsi+rcx*2], di
0x180016a30  jnz     short loc_180016A29
0x180016a32  mov     [rsp+88h+arg_10], ecx
0x180016a39  mov     r14, [rsp+88h+arg_0]
0x180016a41  jmp     short loc_180016A9C
0x180016a43  cmp     word ptr [r9+r8*8], 8
0x180016a49  jnz     short loc_180016A6B
0x180016a4b  mov     r8, [r9+r8*8+8]
0x180016a50  test    r8, r8
0x180016a53  jz      short loc_180016A9C
0x180016a55  mov     rax, rbx
0x180016a58  inc     rax
0x180016a5b  cmp     [r8+rax*2], di
0x180016a60  jnz     short loc_180016A58
0x180016a62  mov     [rsp+88h+arg_18], eax
0x180016a69  jmp     short loc_180016A7D
0x180016a6b  mov     [rsp+88h+arg_18], 3
0x180016a76  lea     r8, asc_1800398A0; "???"
0x180016a7d  mov     r9, rsi; unsigned __int16 *
0x180016a80  lea     rdx, [rsp+88h+arg_10]; unsigned int *
0x180016a88  lea     rcx, [rsp+88h+arg_18]; unsigned int *
0x180016a90  call    ?InsertString@@YAXPEAK0PEAG1@Z; InsertString(ulong *,ulong *,ushort *,ushort *)
0x180016a95  mov     ecx, [rsp+88h+arg_10]
0x180016a9c  cmp     ecx, 3FFh
0x180016aa2  jnb     short loc_180016AAC
0x180016aa4  inc     r12d
0x180016aa7  jmp     loc_180016936
0x180016aac  inc     rbx
0x180016aaf  cmp     [r13+rbx*2+0], di
0x180016ab5  jnz     short loc_180016AAC
0x180016ab7  mov     [rsp+88h+arg_18], ebx
0x180016abe  mov     r9, rsi; unsigned __int16 *
0x180016ac1  mov     r8, r13; unsigned __int16 *
0x180016ac4  lea     rdx, [rsp+88h+arg_10]; unsigned int *
0x180016acc  lea     rcx, [rsp+88h+arg_18]; unsigned int *
0x180016ad4  call    ?InsertString@@YAXPEAK0PEAG1@Z; InsertString(ulong *,ulong *,ushort *,ushort *)
0x180016ad9  mov     eax, [rsp+88h+arg_10]
0x180016ae0  mov     [rsi+rax*2], di
0x180016ae4  mov     rcx, r15; void *
0x180016ae7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016aec  nop
0x180016aed  jmp     short loc_180016B3F
0x180016aef  mov     ebx, [rsp+88h+arg_10]
0x180016af6  test    ebx, ebx
0x180016af8  jns     short loc_180016B3A
0x180016afa  test    byte ptr cs:_bidGblFlags, 2
0x180016b01  jz      short loc_180016B32
0x180016b03  mov     rax, cs:off_180049A10; "<CPersistErrorCache::GetErrorDescriptio"...
0x180016b0a  test    rax, rax
0x180016b0d  jz      short loc_180016B32
0x180016b0f  mov     [rsp+88h+var_68], 2D3h
0x180016b17  mov     r9d, ebx
0x180016b1a  mov     r8, cs:off_180049A10; "<CPersistErrorCache::GetErrorDescriptio"...
0x180016b21  mov     edx, 0B4C00h
0x180016b26  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180016b2d  call    _bidTraceW
0x180016b32  mov     ecx, ebx; int
0x180016b34  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016b3a  mov     rsi, [rsp+88h+var_48]
0x180016b3f  mov     rax, rsi
0x180016b42  jmp     short loc_180016B46
0x180016b44  xor     eax, eax
0x180016b46  add     rsp, 50h
0x180016b4a  pop     r15
0x180016b4c  pop     r14
0x180016b4e  pop     r13
0x180016b50  pop     r12
0x180016b52  pop     rdi
0x180016b53  pop     rsi
0x180016b54  pop     rbx
0x180016b55  retn
```

# CScrubDatabase::EnumerateParityExtent__lambda_aa501a9b46ced6b1573e39e3b88c65e4___

- ea: `0x18001b600`
- end: `0x18001b875`
- name: `CScrubDatabase::EnumerateParityExtent__lambda_aa501a9b46ced6b1573e39e3b88c65e4___`
- size: `629`
- prototype: `__int64 __fastcall(CScrubDatabase *this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001e49c`

## callees

- `0x1800032f8`
- `0x180006470`
- `0x180006498`
- `0x180006688`
- `0x18001b600`
- `0x18001c5a0`
- `0x18002f9e0`
- `0x180037620`

## import_xrefs

- `ESENT!JetMove` at `0x18001b6dd`
- `ESENT!JetMove` at `0x18001b7a9`
- `ESENT!JetMove` at `0x18001b6dd`
- `ESENT!JetMove` at `0x18001b7a9`

## pseudocode

```c
__int64 __fastcall CScrubDatabase::EnumerateParityExtent__lambda_aa501a9b46ced6b1573e39e3b88c65e4___(
        CScrubDatabase *this,
        __int64 a2)
{
  USHORT Length; // cx
  __int64 v5; // r9
  USHORT v6; // dx
  USHORT v7; // ax
  JET_ERR v8; // edi
  unsigned int v9; // r8d
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // eax
  JET_ERR v15; // eax
  int ColumnData; // eax
  unsigned int v17; // edi
  const char *v19; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-28h]
  __int128 v21; // [rsp+40h] [rbp-20h] BYREF

  Length = GlobalIndentString.Length;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v19 = "CScrubDatabase::EnumerateParityExtent";
  v6 = ++*(_WORD *)(v5 + 8);
  *(_QWORD *)(v5 + 16) = "CScrubDatabase::EnumerateParityExtent";
  v7 = Length;
  if ( v6 < Length )
  {
    v7 = v6;
    Length = v6;
  }
  LOWORD(v21) = v7;
  DWORD1(v21) = 0;
  *((_QWORD *)&v21 + 1) = off_180047060;
  WORD1(v21) = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubDatabase::EnumerateParityExtent");
  }
  v8 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0x80000000, 0);
  if ( v8 == -1603 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fcda475cc64433d0b54588bf90bf355f_Traceguids);
    }
    v10 = 0;
  }
  else
  {
    v10 = 0;
    if ( v8 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 11;
LABEL_18:
        WPP_SF_d(v11[2], v12, WPP_fcda475cc64433d0b54588bf90bf355f_Traceguids, (unsigned int)v8);
      }
    }
    else
    {
      do
      {
        v21 = 0;
        ColumnData = CScrubDatabase::RetrieveColumnData(this, (struct _SCRUB_PARITY_EXTENT *)&v21, v9);
        v20 = ColumnData;
        v17 = ColumnData;
        if ( ColumnData < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              WPP_fcda475cc64433d0b54588bf90bf355f_Traceguids,
              (unsigned int)ColumnData);
          }
          CHResultImp::~CHResultImp((CHResultImp *)&v19);
          return v17;
        }
        v14 = lambda_aa501a9b46ced6b1573e39e3b88c65e4_::operator()(a2, &v21);
        v20 = v14;
        if ( v14 )
        {
          v10 = v14;
          goto LABEL_39;
        }
        v15 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
        v8 = v15;
        if ( v15 == -1603 )
          goto LABEL_24;
      }
      while ( !v15 );
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 13;
        goto LABEL_18;
      }
    }
    if ( v8 == -1011 )
    {
      v10 = -2147024882;
    }
    else
    {
      v13 = -v8;
      if ( v8 > 0 )
        LOWORD(v13) = v8;
      v10 = v8 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
    }
  }
LABEL_24:
  v20 = v10;
LABEL_39:
  CHResultImp::~CHResultImp((CHResultImp *)&v19);
  return v10;
}

```

## disassembly

```asm
0x18001b600  mov     [rsp-28h+arg_10], rbx
0x18001b605  mov     [rsp-28h+arg_18], rsi
0x18001b60a  push    rbp
0x18001b60b  push    rdi
0x18001b60c  push    r12
0x18001b60e  push    r14
0x18001b610  push    r15
0x18001b612  mov     rbp, rsp
0x18001b615  sub     rsp, 60h
0x18001b619  mov     rax, cs:__security_cookie
0x18001b620  xor     rax, rsp
0x18001b623  mov     [rbp+var_10], rax
0x18001b627  mov     r8d, cs:_tls_index
0x18001b62e  mov     r14, rdx
0x18001b631  mov     rax, gs:58h
0x18001b63a  mov     rsi, rcx
0x18001b63d  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001b644  mov     r15d, 1
0x18001b64a  mov     edx, 8
0x18001b64f  mov     r9, [rax+r8*8]
0x18001b653  lea     r8, aCscrubdatabase_6; "CScrubDatabase::EnumerateParityExtent"
0x18001b65a  mov     eax, 10h
0x18001b65f  mov     [rbp+var_30], r8
0x18001b663  add     [rdx+r9], r15w
0x18001b668  movzx   edx, word ptr [rdx+r9]
0x18001b66d  mov     [rax+r9], r8
0x18001b671  cmp     dx, cx
0x18001b674  movzx   eax, cx
0x18001b677  cmovb   ax, dx
0x18001b67b  cmovb   cx, dx
0x18001b67f  mov     word ptr [rbp+var_20], ax
0x18001b683  xor     eax, eax
0x18001b685  mov     dword ptr [rbp+var_20+4], eax
0x18001b688  mov     rax, cs:off_180047060; "                                       "...
0x18001b68f  mov     qword ptr [rbp+var_20+8], rax
0x18001b693  mov     word ptr [rbp+var_20+2], cx
0x18001b697  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b69e  lea     r12, WPP_GLOBAL_Control
0x18001b6a5  cmp     rcx, r12
0x18001b6a8  jz      short loc_18001B6CC
0x18001b6aa  test    [rcx+1Ch], r15b
0x18001b6ae  jz      short loc_18001B6CC
0x18001b6b0  cmp     byte ptr [rcx+19h], 5
0x18001b6b4  jb      short loc_18001B6CC
0x18001b6b6  mov     rcx, [rcx+10h]; LoggerHandle
0x18001b6ba  lea     edx, [r15+0Ch]
0x18001b6be  lea     r9, [rbp+var_20]
0x18001b6c2  mov     [rsp+60h+var_40], r8; __int64
0x18001b6c7  call    WPP_SF_aZs
0x18001b6cc  mov     rdx, [rsi+18h]; tableid
0x18001b6d0  xor     r9d, r9d; grbit
0x18001b6d3  mov     rcx, [rsi+8]; sesid
0x18001b6d7  mov     r8d, 80000000h; cRow
0x18001b6dd  call    cs:__imp_JetMove
0x18001b6e3  mov     edi, eax
0x18001b6e5  cmp     eax, 0FFFFF9BDh
0x18001b6ea  jnz     short loc_18001B71D
0x18001b6ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6f3  cmp     rcx, r12
0x18001b6f6  jz      short loc_18001B719
0x18001b6f8  test    [rcx+1Ch], r15b
0x18001b6fc  jz      short loc_18001B719
0x18001b6fe  cmp     byte ptr [rcx+19h], 4
0x18001b702  jb      short loc_18001B719
0x18001b704  mov     rcx, [rcx+10h]
0x18001b708  lea     r8, WPP_fcda475cc64433d0b54588bf90bf355f_Traceguids
0x18001b70f  mov     edx, 0Ah
0x18001b714  call    WPP_SF_
0x18001b719  xor     ebx, ebx
0x18001b71b  jmp     short loc_18001B77C
0x18001b71d  xor     ebx, ebx
0x18001b71f  test    edi, edi
0x18001b721  jz      loc_18001B7BC
0x18001b727  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b72e  cmp     rcx, r12
0x18001b731  jz      short loc_18001B755
0x18001b733  test    [rcx+1Ch], r15b
0x18001b737  jz      short loc_18001B755
0x18001b739  cmp     byte ptr [rcx+19h], 2
0x18001b73d  jb      short loc_18001B755
0x18001b73f  lea     edx, [rbx+0Bh]
0x18001b742  mov     rcx, [rcx+10h]
0x18001b746  lea     r8, WPP_fcda475cc64433d0b54588bf90bf355f_Traceguids
0x18001b74d  mov     r9d, edi
0x18001b750  call    WPP_SF_d
0x18001b755  cmp     edi, 0FFFFFC0Dh
0x18001b75b  jnz     short loc_18001B764
0x18001b75d  mov     ebx, 8007000Eh
0x18001b762  jmp     short loc_18001B77C
0x18001b764  mov     eax, edi
0x18001b766  neg     eax
0x18001b768  cmovs   eax, edi
0x18001b76b  and     edi, 8E5E0000h
0x18001b771  movzx   ebx, ax
0x18001b774  or      ebx, edi
0x18001b776  or      ebx, 0E5E0000h
0x18001b77c  mov     [rbp+var_28], ebx
0x18001b77f  jmp     loc_18001B868
0x18001b784  lea     rdx, [rbp+var_20]
0x18001b788  mov     rcx, r14
0x18001b78b  call    _lambda_aa501a9b46ced6b1573e39e3b88c65e4___operator__
0x18001b790  mov     [rbp+var_28], eax
0x18001b793  test    eax, eax
0x18001b795  jnz     loc_18001B866
0x18001b79b  mov     rdx, [rsi+18h]; tableid
0x18001b79f  xor     r9d, r9d; grbit
0x18001b7a2  mov     rcx, [rsi+8]; sesid
0x18001b7a6  mov     r8d, r15d; cRow
0x18001b7a9  call    cs:__imp_JetMove
0x18001b7af  mov     edi, eax
0x18001b7b1  cmp     eax, 0FFFFF9BDh
0x18001b7b6  jz      short loc_18001B77C
0x18001b7b8  test    eax, eax
0x18001b7ba  jnz     short loc_18001B838
0x18001b7bc  xorps   xmm0, xmm0
0x18001b7bf  lea     rdx, [rbp+var_20]; struct _SCRUB_PARITY_EXTENT *
0x18001b7c3  mov     rcx, rsi; this
0x18001b7c6  movups  [rbp+var_20], xmm0
0x18001b7ca  call    ?RetrieveColumnData@CScrubDatabase@@AEAAJPEAU_SCRUB_PARITY_EXTENT@@K@Z; CScrubDatabase::RetrieveColumnData(_SCRUB_PARITY_EXTENT *,ulong)
0x18001b7cf  mov     [rbp+var_28], eax
0x18001b7d2  mov     edi, eax
0x18001b7d4  test    eax, eax
0x18001b7d6  jns     short loc_18001B784
0x18001b7d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7df  cmp     rcx, r12
0x18001b7e2  jz      short loc_18001B808
0x18001b7e4  test    [rcx+1Ch], r15b
0x18001b7e8  jz      short loc_18001B808
0x18001b7ea  cmp     byte ptr [rcx+19h], 2
0x18001b7ee  jb      short loc_18001B808
0x18001b7f0  mov     rcx, [rcx+10h]
0x18001b7f4  lea     r8, WPP_fcda475cc64433d0b54588bf90bf355f_Traceguids
0x18001b7fb  mov     edx, 0Ch
0x18001b800  mov     r9d, eax
0x18001b803  call    WPP_SF_d
0x18001b808  lea     rcx, [rbp+var_30]; this
0x18001b80c  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001b811  mov     eax, edi
0x18001b813  mov     rcx, [rbp+var_10]
0x18001b817  xor     rcx, rsp; StackCookie
0x18001b81a  call    __security_check_cookie
0x18001b81f  lea     r11, [rsp+60h+var_s0]
0x18001b824  mov     rbx, [r11+40h]
0x18001b828  mov     rsi, [r11+48h]
0x18001b82c  mov     rsp, r11
0x18001b82f  pop     r15
0x18001b831  pop     r14
0x18001b833  pop     r12
0x18001b835  pop     rdi
0x18001b836  pop     rbp
0x18001b837  retn
0x18001b838  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b83f  cmp     rcx, r12
0x18001b842  jz      loc_18001B755
0x18001b848  test    [rcx+1Ch], r15b
0x18001b84c  jz      loc_18001B755
0x18001b852  cmp     byte ptr [rcx+19h], 2
0x18001b856  jb      loc_18001B755
0x18001b85c  mov     edx, 0Dh
0x18001b861  jmp     loc_18001B742
0x18001b866  mov     ebx, eax
0x18001b868  lea     rcx, [rbp+var_30]; this
0x18001b86c  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001b871  mov     eax, ebx
0x18001b873  jmp     short loc_18001B813
```

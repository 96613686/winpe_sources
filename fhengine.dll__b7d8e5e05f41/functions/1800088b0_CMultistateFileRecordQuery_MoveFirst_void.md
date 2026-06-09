# CMultistateFileRecordQuery::MoveFirst(void)

- ea: `0x1800088b0`
- end: `0x180008ac0`
- name: `?MoveFirst@CMultistateFileRecordQuery@@QEAAJXZ`
- size: `528`
- prototype: `__int64 __fastcall(CMultistateFileRecordQuery *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008d18`

## callees

- `0x180007818`
- `0x180008078`
- `0x1800088b0`
- `0x18000935c`
- `0x180034010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800089f8`
- `OLEAUT32!__imp_SysFreeString` at `0x180008a94`
- `OLEAUT32!__imp_SysFreeString` at `0x1800089f8`
- `OLEAUT32!__imp_SysFreeString` at `0x180008a94`

## pseudocode

```c
__int64 __fastcall CMultistateFileRecordQuery::MoveFirst(CMultistateFileRecordQuery *this)
{
  unsigned int v2; // ebx
  int i; // r14d
  __int64 v4; // rcx
  __int64 v5; // r9
  int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v10; // [rsp+60h] [rbp-20h] BYREF
  int v11; // [rsp+64h] [rbp-1Ch] BYREF
  int v12; // [rsp+68h] [rbp-18h] BYREF
  int v13; // [rsp+6Ch] [rbp-14h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-10h] BYREF
  __int64 v15; // [rsp+78h] [rbp-8h] BYREF
  __int16 v16; // [rsp+B0h] [rbp+30h] BYREF
  __int16 v17; // [rsp+B8h] [rbp+38h] BYREF
  int v18; // [rsp+C0h] [rbp+40h] BYREF
  int v19; // [rsp+C8h] [rbp+48h] BYREF

  v2 = 0;
  for ( i = 0; i < *((_DWORD *)this + 2); ++i )
  {
    v11 = 0;
    bstrString = 0;
    v10 = 0;
    v19 = 0;
    v17 = 0;
    v16 = 0;
    v15 = 0;
    v13 = 0;
    v18 = 0;
    v12 = 0;
    v4 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v4 + 24LL * i + 8) )
    {
      *(_DWORD *)(v4 + 24LL * i + 12) = 1;
    }
    else
    {
      v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 24LL * i) + 24LL))(*(_QWORD *)(v4 + 24LL * i));
      if ( (v2 & 0x80000000) != 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 29;
LABEL_21:
          WPP_SF_d(v7[2], v8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids, v2);
        }
LABEL_22:
        SysFreeString(bstrString);
        return v2;
      }
      *(_DWORD *)(*((_QWORD *)this + 2) + 24LL * i + 12) = 0;
      v5 = *((unsigned int *)this + 8);
      if ( (_DWORD)v5 )
      {
        if ( (_DWORD)v5 != 1 )
        {
          v2 = -2147418113;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids,
              v5,
              -2147418113);
          goto LABEL_22;
        }
        v6 = (*(__int64 (__fastcall **)(_QWORD, int *, BSTR *, int *, int *, __int16 *, __int16 *, __int64 *, int *, int *, __int64))(**(_QWORD **)(*((_QWORD *)this + 2) + 24LL * i) + 48LL))(
               *(_QWORD *)(*((_QWORD *)this + 2) + 24LL * i),
               &v11,
               &bstrString,
               &v10,
               &v19,
               &v17,
               &v16,
               &v15,
               &v13,
               &v18,
               *((_QWORD *)this + 2) + 24LL * i + 16);
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD, int *, BSTR *, int *, int *, __int16 *, __int16 *, __int64 *, __int64, int *, int *))(**(_QWORD **)(*((_QWORD *)this + 2) + 24LL * i) + 48LL))(
               *(_QWORD *)(*((_QWORD *)this + 2) + 24LL * i),
               &v11,
               &bstrString,
               &v10,
               &v19,
               &v17,
               &v16,
               &v15,
               *((_QWORD *)this + 2) + 16LL + 24LL * i,
               &v18,
               &v12);
      }
      v2 = v6;
      if ( v6 < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 31;
          goto LABEL_21;
        }
        goto LABEL_22;
      }
    }
    SysFreeString(bstrString);
  }
  CMultistateFileRecordQuery::FindCurrentRecord(this);
  if ( *((_DWORD *)this + 7) )
    return (unsigned int)-2147023728;
  return v2;
}

```

## disassembly

```asm
0x1800088b0  push    rbp
0x1800088b2  push    rbx
0x1800088b3  push    rsi
0x1800088b4  push    rdi
0x1800088b5  push    r14
0x1800088b7  mov     rbp, rsp
0x1800088ba  sub     rsp, 80h
0x1800088c1  mov     rdi, rcx
0x1800088c4  xor     ebx, ebx
0x1800088c6  xor     r14d, r14d
0x1800088c9  cmp     r14d, [rdi+8]
0x1800088cd  jge     loc_180008A9C
0x1800088d3  mov     [rbp+var_1C], 0
0x1800088da  mov     [rbp+bstrString], 0
0x1800088e2  mov     [rbp+var_20], 0
0x1800088e9  mov     [rbp+arg_18], 0
0x1800088f0  xor     eax, eax
0x1800088f2  mov     [rbp+arg_8], ax
0x1800088f6  mov     [rbp+arg_0], ax
0x1800088fa  mov     [rbp+var_8], rax
0x1800088fe  mov     [rbp+var_14], eax
0x180008901  mov     [rbp+arg_10], eax
0x180008904  mov     [rbp+var_18], eax
0x180008907  movsxd  rax, r14d
0x18000890a  lea     rsi, [rax+rax*2]
0x18000890e  mov     rcx, [rdi+10h]
0x180008912  cmp     dword ptr [rcx+rsi*8+8], 0
0x180008917  jz      short loc_180008926
0x180008919  mov     dword ptr [rcx+rsi*8+0Ch], 1
0x180008921  jmp     loc_1800089F4
0x180008926  mov     rcx, [rcx+rsi*8]
0x18000892a  mov     rax, [rcx]
0x18000892d  mov     rax, [rax+18h]
0x180008931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008936  mov     ebx, eax
0x180008938  test    eax, eax
0x18000893a  js      loc_180008A5F
0x180008940  mov     rax, [rdi+10h]
0x180008944  mov     dword ptr [rax+rsi*8+0Ch], 0
0x18000894c  mov     r9d, [rdi+20h]
0x180008950  test    r9d, r9d
0x180008953  jnz     short loc_18000897E
0x180008955  mov     rcx, [rdi+10h]
0x180008959  mov     r10, [rcx+rsi*8]
0x18000895d  lea     rdx, [rcx+10h]
0x180008961  lea     rdx, [rdx+rsi*8]
0x180008965  lea     rcx, [rbp+var_18]
0x180008969  mov     [rsp+80h+var_30], rcx
0x18000896e  lea     rcx, [rbp+arg_10]
0x180008972  mov     [rsp+80h+var_38], rcx
0x180008977  mov     [rsp+80h+var_40], rdx
0x18000897c  jmp     short loc_1800089AF
0x18000897e  cmp     r9d, 1
0x180008982  jnz     loc_180008A26
0x180008988  mov     rcx, [rdi+10h]
0x18000898c  mov     r10, [rcx+rsi*8]
0x180008990  lea     rcx, [rcx+rsi*8]
0x180008994  add     rcx, 10h
0x180008998  mov     [rsp+80h+var_30], rcx
0x18000899d  lea     rcx, [rbp+arg_10]
0x1800089a1  mov     [rsp+80h+var_38], rcx
0x1800089a6  lea     rcx, [rbp+var_14]
0x1800089aa  mov     [rsp+80h+var_40], rcx
0x1800089af  lea     rcx, [rbp+var_8]
0x1800089b3  mov     [rsp+80h+var_48], rcx
0x1800089b8  lea     rcx, [rbp+arg_0]
0x1800089bc  mov     [rsp+80h+var_50], rcx
0x1800089c1  lea     rcx, [rbp+arg_8]
0x1800089c5  mov     [rsp+80h+var_58], rcx
0x1800089ca  lea     rcx, [rbp+arg_18]
0x1800089ce  mov     [rsp+80h+var_60], rcx
0x1800089d3  mov     rax, [r10]
0x1800089d6  lea     r9, [rbp+var_20]
0x1800089da  lea     r8, [rbp+bstrString]
0x1800089de  lea     rdx, [rbp+var_1C]
0x1800089e2  mov     rcx, r10
0x1800089e5  mov     rax, [rax+30h]
0x1800089e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089ee  mov     ebx, eax
0x1800089f0  test    eax, eax
0x1800089f2  js      short loc_180008A06
0x1800089f4  mov     rcx, [rbp+bstrString]; bstrString
0x1800089f8  call    cs:__imp_SysFreeString
0x1800089fe  inc     r14d
0x180008a01  jmp     loc_1800088C9
0x180008a06  lea     rax, WPP_GLOBAL_Control
0x180008a0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a14  cmp     rcx, rax
0x180008a17  jz      short loc_180008A90
0x180008a19  test    byte ptr [rcx+1Ch], 1
0x180008a1d  jz      short loc_180008A90
0x180008a1f  mov     edx, 1Fh
0x180008a24  jmp     short loc_180008A7D
0x180008a26  mov     ebx, 8000FFFFh
0x180008a2b  lea     rax, WPP_GLOBAL_Control
0x180008a32  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a39  cmp     rcx, rax
0x180008a3c  jz      short loc_180008A90
0x180008a3e  test    byte ptr [rcx+1Ch], 1
0x180008a42  jz      short loc_180008A90
0x180008a44  mov     edx, 1Eh
0x180008a49  mov     dword ptr [rsp+80h+var_60], ebx
0x180008a4d  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180008a54  mov     rcx, [rcx+10h]
0x180008a58  call    WPP_SF_dd
0x180008a5d  jmp     short loc_180008A90
0x180008a5f  lea     rax, WPP_GLOBAL_Control
0x180008a66  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a6d  cmp     rcx, rax
0x180008a70  jz      short loc_180008A90
0x180008a72  test    byte ptr [rcx+1Ch], 1
0x180008a76  jz      short loc_180008A90
0x180008a78  mov     edx, 1Dh
0x180008a7d  mov     r9d, ebx
0x180008a80  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180008a87  mov     rcx, [rcx+10h]
0x180008a8b  call    WPP_SF_d
0x180008a90  mov     rcx, [rbp+bstrString]; bstrString
0x180008a94  call    cs:__imp_SysFreeString
0x180008a9a  jmp     short loc_180008AB0
0x180008a9c  mov     rcx, rdi; this
0x180008a9f  call    ?FindCurrentRecord@CMultistateFileRecordQuery@@AEAAXXZ; CMultistateFileRecordQuery::FindCurrentRecord(void)
0x180008aa4  mov     eax, 80070490h
0x180008aa9  cmp     dword ptr [rdi+1Ch], 0
0x180008aad  cmovnz  ebx, eax
0x180008ab0  mov     eax, ebx
0x180008ab2  add     rsp, 80h
0x180008ab9  pop     r14
0x180008abb  pop     rdi
0x180008abc  pop     rsi
0x180008abd  pop     rbx
0x180008abe  pop     rbp
0x180008abf  retn
```

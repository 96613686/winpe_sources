# CMultistateFileRecordQuery::MoveNext(void)

- ea: `0x180008ac8`
- end: `0x180008ca5`
- name: `?MoveNext@CMultistateFileRecordQuery@@QEAAJXZ`
- size: `477`
- prototype: `__int64 __fastcall(CMultistateFileRecordQuery *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cafc`
- `0x180012b44`
- `0x18001789c`

## callees

- `0x180007818`
- `0x180008078`
- `0x180008ac8`
- `0x180034010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180008b8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c80`
- `OLEAUT32!__imp_SysFreeString` at `0x180008b8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c80`

## pseudocode

```c
__int64 __fastcall CMultistateFileRecordQuery::MoveNext(CMultistateFileRecordQuery *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rcx
  OLECHAR *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  int v9; // [rsp+60h] [rbp+17h] BYREF
  int v10; // [rsp+64h] [rbp+1Bh] BYREF
  int v11; // [rsp+68h] [rbp+1Fh] BYREF
  int v12; // [rsp+6Ch] [rbp+23h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+27h] BYREF
  _QWORD v14[5]; // [rsp+78h] [rbp+2Fh] BYREF
  __int16 v15; // [rsp+B0h] [rbp+67h] BYREF
  __int16 v16; // [rsp+B8h] [rbp+6Fh] BYREF
  int v17; // [rsp+C0h] [rbp+77h] BYREF
  int v18; // [rsp+C8h] [rbp+7Fh] BYREF

  v2 = 0;
  if ( !*((_DWORD *)this + 7) )
  {
    v3 = *(_QWORD *)(*((_QWORD *)this + 2) + 24LL * *((int *)this + 6));
    v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
    if ( v2 == -2147023728 )
    {
      *(_DWORD *)(*((_QWORD *)this + 2) + 24LL * *((int *)this + 6) + 12) = 1;
      v2 = 0;
      goto LABEL_21;
    }
    v10 = 0;
    v4 = 0;
    bstrString = 0;
    v9 = 0;
    v18 = 0;
    v16 = 0;
    v15 = 0;
    v14[0] = 0;
    v12 = 0;
    v17 = 0;
    v11 = 0;
    if ( (v2 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_10;
      v5 = 33;
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      goto LABEL_8;
    }
    if ( *((_DWORD *)this + 8) )
    {
      if ( *((_DWORD *)this + 8) != 1 )
      {
LABEL_20:
        SysFreeString(v4);
        goto LABEL_21;
      }
      v7 = (*(__int64 (__fastcall **)(_QWORD, int *, BSTR *, int *, int *, __int16 *, __int16 *, _QWORD *, int *, int *, __int64))(**(_QWORD **)(*((_QWORD *)this + 2) + 24LL * *((int *)this + 6)) + 48LL))(
             *(_QWORD *)(*((_QWORD *)this + 2) + 24LL * *((int *)this + 6)),
             &v10,
             &bstrString,
             &v9,
             &v18,
             &v16,
             &v15,
             v14,
             &v12,
             &v17,
             *((_QWORD *)this + 2) + 24LL * *((int *)this + 6) + 16);
    }
    else
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, int *, BSTR *, int *, int *, __int16 *, __int16 *, _QWORD *, __int64, int *, int *))(**(_QWORD **)(*((_QWORD *)this + 2) + 24LL * *((int *)this + 6)) + 48LL))(
             *(_QWORD *)(*((_QWORD *)this + 2) + 24LL * *((int *)this + 6)),
             &v10,
             &bstrString,
             &v9,
             &v18,
             &v16,
             &v15,
             v14,
             *((_QWORD *)this + 2) + 8 * (3LL * *((int *)this + 6) + 2),
             &v17,
             &v11);
    }
    v2 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      v5 = 34;
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_8:
      WPP_SF_d(v6, v5, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids, v2);
LABEL_9:
      v4 = bstrString;
LABEL_10:
      SysFreeString(v4);
      return v2;
    }
    v4 = bstrString;
    goto LABEL_20;
  }
LABEL_21:
  CMultistateFileRecordQuery::FindCurrentRecord(this);
  if ( *((_DWORD *)this + 7) )
    return (unsigned int)-2147023728;
  return v2;
}

```

## disassembly

```asm
0x180008ac8  push    rbp
0x180008aca  push    rbx
0x180008acb  push    rdi
0x180008acc  push    r14
0x180008ace  lea     rbp, [rsp-3Fh]
0x180008ad3  sub     rsp, 88h
0x180008ada  mov     rdi, rcx
0x180008add  xor     ebx, ebx
0x180008adf  mov     r14d, 80070490h
0x180008ae5  cmp     [rcx+1Ch], ebx
0x180008ae8  jnz     loc_180008C86
0x180008aee  movsxd  rax, dword ptr [rcx+18h]
0x180008af2  lea     rdx, [rax+rax*2]
0x180008af6  mov     rax, [rcx+10h]
0x180008afa  mov     rcx, [rax+rdx*8]
0x180008afe  mov     rax, [rcx]
0x180008b01  mov     rax, [rax+20h]
0x180008b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b0a  mov     ebx, eax
0x180008b0c  cmp     eax, r14d
0x180008b0f  jnz     short loc_180008B2C
0x180008b11  movsxd  rax, dword ptr [rdi+18h]
0x180008b15  lea     rcx, [rax+rax*2]
0x180008b19  mov     rax, [rdi+10h]
0x180008b1d  mov     dword ptr [rax+rcx*8+0Ch], 1
0x180008b25  xor     ebx, ebx
0x180008b27  jmp     loc_180008C86
0x180008b2c  mov     [rbp+57h+var_3C], 0
0x180008b33  xor     ecx, ecx
0x180008b35  mov     [rbp+57h+bstrString], rcx
0x180008b39  mov     [rbp+57h+var_40], ecx
0x180008b3c  mov     [rbp+57h+arg_18], ecx
0x180008b3f  xor     eax, eax
0x180008b41  mov     [rbp+57h+arg_8], ax
0x180008b45  mov     [rbp+57h+arg_0], ax
0x180008b49  mov     [rbp+57h+var_28], rax
0x180008b4d  mov     [rbp+57h+var_34], eax
0x180008b50  mov     [rbp+57h+arg_10], eax
0x180008b53  mov     [rbp+57h+var_38], eax
0x180008b56  test    ebx, ebx
0x180008b58  jns     short loc_180008B99
0x180008b5a  lea     rax, WPP_GLOBAL_Control
0x180008b61  mov     r10, cs:WPP_GLOBAL_Control
0x180008b68  cmp     r10, rax
0x180008b6b  jz      short loc_180008B8E
0x180008b6d  test    byte ptr [r10+1Ch], 1
0x180008b72  jz      short loc_180008B8E
0x180008b74  lea     edx, [rcx+21h]
0x180008b77  mov     rcx, [r10+10h]
0x180008b7b  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180008b82  mov     r9d, ebx
0x180008b85  call    WPP_SF_d
0x180008b8a  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180008b8e  call    cs:__imp_SysFreeString
0x180008b94  jmp     loc_180008C96
0x180008b99  cmp     [rdi+20h], eax
0x180008b9c  jnz     short loc_180008BCF
0x180008b9e  movsxd  rax, dword ptr [rdi+18h]
0x180008ba2  lea     rdx, [rax+rax*2]
0x180008ba6  mov     rcx, [rdi+10h]
0x180008baa  mov     r10, [rcx+rdx*8]
0x180008bae  lea     rdx, [rdx+2]
0x180008bb2  lea     r8, [rcx+rdx*8]
0x180008bb6  lea     rcx, [rbp+57h+var_38]
0x180008bba  mov     [rsp+0A0h+var_50], rcx
0x180008bbf  lea     rcx, [rbp+57h+arg_10]
0x180008bc3  mov     [rsp+0A0h+var_58], rcx
0x180008bc8  mov     [rsp+0A0h+var_60], r8
0x180008bcd  jmp     short loc_180008C08
0x180008bcf  cmp     dword ptr [rdi+20h], 1
0x180008bd3  jnz     loc_180008C80
0x180008bd9  movsxd  rax, dword ptr [rdi+18h]
0x180008bdd  lea     rdx, [rax+rax*2]
0x180008be1  mov     rcx, [rdi+10h]
0x180008be5  mov     r10, [rcx+rdx*8]
0x180008be9  lea     rcx, [rcx+rdx*8]
0x180008bed  add     rcx, 10h
0x180008bf1  mov     [rsp+0A0h+var_50], rcx
0x180008bf6  lea     rcx, [rbp+57h+arg_10]
0x180008bfa  mov     [rsp+0A0h+var_58], rcx
0x180008bff  lea     rcx, [rbp+57h+var_34]
0x180008c03  mov     [rsp+0A0h+var_60], rcx
0x180008c08  lea     rcx, [rbp+57h+var_28]
0x180008c0c  mov     [rsp+0A0h+var_68], rcx
0x180008c11  lea     rcx, [rbp+57h+arg_0]
0x180008c15  mov     [rsp+0A0h+var_70], rcx
0x180008c1a  lea     rcx, [rbp+57h+arg_8]
0x180008c1e  mov     [rsp+0A0h+var_78], rcx
0x180008c23  lea     rcx, [rbp+57h+arg_18]
0x180008c27  mov     [rsp+0A0h+var_80], rcx
0x180008c2c  mov     rax, [r10]
0x180008c2f  lea     r9, [rbp+57h+var_40]
0x180008c33  lea     r8, [rbp+57h+bstrString]
0x180008c37  lea     rdx, [rbp+57h+var_3C]
0x180008c3b  mov     rcx, r10
0x180008c3e  mov     rax, [rax+30h]
0x180008c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c47  mov     ebx, eax
0x180008c49  test    eax, eax
0x180008c4b  jns     short loc_180008C7C
0x180008c4d  lea     rax, WPP_GLOBAL_Control
0x180008c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c5b  cmp     rcx, rax
0x180008c5e  jz      loc_180008B8A
0x180008c64  test    byte ptr [rcx+1Ch], 1
0x180008c68  jz      loc_180008B8A
0x180008c6e  mov     edx, 22h ; '"'
0x180008c73  mov     rcx, [rcx+10h]
0x180008c77  jmp     loc_180008B7B
0x180008c7c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180008c80  call    cs:__imp_SysFreeString
0x180008c86  mov     rcx, rdi; this
0x180008c89  call    ?FindCurrentRecord@CMultistateFileRecordQuery@@AEAAXXZ; CMultistateFileRecordQuery::FindCurrentRecord(void)
0x180008c8e  cmp     dword ptr [rdi+1Ch], 0
0x180008c92  cmovnz  ebx, r14d
0x180008c96  mov     eax, ebx
0x180008c98  add     rsp, 88h
0x180008c9f  pop     r14
0x180008ca1  pop     rdi
0x180008ca2  pop     rbx
0x180008ca3  pop     rbp
0x180008ca4  retn
```

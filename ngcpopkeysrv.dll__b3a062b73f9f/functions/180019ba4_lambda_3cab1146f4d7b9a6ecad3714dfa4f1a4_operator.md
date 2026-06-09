# _lambda_3cab1146f4d7b9a6ecad3714dfa4f1a4_::operator()

- ea: `0x180019ba4`
- end: `0x180019ee8`
- name: `_lambda_3cab1146f4d7b9a6ecad3714dfa4f1a4_::operator()`
- size: `836`
- prototype: `__int64 __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800196f4`

## callees

- `0x18000121c`
- `0x180001384`
- `0x180001430`
- `0x180005858`
- `0x18001069c`
- `0x180019ba4`
- `0x18001bee8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019bd8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019cb5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019da4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019e48`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019bd8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019cb5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019da4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019e48`

## string_xrefs

- `0x180019c2b`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x180019cfd`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall lambda_3cab1146f4d7b9a6ecad3714dfa4f1a4_::operator()(__int64 **a1)
{
  DWORD TickCount; // eax
  __int64 *v3; // rcx
  __int64 **v4; // r13
  __int64 v5; // rdi
  DWORD v6; // ebx
  struct _NgcPregenState *v7; // r9
  __int64 v8; // r8
  int PregenKeyState; // eax
  char v10; // r15
  __int64 v11; // rdx
  __int64 v12; // r12
  __int64 v13; // rdi
  DWORD v14; // eax
  unsigned int v15; // r8d
  unsigned int v16; // ecx
  int v17; // eax
  __int64 i; // r15
  __int64 v19; // rsi
  __int64 v20; // r13
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v28; // [rsp+20h] [rbp-59h]
  int v29; // [rsp+60h] [rbp-19h] BYREF
  int v30; // [rsp+64h] [rbp-15h] BYREF
  int v31; // [rsp+68h] [rbp-11h] BYREF
  DWORD v32; // [rsp+6Ch] [rbp-Dh] BYREF
  int v33; // [rsp+70h] [rbp-9h] BYREF
  int v34; // [rsp+74h] [rbp-5h] BYREF
  int v35; // [rsp+78h] [rbp-1h] BYREF
  int v36; // [rsp+7Ch] [rbp+3h] BYREF
  __int64 **v37; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DWORD v39; // [rsp+E0h] [rbp+67h] BYREF
  struct _NgcPregenState *v40; // [rsp+E8h] [rbp+6Fh] BYREF
  int v41; // [rsp+F0h] [rbp+77h] BYREF
  int v42; // [rsp+F8h] [rbp+7Fh] BYREF

  memset_0((void *)**a1, 0, 16LL * *(unsigned int *)a1[1]);
  TickCount = GetTickCount();
  v3 = a1[1];
  v4 = a1 + 2;
  v5 = 0;
  v39 = TickCount;
  v6 = TickCount;
  v37 = a1 + 2;
  if ( *(_DWORD *)v3 )
  {
    do
    {
      v7 = (struct _NgcPregenState *)(**a1 + 16LL * (unsigned int)v5);
      v8 = **v4;
      *(_DWORD *)v7 = *(_DWORD *)(v8 + 8 * v5);
      PregenKeyState = GetPregenKeyState(0, (struct NgcTimer *)&v39, *(_DWORD *)(v8 + 8 * v5 + 4), v7);
      if ( PregenKeyState < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x494,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)PregenKeyState,
          v28);
      v3 = a1[1];
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < *(_DWORD *)v3 );
  }
  else
  {
    v37 = a1 + 2;
  }
  if ( *(_DWORD *)a1[3] )
  {
    v10 = 0;
    do
    {
      if ( !*(_DWORD *)v3 )
        break;
      v11 = 0;
      while ( *(_DWORD *)(**a1 + 16LL * (unsigned int)v11 + 4) >= *(_DWORD *)(**v4 + 8 * v11 + 4) )
      {
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= *(_DWORD *)v3 )
          goto LABEL_24;
      }
      v12 = 0;
      do
      {
        v40 = (struct _NgcPregenState *)(16LL * (unsigned int)v12 + **a1);
        v13 = **v4;
        v14 = GetTickCount();
        v15 = *(_DWORD *)(v13 + 8 * v12 + 4);
        if ( v14 - v6 >= *(_DWORD *)a1[3] )
          v10 = 1;
        if ( *((_DWORD *)v40 + 1) < v15 )
        {
          v16 = 0;
          if ( !v10 )
            v16 = *(_DWORD *)a1[3];
          v17 = GetPregenKeyState(v16, (struct NgcTimer *)&v39, v15, v40);
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x4C3,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
              (const char *)(unsigned int)v17,
              v28);
        }
        v3 = a1[1];
        v12 = (unsigned int)(v12 + 1);
      }
      while ( (unsigned int)v12 < *(_DWORD *)v3 );
    }
    while ( !v10 );
  }
LABEL_24:
  for ( i = 0; (unsigned int)i < *(_DWORD *)a1[1]; v4 = v37 )
  {
    v19 = **a1;
    v20 = **v4;
    if ( *(_DWORD *)(v19 + 16LL * (unsigned int)i + 8)
      || *(_DWORD *)(v19 + 16LL * (unsigned int)i + 12)
      || *(_DWORD *)(v19 + 16LL * (unsigned int)i + 4) < *(_DWORD *)(v20 + 8 * i + 4) )
    {
      if ( (unsigned int)dword_180037000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180037000, 0x400000000000LL) )
      {
        v30 = *(_DWORD *)(v19 + 16LL * (unsigned int)i + 8);
        v31 = *(_DWORD *)(v19 + 16LL * (unsigned int)i + 12);
        v32 = GetTickCount() - v6;
        v24 = *(_DWORD *)a1[3];
        v34 = *(_DWORD *)(v19 + 16LL * (unsigned int)i + 4);
        v35 = *(_DWORD *)(v20 + 8 * i + 4);
        v36 = *(_DWORD *)(v20 + 8 * i);
        v33 = v24;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)byte_18002ED41,
          v25,
          v26,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v30);
      }
    }
    else if ( (unsigned int)dword_180037000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180037000, 0x400000000000LL) )
    {
      v39 = GetTickCount() - v6;
      v21 = *(_DWORD *)a1[3];
      v41 = *(_DWORD *)(v19 + 16LL * (unsigned int)i + 4);
      v42 = *(_DWORD *)(v20 + 8 * i + 4);
      v29 = *(_DWORD *)(v20 + 8 * i);
      LODWORD(v40) = v21;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&dword_18002EEF4,
        v22,
        v23,
        (__int64)&v29,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39);
    }
    i = (unsigned int)(i + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180019ba4  push    rbp
0x180019ba6  push    rbx
0x180019ba7  push    rsi
0x180019ba8  push    rdi
0x180019ba9  push    r12
0x180019bab  push    r13
0x180019bad  push    r14
0x180019baf  push    r15
0x180019bb1  lea     rbp, [rsp-1Fh]
0x180019bb6  sub     rsp, 98h
0x180019bbd  mov     rax, [rcx+8]
0x180019bc1  mov     r14, rcx
0x180019bc4  mov     rcx, [rcx]
0x180019bc7  xor     edx, edx; Val
0x180019bc9  mov     r8d, [rax]
0x180019bcc  mov     rcx, [rcx]; void *
0x180019bcf  shl     r8, 4; Size
0x180019bd3  call    memset_0
0x180019bd8  call    cs:__imp_GetTickCount
0x180019bde  mov     rcx, [r14+8]
0x180019be2  lea     r13, [r14+10h]
0x180019be6  xor     edi, edi
0x180019be8  mov     [rbp+57h+arg_0], eax
0x180019beb  mov     ebx, eax
0x180019bed  mov     [rbp+57h+var_50], r13
0x180019bf1  lea     esi, [rdi+1]
0x180019bf4  cmp     [rcx], edi
0x180019bf6  jbe     short loc_180019C4B
0x180019bf8  mov     rax, [r14]
0x180019bfb  lea     rdx, [rbp+57h+arg_0]; struct NgcTimer *
0x180019bff  mov     r9d, edi
0x180019c02  xor     ecx, ecx; unsigned int
0x180019c04  shl     r9, 4
0x180019c08  add     r9, [rax]; struct _NgcPregenState *
0x180019c0b  mov     rax, [r13+0]
0x180019c0f  mov     r8, [rax]
0x180019c12  mov     eax, [r8+rdi*8]
0x180019c16  mov     [r9], eax
0x180019c19  mov     r8d, [r8+rdi*8+4]; unsigned int
0x180019c1e  call    ?GetPregenKeyState@@YAJKPEAVNgcTimer@@KPEAU_NgcPregenState@@@Z; GetPregenKeyState(ulong,NgcTimer *,ulong,_NgcPregenState *)
0x180019c23  test    eax, eax
0x180019c25  jns     short loc_180019C3F
0x180019c27  mov     rcx, [rbp+5Fh]; this
0x180019c2b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180019c32  mov     r9d, eax; char *
0x180019c35  mov     edx, 494h; void *
0x180019c3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019c3f  mov     rcx, [r14+8]
0x180019c43  add     edi, esi
0x180019c45  cmp     edi, [rcx]
0x180019c47  jb      short loc_180019BF8
0x180019c49  jmp     short loc_180019C4F
0x180019c4b  mov     [rbp+57h+var_50], r13
0x180019c4f  mov     rax, [r14+18h]
0x180019c53  cmp     dword ptr [rax], 0
0x180019c56  jz      loc_180019D2F
0x180019c5c  xor     r15b, r15b
0x180019c5f  mov     r8d, [rcx]
0x180019c62  test    r8d, r8d
0x180019c65  jz      loc_180019D2F
0x180019c6b  mov     rax, [r13+0]
0x180019c6f  xor     edx, edx
0x180019c71  mov     r9, [rax]
0x180019c74  mov     rax, [r14]
0x180019c77  mov     r10, [rax]
0x180019c7a  mov     eax, [r9+rdx*8+4]
0x180019c7f  mov     ecx, edx
0x180019c81  add     rcx, rcx
0x180019c84  cmp     [r10+rcx*8+4], eax
0x180019c89  jb      short loc_180019C97
0x180019c8b  add     edx, esi
0x180019c8d  cmp     edx, r8d
0x180019c90  jb      short loc_180019C7A
0x180019c92  jmp     loc_180019D2F
0x180019c97  xor     r12d, r12d
0x180019c9a  mov     rax, [r14]
0x180019c9d  mov     edx, r12d
0x180019ca0  shl     rdx, 4
0x180019ca4  mov     rax, [rax]
0x180019ca7  add     rax, rdx
0x180019caa  mov     [rbp+57h+arg_8], rax
0x180019cae  mov     rax, [r13+0]
0x180019cb2  mov     rdi, [rax]
0x180019cb5  call    cs:__imp_GetTickCount
0x180019cbb  mov     rcx, [r14+18h]
0x180019cbf  sub     eax, ebx
0x180019cc1  mov     r8d, [rdi+r12*8+4]; unsigned int
0x180019cc6  movzx   r15d, r15b
0x180019cca  mov     edx, [rcx]
0x180019ccc  cmp     eax, edx
0x180019cce  mov     eax, 1
0x180019cd3  cmovnb  r15d, eax
0x180019cd7  mov     rax, [rbp+57h+arg_8]
0x180019cdb  cmp     [rax+4], r8d
0x180019cdf  jnb     short loc_180019D11
0x180019ce1  xor     ecx, ecx
0x180019ce3  mov     r9, rax; struct _NgcPregenState *
0x180019ce6  test    r15b, r15b
0x180019ce9  cmovz   ecx, edx; unsigned int
0x180019cec  lea     rdx, [rbp+57h+arg_0]; struct NgcTimer *
0x180019cf0  call    ?GetPregenKeyState@@YAJKPEAVNgcTimer@@KPEAU_NgcPregenState@@@Z; GetPregenKeyState(ulong,NgcTimer *,ulong,_NgcPregenState *)
0x180019cf5  test    eax, eax
0x180019cf7  jns     short loc_180019D11
0x180019cf9  mov     rcx, [rbp+5Fh]; this
0x180019cfd  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180019d04  mov     r9d, eax; char *
0x180019d07  mov     edx, 4C3h; void *
0x180019d0c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019d11  mov     rcx, [r14+8]
0x180019d15  mov     esi, 1
0x180019d1a  add     r12d, esi
0x180019d1d  cmp     r12d, [rcx]
0x180019d20  jb      loc_180019C9A
0x180019d26  test    r15b, r15b
0x180019d29  jz      loc_180019C5F
0x180019d2f  mov     rax, [r14+8]
0x180019d33  xor     r15d, r15d
0x180019d36  cmp     [rax], r15d
0x180019d39  jbe     loc_180019ED2
0x180019d3f  mov     rax, [r14]
0x180019d42  mov     edi, r15d
0x180019d45  add     rdi, rdi
0x180019d48  mov     rsi, [rax]
0x180019d4b  mov     rax, [r13+0]
0x180019d4f  cmp     dword ptr [rsi+rdi*8+8], 0
0x180019d54  mov     r13, [rax]
0x180019d57  jnz     loc_180019E0D
0x180019d5d  cmp     dword ptr [rsi+rdi*8+0Ch], 0
0x180019d62  jnz     loc_180019E0D
0x180019d68  mov     eax, [r13+r15*8+4]
0x180019d6d  cmp     [rsi+rdi*8+4], eax
0x180019d71  jb      loc_180019E0D
0x180019d77  mov     eax, cs:dword_180037000
0x180019d7d  cmp     eax, 4
0x180019d80  jbe     loc_180019EBE
0x180019d86  mov     rdx, 400000000000h
0x180019d90  lea     rcx, dword_180037000
0x180019d97  call    _tlgKeywordOn
0x180019d9c  test    al, al
0x180019d9e  jz      loc_180019EBE
0x180019da4  call    cs:__imp_GetTickCount
0x180019daa  sub     eax, ebx
0x180019dac  lea     rdx, dword_18002EEF4
0x180019db3  mov     [rbp+57h+arg_0], eax
0x180019db6  mov     rax, [r14+18h]
0x180019dba  mov     ecx, [rax]
0x180019dbc  mov     eax, [rsi+rdi*8+4]
0x180019dc0  mov     [rbp+57h+arg_10], eax
0x180019dc3  mov     eax, [r13+r15*8+4]
0x180019dc8  mov     [rbp+57h+arg_18], eax
0x180019dcb  mov     eax, [r13+r15*8+0]
0x180019dd0  mov     [rbp+57h+var_70], eax
0x180019dd3  lea     rax, [rbp+57h+arg_0]
0x180019dd7  mov     [rsp+0D0h+var_90], rax
0x180019ddc  lea     rax, [rbp+57h+arg_8]
0x180019de0  mov     [rsp+0D0h+var_98], rax
0x180019de5  lea     rax, [rbp+57h+arg_10]
0x180019de9  mov     [rsp+0D0h+var_A0], rax
0x180019dee  lea     rax, [rbp+57h+arg_18]
0x180019df2  mov     [rsp+0D0h+var_A8], rax
0x180019df7  lea     rax, [rbp+57h+var_70]
0x180019dfb  mov     [rsp+0D0h+var_B0], rax
0x180019e00  mov     dword ptr [rbp+57h+arg_8], ecx
0x180019e03  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019e08  jmp     loc_180019EBE
0x180019e0d  mov     eax, cs:dword_180037000
0x180019e13  cmp     eax, 2
0x180019e16  jbe     loc_180019EBE
0x180019e1c  mov     rdx, 400000000000h
0x180019e26  lea     rcx, dword_180037000
0x180019e2d  call    _tlgKeywordOn
0x180019e32  test    al, al
0x180019e34  jz      loc_180019EBE
0x180019e3a  mov     eax, [rsi+rdi*8+8]
0x180019e3e  mov     [rbp+57h+var_6C], eax
0x180019e41  mov     eax, [rsi+rdi*8+0Ch]
0x180019e45  mov     [rbp+57h+var_68], eax
0x180019e48  call    cs:__imp_GetTickCount
0x180019e4e  sub     eax, ebx
0x180019e50  lea     rdx, byte_18002ED41
0x180019e57  mov     [rbp+57h+var_64], eax
0x180019e5a  mov     rax, [r14+18h]
0x180019e5e  mov     ecx, [rax]
0x180019e60  mov     eax, [rsi+rdi*8+4]
0x180019e64  mov     [rbp+57h+var_5C], eax
0x180019e67  mov     eax, [r13+r15*8+4]
0x180019e6c  mov     [rbp+57h+var_58], eax
0x180019e6f  mov     eax, [r13+r15*8+0]
0x180019e74  mov     [rbp+57h+var_54], eax
0x180019e77  lea     rax, [rbp+57h+var_6C]
0x180019e7b  mov     [rsp+0D0h+var_80], rax
0x180019e80  lea     rax, [rbp+57h+var_68]
0x180019e84  mov     [rsp+0D0h+var_88], rax
0x180019e89  lea     rax, [rbp+57h+var_64]
0x180019e8d  mov     [rsp+0D0h+var_90], rax
0x180019e92  lea     rax, [rbp+57h+var_60]
0x180019e96  mov     [rsp+0D0h+var_98], rax
0x180019e9b  lea     rax, [rbp+57h+var_5C]
0x180019e9f  mov     [rsp+0D0h+var_A0], rax
0x180019ea4  lea     rax, [rbp+57h+var_58]
0x180019ea8  mov     [rsp+0D0h+var_A8], rax
0x180019ead  lea     rax, [rbp+57h+var_54]
0x180019eb1  mov     [rsp+0D0h+var_B0], rax
0x180019eb6  mov     [rbp+57h+var_60], ecx
0x180019eb9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019ebe  mov     rax, [r14+8]
0x180019ec2  inc     r15d
0x180019ec5  mov     r13, [rbp+57h+var_50]
0x180019ec9  cmp     r15d, [rax]
0x180019ecc  jb      loc_180019D3F
0x180019ed2  xor     eax, eax
0x180019ed4  add     rsp, 98h
0x180019edb  pop     r15
0x180019edd  pop     r14
0x180019edf  pop     r13
0x180019ee1  pop     r12
0x180019ee3  pop     rdi
0x180019ee4  pop     rsi
0x180019ee5  pop     rbx
0x180019ee6  pop     rbp
0x180019ee7  retn
```

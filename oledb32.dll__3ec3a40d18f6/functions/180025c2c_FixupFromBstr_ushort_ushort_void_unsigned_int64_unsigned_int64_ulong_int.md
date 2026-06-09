# FixupFromBstr(ushort *,ushort,void *,unsigned __int64 *,unsigned __int64,ulong *,int)

- ea: `0x180025c2c`
- end: `0x180025f2a`
- name: `?FixupFromBstr@@YAJPEAGGPEAXPEA_K_KPEAKH@Z`
- size: `766`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16@<dx>, void *@<r8>, unsigned __int64 *@<r9>, unsigned __int64, unsigned int *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180003320`

## callees

- `0x180013870`
- `0x180025c2c`
- `0x180029560`
- `0x18002ec26`
- `0x18003ef1c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180025ed0`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ed0`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180025cab`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180025cab`
- `ole32!CoTaskMemAlloc` at `0x180025cf1`
- `ole32!CoTaskMemAlloc` at `0x180025e1b`
- `ole32!CoTaskMemAlloc` at `0x180025cf1`
- `ole32!CoTaskMemAlloc` at `0x180025e1b`
- `ole32!CoTaskMemFree` at `0x180025d76`
- `ole32!CoTaskMemFree` at `0x180025d76`

## pseudocode

```c
__int64 __fastcall FixupFromBstr(
        unsigned __int16 *a1,
        __int16 a2,
        unsigned __int8 *a3,
        unsigned __int64 *a4,
        unsigned __int64 a5,
        unsigned int *a6,
        int a7)
{
  unsigned __int8 *v8; // rdi
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 result; // rax
  unsigned int v14; // edx
  unsigned int v15; // ecx
  size_t v16; // rsi
  size_t v17; // rsi
  unsigned int v18; // eax
  unsigned int v19; // edx
  unsigned int v20; // ecx
  unsigned __int64 v21; // rbp
  unsigned __int8 *v22; // rax
  char v23; // al
  unsigned int v24; // r8d
  bool v25; // zf
  unsigned int v26; // eax
  int v27; // r15d
  unsigned __int64 v28; // rbp
  unsigned __int8 *v29; // rax
  char v30; // al
  const char *v31; // [rsp+30h] [rbp-48h]
  const char *v32; // [rsp+30h] [rbp-48h]
  int v33; // [rsp+80h] [rbp+8h] BYREF

  v33 = 0;
  v8 = a3;
  if ( a1 )
  {
    if ( a2 == 8 )
    {
      *a4 = 8;
      result = 0;
      *(_QWORD *)a3 = a1;
      return result;
    }
    v11 = 0;
    v16 = SysStringByteLen(a1);
    if ( a2 == 129 )
    {
      v17 = v16 >> 1;
      v18 = FastWideCharToMultiByte(v15, v14, a1, v17, 0, 0, v31, 0);
      *a4 = v18;
      if ( a7 )
      {
        v21 = v18 + 1LL;
        v22 = (unsigned __int8 *)CoTaskMemAlloc(v21);
        *(_QWORD *)v8 = v22;
        if ( !v22 )
        {
          v23 = bidGblFlags;
          if ( (bidGblFlags & 2) != 0 )
          {
            v11 = bidTraceHR(off_1800C8390[0], 9545737, L"<FixupFromBstr|Trace|HR> ", 2147942414LL);
            v23 = bidGblFlags;
          }
          else
          {
            v11 = -2147024882;
          }
          if ( (v23 & 2) == 0 )
            goto LABEL_43;
          v24 = 9323;
          goto LABEL_15;
        }
        v8 = v22;
      }
      else
      {
        v21 = a5;
      }
      if ( v21 )
      {
        v26 = FastWideCharToMultiByte(v20, v19, a1, v17, v8, v21, v32, &v33);
        if ( v26 == *a4 && v21 > v26 )
        {
          v8[v26] = 0;
          if ( v33 )
            *a6 = 4;
        }
        else
        {
          *a6 = 4;
          v8[v21 - 1] = 0;
        }
        goto LABEL_43;
      }
      v25 = a7 == 0;
    }
    else
    {
      if ( a2 != 130 )
      {
LABEL_43:
        SysFreeString(a1);
        if ( (bidGblFlags & 2) == 0 )
          return v11;
        OLEDBTraceErr(v11, L"<FixupFromBstr|OLEDB|ERR> ", 0x24DBu);
        if ( (bidGblFlags & 2) == 0 )
          return v11;
        v12 = 9662473;
        return (unsigned int)bidTraceHR(off_1800C8390[0], v12, L"<FixupFromBstr|Trace|HR> ", v11);
      }
      *a4 = v16;
      v27 = a7;
      if ( a7 )
      {
        v28 = v16 + 2;
        v29 = (unsigned __int8 *)CoTaskMemAlloc(v16 + 2);
        *(_QWORD *)v8 = v29;
        if ( !v29 )
        {
          v30 = bidGblFlags;
          if ( (bidGblFlags & 2) != 0 )
          {
            v11 = bidTraceHR(off_1800C8390[0], 9613321, L"<FixupFromBstr|Trace|HR> ", 2147942414LL);
            v30 = bidGblFlags;
          }
          else
          {
            v11 = -2147024882;
          }
          if ( (v30 & 2) == 0 )
            goto LABEL_43;
          v24 = 9389;
LABEL_15:
          OLEDBTraceErr(v11, L"<FixupFromBstr|OLEDB|ERR> ", v24);
          goto LABEL_43;
        }
        v8 = v29;
      }
      else
      {
        v28 = a5;
      }
      if ( v28 >= 2 )
      {
        if ( v16 + 2 > v28 )
        {
          *a6 = 4;
          memcpy_0(v8, a1, v28 - 2);
          *(_WORD *)&v8[2 * (v28 >> 1) - 2] = 0;
        }
        else
        {
          memcpy_0(v8, a1, v16);
          *(_WORD *)&v8[2 * (v16 >> 1)] = 0;
        }
        goto LABEL_43;
      }
      v25 = v27 == 0;
    }
    if ( !v25 )
      CoTaskMemFree(v8);
    *a6 = 6;
    goto LABEL_43;
  }
  v11 = -2147024882;
  if ( (bidGblFlags & 2) == 0 )
    return v11;
  OLEDBTraceErr(-2147024882, L"<FixupFromBstr|OLEDB|ERR> ", 0x243Eu);
  if ( (bidGblFlags & 2) == 0 )
    return v11;
  v12 = 9501705;
  return (unsigned int)bidTraceHR(off_1800C8390[0], v12, L"<FixupFromBstr|Trace|HR> ", v11);
}

```

## disassembly

```asm
0x180025c2c  mov     rax, rsp
0x180025c2f  push    rbx
0x180025c30  push    rbp
0x180025c31  push    rsi
0x180025c32  push    rdi
0x180025c33  push    r14
0x180025c35  push    r15
0x180025c37  sub     rsp, 48h
0x180025c3b  mov     dword ptr [rax+8], 0
0x180025c42  mov     r15, r9
0x180025c45  mov     rdi, r8
0x180025c48  movzx   ebp, dx
0x180025c4b  mov     r14, rcx
0x180025c4e  test    rcx, rcx
0x180025c51  jnz     short loc_180025C92
0x180025c53  mov     eax, cs:_bidGblFlags
0x180025c59  mov     ebx, 8007000Eh
0x180025c5e  test    al, 2
0x180025c60  jz      loc_180025F1B
0x180025c66  mov     r8d, 243Eh; unsigned int
0x180025c6c  lea     rdx, aFixupfrombstrO; "<FixupFromBstr|OLEDB|ERR> "
0x180025c73  mov     ecx, ebx; int
0x180025c75  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180025c7a  mov     eax, cs:_bidGblFlags
0x180025c80  test    al, 2
0x180025c82  jz      loc_180025F1B
0x180025c88  mov     edx, 90FC09h
0x180025c8d  jmp     loc_180025F03
0x180025c92  mov     eax, 8
0x180025c97  cmp     bp, ax
0x180025c9a  jnz     short loc_180025CA9
0x180025c9c  mov     [r9], rax
0x180025c9f  xor     eax, eax
0x180025ca1  mov     [r8], r14
0x180025ca4  jmp     loc_180025F1D
0x180025ca9  xor     ebx, ebx
0x180025cab  call    cs:__imp_SysStringByteLen
0x180025cb1  mov     esi, eax
0x180025cb3  mov     eax, 81h
0x180025cb8  cmp     bp, ax
0x180025cbb  jnz     loc_180025DF6
0x180025cc1  mov     [rsp+78h+var_40], rbx; int *
0x180025cc6  mov     r8, r14; unsigned __int16 *
0x180025cc9  shr     rsi, 1
0x180025ccc  mov     r9d, esi; int
0x180025ccf  mov     [rsp+78h+var_50], ebx; int
0x180025cd3  mov     [rsp+78h+var_58], rbx; unsigned __int8 *
0x180025cd8  call    ?FastWideCharToMultiByte@@YAHIKPEBGHPEAEHPEBDPEAH@Z; FastWideCharToMultiByte(uint,ulong,ushort const *,int,uchar *,int,char const *,int *)
0x180025cdd  mov     ebp, eax
0x180025cdf  mov     [r15], rbp
0x180025ce2  cmp     [rsp+78h+arg_30], ebx
0x180025ce9  jz      short loc_180025D5C
0x180025ceb  inc     rbp
0x180025cee  mov     rcx, rbp; cb
0x180025cf1  call    cs:__imp_CoTaskMemAlloc
0x180025cf7  mov     [rdi], rax
0x180025cfa  test    rax, rax
0x180025cfd  jnz     short loc_180025D57
0x180025cff  mov     eax, cs:_bidGblFlags
0x180025d05  test    al, 2
0x180025d07  jz      short loc_180025D31
0x180025d09  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180025d10  lea     r8, aFixupfrombstrT; "<FixupFromBstr|Trace|HR> "
0x180025d17  mov     r9d, 8007000Eh
0x180025d1d  mov     edx, 91A809h
0x180025d22  call    _bidTraceHR
0x180025d27  mov     ebx, eax
0x180025d29  mov     eax, cs:_bidGblFlags
0x180025d2f  jmp     short loc_180025D36
0x180025d31  mov     ebx, 8007000Eh
0x180025d36  test    al, 2
0x180025d38  jz      loc_180025ECD
0x180025d3e  mov     r8d, 246Bh; unsigned int
0x180025d44  lea     rdx, aFixupfrombstrO; "<FixupFromBstr|OLEDB|ERR> "
0x180025d4b  mov     ecx, ebx; int
0x180025d4d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180025d52  jmp     loc_180025ECD
0x180025d57  mov     rdi, rax
0x180025d5a  jmp     short loc_180025D64
0x180025d5c  mov     rbp, [rsp+78h+arg_20]
0x180025d64  cmp     rbp, 1
0x180025d68  jnb     short loc_180025D8F
0x180025d6a  cmp     [rsp+78h+arg_30], ebx
0x180025d71  jz      short loc_180025D7C
0x180025d73  mov     rcx, rdi; pv
0x180025d76  call    cs:__imp_CoTaskMemFree
0x180025d7c  mov     rax, [rsp+78h+arg_28]
0x180025d84  mov     dword ptr [rax], 6
0x180025d8a  jmp     loc_180025ECD
0x180025d8f  lea     rax, [rsp+78h+arg_0]
0x180025d97  mov     r9d, esi; int
0x180025d9a  mov     [rsp+78h+var_40], rax; int *
0x180025d9f  mov     r8, r14; unsigned __int16 *
0x180025da2  mov     [rsp+78h+var_50], ebp; int
0x180025da6  mov     [rsp+78h+var_58], rdi; unsigned __int8 *
0x180025dab  call    ?FastWideCharToMultiByte@@YAHIKPEBGHPEAEHPEBDPEAH@Z; FastWideCharToMultiByte(uint,ulong,ushort const *,int,uchar *,int,char const *,int *)
0x180025db0  mov     eax, eax
0x180025db2  cmp     rax, [r15]
0x180025db5  jnz     short loc_180025DDF
0x180025db7  cmp     rbp, rax
0x180025dba  jbe     short loc_180025DDF
0x180025dbc  mov     [rax+rdi], bl
0x180025dbf  cmp     [rsp+78h+arg_0], ebx
0x180025dc6  jz      loc_180025ECD
0x180025dcc  mov     rax, [rsp+78h+arg_28]
0x180025dd4  mov     dword ptr [rax], 4
0x180025dda  jmp     loc_180025ECD
0x180025ddf  mov     rax, [rsp+78h+arg_28]
0x180025de7  mov     dword ptr [rax], 4
0x180025ded  mov     [rdi+rbp-1], bl
0x180025df1  jmp     loc_180025ECD
0x180025df6  mov     eax, 82h
0x180025dfb  cmp     bp, ax
0x180025dfe  jnz     loc_180025ECD
0x180025e04  mov     [r15], rsi
0x180025e07  mov     r15d, [rsp+78h+arg_30]
0x180025e0f  test    r15d, r15d
0x180025e12  jz      short loc_180025E74
0x180025e14  lea     rbp, [rsi+2]
0x180025e18  mov     rcx, rbp; cb
0x180025e1b  call    cs:__imp_CoTaskMemAlloc
0x180025e21  mov     [rdi], rax
0x180025e24  test    rax, rax
0x180025e27  jnz     short loc_180025E6F
0x180025e29  mov     eax, cs:_bidGblFlags
0x180025e2f  test    al, 2
0x180025e31  jz      short loc_180025E5B
0x180025e33  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180025e3a  lea     r8, aFixupfrombstrT; "<FixupFromBstr|Trace|HR> "
0x180025e41  mov     r9d, 8007000Eh
0x180025e47  mov     edx, 92B009h
0x180025e4c  call    _bidTraceHR
0x180025e51  mov     ebx, eax
0x180025e53  mov     eax, cs:_bidGblFlags
0x180025e59  jmp     short loc_180025E60
0x180025e5b  mov     ebx, 8007000Eh
0x180025e60  test    al, 2
0x180025e62  jz      short loc_180025ECD
0x180025e64  mov     r8d, 24ADh
0x180025e6a  jmp     loc_180025D44
0x180025e6f  mov     rdi, rax
0x180025e72  jmp     short loc_180025E7C
0x180025e74  mov     rbp, [rsp+78h+arg_20]
0x180025e7c  cmp     rbp, 2
0x180025e80  jnb     short loc_180025E8A
0x180025e82  test    r15d, r15d
0x180025e85  jmp     loc_180025D71
0x180025e8a  lea     rax, [rsi+2]
0x180025e8e  mov     rdx, r14; Src
0x180025e91  mov     rcx, rdi; void *
0x180025e94  cmp     rax, rbp
0x180025e97  ja      short loc_180025EAC
0x180025e99  mov     r8, rsi; Size
0x180025e9c  call    memcpy_0
0x180025ea1  shr     rsi, 1
0x180025ea4  xor     eax, eax
0x180025ea6  mov     [rdi+rsi*2], ax
0x180025eaa  jmp     short loc_180025ECD
0x180025eac  mov     rax, [rsp+78h+arg_28]
0x180025eb4  lea     r8, [rbp-2]; Size
0x180025eb8  mov     dword ptr [rax], 4
0x180025ebe  call    memcpy_0
0x180025ec3  shr     rbp, 1
0x180025ec6  xor     eax, eax
0x180025ec8  mov     [rdi+rbp*2-2], ax
0x180025ecd  mov     rcx, r14; bstrString
0x180025ed0  call    cs:__imp_SysFreeString
0x180025ed6  mov     eax, cs:_bidGblFlags
0x180025edc  test    al, 2
0x180025ede  jz      short loc_180025F1B
0x180025ee0  mov     r8d, 24DBh; unsigned int
0x180025ee6  lea     rdx, aFixupfrombstrO; "<FixupFromBstr|OLEDB|ERR> "
0x180025eed  mov     ecx, ebx; int
0x180025eef  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180025ef4  mov     eax, cs:_bidGblFlags
0x180025efa  test    al, 2
0x180025efc  jz      short loc_180025F1B
0x180025efe  mov     edx, 937009h
0x180025f03  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180025f0a  lea     r8, aFixupfrombstrT; "<FixupFromBstr|Trace|HR> "
0x180025f11  mov     r9d, ebx
0x180025f14  call    _bidTraceHR
0x180025f19  mov     ebx, eax
0x180025f1b  mov     eax, ebx
0x180025f1d  add     rsp, 48h
0x180025f21  pop     r15
0x180025f23  pop     r14
0x180025f25  pop     rdi
0x180025f26  pop     rsi
0x180025f27  pop     rbp
0x180025f28  pop     rbx
0x180025f29  retn
```

# CreateIMallocCopyOfProps(ulong,tagDBPROPSET *,ulong *,tagDBPROPSET * *,bool)

- ea: `0x180076e50`
- end: `0x18007712f`
- name: `?CreateIMallocCopyOfProps@@YAJKPEAUtagDBPROPSET@@PEAKPEAPEAU1@_N@Z`
- size: `735`
- prototype: `__int64 __fastcall(unsigned int, struct tagDBPROPSET *, unsigned int *, struct tagDBPROPSET **, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180070950`
- `0x180071b44`
- `0x180074850`

## callees

- `0x180013394`
- `0x180013870`
- `0x180029560`
- `0x18002ec0c`
- `0x180076e50`
- `0x18007e6ca`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180077045`
- `OLEAUT32!__imp_VariantInit` at `0x180077045`
- `ole32!CoTaskMemAlloc` at `0x180076e8c`
- `ole32!CoTaskMemAlloc` at `0x180076f2e`
- `ole32!CoTaskMemAlloc` at `0x180076e8c`
- `ole32!CoTaskMemAlloc` at `0x180076f2e`

## string_xrefs

- `0x180076eaf`: `<CreateIMallocCopyOfProps|OLEDB|ERR> `
- `0x180076f55`: `<CreateIMallocCopyOfProps|OLEDB|ERR> `
- `0x180077076`: `<CreateIMallocCopyOfProps|OLEDB|ERR> `
- `0x180077094`: `<CreateIMallocCopyOfProps|OLEDB|ERR> `
- `0x180076eca`: `<CreateIMallocCopyOfProps|Trace|HR> `
- `0x180076f70`: `<CreateIMallocCopyOfProps|Trace|HR> `
- `0x1800770af`: `<CreateIMallocCopyOfProps|Trace|HR> `
- `0x180077103`: `<CreateIMallocCopyOfProps|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CreateIMallocCopyOfProps(
        unsigned int a1,
        struct tagDBPROPSET *a2,
        unsigned int *a3,
        struct tagDBPROPSET **a4,
        bool a5)
{
  __int64 v7; // rsi
  unsigned int v8; // ebx
  struct tagDBPROPSET *v9; // rax
  int v10; // ebx
  unsigned int i; // r12d
  __int64 v12; // rdi
  struct tagDBPROPSET *v13; // r13
  DBPROP *v14; // rcx
  int v15; // ebx
  __int64 j; // r13
  struct tagDBPROP *v17; // rdx
  struct tagDBPROP *v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // ebx
  int pExceptionObject; // [rsp+20h] [rbp-68h] BYREF
  int v23; // [rsp+24h] [rbp-64h] BYREF
  unsigned int v24; // [rsp+28h] [rbp-60h] BYREF
  unsigned int v25; // [rsp+2Ch] [rbp-5Ch] BYREF
  struct tagDBPROPSET *v26; // [rsp+30h] [rbp-58h]
  struct tagDBPROP *v27; // [rsp+38h] [rbp-50h]
  struct tagDBPROP *v28; // [rsp+40h] [rbp-48h]

  v7 = a1;
  v8 = 0;
  *a3 = a1;
  if ( a1 )
  {
    v9 = (struct tagDBPROPSET *)CoTaskMemAlloc(32LL * a1);
    try
    {
      *a4 = v9;
      if ( !v9 )
      {
        v10 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024882, L"<CreateIMallocCopyOfProps|OLEDB|ERR> ", 0x837u);
          if ( (bidGblFlags & 2) != 0 )
            v10 = bidTraceHR(off_1800C84F0[0], 2153481, L"<CreateIMallocCopyOfProps|Trace|HR> ", 2147942414LL);
        }
        pExceptionObject = v10;
        throw (long *)&pExceptionObject;
      }
      memset_0(v9, 0, 32 * v7);
      for ( i = 0; i < (unsigned int)v7; ++i )
      {
        v12 = i;
        v26 = *a4;
        v13 = v26;
        v14 = (DBPROP *)CoTaskMemAlloc(72LL * a2[v12].cProperties);
        v26[v12].rgProperties = v14;
        if ( !v14 )
        {
          v15 = -2147024882;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024882, L"<CreateIMallocCopyOfProps|OLEDB|ERR> ", 0x841u);
            if ( (bidGblFlags & 2) != 0 )
              v15 = bidTraceHR(off_1800C84F0[0], 2163721, L"<CreateIMallocCopyOfProps|Trace|HR> ", 2147942414LL);
          }
          v23 = v15;
          throw (long *)&v23;
        }
        memset_0(v14, 0, 72LL * a2[v12].cProperties);
        v13[v12].cProperties = a2[v12].cProperties;
        v13[v12].guidPropertySet = a2[v12].guidPropertySet;
        for ( j = 0; (unsigned int)j < a2[v12].cProperties; j = (unsigned int)(j + 1) )
        {
          v17 = &a2[v12].rgProperties[j];
          v27 = v17;
          v18 = &v26[v12].rgProperties[j];
          v28 = v18;
          if ( !a5 )
            goto LABEL_25;
          v19 = *(_QWORD *)&a2[v12].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
          if ( !v19 )
            v19 = *(_QWORD *)a2[v12].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DBINIT.Data4;
          if ( !v19 && (v17->dwPropertyID == 9 || v17->dwPropertyID == 160) )
            v20 = 2;
          else
LABEL_25:
            v20 = 0;
          VariantInit(&v18->vValue);
          v8 = CopyProperty(v28, v27, 1, v20);
          if ( (v8 & 0x80000000) != 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v8, L"<CreateIMallocCopyOfProps|OLEDB|ERR> ", 0x84Fu);
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v8, L"<CreateIMallocCopyOfProps|OLEDB|ERR> ", 0x84Fu);
                if ( (bidGblFlags & 2) != 0 )
                  v8 = bidTraceHR(off_1800C84F0[0], 2178057, L"<CreateIMallocCopyOfProps|Trace|HR> ", v8);
              }
            }
            v24 = v8;
            throw (long *)&v24;
          }
        }
      }
    }
    catch ( long v25 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800C8D80[0] )
      {
        v8 = v25;
        bidTraceA(off_1800C84F0[0], 2184192, off_1800C8D80[0], v25);
      }
      else
      {
        v8 = v25;
      }
      FreePropSets(*a3, *a4);
    }
  }
  else
  {
    *a4 = 0;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C84F0[0], 2190345, L"<CreateIMallocCopyOfProps|Trace|HR> ", v8);
  return v8;
}

```

## disassembly

```asm
0x180076e50  mov     [rsp+arg_18], r9
0x180076e55  mov     [rsp+arg_10], r8
0x180076e5a  push    rbx
0x180076e5b  push    rsi
0x180076e5c  push    rdi
0x180076e5d  push    r12
0x180076e5f  push    r13
0x180076e61  push    r14
0x180076e63  push    r15
0x180076e65  sub     rsp, 50h
0x180076e69  mov     r15, r9
0x180076e6c  mov     r14, rdx
0x180076e6f  mov     esi, ecx
0x180076e71  xor     ebx, ebx
0x180076e73  mov     [r8], esi
0x180076e76  test    ecx, ecx
0x180076e78  jnz     short loc_180076E82
0x180076e7a  mov     [r9], rbx
0x180076e7d  jmp     loc_1800770F7
0x180076e82  mov     rdi, rsi
0x180076e85  shl     rdi, 5
0x180076e89  mov     rcx, rdi; cb
0x180076e8c  call    cs:__imp_CoTaskMemAlloc
0x180076e92  mov     [r15], rax
0x180076e95  test    rax, rax
0x180076e98  jnz     short loc_180076EF9
0x180076e9a  mov     eax, cs:_bidGblFlags
0x180076ea0  mov     ebx, 8007000Eh
0x180076ea5  test    al, 2
0x180076ea7  jz      short loc_180076EE4
0x180076ea9  mov     r8d, 837h; unsigned int
0x180076eaf  lea     rdx, aCreateimallocc; "<CreateIMallocCopyOfProps|OLEDB|ERR> "
0x180076eb6  mov     ecx, ebx; int
0x180076eb8  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180076ebd  mov     eax, cs:_bidGblFlags
0x180076ec3  test    al, 2
0x180076ec5  jz      short loc_180076EE4
0x180076ec7  mov     r9d, ebx
0x180076eca  lea     r8, aCreateimallocc_1; "<CreateIMallocCopyOfProps|Trace|HR> "
0x180076ed1  mov     edx, 20DC09h
0x180076ed6  mov     rcx, cs:off_1800C84F0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180076edd  call    _bidTraceHR
0x180076ee2  mov     ebx, eax
0x180076ee4  mov     [rsp+88h+pExceptionObject], ebx
0x180076ee8  lea     rdx, _TI1J; pThrowInfo
0x180076eef  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180076ef4  call    _CxxThrowException_0
0x180076ef9  mov     r8, rdi; Size
0x180076efc  xor     edx, edx; Val
0x180076efe  mov     rcx, rax; void *
0x180076f01  call    memset_0
0x180076f06  xor     r12d, r12d
0x180076f09  cmp     r12d, esi
0x180076f0c  jnb     loc_1800770EE
0x180076f12  mov     edi, r12d
0x180076f15  shl     rdi, 5
0x180076f19  mov     r13, [r15]
0x180076f1c  mov     [rsp+88h+var_58], r13
0x180076f21  mov     eax, [rdi+r14+8]
0x180076f26  lea     rcx, [rax+rax*8]
0x180076f2a  shl     rcx, 3; cb
0x180076f2e  call    cs:__imp_CoTaskMemAlloc
0x180076f34  mov     rcx, rax; void *
0x180076f37  mov     [rdi+r13], rax
0x180076f3b  test    rax, rax
0x180076f3e  jnz     short loc_180076F9F
0x180076f40  mov     eax, cs:_bidGblFlags
0x180076f46  mov     ebx, 8007000Eh
0x180076f4b  test    al, 2
0x180076f4d  jz      short loc_180076F8A
0x180076f4f  mov     r8d, 841h; unsigned int
0x180076f55  lea     rdx, aCreateimallocc; "<CreateIMallocCopyOfProps|OLEDB|ERR> "
0x180076f5c  mov     ecx, ebx; int
0x180076f5e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180076f63  mov     eax, cs:_bidGblFlags
0x180076f69  test    al, 2
0x180076f6b  jz      short loc_180076F8A
0x180076f6d  mov     r9d, ebx
0x180076f70  lea     r8, aCreateimallocc_1; "<CreateIMallocCopyOfProps|Trace|HR> "
0x180076f77  mov     edx, 210409h
0x180076f7c  mov     rcx, cs:off_1800C84F0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180076f83  call    _bidTraceHR
0x180076f88  mov     ebx, eax
0x180076f8a  mov     [rsp+88h+var_64], ebx
0x180076f8e  lea     rdx, _TI1J; pThrowInfo
0x180076f95  lea     rcx, [rsp+88h+var_64]; pExceptionObject
0x180076f9a  call    _CxxThrowException_0
0x180076f9f  mov     eax, [rdi+r14+8]
0x180076fa4  lea     r8, [rax+rax*8]
0x180076fa8  shl     r8, 3; Size
0x180076fac  xor     edx, edx; Val
0x180076fae  call    memset_0
0x180076fb3  mov     eax, [rdi+r14+8]
0x180076fb8  mov     [rdi+r13+8], eax
0x180076fbd  movups  xmm0, xmmword ptr [rdi+r14+0Ch]
0x180076fc3  movdqu  xmmword ptr [rdi+r13+0Ch], xmm0
0x180076fca  xor     r13d, r13d
0x180076fcd  cmp     r13d, [rdi+r14+8]
0x180076fd2  jnb     loc_1800770E6
0x180076fd8  lea     rcx, ds:0[r13*8]
0x180076fe0  add     rcx, r13
0x180076fe3  mov     rax, [rdi+r14]
0x180076fe7  lea     rdx, [rax+rcx*8]
0x180076feb  mov     [rsp+88h+var_50], rdx
0x180076ff0  mov     rax, [rsp+88h+var_58]
0x180076ff5  mov     rax, [rdi+rax]
0x180076ff9  lea     rcx, [rax+rcx*8]
0x180076ffd  mov     [rsp+88h+var_48], rcx
0x180077002  cmp     [rsp+88h+arg_20], 0
0x18007700a  jz      short loc_18007703F
0x18007700c  mov     rax, [rdi+r14+0Ch]
0x180077011  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x180077018  jnz     short loc_180077026
0x18007701a  mov     rax, [rdi+r14+14h]
0x18007701f  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x180077026  test    rax, rax
0x180077029  jnz     short loc_18007703F
0x18007702b  cmp     dword ptr [rdx], 9
0x18007702e  jz      short loc_180077038
0x180077030  cmp     dword ptr [rdx], 0A0h
0x180077036  jnz     short loc_18007703F
0x180077038  mov     ebx, 2
0x18007703d  jmp     short loc_180077041
0x18007703f  xor     ebx, ebx
0x180077041  add     rcx, 30h ; '0'; pvarg
0x180077045  call    cs:__imp_VariantInit
0x18007704b  mov     r9d, ebx; unsigned int
0x18007704e  mov     r8b, 1; bool
0x180077051  mov     rdx, [rsp+88h+var_50]; struct tagDBPROP *
0x180077056  mov     rcx, [rsp+88h+var_48]; struct tagDBPROP *
0x18007705b  call    ?CopyProperty@@YAJPEAUtagDBPROP@@PEBU1@_NK@Z; CopyProperty(tagDBPROP *,tagDBPROP const *,bool,ulong)
0x180077060  mov     ebx, eax
0x180077062  test    eax, eax
0x180077064  jns     short loc_1800770DE
0x180077066  mov     eax, cs:_bidGblFlags
0x18007706c  test    al, 2
0x18007706e  jz      short loc_1800770C9
0x180077070  mov     r8d, 84Fh; unsigned int
0x180077076  lea     rdx, aCreateimallocc; "<CreateIMallocCopyOfProps|OLEDB|ERR> "
0x18007707d  mov     ecx, ebx; int
0x18007707f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180077084  mov     eax, cs:_bidGblFlags
0x18007708a  test    al, 2
0x18007708c  jz      short loc_1800770C9
0x18007708e  mov     r8d, 84Fh; unsigned int
0x180077094  lea     rdx, aCreateimallocc; "<CreateIMallocCopyOfProps|OLEDB|ERR> "
0x18007709b  mov     ecx, ebx; int
0x18007709d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800770a2  mov     eax, cs:_bidGblFlags
0x1800770a8  test    al, 2
0x1800770aa  jz      short loc_1800770C9
0x1800770ac  mov     r9d, ebx
0x1800770af  lea     r8, aCreateimallocc_1; "<CreateIMallocCopyOfProps|Trace|HR> "
0x1800770b6  mov     edx, 213C09h
0x1800770bb  mov     rcx, cs:off_1800C84F0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800770c2  call    _bidTraceHR
0x1800770c7  mov     ebx, eax
0x1800770c9  mov     [rsp+88h+var_60], ebx
0x1800770cd  lea     rdx, _TI1J; pThrowInfo
0x1800770d4  lea     rcx, [rsp+88h+var_60]; pExceptionObject
0x1800770d9  call    _CxxThrowException_0
0x1800770de  inc     r13d
0x1800770e1  jmp     loc_180076FCD
0x1800770e6  inc     r12d
0x1800770e9  jmp     loc_180076F09
0x1800770ee  jmp     short loc_1800770F7
0x1800770f0  mov     ebx, [rsp+88h+arg_0]
0x1800770f7  test    byte ptr cs:_bidGblFlags, 2
0x1800770fe  jz      short loc_18007711D
0x180077100  mov     r9d, ebx
0x180077103  lea     r8, aCreateimallocc_1; "<CreateIMallocCopyOfProps|Trace|HR> "
0x18007710a  mov     edx, 216C09h
0x18007710f  mov     rcx, cs:off_1800C84F0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180077116  call    _bidTraceHR
0x18007711b  mov     ebx, eax
0x18007711d  mov     eax, ebx
0x18007711f  add     rsp, 50h
0x180077123  pop     r15
0x180077125  pop     r14
0x180077127  pop     r13
0x180077129  pop     r12
0x18007712b  pop     rdi
0x18007712c  pop     rsi
0x18007712d  pop     rbx
0x18007712e  retn
```

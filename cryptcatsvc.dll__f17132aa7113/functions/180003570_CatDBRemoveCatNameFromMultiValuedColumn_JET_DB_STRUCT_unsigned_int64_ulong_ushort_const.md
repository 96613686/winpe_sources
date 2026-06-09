# _CatDBRemoveCatNameFromMultiValuedColumn(_JET_DB_STRUCT *,unsigned __int64,ulong,ushort const *)

- ea: `0x180003570`
- end: `0x1800038e8`
- name: `?_CatDBRemoveCatNameFromMultiValuedColumn@@YAHPEAU_JET_DB_STRUCT@@_KKPEBG@Z`
- size: `888`
- prototype: `int(struct _JET_DB_STRUCT *, unsigned __int64, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180003ef0`
- `0x18001aeb0`

## callees

- `0x180001680`
- `0x180003538`
- `0x180003570`
- `0x1800038f0`
- `0x180003de4`
- `0x18000a59c`
- `0x18000acbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000366d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000366d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003818`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003854`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000386d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003897`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800038b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800038da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003818`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003854`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000386d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003897`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800038b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800038da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003639`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003647`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003639`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003647`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037d1`
- `ESENT!JetUpdate` at `0x1800037f8`
- `ESENT!JetUpdate` at `0x1800037f8`
- `ESENT!JetDelete` at `0x180003834`
- `ESENT!JetDelete` at `0x180003834`
- `ESENT!JetPrepareUpdate` at `0x18000369c`
- `ESENT!JetPrepareUpdate` at `0x18000369c`

## pseudocode

```c
__int64 __fastcall _CatDBRemoveCatNameFromMultiValuedColumn(
        struct _JET_DB_STRUCT *a1,
        JET_TABLEID a2,
        JET_COLUMNID a3,
        const unsigned __int16 *a4)
{
  unsigned int v4; // ebx
  JET_SESID v8; // rcx
  int v9; // eax
  _QWORD *v10; // r15
  unsigned int v11; // r14d
  int v12; // edi
  unsigned int v13; // ebx
  JET_SESID v15; // rcx
  JET_ERR v16; // ebx
  int v17; // ebp
  unsigned int i; // edx
  _WORD *v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // ebx
  const WCHAR *v22; // rax
  WCHAR *v23; // rdi
  const WCHAR *v24; // rsi
  __int64 v25; // r11
  WCHAR *v26; // rdx
  __int64 v27; // r10
  __int64 v28; // r9
  __int64 v29; // rcx
  WCHAR *v30; // r8
  WCHAR *v31; // rcx
  int v32; // ebx
  JET_ERR v33; // ebx
  DWORD v34; // eax
  unsigned int v35; // edx
  unsigned __int16 *v36; // rcx
  unsigned int v37; // r8d
  JET_ERR v38; // ebx
  DWORD v39; // eax
  DWORD v40; // eax
  DWORD v41; // eax
  DWORD v42; // eax
  DWORD v43; // eax
  int v44; // [rsp+28h] [rbp-70h]
  unsigned int v45; // [rsp+40h] [rbp-58h] BYREF
  HLOCAL v46; // [rsp+48h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-48h] BYREF

  v4 = 1;
  hMem = 0;
  v46 = 0;
  v8 = *((_QWORD *)a1 + 1);
  v45 = 0;
  v9 = CatHelperRetrieveLongColumnAsStringVector(
         v8,
         a2,
         a3,
         (unsigned int)a4,
         (unsigned __int16 **)&hMem,
         (unsigned __int16 ***)&v46,
         &v45);
  v10 = v46;
  if ( !v9 )
  {
    v11 = v45;
    if ( v45 )
    {
      if ( (unsigned int)_CatDBJET_errFailure(0) )
      {
        v41 = _CatDBMapJetError(0);
        SetLastError(v41);
        v37 = 5270;
        goto LABEL_46;
      }
      v12 = 0;
      v13 = 0;
      if ( v11 )
      {
        do
        {
          if ( !(unsigned int)_o__wcsicmp(a4, v10[v13]) )
          {
            v10[v13] = 0;
            ++v12;
          }
          ++v13;
        }
        while ( v13 < v11 );
        if ( v12 )
        {
          v15 = *((_QWORD *)a1 + 1);
          if ( v12 == v11 )
          {
            v38 = JetDelete(v15, a2);
            if ( (unsigned int)_CatDBJET_errFailure(v38) )
            {
              v39 = _CatDBMapJetError(v38);
              SetLastError(v39);
              v37 = 5300;
              goto LABEL_46;
            }
          }
          else
          {
            v16 = JetPrepareUpdate(v15, a2, 2u);
            if ( (unsigned int)_CatDBJET_errFailure(v16) )
            {
              v40 = _CatDBMapJetError(v16);
              SetLastError(v40);
              v37 = 5311;
              goto LABEL_46;
            }
            v17 = 0;
            for ( i = 0; i < v11; ++i )
            {
              v19 = (_WORD *)v10[i];
              if ( v19 && *v19 )
              {
                v20 = -1;
                do
                  ++v20;
                while ( v19[v20] );
                v17 += v20 + 1;
              }
            }
            v21 = v17 + 1;
            v22 = (const WCHAR *)_CatDBAlloc(2LL * (unsigned int)(v17 + 1));
            v23 = (WCHAR *)v22;
            if ( !v22 )
            {
              v42 = _CatDBMapJetError(-1011);
              SetLastError(v42);
              v37 = 5327;
              goto LABEL_46;
            }
            v24 = v22;
            v25 = 0;
            do
            {
              v26 = (WCHAR *)v10[v25];
              if ( v26 && *v26 )
              {
                v27 = -1;
                do
                  ++v27;
                while ( v26[v27] );
                v28 = v21;
                if ( v21 - 1 > 0x7FFFFFFE )
                {
                  if ( v21 )
                    *v24 = 0;
                }
                else
                {
                  v29 = 2147483646;
                  v30 = (WCHAR *)v24;
                  while ( v29 )
                  {
                    if ( !*v26 )
                    {
                      if ( !v28 )
                      {
LABEL_35:
                        --v30;
                        break;
                      }
                      break;
                    }
                    *v30++ = *v26++;
                    --v29;
                    if ( !--v28 )
                      goto LABEL_35;
                  }
                  *v30 = 0;
                }
                v31 = (WCHAR *)&v24[(unsigned int)v27];
                *v31 = 124;
                v24 = v31 + 1;
                v21 += -1 - v27;
              }
              v25 = (unsigned int)(v25 + 1);
            }
            while ( (unsigned int)v25 < v11 );
            v22[v17] = 0;
            v32 = CatHelperSetCatalogListColumn(*((_QWORD *)a1 + 1), a2, a3, 0xCu, v22);
            LocalFree(v23);
            if ( (unsigned int)_CatDBJET_errFailure(v32) )
            {
              v43 = _CatDBMapJetError(v32);
              SetLastError(v43);
              v37 = 5357;
              goto LABEL_46;
            }
            v33 = JetUpdate(*((_QWORD *)a1 + 1), a2, 0, 0, 0);
            if ( (unsigned int)_CatDBJET_errFailure(v33) )
            {
              v34 = _CatDBMapJetError(v33);
              SetLastError(v34);
              v37 = 5368;
LABEL_46:
              ErrLog_LogError(v36, v35, v37, 0, 0, v44);
              v4 = 0;
              goto LABEL_6;
            }
          }
        }
      }
      v4 = 1;
    }
  }
LABEL_6:
  if ( hMem )
    LocalFree(hMem);
  if ( v10 )
    LocalFree(v10);
  return v4;
}

```

## disassembly

```asm
0x180003570  mov     rax, rsp
0x180003573  mov     [rax+18h], r8d
0x180003577  mov     [rax+8], rcx
0x18000357b  push    rbx
0x18000357c  push    r15
0x18000357e  sub     rsp, 88h
0x180003585  mov     [rax+10h], rbp
0x180003589  mov     ebx, 1
0x18000358e  mov     [rax-18h], rsi
0x180003592  mov     rbp, r9
0x180003595  mov     [rax-28h], r12
0x180003599  xor     esi, esi
0x18000359b  mov     [rax-30h], r13
0x18000359f  mov     r12, rdx
0x1800035a2  mov     r13, rcx
0x1800035a5  mov     [rax-48h], rsi
0x1800035a9  lea     rcx, [rax-58h]
0x1800035ad  mov     [rax-50h], rsi
0x1800035b1  mov     [rax-68h], rcx
0x1800035b5  lea     rcx, [rax-50h]
0x1800035b9  mov     [rax-70h], rcx
0x1800035bd  lea     rcx, [rax-48h]
0x1800035c1  mov     [rax-78h], rcx
0x1800035c5  mov     rcx, [r13+8]; sesid
0x1800035c9  mov     [rax-58h], esi
0x1800035cc  call    ?CatHelperRetrieveLongColumnAsStringVector@@YAJ_K0KKAEAPEAGAEAPEAPEAGAEAK@Z; CatHelperRetrieveLongColumnAsStringVector(unsigned __int64,unsigned __int64,ulong,ulong,ushort * &,ushort * * &,ulong &)
0x1800035d1  mov     r15, [rsp+98h+var_50]
0x1800035d6  test    eax, eax
0x1800035d8  jnz     short loc_180003615
0x1800035da  mov     [rsp+98h+var_38], r14
0x1800035df  mov     r14d, [rsp+98h+var_58]
0x1800035e4  test    r14d, r14d
0x1800035e7  jz      short loc_180003610
0x1800035e9  xor     ecx, ecx; int
0x1800035eb  mov     [rsp+98h+var_20], rdi
0x1800035f0  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800035f5  test    eax, eax
0x1800035f7  jnz     loc_18000388E
0x1800035fd  mov     edi, esi
0x1800035ff  mov     ebx, esi
0x180003601  test    r14d, r14d
0x180003604  jnz     short loc_180003660
0x180003606  mov     ebx, 1
0x18000360b  mov     rdi, [rsp+98h+var_20]
0x180003610  mov     r14, [rsp+98h+var_38]
0x180003615  mov     rcx, [rsp+98h+hMem]; hMem
0x18000361a  mov     r13, [rsp+98h+var_30]
0x18000361f  mov     r12, [rsp+98h+var_28]
0x180003624  mov     rsi, [rsp+98h+var_18]
0x18000362c  mov     rbp, [rsp+98h+arg_8]
0x180003634  test    rcx, rcx
0x180003637  jz      short loc_18000363F
0x180003639  call    cs:__imp_LocalFree
0x18000363f  test    r15, r15
0x180003642  jz      short loc_18000364D
0x180003644  mov     rcx, r15; hMem
0x180003647  call    cs:__imp_LocalFree
0x18000364d  mov     eax, ebx
0x18000364f  add     rsp, 88h
0x180003656  pop     r15
0x180003658  pop     rbx
0x180003659  retn
0x180003660  mov     eax, ebx
0x180003662  mov     rcx, rbp
0x180003665  mov     rdx, [r15+rax*8]
0x180003669  lea     rsi, [r15+rax*8]
0x18000366d  call    cs:__imp__o__wcsicmp
0x180003673  test    eax, eax
0x180003675  jz      loc_180003826
0x18000367b  inc     ebx
0x18000367d  cmp     ebx, r14d
0x180003680  jb      short loc_180003660
0x180003682  test    edi, edi
0x180003684  jz      short loc_180003606
0x180003686  mov     rcx, [r13+8]; sesid
0x18000368a  mov     rdx, r12; tableid
0x18000368d  cmp     edi, r14d
0x180003690  jz      loc_180003834
0x180003696  mov     r8d, 2; prep
0x18000369c  call    cs:__imp_JetPrepareUpdate
0x1800036a2  mov     ecx, eax; int
0x1800036a4  mov     ebx, eax
0x1800036a6  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800036ab  test    eax, eax
0x1800036ad  jnz     loc_180003864
0x1800036b3  xor     esi, esi
0x1800036b5  mov     ebp, esi
0x1800036b7  mov     edx, esi
0x1800036b9  nop     dword ptr [rax+00000000h]
0x1800036c0  mov     eax, edx
0x1800036c2  mov     rcx, [r15+rax*8]
0x1800036c6  test    rcx, rcx
0x1800036c9  jz      short loc_1800036E4
0x1800036cb  cmp     [rcx], si
0x1800036ce  jz      short loc_1800036E4
0x1800036d0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800036d7  inc     rax
0x1800036da  cmp     [rcx+rax*2], si
0x1800036de  jnz     short loc_1800036D7
0x1800036e0  inc     ebp
0x1800036e2  add     ebp, eax
0x1800036e4  inc     edx
0x1800036e6  cmp     edx, r14d
0x1800036e9  jb      short loc_1800036C0
0x1800036eb  lea     ebx, [rbp+1]
0x1800036ee  mov     ecx, ebx
0x1800036f0  add     rcx, rcx; uBytes
0x1800036f3  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x1800036f8  mov     rdi, rax
0x1800036fb  test    rax, rax
0x1800036fe  jz      loc_1800038A5
0x180003704  mov     rsi, rax
0x180003707  xor     r11d, r11d
0x18000370a  mov     rdx, [r15+r11*8]
0x18000370e  test    rdx, rdx
0x180003711  jz      short loc_180003791
0x180003713  cmp     word ptr [rdx], 0
0x180003717  jz      short loc_180003791
0x180003719  mov     r10, 0FFFFFFFFFFFFFFFFh
0x180003720  inc     r10
0x180003723  cmp     word ptr [rdx+r10*2], 0
0x180003729  jnz     short loc_180003720
0x18000372b  lea     eax, [rbx-1]
0x18000372e  mov     r9d, ebx
0x180003731  cmp     eax, 7FFFFFFEh
0x180003736  ja      loc_1800038BF
0x18000373c  mov     ecx, 7FFFFFFEh
0x180003741  mov     r8, rsi
0x180003744  test    rcx, rcx
0x180003747  jz      short loc_180003771
0x180003749  movzx   eax, word ptr [rdx]
0x18000374c  test    ax, ax
0x18000374f  jz      short loc_18000376C
0x180003751  mov     [r8], ax
0x180003755  add     rdx, 2
0x180003759  add     r8, 2
0x18000375d  dec     rcx
0x180003760  sub     r9, 1
0x180003764  jnz     short loc_180003744
0x180003766  sub     r8, 2
0x18000376a  jmp     short loc_180003771
0x18000376c  test    r9, r9
0x18000376f  jz      short loc_180003766
0x180003771  xor     eax, eax
0x180003773  mov     [r8], ax
0x180003777  mov     eax, r10d
0x18000377a  lea     rcx, [rsi+rax*2]
0x18000377e  mov     eax, 0FFFFFFFFh
0x180003783  mov     word ptr [rcx], 7Ch ; '|'
0x180003788  lea     rsi, [rcx+2]
0x18000378c  sub     eax, r10d
0x18000378f  add     ebx, eax
0x180003791  inc     r11d
0x180003794  cmp     r11d, r14d
0x180003797  jb      loc_18000370A
0x18000379d  mov     r13, [rsp+98h+arg_0]
0x1800037a5  xor     esi, esi
0x1800037a7  mov     r8d, [rsp+98h+columnid]; columnid
0x1800037af  mov     r9d, 0Ch; grbit
0x1800037b5  mov     ecx, ebp
0x1800037b7  mov     rdx, r12; tableid
0x1800037ba  mov     [rsp+98h+pcbActual], rdi; lpWideCharStr
0x1800037bf  mov     [rdi+rcx*2], si
0x1800037c3  mov     rcx, [r13+8]; sesid
0x1800037c7  call    ?CatHelperSetCatalogListColumn@@YAJ_K0KKPEBG@Z; CatHelperSetCatalogListColumn(unsigned __int64,unsigned __int64,ulong,ulong,ushort const *)
0x1800037cc  mov     rcx, rdi; hMem
0x1800037cf  mov     ebx, eax
0x1800037d1  call    cs:__imp_LocalFree
0x1800037d7  mov     ecx, ebx; int
0x1800037d9  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800037de  test    eax, eax
0x1800037e0  jnz     loc_1800038D1
0x1800037e6  mov     rcx, [r13+8]; sesid
0x1800037ea  xor     r9d, r9d; cbBookmark
0x1800037ed  xor     r8d, r8d; pvBookmark
0x1800037f0  mov     [rsp+98h+pcbActual], rsi; pcbActual
0x1800037f5  mov     rdx, r12; tableid
0x1800037f8  call    cs:__imp_JetUpdate
0x1800037fe  mov     ecx, eax; int
0x180003800  mov     ebx, eax
0x180003802  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180003807  test    eax, eax
0x180003809  jz      loc_180003606
0x18000380f  mov     ecx, ebx; int
0x180003811  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003816  mov     ecx, eax; dwErrCode
0x180003818  call    cs:__imp_SetLastError
0x18000381e  mov     r8d, 14F8h
0x180003824  jmp     short loc_18000387B
0x180003826  mov     qword ptr [rsi], 0
0x18000382d  inc     edi
0x18000382f  jmp     loc_18000367B
0x180003834  call    cs:__imp_JetDelete
0x18000383a  mov     ecx, eax; int
0x18000383c  mov     ebx, eax
0x18000383e  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180003843  test    eax, eax
0x180003845  jz      loc_180003606
0x18000384b  mov     ecx, ebx; int
0x18000384d  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003852  mov     ecx, eax; dwErrCode
0x180003854  call    cs:__imp_SetLastError
0x18000385a  xor     esi, esi
0x18000385c  mov     r8d, 14B4h
0x180003862  jmp     short loc_18000387B
0x180003864  mov     ecx, ebx; int
0x180003866  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18000386b  mov     ecx, eax; dwErrCode
0x18000386d  call    cs:__imp_SetLastError
0x180003873  xor     esi, esi
0x180003875  mov     r8d, 14BFh; unsigned int
0x18000387b  xor     r9d, r9d; unsigned int
0x18000387e  mov     dword ptr [rsp+98h+pcbActual], esi; int
0x180003882  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180003887  mov     ebx, esi
0x180003889  jmp     loc_18000360B
0x18000388e  xor     ecx, ecx; int
0x180003890  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003895  mov     ecx, eax; dwErrCode
0x180003897  call    cs:__imp_SetLastError
0x18000389d  mov     r8d, 1496h
0x1800038a3  jmp     short loc_18000387B
0x1800038a5  mov     ecx, 0FFFFFC0Dh; int
0x1800038aa  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800038af  mov     ecx, eax; dwErrCode
0x1800038b1  call    cs:__imp_SetLastError
0x1800038b7  mov     r8d, 14CFh
0x1800038bd  jmp     short loc_18000387B
0x1800038bf  test    ebx, ebx
0x1800038c1  jz      loc_180003777
0x1800038c7  xor     eax, eax
0x1800038c9  mov     [rsi], ax
0x1800038cc  jmp     loc_180003777
0x1800038d1  mov     ecx, ebx; int
0x1800038d3  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800038d8  mov     ecx, eax; dwErrCode
0x1800038da  call    cs:__imp_SetLastError
0x1800038e0  mov     r8d, 14EDh
0x1800038e6  jmp     short loc_18000387B
```

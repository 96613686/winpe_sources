# CDefragEngine::_CreateVolumeStatusList(__MIDL___MIDL_itf_dfengine_0000_0000_0005,__MIDL___MIDL_itf_dfengine_0000_0000_0007 * *,ulong *)

- ea: `0x18001d914`
- end: `0x18001dc91`
- name: `?_CreateVolumeStatusList@CDefragEngine@@AEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0005@@PEAPEAU__MIDL___MIDL_itf_dfengine_0000_0000_0007@@PEAK@Z`
- size: `893`
- prototype: `__int64 __fastcall(__int64, unsigned int, CDefragEngine *, unsigned int *)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c8b0`
- `0x18003ee70`
- `0x1800457b0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001727c`
- `0x180017e50`
- `0x180017e94`
- `0x18001d914`
- `0x18001e998`
- `0x18001ea0c`
- `0x180067b0a`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dc20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dc20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d9de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d9de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001da31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001da31`

## string_xrefs

- `0x18001d94d`: `CDefragEngine::_CreateVolumeStatusList`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall CDefragEngine::_CreateVolumeStatusList(
        __int64 a1,
        unsigned int a2,
        CDefragEngine *a3,
        unsigned int *a4)
{
  int v6; // r15d
  __int64 v7; // rsi
  CDfVolumeListItem *v8; // rbx
  unsigned int v9; // r14d
  struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *v10; // rdi
  CDefragEngine *v11; // rcx
  __int16 v12; // ax
  __int64 v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  __int16 v16; // ax
  struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *v17; // rax
  int *v18; // rcx
  int v19; // r11d
  struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *i; // r13
  __int64 v21; // rdi
  CDfVolumeListItem *v22; // rcx
  unsigned int v23; // edi
  CDfVolumeListItem *v25; // [rsp+28h] [rbp-49h] BYREF
  int v26; // [rsp+30h] [rbp-41h] BYREF
  __int16 v27; // [rsp+34h] [rbp-3Dh]
  __int16 v28; // [rsp+36h] [rbp-3Bh]
  int v29; // [rsp+68h] [rbp-9h] BYREF
  CDfVolumeList *v30[2]; // [rsp+70h] [rbp-1h]
  __int64 v31; // [rsp+80h] [rbp+Fh]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+88h] [rbp+17h]
  struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *v35; // [rsp+F0h] [rbp+7Fh]

  v6 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v26, "CDefragEngine::_CreateVolumeStatusList", 3497, 1);
  v7 = 0;
  v31 = 0;
  v8 = 0;
  v25 = 0;
  v29 = 0;
  *(_OWORD *)v30 = 0;
  v9 = 0;
  v10 = 0;
  v11 = a3;
  if ( a3 )
    *(_QWORD *)a3 = 0;
  if ( a4 )
    *a4 = 0;
  v12 = 3511;
  if ( a3 )
  {
    v27 = 3511;
    v12 = 3512;
    if ( a4 )
    {
      v26 = 0;
      v27 = 3512;
      *a4 = 0;
      *(_QWORD *)a3 = 0;
      CDefragEngine::_RefreshVolumeList((CDefragEngine *)a1, *(struct CDfVolumeList **)(a1 + 104));
      lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 64);
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
      v13 = *(_QWORD *)(a1 + 104);
      v14 = *(_QWORD **)(v13 + 8);
      v15 = (_QWORD *)(v13 + 24);
      while ( v14 != v15 )
      {
        ++v9;
        v14 = (_QWORD *)*v14;
      }
      v27 = 3528;
      v16 = 3530;
      if ( v9 )
      {
        v26 = 0;
        v27 = 3530;
        v17 = (struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *)CoTaskMemAlloc(208 * v9);
        v35 = v17;
        if ( !v17 )
        {
          v26 = -2147024882;
          v28 = 3534;
          v10 = 0;
          goto LABEL_42;
        }
        v26 = 0;
        v27 = 3534;
        v10 = v17;
        memset_0(v17, 0, 208 * v9);
        v18 = *(int **)(a1 + 104);
        if ( v18 )
        {
          v30[1] = *(CDfVolumeList **)(a1 + 104);
          _InterlockedAdd(v18 + 10, 1u);
          v29 = *v18;
          v30[0] = (CDfVolumeList *)(v18 + 2);
          v26 = 0;
          v27 = 3542;
          if ( v18 == (int *)-8LL )
          {
            v26 = -2147418113;
            v16 = 3544;
          }
          else
          {
            v29 = *v18;
            v30[0] = (CDfVolumeList *)(v18 + 2);
            v26 = 0;
            v27 = 3544;
            v19 = CSxList<CDfVolumeList,CDfVolumeListItem>::CSxIter::Next(&v29, &v25);
            v26 = v19;
            v16 = 3546;
            if ( v19 >= 0 )
            {
              for ( i = v10; ; i = (struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *)((char *)i + 208) )
              {
                v27 = v16;
                v8 = v25;
                if ( v19 == 1 )
                  break;
                v21 = *((_QWORD *)v25 + 1);
                if ( v21 )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v21 + 8LL))(*((_QWORD *)v25 + 1));
                if ( v7 )
                {
                  v31 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
                }
                v7 = v21;
                v31 = v21;
                if ( v21 )
                {
                  v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *))(*(_QWORD *)v21 + 88LL))(
                          v21,
                          a2,
                          i);
                  v16 = 3555;
                  if ( v26 < 0 )
                    goto LABEL_34;
                  v27 = 3555;
                }
                if ( v8 )
                {
                  v25 = 0;
                  CDfVolumeListItem::Release(v8);
                }
                v19 = CSxList<CDfVolumeList,CDfVolumeListItem>::CSxIter::Next(&v29, &v25);
                v26 = v19;
                v16 = 3559;
                if ( v19 < 0 )
                {
                  v8 = v25;
LABEL_34:
                  v10 = v35;
                  goto LABEL_41;
                }
              }
              v22 = v25;
              if ( v25 )
              {
                v8 = 0;
                v25 = 0;
                CDfVolumeListItem::Release(v22);
              }
              if ( v30[1] )
              {
                CDfVolumeList::Release(v30[1]);
                v30[1] = 0;
              }
              v30[0] = 0;
              v29 = 0;
              v6 = 0;
              *a4 = v9;
              v10 = v35;
              *(_QWORD *)a3 = v35;
              v26 = 0;
LABEL_42:
              LeaveCriticalSection(lpCriticalSection);
              if ( !v6 )
                goto LABEL_44;
              goto LABEL_43;
            }
            v8 = v25;
          }
        }
        else
        {
          v26 = -2147024809;
          v16 = 3542;
        }
      }
      else
      {
        v26 = -1996488702;
      }
LABEL_41:
      v28 = v16;
      goto LABEL_42;
    }
  }
  v26 = -2147024809;
  v28 = v12;
LABEL_43:
  CDefragEngine::_DeleteVolumeStatusList(v11, v10, v9);
LABEL_44:
  v23 = v26;
  if ( v30[1] )
    CDfVolumeList::Release(v30[1]);
  if ( v8 )
    CDfVolumeListItem::Release(v8);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v26);
  return v23;
}

```

## disassembly

```asm
0x18001d914  mov     rax, rsp
0x18001d917  mov     [rax+8], rbx
0x18001d91b  mov     [rax+18h], r8
0x18001d91f  mov     [rax+10h], edx
0x18001d922  push    rbp
0x18001d923  push    rsi
0x18001d924  push    rdi
0x18001d925  push    r12
0x18001d927  push    r13
0x18001d929  push    r14
0x18001d92b  push    r15
0x18001d92d  lea     rbp, [rax-5Fh]
0x18001d931  sub     rsp, 90h
0x18001d938  mov     r12, r9
0x18001d93b  mov     r13, rcx
0x18001d93e  mov     r15d, 1
0x18001d944  mov     r9d, r15d; unsigned __int16
0x18001d947  mov     r8d, 0DA9h; unsigned __int16
0x18001d94d  lea     rdx, aCdefragengineC_2; "CDefragEngine::_CreateVolumeStatusList"
0x18001d954  lea     rcx, [rbp+57h+var_98]; this
0x18001d958  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001d95d  nop
0x18001d95e  xor     edx, edx
0x18001d960  mov     esi, edx
0x18001d962  mov     [rbp+57h+var_48], rdx
0x18001d966  mov     ebx, edx
0x18001d968  mov     [rbp+57h+var_A0], rdx
0x18001d96c  mov     [rbp+57h+var_60], edx
0x18001d96f  xorps   xmm0, xmm0
0x18001d972  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x18001d977  mov     r14d, edx
0x18001d97a  mov     edi, edx
0x18001d97c  mov     rcx, [rbp+57h+arg_10]
0x18001d980  test    rcx, rcx
0x18001d983  jz      short loc_18001D988
0x18001d985  mov     [rcx], rdx
0x18001d988  test    r12, r12
0x18001d98b  jz      short loc_18001D991
0x18001d98d  mov     [r12], edx
0x18001d991  mov     eax, 0DB7h
0x18001d996  test    rcx, rcx
0x18001d999  jnz     short loc_18001D9AB
0x18001d99b  mov     [rbp+57h+var_98], 80070057h
0x18001d9a2  mov     [rbp+57h+var_92], ax
0x18001d9a6  jmp     loc_18001DC2B
0x18001d9ab  mov     [rbp+57h+var_94], ax
0x18001d9af  mov     eax, 0DB8h
0x18001d9b4  test    r12, r12
0x18001d9b7  jz      short loc_18001D99B
0x18001d9b9  mov     [rbp+57h+var_98], edx
0x18001d9bc  mov     [rbp+57h+var_94], ax
0x18001d9c0  mov     [r12], edx
0x18001d9c4  mov     [rcx], rdx
0x18001d9c7  mov     rdx, [r13+68h]; struct CDfVolumeList *
0x18001d9cb  mov     rcx, r13; this
0x18001d9ce  call    ?_RefreshVolumeList@CDefragEngine@@AEAAJPEAVCDfVolumeList@@@Z; CDefragEngine::_RefreshVolumeList(CDfVolumeList *)
0x18001d9d3  lea     rax, [r13+40h]
0x18001d9d7  mov     [rbp+57h+lpCriticalSection], rax
0x18001d9db  mov     rcx, rax; lpCriticalSection
0x18001d9de  call    cs:__imp_EnterCriticalSection
0x18001d9e4  mov     rax, [r13+68h]
0x18001d9e8  mov     rcx, [rax+8]
0x18001d9ec  mov     dword ptr [rbp+57h+arg_18], edi
0x18001d9ef  add     rax, 18h
0x18001d9f3  jmp     short loc_18001D9FB
0x18001d9f5  add     r14d, r15d
0x18001d9f8  mov     rcx, [rcx]
0x18001d9fb  cmp     rcx, rax
0x18001d9fe  jnz     short loc_18001D9F5
0x18001da00  mov     eax, 0DC8h
0x18001da05  mov     [rbp+57h+var_94], ax
0x18001da09  mov     eax, 0DCAh
0x18001da0e  test    r14d, r14d
0x18001da11  jnz     short loc_18001DA1F
0x18001da13  mov     [rbp+57h+var_98], 89000002h
0x18001da1a  jmp     loc_18001DC18
0x18001da1f  mov     [rbp+57h+var_98], edi
0x18001da22  mov     [rbp+57h+var_94], ax
0x18001da26  imul    eax, r14d, 0D0h
0x18001da2d  mov     edi, eax
0x18001da2f  mov     ecx, eax; cb
0x18001da31  call    cs:__imp_CoTaskMemAlloc
0x18001da37  mov     [rbp+57h+arg_18], rax
0x18001da3b  mov     ecx, 0DCEh
0x18001da40  test    rax, rax
0x18001da43  jnz     short loc_18001DA58
0x18001da45  mov     [rbp+57h+var_98], 8007000Eh
0x18001da4c  mov     [rbp+57h+var_92], cx
0x18001da50  mov     rdi, rax
0x18001da53  jmp     loc_18001DC1C
0x18001da58  mov     [rbp+57h+var_98], 0
0x18001da5f  mov     [rbp+57h+var_94], cx
0x18001da63  mov     r8, rdi; Size
0x18001da66  xor     edx, edx; Val
0x18001da68  mov     rdi, rax
0x18001da6b  mov     rcx, rax; void *
0x18001da6e  call    memset_0
0x18001da73  mov     rcx, [r13+68h]
0x18001da77  test    rcx, rcx
0x18001da7a  jnz     short loc_18001DA8D
0x18001da7c  mov     [rbp+57h+var_98], 80070057h
0x18001da83  mov     eax, 0DD6h
0x18001da88  jmp     loc_18001DC18
0x18001da8d  mov     [rbp+57h+var_58+8], rcx
0x18001da91  lock add [rcx+28h], r15d
0x18001da96  mov     eax, [rcx]
0x18001da98  mov     [rbp+57h+var_60], eax
0x18001da9b  lea     rdx, [rcx+8]
0x18001da9f  mov     [rbp+57h+var_58], rdx
0x18001daa3  mov     [rbp+57h+var_98], 0
0x18001daaa  mov     eax, 0DD6h
0x18001daaf  mov     [rbp+57h+var_94], ax
0x18001dab3  test    rdx, rdx
0x18001dab6  jz      loc_18001DC0C
0x18001dabc  mov     eax, [rcx]
0x18001dabe  mov     [rbp+57h+var_60], eax
0x18001dac1  mov     [rbp+57h+var_58], rdx
0x18001dac5  mov     [rbp+57h+var_98], 0
0x18001dacc  mov     eax, 0DD8h
0x18001dad1  mov     [rbp+57h+var_94], ax
0x18001dad5  lea     rdx, [rbp+57h+var_A0]
0x18001dad9  lea     rcx, [rbp+57h+var_60]
0x18001dadd  call    ?Next@CSxIter@?$CSxList@VCDfVolumeList@@VCDfVolumeListItem@@@@QEAAJPEAPEAVCDfVolumeListItem@@@Z; CSxList<CDfVolumeList,CDfVolumeListItem>::CSxIter::Next(CDfVolumeListItem * *)
0x18001dae2  mov     r11d, eax
0x18001dae5  mov     [rbp+57h+var_98], eax
0x18001dae8  test    eax, eax
0x18001daea  mov     eax, 0DDAh
0x18001daef  jns     short loc_18001DAFA
0x18001daf1  mov     rbx, [rbp+57h+var_A0]
0x18001daf5  jmp     loc_18001DC18
0x18001dafa  mov     r13, rdi
0x18001dafd  mov     [rbp+57h+var_94], ax
0x18001db01  mov     rbx, [rbp+57h+var_A0]
0x18001db05  cmp     r11d, r15d
0x18001db08  jz      loc_18001DBBC
0x18001db0e  mov     rdi, [rbx+8]
0x18001db12  test    rdi, rdi
0x18001db15  jz      short loc_18001DB27
0x18001db17  mov     rax, [rdi]
0x18001db1a  mov     rcx, rdi
0x18001db1d  mov     rax, [rax+8]
0x18001db21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db26  nop
0x18001db27  test    rsi, rsi
0x18001db2a  jz      short loc_18001DB44
0x18001db2c  mov     [rbp+57h+var_48], 0
0x18001db34  mov     rax, [rsi]
0x18001db37  mov     rcx, rsi
0x18001db3a  mov     rax, [rax+10h]
0x18001db3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db43  nop
0x18001db44  mov     rsi, rdi
0x18001db47  mov     [rbp+57h+var_48], rdi
0x18001db4b  test    rdi, rdi
0x18001db4e  jz      short loc_18001DB75
0x18001db50  mov     rax, [rdi]
0x18001db53  mov     r8, r13
0x18001db56  mov     edx, [rbp+57h+arg_8]
0x18001db59  mov     rcx, rdi
0x18001db5c  mov     rax, [rax+58h]
0x18001db60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db65  mov     [rbp+57h+var_98], eax
0x18001db68  test    eax, eax
0x18001db6a  mov     eax, 0DE3h
0x18001db6f  js      short loc_18001DBB6
0x18001db71  mov     [rbp+57h+var_94], ax
0x18001db75  test    rbx, rbx
0x18001db78  jz      short loc_18001DB8A
0x18001db7a  mov     [rbp+57h+var_A0], 0
0x18001db82  mov     rcx, rbx; this
0x18001db85  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x18001db8a  lea     rdx, [rbp+57h+var_A0]
0x18001db8e  lea     rcx, [rbp+57h+var_60]
0x18001db92  call    ?Next@CSxIter@?$CSxList@VCDfVolumeList@@VCDfVolumeListItem@@@@QEAAJPEAPEAVCDfVolumeListItem@@@Z; CSxList<CDfVolumeList,CDfVolumeListItem>::CSxIter::Next(CDfVolumeListItem * *)
0x18001db97  mov     r11d, eax
0x18001db9a  mov     [rbp+57h+var_98], eax
0x18001db9d  test    eax, eax
0x18001db9f  mov     eax, 0DE7h
0x18001dba4  js      short loc_18001DBB2
0x18001dba6  add     r13, 0D0h
0x18001dbad  jmp     loc_18001DAFD
0x18001dbb2  mov     rbx, [rbp+57h+var_A0]
0x18001dbb6  mov     rdi, [rbp+57h+arg_18]
0x18001dbba  jmp     short loc_18001DC18
0x18001dbbc  mov     rcx, rbx; this
0x18001dbbf  test    rbx, rbx
0x18001dbc2  jz      short loc_18001DBCF
0x18001dbc4  xor     ebx, ebx
0x18001dbc6  mov     [rbp+57h+var_A0], rbx
0x18001dbca  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x18001dbcf  mov     rcx, [rbp+57h+var_58+8]; this
0x18001dbd3  test    rcx, rcx
0x18001dbd6  jz      short loc_18001DBE5
0x18001dbd8  call    ?Release@CDfVolumeList@@QEAAKXZ; CDfVolumeList::Release(void)
0x18001dbdd  mov     [rbp+57h+var_58+8], 0
0x18001dbe5  mov     [rbp+57h+var_58], 0
0x18001dbed  mov     [rbp+57h+var_60], 0
0x18001dbf4  xor     r15d, r15d
0x18001dbf7  mov     [r12], r14d
0x18001dbfb  mov     rdi, [rbp+57h+arg_18]
0x18001dbff  mov     r8, [rbp+57h+arg_10]
0x18001dc03  mov     [r8], rdi
0x18001dc06  mov     [rbp+57h+var_98], r15d
0x18001dc0a  jmp     short loc_18001DC1C
0x18001dc0c  mov     [rbp+57h+var_98], 8000FFFFh
0x18001dc13  mov     eax, 0DD8h
0x18001dc18  mov     [rbp+57h+var_92], ax
0x18001dc1c  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18001dc20  call    cs:__imp_LeaveCriticalSection
0x18001dc26  test    r15d, r15d
0x18001dc29  jz      short loc_18001DC36
0x18001dc2b  mov     r8d, r14d; unsigned int
0x18001dc2e  mov     rdx, rdi; struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *
0x18001dc31  call    ?_DeleteVolumeStatusList@CDefragEngine@@AEAAJPEAU__MIDL___MIDL_itf_dfengine_0000_0000_0007@@K@Z; CDefragEngine::_DeleteVolumeStatusList(__MIDL___MIDL_itf_dfengine_0000_0000_0007 *,ulong)
0x18001dc36  mov     edi, [rbp+57h+var_98]
0x18001dc39  mov     rcx, [rbp+57h+var_58+8]; this
0x18001dc3d  test    rcx, rcx
0x18001dc40  jz      short loc_18001DC48
0x18001dc42  call    ?Release@CDfVolumeList@@QEAAKXZ; CDfVolumeList::Release(void)
0x18001dc47  nop
0x18001dc48  test    rbx, rbx
0x18001dc4b  jz      short loc_18001DC56
0x18001dc4d  mov     rcx, rbx; this
0x18001dc50  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x18001dc55  nop
0x18001dc56  test    rsi, rsi
0x18001dc59  jz      short loc_18001DC6B
0x18001dc5b  mov     rcx, [rsi]
0x18001dc5e  mov     rax, [rcx+10h]
0x18001dc62  mov     rcx, rsi
0x18001dc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc6a  nop
0x18001dc6b  lea     rcx, [rbp+57h+var_98]; this
0x18001dc6f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001dc74  mov     eax, edi
0x18001dc76  mov     rbx, [rsp+0C0h+arg_0]
0x18001dc7e  add     rsp, 90h
0x18001dc85  pop     r15
0x18001dc87  pop     r14
0x18001dc89  pop     r13
0x18001dc8b  pop     r12
0x18001dc8d  pop     rdi
0x18001dc8e  pop     rsi
0x18001dc8f  pop     rbp
0x18001dc90  retn
```

# CFLACStream::CreateInstance(CFLACSource *,IMFStreamDescriptor *,CFLACStream * *)

- ea: `0x18002833c`
- end: `0x180028487`
- name: `?CreateInstance@CFLACStream@@SAJPEAVCFLACSource@@PEAUIMFStreamDescriptor@@PEAPEAV1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(struct CFLACSource *, struct IMFStreamDescriptor *, struct CFLACStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180022730`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002823c`
- `0x18002833c`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateEventQueue` at `0x18002843c`
- `MFPlat!MFCreateEventQueue` at `0x18002843c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFLACStream::CreateInstance(
        struct CFLACSource *a1,
        struct IMFStreamDescriptor *a2,
        struct CFLACStream **a3)
{
  int v6; // ecx
  int v7; // r8d
  __int64 v8; // rdx
  __int64 v9; // rbx
  HRESULT v11; // [rsp+80h] [rbp+30h]
  __int64 v12; // [rsp+88h] [rbp+38h] BYREF

  v12 = 0;
  if ( a3 )
  {
    v11 = ATL::CComObject<CFLACStream>::CreateInstance(&v12);
    if ( v11 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        return (unsigned int)v11;
      v8 = 12;
      goto LABEL_4;
    }
    v9 = v12;
    if ( !v12 )
    {
      v11 = -2147024882;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        return (unsigned int)v11;
      v8 = 13;
      goto LABEL_4;
    }
    LODWORD(v12) = 0;
    *(_QWORD *)(v9 + 24) = a1;
    (*(void (__fastcall **)(struct CFLACSource *))(*(_QWORD *)a1 + 8LL))(a1);
    *(_QWORD *)(v9 + 32) = a2;
    ((void (__fastcall *)(struct IMFStreamDescriptor *))a2->lpVtbl->AddRef)(a2);
    v11 = MFCreateEventQueue((IMFMediaEventQueue **)(v9 + 40));
    if ( v11 >= 0 )
    {
      *a3 = (struct CFLACStream *)v9;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      return (unsigned int)v11;
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = 14;
      goto LABEL_4;
    }
  }
  else
  {
    v11 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = (unsigned int)(v7 + 11);
LABEL_4:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_b6551d197bf4350dbd0e8fae33bb32c0_Traceguids, 0, v6);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002833c  mov     [rsp-18h+arg_0], rbx
0x180028341  mov     [rsp-18h+arg_8], rsi
0x180028346  push    rbp
0x180028347  push    rdi
0x180028348  push    r14
0x18002834a  mov     rbp, rsp
0x18002834d  sub     rsp, 50h
0x180028351  mov     rdi, r8
0x180028354  mov     rsi, rdx
0x180028357  mov     r14, rcx
0x18002835a  mov     [rbp+arg_10], 0
0x180028361  mov     [rbp+var_20], 0
0x180028369  lea     rax, [rbp+arg_10]
0x18002836d  mov     [rbp+var_18], rax
0x180028371  mov     [rbp+arg_18], 0
0x180028379  test    r8, r8
0x18002837c  jnz     short loc_1800283BA
0x18002837e  mov     ecx, 80004003h
0x180028383  mov     [rbp+arg_10], ecx
0x180028386  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002838b  cmp     al, 1
0x18002838d  jb      loc_180028471
0x180028393  lea     edx, [r8+0Bh]
0x180028397  mov     [rsp+50h+var_30], ecx
0x18002839b  xor     r9d, r9d
0x18002839e  lea     r8, WPP_b6551d197bf4350dbd0e8fae33bb32c0_Traceguids
0x1800283a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283ac  mov     rcx, [rcx+10h]
0x1800283b0  call    WPP_SF_qd
0x1800283b5  jmp     loc_180028471
0x1800283ba  lea     rcx, [rbp+arg_18]
0x1800283be  call    ?CreateInstance@?$CComObject@VCFLACStream@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFLACStream>::CreateInstance(ATL::CComObject<CFLACStream> * *)
0x1800283c3  mov     ecx, eax
0x1800283c5  mov     [rbp+arg_10], eax
0x1800283c8  test    eax, eax
0x1800283ca  jns     short loc_1800283E0
0x1800283cc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800283d1  cmp     al, 1
0x1800283d3  jb      loc_180028471
0x1800283d9  mov     edx, 0Ch
0x1800283de  jmp     short loc_180028397
0x1800283e0  mov     rbx, [rbp+arg_18]
0x1800283e4  test    rbx, rbx
0x1800283e7  jnz     short loc_1800283FF
0x1800283e9  mov     ecx, 8007000Eh
0x1800283ee  mov     [rbp+arg_10], ecx
0x1800283f1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800283f6  cmp     al, 1
0x1800283f8  jb      short loc_180028471
0x1800283fa  lea     edx, [rbx+0Dh]
0x1800283fd  jmp     short loc_180028397
0x1800283ff  mov     dword ptr [rbp+arg_18], 0
0x180028406  mov     [rbp+var_10], rbx
0x18002840a  lea     rax, [rbp+arg_18]
0x18002840e  mov     [rbp+var_8], rax
0x180028412  mov     [rbx+18h], r14
0x180028416  mov     rax, [r14]
0x180028419  mov     rcx, r14
0x18002841c  mov     rax, [rax+8]
0x180028420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028425  mov     [rbx+20h], rsi
0x180028429  mov     rax, [rsi]
0x18002842c  mov     rcx, rsi
0x18002842f  mov     rax, [rax+8]
0x180028433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028438  lea     rcx, [rbx+28h]; ppMediaEventQueue
0x18002843c  call    cs:__imp_MFCreateEventQueue
0x180028442  mov     ecx, eax
0x180028444  mov     [rbp+arg_10], eax
0x180028447  test    eax, eax
0x180028449  jns     short loc_18002845E
0x18002844b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180028450  cmp     al, 1
0x180028452  jb      short loc_180028471
0x180028454  mov     edx, 0Eh
0x180028459  jmp     loc_180028397
0x18002845e  mov     [rdi], rbx
0x180028461  mov     rax, [rbx]
0x180028464  mov     rcx, rbx
0x180028467  mov     rax, [rax+8]
0x18002846b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028470  nop
0x180028471  mov     eax, [rbp+arg_10]
0x180028474  mov     rbx, [rsp+50h+arg_0]
0x180028479  mov     rsi, [rsp+50h+arg_8]
0x18002847e  add     rsp, 50h
0x180028482  pop     r14
0x180028484  pop     rdi
0x180028485  pop     rbp
0x180028486  retn
```

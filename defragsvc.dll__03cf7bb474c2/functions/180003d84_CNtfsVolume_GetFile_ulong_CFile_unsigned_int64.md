# CNtfsVolume::_GetFile(ulong *,_CFile *,unsigned __int64 *)

- ea: `0x180003d84`
- end: `0x180004449`
- name: `?_GetFile@CNtfsVolume@@AEAAJPEAKPEAU_CFile@@PEA_K@Z`
- size: `1733`
- prototype: `__int64 __fastcall(CNtfsVolume *__hidden this, unsigned int *, struct _CFile *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003c30`
- `0x180005b70`

## callees

- `0x180003a38`
- `0x180003d84`
- `0x180006400`
- `0x18000ad50`
- `0x18000cf94`
- `0x180010d80`
- `0x1800208fc`
- `0x180020dc8`
- `0x180024f20`
- `0x180025268`
- `0x18002e504`
- `0x180034a60`
- `0x1800441ac`
- `0x18004b73c`
- `0x1800620d8`
- `0x180067af2`
- `0x18006a010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000409a`
- `msvcrt!wcsstr` at `0x18000409a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003faa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003faa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800041aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800041aa`

## pseudocode

```c
__int64 __fastcall CNtfsVolume::_GetFile(CNtfsVolume *this, unsigned int *a2, struct _CFile *a3, unsigned __int64 *a4)
{
  int v8; // r14d
  __int64 v9; // rbx
  __int64 v10; // rcx
  struct _CFile *v11; // rax
  __int16 v12; // ax
  int Element; // edi
  unsigned int v14; // r12d
  __int16 v15; // ax
  struct CNtfsFile *v16; // rsi
  __int64 v18; // rcx
  struct CNtfsFile *v19; // rax
  __int64 v20; // rcx
  struct CNtfsFile *v21; // rax
  CNtfsVolume *v22; // rcx
  int v23; // r8d
  wchar_t *v24; // rdi
  struct CNtfsFile *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  struct CNtfsFile *v28; // rax
  struct RETRIEVAL_POINTERS_BUFFER *v29; // rax
  __int64 v30; // rdi
  __int64 v31; // rax
  LPVOID v32; // rax
  bool v33; // zf
  void *v34; // rdi
  unsigned int *v35; // rdx
  int v36; // ecx
  unsigned int v37; // ecx
  int v38; // r9d
  unsigned int *i; // r8
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rcx
  bool v43; // sf
  unsigned __int64 *v44; // [rsp+30h] [rbp-51h]
  int v45; // [rsp+38h] [rbp-49h] BYREF
  __int16 v46; // [rsp+3Ch] [rbp-45h]
  __int16 v47; // [rsp+3Eh] [rbp-43h]
  void *v48; // [rsp+70h] [rbp-11h] BYREF
  __int64 v49; // [rsp+78h] [rbp-9h] BYREF
  __int64 v50; // [rsp+80h] [rbp-1h] BYREF
  struct RETRIEVAL_POINTERS_BUFFER *v51; // [rsp+88h] [rbp+7h] BYREF
  struct CNtfsFile *v52; // [rsp+90h] [rbp+Fh] BYREF
  _QWORD v53[8]; // [rsp+98h] [rbp+17h] BYREF
  unsigned int v56; // [rsp+100h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v45, "CNtfsVolume::_GetFile", 1485, 1);
  v8 = 0;
  v52 = 0;
  v9 = -1;
  v48 = (void *)-1LL;
  v50 = 0;
  v49 = 0;
  v51 = 0;
  v56 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
  {
    v10 = 16;
    v11 = a3;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (struct _CFile *)((char *)v11 + 1);
      --v10;
    }
    while ( v10 );
  }
  if ( a4 )
    *a4 = 0;
  v12 = 1507;
  if ( !a2 || (v46 = 1507, v12 = 1508, !a3) || (v46 = 1508, v12 = 1509, !a4) )
  {
    Element = -2147024809;
LABEL_10:
    v45 = Element;
    v47 = v12;
    goto LABEL_22;
  }
  v45 = 0;
  v46 = 1509;
  Element = CBulkAllocator<CNtfsFile>::Alloc(*((_QWORD *)this + 59), &v56);
  v45 = Element;
  v14 = v56;
  v15 = 1511;
  if ( Element >= 0 )
  {
    v46 = 1511;
    v12 = 1512;
    if ( !v56 )
    {
      Element = -2147024882;
      goto LABEL_10;
    }
    v45 = 0;
    v46 = 1512;
    Element = CBulkAllocator<CNtfsFile>::GetElement(*((_QWORD *)this + 59), &v56, &v52);
    v45 = Element;
    v15 = 1514;
    if ( Element >= 0 )
    {
      v46 = 1514;
      v16 = v52;
      v15 = 1515;
      if ( !v52 )
      {
LABEL_18:
        Element = -2147024882;
        v45 = -2147024882;
        goto LABEL_19;
      }
      v45 = 0;
      v46 = 1515;
      v18 = 40;
      v19 = v52;
      do
      {
        *(_BYTE *)v19 = 0;
        v19 = (struct CNtfsFile *)((char *)v19 + 1);
        --v18;
      }
      while ( v18 );
      while ( 1 )
      {
        if ( *((_DWORD *)this + 96) || *((_WORD *)this + 232) >= 0x10u )
        {
LABEL_48:
          if ( v16 )
          {
            v27 = 40;
            v28 = v16;
            do
            {
              *(_BYTE *)v28 = 0;
              v28 = (struct CNtfsFile *)((char *)v28 + 1);
              --v27;
            }
            while ( v27 );
          }
          while ( 1 )
          {
            Element = (*(__int64 (__fastcall **)(CNtfsVolume *, __int64 *, __int64 *, struct RETRIEVAL_POINTERS_BUFFER **))(*(_QWORD *)this + 408LL))(
                        this,
                        &v50,
                        &v49,
                        &v51);
            v45 = Element;
            v15 = 1581;
            if ( Element < 0 )
              goto LABEL_19;
            v46 = 1581;
            if ( Element == 1 )
            {
              v46 = 1585;
              goto LABEL_20;
            }
            if ( *(_DWORD *)(v50 + 16) == 3 && *(_WORD *)(v50 + 22) == 3 )
            {
              v29 = 0;
              v51 = 0;
            }
            else
            {
              v29 = v51;
            }
            if ( v29 )
            {
              *((_QWORD *)v16 + 2) = *(_QWORD *)(v50 + 16);
              v30 = v49;
              v31 = *(unsigned int *)(v49 + 44);
              if ( (_DWORD)v31 )
              {
                v32 = CoTaskMemAlloc(v31 + 2);
                *((_QWORD *)v16 + 3) = v32;
                v33 = v32 == 0;
                v15 = 1610;
                if ( v33 )
                  goto LABEL_18;
                v45 = 0;
                v46 = 1610;
                v34 = (void *)*((_QWORD *)v16 + 3);
                memcpy_0(v34, (const void *)(v49 + 48), *(unsigned int *)(v49 + 44));
                *((_WORD *)v34 + ((unsigned __int64)*(unsigned int *)(v49 + 44) >> 1)) = 0;
                v30 = v49;
              }
              else
              {
                v8 = 1;
              }
              v53[0] = *((_QWORD *)v16 + 2);
              v53[1] = *((_QWORD *)v16 + 3);
              if ( *(_QWORD *)std::_Tree<std::_Tset_traits<CNtfsStreamName,std::less<CNtfsStreamName>,std::allocator<CNtfsStreamName>,0>>::find(
                                (char *)this + 584,
                                &v52,
                                v53) == *((_QWORD *)this + 74) )
              {
                if ( (*(_BYTE *)(v30 + 8) & 3) != 0 )
                  *((_DWORD *)v16 + 1) |= 1u;
                v35 = (unsigned int *)((char *)v16 + 4);
                v36 = *((_DWORD *)v16 + 1);
                if ( (*(_BYTE *)(v50 + 12) & 0x10) != 0 )
                  v37 = v36 | 4;
                else
                  v37 = v36 & 0xFFFFFFFB;
                *((_DWORD *)v16 + 1) = v37;
                if ( (*(_DWORD *)(v50 + 12) & 0x800) != 0 )
                  *v35 = v37 | 2;
                else
                  *v35 = v37 & 0xFFFFFFFD;
                goto LABEL_71;
              }
              goto LABEL_48;
            }
          }
        }
        if ( v16 )
        {
          v20 = 40;
          v21 = v16;
          do
          {
            *(_BYTE *)v21 = 0;
            v21 = (struct CNtfsFile *)((char *)v21 + 1);
            --v20;
          }
          while ( v20 );
        }
        *((_WORD *)v16 + 16) = ++*((_WORD *)this + 232);
        if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle((HANDLE)v9);
          v48 = (void *)-1LL;
        }
        Element = CNtfsVolume::_GetHandleToFile(this, v16, &v48);
        if ( Element >= 0 )
          break;
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_IS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *((unsigned __int16 *)this + 232),
            v23,
            *((_DWORD *)v16 + 4),
            (__int64)off_18006D5B0[*((unsigned __int16 *)this + 232) - 1]);
        }
        if ( v16 )
          *((_DWORD *)v16 + 1) |= 0x41u;
        v9 = (__int64)v48;
        if ( Element != -1996488674 )
        {
          v45 = Element;
          v15 = 1541;
          goto LABEL_19;
        }
      }
      v9 = (__int64)v48;
      Element = CNtfsVolume::_GetFRNFromHandle(v22, v48, (struct CNtfsFile *)((char *)v16 + 16));
      v45 = Element;
      v15 = 1547;
      if ( Element < 0 )
        goto LABEL_19;
      v46 = 1547;
      if ( Element == 1 )
      {
        Element = -1996488674;
        v45 = -1996488674;
        v15 = 1550;
        goto LABEL_19;
      }
      v24 = wcsstr(off_18006D5B0[*((unsigned __int16 *)v16 + 16) - 1], L":");
      v25 = (struct CNtfsFile *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v52 = v25;
      if ( !v25 )
      {
        Element = -2147024882;
        v45 = -2147024882;
        v47 = 1558;
        goto LABEL_20;
      }
      *(_QWORD *)v25 = *((_QWORD *)v16 + 2);
      *((_QWORD *)v25 + 1) = v24;
      v8 = 0;
      v45 = 0;
      v46 = 1558;
      v26 = std::_Tree_val<std::_Tset_traits<CNtfsStreamName,std::less<CNtfsStreamName>,std::allocator<CNtfsStreamName>,0>>::_Buynode<CNtfsStreamName &>(
              (char *)this + 584,
              v25);
      std::_Tree<std::_Tset_traits<CNtfsStreamName,std::less<CNtfsStreamName>,std::allocator<CNtfsStreamName>,0>>::_Linsert(
        (char *)this + 584,
        v53,
        v26);
LABEL_71:
      v38 = 0;
      for ( i = (unsigned int *)*((_QWORD *)this + 72); i && !v38; i = (unsigned int *)*((_QWORD *)i + 1) )
      {
        if ( (*i | ((unsigned __int64)*((unsigned __int16 *)i + 2) << 32)) == (*((unsigned int *)v16 + 4)
                                                                             | ((unsigned __int64)*((unsigned __int16 *)v16
                                                                                                  + 10) << 32)) )
        {
          if ( v16 )
            *((_DWORD *)v16 + 1) |= 0x20u;
          v38 = 1;
        }
      }
      v40 = *((unsigned int *)v16 + 4) | ((unsigned __int64)*((unsigned __int16 *)v16 + 10) << 32);
      if ( v40 )
      {
        v41 = v40 - 1;
        if ( !v41 || (v42 = v41 - 1) == 0 || v42 == 4 )
        {
          if ( v16 )
            *((_DWORD *)v16 + 1) |= 1u;
        }
      }
      else
      {
        if ( !*((_DWORD *)this + 96) && v16 )
          *((_DWORD *)v16 + 1) |= 1u;
        if ( v8 )
        {
          if ( !v16 )
            goto LABEL_93;
          *((_DWORD *)v16 + 1) |= 0x80u;
        }
        if ( v16 )
          *((_DWORD *)v16 + 1) |= 0x110u;
      }
LABEL_93:
      if ( (unsigned __int16)(*((_WORD *)v16 + 16) - 7) <= 2u && v16 )
        *((_DWORD *)v16 + 1) |= 1u;
      v44 = (unsigned __int64 *)((char *)v16 + 8);
      if ( *((_WORD *)v16 + 16) )
      {
        Element = CVolume::_ScanExtents(this, (void *)v9, 0, v14, (unsigned int *)v16, v44);
        v45 = Element;
        v43 = Element < 0;
        v15 = 1729;
      }
      else
      {
        Element = CVolume::_ScanExtents(this, (void *)0xFFFFFFFFFFFFFFFFLL, v51, v14, (unsigned int *)v16, v44);
        v45 = Element;
        v43 = Element < 0;
        v15 = 1733;
      }
      if ( !v43 )
      {
        v46 = v15;
        if ( Element == 150995200 )
        {
          if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
          {
            WPP_SF_i(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              WPP_e997f3a212193354f3db96f04e525e21_Traceguids,
              *((unsigned int *)v16 + 4) | ((unsigned __int64)*((unsigned __int16 *)v16 + 10) << 32));
          }
          if ( v16 )
            *((_DWORD *)v16 + 1) |= 0x41u;
        }
        *a4 = *((unsigned int *)v16 + 4) | ((unsigned __int64)*((unsigned __int16 *)v16 + 10) << 32);
        *(_OWORD *)a3 = *(_OWORD *)v16;
        *a2 = v14;
        v14 = 0;
        v56 = 0;
        Element = 0;
        v45 = 0;
        goto LABEL_20;
      }
    }
  }
LABEL_19:
  v47 = v15;
LABEL_20:
  if ( v14 )
  {
    CBulkAllocator<CNtfsFile>::Free(*((_QWORD *)this + 59), &v56);
    Element = v45;
  }
LABEL_22:
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v9);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v45);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180003d84  mov     rax, rsp
0x180003d87  mov     [rax+8], rbx
0x180003d8b  mov     [rax+18h], r8
0x180003d8f  mov     [rax+10h], rdx
0x180003d93  push    rbp
0x180003d94  push    rsi
0x180003d95  push    rdi
0x180003d96  push    r12
0x180003d98  push    r13
0x180003d9a  push    r14
0x180003d9c  push    r15
0x180003d9e  lea     rbp, [rax-5Fh]
0x180003da2  sub     rsp, 0A0h
0x180003da9  mov     r13, r9
0x180003dac  mov     rdi, r8
0x180003daf  mov     rsi, rdx
0x180003db2  mov     r15, rcx
0x180003db5  mov     r12d, 1
0x180003dbb  mov     r9d, r12d; unsigned __int16
0x180003dbe  mov     r8d, 5CDh; unsigned __int16
0x180003dc4  lea     rdx, aCntfsvolumeGet_13; "CNtfsVolume::_GetFile"
0x180003dcb  lea     rcx, [rbp+57h+var_A0]; this
0x180003dcf  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180003dd4  nop
0x180003dd5  xor     r14d, r14d
0x180003dd8  mov     [rbp+57h+var_48], r14
0x180003ddc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003de0  mov     [rbp+57h+var_68], rbx
0x180003de4  mov     [rbp+57h+var_58], r14
0x180003de8  mov     [rbp+57h+var_60], r14
0x180003dec  mov     [rbp+57h+var_50], r14
0x180003df0  mov     [rbp+57h+arg_18], r14d
0x180003df4  test    rsi, rsi
0x180003df7  jz      short loc_180003DFC
0x180003df9  mov     [rsi], r14d
0x180003dfc  test    rdi, rdi
0x180003dff  jz      short loc_180003E14
0x180003e01  mov     ecx, 10h
0x180003e06  mov     rax, rdi
0x180003e09  mov     [rax], r14b
0x180003e0c  add     rax, r12
0x180003e0f  sub     rcx, r12
0x180003e12  jnz     short loc_180003E09
0x180003e14  test    r13, r13
0x180003e17  jz      short loc_180003E1D
0x180003e19  mov     [r13+0], r14
0x180003e1d  mov     eax, 5E3h
0x180003e22  test    rsi, rsi
0x180003e25  jnz     short loc_180003E38
0x180003e27  mov     edi, 80070057h
0x180003e2c  mov     [rbp+57h+var_A0], edi
0x180003e2f  mov     [rbp+57h+var_9A], ax
0x180003e33  jmp     loc_180003EF3
0x180003e38  mov     [rbp+57h+var_9C], ax
0x180003e3c  mov     eax, 5E4h
0x180003e41  test    rdi, rdi
0x180003e44  jz      short loc_180003E27
0x180003e46  mov     [rbp+57h+var_9C], ax
0x180003e4a  mov     eax, 5E5h
0x180003e4f  test    r13, r13
0x180003e52  jz      short loc_180003E27
0x180003e54  mov     [rbp+57h+var_A0], r14d
0x180003e58  mov     [rbp+57h+var_9C], ax
0x180003e5c  lea     rdx, [rbp+57h+arg_18]
0x180003e60  mov     rcx, [r15+1D8h]
0x180003e67  call    ?Alloc@?$CBulkAllocator@VCNtfsFile@@@@QEAAJPEAK@Z; CBulkAllocator<CNtfsFile>::Alloc(ulong *)
0x180003e6c  mov     edi, eax
0x180003e6e  mov     [rbp+57h+var_A0], eax
0x180003e71  mov     r12d, [rbp+57h+arg_18]
0x180003e75  test    eax, eax
0x180003e77  mov     eax, 5E7h
0x180003e7c  js      short loc_180003ED7
0x180003e7e  mov     [rbp+57h+var_9C], ax
0x180003e82  mov     eax, 5E8h
0x180003e87  test    r12d, r12d
0x180003e8a  jnz     short loc_180003E93
0x180003e8c  mov     edi, 8007000Eh
0x180003e91  jmp     short loc_180003E2C
0x180003e93  mov     [rbp+57h+var_A0], r14d
0x180003e97  mov     [rbp+57h+var_9C], ax
0x180003e9b  lea     r8, [rbp+57h+var_48]
0x180003e9f  lea     rdx, [rbp+57h+arg_18]
0x180003ea3  mov     rcx, [r15+1D8h]
0x180003eaa  call    ?GetElement@?$CBulkAllocator@VCNtfsFile@@@@QEAAJPEAKPEAPEAVCNtfsFile@@@Z; CBulkAllocator<CNtfsFile>::GetElement(ulong *,CNtfsFile * *)
0x180003eaf  mov     edi, eax
0x180003eb1  mov     [rbp+57h+var_A0], eax
0x180003eb4  test    eax, eax
0x180003eb6  mov     eax, 5EAh
0x180003ebb  js      short loc_180003ED7
0x180003ebd  mov     [rbp+57h+var_9C], ax
0x180003ec1  mov     rsi, [rbp+57h+var_48]
0x180003ec5  mov     eax, 5EBh
0x180003eca  test    rsi, rsi
0x180003ecd  jnz     short loc_180003F2D
0x180003ecf  mov     edi, 8007000Eh
0x180003ed4  mov     [rbp+57h+var_A0], edi
0x180003ed7  mov     [rbp+57h+var_9A], ax
0x180003edb  test    r12d, r12d
0x180003ede  jz      short loc_180003EF3
0x180003ee0  lea     rdx, [rbp+57h+arg_18]
0x180003ee4  mov     rcx, [r15+1D8h]
0x180003eeb  call    ?Free@?$CBulkAllocator@VCNtfsFile@@@@QEAAJPEAK@Z; CBulkAllocator<CNtfsFile>::Free(ulong *)
0x180003ef0  mov     edi, [rbp+57h+var_A0]
0x180003ef3  lea     rcx, [rbx-1]
0x180003ef7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180003efb  ja      short loc_180003F07
0x180003efd  mov     rcx, rbx; hObject
0x180003f00  call    cs:__imp_CloseHandle
0x180003f06  nop
0x180003f07  lea     rcx, [rbp+57h+var_A0]; this
0x180003f0b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180003f10  mov     eax, edi
0x180003f12  mov     rbx, [rsp+0D0h+arg_0]
0x180003f1a  add     rsp, 0A0h
0x180003f21  pop     r15
0x180003f23  pop     r14
0x180003f25  pop     r13
0x180003f27  pop     r12
0x180003f29  pop     rdi
0x180003f2a  pop     rsi
0x180003f2b  pop     rbp
0x180003f2c  retn
0x180003f2d  mov     [rbp+57h+var_A0], r14d
0x180003f31  mov     [rbp+57h+var_9C], ax
0x180003f35  mov     edx, 1
0x180003f3a  test    rsi, rsi
0x180003f3d  jz      short loc_180003F50
0x180003f3f  lea     ecx, [rdx+27h]
0x180003f42  mov     rax, rsi
0x180003f45  mov     [rax], r14b
0x180003f48  add     rax, rdx
0x180003f4b  sub     rcx, rdx
0x180003f4e  jnz     short loc_180003F45
0x180003f50  cmp     [r15+180h], r14d
0x180003f57  jnz     loc_180004119
0x180003f5d  mov     eax, 10h
0x180003f62  cmp     [r15+1D0h], ax
0x180003f6a  jnb     loc_180004119
0x180003f70  test    rsi, rsi
0x180003f73  jz      short loc_180003F86
0x180003f75  lea     ecx, [rax+18h]
0x180003f78  mov     rax, rsi
0x180003f7b  mov     [rax], r14b
0x180003f7e  add     rax, rdx
0x180003f81  sub     rcx, rdx
0x180003f84  jnz     short loc_180003F7B
0x180003f86  movzx   eax, word ptr [r15+1D0h]
0x180003f8e  add     ax, dx
0x180003f91  mov     [rsi+20h], ax
0x180003f95  add     [r15+1D0h], dx
0x180003f9d  lea     rax, [rbx-1]
0x180003fa1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003fa5  ja      short loc_180003FB8
0x180003fa7  mov     rcx, rbx; hObject
0x180003faa  call    cs:__imp_CloseHandle
0x180003fb0  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFFh
0x180003fb8  lea     r8, [rbp+57h+var_68]; void **
0x180003fbc  mov     rdx, rsi; struct CNtfsFile *
0x180003fbf  mov     rcx, r15; this
0x180003fc2  call    ?_GetHandleToFile@CNtfsVolume@@AEAAJPEAVCNtfsFile@@PEAPEAX@Z; CNtfsVolume::_GetHandleToFile(CNtfsFile *,void * *)
0x180003fc7  mov     edi, eax
0x180003fc9  test    eax, eax
0x180003fcb  jns     short loc_180004046
0x180003fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fd4  lea     rax, WPP_GLOBAL_Control
0x180003fdb  cmp     rcx, rax
0x180003fde  jz      short loc_18000401A
0x180003fe0  test    dword ptr [rcx+1Ch], 2000000h
0x180003fe7  jz      short loc_18000401A
0x180003fe9  movzx   edx, word ptr [r15+1D0h]
0x180003ff1  movzx   r9d, word ptr [rsi+14h]
0x180003ff6  shl     r9, 20h
0x180003ffa  mov     eax, [rsi+10h]
0x180003ffd  or      r9, rax
0x180004000  lea     rax, off_18006D5B0; "$Secure::$ATTRIBUTE_LIST"
0x180004007  mov     rax, [rax+rdx*8-8]
0x18000400c  mov     [rsp+0D0h+var_B0], rax
0x180004011  mov     rcx, [rcx+10h]
0x180004015  call    WPP_SF_IS
0x18000401a  test    rsi, rsi
0x18000401d  jz      short loc_180004023
0x18000401f  or      dword ptr [rsi+4], 41h
0x180004023  mov     rbx, [rbp+57h+var_68]
0x180004027  cmp     edi, 8900001Eh
0x18000402d  jnz     short loc_180004039
0x18000402f  mov     edx, 1
0x180004034  jmp     loc_180003F50
0x180004039  mov     [rbp+57h+var_A0], edi
0x18000403c  mov     eax, 605h
0x180004041  jmp     loc_180003ED7
0x180004046  lea     r8, [rsi+10h]; struct FILE_REFERENCE *
0x18000404a  mov     rbx, [rbp+57h+var_68]
0x18000404e  mov     rdx, rbx; void *
0x180004051  call    ?_GetFRNFromHandle@CNtfsVolume@@AEAAJPEAXPEAUFILE_REFERENCE@@@Z; CNtfsVolume::_GetFRNFromHandle(void *,FILE_REFERENCE *)
0x180004056  mov     edi, eax
0x180004058  mov     [rbp+57h+var_A0], eax
0x18000405b  test    eax, eax
0x18000405d  mov     eax, 60Bh
0x180004062  js      loc_180003ED7
0x180004068  mov     [rbp+57h+var_9C], ax
0x18000406c  cmp     edi, 1
0x18000406f  jnz     short loc_180004083
0x180004071  mov     edi, 8900001Eh
0x180004076  mov     [rbp+57h+var_A0], edi
0x180004079  mov     eax, 60Eh
0x18000407e  jmp     loc_180003ED7
0x180004083  movzx   ecx, word ptr [rsi+20h]
0x180004087  lea     rdx, SubStr; ":"
0x18000408e  lea     rax, off_18006D5B0; "$Secure::$ATTRIBUTE_LIST"
0x180004095  mov     rcx, [rax+rcx*8-8]; Str
0x18000409a  call    cs:__imp_wcsstr
0x1800040a0  mov     rdi, rax
0x1800040a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800040aa  mov     ecx, 10h; unsigned __int64
0x1800040af  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800040b4  mov     [rbp+57h+var_48], rax
0x1800040b8  test    rax, rax
0x1800040bb  jz      short loc_180004103
0x1800040bd  mov     rcx, [rsi+10h]
0x1800040c1  mov     [rax], rcx
0x1800040c4  mov     [rax+8], rdi
0x1800040c8  xor     r14d, r14d
0x1800040cb  test    rax, rax
0x1800040ce  jz      short loc_180004103
0x1800040d0  mov     [rbp+57h+var_A0], r14d
0x1800040d4  mov     ecx, 616h
0x1800040d9  mov     [rbp+57h+var_9C], cx
0x1800040dd  lea     rdi, [r15+248h]
0x1800040e4  mov     rdx, rax
0x1800040e7  mov     rcx, rdi
0x1800040ea  call    ??$_Buynode@AEAVCNtfsStreamName@@@?$_Tree_val@V?$_Tset_traits@VCNtfsStreamName@@U?$less@VCNtfsStreamName@@@std@@V?$allocator@VCNtfsStreamName@@@3@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@VCNtfsStreamName@@U?$less@VCNtfsStreamName@@@std@@V?$allocator@VCNtfsStreamName@@@3@$0A@@std@@@1@AEAVCNtfsStreamName@@@Z; std::_Tree_val<std::_Tset_traits<CNtfsStreamName,std::less<CNtfsStreamName>,std::allocator<CNtfsStreamName>,0>>::_Buynode<CNtfsStreamName &>(CNtfsStreamName &)
0x1800040ef  mov     r8, rax
0x1800040f2  lea     rdx, [rbp+57h+var_40]
0x1800040f6  mov     rcx, rdi
0x1800040f9  call    ?_Linsert@?$_Tree@V?$_Tset_traits@VCNtfsStreamName@@U?$less@VCNtfsStreamName@@@std@@V?$allocator@VCNtfsStreamName@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@VCNtfsStreamName@@U?$less@VCNtfsStreamName@@@std@@V?$allocator@VCNtfsStreamName@@@3@$0A@@std@@@std@@@std@@_N@2@PEAU_Node@?$_Tree_nod@V?$_Tset_traits@VCNtfsStreamName@@U?$less@VCNtfsStreamName@@@std@@V?$allocator@VCNtfsStreamName@@@3@$0A@@std@@@2@_N@Z; std::_Tree<std::_Tset_traits<CNtfsStreamName,std::less<CNtfsStreamName>,std::allocator<CNtfsStreamName>,0>>::_Linsert(std::_Tree_nod<std::_Tset_traits<CNtfsStreamName,std::less<CNtfsStreamName>,std::allocator<CNtfsStreamName>,0>>::_Node *,bool)
0x1800040fe  jmp     loc_180004288
0x180004103  mov     edi, 8007000Eh
0x180004108  mov     [rbp+57h+var_A0], edi
0x18000410b  mov     ecx, 616h
0x180004110  mov     [rbp+57h+var_9A], cx
0x180004114  jmp     loc_180003EDB
0x180004119  test    rsi, rsi
0x18000411c  jz      short loc_180004131
0x18000411e  mov     ecx, 28h ; '('
0x180004123  mov     rax, rsi
0x180004126  mov     byte ptr [rax], 0
0x180004129  add     rax, rdx
0x18000412c  sub     rcx, rdx
0x18000412f  jnz     short loc_180004126
0x180004131  mov     rax, [r15]
0x180004134  lea     r9, [rbp+57h+var_50]
0x180004138  lea     r8, [rbp+57h+var_60]
0x18000413c  lea     rdx, [rbp+57h+var_58]
0x180004140  mov     rcx, r15
0x180004143  mov     rax, [rax+198h]
0x18000414a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000414f  mov     edi, eax
0x180004151  mov     [rbp+57h+var_A0], eax
0x180004154  test    eax, eax
0x180004156  mov     eax, 62Dh
0x18000415b  js      loc_180003ED7
0x180004161  mov     [rbp+57h+var_9C], ax
0x180004165  cmp     edi, 1
0x180004168  jz      loc_18000443A
0x18000416e  mov     rcx, [rbp+57h+var_58]
0x180004172  mov     eax, 3
0x180004177  cmp     [rcx+10h], eax
0x18000417a  jnz     short loc_18000418A
0x18000417c  cmp     [rcx+16h], ax
0x180004180  jnz     short loc_18000418A
0x180004182  xor     eax, eax
0x180004184  mov     [rbp+57h+var_50], rax
0x180004188  jmp     short loc_18000418E
0x18000418a  mov     rax, [rbp+57h+var_50]
0x18000418e  test    rax, rax
0x180004191  jz      short loc_180004131
0x180004193  mov     rax, [rcx+10h]
0x180004197  mov     [rsi+10h], rax
0x18000419b  mov     rdi, [rbp+57h+var_60]
0x18000419f  mov     eax, [rdi+2Ch]
0x1800041a2  test    eax, eax
0x1800041a4  jz      short loc_1800041FB
0x1800041a6  lea     rcx, [rax+2]; cb
0x1800041aa  call    cs:__imp_CoTaskMemAlloc
0x1800041b0  mov     [rsi+18h], rax
0x1800041b4  test    rax, rax
0x1800041b7  mov     eax, 64Ah
0x1800041bc  jz      loc_180003ECF
0x1800041c2  mov     [rbp+57h+var_A0], 0
0x1800041c9  mov     [rbp+57h+var_9C], ax
0x1800041cd  mov     rdi, [rsi+18h]
0x1800041d1  mov     rdx, [rbp+57h+var_60]
0x1800041d5  mov     r8d, [rdx+2Ch]; Size
0x1800041d9  add     rdx, 30h ; '0'; Src
0x1800041dd  mov     rcx, rdi; void *
0x1800041e0  call    memcpy_0
0x1800041e5  mov     rax, [rbp+57h+var_60]
0x1800041e9  mov     ecx, [rax+2Ch]
0x1800041ec  shr     rcx, 1
0x1800041ef  xor     eax, eax
  ... truncated ...
```

# Imapi2Utility::GetSupportedWriteSpeedDescriptors(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,tagSAFEARRAY * *)

- ea: `0x180044698`
- end: `0x180044996`
- name: `?GetSupportedWriteSpeedDescriptors@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2 *, enum _IMAPI_MEDIA_PHYSICAL_TYPE, struct tagSAFEARRAY **)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800222d0`
- `0x180031d10`
- `0x18003b360`

## callees

- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x18001cb0c`
- `0x180042ae0`
- `0x1800433d4`
- `0x180044698`
- `0x18004a010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180044787`
- `KERNEL32!LocalAlloc` at `0x180044787`
- `KERNEL32!LocalFree` at `0x1800448c8`
- `KERNEL32!LocalFree` at `0x180044911`
- `KERNEL32!LocalFree` at `0x180044928`
- `KERNEL32!LocalFree` at `0x1800448c8`
- `KERNEL32!LocalFree` at `0x180044911`
- `KERNEL32!LocalFree` at `0x180044928`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::GetSupportedWriteSpeedDescriptors(
        void (__fastcall ***this)(Imapi2Utility *, GUID *, __int64 *),
        struct IDiscRecorder2 *a2,
        _QWORD *a3,
        struct tagSAFEARRAY **a4)
{
  int v5; // ebx
  int v6; // eax
  LONGLONG *v7; // r14
  __int64 v8; // rsi
  int v9; // eax
  int VariantSafeArrayFromIDispatch; // eax
  unsigned int v11; // eax
  __int64 i; // rsi
  LONGLONG v13; // rcx
  __int64 j; // rsi
  __int64 v15; // rcx
  HLOCAL v17; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v18[2]; // [rsp+38h] [rbp-8h] BYREF
  struct IDispatch **v19; // [rsp+80h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+48h] BYREF

  hMem = 0;
  v17 = 0;
  LODWORD(v19) = 0;
  *(_QWORD *)v18 = 0;
  if ( a3 )
  {
    v6 = Imapi2Utility::BuildSupportedDescriptorArray(
           this,
           a2,
           &hMem,
           (struct IWriteSpeedDescriptor ***)&v17,
           (unsigned int **)&v19);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = (LONGLONG *)LocalAlloc(0x40u, 8LL * (unsigned int)v19);
      if ( v7 )
      {
        v8 = 0;
        while ( (unsigned int)v8 < (unsigned int)v19 )
        {
          v9 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64))hMem + v8))(
                 *((_QWORD *)hMem + v8),
                 &GUID_00020400_0000_0000_c000_000000000046,
                 (__int64)&v7[v8]);
          v5 = v9;
          if ( v9 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              123,
              &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
              (unsigned int)v8,
              v9);
            goto LABEL_31;
          }
          v8 = (unsigned int)(v8 + 1);
          if ( v9 < 0 )
            goto LABEL_31;
        }
        VariantSafeArrayFromIDispatch = Imapi2Utility::CreateVariantSafeArrayFromIDispatch(
                                          v7,
                                          (struct IDispatch **)(unsigned int)v19,
                                          (SAFEARRAY **)v18,
                                          a4);
        v5 = VariantSafeArrayFromIDispatch;
        if ( VariantSafeArrayFromIDispatch < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            124,
            &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
            (unsigned int)VariantSafeArrayFromIDispatch);
        }
LABEL_31:
        v11 = (unsigned int)v19;
        for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
        {
          v13 = v7[i];
          if ( v13 )
          {
            (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v13 + 16LL))(v13);
            v7[i] = 0;
            v11 = (unsigned int)v19;
          }
        }
        LocalFree(v7);
      }
      else
      {
        v5 = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            122,
            &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
            (unsigned int)v19,
            (_DWORD)v19);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        121,
        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        (unsigned int)v6);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
    }
    v5 = -2147467261;
  }
  if ( hMem )
  {
    for ( j = 0; (unsigned int)j < (unsigned int)v19; j = (unsigned int)(j + 1) )
    {
      v15 = *((_QWORD *)hMem + j);
      if ( v15 )
      {
        (*(void (__fastcall **)(__int64, struct IDiscRecorder2 *, _QWORD *, struct tagSAFEARRAY **))(*(_QWORD *)v15 + 16LL))(
          v15,
          a2,
          a3,
          a4);
        *((_QWORD *)hMem + j) = 0;
      }
    }
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
  }
  if ( v17 )
  {
    LocalFree(v17);
    v17 = 0;
  }
  if ( v5 < 0 )
  {
    Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)v18, (struct tagSAFEARRAY **)a2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        125,
        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        (unsigned int)v5);
    }
  }
  else
  {
    *a3 = *(_QWORD *)v18;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180044698  mov     [rsp-28h+arg_0], rbx
0x18004469d  mov     [rsp-28h+arg_8], rsi
0x1800446a2  push    rbp
0x1800446a3  push    rdi
0x1800446a4  push    r12
0x1800446a6  push    r14
0x1800446a8  push    r15
0x1800446aa  mov     rbp, rsp
0x1800446ad  sub     rsp, 40h
0x1800446b1  mov     [rbp+hMem], 0
0x1800446b9  mov     r12, r8
0x1800446bc  mov     [rbp+var_10], 0
0x1800446c4  mov     r15b, 4
0x1800446c7  mov     dword ptr [rbp+arg_10], 0
0x1800446ce  lea     rsi, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800446d5  mov     qword ptr [rbp+var_8], 0
0x1800446dd  test    r8, r8
0x1800446e0  jnz     short loc_18004471B
0x1800446e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446e9  lea     rdi, WPP_GLOBAL_Control
0x1800446f0  cmp     rcx, rdi
0x1800446f3  jz      short loc_180044711
0x1800446f5  test    [rcx+1Ch], r15b
0x1800446f9  jz      short loc_180044711
0x1800446fb  cmp     byte ptr [rcx+19h], 3
0x1800446ff  jb      short loc_180044711
0x180044701  mov     rcx, [rcx+10h]
0x180044705  lea     edx, [r8+78h]
0x180044709  mov     r8, rsi
0x18004470c  call    WPP_SF_
0x180044711  mov     ebx, 80004003h
0x180044716  jmp     loc_1800448CE
0x18004471b  lea     rax, [rbp+arg_10]
0x18004471f  lea     r9, [rbp+var_10]; struct IWriteSpeedDescriptor ***
0x180044723  mov     [rsp+40h+var_20], rax; unsigned int **
0x180044728  lea     r8, [rbp+hMem]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x18004472c  call    ?BuildSupportedDescriptorArray@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAPEAPEAUIWriteSpeedDescriptor@@PEAPEAKPEAK@Z; Imapi2Utility::BuildSupportedDescriptorArray(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,IWriteSpeedDescriptor * * *,ulong * *,ulong *)
0x180044731  mov     ebx, eax
0x180044733  test    eax, eax
0x180044735  jns     short loc_18004477B
0x180044737  mov     rcx, cs:WPP_GLOBAL_Control
0x18004473e  lea     rdi, WPP_GLOBAL_Control
0x180044745  cmp     rcx, rdi
0x180044748  jz      loc_1800448CE
0x18004474e  test    [rcx+1Ch], r15b
0x180044752  jz      loc_1800448CE
0x180044758  cmp     byte ptr [rcx+19h], 3
0x18004475c  jb      loc_1800448CE
0x180044762  mov     rcx, [rcx+10h]
0x180044766  mov     edx, 79h ; 'y'
0x18004476b  mov     r9d, eax
0x18004476e  mov     r8, rsi
0x180044771  call    WPP_SF_d
0x180044776  jmp     loc_1800448CE
0x18004477b  mov     edx, dword ptr [rbp+arg_10]
0x18004477e  mov     ecx, 40h ; '@'; uFlags
0x180044783  shl     rdx, 3; uBytes
0x180044787  call    cs:__imp_LocalAlloc
0x18004478d  mov     r14, rax
0x180044790  test    rax, rax
0x180044793  jnz     short loc_1800447E2
0x180044795  mov     ebx, 8007000Eh
0x18004479a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800447a1  lea     rdi, WPP_GLOBAL_Control
0x1800447a8  cmp     rcx, rdi
0x1800447ab  jz      loc_1800448CE
0x1800447b1  test    [rcx+1Ch], r15b
0x1800447b5  jz      loc_1800448CE
0x1800447bb  cmp     byte ptr [rcx+19h], 3
0x1800447bf  jb      loc_1800448CE
0x1800447c5  mov     r9d, dword ptr [rbp+arg_10]
0x1800447c9  lea     edx, [rax+7Ah]
0x1800447cc  mov     rcx, [rcx+10h]
0x1800447d0  mov     r8, rsi
0x1800447d3  mov     dword ptr [rsp+40h+var_20], r9d
0x1800447d8  call    WPP_SF_Dd
0x1800447dd  jmp     loc_1800448CE
0x1800447e2  xor     esi, esi
0x1800447e4  lea     rdi, WPP_GLOBAL_Control
0x1800447eb  mov     edx, dword ptr [rbp+arg_10]; struct IDispatch **
0x1800447ee  cmp     esi, edx
0x1800447f0  jnb     short loc_180044854
0x1800447f2  mov     rax, [rbp+hMem]
0x1800447f6  lea     r8, [r14+rsi*8]
0x1800447fa  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x180044801  mov     rcx, [rax+rsi*8]
0x180044805  mov     rax, [rcx]
0x180044808  mov     rax, [rax]
0x18004480b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044810  mov     ebx, eax
0x180044812  test    eax, eax
0x180044814  jns     short loc_18004482E
0x180044816  mov     rcx, cs:WPP_GLOBAL_Control
0x18004481d  cmp     rcx, rdi
0x180044820  jz      short loc_18004482E
0x180044822  test    [rcx+1Ch], r15b
0x180044826  jz      short loc_18004482E
0x180044828  cmp     byte ptr [rcx+19h], 3
0x18004482c  jnb     short loc_180044836
0x18004482e  inc     esi
0x180044830  test    eax, eax
0x180044832  jns     short loc_1800447EB
0x180044834  jmp     short loc_180044896
0x180044836  mov     rcx, [rcx+10h]
0x18004483a  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180044841  mov     edx, 7Bh ; '{'
0x180044846  mov     dword ptr [rsp+40h+var_20], eax
0x18004484a  mov     r9d, esi
0x18004484d  call    WPP_SF_Dd
0x180044852  jmp     short loc_180044896
0x180044854  lea     r8, [rbp+var_8]; unsigned int
0x180044858  mov     rcx, r14; this
0x18004485b  call    ?CreateVariantSafeArrayFromIDispatch@Imapi2Utility@@YA?BJPEAPEAUIDispatch@@KPEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::CreateVariantSafeArrayFromIDispatch(IDispatch * *,ulong,tagSAFEARRAY * *)
0x180044860  mov     ebx, eax
0x180044862  test    eax, eax
0x180044864  jns     short loc_180044896
0x180044866  mov     rcx, cs:WPP_GLOBAL_Control
0x18004486d  cmp     rcx, rdi
0x180044870  jz      short loc_180044896
0x180044872  test    [rcx+1Ch], r15b
0x180044876  jz      short loc_180044896
0x180044878  cmp     [rcx+19h], r15b
0x18004487c  jb      short loc_180044896
0x18004487e  mov     rcx, [rcx+10h]
0x180044882  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180044889  mov     edx, 7Ch ; '|'
0x18004488e  mov     r9d, eax
0x180044891  call    WPP_SF_d
0x180044896  mov     eax, dword ptr [rbp+arg_10]
0x180044899  xor     esi, esi
0x18004489b  test    eax, eax
0x18004489d  jz      short loc_1800448C5
0x18004489f  mov     rcx, [r14+rsi*8]
0x1800448a3  test    rcx, rcx
0x1800448a6  jz      short loc_1800448BF
0x1800448a8  mov     rax, [rcx]
0x1800448ab  mov     rax, [rax+10h]
0x1800448af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448b4  mov     qword ptr [r14+rsi*8], 0
0x1800448bc  mov     eax, dword ptr [rbp+arg_10]
0x1800448bf  inc     esi
0x1800448c1  cmp     esi, eax
0x1800448c3  jb      short loc_18004489F
0x1800448c5  mov     rcx, r14; hMem
0x1800448c8  call    cs:__imp_LocalFree
0x1800448ce  cmp     [rbp+hMem], 0
0x1800448d3  jz      short loc_18004491F
0x1800448d5  xor     esi, esi
0x1800448d7  cmp     dword ptr [rbp+arg_10], esi
0x1800448da  jbe     short loc_180044908
0x1800448dc  mov     rax, [rbp+hMem]
0x1800448e0  mov     rcx, [rax+rsi*8]
0x1800448e4  test    rcx, rcx
0x1800448e7  jz      short loc_180044901
0x1800448e9  mov     rax, [rcx]
0x1800448ec  mov     rax, [rax+10h]
0x1800448f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448f5  mov     rax, [rbp+hMem]
0x1800448f9  mov     qword ptr [rax+rsi*8], 0
0x180044901  inc     esi
0x180044903  cmp     esi, dword ptr [rbp+arg_10]
0x180044906  jb      short loc_1800448DC
0x180044908  mov     rcx, [rbp+hMem]; hMem
0x18004490c  test    rcx, rcx
0x18004490f  jz      short loc_18004491F
0x180044911  call    cs:__imp_LocalFree
0x180044917  mov     [rbp+hMem], 0
0x18004491f  mov     rcx, [rbp+var_10]; hMem
0x180044923  test    rcx, rcx
0x180044926  jz      short loc_180044936
0x180044928  call    cs:__imp_LocalFree
0x18004492e  mov     [rbp+var_10], 0
0x180044936  test    ebx, ebx
0x180044938  js      short loc_180044944
0x18004493a  mov     rax, qword ptr [rbp+var_8]
0x18004493e  mov     [r12], rax
0x180044942  jmp     short loc_18004497D
0x180044944  lea     rcx, [rbp+var_8]; this
0x180044948  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18004494d  mov     rcx, cs:WPP_GLOBAL_Control
0x180044954  cmp     rcx, rdi
0x180044957  jz      short loc_18004497D
0x180044959  test    [rcx+1Ch], r15b
0x18004495d  jz      short loc_18004497D
0x18004495f  cmp     [rcx+19h], r15b
0x180044963  jb      short loc_18004497D
0x180044965  mov     rcx, [rcx+10h]
0x180044969  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180044970  mov     edx, 7Dh ; '}'
0x180044975  mov     r9d, ebx
0x180044978  call    WPP_SF_d
0x18004497d  mov     rsi, [rsp+40h+arg_8]
0x180044982  mov     eax, ebx
0x180044984  mov     rbx, [rsp+40h+arg_0]
0x180044989  add     rsp, 40h
0x18004498d  pop     r15
0x18004498f  pop     r14
0x180044991  pop     r12
0x180044993  pop     rdi
0x180044994  pop     rbp
0x180044995  retn
```

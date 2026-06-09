# FheFileOperations::CreateDirectoryPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x1800304a4`
- end: `0x180030789`
- name: `?CreateDirectoryPath@FheFileOperations@@YAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `741`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002f970`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x18000801c`
- `0x180008fa0`
- `0x1800091a4`
- `0x180009258`
- `0x180009920`
- `0x1800099ac`
- `0x18000baa8`
- `0x180028c9c`
- `0x1800304a4`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18003051b`
- `KERNEL32!CreateDirectoryW` at `0x1800306e9`
- `KERNEL32!CreateDirectoryW` at `0x18003051b`
- `KERNEL32!CreateDirectoryW` at `0x1800306e9`
- `KERNEL32!GetLastError` at `0x18003052d`
- `KERNEL32!GetLastError` at `0x1800306fa`
- `KERNEL32!GetLastError` at `0x18003052d`
- `KERNEL32!GetLastError` at `0x1800306fa`

## pseudocode

```c
__int64 __fastcall FheFileOperations::CreateDirectoryPath(__int64 *a1)
{
  volatile signed __int32 *v2; // rcx
  const WCHAR *v3; // rbx
  int *v4; // rdi
  volatile signed __int32 *v5; // rbx
  unsigned int v6; // r14d
  signed int LastError; // eax
  int v8; // eax
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rcx
  int *v11; // rdi
  volatile signed __int32 *v12; // rbx
  signed int v13; // edi
  int v14; // eax
  __int64 v15; // rdx
  volatile signed __int32 *v16; // rcx
  int *v17; // rdi
  volatile signed __int32 *v18; // rbx
  volatile signed __int32 *v19; // rcx
  int *v20; // rdi
  volatile signed __int32 *v21; // rbx
  signed int v22; // eax
  __int64 v24; // [rsp+68h] [rbp+10h] BYREF
  LPCWSTR lpPathName; // [rsp+70h] [rbp+18h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpPathName);
  v2 = (volatile signed __int32 *)(*a1 - 24);
  v3 = lpPathName;
  v4 = (int *)(lpPathName - 12);
  if ( v2 != (volatile signed __int32 *)(lpPathName - 12) )
  {
    if ( v4[4] >= 0 && *(_QWORD *)v2 == *(_QWORD *)v4 )
    {
      v5 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v2);
      ATL::CStringData::Release((ATL::CStringData *)v4);
      v3 = (const WCHAR *)(v5 + 6);
      lpPathName = v3;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&lpPathName, *a1, *(unsigned int *)(*a1 - 16));
      v3 = lpPathName;
    }
  }
  while ( !CreateDirectoryW(v3, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 == -2147024893 )
    {
      v8 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
             &lpPathName,
             92);
      if ( v8 <= 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Empty(&lpPathName);
        v3 = lpPathName;
      }
      else
      {
        v9 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                          &lpPathName,
                          &v24,
                          (unsigned int)v8);
        v10 = (volatile signed __int32 *)(v9 - 24);
        v11 = (int *)(v3 - 12);
        if ( (const WCHAR *)(v9 - 24) != v3 - 12 )
        {
          if ( v11[4] >= 0 && *(_QWORD *)v10 == *(_QWORD *)v11 )
          {
            v12 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v10);
            ATL::CStringData::Release((ATL::CStringData *)v11);
            v3 = (const WCHAR *)(v12 + 6);
            lpPathName = v3;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&lpPathName, v9, *(unsigned int *)(v9 - 16));
            v3 = lpPathName;
          }
        }
        ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
      }
      if ( *((_DWORD *)v3 - 4) )
        continue;
    }
    goto LABEL_20;
  }
  v6 = 0;
LABEL_20:
  v13 = 0;
  if ( v6 != -2147024713 )
    v13 = v6;
  while ( v13 >= 0 )
  {
    if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                          (unsigned __int16 **)&lpPathName,
                          *a1) )
      goto LABEL_43;
    v14 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
            a1,
            92,
            (unsigned int)(*((_DWORD *)v3 - 4) + 1));
    if ( v14 <= 0 )
    {
      v19 = (volatile signed __int32 *)(*a1 - 24);
      v20 = (int *)(v3 - 12);
      if ( v19 != (volatile signed __int32 *)(v3 - 12) )
      {
        if ( v20[4] >= 0 && *(_QWORD *)v19 == *(_QWORD *)v20 )
        {
          v21 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v19);
          ATL::CStringData::Release((ATL::CStringData *)v20);
          v3 = (const WCHAR *)(v21 + 6);
          lpPathName = v3;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&lpPathName, *a1, *(unsigned int *)(*a1 - 16));
          v3 = lpPathName;
        }
      }
    }
    else
    {
      v15 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                         a1,
                         &v24,
                         (unsigned int)v14);
      v16 = (volatile signed __int32 *)(v15 - 24);
      v17 = (int *)(v3 - 12);
      if ( (const WCHAR *)(v15 - 24) != v3 - 12 )
      {
        if ( v17[4] >= 0 && *(_QWORD *)v16 == *(_QWORD *)v17 )
        {
          v18 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v16);
          ATL::CStringData::Release((ATL::CStringData *)v17);
          v3 = (const WCHAR *)(v18 + 6);
          lpPathName = v3;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&lpPathName, v15, *(unsigned int *)(v15 - 16));
          v3 = lpPathName;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
    }
    if ( CreateDirectoryW(v3, 0) )
    {
      v13 = 0;
    }
    else
    {
      v22 = GetLastError();
      v13 = v22;
      if ( v22 > 0 )
        v13 = (unsigned __int16)v22 | 0x80070000;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
      (_DWORD)v3,
      v13);
LABEL_43:
  ATL::CStringData::Release((ATL::CStringData *)(v3 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(*a1 - 24));
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800304a4  mov     [rsp+arg_18], rbx
0x1800304a9  mov     [rsp+arg_0], rcx
0x1800304ae  push    rdi
0x1800304af  push    r14
0x1800304b1  push    r15
0x1800304b3  sub     rsp, 40h
0x1800304b7  mov     r15, rcx
0x1800304ba  lea     rcx, [rsp+58h+lpPathName]
0x1800304bf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800304c4  nop
0x1800304c5  mov     rdx, [r15]
0x1800304c8  lea     rcx, [rdx-18h]
0x1800304cc  mov     rbx, [rsp+58h+lpPathName]
0x1800304d1  lea     rdi, [rbx-18h]
0x1800304d5  cmp     rcx, rdi
0x1800304d8  jz      short loc_180030516
0x1800304da  cmp     dword ptr [rdi+10h], 0
0x1800304de  jl      short loc_180030503
0x1800304e0  mov     rax, [rdi]
0x1800304e3  cmp     [rcx], rax
0x1800304e6  jnz     short loc_180030503
0x1800304e8  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800304ed  mov     rbx, rax
0x1800304f0  mov     rcx, rdi; this
0x1800304f3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800304f8  add     rbx, 18h
0x1800304fc  mov     [rsp+58h+lpPathName], rbx
0x180030501  jmp     short loc_180030516
0x180030503  mov     r8d, [rdx-10h]
0x180030507  lea     rcx, [rsp+58h+lpPathName]
0x18003050c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180030511  mov     rbx, [rsp+58h+lpPathName]
0x180030516  xor     edx, edx; lpSecurityAttributes
0x180030518  mov     rcx, rbx; lpPathName
0x18003051b  call    cs:__imp_CreateDirectoryW
0x180030521  test    eax, eax
0x180030523  jz      short loc_18003052D
0x180030525  xor     r14d, r14d
0x180030528  jmp     loc_1800305E8
0x18003052d  call    cs:__imp_GetLastError
0x180030533  mov     r14d, eax
0x180030536  test    eax, eax
0x180030538  jle     short loc_180030545
0x18003053a  movzx   r14d, ax
0x18003053e  or      r14d, 80070000h
0x180030545  cmp     r14d, 80070003h
0x18003054c  jnz     loc_1800305E8
0x180030552  mov     edx, 5Ch ; '\'
0x180030557  lea     rcx, [rsp+58h+lpPathName]
0x18003055c  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x180030561  lea     rcx, [rsp+58h+lpPathName]
0x180030566  test    eax, eax
0x180030568  jle     short loc_1800305D4
0x18003056a  mov     r8d, eax
0x18003056d  lea     rdx, [rsp+58h+arg_8]
0x180030572  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x180030577  nop
0x180030578  mov     rdx, [rax]
0x18003057b  lea     rcx, [rdx-18h]
0x18003057f  lea     rdi, [rbx-18h]
0x180030583  cmp     rcx, rdi
0x180030586  jz      short loc_1800305C4
0x180030588  cmp     dword ptr [rdi+10h], 0
0x18003058c  jl      short loc_1800305B1
0x18003058e  mov     rax, [rdi]
0x180030591  cmp     [rcx], rax
0x180030594  jnz     short loc_1800305B1
0x180030596  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18003059b  mov     rbx, rax
0x18003059e  mov     rcx, rdi; this
0x1800305a1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800305a6  add     rbx, 18h
0x1800305aa  mov     [rsp+58h+lpPathName], rbx
0x1800305af  jmp     short loc_1800305C4
0x1800305b1  mov     r8d, [rdx-10h]
0x1800305b5  lea     rcx, [rsp+58h+lpPathName]
0x1800305ba  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800305bf  mov     rbx, [rsp+58h+lpPathName]
0x1800305c4  mov     rcx, [rsp+58h+arg_8]
0x1800305c9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800305cd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800305d2  jmp     short loc_1800305DE
0x1800305d4  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800305d9  mov     rbx, [rsp+58h+lpPathName]
0x1800305de  cmp     dword ptr [rbx-10h], 0
0x1800305e2  jnz     loc_180030516
0x1800305e8  xor     edi, edi
0x1800305ea  cmp     r14d, 800700B7h
0x1800305f1  cmovnz  edi, r14d
0x1800305f5  test    edi, edi
0x1800305f7  js      loc_18003071A
0x1800305fd  mov     rdx, [r15]
0x180030600  lea     rcx, [rsp+58h+lpPathName]
0x180030605  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x18003060a  nop
0x18003060b  test    eax, eax
0x18003060d  jz      loc_180030718
0x180030613  mov     r8d, [rbx-10h]
0x180030617  inc     r8d
0x18003061a  mov     edx, 5Ch ; '\'
0x18003061f  mov     rcx, r15
0x180030622  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort,int)
0x180030627  test    eax, eax
0x180030629  jle     short loc_180030698
0x18003062b  mov     r8d, eax
0x18003062e  lea     rdx, [rsp+58h+arg_8]
0x180030633  mov     rcx, r15
0x180030636  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x18003063b  nop
0x18003063c  mov     rdx, [rax]
0x18003063f  lea     rcx, [rdx-18h]
0x180030643  lea     rdi, [rbx-18h]
0x180030647  cmp     rcx, rdi
0x18003064a  jz      short loc_180030688
0x18003064c  cmp     dword ptr [rdi+10h], 0
0x180030650  jl      short loc_180030675
0x180030652  mov     rax, [rdi]
0x180030655  cmp     [rcx], rax
0x180030658  jnz     short loc_180030675
0x18003065a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18003065f  mov     rbx, rax
0x180030662  mov     rcx, rdi; this
0x180030665  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003066a  add     rbx, 18h
0x18003066e  mov     [rsp+58h+lpPathName], rbx
0x180030673  jmp     short loc_180030688
0x180030675  mov     r8d, [rdx-10h]
0x180030679  lea     rcx, [rsp+58h+lpPathName]
0x18003067e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180030683  mov     rbx, [rsp+58h+lpPathName]
0x180030688  mov     rcx, [rsp+58h+arg_8]
0x18003068d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030691  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030696  jmp     short loc_1800306E4
0x180030698  mov     rdx, [r15]
0x18003069b  lea     rcx, [rdx-18h]
0x18003069f  lea     rdi, [rbx-18h]
0x1800306a3  cmp     rcx, rdi
0x1800306a6  jz      short loc_1800306E4
0x1800306a8  cmp     dword ptr [rdi+10h], 0
0x1800306ac  jl      short loc_1800306D1
0x1800306ae  mov     rax, [rdi]
0x1800306b1  cmp     [rcx], rax
0x1800306b4  jnz     short loc_1800306D1
0x1800306b6  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800306bb  mov     rbx, rax
0x1800306be  mov     rcx, rdi; this
0x1800306c1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800306c6  add     rbx, 18h
0x1800306ca  mov     [rsp+58h+lpPathName], rbx
0x1800306cf  jmp     short loc_1800306E4
0x1800306d1  mov     r8d, [rdx-10h]
0x1800306d5  lea     rcx, [rsp+58h+lpPathName]
0x1800306da  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800306df  mov     rbx, [rsp+58h+lpPathName]
0x1800306e4  xor     edx, edx; lpSecurityAttributes
0x1800306e6  mov     rcx, rbx; lpPathName
0x1800306e9  call    cs:__imp_CreateDirectoryW
0x1800306ef  test    eax, eax
0x1800306f1  jz      short loc_1800306FA
0x1800306f3  xor     edi, edi
0x1800306f5  jmp     loc_1800305F5
0x1800306fa  call    cs:__imp_GetLastError
0x180030700  mov     edi, eax
0x180030702  test    eax, eax
0x180030704  jle     loc_1800305F5
0x18003070a  movzx   edi, ax
0x18003070d  or      edi, 80070000h
0x180030713  jmp     loc_1800305F5
0x180030718  jmp     short loc_180030762
0x18003071a  lea     rax, WPP_GLOBAL_Control
0x180030721  mov     rcx, cs:WPP_GLOBAL_Control
0x180030728  cmp     rcx, rax
0x18003072b  jz      short loc_180030750
0x18003072d  test    byte ptr [rcx+1Ch], 1
0x180030731  jz      short loc_180030750
0x180030733  mov     edx, 0Fh
0x180030738  mov     [rsp+58h+var_38], edi
0x18003073c  mov     r9, rbx
0x18003073f  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x180030746  mov     rcx, [rcx+10h]
0x18003074a  call    WPP_SF_Sd
0x18003074f  nop
0x180030750  jmp     short loc_180030762
0x180030752  jmp     short $+2
0x180030754  mov     edi, dword ptr [rsp+58h+arg_8]
0x180030758  mov     rbx, [rsp+58h+lpPathName]
0x18003075d  mov     r15, [rsp+58h+arg_0]
0x180030762  lea     rcx, [rbx-18h]; this
0x180030766  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003076b  nop
0x18003076c  mov     rcx, [r15]
0x18003076f  sub     rcx, 18h; this
0x180030773  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030778  mov     eax, edi
0x18003077a  mov     rbx, [rsp+58h+arg_18]
0x18003077f  add     rsp, 40h
0x180030783  pop     r15
0x180030785  pop     r14
0x180030787  pop     rdi
0x180030788  retn
```

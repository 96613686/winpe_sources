# FheFileOperations::DeleteFileWithEmptyParents(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x180030790`
- end: `0x1800309a3`
- name: `?DeleteFileWithEmptyParents@FheFileOperations@@YAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `531`
- prototype: `__int64 __fastcall(const wchar_t **, const wchar_t **)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18000c450`
- `0x18000cafc`
- `0x180013e14`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x180008fa0`
- `0x1800091a4`
- `0x180009258`
- `0x180009920`
- `0x180021e6c`
- `0x180030790`
- `0x1800309ac`
- `0x18003165a`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x180030871`
- `KERNEL32!RemoveDirectoryW` at `0x180030871`
- `KERNEL32!GetLastError` at `0x18003087b`
- `KERNEL32!GetLastError` at `0x18003087b`

## pseudocode

```c
__int64 __fastcall FheFileOperations::DeleteFileWithEmptyParents(const wchar_t **a1, const wchar_t **a2)
{
  const wchar_t **v2; // r15
  const wchar_t **v3; // r12
  signed int v4; // edi
  signed int v5; // r13d
  const wchar_t *v6; // r14
  const unsigned __int16 *v7; // rdx
  volatile signed __int32 *v8; // rcx
  WCHAR *v9; // rbx
  int *v10; // rsi
  volatile signed __int32 *v11; // rbx
  int v12; // esi
  signed int LastError; // eax
  int v14; // eax
  int v16; // [rsp+30h] [rbp-48h] BYREF
  LPCWSTR lpPathName[8]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+18h]
  signed int v21; // [rsp+90h] [rbp+18h]
  signed int v22; // [rsp+98h] [rbp+20h]

  v2 = a2;
  v3 = a1;
  v4 = 0;
  v5 = 0;
  v22 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)lpPathName);
  v20 = *((_DWORD *)*v2 - 4);
  v6 = *v3;
  if ( wcsncmp_0(*v3, *v2, v20) )
  {
    v4 = -2147024809;
    ATL::CStringData::Release((ATL::CStringData *)(lpPathName[0] - 12));
    goto LABEL_32;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v8 = (volatile signed __int32 *)(v6 - 12);
    v9 = (WCHAR *)lpPathName[0];
    v10 = (int *)(lpPathName[0] - 12);
    if ( v6 - 12 != lpPathName[0] - 12 )
    {
      if ( v10[4] >= 0 && *(_QWORD *)v8 == *(_QWORD *)v10 )
      {
        v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v8);
        ATL::CStringData::Release((ATL::CStringData *)v10);
        v9 = (WCHAR *)(v11 + 6);
        lpPathName[0] = v9;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(lpPathName, v6, *((unsigned int *)v6 - 4));
        v9 = (WCHAR *)lpPathName[0];
      }
    }
    v12 = 0;
    while ( *((_DWORD *)v9 - 4) > (signed int)v20 )
    {
      if ( v12 )
      {
        if ( !RemoveDirectoryW(v9) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        v4 = FheFileOperations::DeleteReadOnlyFile(v9, v7);
      }
      if ( (unsigned int)(v4 + 2147024894) <= 1 )
      {
        if ( v12 )
          v4 = v5;
        v5 = v4;
        v4 = 0;
        v22 = v5;
      }
      else
      {
        if ( v12 > 0 && (v4 == -2147024751 || v4 == -2147024864) )
        {
          v4 = 0;
          break;
        }
        if ( v4 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              (unsigned int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
              (_DWORD)v9,
              v4);
          break;
        }
      }
      v14 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
              lpPathName,
              92);
      if ( v14 < 0 )
        break;
      ATL::CSimpleStringT<unsigned short,0>::Truncate(lpPathName, (unsigned int)v14);
      ++v12;
      v9 = (WCHAR *)lpPathName[0];
    }
    ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v16) )
    {
      v21 = v16;
      if ( v16 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
            (unsigned int)v16);
        v2 = a2;
        v3 = a1;
        v4 = v21;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180030939);
        goto LABEL_32;
      }
      v2 = a2;
      v3 = a1;
      v4 = v16;
      v5 = v22;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180030952);
    }
  }
  if ( v4 >= 0 )
    v4 = v5;
LABEL_32:
  ATL::CStringData::Release((ATL::CStringData *)(*v3 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(*v2 - 12));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180030790  mov     [rsp+arg_8], rdx
0x180030795  mov     [rsp+arg_0], rcx
0x18003079a  push    rbx
0x18003079b  push    rsi
0x18003079c  push    rdi
0x18003079d  push    r12
0x18003079f  push    r13
0x1800307a1  push    r14
0x1800307a3  push    r15
0x1800307a5  sub     rsp, 40h
0x1800307a9  mov     r15, rdx
0x1800307ac  mov     r12, rcx
0x1800307af  xor     edi, edi
0x1800307b1  xor     r13d, r13d
0x1800307b4  mov     [rsp+78h+arg_18], r13d
0x1800307bc  lea     rcx, [rsp+78h+lpPathName]
0x1800307c1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800307c6  nop
0x1800307c7  mov     rdx, [r15]; String2
0x1800307ca  mov     eax, [rdx-10h]
0x1800307cd  mov     [rsp+78h+arg_10], eax
0x1800307d4  mov     r14, [r12]
0x1800307d8  mov     r8d, eax; MaxCount
0x1800307db  mov     rcx, r14; String1
0x1800307de  call    wcsncmp_0
0x1800307e3  test    eax, eax
0x1800307e5  jz      short loc_180030800
0x1800307e7  mov     edi, 80070057h
0x1800307ec  mov     rcx, [rsp+78h+lpPathName]
0x1800307f1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800307f5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800307fa  nop
0x1800307fb  jmp     loc_180030977
0x180030800  lea     rcx, [r14-18h]
0x180030804  mov     rbx, [rsp+78h+lpPathName]
0x180030809  lea     rsi, [rbx-18h]
0x18003080d  cmp     rcx, rsi
0x180030810  jz      short loc_180030851
0x180030812  cmp     dword ptr [rsi+10h], 0
0x180030816  jl      short loc_18003083B
0x180030818  mov     rax, [rsi]
0x18003081b  cmp     [rcx], rax
0x18003081e  jnz     short loc_18003083B
0x180030820  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180030825  mov     rbx, rax
0x180030828  mov     rcx, rsi; this
0x18003082b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030830  add     rbx, 18h
0x180030834  mov     [rsp+78h+lpPathName], rbx
0x180030839  jmp     short loc_180030851
0x18003083b  mov     r8d, [r14-10h]
0x18003083f  mov     rdx, r14
0x180030842  lea     rcx, [rsp+78h+lpPathName]
0x180030847  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003084c  mov     rbx, [rsp+78h+lpPathName]
0x180030851  xor     esi, esi
0x180030853  mov     r14d, [rsp+78h+arg_10]
0x18003085b  cmp     [rbx-10h], r14d
0x18003085f  jle     short loc_1800308B1
0x180030861  mov     rcx, rbx; this
0x180030864  test    esi, esi
0x180030866  jnz     short loc_180030871
0x180030868  call    ?DeleteReadOnlyFile@FheFileOperations@@YAJPEBG@Z; FheFileOperations::DeleteReadOnlyFile(ushort const *)
0x18003086d  mov     edi, eax
0x18003086f  jmp     short loc_180030890
0x180030871  call    cs:__imp_RemoveDirectoryW
0x180030877  test    eax, eax
0x180030879  jnz     short loc_180030890
0x18003087b  call    cs:__imp_GetLastError
0x180030881  mov     edi, eax
0x180030883  test    eax, eax
0x180030885  jle     short loc_180030890
0x180030887  movzx   edi, ax
0x18003088a  or      edi, 80070000h
0x180030890  lea     eax, [rdi+7FF8FFFEh]
0x180030896  cmp     eax, 1
0x180030899  jbe     short loc_1800308FB
0x18003089b  test    esi, esi
0x18003089d  jle     short loc_1800308C0
0x18003089f  cmp     edi, 80070091h
0x1800308a5  jz      short loc_1800308AF
0x1800308a7  cmp     edi, 80070020h
0x1800308ad  jnz     short loc_1800308C0
0x1800308af  xor     edi, edi
0x1800308b1  lea     rcx, [rbx-18h]; this
0x1800308b5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800308ba  nop
0x1800308bb  jmp     loc_180030971
0x1800308c0  test    edi, edi
0x1800308c2  jns     short loc_18003090E
0x1800308c4  lea     rax, WPP_GLOBAL_Control
0x1800308cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308d2  cmp     rcx, rax
0x1800308d5  jz      short loc_1800308B1
0x1800308d7  test    byte ptr [rcx+1Ch], 2
0x1800308db  jz      short loc_1800308B1
0x1800308dd  mov     edx, 0Dh
0x1800308e2  mov     [rsp+78h+var_58], edi
0x1800308e6  mov     r9, rbx
0x1800308e9  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x1800308f0  mov     rcx, [rcx+10h]
0x1800308f4  call    WPP_SF_Sd
0x1800308f9  jmp     short loc_1800308B1
0x1800308fb  test    esi, esi
0x1800308fd  cmovnz  edi, r13d
0x180030901  mov     r13d, edi
0x180030904  xor     edi, edi
0x180030906  mov     [rsp+78h+arg_18], r13d
0x18003090e  mov     edx, 5Ch ; '\'
0x180030913  lea     rcx, [rsp+78h+lpPathName]
0x180030918  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x18003091d  test    eax, eax
0x18003091f  js      short loc_1800308B1
0x180030921  mov     edx, eax
0x180030923  lea     rcx, [rsp+78h+lpPathName]
0x180030928  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x18003092d  inc     esi
0x18003092f  mov     rbx, [rsp+78h+lpPathName]
0x180030934  jmp     loc_18003085B
0x180030939  mov     r15, [rsp+78h+arg_8]
0x180030941  mov     r12, [rsp+78h+arg_0]
0x180030949  mov     edi, [rsp+78h+arg_10]
0x180030950  jmp     short loc_180030977
0x180030952  mov     r15, [rsp+78h+arg_8]
0x18003095a  mov     r12, [rsp+78h+arg_0]
0x180030962  mov     edi, [rsp+78h+arg_10]
0x180030969  mov     r13d, [rsp+78h+arg_18]
0x180030971  test    edi, edi
0x180030973  cmovns  edi, r13d
0x180030977  mov     rcx, [r12]
0x18003097b  sub     rcx, 18h; this
0x18003097f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030984  nop
0x180030985  mov     rcx, [r15]
0x180030988  sub     rcx, 18h; this
0x18003098c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030991  mov     eax, edi
0x180030993  add     rsp, 40h
0x180030997  pop     r15
0x180030999  pop     r14
0x18003099b  pop     r13
0x18003099d  pop     r12
0x18003099f  pop     rdi
0x1800309a0  pop     rsi
0x1800309a1  pop     rbx
0x1800309a2  retn
```

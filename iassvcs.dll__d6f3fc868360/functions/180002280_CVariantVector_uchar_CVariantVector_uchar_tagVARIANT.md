# CVariantVector<uchar>::CVariantVector<uchar>(tagVARIANT *)

- ea: `0x180002280`
- end: `0x180002364`
- name: `??0?$CVariantVector@E@@QEAA@PEAUtagVARIANT@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(__int64, __int64, struct IErrorInfo *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ce90`

## callees

- `0x180001e0e`
- `0x180002280`
- `0x180002500`
- `0x1800137b0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18000229a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18000229a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800022d6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800022d6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800022bf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800022bf`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800022f7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800022f7`

## pseudocode

```c
__int64 __fastcall CVariantVector<unsigned char>::CVariantVector<unsigned char>(
        __int64 a1,
        __int64 a2,
        struct IErrorInfo *a3,
        bool a4)
{
  SAFEARRAY *v5; // rcx
  SAFEARRAY *v6; // rcx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  struct IErrorInfo *v9; // r8
  bool v10; // r9
  bool v11; // sf
  HRESULT v12; // eax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  LONG plUbound; // [rsp+50h] [rbp+8h] BYREF
  LONG plLbound; // [rsp+58h] [rbp+10h] BYREF

  v5 = *(SAFEARRAY **)(a2 + 8);
  *(_QWORD *)a1 = v5;
  if ( *(_WORD *)a2 != 8209 || SafeArrayGetDim(v5) != 1 )
  {
    _com_error::_com_error((_com_error *)pExceptionObject, -2147352571, a3, a4);
    throw (_com_error *)pExceptionObject;
  }
  v6 = *(SAFEARRAY **)a1;
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(v6, 1u, &plLbound);
  if ( LBound < 0 )
    _com_issue_error(LBound);
  UBound = SafeArrayGetUBound(*(SAFEARRAY **)a1, 1u, &plUbound);
  if ( UBound < 0 )
    _com_issue_error(UBound);
  v11 = plUbound - plLbound + 1 < 0;
  *(_DWORD *)(a1 + 8) = plUbound - plLbound + 1;
  if ( v11 )
  {
    _com_error::_com_error((_com_error *)pExceptionObject, -2147352565, v9, v10);
    throw (_com_error *)pExceptionObject;
  }
  v12 = SafeArrayAccessData(*(SAFEARRAY **)a1, (void **)(a1 + 16));
  if ( v12 < 0 )
    _com_issue_error(v12);
  return a1;
}

```

## disassembly

```asm
0x180002280  push    rbx
0x180002282  sub     rsp, 40h
0x180002286  mov     rbx, rcx
0x180002289  mov     eax, 2011h
0x18000228e  mov     rcx, [rdx+8]; psa
0x180002292  mov     [rbx], rcx
0x180002295  cmp     [rdx], ax
0x180002298  jnz     short loc_18000230A
0x18000229a  call    cs:__imp_SafeArrayGetDim
0x1800022a0  cmp     eax, 1
0x1800022a3  jnz     short loc_18000230A
0x1800022a5  mov     rcx, [rbx]; psa
0x1800022a8  lea     r8, [rsp+48h+plLbound]; plLbound
0x1800022ad  mov     edx, eax; nDim
0x1800022af  mov     [rsp+48h+plLbound], 0
0x1800022b7  mov     [rsp+48h+plUbound], 0
0x1800022bf  call    cs:__imp_SafeArrayGetLBound
0x1800022c5  test    eax, eax
0x1800022c7  js      short loc_18000232B
0x1800022c9  mov     rcx, [rbx]; psa
0x1800022cc  lea     r8, [rsp+48h+plUbound]; plUbound
0x1800022d1  mov     edx, 1; nDim
0x1800022d6  call    cs:__imp_SafeArrayGetUBound
0x1800022dc  test    eax, eax
0x1800022de  js      short loc_180002333
0x1800022e0  mov     eax, [rsp+48h+plUbound]
0x1800022e4  sub     eax, [rsp+48h+plLbound]
0x1800022e8  add     eax, 1
0x1800022eb  mov     [rbx+8], eax
0x1800022ee  js      short loc_18000233B
0x1800022f0  mov     rcx, [rbx]; psa
0x1800022f3  lea     rdx, [rbx+10h]; ppvData
0x1800022f7  call    cs:__imp_SafeArrayAccessData
0x1800022fd  test    eax, eax
0x1800022ff  js      short loc_18000235C
0x180002301  mov     rax, rbx
0x180002304  add     rsp, 40h
0x180002308  pop     rbx
0x180002309  retn
0x18000230a  mov     edx, 80020005h; int
0x18000230f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002314  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x180002319  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180002320  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002325  call    _CxxThrowException_0
0x18000232b  mov     ecx, eax; int
0x18000232d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180002333  mov     ecx, eax; int
0x180002335  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000233b  mov     edx, 8002000Bh; int
0x180002340  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002345  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x18000234a  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180002351  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002356  call    _CxxThrowException_0
0x18000235c  mov     ecx, eax; int
0x18000235e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```

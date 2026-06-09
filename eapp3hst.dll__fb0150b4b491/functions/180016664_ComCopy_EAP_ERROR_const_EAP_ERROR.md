# ComCopy(_EAP_ERROR const &,_EAP_ERROR &)

- ea: `0x180016664`
- end: `0x180016776`
- name: `?ComCopy@@YAXAEBU_EAP_ERROR@@AEAU1@@Z`
- size: `274`
- prototype: `void __fastcall(const struct _EAP_ERROR *, struct _EAP_ERROR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800168c0`

## callees

- `0x180016664`
- `0x18002f4a4`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800166cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800166cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016734`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001673e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016734`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001673e`

## pseudocode

```c
void __fastcall ComCopy(const struct _EAP_ERROR *a1, struct _EAP_ERROR *a2)
{
  __int64 v3; // rsi
  LPWSTR pRootCauseString; // rcx
  __int64 v6; // rax
  SIZE_T v7; // rbp
  WCHAR *v8; // rax
  LPWSTR pRepairString; // rax
  SIZE_T v10; // rsi
  WCHAR *v11; // rax
  _QWORD pExceptionObject[9]; // [rsp+20h] [rbp-48h] BYREF

  v3 = -1;
  *(_OWORD *)&a2->dwWinError = *(_OWORD *)&a1->dwWinError;
  *(_OWORD *)&a2->type.dwAuthorId = *(_OWORD *)&a1->type.dwAuthorId;
  *(_OWORD *)a2->rootCauseGuid.Data4 = *(_OWORD *)a1->rootCauseGuid.Data4;
  *(_OWORD *)a2->repairGuid.Data4 = *(_OWORD *)a1->repairGuid.Data4;
  *(_OWORD *)a2->helpLinkGuid.Data4 = *(_OWORD *)a1->helpLinkGuid.Data4;
  a2->pRootCauseString = 0;
  a2->pRepairString = 0;
  pRootCauseString = a1->pRootCauseString;
  if ( pRootCauseString )
  {
    v6 = -1;
    do
      ++v6;
    while ( pRootCauseString[v6] );
    v7 = 2 * v6 + 2;
    v8 = (WCHAR *)CoTaskMemAlloc(v7);
    a2->pRootCauseString = v8;
    if ( !v8 )
      goto LABEL_11;
    memcpy_0(v8, a1->pRootCauseString, v7);
  }
  pRepairString = a1->pRepairString;
  if ( !pRepairString )
    return;
  do
    ++v3;
  while ( pRepairString[v3] );
  v10 = 2 * v3 + 2;
  v11 = (WCHAR *)CoTaskMemAlloc(v10);
  a2->pRepairString = v11;
  if ( !v11 )
  {
LABEL_11:
    CoTaskMemFree(a2->pRootCauseString);
    CoTaskMemFree(a2->pRepairString);
    pExceptionObject[2] = 0;
    pExceptionObject[1] = "bad allocation";
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  memcpy_0(v11, a1->pRepairString, v10);
}

```

## disassembly

```asm
0x180016664  push    rbx
0x180016666  push    rbp
0x180016667  push    rsi
0x180016668  push    rdi
0x180016669  push    r14
0x18001666b  sub     rsp, 40h
0x18001666f  movups  xmm0, xmmword ptr [rcx]
0x180016672  xor     r14d, r14d
0x180016675  mov     rdi, rcx
0x180016678  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001667c  mov     rbx, rdx
0x18001667f  movups  xmmword ptr [rdx], xmm0
0x180016682  movups  xmm1, xmmword ptr [rcx+10h]
0x180016686  movups  xmmword ptr [rdx+10h], xmm1
0x18001668a  movups  xmm0, xmmword ptr [rcx+20h]
0x18001668e  movups  xmmword ptr [rdx+20h], xmm0
0x180016692  movups  xmm1, xmmword ptr [rcx+30h]
0x180016696  movups  xmmword ptr [rdx+30h], xmm1
0x18001669a  movups  xmm0, xmmword ptr [rcx+40h]
0x18001669e  movups  xmmword ptr [rdx+40h], xmm0
0x1800166a2  mov     [rdx+48h], r14
0x1800166a6  mov     [rdx+50h], r14
0x1800166aa  mov     rcx, [rcx+48h]
0x1800166ae  test    rcx, rcx
0x1800166b1  jz      short loc_1800166E9
0x1800166b3  mov     rax, rsi
0x1800166b6  inc     rax
0x1800166b9  cmp     [rcx+rax*2], r14w
0x1800166be  jnz     short loc_1800166B6
0x1800166c0  lea     rbp, ds:2[rax*2]
0x1800166c8  mov     rcx, rbp; cb
0x1800166cb  call    cs:__imp_CoTaskMemAlloc
0x1800166d1  mov     [rbx+48h], rax
0x1800166d5  test    rax, rax
0x1800166d8  jz      short loc_180016730
0x1800166da  mov     rdx, [rdi+48h]; Src
0x1800166de  mov     r8, rbp; Size
0x1800166e1  mov     rcx, rax; void *
0x1800166e4  call    memcpy_0
0x1800166e9  mov     rax, [rdi+50h]
0x1800166ed  test    rax, rax
0x1800166f0  jz      short loc_180016725
0x1800166f2  inc     rsi
0x1800166f5  cmp     [rax+rsi*2], r14w
0x1800166fa  jnz     short loc_1800166F2
0x1800166fc  lea     rsi, ds:2[rsi*2]
0x180016704  mov     rcx, rsi; cb
0x180016707  call    cs:__imp_CoTaskMemAlloc
0x18001670d  mov     [rbx+50h], rax
0x180016711  test    rax, rax
0x180016714  jz      short loc_180016730
0x180016716  mov     rdx, [rdi+50h]; Src
0x18001671a  mov     r8, rsi; Size
0x18001671d  mov     rcx, rax; void *
0x180016720  call    memcpy_0
0x180016725  add     rsp, 40h
0x180016729  pop     r14
0x18001672b  pop     rdi
0x18001672c  pop     rsi
0x18001672d  pop     rbp
0x18001672e  pop     rbx
0x18001672f  retn
0x180016730  mov     rcx, [rbx+48h]; pv
0x180016734  call    cs:__imp_CoTaskMemFree
0x18001673a  mov     rcx, [rbx+50h]; pv
0x18001673e  call    cs:__imp_CoTaskMemFree
0x180016744  xorps   xmm0, xmm0
0x180016747  lea     rax, aBadAllocation; "bad allocation"
0x18001674e  movups  [rsp+68h+var_40], xmm0
0x180016753  mov     qword ptr [rsp+68h+var_40], rax
0x180016758  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001675f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180016766  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001676b  mov     [rsp+68h+pExceptionObject], rax
0x180016770  call    _CxxThrowException_0
```

# ComCopy(tagEapPeerMethodResult const &,tagEapPeerMethodResultOle &)

- ea: `0x1800168c0`
- end: `0x180016a75`
- name: `?ComCopy@@YAXAEBUtagEapPeerMethodResult@@AEAUtagEapPeerMethodResultOle@@@Z`
- size: `437`
- prototype: `void __fastcall(const struct tagEapPeerMethodResult *, struct tagEapPeerMethodResultOle *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800081b0`

## callees

- `0x180012a00`
- `0x180016664`
- `0x18001677c`
- `0x1800168c0`
- `0x18002f4a4`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016930`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001696d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800169ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016930`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001696d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800169ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a3b`

## string_xrefs

- `0x18001697b`: `ComCopy`

## pseudocode

```c
void __fastcall ComCopy(const struct tagEapPeerMethodResult *a1, struct tagEapPeerMethodResultOle *a2)
{
  __int128 v4; // xmm6
  __int64 v5; // rbx
  BYTE *pUserData; // r12
  EAP_ATTRIBUTES *pAttribArray; // rdi
  EAP_ERROR *pEapError; // rsi
  void *v9; // rax
  void *v10; // r13
  BYTE *v11; // rax
  struct _EAP_ATTRIBUTES *v12; // rax
  struct _EAP_ERROR *v13; // rax
  _QWORD pExceptionObject[6]; // [rsp+20h] [rbp-A8h] BYREF
  __int128 v15; // [rsp+50h] [rbp-78h]
  BYTE *v16; // [rsp+60h] [rbp-68h]
  EAP_ATTRIBUTES *v17; // [rsp+68h] [rbp-60h]
  EAP_ERROR *v18; // [rsp+70h] [rbp-58h]
  struct EapHost::Attributes *v19; // [rsp+D0h] [rbp+8h]

  v4 = *(_OWORD *)&a1->fIsSuccess;
  v5 = *(_QWORD *)&a1->fSaveUserData;
  pUserData = a1->pUserData;
  pAttribArray = a1->pAttribArray;
  v17 = pAttribArray;
  pEapError = a1->pEapError;
  v18 = pEapError;
  v9 = CoTaskMemAlloc(a1->dwSizeofConnectionData);
  v10 = v9;
  *(_QWORD *)&v15 = v9;
  if ( !v9
    || (memcpy_0(v9, a1->pConnectionData, a1->dwSizeofConnectionData),
        v11 = (BYTE *)CoTaskMemAlloc(a1->dwSizeofUserData),
        pUserData = v11,
        (v16 = v11) == 0) )
  {
LABEL_12:
    CoTaskMemFree(v10);
    CoTaskMemFree(pUserData);
    CoTaskMemFree(pAttribArray);
    CoTaskMemFree(pEapError);
    pExceptionObject[2] = 0;
    pExceptionObject[1] = "bad allocation";
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  memcpy_0(v11, a1->pUserData, a1->dwSizeofUserData);
  v19 = (struct EapHost::Attributes *)a1->pAttribArray;
  if ( v19 )
  {
    v12 = (struct _EAP_ATTRIBUTES *)CoTaskMemAlloc(0x10u);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      pAttribArray = v12;
      if ( !v12 )
        LowMemoryError::Throw(L"ComCopy");
      *v12 = 0;
      ComCopy(v19, v12);
      v17 = pAttribArray;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        pEapError = v18;
        pAttribArray = v17;
        pUserData = v16;
        v10 = (void *)v15;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180016A09);
        goto LABEL_12;
      }
    }
  }
  if ( a1->pEapError )
  {
    v13 = (struct _EAP_ERROR *)CoTaskMemAlloc(0x58u);
    pEapError = v13;
    v18 = v13;
    if ( !v13 )
      goto LABEL_12;
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      ComCopy(a1->pEapError, v13);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        pEapError = v18;
        pAttribArray = v17;
        pUserData = v16;
        v10 = (void *)v15;
        __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_180016A73);
        goto LABEL_12;
      }
    }
  }
  *(_OWORD *)a2 = v4;
  *((_QWORD *)a2 + 2) = v10;
  *((_QWORD *)a2 + 3) = v5;
  *((_QWORD *)a2 + 4) = pUserData;
  *((_QWORD *)a2 + 5) = pAttribArray;
  *((_QWORD *)a2 + 6) = pEapError;
}

```

## disassembly

```asm
0x1800168c0  mov     rax, rsp
0x1800168c3  mov     [rax+10h], rbx
0x1800168c7  mov     [rax+18h], rsi
0x1800168cb  push    rdi
0x1800168cc  push    r12
0x1800168ce  push    r13
0x1800168d0  push    r14
0x1800168d2  push    r15
0x1800168d4  sub     rsp, 0A0h
0x1800168db  movaps  xmmword ptr [rax-38h], xmm6
0x1800168df  mov     r15, rdx
0x1800168e2  mov     r14, rcx
0x1800168e5  movaps  xmm6, xmmword ptr [rcx]
0x1800168e8  mov     rbx, [rcx+18h]
0x1800168ec  mov     r12, [rcx+20h]
0x1800168f0  mov     rdi, [rcx+28h]
0x1800168f4  mov     [rsp+0C8h+var_60], rdi
0x1800168f9  mov     rsi, [rcx+30h]
0x1800168fd  mov     [rsp+0C8h+var_58], rsi
0x180016902  mov     ecx, [rcx+0Ch]; cb
0x180016905  call    cs:__imp_CoTaskMemAlloc
0x18001690b  mov     r13, rax
0x18001690e  mov     qword ptr [rsp+0C8h+var_78], rax
0x180016913  test    rax, rax
0x180016916  jz      loc_180016A1D
0x18001691c  mov     r8d, [r14+0Ch]; Size
0x180016920  mov     rdx, [r14+10h]; Src
0x180016924  mov     rcx, rax; void *
0x180016927  call    memcpy_0
0x18001692c  mov     ecx, [r14+1Ch]; cb
0x180016930  call    cs:__imp_CoTaskMemAlloc
0x180016936  mov     r12, rax
0x180016939  mov     [rsp+0C8h+var_68], rax
0x18001693e  test    rax, rax
0x180016941  jz      loc_180016A1D
0x180016947  mov     r8d, [r14+1Ch]; Size
0x18001694b  mov     rdx, [r14+20h]; Src
0x18001694f  mov     rcx, rax; void *
0x180016952  call    memcpy_0
0x180016957  mov     rax, [r14+28h]
0x18001695b  mov     [rsp+0C8h+arg_0], rax
0x180016963  test    rax, rax
0x180016966  jz      short loc_1800169A2
0x180016968  mov     ecx, 10h; cb
0x18001696d  call    cs:__imp_CoTaskMemAlloc
0x180016973  mov     rdi, rax
0x180016976  test    rax, rax
0x180016979  jnz     short loc_180016987
0x18001697b  lea     rcx, aComcopy; "ComCopy"
0x180016982  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180016987  xorps   xmm0, xmm0
0x18001698a  movups  xmmword ptr [rax], xmm0
0x18001698d  mov     rdx, rdi; struct _EAP_ATTRIBUTES *
0x180016990  mov     rcx, [rsp+0C8h+arg_0]; struct EapHost::Attributes *
0x180016998  call    ?ComCopy@@YAXAEBVAttributes@EapHost@@AEAU_EAP_ATTRIBUTES@@@Z; ComCopy(EapHost::Attributes const &,_EAP_ATTRIBUTES &)
0x18001699d  mov     [rsp+0C8h+var_60], rdi
0x1800169a2  cmp     qword ptr [r14+30h], 0
0x1800169a7  jz      short loc_1800169CE
0x1800169a9  mov     ecx, 58h ; 'X'; cb
0x1800169ae  call    cs:__imp_CoTaskMemAlloc
0x1800169b4  mov     rsi, rax
0x1800169b7  mov     [rsp+0C8h+var_58], rax
0x1800169bc  test    rax, rax
0x1800169bf  jz      short loc_180016A1D
0x1800169c1  mov     rdx, rax; struct _EAP_ERROR *
0x1800169c4  mov     rcx, [r14+30h]; struct _EAP_ERROR *
0x1800169c8  call    ?ComCopy@@YAXAEBU_EAP_ERROR@@AEAU1@@Z; ComCopy(_EAP_ERROR const &,_EAP_ERROR &)
0x1800169cd  nop
0x1800169ce  movdqu  xmmword ptr [r15], xmm6
0x1800169d3  mov     [r15+10h], r13
0x1800169d7  mov     [r15+18h], rbx
0x1800169db  mov     [r15+20h], r12
0x1800169df  mov     [r15+28h], rdi
0x1800169e3  mov     [r15+30h], rsi
0x1800169e7  lea     r11, [rsp+0C8h+var_28]
0x1800169ef  mov     rbx, [r11+38h]
0x1800169f3  mov     rsi, [r11+40h]
0x1800169f7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800169fc  mov     rsp, r11
0x1800169ff  pop     r15
0x180016a01  pop     r14
0x180016a03  pop     r13
0x180016a05  pop     r12
0x180016a07  pop     rdi
0x180016a08  retn
0x180016a09  mov     rsi, [rsp+0C8h+var_58]
0x180016a0e  mov     rdi, [rsp+0C8h+var_60]
0x180016a13  mov     r12, [rsp+0C8h+var_68]
0x180016a18  mov     r13, qword ptr [rsp+0C8h+var_78]
0x180016a1d  mov     rcx, r13; pv
0x180016a20  call    cs:__imp_CoTaskMemFree
0x180016a26  mov     rcx, r12; pv
0x180016a29  call    cs:__imp_CoTaskMemFree
0x180016a2f  mov     rcx, rdi; pv
0x180016a32  call    cs:__imp_CoTaskMemFree
0x180016a38  mov     rcx, rsi; pv
0x180016a3b  call    cs:__imp_CoTaskMemFree
0x180016a41  xorps   xmm0, xmm0
0x180016a44  movups  [rsp+0C8h+var_A0], xmm0
0x180016a49  lea     rax, aBadAllocation; "bad allocation"
0x180016a50  mov     qword ptr [rsp+0C8h+var_A0], rax
0x180016a55  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180016a5c  mov     [rsp+0C8h+pExceptionObject], rax
0x180016a61  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180016a68  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180016a6d  call    _CxxThrowException_0
0x180016a73  jmp     short loc_180016A09
```

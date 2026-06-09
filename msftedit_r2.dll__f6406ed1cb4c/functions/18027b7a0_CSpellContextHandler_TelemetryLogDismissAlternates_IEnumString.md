# CSpellContextHandler::TelemetryLogDismissAlternates(IEnumString *)

- ea: `0x18027b7a0`
- end: `0x18027ba21`
- name: `?TelemetryLogDismissAlternates@CSpellContextHandler@@AEAAXPEAUIEnumString@@@Z`
- size: `641`
- prototype: `void __fastcall(CSpellContextHandler *__hidden this, struct IEnumString *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18027a1b0`
- `0x18027a7a8`
- `0x18027abe4`

## callees

- `0x18006ad18`
- `0x18010c5e8`
- `0x18013ce80`
- `0x18013d268`
- `0x18013dac8`
- `0x18013dc92`
- `0x18027b7a0`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18027b84c`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18027b84c`
- `OLEAUT32!__imp_SysFreeString` at `0x18027b9b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18027b9b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18027b9a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18027b9a3`

## pseudocode

```c
void __fastcall CSpellContextHandler::TelemetryLogDismissAlternates(CSpellContextHandler *this, struct IEnumString *a2)
{
  _QWORD *v2; // r15
  int v5; // r12d
  rsize_t v6; // rcx
  wchar_t *v7; // r13
  LCID CurrentInputMethodLCID; // eax
  char v9; // di
  int v10; // ebx
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  wchar_t *v13; // r8
  __int64 v14; // rax
  char v15; // [rsp+30h] [rbp-D0h]
  BOOL v16; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t *Source; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  rsize_t SizeInWords; // [rsp+50h] [rbp-B0h]
  WCHAR Name[88]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = (_QWORD *)((char *)this + 48);
  if ( a2 )
  {
    ((void (__fastcall *)(struct IEnumString *))a2->lpVtbl->Reset)(a2);
  }
  else if ( !*v2 )
  {
    return;
  }
  v5 = *((_DWORD *)this + 16);
  v6 = (unsigned int)(129 * (*((_DWORD *)this + 18) - v5 + 1));
  v18 = *((_DWORD *)this + 18) - v5 + 1;
  SizeInWords = v6;
  v7 = (wchar_t *)operator new(saturated_mul(v6, 2u));
  *v7 = 0;
  CurrentInputMethodLCID = CSpellerGlobalState::GetCurrentInputMethodLCID(*(CSpellerGlobalState **)(*((_QWORD *)this + 3)
                                                                                                  + 64LL));
  if ( LCIDToLocaleName(CurrentInputMethodLCID, Name, 85, 0) > 0 )
  {
    if ( a2 )
    {
      v9 = 0;
      v15 = 0;
      goto LABEL_10;
    }
    if ( *v2 )
    {
      v9 = 1;
      v15 = 1;
      (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*v2 + 40LL))(*v2, &v18);
      do
      {
LABEL_10:
        Source = 0;
        v16 = 0;
        if ( v9 )
        {
          v11 = *v2;
          v19 = 0;
          v12 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v11 + 32LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
          if ( v12(v11, (unsigned int)(v5 - *((_DWORD *)this + 16)), &v19) < 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
            goto LABEL_30;
          }
          v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v19 + 24LL))(v19, &Source);
          if ( v10 >= 0 )
            v16 = *Source != 12080;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
          v9 = v15;
        }
        else
        {
          v10 = ((__int64 (__fastcall *)(struct IEnumString *, __int64, wchar_t **, BOOL *))a2->lpVtbl->Next)(
                  a2,
                  1,
                  &Source,
                  &v16);
          if ( v10 < 0 )
            goto LABEL_30;
        }
        if ( v16 )
        {
          if ( v5 != *((_DWORD *)this + 16) )
            wcscat_s(v7, SizeInWords, L",");
        }
        else if ( v5 != *((_DWORD *)this + 16) )
        {
          break;
        }
        v13 = (wchar_t *)&qword_1802C65E0;
        if ( Source )
          v13 = Source;
        wcscat_s(v7, SizeInWords, v13);
        if ( a2 )
          CoTaskMemFree(Source);
        else
          SysFreeString(Source);
        ++v5;
      }
      while ( v18 >= v5 - *((_DWORD *)this + 16) + 1 );
      if ( v10 < 0 )
        goto LABEL_30;
    }
    v14 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 64LL) + 80LL);
    ++*(_DWORD *)(v14 + 32);
  }
LABEL_30:
  operator delete(v7);
}

```

## disassembly

```asm
0x18027b7a0  mov     [rsp-8+arg_10], rbx
0x18027b7a5  push    rbp
0x18027b7a6  push    rsi
0x18027b7a7  push    rdi
0x18027b7a8  push    r12
0x18027b7aa  push    r13
0x18027b7ac  push    r14
0x18027b7ae  push    r15
0x18027b7b0  lea     rbp, [rsp-20h]
0x18027b7b5  sub     rsp, 120h
0x18027b7bc  mov     rax, cs:__security_cookie
0x18027b7c3  xor     rax, rsp
0x18027b7c6  mov     [rbp+50h+var_40], rax
0x18027b7ca  lea     r15, [rcx+30h]
0x18027b7ce  mov     r14, rdx
0x18027b7d1  mov     rsi, rcx
0x18027b7d4  test    rdx, rdx
0x18027b7d7  jnz     short loc_18027B7E4
0x18027b7d9  cmp     [r15], rdx
0x18027b7dc  jz      loc_18027B9ED
0x18027b7e2  jmp     short loc_18027B7F3
0x18027b7e4  mov     rax, [rdx]
0x18027b7e7  mov     rcx, r14
0x18027b7ea  mov     rax, [rax+28h]
0x18027b7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027b7f3  mov     eax, [rsi+48h]
0x18027b7f6  mov     r12d, [rsi+40h]
0x18027b7fa  sub     eax, r12d
0x18027b7fd  inc     eax
0x18027b7ff  imul    ecx, eax, 81h
0x18027b805  mov     [rsp+150h+var_110], eax
0x18027b809  mov     eax, 2
0x18027b80e  mul     rcx
0x18027b811  mov     [rsp+150h+SizeInWords], rcx
0x18027b816  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18027b81d  cmovb   rax, rcx
0x18027b821  mov     rcx, rax; Size
0x18027b824  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18027b829  xor     ecx, ecx
0x18027b82b  mov     r13, rax
0x18027b82e  mov     [rax], cx
0x18027b831  mov     rcx, [rsi+18h]
0x18027b835  mov     rcx, [rcx+40h]; this
0x18027b839  call    ?GetCurrentInputMethodLCID@CSpellerGlobalState@@QEBAKXZ; CSpellerGlobalState::GetCurrentInputMethodLCID(void)
0x18027b83e  xor     r9d, r9d; dwFlags
0x18027b841  lea     rdx, [rsp+150h+Name]; lpName
0x18027b846  mov     ecx, eax; Locale
0x18027b848  lea     r8d, [r9+55h]; cchName
0x18027b84c  call    cs:__imp_LCIDToLocaleName
0x18027b853  nop     dword ptr [rax+rax+00h]
0x18027b858  test    eax, eax
0x18027b85a  jle     loc_18027B9E5
0x18027b860  test    r14, r14
0x18027b863  jz      short loc_18027B86F
0x18027b865  xor     dil, dil
0x18027b868  mov     [rsp+150h+var_120], dil
0x18027b86d  jmp     short loc_18027B894
0x18027b86f  mov     rcx, [r15]
0x18027b872  test    rcx, rcx
0x18027b875  jz      loc_18027B9D6
0x18027b87b  mov     rax, [rcx]
0x18027b87e  lea     rdx, [rsp+150h+var_110]
0x18027b883  mov     dil, 1
0x18027b886  mov     [rsp+150h+var_120], dil
0x18027b88b  mov     rax, [rax+28h]
0x18027b88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027b894  mov     [rsp+150h+Source], 0
0x18027b89d  mov     [rsp+150h+var_11C], 0
0x18027b8a5  test    dil, dil
0x18027b8a8  jnz     short loc_18027B8D4
0x18027b8aa  mov     rax, [r14]
0x18027b8ad  lea     r9, [rsp+150h+var_11C]
0x18027b8b2  lea     r8, [rsp+150h+Source]
0x18027b8b7  mov     edx, 1
0x18027b8bc  mov     rcx, r14
0x18027b8bf  mov     rax, [rax+18h]
0x18027b8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027b8c8  mov     ebx, eax
0x18027b8ca  test    eax, eax
0x18027b8cc  js      loc_18027B9E5
0x18027b8d2  jmp     short loc_18027B950
0x18027b8d4  mov     rdi, [r15]
0x18027b8d7  lea     rcx, [rsp+150h+var_108]
0x18027b8dc  mov     [rsp+150h+var_108], 0
0x18027b8e5  mov     rax, [rdi]
0x18027b8e8  mov     rbx, [rax+20h]
0x18027b8ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027b8f1  mov     edx, r12d
0x18027b8f4  lea     r8, [rsp+150h+var_108]
0x18027b8f9  sub     edx, [rsi+40h]
0x18027b8fc  mov     rcx, rdi
0x18027b8ff  mov     rax, rbx
0x18027b902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027b907  test    eax, eax
0x18027b909  js      loc_18027BA15
0x18027b90f  mov     rcx, [rsp+150h+var_108]
0x18027b914  lea     rdx, [rsp+150h+Source]
0x18027b919  mov     rax, [rcx]
0x18027b91c  mov     rax, [rax+18h]
0x18027b920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027b925  mov     ebx, eax
0x18027b927  test    eax, eax
0x18027b929  js      short loc_18027B941
0x18027b92b  mov     rax, [rsp+150h+Source]
0x18027b930  xor     ecx, ecx
0x18027b932  mov     edx, 2F30h
0x18027b937  cmp     [rax], dx
0x18027b93a  setnz   cl
0x18027b93d  mov     [rsp+150h+var_11C], ecx
0x18027b941  lea     rcx, [rsp+150h+var_108]
0x18027b946  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027b94b  mov     dil, [rsp+150h+var_120]
0x18027b950  cmp     [rsp+150h+var_11C], 0
0x18027b955  jnz     short loc_18027B95F
0x18027b957  cmp     r12d, [rsi+40h]
0x18027b95b  jnz     short loc_18027B9D2
0x18027b95d  jmp     short loc_18027B979
0x18027b95f  cmp     r12d, [rsi+40h]
0x18027b963  jz      short loc_18027B979
0x18027b965  mov     rdx, [rsp+150h+SizeInWords]; SizeInWords
0x18027b96a  lea     r8, asc_1802B19EC; ","
0x18027b971  mov     rcx, r13; Destination
0x18027b974  call    wcscat_s
0x18027b979  mov     rax, [rsp+150h+Source]
0x18027b97e  lea     r8, qword_1802C65E0
0x18027b985  mov     rdx, [rsp+150h+SizeInWords]; SizeInWords
0x18027b98a  test    rax, rax
0x18027b98d  mov     rcx, r13; Destination
0x18027b990  cmovnz  r8, rax; Source
0x18027b994  call    wcscat_s
0x18027b999  mov     rcx, [rsp+150h+Source]; bstrString
0x18027b99e  test    r14, r14
0x18027b9a1  jz      short loc_18027B9B1
0x18027b9a3  call    cs:__imp_CoTaskMemFree
0x18027b9aa  nop     dword ptr [rax+rax+00h]
0x18027b9af  jmp     short loc_18027B9BD
0x18027b9b1  call    cs:__imp_SysFreeString
0x18027b9b8  nop     dword ptr [rax+rax+00h]
0x18027b9bd  inc     r12d
0x18027b9c0  mov     eax, r12d
0x18027b9c3  sub     eax, [rsi+40h]
0x18027b9c6  inc     eax
0x18027b9c8  cmp     [rsp+150h+var_110], eax
0x18027b9cc  jnb     loc_18027B894
0x18027b9d2  test    ebx, ebx
0x18027b9d4  js      short loc_18027B9E5
0x18027b9d6  mov     rax, [rsi+18h]
0x18027b9da  mov     rcx, [rax+40h]
0x18027b9de  mov     rax, [rcx+50h]
0x18027b9e2  inc     dword ptr [rax+20h]
0x18027b9e5  mov     rcx, r13; Block
0x18027b9e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18027b9ed  mov     rcx, [rbp+50h+var_40]
0x18027b9f1  xor     rcx, rsp; StackCookie
0x18027b9f4  call    __security_check_cookie
0x18027b9f9  mov     rbx, [rsp+150h+arg_10]
0x18027ba01  add     rsp, 120h
0x18027ba08  pop     r15
0x18027ba0a  pop     r14
0x18027ba0c  pop     r13
0x18027ba0e  pop     r12
0x18027ba10  pop     rdi
0x18027ba11  pop     rsi
0x18027ba12  pop     rbp
0x18027ba13  retn
0x18027ba15  lea     rcx, [rsp+150h+var_108]
0x18027ba1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027ba1f  jmp     short loc_18027B9E5
```

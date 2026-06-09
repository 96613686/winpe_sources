# IsolationAwareImageList_ReplaceIcon

- ea: `0x180007a18`
- end: `0x180007aea`
- name: `IsolationAwareImageList_ReplaceIcon`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006f10`
- `0x180014da8`

## callees

- `0x180005160`
- `0x1800075d0`
- `0x180007a18`
- `0x180015884`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007abc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007abc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007add`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007add`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007ad1`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007ad1`

## string_xrefs

- `0x180007a70`: `ImageList_ReplaceIcon`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_ReplaceIcon(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // edi
  __int64 (__fastcall *v6)(__int64, __int64, __int64); // rbx
  __int64 v8; // rax
  int v9; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+78h] [rbp+20h] BYREF

  v5 = -1;
  v6 = (__int64 (__fastcall *)(__int64, __int64, __int64))`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0xFFFFFFFFLL;
  }
  if ( !v6 )
  {
    v8 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_ReplaceIcon");
    v6 = (__int64 (__fastcall *)(__int64, __int64, __int64))v8;
    if ( !v8 )
      goto LABEL_9;
    `IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn = v8;
  }
  v5 = v6(a1, 0xFFFFFFFFLL, a3);
LABEL_9:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v5 == -1 )
    {
      v9 = 1;
      LastError = GetLastError();
    }
    else
    {
      v9 = 0;
      LastError = 0;
    }
    DeactivateActCtx(0, ulCookie);
    if ( v9 )
      SetLastError(LastError);
  }
  return v5;
}

```

## disassembly

```asm
0x180007a18  push    rbx
0x180007a1a  push    rsi
0x180007a1b  push    rdi
0x180007a1c  push    r14
0x180007a1e  sub     rsp, 38h
0x180007a22  mov     rsi, r8
0x180007a25  mov     r14, rcx
0x180007a28  or      edi, 0FFFFFFFFh
0x180007a2b  mov     [rsp+58h+var_38], edi
0x180007a2f  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_ReplaceIcon@@9@4P6AHPEAU_IMAGELIST@@HPEAUHICON__@@@ZEA; int (*`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn)(_IMAGELIST *,int,HICON__ *)
0x180007a36  mov     [rsp+58h+ulCookie], 0
0x180007a3f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007a46  jnz     short loc_180007A6B
0x180007a48  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007a4f  jnz     short loc_180007A6B
0x180007a51  lea     rcx, [rsp+58h+ulCookie]; lpCookie
0x180007a56  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180007a5b  test    eax, eax
0x180007a5d  jnz     short loc_180007A6B
0x180007a5f  or      eax, edi
0x180007a61  add     rsp, 38h
0x180007a65  pop     r14
0x180007a67  pop     rdi
0x180007a68  pop     rsi
0x180007a69  pop     rbx
0x180007a6a  retn
0x180007a6b  test    rbx, rbx
0x180007a6e  jnz     short loc_180007A8B
0x180007a70  lea     rcx, aImagelistRepla; "ImageList_ReplaceIcon"
0x180007a77  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180007a7c  mov     rbx, rax
0x180007a7f  test    rax, rax
0x180007a82  jz      short loc_180007AA2
0x180007a84  mov     cs:?s_pfn@?1??IsolationAwareImageList_ReplaceIcon@@9@4P6AHPEAU_IMAGELIST@@HPEAUHICON__@@@ZEA, rax; int (*`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn)(_IMAGELIST *,int,HICON__ *)
0x180007a8b  mov     r8, rsi
0x180007a8e  or      edx, 0FFFFFFFFh
0x180007a91  mov     rcx, r14
0x180007a94  mov     rax, rbx
0x180007a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a9c  mov     edi, eax
0x180007a9e  mov     [rsp+58h+var_38], eax
0x180007aa2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007aa9  jz      short loc_180007AB4
0x180007aab  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007ab2  jnz     short loc_180007AE3
0x180007ab4  cmp     edi, 0FFFFFFFFh
0x180007ab7  jnz     short loc_180007AC6
0x180007ab9  lea     esi, [rdi+2]
0x180007abc  call    cs:__imp_GetLastError
0x180007ac2  mov     ebx, eax
0x180007ac4  jmp     short loc_180007ACA
0x180007ac6  xor     esi, esi
0x180007ac8  xor     ebx, ebx
0x180007aca  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x180007acf  xor     ecx, ecx; dwFlags
0x180007ad1  call    cs:__imp_DeactivateActCtx
0x180007ad7  test    esi, esi
0x180007ad9  jz      short loc_180007AE3
0x180007adb  mov     ecx, ebx; dwErrCode
0x180007add  call    cs:__imp_SetLastError
0x180007ae3  mov     eax, edi
0x180007ae5  jmp     loc_180007A61
0x18003ec68  push    rbx
0x18003ec6a  push    rbp
0x18003ec6b  push    rdi
0x18003ec6c  sub     rsp, 20h
0x18003ec70  mov     rbp, rdx
0x18003ec73  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003ec7a  jz      short loc_18003EC85
0x18003ec7c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003ec83  jnz     short loc_18003ECB7
0x18003ec85  cmp     dword ptr [rbp+20h], 0FFFFFFFFh
0x18003ec89  jnz     short loc_18003EC9A
0x18003ec8b  mov     edi, 1
0x18003ec90  call    cs:__imp_GetLastError
0x18003ec96  mov     ebx, eax
0x18003ec98  jmp     short loc_18003EC9E
0x18003ec9a  xor     edi, edi
0x18003ec9c  xor     ebx, ebx
0x18003ec9e  mov     rdx, [rbp+78h]; ulCookie
0x18003eca2  xor     ecx, ecx; dwFlags
0x18003eca4  call    cs:__imp_DeactivateActCtx
0x18003ecaa  test    edi, edi
0x18003ecac  jz      short loc_18003ECB7
0x18003ecae  mov     ecx, ebx; dwErrCode
0x18003ecb0  call    cs:__imp_SetLastError
0x18003ecb6  nop
0x18003ecb7  add     rsp, 20h
0x18003ecbb  pop     rdi
0x18003ecbc  pop     rbp
0x18003ecbd  pop     rbx
0x18003ecbe  retn
```

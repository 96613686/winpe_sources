# IsolationAwareRemoveWindowSubclass

- ea: `0x1800379dc`
- end: `0x180037ab3`
- name: `IsolationAwareRemoveWindowSubclass`
- size: `215`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800358d0`
- `0x180035990`
- `0x180035a50`

## callees

- `0x180005160`
- `0x1800075d0`
- `0x1800379dc`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037a97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ec52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037a97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ec52`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180037a8b`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003ec46`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180037a8b`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003ec46`

## string_xrefs

- `0x180037a2b`: `RemoveWindowSubclass`

## pseudocode

```c
__int64 __fastcall IsolationAwareRemoveWindowSubclass(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // edi
  __int64 (__fastcall *v7)(__int64, __int64, __int64); // rbx
  __int64 result; // rax
  __int64 v9; // rax
  int v10; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+68h] [rbp+20h] BYREF

  v6 = 0;
  v7 = (__int64 (__fastcall *)(__int64, __int64, __int64))`IsolationAwareRemoveWindowSubclass'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    result = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)result )
      return result;
  }
  if ( !v7 )
  {
    v9 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("RemoveWindowSubclass");
    v7 = (__int64 (__fastcall *)(__int64, __int64, __int64))v9;
    if ( !v9 )
      goto LABEL_8;
    `IsolationAwareRemoveWindowSubclass'::`2'::s_pfn = v9;
  }
  v6 = v7(a1, a2, a3);
LABEL_8:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v6 )
    {
      v10 = 0;
      LastError = 0;
    }
    else
    {
      v10 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v10 )
      SetLastError(LastError);
  }
  return v6;
}

```

## disassembly

```asm
0x1800379dc  mov     rax, rsp
0x1800379df  mov     [rax+8], rbx
0x1800379e3  mov     [rax+10h], rsi
0x1800379e7  push    rdi
0x1800379e8  push    r14
0x1800379ea  push    r15
0x1800379ec  sub     rsp, 30h
0x1800379f0  mov     rsi, r8
0x1800379f3  mov     r14, rdx
0x1800379f6  mov     r15, rcx
0x1800379f9  xor     edi, edi
0x1800379fb  mov     [rax-28h], edi
0x1800379fe  mov     rbx, cs:?s_pfn@?1??IsolationAwareRemoveWindowSubclass@@9@4P6AHPEAUHWND__@@P6A_J0I_K_J11@Z1@ZEA; int (*`IsolationAwareRemoveWindowSubclass'::`2'::s_pfn)(HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64),unsigned __int64)
0x180037a05  mov     [rax+20h], rdi
0x180037a09  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180037a0f  jnz     short loc_180037A26
0x180037a11  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180037a17  jnz     short loc_180037A26
0x180037a19  lea     rcx, [rax+20h]; lpCookie
0x180037a1d  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180037a22  test    eax, eax
0x180037a24  jz      short loc_180037A9F
0x180037a26  test    rbx, rbx
0x180037a29  jnz     short loc_180037A46
0x180037a2b  lea     rcx, aRemovewindowsu; "RemoveWindowSubclass"
0x180037a32  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180037a37  mov     rbx, rax
0x180037a3a  test    rax, rax
0x180037a3d  jz      short loc_180037A5D
0x180037a3f  mov     cs:?s_pfn@?1??IsolationAwareRemoveWindowSubclass@@9@4P6AHPEAUHWND__@@P6A_J0I_K_J11@Z1@ZEA, rax; int (*`IsolationAwareRemoveWindowSubclass'::`2'::s_pfn)(HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64),unsigned __int64)
0x180037a46  mov     r8, rsi
0x180037a49  mov     rdx, r14
0x180037a4c  mov     rcx, r15
0x180037a4f  mov     rax, rbx
0x180037a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a57  mov     edi, eax
0x180037a59  mov     [rsp+48h+var_28], eax
0x180037a5d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180037a64  jz      short loc_180037A6F
0x180037a66  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180037a6d  jnz     short loc_180037A9D
0x180037a6f  test    edi, edi
0x180037a71  jnz     short loc_180037A80
0x180037a73  lea     esi, [rdi+1]
0x180037a76  call    cs:__imp_GetLastError
0x180037a7c  mov     ebx, eax
0x180037a7e  jmp     short loc_180037A84
0x180037a80  xor     esi, esi
0x180037a82  xor     ebx, ebx
0x180037a84  mov     rdx, [rsp+48h+ulCookie]; ulCookie
0x180037a89  xor     ecx, ecx; dwFlags
0x180037a8b  call    cs:__imp_DeactivateActCtx
0x180037a91  test    esi, esi
0x180037a93  jz      short loc_180037A9D
0x180037a95  mov     ecx, ebx; dwErrCode
0x180037a97  call    cs:__imp_SetLastError
0x180037a9d  mov     eax, edi
0x180037a9f  mov     rbx, [rsp+48h+arg_0]
0x180037aa4  mov     rsi, [rsp+48h+arg_8]
0x180037aa9  add     rsp, 30h
0x180037aad  pop     r15
0x180037aaf  pop     r14
0x180037ab1  pop     rdi
0x180037ab2  retn
0x18003ec0a  push    rbx
0x18003ec0c  push    rbp
0x18003ec0d  push    rdi
0x18003ec0e  sub     rsp, 20h
0x18003ec12  mov     rbp, rdx
0x18003ec15  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003ec1c  jz      short loc_18003EC27
0x18003ec1e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003ec25  jnz     short loc_18003EC59
0x18003ec27  cmp     dword ptr [rbp+20h], 0
0x18003ec2b  jnz     short loc_18003EC3C
0x18003ec2d  mov     edi, 1
0x18003ec32  call    cs:__imp_GetLastError
0x18003ec38  mov     ebx, eax
0x18003ec3a  jmp     short loc_18003EC40
0x18003ec3c  xor     edi, edi
0x18003ec3e  xor     ebx, ebx
0x18003ec40  mov     rdx, [rbp+68h]; ulCookie
0x18003ec44  xor     ecx, ecx; dwFlags
0x18003ec46  call    cs:__imp_DeactivateActCtx
0x18003ec4c  test    edi, edi
0x18003ec4e  jz      short loc_18003EC59
0x18003ec50  mov     ecx, ebx; dwErrCode
0x18003ec52  call    cs:__imp_SetLastError
0x18003ec58  nop
0x18003ec59  add     rsp, 20h
0x18003ec5d  pop     rdi
0x18003ec5e  pop     rbp
0x18003ec5f  pop     rbx
0x18003ec60  retn
```

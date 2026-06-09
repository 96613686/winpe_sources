# IsolationAwareImageList_Read

- ea: `0x180007b88`
- end: `0x180007c57`
- name: `IsolationAwareImageList_Read`
- size: `207`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007420`
- `0x18000879c`

## callees

- `0x180006a44`
- `0x180007918`
- `0x180007b88`
- `0x18000b010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007c49`
- `KERNEL32!SetLastError` at `0x18000ac0a`
- `KERNEL32!SetLastError` at `0x180007c49`
- `KERNEL32!SetLastError` at `0x18000ac0a`
- `KERNEL32!DeactivateActCtx` at `0x180007c3d`
- `KERNEL32!DeactivateActCtx` at `0x18000abfe`
- `KERNEL32!DeactivateActCtx` at `0x180007c3d`
- `KERNEL32!DeactivateActCtx` at `0x18000abfe`
- `KERNEL32!GetLastError` at `0x180007c28`
- `KERNEL32!GetLastError` at `0x18000abea`
- `KERNEL32!GetLastError` at `0x180007c28`
- `KERNEL32!GetLastError` at `0x18000abea`

## string_xrefs

- `0x180007be0`: `ImageList_Read`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_Read(__int64 a1)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64); // rbx
  __int64 v5; // rax
  int v6; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = (__int64 (__fastcall *)(__int64))`IsolationAwareImageList_Read'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( !v3 )
  {
    v5 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_Read");
    v3 = (__int64 (__fastcall *)(__int64))v5;
    if ( !v5 )
      goto LABEL_9;
    `IsolationAwareImageList_Read'::`2'::s_pfn = v5;
  }
  v2 = v3(a1);
LABEL_9:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v6 = 0;
      LastError = 0;
    }
    else
    {
      v6 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v6 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180007b88  mov     rax, rsp
0x180007b8b  mov     [rax+8], rbx
0x180007b8f  mov     [rax+18h], rsi
0x180007b93  push    rdi
0x180007b94  sub     rsp, 30h
0x180007b98  mov     rsi, rcx
0x180007b9b  xor     edi, edi
0x180007b9d  mov     [rax-18h], rdi
0x180007ba1  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_Read@@9@4P6APEAU_IMAGELIST@@PEAUIStream@@@ZEA; _IMAGELIST * (*`IsolationAwareImageList_Read'::`2'::s_pfn)(IStream *)
0x180007ba8  mov     [rax+10h], rdi
0x180007bac  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180007bb2  jnz     short loc_180007BDB
0x180007bb4  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180007bba  jnz     short loc_180007BDB
0x180007bbc  lea     rcx, [rax+10h]; lpCookie
0x180007bc0  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180007bc5  test    eax, eax
0x180007bc7  jnz     short loc_180007BDB
0x180007bc9  xor     eax, eax
0x180007bcb  mov     rbx, [rsp+38h+arg_0]
0x180007bd0  mov     rsi, [rsp+38h+arg_10]
0x180007bd5  add     rsp, 30h
0x180007bd9  pop     rdi
0x180007bda  retn
0x180007bdb  test    rbx, rbx
0x180007bde  jnz     short loc_180007BFB
0x180007be0  lea     rcx, aImagelistRead; "ImageList_Read"
0x180007be7  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180007bec  mov     rbx, rax
0x180007bef  test    rax, rax
0x180007bf2  jz      short loc_180007C0E
0x180007bf4  mov     cs:?s_pfn@?1??IsolationAwareImageList_Read@@9@4P6APEAU_IMAGELIST@@PEAUIStream@@@ZEA, rax; _IMAGELIST * (*`IsolationAwareImageList_Read'::`2'::s_pfn)(IStream *)
0x180007bfb  mov     rcx, rsi
0x180007bfe  mov     rax, rbx
0x180007c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c06  mov     rdi, rax
0x180007c09  mov     [rsp+38h+var_18], rax
0x180007c0e  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007c15  jz      short loc_180007C20
0x180007c17  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007c1e  jnz     short loc_180007C4F
0x180007c20  test    rdi, rdi
0x180007c23  jnz     short loc_180007C32
0x180007c25  lea     esi, [rdi+1]
0x180007c28  call    cs:__imp_GetLastError
0x180007c2e  mov     ebx, eax
0x180007c30  jmp     short loc_180007C36
0x180007c32  xor     esi, esi
0x180007c34  xor     ebx, ebx
0x180007c36  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180007c3b  xor     ecx, ecx; dwFlags
0x180007c3d  call    cs:__imp_DeactivateActCtx
0x180007c43  test    esi, esi
0x180007c45  jz      short loc_180007C4F
0x180007c47  mov     ecx, ebx; dwErrCode
0x180007c49  call    cs:__imp_SetLastError
0x180007c4f  mov     rax, rdi
0x180007c52  jmp     loc_180007BCB
0x18000abc1  push    rbx
0x18000abc3  push    rbp
0x18000abc4  push    rdi
0x18000abc5  sub     rsp, 20h
0x18000abc9  mov     rbp, rdx
0x18000abcc  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000abd3  jz      short loc_18000ABDE
0x18000abd5  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000abdc  jnz     short loc_18000AC11
0x18000abde  cmp     qword ptr [rbp+20h], 0
0x18000abe3  jnz     short loc_18000ABF4
0x18000abe5  mov     edi, 1
0x18000abea  call    cs:__imp_GetLastError
0x18000abf0  mov     ebx, eax
0x18000abf2  jmp     short loc_18000ABF8
0x18000abf4  xor     edi, edi
0x18000abf6  xor     ebx, ebx
0x18000abf8  mov     rdx, [rbp+48h]; ulCookie
0x18000abfc  xor     ecx, ecx; dwFlags
0x18000abfe  call    cs:__imp_DeactivateActCtx
0x18000ac04  test    edi, edi
0x18000ac06  jz      short loc_18000AC11
0x18000ac08  mov     ecx, ebx; dwErrCode
0x18000ac0a  call    cs:__imp_SetLastError
0x18000ac10  nop
0x18000ac11  add     rsp, 20h
0x18000ac15  pop     rdi
0x18000ac16  pop     rbp
0x18000ac17  pop     rbx
0x18000ac18  retn
```

# IsolationAwareImageList_ReadEx

- ea: `0x180009b58`
- end: `0x180009c40`
- name: `IsolationAwareImageList_ReadEx`
- size: `232`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000879c`

## callees

- `0x180006a44`
- `0x180007918`
- `0x180009b58`
- `0x18000b010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x180009c33`
- `KERNEL32!DeactivateActCtx` at `0x18000aef8`
- `KERNEL32!DeactivateActCtx` at `0x180009c33`
- `KERNEL32!DeactivateActCtx` at `0x18000aef8`
- `KERNEL32!GetLastError` at `0x180009b9b`
- `KERNEL32!GetLastError` at `0x180009bda`
- `KERNEL32!GetLastError` at `0x180009b9b`
- `KERNEL32!GetLastError` at `0x180009bda`

## string_xrefs

- `0x180009bc6`: `ImageList_ReadEx`

## pseudocode

```c
signed int __fastcall IsolationAwareImageList_ReadEx(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 (__fastcall *v7)(__int64, __int64, __int64, __int64); // rbx
  signed int result; // eax
  __int64 v9; // rax
  signed int LastError; // ebx
  ULONG_PTR ulCookie[7]; // [rsp+30h] [rbp-38h] BYREF

  v7 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))`IsolationAwareImageList_ReadEx'::`2'::s_pfn;
  ulCookie[0] = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(ulCookie) )
  {
    result = GetLastError();
    if ( !result )
      result = 1359;
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( !v7 )
  {
    v9 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_ReadEx");
    v7 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1359;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_17;
    }
    `IsolationAwareImageList_ReadEx'::`2'::s_pfn = v9;
  }
  LastError = v7(1, a2, a3, a4);
LABEL_17:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie[0]);
  return LastError;
}

```

## disassembly

```asm
0x180009b58  push    rbx
0x180009b5a  push    rsi
0x180009b5b  push    rdi
0x180009b5c  push    r14
0x180009b5e  sub     rsp, 48h
0x180009b62  mov     rdi, r9
0x180009b65  mov     rsi, r8
0x180009b68  mov     r14, rdx
0x180009b6b  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_ReadEx@@9@4P6AJKPEAUIStream@@AEBU_GUID@@PEAPEAX@ZEA; long (*`IsolationAwareImageList_ReadEx'::`2'::s_pfn)(ulong,IStream *,_GUID const &,void * *)
0x180009b72  mov     [rsp+68h+ulCookie], 0
0x180009b7b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180009b82  jnz     short loc_180009BC1
0x180009b84  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180009b8b  jnz     short loc_180009BC1
0x180009b8d  lea     rcx, [rsp+68h+ulCookie]; lpCookie
0x180009b92  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180009b97  test    eax, eax
0x180009b99  jnz     short loc_180009BC1
0x180009b9b  call    cs:__imp_GetLastError
0x180009ba1  mov     ecx, 54Fh
0x180009ba6  test    eax, eax
0x180009ba8  cmovz   eax, ecx
0x180009bab  test    eax, eax
0x180009bad  jle     short loc_180009BB7
0x180009baf  movzx   eax, ax
0x180009bb2  or      eax, 80070000h
0x180009bb7  add     rsp, 48h
0x180009bbb  pop     r14
0x180009bbd  pop     rdi
0x180009bbe  pop     rsi
0x180009bbf  pop     rbx
0x180009bc0  retn
0x180009bc1  test    rbx, rbx
0x180009bc4  jnz     short loc_180009C02
0x180009bc6  lea     rcx, aImagelistReade; "ImageList_ReadEx"
0x180009bcd  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180009bd2  mov     rbx, rax
0x180009bd5  test    rax, rax
0x180009bd8  jnz     short loc_180009BFB
0x180009bda  call    cs:__imp_GetLastError
0x180009be0  mov     ebx, eax
0x180009be2  mov     ecx, 54Fh
0x180009be7  test    eax, eax
0x180009be9  cmovz   ebx, ecx
0x180009bec  test    ebx, ebx
0x180009bee  jle     short loc_180009C1A
0x180009bf0  movzx   ebx, bx
0x180009bf3  or      ebx, 80070000h
0x180009bf9  jmp     short loc_180009C1A
0x180009bfb  mov     cs:?s_pfn@?1??IsolationAwareImageList_ReadEx@@9@4P6AJKPEAUIStream@@AEBU_GUID@@PEAPEAX@ZEA, rax; long (*`IsolationAwareImageList_ReadEx'::`2'::s_pfn)(ulong,IStream *,_GUID const &,void * *)
0x180009c02  mov     r9, rdi
0x180009c05  mov     r8, rsi
0x180009c08  mov     rdx, r14
0x180009c0b  mov     ecx, 1
0x180009c10  mov     rax, rbx
0x180009c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c18  mov     ebx, eax
0x180009c1a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180009c21  jz      short loc_180009C2C
0x180009c23  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180009c2a  jnz     short loc_180009C39
0x180009c2c  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x180009c31  xor     ecx, ecx; dwFlags
0x180009c33  call    cs:__imp_DeactivateActCtx
0x180009c39  mov     eax, ebx
0x180009c3b  jmp     loc_180009BB7
0x18000aed7  push    rbp
0x18000aed9  sub     rsp, 30h
0x18000aedd  mov     rbp, rdx
0x18000aee0  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000aee7  jz      short loc_18000AEF2
0x18000aee9  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000aef0  jnz     short loc_18000AEFF
0x18000aef2  mov     rdx, [rbp+30h]; ulCookie
0x18000aef6  xor     ecx, ecx; dwFlags
0x18000aef8  call    cs:__imp_DeactivateActCtx
0x18000aefe  nop
0x18000aeff  add     rsp, 30h
0x18000af03  pop     rbp
0x18000af04  retn
```

# IsolationAwareImageList_Destroy

- ea: `0x1800079e0`
- end: `0x180007aa3`
- name: `IsolationAwareImageList_Destroy`
- size: `195`
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
- `0x1800079e0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007a8b`
- `KERNEL32!SetLastError` at `0x18000ace3`
- `KERNEL32!SetLastError` at `0x180007a8b`
- `KERNEL32!SetLastError` at `0x18000ace3`
- `KERNEL32!DeactivateActCtx` at `0x180007a7f`
- `KERNEL32!DeactivateActCtx` at `0x18000acd7`
- `KERNEL32!DeactivateActCtx` at `0x180007a7f`
- `KERNEL32!DeactivateActCtx` at `0x18000acd7`
- `KERNEL32!GetLastError` at `0x180007a6a`
- `KERNEL32!GetLastError` at `0x18000acc3`
- `KERNEL32!GetLastError` at `0x180007a6a`
- `KERNEL32!GetLastError` at `0x18000acc3`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_Destroy(__int64 a1)
{
  unsigned int v2; // edi
  __int64 (__fastcall *v3)(__int64); // rbx
  __int64 result; // rax
  FARPROC v5; // rax
  int v6; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = (__int64 (__fastcall *)(__int64))`IsolationAwareImageList_Destroy'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    result = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)result )
      return result;
  }
  if ( !v3 )
  {
    v5 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_Destroy");
    v3 = (__int64 (__fastcall *)(__int64))v5;
    if ( !v5 )
      goto LABEL_8;
    `IsolationAwareImageList_Destroy'::`2'::s_pfn = (__int64)v5;
  }
  v2 = v3(a1);
LABEL_8:
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
0x1800079e0  mov     rax, rsp
0x1800079e3  mov     [rax+8], rbx
0x1800079e7  mov     [rax+18h], rsi
0x1800079eb  push    rdi
0x1800079ec  sub     rsp, 30h
0x1800079f0  mov     rsi, rcx
0x1800079f3  xor     edi, edi
0x1800079f5  mov     [rax-18h], edi
0x1800079f8  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_Destroy@@9@4P6AHPEAU_IMAGELIST@@@ZEA; int (*`IsolationAwareImageList_Destroy'::`2'::s_pfn)(_IMAGELIST *)
0x1800079ff  mov     [rax+10h], rdi
0x180007a03  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180007a09  jnz     short loc_180007A20
0x180007a0b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180007a11  jnz     short loc_180007A20
0x180007a13  lea     rcx, [rax+10h]; lpCookie
0x180007a17  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180007a1c  test    eax, eax
0x180007a1e  jz      short loc_180007A93
0x180007a20  test    rbx, rbx
0x180007a23  jnz     short loc_180007A40
0x180007a25  lea     rcx, aImagelistDestr; "ImageList_Destroy"
0x180007a2c  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180007a31  mov     rbx, rax
0x180007a34  test    rax, rax
0x180007a37  jz      short loc_180007A51
0x180007a39  mov     cs:?s_pfn@?1??IsolationAwareImageList_Destroy@@9@4P6AHPEAU_IMAGELIST@@@ZEA, rax; int (*`IsolationAwareImageList_Destroy'::`2'::s_pfn)(_IMAGELIST *)
0x180007a40  mov     rcx, rsi
0x180007a43  mov     rax, rbx
0x180007a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a4b  mov     edi, eax
0x180007a4d  mov     [rsp+38h+var_18], eax
0x180007a51  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007a58  jz      short loc_180007A63
0x180007a5a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007a61  jnz     short loc_180007A91
0x180007a63  test    edi, edi
0x180007a65  jnz     short loc_180007A74
0x180007a67  lea     esi, [rdi+1]
0x180007a6a  call    cs:__imp_GetLastError
0x180007a70  mov     ebx, eax
0x180007a72  jmp     short loc_180007A78
0x180007a74  xor     esi, esi
0x180007a76  xor     ebx, ebx
0x180007a78  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180007a7d  xor     ecx, ecx; dwFlags
0x180007a7f  call    cs:__imp_DeactivateActCtx
0x180007a85  test    esi, esi
0x180007a87  jz      short loc_180007A91
0x180007a89  mov     ecx, ebx; dwErrCode
0x180007a8b  call    cs:__imp_SetLastError
0x180007a91  mov     eax, edi
0x180007a93  mov     rbx, [rsp+38h+arg_0]
0x180007a98  mov     rsi, [rsp+38h+arg_10]
0x180007a9d  add     rsp, 30h
0x180007aa1  pop     rdi
0x180007aa2  retn
0x18000ac9b  push    rbx
0x18000ac9d  push    rbp
0x18000ac9e  push    rdi
0x18000ac9f  sub     rsp, 20h
0x18000aca3  mov     rbp, rdx
0x18000aca6  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000acad  jz      short loc_18000ACB8
0x18000acaf  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000acb6  jnz     short loc_18000ACEA
0x18000acb8  cmp     dword ptr [rbp+20h], 0
0x18000acbc  jnz     short loc_18000ACCD
0x18000acbe  mov     edi, 1
0x18000acc3  call    cs:__imp_GetLastError
0x18000acc9  mov     ebx, eax
0x18000accb  jmp     short loc_18000ACD1
0x18000accd  xor     edi, edi
0x18000accf  xor     ebx, ebx
0x18000acd1  mov     rdx, [rbp+48h]; ulCookie
0x18000acd5  xor     ecx, ecx; dwFlags
0x18000acd7  call    cs:__imp_DeactivateActCtx
0x18000acdd  test    edi, edi
0x18000acdf  jz      short loc_18000ACEA
0x18000ace1  mov     ecx, ebx; dwErrCode
0x18000ace3  call    cs:__imp_SetLastError
0x18000ace9  nop
0x18000acea  add     rsp, 20h
0x18000acee  pop     rdi
0x18000acef  pop     rbp
0x18000acf0  pop     rbx
0x18000acf1  retn
```

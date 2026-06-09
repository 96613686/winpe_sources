# IsolationAwareImageList_Create

- ea: `0x18000767c`
- end: `0x180007771`
- name: `IsolationAwareImageList_Create`
- size: `245`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006f10`
- `0x180009000`
- `0x18000b220`
- `0x18000e040`
- `0x180010de0`
- `0x180014da8`
- `0x18001fda0`
- `0x180027a80`
- `0x18002d840`
- `0x18002ea20`

## callees

- `0x180005160`
- `0x1800075d0`
- `0x18000767c`
- `0x1800378f4`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007742`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007763`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007763`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007757`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007757`

## string_xrefs

- `0x1800076e2`: `ImageList_Create`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_Create(unsigned int a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(_QWORD, _QWORD, _QWORD, _QWORD, int); // rbx
  __int64 v11; // rax
  int v12; // edi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h]

  v8 = 0;
  v15 = 0;
  v9 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, int))`IsolationAwareImageList_Create'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( !v9 )
  {
    v11 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_Create");
    v9 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, int))v11;
    if ( !v11 )
    {
      v12 = 1;
      goto LABEL_10;
    }
    `IsolationAwareImageList_Create'::`2'::s_pfn = v11;
  }
  v12 = 1;
  v8 = v9(a1, a2, a3, a4, 1);
  v15 = v8;
LABEL_10:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v8 )
    {
      v12 = 0;
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v12 )
      SetLastError(LastError);
  }
  return v8;
}

```

## disassembly

```asm
0x18000767c  push    rbx
0x18000767e  push    rsi
0x18000767f  push    rdi
0x180007680  push    r12
0x180007682  push    r13
0x180007684  push    r14
0x180007686  push    r15
0x180007688  sub     rsp, 40h
0x18000768c  mov     r14d, r9d
0x18000768f  mov     r15d, r8d
0x180007692  mov     r12d, edx
0x180007695  mov     r13d, ecx
0x180007698  xor     edi, edi
0x18000769a  mov     esi, edi
0x18000769c  mov     [rsp+78h+var_40], rdi
0x1800076a1  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_Create@@9@4P6APEAU_IMAGELIST@@HHIHH@ZEA; _IMAGELIST * (*`IsolationAwareImageList_Create'::`2'::s_pfn)(int,int,uint,int,int)
0x1800076a8  mov     [rsp+78h+ulCookie], rdi
0x1800076ad  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x1800076b3  jnz     short loc_1800076DD
0x1800076b5  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x1800076bb  jnz     short loc_1800076DD
0x1800076bd  lea     rcx, [rsp+78h+ulCookie]; lpCookie
0x1800076c2  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800076c7  test    eax, eax
0x1800076c9  jnz     short loc_1800076DD
0x1800076cb  xor     eax, eax
0x1800076cd  add     rsp, 40h
0x1800076d1  pop     r15
0x1800076d3  pop     r14
0x1800076d5  pop     r13
0x1800076d7  pop     r12
0x1800076d9  pop     rdi
0x1800076da  pop     rsi
0x1800076db  pop     rbx
0x1800076dc  retn
0x1800076dd  test    rbx, rbx
0x1800076e0  jnz     short loc_180007706
0x1800076e2  lea     rcx, aImagelistCreat; "ImageList_Create"
0x1800076e9  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x1800076ee  mov     rbx, rax
0x1800076f1  test    rax, rax
0x1800076f4  jz      short loc_1800076FF
0x1800076f6  mov     cs:?s_pfn@?1??IsolationAwareImageList_Create@@9@4P6APEAU_IMAGELIST@@HHIHH@ZEA, rax; _IMAGELIST * (*`IsolationAwareImageList_Create'::`2'::s_pfn)(int,int,uint,int,int)
0x1800076fd  jmp     short loc_180007706
0x1800076ff  mov     edi, 1
0x180007704  jmp     short loc_18000772B
0x180007706  mov     edi, 1
0x18000770b  mov     [rsp+78h+var_58], edi
0x18000770f  mov     r9d, r14d
0x180007712  mov     r8d, r15d
0x180007715  mov     edx, r12d
0x180007718  mov     ecx, r13d
0x18000771b  mov     rax, rbx
0x18000771e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007723  mov     rsi, rax
0x180007726  mov     [rsp+78h+var_40], rax
0x18000772b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007732  jz      short loc_18000773D
0x180007734  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000773b  jnz     short loc_180007769
0x18000773d  test    rsi, rsi
0x180007740  jnz     short loc_18000774C
0x180007742  call    cs:__imp_GetLastError
0x180007748  mov     ebx, eax
0x18000774a  jmp     short loc_180007750
0x18000774c  xor     edi, edi
0x18000774e  xor     ebx, ebx
0x180007750  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x180007755  xor     ecx, ecx; dwFlags
0x180007757  call    cs:__imp_DeactivateActCtx
0x18000775d  test    edi, edi
0x18000775f  jz      short loc_180007769
0x180007761  mov     ecx, ebx; dwErrCode
0x180007763  call    cs:__imp_SetLastError
0x180007769  mov     rax, rsi
0x18000776c  jmp     loc_1800076CD
0x18003eaef  push    rbx
0x18003eaf1  push    rbp
0x18003eaf2  push    rdi
0x18003eaf3  sub     rsp, 30h
0x18003eaf7  mov     rbp, rdx
0x18003eafa  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003eb01  jz      short loc_18003EB0C
0x18003eb03  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003eb0a  jnz     short loc_18003EB3F
0x18003eb0c  cmp     qword ptr [rbp+38h], 0
0x18003eb11  jnz     short loc_18003EB22
0x18003eb13  mov     edi, 1
0x18003eb18  call    cs:__imp_GetLastError
0x18003eb1e  mov     ebx, eax
0x18003eb20  jmp     short loc_18003EB26
0x18003eb22  xor     edi, edi
0x18003eb24  xor     ebx, ebx
0x18003eb26  mov     rdx, [rbp+30h]; ulCookie
0x18003eb2a  xor     ecx, ecx; dwFlags
0x18003eb2c  call    cs:__imp_DeactivateActCtx
0x18003eb32  test    edi, edi
0x18003eb34  jz      short loc_18003EB3F
0x18003eb36  mov     ecx, ebx; dwErrCode
0x18003eb38  call    cs:__imp_SetLastError
0x18003eb3e  nop
0x18003eb3f  add     rsp, 30h
0x18003eb43  pop     rdi
0x18003eb44  pop     rbp
0x18003eb45  pop     rbx
0x18003eb46  retn
```

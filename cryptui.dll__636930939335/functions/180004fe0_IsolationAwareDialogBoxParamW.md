# IsolationAwareDialogBoxParamW

- ea: `0x180004fe0`
- end: `0x1800050a4`
- name: `IsolationAwareDialogBoxParamW`
- size: `196`
- prototype: `__int64 __fastcall(HINSTANCE hInstance, LPCWSTR lpTemplateName, HWND hWndParent, DLGPROC lpDialogFunc, LPARAM)`
- caller_count: `18`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180003710`
- `0x180004350`
- `0x1800046e0`
- `0x180004a88`
- `0x180007f18`
- `0x180013ce4`
- `0x18001fda0`
- `0x180022490`
- `0x180023ce0`
- `0x180023dd0`
- `0x180023ec0`
- `0x180027a80`
- `0x18002c0f0`
- `0x18002c8b0`
- `0x18002e368`
- `0x18002f360`
- `0x18003c5c0`
- `0x18003cfd0`

## callees

- `0x180004fe0`
- `0x180005160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e9df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005099`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e9ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005099`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e9ff`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000508d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003e9f3`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000508d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003e9f3`
- `USER32!DialogBoxParamW` at `0x18000504f`
- `USER32!DialogBoxParamW` at `0x18000504f`

## pseudocode

```c
INT_PTR __fastcall IsolationAwareDialogBoxParamW(
        HINSTANCE hInstance,
        LPCWSTR lpTemplateName,
        HWND hWndParent,
        DLGPROC lpDialogFunc,
        LPARAM dwInitParam)
{
  INT_PTR v10; // rax
  INT_PTR v11; // rsi
  int v12; // edi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+38h] [rbp-30h]

  v15 = -1;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return -1;
  }
  v10 = DialogBoxParamW(hInstance, lpTemplateName, hWndParent, lpDialogFunc, dwInitParam);
  v11 = v10;
  v15 = v10;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v10 == -1 )
    {
      v12 = 1;
      LastError = GetLastError();
    }
    else
    {
      v12 = 0;
      LastError = 0;
    }
    DeactivateActCtx(0, ulCookie);
    if ( v12 )
      SetLastError(LastError);
  }
  return v11;
}

```

## disassembly

```asm
0x180004fe0  push    rbx
0x180004fe2  push    rsi
0x180004fe3  push    rdi
0x180004fe4  push    r14
0x180004fe6  sub     rsp, 48h
0x180004fea  mov     rbx, r9
0x180004fed  mov     rdi, r8
0x180004ff0  mov     rsi, rdx
0x180004ff3  mov     r14, rcx
0x180004ff6  mov     [rsp+68h+var_30], 0FFFFFFFFFFFFFFFFh
0x180004fff  mov     [rsp+68h+ulCookie], 0
0x180005008  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000500f  jnz     short loc_180005036
0x180005011  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180005018  jnz     short loc_180005036
0x18000501a  lea     rcx, [rsp+68h+ulCookie]; lpCookie
0x18000501f  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180005024  test    eax, eax
0x180005026  jnz     short loc_180005036
0x180005028  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000502c  add     rsp, 48h
0x180005030  pop     r14
0x180005032  pop     rdi
0x180005033  pop     rsi
0x180005034  pop     rbx
0x180005035  retn
0x180005036  mov     rax, [rsp+68h+arg_20]
0x18000503e  mov     [rsp+68h+dwInitParam], rax; dwInitParam
0x180005043  mov     r9, rbx; lpDialogFunc
0x180005046  mov     r8, rdi; hWndParent
0x180005049  mov     rdx, rsi; lpTemplateName
0x18000504c  mov     rcx, r14; hInstance
0x18000504f  call    cs:__imp_DialogBoxParamW
0x180005055  mov     rsi, rax
0x180005058  mov     [rsp+68h+var_30], rax
0x18000505d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180005064  jz      short loc_18000506F
0x180005066  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000506d  jnz     short loc_18000509F
0x18000506f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180005073  jnz     short loc_180005082
0x180005075  lea     edi, [rsi+2]
0x180005078  call    cs:__imp_GetLastError
0x18000507e  mov     ebx, eax
0x180005080  jmp     short loc_180005086
0x180005082  xor     edi, edi
0x180005084  xor     ebx, ebx
0x180005086  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x18000508b  xor     ecx, ecx; dwFlags
0x18000508d  call    cs:__imp_DeactivateActCtx
0x180005093  test    edi, edi
0x180005095  jz      short loc_18000509F
0x180005097  mov     ecx, ebx; dwErrCode
0x180005099  call    cs:__imp_SetLastError
0x18000509f  mov     rax, rsi
0x1800050a2  jmp     short loc_18000502C
0x18003e9b6  push    rbx
0x18003e9b8  push    rbp
0x18003e9b9  push    rdi
0x18003e9ba  sub     rsp, 30h
0x18003e9be  mov     rbp, rdx
0x18003e9c1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003e9c8  jz      short loc_18003E9D3
0x18003e9ca  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003e9d1  jnz     short loc_18003EA06
0x18003e9d3  cmp     qword ptr [rbp+38h], 0FFFFFFFFFFFFFFFFh
0x18003e9d8  jnz     short loc_18003E9E9
0x18003e9da  mov     edi, 1
0x18003e9df  call    cs:__imp_GetLastError
0x18003e9e5  mov     ebx, eax
0x18003e9e7  jmp     short loc_18003E9ED
0x18003e9e9  xor     edi, edi
0x18003e9eb  xor     ebx, ebx
0x18003e9ed  mov     rdx, [rbp+30h]; ulCookie
0x18003e9f1  xor     ecx, ecx; dwFlags
0x18003e9f3  call    cs:__imp_DeactivateActCtx
0x18003e9f9  test    edi, edi
0x18003e9fb  jz      short loc_18003EA06
0x18003e9fd  mov     ecx, ebx; dwErrCode
0x18003e9ff  call    cs:__imp_SetLastError
0x18003ea05  nop
0x18003ea06  add     rsp, 30h
0x18003ea0a  pop     rdi
0x18003ea0b  pop     rbp
0x18003ea0c  pop     rbx
0x18003ea0d  retn
```

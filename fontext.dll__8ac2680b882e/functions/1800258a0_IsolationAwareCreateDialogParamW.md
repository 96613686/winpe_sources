# IsolationAwareCreateDialogParamW

- ea: `0x1800258a0`
- end: `0x180025970`
- name: `IsolationAwareCreateDialogParamW`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025470`

## callees

- `0x18001ba28`
- `0x1800258a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025965`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800316cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025965`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800316cc`
- `KERNEL32!DeactivateActCtx` at `0x180025959`
- `KERNEL32!DeactivateActCtx` at `0x1800316c0`
- `KERNEL32!DeactivateActCtx` at `0x180025959`
- `KERNEL32!DeactivateActCtx` at `0x1800316c0`
- `USER32!CreateDialogParamW` at `0x18002591c`
- `USER32!CreateDialogParamW` at `0x18002591c`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateDialogParamW(__int64 a1, const WCHAR *a2, HWND a3, __int64 a4, LPARAM dwInitParam)
{
  HINSTANCE v7; // rsi
  HWND DialogParamW; // rax
  HWND v10; // rdi
  int v11; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+68h] [rbp+20h] BYREF

  v7 = g_hInstance;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  DialogParamW = CreateDialogParamW(v7, a2, a3, CProgressDialog::_s_DlgProc, dwInitParam);
  v10 = DialogParamW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( DialogParamW )
    {
      v11 = 0;
      LastError = 0;
    }
    else
    {
      v11 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v11 )
      SetLastError(LastError);
  }
  return v10;
}

```

## disassembly

```asm
0x1800258a0  mov     rax, rsp
0x1800258a3  mov     [rax+8], rbx
0x1800258a7  mov     [rax+10h], rsi
0x1800258ab  mov     [rax+20h], r9
0x1800258af  push    rdi
0x1800258b0  sub     rsp, 40h
0x1800258b4  mov     rbx, r8
0x1800258b7  mov     rdi, rdx
0x1800258ba  mov     rsi, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800258c1  mov     qword ptr [rax-18h], 0
0x1800258c9  mov     qword ptr [rax+20h], 0
0x1800258d1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800258d8  jnz     short loc_180025902
0x1800258da  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800258e1  jnz     short loc_180025902
0x1800258e3  lea     rcx, [rax+20h]; lpCookie
0x1800258e7  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800258ec  test    eax, eax
0x1800258ee  jnz     short loc_180025902
0x1800258f0  xor     eax, eax
0x1800258f2  mov     rbx, [rsp+48h+arg_0]
0x1800258f7  mov     rsi, [rsp+48h+arg_8]
0x1800258fc  add     rsp, 40h
0x180025900  pop     rdi
0x180025901  retn
0x180025902  mov     rax, [rsp+48h+arg_20]
0x180025907  mov     [rsp+48h+dwInitParam], rax; dwInitParam
0x18002590c  lea     r9, ?_s_DlgProc@CProgressDialog@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180025913  mov     r8, rbx; hWndParent
0x180025916  mov     rdx, rdi; lpTemplateName
0x180025919  mov     rcx, rsi; hInstance
0x18002591c  call    cs:__imp_CreateDialogParamW
0x180025922  mov     rdi, rax
0x180025925  mov     [rsp+48h+var_18], rax
0x18002592a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180025931  jz      short loc_18002593C
0x180025933  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002593a  jnz     short loc_18002596B
0x18002593c  test    rdi, rdi
0x18002593f  jnz     short loc_18002594E
0x180025941  lea     esi, [rdi+1]
0x180025944  call    cs:__imp_GetLastError
0x18002594a  mov     ebx, eax
0x18002594c  jmp     short loc_180025952
0x18002594e  xor     esi, esi
0x180025950  xor     ebx, ebx
0x180025952  mov     rdx, [rsp+48h+ulCookie]; ulCookie
0x180025957  xor     ecx, ecx; dwFlags
0x180025959  call    cs:__imp_DeactivateActCtx
0x18002595f  test    esi, esi
0x180025961  jz      short loc_18002596B
0x180025963  mov     ecx, ebx; dwErrCode
0x180025965  call    cs:__imp_SetLastError
0x18002596b  mov     rax, rdi
0x18002596e  jmp     short loc_1800258F2
0x180031683  push    rbx
0x180031685  push    rbp
0x180031686  push    rdi
0x180031687  sub     rsp, 30h
0x18003168b  mov     rbp, rdx
0x18003168e  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180031695  jz      short loc_1800316A0
0x180031697  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003169e  jnz     short loc_1800316D3
0x1800316a0  cmp     qword ptr [rbp+30h], 0
0x1800316a5  jnz     short loc_1800316B6
0x1800316a7  mov     edi, 1
0x1800316ac  call    cs:__imp_GetLastError
0x1800316b2  mov     ebx, eax
0x1800316b4  jmp     short loc_1800316BA
0x1800316b6  xor     edi, edi
0x1800316b8  xor     ebx, ebx
0x1800316ba  mov     rdx, [rbp+68h]; ulCookie
0x1800316be  xor     ecx, ecx; dwFlags
0x1800316c0  call    cs:__imp_DeactivateActCtx
0x1800316c6  test    edi, edi
0x1800316c8  jz      short loc_1800316D3
0x1800316ca  mov     ecx, ebx; dwErrCode
0x1800316cc  call    cs:__imp_SetLastError
0x1800316d2  nop
0x1800316d3  add     rsp, 30h
0x1800316d7  pop     rdi
0x1800316d8  pop     rbp
0x1800316d9  pop     rbx
0x1800316da  retn
```

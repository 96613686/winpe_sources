# IsolationAwareCreateDialogParamW

- ea: `0x18002fbb8`
- end: `0x18002fc82`
- name: `IsolationAwareCreateDialogParamW`
- size: `202`
- prototype: `__int64 __fastcall(HINSTANCE hInstance)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002f1a0`

## callees

- `0x18002d87c`
- `0x18002fbb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d16b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d16b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fc77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d18b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fc77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d18b`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002fc6b`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005d17f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002fc6b`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005d17f`
- `USER32!CreateDialogParamW` at `0x18002fc2e`
- `USER32!CreateDialogParamW` at `0x18002fc2e`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateDialogParamW(HINSTANCE hInstance, __int64 a2, HWND a3)
{
  HWND DialogParamW; // rax
  HWND v7; // rbx
  int v8; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+68h] [rbp+20h] BYREF

  ulCookie = 0;
  if ( !__PAIR64__(IsolationAwarePrivateT_SqbjaYRiRY, IsolationAwarePrivateT_SAbnPgpgk)
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  DialogParamW = CreateDialogParamW(
                   hInstance,
                   (LPCWSTR)0x66,
                   a3,
                   ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc,
                   0);
  v7 = DialogParamW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( DialogParamW )
    {
      v8 = 0;
      LastError = 0;
    }
    else
    {
      v8 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v8 )
      SetLastError(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x18002fbb8  mov     rax, rsp
0x18002fbbb  mov     [rax+8], rbx
0x18002fbbf  mov     [rax+10h], rsi
0x18002fbc3  mov     [rax+20h], r9
0x18002fbc7  push    rdi
0x18002fbc8  sub     rsp, 40h
0x18002fbcc  mov     rbx, r8
0x18002fbcf  mov     rdi, rcx
0x18002fbd2  mov     qword ptr [rax-18h], 0
0x18002fbda  mov     qword ptr [rax+20h], 0
0x18002fbe2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002fbe9  jnz     short loc_18002FC13
0x18002fbeb  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002fbf2  jnz     short loc_18002FC13
0x18002fbf4  lea     rcx, [rax+20h]; lpCookie
0x18002fbf8  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18002fbfd  test    eax, eax
0x18002fbff  jnz     short loc_18002FC13
0x18002fc01  xor     eax, eax
0x18002fc03  mov     rbx, [rsp+48h+arg_0]
0x18002fc08  mov     rsi, [rsp+48h+arg_8]
0x18002fc0d  add     rsp, 40h
0x18002fc11  pop     rdi
0x18002fc12  retn
0x18002fc13  mov     [rsp+48h+dwInitParam], 0; dwInitParam
0x18002fc1c  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18002fc23  mov     r8, rbx; hWndParent
0x18002fc26  mov     edx, 66h ; 'f'; lpTemplateName
0x18002fc2b  mov     rcx, rdi; hInstance
0x18002fc2e  call    cs:__imp_CreateDialogParamW
0x18002fc34  mov     rbx, rax
0x18002fc37  mov     [rsp+48h+var_18], rax
0x18002fc3c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002fc43  jz      short loc_18002FC4E
0x18002fc45  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002fc4c  jnz     short loc_18002FC7D
0x18002fc4e  test    rbx, rbx
0x18002fc51  jnz     short loc_18002FC60
0x18002fc53  lea     esi, [rbx+1]
0x18002fc56  call    cs:__imp_GetLastError
0x18002fc5c  mov     edi, eax
0x18002fc5e  jmp     short loc_18002FC64
0x18002fc60  xor     esi, esi
0x18002fc62  xor     edi, edi
0x18002fc64  mov     rdx, [rsp+48h+ulCookie]; ulCookie
0x18002fc69  xor     ecx, ecx; dwFlags
0x18002fc6b  call    cs:__imp_DeactivateActCtx
0x18002fc71  test    esi, esi
0x18002fc73  jz      short loc_18002FC7D
0x18002fc75  mov     ecx, edi; dwErrCode
0x18002fc77  call    cs:__imp_SetLastError
0x18002fc7d  mov     rax, rbx
0x18002fc80  jmp     short loc_18002FC03
0x18005d142  push    rbx
0x18005d144  push    rbp
0x18005d145  push    rdi
0x18005d146  sub     rsp, 30h
0x18005d14a  mov     rbp, rdx
0x18005d14d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18005d154  jz      short loc_18005D15F
0x18005d156  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18005d15d  jnz     short loc_18005D192
0x18005d15f  cmp     qword ptr [rbp+30h], 0
0x18005d164  jnz     short loc_18005D175
0x18005d166  mov     edi, 1
0x18005d16b  call    cs:__imp_GetLastError
0x18005d171  mov     ebx, eax
0x18005d173  jmp     short loc_18005D179
0x18005d175  xor     edi, edi
0x18005d177  xor     ebx, ebx
0x18005d179  mov     rdx, [rbp+68h]; ulCookie
0x18005d17d  xor     ecx, ecx; dwFlags
0x18005d17f  call    cs:__imp_DeactivateActCtx
0x18005d185  test    edi, edi
0x18005d187  jz      short loc_18005D192
0x18005d189  mov     ecx, ebx; dwErrCode
0x18005d18b  call    cs:__imp_SetLastError
0x18005d191  nop
0x18005d192  add     rsp, 30h
0x18005d196  pop     rdi
0x18005d197  pop     rbp
0x18005d198  pop     rbx
0x18005d199  retn
```

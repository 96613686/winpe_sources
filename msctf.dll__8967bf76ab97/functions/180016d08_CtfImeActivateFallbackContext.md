# CtfImeActivateFallbackContext

- ea: `0x180016d08`
- end: `0x180016db8`
- name: `CtfImeActivateFallbackContext`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180018714`

## callees

- `0x180015850`
- `0x180016d08`
- `0x18001b810`
- `0x18001cc80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d40`
- `USER32!GetFocus` at `0x180016d2a`
- `USER32!GetFocus` at `0x180016d2a`
- `USER32!GetKeyboardLayout` at `0x180016d58`
- `USER32!GetKeyboardLayout` at `0x180016d58`
- `USER32!GetWindowThreadProcessId` at `0x180016d38`
- `USER32!GetWindowThreadProcessId` at `0x180016d38`
- `IMM32!ImmGetContext` at `0x180016d4d`
- `IMM32!ImmGetContext` at `0x180016d4d`

## pseudocode

```c
int CtfImeActivateFallbackContext()
{
  CicBridge **TLS; // rax
  struct TLS *v1; // rdi
  CicBridge *v2; // rsi
  HWND Focus; // rbp
  DWORD WindowThreadProcessId; // ebx
  HIMC Context; // rbx

  TLS = (CicBridge **)TLS::GetTLS();
  v1 = (struct TLS *)TLS;
  if ( !TLS )
  {
    CicTrace(1u, "CtfImeActivateFallbackContext. ptls==NULL.");
    return -2147024882;
  }
  v2 = *TLS;
  if ( !*TLS )
  {
    CicTrace(1u, "CtfImeActivateFallbackContext. cic==NULL.");
    return -2147024882;
  }
  Focus = GetFocus();
  WindowThreadProcessId = GetWindowThreadProcessId(Focus, 0);
  if ( GetCurrentThreadId() != WindowThreadProcessId )
    return 1;
  Context = ImmGetContext(Focus);
  GetKeyboardLayout(0);
  return CicBridge::AssociateFocus(v2, v1, Context, 1, Focus, 1, 1);
}

```

## disassembly

```asm
0x180016d08  push    rbx
0x180016d0a  push    rbp
0x180016d0b  push    rsi
0x180016d0c  push    rdi
0x180016d0d  sub     rsp, 48h
0x180016d11  call    ?GetTLS@TLS@@SAPEAV1@XZ; TLS::GetTLS(void)
0x180016d16  mov     rdi, rax
0x180016d19  test    rax, rax
0x180016d1c  jz      loc_180016DA8
0x180016d22  mov     rsi, [rax]
0x180016d25  test    rsi, rsi
0x180016d28  jz      short loc_180016D89
0x180016d2a  call    cs:__imp_GetFocus
0x180016d30  mov     rcx, rax; hWnd
0x180016d33  xor     edx, edx; lpdwProcessId
0x180016d35  mov     rbp, rax
0x180016d38  call    cs:__imp_GetWindowThreadProcessId
0x180016d3e  mov     ebx, eax
0x180016d40  call    cs:__imp_GetCurrentThreadId
0x180016d46  cmp     eax, ebx
0x180016d48  jnz     short loc_180016DB1
0x180016d4a  mov     rcx, rbp; HWND
0x180016d4d  call    cs:__imp_ImmGetContext
0x180016d53  xor     ecx, ecx; idThread
0x180016d55  mov     rbx, rax
0x180016d58  call    cs:__imp_GetKeyboardLayout
0x180016d5e  mov     [rsp+68h+var_38], 1; int
0x180016d66  mov     r9d, 1; int
0x180016d6c  mov     [rsp+68h+var_40], 1; int
0x180016d74  mov     r8, rbx; HIMC
0x180016d77  mov     rdx, rdi; struct TLS *
0x180016d7a  mov     [rsp+68h+var_48], rbp; HWND
0x180016d7f  mov     rcx, rsi; this
0x180016d82  call    ?AssociateFocus@CicBridge@@QEAAJPEAVTLS@@PEAUHIMC__@@HPEAUHWND__@@HH@Z; CicBridge::AssociateFocus(TLS *,HIMC__ *,int,HWND__ *,int,int)
0x180016d87  jmp     short loc_180016D9F
0x180016d89  lea     rdx, aCtfimeactivate; "CtfImeActivateFallbackContext. cic==NUL"...
0x180016d90  mov     ecx, 1; unsigned int
0x180016d95  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180016d9a  mov     eax, 8007000Eh
0x180016d9f  add     rsp, 48h
0x180016da3  pop     rdi
0x180016da4  pop     rsi
0x180016da5  pop     rbp
0x180016da6  pop     rbx
0x180016da7  retn
0x180016da8  lea     rdx, aCtfimeactivate_0; "CtfImeActivateFallbackContext. ptls==NU"...
0x180016daf  jmp     short loc_180016D90
0x180016db1  mov     eax, 1
0x180016db6  jmp     short loc_180016D9F
```

# EnumFunc

- ea: `0x1802bf900`
- end: `0x1802bf998`
- name: `EnumFunc`
- size: `152`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1801adc90`
- `0x1801ae334`
- `0x1801ae380`
- `0x1802bf900`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1802bf94a`
- `KERNEL32!GetCurrentProcessId` at `0x1802bf94a`
- `USER32!GetWindow` at `0x1802bf95e`
- `USER32!GetWindow` at `0x1802bf95e`
- `USER32!GetWindowThreadProcessId` at `0x1802bf944`
- `USER32!GetWindowThreadProcessId` at `0x1802bf944`
- `USER32!IsWindowVisible` at `0x1802bf96c`
- `USER32!IsWindowVisible` at `0x1802bf96c`

## pseudocode

```c
BOOL __fastcall EnumFunc(HWND a1, _QWORD *a2)
{
  BOOL result; // eax
  DWORD dwProcessId; // [rsp+20h] [rbp-18h] BYREF

  sub_1801AE334(&word_18064B966);
  dwProcessId = 0;
  GetWindowThreadProcessId(a1, &dwProcessId);
  if ( dwProcessId != GetCurrentProcessId() )
    return 1;
  if ( GetWindow(a1, 4u) )
    return 1;
  result = IsWindowVisible(a1);
  if ( result )
    return 1;
  *a2 = a1;
  return result;
}

```

## disassembly

```asm
0x1802bf900  mov     [rsp+arg_10], rbx
0x1802bf905  push    rdi
0x1802bf906  mov     eax, 30h
0x1802bf90b  call    __alloca_probe
0x1802bf910  sub     rsp, rax
0x1802bf913  mov     rax, cs:__security_cookie
0x1802bf91a  xor     rax, rsp
0x1802bf91d  mov     [rsp+38h+var_10], rax
0x1802bf922  mov     rbx, rcx
0x1802bf925  mov     rdi, rdx
0x1802bf928  lea     rcx, word_18064B966
0x1802bf92f  call    sub_1801AE334
0x1802bf934  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x1802bf939  mov     [rsp+38h+dwProcessId], 0
0x1802bf941  mov     rcx, rbx; hWnd
0x1802bf944  call    cs:GetWindowThreadProcessId
0x1802bf94a  call    cs:GetCurrentProcessId
0x1802bf950  cmp     [rsp+38h+dwProcessId], eax
0x1802bf954  jnz     short loc_1802BF97B
0x1802bf956  mov     edx, 4; uCmd
0x1802bf95b  mov     rcx, rbx; hWnd
0x1802bf95e  call    cs:GetWindow
0x1802bf964  test    rax, rax
0x1802bf967  jnz     short loc_1802BF97B
0x1802bf969  mov     rcx, rbx; hWnd
0x1802bf96c  call    cs:IsWindowVisible
0x1802bf972  test    eax, eax
0x1802bf974  jnz     short loc_1802BF97B
0x1802bf976  mov     [rdi], rbx
0x1802bf979  jmp     short loc_1802BF980
0x1802bf97b  mov     eax, 1
0x1802bf980  mov     rcx, [rsp+38h+var_10]
0x1802bf985  xor     rcx, rsp; StackCookie
0x1802bf988  call    __security_check_cookie
0x1802bf98d  mov     rbx, [rsp+38h+arg_10]
0x1802bf992  add     rsp, 30h
0x1802bf996  pop     rdi
0x1802bf997  retn
```

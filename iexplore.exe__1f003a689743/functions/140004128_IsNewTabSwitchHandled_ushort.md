# IsNewTabSwitchHandled(ushort *)

- ea: `0x140004128`
- end: `0x140004223`
- name: `?IsNewTabSwitchHandled@@YAHPEAG@Z`
- size: `251`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400014e4`

## callees

- `0x140004128`
- `0x14000566c`
- `0x140005710`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x14000417e`
- `USER32!GetWindowThreadProcessId` at `0x14000417e`
- `USER32!AllowSetForegroundWindow` at `0x140004188`
- `USER32!AllowSetForegroundWindow` at `0x140004188`
- `USER32!FindWindowExW` at `0x140004160`
- `USER32!FindWindowExW` at `0x140004160`
- `USER32!SendMessageTimeoutW` at `0x1400041d5`
- `USER32!SendMessageTimeoutW` at `0x1400041d5`
- `USER32!IsWindowVisible` at `0x14000419e`
- `USER32!IsWindowVisible` at `0x14000419e`
- `USER32!IsWindowEnabled` at `0x140004191`
- `USER32!IsWindowEnabled` at `0x140004191`

## pseudocode

```c
__int64 __fastcall IsNewTabSwitchHandled(unsigned __int16 *a1)
{
  unsigned int v1; // edi
  HWND v3; // rbx
  HWND Window; // rax
  __int64 v5; // rdx
  DWORD dwProcessId; // [rsp+68h] [rbp+10h] BYREF
  ULONG_PTR dwResult; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  if ( IsCommandSwitchPresent(a1, L"-newtab") )
  {
    v3 = 0;
    while ( 1 )
    {
      Window = FindWindowExW(0, v3, L"IEFrame", 0);
      v3 = Window;
      if ( !Window )
        break;
      dwProcessId = 0;
      GetWindowThreadProcessId(Window, &dwProcessId);
      AllowSetForegroundWindow(dwProcessId);
      if ( IsWindowEnabled(v3) )
      {
        if ( IsWindowVisible(v3) )
        {
          dwResult = 0;
          if ( SendMessageTimeoutW(v3, 0x80DAu, 0, 0, 2u, 0x190u, &dwResult) )
          {
            if ( (dwResult & 0x80000000) == 0LL )
            {
              v1 = 1;
              v5 = -1;
              do
                ++v5;
              while ( a1[v5] );
              FindOrRemoveCommandSwitch(a1, v5 + 1, L"-newtab", 1);
              return v1;
            }
          }
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140004128  mov     [rsp+arg_0], rbx
0x14000412d  push    rbp
0x14000412e  push    rsi
0x14000412f  push    rdi
0x140004130  sub     rsp, 40h
0x140004134  xor     ebp, ebp
0x140004136  lea     rdx, aNewtab; "-newtab"
0x14000413d  mov     edi, ebp
0x14000413f  mov     rsi, rcx
0x140004142  call    ?IsCommandSwitchPresent@@YA_NPEAG0@Z; IsCommandSwitchPresent(ushort *,ushort *)
0x140004147  test    al, al
0x140004149  jz      loc_140004214
0x14000414f  mov     ebx, ebp
0x140004151  xor     r9d, r9d; lpszWindow
0x140004154  lea     r8, szClass; "IEFrame"
0x14000415b  mov     rdx, rbx; hWndChildAfter
0x14000415e  xor     ecx, ecx; hWndParent
0x140004160  call    cs:__imp_FindWindowExW
0x140004166  mov     rbx, rax
0x140004169  test    rax, rax
0x14000416c  jz      loc_140004214
0x140004172  lea     rdx, [rsp+58h+dwProcessId]; lpdwProcessId
0x140004177  mov     [rsp+58h+dwProcessId], ebp
0x14000417b  mov     rcx, rax; hWnd
0x14000417e  call    cs:__imp_GetWindowThreadProcessId
0x140004184  mov     ecx, [rsp+58h+dwProcessId]; dwProcessId
0x140004188  call    cs:__imp_AllowSetForegroundWindow
0x14000418e  mov     rcx, rbx; hWnd
0x140004191  call    cs:__imp_IsWindowEnabled
0x140004197  test    eax, eax
0x140004199  jz      short loc_140004151
0x14000419b  mov     rcx, rbx; hWnd
0x14000419e  call    cs:__imp_IsWindowVisible
0x1400041a4  test    eax, eax
0x1400041a6  jz      short loc_140004151
0x1400041a8  lea     rax, [rsp+58h+dwResult]
0x1400041ad  mov     [rsp+58h+dwResult], rbp
0x1400041b2  mov     [rsp+58h+lpdwResult], rax; lpdwResult
0x1400041b7  xor     r9d, r9d; lParam
0x1400041ba  mov     [rsp+58h+uTimeout], 190h; uTimeout
0x1400041c2  xor     r8d, r8d; wParam
0x1400041c5  mov     edx, 80DAh; Msg
0x1400041ca  mov     [rsp+58h+fuFlags], 2; fuFlags
0x1400041d2  mov     rcx, rbx; hWnd
0x1400041d5  call    cs:__imp_SendMessageTimeoutW
0x1400041db  test    rax, rax
0x1400041de  jz      loc_140004151
0x1400041e4  cmp     dword ptr [rsp+58h+dwResult], ebp
0x1400041e8  jl      loc_140004151
0x1400041ee  mov     edi, 1
0x1400041f3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400041f7  inc     rdx
0x1400041fa  cmp     [rsi+rdx*2], bp
0x1400041fe  jnz     short loc_1400041F7
0x140004200  inc     edx; unsigned int
0x140004202  lea     r8, aNewtab; "-newtab"
0x140004209  mov     r9b, dil; bool
0x14000420c  mov     rcx, rsi; unsigned __int16 *
0x14000420f  call    ?FindOrRemoveCommandSwitch@@YA_NPEAGKPEBG_N@Z; FindOrRemoveCommandSwitch(ushort *,ulong,ushort const *,bool)
0x140004214  mov     rbx, [rsp+58h+arg_0]
0x140004219  mov     eax, edi
0x14000421b  add     rsp, 40h
0x14000421f  pop     rdi
0x140004220  pop     rsi
0x140004221  pop     rbp
0x140004222  retn
```

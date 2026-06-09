# TF_SendLangBandMsg

- ea: `0x1800a5690`
- end: `0x1800a5722`
- name: `TF_SendLangBandMsg`
- size: `146`
- prototype: `__int64 __fastcall(LPARAM lParam)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800a5690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a56b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a56b9`
- `USER32!SendMessageW` at `0x1800a56f4`
- `USER32!SendMessageW` at `0x1800a56f4`
- `USER32!PostThreadMessageW` at `0x1800a570c`
- `USER32!PostThreadMessageW` at `0x1800a570c`
- `USER32!GetWindowThreadProcessId` at `0x1800a56b1`
- `USER32!GetWindowThreadProcessId` at `0x1800a56b1`

## pseudocode

```c
BOOL __fastcall TF_SendLangBandMsg(HWND lParam, int a2)
{
  WPARAM v2; // rbx
  DWORD WindowThreadProcessId; // esi
  int v5; // ebx
  int v6; // ebx
  LPARAM v8; // r9
  DWORD v9; // [rsp+40h] [rbp+18h] BYREF

  v2 = a2;
  v9 = 0;
  WindowThreadProcessId = GetWindowThreadProcessId(lParam, &v9);
  if ( WindowThreadProcessId != GetCurrentThreadId() )
    return PostThreadMessageW(WindowThreadProcessId, g_msgPrivate, v2, (LPARAM)lParam);
  v5 = v2 - 25;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return 0;
      v8 = 2;
    }
    else
    {
      v8 = 0;
    }
  }
  else
  {
    v8 = 1;
  }
  SendMessageW(lParam, 0x505u, 0, v8);
  return 1;
}

```

## disassembly

```asm
0x1800a5690  mov     rax, rsp
0x1800a5693  mov     [rax+8], rbx
0x1800a5697  mov     [rax+10h], rsi
0x1800a569b  push    rdi
0x1800a569c  sub     rsp, 20h
0x1800a56a0  movsxd  rbx, edx
0x1800a56a3  mov     rdi, rcx
0x1800a56a6  lea     rdx, [rax+18h]; lpdwProcessId
0x1800a56aa  mov     dword ptr [rax+18h], 0
0x1800a56b1  call    cs:__imp_GetWindowThreadProcessId
0x1800a56b7  mov     esi, eax
0x1800a56b9  call    cs:__imp_GetCurrentThreadId
0x1800a56bf  cmp     esi, eax
0x1800a56c1  jnz     short loc_1800A56FE
0x1800a56c3  mov     esi, 1
0x1800a56c8  sub     ebx, 19h
0x1800a56cb  jz      short loc_1800A56E6
0x1800a56cd  sub     ebx, esi
0x1800a56cf  jz      short loc_1800A56E1
0x1800a56d1  cmp     ebx, esi
0x1800a56d3  jz      short loc_1800A56D9
0x1800a56d5  xor     eax, eax
0x1800a56d7  jmp     short loc_1800A5712
0x1800a56d9  mov     r9d, 2
0x1800a56df  jmp     short loc_1800A56E9
0x1800a56e1  xor     r9d, r9d
0x1800a56e4  jmp     short loc_1800A56E9
0x1800a56e6  mov     r9, rsi; lParam
0x1800a56e9  xor     r8d, r8d; wParam
0x1800a56ec  mov     edx, 505h; Msg
0x1800a56f1  mov     rcx, rdi; hWnd
0x1800a56f4  call    cs:__imp_SendMessageW
0x1800a56fa  mov     eax, esi
0x1800a56fc  jmp     short loc_1800A5712
0x1800a56fe  mov     edx, cs:?g_msgPrivate@@3IA; Msg
0x1800a5704  mov     r8, rbx; wParam
0x1800a5707  mov     r9, rdi; lParam
0x1800a570a  mov     ecx, esi; idThread
0x1800a570c  call    cs:__imp_PostThreadMessageW
0x1800a5712  mov     rbx, [rsp+28h+arg_0]
0x1800a5717  mov     rsi, [rsp+28h+arg_8]
0x1800a571c  add     rsp, 20h
0x1800a5720  pop     rdi
0x1800a5721  retn
```

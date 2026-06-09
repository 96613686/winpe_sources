# OleSetClipboardWithFallbackInternal

- ea: `0x1800d83d0`
- end: `0x1800d8539`
- name: `OleSetClipboardWithFallbackInternal`
- size: `361`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d6714`

## callees

- `0x1800d8160`
- `0x1800d83d0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d84ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d84ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d84d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d84d7`
- `USER32!SetWindowLongPtrW` at `0x1800d842e`
- `USER32!SetWindowLongPtrW` at `0x1800d846b`
- `USER32!SetWindowLongPtrW` at `0x1800d842e`
- `USER32!SetWindowLongPtrW` at `0x1800d846b`
- `USER32!EmptyClipboard` at `0x1800d8437`
- `USER32!EmptyClipboard` at `0x1800d8437`
- `USER32!CloseClipboard` at `0x1800d84e1`
- `USER32!CloseClipboard` at `0x1800d84e1`
- `USER32!SetClipboardData` at `0x1800d84c7`
- `USER32!SetClipboardData` at `0x1800d84c7`
- `USER32!OpenClipboard` at `0x1800d8410`
- `USER32!OpenClipboard` at `0x1800d8410`

## pseudocode

```c
__int64 __fastcall OleSetClipboardWithFallbackInternal(LONG_PTR dwNewLong)
{
  HWND v2; // rax
  HWND v3; // rbx
  unsigned int v4; // ebx
  LONG_PTR v5; // rdi
  __int64 v6; // rcx
  LPVOID v8[5]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+68h] [rbp+10h] BYREF

  v9 = 0;
  memset(v8, 0, 32);
  v2 = (HWND)LockClipboard();
  v3 = v2;
  if ( v2 )
  {
    if ( OpenClipboard(v2) )
    {
      v5 = SetWindowLongPtrW(v3, 0, 0);
      if ( EmptyClipboard() )
      {
        if ( dwNewLong )
        {
          (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)dwNewLong + 8LL))(dwNewLong);
          SetWindowLongPtrW(v3, 0, dwNewLong);
          if ( (*(int (__fastcall **)(LONG_PTR, __int64, __int64 *))(*(_QWORD *)dwNewLong + 64LL))(dwNewLong, 1, &v9) >= 0 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9);
            while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *, _QWORD))(*(_QWORD *)v9 + 24LL))(
                       v9,
                       1,
                       v8,
                       0) )
            {
              SetClipboardData(LOWORD(v8[0]), 0);
              if ( v8[1] )
                CoTaskMemFree(v8[1]);
            }
          }
        }
        v4 = 0;
      }
      else
      {
        v4 = -2147221039;
      }
      CloseClipboard();
    }
    else
    {
      v5 = 0;
      v4 = -2147221040;
    }
    ReleaseSRWLockExclusive(&stru_1801BB4A8);
    if ( v5 )
      (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else
  {
    v4 = -2147467259;
  }
  v6 = v9;
  if ( v9 )
  {
    v9 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x1800d83d0  mov     rax, rsp
0x1800d83d3  mov     [rax+8], rbx
0x1800d83d7  mov     [rax+18h], rsi
0x1800d83db  push    rdi
0x1800d83dc  sub     rsp, 50h
0x1800d83e0  xorps   xmm0, xmm0
0x1800d83e3  mov     qword ptr [rax+10h], 0
0x1800d83eb  movups  xmmword ptr [rax-28h], xmm0
0x1800d83ef  mov     rsi, rcx
0x1800d83f2  movups  xmmword ptr [rax-18h], xmm0
0x1800d83f6  call    LockClipboard
0x1800d83fb  mov     rbx, rax
0x1800d83fe  test    rax, rax
0x1800d8401  jnz     short loc_1800D840D
0x1800d8403  mov     ebx, 80004005h
0x1800d8408  jmp     loc_1800D8508
0x1800d840d  mov     rcx, rbx; hWndNewOwner
0x1800d8410  call    cs:__imp_OpenClipboard
0x1800d8416  test    eax, eax
0x1800d8418  jnz     short loc_1800D8426
0x1800d841a  xor     edi, edi
0x1800d841c  mov     ebx, 800401D0h
0x1800d8421  jmp     loc_1800D84E7
0x1800d8426  xor     r8d, r8d; dwNewLong
0x1800d8429  xor     edx, edx; nIndex
0x1800d842b  mov     rcx, rbx; hWnd
0x1800d842e  call    cs:__imp_SetWindowLongPtrW
0x1800d8434  mov     rdi, rax
0x1800d8437  call    cs:__imp_EmptyClipboard
0x1800d843d  test    eax, eax
0x1800d843f  jnz     short loc_1800D844B
0x1800d8441  mov     ebx, 800401D1h
0x1800d8446  jmp     loc_1800D84E1
0x1800d844b  test    rsi, rsi
0x1800d844e  jz      loc_1800D84DF
0x1800d8454  mov     rax, [rsi]
0x1800d8457  mov     rcx, rsi
0x1800d845a  mov     rax, [rax+8]
0x1800d845e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8463  mov     r8, rsi; dwNewLong
0x1800d8466  xor     edx, edx; nIndex
0x1800d8468  mov     rcx, rbx; hWnd
0x1800d846b  call    cs:__imp_SetWindowLongPtrW
0x1800d8471  mov     rax, [rsi]
0x1800d8474  lea     r8, [rsp+58h+arg_8]
0x1800d8479  mov     ebx, 1
0x1800d847e  mov     rcx, rsi
0x1800d8481  mov     edx, ebx
0x1800d8483  mov     rax, [rax+40h]
0x1800d8487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d848c  test    eax, eax
0x1800d848e  js      short loc_1800D84DF
0x1800d8490  mov     rcx, [rsp+58h+arg_8]
0x1800d8495  mov     rax, [rcx]
0x1800d8498  mov     rax, [rax+28h]
0x1800d849c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d84a1  mov     rcx, [rsp+58h+arg_8]
0x1800d84a6  lea     r8, [rsp+58h+var_28]
0x1800d84ab  xor     r9d, r9d
0x1800d84ae  mov     edx, ebx
0x1800d84b0  mov     rax, [rcx]
0x1800d84b3  mov     rax, [rax+18h]
0x1800d84b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d84bc  test    eax, eax
0x1800d84be  jnz     short loc_1800D84DF
0x1800d84c0  movzx   ecx, [rsp+58h+var_28]; uFormat
0x1800d84c5  xor     edx, edx; hMem
0x1800d84c7  call    cs:__imp_SetClipboardData
0x1800d84cd  mov     rcx, [rsp+58h+pv]; pv
0x1800d84d2  test    rcx, rcx
0x1800d84d5  jz      short loc_1800D84A1
0x1800d84d7  call    cs:__imp_CoTaskMemFree
0x1800d84dd  jmp     short loc_1800D84A1
0x1800d84df  xor     ebx, ebx
0x1800d84e1  call    cs:__imp_CloseClipboard
0x1800d84e7  lea     rcx, stru_1801BB4A8; SRWLock
0x1800d84ee  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d84f4  test    rdi, rdi
0x1800d84f7  jz      short loc_1800D8508
0x1800d84f9  mov     rax, [rdi]
0x1800d84fc  mov     rcx, rdi
0x1800d84ff  mov     rax, [rax+10h]
0x1800d8503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8508  mov     rcx, [rsp+58h+arg_8]
0x1800d850d  test    rcx, rcx
0x1800d8510  jz      short loc_1800D8527
0x1800d8512  mov     [rsp+58h+arg_8], 0
0x1800d851b  mov     rdx, [rcx]
0x1800d851e  mov     rax, [rdx+10h]
0x1800d8522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8527  mov     rsi, [rsp+58h+arg_10]
0x1800d852c  mov     eax, ebx
0x1800d852e  mov     rbx, [rsp+58h+arg_0]
0x1800d8533  add     rsp, 50h
0x1800d8537  pop     rdi
0x1800d8538  retn
```

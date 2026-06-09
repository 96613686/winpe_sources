# OleSetClipboardWithFallbackInternal

- ea: `0x140059700`
- end: `0x140059869`
- name: `OleSetClipboardWithFallbackInternal`
- size: `361`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400579e4`

## callees

- `0x140059490`
- `0x140059700`
- `0x14006b010`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x14005975e`
- `USER32!SetWindowLongPtrW` at `0x14005979b`
- `USER32!SetWindowLongPtrW` at `0x14005975e`
- `USER32!SetWindowLongPtrW` at `0x14005979b`
- `USER32!EmptyClipboard` at `0x140059767`
- `USER32!EmptyClipboard` at `0x140059767`
- `USER32!CloseClipboard` at `0x140059811`
- `USER32!CloseClipboard` at `0x140059811`
- `USER32!OpenClipboard` at `0x140059740`
- `USER32!OpenClipboard` at `0x140059740`
- `USER32!SetClipboardData` at `0x1400597f7`
- `USER32!SetClipboardData` at `0x1400597f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005981e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005981e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140059807`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140059807`

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
    ReleaseSRWLockExclusive(&SRWLock);
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
0x140059700  mov     rax, rsp
0x140059703  mov     [rax+8], rbx
0x140059707  mov     [rax+18h], rsi
0x14005970b  push    rdi
0x14005970c  sub     rsp, 50h
0x140059710  xorps   xmm0, xmm0
0x140059713  mov     qword ptr [rax+10h], 0
0x14005971b  movups  xmmword ptr [rax-28h], xmm0
0x14005971f  mov     rsi, rcx
0x140059722  movups  xmmword ptr [rax-18h], xmm0
0x140059726  call    LockClipboard
0x14005972b  mov     rbx, rax
0x14005972e  test    rax, rax
0x140059731  jnz     short loc_14005973D
0x140059733  mov     ebx, 80004005h
0x140059738  jmp     loc_140059838
0x14005973d  mov     rcx, rbx; hWndNewOwner
0x140059740  call    cs:__imp_OpenClipboard
0x140059746  test    eax, eax
0x140059748  jnz     short loc_140059756
0x14005974a  xor     edi, edi
0x14005974c  mov     ebx, 800401D0h
0x140059751  jmp     loc_140059817
0x140059756  xor     r8d, r8d; dwNewLong
0x140059759  xor     edx, edx; nIndex
0x14005975b  mov     rcx, rbx; hWnd
0x14005975e  call    cs:__imp_SetWindowLongPtrW
0x140059764  mov     rdi, rax
0x140059767  call    cs:__imp_EmptyClipboard
0x14005976d  test    eax, eax
0x14005976f  jnz     short loc_14005977B
0x140059771  mov     ebx, 800401D1h
0x140059776  jmp     loc_140059811
0x14005977b  test    rsi, rsi
0x14005977e  jz      loc_14005980F
0x140059784  mov     rax, [rsi]
0x140059787  mov     rcx, rsi
0x14005978a  mov     rax, [rax+8]
0x14005978e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059793  mov     r8, rsi; dwNewLong
0x140059796  xor     edx, edx; nIndex
0x140059798  mov     rcx, rbx; hWnd
0x14005979b  call    cs:__imp_SetWindowLongPtrW
0x1400597a1  mov     rax, [rsi]
0x1400597a4  lea     r8, [rsp+58h+arg_8]
0x1400597a9  mov     ebx, 1
0x1400597ae  mov     rcx, rsi
0x1400597b1  mov     edx, ebx
0x1400597b3  mov     rax, [rax+40h]
0x1400597b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400597bc  test    eax, eax
0x1400597be  js      short loc_14005980F
0x1400597c0  mov     rcx, [rsp+58h+arg_8]
0x1400597c5  mov     rax, [rcx]
0x1400597c8  mov     rax, [rax+28h]
0x1400597cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400597d1  mov     rcx, [rsp+58h+arg_8]
0x1400597d6  lea     r8, [rsp+58h+var_28]
0x1400597db  xor     r9d, r9d
0x1400597de  mov     edx, ebx
0x1400597e0  mov     rax, [rcx]
0x1400597e3  mov     rax, [rax+18h]
0x1400597e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400597ec  test    eax, eax
0x1400597ee  jnz     short loc_14005980F
0x1400597f0  movzx   ecx, [rsp+58h+var_28]; uFormat
0x1400597f5  xor     edx, edx; hMem
0x1400597f7  call    cs:__imp_SetClipboardData
0x1400597fd  mov     rcx, [rsp+58h+pv]; pv
0x140059802  test    rcx, rcx
0x140059805  jz      short loc_1400597D1
0x140059807  call    cs:__imp_CoTaskMemFree
0x14005980d  jmp     short loc_1400597D1
0x14005980f  xor     ebx, ebx
0x140059811  call    cs:__imp_CloseClipboard
0x140059817  lea     rcx, SRWLock; SRWLock
0x14005981e  call    cs:__imp_ReleaseSRWLockExclusive
0x140059824  test    rdi, rdi
0x140059827  jz      short loc_140059838
0x140059829  mov     rax, [rdi]
0x14005982c  mov     rcx, rdi
0x14005982f  mov     rax, [rax+10h]
0x140059833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059838  mov     rcx, [rsp+58h+arg_8]
0x14005983d  test    rcx, rcx
0x140059840  jz      short loc_140059857
0x140059842  mov     [rsp+58h+arg_8], 0
0x14005984b  mov     rdx, [rcx]
0x14005984e  mov     rax, [rdx+10h]
0x140059852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059857  mov     rsi, [rsp+58h+arg_10]
0x14005985c  mov     eax, ebx
0x14005985e  mov     rbx, [rsp+58h+arg_0]
0x140059863  add     rsp, 50h
0x140059867  pop     rdi
0x140059868  retn
```

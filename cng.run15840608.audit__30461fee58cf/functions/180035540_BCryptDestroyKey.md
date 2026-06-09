# BCryptDestroyKey

- ea: `0x180035540`
- end: `0x1800356c8`
- name: `BCryptDestroyKey`
- size: `392`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800028c0`
- `0x180045c90`
- `0x180082c58`
- `0x1800830dc`
- `0x1800833d0`

## callees

- `0x1800041f0`
- `0x180006470`
- `0x18000743c`
- `0x18001bd90`
- `0x180035540`
- `0x1800358a0`
- `0x18005b260`
- `0x18009d860`

## string_xrefs

- `0x18003561b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003567f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDestroyKey(BCRYPT_KEY_HANDLE hKey)
{
  __int64 v1; // r8
  unsigned int *v3; // rax
  unsigned int *v4; // rdi
  __int64 v5; // rbx
  int v6; // ebp
  void *v7; // r14
  int v8; // eax
  NTSTATUS v9; // esi
  __int64 v10; // rax
  _BYTE *v11; // rcx
  __int64 v13; // r9
  __int64 v14; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 31, v1);
  v3 = (unsigned int *)ValidateBaseKeyHandle(hKey);
  v4 = v3;
  if ( !v3 )
  {
    v9 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 5583);
    return v9;
  }
  v5 = *((_QWORD *)v3 + 1);
  v6 = 0;
  v7 = 0;
  if ( *(_DWORD *)(v5 + 36) == 1 )
  {
    v7 = (void *)*((_QWORD *)v3 + 3);
  }
  else
  {
    if ( *(_DWORD *)(v5 + 36) != 3 )
    {
      if ( *(_DWORD *)(v5 + 36) == 4 )
      {
        v6 = 1;
        v8 = (*(__int64 (__fastcall **)(_QWORD))(v5 + 144))(*((_QWORD *)v3 + 2));
        goto LABEL_7;
      }
      if ( *(_DWORD *)(v5 + 36) != 5 )
      {
        if ( *(_DWORD *)(v5 + 36) == 7 )
        {
          v7 = (void *)*((_QWORD *)v3 + 3);
          v8 = (*(__int64 (__fastcall **)(_QWORD))(v5 + 96))(*((_QWORD *)v3 + 2));
          goto LABEL_7;
        }
        if ( *(_DWORD *)(v5 + 36) != 8 )
        {
          v9 = -1073741816;
          v13 = 5632;
          v14 = 3221225480LL;
          goto LABEL_25;
        }
      }
    }
    v6 = 1;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD))(v5 + 136))(*((_QWORD *)v3 + 2));
LABEL_7:
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = *v4;
    v11 = v4;
    if ( *v4 )
    {
      do
      {
        *v11++ = 0;
        --v10;
      }
      while ( v10 );
    }
    if ( v6 )
      BCryptFree(v4);
    if ( v7 )
      MSCryptFree(v7);
    goto LABEL_14;
  }
  v13 = 5641;
  v14 = (unsigned int)v8;
LABEL_25:
  DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v13);
LABEL_14:
  if ( v5 && v9 >= 0 )
    DecrementReferenceCount(v5);
  return v9;
}

```

## disassembly

```asm
0x180035540  push    rbx
0x180035542  push    rbp
0x180035543  push    rsi
0x180035544  push    rdi
0x180035545  push    r14
0x180035547  sub     rsp, 20h
0x18003554b  mov     rbx, rcx
0x18003554e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035555  lea     rax, WPP_GLOBAL_Control
0x18003555c  cmp     rcx, rax
0x18003555f  jnz     loc_1800355F4
0x180035565  mov     rcx, rbx
0x180035568  call    ValidateBaseKeyHandle
0x18003556d  mov     rdi, rax
0x180035570  test    rax, rax
0x180035573  jz      loc_180035615
0x180035579  mov     rbx, [rax+8]
0x18003557d  xor     ebp, ebp
0x18003557f  xor     r14d, r14d
0x180035582  mov     ecx, [rbx+24h]
0x180035585  sub     ecx, 1
0x180035588  jz      loc_180035690
0x18003558e  sub     ecx, 2
0x180035591  jnz     loc_18003563A
0x180035597  mov     ebp, 1
0x18003559c  mov     rax, [rbx+88h]
0x1800355a3  mov     rcx, [rdi+10h]
0x1800355a7  call    _guard_dispatch_icall
0x1800355ac  mov     esi, eax
0x1800355ae  test    eax, eax
0x1800355b0  js      loc_180035670
0x1800355b6  mov     eax, [rdi]
0x1800355b8  mov     rcx, rdi
0x1800355bb  test    rax, rax
0x1800355be  jz      short loc_1800355CC
0x1800355c0  mov     byte ptr [rcx], 0
0x1800355c3  inc     rcx
0x1800355c6  sub     rax, 1
0x1800355ca  jnz     short loc_1800355C0
0x1800355cc  test    ebp, ebp
0x1800355ce  jnz     loc_180035699
0x1800355d4  test    r14, r14
0x1800355d7  jnz     loc_1800356A6
0x1800355dd  test    rbx, rbx
0x1800355e0  jnz     loc_1800356B3
0x1800355e6  mov     eax, esi
0x1800355e8  add     rsp, 20h
0x1800355ec  pop     r14
0x1800355ee  pop     rdi
0x1800355ef  pop     rsi
0x1800355f0  pop     rbp
0x1800355f1  pop     rbx
0x1800355f2  retn
0x1800355f4  mov     eax, [rcx+2Ch]
0x1800355f7  test    al, 4
0x1800355f9  jz      loc_180035565
0x1800355ff  mov     rcx, [rcx+18h]
0x180035603  mov     edx, 1Fh
0x180035608  mov     r9, rbx
0x18003560b  call    WPP_SF_q
0x180035610  jmp     loc_180035565
0x180035615  mov     r9d, 15CFh
0x18003561b  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180035622  lea     rdx, aStatus; "Status"
0x180035629  mov     ecx, 0C0000008h
0x18003562e  mov     esi, 0C0000008h
0x180035633  call    DebugTraceError
0x180035638  jmp     short loc_1800355E6
0x18003563a  sub     ecx, 1
0x18003563d  jz      loc_1800A0E27
0x180035643  sub     ecx, 1
0x180035646  jz      loc_180035597
0x18003564c  sub     ecx, 2
0x18003564f  jz      loc_1800A0E1A
0x180035655  cmp     ecx, 1
0x180035658  jz      loc_180035597
0x18003565e  mov     esi, 0C0000008h
0x180035663  mov     r9d, 1600h
0x180035669  mov     ecx, 0C0000008h
0x18003566e  jmp     short loc_180035678
0x180035670  mov     r9d, 1609h
0x180035676  mov     ecx, eax
0x180035678  lea     rdx, aStatus; "Status"
0x18003567f  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180035686  call    DebugTraceError
0x18003568b  jmp     loc_1800355DD
0x180035690  mov     r14, [rdi+18h]
0x180035694  jmp     loc_18003559C
0x180035699  mov     rcx, rdi; P
0x18003569c  call    BCryptFree
0x1800356a1  jmp     loc_1800355D4
0x1800356a6  mov     rcx, r14; P
0x1800356a9  call    MSCryptFree
0x1800356ae  jmp     loc_1800355DD
0x1800356b3  test    esi, esi
0x1800356b5  js      loc_1800355E6
0x1800356bb  mov     rcx, rbx
0x1800356be  call    DecrementReferenceCount
0x1800356c3  jmp     loc_1800355E6
0x1800a0e1a  mov     rax, [rbx+60h]
0x1800a0e1e  mov     r14, [rdi+18h]
0x1800a0e22  jmp     loc_1800355A3
0x1800a0e27  mov     rax, [rbx+90h]
0x1800a0e2e  mov     ebp, 1
0x1800a0e33  jmp     loc_1800355A3
```

# BCryptDestroyKey

- ea: `0x18003f5b0`
- end: `0x18003f738`
- name: `BCryptDestroyKey`
- size: `392`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000c9e0`
- `0x18004fd80`
- `0x18008ce48`
- `0x18008d2cc`
- `0x18008d5c0`

## callees

- `0x18000e310`
- `0x180010590`
- `0x18001155c`
- `0x180025ec0`
- `0x18003f5b0`
- `0x18003f910`
- `0x180065430`
- `0x1800a4300`

## string_xrefs

- `0x18003f68b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003f6ef`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x18003f5b0  push    rbx
0x18003f5b2  push    rbp
0x18003f5b3  push    rsi
0x18003f5b4  push    rdi
0x18003f5b5  push    r14
0x18003f5b7  sub     rsp, 20h
0x18003f5bb  mov     rbx, rcx
0x18003f5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f5c5  lea     rax, WPP_GLOBAL_Control
0x18003f5cc  cmp     rcx, rax
0x18003f5cf  jnz     loc_18003F664
0x18003f5d5  mov     rcx, rbx
0x18003f5d8  call    ValidateBaseKeyHandle
0x18003f5dd  mov     rdi, rax
0x18003f5e0  test    rax, rax
0x18003f5e3  jz      loc_18003F685
0x18003f5e9  mov     rbx, [rax+8]
0x18003f5ed  xor     ebp, ebp
0x18003f5ef  xor     r14d, r14d
0x18003f5f2  mov     ecx, [rbx+24h]
0x18003f5f5  sub     ecx, 1
0x18003f5f8  jz      loc_18003F700
0x18003f5fe  sub     ecx, 2
0x18003f601  jnz     loc_18003F6AA
0x18003f607  mov     ebp, 1
0x18003f60c  mov     rax, [rbx+88h]
0x18003f613  mov     rcx, [rdi+10h]
0x18003f617  call    _guard_dispatch_icall
0x18003f61c  mov     esi, eax
0x18003f61e  test    eax, eax
0x18003f620  js      loc_18003F6E0
0x18003f626  mov     eax, [rdi]
0x18003f628  mov     rcx, rdi
0x18003f62b  test    rax, rax
0x18003f62e  jz      short loc_18003F63C
0x18003f630  mov     byte ptr [rcx], 0
0x18003f633  inc     rcx
0x18003f636  sub     rax, 1
0x18003f63a  jnz     short loc_18003F630
0x18003f63c  test    ebp, ebp
0x18003f63e  jnz     loc_18003F709
0x18003f644  test    r14, r14
0x18003f647  jnz     loc_18003F716
0x18003f64d  test    rbx, rbx
0x18003f650  jnz     loc_18003F723
0x18003f656  mov     eax, esi
0x18003f658  add     rsp, 20h
0x18003f65c  pop     r14
0x18003f65e  pop     rdi
0x18003f65f  pop     rsi
0x18003f660  pop     rbp
0x18003f661  pop     rbx
0x18003f662  retn
0x18003f664  mov     eax, [rcx+2Ch]
0x18003f667  test    al, 4
0x18003f669  jz      loc_18003F5D5
0x18003f66f  mov     rcx, [rcx+18h]
0x18003f673  mov     edx, 1Fh
0x18003f678  mov     r9, rbx
0x18003f67b  call    WPP_SF_q
0x18003f680  jmp     loc_18003F5D5
0x18003f685  mov     r9d, 15CFh
0x18003f68b  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f692  lea     rdx, aStatus; "Status"
0x18003f699  mov     ecx, 0C0000008h
0x18003f69e  mov     esi, 0C0000008h
0x18003f6a3  call    DebugTraceError
0x18003f6a8  jmp     short loc_18003F656
0x18003f6aa  sub     ecx, 1
0x18003f6ad  jz      loc_1800A7BC5
0x18003f6b3  sub     ecx, 1
0x18003f6b6  jz      loc_18003F607
0x18003f6bc  sub     ecx, 2
0x18003f6bf  jz      loc_1800A7BB8
0x18003f6c5  cmp     ecx, 1
0x18003f6c8  jz      loc_18003F607
0x18003f6ce  mov     esi, 0C0000008h
0x18003f6d3  mov     r9d, 1600h
0x18003f6d9  mov     ecx, 0C0000008h
0x18003f6de  jmp     short loc_18003F6E8
0x18003f6e0  mov     r9d, 1609h
0x18003f6e6  mov     ecx, eax
0x18003f6e8  lea     rdx, aStatus; "Status"
0x18003f6ef  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f6f6  call    DebugTraceError
0x18003f6fb  jmp     loc_18003F64D
0x18003f700  mov     r14, [rdi+18h]
0x18003f704  jmp     loc_18003F60C
0x18003f709  mov     rcx, rdi; P
0x18003f70c  call    BCryptFree
0x18003f711  jmp     loc_18003F644
0x18003f716  mov     rcx, r14; P
0x18003f719  call    MSCryptFree
0x18003f71e  jmp     loc_18003F64D
0x18003f723  test    esi, esi
0x18003f725  js      loc_18003F656
0x18003f72b  mov     rcx, rbx
0x18003f72e  call    DecrementReferenceCount
0x18003f733  jmp     loc_18003F656
0x1800a7bb8  mov     rax, [rbx+60h]
0x1800a7bbc  mov     r14, [rdi+18h]
0x1800a7bc0  jmp     loc_18003F613
0x1800a7bc5  mov     rax, [rbx+90h]
0x1800a7bcc  mov     ebp, 1
0x1800a7bd1  jmp     loc_18003F613
```

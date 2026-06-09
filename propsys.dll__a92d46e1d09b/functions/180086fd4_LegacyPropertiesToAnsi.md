# _LegacyPropertiesToAnsi

- ea: `0x180086fd4`
- end: `0x180087107`
- name: `_LegacyPropertiesToAnsi`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016208`
- `0x180086cc0`

## callees

- `0x180016208`
- `0x180016688`
- `0x180086eec`
- `0x180086fd4`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18008704a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18008704a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800870a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800870a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008705b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008705b`
- `SHCORE!__imp_SHUnicodeToAnsiCP` at `0x180087099`
- `SHCORE!__imp_SHUnicodeToAnsiCP` at `0x180087099`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LegacyPropertiesToAnsi(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned int v5; // ebp
  unsigned int v6; // r15d
  unsigned int v8; // r9d
  unsigned int v9; // r10d
  unsigned int i; // edi
  const WCHAR *v11; // rcx
  int v12; // r13d
  _BYTE *v13; // r14
  _WORD *v14; // rdx
  unsigned int v16; // [rsp+80h] [rbp+18h]

  v16 = a3;
  v5 = 0;
  v6 = a2;
  if ( (unsigned int)IsAnsiPropertySet(a1, a2, a3, (unsigned int)a3) && v6 != 1200 )
  {
    for ( i = v9; i < v8; ++i )
    {
      if ( *(_WORD *)(a5 + 24LL * i) == 31 )
      {
        v11 = *(const WCHAR **)(a5 + 24LL * i + 8);
        if ( v11 )
        {
          v12 = 3 * lstrlenW(v11);
          v13 = CoTaskMemAlloc(v12 + 3LL);
          if ( !v13 )
          {
            v5 = -2147024882;
            if ( i )
              LegacyPropertiesToUnicode(a1, v6, i, a4, a5);
            return v5;
          }
          v14 = *(_WORD **)(a5 + 24LL * i + 8);
          if ( *v14 )
          {
            if ( !(unsigned int)DoesStringRoundTripCPW(v6, v14, v13, (unsigned int)(v12 + 3)) )
              SHUnicodeToAnsiCP(65001, *(_QWORD *)(a5 + 24LL * i + 8), v13, (unsigned int)(v12 + 3));
          }
          else
          {
            *v13 = 0;
          }
          CoTaskMemFree(*(LPVOID *)(a5 + 24LL * i + 8));
          v8 = v16;
          *(_QWORD *)(a5 + 24LL * i + 8) = v13;
        }
        *(_WORD *)(a5 + 24LL * i) = 30;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180086fd4  mov     [rsp+arg_0], rbx
0x180086fd9  mov     [rsp+arg_18], r9
0x180086fde  mov     [rsp+arg_10], r8d
0x180086fe3  push    rbp
0x180086fe4  push    rsi
0x180086fe5  push    rdi
0x180086fe6  push    r12
0x180086fe8  push    r13
0x180086fea  push    r14
0x180086fec  push    r15
0x180086fee  sub     rsp, 30h
0x180086ff2  xor     r10d, r10d
0x180086ff5  mov     r9d, r8d
0x180086ff8  mov     ebp, r10d
0x180086ffb  mov     r15d, edx
0x180086ffe  mov     r12, rcx
0x180087001  call    _IsAnsiPropertySet
0x180087006  test    eax, eax
0x180087008  jz      loc_1800870F0
0x18008700e  cmp     r15d, 4B0h
0x180087015  jz      loc_1800870F0
0x18008701b  mov     rbx, [rsp+68h+arg_20]
0x180087023  mov     edi, r10d
0x180087026  cmp     edi, r9d
0x180087029  jnb     loc_1800870F0
0x18008702f  mov     eax, edi
0x180087031  lea     rsi, [rax+rax*2]
0x180087035  cmp     word ptr [rbx+rsi*8], 1Fh
0x18008703a  jnz     loc_1800870C5
0x180087040  mov     rcx, [rbx+rsi*8+8]; lpString
0x180087045  test    rcx, rcx
0x180087048  jz      short loc_1800870BF
0x18008704a  call    cs:__imp_lstrlenW
0x180087050  lea     r13d, [rax+rax*2]
0x180087054  movsxd  rcx, r13d
0x180087057  add     rcx, 3; cb
0x18008705b  call    cs:__imp_CoTaskMemAlloc
0x180087061  mov     r14, rax
0x180087064  xor     eax, eax
0x180087066  test    r14, r14
0x180087069  jz      short loc_1800870CC
0x18008706b  mov     rdx, [rbx+rsi*8+8]
0x180087070  cmp     [rdx], ax
0x180087073  jz      short loc_1800870A1
0x180087075  lea     r9d, [r13+3]
0x180087079  mov     r8, r14
0x18008707c  mov     ecx, r15d
0x18008707f  call    _DoesStringRoundTripCPW
0x180087084  test    eax, eax
0x180087086  jnz     short loc_1800870A4
0x180087088  mov     rdx, [rbx+rsi*8+8]
0x18008708d  lea     r9d, [r13+3]
0x180087091  mov     r8, r14
0x180087094  mov     ecx, 0FDE9h
0x180087099  call    cs:__imp_SHUnicodeToAnsiCP
0x18008709f  jmp     short loc_1800870A4
0x1800870a1  mov     [r14], al
0x1800870a4  mov     rcx, [rbx+rsi*8+8]; pv
0x1800870a9  call    cs:__imp_CoTaskMemFree
0x1800870af  mov     r9d, [rsp+68h+arg_10]
0x1800870b7  xor     r10d, r10d
0x1800870ba  mov     [rbx+rsi*8+8], r14
0x1800870bf  mov     word ptr [rbx+rsi*8], 1Eh
0x1800870c5  inc     edi
0x1800870c7  jmp     loc_180087026
0x1800870cc  mov     ebp, 8007000Eh
0x1800870d1  test    edi, edi
0x1800870d3  jz      short loc_1800870F0
0x1800870d5  mov     r9, [rsp+68h+arg_18]
0x1800870dd  mov     r8d, edi
0x1800870e0  mov     edx, r15d
0x1800870e3  mov     [rsp+68h+var_48], rbx
0x1800870e8  mov     rcx, r12
0x1800870eb  call    _LegacyPropertiesToUnicode
0x1800870f0  mov     rbx, [rsp+68h+arg_0]
0x1800870f5  mov     eax, ebp
0x1800870f7  add     rsp, 30h
0x1800870fb  pop     r15
0x1800870fd  pop     r14
0x1800870ff  pop     r13
0x180087101  pop     r12
0x180087103  pop     rdi
0x180087104  pop     rsi
0x180087105  pop     rbp
0x180087106  retn
```

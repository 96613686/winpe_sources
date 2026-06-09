# BCryptDestroyKey

- ea: `0x180036040`
- end: `0x1800361c8`
- name: `BCryptDestroyKey`
- size: `392`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800028c0`
- `0x180046720`
- `0x180083c48`
- `0x1800840cc`
- `0x1800843c0`

## callees

- `0x1800041f0`
- `0x180006470`
- `0x18000743c`
- `0x180018e40`
- `0x180036040`
- `0x1800363a0`
- `0x18005bb50`
- `0x18009f6d0`

## string_xrefs

- `0x18003611b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003617f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x180036040  push    rbx
0x180036042  push    rbp
0x180036043  push    rsi
0x180036044  push    rdi
0x180036045  push    r14
0x180036047  sub     rsp, 20h
0x18003604b  mov     rbx, rcx
0x18003604e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036055  lea     rax, WPP_GLOBAL_Control
0x18003605c  cmp     rcx, rax
0x18003605f  jnz     loc_1800360F4
0x180036065  mov     rcx, rbx
0x180036068  call    ValidateBaseKeyHandle
0x18003606d  mov     rdi, rax
0x180036070  test    rax, rax
0x180036073  jz      loc_180036115
0x180036079  mov     rbx, [rax+8]
0x18003607d  xor     ebp, ebp
0x18003607f  xor     r14d, r14d
0x180036082  mov     ecx, [rbx+24h]
0x180036085  sub     ecx, 1
0x180036088  jz      loc_180036190
0x18003608e  sub     ecx, 2
0x180036091  jnz     loc_18003613A
0x180036097  mov     ebp, 1
0x18003609c  mov     rax, [rbx+88h]
0x1800360a3  mov     rcx, [rdi+10h]
0x1800360a7  call    _guard_dispatch_icall
0x1800360ac  mov     esi, eax
0x1800360ae  test    eax, eax
0x1800360b0  js      loc_180036170
0x1800360b6  mov     eax, [rdi]
0x1800360b8  mov     rcx, rdi
0x1800360bb  test    rax, rax
0x1800360be  jz      short loc_1800360CC
0x1800360c0  mov     byte ptr [rcx], 0
0x1800360c3  inc     rcx
0x1800360c6  sub     rax, 1
0x1800360ca  jnz     short loc_1800360C0
0x1800360cc  test    ebp, ebp
0x1800360ce  jnz     loc_180036199
0x1800360d4  test    r14, r14
0x1800360d7  jnz     loc_1800361A6
0x1800360dd  test    rbx, rbx
0x1800360e0  jnz     loc_1800361B3
0x1800360e6  mov     eax, esi
0x1800360e8  add     rsp, 20h
0x1800360ec  pop     r14
0x1800360ee  pop     rdi
0x1800360ef  pop     rsi
0x1800360f0  pop     rbp
0x1800360f1  pop     rbx
0x1800360f2  retn
0x1800360f4  mov     eax, [rcx+2Ch]
0x1800360f7  test    al, 4
0x1800360f9  jz      loc_180036065
0x1800360ff  mov     rcx, [rcx+18h]
0x180036103  mov     edx, 1Fh
0x180036108  mov     r9, rbx
0x18003610b  call    WPP_SF_q
0x180036110  jmp     loc_180036065
0x180036115  mov     r9d, 15CFh
0x18003611b  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180036122  lea     rdx, aStatus; "Status"
0x180036129  mov     ecx, 0C0000008h
0x18003612e  mov     esi, 0C0000008h
0x180036133  call    DebugTraceError
0x180036138  jmp     short loc_1800360E6
0x18003613a  sub     ecx, 1
0x18003613d  jz      loc_1800A2C57
0x180036143  sub     ecx, 1
0x180036146  jz      loc_180036097
0x18003614c  sub     ecx, 2
0x18003614f  jz      loc_1800A2C4A
0x180036155  cmp     ecx, 1
0x180036158  jz      loc_180036097
0x18003615e  mov     esi, 0C0000008h
0x180036163  mov     r9d, 1600h
0x180036169  mov     ecx, 0C0000008h
0x18003616e  jmp     short loc_180036178
0x180036170  mov     r9d, 1609h
0x180036176  mov     ecx, eax
0x180036178  lea     rdx, aStatus; "Status"
0x18003617f  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180036186  call    DebugTraceError
0x18003618b  jmp     loc_1800360DD
0x180036190  mov     r14, [rdi+18h]
0x180036194  jmp     loc_18003609C
0x180036199  mov     rcx, rdi; P
0x18003619c  call    BCryptFree
0x1800361a1  jmp     loc_1800360D4
0x1800361a6  mov     rcx, r14; P
0x1800361a9  call    MSCryptFree
0x1800361ae  jmp     loc_1800360DD
0x1800361b3  test    esi, esi
0x1800361b5  js      loc_1800360E6
0x1800361bb  mov     rcx, rbx
0x1800361be  call    DecrementReferenceCount
0x1800361c3  jmp     loc_1800360E6
0x1800a2c4a  mov     rax, [rbx+60h]
0x1800a2c4e  mov     r14, [rdi+18h]
0x1800a2c52  jmp     loc_1800360A3
0x1800a2c57  mov     rax, [rbx+90h]
0x1800a2c5e  mov     ebp, 1
0x1800a2c63  jmp     loc_1800360A3
```

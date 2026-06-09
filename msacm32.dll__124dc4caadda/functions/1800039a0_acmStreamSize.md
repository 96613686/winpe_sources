# acmStreamSize

- ea: `0x1800039a0`
- end: `0x180003b2b`
- name: `acmStreamSize`
- size: `395`
- prototype: `MMRESULT __stdcall(HACMSTREAM has, DWORD cbInput, LPDWORD pdwOutputBytes, DWORD fdwSize)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800039a0`
- `0x180003e80`
- `0x180003ec0`
- `0x180009270`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a36`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x180003afa`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x180003afa`

## pseudocode

```c
MMRESULT __stdcall acmStreamSize(HACMSTREAM has, DWORD cbInput, LPDWORD pdwOutputBytes, DWORD fdwSize)
{
  DWORD v8; // ebx
  struct _RTL_CRITICAL_SECTION *v9; // rsi
  _QWORD *v10; // rax
  __int64 (__fastcall *v11)(_QWORD, _QWORD, __int64, HACMSTREAM, LPARAM *); // r10
  MMRESULT v12; // edi
  DWORD v13; // eax
  HDRVR v15; // rcx
  LPARAM lParam2[2]; // [rsp+30h] [rbp-48h] BYREF

  *(_OWORD *)lParam2 = 0;
  if ( !(unsigned int)ValidateWritePointer(pdwOutputBytes, 4) )
    return 11;
  *pdwOutputBytes = 0;
  if ( !(unsigned int)ValidateHandle(has, 3) )
    return 5;
  if ( (fdwSize & 0xFFFFFFF0) != 0 )
    return 10;
  if ( !cbInput )
    return 11;
  HIDWORD(lParam2[0]) = fdwSize;
  v8 = fdwSize & 0xF;
  LODWORD(lParam2[0]) = 16;
  if ( v8 )
  {
    if ( v8 != 1 )
      return 8;
    LODWORD(lParam2[1]) = 0;
    HIDWORD(lParam2[1]) = cbInput;
  }
  else
  {
    lParam2[1] = cbInput;
  }
  v9 = (struct _RTL_CRITICAL_SECTION *)(has - 10);
  EnterCriticalSection((LPCRITICAL_SECTION)has - 1);
  v10 = (_QWORD *)*((_QWORD *)has + 2);
  if ( !v10 )
    goto LABEL_11;
  v11 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, HACMSTREAM, LPARAM *))v10[6];
  if ( v11 )
  {
    if ( v11 == (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, HACMSTREAM, LPARAM *))-1LL )
      v12 = 1;
    else
      v12 = v11(v10[7], *(_QWORD *)((char *)v10 + 20), 24654, has + 7, lParam2);
    goto LABEL_12;
  }
  v15 = (HDRVR)v10[5];
  if ( v15 )
    v12 = SendDriverMessage(v15, 0x604Eu, (LPARAM)(has + 7), (LPARAM)lParam2);
  else
LABEL_11:
    v12 = 5;
LABEL_12:
  LeaveCriticalSection(v9);
  if ( !v12 )
  {
    if ( v8 )
      v13 = lParam2[1];
    else
      v13 = HIDWORD(lParam2[1]);
    *pdwOutputBytes = v13;
    if ( !*pdwOutputBytes )
      return 512;
  }
  return v12;
}

```

## disassembly

```asm
0x1800039a0  push    rbx
0x1800039a2  push    rbp
0x1800039a3  push    rsi
0x1800039a4  push    rdi
0x1800039a5  push    r14
0x1800039a7  sub     rsp, 50h
0x1800039ab  mov     rax, cs:__security_cookie
0x1800039b2  xor     rax, rsp
0x1800039b5  mov     [rsp+78h+var_38], rax
0x1800039ba  mov     esi, edx
0x1800039bc  mov     rdi, rcx
0x1800039bf  xorps   xmm0, xmm0
0x1800039c2  mov     edx, 4
0x1800039c7  mov     rcx, r8
0x1800039ca  mov     ebx, r9d
0x1800039cd  movups  xmmword ptr [rsp+78h+lParam2], xmm0
0x1800039d2  mov     r14, r8
0x1800039d5  call    ValidateWritePointer
0x1800039da  test    eax, eax
0x1800039dc  jz      loc_180003B05
0x1800039e2  xor     ebp, ebp
0x1800039e4  mov     edx, 3
0x1800039e9  mov     rcx, rdi
0x1800039ec  mov     [r14], ebp
0x1800039ef  call    ValidateHandle
0x1800039f4  test    eax, eax
0x1800039f6  jz      loc_180003B13
0x1800039fc  test    ebx, 0FFFFFFF0h
0x180003a02  jnz     loc_180003B0C
0x180003a08  test    esi, esi
0x180003a0a  jz      loc_180003B05
0x180003a10  mov     dword ptr [rsp+78h+lParam2+4], ebx
0x180003a14  and     ebx, 0Fh
0x180003a17  mov     eax, ebx
0x180003a19  mov     dword ptr [rsp+78h+lParam2], 10h
0x180003a21  jnz     loc_180003AD5
0x180003a27  mov     dword ptr [rsp+78h+lParam2+8], esi
0x180003a2b  mov     dword ptr [rsp+78h+lParam2+0Ch], ebp
0x180003a2f  lea     rsi, [rdi-28h]
0x180003a33  mov     rcx, rsi; lpCriticalSection
0x180003a36  call    cs:__imp_EnterCriticalSection
0x180003a3c  mov     rax, [rdi+10h]
0x180003a40  test    rax, rax
0x180003a43  jz      short loc_180003A88
0x180003a45  mov     r10, [rax+30h]
0x180003a49  lea     r8, [rdi+1Ch]; lParam1
0x180003a4d  test    r10, r10
0x180003a50  jz      loc_180003AE7
0x180003a56  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x180003a5a  jz      loc_180003B21
0x180003a60  mov     rdx, [rax+14h]
0x180003a64  lea     rcx, [rsp+78h+lParam2]
0x180003a69  mov     [rsp+78h+var_58], rcx
0x180003a6e  mov     r9, r8
0x180003a71  mov     rcx, [rax+38h]
0x180003a75  mov     r8d, 604Eh
0x180003a7b  mov     rax, r10
0x180003a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a83  mov     rdi, rax
0x180003a86  jmp     short loc_180003A8D
0x180003a88  mov     edi, 5
0x180003a8d  mov     rcx, rsi; lpCriticalSection
0x180003a90  call    cs:__imp_LeaveCriticalSection
0x180003a96  test    edi, edi
0x180003a98  jnz     short loc_180003AB0
0x180003a9a  test    ebx, ebx
0x180003a9c  jnz     short loc_180003ACA
0x180003a9e  mov     eax, dword ptr [rsp+78h+lParam2+0Ch]
0x180003aa2  mov     [r14], eax
0x180003aa5  cmp     [r14], ebp
0x180003aa8  mov     eax, 200h
0x180003aad  cmovz   edi, eax
0x180003ab0  mov     eax, edi
0x180003ab2  mov     rcx, [rsp+78h+var_38]
0x180003ab7  xor     rcx, rsp; StackCookie
0x180003aba  call    __security_check_cookie
0x180003abf  add     rsp, 50h
0x180003ac3  pop     r14
0x180003ac5  pop     rdi
0x180003ac6  pop     rsi
0x180003ac7  pop     rbp
0x180003ac8  pop     rbx
0x180003ac9  retn
0x180003aca  cmp     ebx, 1
0x180003acd  jnz     short loc_180003AA5
0x180003acf  mov     eax, dword ptr [rsp+78h+lParam2+8]
0x180003ad3  jmp     short loc_180003AA2
0x180003ad5  cmp     eax, 1
0x180003ad8  jnz     short loc_180003B1A
0x180003ada  mov     dword ptr [rsp+78h+lParam2+8], ebp
0x180003ade  mov     dword ptr [rsp+78h+lParam2+0Ch], esi
0x180003ae2  jmp     loc_180003A2F
0x180003ae7  mov     rcx, [rax+28h]; hDriver
0x180003aeb  test    rcx, rcx
0x180003aee  jz      short loc_180003A88
0x180003af0  lea     r9, [rsp+78h+lParam2]; lParam2
0x180003af5  mov     edx, 604Eh; message
0x180003afa  call    cs:__imp_SendDriverMessage
0x180003b00  mov     rdi, rax
0x180003b03  jmp     short loc_180003A8D
0x180003b05  mov     eax, 0Bh
0x180003b0a  jmp     short loc_180003AB2
0x180003b0c  mov     eax, 0Ah
0x180003b11  jmp     short loc_180003AB2
0x180003b13  mov     eax, 5
0x180003b18  jmp     short loc_180003AB2
0x180003b1a  mov     eax, 8
0x180003b1f  jmp     short loc_180003AB2
0x180003b21  mov     edi, 1
0x180003b26  jmp     loc_180003A8D
```

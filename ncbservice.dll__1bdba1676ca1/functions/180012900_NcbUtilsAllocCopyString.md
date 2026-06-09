# NcbUtilsAllocCopyString

- ea: `0x180012900`
- end: `0x180012a97`
- name: `NcbUtilsAllocCopyString`
- size: `407`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012490`
- `0x180013d60`
- `0x180017fc8`
- `0x180026724`
- `0x180027fec`

## callees

- `0x18000a0a0`
- `0x180012900`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001295c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001295c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001296d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001296d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012a11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a1a`

## string_xrefs

- `0x180012a83`: `NcbUtilsAllocCopyString: invalid input`
- `0x1800129f4`: `NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongAdd failed`
- `0x180012a68`: `NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongMult failed`
- `0x180012a2e`: `NcbUtilsAllocCopyString: Failed to allocate memory`
- `0x180012a4d`: `NcbUtilsAllocCopyString: StringCchCopyW failed`

## pseudocode

```c
__int64 __fastcall NcbUtilsAllocCopyString(__int64 a1, _QWORD *a2)
{
  _WORD *v3; // rdi
  __int64 v4; // rax
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rsi
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  _WORD *v9; // rax
  _WORD *v10; // rbx
  unsigned int v11; // ebp
  __int64 v12; // rax
  _WORD *v13; // rcx
  const wchar_t *v15; // r8
  DWORD LastError; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx

  v3 = (_WORD *)a1;
  if ( !a2 || !a1 )
  {
    v11 = 87;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      return v11;
    v15 = L"NcbUtilsAllocCopyString: invalid input";
    goto LABEL_30;
  }
  *a2 = 0;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a1 + 2 * v4) );
  a1 = (unsigned int)(v4 + 1);
  if ( (unsigned int)a1 < (unsigned int)v4 )
  {
    v11 = 534;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      return v11;
    v15 = L"NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongAdd failed";
    goto LABEL_30;
  }
  v5 = 2 * a1;
  v6 = (unsigned int)a1;
  a1 = 0xFFFFFFFFLL;
  if ( v5 > 0xFFFFFFFF )
  {
    v11 = 534;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      return v11;
    v15 = L"NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongMult failed";
    goto LABEL_30;
  }
  v7 = v5;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, v7);
  v10 = v9;
  if ( v9 )
  {
    *a2 = v9;
    if ( v6 )
    {
      if ( v6 > 0x7FFFFFFF )
      {
        a1 = 2147942487LL;
        *v9 = 0;
      }
      else
      {
        v11 = 0;
        v12 = 2147483646;
        do
        {
          if ( !v12 )
            break;
          if ( !*v3 )
            break;
          *v10++ = *v3++;
          --v12;
          --v6;
        }
        while ( v6 );
        v13 = v10 - 1;
        if ( v6 )
          v13 = v10;
        *v13 = 0;
        a1 = 2147942522LL;
        if ( v6 )
          return v11;
      }
    }
    else
    {
      a1 = 2147942487LL;
    }
    v11 = (unsigned __int16)a1;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      return v11;
    v15 = L"NcbUtilsAllocCopyString: StringCchCopyW failed";
LABEL_30:
    McTemplateU0zq_EventWriteTransfer(a1, a2, v15, v11);
    return v11;
  }
  SetLastError(8u);
  *a2 = 0;
  LastError = GetLastError();
  v11 = LastError;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v18, v17, L"NcbUtilsAllocCopyString: Failed to allocate memory", LastError);
  return v11;
}

```

## disassembly

```asm
0x180012900  push    rbx
0x180012902  push    rbp
0x180012903  push    rsi
0x180012904  push    rdi
0x180012905  push    r14
0x180012907  sub     rsp, 20h
0x18001290b  mov     r14, rdx
0x18001290e  mov     rdi, rcx
0x180012911  test    rdx, rdx
0x180012914  jz      loc_180012A71
0x18001291a  test    rcx, rcx
0x18001291d  jz      loc_180012A71
0x180012923  mov     qword ptr [rdx], 0
0x18001292a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180012931  inc     rax
0x180012934  cmp     word ptr [rcx+rax*2], 0
0x180012939  jnz     short loc_180012931
0x18001293b  lea     ecx, [rax+1]
0x18001293e  cmp     ecx, eax
0x180012940  jb      loc_1800129E6
0x180012946  lea     rax, [rcx+rcx]
0x18001294a  mov     esi, ecx
0x18001294c  mov     ecx, 0FFFFFFFFh
0x180012951  cmp     rax, rcx
0x180012954  ja      loc_180012A56
0x18001295a  mov     ebx, eax
0x18001295c  call    cs:__imp_GetProcessHeap
0x180012962  mov     r8d, ebx; dwBytes
0x180012965  mov     edx, 8; dwFlags
0x18001296a  mov     rcx, rax; hHeap
0x18001296d  call    cs:__imp_HeapAlloc
0x180012973  mov     rbx, rax
0x180012976  test    rax, rax
0x180012979  jz      loc_180012A0C
0x18001297f  mov     [r14], rax
0x180012982  test    rsi, rsi
0x180012985  jz      short loc_180012A00
0x180012987  cmp     rsi, 7FFFFFFFh
0x18001298e  ja      loc_180012A37
0x180012994  xor     ebp, ebp
0x180012996  mov     eax, 7FFFFFFEh
0x18001299b  test    rax, rax
0x18001299e  jz      short loc_1800129BC
0x1800129a0  movzx   ecx, word ptr [rdi]
0x1800129a3  test    cx, cx
0x1800129a6  jz      short loc_1800129BC
0x1800129a8  mov     [rbx], cx
0x1800129ab  add     rdi, 2
0x1800129af  add     rbx, 2
0x1800129b3  dec     rax
0x1800129b6  sub     rsi, 1
0x1800129ba  jnz     short loc_18001299B
0x1800129bc  test    rsi, rsi
0x1800129bf  lea     rcx, [rbx-2]
0x1800129c3  cmovnz  rcx, rbx
0x1800129c7  xor     eax, eax
0x1800129c9  test    rsi, rsi
0x1800129cc  mov     [rcx], ax
0x1800129cf  mov     ecx, 8007007Ah
0x1800129d4  cmovnz  ecx, eax
0x1800129d7  jz      short loc_180012A41
0x1800129d9  mov     eax, ebp
0x1800129db  add     rsp, 20h
0x1800129df  pop     r14
0x1800129e1  pop     rdi
0x1800129e2  pop     rsi
0x1800129e3  pop     rbp
0x1800129e4  pop     rbx
0x1800129e5  retn
0x1800129e6  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800129ed  mov     ebp, 216h
0x1800129f2  jz      short loc_1800129D9
0x1800129f4  lea     r8, aNcbutilsallocc_3; "NcbUtilsAllocCopyString: Overflow in ca"...
0x1800129fb  jmp     loc_180012A8A
0x180012a00  mov     ecx, 80070057h
0x180012a05  test    rsi, rsi
0x180012a08  jnz     short loc_180012A3C
0x180012a0a  jmp     short loc_180012A41
0x180012a0c  mov     ecx, 8; dwErrCode
0x180012a11  call    cs:__imp_SetLastError
0x180012a17  mov     [r14], rbx
0x180012a1a  call    cs:__imp_GetLastError
0x180012a20  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012a27  mov     ebp, eax
0x180012a29  jz      short loc_1800129D9
0x180012a2b  mov     r9d, eax
0x180012a2e  lea     r8, aNcbutilsallocc_0; "NcbUtilsAllocCopyString: Failed to allo"...
0x180012a35  jmp     short loc_180012A8D
0x180012a37  mov     ecx, 80070057h
0x180012a3c  xor     eax, eax
0x180012a3e  mov     [rbx], ax
0x180012a41  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012a48  movzx   ebp, cx
0x180012a4b  jz      short loc_1800129D9
0x180012a4d  lea     r8, aNcbutilsallocc_1; "NcbUtilsAllocCopyString: StringCchCopyW"...
0x180012a54  jmp     short loc_180012A8A
0x180012a56  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012a5d  mov     ebp, 216h
0x180012a62  jz      loc_1800129D9
0x180012a68  lea     r8, aNcbutilsallocc_2; "NcbUtilsAllocCopyString: Overflow in ca"...
0x180012a6f  jmp     short loc_180012A8A
0x180012a71  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012a78  mov     ebp, 57h ; 'W'
0x180012a7d  jz      loc_1800129D9
0x180012a83  lea     r8, aNcbutilsallocc; "NcbUtilsAllocCopyString: invalid input"
0x180012a8a  mov     r9d, ebp
0x180012a8d  call    McTemplateU0zq_EventWriteTransfer
0x180012a92  jmp     loc_1800129D9
```

# SetReason2

- ea: `0x14000daa4`
- end: `0x14000dbe0`
- name: `SetReason2`
- size: `316`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x140001e90`
- `0x1400024a4`
- `0x140002940`
- `0x1400030b8`
- `0x140003a58`
- `0x140003c48`
- `0x14000406c`
- `0x140004354`
- `0x140004bbc`
- `0x14000612c`
- `0x140006a5c`
- `0x14000752c`
- `0x140008dfc`
- `0x140008fe8`
- `0x140009ae4`
- `0x140009d40`
- `0x14000a0a0`
- `0x14000a3f8`

## callees

- `0x140001cd4`
- `0x14000caa8`
- `0x14000da24`
- `0x14000daa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dbb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dbbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dbb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dbbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dbce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dbce`

## pseudocode

```c
__int64 SetReason2(int a1, const wchar_t *a2, ...)
{
  signed int v2; // ecx
  unsigned int v4; // ebx
  wchar_t *InternalTemporaryBuffer; // rax
  wchar_t *v6; // rdi
  size_t v7; // rsi
  int v8; // eax
  __int64 v9; // [rsp+0h] [rbp-58h] BYREF
  __int64 v10; // [rsp+20h] [rbp-38h]
  va_list Args; // [rsp+70h] [rbp+18h] BYREF

  va_start(Args, a2);
  v10 = 0;
  if ( a2 )
  {
    if ( !a1 )
    {
      SetReason(a2);
      return 1;
    }
    v4 = 0;
    while ( &v9 != (__int64 *)-112LL )
    {
      v4 += 256;
      InternalTemporaryBuffer = (wchar_t *)GetInternalTemporaryBuffer(5u, 0, v4, 1);
      v6 = InternalTemporaryBuffer;
      if ( !InternalTemporaryBuffer )
      {
        if ( GetLastError() )
          return 0;
        v2 = 8;
        goto LABEL_26;
      }
      if ( v4 )
      {
        if ( v4 > 0x7FFFFFFF )
        {
          LOWORD(v2) = 87;
          *InternalTemporaryBuffer = 0;
LABEL_21:
          v2 = (unsigned __int16)v2;
          goto LABEL_26;
        }
        v7 = v4 - 1LL;
        v8 = vsnwprintf(InternalTemporaryBuffer, v7, a2, Args);
        if ( v8 < 0 || v8 > v7 )
        {
          v2 = -2147024774;
          v6[v7] = 0;
        }
        else
        {
          v2 = 0;
          if ( v8 == v7 )
            v6[v7] = 0;
        }
      }
      else
      {
        v2 = -2147024809;
      }
      v10 = 0;
      if ( v2 != -2147024774 )
      {
        if ( v2 >= 0 )
          return SetReason(v6);
        goto LABEL_21;
      }
    }
    if ( GetLastError() )
      return 0;
    v2 = 1067;
    goto LABEL_26;
  }
  if ( !GetLastError() )
  {
    v2 = 87;
LABEL_26:
    SetLastError(v2);
  }
  return 0;
}

```

## disassembly

```asm
0x14000daa4  mov     rax, rsp
0x14000daa7  mov     [rax+10h], rdx
0x14000daab  mov     [rax+18h], r8
0x14000daaf  mov     [rax+20h], r9
0x14000dab3  push    rbx
0x14000dab4  push    rsi
0x14000dab5  push    rdi
0x14000dab6  push    r14
0x14000dab8  sub     rsp, 38h
0x14000dabc  mov     qword ptr [rax-38h], 0
0x14000dac4  test    rdx, rdx
0x14000dac7  jnz     short loc_14000DADF
0x14000dac9  call    cs:__imp_GetLastError
0x14000dacf  test    eax, eax
0x14000dad1  jnz     loc_14000DBD4
0x14000dad7  lea     ecx, [rax+57h]
0x14000dada  jmp     loc_14000DBCE
0x14000dadf  test    ecx, ecx
0x14000dae1  jnz     short loc_14000DAF5
0x14000dae3  mov     rcx, rdx
0x14000dae6  call    SetReason
0x14000daeb  mov     eax, 1
0x14000daf0  jmp     loc_14000DBD6
0x14000daf5  xor     ebx, ebx
0x14000daf7  lea     r14, [rsp+58h+Args]
0x14000dafc  test    r14, r14
0x14000daff  jz      loc_14000DBBF
0x14000db05  xor     edx, edx
0x14000db07  add     ebx, 100h
0x14000db0d  mov     r9d, 1
0x14000db13  mov     r8d, ebx
0x14000db16  lea     ecx, [rdx+5]
0x14000db19  call    GetInternalTemporaryBuffer
0x14000db1e  mov     rdi, rax
0x14000db21  test    rax, rax
0x14000db24  jz      loc_14000DBB0
0x14000db2a  test    ebx, ebx
0x14000db2c  jz      short loc_14000DB75
0x14000db2e  cmp     ebx, 7FFFFFFFh
0x14000db34  ja      short loc_14000DBA1
0x14000db36  mov     r8, [rsp+58h+Format]; Format
0x14000db3b  mov     r9, r14; Args
0x14000db3e  mov     esi, ebx
0x14000db40  mov     rcx, rax; Buffer
0x14000db43  dec     rsi
0x14000db46  mov     rdx, rsi; BufferCount
0x14000db49  call    _vsnwprintf
0x14000db4e  test    eax, eax
0x14000db50  js      short loc_14000DB68
0x14000db52  cdqe
0x14000db54  cmp     rax, rsi
0x14000db57  ja      short loc_14000DB68
0x14000db59  xor     ecx, ecx
0x14000db5b  cmp     rax, rsi
0x14000db5e  jnz     short loc_14000DB7E
0x14000db60  xor     eax, eax
0x14000db62  mov     [rdi+rsi*2], ax
0x14000db66  jmp     short loc_14000DB7E
0x14000db68  xor     eax, eax
0x14000db6a  mov     ecx, 8007007Ah
0x14000db6f  mov     [rdi+rsi*2], ax
0x14000db73  jmp     short loc_14000DB7E
0x14000db75  mov     ecx, 80070057h
0x14000db7a  test    ebx, ebx
0x14000db7c  jnz     short loc_14000DBA6
0x14000db7e  mov     [rsp+58h+var_38], 0
0x14000db87  cmp     ecx, 8007007Ah
0x14000db8d  jz      loc_14000DAF7
0x14000db93  test    ecx, ecx
0x14000db95  js      short loc_14000DBAB
0x14000db97  mov     rcx, rdi
0x14000db9a  call    SetReason
0x14000db9f  jmp     short loc_14000DBD6
0x14000dba1  mov     ecx, 80070057h
0x14000dba6  xor     eax, eax
0x14000dba8  mov     [rdi], ax
0x14000dbab  movzx   ecx, cx
0x14000dbae  jmp     short loc_14000DBCE
0x14000dbb0  call    cs:__imp_GetLastError
0x14000dbb6  test    eax, eax
0x14000dbb8  jnz     short loc_14000DBD4
0x14000dbba  lea     ecx, [rax+8]
0x14000dbbd  jmp     short loc_14000DBCE
0x14000dbbf  call    cs:__imp_GetLastError
0x14000dbc5  test    eax, eax
0x14000dbc7  jnz     short loc_14000DBD4
0x14000dbc9  mov     ecx, 42Bh; dwErrCode
0x14000dbce  call    cs:__imp_SetLastError
0x14000dbd4  xor     eax, eax
0x14000dbd6  add     rsp, 38h
0x14000dbda  pop     r14
0x14000dbdc  pop     rdi
0x14000dbdd  pop     rsi
0x14000dbde  pop     rbx
0x14000dbdf  retn
```

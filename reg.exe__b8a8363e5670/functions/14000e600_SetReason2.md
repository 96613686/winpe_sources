# SetReason2

- ea: `0x14000e600`
- end: `0x14000e755`
- name: `SetReason2`
- size: `341`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x140001e90`
- `0x14000263c`
- `0x140002a78`
- `0x1400031f4`
- `0x140003c24`
- `0x140003e34`
- `0x14000426c`
- `0x14000456c`
- `0x140004e84`
- `0x1400064b0`
- `0x140006e6c`
- `0x14000799c`
- `0x140009374`
- `0x14000957c`
- `0x14000a0e0`
- `0x14000a358`
- `0x14000a6d8`
- `0x14000aa4c`

## callees

- `0x140001cd4`
- `0x14000d3e8`
- `0x14000e560`
- `0x14000e600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e727`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e73c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e73c`

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
0x14000e600  mov     rax, rsp
0x14000e603  mov     [rax+10h], rdx
0x14000e607  mov     [rax+18h], r8
0x14000e60b  mov     [rax+20h], r9
0x14000e60f  push    rbx
0x14000e610  push    rsi
0x14000e611  push    rdi
0x14000e612  push    r14
0x14000e614  sub     rsp, 38h
0x14000e618  mov     qword ptr [rax-38h], 0
0x14000e620  test    rdx, rdx
0x14000e623  jnz     short loc_14000E641
0x14000e625  call    cs:__imp_GetLastError
0x14000e62c  nop     dword ptr [rax+rax+00h]
0x14000e631  test    eax, eax
0x14000e633  jnz     loc_14000E748
0x14000e639  lea     ecx, [rax+57h]
0x14000e63c  jmp     loc_14000E73C
0x14000e641  test    ecx, ecx
0x14000e643  jnz     short loc_14000E657
0x14000e645  mov     rcx, rdx
0x14000e648  call    SetReason
0x14000e64d  mov     eax, 1
0x14000e652  jmp     loc_14000E74A
0x14000e657  xor     ebx, ebx
0x14000e659  lea     r14, [rsp+58h+Args]
0x14000e65e  test    r14, r14
0x14000e661  jz      loc_14000E727
0x14000e667  xor     edx, edx
0x14000e669  add     ebx, 100h
0x14000e66f  mov     r9d, 1
0x14000e675  mov     r8d, ebx
0x14000e678  lea     ecx, [rdx+5]
0x14000e67b  call    GetInternalTemporaryBuffer
0x14000e680  mov     rdi, rax
0x14000e683  test    rax, rax
0x14000e686  jz      loc_14000E712
0x14000e68c  test    ebx, ebx
0x14000e68e  jz      short loc_14000E6D7
0x14000e690  cmp     ebx, 7FFFFFFFh
0x14000e696  ja      short loc_14000E703
0x14000e698  mov     r8, [rsp+58h+Format]; Format
0x14000e69d  mov     r9, r14; Args
0x14000e6a0  mov     esi, ebx
0x14000e6a2  mov     rcx, rax; Buffer
0x14000e6a5  dec     rsi
0x14000e6a8  mov     rdx, rsi; BufferCount
0x14000e6ab  call    _vsnwprintf
0x14000e6b0  test    eax, eax
0x14000e6b2  js      short loc_14000E6CA
0x14000e6b4  cdqe
0x14000e6b6  cmp     rax, rsi
0x14000e6b9  ja      short loc_14000E6CA
0x14000e6bb  xor     ecx, ecx
0x14000e6bd  cmp     rax, rsi
0x14000e6c0  jnz     short loc_14000E6E0
0x14000e6c2  xor     eax, eax
0x14000e6c4  mov     [rdi+rsi*2], ax
0x14000e6c8  jmp     short loc_14000E6E0
0x14000e6ca  xor     eax, eax
0x14000e6cc  mov     ecx, 8007007Ah
0x14000e6d1  mov     [rdi+rsi*2], ax
0x14000e6d5  jmp     short loc_14000E6E0
0x14000e6d7  mov     ecx, 80070057h
0x14000e6dc  test    ebx, ebx
0x14000e6de  jnz     short loc_14000E708
0x14000e6e0  mov     [rsp+58h+var_38], 0
0x14000e6e9  cmp     ecx, 8007007Ah
0x14000e6ef  jz      loc_14000E659
0x14000e6f5  test    ecx, ecx
0x14000e6f7  js      short loc_14000E70D
0x14000e6f9  mov     rcx, rdi
0x14000e6fc  call    SetReason
0x14000e701  jmp     short loc_14000E74A
0x14000e703  mov     ecx, 80070057h
0x14000e708  xor     eax, eax
0x14000e70a  mov     [rdi], ax
0x14000e70d  movzx   ecx, cx
0x14000e710  jmp     short loc_14000E73C
0x14000e712  call    cs:__imp_GetLastError
0x14000e719  nop     dword ptr [rax+rax+00h]
0x14000e71e  test    eax, eax
0x14000e720  jnz     short loc_14000E748
0x14000e722  lea     ecx, [rax+8]
0x14000e725  jmp     short loc_14000E73C
0x14000e727  call    cs:__imp_GetLastError
0x14000e72e  nop     dword ptr [rax+rax+00h]
0x14000e733  test    eax, eax
0x14000e735  jnz     short loc_14000E748
0x14000e737  mov     ecx, 42Bh; dwErrCode
0x14000e73c  call    cs:__imp_SetLastError
0x14000e743  nop     dword ptr [rax+rax+00h]
0x14000e748  xor     eax, eax
0x14000e74a  add     rsp, 38h
0x14000e74e  pop     r14
0x14000e750  pop     rdi
0x14000e751  pop     rsi
0x14000e752  pop     rbx
0x14000e753  retn
```

# ODBC_PARAMETER::CopyValue(_SYSTEMTIME *)

- ea: `0x18000da20`
- end: `0x18000da8f`
- name: `?CopyValue@ODBC_PARAMETER@@QEAAHPEAU_SYSTEMTIME@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(ODBC_PARAMETER *__hidden this, struct _SYSTEMTIME *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b120`

## callees

- `0x18000da20`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000da82`
- `KERNEL32!SetLastError` at `0x18000da82`

## pseudocode

```c
__int64 __fastcall ODBC_PARAMETER::CopyValue(ODBC_PARAMETER *this, struct _SYSTEMTIME *a2)
{
  __int64 v2; // r8
  __int64 result; // rax

  v2 = *((_QWORD *)this + 2);
  if ( v2 && *((_QWORD *)this + 3) >= 0x10u )
  {
    *(_WORD *)v2 = a2->wYear;
    *(_WORD *)(v2 + 2) = a2->wMonth;
    *(_WORD *)(v2 + 4) = a2->wDay;
    *(_WORD *)(v2 + 6) = a2->wHour;
    *(_WORD *)(v2 + 8) = a2->wMinute;
    *(_WORD *)(v2 + 10) = a2->wSecond;
    result = 1;
    *(_DWORD *)(v2 + 12) = 1000000 * a2->wMilliseconds;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000da20  sub     rsp, 28h
0x18000da24  mov     r8, [rcx+10h]
0x18000da28  test    r8, r8
0x18000da2b  jz      short loc_18000DA7D
0x18000da2d  cmp     qword ptr [rcx+18h], 10h
0x18000da32  jb      short loc_18000DA7D
0x18000da34  movzx   eax, word ptr [rdx]
0x18000da37  mov     [r8], ax
0x18000da3b  movzx   eax, word ptr [rdx+2]
0x18000da3f  mov     [r8+2], ax
0x18000da44  movzx   eax, word ptr [rdx+6]
0x18000da48  mov     [r8+4], ax
0x18000da4d  movzx   eax, word ptr [rdx+8]
0x18000da51  mov     [r8+6], ax
0x18000da56  movzx   eax, word ptr [rdx+0Ah]
0x18000da5a  mov     [r8+8], ax
0x18000da5f  movzx   eax, word ptr [rdx+0Ch]
0x18000da63  mov     [r8+0Ah], ax
0x18000da68  movzx   eax, word ptr [rdx+0Eh]
0x18000da6c  imul    ecx, eax, 0F4240h
0x18000da72  mov     eax, 1
0x18000da77  mov     [r8+0Ch], ecx
0x18000da7b  jmp     short loc_18000DA8A
0x18000da7d  mov     ecx, 57h ; 'W'; dwErrCode
0x18000da82  call    cs:__imp_SetLastError
0x18000da88  xor     eax, eax
0x18000da8a  add     rsp, 28h
0x18000da8e  retn
```

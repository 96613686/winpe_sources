# OSWriteFile

- ea: `0x10025b48`
- end: `0x10025be8`
- name: `OSWriteFile`
- size: `160`
- prototype: `int __stdcall(DWORD nNumberOfBytesToWrite)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1000d760`
- `0x10011730`
- `0x10025df5`
- `0x10025e72`
- `0x100260bc`

## callees

- `0x10025b48`
- `0x100269a4`
- `0x10035b40`

## pseudocode

```c
DWORD __fastcall OSWriteFile(int a1, const void *a2, DWORD nNumberOfBytesToWrite)
{
  DWORD result; // eax
  int *v5; // esi
  int v6; // ebx
  int (__thiscall *v7)(_DWORD, _DWORD, _DWORD, _DWORD); // ecx
  int v8; // eax
  int v9; // ecx
  _DWORD v10[3]; // [esp+10h] [ebp-14h] BYREF
  int v11; // [esp+1Ch] [ebp-8h] BYREF

  v11 = 0;
  *(_DWORD *)(a1 + 24) = 1;
  if ( !*(_DWORD *)(a1 + 12) )
    return DOSWriteFile(*(HANDLE *)(a1 + 20), a2, nNumberOfBytesToWrite);
  v5 = *(int **)(a1 + 32);
  v6 = *v5;
  if ( nNumberOfBytesToWrite )
  {
    v8 = (*(int (__thiscall **)(_DWORD, int *, const void *, DWORD, int *))(v6 + 16))(
           *(_DWORD *)(v6 + 16),
           v5,
           a2,
           nNumberOfBytesToWrite,
           &v11);
  }
  else
  {
    (*(void (__thiscall **)(_DWORD, int *, _DWORD, _DWORD, int, _DWORD *))(v6 + 20))(
      *(_DWORD *)(v6 + 20),
      v5,
      0,
      0,
      1,
      v10);
    v7 = *(int (__thiscall **)(_DWORD, _DWORD, _DWORD, _DWORD))(**(_DWORD **)(a1 + 32) + 24);
    v8 = v7(v7, *(_DWORD *)(a1 + 32), v10[0], v10[1]);
  }
  v9 = v8;
  if ( !v8 )
    return v11;
  result = 0xFFFF;
  if ( v9 == -2147286928 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x10025b48  mov     edi, edi
0x10025b4a  push    ebp
0x10025b4b  mov     ebp, esp
0x10025b4d  sub     esp, 18h
0x10025b50  push    ebx
0x10025b51  push    esi
0x10025b52  push    edi
0x10025b53  mov     edi, ecx
0x10025b55  xor     ecx, ecx
0x10025b57  mov     [ebp+var_8], ecx
0x10025b5a  mov     dword ptr [edi+18h], 1
0x10025b61  cmp     [edi+0Ch], ecx
0x10025b64  jnz     short loc_10025B73
0x10025b66  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x10025b69  mov     ecx, [edi+14h]; hFile
0x10025b6c  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x10025b71  jmp     short loc_10025BE1
0x10025b73  mov     esi, [edi+20h]
0x10025b76  mov     ebx, [esi]
0x10025b78  cmp     [ebp+nNumberOfBytesToWrite], ecx
0x10025b7b  jnz     short loc_10025BB0
0x10025b7d  lea     edx, [ebp+var_14]
0x10025b80  mov     eax, ecx
0x10025b82  push    edx
0x10025b83  push    1
0x10025b85  push    eax
0x10025b86  push    ecx
0x10025b87  push    esi
0x10025b88  mov     esi, [ebx+14h]
0x10025b8b  mov     ecx, esi
0x10025b8d  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025b93  call    esi
0x10025b95  mov     eax, [edi+20h]
0x10025b98  push    [ebp+var_10]
0x10025b9b  push    [ebp+var_14]
0x10025b9e  mov     ecx, [eax]
0x10025ba0  push    eax
0x10025ba1  mov     esi, [ecx+18h]
0x10025ba4  mov     ecx, esi
0x10025ba6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025bac  call    esi
0x10025bae  jmp     short loc_10025BC6
0x10025bb0  lea     eax, [ebp+var_8]
0x10025bb3  push    eax
0x10025bb4  push    [ebp+nNumberOfBytesToWrite]
0x10025bb7  push    edx
0x10025bb8  push    esi
0x10025bb9  mov     esi, [ebx+10h]
0x10025bbc  mov     ecx, esi
0x10025bbe  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025bc4  call    esi
0x10025bc6  mov     ecx, eax
0x10025bc8  test    ecx, ecx
0x10025bca  jnz     short loc_10025BD1
0x10025bcc  mov     eax, [ebp+var_8]
0x10025bcf  jmp     short loc_10025BE1
0x10025bd1  xor     edx, edx
0x10025bd3  mov     eax, 0FFFFh
0x10025bd8  cmp     ecx, 80030070h
0x10025bde  cmovz   eax, edx
0x10025be1  pop     edi
0x10025be2  pop     esi
0x10025be3  pop     ebx
0x10025be4  leave
0x10025be5  retn    4
```

# System::AllocateTempFileName(ushort * *,Err &)

- ea: `0x1004ed00`
- end: `0x1004ed92`
- name: `?AllocateTempFileName@System@@QAEXPAPAGAAVErr@@@Z`
- size: `146`
- prototype: `void __thiscall(unsigned __int16 **, struct Err *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1001fe30`

## callees

- `0x1004ed00`
- `0x1004eda0`
- `0x1005d996`
- `0x1005da55`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005e7f3`

## pseudocode

```c
void __thiscall System::AllocateTempFileName(unsigned __int16 **this, void **a2, _BYTE *a3)
{
  struct Err *v3; // ecx
  WCHAR *v4; // eax
  WCHAR PathName[266]; // [esp+8h] [ebp-218h] BYREF

  if ( !JetGetTempPathW(0x104u, PathName) )
  {
LABEL_7:
    System::ErrGetLastError(v3);
    return;
  }
  v4 = (WCHAR *)operator new[](0x20Au);
  *a2 = v4;
  if ( (*a3 & 8) == 0 && !JetGetTempFileNameW(PathName, L"JET", 0, v4) )
  {
    if ( *a2 )
      operator delete[](*a2);
    *a2 = 0;
    goto LABEL_7;
  }
}

```

## disassembly

```asm
0x1004ed00  mov     edi, edi
0x1004ed02  push    ebp
0x1004ed03  mov     ebp, esp
0x1004ed05  and     esp, 0FFFFFFF8h
0x1004ed08  sub     esp, 218h
0x1004ed0e  mov     eax, ___security_cookie
0x1004ed13  xor     eax, esp
0x1004ed15  mov     [esp+218h+var_4], eax
0x1004ed1c  push    esi
0x1004ed1d  mov     esi, [ebp+arg_4]
0x1004ed20  lea     eax, [esp+21Ch+PathName]
0x1004ed24  push    edi
0x1004ed25  mov     edi, [ebp+arg_0]
0x1004ed28  push    eax; lpBuffer
0x1004ed29  push    104h; nBufferLength
0x1004ed2e  call    _JetGetTempPathW@8; JetGetTempPathW(x,x)
0x1004ed33  test    eax, eax
0x1004ed35  jz      short loc_1004ED76
0x1004ed37  push    20Ah; unsigned int
0x1004ed3c  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1004ed41  add     esp, 4
0x1004ed44  mov     [edi], eax
0x1004ed46  test    byte ptr [esi], 8
0x1004ed49  jnz     short loc_1004ED7C
0x1004ed4b  push    eax; lpTempFileName
0x1004ed4c  push    0; uUnique
0x1004ed4e  push    offset ?wszTempPrefix@@3QBGB; "JET"
0x1004ed53  lea     eax, [esp+22Ch+PathName]
0x1004ed57  push    eax; lpPathName
0x1004ed58  call    _JetGetTempFileNameW@16; JetGetTempFileNameW(x,x,x,x)
0x1004ed5d  test    eax, eax
0x1004ed5f  jnz     short loc_1004ED7C
0x1004ed61  mov     eax, [edi]
0x1004ed63  test    eax, eax
0x1004ed65  jz      short loc_1004ED70
0x1004ed67  push    eax; Block
0x1004ed68  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004ed6d  add     esp, 4
0x1004ed70  mov     dword ptr [edi], 0
0x1004ed76  push    esi
0x1004ed77  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1004ed7c  mov     ecx, [esp+220h+var_4]
0x1004ed83  pop     edi
0x1004ed84  pop     esi
0x1004ed85  xor     ecx, esp; StackCookie
0x1004ed87  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004ed8c  mov     esp, ebp
0x1004ed8e  pop     ebp
0x1004ed8f  retn    8
```

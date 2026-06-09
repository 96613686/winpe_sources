# InitGlobals

- ea: `0x14000d114`
- end: `0x14000d1fd`
- name: `InitGlobals`
- size: `233`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000c6d0`
- `0x14000caa8`
- `0x14000cd48`
- `0x14000d978`
- `0x14000da24`

## callees

- `0x14000d114`
- `0x14000e604`
- `0x14000e718`
- `0x14000e7a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d1ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d1ef`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x14000d1d2`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x14000d1d2`

## pseudocode

```c
__int64 InitGlobals()
{
  DWORD v1; // ecx
  _DWORD *DynamicArray; // rax

  if ( g_bInitialized == 1 )
  {
    if ( qword_140014218 && *(_DWORD *)qword_140014218 == 9 )
      return 1;
LABEL_5:
    if ( !GetLastError() )
    {
      v1 = 1067;
LABEL_18:
      SetLastError(v1);
      return 0;
    }
    return 0;
  }
  if ( qword_140014218 )
    goto LABEL_5;
  DynamicArray = CreateDynamicArray();
  qword_140014218 = (__int64)DynamicArray;
  if ( DynamicArray
    && *DynamicArray == 9
    && !(unsigned int)DynArrayAppendString(DynamicArray, (const WCHAR *)&cwszNullString)
    && (unsigned int)DynArrayAppendRow(qword_140014218, 3) == 1
    && (unsigned int)DynArrayAppendRow(qword_140014218, 3) == 2
    && (unsigned int)DynArrayAppendRow(qword_140014218, 3) == 3 )
  {
    g_bInitialized = 1;
    if ( SetThreadUILanguage(0) )
      return 1;
  }
  else if ( !GetLastError() )
  {
    v1 = 8;
    goto LABEL_18;
  }
  return 0;
}

```

## disassembly

```asm
0x14000d114  push    rbx
0x14000d116  sub     rsp, 20h
0x14000d11a  cmp     cs:g_bInitialized, 1
0x14000d121  jnz     short loc_14000D156
0x14000d123  mov     rcx, cs:qword_140014218
0x14000d12a  test    rcx, rcx
0x14000d12d  jz      short loc_14000D13E
0x14000d12f  cmp     dword ptr [rcx], 9
0x14000d132  jnz     short loc_14000D13E
0x14000d134  mov     eax, 1
0x14000d139  jmp     loc_14000D1F7
0x14000d13e  call    cs:__imp_GetLastError
0x14000d144  test    eax, eax
0x14000d146  jnz     loc_14000D1F5
0x14000d14c  mov     ecx, 42Bh
0x14000d151  jmp     loc_14000D1EF
0x14000d156  xor     ebx, ebx
0x14000d158  cmp     cs:qword_140014218, rbx
0x14000d15f  jnz     short loc_14000D13E
0x14000d161  call    CreateDynamicArray
0x14000d166  mov     cs:qword_140014218, rax
0x14000d16d  test    rax, rax
0x14000d170  jz      short loc_14000D1E2
0x14000d172  cmp     dword ptr [rax], 9
0x14000d175  jnz     short loc_14000D1E2
0x14000d177  lea     rdx, cwszNullString
0x14000d17e  mov     rcx, rax
0x14000d181  call    DynArrayAppendString
0x14000d186  test    eax, eax
0x14000d188  jnz     short loc_14000D1E2
0x14000d18a  mov     rcx, cs:qword_140014218
0x14000d191  lea     edx, [rbx+3]
0x14000d194  call    DynArrayAppendRow
0x14000d199  cmp     eax, 1
0x14000d19c  jnz     short loc_14000D1E2
0x14000d19e  mov     rcx, cs:qword_140014218
0x14000d1a5  lea     edx, [rbx+3]
0x14000d1a8  call    DynArrayAppendRow
0x14000d1ad  cmp     eax, 2
0x14000d1b0  jnz     short loc_14000D1E2
0x14000d1b2  mov     rcx, cs:qword_140014218
0x14000d1b9  lea     edx, [rbx+3]
0x14000d1bc  call    DynArrayAppendRow
0x14000d1c1  cmp     eax, 3
0x14000d1c4  jnz     short loc_14000D1E2
0x14000d1c6  xor     ecx, ecx; LangId
0x14000d1c8  mov     cs:g_bInitialized, 1
0x14000d1d2  call    cs:__imp_SetThreadUILanguage
0x14000d1d8  test    ax, ax
0x14000d1db  jz      short loc_14000D1F5
0x14000d1dd  jmp     loc_14000D134
0x14000d1e2  call    cs:__imp_GetLastError
0x14000d1e8  test    eax, eax
0x14000d1ea  jnz     short loc_14000D1F5
0x14000d1ec  lea     ecx, [rax+8]; dwErrCode
0x14000d1ef  call    cs:__imp_SetLastError
0x14000d1f5  xor     eax, eax
0x14000d1f7  add     rsp, 20h
0x14000d1fb  pop     rbx
0x14000d1fc  retn
```

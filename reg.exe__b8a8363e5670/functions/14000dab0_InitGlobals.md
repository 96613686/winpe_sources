# InitGlobals

- ea: `0x14000dab0`
- end: `0x14000dbb2`
- name: `InitGlobals`
- size: `258`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000cf2c`
- `0x14000d3e8`
- `0x14000d694`
- `0x14000e484`
- `0x14000e560`

## callees

- `0x14000dab0`
- `0x14000f294`
- `0x14000f3b0`
- `0x14000f43c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000db8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000db8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000db9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000db9d`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x14000db74`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x14000db74`

## pseudocode

```c
__int64 InitGlobals()
{
  DWORD v1; // ecx
  _DWORD *DynamicArray; // rax

  if ( g_bInitialized == 1 )
  {
    if ( qword_140015218 && *(_DWORD *)qword_140015218 == 9 )
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
  if ( qword_140015218 )
    goto LABEL_5;
  DynamicArray = (_DWORD *)CreateDynamicArray();
  qword_140015218 = (__int64)DynamicArray;
  if ( DynamicArray
    && *DynamicArray == 9
    && !(unsigned int)DynArrayAppendString(DynamicArray, (const WCHAR *)&cwszNullString)
    && (unsigned int)DynArrayAppendRow(qword_140015218, 3) == 1
    && (unsigned int)DynArrayAppendRow(qword_140015218, 3) == 2
    && (unsigned int)DynArrayAppendRow(qword_140015218, 3) == 3 )
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
0x14000dab0  push    rbx
0x14000dab2  sub     rsp, 20h
0x14000dab6  cmp     cs:g_bInitialized, 1
0x14000dabd  jnz     short loc_14000DAF8
0x14000dabf  mov     rcx, cs:qword_140015218
0x14000dac6  test    rcx, rcx
0x14000dac9  jz      short loc_14000DADA
0x14000dacb  cmp     dword ptr [rcx], 9
0x14000dace  jnz     short loc_14000DADA
0x14000dad0  mov     eax, 1
0x14000dad5  jmp     loc_14000DBAB
0x14000dada  call    cs:__imp_GetLastError
0x14000dae1  nop     dword ptr [rax+rax+00h]
0x14000dae6  test    eax, eax
0x14000dae8  jnz     loc_14000DBA9
0x14000daee  mov     ecx, 42Bh
0x14000daf3  jmp     loc_14000DB9D
0x14000daf8  xor     ebx, ebx
0x14000dafa  cmp     cs:qword_140015218, rbx
0x14000db01  jnz     short loc_14000DADA
0x14000db03  call    CreateDynamicArray
0x14000db08  mov     cs:qword_140015218, rax
0x14000db0f  test    rax, rax
0x14000db12  jz      short loc_14000DB8A
0x14000db14  cmp     dword ptr [rax], 9
0x14000db17  jnz     short loc_14000DB8A
0x14000db19  lea     rdx, cwszNullString
0x14000db20  mov     rcx, rax
0x14000db23  call    DynArrayAppendString
0x14000db28  test    eax, eax
0x14000db2a  jnz     short loc_14000DB8A
0x14000db2c  mov     rcx, cs:qword_140015218
0x14000db33  lea     edx, [rbx+3]
0x14000db36  call    DynArrayAppendRow
0x14000db3b  cmp     eax, 1
0x14000db3e  jnz     short loc_14000DB8A
0x14000db40  mov     rcx, cs:qword_140015218
0x14000db47  lea     edx, [rbx+3]
0x14000db4a  call    DynArrayAppendRow
0x14000db4f  cmp     eax, 2
0x14000db52  jnz     short loc_14000DB8A
0x14000db54  mov     rcx, cs:qword_140015218
0x14000db5b  lea     edx, [rbx+3]
0x14000db5e  call    DynArrayAppendRow
0x14000db63  cmp     eax, 3
0x14000db66  jnz     short loc_14000DB8A
0x14000db68  xor     ecx, ecx; LangId
0x14000db6a  mov     cs:g_bInitialized, 1
0x14000db74  call    cs:__imp_SetThreadUILanguage
0x14000db7b  nop     dword ptr [rax+rax+00h]
0x14000db80  test    ax, ax
0x14000db83  jz      short loc_14000DBA9
0x14000db85  jmp     loc_14000DAD0
0x14000db8a  call    cs:__imp_GetLastError
0x14000db91  nop     dword ptr [rax+rax+00h]
0x14000db96  test    eax, eax
0x14000db98  jnz     short loc_14000DBA9
0x14000db9a  lea     ecx, [rax+8]; dwErrCode
0x14000db9d  call    cs:__imp_SetLastError
0x14000dba4  nop     dword ptr [rax+rax+00h]
0x14000dba9  xor     eax, eax
0x14000dbab  add     rsp, 20h
0x14000dbaf  pop     rbx
0x14000dbb0  retn
```

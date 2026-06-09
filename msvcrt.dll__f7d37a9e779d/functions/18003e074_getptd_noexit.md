# _getptd_noexit

- ea: `0x18003e074`
- end: `0x18003e0f3`
- name: `_getptd_noexit`
- size: `127`
- prototype: ``
- caller_count: `26`
- callee_count: `4`
- tags: ``

## callers

- `0x180001038`
- `0x1800023c0`
- `0x180002550`
- `0x180007e80`
- `0x180007ea8`
- `0x180007f00`
- `0x180007f30`
- `0x180007f80`
- `0x180008020`
- `0x180008050`
- `0x1800181e4`
- `0x18002b2b0`
- `0x18002e0a0`
- `0x18002e310`
- `0x18002e660`
- `0x180030340`
- `0x180030e40`
- `0x180033660`
- `0x18003e048`
- `0x18003e3e0`
- `0x18003e600`
- `0x18005011c`
- `0x180052650`
- `0x1800660c0`
- `0x180068140`
- `0x180068c30`

## callees

- `0x18001d300`
- `0x18001d50c`
- `0x18003e074`
- `0x18003e0fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e0df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e0df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e07e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e07e`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x18003e0b8`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x18003e0b8`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x18003e08c`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x18003e08c`

## pseudocode

```c
_QWORD *getptd_noexit()
{
  DWORD LastError; // edi
  _QWORD *Value; // rbx
  _QWORD *v2; // rax

  LastError = GetLastError();
  Value = FlsGetValue(_flsindex);
  if ( !Value )
  {
    v2 = (_QWORD *)calloc_crt(1, 736);
    Value = v2;
    if ( v2 )
    {
      if ( FlsSetValue(_flsindex, v2) )
      {
        initptd(Value, 0);
        Value[1] = -1;
      }
      else
      {
        free(Value);
        Value = 0;
      }
    }
  }
  SetLastError(LastError);
  return Value;
}

```

## disassembly

```asm
0x18003e074  mov     [rsp+arg_0], rbx
0x18003e079  push    rdi
0x18003e07a  sub     rsp, 20h
0x18003e07e  call    cs:__imp_GetLastError
0x18003e084  mov     ecx, cs:__flsindex; dwFlsIndex
0x18003e08a  mov     edi, eax
0x18003e08c  call    cs:__imp_FlsGetValue
0x18003e092  mov     rbx, rax
0x18003e095  test    rax, rax
0x18003e098  jnz     short loc_18003E0DD
0x18003e09a  mov     edx, 2E0h
0x18003e09f  lea     ecx, [rax+1]
0x18003e0a2  call    _calloc_crt
0x18003e0a7  mov     rbx, rax
0x18003e0aa  test    rax, rax
0x18003e0ad  jz      short loc_18003E0DD
0x18003e0af  mov     ecx, cs:__flsindex; dwFlsIndex
0x18003e0b5  mov     rdx, rax; lpFlsData
0x18003e0b8  call    cs:__imp_FlsSetValue
0x18003e0be  mov     rcx, rbx; Block
0x18003e0c1  test    eax, eax
0x18003e0c3  jz      short loc_18003E0D6
0x18003e0c5  xor     edx, edx
0x18003e0c7  call    _initptd
0x18003e0cc  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x18003e0d4  jmp     short loc_18003E0DD
0x18003e0d6  call    free
0x18003e0db  xor     ebx, ebx
0x18003e0dd  mov     ecx, edi; dwErrCode
0x18003e0df  call    cs:__imp_SetLastError
0x18003e0e5  mov     rax, rbx
0x18003e0e8  mov     rbx, [rsp+28h+arg_0]
0x18003e0ed  add     rsp, 20h
0x18003e0f1  pop     rdi
0x18003e0f2  retn
```

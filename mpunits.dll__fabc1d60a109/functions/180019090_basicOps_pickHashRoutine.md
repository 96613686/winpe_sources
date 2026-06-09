# basicOps_pickHashRoutine

- ea: `0x180019090`
- end: `0x1800191b8`
- name: `basicOps_pickHashRoutine`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18003bd6c`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180010a50`
- `0x180010cc0`
- `0x180018c74`
- `0x180019090`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001914e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001914e`

## string_xrefs

- `0x18001913f`: `mpunits.dll`

## pseudocode

```c
__int64 (__fastcall *__fastcall basicOps_pickHashRoutine(__int64 a1))()
{
  __int64 TypeName; // rbx
  HMODULE ModuleHandleA; // rax

  if ( (*(_DWORD *)a1 & 0x100) != 0 )
  {
    MI_ReportErrorDetails_HashingOfNullValuesNotSupported();
    return 0;
  }
  if ( *(_BYTE *)a1 == 13 )
    return basicOps_hash_string;
  if ( (unsigned __int8)(*(_BYTE *)a1 - 1) <= 7u || *(_BYTE *)a1 == 11 )
    return basicOps_hash_integer;
  if ( *(_BYTE *)a1 != 12 )
    goto LABEL_23;
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL) )
    return basicOps_hash_timestamp;
  if ( *(_BYTE *)a1 == 12 && !*(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL) )
    return basicOps_hash_interval;
LABEL_23:
  if ( (unsigned __int8)MintValue_IsGuid(a1) )
    return basicOps_hash_guid;
  if ( (*(_DWORD *)a1 & 0x100) != 0 || *(_BYTE *)a1 )
  {
    TypeName = MintValue_GetTypeName(a1);
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_FormatString_FormatMessage(ModuleHandleA, 2111, TypeName);
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    return 0;
  }
  return basicOps_hash_boolean;
}

```

## disassembly

```asm
0x180019090  push    rbx
0x180019092  sub     rsp, 40h
0x180019096  test    dword ptr [rcx], 100h
0x18001909c  mov     rbx, rcx
0x18001909f  jz      short loc_1800190AD
0x1800190a1  call    MI_ReportErrorDetails_HashingOfNullValuesNotSupported
0x1800190a6  xor     eax, eax
0x1800190a8  jmp     loc_1800191B2
0x1800190ad  cmp     byte ptr [rcx], 0Dh
0x1800190b0  jnz     short loc_1800190BE
0x1800190b2  lea     rax, basicOps_hash_string
0x1800190b9  jmp     loc_1800191B2
0x1800190be  mov     al, [rcx]
0x1800190c0  dec     al
0x1800190c2  cmp     al, 7
0x1800190c4  jbe     loc_1800191AB
0x1800190ca  cmp     byte ptr [rcx], 0Bh
0x1800190cd  jz      loc_1800191AB
0x1800190d3  cmp     byte ptr [rcx], 0Ch
0x1800190d6  jnz     short loc_180019109
0x1800190d8  mov     rax, [rcx+8]
0x1800190dc  cmp     dword ptr [rax+10h], 0
0x1800190e0  jz      short loc_1800190EE
0x1800190e2  lea     rax, basicOps_hash_timestamp
0x1800190e9  jmp     loc_1800191B2
0x1800190ee  cmp     byte ptr [rcx], 0Ch
0x1800190f1  jnz     short loc_180019109
0x1800190f3  mov     rax, [rcx+8]
0x1800190f7  cmp     dword ptr [rax+10h], 0
0x1800190fb  jnz     short loc_180019109
0x1800190fd  lea     rax, basicOps_hash_interval
0x180019104  jmp     loc_1800191B2
0x180019109  call    MintValue_IsGuid
0x18001910e  test    al, al
0x180019110  jz      short loc_18001911E
0x180019112  lea     rax, basicOps_hash_guid
0x180019119  jmp     loc_1800191B2
0x18001911e  test    dword ptr [rbx], 100h
0x180019124  jnz     short loc_180019134
0x180019126  cmp     byte ptr [rbx], 0
0x180019129  jnz     short loc_180019134
0x18001912b  lea     rax, basicOps_hash_boolean
0x180019132  jmp     short loc_1800191B2
0x180019134  mov     rcx, rbx
0x180019137  call    MintValue_GetTypeName
0x18001913c  xorps   xmm0, xmm0
0x18001913f  lea     rcx, ModuleName; "mpunits.dll"
0x180019146  movups  [rsp+48h+var_18], xmm0
0x18001914b  mov     rbx, rax
0x18001914e  call    cs:__imp_GetModuleHandleA
0x180019154  mov     r8, rbx
0x180019157  mov     edx, 83Fh
0x18001915c  mov     rcx, rax
0x18001915f  call    _Intlstr_FormatString_FormatMessage
0x180019164  mov     qword ptr [rsp+48h+var_18], rax
0x180019169  lea     r9, [rsp+48h+var_18]
0x18001916e  mov     byte ptr [rsp+48h+var_18+8], 1
0x180019173  lea     rdx, aMi; "MI"
0x18001917a  movaps  xmm0, [rsp+48h+var_18]
0x18001917f  mov     r8d, 5
0x180019185  mov     [rsp+48h+var_20], 0; __int64
0x18001918e  movdqa  [rsp+48h+var_18], xmm0
0x180019194  mov     [rsp+48h+var_28], 0; __int64
0x18001919d  lea     ecx, [r8-1]; int
0x1800191a1  call    MI_ReportErrorDetails_ForCustomError
0x1800191a6  jmp     loc_1800190A6
0x1800191ab  lea     rax, basicOps_hash_integer
0x1800191b2  add     rsp, 40h
0x1800191b6  pop     rbx
0x1800191b7  retn
```

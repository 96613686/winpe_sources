# ErrGetStringFromErr(x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x100268b0`
- end: `0x100269ad`
- name: `_ErrGetStringFromErr@44`
- size: `253`
- prototype: `int __thiscall(void *, int, int, int, int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100258c0`
- `0x100a3238`

## callees

- `0x100268b0`
- `0x10046c1f`
- `0x10050190`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100268e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002695c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100268e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002695c`

## string_xrefs

- `0x100268bf`: `MSJTER40.DLL`

## pseudocode

```c
int __fastcall ErrGetStringFromErr(
        void *a1,
        unsigned int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        HMODULE *a11)
{
  HMODULE Library; // eax
  FARPROC JetErrFormattedMessage; // eax
  int result; // eax
  int v15; // esi
  FARPROC JetErrRawMessage; // eax
  unsigned int v17[8]; // [esp+Ch] [ebp-38h] BYREF
  unsigned int v18; // [esp+2Ch] [ebp-18h] BYREF
  _BYTE v19[4]; // [esp+30h] [ebp-14h] BYREF
  _BYTE v20[4]; // [esp+34h] [ebp-10h] BYREF
  unsigned int v21; // [esp+38h] [ebp-Ch]
  _DWORD v22[2]; // [esp+3Ch] [ebp-8h] BYREF

  v21 = a2;
  Library = JetLoadLibraryExW(L"MSJTER40.DLL", 0, 0);
  *a11 = Library;
  if ( !Library )
    return -1001;
  JetErrFormattedMessage = GetProcAddress(Library, "JetErrFormattedMessage");
  if ( !JetErrFormattedMessage )
    return -1001;
  v17[1] = v21;
  v17[2] = a6;
  v17[3] = a7;
  v17[4] = a8;
  v17[5] = a3;
  v17[6] = a4;
  v17[7] = a5;
  v17[0] = 32;
  result = ((int (__thiscall *)(FARPROC, void *, unsigned int *, unsigned int *, int, int, _DWORD *, _BYTE *, _BYTE *))JetErrFormattedMessage)(
             JetErrFormattedMessage,
             a1,
             v17,
             &v18,
             a9,
             2048,
             v22,
             v19,
             v20);
  v15 = result;
  if ( result >= 0 && !v22[0] )
  {
    JetErrRawMessage = GetProcAddress(*a11, "JetErrRawMessage");
    if ( JetErrRawMessage )
      return ((int (__thiscall *)(FARPROC, void *, unsigned int *, int, int, _DWORD *, _BYTE *, _BYTE *))JetErrRawMessage)(
               JetErrRawMessage,
               a1,
               &v18,
               a9,
               2048,
               v22,
               v19,
               v20);
    else
      return v15;
  }
  return result;
}

```

## disassembly

```asm
0x100268b0  mov     edi, edi
0x100268b2  push    ebp
0x100268b3  mov     ebp, esp
0x100268b5  sub     esp, 38h
0x100268b8  push    ebx
0x100268b9  push    esi
0x100268ba  push    edi
0x100268bb  push    0; int
0x100268bd  push    0; hFile
0x100268bf  push    offset _c_wszErrorDLL; "MSJTER40.DLL"
0x100268c4  mov     [ebp+var_C], edx
0x100268c7  mov     ebx, ecx
0x100268c9  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x100268ce  mov     edi, [ebp+arg_20]
0x100268d1  mov     [edi], eax
0x100268d3  test    eax, eax
0x100268d5  jz      loc_1002699F
0x100268db  push    offset aJeterrformatte; "JetErrFormattedMessage"
0x100268e0  push    eax; hModule
0x100268e1  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100268e7  mov     esi, eax
0x100268e9  test    esi, esi
0x100268eb  jz      loc_1002699F
0x100268f1  mov     eax, [ebp+var_C]
0x100268f4  mov     ecx, esi
0x100268f6  mov     [ebp+var_34], eax
0x100268f9  mov     eax, [ebp+arg_C]
0x100268fc  mov     [ebp+var_30], eax
0x100268ff  mov     eax, [ebp+arg_10]
0x10026902  mov     [ebp+var_2C], eax
0x10026905  mov     eax, [ebp+arg_14]
0x10026908  mov     [ebp+var_28], eax
0x1002690b  mov     eax, [ebp+arg_0]
0x1002690e  mov     [ebp+var_24], eax
0x10026911  mov     eax, [ebp+arg_4]
0x10026914  mov     [ebp+var_20], eax
0x10026917  mov     eax, [ebp+arg_8]
0x1002691a  mov     [ebp+var_1C], eax
0x1002691d  lea     eax, [ebp+var_10]
0x10026920  push    eax
0x10026921  lea     eax, [ebp+var_14]
0x10026924  mov     [ebp+var_38], 20h ; ' '
0x1002692b  push    eax
0x1002692c  lea     eax, [ebp+var_8]
0x1002692f  push    eax
0x10026930  push    800h
0x10026935  push    [ebp+arg_18]
0x10026938  lea     eax, [ebp+var_18]
0x1002693b  push    eax
0x1002693c  lea     eax, [ebp+var_38]
0x1002693f  push    eax; unsigned int
0x10026940  push    ebx; void *
0x10026941  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10026947  call    esi
0x10026949  mov     esi, eax
0x1002694b  test    esi, esi
0x1002694d  js      short loc_100269A4
0x1002694f  cmp     [ebp+var_8], 0
0x10026953  jnz     short loc_100269A4
0x10026955  push    offset aJeterrrawmessa; "JetErrRawMessage"
0x1002695a  push    dword ptr [edi]; hModule
0x1002695c  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10026962  mov     edi, eax
0x10026964  test    edi, edi
0x10026966  jz      short loc_10026994
0x10026968  lea     eax, [ebp+var_10]
0x1002696b  mov     ecx, edi
0x1002696d  push    eax
0x1002696e  lea     eax, [ebp+var_14]
0x10026971  push    eax
0x10026972  lea     eax, [ebp+var_8]
0x10026975  push    eax
0x10026976  push    800h
0x1002697b  push    [ebp+arg_18]
0x1002697e  lea     eax, [ebp+var_18]
0x10026981  push    eax; unsigned int
0x10026982  push    ebx; void *
0x10026983  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10026989  call    edi
0x1002698b  pop     edi
0x1002698c  pop     esi
0x1002698d  pop     ebx
0x1002698e  mov     esp, ebp
0x10026990  pop     ebp
0x10026991  retn    24h ; '$'
0x10026994  mov     eax, esi
0x10026996  pop     edi
0x10026997  pop     esi
0x10026998  pop     ebx
0x10026999  mov     esp, ebp
0x1002699b  pop     ebp
0x1002699c  retn    24h ; '$'
0x1002699f  mov     eax, 0FFFFFC17h
0x100269a4  pop     edi
0x100269a5  pop     esi
0x100269a6  pop     ebx
0x100269a7  mov     esp, ebp
0x100269a9  pop     ebp
0x100269aa  retn    24h ; '$'
```

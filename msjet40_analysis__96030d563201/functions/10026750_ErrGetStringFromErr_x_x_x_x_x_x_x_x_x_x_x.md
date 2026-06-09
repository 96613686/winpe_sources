# ErrGetStringFromErr(x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x10026750`
- end: `0x1002684d`
- name: `_ErrGetStringFromErr@44`
- size: `253`
- prototype: `int __thiscall(void *, int, int, int, int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x10025760`
- `0x100a30a8`

## callees

- `0x10026750`
- `0x10046a9f`
- `0x10050000`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10026781`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100267fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10026781`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100267fc`

## string_xrefs

- `0x1002675f`: `MSJTER40.DLL`

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
0x10026750  mov     edi, edi
0x10026752  push    ebp
0x10026753  mov     ebp, esp
0x10026755  sub     esp, 38h
0x10026758  push    ebx
0x10026759  push    esi
0x1002675a  push    edi
0x1002675b  push    0; int
0x1002675d  push    0; hFile
0x1002675f  push    offset _c_wszErrorDLL; "MSJTER40.DLL"
0x10026764  mov     [ebp+var_C], edx
0x10026767  mov     ebx, ecx
0x10026769  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x1002676e  mov     edi, [ebp+arg_20]
0x10026771  mov     [edi], eax
0x10026773  test    eax, eax
0x10026775  jz      loc_1002683F
0x1002677b  push    offset aJeterrformatte; "JetErrFormattedMessage"
0x10026780  push    eax; hModule
0x10026781  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10026787  mov     esi, eax
0x10026789  test    esi, esi
0x1002678b  jz      loc_1002683F
0x10026791  mov     eax, [ebp+var_C]
0x10026794  mov     ecx, esi
0x10026796  mov     [ebp+var_34], eax
0x10026799  mov     eax, [ebp+arg_C]
0x1002679c  mov     [ebp+var_30], eax
0x1002679f  mov     eax, [ebp+arg_10]
0x100267a2  mov     [ebp+var_2C], eax
0x100267a5  mov     eax, [ebp+arg_14]
0x100267a8  mov     [ebp+var_28], eax
0x100267ab  mov     eax, [ebp+arg_0]
0x100267ae  mov     [ebp+var_24], eax
0x100267b1  mov     eax, [ebp+arg_4]
0x100267b4  mov     [ebp+var_20], eax
0x100267b7  mov     eax, [ebp+arg_8]
0x100267ba  mov     [ebp+var_1C], eax
0x100267bd  lea     eax, [ebp+var_10]
0x100267c0  push    eax
0x100267c1  lea     eax, [ebp+var_14]
0x100267c4  mov     [ebp+var_38], 20h ; ' '
0x100267cb  push    eax
0x100267cc  lea     eax, [ebp+var_8]
0x100267cf  push    eax
0x100267d0  push    800h
0x100267d5  push    [ebp+arg_18]
0x100267d8  lea     eax, [ebp+var_18]
0x100267db  push    eax
0x100267dc  lea     eax, [ebp+var_38]
0x100267df  push    eax; unsigned int
0x100267e0  push    ebx; void *
0x100267e1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100267e7  call    esi
0x100267e9  mov     esi, eax
0x100267eb  test    esi, esi
0x100267ed  js      short loc_10026844
0x100267ef  cmp     [ebp+var_8], 0
0x100267f3  jnz     short loc_10026844
0x100267f5  push    offset aJeterrrawmessa; "JetErrRawMessage"
0x100267fa  push    dword ptr [edi]; hModule
0x100267fc  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10026802  mov     edi, eax
0x10026804  test    edi, edi
0x10026806  jz      short loc_10026834
0x10026808  lea     eax, [ebp+var_10]
0x1002680b  mov     ecx, edi
0x1002680d  push    eax
0x1002680e  lea     eax, [ebp+var_14]
0x10026811  push    eax
0x10026812  lea     eax, [ebp+var_8]
0x10026815  push    eax
0x10026816  push    800h
0x1002681b  push    [ebp+arg_18]
0x1002681e  lea     eax, [ebp+var_18]
0x10026821  push    eax; unsigned int
0x10026822  push    ebx; void *
0x10026823  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10026829  call    edi
0x1002682b  pop     edi
0x1002682c  pop     esi
0x1002682d  pop     ebx
0x1002682e  mov     esp, ebp
0x10026830  pop     ebp
0x10026831  retn    24h ; '$'
0x10026834  mov     eax, esi
0x10026836  pop     edi
0x10026837  pop     esi
0x10026838  pop     ebx
0x10026839  mov     esp, ebp
0x1002683b  pop     ebp
0x1002683c  retn    24h ; '$'
0x1002683f  mov     eax, 0FFFFFC17h
0x10026844  pop     edi
0x10026845  pop     esi
0x10026846  pop     ebx
0x10026847  mov     esp, ebp
0x10026849  pop     ebp
0x1002684a  retn    24h ; '$'
```

# DOSOpenFile(x,x,x)

- ea: `0x10026925`
- end: `0x1002699e`
- name: `_DOSOpenFile@12`
- size: `121`
- prototype: `int __thiscall(LPCWSTR lpFileName, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x10011280`

## callees

- `0x10026925`
- `0x10032deb`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10026989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10026989`

## pseudocode

```c
int __fastcall DOSOpenFile(LPCWSTR lpFileName, char a2, _DWORD *a3)
{
  DWORD v3; // esi
  DWORD v4; // eax
  HANDLE FileW; // eax
  int result; // eax

  if ( (a2 & 2) != 0 )
  {
    v3 = -1073741824;
  }
  else
  {
    v3 = 0x80000000;
    if ( (a2 & 1) != 0 )
      v3 = 0x40000000;
  }
  if ( (a2 & 0x10) != 0 )
  {
    v4 = 0;
  }
  else if ( (a2 & 0x20) != 0 )
  {
    v4 = 1;
  }
  else
  {
    v4 = 3 - ((a2 & 0x30) != 0);
  }
  FileW = JetCreateFileW(lpFileName, v3, v4, 0, 3u, 128, 0);
  if ( FileW == (HANDLE)-1 )
  {
    result = -(unsigned __int16)GetLastError();
    if ( !result )
      return -2;
  }
  else
  {
    *a3 = FileW;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x10026925  mov     edi, edi
0x10026927  push    ebp
0x10026928  mov     ebp, esp
0x1002692a  push    esi
0x1002692b  test    dl, 2
0x1002692e  jz      short loc_10026937
0x10026930  mov     esi, 0C0000000h
0x10026935  jmp     short loc_10026947
0x10026937  test    dl, 1
0x1002693a  mov     esi, 80000000h
0x1002693f  mov     eax, 40000000h
0x10026944  cmovnz  esi, eax
0x10026947  test    dl, 10h
0x1002694a  jz      short loc_10026950
0x1002694c  xor     eax, eax
0x1002694e  jmp     short loc_10026967
0x10026950  test    dl, 20h
0x10026953  jz      short loc_1002695A
0x10026955  xor     eax, eax
0x10026957  inc     eax
0x10026958  jmp     short loc_10026967
0x1002695a  and     dl, 30h
0x1002695d  movsx   eax, dl
0x10026960  neg     eax
0x10026962  sbb     eax, eax
0x10026964  add     eax, 3
0x10026967  push    0; int
0x10026969  push    80h; int
0x1002696e  push    3; dwCreationDisposition
0x10026970  push    0; int
0x10026972  push    eax; dwShareMode
0x10026973  push    esi; dwDesiredAccess
0x10026974  push    ecx; lpFileName
0x10026975  call    _JetCreateFileW@28; JetCreateFileW(x,x,x,x,x,x,x)
0x1002697a  pop     esi
0x1002697b  cmp     eax, 0FFFFFFFFh
0x1002697e  jz      short loc_10026989
0x10026980  mov     ecx, [ebp+arg_0]
0x10026983  mov     [ecx], eax
0x10026985  xor     eax, eax
0x10026987  jmp     short loc_1002699A
0x10026989  call    ds:__imp__GetLastError@0; GetLastError()
0x1002698f  movzx   eax, ax
0x10026992  push    0FFFFFFFEh
0x10026994  neg     eax
0x10026996  pop     ecx
0x10026997  cmovz   eax, ecx
0x1002699a  pop     ebp
0x1002699b  retn    4
```

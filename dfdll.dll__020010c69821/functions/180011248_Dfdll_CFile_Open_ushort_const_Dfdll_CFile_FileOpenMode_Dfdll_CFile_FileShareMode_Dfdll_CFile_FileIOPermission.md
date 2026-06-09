# Dfdll::CFile::Open(ushort const *,Dfdll::CFile::FileOpenMode,Dfdll::CFile::FileShareMode,Dfdll::CFile::FileIOPermission)

- ea: `0x180011248`
- end: `0x18001138c`
- name: `?Open@CFile@Dfdll@@QEAAJPEBGW4FileOpenMode@12@W4FileShareMode@12@W4FileIOPermission@12@@Z`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18001179c`

## callees

- `0x180011248`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011307`
- `KERNEL32!GetLastError` at `0x180011355`
- `KERNEL32!GetLastError` at `0x180011307`
- `KERNEL32!GetLastError` at `0x180011355`
- `KERNEL32!CloseHandle` at `0x180011329`
- `KERNEL32!CloseHandle` at `0x180011329`
- `KERNEL32!CreateFileW` at `0x1800112f8`
- `KERNEL32!CreateFileW` at `0x1800112f8`
- `KERNEL32!SetFilePointer` at `0x18001134b`
- `KERNEL32!SetFilePointer` at `0x18001134b`

## pseudocode

```c
__int64 __fastcall Dfdll::CFile::Open(__int64 a1, const WCHAR *a2, int a3, char a4, int a5)
{
  DWORD dwCreationDisposition; // r10d
  int v9; // edx
  DWORD v10; // r8d
  DWORD v11; // edx
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v14; // ecx
  void *v15; // rcx
  signed int v16; // eax
  LONG DistanceToMoveHigh[6]; // [rsp+40h] [rbp-18h] BYREF

  if ( a3 )
  {
    if ( a3 == 1 )
    {
      dwCreationDisposition = 2;
    }
    else if ( a3 == 2 )
    {
      dwCreationDisposition = 1;
    }
    else
    {
      dwCreationDisposition = 3;
      if ( a3 != 3 )
      {
        dwCreationDisposition = 4;
        if ( a3 == 5 )
          dwCreationDisposition = 5;
      }
    }
  }
  else
  {
    dwCreationDisposition = 4;
  }
  v9 = a4 & 4 | 1;
  if ( (a4 & 1) == 0 )
    v9 = a4 & 4;
  v10 = v9 | 2;
  if ( (a4 & 2) == 0 )
    v10 = v9;
  v11 = (a5 << 31) | 0x40000000;
  if ( (a5 & 2) == 0 )
    v11 = a5 << 31;
  FileW = CreateFileW(a2, v11, v10, 0, dwCreationDisposition, 0, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_20;
  LastError = GetLastError();
  v14 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v14 = LastError;
  if ( v14 >= 0 )
  {
LABEL_20:
    v15 = *(void **)(a1 + 8);
    if ( v15 != (void *)-1LL )
      CloseHandle(v15);
    *(_QWORD *)(a1 + 8) = FileW;
    if ( !a3
      && (DistanceToMoveHigh[1] = 0,
          DistanceToMoveHigh[0] = SetFilePointer(FileW, 0, &DistanceToMoveHigh[1], 2u),
          v16 = GetLastError(),
          DistanceToMoveHigh[0] == -1)
      && v16 )
    {
      v14 = (unsigned __int16)v16 | 0x80070000;
      if ( v16 <= 0 )
        return (unsigned int)v16;
    }
    else
    {
      return 0;
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180011248  mov     [rsp+arg_0], rbx
0x18001124d  mov     [rsp+arg_8], rsi
0x180011252  push    rdi
0x180011253  sub     rsp, 50h
0x180011257  mov     ebx, r8d
0x18001125a  mov     r11, rdx
0x18001125d  mov     rdi, rcx
0x180011260  mov     edx, 4
0x180011265  lea     r8d, [rdx-3]
0x180011269  test    ebx, ebx
0x18001126b  jnz     short loc_180011272
0x18001126d  mov     r10d, edx
0x180011270  jmp     short loc_1800112A6
0x180011272  cmp     ebx, r8d
0x180011275  jnz     short loc_18001127F
0x180011277  mov     r10d, 2
0x18001127d  jmp     short loc_1800112A6
0x18001127f  cmp     ebx, 2
0x180011282  jnz     short loc_180011289
0x180011284  mov     r10d, r8d
0x180011287  jmp     short loc_1800112A6
0x180011289  mov     r10d, 3
0x18001128f  cmp     ebx, r10d
0x180011292  jz      short loc_1800112A6
0x180011294  mov     r10d, edx
0x180011297  cmp     ebx, edx
0x180011299  jz      short loc_1800112A6
0x18001129b  mov     eax, 5
0x1800112a0  cmp     ebx, eax
0x1800112a2  cmovz   r10d, eax
0x1800112a6  mov     ecx, r9d
0x1800112a9  and     ecx, edx
0x1800112ab  mov     eax, r9d
0x1800112ae  mov     edx, ecx
0x1800112b0  or      edx, r8d
0x1800112b3  and     al, r8b
0x1800112b6  cmovz   edx, ecx
0x1800112b9  mov     eax, [rsp+58h+arg_20]
0x1800112c0  mov     ecx, eax
0x1800112c2  and     ecx, r8d
0x1800112c5  shl     ecx, 1Fh
0x1800112c8  mov     r8d, edx
0x1800112cb  or      r8d, 2
0x1800112cf  and     r9b, 2
0x1800112d3  cmovz   r8d, edx; dwShareMode
0x1800112d7  mov     edx, ecx
0x1800112d9  bts     edx, 1Eh
0x1800112dd  and     al, 2
0x1800112df  cmovz   edx, ecx; dwDesiredAccess
0x1800112e2  and     [rsp+58h+var_28], 0
0x1800112e8  and     [rsp+58h+var_30], 0
0x1800112ed  mov     [rsp+58h+dwCreationDisposition], r10d; dwCreationDisposition
0x1800112f2  xor     r9d, r9d; lpSecurityAttributes
0x1800112f5  mov     rcx, r11; lpFileName
0x1800112f8  call    cs:__imp_CreateFileW
0x1800112fe  mov     rsi, rax
0x180011301  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011305  jnz     short loc_18001131F
0x180011307  call    cs:__imp_GetLastError
0x18001130d  movzx   ecx, ax
0x180011310  or      ecx, 80070000h
0x180011316  test    eax, eax
0x180011318  cmovle  ecx, eax
0x18001131b  test    ecx, ecx
0x18001131d  js      short loc_18001137A
0x18001131f  mov     rcx, [rdi+8]; hObject
0x180011323  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011327  jz      short loc_18001132F
0x180011329  call    cs:__imp_CloseHandle
0x18001132f  mov     [rdi+8], rsi
0x180011333  test    ebx, ebx
0x180011335  jnz     short loc_180011378
0x180011337  and     qword ptr [rsp+58h+DistanceToMoveHigh], 0
0x18001133d  lea     r9d, [rbx+2]; dwMoveMethod
0x180011341  lea     r8, [rsp+58h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x180011346  xor     edx, edx; lDistanceToMove
0x180011348  mov     rcx, rsi; hFile
0x18001134b  call    cs:__imp_SetFilePointer
0x180011351  mov     [rsp+58h+DistanceToMoveHigh], eax
0x180011355  call    cs:__imp_GetLastError
0x18001135b  cmp     [rsp+58h+DistanceToMoveHigh], 0FFFFFFFFh
0x180011360  jnz     short loc_180011378
0x180011362  test    eax, eax
0x180011364  jz      short loc_180011378
0x180011366  movzx   ecx, ax
0x180011369  or      ecx, 80070000h
0x18001136f  test    eax, eax
0x180011371  cmovle  ecx, eax
0x180011374  test    ecx, ecx
0x180011376  js      short loc_18001137A
0x180011378  xor     ecx, ecx
0x18001137a  mov     eax, ecx
0x18001137c  mov     rbx, [rsp+58h+arg_0]
0x180011381  mov     rsi, [rsp+58h+arg_8]
0x180011386  add     rsp, 50h
0x18001138a  pop     rdi
0x18001138b  retn
```

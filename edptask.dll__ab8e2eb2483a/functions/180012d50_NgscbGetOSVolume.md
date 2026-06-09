# NgscbGetOSVolume

- ea: `0x180012d50`
- end: `0x180012e28`
- name: `NgscbGetOSVolume`
- size: `216`
- prototype: `__int64 __fastcall(_WORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010cb0`

## callees

- `0x180012d50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180012de4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180012de4`

## pseudocode

```c
__int64 __fastcall NgscbGetOSVolume(_WORD *a1)
{
  const wchar_t *v1; // rdx
  __int64 v2; // r8
  __int64 v3; // r11
  __int64 v5; // rax
  _WORD *v6; // r9
  __int64 v7; // r10
  _WORD *v8; // rcx
  unsigned int v9; // edx
  UINT v10; // ebx
  WCHAR *v11; // rdi
  UINT SystemWindowsDirectoryW; // eax
  signed int LastError; // eax

  v1 = L"\\\\.\\";
  v2 = 260;
  v3 = 0;
  v5 = 2147483646;
  v6 = a1;
  do
  {
    if ( !v5 )
      break;
    if ( !*v1 )
      break;
    *v6++ = *v1++;
    --v5;
    ++v3;
    --v2;
  }
  while ( v2 );
  v7 = v3 - 1;
  v8 = v6 - 1;
  if ( v2 )
    v7 = v3;
  v9 = v2 == 0 ? 0x8007007A : 0;
  if ( v2 )
    v8 = v6;
  *v8 = 0;
  if ( v2 )
  {
    v10 = 260 - v7;
    if ( (unsigned __int64)(260 - v7) > 0xFFFFFFFF )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v11 = &a1[v7];
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(v11, v10);
      if ( SystemWindowsDirectoryW )
      {
        v9 = 0;
        if ( SystemWindowsDirectoryW <= v10 )
          v11[2] = 0;
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180012d50  mov     [rsp+arg_0], rbx
0x180012d55  mov     [rsp+arg_8], rsi
0x180012d5a  push    rdi
0x180012d5b  sub     rsp, 20h
0x180012d5f  mov     ebx, 104h
0x180012d64  lea     rdx, asc_180018960; "\\\\.\\"
0x180012d6b  xor     esi, esi
0x180012d6d  mov     r8d, ebx
0x180012d70  mov     r11d, esi
0x180012d73  mov     rdi, rcx
0x180012d76  mov     eax, 7FFFFFFEh
0x180012d7b  mov     r9, rcx
0x180012d7e  test    rax, rax
0x180012d81  jz      short loc_180012DA3
0x180012d83  movzx   ecx, word ptr [rdx]
0x180012d86  test    cx, cx
0x180012d89  jz      short loc_180012DA3
0x180012d8b  mov     [r9], cx
0x180012d8f  add     rdx, 2
0x180012d93  add     r9, 2
0x180012d97  dec     rax
0x180012d9a  inc     r11
0x180012d9d  sub     r8, 1
0x180012da1  jnz     short loc_180012D7E
0x180012da3  test    r8, r8
0x180012da6  lea     r10, [r11-1]
0x180012daa  mov     rax, r8
0x180012dad  lea     rcx, [r9-2]
0x180012db1  cmovnz  r10, r11
0x180012db5  neg     rax
0x180012db8  sbb     edx, edx
0x180012dba  not     edx
0x180012dbc  and     edx, 8007007Ah
0x180012dc2  test    r8, r8
0x180012dc5  cmovnz  rcx, r9
0x180012dc9  mov     [rcx], si
0x180012dcc  jz      short loc_180012E16
0x180012dce  sub     rbx, r10
0x180012dd1  mov     eax, 0FFFFFFFFh
0x180012dd6  cmp     rbx, rax
0x180012dd9  ja      short loc_180012E11
0x180012ddb  lea     rdi, [rdi+r10*2]
0x180012ddf  mov     edx, ebx; uSize
0x180012de1  mov     rcx, rdi; lpBuffer
0x180012de4  call    cs:__imp_GetSystemWindowsDirectoryW
0x180012dea  test    eax, eax
0x180012dec  jnz     short loc_180012E05
0x180012dee  call    cs:__imp_GetLastError
0x180012df4  mov     edx, eax
0x180012df6  test    eax, eax
0x180012df8  jle     short loc_180012E16
0x180012dfa  movzx   edx, ax
0x180012dfd  or      edx, 80070000h
0x180012e03  jmp     short loc_180012E16
0x180012e05  mov     edx, esi
0x180012e07  cmp     eax, ebx
0x180012e09  ja      short loc_180012E16
0x180012e0b  mov     [rdi+4], si
0x180012e0f  jmp     short loc_180012E16
0x180012e11  mov     edx, 80070216h
0x180012e16  mov     rbx, [rsp+28h+arg_0]
0x180012e1b  mov     eax, edx
0x180012e1d  mov     rsi, [rsp+28h+arg_8]
0x180012e22  add     rsp, 20h
0x180012e26  pop     rdi
0x180012e27  retn
```

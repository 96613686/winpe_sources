# CuiGetBinaryLocation(ushort const *)

- ea: `0x14000f200`
- end: `0x14000f307`
- name: `?CuiGetBinaryLocation@@YA?AW4_CONTEXT_FILE_LOCATION@@PEBG@Z`
- size: `263`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003040`
- `0x140003820`
- `0x140003b00`
- `0x14000eee4`
- `0x140018d60`

## callees

- `0x14000f200`
- `0x140018c68`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x14000f2a4`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x14000f2a4`
- `SHLWAPI!PathIsURLW` at `0x14000f27f`
- `SHLWAPI!PathIsURLW` at `0x14000f27f`

## pseudocode

```c
__int64 __fastcall CuiGetBinaryLocation(__int64 a1)
{
  __int64 result; // rax
  unsigned __int64 v3; // rcx
  int MarkOfTheWeb; // eax
  UINT DriveTypeW; // eax
  UINT v6; // eax
  UINT v7; // eax
  UINT v8; // eax
  UINT v9; // eax
  UINT v10; // eax
  WCHAR RootPathName[4]; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)RootPathName = 0;
  result = 0;
  if ( a1 )
  {
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)(a1 + 2 * v3) );
    if ( v3 >= 2 )
    {
      MarkOfTheWeb = CuipGetMarkOfTheWeb((const unsigned __int16 *)a1);
      if ( MarkOfTheWeb )
      {
        if ( MarkOfTheWeb != 1 )
          return 6;
        return 3;
      }
      if ( *(_WORD *)a1 != 92 || *(_WORD *)(a1 + 2) != 92 )
      {
        if ( PathIsURLW((LPCWSTR)a1) )
          return 6;
        RootPathName[0] = *(_WORD *)a1;
        RootPathName[1] = *(_WORD *)(a1 + 2);
        RootPathName[2] = 92;
        DriveTypeW = GetDriveTypeW(RootPathName);
        if ( !DriveTypeW )
          return 0;
        v6 = DriveTypeW - 1;
        if ( !v6 )
          return 0;
        v7 = v6 - 1;
        if ( !v7 )
          return 1;
        v8 = v7 - 1;
        if ( !v8 )
          return 2;
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( !v10 )
            return 4;
          if ( v10 == 1 )
            return 5;
          return 0;
        }
      }
      return 3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000f200  mov     [rsp+arg_8], rbx
0x14000f205  mov     [rsp+arg_10], rsi
0x14000f20a  push    rdi
0x14000f20b  sub     rsp, 30h
0x14000f20f  mov     rax, cs:__security_cookie
0x14000f216  xor     rax, rsp
0x14000f219  mov     [rsp+38h+var_10], rax
0x14000f21e  xor     edi, edi
0x14000f220  mov     rbx, rcx
0x14000f223  mov     qword ptr [rsp+38h+RootPathName], rdi
0x14000f228  mov     eax, edi
0x14000f22a  test    rcx, rcx
0x14000f22d  jz      loc_14000F2EA
0x14000f233  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000f237  inc     rcx
0x14000f23a  cmp     [rbx+rcx*2], di
0x14000f23e  jnz     short loc_14000F237
0x14000f240  cmp     rcx, 2
0x14000f244  jb      loc_14000F2EA
0x14000f24a  mov     rcx, rbx; unsigned __int16 *
0x14000f24d  call    ?CuipGetMarkOfTheWeb@@YAKPEBG@Z; CuipGetMarkOfTheWeb(ushort const *)
0x14000f252  test    eax, eax
0x14000f254  jz      short loc_14000F26C
0x14000f256  cmp     eax, 1
0x14000f259  jz      short loc_14000F265
0x14000f25b  mov     eax, 6
0x14000f260  jmp     loc_14000F2EA
0x14000f265  mov     eax, 3
0x14000f26a  jmp     short loc_14000F2EA
0x14000f26c  mov     esi, 5Ch ; '\'
0x14000f271  cmp     [rbx], si
0x14000f274  jnz     short loc_14000F27C
0x14000f276  cmp     [rbx+2], si
0x14000f27a  jz      short loc_14000F265
0x14000f27c  mov     rcx, rbx; pszPath
0x14000f27f  call    cs:__imp_PathIsURLW
0x14000f285  test    eax, eax
0x14000f287  jnz     short loc_14000F25B
0x14000f289  movzx   eax, word ptr [rbx]
0x14000f28c  lea     rcx, [rsp+38h+RootPathName]; lpRootPathName
0x14000f291  mov     [rsp+38h+RootPathName], ax
0x14000f296  movzx   eax, word ptr [rbx+2]
0x14000f29a  mov     [rsp+38h+RootPathName+2], ax
0x14000f29f  mov     [rsp+38h+RootPathName+4], si
0x14000f2a4  call    cs:__imp_GetDriveTypeW
0x14000f2aa  test    eax, eax
0x14000f2ac  jz      short loc_14000F2E8
0x14000f2ae  sub     eax, 1
0x14000f2b1  jz      short loc_14000F2E8
0x14000f2b3  sub     eax, 1
0x14000f2b6  jz      short loc_14000F2E1
0x14000f2b8  sub     eax, 1
0x14000f2bb  jz      short loc_14000F2DA
0x14000f2bd  sub     eax, 1
0x14000f2c0  jz      short loc_14000F265
0x14000f2c2  sub     eax, 1
0x14000f2c5  jz      short loc_14000F2D3
0x14000f2c7  cmp     eax, 1
0x14000f2ca  jnz     short loc_14000F2E8
0x14000f2cc  mov     eax, 5
0x14000f2d1  jmp     short loc_14000F2EA
0x14000f2d3  mov     eax, 4
0x14000f2d8  jmp     short loc_14000F2EA
0x14000f2da  mov     eax, 2
0x14000f2df  jmp     short loc_14000F2EA
0x14000f2e1  mov     eax, 1
0x14000f2e6  jmp     short loc_14000F2EA
0x14000f2e8  mov     eax, edi
0x14000f2ea  mov     rcx, [rsp+38h+var_10]
0x14000f2ef  xor     rcx, rsp; StackCookie
0x14000f2f2  call    __security_check_cookie
0x14000f2f7  mov     rbx, [rsp+38h+arg_8]
0x14000f2fc  mov     rsi, [rsp+38h+arg_10]
0x14000f301  add     rsp, 30h
0x14000f305  pop     rdi
0x14000f306  retn
```

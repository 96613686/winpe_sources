# IsLocalDrivePath(ushort const *)

- ea: `0x1800033c0`
- end: `0x180003461`
- name: `?IsLocalDrivePath@@YAHPEBG@Z`
- size: `161`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800031f0`

## callees

- `0x180001d90`
- `0x1800033c0`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003437`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003437`

## pseudocode

```c
__int64 __fastcall IsLocalDrivePath(const unsigned __int16 *a1)
{
  __int64 result; // rax
  __int64 v3; // rax
  const wchar_t *v4; // rdx
  __int64 v5; // r9
  WCHAR *p_RootPathName; // r8
  WCHAR *v7; // rcx
  WCHAR RootPathName; // [rsp+20h] [rbp-18h] BYREF

  result = IsDrivePath(a1);
  if ( (_DWORD)result )
  {
    v3 = 2147483646;
    v4 = L"A:\\";
    v5 = 4;
    p_RootPathName = &RootPathName;
    do
    {
      if ( !v3 )
        break;
      if ( !*v4 )
        break;
      *p_RootPathName++ = *v4++;
      --v3;
      --v5;
    }
    while ( v5 );
    v7 = p_RootPathName - 1;
    if ( v5 )
      v7 = p_RootPathName;
    *v7 = 0;
    RootPathName = *a1;
    return GetDriveTypeW(&RootPathName) != 4;
  }
  return result;
}

```

## disassembly

```asm
0x1800033c0  push    rbx
0x1800033c2  sub     rsp, 30h
0x1800033c6  mov     rax, cs:__security_cookie
0x1800033cd  xor     rax, rsp
0x1800033d0  mov     [rsp+38h+var_10], rax
0x1800033d5  mov     rbx, rcx
0x1800033d8  call    ?IsDrivePath@@YAHPEBG@Z; IsDrivePath(ushort const *)
0x1800033dd  test    eax, eax
0x1800033df  jz      short loc_18000344D
0x1800033e1  mov     eax, 7FFFFFFEh
0x1800033e6  lea     rdx, aA; "A:\\"
0x1800033ed  mov     r9d, 4
0x1800033f3  lea     r8, [rsp+38h+RootPathName]
0x1800033f8  test    rax, rax
0x1800033fb  jz      short loc_18000341A
0x1800033fd  movzx   ecx, word ptr [rdx]
0x180003400  test    cx, cx
0x180003403  jz      short loc_18000341A
0x180003405  mov     [r8], cx
0x180003409  add     rdx, 2
0x18000340d  add     r8, 2
0x180003411  dec     rax
0x180003414  sub     r9, 1
0x180003418  jnz     short loc_1800033F8
0x18000341a  test    r9, r9
0x18000341d  lea     rcx, [r8-2]
0x180003421  cmovnz  rcx, r8
0x180003425  xor     eax, eax
0x180003427  mov     [rcx], ax
0x18000342a  lea     rcx, [rsp+38h+RootPathName]; lpRootPathName
0x18000342f  movzx   eax, word ptr [rbx]
0x180003432  mov     [rsp+38h+RootPathName], ax
0x180003437  call    cs:__imp_GetDriveTypeW
0x18000343e  nop     dword ptr [rax+rax+00h]
0x180003443  xor     ecx, ecx
0x180003445  cmp     eax, 4
0x180003448  setnz   cl
0x18000344b  mov     eax, ecx
0x18000344d  mov     rcx, [rsp+38h+var_10]
0x180003452  xor     rcx, rsp; StackCookie
0x180003455  call    __security_check_cookie
0x18000345a  add     rsp, 30h
0x18000345e  pop     rbx
0x18000345f  retn
```

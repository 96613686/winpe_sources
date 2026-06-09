# DeleteAppContainerEnumerator

- ea: `0x180002340`
- end: `0x1800023b3`
- name: `DeleteAppContainerEnumerator`
- size: `115`
- prototype: `int __fastcall(HKEY *lpMem, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002340`
- `0x180003fdc`
- `0x180005b60`
- `0x180007c60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002351`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002351`

## pseudocode

```c
int __fastcall DeleteAppContainerEnumerator(HKEY *lpMem, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  HKEY v6; // rcx
  unsigned int v7; // eax
  int v9; // eax
  int v10; // ebx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v6 = *lpMem;
  if ( v6 )
  {
    v7 = RegCloseKey(v6);
    if ( v7 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x139,
               (unsigned int)"minio\\profapi\\appcontainer.cpp",
               (const char *)v7,
               a5);
    *lpMem = 0;
  }
  v9 = ResultFromHeapFree(lpMem);
  v10 = v9;
  if ( v9 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x13D,
    (unsigned int)"minio\\profapi\\appcontainer.cpp",
    (const char *)(unsigned int)v9,
    v11);
  return v10;
}

```

## disassembly

```asm
0x180002340  push    rbx; int
0x180002342  sub     rsp, 20h
0x180002346  mov     rbx, rcx
0x180002349  mov     rcx, [rcx]; hKey
0x18000234c  test    rcx, rcx
0x18000234f  jz      short loc_180002380
0x180002351  call    cs:__imp_RegCloseKey
0x180002357  test    eax, eax
0x180002359  jz      short loc_180002379
0x18000235b  mov     rcx, [rsp+28h]; this
0x180002360  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180002367  mov     r9d, eax; char *
0x18000236a  mov     edx, 139h; void *
0x18000236f  add     rsp, 20h
0x180002373  pop     rbx
0x180002374  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002379  mov     qword ptr [rbx], 0
0x180002380  mov     rcx, rbx; lpMem
0x180002383  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180002388  mov     ebx, eax
0x18000238a  test    eax, eax
0x18000238c  jns     short loc_1800023AB
0x18000238e  mov     rcx, [rsp+28h]; this
0x180002393  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18000239a  mov     r9d, eax; char *
0x18000239d  mov     edx, 13Dh; void *
0x1800023a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800023a7  mov     eax, ebx
0x1800023a9  jmp     short loc_1800023AD
0x1800023ab  xor     eax, eax
0x1800023ad  add     rsp, 20h
0x1800023b1  pop     rbx
0x1800023b2  retn
```

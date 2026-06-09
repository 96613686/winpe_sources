# FileExists(ushort *,unsigned __int64)

- ea: `0x180001610`
- end: `0x180001766`
- name: `?FileExists@@YAHPEAG_K@Z`
- size: `342`
- prototype: `__int64 __fastcall(wchar_t *Str, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001010`
- `0x18000cd74`

## callees

- `0x180001610`
- `0x180001840`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180001710`
- `msvcrt!wcsrchr` at `0x180001710`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800016ca`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800016ca`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180001667`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180001667`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800016f3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800016f3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180001702`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180001702`

## pseudocode

```c
__int64 __fastcall FileExists(wchar_t *Str)
{
  __int64 v2; // rax
  WCHAR *v3; // rdx
  __int64 v4; // r8
  wchar_t *v5; // r9
  wchar_t *v6; // rcx
  DWORD FileAttributesW; // eax
  HANDLE FirstFileW; // rax
  wchar_t *v9; // rax
  LPWSTR FilePart; // [rsp+20h] [rbp-488h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-478h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  FilePart = 0;
  if ( GetFullPathNameW(Str, 0x105u, Buffer, &FilePart) > 0x104 )
    return 0;
  v2 = 2147483646;
  v3 = Buffer;
  v4 = 261;
  v5 = Str;
  do
  {
    if ( !v2 )
      break;
    if ( !*v3 )
      break;
    *v5++ = *v3++;
    --v2;
    --v4;
  }
  while ( v4 );
  v6 = v5 - 1;
  if ( v4 )
    v6 = v5;
  *v6 = 0;
  if ( !v4 )
    return 0;
  FileAttributesW = GetFileAttributesW(Str);
  if ( FileAttributesW == -1 )
    return 0;
  if ( (FileAttributesW & 0x10) != 0 )
    return 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(Str, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return 0;
  FindClose(FirstFileW);
  v9 = wcsrchr(Str, 0x5Cu);
  if ( v9 )
    StringCchCopyW(v9 + 1, 261 - (((char *)v9 - (char *)Str + 2) >> 1), FindFileData.cFileName);
  return 1;
}

```

## disassembly

```asm
0x180001610  mov     [rsp+arg_8], rbx
0x180001615  push    rdi
0x180001616  sub     rsp, 4A0h
0x18000161d  mov     rax, cs:__security_cookie
0x180001624  xor     rax, rsp
0x180001627  mov     [rsp+4A8h+var_18], rax
0x18000162f  mov     rbx, rcx
0x180001632  xor     edx, edx; Val
0x180001634  lea     rcx, [rsp+4A8h+Buffer]; void *
0x18000163c  mov     r8d, 20Ah; Size
0x180001642  call    memset_0
0x180001647  mov     edi, 105h
0x18000164c  mov     [rsp+4A8h+FilePart], 0
0x180001655  mov     edx, edi; nBufferLength
0x180001657  lea     r9, [rsp+4A8h+FilePart]; lpFilePart
0x18000165c  lea     r8, [rsp+4A8h+Buffer]; lpBuffer
0x180001664  mov     rcx, rbx; lpFileName
0x180001667  call    cs:__imp_GetFullPathNameW
0x18000166d  cmp     eax, 104h
0x180001672  ja      loc_180001743
0x180001678  mov     eax, 7FFFFFFEh
0x18000167d  lea     rdx, [rsp+4A8h+Buffer]
0x180001685  mov     r8d, edi
0x180001688  mov     r9, rbx
0x18000168b  nop     dword ptr [rax+rax+00h]
0x180001690  test    rax, rax
0x180001693  jz      short loc_1800016B2
0x180001695  movzx   ecx, word ptr [rdx]
0x180001698  test    cx, cx
0x18000169b  jz      short loc_1800016B2
0x18000169d  mov     [r9], cx
0x1800016a1  add     rdx, 2
0x1800016a5  add     r9, 2
0x1800016a9  dec     rax
0x1800016ac  sub     r8, 1
0x1800016b0  jnz     short loc_180001690
0x1800016b2  test    r8, r8
0x1800016b5  lea     rcx, [r9-2]
0x1800016b9  cmovnz  rcx, r9
0x1800016bd  xor     eax, eax
0x1800016bf  mov     [rcx], ax
0x1800016c2  test    r8, r8
0x1800016c5  jz      short loc_180001743
0x1800016c7  mov     rcx, rbx; lpFileName
0x1800016ca  call    cs:__imp_GetFileAttributesW
0x1800016d0  cmp     eax, 0FFFFFFFFh
0x1800016d3  jz      short loc_180001743
0x1800016d5  test    al, 10h
0x1800016d7  jnz     short loc_180001743
0x1800016d9  xor     edx, edx; Val
0x1800016db  lea     rcx, [rsp+4A8h+FindFileData]; void *
0x1800016e0  mov     r8d, 250h; Size
0x1800016e6  call    memset_0
0x1800016eb  lea     rdx, [rsp+4A8h+FindFileData]; lpFindFileData
0x1800016f0  mov     rcx, rbx; lpFileName
0x1800016f3  call    cs:__imp_FindFirstFileW
0x1800016f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800016fd  jz      short loc_180001743
0x1800016ff  mov     rcx, rax; hFindFile
0x180001702  call    cs:__imp_FindClose
0x180001708  mov     edx, 5Ch ; '\'; Ch
0x18000170d  mov     rcx, rbx; Str
0x180001710  call    cs:__imp_wcsrchr
0x180001716  test    rax, rax
0x180001719  jz      short loc_18000173C
0x18000171b  mov     rcx, rax
0x18000171e  lea     r8, [rsp+4A8h+FindFileData.cFileName]; unsigned __int16 *
0x180001723  sub     rcx, rbx
0x180001726  add     rcx, 2
0x18000172a  sar     rcx, 1
0x18000172d  sub     rdi, rcx
0x180001730  lea     rcx, [rax+2]; unsigned __int16 *
0x180001734  mov     rdx, rdi; unsigned __int64
0x180001737  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000173c  mov     eax, 1
0x180001741  jmp     short loc_180001745
0x180001743  xor     eax, eax
0x180001745  mov     rcx, [rsp+4A8h+var_18]
0x18000174d  xor     rcx, rsp; StackCookie
0x180001750  call    __security_check_cookie
0x180001755  mov     rbx, [rsp+4A8h+arg_8]
0x18000175d  add     rsp, 4A0h
0x180001764  pop     rdi
0x180001765  retn
```

# SNILoadSystemLibA

- ea: `0x100417768`
- end: `0x10041785b`
- name: `SNILoadSystemLibA`
- size: `243`
- prototype: `__int64 __fastcall(LPCSTR lpLibFileName)`
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x100413e30`
- `0x10042f37c`
- `0x100434a28`
- `0x1004354b4`
- `0x1004394a8`
- `0x100439fac`
- `0x10043b49c`
- `0x10043ff40`

## callees

- `0x100417768`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x1004177b9`
- `KERNEL32!LoadLibraryExA` at `0x1004177b9`
- `KERNEL32!GetLastError` at `0x1004177c7`
- `KERNEL32!GetLastError` at `0x1004177c7`
- `KERNEL32!SetLastError` at `0x10041783d`
- `KERNEL32!SetLastError` at `0x10041783d`

## pseudocode

```c
HMODULE __fastcall SNILoadSystemLibA(LPCSTR lpLibFileName)
{
  DWORD v2; // ebx
  HMODULE Library; // rdi
  DWORD LastError; // eax
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7820[0] )
    bidScopeEnterW(&v6, off_1005E7820[0], lpLibFileName);
  v2 = 0;
  Library = LoadLibraryExA(lpLibFileName, 0, 0x800u);
  if ( !Library )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_1005E47D8[0] )
        bidTraceW(0, 3617792, off_1005E47D8[0], LastError);
    }
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E47E0[0] )
    bidTraceW(0, 3623936, off_1005E47E0[0], Library);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v6);
  if ( v2 )
    SetLastError(v2);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v6);
  return Library;
}

```

## disassembly

```asm
0x100417768  mov     [rsp+arg_0], rbx
0x10041776d  push    rdi
0x10041776e  sub     rsp, 20h
0x100417772  mov     eax, cs:_bidGblFlags
0x100417778  mov     rdi, rcx
0x10041777b  or      [rsp+28h+arg_8], 0FFFFFFFFFFFFFFFFh
0x100417781  mov     ecx, 20004h
0x100417786  and     eax, ecx
0x100417788  cmp     eax, ecx
0x10041778a  jnz     short loc_1004177AC
0x10041778c  mov     rax, cs:off_1005E7820; "<SNILoadSystemLibA|API|SNI> szDllFileNa"...
0x100417793  test    rax, rax
0x100417796  jz      short loc_1004177AC
0x100417798  mov     rdx, cs:off_1005E7820; "<SNILoadSystemLibA|API|SNI> szDllFileNa"...
0x10041779f  lea     rcx, [rsp+28h+arg_8]
0x1004177a4  mov     r8, rdi
0x1004177a7  call    _bidScopeEnterW
0x1004177ac  xor     edx, edx; hFile
0x1004177ae  mov     r8d, 800h; dwFlags
0x1004177b4  mov     rcx, rdi; lpLibFileName
0x1004177b7  xor     ebx, ebx
0x1004177b9  call    cs:__imp_LoadLibraryExA
0x1004177bf  mov     rdi, rax
0x1004177c2  test    rax, rax
0x1004177c5  jnz     short loc_1004177FA
0x1004177c7  call    cs:__imp_GetLastError
0x1004177cd  test    byte ptr cs:_bidGblFlags, 2
0x1004177d4  mov     ebx, eax
0x1004177d6  jz      short loc_1004177FA
0x1004177d8  mov     rcx, cs:off_1005E47D8; "<SNILoadSystemLibA|ERR|SNI> LoadLibrary"...
0x1004177df  test    rcx, rcx
0x1004177e2  jz      short loc_1004177FA
0x1004177e4  mov     r8, cs:off_1005E47D8; "<SNILoadSystemLibA|ERR|SNI> LoadLibrary"...
0x1004177eb  mov     r9d, eax
0x1004177ee  mov     edx, 373400h
0x1004177f3  xor     ecx, ecx
0x1004177f5  call    _bidTraceW
0x1004177fa  mov     eax, cs:_bidGblFlags
0x100417800  mov     ecx, 20002h
0x100417805  and     eax, ecx
0x100417807  cmp     eax, ecx
0x100417809  jnz     short loc_10041782D
0x10041780b  mov     rax, cs:off_1005E47E0; "<SNILoadSystemLibA|RET|SNI> %p{HMODULE}"...
0x100417812  test    rax, rax
0x100417815  jz      short loc_10041782D
0x100417817  mov     r8, cs:off_1005E47E0; "<SNILoadSystemLibA|RET|SNI> %p{HMODULE}"...
0x10041781e  mov     r9, rdi
0x100417821  mov     edx, 374C00h
0x100417826  xor     ecx, ecx
0x100417828  call    _bidTraceW
0x10041782d  lea     rcx, [rsp+28h+arg_8]; this
0x100417832  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100417837  test    ebx, ebx
0x100417839  jz      short loc_100417843
0x10041783b  mov     ecx, ebx; dwErrCode
0x10041783d  call    cs:__imp_SetLastError
0x100417843  lea     rcx, [rsp+28h+arg_8]; this
0x100417848  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10041784d  mov     rbx, [rsp+28h+arg_0]
0x100417852  mov     rax, rdi
0x100417855  add     rsp, 20h
0x100417859  pop     rdi
0x10041785a  retn
```

# SNILoadSystemLibA

- ea: `0x180157620`
- end: `0x180157740`
- name: `SNILoadSystemLibA`
- size: `288`
- prototype: `__int64 __fastcall(LPCSTR lpLibFileName)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180153310`
- `0x180164760`
- `0x1801652a0`
- `0x180178220`
- `0x18017be20`
- `0x18017f4d0`
- `0x180182ee0`
- `0x1801aa680`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180157620`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180157692`
- `KERNEL32!GetLastError` at `0x180157692`
- `KERNEL32!SetLastError` at `0x180157713`
- `KERNEL32!SetLastError` at `0x180157713`
- `KERNEL32!LoadLibraryExA` at `0x180157684`
- `KERNEL32!LoadLibraryExA` at `0x180157684`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HMODULE __fastcall SNILoadSystemLibA(LPCSTR lpLibFileName, __int64 a2, __int64 a3, __int64 a4)
{
  DWORD v5; // ebx
  HMODULE Library; // rdi
  DWORD LastError; // eax
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF

  v9 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1802667E8[0] )
    bidScopeEnterW(&v9, off_1802667E8[0], lpLibFileName, a4);
  v5 = 0;
  Library = LoadLibraryExA(lpLibFileName, 0, 0x800u);
  if ( !Library )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180263ED8[0] )
        bidTraceW(off_180260B90[0], 3347456, off_180263ED8[0], LastError);
    }
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263EE0[0] )
    bidTraceW(off_180260B98[0], 3353600, off_180263EE0[0], Library);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v9);
  if ( v5 )
    SetLastError(v5);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v9);
  return Library;
}

```

## disassembly

```asm
0x180157620  mov     [rsp+arg_8], rbx
0x180157625  push    rdi
0x180157626  sub     rsp, 30h
0x18015762a  mov     rax, cs:__security_cookie
0x180157631  xor     rax, rsp
0x180157634  mov     [rsp+38h+var_10], rax
0x180157639  mov     rdi, rcx
0x18015763c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFFh
0x180157645  mov     eax, cs:_bidGblFlags
0x18015764b  and     eax, 20004h
0x180157650  cmp     eax, 20004h
0x180157655  jnz     short loc_180157677
0x180157657  mov     rax, cs:off_1802667E8; "<SNILoadSystemLibA|API|SNI> szDllFileNa"...
0x18015765e  test    rax, rax
0x180157661  jz      short loc_180157677
0x180157663  mov     r8, rcx
0x180157666  mov     rdx, cs:off_1802667E8; "<SNILoadSystemLibA|API|SNI> szDllFileNa"...
0x18015766d  lea     rcx, [rsp+38h+var_18]
0x180157672  call    _bidScopeEnterW
0x180157677  xor     ebx, ebx
0x180157679  xor     edx, edx; hFile
0x18015767b  mov     r8d, 800h; dwFlags
0x180157681  mov     rcx, rdi; lpLibFileName
0x180157684  call    cs:__imp_LoadLibraryExA
0x18015768a  mov     rdi, rax
0x18015768d  test    rax, rax
0x180157690  jnz     short loc_1801576CA
0x180157692  call    cs:__imp_GetLastError
0x180157698  mov     ebx, eax
0x18015769a  test    byte ptr cs:_bidGblFlags, 2
0x1801576a1  jz      short loc_1801576CA
0x1801576a3  mov     rcx, cs:off_180263ED8; "<SNILoadSystemLibA|ERR|SNI> LoadLibrary"...
0x1801576aa  test    rcx, rcx
0x1801576ad  jz      short loc_1801576CA
0x1801576af  mov     r9d, eax
0x1801576b2  mov     r8, cs:off_180263ED8; "<SNILoadSystemLibA|ERR|SNI> LoadLibrary"...
0x1801576b9  mov     edx, 331400h
0x1801576be  mov     rcx, cs:off_180260B90; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801576c5  call    _bidTraceW
0x1801576ca  mov     eax, cs:_bidGblFlags
0x1801576d0  and     eax, 20002h
0x1801576d5  cmp     eax, 20002h
0x1801576da  jnz     short loc_180157703
0x1801576dc  mov     rax, cs:off_180263EE0; "<SNILoadSystemLibA|RET|SNI> %p{HMODULE}"...
0x1801576e3  test    rax, rax
0x1801576e6  jz      short loc_180157703
0x1801576e8  mov     r9, rdi
0x1801576eb  mov     r8, cs:off_180263EE0; "<SNILoadSystemLibA|RET|SNI> %p{HMODULE}"...
0x1801576f2  mov     edx, 332C00h
0x1801576f7  mov     rcx, cs:off_180260B98; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801576fe  call    _bidTraceW
0x180157703  lea     rcx, [rsp+38h+var_18]; this
0x180157708  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015770d  test    ebx, ebx
0x18015770f  jz      short loc_18015771A
0x180157711  mov     ecx, ebx; dwErrCode
0x180157713  call    cs:__imp_SetLastError
0x180157719  nop
0x18015771a  lea     rcx, [rsp+38h+var_18]; this
0x18015771f  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180157724  nop
0x180157725  mov     rax, rdi
0x180157728  mov     rcx, [rsp+38h+var_10]
0x18015772d  xor     rcx, rsp; StackCookie
0x180157730  call    __security_check_cookie
0x180157735  mov     rbx, [rsp+38h+arg_8]
0x18015773a  add     rsp, 30h
0x18015773e  pop     rdi
0x18015773f  retn
```

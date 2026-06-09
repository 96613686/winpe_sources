# myLoadNetApi(ushort const *,char const *,ushort const *,HINSTANCE__ * *,__int64 (**)(void))

- ea: `0x1800103fc`
- end: `0x1800104d3`
- name: `?myLoadNetApi@@YAJPEBGPEBD0PEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z`
- size: `215`
- prototype: `__int64 __fastcall(const unsigned __int16 *, CHAR *lpProcName, const unsigned __int16 *, HINSTANCE *, __int64 (**)(void))`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180028150`
- `0x1800281d8`
- `0x18002a530`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000d9f0`
- `0x1800103fc`
- `0x180012450`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010475`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010475`

## string_xrefs

- `0x180010444`: `netapi32.dll`

## pseudocode

```c
__int64 __fastcall myLoadNetApi(
        const unsigned __int16 *a1,
        CHAR *lpProcName,
        const unsigned __int16 *a3,
        HINSTANCE *a4,
        __int64 (**a5)(void))
{
  HMODULE System32Library; // rax
  int v10; // eax
  void *v11; // rdx
  int v12; // eax
  unsigned int v13; // ecx
  __int64 (*ProcAddress)(void); // rax
  unsigned int v15; // ebx

  System32Library = *a4;
  if ( *a4
    || (System32Library = myLoadSystem32LibraryEx(a1, lpProcName, 0), (*a4 = System32Library) != 0)
    || (v10 = myHLastError(),
        CSPrintErrorLineFileData2(a1, 0x2A01CBu, v10, 0),
        System32Library = myLoadSystem32LibraryEx(L"netapi32.dll", v11, 0),
        (*a4 = System32Library) != 0) )
  {
    if ( *a5 )
      return 0;
    ProcAddress = GetProcAddress(System32Library, lpProcName);
    *a5 = ProcAddress;
    if ( ProcAddress )
      return 0;
    v12 = myHLastError();
    v13 = 4129227;
  }
  else
  {
    v12 = myHLastError();
    v13 = 3146187;
  }
  v15 = v12;
  CSPrintErrorLineFile(v13, v12);
  if ( v15 )
  {
    CSPrintErrorLineFileData2(a1, 0x4801CBu, 1, 0);
    CSPrintErrorLineFileData2(a3, 0x4901CBu, 1, 0);
  }
  return v15;
}

```

## disassembly

```asm
0x1800103fc  push    rbx
0x1800103fe  push    rbp
0x1800103ff  push    rsi
0x180010400  push    rdi
0x180010401  sub     rsp, 28h
0x180010405  mov     rax, [r9]
0x180010408  mov     rbx, r9
0x18001040b  mov     rbp, r8
0x18001040e  mov     rsi, rdx
0x180010411  mov     rdi, rcx
0x180010414  test    rax, rax
0x180010417  jnz     short loc_180010464
0x180010419  xor     r8d, r8d; unsigned int
0x18001041c  call    ?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; myLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x180010421  mov     [rbx], rax
0x180010424  test    rax, rax
0x180010427  jnz     short loc_180010464
0x180010429  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001042e  xor     r9d, r9d; int
0x180010431  mov     r8d, eax; int
0x180010434  mov     edx, 2A01CBh; unsigned int
0x180010439  mov     rcx, rdi; unsigned __int16 *
0x18001043c  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180010441  xor     r8d, r8d; unsigned int
0x180010444  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x18001044b  call    ?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; myLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x180010450  mov     [rbx], rax
0x180010453  test    rax, rax
0x180010456  jnz     short loc_180010464
0x180010458  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001045d  mov     ecx, 3001CBh
0x180010462  jmp     short loc_18001048D
0x180010464  mov     rbx, [rsp+48h+arg_20]
0x180010469  cmp     qword ptr [rbx], 0
0x18001046d  jnz     short loc_1800104C6
0x18001046f  mov     rdx, rsi; lpProcName
0x180010472  mov     rcx, rax; hModule
0x180010475  call    cs:__imp_GetProcAddress
0x18001047b  mov     [rbx], rax
0x18001047e  test    rax, rax
0x180010481  jnz     short loc_1800104C6
0x180010483  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010488  mov     ecx, 3F01CBh; unsigned int
0x18001048d  mov     edx, eax; int
0x18001048f  mov     ebx, eax
0x180010491  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180010496  test    ebx, ebx
0x180010498  jz      short loc_1800104C8
0x18001049a  xor     r9d, r9d; int
0x18001049d  mov     edx, 4801CBh; unsigned int
0x1800104a2  mov     rcx, rdi; unsigned __int16 *
0x1800104a5  lea     esi, [r9+1]
0x1800104a9  mov     r8d, esi; int
0x1800104ac  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800104b1  xor     r9d, r9d; int
0x1800104b4  mov     r8d, esi; int
0x1800104b7  mov     edx, 4901CBh; unsigned int
0x1800104bc  mov     rcx, rbp; unsigned __int16 *
0x1800104bf  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800104c4  jmp     short loc_1800104C8
0x1800104c6  xor     ebx, ebx
0x1800104c8  mov     eax, ebx
0x1800104ca  add     rsp, 28h
0x1800104ce  pop     rdi
0x1800104cf  pop     rsi
0x1800104d0  pop     rbp
0x1800104d1  pop     rbx
0x1800104d2  retn
```

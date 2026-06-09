# LinkToDll(HINSTANCE__ * *,char const *,char const * *,void * * const,ulong)

- ea: `0x1800035ec`
- end: `0x1800036eb`
- name: `?LinkToDll@@YAHPEAPEAUHINSTANCE__@@PEBDPEAPEBDQEAPEAXK@Z`
- size: `255`
- prototype: `__int64 __fastcall(HINSTANCE *, const char *, const char **, void **const, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002310`

## callees

- `0x1800035ec`
- `0x180004d54`
- `0x180004e1c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180003688`
- `KERNEL32!GetProcAddress` at `0x180003688`
- `KERNEL32!LoadLibraryExA` at `0x180003626`
- `KERNEL32!LoadLibraryExA` at `0x180003626`
- `KERNEL32!GetLastError` at `0x1800036b1`
- `KERNEL32!GetLastError` at `0x1800036b1`

## string_xrefs

- `0x1800035fe`: `advapi32.dll`
- `0x180003609`: `LinkToDll - Loading library - %s`
- `0x180003649`: `LinkToDll[phInst=%p, *pszDll=%s, ppszPfn=%p,`
- `0x18000365b`: `	ppvPfn=%p] LoadLibrary() failed.`
- `0x1800036a2`: `BindLinkage(hInstDll=%d,ppszPfn=%p,ppvPfn=%p)`
- `0x1800036bb`: `	GetProcAddress(hInstDll=%d,*pszProc=%S) failed, GLE=%u.`

## pseudocode

```c
__int64 __fastcall LinkToDll(HINSTANCE *a1, const char *a2, const char **a3, void **const a4)
{
  HMODULE Library; // rax
  HMODULE v7; // r15
  unsigned int v9; // ebp
  __int64 v10; // rbx
  const CHAR *v11; // rdx
  FARPROC ProcAddress; // rax

  MyDbgPrintfA(0xFFFFFFFFLL, "LinkToDll - Loading library - %s", "advapi32.dll");
  Library = LoadLibraryExA("advapi32.dll", 0, 0);
  *a1 = Library;
  v7 = Library;
  if ( Library )
  {
    v9 = 1;
    v10 = 0;
    do
    {
      v11 = (const CHAR *)(&apszAdvapi32)[v10];
      if ( !v11 )
        break;
      if ( !a4[v10] )
      {
        ProcAddress = GetProcAddress(v7, v11);
        a4[v10] = ProcAddress;
        if ( !ProcAddress )
        {
          MyDbgPrintfW(0xFFFFFFFFLL, L"BindLinkage(hInstDll=%d,ppszPfn=%p,ppvPfn=%p)", v7, &apszAdvapi32);
          GetLastError();
          MyDbgPrintfW(
            0xFFFFFFFFLL,
            L"\tGetProcAddress(hInstDll=%d,*pszProc=%S) failed, GLE=%u.",
            v7,
            (&apszAdvapi32)[v10]);
          v9 = 0;
        }
      }
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < 0xC );
    return v9;
  }
  else
  {
    MyDbgPrintfA(0xFFFFFFFFLL, "LinkToDll[phInst=%p, *pszDll=%s, ppszPfn=%p,", a1, "advapi32.dll", &apszAdvapi32);
    MyDbgPrintfA(0xFFFFFFFFLL, "\tppvPfn=%p] LoadLibrary() failed.", a4);
    return 0;
  }
}

```

## disassembly

```asm
0x1800035ec  push    rbx
0x1800035ee  push    rbp
0x1800035ef  push    rsi
0x1800035f0  push    rdi
0x1800035f1  push    r12
0x1800035f3  push    r14
0x1800035f5  push    r15
0x1800035f7  sub     rsp, 30h
0x1800035fb  mov     rbx, rcx
0x1800035fe  lea     rsi, aAdvapi32Dll_0; "advapi32.dll"
0x180003605  or      r12d, 0FFFFFFFFh
0x180003609  lea     rdx, aLinktodllLoadi; "LinkToDll - Loading library - %s"
0x180003610  mov     r8, rsi
0x180003613  mov     ecx, r12d
0x180003616  mov     r14, r9
0x180003619  call    MyDbgPrintfA
0x18000361e  xor     r8d, r8d; dwFlags
0x180003621  xor     edx, edx; hFile
0x180003623  mov     rcx, rsi; lpLibFileName
0x180003626  call    cs:__imp_LoadLibraryExA
0x18000362c  mov     [rbx], rax
0x18000362f  mov     r15, rax
0x180003632  lea     rdi, ?apszAdvapi32@@3PAPEBDA; char const * near * apszAdvapi32
0x180003639  test    rax, rax
0x18000363c  jnz     short loc_18000366E
0x18000363e  mov     r9, rsi
0x180003641  mov     [rsp+68h+var_48], rdi
0x180003646  mov     r8, rbx
0x180003649  lea     rdx, aLinktodllPhins; "LinkToDll[phInst=%p, *pszDll=%s, ppszPf"...
0x180003650  mov     ecx, r12d
0x180003653  call    MyDbgPrintfA
0x180003658  mov     r8, r14
0x18000365b  lea     rdx, aPpvpfnPLoadlib; "\tppvPfn=%p] LoadLibrary() failed."
0x180003662  mov     ecx, r12d
0x180003665  call    MyDbgPrintfA
0x18000366a  xor     eax, eax
0x18000366c  jmp     short loc_1800036DC
0x18000366e  mov     ebp, 1
0x180003673  xor     ebx, ebx
0x180003675  mov     rdx, [rdi+rbx*8]; lpProcName
0x180003679  test    rdx, rdx
0x18000367c  jz      short loc_1800036DA
0x18000367e  cmp     qword ptr [r14+rbx*8], 0
0x180003683  jnz     short loc_1800036D3
0x180003685  mov     rcx, r15; hModule
0x180003688  call    cs:__imp_GetProcAddress
0x18000368e  mov     [r14+rbx*8], rax
0x180003692  test    rax, rax
0x180003695  jnz     short loc_1800036D3
0x180003697  mov     r9, rdi
0x18000369a  mov     [rsp+68h+var_48], r14
0x18000369f  mov     r8, r15
0x1800036a2  lea     rdx, aBindlinkageHin; "BindLinkage(hInstDll=%d,ppszPfn=%p,ppvP"...
0x1800036a9  mov     ecx, r12d
0x1800036ac  call    MyDbgPrintfW
0x1800036b1  call    cs:__imp_GetLastError
0x1800036b7  mov     r9, [rdi+rbx*8]
0x1800036bb  lea     rdx, aGetprocaddress_6; "\tGetProcAddress(hInstDll=%d,*pszProc=%"...
0x1800036c2  mov     r8, r15
0x1800036c5  mov     dword ptr [rsp+68h+var_48], eax
0x1800036c9  mov     ecx, r12d
0x1800036cc  call    MyDbgPrintfW
0x1800036d1  xor     ebp, ebp
0x1800036d3  inc     ebx
0x1800036d5  cmp     ebx, 0Ch
0x1800036d8  jb      short loc_180003675
0x1800036da  mov     eax, ebp
0x1800036dc  add     rsp, 30h
0x1800036e0  pop     r15
0x1800036e2  pop     r14
0x1800036e4  pop     r12
0x1800036e6  pop     rdi
0x1800036e7  pop     rsi
0x1800036e8  pop     rbp
0x1800036e9  pop     rbx
0x1800036ea  retn
```

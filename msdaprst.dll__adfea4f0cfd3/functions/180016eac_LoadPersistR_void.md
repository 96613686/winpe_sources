# LoadPersistR(void)

- ea: `0x180016eac`
- end: `0x180017087`
- name: `?LoadPersistR@@YAXXZ`
- size: `475`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180016e0c`

## callees

- `0x180001858`
- `0x180009ffc`
- `0x180016eac`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f0e0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180016eee`
- `KERNEL32!GetModuleFileNameW` at `0x180016eee`
- `KERNEL32!LoadLibraryExW` at `0x180017001`
- `KERNEL32!LoadLibraryExW` at `0x180017001`

## string_xrefs

- `0x180016f9a`: `msdaprsr.dll`

## pseudocode

```c
void LoadPersistR(void)
{
  int v0; // eax
  unsigned __int64 v1; // rdx
  unsigned __int64 v2; // rdx
  int v3; // eax
  int v4; // ebx
  WCHAR Filename[256]; // [rsp+30h] [rbp-218h] BYREF

  if ( !g_hinstance_PersistR )
  {
    LOWORD(v0) = GetModuleFileNameW(g_hInstancePersistMain, Filename, 0xFFu);
    if ( (__int16)v0 <= 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049AD0[0] )
          bidTraceW(off_1800491E8[0], 71680, off_180049AD0[0], 2147500037LL, 70);
      }
      goto LABEL_22;
    }
    v0 = (__int16)v0;
    do
      v1 = v0--;
    while ( Filename[v0] != 92 );
    v2 = v1;
    if ( v2 >= 256 )
      _report_rangecheckfailure();
    Filename[v2] = 0;
    if ( (unsigned __int64)(v0 + 12LL) >= 0xFF )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049AC8[0] )
        bidTraceW(off_1800491E8[0], 82944, off_180049AC8[0], 2147500037LL, 81);
      goto LABEL_22;
    }
    v3 = StringCchCatW(Filename, 0x100u, L"msdaprsr.dll");
    v4 = v3;
    if ( v3 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049AC0[0] )
        bidTraceW(off_1800491E8[0], 86016, off_180049AC0[0], (unsigned int)v3, 84);
      ThrowHR(v4);
    }
    g_hinstance_PersistR = LoadLibraryExW(Filename, 0, 8u);
    if ( !g_hinstance_PersistR )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049AB8[0] )
        bidTraceW(off_1800491E8[0], 92160, off_180049AB8[0], 2147500037LL, 90);
LABEL_22:
      ThrowHR(-2147467259);
    }
  }
}

```

## disassembly

```asm
0x180016eac  mov     [rsp+arg_0], rbx
0x180016eb1  push    rdi
0x180016eb2  sub     rsp, 240h
0x180016eb9  mov     rax, cs:__security_cookie
0x180016ec0  xor     rax, rsp
0x180016ec3  mov     [rsp+248h+var_18], rax
0x180016ecb  xor     edi, edi
0x180016ecd  cmp     cs:?g_hinstance_PersistR@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hinstance_PersistR
0x180016ed4  jnz     loc_180017065
0x180016eda  mov     rcx, cs:?g_hInstancePersistMain@@3PEAUHINSTANCE__@@EA; hModule
0x180016ee1  lea     rdx, [rsp+248h+Filename]; lpFilename
0x180016ee6  mov     ebx, 0FFh
0x180016eeb  mov     r8d, ebx; nSize
0x180016eee  call    cs:__imp_GetModuleFileNameW
0x180016ef5  nop     dword ptr [rax+rax+00h]
0x180016efa  test    ax, ax
0x180016efd  jg      short loc_180016F35
0x180016eff  test    byte ptr cs:_bidGblFlags, 2
0x180016f06  jz      loc_180017054
0x180016f0c  mov     rax, cs:off_180049AD0; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180016f13  test    rax, rax
0x180016f16  jz      loc_180017054
0x180016f1c  mov     r8, cs:off_180049AD0; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180016f23  mov     edx, 11800h
0x180016f28  mov     [rsp+248h+var_228], 46h ; 'F'
0x180016f30  jmp     loc_180017042
0x180016f35  cwde
0x180016f36  movsxd  rdx, eax
0x180016f39  dec     eax
0x180016f3b  movsxd  rcx, eax
0x180016f3e  cmp     [rsp+rcx*2+248h+Filename], 5Ch ; '\'
0x180016f44  jnz     short loc_180016F36
0x180016f46  add     rdx, rdx
0x180016f49  cmp     rdx, 200h
0x180016f50  jnb     loc_18001705F
0x180016f56  lea     rax, [rcx+0Ch]
0x180016f5a  mov     [rsp+rdx+248h+Filename], di
0x180016f5f  cmp     rax, rbx
0x180016f62  jb      short loc_180016F9A
0x180016f64  test    byte ptr cs:_bidGblFlags, 2
0x180016f6b  jz      loc_180017054
0x180016f71  mov     rax, cs:off_180049AC8; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180016f78  test    rax, rax
0x180016f7b  jz      loc_180017054
0x180016f81  mov     r8, cs:off_180049AC8; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180016f88  mov     edx, 14400h
0x180016f8d  mov     [rsp+248h+var_228], 51h ; 'Q'
0x180016f95  jmp     loc_180017042
0x180016f9a  lea     r8, aMsdaprsrDll; "msdaprsr.dll"
0x180016fa1  mov     edx, 100h; unsigned __int64
0x180016fa6  lea     rcx, [rsp+248h+Filename]; unsigned __int16 *
0x180016fab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016fb0  mov     ebx, eax
0x180016fb2  test    eax, eax
0x180016fb4  jns     short loc_180016FF6
0x180016fb6  test    byte ptr cs:_bidGblFlags, 2
0x180016fbd  jz      short loc_180016FEE
0x180016fbf  mov     rcx, cs:off_180049AC0; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180016fc6  test    rcx, rcx
0x180016fc9  jz      short loc_180016FEE
0x180016fcb  mov     r8, cs:off_180049AC0; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180016fd2  mov     r9d, eax
0x180016fd5  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180016fdc  mov     edx, 15000h
0x180016fe1  mov     [rsp+248h+var_228], 54h ; 'T'
0x180016fe9  call    _bidTraceW
0x180016fee  mov     ecx, ebx; int
0x180016ff0  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016ff6  xor     edx, edx; hFile
0x180016ff8  lea     rcx, [rsp+248h+Filename]; lpLibFileName
0x180016ffd  lea     r8d, [rdx+8]; dwFlags
0x180017001  call    cs:__imp_LoadLibraryExW
0x180017008  nop     dword ptr [rax+rax+00h]
0x18001700d  mov     cs:?g_hinstance_PersistR@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinstance_PersistR
0x180017014  test    rax, rax
0x180017017  jnz     short loc_180017065
0x180017019  test    byte ptr cs:_bidGblFlags, 2
0x180017020  jz      short loc_180017054
0x180017022  mov     rax, cs:off_180049AB8; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180017029  test    rax, rax
0x18001702c  jz      short loc_180017054
0x18001702e  mov     r8, cs:off_180049AB8; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180017035  mov     edx, 16800h
0x18001703a  mov     [rsp+248h+var_228], 5Ah ; 'Z'
0x180017042  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017049  mov     r9d, 80004005h
0x18001704f  call    _bidTraceW
0x180017054  mov     ecx, 80004005h; int
0x180017059  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001705f  call    __report_rangecheckfailure
0x180017065  mov     rcx, [rsp+248h+var_18]
0x18001706d  xor     rcx, rsp; StackCookie
0x180017070  call    __security_check_cookie
0x180017075  mov     rbx, [rsp+248h+arg_0]
0x18001707d  add     rsp, 240h
0x180017084  pop     rdi
0x180017085  retn
```

# CMapsToastTaskHandler::LoadResources(ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800040f0`
- end: `0x1800042dd`
- name: `?LoadResources@CMapsToastTaskHandler@@AEAAJKKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `493`
- prototype: `__int64 __fastcall(const void *, UINT, UINT, char **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180005e60`

## callees

- `0x1800015b0`
- `0x1800020a4`
- `0x1800040f0`
- `0x18000954c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x180004176`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180004176`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004138`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004138`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800042b1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800042b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004193`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004228`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004193`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004232`

## string_xrefs

- `0x180004128`: `moshost.dll`
- `0x18000416d`: `CMapsToastTaskHandler::LoadResources`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::LoadResources(const void *a1, UINT a2, UINT a3, char **a4, void **a5)
{
  HMODULE Library; // rax
  HMODULE v10; // r15
  signed int LastError; // eax
  int v12; // r8d
  unsigned int v13; // esi
  __int64 v14; // r8
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rdx
  char *v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // r8
  void *v20; // rbp
  WCHAR Buffer[1024]; // [rsp+20h] [rbp-858h] BYREF

  Library = LoadLibraryExW(L"moshost.dll", 0, 0x822u);
  v10 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v12 = 207;
LABEL_7:
    v13 = ZTraceReportOrigination(LastError, "CMapsToastTaskHandler::LoadResources", v12, a1);
    goto LABEL_36;
  }
  if ( !LoadStringW(Library, a2, Buffer, 1024) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v12 = 209;
    goto LABEL_7;
  }
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( Buffer[v16] );
  if ( v16 > (unsigned __int64)a4[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      a4,
      v16,
      v14,
      Buffer);
  }
  else
  {
    if ( (unsigned __int64)a4[3] <= 7 )
      v17 = (char *)a4;
    else
      v17 = *a4;
    a4[2] = (char *)v16;
    v18 = 2 * v16;
    memmove_0(v17, Buffer, 2 * v16);
    *(_WORD *)&v17[v18] = 0;
  }
  if ( !LoadStringW(v10, a3, Buffer, 1024) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v12 = 212;
    goto LABEL_7;
  }
  v13 = 0;
  do
    ++v15;
  while ( Buffer[v15] );
  if ( v15 > (unsigned __int64)a5[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      a5,
      v15,
      v19,
      Buffer);
  }
  else
  {
    if ( (unsigned __int64)a5[3] <= 7 )
      v20 = a5;
    else
      v20 = *a5;
    a5[2] = (void *)v15;
    memmove_0(v20, Buffer, 2 * v15);
    *((_WORD *)v20 + v15) = 0;
  }
LABEL_36:
  FreeLibrary(v10);
  return v13;
}

```

## disassembly

```asm
0x1800040f0  push    rbx
0x1800040f2  push    rbp
0x1800040f3  push    rsi
0x1800040f4  push    rdi
0x1800040f5  push    r12
0x1800040f7  push    r13
0x1800040f9  push    r14
0x1800040fb  push    r15
0x1800040fd  sub     rsp, 838h
0x180004104  mov     rax, cs:__security_cookie
0x18000410b  xor     rax, rsp
0x18000410e  mov     [rsp+878h+var_58], rax
0x180004116  mov     r14, [rsp+878h+arg_20]
0x18000411e  mov     r12d, r8d
0x180004121  mov     edi, edx
0x180004123  mov     rbp, rcx
0x180004126  xor     edx, edx; hFile
0x180004128  lea     rcx, LibFileName; "moshost.dll"
0x18000412f  mov     r8d, 822h; dwFlags
0x180004135  mov     rbx, r9
0x180004138  call    cs:__imp_LoadLibraryExW
0x18000413e  xor     r13d, r13d
0x180004141  mov     r15, rax
0x180004144  test    rax, rax
0x180004147  jnz     short loc_180004183
0x180004149  call    cs:__imp_GetLastError
0x18000414f  test    eax, eax
0x180004151  jz      short loc_18000415F
0x180004153  jle     short loc_180004164
0x180004155  movzx   eax, ax
0x180004158  or      eax, 80070000h
0x18000415d  jmp     short loc_180004164
0x18000415f  mov     eax, 80390004h
0x180004164  mov     r8d, 0CFh
0x18000416a  mov     r9, rbp
0x18000416d  lea     rdx, aCmapstoasttask; "CMapsToastTaskHandler::LoadResources"
0x180004174  mov     ecx, eax
0x180004176  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000417c  mov     esi, eax
0x18000417e  jmp     loc_1800042AE
0x180004183  mov     r9d, 400h; cchBufferMax
0x180004189  lea     r8, [rsp+878h+Buffer]; lpBuffer
0x18000418e  mov     edx, edi; uID
0x180004190  mov     rcx, r15; hInstance
0x180004193  call    cs:__imp_LoadStringW
0x180004199  test    eax, eax
0x18000419b  jnz     short loc_1800041C0
0x18000419d  call    cs:__imp_GetLastError
0x1800041a3  test    eax, eax
0x1800041a5  jz      short loc_1800041B3
0x1800041a7  jle     short loc_1800041B8
0x1800041a9  movzx   eax, ax
0x1800041ac  or      eax, 80070000h
0x1800041b1  jmp     short loc_1800041B8
0x1800041b3  mov     eax, 80390004h
0x1800041b8  mov     r8d, 0D1h
0x1800041be  jmp     short loc_18000416A
0x1800041c0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800041c4  lea     rax, [rsp+878h+Buffer]
0x1800041c9  mov     rdx, rdi
0x1800041cc  inc     rdx
0x1800041cf  cmp     [rax+rdx*2], r13w
0x1800041d4  jnz     short loc_1800041CC
0x1800041d6  cmp     rdx, [rbx+18h]
0x1800041da  ja      short loc_18000420A
0x1800041dc  cmp     qword ptr [rbx+18h], 7
0x1800041e1  jbe     short loc_1800041E8
0x1800041e3  mov     rsi, [rbx]
0x1800041e6  jmp     short loc_1800041EB
0x1800041e8  mov     rsi, rbx
0x1800041eb  mov     [rbx+10h], rdx
0x1800041ef  mov     rcx, rsi; void *
0x1800041f2  lea     rbx, [rdx+rdx]
0x1800041f6  mov     r8, rbx; Size
0x1800041f9  lea     rdx, [rsp+878h+Buffer]; Src
0x1800041fe  call    memmove_0
0x180004203  mov     [rbx+rsi], r13w
0x180004208  jmp     short loc_180004217
0x18000420a  lea     r9, [rsp+878h+Buffer]
0x18000420f  mov     rcx, rbx
0x180004212  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180004217  mov     r9d, 400h; cchBufferMax
0x18000421d  lea     r8, [rsp+878h+Buffer]; lpBuffer
0x180004222  mov     edx, r12d; uID
0x180004225  mov     rcx, r15; hInstance
0x180004228  call    cs:__imp_LoadStringW
0x18000422e  test    eax, eax
0x180004230  jnz     short loc_180004258
0x180004232  call    cs:__imp_GetLastError
0x180004238  test    eax, eax
0x18000423a  jz      short loc_180004248
0x18000423c  jle     short loc_18000424D
0x18000423e  movzx   eax, ax
0x180004241  or      eax, 80070000h
0x180004246  jmp     short loc_18000424D
0x180004248  mov     eax, 80390004h
0x18000424d  mov     r8d, 0D4h
0x180004253  jmp     loc_18000416A
0x180004258  mov     esi, r13d
0x18000425b  lea     rax, [rsp+878h+Buffer]
0x180004260  inc     rdi
0x180004263  cmp     [rax+rdi*2], r13w
0x180004268  jnz     short loc_180004260
0x18000426a  cmp     rdi, [r14+18h]
0x18000426e  ja      short loc_18000429E
0x180004270  cmp     qword ptr [r14+18h], 7
0x180004275  jbe     short loc_18000427C
0x180004277  mov     rbp, [r14]
0x18000427a  jmp     short loc_18000427F
0x18000427c  mov     rbp, r14
0x18000427f  lea     rbx, [rdi+rdi]
0x180004283  mov     [r14+10h], rdi
0x180004287  mov     r8, rbx; Size
0x18000428a  lea     rdx, [rsp+878h+Buffer]; Src
0x18000428f  mov     rcx, rbp; void *
0x180004292  call    memmove_0
0x180004297  mov     [rbx+rbp], r13w
0x18000429c  jmp     short loc_1800042AE
0x18000429e  lea     r9, [rsp+878h+Buffer]
0x1800042a3  mov     rdx, rdi
0x1800042a6  mov     rcx, r14
0x1800042a9  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800042ae  mov     rcx, r15; hLibModule
0x1800042b1  call    cs:__imp_FreeLibrary
0x1800042b7  mov     eax, esi
0x1800042b9  mov     rcx, [rsp+878h+var_58]
0x1800042c1  xor     rcx, rsp; StackCookie
0x1800042c4  call    __security_check_cookie
0x1800042c9  add     rsp, 838h
0x1800042d0  pop     r15
0x1800042d2  pop     r14
0x1800042d4  pop     r13
0x1800042d6  pop     r12
0x1800042d8  pop     rdi
0x1800042d9  pop     rsi
0x1800042da  pop     rbp
0x1800042db  pop     rbx
0x1800042dc  retn
```

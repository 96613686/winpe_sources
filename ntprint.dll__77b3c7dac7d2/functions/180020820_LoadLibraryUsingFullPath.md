# LoadLibraryUsingFullPath

- ea: `0x180020820`
- end: `0x180020991`
- name: `LoadLibraryUsingFullPath`
- size: `369`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000c398`
- `0x18000ea18`
- `0x1800155f4`
- `0x1800252ac`

## callees

- `0x180002300`
- `0x1800026e0`
- `0x180002f48`
- `0x1800078f0`
- `0x180017810`
- `0x1800206ec`
- `0x180020820`
- `0x180034a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020925`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002088f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002088f`

## pseudocode

```c
__int64 __fastcall LoadLibraryUsingFullPath(unsigned __int16 *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  unsigned __int64 v4; // rcx
  __int64 LibraryW; // rbx
  struct SplLogType *v6; // rax
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h]
  int v10; // [rsp+40h] [rbp-C0h]
  DWORD LastError; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+58h] [rbp-A8h]
  _BYTE v14[32]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( !a1 )
    return 0;
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  if ( !(_DWORD)v3 || !GetSystemDirectoryW(Buffer, 0x104u) )
    return 0;
  do
    ++v2;
  while ( Buffer[v2] );
  if ( *(_WORD *)&v14[2 * (int)v2 + 30] != 92 )
  {
    if ( (unsigned __int64)((int)v2 + 1LL) >= 0x104 )
      return 0;
    v4 = (int)v2 + 1LL;
    Buffer[(int)v2] = 92;
    if ( v4 >= 260 )
      _report_rangecheckfailure(v4 * 2);
    Buffer[v4] = 0;
    LODWORD(v2) = v2 + 1;
  }
  if ( (int)v3 + (int)v2 >= 260 )
    return 0;
  StringCchCatW(Buffer, 0x104u, a1);
  LibraryW = IsolationAwareLoadLibraryW(Buffer);
  if ( !LibraryW )
  {
    v8 = 108;
    v9 = 4;
    v10 = 0;
    v12 = 4;
    LastError = GetLastError();
    v13 = 0;
    v6 = SplLogType::SplLogType((SplLogType *)v14, Buffer);
    SplLogEvent2(&LOAD_PLUGIN_FAILED_EVENT, v6, &LastError, &v8, 0);
  }
  return LibraryW;
}

```

## disassembly

```asm
0x180020820  push    rbp
0x180020822  push    rbx
0x180020823  push    rsi
0x180020824  push    rdi
0x180020825  push    r14
0x180020827  push    r15
0x180020829  lea     rbp, [rsp-1A8h]
0x180020831  sub     rsp, 2A8h
0x180020838  mov     rax, cs:__security_cookie
0x18002083f  xor     rax, rsp
0x180020842  mov     [rbp+1D0h+var_40], rax
0x180020849  mov     rsi, rcx
0x18002084c  xor     edx, edx; Val
0x18002084e  lea     rcx, [rbp+1D0h+Buffer]; void *
0x180020852  mov     r8d, 208h; Size
0x180020858  call    memset_0
0x18002085d  xor     r14d, r14d
0x180020860  test    rsi, rsi
0x180020863  jz      loc_180020970
0x180020869  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002086d  mov     rdi, rbx
0x180020870  inc     rdi
0x180020873  cmp     [rsi+rdi*2], r14w
0x180020878  jnz     short loc_180020870
0x18002087a  test    edi, edi
0x18002087c  jz      loc_180020970
0x180020882  mov     r15d, 104h
0x180020888  lea     rcx, [rbp+1D0h+Buffer]; lpBuffer
0x18002088c  mov     edx, r15d; uSize
0x18002088f  call    cs:__imp_GetSystemDirectoryW
0x180020895  test    eax, eax
0x180020897  jz      loc_180020970
0x18002089d  lea     rax, [rbp+1D0h+Buffer]
0x1800208a1  inc     rbx
0x1800208a4  cmp     [rax+rbx*2], r14w
0x1800208a9  jnz     short loc_1800208A1
0x1800208ab  movsxd  rax, ebx
0x1800208ae  mov     edx, 5Ch ; '\'
0x1800208b3  cmp     [rsp+rax*2+2D0h+var_252], dx
0x1800208b8  jz      short loc_1800208E4
0x1800208ba  lea     rcx, [rax+1]
0x1800208be  cmp     rcx, r15
0x1800208c1  jnb     loc_180020970
0x1800208c7  add     rcx, rcx
0x1800208ca  mov     [rbp+rax*2+1D0h+Buffer], dx
0x1800208cf  cmp     rcx, 208h
0x1800208d6  jnb     loc_18002096A
0x1800208dc  mov     [rbp+rcx+1D0h+Buffer], r14w
0x1800208e2  inc     ebx
0x1800208e4  lea     eax, [rdi+rbx]
0x1800208e7  cmp     eax, r15d
0x1800208ea  jge     loc_180020970
0x1800208f0  mov     r8, rsi; unsigned __int16 *
0x1800208f3  lea     rcx, [rbp+1D0h+Buffer]; unsigned __int16 *
0x1800208f7  mov     rdx, r15; unsigned __int64
0x1800208fa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800208ff  lea     rcx, [rbp+1D0h+Buffer]; lpLibFileName
0x180020903  call    IsolationAwareLoadLibraryW
0x180020908  mov     rbx, rax
0x18002090b  test    rax, rax
0x18002090e  jnz     short loc_180020965
0x180020910  lea     edi, [rax+4]
0x180020913  mov     [rsp+2D0h+var_2A0], 6Ch ; 'l'
0x18002091b  mov     [rsp+2D0h+var_298], rdi
0x180020920  mov     [rsp+2D0h+var_290], r14d
0x180020925  call    cs:__imp_GetLastError
0x18002092b  lea     rdx, [rbp+1D0h+Buffer]; unsigned __int16 *
0x18002092f  mov     [rsp+2D0h+var_280], rdi
0x180020934  lea     rcx, [rsp+2D0h+var_270]; this
0x180020939  mov     [rsp+2D0h+var_288], eax
0x18002093d  mov     [rsp+2D0h+var_278], r14d
0x180020942  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180020947  lea     r9, [rsp+2D0h+var_2A0]
0x18002094c  mov     [rsp+2D0h+var_2B0], r14
0x180020951  lea     r8, [rsp+2D0h+var_288]
0x180020956  mov     rdx, rax; struct SplLogType *
0x180020959  lea     rcx, LOAD_PLUGIN_FAILED_EVENT; struct _EVENT_DESCRIPTOR *
0x180020960  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180020965  mov     rax, rbx
0x180020968  jmp     short loc_180020972
0x18002096a  call    __report_rangecheckfailure
0x180020970  xor     eax, eax
0x180020972  mov     rcx, [rbp+1D0h+var_40]
0x180020979  xor     rcx, rsp; StackCookie
0x18002097c  call    __security_check_cookie
0x180020981  add     rsp, 2A8h
0x180020988  pop     r15
0x18002098a  pop     r14
0x18002098c  pop     rdi
0x18002098d  pop     rsi
0x18002098e  pop     rbx
0x18002098f  pop     rbp
0x180020990  retn
```

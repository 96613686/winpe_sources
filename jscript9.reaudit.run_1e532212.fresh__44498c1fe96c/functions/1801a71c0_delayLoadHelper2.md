# __delayLoadHelper2

- ea: `0x1801a71c0`
- end: `0x1801a7355`
- name: `__delayLoadHelper2`
- size: `405`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801cbab6`
- `0x1801cbbfc`
- `0x1801cbfa8`

## callees

- `0x1801a71c0`
- `0x1801a735c`
- `0x1801cc26b`
- `0x180364010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x1801a7293`
- `KERNEL32!LoadLibraryExA` at `0x1801a7293`
- `KERNEL32!FreeLibrary` at `0x1801a72fb`
- `KERNEL32!FreeLibrary` at `0x1801a72fb`
- `KERNEL32!GetProcAddress` at `0x1801a7310`
- `KERNEL32!GetProcAddress` at `0x1801a7310`
- `KERNEL32!DelayLoadFailureHook` at `0x1801a732c`
- `KERNEL32!DelayLoadFailureHook` at `0x1801a721d`
- `KERNEL32!DelayLoadFailureHook` at `0x1801a732c`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(unsigned int *a1, FARPROC *a2)
{
  __int64 v2; // rsi
  __int64 v3; // rbp
  __int64 v5; // r15
  HMODULE v6; // rbx
  FARPROC result; // rax
  const CHAR *v8; // rsi
  __int64 v9; // rdx
  const CHAR *v10; // rdi
  HMODULE Library; // rax
  signed __int64 v12; // rbp
  volatile signed __int64 *v13; // [rsp+40h] [rbp-88h]
  struct DelayLoadInfo v14; // [rsp+50h] [rbp-78h] BYREF

  v2 = a1[1];
  v3 = a1[3];
  v5 = a1[4];
  v13 = (volatile signed __int64 *)(&_ImageBase + a1[2]);
  v6 = (HMODULE)*v13;
  if ( (unsigned __int8)DloadResolve() )
    return (FARPROC)((__int64 (__fastcall *)(bool *, unsigned int *, __int64, __int64 (__fastcall *)(_QWORD, _QWORD), FARPROC *, _DWORD))DloadResolveDelayLoadedAPI)(
                      &_ImageBase,
                      a1,
                      _pfnDefaultDliFailureHook2,
                      DelayLoadFailureHook,
                      a2,
                      0);
  v8 = (const CHAR *)(&_ImageBase + v2);
  v9 = v5 + 8LL * (unsigned int)(((char *)a2 - v3 - (char *)&_ImageBase) >> 3);
  if ( *(__int64 *)(&_ImageBase + v9) < 0 )
    v10 = (const CHAR *)*(unsigned __int16 *)(&_ImageBase + v9);
  else
    v10 = (char *)&word_180000002 + *(unsigned int *)(&_ImageBase + v9);
  if ( !v6 )
  {
    Library = LoadLibraryExA(v8, 0, 0);
    v6 = Library;
    if ( !Library )
      return (FARPROC)DelayLoadFailureHook(v8, v10);
    v12 = _InterlockedCompareExchange64(v13, (signed __int64)Library, 0);
    if ( v12 )
    {
      FreeLibrary(Library);
      v6 = (HMODULE)v12;
    }
    else
    {
      memset_0(&v14, 0, sizeof(v14));
      v14.cb = 72;
      v14.szDll = v8;
      v14.hmodCur = v6;
      if ( _pfnDliNotifyHook2 )
        _pfnDliNotifyHook2(5u, &v14);
    }
  }
  result = GetProcAddress(v6, v10);
  if ( result )
  {
    *a2 = result;
    return result;
  }
  return (FARPROC)DelayLoadFailureHook(v8, v10);
}

```

## disassembly

```asm
0x1801a71c0  mov     rax, rsp
0x1801a71c3  mov     [rax+18h], rbx
0x1801a71c7  mov     [rax+20h], rbp
0x1801a71cb  mov     [rax+10h], rdx
0x1801a71cf  mov     [rax+8], rcx
0x1801a71d3  push    rsi
0x1801a71d4  push    rdi
0x1801a71d5  push    r12
0x1801a71d7  push    r14
0x1801a71d9  push    r15
0x1801a71db  sub     rsp, 0A0h
0x1801a71e2  mov     eax, [rcx+8]
0x1801a71e5  lea     r12, __ImageBase
0x1801a71ec  mov     esi, [rcx+4]
0x1801a71ef  add     rax, r12
0x1801a71f2  mov     ebp, [rcx+0Ch]
0x1801a71f5  mov     rdi, rcx
0x1801a71f8  mov     r15d, [rcx+10h]
0x1801a71fc  mov     [rsp+0C8h+var_88], rax
0x1801a7201  mov     rax, [rsp+0C8h+var_88]
0x1801a7206  mov     rbx, [rax]
0x1801a7209  call    DloadResolve
0x1801a720e  test    al, al
0x1801a7210  jz      short loc_1801A724C
0x1801a7212  mov     rcx, [rsp+0C8h+arg_8]
0x1801a721a  mov     rdx, rdi
0x1801a721d  mov     r9, cs:__imp_DelayLoadFailureHook
0x1801a7224  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1801a722b  mov     rax, cs:DloadResolveDelayLoadedAPI
0x1801a7232  mov     [rsp+0C8h+var_A0], 0
0x1801a723a  mov     [rsp+0C8h+var_A8], rcx
0x1801a723f  mov     rcx, r12
0x1801a7242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a7247  jmp     loc_1801A7338
0x1801a724c  mov     r14, [rsp+0C8h+arg_8]
0x1801a7254  add     rsi, r12
0x1801a7257  mov     rcx, r14
0x1801a725a  sub     rcx, rbp
0x1801a725d  sub     rcx, r12
0x1801a7260  sar     rcx, 3
0x1801a7264  mov     ecx, ecx
0x1801a7266  lea     rdx, [r15+rcx*8]
0x1801a726a  cmp     qword ptr [rdx+r12], 0
0x1801a726f  jl      short loc_1801A7281
0x1801a7271  mov     edi, [rdx+r12]
0x1801a7275  lea     rax, word_180000002
0x1801a727c  add     rdi, rax
0x1801a727f  jmp     short loc_1801A7286
0x1801a7281  movzx   edi, word ptr [rdx+r12]
0x1801a7286  test    rbx, rbx
0x1801a7289  jnz     short loc_1801A730A
0x1801a728b  xor     r8d, r8d; dwFlags
0x1801a728e  xor     edx, edx; hFile
0x1801a7290  mov     rcx, rsi; lpLibFileName
0x1801a7293  call    cs:__imp_LoadLibraryExA
0x1801a729a  nop     dword ptr [rax+rax+00h]
0x1801a729f  mov     rbx, rax
0x1801a72a2  test    rax, rax
0x1801a72a5  jz      short loc_1801A7326
0x1801a72a7  mov     rcx, [rsp+0C8h+var_88]
0x1801a72ac  xor     eax, eax
0x1801a72ae  lock cmpxchg [rcx], rbx
0x1801a72b3  mov     rbp, rax
0x1801a72b6  jnz     short loc_1801A72F8
0x1801a72b8  mov     ebp, 48h ; 'H'
0x1801a72bd  lea     rcx, [rsp+0C8h+var_78]; void *
0x1801a72c2  mov     r8d, ebp; Size
0x1801a72c5  xor     edx, edx; Val
0x1801a72c7  call    memset_0
0x1801a72cc  mov     rax, cs:__pfnDliNotifyHook2
0x1801a72d3  mov     [rsp+0C8h+var_78], ebp
0x1801a72d7  mov     [rsp+0C8h+var_60], rsi
0x1801a72dc  mov     [rsp+0C8h+var_48], rbx
0x1801a72e4  test    rax, rax
0x1801a72e7  jz      short loc_1801A730A
0x1801a72e9  lea     rdx, [rsp+0C8h+var_78]
0x1801a72ee  lea     ecx, [rbp-43h]
0x1801a72f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a72f6  jmp     short loc_1801A730A
0x1801a72f8  mov     rcx, rbx; hLibModule
0x1801a72fb  call    cs:__imp_FreeLibrary
0x1801a7302  nop     dword ptr [rax+rax+00h]
0x1801a7307  mov     rbx, rbp
0x1801a730a  mov     rdx, rdi; lpProcName
0x1801a730d  mov     rcx, rbx; hModule
0x1801a7310  call    cs:__imp_GetProcAddress
0x1801a7317  nop     dword ptr [rax+rax+00h]
0x1801a731c  test    rax, rax
0x1801a731f  jz      short loc_1801A7326
0x1801a7321  mov     [r14], rax
0x1801a7324  jmp     short loc_1801A7338
0x1801a7326  mov     rdx, rdi
0x1801a7329  mov     rcx, rsi
0x1801a732c  call    cs:__imp_DelayLoadFailureHook
0x1801a7333  nop     dword ptr [rax+rax+00h]
0x1801a7338  lea     r11, [rsp+0C8h+var_28]
0x1801a7340  mov     rbx, [r11+40h]
0x1801a7344  mov     rbp, [r11+48h]
0x1801a7348  mov     rsp, r11
0x1801a734b  pop     r15
0x1801a734d  pop     r14
0x1801a734f  pop     r12
0x1801a7351  pop     rdi
0x1801a7352  pop     rsi
0x1801a7353  retn
```

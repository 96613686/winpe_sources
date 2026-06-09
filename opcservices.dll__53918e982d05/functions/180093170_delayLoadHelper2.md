# __delayLoadHelper2

- ea: `0x180093170`
- end: `0x1800932da`
- name: `__delayLoadHelper2`
- size: `362`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800cdd40`
- `0x1800cde3d`
- `0x1800d0d7a`
- `0x1800d0eef`
- `0x1800d0f7a`
- `0x1800d103b`
- `0x1800d11fc`

## callees

- `0x180093170`
- `0x1800932e0`
- `0x1800cde19`
- `0x1800cde25`
- `0x1800d6354`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180093233`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180093233`
- `KERNEL32!DelayLoadFailureHook` at `0x1800932b8`
- `KERNEL32!DelayLoadFailureHook` at `0x1800931c2`
- `KERNEL32!DelayLoadFailureHook` at `0x1800932b8`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(unsigned int *a1, FARPROC *a2)
{
  __int64 v2; // rsi
  __int64 v3; // rbp
  __int64 v5; // r15
  HMODULE v7; // rbx
  FARPROC result; // rax
  const CHAR *v9; // rsi
  __int64 v10; // rdx
  const CHAR *v11; // rdi
  HMODULE Library; // rax
  signed __int64 v13; // rbp
  struct DelayLoadInfo v14; // [rsp+40h] [rbp-78h] BYREF
  volatile signed __int64 *v15; // [rsp+C0h] [rbp+8h]

  v2 = a1[1];
  v3 = a1[3];
  v5 = a1[4];
  v15 = (volatile signed __int64 *)((char *)&_ImageBase + a1[2]);
  v7 = (HMODULE)*v15;
  if ( (unsigned __int8)DloadResolve() )
    return (FARPROC)((__int64 (__fastcall *)(__int16 *, unsigned int *, __int64, __int64 (__fastcall *)(_QWORD, _QWORD), FARPROC *, _DWORD))DloadResolveDelayLoadedAPI)(
                      &_ImageBase,
                      a1,
                      _pfnDefaultDliFailureHook2,
                      DelayLoadFailureHook,
                      a2,
                      0);
  v9 = (char *)&_ImageBase + v2;
  v10 = v5 + 8LL * (unsigned int)(((char *)a2 - v3 - (char *)&_ImageBase) >> 3);
  if ( *(__int64 *)((char *)&_ImageBase + v10) < 0 )
    v11 = (const CHAR *)*(unsigned __int16 *)((char *)&_ImageBase + v10);
  else
    v11 = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v10);
  if ( !v7 )
  {
    Library = LoadLibraryExA(v9, 0, 0);
    v7 = Library;
    if ( !Library )
      return (FARPROC)DelayLoadFailureHook(v9, v11);
    v13 = _InterlockedCompareExchange64(v15, (signed __int64)Library, 0);
    if ( v13 )
    {
      FreeLibrary_0(Library);
      v7 = (HMODULE)v13;
    }
    else
    {
      memset_0(&v14, 0, sizeof(v14));
      v14.cb = 72;
      v14.szDll = v9;
      v14.hmodCur = v7;
      if ( _pfnDliNotifyHook2 )
        _pfnDliNotifyHook2(5u, &v14);
    }
  }
  result = GetProcAddress_0(v7, v11);
  if ( result )
  {
    *a2 = result;
    return result;
  }
  return (FARPROC)DelayLoadFailureHook(v9, v11);
}

```

## disassembly

```asm
0x180093170  mov     [rsp+arg_8], rbx
0x180093175  mov     [rsp+arg_10], rbp
0x18009317a  push    rsi
0x18009317b  push    rdi
0x18009317c  push    r12
0x18009317e  push    r14
0x180093180  push    r15
0x180093182  sub     rsp, 90h
0x180093189  mov     eax, [rcx+8]
0x18009318c  lea     r12, __ImageBase
0x180093193  mov     esi, [rcx+4]
0x180093196  add     rax, r12
0x180093199  mov     ebp, [rcx+0Ch]
0x18009319c  mov     r14, rdx
0x18009319f  mov     r15d, [rcx+10h]
0x1800931a3  mov     rdi, rcx
0x1800931a6  mov     [rsp+0B8h+arg_0], rax
0x1800931ae  mov     rax, [rsp+0B8h+arg_0]
0x1800931b6  mov     rbx, [rax]
0x1800931b9  call    DloadResolve
0x1800931be  test    al, al
0x1800931c0  jz      short loc_1800931F4
0x1800931c2  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800931c9  mov     rdx, rdi
0x1800931cc  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800931d3  mov     rcx, r12
0x1800931d6  mov     rax, cs:DloadResolveDelayLoadedAPI
0x1800931dd  mov     [rsp+0B8h+var_90], 0
0x1800931e5  mov     [rsp+0B8h+var_98], r14
0x1800931ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800931ef  jmp     loc_1800932BE
0x1800931f4  mov     rcx, r14
0x1800931f7  add     rsi, r12
0x1800931fa  sub     rcx, rbp
0x1800931fd  sub     rcx, r12
0x180093200  sar     rcx, 3
0x180093204  mov     ecx, ecx
0x180093206  lea     rdx, [r15+rcx*8]
0x18009320a  cmp     qword ptr [rdx+r12], 0
0x18009320f  jl      short loc_180093221
0x180093211  mov     edi, [rdx+r12]
0x180093215  lea     rax, word_180000002
0x18009321c  add     rdi, rax
0x18009321f  jmp     short loc_180093226
0x180093221  movzx   edi, word ptr [rdx+r12]
0x180093226  test    rbx, rbx
0x180093229  jnz     short loc_18009329D
0x18009322b  xor     r8d, r8d; dwFlags
0x18009322e  xor     edx, edx; hFile
0x180093230  mov     rcx, rsi; lpLibFileName
0x180093233  call    cs:__imp_LoadLibraryExA
0x180093239  mov     rbx, rax
0x18009323c  test    rax, rax
0x18009323f  jz      short loc_1800932B2
0x180093241  mov     rcx, [rsp+0B8h+arg_0]
0x180093249  xor     eax, eax
0x18009324b  lock cmpxchg [rcx], rbx
0x180093250  mov     rbp, rax
0x180093253  jnz     short loc_180093292
0x180093255  mov     ebp, 48h ; 'H'
0x18009325a  lea     rcx, [rsp+0B8h+var_78]; void *
0x18009325f  mov     r8d, ebp; Size
0x180093262  xor     edx, edx; Val
0x180093264  call    memset_0
0x180093269  mov     rax, cs:__pfnDliNotifyHook2
0x180093270  mov     [rsp+0B8h+var_78], ebp
0x180093274  mov     [rsp+0B8h+var_60], rsi
0x180093279  mov     [rsp+0B8h+var_48], rbx
0x18009327e  test    rax, rax
0x180093281  jz      short loc_18009329D
0x180093283  lea     rdx, [rsp+0B8h+var_78]
0x180093288  lea     ecx, [rbp-43h]
0x18009328b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093290  jmp     short loc_18009329D
0x180093292  mov     rcx, rbx; hLibModule
0x180093295  call    FreeLibrary_0
0x18009329a  mov     rbx, rbp
0x18009329d  mov     rdx, rdi; lpProcName
0x1800932a0  mov     rcx, rbx; hModule
0x1800932a3  call    GetProcAddress_0
0x1800932a8  test    rax, rax
0x1800932ab  jz      short loc_1800932B2
0x1800932ad  mov     [r14], rax
0x1800932b0  jmp     short loc_1800932BE
0x1800932b2  mov     rdx, rdi
0x1800932b5  mov     rcx, rsi
0x1800932b8  call    cs:__imp_DelayLoadFailureHook
0x1800932be  lea     r11, [rsp+0B8h+var_28]
0x1800932c6  mov     rbx, [r11+38h]
0x1800932ca  mov     rbp, [r11+40h]
0x1800932ce  mov     rsp, r11
0x1800932d1  pop     r15
0x1800932d3  pop     r14
0x1800932d5  pop     r12
0x1800932d7  pop     rdi
0x1800932d8  pop     rsi
0x1800932d9  retn
```

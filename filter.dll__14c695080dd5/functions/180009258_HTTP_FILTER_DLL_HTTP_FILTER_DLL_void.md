# HTTP_FILTER_DLL::~HTTP_FILTER_DLL(void)

- ea: `0x180009258`
- end: `0x1800092c0`
- name: `??1HTTP_FILTER_DLL@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(HTTP_FILTER_DLL *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006f50`
- `0x1800092c8`

## callees

- `0x180009258`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000929d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000929d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800092b2`

## pseudocode

```c
void __fastcall HTTP_FILTER_DLL::~HTTP_FILTER_DLL(HTTP_FILTER_DLL *this)
{
  char *v1; // rax
  __int64 v2; // rdx
  char **v4; // rcx
  void (__fastcall *v5)(_QWORD); // rax
  HMODULE v6; // rcx

  --HTTP_FILTER_DLL::sm_cLoadedFilters;
  v1 = (char *)this + 8;
  v2 = *((_QWORD *)this + 1);
  if ( *(HTTP_FILTER_DLL **)(v2 + 8) != (HTTP_FILTER_DLL *)((char *)this + 8)
    || (v4 = (char **)*((_QWORD *)this + 2), *v4 != v1) )
  {
    __fastfail(3u);
  }
  *v4 = (char *)v2;
  *(_QWORD *)(v2 + 8) = v4;
  v5 = (void (__fastcall *)(_QWORD))*((_QWORD *)this + 6);
  if ( v5 )
    v5(0);
  v6 = (HMODULE)*((_QWORD *)this + 3);
  if ( v6 )
    FreeLibrary(v6);
  *(_DWORD *)this = 1819042918;
  STRU::~STRU((HTTP_FILTER_DLL *)((char *)this + 72));
}

```

## disassembly

```asm
0x180009258  push    rbx
0x18000925a  sub     rsp, 20h
0x18000925e  dec     cs:?sm_cLoadedFilters@HTTP_FILTER_DLL@@0KA; ulong HTTP_FILTER_DLL::sm_cLoadedFilters
0x180009264  lea     rax, [rcx+8]
0x180009268  mov     rdx, [rax]
0x18000926b  mov     rbx, rcx
0x18000926e  cmp     [rdx+8], rax
0x180009272  jnz     short loc_1800092B9
0x180009274  mov     rcx, [rax+8]
0x180009278  cmp     [rcx], rax
0x18000927b  jnz     short loc_1800092B9
0x18000927d  mov     [rcx], rdx
0x180009280  mov     [rdx+8], rcx
0x180009284  mov     rax, [rbx+30h]
0x180009288  test    rax, rax
0x18000928b  jz      short loc_180009294
0x18000928d  xor     ecx, ecx
0x18000928f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009294  mov     rcx, [rbx+18h]; hLibModule
0x180009298  test    rcx, rcx
0x18000929b  jz      short loc_1800092A3
0x18000929d  call    cs:__imp_FreeLibrary
0x1800092a3  lea     rcx, [rbx+48h]
0x1800092a7  mov     dword ptr [rbx], 6C6C6466h
0x1800092ad  add     rsp, 20h
0x1800092b1  pop     rbx
0x1800092b2  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800092b9  mov     ecx, 3
0x1800092be  int     29h; Win8: RtlFailFast(ecx)
```

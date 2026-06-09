# MIME_MAP::Initialize(INativeConfigurationElement *,int)

- ea: `0x180007524`
- end: `0x180007614`
- name: `?Initialize@MIME_MAP@@QEAAJPEAVINativeConfigurationElement@@H@Z`
- size: `240`
- prototype: `int(MIME_MAP *__hidden this, struct INativeConfigurationElement *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800065f0`

## callees

- `0x180001010`
- `0x180001ff0`
- `0x180002c28`
- `0x180007524`
- `0x180007710`
- `0x180007836`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007582`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007582`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007558`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007558`

## pseudocode

```c
__int64 __fastcall MIME_MAP::Initialize(MIME_MAP *this, struct INativeConfigurationElement *a2, int a3)
{
  struct MIME_MAP_TABLE **v4; // rbx
  bool v6; // zf
  _DWORD *v7; // rax
  struct MIME_MAP_TABLE *v8; // rdi
  int v9; // edi

  *((_DWORD *)this + 2) = a3;
  v4 = (struct MIME_MAP_TABLE **)((char *)this + 16);
  if ( a3 )
  {
    v6 = MIME_MAP_TABLE::sm_pGlobalTable == 0;
    *v4 = 0;
    if ( !v6 )
    {
      AcquireSRWLockShared(&MIME_MAP_TABLE::sm_GlobalLock);
      if ( MIME_MAP_TABLE::sm_pGlobalTable )
      {
        _InterlockedIncrement((volatile signed __int32 *)MIME_MAP_TABLE::sm_pGlobalTable + 266);
        *v4 = MIME_MAP_TABLE::sm_pGlobalTable;
      }
      ReleaseSRWLockShared(&MIME_MAP_TABLE::sm_GlobalLock);
    }
    if ( *v4 )
      return 0;
  }
  v7 = operator new(0x430u);
  v8 = (struct MIME_MAP_TABLE *)v7;
  if ( !v7 )
  {
    v9 = -2147024888;
    goto LABEL_14;
  }
  v7[264] = 0;
  memset_0(v7 + 2, 0, 0x418u);
  *((_DWORD *)v8 + 266) = 1;
  *(_QWORD *)v8 = &MIME_MAP_TABLE::`vftable';
  *v4 = v8;
  v9 = MIME_MAP_TABLE::Initialize(v8, a2);
  if ( v9 >= 0 )
  {
    if ( a3 )
      MIME_MAP_TABLE::SetGlobalTable(v4);
    return 0;
  }
  MIME_MAP_TABLE::Dereference(*v4);
LABEL_14:
  *v4 = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007524  push    rbx
0x180007526  push    rbp
0x180007527  push    rsi
0x180007528  push    rdi
0x180007529  sub     rsp, 28h
0x18000752d  mov     [rcx+8], r8d
0x180007531  mov     esi, r8d
0x180007534  lea     rbx, [rcx+10h]
0x180007538  mov     rbp, rdx
0x18000753b  test    r8d, r8d
0x18000753e  jz      short loc_18000758E
0x180007540  cmp     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180007548  mov     qword ptr [rbx], 0
0x18000754f  jz      short loc_180007588
0x180007551  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180007558  call    cs:__imp_AcquireSRWLockShared
0x18000755e  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180007565  test    rax, rax
0x180007568  jz      short loc_18000757B
0x18000756a  lock inc dword ptr [rax+428h]
0x180007571  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180007578  mov     [rbx], rax
0x18000757b  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180007582  call    cs:__imp_ReleaseSRWLockShared
0x180007588  cmp     qword ptr [rbx], 0
0x18000758c  jnz     short loc_1800075F9
0x18000758e  mov     ecx, 430h; Size
0x180007593  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007598  mov     rdi, rax
0x18000759b  test    rax, rax
0x18000759e  jz      short loc_1800075FD
0x1800075a0  lea     rcx, [rax+8]; void *
0x1800075a4  xor     edx, edx; Val
0x1800075a6  mov     r8d, 418h; Size
0x1800075ac  mov     dword ptr [rcx+418h], 0
0x1800075b6  call    memset_0
0x1800075bb  lea     rax, ??_7MIME_MAP_TABLE@@6B@; const MIME_MAP_TABLE::`vftable'
0x1800075c2  mov     dword ptr [rdi+428h], 1
0x1800075cc  mov     [rdi], rax
0x1800075cf  mov     rdx, rbp; struct INativeConfigurationElement *
0x1800075d2  mov     rcx, rdi; this
0x1800075d5  mov     [rbx], rdi
0x1800075d8  call    ?Initialize@MIME_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@@Z; MIME_MAP_TABLE::Initialize(INativeConfigurationElement *)
0x1800075dd  mov     edi, eax
0x1800075df  test    eax, eax
0x1800075e1  jns     short loc_1800075ED
0x1800075e3  mov     rcx, [rbx]; this
0x1800075e6  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x1800075eb  jmp     short loc_180007602
0x1800075ed  test    esi, esi
0x1800075ef  jz      short loc_1800075F9
0x1800075f1  mov     rcx, rbx; struct MIME_MAP_TABLE **
0x1800075f4  call    ?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z; MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)
0x1800075f9  xor     eax, eax
0x1800075fb  jmp     short loc_18000760B
0x1800075fd  mov     edi, 80070008h
0x180007602  mov     qword ptr [rbx], 0
0x180007609  mov     eax, edi
0x18000760b  add     rsp, 28h
0x18000760f  pop     rdi
0x180007610  pop     rsi
0x180007611  pop     rbp
0x180007612  pop     rbx
0x180007613  retn
```

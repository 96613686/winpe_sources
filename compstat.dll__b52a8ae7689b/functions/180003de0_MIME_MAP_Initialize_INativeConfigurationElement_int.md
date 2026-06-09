# MIME_MAP::Initialize(INativeConfigurationElement *,int)

- ea: `0x180003de0`
- end: `0x180003e89`
- name: `?Initialize@MIME_MAP@@QEAAJPEAVINativeConfigurationElement@@H@Z`
- size: `169`
- prototype: `int(MIME_MAP *__hidden this, struct INativeConfigurationElement *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800033c0`

## callees

- `0x180003900`
- `0x180003de0`
- `0x180004ad0`
- `0x180005460`
- `0x180005f52`
- `0x180008480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007295`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007295`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800072bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800072bf`

## pseudocode

```c
__int64 __fastcall MIME_MAP::Initialize(MIME_MAP *this, struct INativeConfigurationElement *a2, int a3)
{
  struct MIME_MAP_TABLE **v3; // rbx
  bool v6; // zf
  _DWORD *v7; // rax
  struct MIME_MAP_TABLE *v8; // rdi
  int v9; // edi
  __int64 result; // rax

  *((_DWORD *)this + 2) = a3;
  v3 = (struct MIME_MAP_TABLE **)((char *)this + 16);
  if ( a3 )
  {
    v6 = MIME_MAP_TABLE::sm_pGlobalTable == 0;
    *v3 = 0;
    if ( !v6 )
    {
      AcquireSRWLockShared(&MIME_MAP_TABLE::sm_GlobalLock);
      if ( MIME_MAP_TABLE::sm_pGlobalTable )
      {
        _InterlockedIncrement((volatile signed __int32 *)MIME_MAP_TABLE::sm_pGlobalTable + 266);
        *v3 = MIME_MAP_TABLE::sm_pGlobalTable;
      }
      ReleaseSRWLockShared(&MIME_MAP_TABLE::sm_GlobalLock);
    }
    if ( *v3 )
      return 0;
  }
  v7 = operator new(0x430u);
  v8 = (struct MIME_MAP_TABLE *)v7;
  if ( v7 )
  {
    v7[264] = 0;
    memset_0(v7 + 2, 0, 0x418u);
    *((_DWORD *)v8 + 266) = 1;
    *(_QWORD *)v8 = &MIME_MAP_TABLE::`vftable';
    *v3 = v8;
    v9 = MIME_MAP_TABLE::Initialize(v8, a2);
    if ( v9 >= 0 )
    {
      if ( a3 )
        MIME_MAP_TABLE::SetGlobalTable(v3);
      return 0;
    }
    MIME_MAP_TABLE::Dereference(*v3);
    result = (unsigned int)v9;
  }
  else
  {
    result = 2147942408LL;
  }
  *v3 = 0;
  return result;
}

```

## disassembly

```asm
0x180003de0  push    rbx
0x180003de2  push    rbp
0x180003de3  push    rsi
0x180003de4  push    rdi
0x180003de5  push    r14
0x180003de7  sub     rsp, 20h
0x180003deb  xor     r14d, r14d
0x180003dee  mov     [rcx+8], r8d
0x180003df2  lea     rbx, [rcx+10h]
0x180003df6  mov     esi, r8d
0x180003df9  mov     rbp, rdx
0x180003dfc  test    r8d, r8d
0x180003dff  jz      short loc_180003E16
0x180003e01  cmp     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, r14; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180003e08  mov     [rbx], r14
0x180003e0b  jnz     loc_18000728E
0x180003e11  cmp     [rbx], r14
0x180003e14  jnz     short loc_180003E7C
0x180003e16  mov     ecx, 430h; Size
0x180003e1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e20  mov     rdi, rax
0x180003e23  test    rax, rax
0x180003e26  jz      loc_1800072D7
0x180003e2c  lea     rcx, [rax+8]; void *
0x180003e30  xor     edx, edx; Val
0x180003e32  mov     r8d, 418h; Size
0x180003e38  mov     [rcx+418h], r14d
0x180003e3f  call    memset_0
0x180003e44  lea     rax, ??_7MIME_MAP_TABLE@@6B@; const MIME_MAP_TABLE::`vftable'
0x180003e4b  mov     dword ptr [rdi+428h], 1
0x180003e55  mov     [rdi], rax
0x180003e58  mov     rdx, rbp; struct INativeConfigurationElement *
0x180003e5b  mov     rcx, rdi; this
0x180003e5e  mov     [rbx], rdi
0x180003e61  call    ?Initialize@MIME_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@@Z; MIME_MAP_TABLE::Initialize(INativeConfigurationElement *)
0x180003e66  mov     edi, eax
0x180003e68  test    eax, eax
0x180003e6a  js      loc_1800072CB
0x180003e70  test    esi, esi
0x180003e72  jz      short loc_180003E7C
0x180003e74  mov     rcx, rbx; struct MIME_MAP_TABLE **
0x180003e77  call    ?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z; MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)
0x180003e7c  xor     eax, eax
0x180003e7e  add     rsp, 20h
0x180003e82  pop     r14
0x180003e84  pop     rdi
0x180003e85  pop     rsi
0x180003e86  pop     rbp
0x180003e87  pop     rbx
0x180003e88  retn
0x18000728e  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180007295  call    cs:__imp_AcquireSRWLockShared
0x18000729b  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x1800072a2  test    rax, rax
0x1800072a5  jz      short loc_1800072B8
0x1800072a7  lock inc dword ptr [rax+428h]
0x1800072ae  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x1800072b5  mov     [rbx], rax
0x1800072b8  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800072bf  call    cs:__imp_ReleaseSRWLockShared
0x1800072c5  nop
0x1800072c6  jmp     loc_180003E11
0x1800072cb  mov     rcx, [rbx]; this
0x1800072ce  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x1800072d3  mov     eax, edi
0x1800072d5  jmp     short loc_1800072DC
0x1800072d7  mov     eax, 80070008h
0x1800072dc  mov     [rbx], r14
0x1800072df  jmp     loc_180003E7E
```

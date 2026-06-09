# META_SCRIPT_MAP::Initialize(INativeConfigurationElement *,int,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)

- ea: `0x180033a40`
- end: `0x180033b67`
- name: `?Initialize@META_SCRIPT_MAP@@QEAAJPEAVINativeConfigurationElement@@HPEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z`
- size: `295`
- prototype: `int(META_SCRIPT_MAP *__hidden this, struct INativeConfigurationElement *, int, struct IHttpServer *, int, struct LANG_STRING *, const char *, unsigned __int16, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180030010`

## callees

- `0x180019558`
- `0x18001ada4`
- `0x180033a40`
- `0x180033b70`
- `0x1800341d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180033a9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180033a9c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180033a76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180033a76`

## pseudocode

```c
__int64 __fastcall META_SCRIPT_MAP::Initialize(
        META_SCRIPT_MAP *this,
        struct INativeConfigurationElement *a2,
        int a3,
        struct IHttpServer *a4,
        int a5,
        struct LANG_STRING *a6,
        char *a7,
        unsigned __int16 a8,
        struct STRU *a9,
        struct IHttpTraceContext *a10)
{
  struct META_SCRIPT_MAP_TABLE **v11; // rbx
  bool v14; // zf
  struct META_SCRIPT_MAP_TABLE *v15; // rax
  int v16; // edi

  *(_DWORD *)this = a3;
  v11 = (struct META_SCRIPT_MAP_TABLE **)((char *)this + 8);
  if ( a3 )
  {
    v14 = META_SCRIPT_MAP_TABLE::sm_pGlobalTable == 0;
    *v11 = 0;
    if ( !v14 )
    {
      AcquireSRWLockShared(&META_SCRIPT_MAP_TABLE::sm_GlobalLock);
      if ( META_SCRIPT_MAP_TABLE::sm_pGlobalTable )
      {
        _InterlockedIncrement((volatile signed __int32 *)META_SCRIPT_MAP_TABLE::sm_pGlobalTable);
        *v11 = META_SCRIPT_MAP_TABLE::sm_pGlobalTable;
      }
      ReleaseSRWLockShared(&META_SCRIPT_MAP_TABLE::sm_GlobalLock);
    }
    if ( *v11 )
      return 0;
  }
  v15 = (struct META_SCRIPT_MAP_TABLE *)operator new(0x28u);
  if ( !v15 )
  {
    v16 = -2147024888;
    goto LABEL_14;
  }
  *(_DWORD *)v15 = 1;
  *((_QWORD *)v15 + 2) = (char *)v15 + 8;
  *((_QWORD *)v15 + 1) = (char *)v15 + 8;
  *((_QWORD *)v15 + 4) = (char *)v15 + 24;
  *((_QWORD *)v15 + 3) = (char *)v15 + 24;
  *v11 = v15;
  v16 = META_SCRIPT_MAP_TABLE::Initialize(v15, a2, a4, (unsigned int)v15, a6, a7, a8, a9, a10);
  if ( v16 >= 0 )
  {
    if ( a3 )
      META_SCRIPT_MAP_TABLE::SetGlobalTable(v11);
    return 0;
  }
  META_SCRIPT_MAP_TABLE::Dereference(*v11);
LABEL_14:
  *v11 = 0;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180033a40  push    rbx
0x180033a42  push    rbp
0x180033a43  push    rsi
0x180033a44  push    rdi
0x180033a45  sub     rsp, 58h
0x180033a49  mov     [rcx], r8d
0x180033a4c  mov     rdi, r9
0x180033a4f  lea     rbx, [rcx+8]
0x180033a53  mov     esi, r8d
0x180033a56  mov     rbp, rdx
0x180033a59  test    r8d, r8d
0x180033a5c  jz      short loc_180033AAC
0x180033a5e  cmp     cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA, 0; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180033a66  mov     qword ptr [rbx], 0
0x180033a6d  jz      short loc_180033AA2
0x180033a6f  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180033a76  call    cs:__imp_AcquireSRWLockShared
0x180033a7c  mov     rax, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180033a83  test    rax, rax
0x180033a86  jz      short loc_180033A95
0x180033a88  lock inc dword ptr [rax]
0x180033a8b  mov     rax, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180033a92  mov     [rbx], rax
0x180033a95  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180033a9c  call    cs:__imp_ReleaseSRWLockShared
0x180033aa2  cmp     qword ptr [rbx], 0
0x180033aa6  jnz     loc_180033B4C
0x180033aac  mov     ecx, 28h ; '('; Size
0x180033ab1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033ab6  mov     r9, rax; int
0x180033ab9  test    rax, rax
0x180033abc  jz      loc_180033B50
0x180033ac2  mov     dword ptr [rax], 1
0x180033ac8  lea     rcx, [rax+8]
0x180033acc  mov     [rcx+8], rcx
0x180033ad0  mov     r8, rdi; struct IHttpServer *
0x180033ad3  mov     [rcx], rcx
0x180033ad6  mov     rdx, rbp; struct INativeConfigurationElement *
0x180033ad9  lea     rcx, [rax+18h]
0x180033add  mov     [rcx+8], rcx
0x180033ae1  mov     [rcx], rcx
0x180033ae4  mov     rcx, [rsp+78h+arg_48]
0x180033aec  mov     [rsp+78h+var_38], rcx; struct IHttpTraceContext *
0x180033af1  mov     rcx, [rsp+78h+arg_40]
0x180033af9  mov     [rsp+78h+var_40], rcx; struct STRU *
0x180033afe  mov     rcx, r9; this
0x180033b01  mov     [rbx], rax
0x180033b04  movzx   eax, [rsp+78h+arg_38]
0x180033b0c  mov     [rsp+78h+var_48], ax; unsigned __int16
0x180033b11  mov     rax, [rsp+78h+arg_30]
0x180033b19  mov     [rsp+78h+var_50], rax; char *
0x180033b1e  mov     rax, [rsp+78h+arg_28]
0x180033b26  mov     [rsp+78h+var_58], rax; struct LANG_STRING *
0x180033b2b  call    ?Initialize@META_SCRIPT_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@PEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z; META_SCRIPT_MAP_TABLE::Initialize(INativeConfigurationElement *,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)
0x180033b30  mov     edi, eax
0x180033b32  test    eax, eax
0x180033b34  jns     short loc_180033B40
0x180033b36  mov     rcx, [rbx]; this
0x180033b39  call    ?Dereference@META_SCRIPT_MAP_TABLE@@QEAAXXZ; META_SCRIPT_MAP_TABLE::Dereference(void)
0x180033b3e  jmp     short loc_180033B55
0x180033b40  test    esi, esi
0x180033b42  jz      short loc_180033B4C
0x180033b44  mov     rcx, rbx; struct META_SCRIPT_MAP_TABLE **
0x180033b47  call    ?SetGlobalTable@META_SCRIPT_MAP_TABLE@@SAXPEAPEAV1@@Z; META_SCRIPT_MAP_TABLE::SetGlobalTable(META_SCRIPT_MAP_TABLE * *)
0x180033b4c  xor     eax, eax
0x180033b4e  jmp     short loc_180033B5E
0x180033b50  mov     edi, 80070008h
0x180033b55  mov     qword ptr [rbx], 0
0x180033b5c  mov     eax, edi
0x180033b5e  add     rsp, 58h
0x180033b62  pop     rdi
0x180033b63  pop     rsi
0x180033b64  pop     rbp
0x180033b65  pop     rbx
0x180033b66  retn
```

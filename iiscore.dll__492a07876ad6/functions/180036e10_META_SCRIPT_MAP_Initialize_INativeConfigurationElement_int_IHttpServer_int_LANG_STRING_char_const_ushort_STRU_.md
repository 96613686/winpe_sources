# META_SCRIPT_MAP::Initialize(INativeConfigurationElement *,int,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)

- ea: `0x180036e10`
- end: `0x180036f44`
- name: `?Initialize@META_SCRIPT_MAP@@QEAAJPEAVINativeConfigurationElement@@HPEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z`
- size: `308`
- prototype: `int(META_SCRIPT_MAP *__hidden this, struct INativeConfigurationElement *, int, struct IHttpServer *, int, struct LANG_STRING *, const char *, unsigned __int16, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180032c80`

## callees

- `0x18001ab30`
- `0x18001c4b8`
- `0x180036e10`
- `0x180036f4c`
- `0x18003756c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180036e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180036e72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180036e46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180036e46`

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
0x180036e10  push    rbx
0x180036e12  push    rbp
0x180036e13  push    rsi
0x180036e14  push    rdi
0x180036e15  sub     rsp, 58h
0x180036e19  mov     [rcx], r8d
0x180036e1c  mov     rdi, r9
0x180036e1f  lea     rbx, [rcx+8]
0x180036e23  mov     esi, r8d
0x180036e26  mov     rbp, rdx
0x180036e29  test    r8d, r8d
0x180036e2c  jz      short loc_180036E88
0x180036e2e  cmp     cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA, 0; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180036e36  mov     qword ptr [rbx], 0
0x180036e3d  jz      short loc_180036E7E
0x180036e3f  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180036e46  call    cs:__imp_AcquireSRWLockShared
0x180036e4d  nop     dword ptr [rax+rax+00h]
0x180036e52  mov     rax, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180036e59  test    rax, rax
0x180036e5c  jz      short loc_180036E6B
0x180036e5e  lock inc dword ptr [rax]
0x180036e61  mov     rax, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180036e68  mov     [rbx], rax
0x180036e6b  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180036e72  call    cs:__imp_ReleaseSRWLockShared
0x180036e79  nop     dword ptr [rax+rax+00h]
0x180036e7e  cmp     qword ptr [rbx], 0
0x180036e82  jnz     loc_180036F28
0x180036e88  mov     ecx, 28h ; '('; Size
0x180036e8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036e92  mov     r9, rax; int
0x180036e95  test    rax, rax
0x180036e98  jz      loc_180036F2C
0x180036e9e  mov     dword ptr [rax], 1
0x180036ea4  lea     rcx, [rax+8]
0x180036ea8  mov     [rcx+8], rcx
0x180036eac  mov     r8, rdi; struct IHttpServer *
0x180036eaf  mov     [rcx], rcx
0x180036eb2  mov     rdx, rbp; struct INativeConfigurationElement *
0x180036eb5  lea     rcx, [rax+18h]
0x180036eb9  mov     [rcx+8], rcx
0x180036ebd  mov     [rcx], rcx
0x180036ec0  mov     rcx, [rsp+78h+arg_48]
0x180036ec8  mov     [rsp+78h+var_38], rcx; struct IHttpTraceContext *
0x180036ecd  mov     rcx, [rsp+78h+arg_40]
0x180036ed5  mov     [rsp+78h+var_40], rcx; struct STRU *
0x180036eda  mov     rcx, r9; this
0x180036edd  mov     [rbx], rax
0x180036ee0  movzx   eax, [rsp+78h+arg_38]
0x180036ee8  mov     [rsp+78h+var_48], ax; unsigned __int16
0x180036eed  mov     rax, [rsp+78h+arg_30]
0x180036ef5  mov     [rsp+78h+var_50], rax; char *
0x180036efa  mov     rax, [rsp+78h+arg_28]
0x180036f02  mov     [rsp+78h+var_58], rax; struct LANG_STRING *
0x180036f07  call    ?Initialize@META_SCRIPT_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@PEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z; META_SCRIPT_MAP_TABLE::Initialize(INativeConfigurationElement *,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)
0x180036f0c  mov     edi, eax
0x180036f0e  test    eax, eax
0x180036f10  jns     short loc_180036F1C
0x180036f12  mov     rcx, [rbx]; this
0x180036f15  call    ?Dereference@META_SCRIPT_MAP_TABLE@@QEAAXXZ; META_SCRIPT_MAP_TABLE::Dereference(void)
0x180036f1a  jmp     short loc_180036F31
0x180036f1c  test    esi, esi
0x180036f1e  jz      short loc_180036F28
0x180036f20  mov     rcx, rbx; struct META_SCRIPT_MAP_TABLE **
0x180036f23  call    ?SetGlobalTable@META_SCRIPT_MAP_TABLE@@SAXPEAPEAV1@@Z; META_SCRIPT_MAP_TABLE::SetGlobalTable(META_SCRIPT_MAP_TABLE * *)
0x180036f28  xor     eax, eax
0x180036f2a  jmp     short loc_180036F3A
0x180036f2c  mov     edi, 80070008h
0x180036f31  mov     qword ptr [rbx], 0
0x180036f38  mov     eax, edi
0x180036f3a  add     rsp, 58h
0x180036f3e  pop     rdi
0x180036f3f  pop     rsi
0x180036f40  pop     rbp
0x180036f41  pop     rbx
0x180036f42  retn
```

# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180003720`
- end: `0x18000382b`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800028e0`
- `0x180003208`
- `0x180003230`
- `0x180003720`
- `0x180004010`

## import_xrefs

- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x18000378f`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x18000378f`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v4; // rax
  __int64 result; // rax
  TREE_HASH_TABLE *v6; // rax
  TREE_HASH_TABLE *v7; // rbx
  FILE_CACHE *v8; // rcx
  signed int v9; // ebx

  g_pGlobalInfo = a3;
  v4 = operator new(8u);
  if ( !v4 )
    return 2147942408LL;
  *v4 = &CIISGlobalModule::`vftable';
  result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
             a2,
             v4,
             148);
  if ( (int)result < 0 )
    return result;
  v6 = (TREE_HASH_TABLE *)operator new(0x100u);
  v7 = v6;
  if ( !v6 )
  {
    g_pFileCache = 0;
    return 2147942408LL;
  }
  TREE_HASH_TABLE::TREE_HASH_TABLE(v6, 1);
  *((_QWORD *)v7 + 5) = 0x40000;
  *(_QWORD *)v7 = &FILE_CACHE::`vftable';
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 7) = 0;
  *((_QWORD *)v7 + 14) = 0;
  *((_QWORD *)v7 + 15) = 0;
  *((_WORD *)v7 + 32) = 257;
  *((_QWORD *)v7 + 16) = 0;
  *((_QWORD *)v7 + 17) = 0;
  *((_BYTE *)v7 + 66) = 0;
  *((_DWORD *)v7 + 17) = 5000;
  *((_DWORD *)v7 + 36) = 0;
  *((_DWORD *)v7 + 48) = 0;
  g_pFileCache = v7;
  v9 = FILE_CACHE::Initialize(v8);
  if ( v9 >= 0 )
    return 0;
  if ( g_pFileCache )
    FILE_CACHE::`scalar deleting destructor'((FILE_CACHE *)g_pFileCache);
  g_pFileCache = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003720  mov     [rsp+arg_0], rbx
0x180003725  push    rdi
0x180003726  sub     rsp, 20h
0x18000372a  mov     ecx, 8; Size
0x18000372f  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, r8; IHttpServer * g_pGlobalInfo
0x180003736  mov     rbx, rdx
0x180003739  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000373e  xor     edi, edi
0x180003740  mov     rdx, rax
0x180003743  test    rax, rax
0x180003746  jz      loc_18000381B
0x18000374c  lea     rax, ??_7CIISGlobalModule@@6B@; const CIISGlobalModule::`vftable'
0x180003753  mov     r8d, 94h
0x180003759  mov     [rdx], rax
0x18000375c  mov     rcx, [rbx]
0x18000375f  mov     rax, [rcx+18h]
0x180003763  mov     rcx, rbx
0x180003766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000376b  test    eax, eax
0x18000376d  js      loc_180003820
0x180003773  mov     ecx, 100h; Size
0x180003778  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000377d  mov     rbx, rax
0x180003780  test    rax, rax
0x180003783  jz      loc_180003814
0x180003789  lea     edx, [rdi+1]
0x18000378c  mov     rcx, rax
0x18000378f  call    cs:__imp_??0TREE_HASH_TABLE@@QEAA@H@Z; TREE_HASH_TABLE::TREE_HASH_TABLE(int)
0x180003795  lea     rax, ??_7FILE_CACHE@@6B@; const FILE_CACHE::`vftable'
0x18000379c  mov     qword ptr [rbx+28h], 40000h
0x1800037a4  mov     [rbx], rax
0x1800037a7  mov     [rbx+30h], rdi
0x1800037ab  mov     [rbx+38h], rdi
0x1800037af  mov     [rbx+70h], rdi
0x1800037b3  mov     [rbx+78h], rdi
0x1800037b7  mov     word ptr [rbx+40h], 101h
0x1800037bd  mov     [rbx+80h], rdi
0x1800037c4  mov     [rbx+88h], rdi
0x1800037cb  mov     [rbx+42h], dil
0x1800037cf  mov     dword ptr [rbx+44h], 1388h
0x1800037d6  mov     [rbx+90h], edi
0x1800037dc  mov     [rbx+0C0h], edi
0x1800037e2  mov     cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA, rbx; FILE_CACHE * g_pFileCache
0x1800037e9  call    ?Initialize@FILE_CACHE@@QEAAJXZ; FILE_CACHE::Initialize(void)
0x1800037ee  mov     ebx, eax
0x1800037f0  test    eax, eax
0x1800037f2  jns     short loc_180003810
0x1800037f4  mov     rcx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; this
0x1800037fb  test    rcx, rcx
0x1800037fe  jz      short loc_180003805
0x180003800  call    ??_GFILE_CACHE@@QEAAPEAXI@Z; FILE_CACHE::`scalar deleting destructor'(uint)
0x180003805  mov     cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA, rdi; FILE_CACHE * g_pFileCache
0x18000380c  mov     eax, ebx
0x18000380e  jmp     short loc_180003820
0x180003810  xor     eax, eax
0x180003812  jmp     short loc_180003820
0x180003814  mov     cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA, rdi; FILE_CACHE * g_pFileCache
0x18000381b  mov     eax, 80070008h
0x180003820  mov     rbx, [rsp+28h+arg_0]
0x180003825  add     rsp, 20h
0x180003829  pop     rdi
0x18000382a  retn
```

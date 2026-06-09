# ResourceCache::InternalLoadResource(HINSTANCE__ *,uint,ushort const *,void * &)

- ea: `0x18000b838`
- end: `0x18000b954`
- name: `?InternalLoadResource@ResourceCache@@CAJPEAUHINSTANCE__@@IPEBGAEAPEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(HINSTANCE hModule, unsigned int, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005890`

## callees

- `0x18000b838`
- `0x18000b95c`
- `0x18000b980`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000b897`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000b897`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000b8ed`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000b8ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x18000b938`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x18000b938`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18000b85f`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18000b85f`

## pseudocode

```c
__int64 __fastcall ResourceCache::InternalLoadResource(
        HINSTANCE hModule,
        unsigned int a2,
        const unsigned __int16 *a3,
        void **a4)
{
  HRSRC ResourceW; // rax
  unsigned int Error; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  HGLOBAL Resource; // rax
  void *v12; // rdi
  void *v13; // rax

  *a4 = 0;
  ResourceW = FindResourceW(hModule, (LPCWSTR)(unsigned __int16)a2, (LPCWSTR)5);
  if ( ResourceW )
  {
    Resource = LoadResource(hModule, ResourceW);
    v12 = Resource;
    if ( Resource )
    {
      v13 = LockResource(Resource);
      *a4 = v13;
      if ( v13 )
      {
        return 0;
      }
      else
      {
        Error = -2147418113;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          WPP_SF_dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            25,
            WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids,
            a2,
            -2147418113);
        FreeResource(v12);
      }
    }
    else
    {
      Error = ResourceCache::LastError();
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v10 = 24;
        goto LABEL_9;
      }
    }
  }
  else
  {
    Error = ResourceCache::LastError();
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v10 = 23;
LABEL_9:
      WPP_SF_dd(*(_QWORD *)(v9 + 16), v10, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids, a2, Error);
    }
  }
  return Error;
}

```

## disassembly

```asm
0x18000b838  mov     [rsp+arg_0], rbx
0x18000b83d  mov     [rsp+arg_8], rsi
0x18000b842  push    rdi
0x18000b843  sub     rsp, 30h
0x18000b847  mov     esi, edx
0x18000b849  mov     r8d, 5; lpType
0x18000b84f  movzx   edx, dx; lpName
0x18000b852  mov     rbx, r9
0x18000b855  mov     rdi, rcx
0x18000b858  mov     qword ptr [r9], 0
0x18000b85f  call    cs:__imp_FindResourceW
0x18000b865  test    rax, rax
0x18000b868  jnz     short loc_18000B891
0x18000b86a  xor     edi, edi
0x18000b86c  call    ?LastError@ResourceCache@@CAJXZ; ResourceCache::LastError(void)
0x18000b871  mov     ebx, eax
0x18000b873  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b87a  lea     rax, WPP_GLOBAL_Control
0x18000b881  cmp     rcx, rax
0x18000b884  jz      short loc_18000B8DF
0x18000b886  cmp     byte ptr [rcx+19h], 2
0x18000b88a  jb      short loc_18000B8DF
0x18000b88c  lea     edx, [rdi+17h]
0x18000b88f  jmp     short loc_18000B8C8
0x18000b891  mov     rdx, rax; hResInfo
0x18000b894  mov     rcx, rdi; hModule
0x18000b897  call    cs:__imp_LoadResource
0x18000b89d  mov     rdi, rax
0x18000b8a0  test    rax, rax
0x18000b8a3  jnz     short loc_18000B8EA
0x18000b8a5  call    ?LastError@ResourceCache@@CAJXZ; ResourceCache::LastError(void)
0x18000b8aa  mov     ebx, eax
0x18000b8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8b3  lea     rax, WPP_GLOBAL_Control
0x18000b8ba  cmp     rcx, rax
0x18000b8bd  jz      short loc_18000B8DF
0x18000b8bf  cmp     byte ptr [rcx+19h], 2
0x18000b8c3  jb      short loc_18000B8DF
0x18000b8c5  lea     edx, [rdi+18h]
0x18000b8c8  mov     rcx, [rcx+10h]
0x18000b8cc  lea     r8, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids
0x18000b8d3  mov     r9d, esi
0x18000b8d6  mov     [rsp+38h+var_18], ebx
0x18000b8da  call    WPP_SF_dd
0x18000b8df  test    ebx, ebx
0x18000b8e1  jns     short loc_18000B942
0x18000b8e3  test    rdi, rdi
0x18000b8e6  jz      short loc_18000B942
0x18000b8e8  jmp     short loc_18000B935
0x18000b8ea  mov     rcx, rax; hResData
0x18000b8ed  call    cs:__imp_LockResource
0x18000b8f3  mov     [rbx], rax
0x18000b8f6  test    rax, rax
0x18000b8f9  jnz     short loc_18000B940
0x18000b8fb  mov     ebx, 8000FFFFh
0x18000b900  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b907  lea     rax, WPP_GLOBAL_Control
0x18000b90e  cmp     rcx, rax
0x18000b911  jz      short loc_18000B935
0x18000b913  cmp     byte ptr [rcx+19h], 2
0x18000b917  jb      short loc_18000B935
0x18000b919  mov     rcx, [rcx+10h]
0x18000b91d  lea     r8, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids
0x18000b924  mov     edx, 19h
0x18000b929  mov     [rsp+38h+var_18], ebx
0x18000b92d  mov     r9d, esi
0x18000b930  call    WPP_SF_dd
0x18000b935  mov     rcx, rdi; hResData
0x18000b938  call    cs:__imp_FreeResource
0x18000b93e  jmp     short loc_18000B942
0x18000b940  xor     ebx, ebx
0x18000b942  mov     rsi, [rsp+38h+arg_8]
0x18000b947  mov     eax, ebx
0x18000b949  mov     rbx, [rsp+38h+arg_0]
0x18000b94e  add     rsp, 30h
0x18000b952  pop     rdi
0x18000b953  retn
```

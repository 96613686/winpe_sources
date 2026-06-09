# UnloadPlugin(_ApPluginPkg *)

- ea: `0x18004cfe0`
- end: `0x18004d116`
- name: `?UnloadPlugin@@YAXPEAU_ApPluginPkg@@@Z`
- size: `310`
- prototype: `void __fastcall(struct _ApPluginPkg *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18004cf6c`

## callees

- `0x18004cf60`
- `0x18004cfe0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004d0bb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004d0bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d0e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d0e9`
- `ntdll!RtlDeleteResource` at `0x18004d043`
- `ntdll!RtlDeleteResource` at `0x18004d043`

## pseudocode

```c
void __fastcall UnloadPlugin(struct _ApPluginPkg *a1)
{
  void (*v2)(void); // rax
  struct _RTL_RESOURCE *v3; // rcx
  struct _RTL_BALANCED_NODE *v4; // rcx
  struct _RTL_BALANCED_NODE **v5; // rax
  ULONG_PTR ParentValue; // rdi
  unsigned __int64 v7; // rdi
  HKEY v8; // rcx

  if ( a1 )
  {
    if ( *((_QWORD *)a1 + 2) && g_pLsaIdProvHostFunctionTable )
      (*((void (**)(void))g_pLsaIdProvHostFunctionTable + 1))();
    if ( *((_QWORD *)a1 + 1) )
    {
      v2 = (void (*)(void))*((_QWORD *)a1 + 22);
      if ( v2 )
        v2();
    }
    v3 = (struct _RTL_RESOURCE *)*((_QWORD *)a1 + 45);
    if ( v3 )
    {
      if ( *((_DWORD *)a1 + 92) )
        RtlDeleteResource(v3);
      ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)a1 + 45));
    }
    v4 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)a1 + 47);
    if ( v4 )
    {
      while ( !v4->Children[0] )
      {
        v5 = &v4->Children[1];
        if ( v4->Children[1] )
        {
          v4 = *v5;
LABEL_17:
          *v5 = 0;
        }
        else
        {
          ParentValue = v4->ParentValue;
          SubPkgTable_FreeRoutine(v4, 0);
          v7 = ParentValue & 0xFFFFFFFFFFFFFFFCuLL;
          if ( !v7 )
            goto LABEL_20;
          v4 = (struct _RTL_BALANCED_NODE *)v7;
        }
      }
      v5 = (struct _RTL_BALANCED_NODE **)v4;
      v4 = v4->Children[0];
      goto LABEL_17;
    }
LABEL_20:
    *((_QWORD *)a1 + 47) = 0;
    if ( *(_QWORD *)a1 )
      FreeLibrary(*(HMODULE *)a1);
    if ( *((_QWORD *)a1 + 43) )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    v8 = (HKEY)*((_QWORD *)a1 + 44);
    if ( v8 )
      RegCloseKey(v8);
    if ( *((_QWORD *)a1 + 19) )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
}

```

## disassembly

```asm
0x18004cfe0  test    rcx, rcx
0x18004cfe3  jz      locret_18004D115
0x18004cfe9  mov     [rsp+arg_0], rbx
0x18004cfee  push    rdi
0x18004cfef  sub     rsp, 20h
0x18004cff3  mov     rbx, rcx
0x18004cff6  mov     rcx, [rcx+10h]
0x18004cffa  test    rcx, rcx
0x18004cffd  jz      short loc_18004D014
0x18004cfff  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18004d006  test    rax, rax
0x18004d009  jz      short loc_18004D014
0x18004d00b  mov     rax, [rax+8]
0x18004d00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d014  mov     rcx, [rbx+8]
0x18004d018  test    rcx, rcx
0x18004d01b  jz      short loc_18004D02E
0x18004d01d  mov     rax, [rbx+0B0h]
0x18004d024  test    rax, rax
0x18004d027  jz      short loc_18004D02E
0x18004d029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d02e  mov     rcx, [rbx+168h]; Resource
0x18004d035  test    rcx, rcx
0x18004d038  jz      short loc_18004D060
0x18004d03a  cmp     dword ptr [rbx+170h], 0
0x18004d041  jz      short loc_18004D049
0x18004d043  call    cs:__imp_RtlDeleteResource
0x18004d049  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004d050  mov     rcx, [rbx+168h]
0x18004d057  mov     rax, [rax+30h]
0x18004d05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d060  mov     rcx, [rbx+178h]; struct _RTL_BALANCED_NODE *
0x18004d067  test    rcx, rcx
0x18004d06a  jz      short loc_18004D0A8
0x18004d06c  mov     rdx, [rcx]
0x18004d06f  test    rdx, rdx
0x18004d072  jz      short loc_18004D07C
0x18004d074  mov     rax, rcx
0x18004d077  mov     rcx, rdx
0x18004d07a  jmp     short loc_18004D089
0x18004d07c  lea     rax, [rcx+8]
0x18004d080  cmp     qword ptr [rax], 0
0x18004d084  jz      short loc_18004D092
0x18004d086  mov     rcx, [rax]
0x18004d089  mov     qword ptr [rax], 0
0x18004d090  jmp     short loc_18004D06C
0x18004d092  mov     rdi, [rcx+10h]
0x18004d096  xor     edx, edx; void *
0x18004d098  call    ?SubPkgTable_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; SubPkgTable_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18004d09d  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18004d0a1  jz      short loc_18004D0A8
0x18004d0a3  mov     rcx, rdi
0x18004d0a6  jmp     short loc_18004D06C
0x18004d0a8  mov     qword ptr [rbx+178h], 0
0x18004d0b3  mov     rcx, [rbx]; hLibModule
0x18004d0b6  test    rcx, rcx
0x18004d0b9  jz      short loc_18004D0C1
0x18004d0bb  call    cs:__imp_FreeLibrary
0x18004d0c1  mov     rcx, [rbx+158h]
0x18004d0c8  test    rcx, rcx
0x18004d0cb  jz      short loc_18004D0DD
0x18004d0cd  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004d0d4  mov     rax, [rax+30h]
0x18004d0d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0dd  mov     rcx, [rbx+160h]; hKey
0x18004d0e4  test    rcx, rcx
0x18004d0e7  jz      short loc_18004D0EF
0x18004d0e9  call    cs:__imp_RegCloseKey
0x18004d0ef  mov     rcx, [rbx+98h]
0x18004d0f6  test    rcx, rcx
0x18004d0f9  jz      short loc_18004D10B
0x18004d0fb  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004d102  mov     rax, [rax+30h]
0x18004d106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d10b  mov     rbx, [rsp+28h+arg_0]
0x18004d110  add     rsp, 20h
0x18004d114  pop     rdi
0x18004d115  retn
```

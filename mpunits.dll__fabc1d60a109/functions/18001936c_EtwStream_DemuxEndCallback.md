# EtwStream_DemuxEndCallback

- ea: `0x18001936c`
- end: `0x18001941a`
- name: `EtwStream_DemuxEndCallback`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180019420`

## callees

- `0x180006ef8`
- `0x18001936c`
- `0x180042c5c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001939a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001939a`

## string_xrefs

- `0x180019393`: `mpunits.dll`

## pseudocode

```c
const MI_InstanceFT *__fastcall EtwStream_DemuxEndCallback(__int64 a1)
{
  __int64 v1; // rbx
  GUID *v2; // rcx
  HMODULE ModuleHandleA; // rax
  int String_LoadString; // eax
  const MI_InstanceFT *result; // rax
  MI_Instance *extendedError; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  v2 = *(GUID **)(a1 + 112);
  extendedError = 0;
  ExecutionContext_SetContext(v2);
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  String_LoadString = Intlstr_GetString_LoadString(ModuleHandleA, 2035);
  CreateOMIError_shared(String_LoadString, 10, (int)L"ETW Normalizer", 14, (__int64)&OMI_Error_rtti, &extendedError);
  result = (const MI_InstanceFT *)((__int64 (__fastcall *)(__int64, __int64, MI_Instance *))ObserverProtocol_PostErrorAndDispose)(
                                    v1,
                                    1,
                                    extendedError);
  if ( extendedError )
  {
    result = extendedError->ft;
    if ( extendedError->ft )
      return (const MI_InstanceFT *)((__int64 (*)(void))result->Delete)();
  }
  return result;
}

```

## disassembly

```asm
0x18001936c  push    rbx
0x18001936e  sub     rsp, 30h
0x180019372  mov     rax, cs:off_180047C30
0x180019379  mov     rbx, [rcx+40h]
0x18001937d  mov     rcx, [rcx+70h]
0x180019381  mov     [rsp+38h+arg_0], 0
0x18001938a  mov     rax, [rax+10h]
0x18001938e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019393  lea     rcx, ModuleName; "mpunits.dll"
0x18001939a  call    cs:__imp_GetModuleHandleA
0x1800193a0  mov     rcx, rax
0x1800193a3  mov     edx, 7F3h
0x1800193a8  call    _Intlstr_GetString_LoadString
0x1800193ad  lea     rcx, [rsp+38h+arg_0]
0x1800193b2  mov     r9d, 0Eh; int
0x1800193b8  mov     [rsp+38h+extendedError], rcx; extendedError
0x1800193bd  lea     r8, aEtwNormalizer; "ETW Normalizer"
0x1800193c4  lea     rcx, OMI_Error_rtti
0x1800193cb  mov     [rsp+38h+var_18], rcx; __int64
0x1800193d0  mov     rcx, rax; int
0x1800193d3  lea     edx, [r9-4]; int
0x1800193d7  call    CreateOMIError_shared
0x1800193dc  mov     rax, cs:off_180047BB0
0x1800193e3  mov     edx, 1
0x1800193e8  mov     r8, [rsp+38h+arg_0]
0x1800193ed  mov     rcx, rbx
0x1800193f0  mov     rax, [rax+60h]
0x1800193f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193f9  mov     rcx, [rsp+38h+arg_0]
0x1800193fe  test    rcx, rcx
0x180019401  jz      short loc_180019414
0x180019403  mov     rax, [rcx]
0x180019406  test    rax, rax
0x180019409  jz      short loc_180019414
0x18001940b  mov     rax, [rax+10h]
0x18001940f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019414  add     rsp, 30h
0x180019418  pop     rbx
0x180019419  retn
```

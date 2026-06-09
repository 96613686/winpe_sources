# UnravelIntoContinuationObserver_OnNext

- ea: `0x1800386f0`
- end: `0x1800387d7`
- name: `UnravelIntoContinuationObserver_OnNext`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180006ef8`
- `0x1800084f0`
- `0x1800386f0`
- `0x180042c5c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180038753`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180038753`

## string_xrefs

- `0x180038743`: `mpunits.dll`

## pseudocode

```c
const MI_InstanceFT *__fastcall UnravelIntoContinuationObserver_OnNext(__int64 a1, __int64 a2)
{
  const MI_InstanceFT *result; // rax
  HMODULE ModuleHandleA; // rax
  int String_LoadString; // eax
  MI_Instance *extendedError; // [rsp+40h] [rbp+8h] BYREF

  if ( ++*(_DWORD *)(a1 + 320) == 1 )
  {
    result = (const MI_InstanceFT *)Item_Clone(a2, a1 + 264);
    if ( (_DWORD)result )
      return (const MI_InstanceFT *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ObserverProtocol_PostErrorAndDispose)(
                                      *(_QWORD *)(a1 + 152),
                                      (unsigned int)result,
                                      0);
  }
  else
  {
    extendedError = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    String_LoadString = Intlstr_GetString_LoadString(ModuleHandleA, 2067);
    CreateOMIError_shared(String_LoadString, 7, (int)L"MI", 11, (__int64)&OMI_Error_rtti, &extendedError);
    result = (const MI_InstanceFT *)((__int64 (__fastcall *)(_QWORD, __int64, MI_Instance *))ObserverProtocol_PostErrorAndDispose)(
                                      *(_QWORD *)(a1 + 152),
                                      7,
                                      extendedError);
    if ( extendedError )
    {
      result = extendedError->ft;
      if ( extendedError->ft )
        return (const MI_InstanceFT *)((__int64 (*)(void))result->Delete)();
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800386f0  push    rbx
0x1800386f2  sub     rsp, 30h
0x1800386f6  inc     dword ptr [rcx+140h]
0x1800386fc  mov     rax, rdx
0x1800386ff  cmp     dword ptr [rcx+140h], 1
0x180038706  mov     rbx, rcx
0x180038709  jnz     short loc_180038743
0x18003870b  lea     rdx, [rcx+108h]
0x180038712  mov     rcx, rax
0x180038715  call    Item_Clone
0x18003871a  mov     edx, eax
0x18003871c  test    eax, eax
0x18003871e  jz      loc_1800387D1
0x180038724  mov     rcx, cs:off_180047BB0
0x18003872b  xor     r8d, r8d
0x18003872e  mov     rax, [rcx+60h]
0x180038732  mov     rcx, [rbx+98h]
0x180038739  add     rsp, 30h
0x18003873d  pop     rbx
0x18003873e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180038743  lea     rcx, ModuleName; "mpunits.dll"
0x18003874a  mov     [rsp+38h+arg_0], 0
0x180038753  call    cs:__imp_GetModuleHandleA
0x180038759  mov     rcx, rax
0x18003875c  mov     edx, 813h
0x180038761  call    _Intlstr_GetString_LoadString
0x180038766  lea     rcx, [rsp+38h+arg_0]
0x18003876b  mov     r9d, 0Bh; int
0x180038771  mov     [rsp+38h+extendedError], rcx; extendedError
0x180038776  lea     r8, aMi; "MI"
0x18003877d  lea     rcx, OMI_Error_rtti
0x180038784  mov     [rsp+38h+var_18], rcx; __int64
0x180038789  mov     rcx, rax; int
0x18003878c  lea     edx, [r9-4]; int
0x180038790  call    CreateOMIError_shared
0x180038795  mov     rax, cs:off_180047BB0
0x18003879c  mov     edx, 7
0x1800387a1  mov     r8, [rsp+38h+arg_0]
0x1800387a6  mov     rcx, [rbx+98h]
0x1800387ad  mov     rax, [rax+60h]
0x1800387b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387b6  mov     rcx, [rsp+38h+arg_0]
0x1800387bb  test    rcx, rcx
0x1800387be  jz      short loc_1800387D1
0x1800387c0  mov     rax, [rcx]
0x1800387c3  test    rax, rax
0x1800387c6  jz      short loc_1800387D1
0x1800387c8  mov     rax, [rax+10h]
0x1800387cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387d1  add     rsp, 30h
0x1800387d5  pop     rbx
0x1800387d6  retn
```

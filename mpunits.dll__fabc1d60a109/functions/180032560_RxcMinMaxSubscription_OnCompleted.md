# RxcMinMaxSubscription_OnCompleted

- ea: `0x180032560`
- end: `0x18003264e`
- name: `RxcMinMaxSubscription_OnCompleted`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180006ef8`
- `0x180032560`
- `0x180042c5c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003258d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003259a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003258d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003259a`

## string_xrefs

- `0x18003257b`: `mpunits.dll`

## pseudocode

```c
const MI_InstanceFT *__fastcall RxcMinMaxSubscription_OnCompleted(_QWORD *a1)
{
  bool v2; // zf
  HMODULE ModuleHandleA; // rax
  __int64 v4; // rdx
  int String_LoadString; // eax
  unsigned int v6; // eax
  __int64 v7; // rdx
  const MI_InstanceFT *result; // rax
  __int64 (*Delete)(void); // rax
  MI_Instance *extendedError; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_DWORD *)a1 + 2) )
  {
    ((void (__fastcall *)(_QWORD, _QWORD *))ObserverProtocol_PostNext)(*a1, a1 + 2);
    Delete = ObserverProtocol_PostCompletedAndDispose;
    return (const MI_InstanceFT *)Delete();
  }
  v2 = *((_DWORD *)a1 + 22) == 0;
  extendedError = 0;
  if ( v2 )
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v4 = 2096;
  }
  else
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v4 = 2097;
  }
  String_LoadString = Intlstr_GetString_LoadString(ModuleHandleA, v4);
  v6 = CreateOMIError_shared(String_LoadString, 4, (int)L"MI", 5, (__int64)&OMI_Error_rtti, &extendedError);
  v7 = v6;
  if ( !v6 )
    v7 = 4;
  result = (const MI_InstanceFT *)((__int64 (__fastcall *)(_QWORD, __int64, MI_Instance *))ObserverProtocol_PostErrorAndDispose)(
                                    *a1,
                                    v7,
                                    extendedError);
  if ( extendedError )
  {
    result = extendedError->ft;
    if ( extendedError->ft )
    {
      Delete = (__int64 (*)(void))result->Delete;
      return (const MI_InstanceFT *)Delete();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180032560  mov     [rsp+arg_8], rbx
0x180032565  push    rdi
0x180032566  sub     rsp, 30h
0x18003256a  cmp     dword ptr [rcx+8], 0
0x18003256e  mov     rbx, rcx
0x180032571  jz      loc_180032619
0x180032577  cmp     dword ptr [rcx+58h], 0
0x18003257b  lea     rcx, ModuleName; "mpunits.dll"
0x180032582  mov     [rsp+38h+arg_0], 0
0x18003258b  jz      short loc_18003259A
0x18003258d  call    cs:__imp_GetModuleHandleA
0x180032593  mov     edx, 831h
0x180032598  jmp     short loc_1800325A5
0x18003259a  call    cs:__imp_GetModuleHandleA
0x1800325a0  mov     edx, 830h
0x1800325a5  mov     rcx, rax
0x1800325a8  mov     edi, 5
0x1800325ad  call    _Intlstr_GetString_LoadString
0x1800325b2  mov     rcx, rax; int
0x1800325b5  lea     r8, aMi; "MI"
0x1800325bc  lea     rax, [rsp+38h+arg_0]
0x1800325c1  movzx   r9d, di; int
0x1800325c5  mov     [rsp+38h+extendedError], rax; extendedError
0x1800325ca  mov     edi, 4
0x1800325cf  lea     rax, OMI_Error_rtti
0x1800325d6  mov     edx, edi; int
0x1800325d8  mov     [rsp+38h+var_18], rax; __int64
0x1800325dd  call    CreateOMIError_shared
0x1800325e2  mov     r8, [rsp+38h+arg_0]
0x1800325e7  mov     edx, eax
0x1800325e9  mov     rcx, [rbx]
0x1800325ec  test    eax, eax
0x1800325ee  mov     rax, cs:off_180047BB0
0x1800325f5  cmovz   edx, edi
0x1800325f8  mov     rax, [rax+60h]
0x1800325fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032601  mov     rcx, [rsp+38h+arg_0]
0x180032606  test    rcx, rcx
0x180032609  jz      short loc_180032643
0x18003260b  mov     rax, [rcx]
0x18003260e  test    rax, rax
0x180032611  jz      short loc_180032643
0x180032613  mov     rax, [rax+10h]
0x180032617  jmp     short loc_18003263E
0x180032619  mov     rax, cs:off_180047BB0
0x180032620  lea     rdx, [rcx+10h]
0x180032624  mov     rcx, [rcx]
0x180032627  mov     rax, [rax+20h]
0x18003262b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032630  mov     rax, cs:off_180047BB0
0x180032637  mov     rcx, [rbx]
0x18003263a  mov     rax, [rax+40h]
0x18003263e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032643  mov     rbx, [rsp+38h+arg_8]
0x180032648  add     rsp, 30h
0x18003264c  pop     rdi
0x18003264d  retn
```

# _lambda_8a03d23fdee2c1785e106aafab25a0f7_::_lambda_invoker_cdecl_

- ea: `0x180034840`
- end: `0x180034896`
- name: `_lambda_8a03d23fdee2c1785e106aafab25a0f7_::_lambda_invoker_cdecl_`
- size: `86`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180034840`
- `0x180039010`

## import_xrefs

- `ntdll!LdrAddRefDll` at `0x180034859`
- `ntdll!LdrAddRefDll` at `0x180034859`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180034873`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180034873`

## pseudocode

```c
void __fastcall lambda_8a03d23fdee2c1785e106aafab25a0f7_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        void (__fastcall **Context)(_QWORD),
        PTP_WORK Work)
{
  if ( LdrAddRefDll(0, &_ImageBase) >= 0 )
    FreeLibraryWhenCallbackReturns(Instance, &_ImageBase);
  Context[1](Context[2]);
}

```

## disassembly

```asm
0x180034840  mov     [rsp+arg_0], rbx
0x180034845  push    rdi
0x180034846  sub     rsp, 20h
0x18003484a  mov     rbx, rdx
0x18003484d  mov     rdi, rcx
0x180034850  lea     rdx, __ImageBase; BaseAddress
0x180034857  xor     ecx, ecx; Flags
0x180034859  call    cs:__imp_LdrAddRefDll
0x180034860  nop     dword ptr [rax+rax+00h]
0x180034865  test    eax, eax
0x180034867  js      short loc_18003487F
0x180034869  lea     rdx, __ImageBase; mod
0x180034870  mov     rcx, rdi; pci
0x180034873  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x18003487a  nop     dword ptr [rax+rax+00h]
0x18003487f  mov     rcx, [rbx+10h]
0x180034883  mov     rax, [rbx+8]
0x180034887  mov     rbx, [rsp+28h+arg_0]
0x18003488c  add     rsp, 20h
0x180034890  pop     rdi
0x180034891  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

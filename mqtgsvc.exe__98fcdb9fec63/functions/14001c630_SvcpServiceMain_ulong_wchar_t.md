# SvcpServiceMain(ulong,wchar_t * *)

- ea: `0x14001c630`
- end: `0x14001c662`
- name: `?SvcpServiceMain@@YAXKPEAPEA_W@Z`
- size: `50`
- prototype: `void __fastcall(__int64, const wchar_t **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x14000d75c`
- `0x14001c630`
- `0x14001c668`

## import_xrefs

- `KERNEL32!HeapSetInformation` at `0x14001c645`
- `KERNEL32!HeapSetInformation` at `0x14001c645`

## pseudocode

```c
void __fastcall SvcpServiceMain(__int64 a1, const wchar_t **a2)
{
  void (*v3)(unsigned int); // rcx

  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  try
  {
    SvcpRegisterServiceCtrlHandler(v3);
    AppRun(*a2);
  }
  catch ( exception )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e256a6a9c48f38ddd38dc91143465c3b_Traceguids);
  }
}

```

## disassembly

```asm
0x14001c630  push    rbx
0x14001c632  sub     rsp, 20h
0x14001c636  mov     rbx, rdx
0x14001c639  xor     r9d, r9d; HeapInformationLength
0x14001c63c  xor     r8d, r8d; HeapInformation
0x14001c63f  lea     edx, [r9+1]; HeapInformationClass
0x14001c643  xor     ecx, ecx; HeapHandle
0x14001c645  call    cs:__imp_HeapSetInformation
0x14001c64b  nop
0x14001c64c  call    ?SvcpRegisterServiceCtrlHandler@@YAXP6AXK@Z@Z; SvcpRegisterServiceCtrlHandler(void (*)(ulong))
0x14001c651  mov     rcx, [rbx]; wchar_t *
0x14001c654  call    ?AppRun@@YAXPEB_W@Z; AppRun(wchar_t const *)
0x14001c659  nop
0x14001c65a  jmp     short $+2
0x14001c65c  add     rsp, 20h
0x14001c660  pop     rbx
0x14001c661  retn
```

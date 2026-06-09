# JsUtil::BackgroundJobProcessor::StaticThreadProc(void *)

- ea: `0x180340d60`
- end: `0x180340deb`
- name: `?StaticThreadProc@BackgroundJobProcessor@JsUtil@@CAIPEAX@Z`
- size: `139`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18010fd20`
- `0x1801b0d28`
- `0x180340d60`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x180340dd7`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180340dd7`
- `KERNEL32!SetEvent` at `0x180340dac`
- `KERNEL32!SetEvent` at `0x180340dc5`
- `KERNEL32!SetEvent` at `0x180340dac`
- `KERNEL32!SetEvent` at `0x180340dc5`
- `KERNEL32!GetModuleHandleExW` at `0x180340d85`
- `KERNEL32!GetModuleHandleExW` at `0x180340d85`

## pseudocode

```c
__int64 __fastcall JsUtil::BackgroundJobProcessor::StaticThreadProc(HANDLE *a1)
{
  HMODULE hLibModule[4]; // [rsp+28h] [rbp-20h] BYREF

  hLibModule[0] = 0;
  if ( !GetModuleHandleExW(0, &AutoSystemInfo::binaryName, hLibModule) )
    hLibModule[0] = 0;
  hLibModule[1] = (HMODULE)(a1 + 38);
  SetEvent(a1[38]);
  JsUtil::BackgroundJobProcessor::Run((JsUtil::BackgroundJobProcessor *)a1);
  SetEvent(a1[38]);
  if ( hLibModule[0] )
    FreeLibraryAndExitThread(hLibModule[0], 0);
  return 0;
}

```

## disassembly

```asm
0x180340d60  mov     rax, rsp
0x180340d63  mov     [rax+10h], rbx
0x180340d67  mov     [rax+8], rcx
0x180340d6b  push    rdi
0x180340d6c  sub     rsp, 40h
0x180340d70  mov     qword ptr [rax-20h], 0
0x180340d78  lea     r8, [rax-20h]; phModule
0x180340d7c  lea     rdx, ?binaryName@AutoSystemInfo@@0PAGA; lpModuleName
0x180340d83  xor     ecx, ecx; dwFlags
0x180340d85  call    cs:__imp_GetModuleHandleExW
0x180340d8b  test    eax, eax
0x180340d8d  jnz     short loc_180340D98
0x180340d8f  mov     [rsp+48h+hLibModule], 0
0x180340d98  mov     rdi, [rsp+48h+arg_0]
0x180340d9d  lea     rbx, [rdi+130h]
0x180340da4  mov     [rsp+48h+var_18], rbx
0x180340da9  mov     rcx, [rbx]; hEvent
0x180340dac  call    cs:__imp_SetEvent
0x180340db2  nop
0x180340db3  mov     rcx, rdi; this
0x180340db6  call    ?Run@BackgroundJobProcessor@JsUtil@@AEAAXXZ; JsUtil::BackgroundJobProcessor::Run(void)
0x180340dbb  jmp     short loc_180340DC2
0x180340dbd  mov     rbx, [rsp+48h+var_18]
0x180340dc2  mov     rcx, [rbx]; hEvent
0x180340dc5  call    cs:__imp_SetEvent
0x180340dcb  mov     rcx, [rsp+48h+hLibModule]; hLibModule
0x180340dd0  test    rcx, rcx
0x180340dd3  jz      short loc_180340DDE
0x180340dd5  xor     edx, edx; dwExitCode
0x180340dd7  call    cs:__imp_FreeLibraryAndExitThread
0x180340dde  xor     eax, eax
0x180340de0  mov     rbx, [rsp+48h+arg_8]
0x180340de5  add     rsp, 40h
0x180340de9  pop     rdi
0x180340dea  retn
0x18035d911  mov     [rsp+arg_0], rcx
0x18035d916  mov     [rsp+arg_8], rdx
0x18035d91b  push    rbp
0x18035d91c  sub     rsp, 20h
0x18035d920  mov     rbp, rdx
0x18035d923  mov     [rbp+38h], rcx
0x18035d927  call    ?Flush@Output@@SAXXZ; Output::Flush(void)
0x18035d92c  mov     dword ptr [rbp+20h], 0
0x18035d933  mov     eax, [rbp+20h]
0x18035d936  add     rsp, 20h
0x18035d93a  pop     rbp
0x18035d93b  retn
```

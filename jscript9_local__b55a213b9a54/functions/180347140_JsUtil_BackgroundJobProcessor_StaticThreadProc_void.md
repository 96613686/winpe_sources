# JsUtil::BackgroundJobProcessor::StaticThreadProc(void *)

- ea: `0x180347140`
- end: `0x1803471e4`
- name: `?StaticThreadProc@BackgroundJobProcessor@JsUtil@@CAIPEAX@Z`
- size: `164`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800045e4`
- `0x1801b3330`
- `0x180347140`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x1803471c9`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1803471c9`
- `KERNEL32!SetEvent` at `0x180347192`
- `KERNEL32!SetEvent` at `0x1803471b1`
- `KERNEL32!SetEvent` at `0x180347192`
- `KERNEL32!SetEvent` at `0x1803471b1`
- `KERNEL32!GetModuleHandleExW` at `0x180347165`
- `KERNEL32!GetModuleHandleExW` at `0x180347165`

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
0x180347140  mov     rax, rsp
0x180347143  mov     [rax+10h], rbx
0x180347147  mov     [rax+8], rcx
0x18034714b  push    rdi
0x18034714c  sub     rsp, 40h
0x180347150  mov     qword ptr [rax-20h], 0
0x180347158  lea     r8, [rax-20h]; phModule
0x18034715c  lea     rdx, ?binaryName@AutoSystemInfo@@0PAGA; lpModuleName
0x180347163  xor     ecx, ecx; dwFlags
0x180347165  call    cs:__imp_GetModuleHandleExW
0x18034716c  nop     dword ptr [rax+rax+00h]
0x180347171  test    eax, eax
0x180347173  jnz     short loc_18034717E
0x180347175  mov     [rsp+48h+hLibModule], 0
0x18034717e  mov     rdi, [rsp+48h+arg_0]
0x180347183  lea     rbx, [rdi+130h]
0x18034718a  mov     [rsp+48h+var_18], rbx
0x18034718f  mov     rcx, [rbx]; hEvent
0x180347192  call    cs:__imp_SetEvent
0x180347199  nop     dword ptr [rax+rax+00h]
0x18034719e  nop
0x18034719f  mov     rcx, rdi; this
0x1803471a2  call    ?Run@BackgroundJobProcessor@JsUtil@@AEAAXXZ; JsUtil::BackgroundJobProcessor::Run(void)
0x1803471a7  jmp     short loc_1803471AE
0x1803471a9  mov     rbx, [rsp+48h+var_18]
0x1803471ae  mov     rcx, [rbx]; hEvent
0x1803471b1  call    cs:__imp_SetEvent
0x1803471b8  nop     dword ptr [rax+rax+00h]
0x1803471bd  mov     rcx, [rsp+48h+hLibModule]; hLibModule
0x1803471c2  test    rcx, rcx
0x1803471c5  jz      short loc_1803471D6
0x1803471c7  xor     edx, edx; dwExitCode
0x1803471c9  call    cs:__imp_FreeLibraryAndExitThread
0x1803471d6  xor     eax, eax
0x1803471d8  mov     rbx, [rsp+48h+arg_8]
0x1803471dd  add     rsp, 40h
0x1803471e1  pop     rdi
0x1803471e2  retn
0x180363ccb  mov     [rsp+arg_0], rcx
0x180363cd0  mov     [rsp+arg_8], rdx
0x180363cd5  push    rbp
0x180363cd6  sub     rsp, 20h
0x180363cda  mov     rbp, rdx
0x180363cdd  mov     [rbp+38h], rcx
0x180363ce1  call    ?Flush@Output@@SAXXZ; Output::Flush(void)
0x180363ce6  mov     dword ptr [rbp+20h], 0
0x180363ced  mov     eax, [rbp+20h]
0x180363cf0  add     rsp, 20h
0x180363cf4  pop     rbp
0x180363cf5  retn
```

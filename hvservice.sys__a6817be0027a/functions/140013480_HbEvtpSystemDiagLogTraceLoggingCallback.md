# HbEvtpSystemDiagLogTraceLoggingCallback

- ea: `0x140013480`
- end: `0x140013507`
- name: `HbEvtpSystemDiagLogTraceLoggingCallback`
- size: `135`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, int, struct _IO_REMOVE_LOCK *Tag)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001270`
- `0x140013480`
- `0x140013ef0`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400134b2`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400134b2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400134ea`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400134ea`

## pseudocode

```c
void __fastcall HbEvtpSystemDiagLogTraceLoggingCallback(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        struct _IO_REMOVE_LOCK *Tag)
{
  if ( IoAcquireRemoveLockEx(Tag + 2, Tag, File, 1u, 0x20u) >= 0 )
  {
    if ( a2 == 1 )
    {
      HbEvtpScheduleSystemDiagLogWorkItem(Tag);
    }
    else if ( a2 == 2 )
    {
      HbEvtpProcessSystemDiagLog(1);
    }
    IoReleaseRemoveLockEx(Tag + 2, Tag, 0x20u);
  }
}

```

## disassembly

```asm
0x140013480  mov     [rsp+arg_0], rbx
0x140013485  mov     [rsp+arg_8], rsi
0x14001348a  push    rdi
0x14001348b  sub     rsp, 30h
0x14001348f  mov     rbx, [rsp+38h+Tag]
0x140013494  lea     r8, File; File
0x14001349b  mov     edi, edx
0x14001349d  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x1400134a5  mov     r9d, 1; Line
0x1400134ab  mov     rdx, rbx; Tag
0x1400134ae  lea     rcx, [rbx+40h]; RemoveLock
0x1400134b2  call    cs:__imp_IoAcquireRemoveLockEx
0x1400134b9  nop     dword ptr [rax+rax+00h]
0x1400134be  test    eax, eax
0x1400134c0  js      short loc_1400134F6
0x1400134c2  cmp     edi, 1
0x1400134c5  jnz     short loc_1400134D1
0x1400134c7  mov     rcx, rbx; Tag
0x1400134ca  call    HbEvtpScheduleSystemDiagLogWorkItem
0x1400134cf  jmp     short loc_1400134DD
0x1400134d1  cmp     edi, 2
0x1400134d4  jnz     short loc_1400134DD
0x1400134d6  mov     cl, 1
0x1400134d8  call    HbEvtpProcessSystemDiagLog
0x1400134dd  mov     r8d, 20h ; ' '; RemlockSize
0x1400134e3  lea     rcx, [rbx+40h]; RemoveLock
0x1400134e7  mov     rdx, rbx; Tag
0x1400134ea  call    cs:__imp_IoReleaseRemoveLockEx
0x1400134f1  nop     dword ptr [rax+rax+00h]
0x1400134f6  mov     rbx, [rsp+38h+arg_0]
0x1400134fb  mov     rsi, [rsp+38h+arg_8]
0x140013500  add     rsp, 30h
0x140013504  pop     rdi
0x140013505  retn
```

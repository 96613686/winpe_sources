# CCrashReport::OnWerMiniDumpCallback(int *,_MINIDUMP_CALLBACK_INPUT *,_MINIDUMP_CALLBACK_OUTPUT *)

- ea: `0x180014278`
- end: `0x1800143a1`
- name: `?OnWerMiniDumpCallback@CCrashReport@@AEAAHPEAHPEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(CCrashReport *__hidden this, int *, struct _MINIDUMP_CALLBACK_INPUT *, struct _MINIDUMP_CALLBACK_OUTPUT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001611c`

## callees

- `0x180014278`
- `0x18003e5a8`

## import_xrefs

- `wer!WerpStitchedMinidumpVmPostReadCallback` at `0x180014341`
- `wer!WerpStitchedMinidumpVmPostReadCallback` at `0x180014341`
- `wer!WerpStitchedMinidumpVmPreReadCallback` at `0x180014366`
- `wer!WerpStitchedMinidumpVmPreReadCallback` at `0x180014366`
- `wer!WerpStitchedMinidumpVmQueryCallback` at `0x180014379`
- `wer!WerpStitchedMinidumpVmQueryCallback` at `0x180014379`

## pseudocode

```c
__int64 __fastcall CCrashReport::OnWerMiniDumpCallback(
        CCrashReport *this,
        int *a2,
        struct _MINIDUMP_CALLBACK_INPUT *a3,
        struct _MINIDUMP_CALLBACK_OUTPUT *a4)
{
  struct _WERP_STITCHED_DUMP_WRITER *v8; // rbp
  ULONG Callback; // eax

  if ( *((_QWORD *)this + 617) && !*((_DWORD *)this + 1238) )
  {
    v8 = (CCrashReport *)((char *)this + 4960);
    if ( !*((_QWORD *)this + 623) )
      MicrosoftTelemetryAssertTriggeredNoArgs(this);
    if ( !*((_QWORD *)this + 625) )
      MicrosoftTelemetryAssertTriggeredNoArgs(this);
    if ( !*((_QWORD *)this + 626) )
      MicrosoftTelemetryAssertTriggeredNoArgs(this);
    if ( !*((_QWORD *)this + 627) )
      MicrosoftTelemetryAssertTriggeredNoArgs(this);
    *a2 = 1;
    switch ( a3->CallbackType )
    {
      case 0x11u:
        a4->ModuleWriteFlags = 1;
        return 1;
      case 0x12u:
        Callback = WerpStitchedMinidumpVmQueryCallback(v8, &a4->VmQueryResult, a3->IncludeModule.BaseOfImage);
        goto LABEL_18;
      case 0x13u:
        ++*((_DWORD *)this + 1276);
        Callback = WerpStitchedMinidumpVmPreReadCallback(
                     v8,
                     &a4->VmReadBytesCompleted,
                     a3->IncludeModule.BaseOfImage,
                     a3->VmPreRead.Buffer,
                     a3->Module.SizeOfImage);
        goto LABEL_18;
      case 0x14u:
        ++*((_DWORD *)this + 1277);
        Callback = WerpStitchedMinidumpVmPostReadCallback(
                     v8,
                     &a4->VmReadBytesCompleted,
                     a3->IncludeModule.BaseOfImage,
                     a3->VmPreRead.Buffer,
                     a3->Module.SizeOfImage,
                     a3->Module.CheckSum,
                     a3->Module.TimeDateStamp);
LABEL_18:
        a4->ModuleWriteFlags = Callback;
        return 1;
    }
  }
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x180014278  push    rbx
0x18001427a  push    rbp
0x18001427b  push    rsi
0x18001427c  push    rdi
0x18001427d  push    r12
0x18001427f  push    r14
0x180014281  sub     rsp, 48h
0x180014285  cmp     qword ptr [rcx+1348h], 0
0x18001428d  mov     rsi, r9
0x180014290  mov     rdi, r8
0x180014293  mov     r14, rdx
0x180014296  mov     rbx, rcx
0x180014299  jz      loc_18001438B
0x18001429f  cmp     dword ptr [rcx+1358h], 0
0x1800142a6  jnz     loc_18001438B
0x1800142ac  lea     rbp, [rcx+1360h]
0x1800142b3  cmp     qword ptr [rbp+18h], 0
0x1800142b8  jnz     short loc_1800142BF
0x1800142ba  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800142bf  cmp     qword ptr [rbx+1388h], 0
0x1800142c7  jnz     short loc_1800142CE
0x1800142c9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800142ce  cmp     qword ptr [rbx+1390h], 0
0x1800142d6  jnz     short loc_1800142DD
0x1800142d8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800142dd  cmp     qword ptr [rbx+1398h], 0
0x1800142e5  jnz     short loc_1800142EC
0x1800142e7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800142ec  mov     r12d, 1
0x1800142f2  mov     [r14], r12d
0x1800142f5  mov     edx, [rdi+0Ch]
0x1800142f8  sub     edx, 11h
0x1800142fb  jz      loc_180014383
0x180014301  sub     edx, r12d
0x180014304  jz      short loc_18001436E
0x180014306  sub     edx, r12d
0x180014309  jz      short loc_180014349
0x18001430b  cmp     edx, r12d
0x18001430e  jnz     short loc_18001438B
0x180014310  add     [rbx+13F4h], r12d
0x180014317  lea     rdx, [rsi+4]
0x18001431b  mov     r8d, [rdi+28h]
0x18001431f  mov     rcx, rbp
0x180014322  mov     r9, [rdi+18h]
0x180014326  mov     [rsp+78h+var_48], r8d
0x18001432b  mov     r8d, [rdi+24h]
0x18001432f  mov     [rsp+78h+var_50], r8d
0x180014334  mov     r8d, [rdi+20h]
0x180014338  mov     [rsp+78h+var_58], r8d
0x18001433d  mov     r8, [rdi+10h]
0x180014341  call    cs:__imp_?WerpStitchedMinidumpVmPostReadCallback@@YAJPEAU_WERP_STITCHED_DUMP_WRITER@@PEAK_KPEAXKKJ@Z; WerpStitchedMinidumpVmPostReadCallback(_WERP_STITCHED_DUMP_WRITER *,ulong *,unsigned __int64,void *,ulong,ulong,long)
0x180014347  jmp     short loc_18001437F
0x180014349  add     [rbx+13F0h], r12d
0x180014350  lea     rdx, [rsi+4]
0x180014354  mov     eax, [rdi+20h]
0x180014357  mov     rcx, rbp
0x18001435a  mov     r9, [rdi+18h]
0x18001435e  mov     r8, [rdi+10h]
0x180014362  mov     [rsp+78h+var_58], eax
0x180014366  call    cs:__imp_?WerpStitchedMinidumpVmPreReadCallback@@YAJPEAU_WERP_STITCHED_DUMP_WRITER@@PEAK_KPEAXK@Z; WerpStitchedMinidumpVmPreReadCallback(_WERP_STITCHED_DUMP_WRITER *,ulong *,unsigned __int64,void *,ulong)
0x18001436c  jmp     short loc_18001437F
0x18001436e  mov     r8, [rdi+10h]
0x180014372  lea     rdx, [rsi+4]
0x180014376  mov     rcx, rbp
0x180014379  call    cs:__imp_?WerpStitchedMinidumpVmQueryCallback@@YAJPEAU_WERP_STITCHED_DUMP_WRITER@@PEAU_MINIDUMP_MEMORY_INFO@@_K@Z; WerpStitchedMinidumpVmQueryCallback(_WERP_STITCHED_DUMP_WRITER *,_MINIDUMP_MEMORY_INFO *,unsigned __int64)
0x18001437f  mov     [rsi], eax
0x180014381  jmp     short loc_180014386
0x180014383  mov     [rsi], r12d
0x180014386  mov     eax, r12d
0x180014389  jmp     short loc_180014394
0x18001438b  mov     dword ptr [r14], 0
0x180014392  xor     eax, eax
0x180014394  add     rsp, 48h
0x180014398  pop     r14
0x18001439a  pop     r12
0x18001439c  pop     rdi
0x18001439d  pop     rsi
0x18001439e  pop     rbp
0x18001439f  pop     rbx
0x1800143a0  retn
```

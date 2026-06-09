# BootGraphicsUpdateThread(CDDPDEV *)

- ea: `0x14001d300`
- end: `0x14001d450`
- name: `?BootGraphicsUpdateThread@@YAXPEAUCDDPDEV@@@Z`
- size: `336`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x14001d300`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14001d3a0`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001d3a0`
- `ntoskrnl!ObfReferenceObject` at `0x14001d32b`
- `ntoskrnl!ObfReferenceObject` at `0x14001d32b`
- `ntoskrnl!KeSetEvent` at `0x14001d343`
- `ntoskrnl!KeSetEvent` at `0x14001d343`
- `watchdog!SMgrGdiCallout` at `0x14001d442`
- `watchdog!SMgrGdiCallout` at `0x14001d442`

## pseudocode

```c
void __fastcall BootGraphicsUpdateThread(unsigned int *StartContext)
{
  struct _KTHREAD *CurrentThread; // rcx
  int v3; // edi
  int v4; // esi
  _OWORD v5[2]; // [rsp+30h] [rbp-28h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF

  Interval.QuadPart = 0;
  CurrentThread = KeGetCurrentThread();
  *((_QWORD *)StartContext + 323) = CurrentThread;
  ObfReferenceObject(CurrentThread);
  KeSetEvent(*((PRKEVENT *)StartContext + 331), 0, 0);
  if ( (*((unsigned __int8 (__fastcall **)(__int64))StartContext + 64))(3) )
  {
    Interval.QuadPart = -333333;
    v3 = -1;
    while ( (*((unsigned int (**)(void))StartContext + 63))() == 3 )
    {
      v4 = (*((__int64 (**)(void))StartContext + 66))();
      if ( v3 != v4 )
      {
        (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))StartContext + 62))(
          StartContext[631],
          StartContext[632],
          StartContext[196],
          (char *)StartContext + 1048);
        v3 = v4;
      }
      KeDelayExecutionThread(0, 0, &Interval);
    }
    (*((void (__fastcall **)(_QWORD, _QWORD))StartContext + 65))(0, StartContext[630]);
    if ( *((_BYTE *)StartContext + 2716) )
    {
      memset(v5, 0, sizeof(v5));
      LODWORD(v5[0]) = 12;
      ((void (__fastcall *)(_OWORD *, __int64, _QWORD, _QWORD, _QWORD, _QWORD))SMgrGdiCallout)(
        v5,
        0x200000000LL,
        0,
        0,
        0,
        0);
    }
  }
}

```

## disassembly

```asm
0x14001d300  mov     [rsp+arg_8], rbx
0x14001d305  mov     [rsp+arg_10], rsi
0x14001d30a  push    rdi
0x14001d30b  sub     rsp, 50h
0x14001d30f  mov     rbx, rcx
0x14001d312  mov     qword ptr [rsp+58h+Interval], 0
0x14001d31b  mov     rcx, gs:188h; Object
0x14001d324  mov     [rbx+0A18h], rcx
0x14001d32b  call    cs:__imp_ObfReferenceObject
0x14001d332  nop     dword ptr [rax+rax+00h]
0x14001d337  mov     rcx, [rbx+0A58h]; Event
0x14001d33e  xor     r8d, r8d; Wait
0x14001d341  xor     edx, edx; Increment
0x14001d343  call    cs:__imp_KeSetEvent
0x14001d34a  nop     dword ptr [rax+rax+00h]
0x14001d34f  mov     rax, [rbx+200h]
0x14001d356  mov     ecx, 3
0x14001d35b  call    _guard_dispatch_icall
0x14001d360  test    al, al
0x14001d362  jz      loc_14001D3F5
0x14001d368  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFAE9EBh
0x14001d371  or      edi, 0FFFFFFFFh
0x14001d374  mov     rax, [rbx+1F8h]
0x14001d37b  call    _guard_dispatch_icall
0x14001d380  cmp     eax, 3
0x14001d383  jnz     short loc_14001D3D8
0x14001d385  mov     rax, [rbx+210h]
0x14001d38c  call    _guard_dispatch_icall
0x14001d391  mov     esi, eax
0x14001d393  cmp     edi, eax
0x14001d395  jnz     short loc_14001D3AE
0x14001d397  lea     r8, [rsp+58h+Interval]; Interval
0x14001d39c  xor     edx, edx; Alertable
0x14001d39e  xor     ecx, ecx; WaitMode
0x14001d3a0  call    cs:__imp_KeDelayExecutionThread
0x14001d3a7  nop     dword ptr [rax+rax+00h]
0x14001d3ac  jmp     short loc_14001D374
0x14001d3ae  mov     rax, [rbx+1F0h]
0x14001d3b5  lea     r9, [rbx+418h]
0x14001d3bc  mov     r8d, [rbx+310h]
0x14001d3c3  mov     edx, [rbx+9E0h]
0x14001d3c9  mov     ecx, [rbx+9DCh]
0x14001d3cf  call    _guard_dispatch_icall
0x14001d3d4  mov     edi, esi
0x14001d3d6  jmp     short loc_14001D397
0x14001d3d8  mov     rax, [rbx+208h]
0x14001d3df  xor     ecx, ecx
0x14001d3e1  mov     edx, [rbx+9D8h]
0x14001d3e7  call    _guard_dispatch_icall
0x14001d3ec  cmp     byte ptr [rbx+0A9Ch], 0
0x14001d3f3  jnz     short loc_14001D406
0x14001d3f5  mov     rbx, [rsp+58h+arg_8]
0x14001d3fa  mov     rsi, [rsp+58h+arg_10]
0x14001d3ff  add     rsp, 50h
0x14001d403  pop     rdi
0x14001d404  retn
0x14001d406  xorps   xmm0, xmm0
0x14001d409  mov     [rsp+58h+var_30], 0
0x14001d412  movups  [rsp+58h+var_28], xmm0
0x14001d417  xor     r9d, r9d
0x14001d41a  mov     dword ptr [rsp+58h+var_28], 0Ch
0x14001d422  xor     r8d, r8d
0x14001d425  mov     [rsp+58h+var_38], 0
0x14001d42e  mov     rdx, 200000000h
0x14001d438  lea     rcx, [rsp+58h+var_28]
0x14001d43d  movups  [rsp+58h+var_18], xmm0
0x14001d442  call    cs:__imp_SMgrGdiCallout
0x14001d449  nop     dword ptr [rax+rax+00h]
0x14001d44e  jmp     short loc_14001D3F5
```

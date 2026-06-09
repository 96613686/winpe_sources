# DepFSInstanceTeardownComplete

- ea: `0x180010fd0`
- end: `0x1800110b4`
- name: `DepFSInstanceTeardownComplete`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800010b8`
- `0x18000f91c`
- `0x18000f970`
- `0x180010c00`
- `0x180010fd0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x180011065`
- `FLTMGR!FltReleaseContext` at `0x180011065`
- `FLTMGR!FltGetInstanceContext` at `0x18001102d`
- `FLTMGR!FltGetInstanceContext` at `0x18001102d`

## pseudocode

```c
void __fastcall DepFSInstanceTeardownComplete(__int64 a1)
{
  int v2; // ebx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  Context = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      21,
      WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids,
      *(_QWORD *)(a1 + 24));
  }
  if ( FltGetInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), &Context) >= 0 )
  {
    v2 = ReferenceVolumeContext(Context);
    DepFSCleanupVolumeContext(Context);
    if ( v2 < 0 )
      FltReleaseContext(Context);
    else
      DereferenceVolumeContext(Context);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids,
      *(_QWORD *)(a1 + 24));
  }
}

```

## disassembly

```asm
0x180010fd0  mov     [rsp+arg_8], rbx
0x180010fd5  mov     [rsp+arg_10], rbp
0x180010fda  push    rdi
0x180010fdb  sub     rsp, 20h
0x180010fdf  mov     rdi, rcx
0x180010fe2  mov     [rsp+28h+Context], 0
0x180010feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ff2  lea     rbp, WPP_GLOBAL_Control
0x180010ff9  cmp     rcx, rbp
0x180010ffc  jz      short loc_180011024
0x180010ffe  mov     eax, [rcx+2Ch]
0x180011001  test    al, 4
0x180011003  jz      short loc_180011024
0x180011005  cmp     byte ptr [rcx+29h], 4
0x180011009  jb      short loc_180011024
0x18001100b  mov     r9, [rdi+18h]
0x18001100f  lea     r8, WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids
0x180011016  mov     rcx, [rcx+18h]
0x18001101a  mov     edx, 15h
0x18001101f  call    WPP_SF_q
0x180011024  mov     rcx, [rdi+18h]; Instance
0x180011028  lea     rdx, [rsp+28h+Context]; Context
0x18001102d  call    cs:__imp_FltGetInstanceContext
0x180011034  nop     dword ptr [rax+rax+00h]
0x180011039  test    eax, eax
0x18001103b  js      short loc_180011071
0x18001103d  mov     rcx, [rsp+28h+Context]; Context
0x180011042  mov     dl, 1
0x180011044  call    ReferenceVolumeContext
0x180011049  mov     rcx, [rsp+28h+Context]
0x18001104e  mov     ebx, eax
0x180011050  call    DepFSCleanupVolumeContext
0x180011055  mov     rcx, [rsp+28h+Context]; Context
0x18001105a  test    ebx, ebx
0x18001105c  js      short loc_180011065
0x18001105e  call    DereferenceVolumeContext
0x180011063  jmp     short loc_180011071
0x180011065  call    cs:__imp_FltReleaseContext
0x18001106c  nop     dword ptr [rax+rax+00h]
0x180011071  mov     rcx, cs:WPP_GLOBAL_Control
0x180011078  cmp     rcx, rbp
0x18001107b  jz      short loc_1800110A3
0x18001107d  mov     eax, [rcx+2Ch]
0x180011080  test    al, 4
0x180011082  jz      short loc_1800110A3
0x180011084  cmp     byte ptr [rcx+29h], 4
0x180011088  jb      short loc_1800110A3
0x18001108a  mov     r9, [rdi+18h]
0x18001108e  lea     r8, WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids
0x180011095  mov     rcx, [rcx+18h]
0x180011099  mov     edx, 16h
0x18001109e  call    WPP_SF_q
0x1800110a3  mov     rbx, [rsp+28h+arg_8]
0x1800110a8  mov     rbp, [rsp+28h+arg_10]
0x1800110ad  add     rsp, 20h
0x1800110b1  pop     rdi
0x1800110b2  retn
```

# EapHost::Peer::ConnectionSessionInfo::StopListeningThread(bool)

- ea: `0x18000ca10`
- end: `0x18000cae0`
- name: `?StopListeningThread@ConnectionSessionInfo@Peer@EapHost@@QEAAX_N@Z`
- size: `208`
- prototype: `void __fastcall(EapHost::Peer::ConnectionSessionInfo *__hidden this, bool)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bd30`
- `0x18000c720`
- `0x18000c88c`
- `0x18000cae8`

## callees

- `0x18000b1b0`
- `0x18000ca10`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ca8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ca8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ca4d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ca4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EapHost::Peer::ConnectionSessionInfo::StopListeningThread(
        EapHost::Peer::ConnectionSessionInfo *this,
        char a2)
{
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  _QWORD *v7; // rcx
  int v8; // edx

  v4 = *((_QWORD *)this + 22);
  if ( v4 )
  {
    *((_QWORD *)this + 22) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = (void *)*((_QWORD *)this + 14);
  if ( v5 )
  {
    SetEvent(v5);
    v6 = (void *)*((_QWORD *)this + 16);
    if ( v6 )
    {
      if ( a2 )
        WaitForSingleObject(v6, 0xFFFFFFFF);
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 12;
LABEL_13:
        WPP_SF_Sd(
          v7[2],
          v8,
          (unsigned int)WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids,
          (_DWORD)this + 20,
          *(_DWORD *)this);
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 13;
      goto LABEL_13;
    }
  }
}

```

## disassembly

```asm
0x18000ca10  mov     [rsp+arg_0], rbx
0x18000ca15  push    rdi
0x18000ca16  sub     rsp, 30h
0x18000ca1a  mov     dil, dl
0x18000ca1d  mov     rbx, rcx
0x18000ca20  mov     rcx, [rcx+0B0h]
0x18000ca27  test    rcx, rcx
0x18000ca2a  jz      short loc_18000CA44
0x18000ca2c  mov     qword ptr [rbx+0B0h], 0
0x18000ca37  mov     rax, [rcx]
0x18000ca3a  mov     rax, [rax+10h]
0x18000ca3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca43  nop
0x18000ca44  mov     rcx, [rbx+70h]; hEvent
0x18000ca48  test    rcx, rcx
0x18000ca4b  jz      short loc_18000CA9B
0x18000ca4d  call    cs:__imp_SetEvent
0x18000ca54  nop     dword ptr [rax+rax+00h]
0x18000ca59  mov     rcx, [rbx+80h]; hHandle
0x18000ca60  test    rcx, rcx
0x18000ca63  jnz     short loc_18000CA85
0x18000ca65  lea     rax, WPP_GLOBAL_Control
0x18000ca6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca73  cmp     rcx, rax
0x18000ca76  jz      short loc_18000CAD4
0x18000ca78  test    byte ptr [rcx+1Ch], 1
0x18000ca7c  jz      short loc_18000CAD4
0x18000ca7e  mov     edx, 0Ch
0x18000ca83  jmp     short loc_18000CAB9
0x18000ca85  test    dil, dil
0x18000ca88  jz      short loc_18000CAD4
0x18000ca8a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ca8d  call    cs:__imp_WaitForSingleObject
0x18000ca94  nop     dword ptr [rax+rax+00h]
0x18000ca99  jmp     short loc_18000CAD4
0x18000ca9b  lea     rax, WPP_GLOBAL_Control
0x18000caa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000caa9  cmp     rcx, rax
0x18000caac  jz      short loc_18000CAD4
0x18000caae  test    byte ptr [rcx+1Ch], 1
0x18000cab2  jz      short loc_18000CAD4
0x18000cab4  mov     edx, 0Dh
0x18000cab9  mov     eax, [rbx]
0x18000cabb  mov     [rsp+38h+var_18], eax
0x18000cabf  lea     r9, [rbx+14h]
0x18000cac3  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000caca  mov     rcx, [rcx+10h]
0x18000cace  call    WPP_SF_Sd
0x18000cad3  nop
0x18000cad4  mov     rbx, [rsp+38h+arg_0]
0x18000cad9  add     rsp, 30h
0x18000cadd  pop     rdi
0x18000cade  retn
```

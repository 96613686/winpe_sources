# DrOnSessionConnect

- ea: `0x14002aebc`
- end: `0x14002b081`
- name: `DrOnSessionConnect`
- size: `453`
- prototype: `__int64 __fastcall(_QWORD *StartContext)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14002acc0`

## callees

- `0x140003064`
- `0x14000324c`
- `0x14000327c`
- `0x1400068c0`
- `0x140011c9c`
- `0x14001a728`
- `0x14001d9d4`
- `0x14002aebc`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14002af03`
- `ntoskrnl!ProbeForRead` at `0x14002af03`
- `ntoskrnl!ProbeForWrite` at `0x14002af1c`
- `ntoskrnl!ProbeForWrite` at `0x14002af1c`

## pseudocode

```c
__int64 __fastcall DrOnSessionConnect(_QWORD *StartContext)
{
  volatile void *v2; // rdi
  volatile void *v3; // rsi
  DrSessionManager *v4; // rcx
  int started; // ebx
  _DWORD v7[30]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v8; // [rsp+A0h] [rbp+8h] BYREF

  memset(v7, 0, 0x50u);
  v8 = 0;
  v2 = (volatile void *)StartContext[69];
  v3 = (volatile void *)StartContext[70];
  ProbeForRead(v2, 0x50u, 1u);
  ProbeForWrite(v3, 8u, 1u);
  if ( StartContext[69]
    && *((_DWORD *)StartContext + 142) >= 0x50u
    && *((_DWORD *)StartContext + 143) >= 8u
    && StartContext[70] )
  {
    RtlCopyFromUser(v7, (void *)v2, 0x50u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids, v7[0]);
    started = DrStartMinirdr(StartContext);
    if ( started >= 0 )
      DrSessionManager::OnConnect(v4, (struct tagCHANNEL_CONNECT_IN *)v7, (struct tagCHANNEL_CONNECT_OUT *)&v8);
    RtlWriteULong64ToUser(v3, v8);
    return (unsigned int)started;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14002aebc  push    rbx
0x14002aebe  push    rsi
0x14002aebf  push    rdi
0x14002aec0  push    r12
0x14002aec2  sub     rsp, 78h
0x14002aec6  mov     rbx, rcx
0x14002aec9  mov     r12d, 50h ; 'P'
0x14002aecf  mov     r8d, r12d; Size
0x14002aed2  xor     edx, edx; Val
0x14002aed4  lea     rcx, [rsp+98h+var_78]; void *
0x14002aed9  call    memset
0x14002aede  mov     [rsp+98h+arg_0], 0
0x14002aeea  mov     rdi, [rbx+228h]
0x14002aef1  mov     rsi, [rbx+230h]
0x14002aef8  lea     r8d, [r12-4Fh]; Alignment
0x14002aefd  mov     edx, r12d; Length
0x14002af00  mov     rcx, rdi; Address
0x14002af03  call    cs:__imp_ProbeForRead
0x14002af0a  nop     dword ptr [rax+rax+00h]
0x14002af0f  lea     edx, [r12-48h]; Length
0x14002af14  lea     r8d, [r12-4Fh]; Alignment
0x14002af19  mov     rcx, rsi; Address
0x14002af1c  call    cs:__imp_ProbeForWrite
0x14002af23  nop     dword ptr [rax+rax+00h]
0x14002af28  cmp     qword ptr [rbx+228h], 0
0x14002af30  jz      loc_14002B00F
0x14002af36  cmp     [rbx+238h], r12d
0x14002af3d  jb      loc_14002B00F
0x14002af43  cmp     dword ptr [rbx+23Ch], 8
0x14002af4a  jb      loc_14002B00F
0x14002af50  cmp     qword ptr [rbx+230h], 0
0x14002af58  jz      loc_14002B00F
0x14002af5e  mov     r8d, r12d; Size
0x14002af61  mov     rdx, rdi; Src
0x14002af64  lea     rcx, [rsp+98h+var_78]; void *
0x14002af69  call    RtlCopyFromUser
0x14002af6e  lea     rax, WPP_GLOBAL_Control
0x14002af75  mov     rcx, cs:WPP_GLOBAL_Control
0x14002af7c  cmp     rcx, rax
0x14002af7f  jz      short loc_14002AFA2
0x14002af81  cmp     byte ptr [rcx+29h], 4
0x14002af85  jb      short loc_14002AFA2
0x14002af87  lea     edx, [r12-40h]
0x14002af8c  mov     r9d, [rsp+98h+var_78]
0x14002af91  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14002af98  mov     rcx, [rcx+18h]
0x14002af9c  call    WPP_SF_d
0x14002afa1  nop
0x14002afa2  mov     rcx, rbx; StartContext
0x14002afa5  call    DrStartMinirdr
0x14002afaa  mov     ebx, eax
0x14002afac  test    eax, eax
0x14002afae  js      short loc_14002AFC3
0x14002afb0  lea     r8, [rsp+98h+arg_0]; struct tagCHANNEL_CONNECT_OUT *
0x14002afb8  lea     rdx, [rsp+98h+var_78]; struct tagCHANNEL_CONNECT_IN *
0x14002afbd  call    ?OnConnect@DrSessionManager@@QEAAHPEAUtagCHANNEL_CONNECT_IN@@PEAUtagCHANNEL_CONNECT_OUT@@@Z; DrSessionManager::OnConnect(tagCHANNEL_CONNECT_IN *,tagCHANNEL_CONNECT_OUT *)
0x14002afc2  nop
0x14002afc3  mov     rdx, [rsp+98h+arg_0]
0x14002afcb  mov     rcx, rsi
0x14002afce  call    RtlWriteULong64ToUser
0x14002afd3  nop
0x14002afd4  mov     eax, ebx
0x14002afd6  jmp     loc_14002B076
0x14002afdb  mov     ebx, eax
0x14002afdd  lea     rax, WPP_GLOBAL_Control
0x14002afe4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002afeb  cmp     rcx, rax
0x14002afee  jz      short loc_14002B00B
0x14002aff0  cmp     byte ptr [rcx+29h], 4
0x14002aff4  jb      short loc_14002B00B
0x14002aff6  mov     edx, 12h
0x14002affb  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14002b002  mov     rcx, [rcx+18h]
0x14002b006  call    WPP_SF_
0x14002b00b  mov     eax, ebx
0x14002b00d  jmp     short loc_14002B076
0x14002b00f  lea     rax, WPP_GLOBAL_Control
0x14002b016  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b01d  cmp     rcx, rax
0x14002b020  jz      short loc_14002B03D
0x14002b022  cmp     byte ptr [rcx+29h], 2
0x14002b026  jb      short loc_14002B03D
0x14002b028  mov     edx, 0Fh
0x14002b02d  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14002b034  mov     rcx, [rcx+18h]
0x14002b038  call    WPP_SF_
0x14002b03d  mov     eax, 0C000000Dh
0x14002b042  jmp     short loc_14002B076
0x14002b044  mov     ebx, eax
0x14002b046  lea     rax, WPP_GLOBAL_Control
0x14002b04d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b054  cmp     rcx, rax
0x14002b057  jz      short loc_14002B074
0x14002b059  cmp     byte ptr [rcx+29h], 4
0x14002b05d  jb      short loc_14002B074
0x14002b05f  mov     edx, 11h
0x14002b064  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14002b06b  mov     rcx, [rcx+18h]
0x14002b06f  call    WPP_SF_
0x14002b074  mov     eax, ebx
0x14002b076  add     rsp, 78h
0x14002b07a  pop     r12
0x14002b07c  pop     rdi
0x14002b07d  pop     rsi
0x14002b07e  pop     rbx
0x14002b07f  retn
```

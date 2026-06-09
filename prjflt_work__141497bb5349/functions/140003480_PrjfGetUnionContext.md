# PrjfGetUnionContext

- ea: `0x140003480`
- end: `0x1400035cb`
- name: `PrjfGetUnionContext`
- size: `331`
- prototype: `_QWORD *__fastcall(struct _FLT_INSTANCE *, _QWORD *)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004640`
- `0x1400047cc`
- `0x1400217a4`
- `0x140021f8c`
- `0x1400280f0`
- `0x140029650`
- `0x14002aa24`
- `0x140033bd0`

## callees

- `0x140003480`
- `0x14000b1d0`
- `0x14000d128`

## import_xrefs

- `FLTMGR!FltReleaseResource` at `0x140003597`
- `FLTMGR!FltReleaseResource` at `0x140003597`
- `FLTMGR!FltAcquireResourceShared` at `0x14000352d`
- `FLTMGR!FltAcquireResourceShared` at `0x14000352d`
- `FLTMGR!FltGetInstanceContext` at `0x140003499`
- `FLTMGR!FltGetInstanceContext` at `0x140003499`
- `FLTMGR!FltReleaseContext` at `0x1400035b0`
- `FLTMGR!FltReleaseContext` at `0x1400035b0`

## pseudocode

```c
_QWORD *__fastcall PrjfGetUnionContext(struct _FLT_INSTANCE *a1, _QWORD *a2)
{
  _QWORD *v3; // rbx
  NTSTATUS InstanceContext; // eax
  int v5; // edx
  int v6; // r8d
  _QWORD *i; // rdx
  volatile signed __int32 *v8; // rcx
  PFLT_CONTEXT Context; // [rsp+80h] [rbp+18h] BYREF

  v3 = 0;
  Context = 0;
  InstanceContext = FltGetInstanceContext(a1, &Context);
  if ( InstanceContext >= 0 )
  {
    FltAcquireResourceShared((PERESOURCE)((char *)Context + 48));
    for ( i = (_QWORD *)*((_QWORD *)Context + 19); i != (_QWORD *)((char *)Context + 152); i = (_QWORD *)*i )
    {
      v8 = (volatile signed __int32 *)(i - 2);
      if ( *a2 == *(i - 2) && a2[1] == *((_QWORD *)v8 + 1) )
      {
        v3 = i - 2;
        if ( i != (_QWORD *)16 && _InterlockedIncrement(v8 + 22) <= 1 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, i);
        break;
      }
    }
    FltReleaseResource((PERESOURCE)((char *)Context + 48));
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      526,
      v5,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      35,
      (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
      54,
      InstanceContext);
  }
  if ( Context )
    FltReleaseContext(Context);
  return v3;
}

```

## disassembly

```asm
0x140003480  mov     rax, rsp
0x140003483  mov     [rax+8], rbx
0x140003487  push    rdi
0x140003488  sub     rsp, 60h
0x14000348c  mov     rdi, rdx
0x14000348f  xor     ebx, ebx
0x140003491  lea     rdx, [rax+18h]; Context
0x140003495  mov     [rax+18h], rbx
0x140003499  call    cs:__imp_FltGetInstanceContext
0x1400034a0  nop     dword ptr [rax+rax+00h]
0x1400034a5  test    eax, eax
0x1400034a7  jns     short loc_140003521
0x1400034a9  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400034af  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400034b6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400034bd  setnz   r8b
0x1400034c1  and     dl, 40h
0x1400034c4  jnz     short loc_1400034CF
0x1400034c6  test    r8b, r8b
0x1400034c9  jz      loc_1400035A3
0x1400034cf  mov     r9, cs:WPP_GLOBAL_Control
0x1400034d6  mov     ecx, 20Eh
0x1400034db  mov     [rsp+68h+var_18], eax
0x1400034df  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400034e6  mov     [rsp+68h+var_20], 736h
0x1400034ee  mov     [rsp+68h+var_28], rax
0x1400034f3  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x1400034fa  mov     r9, [r9+40h]
0x1400034fe  mov     [rsp+68h+var_30], rax
0x140003503  mov     [rsp+68h+var_38], 23h ; '#'
0x14000350a  mov     [rsp+68h+var_40], 0Eh
0x140003512  mov     [rsp+68h+var_48], 2
0x140003517  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14000351c  jmp     loc_1400035A3
0x140003521  mov     rcx, [rsp+68h+Context]
0x140003529  add     rcx, 30h ; '0'; Resource
0x14000352d  call    cs:__imp_FltAcquireResourceShared
0x140003534  nop     dword ptr [rax+rax+00h]
0x140003539  mov     r8, [rsp+68h+Context]
0x140003541  add     r8, 98h
0x140003548  mov     rdx, [r8]
0x14000354b  jmp     short loc_140003566
0x14000354d  mov     rax, [rdi]
0x140003550  lea     rcx, [rdx-10h]
0x140003554  cmp     rax, [rcx]
0x140003557  jnz     short loc_140003563
0x140003559  mov     rax, [rdi+8]
0x14000355d  cmp     rax, [rcx+8]
0x140003561  jz      short loc_14000356D
0x140003563  mov     rdx, [rdx]
0x140003566  cmp     rdx, r8
0x140003569  jnz     short loc_14000354D
0x14000356b  jmp     short loc_14000358B
0x14000356d  mov     rbx, rcx
0x140003570  test    rcx, rcx
0x140003573  jz      short loc_14000358B
0x140003575  mov     eax, 1
0x14000357a  lock xadd [rcx+58h], eax
0x14000357f  inc     eax
0x140003581  cmp     eax, 1
0x140003584  jg      short loc_14000358B
0x140003586  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000358b  mov     rcx, [rsp+68h+Context]
0x140003593  add     rcx, 30h ; '0'; Resource
0x140003597  call    cs:__imp_FltReleaseResource
0x14000359e  nop     dword ptr [rax+rax+00h]
0x1400035a3  mov     rcx, [rsp+68h+Context]; Context
0x1400035ab  test    rcx, rcx
0x1400035ae  jz      short loc_1400035BC
0x1400035b0  call    cs:__imp_FltReleaseContext
0x1400035b7  nop     dword ptr [rax+rax+00h]
0x1400035bc  mov     rax, rbx
0x1400035bf  mov     rbx, [rsp+68h+arg_0]
0x1400035c4  add     rsp, 60h
0x1400035c8  pop     rdi
0x1400035c9  retn
```

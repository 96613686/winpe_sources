# PrjfPopulateFile

- ea: `0x14002b0d0`
- end: `0x14002b3b9`
- name: `PrjfPopulateFile`
- size: `745`
- prototype: `__int64 __fastcall(int, const UNICODE_STRING *, const UNICODE_STRING *, _OWORD *, struct _FLT_INSTANCE *Instance, struct _FILE_OBJECT *FileObject, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002aecc`

## callees

- `0x140002b50`
- `0x14000d128`
- `0x14000d754`
- `0x14002b0d0`
- `0x140034c70`
- `0x140042b6c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002b396`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b396`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b287`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b287`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002b26a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002b26a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002b24d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002b24d`
- `ntoskrnl!ExAllocatePool2` at `0x14002b227`
- `ntoskrnl!ExAllocatePool2` at `0x14002b227`
- `FLTMGR!FltReleaseContext` at `0x14002b36d`
- `FLTMGR!FltReleaseContext` at `0x14002b37c`
- `FLTMGR!FltReleaseContext` at `0x14002b36d`
- `FLTMGR!FltReleaseContext` at `0x14002b37c`

## pseudocode

```c
__int64 __fastcall PrjfPopulateFile(
        int a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        _OWORD *a4,
        struct _FLT_INSTANCE *Instance,
        struct _FILE_OBJECT *FileObject,
        __int64 a7)
{
  int v11; // edx
  int appended; // ebx
  int v13; // r8d
  unsigned __int16 v14; // ax
  __int16 v15; // dx
  unsigned __int16 v16; // cx
  int v17; // edx
  int v18; // r8d
  PFLT_CONTEXT v20[2]; // [rsp+60h] [rbp-31h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp-21h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-19h] BYREF

  DestinationString = 0;
  Context = 0;
  v20[0] = 0;
  PrjfGetContextFileObject(Instance, FileObject);
  if ( !MEMORY[0x104] )
    goto LABEL_8;
  v20[0] = 0;
  appended = PrjfLookupInMemoryTombstoneEntry(0, a2, 2u, 0, (PRTL_DYNAMIC_HASH_TABLE_ENTRY *)v20);
  if ( appended >= 0 )
  {
    appended = -1073741267;
    goto LABEL_22;
  }
  if ( appended == -1073741275 )
  {
LABEL_8:
    v14 = a2->Length + a3->Length;
    v15 = a3->Length != 0 ? 2 : 0;
    if ( v14 < a3->Length || (v16 = v15 + v14, (unsigned __int16)(v15 + v14) < v14) )
    {
      appended = -1073741675;
    }
    else
    {
      if ( !v16 )
        goto LABEL_16;
      DestinationString.MaximumLength = v15 + v14;
      DestinationString.Length = 0;
      DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v16, 1852197456);
      if ( !DestinationString.Buffer )
      {
        appended = -1073741670;
        goto LABEL_22;
      }
      RtlCopyUnicodeString(&DestinationString, a3);
      if ( !a3->Length || (appended = RtlAppendUnicodeToString(&DestinationString, L"\\"), appended >= 0) )
      {
        appended = RtlAppendUnicodeStringToString(&DestinationString, a2);
        if ( appended >= 0 )
        {
LABEL_16:
          *(_OWORD *)v20 = *a4;
          appended = PrjfSendGetPlaceholderInformationCommand(
                       a1,
                       (_DWORD)Instance,
                       (unsigned int)v20,
                       (unsigned int)&DestinationString,
                       MEMORY[0x70],
                       a7);
          if ( (int)(appended + 0x80000000) >= 0
            && appended != -1073741772
            && (SBYTE1(xmmword_14001A3D0) < 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
          {
            LOBYTE(v17) = BYTE1(xmmword_14001A3D0) & 0x80;
            LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdZ(
              527,
              v17,
              v18,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              15,
              38,
              (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
              157,
              appended,
              (__int64)&DestinationString);
          }
        }
      }
    }
  }
  else if ( SBYTE1(xmmword_14001A3D0) < 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x80;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      527,
      v11,
      v13,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      15,
      37,
      (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
      71,
      appended);
  }
LABEL_22:
  if ( Context )
    FltReleaseContext(Context);
  FltReleaseContext(0);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664A50u);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14002b0d0  push    rbp
0x14002b0d2  push    rbx
0x14002b0d3  push    rsi
0x14002b0d4  push    rdi
0x14002b0d5  push    r12
0x14002b0d7  push    r13
0x14002b0d9  push    r14
0x14002b0db  push    r15
0x14002b0dd  lea     rbp, [rsp-7]
0x14002b0e2  sub     rsp, 98h
0x14002b0e9  mov     r15, r9
0x14002b0ec  mov     rdi, r8
0x14002b0ef  mov     rsi, rdx
0x14002b0f2  lea     r9, [rbp+3Fh+Context]
0x14002b0f6  mov     rdx, [rbp+3Fh+FileObject]; FileObject
0x14002b0fa  lea     r8, [rbp+3Fh+var_70]
0x14002b0fe  mov     r12, rcx
0x14002b101  xorps   xmm0, xmm0
0x14002b104  mov     rcx, [rbp+3Fh+Instance]; Instance
0x14002b108  xor     r13d, r13d
0x14002b10b  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x14002b10f  mov     [rbp+3Fh+Context], r13
0x14002b113  mov     [rbp+3Fh+var_70], r13
0x14002b117  call    PrjfGetContextFileObject
0x14002b11c  mov     r14, [rbp+3Fh+var_70]
0x14002b120  cmp     [r14+104h], r13d
0x14002b127  jz      loc_14002B1DC
0x14002b12d  lea     rax, [rbp+3Fh+var_70]
0x14002b131  mov     [rbp+3Fh+var_70], r13
0x14002b135  xor     r9d, r9d
0x14002b138  mov     [rsp+0D0h+var_B0], rax
0x14002b13d  lea     r8d, [r13+2]
0x14002b141  mov     rdx, rsi
0x14002b144  mov     rcx, r14
0x14002b147  call    PrjfLookupInMemoryTombstoneEntry
0x14002b14c  mov     ebx, eax
0x14002b14e  test    eax, eax
0x14002b150  js      short loc_14002B15C
0x14002b152  mov     ebx, 0C000022Dh
0x14002b157  jmp     loc_14002B364
0x14002b15c  cmp     ebx, 0C0000225h
0x14002b162  jz      short loc_14002B1DC
0x14002b164  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002b16a  lea     rax, WPP_RECORDER_INITIALIZED
0x14002b171  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002b178  setnz   r8b
0x14002b17c  and     dl, 80h
0x14002b17f  jnz     short loc_14002B18A
0x14002b181  test    r8b, r8b
0x14002b184  jz      loc_14002B364
0x14002b18a  mov     r9, cs:WPP_GLOBAL_Control
0x14002b191  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002b198  mov     [rsp+0D0h+var_80], ebx
0x14002b19c  mov     ecx, 20Fh
0x14002b1a1  mov     [rsp+0D0h+var_88], 0A47h
0x14002b1a9  mov     [rsp+0D0h+var_90], rax
0x14002b1ae  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002b1b5  mov     r9, [r9+40h]
0x14002b1b9  mov     [rsp+0D0h+var_98], rax
0x14002b1be  mov     [rsp+0D0h+var_A0], 25h ; '%'
0x14002b1c5  mov     dword ptr [rsp+0D0h+var_A8], 0Fh
0x14002b1cd  mov     byte ptr [rsp+0D0h+var_B0], 2
0x14002b1d2  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002b1d7  jmp     loc_14002B364
0x14002b1dc  movzx   ecx, word ptr [rdi]
0x14002b1df  movzx   eax, cx
0x14002b1e2  neg     ax
0x14002b1e5  movzx   eax, cx
0x14002b1e8  sbb     dx, dx
0x14002b1eb  add     ax, [rsi]
0x14002b1ee  and     dx, 2
0x14002b1f2  cmp     ax, cx
0x14002b1f5  jb      loc_14002B35F
0x14002b1fb  lea     ecx, [rdx+rax]
0x14002b1fe  cmp     cx, ax
0x14002b201  jb      loc_14002B35F
0x14002b207  test    cx, cx
0x14002b20a  jz      loc_14002B29D
0x14002b210  mov     [rbp+3Fh+DestinationString.MaximumLength], cx
0x14002b214  mov     r8d, 6E664A50h
0x14002b21a  movzx   edx, cx
0x14002b21d  mov     ecx, 100h
0x14002b222  mov     [rbp+3Fh+DestinationString.Length], r13w
0x14002b227  call    cs:__imp_ExAllocatePool2
0x14002b22e  nop     dword ptr [rax+rax+00h]
0x14002b233  mov     [rbp+3Fh+DestinationString.Buffer], rax
0x14002b237  test    rax, rax
0x14002b23a  jnz     short loc_14002B246
0x14002b23c  mov     ebx, 0C000009Ah
0x14002b241  jmp     loc_14002B364
0x14002b246  mov     rdx, rdi; SourceString
0x14002b249  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x14002b24d  call    cs:__imp_RtlCopyUnicodeString
0x14002b254  nop     dword ptr [rax+rax+00h]
0x14002b259  cmp     [rdi], r13w
0x14002b25d  jz      short loc_14002B280
0x14002b25f  lea     rdx, asc_14001595C; "\\"
0x14002b266  lea     rcx, [rbp+3Fh+DestinationString]; Destination
0x14002b26a  call    cs:__imp_RtlAppendUnicodeToString
0x14002b271  nop     dword ptr [rax+rax+00h]
0x14002b276  mov     ebx, eax
0x14002b278  test    eax, eax
0x14002b27a  js      loc_14002B364
0x14002b280  mov     rdx, rsi; Source
0x14002b283  lea     rcx, [rbp+3Fh+DestinationString]; Destination
0x14002b287  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002b28e  nop     dword ptr [rax+rax+00h]
0x14002b293  mov     ebx, eax
0x14002b295  test    eax, eax
0x14002b297  js      loc_14002B364
0x14002b29d  mov     rax, [rbp+3Fh+arg_30]
0x14002b2a1  lea     r9, [rbp+3Fh+DestinationString]
0x14002b2a5  movaps  xmm0, xmmword ptr [r15]
0x14002b2a9  lea     r8, [rbp+3Fh+var_70]
0x14002b2ad  mov     rdx, [rbp+3Fh+Instance]
0x14002b2b1  mov     rcx, r12
0x14002b2b4  mov     [rsp+0D0h+var_A8], rax
0x14002b2b9  mov     rax, [r14+70h]
0x14002b2bd  mov     [rsp+0D0h+var_B0], rax
0x14002b2c2  movdqa  xmmword ptr [rbp+3Fh+var_70], xmm0
0x14002b2c7  call    PrjfSendGetPlaceholderInformationCommand
0x14002b2cc  mov     ecx, 80000000h
0x14002b2d1  mov     ebx, eax
0x14002b2d3  add     eax, ecx
0x14002b2d5  test    ecx, eax
0x14002b2d7  jnz     loc_14002B364
0x14002b2dd  cmp     ebx, 0C0000034h
0x14002b2e3  jz      short loc_14002B364
0x14002b2e5  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002b2eb  lea     rax, WPP_RECORDER_INITIALIZED
0x14002b2f2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002b2f9  setnz   r8b
0x14002b2fd  and     dl, 80h
0x14002b300  jnz     short loc_14002B307
0x14002b302  test    r8b, r8b
0x14002b305  jz      short loc_14002B364
0x14002b307  mov     r9, cs:WPP_GLOBAL_Control
0x14002b30e  lea     rax, [rbp+3Fh+DestinationString]
0x14002b312  mov     [rsp+0D0h+var_78], rax
0x14002b317  mov     ecx, 20Fh
0x14002b31c  mov     [rsp+0D0h+var_80], ebx
0x14002b320  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002b327  mov     [rsp+0D0h+var_88], 0A9Dh
0x14002b32f  mov     r9, [r9+40h]
0x14002b333  mov     [rsp+0D0h+var_90], rax
0x14002b338  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002b33f  mov     [rsp+0D0h+var_98], rax
0x14002b344  mov     [rsp+0D0h+var_A0], 26h ; '&'
0x14002b34b  mov     dword ptr [rsp+0D0h+var_A8], 0Fh
0x14002b353  mov     byte ptr [rsp+0D0h+var_B0], 2
0x14002b358  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14002b35d  jmp     short loc_14002B364
0x14002b35f  mov     ebx, 0C0000095h
0x14002b364  mov     rcx, [rbp+3Fh+Context]; Context
0x14002b368  test    rcx, rcx
0x14002b36b  jz      short loc_14002B379
0x14002b36d  call    cs:__imp_FltReleaseContext
0x14002b374  nop     dword ptr [rax+rax+00h]
0x14002b379  mov     rcx, r14; Context
0x14002b37c  call    cs:__imp_FltReleaseContext
0x14002b383  nop     dword ptr [rax+rax+00h]
0x14002b388  mov     rcx, [rbp+3Fh+DestinationString.Buffer]; P
0x14002b38c  test    rcx, rcx
0x14002b38f  jz      short loc_14002B3A2
0x14002b391  mov     edx, 6E664A50h; Tag
0x14002b396  call    cs:__imp_ExFreePoolWithTag
0x14002b39d  nop     dword ptr [rax+rax+00h]
0x14002b3a2  mov     eax, ebx
0x14002b3a4  add     rsp, 98h
0x14002b3ab  pop     r15
0x14002b3ad  pop     r14
0x14002b3af  pop     r13
0x14002b3b1  pop     r12
0x14002b3b3  pop     rdi
0x14002b3b4  pop     rsi
0x14002b3b5  pop     rbx
0x14002b3b6  pop     rbp
0x14002b3b7  retn
```

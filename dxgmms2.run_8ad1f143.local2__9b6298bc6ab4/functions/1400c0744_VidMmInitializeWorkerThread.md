# VidMmInitializeWorkerThread

- ea: `0x1400c0744`
- end: `0x1400c088c`
- name: `VidMmInitializeWorkerThread`
- size: `328`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400bf974`

## callees

- `0x1400037a0`
- `0x1400c0744`
- `0x14011023c`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400c0850`
- `ntoskrnl!ObfReferenceObject` at `0x1400c0850`
- `ntoskrnl!ZwClose` at `0x1400c0864`
- `ntoskrnl!ZwClose` at `0x1400c0864`
- `ntoskrnl!PsCreateSystemThread` at `0x1400c082d`
- `ntoskrnl!PsCreateSystemThread` at `0x1400c082d`
- `ntoskrnl!KeInitializeEvent` at `0x1400c079b`
- `ntoskrnl!KeInitializeEvent` at `0x1400c079b`

## pseudocode

```c
__int64 __fastcall VidMmInitializeWorkerThread(__int64 *StartContext, _QWORD *a2)
{
  __int64 v4; // rax
  __int64 i; // rdi
  __int64 v7; // rax
  bool v8; // zf
  void (__fastcall *StartRoutine)(char *); // rax
  __int64 v10; // rdx
  NTSTATUS v11; // edi
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *ThreadHandle; // [rsp+80h] [rbp+8h] BYREF

  *a2 = 0;
  v4 = operator new(72, 926181718, 64);
  StartContext[3] = v4;
  if ( !v4 )
    return 3221225495LL;
  for ( i = 0; i != 3; ++i )
    KeInitializeEvent((PRKEVENT)(StartContext[3] + 24 * i), SynchronizationEvent, 0);
  v7 = *StartContext;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ThreadHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = (*(_BYTE *)(v7 + 37225) & 0x10) == 0;
  StartRoutine = (void (__fastcall *)(char *))VidMmWorkerThreadProc2;
  if ( v8 )
    StartRoutine = VidMmWorkerThreadProc;
  v11 = PsCreateSystemThread(
          &ThreadHandle,
          0x1FFFFFu,
          &ObjectAttributes,
          0,
          0,
          (PKSTART_ROUTINE)StartRoutine,
          StartContext);
  if ( v11 >= 0 )
  {
    LOBYTE(v10) = 1;
    VidMmRequestWorkerThreadStatus(StartContext, v10, 0);
    ObfReferenceObject((PVOID)StartContext[1]);
    ZwClose(ThreadHandle);
    *a2 = StartContext[3];
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400c0744  mov     [rsp+arg_8], rbx
0x1400c0749  mov     [rsp+arg_10], rsi
0x1400c074e  push    rdi
0x1400c074f  sub     rsp, 70h
0x1400c0753  mov     rbx, rcx
0x1400c0756  mov     qword ptr [rdx], 0
0x1400c075d  mov     ecx, 48h ; 'H'
0x1400c0762  mov     rsi, rdx
0x1400c0765  mov     edx, 37346956h
0x1400c076a  lea     r8d, [rcx-8]
0x1400c076e  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400c0773  mov     [rbx+18h], rax
0x1400c0777  test    rax, rax
0x1400c077a  jnz     short loc_1400C0786
0x1400c077c  mov     eax, 0C0000017h
0x1400c0781  jmp     loc_1400C0879
0x1400c0786  xor     edi, edi
0x1400c0788  mov     rax, [rbx+18h]
0x1400c078c  lea     rcx, [rdi+rdi*2]
0x1400c0790  xor     r8d, r8d; State
0x1400c0793  lea     rcx, [rax+rcx*8]; Event
0x1400c0797  lea     edx, [r8+1]; Type
0x1400c079b  call    cs:__imp_KeInitializeEvent
0x1400c07a2  nop     dword ptr [rax+rax+00h]
0x1400c07a7  inc     rdi
0x1400c07aa  cmp     rdi, 3
0x1400c07ae  jnz     short loc_1400C0788
0x1400c07b0  mov     rax, [rbx]
0x1400c07b3  lea     rcx, VidMmWorkerThreadProc
0x1400c07ba  xorps   xmm0, xmm0
0x1400c07bd  mov     qword ptr [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x1400c07c6  mov     qword ptr [rsp+78h+ObjectAttributes.Attributes], 200h
0x1400c07cf  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x1400c07d4  mov     [rsp+78h+ThreadHandle], 0
0x1400c07e0  mov     edx, 1FFFFFh; DesiredAccess
0x1400c07e5  mov     [rsp+78h+ObjectAttributes.RootDirectory], 0
0x1400c07ee  mov     [rsp+78h+ObjectAttributes.ObjectName], 0
0x1400c07f7  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400c07fd  test    byte ptr [rax+9169h], 10h
0x1400c0804  lea     rax, ?VidMmWorkerThreadProc2@@YAXPEAX@Z; VidMmWorkerThreadProc2(void *)
0x1400c080b  mov     [rsp+78h+StartContext], rbx; StartContext
0x1400c0810  cmovz   rax, rcx
0x1400c0814  xor     r9d, r9d; ProcessHandle
0x1400c0817  mov     [rsp+78h+StartRoutine], rax; StartRoutine
0x1400c081c  lea     rcx, [rsp+78h+ThreadHandle]; ThreadHandle
0x1400c0824  mov     [rsp+78h+ClientId], 0; ClientId
0x1400c082d  call    cs:__imp_PsCreateSystemThread
0x1400c0834  nop     dword ptr [rax+rax+00h]
0x1400c0839  mov     edi, eax
0x1400c083b  test    eax, eax
0x1400c083d  js      short loc_1400C0877
0x1400c083f  xor     r8d, r8d
0x1400c0842  mov     dl, 1
0x1400c0844  mov     rcx, rbx
0x1400c0847  call    VidMmRequestWorkerThreadStatus
0x1400c084c  mov     rcx, [rbx+8]; Object
0x1400c0850  call    cs:__imp_ObfReferenceObject
0x1400c0857  nop     dword ptr [rax+rax+00h]
0x1400c085c  mov     rcx, [rsp+78h+ThreadHandle]; Handle
0x1400c0864  call    cs:__imp_ZwClose
0x1400c086b  nop     dword ptr [rax+rax+00h]
0x1400c0870  mov     rcx, [rbx+18h]
0x1400c0874  mov     [rsi], rcx
0x1400c0877  mov     eax, edi
0x1400c0879  lea     r11, [rsp+78h+var_8]
0x1400c087e  mov     rbx, [r11+18h]
0x1400c0882  mov     rsi, [r11+20h]
0x1400c0886  mov     rsp, r11
0x1400c0889  pop     rdi
0x1400c088a  retn
```

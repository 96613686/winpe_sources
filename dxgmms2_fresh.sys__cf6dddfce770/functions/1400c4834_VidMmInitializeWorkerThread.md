# VidMmInitializeWorkerThread

- ea: `0x1400c4834`
- end: `0x1400c497c`
- name: `VidMmInitializeWorkerThread`
- size: `328`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400c3a64`

## callees

- `0x140003490`
- `0x1400c4834`
- `0x1401129d0`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400c4940`
- `ntoskrnl!ObfReferenceObject` at `0x1400c4940`
- `ntoskrnl!ZwClose` at `0x1400c4954`
- `ntoskrnl!ZwClose` at `0x1400c4954`
- `ntoskrnl!PsCreateSystemThread` at `0x1400c491d`
- `ntoskrnl!PsCreateSystemThread` at `0x1400c491d`
- `ntoskrnl!KeInitializeEvent` at `0x1400c488b`
- `ntoskrnl!KeInitializeEvent` at `0x1400c488b`

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
0x1400c4834  mov     [rsp+arg_8], rbx
0x1400c4839  mov     [rsp+arg_10], rsi
0x1400c483e  push    rdi
0x1400c483f  sub     rsp, 70h
0x1400c4843  mov     rbx, rcx
0x1400c4846  mov     qword ptr [rdx], 0
0x1400c484d  mov     ecx, 48h ; 'H'
0x1400c4852  mov     rsi, rdx
0x1400c4855  mov     edx, 37346956h
0x1400c485a  lea     r8d, [rcx-8]
0x1400c485e  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400c4863  mov     [rbx+18h], rax
0x1400c4867  test    rax, rax
0x1400c486a  jnz     short loc_1400C4876
0x1400c486c  mov     eax, 0C0000017h
0x1400c4871  jmp     loc_1400C4969
0x1400c4876  xor     edi, edi
0x1400c4878  mov     rax, [rbx+18h]
0x1400c487c  lea     rcx, [rdi+rdi*2]
0x1400c4880  xor     r8d, r8d; State
0x1400c4883  lea     rcx, [rax+rcx*8]; Event
0x1400c4887  lea     edx, [r8+1]; Type
0x1400c488b  call    cs:__imp_KeInitializeEvent
0x1400c4892  nop     dword ptr [rax+rax+00h]
0x1400c4897  inc     rdi
0x1400c489a  cmp     rdi, 3
0x1400c489e  jnz     short loc_1400C4878
0x1400c48a0  mov     rax, [rbx]
0x1400c48a3  lea     rcx, VidMmWorkerThreadProc
0x1400c48aa  xorps   xmm0, xmm0
0x1400c48ad  mov     qword ptr [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x1400c48b6  mov     qword ptr [rsp+78h+ObjectAttributes.Attributes], 200h
0x1400c48bf  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x1400c48c4  mov     [rsp+78h+ThreadHandle], 0
0x1400c48d0  mov     edx, 1FFFFFh; DesiredAccess
0x1400c48d5  mov     [rsp+78h+ObjectAttributes.RootDirectory], 0
0x1400c48de  mov     [rsp+78h+ObjectAttributes.ObjectName], 0
0x1400c48e7  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400c48ed  test    byte ptr [rax+9169h], 10h
0x1400c48f4  lea     rax, ?VidMmWorkerThreadProc2@@YAXPEAX@Z; VidMmWorkerThreadProc2(void *)
0x1400c48fb  mov     [rsp+78h+StartContext], rbx; StartContext
0x1400c4900  cmovz   rax, rcx
0x1400c4904  xor     r9d, r9d; ProcessHandle
0x1400c4907  mov     [rsp+78h+StartRoutine], rax; StartRoutine
0x1400c490c  lea     rcx, [rsp+78h+ThreadHandle]; ThreadHandle
0x1400c4914  mov     [rsp+78h+ClientId], 0; ClientId
0x1400c491d  call    cs:__imp_PsCreateSystemThread
0x1400c4924  nop     dword ptr [rax+rax+00h]
0x1400c4929  mov     edi, eax
0x1400c492b  test    eax, eax
0x1400c492d  js      short loc_1400C4967
0x1400c492f  xor     r8d, r8d
0x1400c4932  mov     dl, 1
0x1400c4934  mov     rcx, rbx
0x1400c4937  call    VidMmRequestWorkerThreadStatus
0x1400c493c  mov     rcx, [rbx+8]; Object
0x1400c4940  call    cs:__imp_ObfReferenceObject
0x1400c4947  nop     dword ptr [rax+rax+00h]
0x1400c494c  mov     rcx, [rsp+78h+ThreadHandle]; Handle
0x1400c4954  call    cs:__imp_ZwClose
0x1400c495b  nop     dword ptr [rax+rax+00h]
0x1400c4960  mov     rcx, [rbx+18h]
0x1400c4964  mov     [rsi], rcx
0x1400c4967  mov     eax, edi
0x1400c4969  lea     r11, [rsp+78h+var_8]
0x1400c496e  mov     rbx, [r11+18h]
0x1400c4972  mov     rsi, [r11+20h]
0x1400c4976  mov     rsp, r11
0x1400c4979  pop     rdi
0x1400c497a  retn
```

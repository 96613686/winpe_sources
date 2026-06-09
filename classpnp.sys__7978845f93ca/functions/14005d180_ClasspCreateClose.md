# ClasspCreateClose

- ea: `0x14005d180`
- end: `0x14005d5c0`
- name: `ClasspCreateClose`
- size: `1088`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14005d0d0`

## callees

- `0x140016230`
- `0x140016820`
- `0x140016a40`
- `0x14001fbf4`
- `0x14001fc38`
- `0x14001feac`
- `0x140028da8`
- `0x14005d180`
- `0x14005d5d0`
- `0x14005d880`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14005d308`
- `ntoskrnl!IofCallDriver` at `0x14005d308`
- `ntoskrnl!KeInitializeEvent` at `0x14005d2aa`
- `ntoskrnl!KeInitializeEvent` at `0x14005d2aa`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005d56a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005d56a`

## pseudocode

```c
__int64 __fastcall ClasspCreateClose(__int64 a1, IRP *a2, int a3, int a4)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  int v5; // esi
  __int64 v6; // r15
  _FILE_OBJECT *FileObject; // r12
  _QWORD *p_Type; // rdx
  __int64 DictionaryEntry; // rax
  __int64 v12; // rbx
  _IO_STACK_LOCATION *v13; // rax
  _IO_STACK_LOCATION *v14; // rax
  NTSTATUS Status; // ebx
  _IO_SECURITY_CONTEXT *SecurityContext; // r13
  int v18; // eax
  const char *v19; // r9
  struct _KEVENT Event; // [rsp+30h] [rbp-48h] BYREF
  _OWORD *v21; // [rsp+80h] [rbp+8h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = 0;
  v6 = *(_QWORD *)(a1 + 64);
  if ( CurrentStackLocation->MajorFunction )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      FileObject = CurrentStackLocation->FileObject;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids, FileObject);
      }
    }
    p_Type = &CurrentStackLocation->FileObject->Type;
    if ( p_Type )
    {
      DictionaryEntry = GetDictionaryEntry(v6 + 416);
      v12 = DictionaryEntry;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids,
          DictionaryEntry);
      }
      if ( v12 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids);
        }
        ClasspCleanupProtectedLocks(v12);
        ClasspCleanupDisableMcn(v12);
        FreeDictionaryEntry(v6 + 416, v12);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids,
            SecurityContext->DesiredAccess);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids,
            CurrentStackLocation->FileObject);
        }
      }
    }
    p_Type = &CurrentStackLocation->FileObject->Type;
    if ( p_Type )
    {
      v21 = 0;
      v18 = AllocateDictionaryEntry((int)v6 + 416, (_DWORD)p_Type, a3, a4, (__int64)&v21);
      v5 = v18;
      if ( v18 < 0 )
      {
        if ( v18 == -1073741771 )
          v5 = 0;
      }
      else
      {
        p_Type = v21;
        *v21 = 0;
        p_Type[2] = 0;
        *p_Type = CurrentStackLocation->FileObject;
        p_Type[1] = a1;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v19 = "Success";
    if ( v5 < 0 )
      v19 = "FAILED";
    WPP_SF_sq(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)p_Type, a3, (_DWORD)v19, a1);
  }
  if ( v5 < 0 )
    return (unsigned int)v5;
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v13 = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v13[-1].MajorFunction = *(_OWORD *)&v13->MajorFunction;
  *(_OWORD *)&v13[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v13->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v13[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v13->Parameters.SetQuota + 6);
  v13[-1].FileObject = v13->FileObject;
  v13[-1].Control = 0;
  v14 = a2->Tail.Overlay.CurrentStackLocation;
  v14[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ClassSignalCompletion;
  v14[-1].Context = &Event;
  v14[-1].Control = -32;
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(v6 + 16), a2);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = a2->IoStatus.Status;
  }
  if ( Status < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14005d180  mov     rax, rsp
0x14005d183  push    rbx
0x14005d184  push    rsi
0x14005d185  push    rdi
0x14005d186  push    r14
0x14005d188  push    r15
0x14005d18a  sub     rsp, 50h
0x14005d18e  mov     rbx, [rdx+0B8h]
0x14005d195  xor     esi, esi
0x14005d197  mov     r15, [rcx+40h]
0x14005d19b  mov     r14, rdx
0x14005d19e  mov     [rax+10h], rbp
0x14005d1a2  mov     rbp, rcx
0x14005d1a5  cmp     [rbx], sil
0x14005d1a8  jz      loc_14005D338
0x14005d1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d1b5  lea     rdi, WPP_GLOBAL_Control
0x14005d1bc  mov     [rax+18h], r12
0x14005d1c0  cmp     rcx, rdi
0x14005d1c3  jz      short loc_14005D1EF
0x14005d1c5  test    dword ptr [rcx+2Ch], 100h
0x14005d1cc  mov     r12, [rbx+30h]
0x14005d1d0  jnz     loc_14005D48A
0x14005d1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d1dd  cmp     rcx, rdi
0x14005d1e0  jz      short loc_14005D1EF
0x14005d1e2  test    dword ptr [rcx+2Ch], 100h
0x14005d1e9  jnz     loc_14005D4B1
0x14005d1ef  mov     rdx, [rbx+30h]
0x14005d1f3  test    rdx, rdx
0x14005d1f6  jz      short loc_14005D25D
0x14005d1f8  lea     rcx, [r15+1A0h]
0x14005d1ff  call    GetDictionaryEntry
0x14005d204  mov     rbx, rax
0x14005d207  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d20e  cmp     rcx, rdi
0x14005d211  jz      short loc_14005D220
0x14005d213  test    dword ptr [rcx+2Ch], 100h
0x14005d21a  jnz     loc_14005D4D8
0x14005d220  test    rbx, rbx
0x14005d223  jz      short loc_14005D25D
0x14005d225  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d22c  cmp     rcx, rdi
0x14005d22f  jz      short loc_14005D23E
0x14005d231  test    dword ptr [rcx+2Ch], 100h
0x14005d238  jnz     loc_14005D4FF
0x14005d23e  mov     rcx, rbx
0x14005d241  call    ClasspCleanupProtectedLocks
0x14005d246  mov     rcx, rbx
0x14005d249  call    ClasspCleanupDisableMcn
0x14005d24e  mov     rdx, rbx
0x14005d251  lea     rcx, [r15+1A0h]
0x14005d258  call    FreeDictionaryEntry
0x14005d25d  mov     r12, [rsp+78h+arg_10]
0x14005d265  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d26c  cmp     rcx, rdi
0x14005d26f  jz      short loc_14005D27E
0x14005d271  test    dword ptr [rcx+2Ch], 100h
0x14005d278  jnz     loc_14005D523
0x14005d27e  mov     rbp, [rsp+78h+arg_8]
0x14005d286  test    esi, esi
0x14005d288  js      loc_14005D3FA
0x14005d28e  xorps   xmm0, xmm0
0x14005d291  lea     rcx, [rsp+78h+Event]; Event
0x14005d296  xor     eax, eax
0x14005d298  xor     r8d, r8d; State
0x14005d29b  mov     edx, 1; Type
0x14005d2a0  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x14005d2a5  movups  xmmword ptr [rsp+78h+Event.Header.___u0], xmm0
0x14005d2aa  call    cs:__imp_KeInitializeEvent
0x14005d2b1  nop     dword ptr [rax+rax+00h]
0x14005d2b6  mov     rax, [r14+0B8h]
0x14005d2bd  lea     rcx, ClassSignalCompletion
0x14005d2c4  mov     rdx, r14; Irp
0x14005d2c7  movups  xmm0, xmmword ptr [rax]
0x14005d2ca  movups  xmmword ptr [rax-48h], xmm0
0x14005d2ce  movups  xmm1, xmmword ptr [rax+10h]
0x14005d2d2  movups  xmmword ptr [rax-38h], xmm1
0x14005d2d6  movups  xmm0, xmmword ptr [rax+20h]
0x14005d2da  movups  xmmword ptr [rax-28h], xmm0
0x14005d2de  movsd   xmm1, qword ptr [rax+30h]
0x14005d2e3  movsd   qword ptr [rax-18h], xmm1
0x14005d2e8  mov     byte ptr [rax-45h], 0
0x14005d2ec  mov     rax, [r14+0B8h]
0x14005d2f3  mov     [rax-10h], rcx
0x14005d2f7  lea     rcx, [rsp+78h+Event]
0x14005d2fc  mov     [rax-8], rcx
0x14005d300  mov     byte ptr [rax-45h], 0E0h
0x14005d304  mov     rcx, [r15+10h]; DeviceObject
0x14005d308  call    cs:__imp_IofCallDriver
0x14005d30f  nop     dword ptr [rax+rax+00h]
0x14005d314  mov     ebx, eax
0x14005d316  cmp     eax, 103h
0x14005d31b  jz      loc_14005D554
0x14005d321  test    ebx, ebx
0x14005d323  js      loc_14005D57F
0x14005d329  mov     eax, ebx
0x14005d32b  add     rsp, 50h
0x14005d32f  pop     r15
0x14005d331  pop     r14
0x14005d333  pop     rdi
0x14005d334  pop     rsi
0x14005d335  pop     rbx
0x14005d336  retn
0x14005d338  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d33f  lea     rdi, WPP_GLOBAL_Control
0x14005d346  cmp     rcx, rdi
0x14005d349  jz      short loc_14005D39E
0x14005d34b  test    dword ptr [rcx+2Ch], 100h
0x14005d352  mov     [rsp+78h+arg_18], r13
0x14005d35a  mov     r13, [rbx+8]
0x14005d35e  jnz     loc_14005D401
0x14005d364  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d36b  cmp     rcx, rdi
0x14005d36e  jz      short loc_14005D396
0x14005d370  test    dword ptr [rcx+2Ch], 100h
0x14005d377  jnz     loc_14005D428
0x14005d37d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d384  cmp     rcx, rdi
0x14005d387  jz      short loc_14005D396
0x14005d389  test    dword ptr [rcx+2Ch], 100h
0x14005d390  jnz     loc_14005D450
0x14005d396  mov     r13, [rsp+78h+arg_18]
0x14005d39e  mov     rdx, [rbx+30h]
0x14005d3a2  test    rdx, rdx
0x14005d3a5  jz      loc_14005D265
0x14005d3ab  lea     rax, [rsp+78h+arg_0]
0x14005d3b3  mov     [rsp+78h+arg_0], rsi
0x14005d3bb  lea     rcx, [r15+1A0h]
0x14005d3c2  mov     [rsp+78h+Timeout], rax
0x14005d3c7  call    AllocateDictionaryEntry
0x14005d3cc  mov     esi, eax
0x14005d3ce  test    eax, eax
0x14005d3d0  js      loc_14005D478
0x14005d3d6  mov     rdx, [rsp+78h+arg_0]
0x14005d3de  xorps   xmm0, xmm0
0x14005d3e1  xor     eax, eax
0x14005d3e3  movups  xmmword ptr [rdx], xmm0
0x14005d3e6  mov     [rdx+10h], rax
0x14005d3ea  mov     rcx, [rbx+30h]
0x14005d3ee  mov     [rdx], rcx
0x14005d3f1  mov     [rdx+8], rbp
0x14005d3f5  jmp     loc_14005D265
0x14005d3fa  mov     eax, esi
0x14005d3fc  jmp     loc_14005D32B
0x14005d401  cmp     byte ptr [rcx+29h], 4
0x14005d405  jb      loc_14005D364
0x14005d40b  mov     rcx, [rcx+18h]
0x14005d40f  lea     r8, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids
0x14005d416  mov     edx, 0Ah
0x14005d41b  mov     r9, rbp
0x14005d41e  call    WPP_SF_q
0x14005d423  jmp     loc_14005D364
0x14005d428  cmp     byte ptr [rcx+29h], 4
0x14005d42c  jb      loc_14005D37D
0x14005d432  mov     r9d, [r13+10h]
0x14005d436  lea     r8, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids
0x14005d43d  mov     rcx, [rcx+18h]
0x14005d441  mov     edx, 0Bh
0x14005d446  call    WPP_SF_d
0x14005d44b  jmp     loc_14005D37D
0x14005d450  cmp     byte ptr [rcx+29h], 4
0x14005d454  jb      loc_14005D396
0x14005d45a  mov     r9, [rbx+30h]
0x14005d45e  lea     r8, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids
0x14005d465  mov     rcx, [rcx+18h]
0x14005d469  mov     edx, 0Ch
0x14005d46e  call    WPP_SF_q
0x14005d473  jmp     loc_14005D396
0x14005d478  cmp     eax, 0C0000035h
0x14005d47d  jnz     loc_14005D265
0x14005d483  xor     esi, esi
0x14005d485  jmp     loc_14005D265
0x14005d48a  cmp     byte ptr [rcx+29h], 4
0x14005d48e  jb      loc_14005D1D6
0x14005d494  mov     rcx, [rcx+18h]
0x14005d498  lea     r8, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids
0x14005d49f  mov     edx, 0Dh
0x14005d4a4  mov     r9, rbp
0x14005d4a7  call    WPP_SF_q
0x14005d4ac  jmp     loc_14005D1D6
0x14005d4b1  cmp     byte ptr [rcx+29h], 4
0x14005d4b5  jb      loc_14005D1EF
0x14005d4bb  mov     rcx, [rcx+18h]
0x14005d4bf  lea     r8, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids
0x14005d4c6  mov     edx, 0Eh
0x14005d4cb  mov     r9, r12
0x14005d4ce  call    WPP_SF_q
0x14005d4d3  jmp     loc_14005D1EF
0x14005d4d8  cmp     byte ptr [rcx+29h], 4
0x14005d4dc  jb      loc_14005D220
0x14005d4e2  mov     rcx, [rcx+18h]
0x14005d4e6  lea     r8, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids
0x14005d4ed  mov     edx, 0Fh
0x14005d4f2  mov     r9, rbx
0x14005d4f5  call    WPP_SF_q
0x14005d4fa  jmp     loc_14005D220
0x14005d4ff  cmp     byte ptr [rcx+29h], 4
0x14005d503  jb      loc_14005D23E
0x14005d509  mov     rcx, [rcx+18h]
0x14005d50d  lea     r8, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids
0x14005d514  mov     edx, 10h
0x14005d519  call    WPP_SF_
0x14005d51e  jmp     loc_14005D23E
0x14005d523  cmp     byte ptr [rcx+29h], 4
0x14005d527  jb      loc_14005D27E
0x14005d52d  mov     rcx, [rcx+18h]
0x14005d531  lea     rax, aFailed_0; "FAILED"
0x14005d538  test    esi, esi
0x14005d53a  mov     [rsp+78h+Timeout], rbp
0x14005d53f  lea     r9, aSuccess; "Success"
0x14005d546  cmovs   r9, rax
0x14005d54a  call    WPP_SF_sq
0x14005d54f  jmp     loc_14005D27E
0x14005d554  xor     r9d, r9d; Alertable
0x14005d557  mov     [rsp+78h+Timeout], 0; Timeout
0x14005d560  xor     r8d, r8d; WaitMode
0x14005d563  lea     rcx, [rsp+78h+Event]; Object
0x14005d568  xor     edx, edx; WaitReason
0x14005d56a  call    cs:__imp_KeWaitForSingleObject
0x14005d571  nop     dword ptr [rax+rax+00h]
0x14005d576  mov     ebx, [r14+30h]
0x14005d57a  jmp     loc_14005D321
0x14005d57f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d586  cmp     rcx, rdi
0x14005d589  jz      loc_14005D329
0x14005d58f  test    dword ptr [rcx+2Ch], 100h
0x14005d596  jz      loc_14005D329
0x14005d59c  cmp     byte ptr [rcx+29h], 2
0x14005d5a0  jb      loc_14005D329
0x14005d5a6  mov     rcx, [rcx+18h]
0x14005d5aa  lea     r8, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids
0x14005d5b1  mov     edx, 12h
0x14005d5b6  call    WPP_SF_
0x14005d5bb  jmp     loc_14005D329
```

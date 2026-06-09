# SecOpenFileAndRequestOplock

- ea: `0x140029388`
- end: `0x140029596`
- name: `SecOpenFileAndRequestOplock`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400223a4`

## callees

- `0x140005980`
- `0x14001041f`
- `0x14001042b`
- `0x1400104af`
- `0x140011650`
- `0x140029388`
- `0x1400298fc`
- `0x14003d898`

## import_xrefs

- `ntoskrnl!ZwDuplicateObject` at `0x1400294af`
- `ntoskrnl!ZwDuplicateObject` at `0x1400294af`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400293ed`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140029415`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14002946a`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140029514`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400293ed`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140029415`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14002946a`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140029514`
- `ntoskrnl!ZwClose` at `0x1400294ff`
- `ntoskrnl!ZwClose` at `0x1400294ff`
- `ntoskrnl!ObfDereferenceObject` at `0x1400294ea`
- `ntoskrnl!ObfDereferenceObject` at `0x1400294ea`

## pseudocode

```c
__int64 __fastcall SecOpenFileAndRequestOplock(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        void **a6)
{
  NTSTATUS v8; // esi
  NTSTATUS v9; // r15d
  char v10; // di
  NTSTATUS v11; // ebx
  int v15; // [rsp+58h] [rbp-41h]
  HANDLE SourceHandle; // [rsp+60h] [rbp-39h] BYREF
  void *TargetHandle; // [rsp+68h] [rbp-31h] BYREF
  PVOID Object; // [rsp+70h] [rbp-29h] BYREF
  __int64 v20; // [rsp+78h] [rbp-21h] BYREF
  __int64 v21; // [rsp+80h] [rbp-19h] BYREF
  __int64 v22; // [rsp+88h] [rbp-11h] BYREF

  *a6 = 0;
  v8 = 0;
  v9 = 0;
  SourceHandle = 0;
  TargetHandle = 0;
  Object = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  KeQuerySystemTimePrecise(&v22);
  FltAcquirePushLockExclusiveEx_0((char *)SecData + 1304, 0);
  v10 = 1;
  KeQuerySystemTimePrecise(&v21);
  v15 = SecOpenFileObject(a1, a2, a3, a4, &SourceHandle, &Object);
  v11 = v15;
  if ( v15 >= 0 )
  {
    v11 = SecRequestOplockOnFile(SourceHandle, a5);
    v8 = v11;
    if ( v11 >= 0 )
    {
      KeQuerySystemTimePrecise(&v20);
      FltReleasePushLockEx_0((char *)SecData + 1304, 0);
      v10 = 0;
      v11 = ZwDuplicateObject(
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              SourceHandle,
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              &TargetHandle,
              0,
              0,
              2u);
      v9 = v11;
      if ( v11 >= 0 )
      {
        *a6 = TargetHandle;
        TargetHandle = 0;
      }
    }
  }
  if ( SourceHandle )
    FltClose_0(SourceHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( TargetHandle )
    ZwClose(TargetHandle);
  if ( v10 )
  {
    KeQuerySystemTimePrecise(&v20);
    FltReleasePushLockEx_0((char *)SecData + 1304, 0);
  }
  SecSendOpenFileAndAcquireOplockEvent(a1, a2, a3, a4, v22, v21, v20, v8, v15, v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140029388  push    rbp
0x14002938a  push    rbx
0x14002938b  push    rsi
0x14002938c  push    rdi
0x14002938d  push    r12
0x14002938f  push    r13
0x140029391  push    r14
0x140029393  push    r15
0x140029395  lea     rbp, [rsp-0Fh]
0x14002939a  sub     rsp, 0A8h
0x1400293a1  mov     rax, cs:__security_cookie
0x1400293a8  xor     rax, rsp
0x1400293ab  mov     [rbp+47h+var_50], rax
0x1400293af  mov     r14, [rbp+47h+arg_28]
0x1400293b3  xor     eax, eax
0x1400293b5  mov     r12, [rbp+47h+arg_20]
0x1400293b9  mov     r13, rcx
0x1400293bc  lea     rcx, [rbp+47h+var_58]
0x1400293c0  mov     [rbp+47h+var_90], r9d
0x1400293c4  mov     [rbp+47h+var_8C], r8d
0x1400293c8  mov     ebx, edx
0x1400293ca  mov     [r14], rax
0x1400293cd  mov     esi, eax
0x1400293cf  mov     [rbp+47h+var_84], edx
0x1400293d2  mov     r15d, eax
0x1400293d5  mov     [rbp+47h+SourceHandle], rax
0x1400293d9  mov     [rbp+47h+TargetHandle], rax
0x1400293dd  mov     [rbp+47h+Object], rax
0x1400293e1  mov     [rbp+47h+var_58], rax
0x1400293e5  mov     [rbp+47h+var_60], rax
0x1400293e9  mov     [rbp+47h+var_68], rax
0x1400293ed  call    cs:__imp_KeQuerySystemTimePrecise
0x1400293f4  nop     dword ptr [rax+rax+00h]
0x1400293f9  mov     rcx, cs:SecData
0x140029400  xor     edx, edx
0x140029402  add     rcx, 518h
0x140029409  call    FltAcquirePushLockExclusiveEx_0
0x14002940e  lea     rcx, [rbp+47h+var_60]
0x140029412  mov     dil, 1
0x140029415  call    cs:__imp_KeQuerySystemTimePrecise
0x14002941c  nop     dword ptr [rax+rax+00h]
0x140029421  mov     r9d, [rbp+47h+var_90]
0x140029425  lea     rax, [rbp+47h+Object]
0x140029429  mov     r8d, [rbp+47h+var_8C]
0x14002942d  mov     edx, ebx
0x14002942f  mov     qword ptr [rsp+0E0h+HandleAttributes], rax
0x140029434  mov     rcx, r13
0x140029437  lea     rax, [rbp+47h+SourceHandle]
0x14002943b  mov     qword ptr [rsp+0E0h+DesiredAccess], rax
0x140029440  call    SecOpenFileObject
0x140029445  mov     [rbp+47h+var_88], eax
0x140029448  mov     ebx, eax
0x14002944a  test    eax, eax
0x14002944c  js      loc_1400294D3
0x140029452  mov     rcx, [rbp+47h+SourceHandle]
0x140029456  mov     rdx, r12
0x140029459  call    SecRequestOplockOnFile
0x14002945e  mov     ebx, eax
0x140029460  mov     esi, eax
0x140029462  test    eax, eax
0x140029464  js      short loc_1400294D3
0x140029466  lea     rcx, [rbp+47h+var_68]
0x14002946a  call    cs:__imp_KeQuerySystemTimePrecise
0x140029471  nop     dword ptr [rax+rax+00h]
0x140029476  mov     rcx, cs:SecData
0x14002947d  xor     edx, edx
0x14002947f  add     rcx, 518h
0x140029486  call    FltReleasePushLockEx_0
0x14002948b  mov     rdx, [rbp+47h+SourceHandle]; SourceHandle
0x14002948f  lea     r9, [rbp+47h+TargetHandle]; TargetHandle
0x140029493  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x140029497  mov     [rsp+0E0h+Options], 2; Options
0x14002949f  mov     r8, rcx; TargetProcessHandle
0x1400294a2  mov     [rsp+0E0h+HandleAttributes], r15d; HandleAttributes
0x1400294a7  xor     dil, dil
0x1400294aa  mov     [rsp+0E0h+DesiredAccess], r15d; DesiredAccess
0x1400294af  call    cs:__imp_ZwDuplicateObject
0x1400294b6  nop     dword ptr [rax+rax+00h]
0x1400294bb  mov     ebx, eax
0x1400294bd  mov     r15d, eax
0x1400294c0  test    eax, eax
0x1400294c2  js      short loc_1400294D3
0x1400294c4  mov     rax, [rbp+47h+TargetHandle]
0x1400294c8  mov     [r14], rax
0x1400294cb  mov     [rbp+47h+TargetHandle], 0
0x1400294d3  mov     rcx, [rbp+47h+SourceHandle]; FileHandle
0x1400294d7  test    rcx, rcx
0x1400294da  jz      short loc_1400294E1
0x1400294dc  call    FltClose_0
0x1400294e1  mov     rcx, [rbp+47h+Object]; Object
0x1400294e5  test    rcx, rcx
0x1400294e8  jz      short loc_1400294F6
0x1400294ea  call    cs:__imp_ObfDereferenceObject
0x1400294f1  nop     dword ptr [rax+rax+00h]
0x1400294f6  mov     rcx, [rbp+47h+TargetHandle]; Handle
0x1400294fa  test    rcx, rcx
0x1400294fd  jz      short loc_14002950B
0x1400294ff  call    cs:__imp_ZwClose
0x140029506  nop     dword ptr [rax+rax+00h]
0x14002950b  test    dil, dil
0x14002950e  jz      short loc_140029535
0x140029510  lea     rcx, [rbp+47h+var_68]
0x140029514  call    cs:__imp_KeQuerySystemTimePrecise
0x14002951b  nop     dword ptr [rax+rax+00h]
0x140029520  mov     rcx, cs:SecData
0x140029527  xor     edx, edx
0x140029529  add     rcx, 518h
0x140029530  call    FltReleasePushLockEx_0
0x140029535  mov     eax, [rbp+47h+var_88]
0x140029538  mov     rcx, r13
0x14002953b  mov     r9d, [rbp+47h+var_90]
0x14002953f  mov     r8d, [rbp+47h+var_8C]
0x140029543  mov     edx, [rbp+47h+var_84]
0x140029546  mov     [rsp+0E0h+var_98], r15d
0x14002954b  mov     [rsp+0E0h+var_A0], eax
0x14002954f  mov     rax, [rbp+47h+var_68]
0x140029553  mov     [rsp+0E0h+var_A8], esi
0x140029557  mov     qword ptr [rsp+0E0h+Options], rax
0x14002955c  mov     rax, [rbp+47h+var_60]
0x140029560  mov     qword ptr [rsp+0E0h+HandleAttributes], rax
0x140029565  mov     rax, [rbp+47h+var_58]
0x140029569  mov     qword ptr [rsp+0E0h+DesiredAccess], rax
0x14002956e  call    SecSendOpenFileAndAcquireOplockEvent
0x140029573  mov     eax, ebx
0x140029575  mov     rcx, [rbp+47h+var_50]
0x140029579  xor     rcx, rsp; StackCookie
0x14002957c  call    __security_check_cookie
0x140029581  add     rsp, 0A8h
0x140029588  pop     r15
0x14002958a  pop     r14
0x14002958c  pop     r13
0x14002958e  pop     r12
0x140029590  pop     rdi
0x140029591  pop     rsi
0x140029592  pop     rbx
0x140029593  pop     rbp
0x140029594  retn
```

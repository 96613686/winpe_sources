# PCW_USER_REGISTRATION::SendNotificationToRegistration(PCW_NOTIFICATION *)

- ea: `0x14000c910`
- end: `0x14000ca51`
- name: `?SendNotificationToRegistration@PCW_USER_REGISTRATION@@QEAAJPEAVPCW_NOTIFICATION@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(PCW_USER_REGISTRATION *__hidden this, struct PCW_NOTIFICATION *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c460`
- `0x14000c5e0`

## callees

- `0x14000bfd4`
- `0x14000c910`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c92e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c92e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ca2f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ca2f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c940`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c940`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ca23`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ca23`
- `ntoskrnl!ExAllocatePool2` at `0x14000c992`
- `ntoskrnl!ExAllocatePool2` at `0x14000c992`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9e1`

## pseudocode

```c
__int64 __fastcall PCW_USER_REGISTRATION::SendNotificationToRegistration(
        PCW_USER_REGISTRATION *this,
        struct PCW_NOTIFICATION *a2)
{
  char v2; // bp
  unsigned int v5; // ebx
  __int64 Pool2; // rax
  PCW_USER_REGISTRATION *v7; // rdi
  volatile signed __int32 *v8; // rcx
  PCW_USER_REGISTRATION **v9; // rcx
  PVOID P; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  LODWORD(P) = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx((char *)this + 32, 0);
  if ( !*((_BYTE *)this + 93) )
  {
    if ( *((_BYTE *)this + 95) )
    {
      Pool2 = ExAllocatePool2(256, 24, 1316447056);
      v7 = (PCW_USER_REGISTRATION *)Pool2;
      if ( Pool2 )
      {
        if ( a2 )
          _InterlockedIncrement((volatile signed __int32 *)a2 + 19);
        v8 = 0;
        *(_OWORD *)Pool2 = 0;
        *(_QWORD *)(Pool2 + 16) = a2;
        v2 = 1;
      }
      else
      {
        v8 = (volatile signed __int32 *)P;
        v7 = 0;
      }
      if ( (v2 & 1) != 0 && v8 && _InterlockedExchangeAdd(v8 + 19, 0xFFFFFFFF) == 1 )
        ExFreePoolWithTag((PVOID)v8, 0);
      if ( !v7 )
      {
        v5 = -1073741670;
        goto LABEL_22;
      }
      v9 = (PCW_USER_REGISTRATION **)*((_QWORD *)this + 9);
      if ( *v9 != (PCW_USER_REGISTRATION *)((char *)this + 64) )
        __fastfail(3u);
      *(_QWORD *)v7 = (char *)this + 64;
      *((_QWORD *)v7 + 1) = v9;
      *v9 = v7;
      *((_QWORD *)this + 9) = v7;
    }
    else
    {
      if ( a2 )
        _InterlockedIncrement((volatile signed __int32 *)a2 + 19);
      P = a2;
      PCW_USER_REGISTRATION::DeliverNotification((__int64)this, (volatile signed __int32 **)&P);
    }
    v5 = 0;
    goto LABEL_22;
  }
  v5 = -1073741436;
LABEL_22:
  ExReleasePushLockExclusiveEx((char *)this + 32, 0);
  KeLeaveCriticalRegion();
  return v5;
}

```

## disassembly

```asm
0x14000c910  mov     [rsp+arg_8], rbx
0x14000c915  mov     [rsp+arg_10], rbp
0x14000c91a  push    rsi
0x14000c91b  push    rdi
0x14000c91c  push    r14
0x14000c91e  sub     rsp, 20h
0x14000c922  xor     ebp, ebp
0x14000c924  mov     rbx, rdx
0x14000c927  mov     dword ptr [rsp+38h+P], ebp
0x14000c92b  mov     rsi, rcx
0x14000c92e  call    cs:__imp_KeEnterCriticalRegion
0x14000c935  nop     dword ptr [rax+rax+00h]
0x14000c93a  xor     edx, edx
0x14000c93c  lea     rcx, [rsi+20h]
0x14000c940  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c947  nop     dword ptr [rax+rax+00h]
0x14000c94c  cmp     [rsi+5Dh], bpl
0x14000c950  jz      short loc_14000C95C
0x14000c952  mov     ebx, 0C0000184h
0x14000c957  jmp     loc_14000CA1D
0x14000c95c  cmp     [rsi+5Fh], bpl
0x14000c960  jnz     short loc_14000C982
0x14000c962  test    rbx, rbx
0x14000c965  jz      short loc_14000C96B
0x14000c967  lock inc dword ptr [rbx+4Ch]
0x14000c96b  lea     rdx, [rsp+38h+P]
0x14000c970  mov     [rsp+38h+P], rbx
0x14000c975  mov     rcx, rsi
0x14000c978  call    ?DeliverNotification@PCW_USER_REGISTRATION@@AEAAXV?$unique_ptr@VPCW_NOTIFICATION@@U?$ReleaseDeleter@VPCW_NOTIFICATION@@@@@utl@@@Z; PCW_USER_REGISTRATION::DeliverNotification(utl::unique_ptr<PCW_NOTIFICATION,ReleaseDeleter<PCW_NOTIFICATION>>)
0x14000c97d  jmp     loc_14000CA1B
0x14000c982  mov     edx, 18h
0x14000c987  mov     ecx, 100h
0x14000c98c  mov     r8d, 4E776350h
0x14000c992  call    cs:__imp_ExAllocatePool2
0x14000c999  nop     dword ptr [rax+rax+00h]
0x14000c99e  mov     rdi, rax
0x14000c9a1  test    rax, rax
0x14000c9a4  jz      short loc_14000C9C0
0x14000c9a6  test    rbx, rbx
0x14000c9a9  jz      short loc_14000C9AF
0x14000c9ab  lock inc dword ptr [rbx+4Ch]
0x14000c9af  xor     ecx, ecx
0x14000c9b1  xorps   xmm0, xmm0
0x14000c9b4  movups  xmmword ptr [rax], xmm0
0x14000c9b7  mov     [rax+10h], rbx
0x14000c9bb  lea     ebp, [rcx+1]
0x14000c9be  jmp     short loc_14000C9C7
0x14000c9c0  mov     rcx, [rsp+38h+P]; P
0x14000c9c5  xor     edi, edi
0x14000c9c7  test    bpl, 1
0x14000c9cb  jz      short loc_14000C9ED
0x14000c9cd  test    rcx, rcx
0x14000c9d0  jz      short loc_14000C9ED
0x14000c9d2  or      eax, 0FFFFFFFFh
0x14000c9d5  lock xadd [rcx+4Ch], eax
0x14000c9da  cmp     eax, 1
0x14000c9dd  jnz     short loc_14000C9ED
0x14000c9df  xor     edx, edx; Tag
0x14000c9e1  call    cs:__imp_ExFreePoolWithTag
0x14000c9e8  nop     dword ptr [rax+rax+00h]
0x14000c9ed  test    rdi, rdi
0x14000c9f0  jnz     short loc_14000C9F9
0x14000c9f2  mov     ebx, 0C000009Ah
0x14000c9f7  jmp     short loc_14000CA1D
0x14000c9f9  lea     rax, [rsi+40h]
0x14000c9fd  mov     rcx, [rax+8]
0x14000ca01  cmp     [rcx], rax
0x14000ca04  jz      short loc_14000CA0D
0x14000ca06  mov     ecx, 3
0x14000ca0b  int     29h; Win8: RtlFailFast(ecx)
0x14000ca0d  mov     [rdi], rax
0x14000ca10  mov     [rdi+8], rcx
0x14000ca14  mov     [rcx], rdi
0x14000ca17  mov     [rax+8], rdi
0x14000ca1b  xor     ebx, ebx
0x14000ca1d  xor     edx, edx
0x14000ca1f  lea     rcx, [rsi+20h]
0x14000ca23  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ca2a  nop     dword ptr [rax+rax+00h]
0x14000ca2f  call    cs:__imp_KeLeaveCriticalRegion
0x14000ca36  nop     dword ptr [rax+rax+00h]
0x14000ca3b  mov     rbp, [rsp+38h+arg_10]
0x14000ca40  mov     eax, ebx
0x14000ca42  mov     rbx, [rsp+38h+arg_8]
0x14000ca47  add     rsp, 20h
0x14000ca4b  pop     r14
0x14000ca4d  pop     rdi
0x14000ca4e  pop     rsi
0x14000ca4f  retn
```

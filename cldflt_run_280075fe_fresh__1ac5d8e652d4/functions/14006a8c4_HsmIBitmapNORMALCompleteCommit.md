# HsmIBitmapNORMALCompleteCommit

- ea: `0x14006a8c4`
- end: `0x14006ab84`
- name: `HsmIBitmapNORMALCompleteCommit`
- size: `704`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140069710`

## callees

- `0x140018a84`
- `0x14006a8c4`
- `0x14006b7ec`
- `0x14006b93c`

## import_xrefs

- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x14006aa3e`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x14006aa3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a956`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aa54`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aa7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aafe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab40`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab73`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a956`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aa54`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aa7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aafe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab40`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab73`
- `FLTMGR!FltReleasePushLockEx` at `0x14006a9d4`
- `FLTMGR!FltReleasePushLockEx` at `0x14006a9d4`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006a919`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006a919`

## pseudocode

```c
void __fastcall HsmIBitmapNORMALCompleteCommit(char *Context)
{
  bool v1; // sf
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rax
  void *v7; // rcx
  __int64 v8; // rcx
  PVOID **v9; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rbx
  __int64 v12; // rax
  __int64 i; // rdi
  BASE_MCB *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  PVOID P[3]; // [rsp+40h] [rbp-18h] BYREF

  v1 = *((int *)Context + 6) < 0;
  *(_OWORD *)P = 0;
  if ( !v1 )
  {
    v3 = *((_QWORD *)Context + 19);
    *((_QWORD *)Context + 1) = *(_QWORD *)v3;
    v4 = *(_QWORD *)(v3 + 8);
    *((_QWORD *)Context + 18) = v4;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qisci(
        WPP_GLOBAL_Control->AttachedDevice,
        (*(_DWORD *)(v3 + 24) & 8u) >> 3,
        v4,
        (_DWORD)Context,
        *(_QWORD *)Context,
        (__int64)(Context + 32),
        (*(_DWORD *)(v3 + 24) & 8u) >> 3,
        v4,
        P[0],
        P[1]);
    }
    FltAcquirePushLockExclusiveEx(Context + 48, 0);
    v5 = *((_QWORD *)Context + 19);
    if ( (*(_DWORD *)(v5 + 24) & 8) != 0 )
    {
      *((_DWORD *)Context + 4) |= 0x10u;
      v16 = *(void **)(v5 + 16);
      if ( v16 )
      {
        ExFreePoolWithTag(v16, 0x6D427348u);
        *(_QWORD *)(*((_QWORD *)Context + 19) + 16LL) = 0;
      }
      HsmiBitmapNORMALDeleteOnDisk((unsigned int *)Context);
    }
    v6 = *((_QWORD *)Context + 19);
    v7 = (void *)*((_QWORD *)Context + 7);
    if ( v7 == *(void **)(v6 + 16) )
    {
      *(_QWORD *)(v6 + 16) = 0;
    }
    else
    {
      if ( v7 )
        ExFreePoolWithTag(v7, 0x6D427348u);
      v8 = *((_QWORD *)Context + 19);
      *((_QWORD *)Context + 7) = *(_QWORD *)(v8 + 16);
      *(_QWORD *)(v8 + 16) = 0;
    }
    v9 = (PVOID **)*((_QWORD *)Context + 17);
    *(_OWORD *)P = *((_OWORD *)Context + 8);
    *v9 = P;
    *((_QWORD *)P[0] + 1) = P;
    *((_QWORD *)Context + 17) = Context + 128;
    *((_QWORD *)Context + 16) = Context + 128;
    v10 = *((_QWORD *)Context + 19);
    *((_DWORD *)Context + 4) ^= ((unsigned __int16)*((_DWORD *)Context + 4)
                               ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)(v10 + 24) << 12))
                              & 0x7000;
    if ( v10 )
    {
      v15 = *(void **)(v10 + 16);
      if ( v15 && v15 != *((void **)Context + 7) )
        ExFreePoolWithTag(v15, 0x6D427348u);
      ExFreePoolWithTag(*((PVOID *)Context + 19), 0x63427348u);
      *((_QWORD *)Context + 19) = 0;
    }
    FltReleasePushLockEx(Context + 48, 0);
    if ( (*((_DWORD *)Context + 4) & 0x7000) == 0 )
    {
      HsmiBitmapNORMALCloseOnDisk(Context);
      HsmiBitmapNORMALDeleteOnDisk((unsigned int *)Context);
    }
    while ( 1 )
    {
      v11 = P[0];
      if ( P[0] == P )
        break;
      if ( *((PVOID **)P[0] + 1) != P || (v12 = *(_QWORD *)P[0], *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0]) )
        __fastfail(3u);
      P[0] = *(PVOID *)P[0];
      *(_QWORD *)(v12 + 8) = P;
      for ( i = 0; i != 3; ++i )
      {
        v14 = (BASE_MCB *)v11[i + 2];
        if ( v14 )
        {
          FsRtlUninitializeBaseMcb(v14);
          ExFreePoolWithTag((PVOID)v11[i + 2], 0x634D7348u);
          v11[i + 2] = 0;
        }
      }
      ExFreePoolWithTag(v11, 0x6D427348u);
    }
  }
}

```

## disassembly

```asm
0x14006a8c4  mov     [rsp+arg_0], rbx
0x14006a8c9  push    rdi
0x14006a8ca  sub     rsp, 50h
0x14006a8ce  cmp     dword ptr [rcx+18h], 0
0x14006a8d2  xorps   xmm0, xmm0
0x14006a8d5  movups  xmmword ptr [rsp+58h+P], xmm0
0x14006a8da  mov     rbx, rcx
0x14006a8dd  jl      loc_14006A9FC
0x14006a8e3  mov     rdx, [rcx+98h]
0x14006a8ea  mov     rax, [rdx]
0x14006a8ed  mov     [rcx+8], rax
0x14006a8f1  mov     r8, [rdx+8]
0x14006a8f5  mov     [rcx+90h], r8
0x14006a8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a903  lea     rax, WPP_GLOBAL_Control
0x14006a90a  cmp     rcx, rax
0x14006a90d  jnz     loc_14006AA8B
0x14006a913  xor     edx, edx
0x14006a915  lea     rcx, [rbx+30h]
0x14006a919  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006a920  nop     dword ptr [rax+rax+00h]
0x14006a925  mov     rcx, [rbx+98h]
0x14006a92c  mov     eax, [rcx+18h]
0x14006a92f  test    al, 8
0x14006a931  jnz     loc_14006AB2E
0x14006a937  mov     rax, [rbx+98h]
0x14006a93e  mov     rcx, [rbx+38h]; P
0x14006a942  cmp     rcx, [rax+10h]
0x14006a946  jz      loc_14006AB1A
0x14006a94c  test    rcx, rcx
0x14006a94f  jz      short loc_14006A962
0x14006a951  mov     edx, 6D427348h; Tag
0x14006a956  call    cs:__imp_ExFreePoolWithTag
0x14006a95d  nop     dword ptr [rax+rax+00h]
0x14006a962  mov     rcx, [rbx+98h]
0x14006a969  mov     rax, [rcx+10h]
0x14006a96d  mov     [rbx+38h], rax
0x14006a971  mov     qword ptr [rcx+10h], 0
0x14006a979  lea     rcx, [rbx+80h]
0x14006a980  movups  xmm0, xmmword ptr [rcx]
0x14006a983  mov     rax, [rcx+8]
0x14006a987  lea     rdx, [rsp+58h+P]
0x14006a98c  movups  xmmword ptr [rsp+58h+P], xmm0
0x14006a991  mov     [rax], rdx
0x14006a994  lea     rdx, [rsp+58h+P]
0x14006a999  mov     rax, [rsp+58h+P]
0x14006a99e  mov     [rax+8], rdx
0x14006a9a2  mov     [rcx+8], rcx
0x14006a9a6  mov     [rcx], rcx
0x14006a9a9  mov     ecx, [rbx+10h]
0x14006a9ac  mov     rdx, [rbx+98h]
0x14006a9b3  mov     eax, [rdx+18h]
0x14006a9b6  shl     eax, 0Ch
0x14006a9b9  xor     eax, ecx
0x14006a9bb  and     eax, 7000h
0x14006a9c0  xor     eax, ecx
0x14006a9c2  mov     [rbx+10h], eax
0x14006a9c5  test    rdx, rdx
0x14006a9c8  jnz     loc_14006AAE9
0x14006a9ce  xor     edx, edx
0x14006a9d0  lea     rcx, [rbx+30h]
0x14006a9d4  call    cs:__imp_FltReleasePushLockEx
0x14006a9db  nop     dword ptr [rax+rax+00h]
0x14006a9e0  test    dword ptr [rbx+10h], 7000h
0x14006a9e7  jz      loc_14006AAD4
0x14006a9ed  mov     rbx, [rsp+58h+P]
0x14006a9f2  lea     rax, [rsp+58h+P]
0x14006a9f7  cmp     rbx, rax
0x14006a9fa  jnz     short loc_14006AA08
0x14006a9fc  mov     rbx, [rsp+58h+arg_0]
0x14006aa01  add     rsp, 50h
0x14006aa05  pop     rdi
0x14006aa06  retn
0x14006aa08  lea     rax, [rsp+58h+P]
0x14006aa0d  cmp     [rbx+8], rax
0x14006aa11  jnz     loc_14006AB27
0x14006aa17  mov     rax, [rbx]
0x14006aa1a  cmp     [rax+8], rbx
0x14006aa1e  jnz     loc_14006AB27
0x14006aa24  lea     rcx, [rsp+58h+P]
0x14006aa29  mov     [rsp+58h+P], rax
0x14006aa2e  mov     [rax+8], rcx
0x14006aa32  xor     edi, edi
0x14006aa34  mov     rcx, [rbx+rdi*8+10h]; Mcb
0x14006aa39  test    rcx, rcx
0x14006aa3c  jz      short loc_14006AA69
0x14006aa3e  call    cs:__imp_FsRtlUninitializeBaseMcb
0x14006aa45  nop     dword ptr [rax+rax+00h]
0x14006aa4a  mov     rcx, [rbx+rdi*8+10h]; P
0x14006aa4f  mov     edx, 634D7348h; Tag
0x14006aa54  call    cs:__imp_ExFreePoolWithTag
0x14006aa5b  nop     dword ptr [rax+rax+00h]
0x14006aa60  mov     qword ptr [rbx+rdi*8+10h], 0
0x14006aa69  inc     rdi
0x14006aa6c  cmp     rdi, 3
0x14006aa70  jnz     short loc_14006AA34
0x14006aa72  mov     edx, 6D427348h; Tag
0x14006aa77  mov     rcx, rbx; P
0x14006aa7a  call    cs:__imp_ExFreePoolWithTag
0x14006aa81  nop     dword ptr [rax+rax+00h]
0x14006aa86  jmp     loc_14006A9ED
0x14006aa8b  mov     eax, [rcx+2Ch]
0x14006aa8e  test    al, 1
0x14006aa90  jz      loc_14006A913
0x14006aa96  cmp     byte ptr [rcx+29h], 5
0x14006aa9a  jb      loc_14006A913
0x14006aaa0  mov     edx, [rdx+18h]
0x14006aaa3  lea     rax, [rbx+20h]
0x14006aaa7  mov     rcx, [rcx+18h]
0x14006aaab  and     edx, 8
0x14006aaae  mov     [rsp+58h+var_20], r8
0x14006aab3  mov     r9, rbx
0x14006aab6  shr     edx, 3
0x14006aab9  mov     [rsp+58h+var_28], dl
0x14006aabd  mov     [rsp+58h+var_30], rax
0x14006aac2  mov     rax, [rbx]
0x14006aac5  mov     [rsp+58h+var_38], rax
0x14006aaca  call    WPP_SF_qisci
0x14006aacf  jmp     loc_14006A913
0x14006aad4  mov     rcx, rbx
0x14006aad7  call    HsmiBitmapNORMALCloseOnDisk
0x14006aadc  mov     rcx, rbx; Context
0x14006aadf  call    HsmiBitmapNORMALDeleteOnDisk
0x14006aae4  jmp     loc_14006A9ED
0x14006aae9  mov     rcx, [rdx+10h]; P
0x14006aaed  test    rcx, rcx
0x14006aaf0  jnz     short loc_14006AB68
0x14006aaf2  mov     rcx, [rbx+98h]; P
0x14006aaf9  mov     edx, 63427348h; Tag
0x14006aafe  call    cs:__imp_ExFreePoolWithTag
0x14006ab05  nop     dword ptr [rax+rax+00h]
0x14006ab0a  mov     qword ptr [rbx+98h], 0
0x14006ab15  jmp     loc_14006A9CE
0x14006ab1a  mov     qword ptr [rax+10h], 0
0x14006ab22  jmp     loc_14006A979
0x14006ab27  mov     ecx, 3
0x14006ab2c  int     29h; Win8: RtlFailFast(ecx)
0x14006ab2e  or      dword ptr [rbx+10h], 10h
0x14006ab32  mov     rcx, [rcx+10h]; P
0x14006ab36  test    rcx, rcx
0x14006ab39  jz      short loc_14006AB5B
0x14006ab3b  mov     edx, 6D427348h; Tag
0x14006ab40  call    cs:__imp_ExFreePoolWithTag
0x14006ab47  nop     dword ptr [rax+rax+00h]
0x14006ab4c  mov     rax, [rbx+98h]
0x14006ab53  mov     qword ptr [rax+10h], 0
0x14006ab5b  mov     rcx, rbx; Context
0x14006ab5e  call    HsmiBitmapNORMALDeleteOnDisk
0x14006ab63  jmp     loc_14006A937
0x14006ab68  cmp     rcx, [rbx+38h]
0x14006ab6c  jz      short loc_14006AAF2
0x14006ab6e  mov     edx, 6D427348h; Tag
0x14006ab73  call    cs:__imp_ExFreePoolWithTag
0x14006ab7a  nop     dword ptr [rax+rax+00h]
0x14006ab7f  jmp     loc_14006AAF2
```

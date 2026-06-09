# HsmIBitmapNORMALCompleteCommit

- ea: `0x14006a9e4`
- end: `0x14006aca4`
- name: `HsmIBitmapNORMALCompleteCommit`
- size: `704`
- prototype: `void __fastcall(char *Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140069830`

## callees

- `0x140018b04`
- `0x14006a9e4`
- `0x14006b90c`
- `0x14006ba5c`

## import_xrefs

- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x14006ab5e`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x14006ab5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aa76`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ac1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ac60`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ac93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aa76`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ac1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ac60`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ac93`
- `FLTMGR!FltReleasePushLockEx` at `0x14006aaf4`
- `FLTMGR!FltReleasePushLockEx` at `0x14006aaf4`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006aa39`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006aa39`

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
      HsmiBitmapNORMALDeleteOnDisk(Context);
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
      HsmiBitmapNORMALDeleteOnDisk(Context);
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
0x14006a9e4  mov     [rsp+arg_0], rbx
0x14006a9e9  push    rdi
0x14006a9ea  sub     rsp, 50h
0x14006a9ee  cmp     dword ptr [rcx+18h], 0
0x14006a9f2  xorps   xmm0, xmm0
0x14006a9f5  movups  xmmword ptr [rsp+58h+P], xmm0
0x14006a9fa  mov     rbx, rcx
0x14006a9fd  jl      loc_14006AB1C
0x14006aa03  mov     rdx, [rcx+98h]
0x14006aa0a  mov     rax, [rdx]
0x14006aa0d  mov     [rcx+8], rax
0x14006aa11  mov     r8, [rdx+8]
0x14006aa15  mov     [rcx+90h], r8
0x14006aa1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006aa23  lea     rax, WPP_GLOBAL_Control
0x14006aa2a  cmp     rcx, rax
0x14006aa2d  jnz     loc_14006ABAB
0x14006aa33  xor     edx, edx
0x14006aa35  lea     rcx, [rbx+30h]
0x14006aa39  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006aa40  nop     dword ptr [rax+rax+00h]
0x14006aa45  mov     rcx, [rbx+98h]
0x14006aa4c  mov     eax, [rcx+18h]
0x14006aa4f  test    al, 8
0x14006aa51  jnz     loc_14006AC4E
0x14006aa57  mov     rax, [rbx+98h]
0x14006aa5e  mov     rcx, [rbx+38h]; P
0x14006aa62  cmp     rcx, [rax+10h]
0x14006aa66  jz      loc_14006AC3A
0x14006aa6c  test    rcx, rcx
0x14006aa6f  jz      short loc_14006AA82
0x14006aa71  mov     edx, 6D427348h; Tag
0x14006aa76  call    cs:__imp_ExFreePoolWithTag
0x14006aa7d  nop     dword ptr [rax+rax+00h]
0x14006aa82  mov     rcx, [rbx+98h]
0x14006aa89  mov     rax, [rcx+10h]
0x14006aa8d  mov     [rbx+38h], rax
0x14006aa91  mov     qword ptr [rcx+10h], 0
0x14006aa99  lea     rcx, [rbx+80h]
0x14006aaa0  movups  xmm0, xmmword ptr [rcx]
0x14006aaa3  mov     rax, [rcx+8]
0x14006aaa7  lea     rdx, [rsp+58h+P]
0x14006aaac  movups  xmmword ptr [rsp+58h+P], xmm0
0x14006aab1  mov     [rax], rdx
0x14006aab4  lea     rdx, [rsp+58h+P]
0x14006aab9  mov     rax, [rsp+58h+P]
0x14006aabe  mov     [rax+8], rdx
0x14006aac2  mov     [rcx+8], rcx
0x14006aac6  mov     [rcx], rcx
0x14006aac9  mov     ecx, [rbx+10h]
0x14006aacc  mov     rdx, [rbx+98h]
0x14006aad3  mov     eax, [rdx+18h]
0x14006aad6  shl     eax, 0Ch
0x14006aad9  xor     eax, ecx
0x14006aadb  and     eax, 7000h
0x14006aae0  xor     eax, ecx
0x14006aae2  mov     [rbx+10h], eax
0x14006aae5  test    rdx, rdx
0x14006aae8  jnz     loc_14006AC09
0x14006aaee  xor     edx, edx
0x14006aaf0  lea     rcx, [rbx+30h]
0x14006aaf4  call    cs:__imp_FltReleasePushLockEx
0x14006aafb  nop     dword ptr [rax+rax+00h]
0x14006ab00  test    dword ptr [rbx+10h], 7000h
0x14006ab07  jz      loc_14006ABF4
0x14006ab0d  mov     rbx, [rsp+58h+P]
0x14006ab12  lea     rax, [rsp+58h+P]
0x14006ab17  cmp     rbx, rax
0x14006ab1a  jnz     short loc_14006AB28
0x14006ab1c  mov     rbx, [rsp+58h+arg_0]
0x14006ab21  add     rsp, 50h
0x14006ab25  pop     rdi
0x14006ab26  retn
0x14006ab28  lea     rax, [rsp+58h+P]
0x14006ab2d  cmp     [rbx+8], rax
0x14006ab31  jnz     loc_14006AC47
0x14006ab37  mov     rax, [rbx]
0x14006ab3a  cmp     [rax+8], rbx
0x14006ab3e  jnz     loc_14006AC47
0x14006ab44  lea     rcx, [rsp+58h+P]
0x14006ab49  mov     [rsp+58h+P], rax
0x14006ab4e  mov     [rax+8], rcx
0x14006ab52  xor     edi, edi
0x14006ab54  mov     rcx, [rbx+rdi*8+10h]; Mcb
0x14006ab59  test    rcx, rcx
0x14006ab5c  jz      short loc_14006AB89
0x14006ab5e  call    cs:__imp_FsRtlUninitializeBaseMcb
0x14006ab65  nop     dword ptr [rax+rax+00h]
0x14006ab6a  mov     rcx, [rbx+rdi*8+10h]; P
0x14006ab6f  mov     edx, 634D7348h; Tag
0x14006ab74  call    cs:__imp_ExFreePoolWithTag
0x14006ab7b  nop     dword ptr [rax+rax+00h]
0x14006ab80  mov     qword ptr [rbx+rdi*8+10h], 0
0x14006ab89  inc     rdi
0x14006ab8c  cmp     rdi, 3
0x14006ab90  jnz     short loc_14006AB54
0x14006ab92  mov     edx, 6D427348h; Tag
0x14006ab97  mov     rcx, rbx; P
0x14006ab9a  call    cs:__imp_ExFreePoolWithTag
0x14006aba1  nop     dword ptr [rax+rax+00h]
0x14006aba6  jmp     loc_14006AB0D
0x14006abab  mov     eax, [rcx+2Ch]
0x14006abae  test    al, 1
0x14006abb0  jz      loc_14006AA33
0x14006abb6  cmp     byte ptr [rcx+29h], 5
0x14006abba  jb      loc_14006AA33
0x14006abc0  mov     edx, [rdx+18h]
0x14006abc3  lea     rax, [rbx+20h]
0x14006abc7  mov     rcx, [rcx+18h]
0x14006abcb  and     edx, 8
0x14006abce  mov     [rsp+58h+var_20], r8
0x14006abd3  mov     r9, rbx
0x14006abd6  shr     edx, 3
0x14006abd9  mov     [rsp+58h+var_28], dl
0x14006abdd  mov     [rsp+58h+var_30], rax
0x14006abe2  mov     rax, [rbx]
0x14006abe5  mov     [rsp+58h+var_38], rax
0x14006abea  call    WPP_SF_qisci
0x14006abef  jmp     loc_14006AA33
0x14006abf4  mov     rcx, rbx
0x14006abf7  call    HsmiBitmapNORMALCloseOnDisk
0x14006abfc  mov     rcx, rbx; Context
0x14006abff  call    HsmiBitmapNORMALDeleteOnDisk
0x14006ac04  jmp     loc_14006AB0D
0x14006ac09  mov     rcx, [rdx+10h]; P
0x14006ac0d  test    rcx, rcx
0x14006ac10  jnz     short loc_14006AC88
0x14006ac12  mov     rcx, [rbx+98h]; P
0x14006ac19  mov     edx, 63427348h; Tag
0x14006ac1e  call    cs:__imp_ExFreePoolWithTag
0x14006ac25  nop     dword ptr [rax+rax+00h]
0x14006ac2a  mov     qword ptr [rbx+98h], 0
0x14006ac35  jmp     loc_14006AAEE
0x14006ac3a  mov     qword ptr [rax+10h], 0
0x14006ac42  jmp     loc_14006AA99
0x14006ac47  mov     ecx, 3
0x14006ac4c  int     29h; Win8: RtlFailFast(ecx)
0x14006ac4e  or      dword ptr [rbx+10h], 10h
0x14006ac52  mov     rcx, [rcx+10h]; P
0x14006ac56  test    rcx, rcx
0x14006ac59  jz      short loc_14006AC7B
0x14006ac5b  mov     edx, 6D427348h; Tag
0x14006ac60  call    cs:__imp_ExFreePoolWithTag
0x14006ac67  nop     dword ptr [rax+rax+00h]
0x14006ac6c  mov     rax, [rbx+98h]
0x14006ac73  mov     qword ptr [rax+10h], 0
0x14006ac7b  mov     rcx, rbx; Context
0x14006ac7e  call    HsmiBitmapNORMALDeleteOnDisk
0x14006ac83  jmp     loc_14006AA57
0x14006ac88  cmp     rcx, [rbx+38h]
0x14006ac8c  jz      short loc_14006AC12
0x14006ac8e  mov     edx, 6D427348h; Tag
0x14006ac93  call    cs:__imp_ExFreePoolWithTag
0x14006ac9a  nop     dword ptr [rax+rax+00h]
0x14006ac9f  jmp     loc_14006AC12
```

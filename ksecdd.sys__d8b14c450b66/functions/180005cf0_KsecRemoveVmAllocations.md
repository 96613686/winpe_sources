# KsecRemoveVmAllocations

- ea: `0x180005cf0`
- end: `0x180005e8d`
- name: `KsecRemoveVmAllocations`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800272b0`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180005cf0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180005d21`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005dba`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005d21`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005dba`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180005dcb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180005dcb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180005e5d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180005e5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005dae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005e69`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005dae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005e69`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180005d3e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180005d3e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180005d77`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180005da2`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180005d77`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180005da2`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x180005d8d`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x180005d8d`
- `ntoskrnl!PsIsProtectedProcess` at `0x180005d0d`
- `ntoskrnl!PsIsProtectedProcess` at `0x180005d0d`
- `ntoskrnl!ZwClose` at `0x180005e00`
- `ntoskrnl!ZwClose` at `0x180005e00`

## pseudocode

```c
void __fastcall KsecRemoveVmAllocations(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  unsigned int v4; // ecx
  __int64 v5; // rdi
  unsigned int v6; // ecx
  __int64 v7; // r14
  __int64 v8; // rbp
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // [rsp+68h] [rbp+10h] BYREF

  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v12);
  if ( (unsigned int)PsIsProtectedProcess(a1) )
  {
    KeEnterCriticalRegion();
    v2 = v12;
    v3 = v12 + 568;
    ExAcquirePushLockSharedEx(v12 + 568, 0);
    v4 = *(_DWORD *)(v2 + 576);
    v5 = 0;
    if ( v4 )
    {
      while ( *(_QWORD *)(*(_QWORD *)(v2 + 584) + 40 * v5 + 8) != a1 )
      {
        v5 = (unsigned int)(v5 + 1);
        if ( (unsigned int)v5 >= v4 )
          goto LABEL_5;
      }
    }
    else
    {
LABEL_5:
      if ( (_DWORD)v5 == v4 )
      {
        ExReleasePushLockSharedEx(v3, 0);
LABEL_19:
        KeLeaveCriticalRegion();
        goto LABEL_20;
      }
    }
    if ( !(unsigned __int8)ExTryConvertPushLockSharedToExclusiveEx(v3, 0) )
    {
      ExReleasePushLockSharedEx(v3, 0);
      KeLeaveCriticalRegion();
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v3, 0);
      v5 = 0;
    }
    v6 = *(_DWORD *)(v2 + 576);
    while ( (unsigned int)v5 < v6 )
    {
      v7 = *(_QWORD *)(v2 + 584);
      v8 = 5 * v5;
      if ( *(_QWORD *)(v7 + 40 * v5 + 8) == a1 )
      {
        if ( (*(_DWORD *)(v7 + 40 * v5 + 32) & 1) == 0 )
          ZwClose(*(HANDLE *)(v7 + 40 * v5));
        v9 = (unsigned int)(*(_DWORD *)(v2 + 576) - 1);
        if ( (_DWORD)v5 != (_DWORD)v9 )
        {
          v10 = 5 * v9;
          LODWORD(v5) = v5 - 1;
          v11 = *(_QWORD *)(v2 + 584);
          *(_OWORD *)(v7 + 8 * v8) = *(_OWORD *)(v11 + 8 * v10);
          *(_OWORD *)(v7 + 8 * v8 + 16) = *(_OWORD *)(v11 + 8 * v10 + 16);
          *(_QWORD *)(v7 + 8 * v8 + 32) = *(_QWORD *)(v11 + 8 * v10 + 32);
        }
        v6 = --*(_DWORD *)(v2 + 576);
      }
      v5 = (unsigned int)(v5 + 1);
    }
    ExReleasePushLockExclusiveEx(v3, 0);
    goto LABEL_19;
  }
LABEL_20:
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v12);
}

```

## disassembly

```asm
0x180005cf0  push    rbx
0x180005cf2  push    rbp
0x180005cf3  push    rsi
0x180005cf4  push    rdi
0x180005cf5  push    r14
0x180005cf7  push    r15
0x180005cf9  sub     rsp, 28h
0x180005cfd  mov     r15, rcx
0x180005d00  lea     rcx, [rsp+58h+arg_8]; this
0x180005d05  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180005d0a  mov     rcx, r15
0x180005d0d  call    cs:__imp_PsIsProtectedProcess
0x180005d14  nop     dword ptr [rax+rax+00h]
0x180005d19  test    eax, eax
0x180005d1b  jz      loc_180005E75
0x180005d21  call    cs:__imp_KeEnterCriticalRegion
0x180005d28  nop     dword ptr [rax+rax+00h]
0x180005d2d  mov     rbx, [rsp+58h+arg_8]
0x180005d32  xor     edx, edx
0x180005d34  lea     rsi, [rbx+238h]
0x180005d3b  mov     rcx, rsi
0x180005d3e  call    cs:__imp_ExAcquirePushLockSharedEx
0x180005d45  nop     dword ptr [rax+rax+00h]
0x180005d4a  mov     ecx, [rbx+240h]
0x180005d50  xor     edi, edi
0x180005d52  test    ecx, ecx
0x180005d54  jz      short loc_180005D6E
0x180005d56  mov     r8, [rbx+248h]
0x180005d5d  lea     rdx, [rdi+rdi*4]
0x180005d61  cmp     [r8+rdx*8+8], r15
0x180005d66  jz      short loc_180005D88
0x180005d68  inc     edi
0x180005d6a  cmp     edi, ecx
0x180005d6c  jb      short loc_180005D5D
0x180005d6e  cmp     edi, ecx
0x180005d70  jnz     short loc_180005D88
0x180005d72  xor     edx, edx
0x180005d74  mov     rcx, rsi
0x180005d77  call    cs:__imp_ExReleasePushLockSharedEx
0x180005d7e  nop     dword ptr [rax+rax+00h]
0x180005d83  jmp     loc_180005E69
0x180005d88  xor     edx, edx
0x180005d8a  mov     rcx, rsi
0x180005d8d  call    cs:__imp_ExTryConvertPushLockSharedToExclusiveEx
0x180005d94  nop     dword ptr [rax+rax+00h]
0x180005d99  test    al, al
0x180005d9b  jnz     short loc_180005DD9
0x180005d9d  xor     edx, edx
0x180005d9f  mov     rcx, rsi
0x180005da2  call    cs:__imp_ExReleasePushLockSharedEx
0x180005da9  nop     dword ptr [rax+rax+00h]
0x180005dae  call    cs:__imp_KeLeaveCriticalRegion
0x180005db5  nop     dword ptr [rax+rax+00h]
0x180005dba  call    cs:__imp_KeEnterCriticalRegion
0x180005dc1  nop     dword ptr [rax+rax+00h]
0x180005dc6  xor     edx, edx
0x180005dc8  mov     rcx, rsi
0x180005dcb  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x180005dd2  nop     dword ptr [rax+rax+00h]
0x180005dd7  xor     edi, edi
0x180005dd9  mov     ecx, [rbx+240h]
0x180005ddf  jmp     short loc_180005E54
0x180005de1  mov     r14, [rbx+248h]
0x180005de8  lea     rbp, [rdi+rdi*4]
0x180005dec  cmp     [r14+rbp*8+8], r15
0x180005df1  jnz     short loc_180005E52
0x180005df3  mov     eax, [r14+rbp*8+20h]
0x180005df8  test    al, 1
0x180005dfa  jnz     short loc_180005E0C
0x180005dfc  mov     rcx, [r14+rbp*8]; Handle
0x180005e00  call    cs:__imp_ZwClose
0x180005e07  nop     dword ptr [rax+rax+00h]
0x180005e0c  mov     eax, [rbx+240h]
0x180005e12  dec     eax
0x180005e14  cmp     edi, eax
0x180005e16  jz      short loc_180005E46
0x180005e18  lea     rcx, [rax+rax*4]
0x180005e1c  dec     edi
0x180005e1e  mov     rax, [rbx+248h]
0x180005e25  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180005e29  movups  xmmword ptr [r14+rbp*8], xmm0
0x180005e2e  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x180005e33  movups  xmmword ptr [r14+rbp*8+10h], xmm1
0x180005e39  movsd   xmm0, qword ptr [rax+rcx*8+20h]
0x180005e3f  movsd   qword ptr [r14+rbp*8+20h], xmm0
0x180005e46  dec     dword ptr [rbx+240h]
0x180005e4c  mov     ecx, [rbx+240h]
0x180005e52  inc     edi
0x180005e54  cmp     edi, ecx
0x180005e56  jb      short loc_180005DE1
0x180005e58  xor     edx, edx
0x180005e5a  mov     rcx, rsi
0x180005e5d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180005e64  nop     dword ptr [rax+rax+00h]
0x180005e69  call    cs:__imp_KeLeaveCriticalRegion
0x180005e70  nop     dword ptr [rax+rax+00h]
0x180005e75  lea     rcx, [rsp+58h+arg_8]; this
0x180005e7a  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180005e7f  add     rsp, 28h
0x180005e83  pop     r15
0x180005e85  pop     r14
0x180005e87  pop     rdi
0x180005e88  pop     rsi
0x180005e89  pop     rbp
0x180005e8a  pop     rbx
0x180005e8b  retn
```

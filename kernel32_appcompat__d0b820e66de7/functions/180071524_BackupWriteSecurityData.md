# BackupWriteSecurityData

- ea: `0x180071524`
- end: `0x18007168c`
- name: `BackupWriteSecurityData`
- size: `360`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180070ff0`

## callees

- `0x18000ccf0`
- `0x180055abc`
- `0x180071524`

## import_xrefs

- `ntdll!NtSetSecurityObject` at `0x1800715c2`
- `ntdll!NtSetSecurityObject` at `0x1800715de`
- `ntdll!NtSetSecurityObject` at `0x180071605`
- `ntdll!NtSetSecurityObject` at `0x180071625`
- `ntdll!NtSetSecurityObject` at `0x180071642`
- `ntdll!NtSetSecurityObject` at `0x18007165f`
- `ntdll!NtSetSecurityObject` at `0x1800715c2`
- `ntdll!NtSetSecurityObject` at `0x1800715de`
- `ntdll!NtSetSecurityObject` at `0x180071605`
- `ntdll!NtSetSecurityObject` at `0x180071625`
- `ntdll!NtSetSecurityObject` at `0x180071642`
- `ntdll!NtSetSecurityObject` at `0x18007165f`

## pseudocode

```c
_BOOL8 __fastcall BackupWriteSecurityData(HANDLE Handle, __int64 a2, __int64 a3)
{
  int v6; // eax
  int v7; // eax
  __int64 v9; // r8
  __int16 v10; // dx
  SECURITY_INFORMATION v11; // ebx
  __int64 v12; // rcx
  __int16 v13; // ax
  NTSTATUS v14; // esi
  SECURITY_INFORMATION v15; // ebx
  NTSTATUS v16; // eax

  v6 = BackupWriteBuffer(a2, a3);
  if ( !v6 )
    return 0;
  v7 = v6 - 1;
  if ( v7 )
    return v7 == 1;
  if ( !*(_BYTE *)(a3 + 20) )
    return 1;
  v9 = *(_QWORD *)(a2 + 1088);
  v10 = *(_WORD *)(v9 + 2);
  v11 = v10 & 4 | 0x7B;
  if ( (v10 & 0x10) == 0 )
    v11 = *(_WORD *)(v9 + 2) & 4 | 3;
  if ( (v10 & 0x400) != 0 )
    *(_WORD *)(v9 + 2) = v10 | 0x100;
  v12 = *(_QWORD *)(a2 + 1088);
  v13 = *(_WORD *)(v12 + 2);
  if ( (v13 & 0x800) != 0 )
    *(_WORD *)(v12 + 2) = v13 | 0x200;
  if ( NtSetSecurityObject(Handle, v11 | 0x10000, *(PSECURITY_DESCRIPTOR *)(a2 + 1088)) >= 0 )
    return 1;
  v14 = NtSetSecurityObject(Handle, v11, *(PSECURITY_DESCRIPTOR *)(a2 + 1088));
  if ( v14 >= 0 )
    return 1;
  if ( (v11 & 0x48) != 0 )
    NtSetSecurityObject(Handle, v11 & 0x48, *(PSECURITY_DESCRIPTOR *)(a2 + 1088));
  if ( (v11 & 0x10) != 0 )
    NtSetSecurityObject(Handle, 0x10u, *(PSECURITY_DESCRIPTOR *)(a2 + 1088));
  v15 = v11 & 0x24;
  if ( v15 )
    v14 = NtSetSecurityObject(Handle, v15, *(PSECURITY_DESCRIPTOR *)(a2 + 1088));
  v16 = NtSetSecurityObject(Handle, 3u, *(PSECURITY_DESCRIPTOR *)(a2 + 1088));
  if ( v14 >= 0 )
  {
    if ( v16 >= 0 )
      return 1;
    v14 = v16;
  }
  BaseSetLastNTError((unsigned int)v14);
  return 0;
}

```

## disassembly

```asm
0x180071524  push    rbx
0x180071526  push    rbp
0x180071527  push    rsi
0x180071528  push    rdi
0x180071529  sub     rsp, 28h
0x18007152d  mov     rdi, rdx
0x180071530  mov     rbp, rcx
0x180071533  mov     rcx, rdi
0x180071536  mov     rdx, r8
0x180071539  mov     rbx, r8
0x18007153c  call    BackupWriteBuffer
0x180071541  test    eax, eax
0x180071543  jz      loc_180071680
0x180071549  sub     eax, 1
0x18007154c  jz      short loc_180071558
0x18007154e  cmp     eax, 1
0x180071551  jz      short loc_18007155E
0x180071553  jmp     loc_180071680
0x180071558  cmp     byte ptr [rbx+14h], 0
0x18007155c  jnz     short loc_180071568
0x18007155e  mov     eax, 1
0x180071563  jmp     loc_180071682
0x180071568  mov     r8, [rdi+440h]
0x18007156f  movzx   edx, word ptr [r8+2]
0x180071574  mov     ecx, edx
0x180071576  and     ecx, 4
0x180071579  or      ecx, 3
0x18007157c  mov     ebx, ecx
0x18007157e  or      ebx, 78h
0x180071581  test    dl, 10h
0x180071584  cmovz   ebx, ecx
0x180071587  bt      dx, 0Ah
0x18007158c  jnb     short loc_180071598
0x18007158e  or      dx, 100h
0x180071593  mov     [r8+2], dx
0x180071598  mov     rcx, [rdi+440h]
0x18007159f  movzx   eax, word ptr [rcx+2]
0x1800715a3  bt      ax, 0Bh
0x1800715a8  jnb     short loc_1800715B2
0x1800715aa  or      ax, 200h
0x1800715ae  mov     [rcx+2], ax
0x1800715b2  mov     r8, [rdi+440h]; SecurityDescriptor
0x1800715b9  mov     edx, ebx
0x1800715bb  bts     edx, 10h; SecurityInformation
0x1800715bf  mov     rcx, rbp; Handle
0x1800715c2  call    cs:__imp_NtSetSecurityObject
0x1800715c9  nop     dword ptr [rax+rax+00h]
0x1800715ce  test    eax, eax
0x1800715d0  jns     short loc_18007155E
0x1800715d2  mov     r8, [rdi+440h]; SecurityDescriptor
0x1800715d9  mov     edx, ebx; SecurityInformation
0x1800715db  mov     rcx, rbp; Handle
0x1800715de  call    cs:__imp_NtSetSecurityObject
0x1800715e5  nop     dword ptr [rax+rax+00h]
0x1800715ea  mov     esi, eax
0x1800715ec  test    eax, eax
0x1800715ee  jns     loc_18007155E
0x1800715f4  mov     edx, ebx
0x1800715f6  and     edx, 48h; SecurityInformation
0x1800715f9  jz      short loc_180071611
0x1800715fb  mov     r8, [rdi+440h]; SecurityDescriptor
0x180071602  mov     rcx, rbp; Handle
0x180071605  call    cs:__imp_NtSetSecurityObject
0x18007160c  nop     dword ptr [rax+rax+00h]
0x180071611  test    bl, 10h
0x180071614  jz      short loc_180071631
0x180071616  mov     r8, [rdi+440h]; SecurityDescriptor
0x18007161d  mov     edx, 10h; SecurityInformation
0x180071622  mov     rcx, rbp; Handle
0x180071625  call    cs:__imp_NtSetSecurityObject
0x18007162c  nop     dword ptr [rax+rax+00h]
0x180071631  and     ebx, 24h
0x180071634  jz      short loc_180071650
0x180071636  mov     r8, [rdi+440h]; SecurityDescriptor
0x18007163d  mov     edx, ebx; SecurityInformation
0x18007163f  mov     rcx, rbp; Handle
0x180071642  call    cs:__imp_NtSetSecurityObject
0x180071649  nop     dword ptr [rax+rax+00h]
0x18007164e  mov     esi, eax
0x180071650  mov     r8, [rdi+440h]; SecurityDescriptor
0x180071657  mov     edx, 3; SecurityInformation
0x18007165c  mov     rcx, rbp; Handle
0x18007165f  call    cs:__imp_NtSetSecurityObject
0x180071666  nop     dword ptr [rax+rax+00h]
0x18007166b  test    esi, esi
0x18007166d  js      short loc_180071679
0x18007166f  test    eax, eax
0x180071671  jns     loc_18007155E
0x180071677  mov     esi, eax
0x180071679  mov     ecx, esi
0x18007167b  call    BaseSetLastNTError
0x180071680  xor     eax, eax
0x180071682  add     rsp, 28h
0x180071686  pop     rdi
0x180071687  pop     rsi
0x180071688  pop     rbp
0x180071689  pop     rbx
0x18007168a  retn
```

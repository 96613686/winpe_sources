# NpImpersonate

- ea: `0x1400100bc`
- end: `0x1400101c9`
- name: `NpImpersonate`
- size: `269`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000efb0`

## callees

- `0x14000fb00`
- `0x1400100bc`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010178`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010178`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400101a0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400101a0`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140010157`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140010157`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140010121`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140010121`
- `ntoskrnl!SeImpersonateClientEx` at `0x140010144`
- `ntoskrnl!SeImpersonateClientEx` at `0x140010144`

## pseudocode

```c
__int64 __fastcall NpImpersonate(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rcx
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rcx
  struct _SECURITY_CLIENT_CONTEXT *v8; // rcx
  unsigned int v9; // ebx

  v4 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL);
  if ( **(_WORD **)(v4 + 24) != 514 || (*(_QWORD *)(v4 + 32) & 1) == 0 || (*(_QWORD *)(v4 + 32) & 2) == 0 && !(_DWORD)a3 )
    return 3221225647LL;
  if ( (*(_QWORD *)(v4 + 32) & 1) != 0 )
  {
    v5 = *(_QWORD *)(v4 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
    v6 = v5 + 64;
    v7 = v5 + 64;
    if ( (_DWORD)a3 )
    {
      ExAcquirePushLockExclusiveEx(v7, 0, a3, a4);
      NpFreeClientSecurityContext(*(PVOID *)(v5 + 264));
      *(_QWORD *)(v5 + 264) = -1;
      ExReleasePushLockExclusiveEx(v5 + 64, 0);
      return 0;
    }
    else
    {
      ExAcquirePushLockSharedEx(v7, 0);
      v8 = *(struct _SECURITY_CLIENT_CONTEXT **)(v5 + 264);
      if ( (unsigned __int64)&v8[-1].ClientTokenControl + 43 > 0xFFFFFFFFFFFFFFFDuLL )
        v9 = -1073741555;
      else
        v9 = SeImpersonateClientEx(v8, 0);
      ExReleasePushLockSharedEx(v6, 0);
    }
  }
  else
  {
    return (unsigned int)-1073741649;
  }
  return v9;
}

```

## disassembly

```asm
0x1400100bc  mov     [rsp+arg_0], rbx
0x1400100c1  push    rdi
0x1400100c2  sub     rsp, 20h
0x1400100c6  mov     rax, [rdx+0B8h]
0x1400100cd  mov     edx, 202h
0x1400100d2  mov     rcx, [rax+30h]
0x1400100d6  mov     rax, [rcx+18h]
0x1400100da  cmp     [rax], dx
0x1400100dd  jnz     loc_140010171
0x1400100e3  mov     rax, [rcx+20h]
0x1400100e7  mov     dl, 1
0x1400100e9  test    dl, al
0x1400100eb  jz      loc_140010171
0x1400100f1  mov     rbx, [rcx+20h]
0x1400100f5  mov     rax, [rcx+20h]
0x1400100f9  shr     al, 1
0x1400100fb  test    dl, al
0x1400100fd  jz      loc_1400101B0
0x140010103  mov     rax, [rcx+20h]
0x140010107  test    dl, al
0x140010109  jz      loc_1400101BB
0x14001010f  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140010113  xor     edx, edx
0x140010115  lea     rdi, [rbx+40h]
0x140010119  mov     rcx, rdi
0x14001011c  test    r8d, r8d
0x14001011f  jnz     short loc_140010178
0x140010121  call    cs:__imp_ExAcquirePushLockSharedEx
0x140010128  nop     dword ptr [rax+rax+00h]
0x14001012d  mov     rcx, [rbx+108h]; ClientContext
0x140010134  lea     rax, [rcx-1]
0x140010138  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001013c  ja      loc_1400101C2
0x140010142  xor     edx, edx; ServerThread
0x140010144  call    cs:__imp_SeImpersonateClientEx
0x14001014b  nop     dword ptr [rax+rax+00h]
0x140010150  mov     ebx, eax
0x140010152  xor     edx, edx
0x140010154  mov     rcx, rdi
0x140010157  call    cs:__imp_ExReleasePushLockSharedEx
0x14001015e  nop     dword ptr [rax+rax+00h]
0x140010163  mov     eax, ebx
0x140010165  mov     rbx, [rsp+28h+arg_0]
0x14001016a  add     rsp, 20h
0x14001016e  pop     rdi
0x14001016f  retn
0x140010171  mov     eax, 0C00000AFh
0x140010176  jmp     short loc_140010165
0x140010178  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001017f  nop     dword ptr [rax+rax+00h]
0x140010184  mov     rcx, [rbx+108h]; P
0x14001018b  call    NpFreeClientSecurityContext
0x140010190  xor     edx, edx
0x140010192  mov     qword ptr [rbx+108h], 0FFFFFFFFFFFFFFFFh
0x14001019d  mov     rcx, rdi
0x1400101a0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400101a7  nop     dword ptr [rax+rax+00h]
0x1400101ac  xor     ebx, ebx
0x1400101ae  jmp     short loc_140010163
0x1400101b0  test    r8d, r8d
0x1400101b3  jnz     loc_140010103
0x1400101b9  jmp     short loc_140010171
0x1400101bb  mov     ebx, 0C00000AFh
0x1400101c0  jmp     short loc_140010163
0x1400101c2  mov     ebx, 0C000010Dh
0x1400101c7  jmp     short loc_140010152
```

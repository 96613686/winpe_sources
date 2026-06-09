# Smb2ShareFlushAndPurge

- ea: `0x140051af4`
- end: `0x140051bf9`
- name: `Smb2ShareFlushAndPurge`
- size: `261`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001cc00`

## callees

- `0x140051af4`

## import_xrefs

- `ntoskrnl!SeExports` at `0x140051b3a`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140051b4b`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140051b4b`
- `rdbss!RxForceScavengerToRun` at `0x140051bc7`
- `rdbss!RxForceScavengerToRun` at `0x140051bc7`

## pseudocode

```c
__int64 __fastcall Smb2ShareFlushAndPurge(__int64 a1)
{
  __int64 v1; // rax
  __int64 v4; // rax
  KPROCESSOR_MODE v5; // dl
  unsigned int v6; // eax
  __int64 v7; // rdx
  int v8; // eax

  v1 = *(_QWORD *)(a1 + 80);
  *(_QWORD *)(a1 + 184) = 0;
  if ( (*(_BYTE *)(v1 + 1314) & 4) == 0 )
    return 3221225659LL;
  v4 = *(_QWORD *)(a1 + 40);
  v5 = v4 && (*(_BYTE *)(v4 + 64) || *(_BYTE *)(a1 + 33) != 4);
  if ( !SeSinglePrivilegeCheck(SeExports->SeManageVolumePrivilege, v5) )
    return 3221225569LL;
  v6 = *(_DWORD *)(a1 + 568);
  if ( !v6 )
    goto LABEL_15;
  if ( v6 < 2 )
    return 3221225476LL;
  if ( **(_WORD **)(a1 + 552) != 2 )
    return 3221225560LL;
LABEL_15:
  v7 = *(_QWORD *)(a1 + 56);
  if ( (unsigned __int16)(*(_WORD *)v7 + 5359) > 1u && (*(_WORD *)v7 & 0xFFF0) != 0xEC20 )
    return 3221225508LL;
  v8 = RxForceScavengerToRun(*(_QWORD *)(a1 + 80), *(_QWORD *)(v7 + 120));
  if ( *(_DWORD *)(a1 + 572) >= 4u )
  {
    **(_DWORD **)(a1 + 560) = v8;
    *(_QWORD *)(a1 + 184) = 4;
  }
  return 0;
}

```

## disassembly

```asm
0x140051af4  push    rbx
0x140051af6  sub     rsp, 20h
0x140051afa  mov     rax, [rcx+50h]
0x140051afe  mov     rbx, rcx
0x140051b01  mov     qword ptr [rcx+0B8h], 0
0x140051b0c  test    byte ptr [rax+522h], 4
0x140051b13  jnz     short loc_140051B1F
0x140051b15  mov     eax, 0C00000BBh
0x140051b1a  jmp     loc_140051BF2
0x140051b1f  mov     rax, [rcx+28h]
0x140051b23  test    rax, rax
0x140051b26  jz      short loc_140051B38
0x140051b28  cmp     byte ptr [rax+40h], 0
0x140051b2c  jnz     short loc_140051B34
0x140051b2e  cmp     byte ptr [rcx+21h], 4
0x140051b32  jz      short loc_140051B38
0x140051b34  mov     dl, 1
0x140051b36  jmp     short loc_140051B3A
0x140051b38  xor     dl, dl; PreviousMode
0x140051b3a  mov     rax, cs:__imp_SeExports
0x140051b41  mov     rcx, [rax]
0x140051b44  mov     rcx, [rcx+190h]; PrivilegeValue
0x140051b4b  call    cs:__imp_SeSinglePrivilegeCheck
0x140051b52  nop     dword ptr [rax+rax+00h]
0x140051b57  test    al, al
0x140051b59  jnz     short loc_140051B65
0x140051b5b  mov     eax, 0C0000061h
0x140051b60  jmp     loc_140051BF2
0x140051b65  mov     eax, [rbx+238h]
0x140051b6b  test    eax, eax
0x140051b6d  jz      short loc_140051B92
0x140051b6f  mov     ecx, 2
0x140051b74  cmp     eax, ecx
0x140051b76  jnb     short loc_140051B7F
0x140051b78  mov     eax, 0C0000004h
0x140051b7d  jmp     short loc_140051BF2
0x140051b7f  mov     rax, [rbx+228h]
0x140051b86  cmp     [rax], cx
0x140051b89  jz      short loc_140051B92
0x140051b8b  mov     eax, 0C0000058h
0x140051b90  jmp     short loc_140051BF2
0x140051b92  mov     rdx, [rbx+38h]
0x140051b96  mov     eax, 14EFh
0x140051b9b  movzx   ecx, word ptr [rdx]
0x140051b9e  add     eax, ecx
0x140051ba0  cmp     ax, 1
0x140051ba4  jbe     short loc_140051BBF
0x140051ba6  mov     eax, 0FFF0h
0x140051bab  and     cx, ax
0x140051bae  mov     eax, 0EC20h
0x140051bb3  cmp     cx, ax
0x140051bb6  jz      short loc_140051BBF
0x140051bb8  mov     eax, 0C0000024h
0x140051bbd  jmp     short loc_140051BF2
0x140051bbf  mov     rdx, [rdx+78h]
0x140051bc3  mov     rcx, [rbx+50h]
0x140051bc7  call    cs:__imp_RxForceScavengerToRun
0x140051bce  nop     dword ptr [rax+rax+00h]
0x140051bd3  cmp     dword ptr [rbx+23Ch], 4
0x140051bda  jb      short loc_140051BF0
0x140051bdc  mov     rcx, [rbx+230h]
0x140051be3  mov     [rcx], eax
0x140051be5  mov     qword ptr [rbx+0B8h], 4
0x140051bf0  xor     eax, eax
0x140051bf2  add     rsp, 20h
0x140051bf6  pop     rbx
0x140051bf7  retn
```

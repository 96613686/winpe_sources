# BiAcquirePrivilege

- ea: `0x1800350ac`
- end: `0x180035143`
- name: `BiAcquirePrivilege`
- size: `151`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800334d4`
- `0x180033e80`
- `0x180035684`
- `0x1800368f0`
- `0x18003699c`
- `0x180036b18`
- `0x180036d98`
- `0x180037abc`
- `0x180037b54`
- `0x180037c88`
- `0x180037dc4`
- `0x180037e68`

## callees

- `0x1800350ac`
- `0x18003514c`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18003511d`
- `ntdll!NtSetInformationThread` at `0x18003511d`
- `ntdll!RtlImpersonateSelf` at `0x1800350d6`
- `ntdll!RtlImpersonateSelf` at `0x1800350d6`

## pseudocode

```c
NTSTATUS __fastcall BiAcquirePrivilege(unsigned int a1, __int64 a2)
{
  ULONG IsImpersonating; // eax
  __int64 v3; // rdi
  char v5; // bl
  NTSTATUS result; // eax
  int v7; // esi
  __int64 ThreadInformation; // [rsp+60h] [rbp+18h] BYREF

  IsImpersonating = NtCurrentTeb()->IsImpersonating;
  v3 = a2;
  LOBYTE(ThreadInformation) = 0;
  if ( IsImpersonating )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    result = RtlImpersonateSelf(SecurityImpersonation);
    if ( result < 0 )
      return result;
  }
  LOBYTE(a2) = 1;
  v7 = BiAdjustPrivilege(a1, a2, &ThreadInformation);
  if ( v7 >= 0 )
  {
    *(_BYTE *)(v3 + 4) = ThreadInformation;
    *(_BYTE *)(v3 + 5) = v5;
    *(_DWORD *)v3 = a1;
  }
  else if ( !v5 )
  {
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  return v7;
}

```

## disassembly

```asm
0x1800350ac  push    rbx
0x1800350ae  push    rbp
0x1800350af  push    rsi
0x1800350b0  push    rdi
0x1800350b1  sub     rsp, 28h
0x1800350b5  mov     eax, gs:179Ch
0x1800350bd  mov     rdi, rdx
0x1800350c0  mov     byte ptr [rsp+48h+ThreadInformation], 0
0x1800350c5  mov     ebp, ecx
0x1800350c7  test    eax, eax
0x1800350c9  jz      short loc_1800350CF
0x1800350cb  mov     bl, 1
0x1800350cd  jmp     short loc_1800350E6
0x1800350cf  mov     ecx, 2; ImpersonationLevel
0x1800350d4  xor     bl, bl
0x1800350d6  call    cs:__imp_RtlImpersonateSelf
0x1800350dd  nop     dword ptr [rax+rax+00h]
0x1800350e2  test    eax, eax
0x1800350e4  js      short loc_180035139
0x1800350e6  lea     r8, [rsp+48h+ThreadInformation]
0x1800350eb  mov     dl, 1
0x1800350ed  mov     ecx, ebp
0x1800350ef  call    BiAdjustPrivilege
0x1800350f4  mov     esi, eax
0x1800350f6  test    eax, eax
0x1800350f8  jns     short loc_18003512B
0x1800350fa  test    bl, bl
0x1800350fc  jnz     short loc_180035137
0x1800350fe  mov     r9d, 8; ThreadInformationLength
0x180035104  mov     [rsp+48h+ThreadInformation], 0
0x18003510d  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x180035112  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180035119  lea     edx, [r9-3]; ThreadInformationClass
0x18003511d  call    cs:__imp_NtSetInformationThread
0x180035124  nop     dword ptr [rax+rax+00h]
0x180035129  jmp     short loc_180035137
0x18003512b  mov     al, byte ptr [rsp+48h+ThreadInformation]
0x18003512f  mov     [rdi+4], al
0x180035132  mov     [rdi+5], bl
0x180035135  mov     [rdi], ebp
0x180035137  mov     eax, esi
0x180035139  add     rsp, 28h
0x18003513d  pop     rdi
0x18003513e  pop     rsi
0x18003513f  pop     rbp
0x180035140  pop     rbx
0x180035141  retn
```

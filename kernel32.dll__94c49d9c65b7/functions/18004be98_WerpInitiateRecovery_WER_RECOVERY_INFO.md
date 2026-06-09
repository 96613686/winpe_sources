# WerpInitiateRecovery(WER_RECOVERY_INFO *)

- ea: `0x18004be98`
- end: `0x18004bff5`
- name: `?WerpInitiateRecovery@@YAJPEAUWER_RECOVERY_INFO@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(struct WER_RECOVERY_INFO *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180046438`
- `0x18004be08`

## callees

- `0x18004be98`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlDecodeSystemPointer` at `0x18004bf66`
- `ntdll!RtlDecodeSystemPointer` at `0x18004bf66`
- `ntdll!DbgPrintEx` at `0x18004bed2`
- `ntdll!DbgPrintEx` at `0x18004bf07`
- `ntdll!DbgPrintEx` at `0x18004bfa0`
- `ntdll!DbgPrintEx` at `0x18004bfd8`
- `ntdll!DbgPrintEx` at `0x18004bed2`
- `ntdll!DbgPrintEx` at `0x18004bf07`
- `ntdll!DbgPrintEx` at `0x18004bfa0`
- `ntdll!DbgPrintEx` at `0x18004bfd8`
- `ntdll!NtClearEvent` at `0x18004bf1b`
- `ntdll!NtClearEvent` at `0x18004bf27`
- `ntdll!NtClearEvent` at `0x18004bf33`
- `ntdll!NtClearEvent` at `0x18004bf1b`
- `ntdll!NtClearEvent` at `0x18004bf27`
- `ntdll!NtClearEvent` at `0x18004bf33`

## string_xrefs

- `0x18004bef9`: `WER/Recovery/%u:%u: ERROR Already in recovery\n`

## pseudocode

```c
__int64 __fastcall WerpInitiateRecovery(struct WER_RECOVERY_INFO *a1)
{
  NTSTATUS v3; // edi
  NTSTATUS v4; // ebx
  const CHAR *v5; // r8
  void *v6; // rcx
  void (__fastcall *v7)(_QWORD); // rax
  int v9; // [rsp+20h] [rbp-18h]

  if ( !a1 )
  {
    DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR Invalid params\n", NtCurrentTeb()->ClientId.UniqueProcess, 90);
    return 2147942487LL;
  }
  if ( *((_DWORD *)a1 + 12) )
  {
    DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR Already in recovery\n", NtCurrentTeb()->ClientId.UniqueProcess, 96);
    return 2147947423LL;
  }
  v3 = NtClearEvent(*((HANDLE *)a1 + 3));
  v4 = NtClearEvent(*((HANDLE *)a1 + 4));
  if ( (~v4 & ~NtClearEvent(*((HANDLE *)a1 + 5)) & ~v3) >= 0 )
  {
    v9 = 108;
    v5 = "WER/Recovery/%u:%u: ERROR Invalid events\n";
LABEL_10:
    DbgPrintEx(0x96u, 0, v5, NtCurrentTeb()->ClientId.UniqueProcess, v9);
    return (unsigned int)-2147467259;
  }
  v6 = (void *)*((_QWORD *)a1 + 1);
  if ( !v6 )
  {
    v9 = 139;
    v5 = "WER/Recovery/%u:%u: ERROR No recovery function found\n";
    goto LABEL_10;
  }
  *((_DWORD *)a1 + 12) = 1;
  v7 = (void (__fastcall *)(_QWORD))RtlDecodeSystemPointer(v6);
  v7(*((_QWORD *)a1 + 2));
  *((_DWORD *)a1 + 12) = 0;
  return 0;
}

```

## disassembly

```asm
0x18004be98  mov     rax, rsp
0x18004be9b  mov     [rax+10h], rbx
0x18004be9f  mov     [rax+18h], rsi
0x18004bea3  mov     [rax+8], rcx
0x18004bea7  push    rdi
0x18004bea8  sub     rsp, 30h
0x18004beac  mov     rsi, rcx
0x18004beaf  test    rcx, rcx
0x18004beb2  jnz     short loc_18004BEE2
0x18004beb4  mov     r9, gs:40h
0x18004bebd  mov     dword ptr [rax-18h], 5Ah ; 'Z'
0x18004bec4  lea     r8, aWerRecoveryUUE_0; "WER/Recovery/%u:%u: ERROR Invalid param"...
0x18004becb  xor     edx, edx; Level
0x18004becd  mov     ecx, 96h; ComponentId
0x18004bed2  call    cs:__imp_DbgPrintEx
0x18004bed8  mov     eax, 80070057h
0x18004bedd  jmp     loc_18004BFE5
0x18004bee2  cmp     dword ptr [rcx+30h], 0
0x18004bee6  jz      short loc_18004BF17
0x18004bee8  mov     r9, gs:40h
0x18004bef1  mov     [rsp+38h+var_18], 60h ; '`'
0x18004bef9  lea     r8, aWerRecoveryUUE_5; "WER/Recovery/%u:%u: ERROR Already in re"...
0x18004bf00  xor     edx, edx; Level
0x18004bf02  mov     ecx, 96h; ComponentId
0x18004bf07  call    cs:__imp_DbgPrintEx
0x18004bf0d  mov     eax, 8007139Fh
0x18004bf12  jmp     loc_18004BFE5
0x18004bf17  mov     rcx, [rcx+18h]; EventHandle
0x18004bf1b  call    cs:__imp_NtClearEvent
0x18004bf21  mov     edi, eax
0x18004bf23  mov     rcx, [rsi+20h]; EventHandle
0x18004bf27  call    cs:__imp_NtClearEvent
0x18004bf2d  mov     ebx, eax
0x18004bf2f  mov     rcx, [rsi+28h]; EventHandle
0x18004bf33  call    cs:__imp_NtClearEvent
0x18004bf39  not     eax
0x18004bf3b  not     ebx
0x18004bf3d  and     eax, ebx
0x18004bf3f  not     edi
0x18004bf41  test    edi, eax
0x18004bf43  js      short loc_18004BF56
0x18004bf45  mov     [rsp+38h+var_18], 6Ch ; 'l'
0x18004bf4d  lea     r8, aWerRecoveryUUE_3; "WER/Recovery/%u:%u: ERROR Invalid event"...
0x18004bf54  jmp     short loc_18004BFC8
0x18004bf56  mov     rcx, [rsi+8]; Pointer
0x18004bf5a  test    rcx, rcx
0x18004bf5d  jz      short loc_18004BFB9
0x18004bf5f  mov     dword ptr [rsi+30h], 1
0x18004bf66  call    cs:__imp_RtlDecodeSystemPointer
0x18004bf6c  mov     rcx, [rsi+10h]
0x18004bf70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf75  nop
0x18004bf76  mov     dword ptr [rsi+30h], 0
0x18004bf7d  xor     ecx, ecx
0x18004bf7f  jmp     short loc_18004BFE3
0x18004bf81  mov     r9, gs:40h
0x18004bf8a  mov     [rsp+38h+var_18], 80h
0x18004bf92  lea     r8, aWerRecoveryUUE_1; "WER/Recovery/%u:%u: ERROR Exception enc"...
0x18004bf99  xor     edx, edx; Level
0x18004bf9b  mov     ecx, 96h; ComponentId
0x18004bfa0  call    cs:__imp_DbgPrintEx
0x18004bfa6  mov     ecx, 80004005h
0x18004bfab  mov     rax, [rsp+38h+arg_0]
0x18004bfb0  mov     dword ptr [rax+30h], 0
0x18004bfb7  jmp     short loc_18004BFE3
0x18004bfb9  mov     [rsp+38h+var_18], 8Bh
0x18004bfc1  lea     r8, aWerRecoveryUUE; "WER/Recovery/%u:%u: ERROR No recovery f"...
0x18004bfc8  mov     r9, gs:40h
0x18004bfd1  xor     edx, edx; Level
0x18004bfd3  mov     ecx, 96h; ComponentId
0x18004bfd8  call    cs:__imp_DbgPrintEx
0x18004bfde  mov     ecx, 80004005h
0x18004bfe3  mov     eax, ecx
0x18004bfe5  mov     rbx, [rsp+38h+arg_8]
0x18004bfea  mov     rsi, [rsp+38h+arg_10]
0x18004bfef  add     rsp, 30h
0x18004bff3  pop     rdi
0x18004bff4  retn
0x18007b332  push    rbp
0x18007b334  sub     rsp, 30h
0x18007b338  mov     rbp, rdx
0x18007b33b  mov     rax, [rcx]
0x18007b33e  xor     ecx, ecx
0x18007b340  cmp     dword ptr [rax], 0C0000005h
0x18007b346  setz    cl
0x18007b349  mov     eax, ecx
0x18007b34b  add     rsp, 30h
0x18007b34f  pop     rbp
0x18007b350  retn
```

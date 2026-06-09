# WerpInitiateRecovery(WER_RECOVERY_INFO *)

- ea: `0x180050558`
- end: `0x1800506e6`
- name: `?WerpInitiateRecovery@@YAJPEAUWER_RECOVERY_INFO@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(struct WER_RECOVERY_INFO *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004ac44`
- `0x1800504b8`

## callees

- `0x180050558`
- `0x180084010`

## import_xrefs

- `ntdll!RtlDecodeSystemPointer` at `0x180050644`
- `ntdll!RtlDecodeSystemPointer` at `0x180050644`
- `ntdll!DbgPrintEx` at `0x180050592`
- `ntdll!DbgPrintEx` at `0x1800505cd`
- `ntdll!DbgPrintEx` at `0x180050684`
- `ntdll!DbgPrintEx` at `0x1800506c2`
- `ntdll!DbgPrintEx` at `0x180050592`
- `ntdll!DbgPrintEx` at `0x1800505cd`
- `ntdll!DbgPrintEx` at `0x180050684`
- `ntdll!DbgPrintEx` at `0x1800506c2`
- `ntdll!NtClearEvent` at `0x1800505e7`
- `ntdll!NtClearEvent` at `0x1800505f9`
- `ntdll!NtClearEvent` at `0x18005060b`
- `ntdll!NtClearEvent` at `0x1800505e7`
- `ntdll!NtClearEvent` at `0x1800505f9`
- `ntdll!NtClearEvent` at `0x18005060b`

## string_xrefs

- `0x1800505bf`: `WER/Recovery/%u:%u: ERROR Already in recovery\n`

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
0x180050558  mov     rax, rsp
0x18005055b  mov     [rax+10h], rbx
0x18005055f  mov     [rax+18h], rsi
0x180050563  mov     [rax+8], rcx
0x180050567  push    rdi
0x180050568  sub     rsp, 30h
0x18005056c  mov     rsi, rcx
0x18005056f  test    rcx, rcx
0x180050572  jnz     short loc_1800505A8
0x180050574  mov     r9, gs:40h
0x18005057d  mov     dword ptr [rax-18h], 5Ah ; 'Z'
0x180050584  lea     r8, aWerRecoveryUUE_0; "WER/Recovery/%u:%u: ERROR Invalid param"...
0x18005058b  xor     edx, edx; Level
0x18005058d  mov     ecx, 96h; ComponentId
0x180050592  call    cs:__imp_DbgPrintEx
0x180050599  nop     dword ptr [rax+rax+00h]
0x18005059e  mov     eax, 80070057h
0x1800505a3  jmp     loc_1800506D5
0x1800505a8  cmp     dword ptr [rcx+30h], 0
0x1800505ac  jz      short loc_1800505E3
0x1800505ae  mov     r9, gs:40h
0x1800505b7  mov     [rsp+38h+var_18], 60h ; '`'
0x1800505bf  lea     r8, aWerRecoveryUUE_5; "WER/Recovery/%u:%u: ERROR Already in re"...
0x1800505c6  xor     edx, edx; Level
0x1800505c8  mov     ecx, 96h; ComponentId
0x1800505cd  call    cs:__imp_DbgPrintEx
0x1800505d4  nop     dword ptr [rax+rax+00h]
0x1800505d9  mov     eax, 8007139Fh
0x1800505de  jmp     loc_1800506D5
0x1800505e3  mov     rcx, [rcx+18h]; EventHandle
0x1800505e7  call    cs:__imp_NtClearEvent
0x1800505ee  nop     dword ptr [rax+rax+00h]
0x1800505f3  mov     edi, eax
0x1800505f5  mov     rcx, [rsi+20h]; EventHandle
0x1800505f9  call    cs:__imp_NtClearEvent
0x180050600  nop     dword ptr [rax+rax+00h]
0x180050605  mov     ebx, eax
0x180050607  mov     rcx, [rsi+28h]; EventHandle
0x18005060b  call    cs:__imp_NtClearEvent
0x180050612  nop     dword ptr [rax+rax+00h]
0x180050617  not     eax
0x180050619  not     ebx
0x18005061b  and     eax, ebx
0x18005061d  not     edi
0x18005061f  test    edi, eax
0x180050621  js      short loc_180050634
0x180050623  mov     [rsp+38h+var_18], 6Ch ; 'l'
0x18005062b  lea     r8, aWerRecoveryUUE_3; "WER/Recovery/%u:%u: ERROR Invalid event"...
0x180050632  jmp     short loc_1800506B2
0x180050634  mov     rcx, [rsi+8]; Pointer
0x180050638  test    rcx, rcx
0x18005063b  jz      short loc_1800506A3
0x18005063d  mov     dword ptr [rsi+30h], 1
0x180050644  call    cs:__imp_RtlDecodeSystemPointer
0x18005064b  nop     dword ptr [rax+rax+00h]
0x180050650  mov     rcx, [rsi+10h]
0x180050654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050659  nop
0x18005065a  mov     dword ptr [rsi+30h], 0
0x180050661  xor     ecx, ecx
0x180050663  jmp     short loc_1800506D3
0x180050665  mov     r9, gs:40h
0x18005066e  mov     [rsp+38h+var_18], 80h
0x180050676  lea     r8, aWerRecoveryUUE_1; "WER/Recovery/%u:%u: ERROR Exception enc"...
0x18005067d  xor     edx, edx; Level
0x18005067f  mov     ecx, 96h; ComponentId
0x180050684  call    cs:__imp_DbgPrintEx
0x18005068b  nop     dword ptr [rax+rax+00h]
0x180050690  mov     ecx, 80004005h
0x180050695  mov     rax, [rsp+38h+arg_0]
0x18005069a  mov     dword ptr [rax+30h], 0
0x1800506a1  jmp     short loc_1800506D3
0x1800506a3  mov     [rsp+38h+var_18], 8Bh
0x1800506ab  lea     r8, aWerRecoveryUUE; "WER/Recovery/%u:%u: ERROR No recovery f"...
0x1800506b2  mov     r9, gs:40h
0x1800506bb  xor     edx, edx; Level
0x1800506bd  mov     ecx, 96h; ComponentId
0x1800506c2  call    cs:__imp_DbgPrintEx
0x1800506c9  nop     dword ptr [rax+rax+00h]
0x1800506ce  mov     ecx, 80004005h
0x1800506d3  mov     eax, ecx
0x1800506d5  mov     rbx, [rsp+38h+arg_8]
0x1800506da  mov     rsi, [rsp+38h+arg_10]
0x1800506df  add     rsp, 30h
0x1800506e3  pop     rdi
0x1800506e4  retn
0x1800833db  push    rbp
0x1800833dd  sub     rsp, 30h
0x1800833e1  mov     rbp, rdx
0x1800833e4  mov     rax, [rcx]
0x1800833e7  xor     ecx, ecx
0x1800833e9  cmp     dword ptr [rax], 0C0000005h
0x1800833ef  setz    cl
0x1800833f2  mov     eax, ecx
0x1800833f4  add     rsp, 30h
0x1800833f8  pop     rbp
0x1800833f9  retn
```

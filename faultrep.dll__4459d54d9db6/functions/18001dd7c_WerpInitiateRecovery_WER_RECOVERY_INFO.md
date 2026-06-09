# WerpInitiateRecovery(WER_RECOVERY_INFO *)

- ea: `0x18001dd7c`
- end: `0x18001dedb`
- name: `?WerpInitiateRecovery@@YAJPEAUWER_RECOVERY_INFO@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(struct WER_RECOVERY_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180042690`

## callees

- `0x180003617`
- `0x18001dd7c`
- `0x18004b010`

## import_xrefs

- `ntdll!RtlDecodeSystemPointer` at `0x18001de4e`
- `ntdll!RtlDecodeSystemPointer` at `0x18001de4e`
- `ntdll!NtClearEvent` at `0x18001ddfe`
- `ntdll!NtClearEvent` at `0x18001de0a`
- `ntdll!NtClearEvent` at `0x18001de16`
- `ntdll!NtClearEvent` at `0x18001ddfe`
- `ntdll!NtClearEvent` at `0x18001de0a`
- `ntdll!NtClearEvent` at `0x18001de16`
- `ntdll!DbgPrintEx` at `0x18001ddb6`
- `ntdll!DbgPrintEx` at `0x18001ddea`
- `ntdll!DbgPrintEx` at `0x18001de87`
- `ntdll!DbgPrintEx` at `0x18001debe`
- `ntdll!DbgPrintEx` at `0x18001ddb6`
- `ntdll!DbgPrintEx` at `0x18001ddea`
- `ntdll!DbgPrintEx` at `0x18001de87`
- `ntdll!DbgPrintEx` at `0x18001debe`

## string_xrefs

- `0x18001dddc`: `WER/Recovery/%u:%u: ERROR Already in recovery\n`

## pseudocode

```c
__int64 __fastcall WerpInitiateRecovery(struct WER_RECOVERY_INFO *a1)
{
  DWORD CurrentProcessId_0; // eax
  DWORD v4; // eax
  NTSTATUS v5; // edi
  NTSTATUS v6; // ebx
  DWORD v7; // eax
  void *v8; // rcx
  void (__fastcall *v9)(_QWORD); // rax
  DWORD v11; // eax

  if ( !a1 )
  {
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR Invalid params\n", CurrentProcessId_0, 90);
    return 2147942487LL;
  }
  if ( *((_DWORD *)a1 + 12) )
  {
    v4 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR Already in recovery\n", v4, 96);
    return 2147947423LL;
  }
  v5 = NtClearEvent(*((HANDLE *)a1 + 3));
  v6 = NtClearEvent(*((HANDLE *)a1 + 4));
  if ( (~v6 & ~NtClearEvent(*((HANDLE *)a1 + 5)) & ~v5) >= 0 )
  {
    v7 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR Invalid events\n", v7, 108);
    return (unsigned int)-2147467259;
  }
  v8 = (void *)*((_QWORD *)a1 + 1);
  if ( !v8 )
  {
    v11 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR No recovery function found\n", v11, 139);
    return (unsigned int)-2147467259;
  }
  *((_DWORD *)a1 + 12) = 1;
  v9 = (void (__fastcall *)(_QWORD))RtlDecodeSystemPointer(v8);
  v9(*((_QWORD *)a1 + 2));
  *((_DWORD *)a1 + 12) = 0;
  return 0;
}

```

## disassembly

```asm
0x18001dd7c  mov     [rsp+arg_8], rbx
0x18001dd81  mov     [rsp+arg_10], rsi
0x18001dd86  mov     [rsp+arg_0], rcx
0x18001dd8b  push    rdi
0x18001dd8c  sub     rsp, 30h
0x18001dd90  mov     rsi, rcx
0x18001dd93  test    rcx, rcx
0x18001dd96  jnz     short loc_18001DDC6
0x18001dd98  call    GetCurrentProcessId_0
0x18001dd9d  mov     r9d, eax
0x18001dda0  mov     [rsp+38h+var_18], 5Ah ; 'Z'
0x18001dda8  lea     r8, aWerRecoveryUUE_2; "WER/Recovery/%u:%u: ERROR Invalid param"...
0x18001ddaf  xor     edx, edx; Level
0x18001ddb1  mov     ecx, 96h; ComponentId
0x18001ddb6  call    cs:__imp_DbgPrintEx
0x18001ddbc  mov     eax, 80070057h
0x18001ddc1  jmp     loc_18001DECB
0x18001ddc6  cmp     dword ptr [rcx+30h], 0
0x18001ddca  jz      short loc_18001DDFA
0x18001ddcc  call    GetCurrentProcessId_0
0x18001ddd1  mov     r9d, eax
0x18001ddd4  mov     [rsp+38h+var_18], 60h ; '`'
0x18001dddc  lea     r8, aWerRecoveryUUE_10; "WER/Recovery/%u:%u: ERROR Already in re"...
0x18001dde3  xor     edx, edx; Level
0x18001dde5  mov     ecx, 96h; ComponentId
0x18001ddea  call    cs:__imp_DbgPrintEx
0x18001ddf0  mov     eax, 8007139Fh
0x18001ddf5  jmp     loc_18001DECB
0x18001ddfa  mov     rcx, [rcx+18h]; EventHandle
0x18001ddfe  call    cs:__imp_NtClearEvent
0x18001de04  mov     edi, eax
0x18001de06  mov     rcx, [rsi+20h]; EventHandle
0x18001de0a  call    cs:__imp_NtClearEvent
0x18001de10  mov     ebx, eax
0x18001de12  mov     rcx, [rsi+28h]; EventHandle
0x18001de16  call    cs:__imp_NtClearEvent
0x18001de1c  not     eax
0x18001de1e  not     ebx
0x18001de20  and     eax, ebx
0x18001de22  not     edi
0x18001de24  test    edi, eax
0x18001de26  js      short loc_18001DE3E
0x18001de28  call    GetCurrentProcessId_0
0x18001de2d  mov     [rsp+38h+var_18], 6Ch ; 'l'
0x18001de35  lea     r8, aWerRecoveryUUE_7; "WER/Recovery/%u:%u: ERROR Invalid event"...
0x18001de3c  jmp     short loc_18001DEB4
0x18001de3e  mov     rcx, [rsi+8]; Pointer
0x18001de42  test    rcx, rcx
0x18001de45  jz      short loc_18001DEA0
0x18001de47  mov     dword ptr [rsi+30h], 1
0x18001de4e  call    cs:__imp_RtlDecodeSystemPointer
0x18001de54  mov     rcx, [rsi+10h]
0x18001de58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de5d  nop
0x18001de5e  mov     dword ptr [rsi+30h], 0
0x18001de65  xor     ecx, ecx
0x18001de67  jmp     short loc_18001DEC9
0x18001de69  call    GetCurrentProcessId_0
0x18001de6e  mov     r9d, eax
0x18001de71  mov     [rsp+38h+var_18], 80h
0x18001de79  lea     r8, aWerRecoveryUUE_6; "WER/Recovery/%u:%u: ERROR Exception enc"...
0x18001de80  xor     edx, edx; Level
0x18001de82  mov     ecx, 96h; ComponentId
0x18001de87  call    cs:__imp_DbgPrintEx
0x18001de8d  mov     ecx, 80004005h
0x18001de92  mov     rax, [rsp+38h+arg_0]
0x18001de97  mov     dword ptr [rax+30h], 0
0x18001de9e  jmp     short loc_18001DEC9
0x18001dea0  call    GetCurrentProcessId_0
0x18001dea5  mov     [rsp+38h+var_18], 8Bh
0x18001dead  lea     r8, aWerRecoveryUUE_1; "WER/Recovery/%u:%u: ERROR No recovery f"...
0x18001deb4  mov     r9d, eax
0x18001deb7  xor     edx, edx; Level
0x18001deb9  mov     ecx, 96h; ComponentId
0x18001debe  call    cs:__imp_DbgPrintEx
0x18001dec4  mov     ecx, 80004005h
0x18001dec9  mov     eax, ecx
0x18001decb  mov     rbx, [rsp+38h+arg_8]
0x18001ded0  mov     rsi, [rsp+38h+arg_10]
0x18001ded5  add     rsp, 30h
0x18001ded9  pop     rdi
0x18001deda  retn
0x1800499d2  push    rbp
0x1800499d4  sub     rsp, 30h
0x1800499d8  mov     rbp, rdx
0x1800499db  mov     rax, [rcx]
0x1800499de  xor     ecx, ecx
0x1800499e0  cmp     dword ptr [rax], 0C0000005h
0x1800499e6  setz    cl
0x1800499e9  mov     eax, ecx
0x1800499eb  add     rsp, 30h
0x1800499ef  pop     rbp
0x1800499f0  retn
```

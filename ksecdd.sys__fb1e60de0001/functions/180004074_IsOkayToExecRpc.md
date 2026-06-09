# IsOkayToExecRpc

- ea: `0x180004074`
- end: `0x1800040cb`
- name: `IsOkayToExecRpc`
- size: `87`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002a84`
- `0x180003574`
- `0x18000368c`
- `0x180003a54`
- `0x180003c38`
- `0x180003e20`
- `0x18000ad04`
- `0x18000ae18`
- `0x18000af24`
- `0x18000b048`
- `0x18000b184`

## callees

- `0x180001a68`
- `0x180001ae4`
- `0x180004074`

## import_xrefs

- `ntoskrnl!PsGetProcessSecurityPort` at `0x18000408c`
- `ntoskrnl!PsGetProcessSecurityPort` at `0x18000408c`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000407d`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000407d`

## pseudocode

```c
__int64 __fastcall IsOkayToExecRpc(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 CurrentProcess; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 result; // rax
  __int64 RpcConnection; // rax

  CurrentProcess = PsGetCurrentProcess(a1, a2, a3, a4);
  if ( PsGetProcessSecurityPort(CurrentProcess) == 1 )
    return 3221225738LL;
  result = IsOkayToExec(v7, v6);
  if ( (int)result >= 0 )
  {
    RpcConnection = KsecpGetRpcConnection();
    if ( RpcConnection )
    {
      *a1 = RpcConnection;
      return 0;
    }
    else
    {
      return 3221225792LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004074  push    rbx
0x180004076  sub     rsp, 20h
0x18000407a  mov     rbx, rcx
0x18000407d  call    cs:__imp_PsGetCurrentProcess
0x180004084  nop     dword ptr [rax+rax+00h]
0x180004089  mov     rcx, rax
0x18000408c  call    cs:__imp_PsGetProcessSecurityPort
0x180004093  nop     dword ptr [rax+rax+00h]
0x180004098  cmp     rax, 1
0x18000409c  jnz     short loc_1800040A5
0x18000409e  mov     eax, 0C000010Ah
0x1800040a3  jmp     short loc_1800040C4
0x1800040a5  call    IsOkayToExec
0x1800040aa  test    eax, eax
0x1800040ac  js      short loc_1800040C4
0x1800040ae  call    KsecpGetRpcConnection
0x1800040b3  test    rax, rax
0x1800040b6  jnz     short loc_1800040BF
0x1800040b8  mov     eax, 0C0000140h
0x1800040bd  jmp     short loc_1800040C4
0x1800040bf  mov     [rbx], rax
0x1800040c2  xor     eax, eax
0x1800040c4  add     rsp, 20h
0x1800040c8  pop     rbx
0x1800040c9  retn
```

# EfsNotifyEnterpriseFileWriteClient

- ea: `0x140058688`
- end: `0x140058778`
- name: `EfsNotifyEnterpriseFileWriteClient`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140053460`

## callees

- `0x14000aac4`
- `0x140057bd4`
- `0x140057c8c`
- `0x140057e50`
- `0x140058688`

## import_xrefs

- `msrpc!I_RpcExceptionFilter` at `0x1400607eb`
- `msrpc!I_RpcExceptionFilter` at `0x14006080d`
- `msrpc!I_RpcExceptionFilter` at `0x1400607eb`
- `msrpc!I_RpcExceptionFilter` at `0x14006080d`

## pseudocode

```c
__int64 __fastcall EfsNotifyEnterpriseFileWriteClient(int a1, int a2, int a3, __int64 a4, __int64 a5)
{
  int v9; // ecx
  unsigned int v10; // ebx
  int v11; // ecx

  if ( !(unsigned __int8)EfsAcquireRpcHandle() )
    return (unsigned int)-1073610729;
  v10 = EfsKRpcNotifyEnterpriseFileWrite(v9, a1, a2, a3, a4, a5);
  if ( ((v10 + 1073610729) & 0xFFFFFFFA) != 0 || v10 == -1073610728 )
    goto LABEL_6;
  if ( (unsigned __int8)EfsRpcTryToReconnect() )
  {
    v10 = EfsKRpcNotifyEnterpriseFileWrite(v11, a1, a2, a3, a4, a5);
LABEL_6:
    EfsReleaseRpcHandle();
  }
  return v10;
}

```

## disassembly

```asm
0x140058688  mov     rax, rsp
0x14005868b  mov     [rax+20h], r9
0x14005868f  mov     [rax+18h], r8
0x140058693  mov     [rax+10h], rdx
0x140058697  mov     [rax+8], rcx
0x14005869b  push    rbx
0x14005869c  push    rsi
0x14005869d  push    rdi
0x14005869e  push    r12
0x1400586a0  push    r14
0x1400586a2  push    r15
0x1400586a4  sub     rsp, 48h
0x1400586a8  mov     rdi, r9
0x1400586ab  mov     rsi, r8
0x1400586ae  mov     r14, rdx
0x1400586b1  mov     r15, rcx
0x1400586b4  call    EfsAcquireRpcHandle
0x1400586b9  test    al, al
0x1400586bb  jz      loc_140058762
0x1400586c1  mov     r12, [rsp+78h+arg_20]
0x1400586c9  mov     [rsp+78h+var_50], r12
0x1400586ce  mov     [rsp+78h+var_58], rdi
0x1400586d3  mov     r9, rsi
0x1400586d6  mov     r8, r14
0x1400586d9  mov     rdx, r15
0x1400586dc  call    EfsKRpcNotifyEnterpriseFileWrite
0x1400586e1  mov     ebx, eax
0x1400586e3  mov     [rsp+78h+var_48], eax
0x1400586e7  jmp     short loc_140058717
0x1400586e9  mov     ebx, eax
0x1400586eb  mov     [rsp+78h+var_48], eax
0x1400586ef  mov     r12, [rsp+78h+arg_20]
0x1400586f7  mov     rdi, [rsp+78h+arg_18]
0x1400586ff  mov     rsi, [rsp+78h+arg_10]
0x140058707  mov     r14, [rsp+78h+arg_8]
0x14005870f  mov     r15, [rsp+78h+arg_0]
0x140058717  lea     eax, [rbx+3FFDFFE9h]
0x14005871d  test    eax, 0FFFFFFFAh
0x140058722  jnz     short loc_14005875B
0x140058724  cmp     ebx, 0C0020018h
0x14005872a  jz      short loc_14005875B
0x14005872c  call    EfsRpcTryToReconnect
0x140058731  test    al, al
0x140058733  jz      short loc_140058767
0x140058735  mov     [rsp+78h+var_50], r12
0x14005873a  mov     [rsp+78h+var_58], rdi
0x14005873f  mov     r9, rsi
0x140058742  mov     r8, r14
0x140058745  mov     rdx, r15
0x140058748  call    EfsKRpcNotifyEnterpriseFileWrite
0x14005874d  mov     ebx, eax
0x14005874f  mov     [rsp+78h+var_48], eax
0x140058753  jmp     short loc_14005875B
0x140058755  mov     ebx, eax
0x140058757  mov     [rsp+78h+var_48], eax
0x14005875b  call    EfsReleaseRpcHandle
0x140058760  jmp     short loc_140058767
0x140058762  mov     ebx, 0C0020017h
0x140058767  mov     eax, ebx
0x140058769  add     rsp, 48h
0x14005876d  pop     r15
0x14005876f  pop     r14
0x140058771  pop     r12
0x140058773  pop     rdi
0x140058774  pop     rsi
0x140058775  pop     rbx
0x140058776  retn
0x1400607dd  push    rbp
0x1400607df  sub     rsp, 30h
0x1400607e3  mov     rbp, rdx
0x1400607e6  mov     rcx, [rcx]
0x1400607e9  mov     ecx, [rcx]; ExceptionCode
0x1400607eb  call    cs:__imp_I_RpcExceptionFilter
0x1400607f2  nop     dword ptr [rax+rax+00h]
0x1400607f7  nop
0x1400607f8  add     rsp, 30h
0x1400607fc  pop     rbp
0x1400607fd  retn
0x1400607ff  push    rbp
0x140060801  sub     rsp, 30h
0x140060805  mov     rbp, rdx
0x140060808  mov     rcx, [rcx]
0x14006080b  mov     ecx, [rcx]; ExceptionCode
0x14006080d  call    cs:__imp_I_RpcExceptionFilter
0x140060814  nop     dword ptr [rax+rax+00h]
0x140060819  nop
0x14006081a  add     rsp, 30h
0x14006081e  pop     rbp
0x14006081f  retn
```

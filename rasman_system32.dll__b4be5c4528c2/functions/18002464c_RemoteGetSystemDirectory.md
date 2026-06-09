# RemoteGetSystemDirectory

- ea: `0x18002464c`
- end: `0x1800246bb`
- name: `RemoteGetSystemDirectory`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180023750`

## callees

- `0x180023d60`
- `0x18002464c`
- `0x18002739e`
- `0x1800273d0`

## pseudocode

```c
__int64 __fastcall RemoteGetSystemDirectory(_QWORD *a1)
{
  __int16 v3; // [rsp+30h] [rbp-228h] BYREF
  _BYTE v4[526]; // [rsp+32h] [rbp-226h] BYREF

  v3 = 0;
  memset_0(v4, 0, 0x208u);
  return (unsigned int)RasRpcGetSystemDirectory(*a1, &v3, 261);
}

```

## disassembly

```asm
0x18002464c  push    rbx
0x18002464e  sub     rsp, 250h
0x180024655  mov     rax, cs:__security_cookie
0x18002465c  xor     rax, rsp
0x18002465f  mov     [rsp+258h+var_18], rax
0x180024667  mov     rbx, rcx
0x18002466a  xor     eax, eax
0x18002466c  mov     [rsp+258h+var_228], ax
0x180024671  xor     edx, edx; Val
0x180024673  mov     r8d, 208h; Size
0x180024679  lea     rcx, [rsp+258h+var_226]; void *
0x18002467e  call    memset_0
0x180024683  nop
0x180024684  mov     r8d, 105h
0x18002468a  lea     rdx, [rsp+258h+var_228]
0x18002468f  mov     rcx, [rbx]
0x180024692  call    RasRpcGetSystemDirectory
0x180024697  mov     [rsp+258h+var_238], eax
0x18002469b  mov     eax, [rsp+258h+var_238]
0x18002469f  jmp     short $+2
0x1800246a1  mov     rcx, [rsp+258h+var_18]
0x1800246a9  xor     rcx, rsp; StackCookie
0x1800246ac  call    __security_check_cookie
0x1800246b1  add     rsp, 250h
0x1800246b8  pop     rbx
0x1800246b9  retn
0x1800277f6  push    rbp
0x1800277f8  sub     rsp, 20h
0x1800277fc  mov     rbp, rdx
0x1800277ff  mov     rax, [rcx]
0x180027802  mov     ecx, [rax]
0x180027804  mov     [rbp+20h], ecx
0x180027807  mov     ecx, [rbp+20h]; ExceptionCode
0x18002780a  call    cs:__imp_I_RpcExceptionFilter
0x180027811  nop     dword ptr [rax+rax+00h]
0x180027816  nop
0x180027817  add     rsp, 20h
0x18002781b  pop     rbp
0x18002781c  retn
```

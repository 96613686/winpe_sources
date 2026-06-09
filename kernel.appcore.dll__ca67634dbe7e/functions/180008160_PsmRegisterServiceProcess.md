# PsmRegisterServiceProcess

- ea: `0x180008160`
- end: `0x18000821d`
- name: `PsmRegisterServiceProcess`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004e20`
- `0x180008160`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x1800081ac`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800081ac`
- `RPCRT4!RpcExceptionFilter` at `0x180009fa0`
- `RPCRT4!RpcExceptionFilter` at `0x180009fa0`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800081ff`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800081ff`

## pseudocode

```c
__int64 __fastcall PsmRegisterServiceProcess(int a1, __int64 a2, int a3, __int64 a4, __int64 a5, int a6)
{
  int v10; // eax
  int v11; // r9d
  int v12; // edx
  __int64 v14; // [rsp+58h] [rbp-40h] BYREF
  _QWORD v15[7]; // [rsp+60h] [rbp-38h] BYREF

  v14 = 0;
  v15[0] = qword_18000B020;
  v15[1] = PsmCltOpenActivationChannel;
  v10 = RtlRunOnceExecuteOnce(&PsmpActInitContext, PsmpAcquireContextHandle, v15, &v14);
  v12 = 0;
  if ( v10 < 0 )
    v12 = v10;
  if ( v12 >= 0 )
  {
    v12 = PsmCltRegisterProcess(v14, a1, a6, v11, a4, a2, a3, a5, 8);
    if ( v12 >= 0 )
      return 0;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180008160  mov     r11, rsp
0x180008163  push    rbx
0x180008164  push    rsi
0x180008165  push    rdi
0x180008166  push    r14
0x180008168  sub     rsp, 78h
0x18000816c  mov     rbx, r9
0x18000816f  mov     edi, r8d
0x180008172  mov     rsi, rdx
0x180008175  mov     r14, rcx
0x180008178  mov     qword ptr [r11-40h], 0
0x180008180  lea     rax, qword_18000B020
0x180008187  mov     [r11-38h], rax
0x18000818b  lea     rax, PsmCltOpenActivationChannel
0x180008192  mov     [r11-30h], rax
0x180008196  lea     r9, [r11-40h]
0x18000819a  lea     r8, [r11-38h]
0x18000819e  lea     rdx, PsmpAcquireContextHandle
0x1800081a5  lea     rcx, PsmpActInitContext
0x1800081ac  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800081b2  xor     edx, edx
0x1800081b4  test    eax, eax
0x1800081b6  cmovs   edx, eax
0x1800081b9  test    edx, edx
0x1800081bb  js      short loc_180008211
0x1800081bd  mov     [rsp+98h+var_58], 8
0x1800081c5  mov     rax, [rsp+98h+arg_20]
0x1800081cd  mov     [rsp+98h+var_60], rax
0x1800081d2  mov     [rsp+98h+var_68], edi
0x1800081d6  mov     [rsp+98h+var_70], rsi
0x1800081db  mov     [rsp+98h+var_78], rbx
0x1800081e0  mov     r8d, [rsp+98h+arg_28]
0x1800081e8  mov     rdx, r14
0x1800081eb  mov     rcx, [rsp+98h+var_40]
0x1800081f0  call    PsmCltRegisterProcess
0x1800081f5  mov     edx, eax
0x1800081f7  mov     [rsp+98h+var_48], eax
0x1800081fb  jmp     short loc_18000820B
0x1800081fd  mov     ecx, eax; Status
0x1800081ff  call    cs:__imp_I_RpcMapWin32Status
0x180008205  mov     edx, eax
0x180008207  mov     [rsp+98h+var_48], eax
0x18000820b  test    edx, edx
0x18000820d  js      short loc_180008211
0x18000820f  xor     edx, edx
0x180008211  mov     eax, edx
0x180008213  add     rsp, 78h
0x180008217  pop     r14
0x180008219  pop     rdi
0x18000821a  pop     rsi
0x18000821b  pop     rbx
0x18000821c  retn
0x180009f92  push    rbp
0x180009f94  sub     rsp, 50h
0x180009f98  mov     rbp, rdx
0x180009f9b  mov     rcx, [rcx]
0x180009f9e  mov     ecx, [rcx]; ExceptionCode
0x180009fa0  call    cs:__imp_RpcExceptionFilter
0x180009fa6  nop
0x180009fa7  add     rsp, 50h
0x180009fab  pop     rbp
0x180009fac  retn
```

# LdrpWaitForInitializationComplete

- ea: `0x1800d58a0`
- end: `0x1800d5950`
- name: `LdrpWaitForInitializationComplete`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800d5958`
- `0x1800d5d68`

## callees

- `0x18001eb80`
- `0x1800d58a0`
- `0x18015e350`
- `0x18015e950`

## string_xrefs

- `0x1800d58d3`: `LdrpWaitForInitializationComplete`
- `0x1800d591c`: `LdrpWaitForInitializationComplete`

## pseudocode

```c
void __fastcall LdrpWaitForInitializationComplete(_DWORD *a1, HANDLE *a2)
{
  NTSTATUS ArgList; // eax
  int v4; // eax
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  if ( *a2 )
  {
    ArgList = NtWaitForSingleObject(*a2, 0, 0);
    if ( ArgList >= 0 )
      return;
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      1290,
      (int)"LdrpWaitForInitializationComplete",
      1,
      "NtWaitForSingleObject failed with status 0x%08lx, fallback to delay loop\n",
      ArgList);
  }
  v5 = -300000;
  while ( *a1 == 1 )
  {
    v4 = ZwDelayExecution(0, &v5);
    if ( v4 < 0 )
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        1308,
        (int)"LdrpWaitForInitializationComplete",
        1,
        "Delaying execution for hot patch initialization failed with status 0x%08lx\n",
        v4);
  }
}

```

## disassembly

```asm
0x1800d58a0  push    rbx
0x1800d58a2  sub     rsp, 30h
0x1800d58a6  mov     rbx, rcx
0x1800d58a9  mov     [rsp+38h+arg_8], 0
0x1800d58b2  mov     rcx, [rdx]; Handle
0x1800d58b5  test    rcx, rcx
0x1800d58b8  jz      short loc_1800D58FD
0x1800d58ba  xor     r8d, r8d; Timeout
0x1800d58bd  xor     edx, edx; Alertable
0x1800d58bf  call    NtWaitForSingleObject
0x1800d58c4  test    eax, eax
0x1800d58c6  js      short loc_1800D58CF
0x1800d58c8  add     rsp, 30h
0x1800d58cc  pop     rbx
0x1800d58cd  retn
0x1800d58cf  mov     dword ptr [rsp+38h+ArgList], eax; ArgList
0x1800d58d3  lea     r8, aLdrpwaitforini; "LdrpWaitForInitializationComplete"
0x1800d58da  lea     rax, aNtwaitforsingl_0; "NtWaitForSingleObject failed with statu"...
0x1800d58e1  mov     r9d, 1; int
0x1800d58e7  mov     edx, 50Ah; int
0x1800d58ec  mov     [rsp+38h+Format], rax; Format
0x1800d58f1  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800d58f8  call    LdrpLogInternal
0x1800d58fd  mov     [rsp+38h+arg_8], 0FFFFFFFFFFFB6C20h
0x1800d5906  jmp     short loc_1800D5946
0x1800d5908  lea     rdx, [rsp+38h+arg_8]
0x1800d590d  xor     ecx, ecx
0x1800d590f  call    ZwDelayExecution
0x1800d5914  test    eax, eax
0x1800d5916  jns     short loc_1800D5946
0x1800d5918  mov     dword ptr [rsp+38h+ArgList], eax; ArgList
0x1800d591c  lea     r8, aLdrpwaitforini; "LdrpWaitForInitializationComplete"
0x1800d5923  lea     rax, aDelayingExecut; "Delaying execution for hot patch initia"...
0x1800d592a  mov     r9d, 1; int
0x1800d5930  mov     edx, 51Ch; int
0x1800d5935  mov     [rsp+38h+Format], rax; Format
0x1800d593a  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800d5941  call    LdrpLogInternal
0x1800d5946  cmp     dword ptr [rbx], 1
0x1800d5949  jz      short loc_1800D5908
0x1800d594b  jmp     loc_1800D58C8
```

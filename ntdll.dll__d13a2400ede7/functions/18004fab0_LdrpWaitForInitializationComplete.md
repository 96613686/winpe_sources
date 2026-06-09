# LdrpWaitForInitializationComplete

- ea: `0x18004fab0`
- end: `0x18004fb60`
- name: `LdrpWaitForInitializationComplete`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004fb68`
- `0x18004ff78`

## callees

- `0x18001eb80`
- `0x18004fab0`
- `0x18015eb60`
- `0x18015f160`

## string_xrefs

- `0x18004fae3`: `LdrpWaitForInitializationComplete`
- `0x18004fb2c`: `LdrpWaitForInitializationComplete`

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
0x18004fab0  push    rbx
0x18004fab2  sub     rsp, 30h
0x18004fab6  mov     rbx, rcx
0x18004fab9  mov     [rsp+38h+arg_8], 0
0x18004fac2  mov     rcx, [rdx]; Handle
0x18004fac5  test    rcx, rcx
0x18004fac8  jz      short loc_18004FB0D
0x18004faca  xor     r8d, r8d; Timeout
0x18004facd  xor     edx, edx; Alertable
0x18004facf  call    NtWaitForSingleObject
0x18004fad4  test    eax, eax
0x18004fad6  js      short loc_18004FADF
0x18004fad8  add     rsp, 30h
0x18004fadc  pop     rbx
0x18004fadd  retn
0x18004fadf  mov     dword ptr [rsp+38h+ArgList], eax; ArgList
0x18004fae3  lea     r8, aLdrpwaitforini; "LdrpWaitForInitializationComplete"
0x18004faea  lea     rax, aNtwaitforsingl_0; "NtWaitForSingleObject failed with statu"...
0x18004faf1  mov     r9d, 1; int
0x18004faf7  mov     edx, 50Ah; int
0x18004fafc  mov     [rsp+38h+Format], rax; Format
0x18004fb01  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18004fb08  call    LdrpLogInternal
0x18004fb0d  mov     [rsp+38h+arg_8], 0FFFFFFFFFFFB6C20h
0x18004fb16  jmp     short loc_18004FB56
0x18004fb18  lea     rdx, [rsp+38h+arg_8]
0x18004fb1d  xor     ecx, ecx
0x18004fb1f  call    ZwDelayExecution
0x18004fb24  test    eax, eax
0x18004fb26  jns     short loc_18004FB56
0x18004fb28  mov     dword ptr [rsp+38h+ArgList], eax; ArgList
0x18004fb2c  lea     r8, aLdrpwaitforini; "LdrpWaitForInitializationComplete"
0x18004fb33  lea     rax, aDelayingExecut; "Delaying execution for hot patch initia"...
0x18004fb3a  mov     r9d, 1; int
0x18004fb40  mov     edx, 51Ch; int
0x18004fb45  mov     [rsp+38h+Format], rax; Format
0x18004fb4a  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18004fb51  call    LdrpLogInternal
0x18004fb56  cmp     dword ptr [rbx], 1
0x18004fb59  jz      short loc_18004FB18
0x18004fb5b  jmp     loc_18004FAD8
```

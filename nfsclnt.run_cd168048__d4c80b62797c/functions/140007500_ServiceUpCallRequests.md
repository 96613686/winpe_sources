# ServiceUpCallRequests

- ea: `0x140007500`
- end: `0x140007627`
- name: `ServiceUpCallRequests`
- size: `295`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1400072b8`
- `0x140007500`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14000757a`
- `KERNEL32!WaitForSingleObject` at `0x1400075f9`
- `KERNEL32!WaitForSingleObject` at `0x14000757a`
- `KERNEL32!WaitForSingleObject` at `0x1400075f9`
- `ntdll!NtDeviceIoControlFile` at `0x140007566`
- `ntdll!NtDeviceIoControlFile` at `0x1400075e5`
- `ntdll!NtDeviceIoControlFile` at `0x140007566`
- `ntdll!NtDeviceIoControlFile` at `0x1400075e5`

## pseudocode

```c
NTSTATUS __fastcall ServiceUpCallRequests(HANDLE *Parameter)
{
  char *OutputBuffer; // rsi
  NTSTATUS result; // eax
  __int64 v4; // r9
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  ULONG InputBufferLength; // [rsp+70h] [rbp+8h] BYREF

  InputBufferLength = 0;
  IoStatusBlock = 0;
  OutputBuffer = (char *)(Parameter + 3);
  do
  {
    result = NtDeviceIoControlFile(
               *(&hObject + 1),
               Parameter[2],
               0,
               0,
               &IoStatusBlock,
               0x2000E004u,
               0,
               0,
               OutputBuffer,
               0x800u);
    if ( result == 259 )
    {
      WaitForSingleObject(Parameter[2], 0xFFFFFFFF);
      result = IoStatusBlock.Status;
    }
    if ( result >= 0 )
    {
      ServiceUpCall(
        (unsigned int *)OutputBuffer,
        IoStatusBlock.Information,
        (__int64)(Parameter + 259),
        v4,
        &InputBufferLength);
      result = NtDeviceIoControlFile(
                 *(&hObject + 1),
                 Parameter[2],
                 0,
                 0,
                 &IoStatusBlock,
                 0x2000E008u,
                 Parameter + 259,
                 InputBufferLength,
                 Parameter + 259,
                 0x800u);
      if ( result == 259 )
      {
        WaitForSingleObject(Parameter[2], 0xFFFFFFFF);
        result = IoStatusBlock.Status;
      }
    }
  }
  while ( result != -1073741536 && result != 128 );
  return result;
}

```

## disassembly

```asm
0x140007500  mov     rax, rsp
0x140007503  mov     [rax+10h], rbx
0x140007507  mov     [rax+18h], rsi
0x14000750b  push    rdi
0x14000750c  sub     rsp, 60h
0x140007510  xorps   xmm0, xmm0
0x140007513  mov     dword ptr [rax+8], 0
0x14000751a  movups  xmmword ptr [rax-18h], xmm0
0x14000751e  mov     rdi, rcx
0x140007521  lea     rsi, [rcx+18h]
0x140007525  mov     rdx, [rdi+10h]; Event
0x140007529  lea     rax, [rsp+68h+var_18]
0x14000752e  mov     rcx, qword ptr cs:hObject+8; FileHandle
0x140007535  xor     r9d, r9d; ApcContext
0x140007538  mov     [rsp+68h+OutputBufferLength], 800h; OutputBufferLength
0x140007540  xor     r8d, r8d; ApcRoutine
0x140007543  mov     [rsp+68h+OutputBuffer], rsi; OutputBuffer
0x140007548  mov     [rsp+68h+InputBufferLength], 0; InputBufferLength
0x140007550  mov     [rsp+68h+InputBuffer], 0; InputBuffer
0x140007559  mov     [rsp+68h+IoControlCode], 2000E004h; IoControlCode
0x140007561  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x140007566  call    cs:__imp_NtDeviceIoControlFile
0x14000756c  cmp     eax, 103h
0x140007571  jnz     short loc_140007584
0x140007573  mov     rcx, [rdi+10h]; hHandle
0x140007577  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000757a  call    cs:__imp_WaitForSingleObject
0x140007580  mov     eax, dword ptr [rsp+68h+var_18]
0x140007584  test    eax, eax
0x140007586  js      short loc_140007603
0x140007588  mov     edx, dword ptr [rsp+68h+var_18.Information]
0x14000758c  lea     rax, [rsp+68h+arg_0]
0x140007591  lea     rbx, [rdi+818h]
0x140007598  mov     [rsp+68h+IoStatusBlock], rax
0x14000759d  mov     r8, rbx
0x1400075a0  mov     rcx, rsi
0x1400075a3  call    ServiceUpCall
0x1400075a8  mov     eax, [rsp+68h+arg_0]
0x1400075ac  xor     r9d, r9d; ApcContext
0x1400075af  mov     rdx, [rdi+10h]; Event
0x1400075b3  xor     r8d, r8d; ApcRoutine
0x1400075b6  mov     rcx, qword ptr cs:hObject+8; FileHandle
0x1400075bd  mov     [rsp+68h+OutputBufferLength], 800h; OutputBufferLength
0x1400075c5  mov     [rsp+68h+OutputBuffer], rbx; OutputBuffer
0x1400075ca  mov     [rsp+68h+InputBufferLength], eax; InputBufferLength
0x1400075ce  lea     rax, [rsp+68h+var_18]
0x1400075d3  mov     [rsp+68h+InputBuffer], rbx; InputBuffer
0x1400075d8  mov     [rsp+68h+IoControlCode], 2000E008h; IoControlCode
0x1400075e0  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1400075e5  call    cs:__imp_NtDeviceIoControlFile
0x1400075eb  cmp     eax, 103h
0x1400075f0  jnz     short loc_140007603
0x1400075f2  mov     rcx, [rdi+10h]; hHandle
0x1400075f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400075f9  call    cs:__imp_WaitForSingleObject
0x1400075ff  mov     eax, dword ptr [rsp+68h+var_18]
0x140007603  cmp     eax, 0C0000120h
0x140007608  jz      short loc_140007615
0x14000760a  cmp     eax, 80h
0x14000760f  jnz     loc_140007525
0x140007615  lea     r11, [rsp+68h+var_8]
0x14000761a  mov     rbx, [r11+18h]
0x14000761e  mov     rsi, [r11+20h]
0x140007622  mov     rsp, r11
0x140007625  pop     rdi
0x140007626  retn
```

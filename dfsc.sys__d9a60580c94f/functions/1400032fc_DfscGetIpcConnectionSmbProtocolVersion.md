# DfscGetIpcConnectionSmbProtocolVersion

- ea: `0x1400032fc`
- end: `0x1400033cc`
- name: `DfscGetIpcConnectionSmbProtocolVersion`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001b230`

## callees

- `0x1400032fc`
- `0x1400033d4`
- `0x140005f70`
- `0x140006380`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x140003356`
- `ntoskrnl!ZwQueryInformationFile` at `0x140003356`

## pseudocode

```c
__int64 __fastcall DfscGetIpcConnectionSmbProtocolVersion(__int64 a1, _WORD *a2, _WORD *a3)
{
  void *v6; // rcx
  NTSTATUS v7; // ebx
  __int64 v8; // r8
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-B8h] BYREF
  _WORD FileInformation[64]; // [rsp+40h] [rbp-A8h] BYREF

  memset(FileInformation, 0, 0x74u);
  v6 = *(void **)(a1 + 40);
  IoStatusBlock = 0;
  v7 = ZwQueryInformationFile(v6, &IoStatusBlock, FileInformation, 0x74u, FileRemoteProtocolInformation);
  if ( v7 >= 0 )
  {
    *a2 = FileInformation[4];
    *a3 = FileInformation[5];
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_Ddd(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned __int16)*a2,
      v8,
      (unsigned int)v7,
      (unsigned __int16)*a2,
      (unsigned __int16)*a3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400032fc  push    rbx
0x1400032fe  push    rsi
0x1400032ff  push    rdi
0x140003300  sub     rsp, 0D0h
0x140003307  mov     rax, cs:__security_cookie
0x14000330e  xor     rax, rsp
0x140003311  mov     [rsp+0E8h+var_28], rax
0x140003319  mov     rdi, rdx
0x14000331c  mov     rsi, r8
0x14000331f  xor     edx, edx; Val
0x140003321  mov     rbx, rcx
0x140003324  lea     rcx, [rsp+0E8h+FileInformation]; void *
0x140003329  lea     r8d, [rdx+74h]; Size
0x14000332d  call    memset
0x140003332  mov     rcx, [rbx+28h]; FileHandle
0x140003336  lea     r8, [rsp+0E8h+FileInformation]; FileInformation
0x14000333b  xorps   xmm0, xmm0
0x14000333e  mov     [rsp+0E8h+FileInformationClass], 37h ; '7'; FileInformationClass
0x140003346  mov     r9d, 74h ; 't'; Length
0x14000334c  lea     rdx, [rsp+0E8h+IoStatusBlock]; IoStatusBlock
0x140003351  movups  xmmword ptr [rsp+0E8h+IoStatusBlock], xmm0
0x140003356  call    cs:__imp_ZwQueryInformationFile
0x14000335d  nop     dword ptr [rax+rax+00h]
0x140003362  mov     ebx, eax
0x140003364  test    eax, eax
0x140003366  js      short loc_140003378
0x140003368  movzx   ecx, [rsp+0E8h+var_A0]
0x14000336d  mov     [rdi], cx
0x140003370  movzx   ecx, [rsp+0E8h+var_9E]
0x140003375  mov     [rsi], cx
0x140003378  mov     rcx, cs:WPP_GLOBAL_Control
0x14000337f  lea     rax, WPP_GLOBAL_Control
0x140003386  cmp     rcx, rax
0x140003389  jz      short loc_1400033AE
0x14000338b  test    dword ptr [rcx+2Ch], 400000h
0x140003392  jz      short loc_1400033AE
0x140003394  movzx   eax, word ptr [rsi]
0x140003397  mov     r9d, ebx
0x14000339a  movzx   edx, word ptr [rdi]
0x14000339d  mov     rcx, [rcx+18h]
0x1400033a1  mov     [rsp+0E8h+var_C0], eax
0x1400033a5  mov     [rsp+0E8h+FileInformationClass], edx
0x1400033a9  call    WPP_SF_Ddd
0x1400033ae  mov     eax, ebx
0x1400033b0  mov     rcx, [rsp+0E8h+var_28]
0x1400033b8  xor     rcx, rsp; StackCookie
0x1400033bb  call    __security_check_cookie
0x1400033c0  add     rsp, 0D0h
0x1400033c7  pop     rdi
0x1400033c8  pop     rsi
0x1400033c9  pop     rbx
0x1400033ca  retn
```

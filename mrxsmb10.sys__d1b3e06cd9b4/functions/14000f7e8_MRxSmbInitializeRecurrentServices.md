# MRxSmbInitializeRecurrentServices

- ea: `0x14000f7e8`
- end: `0x14000f8ac`
- name: `MRxSmbInitializeRecurrentServices`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400328a0`

## callees

- `0x14000dfa8`
- `0x14000f7e8`
- `0x14003f870`
- `0x14003f98c`

## import_xrefs

- `mrxsmb!MRxSmbInitializeRecurrentService` at `0x14000f837`
- `mrxsmb!MRxSmbInitializeRecurrentService` at `0x14000f837`
- `mrxsmb!MRxSmbDeviceObject` at `0x14000f812`

## pseudocode

```c
__int64 MRxSmbInitializeRecurrentServices()
{
  __int64 v1; // [rsp+50h] [rbp+8h] BYREF

  v1 = 300000000;
  MRxSmbInitializeRecurrentService(
    MRxSmbEchoProbeServiceContext,
    SmbCeProbeServers,
    MRxSmbEchoProbeServiceContext,
    &v1,
    MRxSmbDeviceObject);
  return (unsigned int)MRxSmbInitializeEchoProbeService();
}

```

## disassembly

```asm
0x14000f7e8  mov     rax, rsp
0x14000f7eb  mov     [rax+10h], rbx
0x14000f7ef  push    rdi
0x14000f7f0  sub     rsp, 40h
0x14000f7f4  mov     dword ptr [rax-14h], 0C000000Dh
0x14000f7fb  mov     qword ptr [rax+8], 0
0x14000f803  xor     dil, dil
0x14000f806  mov     [rax-18h], dil
0x14000f80a  mov     qword ptr [rax+8], 11E1A300h
0x14000f812  mov     rax, cs:__imp_MRxSmbDeviceObject
0x14000f819  mov     rcx, [rax]
0x14000f81c  mov     [rsp+48h+var_28], rcx
0x14000f821  lea     r9, [rsp+48h+arg_0]
0x14000f826  lea     rcx, MRxSmbEchoProbeServiceContext
0x14000f82d  mov     r8, rcx
0x14000f830  lea     rdx, SmbCeProbeServers
0x14000f837  call    cs:__imp_MRxSmbInitializeRecurrentService
0x14000f83e  nop     dword ptr [rax+rax+00h]
0x14000f843  call    MRxSmbInitializeEchoProbeService
0x14000f848  mov     ebx, eax
0x14000f84a  mov     [rsp+48h+var_14], eax
0x14000f84e  movzx   eax, dil
0x14000f852  mov     ecx, 1
0x14000f857  test    ebx, ebx
0x14000f859  cmovz   eax, ecx
0x14000f85c  mov     [rsp+48h+var_18], al
0x14000f860  test    ebx, ebx
0x14000f862  jz      short loc_14000F89E
0x14000f864  test    al, al
0x14000f866  jz      short loc_14000F89E
0x14000f868  lea     rax, WPP_GLOBAL_Control
0x14000f86f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f876  cmp     rcx, rax
0x14000f879  jz      short loc_14000F899
0x14000f87b  test    dword ptr [rcx+2Ch], 200h
0x14000f882  jz      short loc_14000F899
0x14000f884  mov     edx, 16h
0x14000f889  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x14000f890  mov     rcx, [rcx+18h]
0x14000f894  call    WPP_SF_
0x14000f899  call    MRxSmbTearDownEchoProbeService
0x14000f89e  mov     eax, ebx
0x14000f8a0  mov     rbx, [rsp+48h+arg_8]
0x14000f8a5  add     rsp, 40h
0x14000f8a9  pop     rdi
0x14000f8aa  retn
0x140016fc6  push    rbp
0x140016fc8  sub     rsp, 30h
0x140016fcc  mov     rbp, rdx
0x140016fcf  cmp     dword ptr [rbp+34h], 0
0x140016fd3  jz      short loc_140017013
0x140016fd5  cmp     byte ptr [rbp+30h], 0
0x140016fd9  jz      short loc_140017013
0x140016fdb  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140016fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x140016fe9  cmp     rcx, rax
0x140016fec  jz      short loc_14001700D
0x140016fee  mov     eax, [rcx+2Ch]
0x140016ff1  bt      eax, 9
0x140016ff5  jnb     short loc_14001700D
0x140016ff7  mov     edx, 16h
0x140016ffc  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x140017003  mov     rcx, [rcx+18h]
0x140017007  call    WPP_SF_
0x14001700c  nop
0x14001700d  call    MRxSmbTearDownEchoProbeService
0x140017012  nop
0x140017013  add     rsp, 30h
0x140017017  pop     rbp
0x140017018  retn
```

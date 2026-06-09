# lldpOpenPort

- ea: `0x14000fd1c`
- end: `0x14000fdc8`
- name: `lldpOpenPort`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000efd0`

## callees

- `0x1400047c4`
- `0x140004a60`
- `0x14000628c`
- `0x14000fd1c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000fd42`
- `ntoskrnl!ExAllocatePool2` at `0x14000fd42`

## pseudocode

```c
__int64 __fastcall lldpOpenPort(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 Pool2; // rax

  Pool2 = ExAllocatePool2(64, 48, 1346653260);
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 4) = 0;
    *(_DWORD *)(Pool2 + 12) = 0;
    *(_QWORD *)(Pool2 + 32) = 0;
    *(_DWORD *)Pool2 = 1866746956;
    *(_QWORD *)(Pool2 + 24) = a1;
    *(_QWORD *)(Pool2 + 16) = a2;
    *(_QWORD *)(Pool2 + 40) = a3;
    *(_DWORD *)(Pool2 + 32) = 0;
    lldpReferencePort(a1);
    return lldpReferenceClient(a2);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_044ea0c6c24b336fce62604a60a90133_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x14000fd1c  mov     [rsp+arg_0], rbx
0x14000fd21  mov     [rsp+arg_8], rsi
0x14000fd26  push    rdi
0x14000fd27  sub     rsp, 20h
0x14000fd2b  mov     rbx, rdx
0x14000fd2e  mov     rsi, r8
0x14000fd31  mov     edx, 30h ; '0'
0x14000fd36  mov     rdi, rcx
0x14000fd39  mov     r8d, 50444C4Ch
0x14000fd3f  lea     ecx, [rdx+10h]
0x14000fd42  call    cs:__imp_ExAllocatePool2
0x14000fd49  nop     dword ptr [rax+rax+00h]
0x14000fd4e  xor     ecx, ecx
0x14000fd50  test    rax, rax
0x14000fd53  jnz     short loc_14000FD87
0x14000fd55  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd5c  lea     rax, WPP_GLOBAL_Control
0x14000fd63  cmp     rcx, rax
0x14000fd66  jz      short loc_14000FD83
0x14000fd68  cmp     byte ptr [rcx+29h], 2
0x14000fd6c  jb      short loc_14000FD83
0x14000fd6e  mov     rcx, [rcx+18h]
0x14000fd72  lea     r8, WPP_044ea0c6c24b336fce62604a60a90133_Traceguids
0x14000fd79  mov     edx, 0Ah
0x14000fd7e  call    WPP_SF_
0x14000fd83  xor     eax, eax
0x14000fd85  jmp     short loc_14000FDB7
0x14000fd87  mov     [rax+4], rcx
0x14000fd8b  mov     [rax+0Ch], ecx
0x14000fd8e  mov     [rax+20h], rcx
0x14000fd92  mov     dword ptr [rax], 6F444C4Ch
0x14000fd98  mov     [rax+18h], rdi
0x14000fd9c  mov     [rax+10h], rbx
0x14000fda0  mov     [rax+28h], rsi
0x14000fda4  mov     [rax+20h], ecx
0x14000fda7  mov     rcx, rdi
0x14000fdaa  call    lldpReferencePort
0x14000fdaf  mov     rcx, rbx
0x14000fdb2  call    lldpReferenceClient
0x14000fdb7  mov     rbx, [rsp+28h+arg_0]
0x14000fdbc  mov     rsi, [rsp+28h+arg_8]
0x14000fdc1  add     rsp, 20h
0x14000fdc5  pop     rdi
0x14000fdc6  retn
```

# DfscFsctrlRemoveDriveLetter

- ea: `0x140028004`
- end: `0x1400281a4`
- name: `DfscFsctrlRemoveDriveLetter`
- size: `416`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config`

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x140005f70`
- `0x140014658`
- `0x1400187e4`
- `0x14002545c`
- `0x140026bf0`
- `0x140028004`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400280da`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400280da`

## pseudocode

```c
__int64 __fastcall DfscFsctrlRemoveDriveLetter(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, unsigned int *a5)
{
  int v8; // ecx
  int ContainerContextFromIrp; // ebx
  int inited; // eax
  int v11; // eax
  __int64 v13; // [rsp+40h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v15[8]; // [rsp+58h] [rbp-40h] BYREF

  v13 = 0;
  DestinationString = 0;
  if ( (a3 & 1) != 0 )
    return (unsigned int)-1073741811;
  if ( a3 - 8 > 0xFFF6 )
    return (unsigned int)-1073741811;
  if ( !a2 )
    return (unsigned int)-1073741811;
  v8 = *a5;
  if ( *a5 < 8 || !a4 || *(_WORD *)(a2 + 2LL * (((a3 - 4) >> 1) - 1) + 4) || (((_BYTE)v8 - 4) & 1) != 0 )
  {
    return (unsigned int)-1073741811;
  }
  else if ( (unsigned int)(v8 - 4) >= 4 )
  {
    if ( *(_WORD *)(a2 + 4) == 92 || *(_WORD *)(a2 + 6) != 58 )
      inited = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)(a2 + 4));
    else
      inited = DfscGetNormalizedDriveLetterUnicodeString((wint_t *)(a2 + 4), a3, (__int64)v15, &DestinationString);
    ContainerContextFromIrp = inited;
    if ( !inited )
    {
      ContainerContextFromIrp = DfscGetContainerContextFromIrp(a1, &v13);
      if ( ContainerContextFromIrp >= 0 )
      {
        v11 = DfscDeleteNetUseConnection(v13, (__int64)&DestinationString, a1, *(_DWORD *)a2, a4, a5, 0);
        ContainerContextFromIrp = v11;
        if ( v11 )
        {
          if ( v11 == -2147483643 )
          {
            *a4 = *a5;
            *(_QWORD *)(a1 + 56) = 4;
          }
        }
        else
        {
          *(_QWORD *)(a1 + 56) = *a5;
          if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.DeviceObject & 4) == 0 )
            DfscReadLinkedConnectionPolicy();
          if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.DeviceObject & 2) != 0 )
            DfscDeleteLinkedConnection(v13, (__int64)&DestinationString, a1, *(_DWORD *)a2);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-1073741789;
  }
  return (unsigned int)ContainerContextFromIrp;
}

```

## disassembly

```asm
0x140028004  mov     [rsp+arg_10], rbx
0x140028009  push    rbp
0x14002800a  push    rsi
0x14002800b  push    rdi
0x14002800c  push    r14
0x14002800e  push    r15
0x140028010  sub     rsp, 70h
0x140028014  mov     rax, cs:__security_cookie
0x14002801b  xor     rax, rsp
0x14002801e  mov     [rsp+98h+var_38], rax
0x140028023  mov     r14, [rsp+98h+arg_20]
0x14002802b  xor     ebp, ebp
0x14002802d  mov     [rsp+98h+var_58], rbp
0x140028032  xorps   xmm0, xmm0
0x140028035  mov     r15, r9
0x140028038  mov     r10d, r8d
0x14002803b  mov     rdi, rdx
0x14002803e  mov     rsi, rcx
0x140028041  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x140028046  test    r8b, 1
0x14002804a  jnz     loc_14002817B
0x140028050  lea     eax, [r8-8]
0x140028054  cmp     eax, 0FFF6h
0x140028059  ja      loc_14002817B
0x14002805f  test    rdx, rdx
0x140028062  jz      loc_14002817B
0x140028068  mov     ecx, [r14]
0x14002806b  cmp     ecx, 8
0x14002806e  jb      loc_14002817B
0x140028074  test    r9, r9
0x140028077  jz      loc_14002817B
0x14002807d  lea     eax, [r8-4]
0x140028081  shr     eax, 1
0x140028083  dec     eax
0x140028085  cmp     [rdx+rax*2+4], bp
0x14002808a  jnz     loc_14002817B
0x140028090  lea     eax, [rcx-4]
0x140028093  test    al, 1
0x140028095  jnz     loc_14002817B
0x14002809b  cmp     eax, 4
0x14002809e  jnb     short loc_1400280AA
0x1400280a0  mov     ebx, 0C0000023h
0x1400280a5  jmp     loc_140028180
0x1400280aa  lea     rax, [rdx+4]
0x1400280ae  cmp     word ptr [rax], 5Ch ; '\'
0x1400280b2  jz      short loc_1400280D2
0x1400280b4  cmp     word ptr [rdx+6], 3Ah ; ':'
0x1400280b9  jnz     short loc_1400280D2
0x1400280bb  lea     r9, [rsp+98h+DestinationString]
0x1400280c0  mov     edx, r10d
0x1400280c3  lea     r8, [rsp+98h+var_40]
0x1400280c8  mov     rcx, rax
0x1400280cb  call    DfscGetNormalizedDriveLetterUnicodeString
0x1400280d0  jmp     short loc_1400280E6
0x1400280d2  mov     rdx, rax; SourceString
0x1400280d5  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1400280da  call    cs:__imp_RtlInitUnicodeStringEx
0x1400280e1  nop     dword ptr [rax+rax+00h]
0x1400280e6  mov     ebx, eax
0x1400280e8  test    eax, eax
0x1400280ea  jnz     loc_140028180
0x1400280f0  lea     rdx, [rsp+98h+var_58]
0x1400280f5  mov     rcx, rsi
0x1400280f8  call    DfscGetContainerContextFromIrp
0x1400280fd  mov     ebx, eax
0x1400280ff  test    eax, eax
0x140028101  js      short loc_140028180
0x140028103  mov     r9d, [rdi]
0x140028106  lea     rdx, [rsp+98h+DestinationString]
0x14002810b  mov     rcx, [rsp+98h+var_58]
0x140028110  mov     r8, rsi
0x140028113  mov     [rsp+98h+var_68], bpl
0x140028118  mov     [rsp+98h+var_70], r14
0x14002811d  mov     [rsp+98h+var_78], r15
0x140028122  call    DfscDeleteNetUseConnection
0x140028127  mov     ebx, eax
0x140028129  test    eax, eax
0x14002812b  jnz     short loc_140028164
0x14002812d  mov     eax, [r14]
0x140028130  mov     [rsi+38h], rax
0x140028134  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x14002813a  test    al, 4
0x14002813c  jnz     short loc_140028143
0x14002813e  call    DfscReadLinkedConnectionPolicy
0x140028143  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x140028149  test    al, 2
0x14002814b  jz      short loc_140028180
0x14002814d  mov     r9d, [rdi]
0x140028150  lea     rdx, [rsp+98h+DestinationString]
0x140028155  mov     rcx, [rsp+98h+var_58]
0x14002815a  mov     r8, rsi
0x14002815d  call    DfscDeleteLinkedConnection
0x140028162  jmp     short loc_140028180
0x140028164  cmp     eax, 80000005h
0x140028169  jnz     short loc_140028180
0x14002816b  mov     eax, [r14]
0x14002816e  mov     [r15], eax
0x140028171  mov     qword ptr [rsi+38h], 4
0x140028179  jmp     short loc_140028180
0x14002817b  mov     ebx, 0C000000Dh
0x140028180  mov     eax, ebx
0x140028182  mov     rcx, [rsp+98h+var_38]
0x140028187  xor     rcx, rsp; StackCookie
0x14002818a  call    __security_check_cookie
0x14002818f  mov     rbx, [rsp+98h+arg_10]
0x140028197  add     rsp, 70h
0x14002819b  pop     r15
0x14002819d  pop     r14
0x14002819f  pop     rdi
0x1400281a0  pop     rsi
0x1400281a1  pop     rbp
0x1400281a2  retn
```

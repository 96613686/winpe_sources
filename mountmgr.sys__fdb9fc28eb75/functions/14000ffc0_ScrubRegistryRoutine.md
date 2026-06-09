# ScrubRegistryRoutine

- ea: `0x14000ffc0`
- end: `0x14001009e`
- name: `ScrubRegistryRoutine`
- size: `222`
- prototype: `__int64 __usercall@<rax>(PCWSTR ValueName@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001ae0`
- `0x14000ffc0`

## import_xrefs

- `ntoskrnl!RtlDeleteRegistryValue` at `0x14001002f`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14001002f`
- `ntoskrnl!RtlCompareMemory` at `0x14001000d`
- `ntoskrnl!RtlCompareMemory` at `0x14001000d`

## string_xrefs

- `0x140010026`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall ScrubRegistryRoutine(
        PCWSTR ValueName,
        int a2,
        const void *a3,
        unsigned int a4,
        __int64 a5,
        _BYTE *a6)
{
  SIZE_T v6; // rbp
  _QWORD *i; // rdi
  unsigned __int16 *v10; // rcx
  NTSTATUS v11; // ebx
  __int64 v12; // r8

  v6 = a4;
  if ( a2 != 3 )
    return 0;
  for ( i = *(_QWORD **)(a5 + 16); i != (_QWORD *)(a5 + 16); i = (_QWORD *)*i )
  {
    v10 = (unsigned __int16 *)i[12];
    if ( v10 && *v10 == (_DWORD)v6 && RtlCompareMemory(v10 + 1, a3, v6) == v6 )
      return 0;
  }
  v11 = RtlDeleteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", ValueName);
  if ( v11 >= 0 )
  {
    *a6 = 1;
    return 3221225473LL;
  }
  else
  {
    *a6 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 329, v12, (unsigned int)v11);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x14000ffc0  push    rbx
0x14000ffc2  push    rbp
0x14000ffc3  push    rsi
0x14000ffc4  push    rdi
0x14000ffc5  push    r14
0x14000ffc7  push    r15
0x14000ffc9  sub     rsp, 28h
0x14000ffcd  mov     ebp, r9d
0x14000ffd0  mov     r15, r8
0x14000ffd3  mov     r14, rcx
0x14000ffd6  cmp     edx, 3
0x14000ffd9  jnz     loc_14001008E
0x14000ffdf  mov     rsi, [rsp+58h+arg_20]
0x14000ffe7  add     rsi, 10h
0x14000ffeb  mov     rdi, [rsi]
0x14000ffee  cmp     rdi, rsi
0x14000fff1  jz      short loc_140010023
0x14000fff3  mov     rcx, [rdi+60h]
0x14000fff7  test    rcx, rcx
0x14000fffa  jz      short loc_14001001E
0x14000fffc  movzx   eax, word ptr [rcx]
0x14000ffff  cmp     eax, ebp
0x140010001  jnz     short loc_14001001E
0x140010003  add     rcx, 2; Source1
0x140010007  mov     r8, rbp; Length
0x14001000a  mov     rdx, r15; Source2
0x14001000d  call    cs:__imp_RtlCompareMemory
0x140010014  nop     dword ptr [rax+rax+00h]
0x140010019  cmp     rax, rbp
0x14001001c  jz      short loc_14001008E
0x14001001e  mov     rdi, [rdi]
0x140010021  jmp     short loc_14000FFEE
0x140010023  mov     r8, r14; ValueName
0x140010026  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14001002d  xor     ecx, ecx; RelativeTo
0x14001002f  call    cs:__imp_RtlDeleteRegistryValue
0x140010036  nop     dword ptr [rax+rax+00h]
0x14001003b  mov     ebx, eax
0x14001003d  test    eax, eax
0x14001003f  jns     short loc_14001007C
0x140010041  mov     rcx, [rsp+58h+arg_28]
0x140010049  mov     byte ptr [rcx], 0
0x14001004c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010053  lea     rax, WPP_GLOBAL_Control
0x14001005a  cmp     rcx, rax
0x14001005d  jz      short loc_140010078
0x14001005f  mov     edx, [rcx+2Ch]
0x140010062  test    dl, 1
0x140010065  jz      short loc_140010078
0x140010067  mov     rcx, [rcx+18h]
0x14001006b  mov     edx, 149h
0x140010070  mov     r9d, ebx
0x140010073  call    WPP_SF_L
0x140010078  mov     eax, ebx
0x14001007a  jmp     short loc_140010090
0x14001007c  mov     rax, [rsp+58h+arg_28]
0x140010084  mov     byte ptr [rax], 1
0x140010087  mov     eax, 0C0000001h
0x14001008c  jmp     short loc_140010090
0x14001008e  xor     eax, eax
0x140010090  add     rsp, 28h
0x140010094  pop     r15
0x140010096  pop     r14
0x140010098  pop     rdi
0x140010099  pop     rsi
0x14001009a  pop     rbp
0x14001009b  pop     rbx
0x14001009c  retn
```

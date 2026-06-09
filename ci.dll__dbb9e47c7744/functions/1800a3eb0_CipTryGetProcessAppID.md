# CipTryGetProcessAppID

- ea: `0x1800a3eb0`
- end: `0x1800a408f`
- name: `CipTryGetProcessAppID`
- size: `479`
- prototype: `__int64 __fastcall(PRKPROCESS PROCESS, PUNICODE_STRING StringOut)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18006466c`
- `0x18009a008`
- `0x1800a3e10`
- `0x1800b5098`

## callees

- `0x18002bf20`
- `0x1800a3eb0`
- `0x1800a4240`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1800a3f27`
- `ntoskrnl!KeStackAttachProcess` at `0x1800a3f27`
- `ntoskrnl!RtlImageNtHeader` at `0x1800a3f46`
- `ntoskrnl!RtlImageNtHeader` at `0x1800a3f46`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a3f04`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a3f37`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a3f7e`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a3f04`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a3f37`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a3f7e`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a4002`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a402f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a4002`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a402f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800a405c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800a405c`

## pseudocode

```c
__int64 __fastcall CipTryGetProcessAppID(
        PRKPROCESS PROCESS,
        PUNICODE_STRING StringOut,
        __int64 a3,
        struct _UNICODE_STRING *a4)
{
  int OriginalFilenameAndVersionFromImageBase; // ebx
  void *ProcessSectionBaseAddress; // rax
  PIMAGE_NT_HEADERS v9; // rax
  DWORD SizeOfImage; // ebx
  void *v11; // rax
  int v13; // [rsp+30h] [rbp-A8h]
  __int64 v14; // [rsp+58h] [rbp-80h] BYREF
  UNICODE_STRING StringIn; // [rsp+60h] [rbp-78h] BYREF
  UNICODE_STRING v16; // [rsp+70h] [rbp-68h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+80h] [rbp-58h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  StringIn = 0;
  v16 = 0;
  v14 = 0;
  if ( ((__int64 (*)(void))PsGetProcessSectionBaseAddress)() )
  {
    KeStackAttachProcess(PROCESS, &ApcState);
    ProcessSectionBaseAddress = (void *)PsGetProcessSectionBaseAddress(PROCESS);
    v9 = RtlImageNtHeader(ProcessSectionBaseAddress);
    if ( !v9 || ((v9->OptionalHeader.Magic - 267) & 0xFEFF) != 0 )
    {
      OriginalFilenameAndVersionFromImageBase = -1073741701;
    }
    else
    {
      SizeOfImage = v9->OptionalHeader.SizeOfImage;
      v11 = (void *)PsGetProcessSectionBaseAddress(PROCESS);
      OriginalFilenameAndVersionFromImageBase = SIPolicyGetOriginalFilenameAndVersionFromImageBase(
                                                  v11,
                                                  SizeOfImage,
                                                  0,
                                                  &StringIn,
                                                  &v14,
                                                  0,
                                                  v13,
                                                  0,
                                                  &v16);
      if ( (unsigned int)(OriginalFilenameAndVersionFromImageBase + 1073741687) <= 2
        || OriginalFilenameAndVersionFromImageBase == -1073741793
        || OriginalFilenameAndVersionFromImageBase == -1073741308 )
      {
        OriginalFilenameAndVersionFromImageBase = -1073741275;
      }
      if ( OriginalFilenameAndVersionFromImageBase >= 0 )
      {
        if ( !StringOut
          || !StringIn.Buffer
          || (OriginalFilenameAndVersionFromImageBase = RtlDuplicateUnicodeString(0, &StringIn, StringOut),
              OriginalFilenameAndVersionFromImageBase >= 0) )
        {
          if ( a4 && v16.Buffer )
            OriginalFilenameAndVersionFromImageBase = RtlDuplicateUnicodeString(0, &v16, a4);
        }
      }
    }
    KeUnstackDetachProcess(&ApcState);
  }
  else
  {
    return 0;
  }
  return (unsigned int)OriginalFilenameAndVersionFromImageBase;
}

```

## disassembly

```asm
0x1800a3eb0  mov     r11, rsp
0x1800a3eb3  mov     [r11+18h], rbx
0x1800a3eb7  push    rsi
0x1800a3eb8  push    rdi
0x1800a3eb9  push    r14
0x1800a3ebb  sub     rsp, 0C0h
0x1800a3ec2  mov     rax, cs:__security_cookie
0x1800a3ec9  xor     rax, rsp
0x1800a3ecc  mov     [rsp+0D8h+var_28], rax
0x1800a3ed4  mov     rsi, r9
0x1800a3ed7  mov     r14, rdx
0x1800a3eda  mov     rdi, rcx
0x1800a3edd  xorps   xmm0, xmm0
0x1800a3ee0  movups  xmmword ptr [r11-58h], xmm0
0x1800a3ee5  movups  xmmword ptr [r11-48h], xmm0
0x1800a3eea  movups  xmmword ptr [r11-38h], xmm0
0x1800a3eef  movups  xmmword ptr [rsp+0D8h+StringIn.Length], xmm0
0x1800a3ef4  xorps   xmm1, xmm1
0x1800a3ef7  movups  xmmword ptr [rsp+0D8h+var_68.Length], xmm1
0x1800a3efc  mov     qword ptr [r11-80h], 0
0x1800a3f04  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1800a3f0b  nop     dword ptr [rax+rax+00h]
0x1800a3f10  test    rax, rax
0x1800a3f13  jnz     short loc_1800A3F1C
0x1800a3f15  xor     ebx, ebx
0x1800a3f17  jmp     loc_1800A4068
0x1800a3f1c  lea     rdx, [rsp+0D8h+ApcState]; ApcState
0x1800a3f24  mov     rcx, rdi; PROCESS
0x1800a3f27  call    cs:__imp_KeStackAttachProcess
0x1800a3f2e  nop     dword ptr [rax+rax+00h]
0x1800a3f33  nop
0x1800a3f34  mov     rcx, rdi
0x1800a3f37  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1800a3f3e  nop     dword ptr [rax+rax+00h]
0x1800a3f43  mov     rcx, rax; BaseAddress
0x1800a3f46  call    cs:__imp_RtlImageNtHeader
0x1800a3f4d  nop     dword ptr [rax+rax+00h]
0x1800a3f52  mov     rbx, rax
0x1800a3f55  test    rax, rax
0x1800a3f58  jz      loc_1800A4043
0x1800a3f5e  mov     ecx, 10Bh
0x1800a3f63  movzx   eax, word ptr [rax+18h]
0x1800a3f67  sub     ax, cx
0x1800a3f6a  mov     ecx, 0FEFFh
0x1800a3f6f  test    cx, ax
0x1800a3f72  jnz     loc_1800A4043
0x1800a3f78  mov     ebx, [rbx+50h]
0x1800a3f7b  mov     rcx, rdi
0x1800a3f7e  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1800a3f85  nop     dword ptr [rax+rax+00h]
0x1800a3f8a  lea     rcx, [rsp+0D8h+var_68]
0x1800a3f8f  mov     [rsp+0D8h+var_98], rcx; __int64
0x1800a3f94  mov     [rsp+0D8h+var_A0], 0; __int64
0x1800a3f9d  mov     [rsp+0D8h+var_B0], 0; __int64
0x1800a3fa6  lea     rcx, [rsp+0D8h+var_80]
0x1800a3fab  mov     [rsp+0D8h+var_B8], rcx; __int64
0x1800a3fb0  lea     r9, [rsp+0D8h+StringIn]
0x1800a3fb5  xor     r8d, r8d
0x1800a3fb8  mov     edx, ebx; Size
0x1800a3fba  mov     rcx, rax; BaseAddress
0x1800a3fbd  call    SIPolicyGetOriginalFilenameAndVersionFromImageBase
0x1800a3fc2  mov     ebx, eax
0x1800a3fc4  add     eax, 3FFFFF77h
0x1800a3fc9  cmp     eax, 2
0x1800a3fcc  jbe     short loc_1800A3FDE
0x1800a3fce  cmp     ebx, 0C000001Fh
0x1800a3fd4  jz      short loc_1800A3FDE
0x1800a3fd6  cmp     ebx, 0C0000204h
0x1800a3fdc  jnz     short loc_1800A3FE3
0x1800a3fde  mov     ebx, 0C0000225h
0x1800a3fe3  mov     [rsp+0D8h+var_88], ebx
0x1800a3fe7  test    ebx, ebx
0x1800a3fe9  js      short loc_1800A404C
0x1800a3feb  test    r14, r14
0x1800a3fee  jz      short loc_1800A4018
0x1800a3ff0  cmp     [rsp+0D8h+StringIn.Buffer], 0
0x1800a3ff6  jz      short loc_1800A4018
0x1800a3ff8  mov     r8, r14; StringOut
0x1800a3ffb  lea     rdx, [rsp+0D8h+StringIn]; StringIn
0x1800a4000  xor     ecx, ecx; Flags
0x1800a4002  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a4009  nop     dword ptr [rax+rax+00h]
0x1800a400e  mov     ebx, eax
0x1800a4010  mov     [rsp+0D8h+var_88], eax
0x1800a4014  test    eax, eax
0x1800a4016  js      short loc_1800A404C
0x1800a4018  test    rsi, rsi
0x1800a401b  jz      short loc_1800A404C
0x1800a401d  cmp     [rsp+0D8h+var_68.Buffer], 0
0x1800a4023  jz      short loc_1800A404C
0x1800a4025  mov     r8, rsi; StringOut
0x1800a4028  lea     rdx, [rsp+0D8h+var_68]; StringIn
0x1800a402d  xor     ecx, ecx; Flags
0x1800a402f  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a4036  nop     dword ptr [rax+rax+00h]
0x1800a403b  mov     ebx, eax
0x1800a403d  mov     [rsp+0D8h+var_88], eax
0x1800a4041  jmp     short loc_1800A404C
0x1800a4043  mov     ebx, 0C000007Bh
0x1800a4048  mov     [rsp+0D8h+var_88], ebx
0x1800a404c  jmp     short loc_1800A4054
0x1800a404e  mov     ebx, eax
0x1800a4050  mov     [rsp+0D8h+var_88], eax
0x1800a4054  lea     rcx, [rsp+0D8h+ApcState]; ApcState
0x1800a405c  call    cs:__imp_KeUnstackDetachProcess
0x1800a4063  nop     dword ptr [rax+rax+00h]
0x1800a4068  mov     eax, ebx
0x1800a406a  mov     rcx, [rsp+0D8h+var_28]
0x1800a4072  xor     rcx, rsp; StackCookie
0x1800a4075  call    __security_check_cookie
0x1800a407a  mov     rbx, [rsp+0D8h+arg_10]
0x1800a4082  add     rsp, 0C0h
0x1800a4089  pop     r14
0x1800a408b  pop     rdi
0x1800a408c  pop     rsi
0x1800a408d  retn
```

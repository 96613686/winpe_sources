# CipTryGetProcessAppID

- ea: `0x1800a4350`
- end: `0x1800a452f`
- name: `CipTryGetProcessAppID`
- size: `479`
- prototype: `__int64 __fastcall(PRKPROCESS PROCESS, PUNICODE_STRING StringOut)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800647dc`
- `0x18009e8d4`
- `0x1800a42b0`
- `0x1800b4f38`

## callees

- `0x18002c0d0`
- `0x1800a4350`
- `0x1800a46e0`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1800a43c7`
- `ntoskrnl!KeStackAttachProcess` at `0x1800a43c7`
- `ntoskrnl!RtlImageNtHeader` at `0x1800a43e6`
- `ntoskrnl!RtlImageNtHeader` at `0x1800a43e6`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a43a4`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a43d7`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a441e`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a43a4`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a43d7`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a441e`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a44a2`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a44cf`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a44a2`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a44cf`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800a44fc`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800a44fc`

## pseudocode

```c
__int64 __fastcall CipTryGetProcessAppID(
        PRKPROCESS PROCESS,
        PUNICODE_STRING StringOut,
        __int64 a3,
        struct _UNICODE_STRING *a4)
{
  NTSTATUS OriginalFilenameAndVersionFromImageBase; // ebx
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
                                                  (__int64)&v14,
                                                  0,
                                                  v13,
                                                  0,
                                                  (__int64)&v16);
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
0x1800a4350  mov     r11, rsp
0x1800a4353  mov     [r11+18h], rbx
0x1800a4357  push    rsi
0x1800a4358  push    rdi
0x1800a4359  push    r14
0x1800a435b  sub     rsp, 0C0h
0x1800a4362  mov     rax, cs:__security_cookie
0x1800a4369  xor     rax, rsp
0x1800a436c  mov     [rsp+0D8h+var_28], rax
0x1800a4374  mov     rsi, r9
0x1800a4377  mov     r14, rdx
0x1800a437a  mov     rdi, rcx
0x1800a437d  xorps   xmm0, xmm0
0x1800a4380  movups  xmmword ptr [r11-58h], xmm0
0x1800a4385  movups  xmmword ptr [r11-48h], xmm0
0x1800a438a  movups  xmmword ptr [r11-38h], xmm0
0x1800a438f  movups  xmmword ptr [rsp+0D8h+StringIn.Length], xmm0
0x1800a4394  xorps   xmm1, xmm1
0x1800a4397  movups  xmmword ptr [rsp+0D8h+var_68.Length], xmm1
0x1800a439c  mov     qword ptr [r11-80h], 0
0x1800a43a4  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1800a43ab  nop     dword ptr [rax+rax+00h]
0x1800a43b0  test    rax, rax
0x1800a43b3  jnz     short loc_1800A43BC
0x1800a43b5  xor     ebx, ebx
0x1800a43b7  jmp     loc_1800A4508
0x1800a43bc  lea     rdx, [rsp+0D8h+ApcState]; ApcState
0x1800a43c4  mov     rcx, rdi; PROCESS
0x1800a43c7  call    cs:__imp_KeStackAttachProcess
0x1800a43ce  nop     dword ptr [rax+rax+00h]
0x1800a43d3  nop
0x1800a43d4  mov     rcx, rdi
0x1800a43d7  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1800a43de  nop     dword ptr [rax+rax+00h]
0x1800a43e3  mov     rcx, rax; BaseAddress
0x1800a43e6  call    cs:__imp_RtlImageNtHeader
0x1800a43ed  nop     dword ptr [rax+rax+00h]
0x1800a43f2  mov     rbx, rax
0x1800a43f5  test    rax, rax
0x1800a43f8  jz      loc_1800A44E3
0x1800a43fe  mov     ecx, 10Bh
0x1800a4403  movzx   eax, word ptr [rax+18h]
0x1800a4407  sub     ax, cx
0x1800a440a  mov     ecx, 0FEFFh
0x1800a440f  test    cx, ax
0x1800a4412  jnz     loc_1800A44E3
0x1800a4418  mov     ebx, [rbx+50h]
0x1800a441b  mov     rcx, rdi
0x1800a441e  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1800a4425  nop     dword ptr [rax+rax+00h]
0x1800a442a  lea     rcx, [rsp+0D8h+var_68]
0x1800a442f  mov     [rsp+0D8h+var_98], rcx; __int64
0x1800a4434  mov     [rsp+0D8h+var_A0], 0; __int64
0x1800a443d  mov     [rsp+0D8h+var_B0], 0; __int64
0x1800a4446  lea     rcx, [rsp+0D8h+var_80]
0x1800a444b  mov     [rsp+0D8h+var_B8], rcx; __int64
0x1800a4450  lea     r9, [rsp+0D8h+StringIn]
0x1800a4455  xor     r8d, r8d
0x1800a4458  mov     edx, ebx; Size
0x1800a445a  mov     rcx, rax; BaseAddress
0x1800a445d  call    SIPolicyGetOriginalFilenameAndVersionFromImageBase
0x1800a4462  mov     ebx, eax
0x1800a4464  add     eax, 3FFFFF77h
0x1800a4469  cmp     eax, 2
0x1800a446c  jbe     short loc_1800A447E
0x1800a446e  cmp     ebx, 0C000001Fh
0x1800a4474  jz      short loc_1800A447E
0x1800a4476  cmp     ebx, 0C0000204h
0x1800a447c  jnz     short loc_1800A4483
0x1800a447e  mov     ebx, 0C0000225h
0x1800a4483  mov     [rsp+0D8h+var_88], ebx
0x1800a4487  test    ebx, ebx
0x1800a4489  js      short loc_1800A44EC
0x1800a448b  test    r14, r14
0x1800a448e  jz      short loc_1800A44B8
0x1800a4490  cmp     [rsp+0D8h+StringIn.Buffer], 0
0x1800a4496  jz      short loc_1800A44B8
0x1800a4498  mov     r8, r14; StringOut
0x1800a449b  lea     rdx, [rsp+0D8h+StringIn]; StringIn
0x1800a44a0  xor     ecx, ecx; Flags
0x1800a44a2  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a44a9  nop     dword ptr [rax+rax+00h]
0x1800a44ae  mov     ebx, eax
0x1800a44b0  mov     [rsp+0D8h+var_88], eax
0x1800a44b4  test    eax, eax
0x1800a44b6  js      short loc_1800A44EC
0x1800a44b8  test    rsi, rsi
0x1800a44bb  jz      short loc_1800A44EC
0x1800a44bd  cmp     [rsp+0D8h+var_68.Buffer], 0
0x1800a44c3  jz      short loc_1800A44EC
0x1800a44c5  mov     r8, rsi; StringOut
0x1800a44c8  lea     rdx, [rsp+0D8h+var_68]; StringIn
0x1800a44cd  xor     ecx, ecx; Flags
0x1800a44cf  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a44d6  nop     dword ptr [rax+rax+00h]
0x1800a44db  mov     ebx, eax
0x1800a44dd  mov     [rsp+0D8h+var_88], eax
0x1800a44e1  jmp     short loc_1800A44EC
0x1800a44e3  mov     ebx, 0C000007Bh
0x1800a44e8  mov     [rsp+0D8h+var_88], ebx
0x1800a44ec  jmp     short loc_1800A44F4
0x1800a44ee  mov     ebx, eax
0x1800a44f0  mov     [rsp+0D8h+var_88], eax
0x1800a44f4  lea     rcx, [rsp+0D8h+ApcState]; ApcState
0x1800a44fc  call    cs:__imp_KeUnstackDetachProcess
0x1800a4503  nop     dword ptr [rax+rax+00h]
0x1800a4508  mov     eax, ebx
0x1800a450a  mov     rcx, [rsp+0D8h+var_28]
0x1800a4512  xor     rcx, rsp; StackCookie
0x1800a4515  call    __security_check_cookie
0x1800a451a  mov     rbx, [rsp+0D8h+arg_10]
0x1800a4522  add     rsp, 0C0h
0x1800a4529  pop     r14
0x1800a452b  pop     rdi
0x1800a452c  pop     rsi
0x1800a452d  retn
```

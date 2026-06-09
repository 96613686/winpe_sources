# CipTryGetProcessAppID

- ea: `0x1800a2880`
- end: `0x1800a2a5f`
- name: `CipTryGetProcessAppID`
- size: `479`
- prototype: `__int64 __fastcall(PRKPROCESS PROCESS, PUNICODE_STRING StringOut)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180063d3c`
- `0x1800989d8`
- `0x1800a27e0`
- `0x1800b3c18`

## callees

- `0x18002bef0`
- `0x1800a2880`
- `0x1800a2c10`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1800a28f7`
- `ntoskrnl!KeStackAttachProcess` at `0x1800a28f7`
- `ntoskrnl!RtlImageNtHeader` at `0x1800a2916`
- `ntoskrnl!RtlImageNtHeader` at `0x1800a2916`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a28d4`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a2907`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a294e`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a28d4`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a2907`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1800a294e`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a29d2`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a29ff`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a29d2`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a29ff`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800a2a2c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800a2a2c`

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
0x1800a2880  mov     r11, rsp
0x1800a2883  mov     [r11+18h], rbx
0x1800a2887  push    rsi
0x1800a2888  push    rdi
0x1800a2889  push    r14
0x1800a288b  sub     rsp, 0C0h
0x1800a2892  mov     rax, cs:__security_cookie
0x1800a2899  xor     rax, rsp
0x1800a289c  mov     [rsp+0D8h+var_28], rax
0x1800a28a4  mov     rsi, r9
0x1800a28a7  mov     r14, rdx
0x1800a28aa  mov     rdi, rcx
0x1800a28ad  xorps   xmm0, xmm0
0x1800a28b0  movups  xmmword ptr [r11-58h], xmm0
0x1800a28b5  movups  xmmword ptr [r11-48h], xmm0
0x1800a28ba  movups  xmmword ptr [r11-38h], xmm0
0x1800a28bf  movups  xmmword ptr [rsp+0D8h+StringIn.Length], xmm0
0x1800a28c4  xorps   xmm1, xmm1
0x1800a28c7  movups  xmmword ptr [rsp+0D8h+var_68.Length], xmm1
0x1800a28cc  mov     qword ptr [r11-80h], 0
0x1800a28d4  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1800a28db  nop     dword ptr [rax+rax+00h]
0x1800a28e0  test    rax, rax
0x1800a28e3  jnz     short loc_1800A28EC
0x1800a28e5  xor     ebx, ebx
0x1800a28e7  jmp     loc_1800A2A38
0x1800a28ec  lea     rdx, [rsp+0D8h+ApcState]; ApcState
0x1800a28f4  mov     rcx, rdi; PROCESS
0x1800a28f7  call    cs:__imp_KeStackAttachProcess
0x1800a28fe  nop     dword ptr [rax+rax+00h]
0x1800a2903  nop
0x1800a2904  mov     rcx, rdi
0x1800a2907  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1800a290e  nop     dword ptr [rax+rax+00h]
0x1800a2913  mov     rcx, rax; BaseAddress
0x1800a2916  call    cs:__imp_RtlImageNtHeader
0x1800a291d  nop     dword ptr [rax+rax+00h]
0x1800a2922  mov     rbx, rax
0x1800a2925  test    rax, rax
0x1800a2928  jz      loc_1800A2A13
0x1800a292e  mov     ecx, 10Bh
0x1800a2933  movzx   eax, word ptr [rax+18h]
0x1800a2937  sub     ax, cx
0x1800a293a  mov     ecx, 0FEFFh
0x1800a293f  test    cx, ax
0x1800a2942  jnz     loc_1800A2A13
0x1800a2948  mov     ebx, [rbx+50h]
0x1800a294b  mov     rcx, rdi
0x1800a294e  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1800a2955  nop     dword ptr [rax+rax+00h]
0x1800a295a  lea     rcx, [rsp+0D8h+var_68]
0x1800a295f  mov     [rsp+0D8h+var_98], rcx; __int64
0x1800a2964  mov     [rsp+0D8h+var_A0], 0; __int64
0x1800a296d  mov     [rsp+0D8h+var_B0], 0; __int64
0x1800a2976  lea     rcx, [rsp+0D8h+var_80]
0x1800a297b  mov     [rsp+0D8h+var_B8], rcx; __int64
0x1800a2980  lea     r9, [rsp+0D8h+StringIn]
0x1800a2985  xor     r8d, r8d
0x1800a2988  mov     edx, ebx; Size
0x1800a298a  mov     rcx, rax; BaseAddress
0x1800a298d  call    SIPolicyGetOriginalFilenameAndVersionFromImageBase
0x1800a2992  mov     ebx, eax
0x1800a2994  add     eax, 3FFFFF77h
0x1800a2999  cmp     eax, 2
0x1800a299c  jbe     short loc_1800A29AE
0x1800a299e  cmp     ebx, 0C000001Fh
0x1800a29a4  jz      short loc_1800A29AE
0x1800a29a6  cmp     ebx, 0C0000204h
0x1800a29ac  jnz     short loc_1800A29B3
0x1800a29ae  mov     ebx, 0C0000225h
0x1800a29b3  mov     [rsp+0D8h+var_88], ebx
0x1800a29b7  test    ebx, ebx
0x1800a29b9  js      short loc_1800A2A1C
0x1800a29bb  test    r14, r14
0x1800a29be  jz      short loc_1800A29E8
0x1800a29c0  cmp     [rsp+0D8h+StringIn.Buffer], 0
0x1800a29c6  jz      short loc_1800A29E8
0x1800a29c8  mov     r8, r14; StringOut
0x1800a29cb  lea     rdx, [rsp+0D8h+StringIn]; StringIn
0x1800a29d0  xor     ecx, ecx; Flags
0x1800a29d2  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a29d9  nop     dword ptr [rax+rax+00h]
0x1800a29de  mov     ebx, eax
0x1800a29e0  mov     [rsp+0D8h+var_88], eax
0x1800a29e4  test    eax, eax
0x1800a29e6  js      short loc_1800A2A1C
0x1800a29e8  test    rsi, rsi
0x1800a29eb  jz      short loc_1800A2A1C
0x1800a29ed  cmp     [rsp+0D8h+var_68.Buffer], 0
0x1800a29f3  jz      short loc_1800A2A1C
0x1800a29f5  mov     r8, rsi; StringOut
0x1800a29f8  lea     rdx, [rsp+0D8h+var_68]; StringIn
0x1800a29fd  xor     ecx, ecx; Flags
0x1800a29ff  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a2a06  nop     dword ptr [rax+rax+00h]
0x1800a2a0b  mov     ebx, eax
0x1800a2a0d  mov     [rsp+0D8h+var_88], eax
0x1800a2a11  jmp     short loc_1800A2A1C
0x1800a2a13  mov     ebx, 0C000007Bh
0x1800a2a18  mov     [rsp+0D8h+var_88], ebx
0x1800a2a1c  jmp     short loc_1800A2A24
0x1800a2a1e  mov     ebx, eax
0x1800a2a20  mov     [rsp+0D8h+var_88], eax
0x1800a2a24  lea     rcx, [rsp+0D8h+ApcState]; ApcState
0x1800a2a2c  call    cs:__imp_KeUnstackDetachProcess
0x1800a2a33  nop     dword ptr [rax+rax+00h]
0x1800a2a38  mov     eax, ebx
0x1800a2a3a  mov     rcx, [rsp+0D8h+var_28]
0x1800a2a42  xor     rcx, rsp; StackCookie
0x1800a2a45  call    __security_check_cookie
0x1800a2a4a  mov     rbx, [rsp+0D8h+arg_10]
0x1800a2a52  add     rsp, 0C0h
0x1800a2a59  pop     r14
0x1800a2a5b  pop     rdi
0x1800a2a5c  pop     rsi
0x1800a2a5d  retn
```

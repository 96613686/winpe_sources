# LdrpLoadShimEngine

- ea: `0x1800c19c0`
- end: `0x1800c1c45`
- name: `LdrpLoadShimEngine`
- size: `645`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callers

- `0x1800bfe70`
- `0x1800c18c0`

## callees

- `0x18001eb80`
- `0x180023e10`
- `0x18002b9f0`
- `0x18002c35c`
- `0x18004eb70`
- `0x18006ffa0`
- `0x180070490`
- `0x1800709e0`
- `0x1800c0e80`
- `0x1800c19c0`
- `0x1800c4700`
- `0x1800e6424`
- `0x18010dfc8`
- `0x18011a8b8`
- `0x18015f060`
- `0x180162810`
- `0x18016f020`
- `0x18016f030`

## string_xrefs

- `0x1800c1a97`: `Loading the shim DLL "%wZ" failed with status 0x%08lx\n`
- `0x1800c1b24`: `Initializing the shim DLL "%wZ" failed with status 0x%08lx\n`

## pseudocode

```c
char __fastcall LdrpLoadShimEngine(PCWSTR SourceString)
{
  char v2; // r14
  void (__fastcall *v3)(_QWORD); // r15
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // esi
  __int64 v8; // rdi
  __int64 i; // rax
  __int64 *v10; // rbx
  __int64 v12; // [rsp+40h] [rbp-99h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-91h] BYREF
  __int64 v14[16]; // [rsp+60h] [rbp-79h] BYREF

  memset_thunk_772440563353939046(v14, 0, 0x80u);
  v12 = 0;
  DestinationString = 0;
  v2 = 1;
  LdrpInitializeDllPath(0, 16385, v14);
  g_ShimsLoading = 1;
  v3 = (void (__fastcall *)(_QWORD))(__ROR8__(g_pfnSE_ShimDllLoaded, 64 - (MEMORY[0x7FFE0330] & 0x3Fu))
                                   ^ MEMORY[0x7FFE0330]);
  while ( *SourceString )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    if ( (int)LdrpLoadDll(&DestinationString.Length, (__int64)v14, 1u, (__int64)&v12) >= 0 )
    {
      v4 = v12;
      v5 = v12;
      *(_DWORD *)(v12 + 104) |= 0x100u;
      LdrpPinModule(v5);
      v6 = *(_QWORD *)(v4 + 152);
      if ( *(_DWORD *)(v6 + 56) == 7 )
      {
        v7 = LdrpInitializeNode(v6);
        if ( v7 < 0 )
        {
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrinit.c",
            3411,
            (int)"LdrpLoadShimEngine",
            0,
            "Initializing the shim DLL \"%wZ\" failed with status 0x%08lx\n",
            (char)&DestinationString);
          v2 = 0;
          LdrpInitializationFailure((unsigned int)v7);
          ZwTerminateProcess(-1, (unsigned int)v7);
          break;
        }
      }
      v3(*(_QWORD *)(v4 + 48));
      LdrpDereferenceModule(v4);
    }
    else
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        3385,
        (int)"LdrpLoadShimEngine",
        0,
        "Loading the shim DLL \"%wZ\" failed with status 0x%08lx\n",
        (char)&DestinationString);
      v2 = 0;
    }
    SourceString += (unsigned __int64)DestinationString.MaximumLength >> 1;
  }
  LdrpReleaseDllPath(v14);
  ((void (*)(void))(MEMORY[0x7FFE0330] ^ __ROR8__(g_pfnSE_InstallBeforeInit, 64 - (MEMORY[0x7FFE0330] & 0x3Fu))))();
  v8 = __ROR8__(g_pfnSE_DllLoaded, 64 - (MEMORY[0x7FFE0330] & 0x3Fu)) ^ MEMORY[0x7FFE0330];
  RtlEnterCriticalSection(&LdrpDllNotificationLock);
  if ( g_ShimsEnabled )
  {
    for ( i = qword_1801CA8D0; (__int64 *)i != &qword_1801CA8D0; i = *(_QWORD *)i )
      _InterlockedAnd((volatile signed __int32 *)(i + 104), 0xFFFFF7FF);
  }
  v10 = (__int64 *)qword_1801CA8D0;
  if ( LdrInitState >= 2 )
    goto LABEL_19;
  while ( 1 )
  {
    v10 = (__int64 *)*v10;
LABEL_19:
    if ( v10 == &qword_1801CA8D0 )
      break;
    LdrpSendShimEngineInitialNotifications(v10[19], v8);
  }
  g_ShimsLoading = 0;
  g_ShimsEnabled = 1;
  RtlLeaveCriticalSection(&LdrpDllNotificationLock);
  LdrpInitializeShimDllDependencies();
  return v2;
}

```

## disassembly

```asm
0x1800c19c0  push    rbp
0x1800c19c2  push    rbx
0x1800c19c3  push    rsi
0x1800c19c4  push    rdi
0x1800c19c5  push    r12
0x1800c19c7  push    r13
0x1800c19c9  push    r14
0x1800c19cb  push    r15
0x1800c19cd  lea     rbp, [rsp-1Fh]
0x1800c19d2  sub     rsp, 0F8h
0x1800c19d9  mov     rax, cs:__security_cookie
0x1800c19e0  xor     rax, rsp
0x1800c19e3  mov     [rbp+57h+var_50], rax
0x1800c19e7  mov     rdi, rcx
0x1800c19ea  xor     edx, edx; Val
0x1800c19ec  lea     rcx, [rbp+57h+var_D0]; void *
0x1800c19f0  mov     r8d, 80h; Size
0x1800c19f6  call    memset$thunk$772440563353939046
0x1800c19fb  xorps   xmm0, xmm0
0x1800c19fe  lea     r8, [rbp+57h+var_D0]
0x1800c1a02  xor     r13d, r13d
0x1800c1a05  mov     edx, 4001h
0x1800c1a0a  xor     ecx, ecx
0x1800c1a0c  mov     [rsp+130h+var_F0], r13
0x1800c1a11  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x1800c1a16  mov     r14b, 1
0x1800c1a19  call    LdrpInitializeDllPath
0x1800c1a1e  mov     cs:g_ShimsLoading, r14b
0x1800c1a25  lea     r12d, [r13+40h]
0x1800c1a29  mov     r15d, ds:7FFE0330h
0x1800c1a31  mov     ecx, r12d
0x1800c1a34  mov     eax, r15d
0x1800c1a37  and     eax, 3Fh
0x1800c1a3a  sub     ecx, eax
0x1800c1a3c  mov     rax, cs:g_pfnSE_ShimDllLoaded
0x1800c1a43  ror     rax, cl
0x1800c1a46  xor     r15, rax
0x1800c1a49  jmp     loc_1800C1B03
0x1800c1a4e  mov     rdx, rdi; SourceString
0x1800c1a51  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x1800c1a56  call    RtlInitUnicodeString
0x1800c1a5b  lea     r9, [rsp+130h+var_F0]
0x1800c1a60  mov     r8d, 1
0x1800c1a66  lea     rdx, [rbp+57h+var_D0]
0x1800c1a6a  lea     rcx, [rsp+130h+DestinationString]; ArgList
0x1800c1a6f  call    LdrpLoadDll
0x1800c1a74  test    eax, eax
0x1800c1a76  jns     short loc_1800C1AB2
0x1800c1a78  mov     [rsp+130h+var_100], eax
0x1800c1a7c  lea     r8, aLdrploadshimen; "LdrpLoadShimEngine"
0x1800c1a83  lea     rax, [rsp+130h+DestinationString]
0x1800c1a88  xor     r9d, r9d; int
0x1800c1a8b  mov     qword ptr [rsp+130h+ArgList], rax; ArgList
0x1800c1a90  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800c1a97  lea     rax, aLoadingTheShim_0; "Loading the shim DLL \"%wZ\" failed wit"...
0x1800c1a9e  mov     edx, 0D39h; int
0x1800c1aa3  mov     [rsp+130h+Format], rax; Format
0x1800c1aa8  call    LdrpLogInternal
0x1800c1aad  mov     r14b, r13b
0x1800c1ab0  jmp     short loc_1800C1AF7
0x1800c1ab2  mov     rbx, [rsp+130h+var_F0]
0x1800c1ab7  mov     rcx, rbx
0x1800c1aba  mov     eax, [rbx+68h]
0x1800c1abd  bts     eax, 8
0x1800c1ac1  mov     [rbx+68h], eax
0x1800c1ac4  call    LdrpPinModule
0x1800c1ac9  mov     rcx, [rbx+98h]
0x1800c1ad0  mov     eax, [rcx+38h]
0x1800c1ad3  cmp     eax, 7
0x1800c1ad6  jnz     short loc_1800C1AE3
0x1800c1ad8  call    LdrpInitializeNode
0x1800c1add  mov     esi, eax
0x1800c1adf  test    eax, eax
0x1800c1ae1  js      short loc_1800C1B0F
0x1800c1ae3  mov     rcx, [rbx+30h]
0x1800c1ae7  mov     rax, r15
0x1800c1aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1aef  mov     rcx, rbx
0x1800c1af2  call    LdrpDereferenceModule
0x1800c1af7  movzx   eax, [rsp+130h+DestinationString.MaximumLength]
0x1800c1afc  shr     rax, 1
0x1800c1aff  lea     rdi, [rdi+rax*2]
0x1800c1b03  cmp     [rdi], r13w
0x1800c1b07  jnz     loc_1800C1A4E
0x1800c1b0d  jmp     short loc_1800C1B59
0x1800c1b0f  lea     rax, [rsp+130h+DestinationString]
0x1800c1b14  mov     [rsp+130h+var_100], esi
0x1800c1b18  mov     qword ptr [rsp+130h+ArgList], rax; ArgList
0x1800c1b1d  lea     r8, aLdrploadshimen; "LdrpLoadShimEngine"
0x1800c1b24  lea     rax, aInitializingTh_2; "Initializing the shim DLL \"%wZ\" faile"...
0x1800c1b2b  xor     r9d, r9d; int
0x1800c1b2e  mov     edx, 0D53h; int
0x1800c1b33  mov     [rsp+130h+Format], rax; Format
0x1800c1b38  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800c1b3f  call    LdrpLogInternal
0x1800c1b44  mov     ecx, esi
0x1800c1b46  mov     r14b, r13b
0x1800c1b49  call    LdrpInitializationFailure
0x1800c1b4e  mov     edx, esi
0x1800c1b50  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800c1b54  call    ZwTerminateProcess
0x1800c1b59  lea     rcx, [rbp+57h+var_D0]
0x1800c1b5d  call    LdrpReleaseDllPath
0x1800c1b62  mov     edx, ds:7FFE0330h
0x1800c1b69  mov     ecx, r12d
0x1800c1b6c  mov     eax, edx
0x1800c1b6e  and     eax, 3Fh
0x1800c1b71  sub     ecx, eax
0x1800c1b73  mov     rax, cs:g_pfnSE_InstallBeforeInit
0x1800c1b7a  ror     rax, cl
0x1800c1b7d  xor     rax, rdx
0x1800c1b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1b85  mov     edi, ds:7FFE0330h
0x1800c1b8c  mov     eax, edi
0x1800c1b8e  and     eax, 3Fh
0x1800c1b91  sub     r12d, eax
0x1800c1b94  mov     rax, cs:g_pfnSE_DllLoaded
0x1800c1b9b  mov     cl, r12b
0x1800c1b9e  ror     rax, cl
0x1800c1ba1  lea     rcx, LdrpDllNotificationLock
0x1800c1ba8  xor     rdi, rax
0x1800c1bab  call    RtlEnterCriticalSection
0x1800c1bb0  cmp     cs:g_ShimsEnabled, r13b
0x1800c1bb7  lea     rsi, qword_1801CA8D0
0x1800c1bbe  jz      short loc_1800C1BD9
0x1800c1bc0  mov     rax, cs:qword_1801CA8D0
0x1800c1bc7  jmp     short loc_1800C1BD4
0x1800c1bc9  lock and dword ptr [rax+68h], 0FFFFF7FFh
0x1800c1bd1  mov     rax, [rax]
0x1800c1bd4  cmp     rax, rsi
0x1800c1bd7  jnz     short loc_1800C1BC9
0x1800c1bd9  cmp     cs:LdrInitState, 2
0x1800c1be0  mov     rbx, cs:qword_1801CA8D0
0x1800c1be7  jge     short loc_1800C1BFD
0x1800c1be9  jmp     short loc_1800C1BFA
0x1800c1beb  mov     rcx, [rbx+98h]
0x1800c1bf2  mov     rdx, rdi
0x1800c1bf5  call    LdrpSendShimEngineInitialNotifications
0x1800c1bfa  mov     rbx, [rbx]
0x1800c1bfd  cmp     rbx, rsi
0x1800c1c00  jnz     short loc_1800C1BEB
0x1800c1c02  lea     rcx, LdrpDllNotificationLock
0x1800c1c09  mov     cs:g_ShimsLoading, r13b
0x1800c1c10  mov     cs:g_ShimsEnabled, 1
0x1800c1c17  call    RtlLeaveCriticalSection
0x1800c1c1c  call    LdrpInitializeShimDllDependencies
0x1800c1c21  mov     al, r14b
0x1800c1c24  mov     rcx, [rbp+57h+var_50]
0x1800c1c28  xor     rcx, rsp; StackCookie
0x1800c1c2b  call    __security_check_cookie
0x1800c1c30  add     rsp, 0F8h
0x1800c1c37  pop     r15
0x1800c1c39  pop     r14
0x1800c1c3b  pop     r13
0x1800c1c3d  pop     r12
0x1800c1c3f  pop     rdi
0x1800c1c40  pop     rsi
0x1800c1c41  pop     rbx
0x1800c1c42  pop     rbp
0x1800c1c43  retn
```

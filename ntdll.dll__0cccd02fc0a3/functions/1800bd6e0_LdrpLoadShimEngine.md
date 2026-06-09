# LdrpLoadShimEngine

- ea: `0x1800bd6e0`
- end: `0x1800bd965`
- name: `LdrpLoadShimEngine`
- size: `645`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callers

- `0x1800bbb90`
- `0x1800bd5e0`

## callees

- `0x18001eb80`
- `0x180023e20`
- `0x18002c6f0`
- `0x18002d05c`
- `0x1800414e0`
- `0x1800535c0`
- `0x180053ab0`
- `0x180054000`
- `0x1800bcba0`
- `0x1800bd6e0`
- `0x1800c0420`
- `0x1800e60a4`
- `0x18010cc78`
- `0x180119dc8`
- `0x18015e850`
- `0x180162000`
- `0x18016f020`
- `0x18016f030`

## string_xrefs

- `0x1800bd844`: `Initializing the shim DLL "%wZ" failed with status 0x%08lx\n`
- `0x1800bd7b7`: `Loading the shim DLL "%wZ" failed with status 0x%08lx\n`

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
0x1800bd6e0  push    rbp
0x1800bd6e2  push    rbx
0x1800bd6e3  push    rsi
0x1800bd6e4  push    rdi
0x1800bd6e5  push    r12
0x1800bd6e7  push    r13
0x1800bd6e9  push    r14
0x1800bd6eb  push    r15
0x1800bd6ed  lea     rbp, [rsp-1Fh]
0x1800bd6f2  sub     rsp, 0F8h
0x1800bd6f9  mov     rax, cs:__security_cookie
0x1800bd700  xor     rax, rsp
0x1800bd703  mov     [rbp+57h+var_50], rax
0x1800bd707  mov     rdi, rcx
0x1800bd70a  xor     edx, edx; Val
0x1800bd70c  lea     rcx, [rbp+57h+var_D0]; void *
0x1800bd710  mov     r8d, 80h; Size
0x1800bd716  call    memset$thunk$772440563353939046
0x1800bd71b  xorps   xmm0, xmm0
0x1800bd71e  lea     r8, [rbp+57h+var_D0]
0x1800bd722  xor     r13d, r13d
0x1800bd725  mov     edx, 4001h
0x1800bd72a  xor     ecx, ecx
0x1800bd72c  mov     [rsp+130h+var_F0], r13
0x1800bd731  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x1800bd736  mov     r14b, 1
0x1800bd739  call    LdrpInitializeDllPath
0x1800bd73e  mov     cs:g_ShimsLoading, r14b
0x1800bd745  lea     r12d, [r13+40h]
0x1800bd749  mov     r15d, ds:7FFE0330h
0x1800bd751  mov     ecx, r12d
0x1800bd754  mov     eax, r15d
0x1800bd757  and     eax, 3Fh
0x1800bd75a  sub     ecx, eax
0x1800bd75c  mov     rax, cs:g_pfnSE_ShimDllLoaded
0x1800bd763  ror     rax, cl
0x1800bd766  xor     r15, rax
0x1800bd769  jmp     loc_1800BD823
0x1800bd76e  mov     rdx, rdi; SourceString
0x1800bd771  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x1800bd776  call    RtlInitUnicodeString
0x1800bd77b  lea     r9, [rsp+130h+var_F0]
0x1800bd780  mov     r8d, 1
0x1800bd786  lea     rdx, [rbp+57h+var_D0]
0x1800bd78a  lea     rcx, [rsp+130h+DestinationString]; ArgList
0x1800bd78f  call    LdrpLoadDll
0x1800bd794  test    eax, eax
0x1800bd796  jns     short loc_1800BD7D2
0x1800bd798  mov     [rsp+130h+var_100], eax
0x1800bd79c  lea     r8, aLdrploadshimen; "LdrpLoadShimEngine"
0x1800bd7a3  lea     rax, [rsp+130h+DestinationString]
0x1800bd7a8  xor     r9d, r9d; int
0x1800bd7ab  mov     qword ptr [rsp+130h+ArgList], rax; ArgList
0x1800bd7b0  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800bd7b7  lea     rax, aLoadingTheShim_0; "Loading the shim DLL \"%wZ\" failed wit"...
0x1800bd7be  mov     edx, 0D39h; int
0x1800bd7c3  mov     [rsp+130h+Format], rax; Format
0x1800bd7c8  call    LdrpLogInternal
0x1800bd7cd  mov     r14b, r13b
0x1800bd7d0  jmp     short loc_1800BD817
0x1800bd7d2  mov     rbx, [rsp+130h+var_F0]
0x1800bd7d7  mov     rcx, rbx
0x1800bd7da  mov     eax, [rbx+68h]
0x1800bd7dd  bts     eax, 8
0x1800bd7e1  mov     [rbx+68h], eax
0x1800bd7e4  call    LdrpPinModule
0x1800bd7e9  mov     rcx, [rbx+98h]
0x1800bd7f0  mov     eax, [rcx+38h]
0x1800bd7f3  cmp     eax, 7
0x1800bd7f6  jnz     short loc_1800BD803
0x1800bd7f8  call    LdrpInitializeNode
0x1800bd7fd  mov     esi, eax
0x1800bd7ff  test    eax, eax
0x1800bd801  js      short loc_1800BD82F
0x1800bd803  mov     rcx, [rbx+30h]
0x1800bd807  mov     rax, r15
0x1800bd80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd80f  mov     rcx, rbx
0x1800bd812  call    LdrpDereferenceModule
0x1800bd817  movzx   eax, [rsp+130h+DestinationString.MaximumLength]
0x1800bd81c  shr     rax, 1
0x1800bd81f  lea     rdi, [rdi+rax*2]
0x1800bd823  cmp     [rdi], r13w
0x1800bd827  jnz     loc_1800BD76E
0x1800bd82d  jmp     short loc_1800BD879
0x1800bd82f  lea     rax, [rsp+130h+DestinationString]
0x1800bd834  mov     [rsp+130h+var_100], esi
0x1800bd838  mov     qword ptr [rsp+130h+ArgList], rax; ArgList
0x1800bd83d  lea     r8, aLdrploadshimen; "LdrpLoadShimEngine"
0x1800bd844  lea     rax, aInitializingTh_2; "Initializing the shim DLL \"%wZ\" faile"...
0x1800bd84b  xor     r9d, r9d; int
0x1800bd84e  mov     edx, 0D53h; int
0x1800bd853  mov     [rsp+130h+Format], rax; Format
0x1800bd858  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800bd85f  call    LdrpLogInternal
0x1800bd864  mov     ecx, esi
0x1800bd866  mov     r14b, r13b
0x1800bd869  call    LdrpInitializationFailure
0x1800bd86e  mov     edx, esi
0x1800bd870  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800bd874  call    ZwTerminateProcess
0x1800bd879  lea     rcx, [rbp+57h+var_D0]
0x1800bd87d  call    LdrpReleaseDllPath
0x1800bd882  mov     edx, ds:7FFE0330h
0x1800bd889  mov     ecx, r12d
0x1800bd88c  mov     eax, edx
0x1800bd88e  and     eax, 3Fh
0x1800bd891  sub     ecx, eax
0x1800bd893  mov     rax, cs:g_pfnSE_InstallBeforeInit
0x1800bd89a  ror     rax, cl
0x1800bd89d  xor     rax, rdx
0x1800bd8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd8a5  mov     edi, ds:7FFE0330h
0x1800bd8ac  mov     eax, edi
0x1800bd8ae  and     eax, 3Fh
0x1800bd8b1  sub     r12d, eax
0x1800bd8b4  mov     rax, cs:g_pfnSE_DllLoaded
0x1800bd8bb  mov     cl, r12b
0x1800bd8be  ror     rax, cl
0x1800bd8c1  lea     rcx, LdrpDllNotificationLock
0x1800bd8c8  xor     rdi, rax
0x1800bd8cb  call    RtlEnterCriticalSection
0x1800bd8d0  cmp     cs:g_ShimsEnabled, r13b
0x1800bd8d7  lea     rsi, qword_1801CA8D0
0x1800bd8de  jz      short loc_1800BD8F9
0x1800bd8e0  mov     rax, cs:qword_1801CA8D0
0x1800bd8e7  jmp     short loc_1800BD8F4
0x1800bd8e9  lock and dword ptr [rax+68h], 0FFFFF7FFh
0x1800bd8f1  mov     rax, [rax]
0x1800bd8f4  cmp     rax, rsi
0x1800bd8f7  jnz     short loc_1800BD8E9
0x1800bd8f9  cmp     cs:LdrInitState, 2
0x1800bd900  mov     rbx, cs:qword_1801CA8D0
0x1800bd907  jge     short loc_1800BD91D
0x1800bd909  jmp     short loc_1800BD91A
0x1800bd90b  mov     rcx, [rbx+98h]
0x1800bd912  mov     rdx, rdi
0x1800bd915  call    LdrpSendShimEngineInitialNotifications
0x1800bd91a  mov     rbx, [rbx]
0x1800bd91d  cmp     rbx, rsi
0x1800bd920  jnz     short loc_1800BD90B
0x1800bd922  lea     rcx, LdrpDllNotificationLock
0x1800bd929  mov     cs:g_ShimsLoading, r13b
0x1800bd930  mov     cs:g_ShimsEnabled, 1
0x1800bd937  call    RtlLeaveCriticalSection
0x1800bd93c  call    LdrpInitializeShimDllDependencies
0x1800bd941  mov     al, r14b
0x1800bd944  mov     rcx, [rbp+57h+var_50]
0x1800bd948  xor     rcx, rsp; StackCookie
0x1800bd94b  call    __security_check_cookie
0x1800bd950  add     rsp, 0F8h
0x1800bd957  pop     r15
0x1800bd959  pop     r14
0x1800bd95b  pop     r13
0x1800bd95d  pop     r12
0x1800bd95f  pop     rdi
0x1800bd960  pop     rsi
0x1800bd961  pop     rbx
0x1800bd962  pop     rbp
0x1800bd963  retn
```

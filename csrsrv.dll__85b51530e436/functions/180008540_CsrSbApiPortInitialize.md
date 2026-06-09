# CsrSbApiPortInitialize

- ea: `0x180008540`
- end: `0x180008775`
- name: `CsrSbApiPortInitialize`
- size: `565`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004a20`

## callees

- `0x180001bb0`
- `0x180007ee0`
- `0x180008540`
- `0x18000ab61`
- `0x18000ab80`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800085b8`
- `ntdll!RtlAllocateHeap` at `0x1800085b8`
- `ntdll!RtlFreeHeap` at `0x1800086c9`
- `ntdll!RtlFreeHeap` at `0x1800086c9`
- `ntdll!NtResumeThread` at `0x180008747`
- `ntdll!NtResumeThread` at `0x180008747`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800085f9`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800085f9`
- `ntdll!RtlAppendUnicodeToString` at `0x18000860f`
- `ntdll!RtlAppendUnicodeToString` at `0x180008625`
- `ntdll!RtlAppendUnicodeToString` at `0x18000860f`
- `ntdll!RtlAppendUnicodeToString` at `0x180008625`
- `ntdll!RtlCreateUserThread` at `0x180008721`
- `ntdll!RtlCreateUserThread` at `0x180008721`
- `ntdll!NtAlpcCreatePort` at `0x1800086aa`
- `ntdll!NtAlpcCreatePort` at `0x1800086aa`

## pseudocode

```c
int CsrSbApiPortInitialize()
{
  USHORT v0; // bx
  int result; // eax
  PVOID v2; // rdi
  int v3; // ebx
  void *v4; // r8
  HANDLE ThreadHandle; // [rsp+50h] [rbp-59h] BYREF
  PVOID BaseAddress; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v7[48]; // [rsp+60h] [rbp-49h] BYREF
  __int128 Reserved8; // [rsp+90h] [rbp-19h] BYREF
  int v9; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v10; // [rsp+A4h] [rbp-5h]
  int v11; // [rsp+ACh] [rbp+3h]
  __int64 v12; // [rsp+B0h] [rbp+7h]
  __int64 v13; // [rsp+B8h] [rbp+Fh]
  __int128 v14; // [rsp+C0h] [rbp+17h]
  __int128 v15; // [rsp+D0h] [rbp+27h]
  __int64 v16; // [rsp+E0h] [rbp+37h]

  memset(v7, 0, 44);
  memset_0(&v9, 0, 0x48u);
  v0 = CsrDirectoryName.Length + 22;
  ThreadHandle = 0;
  Reserved8 = 0;
  BaseAddress = 0;
  CsrSbApiPortName.Buffer = (PWSTR)RtlAllocateHeap(
                                     CsrHeap,
                                     CsrBaseTag + 0x40000,
                                     (unsigned int)CsrDirectoryName.Length + 22);
  if ( !CsrSbApiPortName.Buffer )
    return -1073741801;
  CsrSbApiPortName.MaximumLength = v0;
  CsrSbApiPortName.Length = 0;
  RtlAppendUnicodeStringToString(&CsrSbApiPortName, &CsrDirectoryName);
  RtlAppendUnicodeToString(&CsrSbApiPortName, L"\\");
  RtlAppendUnicodeToString(&CsrSbApiPortName, L"SbApiPort");
  result = CsrCreateLocalSystemSD((struct _ACL **)&BaseAddress, 0x1F0001u);
  if ( result >= 0 )
  {
    v2 = BaseAddress;
    *(_OWORD *)&v7[32] = (unsigned __int64)BaseAddress;
    *(_DWORD *)v7 = 48;
    *(_QWORD *)&v7[8] = 0;
    *(_DWORD *)&v7[24] = 0;
    *(_QWORD *)&v7[16] = &CsrSbApiPortName;
    v10 = 0;
    v11 = 0;
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v9 = 0x20000;
    v12 = 288;
    v3 = NtAlpcCreatePort(&CsrSbApiPort, v7, &v9);
    if ( v2 )
      RtlFreeHeap(CsrHeap, 0, v2);
    if ( v3 >= 0 )
    {
      LOBYTE(v4) = 1;
      result = RtlCreateUserThread(
                 (PVOID)0xFFFFFFFFFFFFFFFFLL,
                 0,
                 v4,
                 0,
                 0,
                 0,
                 CsrSbApiRequestThread,
                 0,
                 &ThreadHandle,
                 &Reserved8);
      if ( result >= 0 )
      {
        CsrAddStaticServerThread((__int64)ThreadHandle, &Reserved8, 0);
        return NtResumeThread(ThreadHandle, 0);
      }
    }
    else
    {
      return v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008540  mov     [rsp-8+arg_8], rbx
0x180008545  mov     [rsp-8+arg_10], rsi
0x18000854a  push    rbp
0x18000854b  lea     rbp, [rsp-57h]
0x180008550  sub     rsp, 100h
0x180008557  mov     rax, cs:__security_cookie
0x18000855e  xor     rax, rsp
0x180008561  mov     [rbp+57h+var_10], rax
0x180008565  xorps   xmm0, xmm0
0x180008568  lea     rcx, [rbp+57h+var_60]; void *
0x18000856c  movups  [rbp+57h+var_90], xmm0
0x180008570  xor     eax, eax
0x180008572  xor     edx, edx; Val
0x180008574  mov     r8d, 48h ; 'H'; Size
0x18000857a  movups  [rbp+57h+var_90+0Ch], xmm0
0x18000857e  movups  [rbp+57h+var_A0], xmm0
0x180008582  call    memset_0
0x180008587  movzx   ebx, cs:CsrDirectoryName.Length
0x18000858e  xor     esi, esi
0x180008590  mov     edx, cs:CsrBaseTag
0x180008596  xorps   xmm0, xmm0
0x180008599  mov     rcx, cs:CsrHeap; HeapHandle
0x1800085a0  add     ebx, 16h
0x1800085a3  mov     r8d, ebx; Size
0x1800085a6  add     edx, 40000h; Flags
0x1800085ac  mov     [rbp+57h+ThreadHandle], rsi
0x1800085b0  movups  [rbp+57h+var_70], xmm0
0x1800085b4  mov     [rbp+57h+BaseAddress], rsi
0x1800085b8  call    cs:__imp_RtlAllocateHeap
0x1800085bf  nop     dword ptr [rax+rax+00h]
0x1800085c4  mov     cs:CsrSbApiPortName.Buffer, rax
0x1800085cb  test    rax, rax
0x1800085ce  jnz     short loc_1800085DA
0x1800085d0  mov     eax, 0C0000017h
0x1800085d5  jmp     loc_180008753
0x1800085da  mov     cs:CsrSbApiPortName.MaximumLength, bx
0x1800085e1  lea     rdx, CsrDirectoryName; Source
0x1800085e8  lea     rbx, CsrSbApiPortName
0x1800085ef  mov     cs:CsrSbApiPortName.Length, si
0x1800085f6  mov     rcx, rbx; Destination
0x1800085f9  call    cs:__imp_RtlAppendUnicodeStringToString
0x180008600  nop     dword ptr [rax+rax+00h]
0x180008605  lea     rdx, Source; "\\"
0x18000860c  mov     rcx, rbx; Destination
0x18000860f  call    cs:__imp_RtlAppendUnicodeToString
0x180008616  nop     dword ptr [rax+rax+00h]
0x18000861b  lea     rdx, aSbapiport; "SbApiPort"
0x180008622  mov     rcx, rbx; Destination
0x180008625  call    cs:__imp_RtlAppendUnicodeToString
0x18000862c  nop     dword ptr [rax+rax+00h]
0x180008631  mov     edx, 1F0001h
0x180008636  lea     rcx, [rbp+57h+BaseAddress]
0x18000863a  call    CsrCreateLocalSystemSD
0x18000863f  test    eax, eax
0x180008641  js      loc_180008753
0x180008647  xorps   xmm0, xmm0
0x18000864a  mov     [rsp+100h+arg_0], rdi
0x180008652  mov     rdi, [rbp+57h+BaseAddress]
0x180008656  lea     r8, [rbp+57h+var_60]
0x18000865a  xorps   xmm1, xmm1
0x18000865d  mov     [rbp+57h+var_80], rdi
0x180008661  lea     rdx, [rbp+57h+var_A0]
0x180008665  mov     dword ptr [rbp+57h+var_A0], 30h ; '0'
0x18000866c  lea     rcx, CsrSbApiPort
0x180008673  mov     qword ptr [rbp+57h+var_A0+8], rsi
0x180008677  mov     dword ptr [rbp+57h+var_90+8], esi
0x18000867a  mov     qword ptr [rbp+57h+var_90], rbx
0x18000867e  mov     [rbp+57h+var_78], rsi
0x180008682  mov     [rbp+57h+var_5C], rsi
0x180008686  mov     [rbp+57h+var_54], esi
0x180008689  mov     [rbp+57h+var_48], rsi
0x18000868d  movdqa  [rbp+57h+var_40], xmm0
0x180008692  movdqa  [rbp+57h+var_30], xmm1
0x180008697  mov     [rbp+57h+var_20], rsi
0x18000869b  mov     [rbp+57h+var_60], 20000h
0x1800086a2  mov     [rbp+57h+var_50], 120h
0x1800086aa  call    cs:__imp_NtAlpcCreatePort
0x1800086b1  nop     dword ptr [rax+rax+00h]
0x1800086b6  mov     ebx, eax
0x1800086b8  test    rdi, rdi
0x1800086bb  jz      short loc_1800086D5
0x1800086bd  mov     rcx, cs:CsrHeap; HeapHandle
0x1800086c4  mov     r8, rdi; BaseAddress
0x1800086c7  xor     edx, edx; Flags
0x1800086c9  call    cs:__imp_RtlFreeHeap
0x1800086d0  nop     dword ptr [rax+rax+00h]
0x1800086d5  mov     rdi, [rsp+100h+arg_0]
0x1800086dd  test    ebx, ebx
0x1800086df  jns     short loc_1800086E5
0x1800086e1  mov     eax, ebx
0x1800086e3  jmp     short loc_180008753
0x1800086e5  lea     rax, [rbp+57h+var_70]
0x1800086e9  xor     r9d, r9d; Reserved2
0x1800086ec  mov     [rsp+100h+Reserved8], rax; Reserved8
0x1800086f1  mov     r8b, 1; Reserved1
0x1800086f4  lea     rax, [rbp+57h+ThreadHandle]
0x1800086f8  xor     edx, edx; OutThreadHandle
0x1800086fa  mov     [rsp+100h+Reserved7], rax; Reserved7
0x1800086ff  mov     rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x180008706  mov     [rsp+100h+Reserved6], rsi; Reserved6
0x18000870b  lea     rax, CsrSbApiRequestThread
0x180008712  mov     [rsp+100h+Reserved5], rax; Reserved5
0x180008717  mov     [rsp+100h+Reserved4], rsi; Reserved4
0x18000871c  mov     [rsp+100h+Reserved3], rsi; Reserved3
0x180008721  call    cs:__imp_RtlCreateUserThread
0x180008728  nop     dword ptr [rax+rax+00h]
0x18000872d  test    eax, eax
0x18000872f  js      short loc_180008753
0x180008731  mov     rcx, [rbp+57h+ThreadHandle]
0x180008735  lea     rdx, [rbp+57h+var_70]
0x180008739  xor     r8d, r8d
0x18000873c  call    CsrAddStaticServerThread
0x180008741  mov     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x180008745  xor     edx, edx; SuspendCount
0x180008747  call    cs:__imp_NtResumeThread
0x18000874e  nop     dword ptr [rax+rax+00h]
0x180008753  mov     rcx, [rbp+57h+var_10]
0x180008757  xor     rcx, rsp; StackCookie
0x18000875a  call    __security_check_cookie
0x18000875f  lea     r11, [rsp+100h+var_s0]
0x180008767  mov     rbx, [r11+18h]
0x18000876b  mov     rsi, [r11+20h]
0x18000876f  mov     rsp, r11
0x180008772  pop     rbp
0x180008773  retn
```

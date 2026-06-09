# DsRolepSetLsaInformationForReplica

- ea: `0x180022898`
- end: `0x180022c2d`
- name: `DsRolepSetLsaInformationForReplica`
- size: `917`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012460`

## callees

- `0x18000e4d0`
- `0x180016374`
- `0x1800203d0`
- `0x180020530`
- `0x1800206a4`
- `0x180020718`
- `0x180020dbc`
- `0x180022898`
- `0x18002c012`

## import_xrefs

- `msvcrt!malloc` at `0x180022968`
- `msvcrt!malloc` at `0x180022ad0`
- `msvcrt!malloc` at `0x180022968`
- `msvcrt!malloc` at `0x180022ad0`
- `msvcrt!free` at `0x1800229af`
- `msvcrt!free` at `0x180022b13`
- `msvcrt!free` at `0x1800229af`
- `msvcrt!free` at `0x180022b13`
- `ntdll!RtlAllocateHeap` at `0x1800229e3`
- `ntdll!RtlAllocateHeap` at `0x1800229e3`
- `ntdll!RtlNtStatusToDosError` at `0x180022bf7`
- `ntdll!RtlNtStatusToDosError` at `0x180022bf7`
- `ntdll!RtlFreeHeap` at `0x180022beb`
- `ntdll!RtlFreeHeap` at `0x180022beb`
- `ntdll!RtlInitUnicodeString` at `0x18002291f`
- `ntdll!RtlInitUnicodeString` at `0x18002291f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180022b92`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180022b92`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180022b5f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180022b5f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180022a9e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180022a9e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x180022b53`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x180022b53`

## string_xrefs

- `0x18002298b`: `LsaOpenPolicy on %ws failed with  0x%lx. Establishing use.\n`
- `0x180022af1`: `LsaOpenPolicy on %ws failed with  0x%lx.\n`
- `0x180022aad`: `Local LsaOpenPoolicy returned 0x%lx\n`

## pseudocode

```c
__int64 __fastcall DsRolepSetLsaInformationForReplica(__int64 a1, const WCHAR *a2, int a3, int a4)
{
  WCHAR *v4; // rdi
  __int64 v8; // r13
  ULONG v10; // esi
  int v11; // ebx
  unsigned int v12; // edi
  _WORD *v13; // rax
  _WORD *v14; // rbx
  __int64 v15; // rax
  size_t v16; // rbx
  wchar_t *Heap; // rax
  ULONG v18; // eax
  NTSTATUS v19; // eax
  unsigned int Length; // r13d
  _WORD *v21; // rax
  _WORD *v22; // r15
  int v23; // r15d
  POLICY_INFORMATION_CLASS v24; // r12d
  char v25; // [rsp+38h] [rbp-59h]
  __int64 v26; // [rsp+40h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-49h] BYREF
  POLICY_INFORMATION_CLASS InformationClass[2]; // [rsp+58h] [rbp-39h]
  PVOID Buffer; // [rsp+60h] [rbp-31h] BYREF
  PVOID PolicyHandle; // [rsp+68h] [rbp-29h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-21h] BYREF

  InformationClass[0] = PolicyDnsDomainInformation;
  v4 = 0;
  PolicyHandle = 0;
  v26 = 0;
  Buffer = 0;
  v8 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a2 )
    return 87;
  v25 = 0;
  v10 = 0;
  DsRolepSetCurrentOperationStatus(28681, a2, 0);
  RtlInitUnicodeString(&DestinationString, a2);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v11 = ImpLsaOpenPolicy(v8, &DestinationString, &ObjectAttributes, 0x2000000, &v26);
  if ( v11 != -1073741790 )
  {
    if ( v11 < 0 )
    {
      Length = DestinationString.Length;
      v21 = malloc(DestinationString.Length + 2LL);
      v22 = v21;
      if ( v21 )
      {
        memcpy_0(v21, DestinationString.Buffer, Length);
        v22[(unsigned __int64)DestinationString.Length >> 1] = 0;
        DsRolepLogPrintRoutine(4, "LsaOpenPolicy on %ws failed with  0x%lx.\n", v22, (unsigned int)v11);
        free(v22);
      }
      v8 = a1;
      goto LABEL_23;
    }
    goto LABEL_17;
  }
  v12 = DestinationString.Length;
  v13 = malloc(DestinationString.Length + 2LL);
  v14 = v13;
  if ( v13 )
  {
    memcpy_0(v13, DestinationString.Buffer, v12);
    v14[(unsigned __int64)DestinationString.Length >> 1] = 0;
    DsRolepLogPrintRoutine(4, "LsaOpenPolicy on %ws failed with  0x%lx. Establishing use.\n", v14, 3221225506LL);
    free(v14);
  }
  if ( *a2 == 92 )
  {
    v4 = (WCHAR *)a2;
  }
  else
  {
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    v16 = v15 + 3;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * (v15 + 3));
    v4 = Heap;
    if ( !Heap )
    {
      v11 = -1073741670;
      goto LABEL_23;
    }
    StringCchPrintfW(Heap, v16, L"\\\\%ws", a2);
  }
  v18 = ImpNetpManageIPCConnect(v8, (_DWORD)v4, a3, a4, 1);
  v10 = v18;
  if ( v18 )
  {
    DsRolepLogPrintRoutine(4, "NetUseAdd to %ws failed with %lu\n", v4, v18);
    v11 = -1073741823;
  }
  else
  {
    v25 = 1;
    v11 = ImpLsaOpenPolicy(v8, &DestinationString, &ObjectAttributes, 0x2000000, &v26);
  }
  if ( v11 >= 0 )
  {
LABEL_17:
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v19 = LsaOpenPolicy(0, &ObjectAttributes, 0x2000000u, &PolicyHandle);
    v11 = v19;
    if ( v19 < 0 )
      DsRolepLogPrintRoutine(4, "Local LsaOpenPoolicy returned 0x%lx\n", v19);
  }
LABEL_23:
  v23 = 0;
  do
  {
    if ( v11 < 0 )
      break;
    v24 = InformationClass[v23];
    v11 = ImpLsaQueryInformationPolicy(v8, v26, (unsigned int)v24, &Buffer);
    if ( v11 >= 0 )
    {
      v11 = LsaSetInformationPolicy(PolicyHandle, v24, Buffer);
      LsaFreeMemory(Buffer);
    }
    DsRolepLogPrintRoutine(4, "Setting Lsa policy %lu returned 0x%lx\n", v24, v11);
    ++v23;
  }
  while ( !v23 );
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v26 )
    ImpLsaClose(v8, v26);
  if ( v25 )
    v10 = ImpNetpManageIPCConnect(v8, (_DWORD)v4, a3, a4, 34);
  if ( v4 && v4 != a2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( v10 || (v10 = RtlNtStatusToDosError(v11)) != 0 )
    DsRolepLogPrintRoutine(4, "DsRolepSetLsaInformationForReplica failed with %lu\n", v10);
  return v10;
}

```

## disassembly

```asm
0x180022898  mov     rax, rsp
0x18002289b  mov     [rax+20h], r9
0x18002289f  mov     [rax+18h], r8
0x1800228a3  mov     [rax+10h], rdx
0x1800228a7  mov     [rax+8], rcx
0x1800228ab  push    rbp
0x1800228ac  push    rbx
0x1800228ad  push    rsi
0x1800228ae  push    rdi
0x1800228af  push    r12
0x1800228b1  push    r13
0x1800228b3  push    r14
0x1800228b5  push    r15
0x1800228b7  lea     rbp, [rax-5Fh]
0x1800228bb  sub     rsp, 0A8h
0x1800228c2  xorps   xmm0, xmm0
0x1800228c5  mov     [rbp+57h+InformationClass], 0Ch
0x1800228cc  xor     edi, edi
0x1800228ce  xor     eax, eax
0x1800228d0  mov     [rbp+57h+PolicyHandle], rdi
0x1800228d4  mov     r12, r9
0x1800228d7  mov     [rbp+57h+var_A8], rdi
0x1800228db  mov     r15, r8
0x1800228de  mov     [rbp+57h+Buffer], rdi
0x1800228e2  mov     r14, rdx
0x1800228e5  mov     r13, rcx
0x1800228e8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800228ec  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800228f0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800228f4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800228f8  test    rdx, rdx
0x1800228fb  jnz     short loc_180022905
0x1800228fd  lea     eax, [rdx+57h]
0x180022900  jmp     loc_180022C19
0x180022905  xor     r8d, r8d
0x180022908  mov     [rbp+57h+var_B0], dil
0x18002290c  mov     ecx, 7009h
0x180022911  mov     esi, edi
0x180022913  call    DsRolepSetCurrentOperationStatus
0x180022918  mov     rdx, r14; SourceString
0x18002291b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002291f  call    cs:__imp_RtlInitUnicodeString
0x180022925  xorps   xmm0, xmm0
0x180022928  lea     rax, [rbp+57h+var_A8]
0x18002292c  mov     r9d, 2000000h
0x180022932  mov     [rsp+20h], rax
0x180022937  lea     r8, [rbp+57h+ObjectAttributes]
0x18002293b  mov     rcx, r13
0x18002293e  lea     rdx, [rbp+57h+DestinationString]
0x180022942  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180022946  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002294a  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002294e  call    ImpLsaOpenPolicy
0x180022953  mov     ebx, eax
0x180022955  cmp     eax, 0C0000022h
0x18002295a  jnz     loc_180022AC0
0x180022960  movzx   edi, [rbp+57h+DestinationString.Length]
0x180022964  lea     rcx, [rdi+2]; Size
0x180022968  call    cs:__imp_malloc
0x18002296e  xor     ecx, ecx
0x180022970  mov     rbx, rax
0x180022973  test    rax, rax
0x180022976  jz      short loc_1800229B7
0x180022978  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x18002297c  mov     r8d, edi; Size
0x18002297f  mov     rcx, rax; void *
0x180022982  call    memcpy_0
0x180022987  movzx   ecx, [rbp+57h+DestinationString.Length]
0x18002298b  lea     rdx, aLsaopenpolicyO; "LsaOpenPolicy on %ws failed with  0x%lx"...
0x180022992  shr     rcx, 1
0x180022995  xor     eax, eax
0x180022997  mov     r9d, 0C0000022h
0x18002299d  mov     r8, rbx
0x1800229a0  mov     [rbx+rcx*2], ax
0x1800229a4  lea     ecx, [rax+4]
0x1800229a7  call    DsRolepLogPrintRoutine
0x1800229ac  mov     rcx, rbx; Block
0x1800229af  call    cs:__imp_free
0x1800229b5  xor     ecx, ecx
0x1800229b7  cmp     word ptr [r14], 5Ch ; '\'
0x1800229bc  jz      short loc_180022A12
0x1800229be  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800229c2  inc     rax
0x1800229c5  cmp     [r14+rax*2], cx
0x1800229ca  jnz     short loc_1800229C2
0x1800229cc  mov     rcx, gs:60h
0x1800229d5  lea     rbx, [rax+3]
0x1800229d9  lea     r8, [rbx+rbx]; Size
0x1800229dd  xor     edx, edx; Flags
0x1800229df  mov     rcx, [rcx+30h]; HeapHandle
0x1800229e3  call    cs:__imp_RtlAllocateHeap
0x1800229e9  mov     rdi, rax
0x1800229ec  test    rax, rax
0x1800229ef  jnz     short loc_1800229FB
0x1800229f1  mov     ebx, 0C000009Ah
0x1800229f6  jmp     loc_180022B1D
0x1800229fb  mov     r9, r14
0x1800229fe  lea     r8, aWs; "\\\\%ws"
0x180022a05  mov     rdx, rbx; cchDest
0x180022a08  mov     rcx, rax; pszDest
0x180022a0b  call    StringCchPrintfW
0x180022a10  jmp     short loc_180022A15
0x180022a12  mov     rdi, r14
0x180022a15  mov     r9, r12
0x180022a18  mov     dword ptr [rsp+20h], 1
0x180022a20  mov     r8, r15
0x180022a23  mov     rdx, rdi
0x180022a26  mov     rcx, r13
0x180022a29  call    ImpNetpManageIPCConnect
0x180022a2e  mov     esi, eax
0x180022a30  test    eax, eax
0x180022a32  jnz     short loc_180022A5B
0x180022a34  lea     rax, [rbp+57h+var_A8]
0x180022a38  mov     [rbp+57h+var_B0], 1
0x180022a3c  mov     r9d, 2000000h
0x180022a42  mov     [rsp+20h], rax
0x180022a47  lea     r8, [rbp+57h+ObjectAttributes]
0x180022a4b  mov     rcx, r13
0x180022a4e  lea     rdx, [rbp+57h+DestinationString]
0x180022a52  call    ImpLsaOpenPolicy
0x180022a57  mov     ebx, eax
0x180022a59  jmp     short loc_180022A77
0x180022a5b  mov     r9d, eax
0x180022a5e  lea     rdx, aNetuseaddToWsF; "NetUseAdd to %ws failed with %lu\n"
0x180022a65  mov     r8, rdi
0x180022a68  mov     ecx, 4
0x180022a6d  call    DsRolepLogPrintRoutine
0x180022a72  mov     ebx, 0C0000001h
0x180022a77  test    ebx, ebx
0x180022a79  js      loc_180022B1D
0x180022a7f  xorps   xmm0, xmm0
0x180022a82  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x180022a86  mov     r8d, 2000000h; DesiredAccess
0x180022a8c  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180022a90  xor     ecx, ecx; SystemName
0x180022a92  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180022a96  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180022a9a  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180022a9e  call    cs:__imp_LsaOpenPolicy
0x180022aa4  mov     ebx, eax
0x180022aa6  test    eax, eax
0x180022aa8  jns     short loc_180022B1D
0x180022aaa  mov     r8d, eax
0x180022aad  lea     rdx, aLocalLsaopenpo; "Local LsaOpenPoolicy returned 0x%lx\n"
0x180022ab4  mov     ecx, 4
0x180022ab9  call    DsRolepLogPrintRoutine
0x180022abe  jmp     short loc_180022B1D
0x180022ac0  xor     r12d, r12d
0x180022ac3  test    ebx, ebx
0x180022ac5  jns     short loc_180022A7F
0x180022ac7  movzx   r13d, [rbp+57h+DestinationString.Length]
0x180022acc  lea     rcx, [r13+2]; Size
0x180022ad0  call    cs:__imp_malloc
0x180022ad6  mov     r15, rax
0x180022ad9  test    rax, rax
0x180022adc  jz      short loc_180022B19
0x180022ade  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x180022ae2  mov     r8d, r13d; Size
0x180022ae5  mov     rcx, rax; void *
0x180022ae8  call    memcpy_0
0x180022aed  movzx   ecx, [rbp+57h+DestinationString.Length]
0x180022af1  lea     rdx, aLsaopenpolicyO_0; "LsaOpenPolicy on %ws failed with  0x%lx"...
0x180022af8  shr     rcx, 1
0x180022afb  mov     r9d, ebx
0x180022afe  mov     r8, r15
0x180022b01  mov     [r15+rcx*2], r12w
0x180022b06  lea     ecx, [r12+4]
0x180022b0b  call    DsRolepLogPrintRoutine
0x180022b10  mov     rcx, r15; Block
0x180022b13  call    cs:__imp_free
0x180022b19  mov     r13, [rbp+57h+arg_0]
0x180022b1d  xor     r14d, r14d
0x180022b20  mov     r15d, r14d
0x180022b23  test    ebx, ebx
0x180022b25  js      short loc_180022B85
0x180022b27  mov     rdx, [rbp+57h+var_A8]
0x180022b2b  lea     r9, [rbp+57h+Buffer]
0x180022b2f  mov     eax, r15d
0x180022b32  mov     rcx, r13
0x180022b35  mov     r12d, [rbp+rax*4+57h+InformationClass]
0x180022b3a  mov     r8d, r12d
0x180022b3d  call    ImpLsaQueryInformationPolicy
0x180022b42  mov     ebx, eax
0x180022b44  test    eax, eax
0x180022b46  js      short loc_180022B65
0x180022b48  mov     r8, [rbp+57h+Buffer]; Buffer
0x180022b4c  mov     edx, r12d; InformationClass
0x180022b4f  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180022b53  call    cs:__imp_LsaSetInformationPolicy
0x180022b59  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180022b5d  mov     ebx, eax
0x180022b5f  call    cs:__imp_LsaFreeMemory
0x180022b65  mov     r9d, ebx
0x180022b68  lea     rdx, aSettingLsaPoli; "Setting Lsa policy %lu returned 0x%lx\n"
0x180022b6f  mov     r8d, r12d
0x180022b72  mov     ecx, 4
0x180022b77  call    DsRolepLogPrintRoutine
0x180022b7c  inc     r15d
0x180022b7f  cmp     r15d, 1
0x180022b83  jb      short loc_180022B23
0x180022b85  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x180022b89  mov     r14, [rbp+57h+arg_8]
0x180022b8d  test    rcx, rcx
0x180022b90  jz      short loc_180022B98
0x180022b92  call    cs:__imp_LsaClose
0x180022b98  mov     rdx, [rbp+57h+var_A8]
0x180022b9c  xor     r15d, r15d
0x180022b9f  test    rdx, rdx
0x180022ba2  jz      short loc_180022BAC
0x180022ba4  mov     rcx, r13
0x180022ba7  call    ImpLsaClose
0x180022bac  cmp     [rbp+57h+var_B0], r15b
0x180022bb0  jz      short loc_180022BCF
0x180022bb2  mov     r9, [rbp+57h+arg_18]
0x180022bb6  mov     rdx, rdi
0x180022bb9  mov     r8, [rbp+57h+arg_10]
0x180022bbd  mov     rcx, r13
0x180022bc0  mov     dword ptr [rsp+20h], 22h ; '"'
0x180022bc8  call    ImpNetpManageIPCConnect
0x180022bcd  mov     esi, eax
0x180022bcf  test    rdi, rdi
0x180022bd2  jz      short loc_180022BF1
0x180022bd4  cmp     rdi, r14
0x180022bd7  jz      short loc_180022BF1
0x180022bd9  mov     rcx, gs:60h
0x180022be2  mov     r8, rdi; P
0x180022be5  xor     edx, edx; Flags
0x180022be7  mov     rcx, [rcx+30h]; HeapHandle
0x180022beb  call    cs:__imp_RtlFreeHeap
0x180022bf1  test    esi, esi
0x180022bf3  jnz     short loc_180022C03
0x180022bf5  mov     ecx, ebx; Status
0x180022bf7  call    cs:__imp_RtlNtStatusToDosError
0x180022bfd  mov     esi, eax
0x180022bff  test    eax, eax
0x180022c01  jz      short loc_180022C17
0x180022c03  mov     r8d, esi
0x180022c06  lea     rdx, aDsrolepsetlsai; "DsRolepSetLsaInformationForReplica fail"...
0x180022c0d  mov     ecx, 4
0x180022c12  call    DsRolepLogPrintRoutine
0x180022c17  mov     eax, esi
0x180022c19  add     rsp, 0A8h
0x180022c20  pop     r15
0x180022c22  pop     r14
0x180022c24  pop     r13
0x180022c26  pop     r12
0x180022c28  pop     rdi
0x180022c29  pop     rsi
0x180022c2a  pop     rbx
0x180022c2b  pop     rbp
0x180022c2c  retn
```

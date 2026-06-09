# CsrLoadServerDll

- ea: `0x180001540`
- end: `0x18000199f`
- name: `CsrLoadServerDll`
- size: `1119`
- prototype: `NTSTATUS __fastcall(PCSZ SourceString, PCSZ, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180005180`

## callees

- `0x180001140`
- `0x180001540`
- `0x1800035c0`
- `0x180008c50`
- `0x180008ca4`
- `0x180008f00`
- `0x18000ab61`
- `0x18000b010`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000161a`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000161a`
- `ntdll!RtlAllocateHeap` at `0x180001740`
- `ntdll!RtlAllocateHeap` at `0x180001740`
- `ntdll!RtlFreeUnicodeString` at `0x1800016e9`
- `ntdll!RtlFreeUnicodeString` at `0x1800016e9`
- `ntdll!RtlInitUnicodeString` at `0x180001685`
- `ntdll!RtlInitUnicodeString` at `0x180001685`
- `ntdll!RtlFreeHeap` at `0x18000197d`
- `ntdll!RtlFreeHeap` at `0x18000197d`
- `ntdll!RtlInitString` at `0x180001837`
- `ntdll!RtlInitString` at `0x180001837`
- `ntdll!LdrGetProcedureAddress` at `0x18000185b`
- `ntdll!LdrGetProcedureAddress` at `0x18000185b`
- `ntdll!strncpy_s` at `0x1800017ec`
- `ntdll!strncpy_s` at `0x1800017ec`
- `ntdll!LdrUnloadDll` at `0x180001769`
- `ntdll!LdrUnloadDll` at `0x18000189d`
- `ntdll!LdrUnloadDll` at `0x18000194a`
- `ntdll!LdrUnloadDll` at `0x180001769`
- `ntdll!LdrUnloadDll` at `0x18000189d`
- `ntdll!LdrUnloadDll` at `0x18000194a`
- `ntdll!RtlSetUnhandledExceptionFilter` at `0x180001707`
- `ntdll!RtlSetUnhandledExceptionFilter` at `0x180001707`
- `ntdll!LdrLoadDll` at `0x18000163f`
- `ntdll!LdrLoadDll` at `0x18000163f`
- `ntdll!NtRaiseHardError` at `0x1800016d8`
- `ntdll!NtRaiseHardError` at `0x1800016d8`
- `ntdll!RtlInitAnsiString` at `0x1800015f9`
- `ntdll!RtlInitAnsiString` at `0x1800015f9`

## string_xrefs

- `0x1800015b5`: `CsrLoadServerDll`
- `0x1800015db`: `CsrLoadServerDll`
- `0x1800016a0`: `CsrLoadServerDll`
- `0x180001788`: `CsrLoadServerDll`
- `0x18000187c`: `CsrLoadServerDll`
- `0x180001965`: `CsrLoadServerDll`
- `0x180001679`: `Default Load Path`
- `0x18000182b`: `ServerDllInitialization`

## pseudocode

```c
NTSTATUS __fastcall CsrLoadServerDll(PCSZ SourceString, PCSZ a2, unsigned int a3)
{
  NTSTATUS result; // eax
  NTSTATUS v7; // esi
  unsigned int v8; // r13d
  char *Heap; // rax
  char *v10; // rsi
  _QWORD *v11; // r13
  unsigned int MaximumLength; // eax
  const char *v13; // rdx
  NTSTATUS v14; // eax
  int v15; // ebx
  int v16; // eax
  __int64 v17; // rcx
  PVOID ProcedureAddress; // [rsp+38h] [rbp-A0h] BYREF
  _STRING DestinationString; // [rsp+40h] [rbp-98h] BYREF
  unsigned __int64 Parameters[2]; // [rsp+50h] [rbp-88h] BYREF
  struct _UNICODE_STRING v21; // [rsp+60h] [rbp-78h] BYREF
  _UNICODE_STRING Name; // [rsp+70h] [rbp-68h] BYREF
  char *v23; // [rsp+80h] [rbp-58h]
  struct _STRING v24; // [rsp+88h] [rbp-50h] BYREF
  ULONG Response; // [rsp+F0h] [rbp+18h] BYREF
  PVOID BaseAddress; // [rsp+F8h] [rbp+20h] BYREF

  DestinationString = 0;
  Name = 0;
  BaseAddress = 0;
  v24 = 0;
  ProcedureAddress = 0;
  if ( a3 >= 6 )
    return -1073741619;
  if ( CsrLoadedServerDll[a3] )
  {
    CsrpLogModuleFailureInt("CsrLoadServerDll", 282, SourceString, a3);
    return -1073741811;
  }
  if ( !SourceString )
  {
    CsrpLogFailure("CsrLoadServerDll");
    return -1073741811;
  }
  RtlInitAnsiString(&DestinationString, SourceString);
  if ( a3 )
  {
    result = RtlAnsiStringToUnicodeString(&Name, &DestinationString, 1u);
    if ( result < 0 )
      return result;
    v7 = LdrLoadDll(0, 0, &Name, &BaseAddress);
    if ( v7 < 0 )
    {
      v21 = 0;
      Response = 0;
      Parameters[0] = (unsigned __int64)&Name;
      Parameters[1] = (unsigned __int64)&v21;
      RtlInitUnicodeString(&v21, L"Default Load Path");
      CsrpLogModuleFailureString("CsrLoadServerDll", v7);
      CsrFlushToBlackBoxRecorder();
      NtRaiseHardError(v7, 2u, 3u, Parameters, 1u, &Response);
    }
    RtlFreeUnicodeString(&Name);
    if ( v7 < 0 )
      return v7;
    RtlSetUnhandledExceptionFilter((PRTLP_UNHANDLED_EXCEPTION_FILTER)CsrUnhandledExceptionFilter);
  }
  else
  {
    BaseAddress = 0;
  }
  v8 = DestinationString.MaximumLength + 120;
  Heap = (char *)RtlAllocateHeap(CsrHeap, CsrBaseTag + 0x40000, v8);
  v10 = Heap;
  v23 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, v8);
    v11 = v10 + 96;
    Parameters[0] = (unsigned __int64)(v10 + 96);
    *((_QWORD *)v10 + 12) = CsrSrvSharedSectionHeap;
    *(_WORD *)v10 = DestinationString.Length;
    MaximumLength = DestinationString.MaximumLength;
    *((_WORD *)v10 + 1) = DestinationString.MaximumLength;
    *((_QWORD *)v10 + 1) = v10 + 120;
    if ( DestinationString.Length )
      strncpy_s(v10 + 120, MaximumLength, DestinationString.Buffer, DestinationString.Length);
    *(_QWORD *)&v21.Length = v10 + 24;
    *((_DWORD *)v10 + 6) = a3;
    *((_QWORD *)v10 + 2) = BaseAddress;
    if ( BaseAddress )
    {
      v13 = "ServerDllInitialization";
      if ( a2 )
        v13 = a2;
      RtlInitString(&v24, v13);
      v14 = LdrGetProcedureAddress(BaseAddress, &v24, 0, &ProcedureAddress);
      v15 = v14;
      if ( v14 < 0 )
        CsrpLogModuleFailureString("CsrLoadServerDll", v14);
      if ( v15 < 0 )
      {
        if ( BaseAddress )
          LdrUnloadDll(BaseAddress);
        goto LABEL_37;
      }
      v16 = ((__int64 (__fastcall *)(char *))ProcedureAddress)(v10);
    }
    else
    {
      ProcedureAddress = CsrServerDllInitialization;
      v16 = ((__int64 (__fastcall *)(char *))CsrServerDllInitialization)(v10);
    }
    v15 = v16;
    if ( v16 >= 0 )
    {
      LODWORD(CsrTotalPerProcessDataLength) = ((*((_DWORD *)v10 + 16) + 7) & 0xFFFFFFF8) + CsrTotalPerProcessDataLength;
      v17 = *((unsigned int *)v10 + 6);
      CsrLoadedServerDll[v17] = (__int64)v10;
      if ( (HANDLE)*v11 != CsrSrvSharedSectionHeap )
        *(_QWORD *)(v17 * 8 + CsrSrvSharedStaticServerData) = *v11;
      return v15;
    }
    if ( BaseAddress )
      LdrUnloadDll(BaseAddress);
    CsrpLogModuleFailureString("CsrLoadServerDll", v15);
LABEL_37:
    RtlFreeHeap(CsrHeap, 0, v10);
    return v15;
  }
  if ( BaseAddress )
    LdrUnloadDll(BaseAddress);
  CsrpLogModuleFailureInt("CsrLoadServerDll", 364, SourceString, v8);
  return -1073741801;
}

```

## disassembly

```asm
0x180001540  mov     rax, rsp
0x180001543  mov     [rax+10h], rdx
0x180001547  mov     [rax+8], rcx
0x18000154b  push    rbx
0x18000154c  push    rsi
0x18000154d  push    rdi
0x18000154e  push    r12
0x180001550  push    r13
0x180001552  push    r14
0x180001554  push    r15
0x180001556  sub     rsp, 0A0h
0x18000155d  mov     ebx, r8d
0x180001560  mov     r15, rdx
0x180001563  mov     rdi, rcx
0x180001566  xorps   xmm0, xmm0
0x180001569  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x18000156e  xorps   xmm1, xmm1
0x180001571  movups  xmmword ptr [rax-68h], xmm1
0x180001575  xor     r12d, r12d
0x180001578  mov     [rax+20h], r12
0x18000157c  movups  xmmword ptr [rax-50h], xmm0
0x180001580  mov     [rsp+0D8h+ProcedureAddress], r12
0x180001585  cmp     r8d, 6
0x180001589  jb      short loc_180001595
0x18000158b  mov     eax, 0C00000CDh
0x180001590  jmp     loc_18000198B
0x180001595  lea     r14, CsrLoadedServerDll
0x18000159c  cmp     [r14+rbx*8], r12
0x1800015a0  jz      short loc_1800015CB
0x1800015a2  mov     [rsp+0D8h+ValidResponseOptions], 0C000000Dh; int
0x1800015aa  mov     r9d, ebx
0x1800015ad  mov     r8, rdi
0x1800015b0  mov     edx, 11Ah
0x1800015b5  lea     rcx, aCsrloadserverd; "CsrLoadServerDll"
0x1800015bc  call    CsrpLogModuleFailureInt
0x1800015c1  mov     eax, 0C000000Dh
0x1800015c6  jmp     loc_18000198B
0x1800015cb  test    rdi, rdi
0x1800015ce  jnz     short loc_1800015F1
0x1800015d0  mov     edx, 122h
0x1800015d5  mov     r8d, 0C000000Dh
0x1800015db  lea     rcx, aCsrloadserverd; "CsrLoadServerDll"
0x1800015e2  call    CsrpLogFailure
0x1800015e7  mov     eax, 0C000000Dh
0x1800015ec  jmp     loc_18000198B
0x1800015f1  mov     rdx, rdi; SourceString
0x1800015f4  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x1800015f9  call    cs:__imp_RtlInitAnsiString
0x180001600  nop     dword ptr [rax+rax+00h]
0x180001605  test    ebx, ebx
0x180001607  jz      loc_180001715
0x18000160d  mov     r8b, 1; AllocateDestinationString
0x180001610  lea     rdx, [rsp+0D8h+DestinationString]; SourceString
0x180001615  lea     rcx, [rsp+0D8h+Name]; DestinationString
0x18000161a  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180001621  nop     dword ptr [rax+rax+00h]
0x180001626  test    eax, eax
0x180001628  js      loc_18000198B
0x18000162e  lea     r9, [rsp+0D8h+BaseAddress]; BaseAddress
0x180001636  lea     r8, [rsp+0D8h+Name]; Name
0x18000163b  xor     edx, edx; LoadFlags
0x18000163d  xor     ecx, ecx; SearchPath
0x18000163f  call    cs:__imp_LdrLoadDll
0x180001646  nop     dword ptr [rax+rax+00h]
0x18000164b  mov     esi, eax
0x18000164d  test    eax, eax
0x18000164f  jns     loc_1800016E4
0x180001655  xorps   xmm0, xmm0
0x180001658  movups  xmmword ptr [rsp+0D8h+var_78.Length], xmm0
0x18000165d  mov     [rsp+0D8h+arg_10], r12d
0x180001665  lea     rax, [rsp+0D8h+Name]
0x18000166a  mov     [rsp+0D8h+Parameters], rax
0x18000166f  lea     rax, [rsp+0D8h+var_78]
0x180001674  mov     [rsp+0D8h+var_80], rax
0x180001679  lea     rdx, SourceString; "Default Load Path"
0x180001680  lea     rcx, [rsp+0D8h+var_78]; DestinationString
0x180001685  call    cs:__imp_RtlInitUnicodeString
0x18000168c  nop     dword ptr [rax+rax+00h]
0x180001691  mov     [rsp+0D8h+ValidResponseOptions], esi; int
0x180001695  mov     r9, r15
0x180001698  mov     r8, rdi
0x18000169b  mov     edx, 141h
0x1800016a0  lea     rcx, aCsrloadserverd; "CsrLoadServerDll"
0x1800016a7  call    CsrpLogModuleFailureString
0x1800016ac  call    CsrFlushToBlackBoxRecorder
0x1800016b1  lea     rax, [rsp+0D8h+arg_10]
0x1800016b9  mov     [rsp+0D8h+Response], rax; Response
0x1800016be  mov     [rsp+0D8h+ValidResponseOptions], 1; ValidResponseOptions
0x1800016c6  lea     r9, [rsp+0D8h+Parameters]; Parameters
0x1800016cb  mov     edx, 2; NumberOfParameters
0x1800016d0  mov     r8d, 3; UnicodeStringParameterMask
0x1800016d6  mov     ecx, esi; ErrorStatus
0x1800016d8  call    cs:__imp_NtRaiseHardError
0x1800016df  nop     dword ptr [rax+rax+00h]
0x1800016e4  lea     rcx, [rsp+0D8h+Name]; UnicodeString
0x1800016e9  call    cs:__imp_RtlFreeUnicodeString
0x1800016f0  nop     dword ptr [rax+rax+00h]
0x1800016f5  test    esi, esi
0x1800016f7  jns     short loc_180001700
0x1800016f9  mov     eax, esi
0x1800016fb  jmp     loc_18000198B
0x180001700  lea     rcx, CsrUnhandledExceptionFilter; TopLevelExceptionFilter
0x180001707  call    cs:__imp_RtlSetUnhandledExceptionFilter
0x18000170e  nop     dword ptr [rax+rax+00h]
0x180001713  jmp     short loc_18000171D
0x180001715  mov     [rsp+0D8h+BaseAddress], r12
0x18000171d  movzx   r13d, [rsp+0D8h+DestinationString.MaximumLength]
0x180001723  add     r13d, 78h ; 'x'
0x180001727  mov     r12d, r13d
0x18000172a  mov     edx, cs:CsrBaseTag
0x180001730  add     edx, 40000h; Flags
0x180001736  mov     r8d, r13d; Size
0x180001739  mov     rcx, cs:CsrHeap; HeapHandle
0x180001740  call    cs:__imp_RtlAllocateHeap
0x180001747  nop     dword ptr [rax+rax+00h]
0x18000174c  mov     rsi, rax
0x18000174f  mov     [rsp+0D8h+var_58], rax
0x180001757  test    rax, rax
0x18000175a  jnz     short loc_18000179E
0x18000175c  mov     rcx, [rsp+0D8h+BaseAddress]; BaseAddress
0x180001764  test    rcx, rcx
0x180001767  jz      short loc_180001775
0x180001769  call    cs:__imp_LdrUnloadDll
0x180001770  nop     dword ptr [rax+rax+00h]
0x180001775  mov     [rsp+0D8h+ValidResponseOptions], 0C0000017h; int
0x18000177d  mov     r9d, r13d
0x180001780  mov     r8, rdi
0x180001783  mov     edx, 16Ch
0x180001788  lea     rcx, aCsrloadserverd; "CsrLoadServerDll"
0x18000178f  call    CsrpLogModuleFailureInt
0x180001794  mov     eax, 0C0000017h
0x180001799  jmp     loc_18000198B
0x18000179e  mov     r8, r12; Size
0x1800017a1  xor     edx, edx; Val
0x1800017a3  mov     rcx, rsi; void *
0x1800017a6  call    memset_0
0x1800017ab  lea     r13, [rsi+60h]
0x1800017af  mov     [rsp+0D8h+Parameters], r13
0x1800017b4  mov     rax, cs:CsrSrvSharedSectionHeap
0x1800017bb  mov     [r13+0], rax
0x1800017bf  movzx   eax, [rsp+0D8h+DestinationString.Length]
0x1800017c4  mov     [rsi], ax
0x1800017c7  movzx   eax, [rsp+0D8h+DestinationString.MaximumLength]
0x1800017cc  mov     [rsi+2], ax
0x1800017d0  lea     rcx, [rsi+78h]; char *
0x1800017d4  mov     [rsi+8], rcx
0x1800017d8  movzx   edx, [rsp+0D8h+DestinationString.Length]
0x1800017dd  test    dx, dx
0x1800017e0  jz      short loc_1800017F8
0x1800017e2  mov     r9d, edx; MaxCount
0x1800017e5  mov     edx, eax; SizeInBytes
0x1800017e7  mov     r8, [rsp+0D8h+DestinationString.Buffer]; Src
0x1800017ec  call    cs:__imp_strncpy_s
0x1800017f3  nop     dword ptr [rax+rax+00h]
0x1800017f8  lea     r12, [rsi+18h]
0x1800017fc  mov     qword ptr [rsp+0D8h+var_78.Length], r12
0x180001801  mov     [r12], ebx
0x180001805  mov     rax, [rsp+0D8h+BaseAddress]
0x18000180d  mov     [rsi+10h], rax
0x180001811  cmp     [rsp+0D8h+BaseAddress], 0
0x18000181a  jz      loc_1800018B5
0x180001820  lea     rcx, [rsp+0D8h+var_50]; DestinationString
0x180001828  test    r15, r15
0x18000182b  lea     rdx, aServerdlliniti; "ServerDllInitialization"
0x180001832  jz      short loc_180001837
0x180001834  mov     rdx, r15; SourceString
0x180001837  call    cs:__imp_RtlInitString
0x18000183e  nop     dword ptr [rax+rax+00h]
0x180001843  lea     r9, [rsp+0D8h+ProcedureAddress]; ProcedureAddress
0x180001848  xor     r8d, r8d; Ordinal
0x18000184b  lea     rdx, [rsp+0D8h+var_50]; Name
0x180001853  mov     rcx, [rsp+0D8h+BaseAddress]; BaseAddress
0x18000185b  call    cs:__imp_LdrGetProcedureAddress
0x180001862  nop     dword ptr [rax+rax+00h]
0x180001867  mov     ebx, eax
0x180001869  test    eax, eax
0x18000186b  jns     short loc_180001888
0x18000186d  mov     [rsp+0D8h+ValidResponseOptions], eax; int
0x180001871  mov     r9, r15
0x180001874  mov     r8, rdi
0x180001877  mov     edx, 198h
0x18000187c  lea     rcx, aCsrloadserverd; "CsrLoadServerDll"
0x180001883  call    CsrpLogModuleFailureString
0x180001888  test    ebx, ebx
0x18000188a  jns     short loc_1800018AE
0x18000188c  mov     rcx, [rsp+0D8h+BaseAddress]; BaseAddress
0x180001894  test    rcx, rcx
0x180001897  jz      loc_180001971
0x18000189d  call    cs:__imp_LdrUnloadDll
0x1800018a4  nop     dword ptr [rax+rax+00h]
0x1800018a9  jmp     loc_180001971
0x1800018ae  mov     rax, [rsp+0D8h+ProcedureAddress]
0x1800018b3  jmp     short loc_1800018C1
0x1800018b5  lea     rax, CsrServerDllInitialization
0x1800018bc  mov     [rsp+0D8h+ProcedureAddress], rax
0x1800018c1  mov     rcx, rsi
0x1800018c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018c9  mov     ebx, eax
0x1800018cb  mov     [rsp+0D8h+var_A8], eax
0x1800018cf  jmp     short loc_180001900
0x1800018d1  mov     ebx, eax
0x1800018d3  mov     [rsp+0D8h+var_A8], eax
0x1800018d7  lea     r14, CsrLoadedServerDll
0x1800018de  mov     r15, [rsp+0D8h+arg_8]
0x1800018e6  mov     rdi, [rsp+0D8h+arg_0]
0x1800018ee  mov     rsi, [rsp+0D8h+var_58]
0x1800018f6  mov     r13, [rsp+0D8h+Parameters]
0x1800018fb  mov     r12, qword ptr [rsp+0D8h+var_78.Length]
0x180001900  test    ebx, ebx
0x180001902  js      short loc_18000193D
0x180001904  mov     eax, [rsi+40h]
0x180001907  add     eax, 7
0x18000190a  and     eax, 0FFFFFFF8h
0x18000190d  add     cs:CsrTotalPerProcessDataLength, eax
0x180001913  mov     eax, [r12]
0x180001917  lea     rcx, ds:0[rax*8]
0x18000191f  mov     [rcx+r14], rsi
0x180001923  mov     rdx, [r13+0]
0x180001927  cmp     rdx, cs:CsrSrvSharedSectionHeap
0x18000192e  jz      short loc_180001989
0x180001930  mov     rax, cs:CsrSrvSharedStaticServerData
0x180001937  mov     [rcx+rax], rdx
0x18000193b  jmp     short loc_180001989
0x18000193d  mov     rcx, [rsp+0D8h+BaseAddress]; BaseAddress
0x180001945  test    rcx, rcx
0x180001948  jz      short loc_180001956
0x18000194a  call    cs:__imp_LdrUnloadDll
0x180001951  nop     dword ptr [rax+rax+00h]
0x180001956  mov     [rsp+0D8h+ValidResponseOptions], ebx; int
0x18000195a  mov     r9, r15
0x18000195d  mov     r8, rdi
0x180001960  mov     edx, 1BDh
0x180001965  lea     rcx, aCsrloadserverd; "CsrLoadServerDll"
0x18000196c  call    CsrpLogModuleFailureString
0x180001971  mov     r8, rsi; BaseAddress
0x180001974  xor     edx, edx; Flags
0x180001976  mov     rcx, cs:CsrHeap; HeapHandle
0x18000197d  call    cs:__imp_RtlFreeHeap
0x180001984  nop     dword ptr [rax+rax+00h]
0x180001989  mov     eax, ebx
0x18000198b  add     rsp, 0A0h
0x180001992  pop     r15
0x180001994  pop     r14
0x180001996  pop     r13
0x180001998  pop     r12
0x18000199a  pop     rdi
0x18000199b  pop     rsi
0x18000199c  pop     rbx
0x18000199d  retn
0x18000ac30  push    rbp
0x18000ac32  sub     rsp, 30h
0x18000ac36  mov     rbp, rdx
0x18000ac39  call    CsrUnhandledExceptionFilter
0x18000ac3e  nop
0x18000ac3f  add     rsp, 30h
0x18000ac43  pop     rbp
0x18000ac44  retn
```

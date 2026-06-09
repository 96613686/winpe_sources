# IkeSaDbSetSecurityInfo

- ea: `0x1800ec7c4`
- end: `0x1800ec997`
- name: `IkeSaDbSetSecurityInfo`
- size: `467`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, RPC_BINDING_HANDLE BindingHandle, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR ModificationDescriptor, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ec9a0`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x180016534`
- `0x18004aa3c`
- `0x180050850`
- `0x1800ec38c`
- `0x1800ec4d8`
- `0x1800ec7c4`
- `0x180117fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec91b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec91b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800ec8a3`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800ec8a3`
- `ntdll!RtlAllocateHeap` at `0x1800ec8be`
- `ntdll!RtlAllocateHeap` at `0x1800ec8be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec948`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800ec958`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800ec958`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x1800ec911`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x1800ec911`

## string_xrefs

- `0x1800ec807`: `IkeSaDbSetSecurityInfo`
- `0x1800ec960`: `IkeSaDbSetSecurityInfo`
- `0x1800ec96c`: `IkeSaDbSetSecurityInfo`
- `0x1800ec927`: `SetPrivateObjectSecurityEx`

## pseudocode

```c
__int64 __fastcall IkeSaDbSetSecurityInfo(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        RPC_BINDING_HANDLE BindingHandle,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR ModificationDescriptor,
        PSECURITY_DESCRIPTOR *a5)
{
  __int64 v9; // rbx
  __int64 AccessTokenFromRpcClientBinding; // rax
  HANDLE Token; // rdi
  SIZE_T v12; // r14
  PVOID Heap; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  DWORD LastError; // eax
  __int64 v17; // rcx
  HANDLE hObject; // [rsp+30h] [rbp-58h] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+38h] [rbp-50h] BYREF

  ObjectsSecurityDescriptor = 0;
  hObject = 0;
  TraceLogHelper("IkeSaDbSetSecurityInfo", 1);
  if ( (SecurityInformation & 3) != 0 && (v9 = IkeAuthzAccessCheck(pSecurityDescriptor)) != 0
    || (SecurityInformation & 4) != 0 && (v9 = IkeAuthzAccessCheck(pSecurityDescriptor)) != 0
    || (SecurityInformation & 8) != 0 && (v9 = IkeAuthzAccessCheck(pSecurityDescriptor)) != 0 )
  {
LABEL_17:
    DestroyPrivateObjectSecurity(&ObjectsSecurityDescriptor);
    goto LABEL_18;
  }
  AccessTokenFromRpcClientBinding = IkeGetAccessTokenFromRpcClientBinding(BindingHandle, &hObject);
  Token = hObject;
  v9 = AccessTokenFromRpcClientBinding;
  if ( !AccessTokenFromRpcClientBinding )
  {
    v12 = RtlLengthSecurityDescriptor(pSecurityDescriptor);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    ObjectsSecurityDescriptor = Heap;
    if ( !Heap )
    {
      v15 = WfpReportSysErrorAsNtStatus(v14, "RtlAllocateHeap", 3221225495LL);
LABEL_10:
      v9 = v15;
      goto LABEL_14;
    }
    memcpy_0(Heap, pSecurityDescriptor, v12);
    if ( !SetPrivateObjectSecurityEx(
            SecurityInformation,
            ModificationDescriptor,
            &ObjectsSecurityDescriptor,
            0,
            (PGENERIC_MAPPING)&IKE_GENERIC_MAPPING,
            Token) )
    {
      LastError = GetLastError();
      v15 = WfpReportSysErrorAsWinError(v17, "SetPrivateObjectSecurityEx", LastError, 1);
      goto LABEL_10;
    }
    *a5 = ObjectsSecurityDescriptor;
  }
LABEL_14:
  if ( Token )
    CloseHandle(Token);
  if ( v9 )
    goto LABEL_17;
LABEL_18:
  TraceLogHelper("IkeSaDbSetSecurityInfo", 0);
  return IkeReturnError(v9, "IkeSaDbSetSecurityInfo");
}

```

## disassembly

```asm
0x1800ec7c4  push    rbx
0x1800ec7c6  push    rbp
0x1800ec7c7  push    rsi
0x1800ec7c8  push    rdi
0x1800ec7c9  push    r12
0x1800ec7cb  push    r14
0x1800ec7cd  push    r15
0x1800ec7cf  sub     rsp, 50h
0x1800ec7d3  mov     rax, cs:__security_cookie
0x1800ec7da  xor     rax, rsp
0x1800ec7dd  mov     [rsp+88h+var_48], rax
0x1800ec7e2  mov     r15, [rsp+88h+arg_20]
0x1800ec7ea  mov     rdi, rdx
0x1800ec7ed  mov     rsi, rcx
0x1800ec7f0  mov     [rsp+88h+ObjectsSecurityDescriptor], 0
0x1800ec7f9  mov     edx, 1
0x1800ec7fe  mov     [rsp+88h+hObject], 0
0x1800ec807  lea     rcx, aIkesadbsetsecu_0; "IkeSaDbSetSecurityInfo"
0x1800ec80e  mov     r12, r9
0x1800ec811  mov     ebp, r8d
0x1800ec814  call    TraceLogHelper
0x1800ec819  test    bpl, 3
0x1800ec81d  jz      short loc_1800EC83C
0x1800ec81f  mov     r8d, 80000h
0x1800ec825  mov     rdx, rdi
0x1800ec828  mov     rcx, rsi; pSecurityDescriptor
0x1800ec82b  call    IkeAuthzAccessCheck
0x1800ec830  mov     rbx, rax
0x1800ec833  test    rax, rax
0x1800ec836  jnz     loc_1800EC953
0x1800ec83c  test    bpl, 4
0x1800ec840  jz      short loc_1800EC85F
0x1800ec842  mov     r8d, 40000h
0x1800ec848  mov     rdx, rdi
0x1800ec84b  mov     rcx, rsi; pSecurityDescriptor
0x1800ec84e  call    IkeAuthzAccessCheck
0x1800ec853  mov     rbx, rax
0x1800ec856  test    rax, rax
0x1800ec859  jnz     loc_1800EC953
0x1800ec85f  test    bpl, 8
0x1800ec863  jz      short loc_1800EC882
0x1800ec865  mov     r8d, 1000000h
0x1800ec86b  mov     rdx, rdi
0x1800ec86e  mov     rcx, rsi; pSecurityDescriptor
0x1800ec871  call    IkeAuthzAccessCheck
0x1800ec876  mov     rbx, rax
0x1800ec879  test    rax, rax
0x1800ec87c  jnz     loc_1800EC953
0x1800ec882  lea     rdx, [rsp+88h+hObject]
0x1800ec887  mov     rcx, rdi; BindingHandle
0x1800ec88a  call    IkeGetAccessTokenFromRpcClientBinding
0x1800ec88f  mov     rdi, [rsp+88h+hObject]
0x1800ec894  mov     rbx, rax
0x1800ec897  test    rax, rax
0x1800ec89a  jnz     loc_1800EC940
0x1800ec8a0  mov     rcx, rsi; SecurityDescriptor
0x1800ec8a3  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800ec8a9  mov     rcx, gs:60h
0x1800ec8b2  xor     edx, edx; Flags
0x1800ec8b4  mov     r8d, eax; Size
0x1800ec8b7  mov     r14d, eax
0x1800ec8ba  mov     rcx, [rcx+30h]; HeapHandle
0x1800ec8be  call    cs:__imp_RtlAllocateHeap
0x1800ec8c4  mov     [rsp+88h+ObjectsSecurityDescriptor], rax
0x1800ec8c9  test    rax, rax
0x1800ec8cc  jnz     short loc_1800EC8E5
0x1800ec8ce  mov     r8d, 0C0000017h
0x1800ec8d4  lea     rdx, aRtlallocatehea; "RtlAllocateHeap"
0x1800ec8db  call    WfpReportSysErrorAsNtStatus
0x1800ec8e0  mov     rbx, rax
0x1800ec8e3  jmp     short loc_1800EC940
0x1800ec8e5  mov     r8, r14; Size
0x1800ec8e8  mov     rdx, rsi; Src
0x1800ec8eb  mov     rcx, rax; void *
0x1800ec8ee  call    memcpy_0
0x1800ec8f3  lea     rax, IKE_GENERIC_MAPPING
0x1800ec8fa  mov     [rsp+88h+Token], rdi; Token
0x1800ec8ff  xor     r9d, r9d; AutoInheritFlags
0x1800ec902  mov     [rsp+88h+GenericMapping], rax; GenericMapping
0x1800ec907  lea     r8, [rsp+88h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x1800ec90c  mov     rdx, r12; ModificationDescriptor
0x1800ec90f  mov     ecx, ebp; SecurityInformation
0x1800ec911  call    cs:__imp_SetPrivateObjectSecurityEx
0x1800ec917  test    eax, eax
0x1800ec919  jnz     short loc_1800EC938
0x1800ec91b  call    cs:__imp_GetLastError
0x1800ec921  mov     r9d, 1
0x1800ec927  lea     rdx, aSetprivateobje; "SetPrivateObjectSecurityEx"
0x1800ec92e  mov     r8d, eax
0x1800ec931  call    WfpReportSysErrorAsWinError
0x1800ec936  jmp     short loc_1800EC8E0
0x1800ec938  mov     rax, [rsp+88h+ObjectsSecurityDescriptor]
0x1800ec93d  mov     [r15], rax
0x1800ec940  test    rdi, rdi
0x1800ec943  jz      short loc_1800EC94E
0x1800ec945  mov     rcx, rdi; hObject
0x1800ec948  call    cs:__imp_CloseHandle
0x1800ec94e  test    rbx, rbx
0x1800ec951  jz      short loc_1800EC95E
0x1800ec953  lea     rcx, [rsp+88h+ObjectsSecurityDescriptor]; ObjectDescriptor
0x1800ec958  call    cs:__imp_DestroyPrivateObjectSecurity
0x1800ec95e  xor     edx, edx
0x1800ec960  lea     rcx, aIkesadbsetsecu_0; "IkeSaDbSetSecurityInfo"
0x1800ec967  call    TraceLogHelper
0x1800ec96c  lea     rdx, aIkesadbsetsecu_0; "IkeSaDbSetSecurityInfo"
0x1800ec973  mov     rcx, rbx
0x1800ec976  call    IkeReturnError
0x1800ec97b  mov     rcx, [rsp+88h+var_48]
0x1800ec980  xor     rcx, rsp; StackCookie
0x1800ec983  call    __security_check_cookie
0x1800ec988  add     rsp, 50h
0x1800ec98c  pop     r15
0x1800ec98e  pop     r14
0x1800ec990  pop     r12
0x1800ec992  pop     rdi
0x1800ec993  pop     rsi
0x1800ec994  pop     rbp
0x1800ec995  pop     rbx
0x1800ec996  retn
```

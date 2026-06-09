# EnsureTracingDirectory(CBsString *)

- ea: `0x180059e64`
- end: `0x180059ff4`
- name: `?EnsureTracingDirectory@@YAJPEAVCBsString@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(LPCWSTR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002a4b0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180011ac4`
- `0x18001a630`
- `0x180059e64`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180059f87`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180059f87`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180059f03`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180059f03`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180059ee0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180059ee0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059f91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059f91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059fc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059fc6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180059f3e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180059f3e`

## string_xrefs

- `0x180059e81`: `EnsureTracingDirectory`

## pseudocode

```c
__int64 __fastcall EnsureTracingDirectory(LPCWSTR *a1)
{
  __int16 v2; // ax
  DWORD FileAttributesW; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  DWORD LastError; // eax
  signed int v13; // ecx
  unsigned int v14; // ebx
  _QWORD v16[2]; // [rsp+20h] [rbp-60h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-50h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-38h] BYREF
  __int16 v19; // [rsp+4Ch] [rbp-34h]
  __int16 v20; // [rsp+4Eh] [rbp-32h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+90h] [rbp+10h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "EnsureTracingDirectory", 0x1Eu, 1u);
  v16[0] = &qword_18006F470;
  v16[1] = 0;
  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a1 )
  {
    LastFailureAsHRESULT = -2147024809;
    v2 = 37;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v19 = 37;
  FileAttributesW = GetFileAttributesW(*a1);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) != 0 )
    {
      LastFailureAsHRESULT = 0;
      v2 = 45;
      goto LABEL_18;
    }
    if ( !DeleteFileW(*a1) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v5, v4, v6, v7, v16[0]);
      v2 = 55;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v19 = 55;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9, v8, v10, v11, v16[0]);
    v2 = 66;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v19 = 66;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  if ( CreateDirectoryW(*a1, &SecurityAttributes) )
    goto LABEL_19;
  LastError = GetLastError();
  v13 = 0;
  if ( LastError != 183 )
    v13 = LastError;
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
  LastFailureAsHRESULT = v13;
  v2 = 79;
  if ( v13 >= 0 )
  {
LABEL_18:
    v19 = v2;
    goto LABEL_19;
  }
LABEL_3:
  v20 = v2;
LABEL_19:
  LocalFree(SecurityDescriptor);
  v14 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)v16);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v14;
}

```

## disassembly

```asm
0x180059e64  mov     [rsp-8+arg_8], rbx
0x180059e69  push    rbp
0x180059e6a  mov     rbp, rsp
0x180059e6d  sub     rsp, 80h
0x180059e74  mov     rbx, rcx
0x180059e77  mov     r9d, 1; unsigned __int16
0x180059e7d  lea     r8d, [r9+1Dh]; unsigned __int16
0x180059e81  lea     rdx, aEnsuretracingd; "EnsureTracingDirectory"
0x180059e88  lea     rcx, [rbp+var_38]; this
0x180059e8c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180059e91  lea     rax, qword_18006F470
0x180059e98  mov     [rbp+var_60], rax
0x180059e9c  mov     [rbp+var_58], 0
0x180059ea4  mov     [rbp+SecurityDescriptor], 0
0x180059eac  xorps   xmm0, xmm0
0x180059eaf  xor     eax, eax
0x180059eb1  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x180059eb5  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x180059eb9  test    rbx, rbx
0x180059ebc  jnz     short loc_180059ED1
0x180059ebe  mov     [rbp+var_38], 80070057h
0x180059ec5  lea     eax, [rbx+25h]
0x180059ec8  mov     [rbp+var_32], ax
0x180059ecc  jmp     loc_180059FC2
0x180059ed1  mov     [rbp+var_38], eax
0x180059ed4  mov     eax, 25h ; '%'
0x180059ed9  mov     [rbp+var_34], ax
0x180059edd  mov     rcx, [rbx]; lpFileName
0x180059ee0  call    cs:__imp_GetFileAttributesW
0x180059ee6  cmp     eax, 0FFFFFFFFh
0x180059ee9  jz      short loc_180059F2C
0x180059eeb  test    al, 10h
0x180059eed  jz      short loc_180059F00
0x180059eef  mov     [rbp+var_38], 0
0x180059ef6  mov     eax, 2Dh ; '-'
0x180059efb  jmp     loc_180059FBE
0x180059f00  mov     rcx, [rbx]; lpFileName
0x180059f03  call    cs:__imp_DeleteFileW
0x180059f09  test    eax, eax
0x180059f0b  jnz     short loc_180059F1C
0x180059f0d  call    GetLastFailureAsHRESULT
0x180059f12  mov     [rbp+var_38], eax
0x180059f15  mov     eax, 37h ; '7'
0x180059f1a  jmp     short loc_180059EC8
0x180059f1c  mov     [rbp+var_38], 0
0x180059f23  mov     eax, 37h ; '7'
0x180059f28  mov     [rbp+var_34], ax
0x180059f2c  xor     r9d, r9d; SecurityDescriptorSize
0x180059f2f  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180059f33  lea     edx, [r9+1]; StringSDRevision
0x180059f37  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;"...
0x180059f3e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180059f44  test    eax, eax
0x180059f46  jnz     short loc_180059F5A
0x180059f48  call    GetLastFailureAsHRESULT
0x180059f4d  mov     [rbp+var_38], eax
0x180059f50  mov     eax, 42h ; 'B'
0x180059f55  jmp     loc_180059EC8
0x180059f5a  mov     [rbp+var_38], 0
0x180059f61  mov     eax, 42h ; 'B'
0x180059f66  mov     [rbp+var_34], ax
0x180059f6a  mov     [rbp+SecurityAttributes.nLength], 18h
0x180059f71  mov     [rbp+SecurityAttributes.bInheritHandle], 0
0x180059f78  mov     rax, [rbp+SecurityDescriptor]
0x180059f7c  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x180059f80  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x180059f84  mov     rcx, [rbx]; lpPathName
0x180059f87  call    cs:__imp_CreateDirectoryW
0x180059f8d  test    eax, eax
0x180059f8f  jnz     short loc_180059FC2
0x180059f91  call    cs:__imp_GetLastError
0x180059f97  xor     ecx, ecx
0x180059f99  cmp     eax, 0B7h
0x180059f9e  cmovnz  ecx, eax
0x180059fa1  test    ecx, ecx
0x180059fa3  jle     short loc_180059FAE
0x180059fa5  movzx   ecx, cx
0x180059fa8  or      ecx, 80070000h
0x180059fae  mov     [rbp+var_38], ecx
0x180059fb1  mov     eax, 4Fh ; 'O'
0x180059fb6  test    ecx, ecx
0x180059fb8  js      loc_180059EC8
0x180059fbe  mov     [rbp+var_34], ax
0x180059fc2  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180059fc6  call    cs:__imp_LocalFree
0x180059fcc  mov     ebx, [rbp+var_38]
0x180059fcf  lea     rcx, [rbp+var_60]; this
0x180059fd3  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180059fd8  lea     rcx, [rbp+var_38]; this
0x180059fdc  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180059fe1  mov     eax, ebx
0x180059fe3  mov     rbx, [rsp+80h+arg_8]
0x180059feb  add     rsp, 80h
0x180059ff2  pop     rbp
0x180059ff3  retn
```

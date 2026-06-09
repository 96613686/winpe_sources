# SspLogNTLMServerBlockedHigher

- ea: `0x180051d50`
- end: `0x1800520bf`
- name: `SspLogNTLMServerBlockedHigher`
- size: `879`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a470`

## callees

- `0x18000cba0`
- `0x18002e3e8`
- `0x18002fb50`
- `0x180051104`
- `0x180051d50`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005207d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005207d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180051f54`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180051f54`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180051f70`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180051f70`
- `ntdll!EtwEventEnabled` at `0x180051df1`
- `ntdll!EtwEventEnabled` at `0x180051df1`
- `ntdll!EtwEventWrite` at `0x18005200d`
- `ntdll!EtwEventWrite` at `0x18005200d`

## pseudocode

```c
int __fastcall SspLogNTLMServerBlockedHigher(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5, int a6)
{
  void *v6; // r15
  unsigned __int16 *v7; // r14
  int result; // eax
  __int64 *v12; // rdx
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rax
  HANDLE v18; // rax
  __int64 *v19; // rdx
  DWORD dwSize; // [rsp+20h] [rbp-E0h] BYREF
  BOOL v21; // [rsp+24h] [rbp-DCh] BYREF
  unsigned __int16 *v22; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwProcessId[4]; // [rsp+60h] [rbp-A0h] BYREF
  struct ASN1objectidentifier_s *v27; // [rsp+70h] [rbp-90h]
  const wchar_t *v28; // [rsp+80h] [rbp-80h]
  __int64 v29; // [rsp+88h] [rbp-78h]
  const wchar_t *v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  const wchar_t *v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  DWORD *v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  WCHAR *v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  int *v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  BOOL *v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  WCHAR ExeName[264]; // [rsp+100h] [rbp+0h] BYREF
  int v45; // [rsp+378h] [rbp+278h] BYREF

  v45 = a4;
  dwSize = 261;
  v22 = 0;
  v21 = 0;
  v27 = 0;
  v6 = 0;
  v7 = 0;
  *(_OWORD *)dwProcessId = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  result = SspInitEtwLogHandle();
  if ( result < 0 )
    goto LABEL_34;
  v12 = (__int64 *)&NTLMClientBlocked;
  if ( !a6 )
    v12 = NTLMClientBlockedAudit;
  result = EtwEventEnabled(MsvEtwLogHandle, v12);
  if ( (_BYTE)result )
  {
    result = NtLmDuplicateUnicodeString(&v23, a1);
    if ( result >= 0 )
    {
      result = NtLmDuplicateUnicodeString(&v24, a2);
      if ( result >= 0 )
      {
        result = NtLmDuplicateUnicodeString(&v25, a3);
        if ( result >= 0 )
        {
          v13 = *((_QWORD *)&v23 + 1);
          if ( *((_QWORD *)&v23 + 1) && (_WORD)v23 )
          {
            v28 = (const wchar_t *)*((_QWORD *)&v23 + 1);
            v29 = (unsigned int)(unsigned __int16)v23 + 2;
          }
          else
          {
            v28 = L"(NULL)";
            v29 = 14;
          }
          v14 = *((_QWORD *)&v24 + 1);
          if ( *((_QWORD *)&v24 + 1) && (_WORD)v24 )
          {
            v30 = (const wchar_t *)*((_QWORD *)&v24 + 1);
            v31 = (unsigned int)(unsigned __int16)v24 + 2;
          }
          else
          {
            v30 = L"(NULL)";
            v31 = 14;
          }
          v15 = *((_QWORD *)&v25 + 1);
          if ( *((_QWORD *)&v25 + 1) && (_WORD)v25 )
          {
            v32 = (const wchar_t *)*((_QWORD *)&v25 + 1);
            v33 = (unsigned int)(unsigned __int16)v25 + 2;
          }
          else
          {
            v32 = L"(NULL)";
            v33 = 14;
          }
          if ( ((unsigned __int8 (__fastcall *)(DWORD *))LsaFunctions->GetCallInfo)(dwProcessId)
            && (v16 = SspOIDToString(v27, &v22), v7 = v22, v16) )
          {
            v17 = -1;
            do
              ++v17;
            while ( v22[v17] );
            v42 = v22;
            v43 = (unsigned int)(2 * v17 + 2);
          }
          else
          {
            v42 = L"(NULL)";
            v43 = 14;
          }
          v34 = dwProcessId;
          v35 = 4;
          v18 = OpenProcess(0x1000u, 0, dwProcessId[0]);
          v6 = v18;
          if ( v18 && QueryFullProcessImageNameW(v18, 0, ExeName, &dwSize) && dwSize )
          {
            v36 = ExeName;
            v37 = 2 * dwSize + 2;
          }
          else
          {
            v37 = 4;
            v36 = L"-";
          }
          v19 = NTLMServerBlockedHigher;
          v38 = &v45;
          v39 = 4;
          v41 = 4;
          v21 = a5 == -1;
          v40 = &v21;
          if ( !a6 )
            v19 = NTLMServerBlockedHigherAudit;
          result = EtwEventWrite(MsvEtwLogHandle, v19, 8);
          goto LABEL_35;
        }
      }
    }
LABEL_34:
    v13 = *((_QWORD *)&v23 + 1);
    v14 = *((_QWORD *)&v24 + 1);
    v15 = *((_QWORD *)&v25 + 1);
LABEL_35:
    if ( v13 )
      result = ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v13);
    if ( v14 )
      result = ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v14);
    if ( v15 )
      result = ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v15);
    if ( v6 )
      result = CloseHandle(v6);
    if ( v7 )
      return ((__int64 (__fastcall *)(unsigned __int16 *))LsaFunctions->FreePrivateHeap)(v7);
  }
  return result;
}

```

## disassembly

```asm
0x180051d50  mov     [rsp-8+arg_18], r9d
0x180051d55  push    rbp
0x180051d56  push    rbx
0x180051d57  push    rsi
0x180051d58  push    rdi
0x180051d59  push    r13
0x180051d5b  push    r14
0x180051d5d  push    r15
0x180051d5f  lea     rbp, [rsp-220h]
0x180051d67  sub     rsp, 320h
0x180051d6e  mov     rax, cs:__security_cookie
0x180051d75  xor     rax, rsp
0x180051d78  mov     [rbp+250h+var_40], rax
0x180051d7f  xor     r13d, r13d
0x180051d82  mov     [rsp+350h+dwSize], 105h
0x180051d8a  xorps   xmm0, xmm0
0x180051d8d  mov     [rsp+350h+var_328], r13
0x180051d92  xor     eax, eax
0x180051d94  mov     [rsp+350h+var_32C], r13d
0x180051d99  xorps   xmm1, xmm1
0x180051d9c  mov     [rsp+350h+var_2E0], rax
0x180051da1  mov     r15d, r13d
0x180051da4  mov     r14d, r13d
0x180051da7  movups  xmmword ptr [rsp+350h+dwProcessId], xmm0
0x180051dac  mov     rsi, r8
0x180051daf  mov     rdi, rdx
0x180051db2  movups  [rsp+350h+var_320], xmm0
0x180051db7  mov     rbx, rcx
0x180051dba  movups  [rsp+350h+var_310], xmm1
0x180051dbf  movups  [rsp+350h+var_300], xmm0
0x180051dc4  call    SspInitEtwLogHandle
0x180051dc9  test    eax, eax
0x180051dcb  js      loc_180052015
0x180051dd1  cmp     [rbp+250h+arg_28], r13d
0x180051dd8  lea     rax, NTLMClientBlockedAudit
0x180051ddf  mov     rcx, cs:MsvEtwLogHandle
0x180051de6  lea     rdx, NTLMClientBlocked
0x180051ded  cmovz   rdx, rax
0x180051df1  call    cs:__imp_EtwEventEnabled
0x180051df7  test    al, al
0x180051df9  jz      loc_18005209E
0x180051dff  mov     rdx, rbx
0x180051e02  lea     rcx, [rsp+350h+var_320]
0x180051e07  call    NtLmDuplicateUnicodeString
0x180051e0c  test    eax, eax
0x180051e0e  js      loc_180052015
0x180051e14  mov     rdx, rdi
0x180051e17  lea     rcx, [rsp+350h+var_310]
0x180051e1c  call    NtLmDuplicateUnicodeString
0x180051e21  test    eax, eax
0x180051e23  js      loc_180052015
0x180051e29  mov     rdx, rsi
0x180051e2c  lea     rcx, [rsp+350h+var_300]
0x180051e31  call    NtLmDuplicateUnicodeString
0x180051e36  test    eax, eax
0x180051e38  js      loc_180052015
0x180051e3e  mov     rsi, qword ptr [rsp+350h+var_320+8]
0x180051e43  lea     r15, aNull; "(NULL)"
0x180051e4a  test    rsi, rsi
0x180051e4d  jz      short loc_180051E69
0x180051e4f  movzx   eax, word ptr [rsp+350h+var_320]
0x180051e54  test    ax, ax
0x180051e57  jz      short loc_180051E69
0x180051e59  add     eax, 2
0x180051e5c  mov     [rbp+250h+var_2D0], rsi
0x180051e60  mov     dword ptr [rbp+250h+var_2C8], eax
0x180051e63  mov     dword ptr [rbp+250h+var_2C8+4], r13d
0x180051e67  jmp     short loc_180051E75
0x180051e69  mov     [rbp+250h+var_2D0], r15
0x180051e6d  mov     [rbp+250h+var_2C8], 0Eh
0x180051e75  mov     rdi, qword ptr [rsp+350h+var_310+8]
0x180051e7a  test    rdi, rdi
0x180051e7d  jz      short loc_180051E99
0x180051e7f  movzx   eax, word ptr [rsp+350h+var_310]
0x180051e84  test    ax, ax
0x180051e87  jz      short loc_180051E99
0x180051e89  add     eax, 2
0x180051e8c  mov     [rbp+250h+var_2C0], rdi
0x180051e90  mov     dword ptr [rbp+250h+var_2B8], eax
0x180051e93  mov     dword ptr [rbp+250h+var_2B8+4], r13d
0x180051e97  jmp     short loc_180051EA5
0x180051e99  mov     [rbp+250h+var_2C0], r15
0x180051e9d  mov     [rbp+250h+var_2B8], 0Eh
0x180051ea5  mov     rbx, qword ptr [rsp+350h+var_300+8]
0x180051eaa  test    rbx, rbx
0x180051ead  jz      short loc_180051EC9
0x180051eaf  movzx   eax, word ptr [rsp+350h+var_300]
0x180051eb4  test    ax, ax
0x180051eb7  jz      short loc_180051EC9
0x180051eb9  add     eax, 2
0x180051ebc  mov     [rbp+250h+var_2B0], rbx
0x180051ec0  mov     dword ptr [rbp+250h+var_2A8], eax
0x180051ec3  mov     dword ptr [rbp+250h+var_2A8+4], r13d
0x180051ec7  jmp     short loc_180051ED5
0x180051ec9  mov     [rbp+250h+var_2B0], r15
0x180051ecd  mov     [rbp+250h+var_2A8], 0Eh
0x180051ed5  mov     rax, cs:LsaFunctions
0x180051edc  lea     rcx, [rsp+350h+dwProcessId]
0x180051ee1  mov     rax, [rax+0C0h]
0x180051ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051eed  test    al, al
0x180051eef  jz      short loc_180051F2B
0x180051ef1  mov     rcx, [rsp+350h+var_2E0]; struct ASN1objectidentifier_s *
0x180051ef6  lea     rdx, [rsp+350h+var_328]; unsigned __int16 **
0x180051efb  call    ?SspOIDToString@@YAHPEAUASN1objectidentifier_s@@PEAPEAG@Z; SspOIDToString(ASN1objectidentifier_s *,ushort * *)
0x180051f00  mov     r14, [rsp+350h+var_328]
0x180051f05  test    eax, eax
0x180051f07  jz      short loc_180051F2B
0x180051f09  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051f0d  inc     rax
0x180051f10  cmp     [r14+rax*2], r13w
0x180051f15  jnz     short loc_180051F0D
0x180051f17  lea     eax, ds:2[rax*2]
0x180051f1e  mov     [rbp+250h+var_260], r14
0x180051f22  mov     dword ptr [rbp+250h+var_258], eax
0x180051f25  mov     dword ptr [rbp+250h+var_258+4], r13d
0x180051f29  jmp     short loc_180051F37
0x180051f2b  mov     [rbp+250h+var_260], r15
0x180051f2f  mov     [rbp+250h+var_258], 0Eh
0x180051f37  mov     r8d, [rsp+350h+dwProcessId]; dwProcessId
0x180051f3c  lea     rax, [rsp+350h+dwProcessId]
0x180051f41  xor     edx, edx; bInheritHandle
0x180051f43  mov     [rbp+250h+var_2A0], rax
0x180051f47  mov     ecx, 1000h; dwDesiredAccess
0x180051f4c  mov     [rbp+250h+var_298], 4
0x180051f54  call    cs:__imp_OpenProcess
0x180051f5a  mov     r15, rax
0x180051f5d  test    rax, rax
0x180051f60  jz      short loc_180051F9A
0x180051f62  lea     r9, [rsp+350h+dwSize]; lpdwSize
0x180051f67  xor     edx, edx; dwFlags
0x180051f69  lea     r8, [rbp+250h+ExeName]; lpExeName
0x180051f6d  mov     rcx, rax; hProcess
0x180051f70  call    cs:__imp_QueryFullProcessImageNameW
0x180051f76  test    eax, eax
0x180051f78  jz      short loc_180051F9A
0x180051f7a  mov     eax, [rsp+350h+dwSize]
0x180051f7e  test    eax, eax
0x180051f80  jz      short loc_180051F9A
0x180051f82  lea     rcx, [rbp+250h+ExeName]
0x180051f86  mov     dword ptr [rbp+250h+var_288+4], r13d
0x180051f8a  lea     eax, ds:2[rax*2]
0x180051f91  mov     [rbp+250h+var_290], rcx
0x180051f95  mov     dword ptr [rbp+250h+var_288], eax
0x180051f98  jmp     short loc_180051FAD
0x180051f9a  lea     rax, asc_1800745A0; "-"
0x180051fa1  mov     [rbp+250h+var_288], 4
0x180051fa9  mov     [rbp+250h+var_290], rax
0x180051fad  cmp     [rbp+250h+arg_20], 0FFFFFFFFFFFFFFFFh
0x180051fb5  lea     rax, [rbp+250h+arg_18]
0x180051fbc  mov     rcx, cs:MsvEtwLogHandle
0x180051fc3  lea     rdx, NTLMServerBlockedHigher
0x180051fca  mov     [rbp+250h+var_280], rax
0x180051fce  lea     r9, [rbp+250h+var_2D0]
0x180051fd2  mov     eax, r13d
0x180051fd5  mov     [rbp+250h+var_278], 4
0x180051fdd  setz    al
0x180051fe0  mov     [rbp+250h+var_268], 4
0x180051fe8  cmp     [rbp+250h+arg_28], r13d
0x180051fef  mov     r8d, 8
0x180051ff5  mov     [rsp+350h+var_32C], eax
0x180051ff9  lea     rax, [rsp+350h+var_32C]
0x180051ffe  mov     [rbp+250h+var_270], rax
0x180052002  lea     rax, NTLMServerBlockedHigherAudit
0x180052009  cmovz   rdx, rax
0x18005200d  call    cs:__imp_EtwEventWrite
0x180052013  jmp     short loc_180052024
0x180052015  mov     rsi, qword ptr [rsp+350h+var_320+8]
0x18005201a  mov     rdi, qword ptr [rsp+350h+var_310+8]
0x18005201f  mov     rbx, qword ptr [rsp+350h+var_300+8]
0x180052024  test    rsi, rsi
0x180052027  jz      short loc_18005203F
0x180052029  mov     rax, cs:LsaFunctions
0x180052030  mov     rcx, rsi
0x180052033  mov     rax, [rax+188h]
0x18005203a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005203f  test    rdi, rdi
0x180052042  jz      short loc_18005205A
0x180052044  mov     rax, cs:LsaFunctions
0x18005204b  mov     rcx, rdi
0x18005204e  mov     rax, [rax+188h]
0x180052055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005205a  test    rbx, rbx
0x18005205d  jz      short loc_180052075
0x18005205f  mov     rax, cs:LsaFunctions
0x180052066  mov     rcx, rbx
0x180052069  mov     rax, [rax+188h]
0x180052070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052075  test    r15, r15
0x180052078  jz      short loc_180052083
0x18005207a  mov     rcx, r15; hObject
0x18005207d  call    cs:__imp_CloseHandle
0x180052083  test    r14, r14
0x180052086  jz      short loc_18005209E
0x180052088  mov     rax, cs:LsaFunctions
0x18005208f  mov     rcx, r14
0x180052092  mov     rax, [rax+188h]
0x180052099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005209e  mov     rcx, [rbp+250h+var_40]
0x1800520a5  xor     rcx, rsp; StackCookie
0x1800520a8  call    __security_check_cookie
0x1800520ad  add     rsp, 320h
0x1800520b4  pop     r15
0x1800520b6  pop     r14
0x1800520b8  pop     r13
0x1800520ba  pop     rdi
0x1800520bb  pop     rsi
0x1800520bc  pop     rbx
0x1800520bd  pop     rbp
0x1800520be  retn
```

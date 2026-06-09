# GetClientNameFromBinding(void *,wchar_t * *)

- ea: `0x18009484c`
- end: `0x1800949a8`
- name: `?GetClientNameFromBinding@@YAJPEAXPEAPEA_W@Z`
- size: `348`
- prototype: `__int64 __fastcall(void *, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800949b0`

## callees

- `0x18002c6c8`
- `0x18002c770`
- `0x180064f48`
- `0x18009484c`
- `0x18009bd1c`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x18009493b`
- `msvcrt!free` at `0x18009495a`
- `msvcrt!free` at `0x18009493b`
- `msvcrt!free` at `0x18009495a`
- `KERNEL32!GetLastError` at `0x1800948ca`
- `KERNEL32!GetLastError` at `0x180094919`
- `KERNEL32!GetLastError` at `0x18009496f`
- `KERNEL32!GetLastError` at `0x1800948ca`
- `KERNEL32!GetLastError` at `0x180094919`
- `KERNEL32!GetLastError` at `0x18009496f`
- `Secur32!GetUserNameExW` at `0x1800948bc`
- `Secur32!GetUserNameExW` at `0x18009490f`
- `Secur32!GetUserNameExW` at `0x1800948bc`
- `Secur32!GetUserNameExW` at `0x18009490f`
- `mqsec!MQSec_GetImpersonationObject` at `0x180094874`
- `mqsec!MQSec_GetImpersonationObject` at `0x180094874`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetClientNameFromBinding(void *a1, wchar_t **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  void *v5; // rbx
  DWORD v6; // eax
  DWORD LastError; // eax
  void *nSize; // [rsp+30h] [rbp+8h] BYREF
  struct CImpersonate *v10; // [rsp+38h] [rbp+10h] BYREF
  void *v11; // [rsp+40h] [rbp+18h]

  nSize = a1;
  *a2 = 0;
  v10 = 0;
  MQSec_GetImpersonationObject(0, &v10);
  v3 = (*(__int64 (__fastcall **)(struct CImpersonate *))(*(_QWORD *)v10 + 8LL))(v10);
  v4 = v3;
  if ( v3 )
  {
    LogMsgRPCStatus(v3, (wchar_t *)L"qm/ual", 0x14u);
LABEL_9:
    P<CInSeqLogContext>::~P<CInSeqLogContext>(&v10);
    return v4;
  }
  LODWORD(nSize) = 0;
  if ( GetUserNameExW(NameSamCompatible, 0, (PULONG)&nSize) || GetLastError() != 234 )
  {
    LastError = GetLastError();
    if ( LastError )
      LogMsgNTStatus(LastError, (wchar_t *)L"qm/ual", 0x1Eu);
    P<CInSeqLogContext>::~P<CInSeqLogContext>(&v10);
    return 5;
  }
  else
  {
    v5 = MmAllocate(saturated_mul((unsigned int)nSize, 2u));
    v11 = v5;
    if ( !GetUserNameExW(NameSamCompatible, (LPWSTR)v5, (PULONG)&nSize) )
    {
      v6 = GetLastError();
      if ( v6 )
        LogMsgNTStatus(v6, (wchar_t *)L"qm/ual", 0x28u);
      free(v5);
      v4 = 5;
      goto LABEL_9;
    }
    *a2 = (wchar_t *)v5;
    free(0);
    P<CInSeqLogContext>::~P<CInSeqLogContext>(&v10);
    return 0;
  }
}

```

## disassembly

```asm
0x18009484c  mov     rax, rsp
0x18009484f  mov     [rax+20h], rbx
0x180094853  mov     [rax+8], rcx
0x180094857  push    rdi
0x180094858  sub     rsp, 20h
0x18009485c  mov     rdi, rdx
0x18009485f  mov     qword ptr [rdx], 0
0x180094866  mov     qword ptr [rax+10h], 0
0x18009486e  lea     rdx, [rax+10h]
0x180094872  xor     ecx, ecx
0x180094874  call    cs:__imp_?MQSec_GetImpersonationObject@@YAXHPEAPEAVCImpersonate@@@Z; MQSec_GetImpersonationObject(int,CImpersonate * *)
0x18009487a  mov     rcx, [rsp+28h+arg_8]
0x18009487f  mov     rax, [rcx]
0x180094882  mov     rax, [rax+8]
0x180094886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009488b  mov     ebx, eax
0x18009488d  test    eax, eax
0x18009488f  jz      short loc_1800948AA
0x180094891  mov     r8d, 14h; unsigned __int16
0x180094897  lea     rdx, aQmUal; "qm/ual"
0x18009489e  mov     ecx, eax; int
0x1800948a0  call    ?LogMsgRPCStatus@@YAXJPEA_WG@Z; LogMsgRPCStatus(long,wchar_t *,ushort)
0x1800948a5  jmp     loc_180094947
0x1800948aa  mov     dword ptr [rsp+28h+nSize], 0
0x1800948b2  lea     r8, [rsp+28h+nSize]; nSize
0x1800948b7  xor     edx, edx; lpNameBuffer
0x1800948b9  lea     ecx, [rdx+2]; NameFormat
0x1800948bc  call    cs:__imp_GetUserNameExW
0x1800948c2  test    al, al
0x1800948c4  jnz     loc_18009496F
0x1800948ca  call    cs:__imp_GetLastError
0x1800948d0  cmp     eax, 0EAh
0x1800948d5  jnz     loc_18009496F
0x1800948db  mov     edx, dword ptr [rsp+28h+nSize]
0x1800948df  mov     eax, 2
0x1800948e4  mul     rdx
0x1800948e7  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800948ee  cmovb   rax, rdx
0x1800948f2  mov     rcx, rax; unsigned __int64
0x1800948f5  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800948fa  mov     rbx, rax
0x1800948fd  mov     [rsp+28h+arg_10], rax
0x180094902  lea     r8, [rsp+28h+nSize]; nSize
0x180094907  mov     rdx, rax; lpNameBuffer
0x18009490a  mov     ecx, 2; NameFormat
0x18009490f  call    cs:__imp_GetUserNameExW
0x180094915  test    al, al
0x180094917  jnz     short loc_180094955
0x180094919  call    cs:__imp_GetLastError
0x18009491f  test    eax, eax
0x180094921  jz      short loc_180094938
0x180094923  mov     r8d, 28h ; '('; unsigned __int16
0x180094929  lea     rdx, aQmUal; "qm/ual"
0x180094930  mov     ecx, eax; int
0x180094932  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180094937  nop
0x180094938  mov     rcx, rbx; Block
0x18009493b  call    cs:__imp_free
0x180094941  nop
0x180094942  mov     ebx, 5
0x180094947  lea     rcx, [rsp+28h+arg_8]
0x18009494c  call    ??1?$P@VCInSeqLogContext@@@@QEAA@XZ; P<CInSeqLogContext>::~P<CInSeqLogContext>(void)
0x180094951  mov     eax, ebx
0x180094953  jmp     short loc_18009499D
0x180094955  mov     [rdi], rbx
0x180094958  xor     ecx, ecx; Block
0x18009495a  call    cs:__imp_free
0x180094960  nop
0x180094961  lea     rcx, [rsp+28h+arg_8]
0x180094966  call    ??1?$P@VCInSeqLogContext@@@@QEAA@XZ; P<CInSeqLogContext>::~P<CInSeqLogContext>(void)
0x18009496b  xor     eax, eax
0x18009496d  jmp     short loc_18009499D
0x18009496f  call    cs:__imp_GetLastError
0x180094975  test    eax, eax
0x180094977  jz      short loc_18009498E
0x180094979  mov     r8d, 1Eh; unsigned __int16
0x18009497f  lea     rdx, aQmUal; "qm/ual"
0x180094986  mov     ecx, eax; int
0x180094988  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18009498d  nop
0x18009498e  lea     rcx, [rsp+28h+arg_8]
0x180094993  call    ??1?$P@VCInSeqLogContext@@@@QEAA@XZ; P<CInSeqLogContext>::~P<CInSeqLogContext>(void)
0x180094998  mov     eax, 5
0x18009499d  mov     rbx, [rsp+28h+arg_18]
0x1800949a2  add     rsp, 20h
0x1800949a6  pop     rdi
0x1800949a7  retn
```

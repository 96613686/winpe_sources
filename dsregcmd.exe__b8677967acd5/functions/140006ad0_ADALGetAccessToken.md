# ADALGetAccessToken

- ea: `0x140006ad0`
- end: `0x140006b4c`
- name: `ADALGetAccessToken`
- size: `124`
- prototype: `__int64 __fastcall(struct HADALREQUEST__ *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003bc0`

## callees

- `0x14000579c`
- `0x140005f28`
- `0x140006ad0`
- `0x14000a0a0`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006aef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006b34`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall ADALGetAccessToken(struct HADALREQUEST__ *a1, unsigned __int16 *a2, unsigned int *a3)
{
  struct TokenRequest *v6; // rax
  const struct CSecureString *v7; // rax
  unsigned int v8; // ebx
  DWORD result; // eax
  const struct ILogContext *v10; // rax
  const Exception *v11; // rbx
  const struct ILogContext *v12; // rax
  const Exception *v13; // [rsp+20h] [rbp-18h] BYREF
  const std::exception *v14; // [rsp+28h] [rbp-10h] BYREF
  char v16; // [rsp+58h] [rbp+20h] BYREF

  SetLastError(0);
  try
  {
    v6 = APIReq::Unwrap(a1);
    v7 = (const struct CSecureString *)(*(__int64 (__fastcall **)(struct TokenRequest *, char *))(*(_QWORD *)v6 + 16LL))(
                                         v6,
                                         &v16);
    v8 = FillAPIIntegralString(v7, a2, a3);
    CSecureString::~CSecureString((CSecureString *)&v16);
    result = v8;
  }
  catch ( const Exception *v13 )
  {
    v10 = APIReq::UnwrapNoException(a1);
    v11 = v13;
    Log::Error(v10, v13);
    SetLastError(*((_DWORD *)v11 + 2));
    return GetLastError();
  }
  catch ( const std::exception *v14 )
  {
    v12 = APIReq::UnwrapNoException(a1);
    HandleException(v12, v14);
    return GetLastError();
  }
  return result;
}

```

## disassembly

```asm
0x140006ad0  mov     [rsp+arg_8], rbx
0x140006ad5  mov     [rsp+arg_10], rsi
0x140006ada  mov     [rsp+arg_0], rcx
0x140006adf  push    rdi
0x140006ae0  sub     rsp, 30h
0x140006ae4  mov     rdi, r8
0x140006ae7  mov     rsi, rdx
0x140006aea  mov     rbx, rcx
0x140006aed  xor     ecx, ecx; dwErrCode
0x140006aef  call    cs:__imp_SetLastError
0x140006af5  nop
0x140006af6  mov     rcx, rbx; struct HADALREQUEST__ *
0x140006af9  call    ?Unwrap@APIReq@@SAPEAVTokenRequest@@PEAUHADALREQUEST__@@@Z; APIReq::Unwrap(HADALREQUEST__ *)
0x140006afe  mov     r9, rax
0x140006b01  mov     rcx, [rax]
0x140006b04  mov     rax, [rcx+10h]
0x140006b08  lea     rdx, [rsp+38h+arg_18]
0x140006b0d  mov     rcx, r9
0x140006b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b15  nop
0x140006b16  mov     r8, rdi; unsigned int *
0x140006b19  mov     rdx, rsi; unsigned __int16 *
0x140006b1c  mov     rcx, rax; struct CSecureString *
0x140006b1f  call    ?FillAPIIntegralString@@YAKAEBVCSecureString@@PEAGPEAK@Z; FillAPIIntegralString(CSecureString const &,ushort *,ulong *)
0x140006b24  mov     ebx, eax
0x140006b26  lea     rcx, [rsp+38h+arg_18]; this
0x140006b2b  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140006b30  mov     eax, ebx
0x140006b32  jmp     short loc_140006B3B
0x140006b34  call    cs:__imp_GetLastError
0x140006b3a  nop
0x140006b3b  mov     rbx, [rsp+38h+arg_8]
0x140006b40  mov     rsi, [rsp+38h+arg_10]
0x140006b45  add     rsp, 30h
0x140006b49  pop     rdi
0x140006b4a  retn
```

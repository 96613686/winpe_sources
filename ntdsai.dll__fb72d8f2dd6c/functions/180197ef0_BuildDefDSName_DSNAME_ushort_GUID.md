# BuildDefDSName(_DSNAME *,ushort *,_GUID *)

- ea: `0x180197ef0`
- end: `0x180198055`
- name: `?BuildDefDSName@@YAXPEAU_DSNAME@@PEAGPEAU_GUID@@@Z`
- size: `357`
- prototype: `void __fastcall(struct _DSNAME *, unsigned __int16 *, struct _GUID *)`
- caller_count: `12`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18018bf28`
- `0x18018c7f4`
- `0x18018d798`
- `0x18018f88c`
- `0x180190294`
- `0x180193778`
- `0x180193c18`
- `0x180194070`
- `0x180197a2c`
- `0x180197e18`
- `0x180198f84`
- `0x1801991a0`

## callees

- `0x180021aa3`
- `0x180192394`
- `0x180197ef0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180197f3c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180197f3c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180197f73`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180197f73`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180197fb9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180197ff4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180197fb9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180197ff4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180197f9c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180197fc9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180197f9c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180197fc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197f8c`
- `ntdll!RtlLengthSid` at `0x180197fa7`
- `ntdll!RtlLengthSid` at `0x180197fa7`

## string_xrefs

- `0x180197f32`: `<SID=S-`

## pseudocode

```c
void __fastcall BuildDefDSName(struct _DSNAME *a1, unsigned __int16 *a2, struct _GUID *a3)
{
  __int64 v3; // rbp
  __int64 v5; // rsi
  unsigned __int16 *v6; // rdi
  __int64 v8; // rax
  __int64 v9; // rsi
  BOOL v10; // eax
  ULONG v11; // eax
  PSID Sid; // [rsp+60h] [rbp+18h] BYREF

  v3 = -1;
  v5 = -1;
  v6 = a2;
  do
    ++v5;
  while ( a2[v5] );
  if ( (unsigned int)v5 <= 8
    || (unsigned int)_o__wcsnicmp(a2, L"<SID=S-", 7)
    || (v8 = (unsigned int)(v5 - 1), v9 = v8, v6[v8] != 62) )
  {
    do
      ++v3;
    while ( v6[v3] );
    *((_DWORD *)a1 + 13) = v3;
    *(_DWORD *)a1 = 2 * v3 + 58;
    StringCchCopyW((unsigned __int16 *)a1 + 28, (unsigned int)(v3 + 1), v6);
    LODWORD(v6) = 0;
  }
  else
  {
    Sid = 0;
    v6[v8] = 0;
    v10 = ConvertStringSidToSidW(v6 + 5, &Sid);
    v6[v9] = 62;
    if ( !v10 )
    {
      GetLastError();
      RaiseException(0xF007u, 1u, 0, 0);
    }
    v11 = RtlLengthSid(Sid);
    v6 = (unsigned __int16 *)v11;
    if ( v11 > 0x1C )
    {
      FreeSid(Sid);
      RaiseException(0xF007u, 1u, 0, 0);
    }
    *((_DWORD *)a1 + 13) = 0;
    *(_DWORD *)a1 = 58;
    *((_WORD *)a1 + 28) = 0;
    memcpy_0((char *)a1 + 24, Sid, (size_t)v6);
    FreeSid(Sid);
  }
  *((_DWORD *)a1 + 1) = (_DWORD)v6;
  if ( a3 )
    *(struct _GUID *)((char *)a1 + 8) = *a3;
  else
    *(_OWORD *)((char *)a1 + 8) = 0;
}

```

## disassembly

```asm
0x180197ef0  mov     [rsp+arg_0], rbx
0x180197ef5  mov     [rsp+arg_8], rbp
0x180197efa  push    rsi
0x180197efb  push    rdi
0x180197efc  push    r12
0x180197efe  push    r14
0x180197f00  push    r15
0x180197f02  sub     rsp, 20h
0x180197f06  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180197f0a  mov     r14, r8
0x180197f0d  mov     rsi, rbp
0x180197f10  xor     r15d, r15d
0x180197f13  mov     rdi, rdx
0x180197f16  mov     rbx, rcx
0x180197f19  inc     rsi
0x180197f1c  cmp     [rdx+rsi*2], r15w
0x180197f21  jnz     short loc_180197F19
0x180197f23  cmp     esi, 8
0x180197f26  jbe     loc_180197FFC
0x180197f2c  mov     r8d, 7
0x180197f32  lea     rdx, aSidS_0; "<SID=S-"
0x180197f39  mov     rcx, rdi
0x180197f3c  call    cs:__imp__o__wcsnicmp
0x180197f42  test    eax, eax
0x180197f44  jnz     loc_180197FFC
0x180197f4a  lea     eax, [rsi-1]
0x180197f4d  mov     r12d, 3Eh ; '>'
0x180197f53  mov     esi, eax
0x180197f55  cmp     [rdi+rax*2], r12w
0x180197f5a  jnz     loc_180197FFC
0x180197f60  lea     rcx, [rdi+0Ah]; StringSid
0x180197f64  mov     [rsp+48h+Sid], r15
0x180197f69  lea     rdx, [rsp+48h+Sid]; Sid
0x180197f6e  mov     [rdi+rax*2], r15w
0x180197f73  call    cs:__imp_ConvertStringSidToSidW
0x180197f79  mov     [rdi+rsi*2], r12w
0x180197f7e  mov     ebp, 0F007h
0x180197f83  lea     esi, [r12-3Dh]
0x180197f88  test    eax, eax
0x180197f8a  jnz     short loc_180197FA2
0x180197f8c  call    cs:__imp_GetLastError
0x180197f92  xor     r9d, r9d; lpArguments
0x180197f95  xor     r8d, r8d; nNumberOfArguments
0x180197f98  mov     edx, esi; dwExceptionFlags
0x180197f9a  mov     ecx, ebp; dwExceptionCode
0x180197f9c  call    cs:__imp_RaiseException
0x180197fa2  mov     rcx, [rsp+48h+Sid]; Sid
0x180197fa7  call    cs:__imp_RtlLengthSid
0x180197fad  mov     edi, eax
0x180197faf  cmp     eax, 1Ch
0x180197fb2  jbe     short loc_180197FCF
0x180197fb4  mov     rcx, [rsp+48h+Sid]; pSid
0x180197fb9  call    cs:__imp_FreeSid
0x180197fbf  xor     r9d, r9d; lpArguments
0x180197fc2  xor     r8d, r8d; nNumberOfArguments
0x180197fc5  mov     edx, esi; dwExceptionFlags
0x180197fc7  mov     ecx, ebp; dwExceptionCode
0x180197fc9  call    cs:__imp_RaiseException
0x180197fcf  mov     [rbx+34h], r15d
0x180197fd3  lea     rcx, [rbx+18h]; void *
0x180197fd7  mov     dword ptr [rbx], 3Ah ; ':'
0x180197fdd  mov     r8, rdi; Size
0x180197fe0  mov     [rbx+38h], r15w
0x180197fe5  mov     rdx, [rsp+48h+Sid]; Src
0x180197fea  call    memcpy_0
0x180197fef  mov     rcx, [rsp+48h+Sid]; pSid
0x180197ff4  call    cs:__imp_FreeSid
0x180197ffa  jmp     short loc_180198024
0x180197ffc  inc     rbp
0x180197fff  cmp     [rdi+rbp*2], r15w
0x180198004  jnz     short loc_180197FFC
0x180198006  lea     eax, ds:3Ah[rbp*2]
0x18019800d  mov     [rbx+34h], ebp
0x180198010  lea     edx, [rbp+1]; unsigned __int64
0x180198013  mov     [rbx], eax
0x180198015  lea     rcx, [rbx+38h]; unsigned __int16 *
0x180198019  mov     r8, rdi; unsigned __int16 *
0x18019801c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180198021  mov     edi, r15d
0x180198024  mov     [rbx+4], edi
0x180198027  test    r14, r14
0x18019802a  jz      short loc_180198037
0x18019802c  movups  xmm0, xmmword ptr [r14]
0x180198030  movdqu  xmmword ptr [rbx+8], xmm0
0x180198035  jmp     short loc_18019803E
0x180198037  xorps   xmm0, xmm0
0x18019803a  movups  xmmword ptr [rbx+8], xmm0
0x18019803e  mov     rbx, [rsp+48h+arg_0]
0x180198043  mov     rbp, [rsp+48h+arg_8]
0x180198048  add     rsp, 20h
0x18019804c  pop     r15
0x18019804e  pop     r14
0x180198050  pop     r12
0x180198052  pop     rdi
0x180198053  pop     rsi
0x180198054  retn
```

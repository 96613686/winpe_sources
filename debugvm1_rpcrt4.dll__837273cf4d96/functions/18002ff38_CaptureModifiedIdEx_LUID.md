# CaptureModifiedIdEx(_LUID *)

- ea: `0x18002ff38`
- end: `0x18003007f`
- name: `?CaptureModifiedIdEx@@YAJPEAU_LUID@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(struct _LUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002a2a0`
- `0x18002e0f0`

## callees

- `0x1800283bc`
- `0x18002ff38`
- `0x1800ca140`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18002ff91`
- `ntdll!NtOpenThreadToken` at `0x18002ff91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003002e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003002e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030019`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030019`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ff7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ff7a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030009`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030009`

## pseudocode

```c
__int64 __fastcall CaptureModifiedIdEx(struct _LUID *a1)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // edi
  NTSTATUS v4; // eax
  DWORD LastError; // esi
  void *TokenHandle; // [rsp+30h] [rbp-39h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-31h] BYREF
  _DWORD v9[6]; // [rsp+40h] [rbp-29h] BYREF
  _OWORD TokenInformation[3]; // [rsp+58h] [rbp-11h] BYREF
  struct _LUID v11; // [rsp+88h] [rbp+1Fh]

  TokenHandle = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v11 = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  v3 = 14;
  v4 = NtOpenThreadToken(CurrentThread, 0xEu, 1u, &TokenHandle);
  if ( v4 == -1073741790 )
  {
    v3 = 5;
    goto LABEL_17;
  }
  if ( v4 != -1073741700 )
  {
    if ( v4 == -1073741658 )
      goto LABEL_15;
    if ( !v4 )
    {
      if ( TokenHandle == (void *)4294967293LL )
        goto LABEL_3;
      if ( TokenHandle != (void *)4294967294LL )
      {
        if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
          LastError = 0;
        else
          LastError = GetLastError();
        CloseHandle(TokenHandle);
        if ( !LastError )
        {
          v3 = 0;
          *a1 = v11;
          return v3;
        }
LABEL_18:
        *a1 = 0;
        return v3;
      }
LABEL_15:
      a1->LowPart = -2;
      goto LABEL_4;
    }
LABEL_17:
    v9[2] = v4;
    TokenHandle = 0;
    v9[0] = 3;
    RpcpErrorAddRecord(2u, v3, 0x460u, 1, (struct tagParam *)v9);
    goto LABEL_18;
  }
LABEL_3:
  a1->LowPart = -3;
LABEL_4:
  a1->HighPart = 0;
  return 0;
}

```

## disassembly

```asm
0x18002ff38  push    rbp
0x18002ff3a  push    rbx
0x18002ff3b  push    rsi
0x18002ff3c  push    rdi
0x18002ff3d  lea     rbp, [rsp-3Fh]
0x18002ff42  sub     rsp, 0A8h
0x18002ff49  mov     rax, cs:__security_cookie
0x18002ff50  xor     rax, rsp
0x18002ff53  mov     [rbp+57h+var_30], rax
0x18002ff57  xorps   xmm0, xmm0
0x18002ff5a  mov     [rbp+57h+TokenHandle], 0
0x18002ff62  xor     eax, eax
0x18002ff64  mov     rbx, rcx
0x18002ff67  movups  [rbp+57h+TokenInformation], xmm0
0x18002ff6b  mov     [rbp+57h+var_38], rax
0x18002ff6f  movups  [rbp+57h+var_58], xmm0
0x18002ff73  mov     [rbp+57h+var_88], eax
0x18002ff76  movups  [rbp+57h+var_48], xmm0
0x18002ff7a  call    cs:__imp_GetCurrentThread
0x18002ff80  mov     edi, 0Eh
0x18002ff85  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002ff89  mov     edx, edi; DesiredAccess
0x18002ff8b  mov     rcx, rax; ThreadHandle
0x18002ff8e  mov     r8b, 1; OpenAsSelf
0x18002ff91  call    cs:__imp_NtOpenThreadToken
0x18002ff97  cmp     eax, 0C0000022h
0x18002ff9c  jz      loc_180030040
0x18002ffa2  mov     edx, 0FFFFFFFDh
0x18002ffa7  cmp     eax, 0C000007Ch
0x18002ffac  jnz     short loc_18002FFD3
0x18002ffae  mov     [rbx], edx
0x18002ffb0  mov     dword ptr [rbx+4], 0
0x18002ffb7  xor     edi, edi
0x18002ffb9  mov     eax, edi
0x18002ffbb  mov     rcx, [rbp+57h+var_30]
0x18002ffbf  xor     rcx, rsp; StackCookie
0x18002ffc2  call    __security_check_cookie
0x18002ffc7  add     rsp, 0A8h
0x18002ffce  pop     rdi
0x18002ffcf  pop     rsi
0x18002ffd0  pop     rbx
0x18002ffd1  pop     rbp
0x18002ffd2  retn
0x18002ffd3  mov     r8d, 0FFFFFFFEh
0x18002ffd9  cmp     eax, 0C00000A6h
0x18002ffde  jz      short loc_180030038
0x18002ffe0  test    eax, eax
0x18002ffe2  jnz     short loc_180030045
0x18002ffe4  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002ffe8  cmp     rcx, rdx
0x18002ffeb  jz      short loc_18002FFAE
0x18002ffed  cmp     rcx, r8
0x18002fff0  jz      short loc_180030038
0x18002fff2  mov     r9d, 38h ; '8'; TokenInformationLength
0x18002fff8  lea     rax, [rbp+57h+var_88]
0x18002fffc  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180030000  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180030005  lea     edx, [r9-2Eh]; TokenInformationClass
0x180030009  call    cs:__imp_GetTokenInformation
0x18003000f  test    eax, eax
0x180030011  jz      short loc_18003002E
0x180030013  xor     esi, esi
0x180030015  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180030019  call    cs:__imp_CloseHandle
0x18003001f  test    esi, esi
0x180030021  jnz     short loc_180030073
0x180030023  mov     rax, [rbp+57h+var_38]
0x180030027  xor     edi, edi
0x180030029  mov     [rbx], rax
0x18003002c  jmp     short loc_18002FFB9
0x18003002e  call    cs:__imp_GetLastError
0x180030034  mov     esi, eax
0x180030036  jmp     short loc_180030015
0x180030038  mov     [rbx], r8d
0x18003003b  jmp     loc_18002FFB0
0x180030040  mov     edi, 5
0x180030045  xor     ecx, ecx
0x180030047  mov     [rbp+57h+var_78], eax
0x18003004a  mov     [rbp+57h+TokenHandle], rcx
0x18003004e  lea     rax, [rbp+57h+var_80]
0x180030052  mov     r8d, 460h; unsigned __int16
0x180030058  mov     [rbp+57h+var_80], 3
0x18003005f  mov     edx, edi; int
0x180030061  mov     [rsp+0C0h+ReturnLength], rax; struct tagParam *
0x180030066  lea     r9d, [rcx+1]; int
0x18003006a  lea     ecx, [r9+1]; unsigned int
0x18003006e  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180030073  mov     qword ptr [rbx], 0
0x18003007a  jmp     loc_18002FFB9
```

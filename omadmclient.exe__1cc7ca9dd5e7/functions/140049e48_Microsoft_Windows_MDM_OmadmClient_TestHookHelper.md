# Microsoft::Windows::MDM::OmadmClient::TestHookHelper

- ea: `0x140049e48`
- end: `0x14004a080`
- name: `Microsoft::Windows::MDM::OmadmClient::TestHookHelper`
- size: `568`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140046ed4`
- `0x140048db0`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x140049e48`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049f49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049ff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049f49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049ff4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049f68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004a013`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049f68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004a013`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140049f5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a005`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140049f5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a005`
- `DMCmnUtils!CopyString` at `0x140049f82`
- `DMCmnUtils!CopyString` at `0x14004a030`
- `DMCmnUtils!CopyString` at `0x140049f82`
- `DMCmnUtils!CopyString` at `0x14004a030`

## string_xrefs

- `0x140049efd`: `Token`
- `0x140049fa8`: `DeviceToken`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::TestHookHelper(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  __int64 v5; // rax
  void *v6; // rbp
  DWORD LastError; // ebx
  void *v8; // rbp
  DWORD v9; // ebx
  _DWORD v11[4]; // [rsp+30h] [rbp-468h] BYREF
  unsigned __int16 v12[264]; // [rsp+40h] [rbp-458h] BYREF
  unsigned __int16 v13[264]; // [rsp+250h] [rbp-248h] BYREF

  if ( !*(_QWORD *)(a2 + 600) )
    return 2147943568LL;
  v11[0] = 0;
  memset_0(v12, 0, 0x208u);
  memset_0(v13, 0, 0x208u);
  if ( (*(int (__fastcall **)(__int64, _QWORD, const wchar_t *, _DWORD *))(*(_QWORD *)a1 + 272LL))(
         a1,
         *(_QWORD *)(a2 + 560),
         L"Enrolled",
         v11) >= 0 )
    *(_DWORD *)(a2 + 712) = v11[0] != 0;
  v4 = -1;
  if ( (*(int (__fastcall **)(__int64, _QWORD, const wchar_t *, unsigned __int16 *, int))(*(_QWORD *)a1 + 280LL))(
         a1,
         *(_QWORD *)(a2 + 560),
         L"Token",
         v12,
         260) < 0 )
    goto LABEL_21;
  v5 = -1;
  do
    ++v5;
  while ( v12[v5] );
  if ( !v5 )
    goto LABEL_21;
  v6 = *(void **)(a2 + 608);
  if ( v6 )
  {
    LastError = GetLastError();
    LocalFree(v6);
    SetLastError(LastError);
  }
  *(_QWORD *)(a2 + 608) = 0;
  if ( (int)CopyString(v12, 0xFFFFFFFF, (unsigned __int16 **)(a2 + 608)) < 0 )
  {
LABEL_21:
    if ( (*(int (__fastcall **)(__int64, _QWORD, const wchar_t *, unsigned __int16 *, int))(*(_QWORD *)a1 + 280LL))(
           a1,
           *(_QWORD *)(a2 + 560),
           L"DeviceToken",
           v13,
           260) < 0 )
      return 2147943568LL;
    do
      ++v4;
    while ( v13[v4] );
    if ( !v4 )
      return 2147943568LL;
    v8 = *(void **)(a2 + 616);
    if ( v8 )
    {
      v9 = GetLastError();
      LocalFree(v8);
      SetLastError(v9);
    }
    *(_QWORD *)(a2 + 616) = 0;
    if ( (int)CopyString(v13, 0xFFFFFFFF, (unsigned __int16 **)(a2 + 616)) < 0 )
      return 2147943568LL;
  }
  *(_DWORD *)(a2 + 712) = 1;
  return 0;
}

```

## disassembly

```asm
0x140049e48  mov     [rsp+arg_10], rbx
0x140049e4d  mov     [rsp+arg_18], rbp
0x140049e52  push    rsi
0x140049e53  push    rdi
0x140049e54  push    r12
0x140049e56  push    r14
0x140049e58  push    r15
0x140049e5a  sub     rsp, 470h
0x140049e61  mov     rax, cs:__security_cookie
0x140049e68  xor     rax, rsp
0x140049e6b  mov     [rsp+498h+var_38], rax
0x140049e73  xor     r12d, r12d
0x140049e76  mov     rdi, rdx
0x140049e79  mov     r15, rcx
0x140049e7c  cmp     [rdx+258h], r12
0x140049e83  jz      loc_14004A04E
0x140049e89  mov     ebx, 208h
0x140049e8e  mov     [rsp+498h+var_468], r12d
0x140049e93  mov     r8d, ebx; Size
0x140049e96  lea     rcx, [rsp+498h+var_458]; void *
0x140049e9b  xor     edx, edx; Val
0x140049e9d  call    memset_0
0x140049ea2  mov     r8d, ebx; Size
0x140049ea5  lea     rcx, [rsp+498h+var_248]; void *
0x140049ead  xor     edx, edx; Val
0x140049eaf  call    memset_0
0x140049eb4  mov     rax, [r15]
0x140049eb7  lea     r9, [rsp+498h+var_468]
0x140049ebc  mov     rdx, [rdi+230h]
0x140049ec3  lea     r8, aEnrolled; "Enrolled"
0x140049eca  mov     rcx, r15
0x140049ecd  mov     rax, [rax+110h]
0x140049ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049ed9  test    eax, eax
0x140049edb  js      short loc_140049EEE
0x140049edd  cmp     [rsp+498h+var_468], r12d
0x140049ee2  mov     eax, r12d
0x140049ee5  setnz   al
0x140049ee8  mov     [rdi+2C8h], eax
0x140049eee  mov     rax, [r15]
0x140049ef1  lea     r9, [rsp+498h+var_458]
0x140049ef6  mov     rdx, [rdi+230h]
0x140049efd  lea     r8, aToken; "Token"
0x140049f04  mov     rcx, r15
0x140049f07  mov     [rsp+498h+var_478], 104h
0x140049f0f  mov     rax, [rax+118h]
0x140049f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049f1b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140049f1f  test    eax, eax
0x140049f21  js      short loc_140049F96
0x140049f23  lea     rcx, [rsp+498h+var_458]
0x140049f28  mov     rax, rsi
0x140049f2b  inc     rax
0x140049f2e  cmp     [rcx+rax*2], r12w
0x140049f33  jnz     short loc_140049F2B
0x140049f35  test    rax, rax
0x140049f38  jz      short loc_140049F96
0x140049f3a  lea     r14, [rdi+260h]
0x140049f41  mov     rbp, [r14]
0x140049f44  test    rbp, rbp
0x140049f47  jz      short loc_140049F74
0x140049f49  call    cs:__imp_GetLastError
0x140049f50  nop     dword ptr [rax+rax+00h]
0x140049f55  mov     rcx, rbp; hMem
0x140049f58  mov     ebx, eax
0x140049f5a  call    cs:__imp_LocalFree
0x140049f61  nop     dword ptr [rax+rax+00h]
0x140049f66  mov     ecx, ebx; dwErrCode
0x140049f68  call    cs:__imp_SetLastError
0x140049f6f  nop     dword ptr [rax+rax+00h]
0x140049f74  mov     r8, r14
0x140049f77  mov     [r14], r12
0x140049f7a  or      edx, 0FFFFFFFFh
0x140049f7d  lea     rcx, [rsp+498h+var_458]
0x140049f82  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140049f89  nop     dword ptr [rax+rax+00h]
0x140049f8e  test    eax, eax
0x140049f90  jns     loc_14004A040
0x140049f96  mov     rax, [r15]
0x140049f99  lea     r9, [rsp+498h+var_248]
0x140049fa1  mov     rdx, [rdi+230h]
0x140049fa8  lea     r8, aDevicetoken; "DeviceToken"
0x140049faf  mov     rcx, r15
0x140049fb2  mov     [rsp+498h+var_478], 104h
0x140049fba  mov     rax, [rax+118h]
0x140049fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049fc6  test    eax, eax
0x140049fc8  js      loc_14004A04E
0x140049fce  lea     rax, [rsp+498h+var_248]
0x140049fd6  inc     rsi
0x140049fd9  cmp     [rax+rsi*2], r12w
0x140049fde  jnz     short loc_140049FD6
0x140049fe0  test    rsi, rsi
0x140049fe3  jz      short loc_14004A04E
0x140049fe5  lea     rsi, [rdi+268h]
0x140049fec  mov     rbp, [rsi]
0x140049fef  test    rbp, rbp
0x140049ff2  jz      short loc_14004A01F
0x140049ff4  call    cs:__imp_GetLastError
0x140049ffb  nop     dword ptr [rax+rax+00h]
0x14004a000  mov     rcx, rbp; hMem
0x14004a003  mov     ebx, eax
0x14004a005  call    cs:__imp_LocalFree
0x14004a00c  nop     dword ptr [rax+rax+00h]
0x14004a011  mov     ecx, ebx; dwErrCode
0x14004a013  call    cs:__imp_SetLastError
0x14004a01a  nop     dword ptr [rax+rax+00h]
0x14004a01f  mov     r8, rsi
0x14004a022  mov     [rsi], r12
0x14004a025  or      edx, 0FFFFFFFFh
0x14004a028  lea     rcx, [rsp+498h+var_248]
0x14004a030  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x14004a037  nop     dword ptr [rax+rax+00h]
0x14004a03c  test    eax, eax
0x14004a03e  js      short loc_14004A04E
0x14004a040  mov     dword ptr [rdi+2C8h], 1
0x14004a04a  xor     eax, eax
0x14004a04c  jmp     short loc_14004A053
0x14004a04e  mov     eax, 80070490h
0x14004a053  mov     rcx, [rsp+498h+var_38]
0x14004a05b  xor     rcx, rsp; StackCookie
0x14004a05e  call    __security_check_cookie
0x14004a063  lea     r11, [rsp+498h+var_28]
0x14004a06b  mov     rbx, [r11+40h]
0x14004a06f  mov     rbp, [r11+48h]
0x14004a073  mov     rsp, r11
0x14004a076  pop     r15
0x14004a078  pop     r14
0x14004a07a  pop     r12
0x14004a07c  pop     rdi
0x14004a07d  pop     rsi
0x14004a07e  retn
```

# Microsoft::HostGuardian::Client::HgKeyProtection::UnwrapKeyProtector(wchar_t *,HgBlob *,HgUnwrapKeyProtectorFlag,HgBlob *,HgBlob *,HgBlob *,HgBlob *,HgUnwrapKeyProtectorResultFlag *)

- ea: `0x18000b260`
- end: `0x18000b3a9`
- name: `?UnwrapKeyProtector@HgKeyProtection@Client@HostGuardian@Microsoft@@UEAAJPEA_WPEAUHgBlob@@W4HgUnwrapKeyProtectorFlag@@1111PEAW4HgUnwrapKeyProtectorResultFlag@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(__int64, OLECHAR *, __int64, char, __int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800064b4`
- `0x18000b260`
- `0x18000e100`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000b2fd`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b2fd`

## string_xrefs

- `0x18000b37c`: `servercommon\base\securehostingservice\common\service\lib\hgkeyprotection.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgKeyProtection::UnwrapKeyProtector(
        __int64 a1,
        OLECHAR *a2,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9)
{
  OLECHAR *v11; // rax
  __int64 v12; // rdx
  const char *v13; // r9
  __int64 result; // rax
  wil *v15; // rcx
  int v16; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v11 = a2;
  if ( !a3 || !*(_DWORD *)a3 || !*(_QWORD *)(a3 + 8) || !a5 || !a6 || !a7 || !a8 || !a9 )
  {
    v12 = 35;
    goto LABEL_14;
  }
  if ( (a4 & 1) != 0 )
  {
    if ( !SysStringLen(a2) )
    {
      v12 = 38;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgkeyprotection.cpp",
        (const char *)0x80070057LL,
        v16);
      return 2147942487LL;
    }
    v11 = a2;
  }
  try
  {
    *(_OWORD *)a5 = 0;
    *(_OWORD *)a6 = 0;
    *(_OWORD *)a7 = 0;
    *(_OWORD *)a8 = 0;
    Microsoft::HostGuardian::Client::HgServiceController::UnwrapKeyProtector(
      *((RTL_SRWLOCK **)g_service + 24),
      v11,
      (__int128 *)a3,
      a4,
      a5,
      a6,
      a7,
      a8,
      a9);
    result = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x3C,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgkeyprotection.cpp",
      v13);
    if ( *(_DWORD *)a5 && *(_QWORD *)(a5 + 8) )
    {
      CoTaskMemFree(*(LPVOID *)(a5 + 8));
      *(_QWORD *)(a5 + 8) = 0;
      *(_DWORD *)a5 = 0;
    }
    if ( *(_DWORD *)a6 && *(_QWORD *)(a6 + 8) )
    {
      CoTaskMemFree(*(LPVOID *)(a6 + 8));
      *(_QWORD *)(a6 + 8) = 0;
      *(_DWORD *)a6 = 0;
    }
    if ( *(_DWORD *)a7 && *(_QWORD *)(a7 + 8) )
    {
      CoTaskMemFree(*(LPVOID *)(a7 + 8));
      *(_QWORD *)(a7 + 8) = 0;
      *(_DWORD *)a7 = 0;
    }
    if ( *(_DWORD *)a8 && *(_QWORD *)(a8 + 8) )
    {
      CoTaskMemFree(*(LPVOID *)(a8 + 8));
      *(_QWORD *)(a8 + 8) = 0;
      *(_DWORD *)a8 = 0;
    }
    return (unsigned int)wil::ResultFromCaughtException(v15);
  }
  return result;
}

```

## disassembly

```asm
0x18000b260  mov     [rsp+arg_0], rbx
0x18000b265  mov     [rsp+arg_18], rsi
0x18000b26a  mov     [rsp+arg_8], rdx
0x18000b26f  push    rdi
0x18000b270  push    r12
0x18000b272  push    r13
0x18000b274  push    r14
0x18000b276  push    r15
0x18000b278  sub     rsp, 50h
0x18000b27c  mov     r13d, r9d
0x18000b27f  mov     rbx, r8
0x18000b282  mov     rax, rdx
0x18000b285  test    r8, r8
0x18000b288  jz      loc_18000B36F
0x18000b28e  cmp     dword ptr [r8], 0
0x18000b292  jbe     loc_18000B36F
0x18000b298  cmp     qword ptr [r8+8], 0
0x18000b29d  jz      loc_18000B36F
0x18000b2a3  mov     rdi, [rsp+78h+arg_20]
0x18000b2ab  test    rdi, rdi
0x18000b2ae  jz      loc_18000B36F
0x18000b2b4  mov     rsi, [rsp+78h+arg_28]
0x18000b2bc  test    rsi, rsi
0x18000b2bf  jz      loc_18000B36F
0x18000b2c5  mov     r14, [rsp+78h+arg_30]
0x18000b2cd  test    r14, r14
0x18000b2d0  jz      loc_18000B36F
0x18000b2d6  mov     r15, [rsp+78h+arg_38]
0x18000b2de  test    r15, r15
0x18000b2e1  jz      loc_18000B36F
0x18000b2e7  mov     r12, [rsp+78h+arg_40]
0x18000b2ef  test    r12, r12
0x18000b2f2  jz      short loc_18000B36F
0x18000b2f4  test    r13b, 1
0x18000b2f8  jz      short loc_18000B314
0x18000b2fa  mov     rcx, rdx; pbstr
0x18000b2fd  call    cs:__imp_SysStringLen
0x18000b303  test    eax, eax
0x18000b305  jnz     short loc_18000B30C
0x18000b307  lea     edx, [rax+26h]
0x18000b30a  jmp     short loc_18000B374
0x18000b30c  mov     rax, [rsp+78h+arg_8]
0x18000b314  xorps   xmm0, xmm0
0x18000b317  movdqu  xmmword ptr [rdi], xmm0
0x18000b31b  xorps   xmm1, xmm1
0x18000b31e  movdqu  xmmword ptr [rsi], xmm1
0x18000b322  movdqu  xmmword ptr [r14], xmm0
0x18000b327  movdqu  xmmword ptr [r15], xmm1
0x18000b32c  mov     [rsp+78h+var_38], r12
0x18000b331  mov     [rsp+78h+var_40], r15
0x18000b336  mov     [rsp+78h+var_48], r14
0x18000b33b  mov     [rsp+78h+var_50], rsi
0x18000b340  mov     [rsp+78h+var_58], rdi
0x18000b345  mov     r9d, r13d
0x18000b348  mov     r8, rbx
0x18000b34b  mov     rdx, rax
0x18000b34e  mov     rcx, cs:?g_service@@3PEAVHgService@Client@HostGuardian@Microsoft@@EA; Microsoft::HostGuardian::Client::HgService * g_service
0x18000b355  mov     rcx, [rcx+0C0h]
0x18000b35c  call    ?UnwrapKeyProtector@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXQEA_WQEAUHgBlob@@W4HgUnwrapKeyProtectorFlag@@PEAU5@333PEAW4HgUnwrapKeyProtectorResultFlag@@@Z; Microsoft::HostGuardian::Client::HgServiceController::UnwrapKeyProtector(wchar_t * const,HgBlob * const,HgUnwrapKeyProtectorFlag,HgBlob *,HgBlob *,HgBlob *,HgBlob *,HgUnwrapKeyProtectorResultFlag *)
0x18000b361  nop
0x18000b362  xor     eax, eax
0x18000b364  jmp     short loc_18000B38F
0x18000b366  mov     eax, [rsp+78h+arg_10]
0x18000b36d  jmp     short loc_18000B38F
0x18000b36f  mov     edx, 23h ; '#'; void *
0x18000b374  mov     ebx, 80070057h
0x18000b379  mov     r9d, ebx; char *
0x18000b37c  lea     r8, aServercommonBa_6; "servercommon\\base\\securehostingservic"...
0x18000b383  mov     rcx, [rsp+78h]; this
0x18000b388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b38d  mov     eax, ebx
0x18000b38f  lea     r11, [rsp+78h+var_28]
0x18000b394  mov     rbx, [r11+30h]
0x18000b398  mov     rsi, [r11+48h]
0x18000b39c  mov     rsp, r11
0x18000b39f  pop     r15
0x18000b3a1  pop     r14
0x18000b3a3  pop     r13
0x18000b3a5  pop     r12
0x18000b3a7  pop     rdi
0x18000b3a8  retn
```

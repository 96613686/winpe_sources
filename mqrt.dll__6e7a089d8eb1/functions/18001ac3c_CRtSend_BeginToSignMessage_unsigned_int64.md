# CRtSend::BeginToSignMessage(unsigned __int64 *)

- ea: `0x18001ac3c`
- end: `0x18001ad11`
- name: `?BeginToSignMessage@CRtSend@@AEAAJPEA_K@Z`
- size: `213`
- prototype: `int(CRtSend *__hidden this, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bf20`
- `0x18001c188`

## callees

- `0x180013c74`
- `0x18001ac3c`
- `0x180026010`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x18001acbb`
- `ADVAPI32!CryptCreateHash` at `0x18001acbb`
- `KERNEL32!GetLastError` at `0x18001acc5`
- `KERNEL32!GetLastError` at `0x18001acc5`
- `mqsec!MQSec_UpgradeHashAlgorithm` at `0x18001ac89`
- `mqsec!MQSec_UpgradeHashAlgorithm` at `0x18001ac89`

## pseudocode

```c
__int64 __fastcall CRtSend::BeginToSignMessage(CRtSend *this, unsigned __int64 *a2)
{
  int v4; // ebx
  unsigned __int16 v5; // r8
  ALG_ID v7; // ebx
  HCRYPTPROV v8; // rax
  signed int LastError; // eax
  bool v10; // sf

  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 93) + 8LL))(*((_QWORD *)this + 93));
  if ( v4 < 0 )
  {
    v5 = 160;
LABEL_3:
    LogMsgHR(v4, (wchar_t *)L"rt/CRtSend", v5);
    return (unsigned int)v4;
  }
  MQSec_UpgradeHashAlgorithm(*((unsigned int **)this + 32));
  v7 = **((_DWORD **)this + 32);
  v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 93) + 16LL))(*((_QWORD *)this + 93));
  if ( !CryptCreateHash(v8, v7, 0, 0, a2) )
  {
    LastError = GetLastError();
    v10 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v10 = LastError < 0;
    }
    if ( v10 )
      LogMsgHR(LastError, (wchar_t *)L"rt/CRtSend", 0xA5u);
    v5 = 170;
    v4 = -1072824272;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18001ac3c  mov     [rsp+arg_0], rbx
0x18001ac41  mov     [rsp+arg_8], rsi
0x18001ac46  push    rdi
0x18001ac47  sub     rsp, 30h
0x18001ac4b  mov     rdi, rcx
0x18001ac4e  mov     rsi, rdx
0x18001ac51  mov     rcx, [rcx+2E8h]
0x18001ac58  mov     rax, [rcx]
0x18001ac5b  mov     rax, [rax+8]
0x18001ac5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac64  mov     ebx, eax
0x18001ac66  test    eax, eax
0x18001ac68  jns     short loc_18001AC82
0x18001ac6a  mov     r8d, 0A0h; unsigned __int16
0x18001ac70  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x18001ac77  mov     ecx, ebx; int
0x18001ac79  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001ac7e  mov     eax, ebx
0x18001ac80  jmp     short loc_18001AD01
0x18001ac82  mov     rcx, [rdi+100h]
0x18001ac89  call    cs:__imp_?MQSec_UpgradeHashAlgorithm@@YAXPEAI@Z; MQSec_UpgradeHashAlgorithm(uint *)
0x18001ac8f  mov     rax, [rdi+100h]
0x18001ac96  mov     rcx, [rdi+2E8h]
0x18001ac9d  mov     ebx, [rax]
0x18001ac9f  mov     rax, [rcx]
0x18001aca2  mov     rax, [rax+10h]
0x18001aca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acab  xor     r9d, r9d; dwFlags
0x18001acae  mov     [rsp+38h+phHash], rsi; phHash
0x18001acb3  xor     r8d, r8d; hKey
0x18001acb6  mov     edx, ebx; Algid
0x18001acb8  mov     rcx, rax; hProv
0x18001acbb  call    cs:__imp_CryptCreateHash
0x18001acc1  test    eax, eax
0x18001acc3  jnz     short loc_18001ACFF
0x18001acc5  call    cs:__imp_GetLastError
0x18001accb  test    eax, eax
0x18001accd  jle     short loc_18001ACD9
0x18001accf  movzx   eax, ax
0x18001acd2  or      eax, 80070000h
0x18001acd7  test    eax, eax
0x18001acd9  jns     short loc_18001ACEF
0x18001acdb  mov     r8d, 0A5h; unsigned __int16
0x18001ace1  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x18001ace8  mov     ecx, eax; int
0x18001acea  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001acef  mov     r8d, 0AAh
0x18001acf5  mov     ebx, 0C00E0030h
0x18001acfa  jmp     loc_18001AC70
0x18001acff  xor     eax, eax
0x18001ad01  mov     rbx, [rsp+38h+arg_0]
0x18001ad06  mov     rsi, [rsp+38h+arg_8]
0x18001ad0b  add     rsp, 30h
0x18001ad0f  pop     rdi
0x18001ad10  retn
```

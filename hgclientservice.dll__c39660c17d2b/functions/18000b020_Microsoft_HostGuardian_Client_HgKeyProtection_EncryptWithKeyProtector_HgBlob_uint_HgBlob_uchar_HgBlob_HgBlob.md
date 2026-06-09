# Microsoft::HostGuardian::Client::HgKeyProtection::EncryptWithKeyProtector(HgBlob *,uint,HgBlob *,uchar,HgBlob *,HgBlob *)

- ea: `0x18000b020`
- end: `0x18000b0cd`
- name: `?EncryptWithKeyProtector@HgKeyProtection@Client@HostGuardian@Microsoft@@UEAAJPEAUHgBlob@@I0E00@Z`
- size: `173`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::HgKeyProtection *this, struct HgBlob *, unsigned int, struct HgBlob *, unsigned __int8, struct HgBlob *, struct HgBlob *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800064b4`
- `0x18000b020`
- `0x18000d190`

## string_xrefs

- `0x18000b0b4`: `servercommon\base\securehostingservice\common\service\lib\hgkeyprotection.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgKeyProtection::EncryptWithKeyProtector(
        Microsoft::HostGuardian::Client::HgKeyProtection *this,
        struct HgBlob *a2,
        unsigned int a3,
        struct HgBlob *a4,
        unsigned __int8 a5,
        struct HgBlob *a6,
        struct HgBlob *a7)
{
  const char *v7; // r9
  __int64 result; // rax
  wil *v9; // rcx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a2 && *(_DWORD *)a2 && *((_QWORD *)a2 + 1) && a4 && *(_DWORD *)a4 && *((_QWORD *)a4 + 1) && a6 && a7 )
  {
    try
    {
      *(_OWORD *)a7 = 0;
      *(_OWORD *)a6 = 0;
      Microsoft::HostGuardian::Client::HgServiceController::EncryptWithKeyProtector(
        *((Microsoft::HostGuardian::Client::HgServiceController **)g_service + 24),
        a2,
        a3,
        a4,
        a5 == 1,
        a6,
        a7);
      result = 0;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x80,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgkeyprotection.cpp",
        v7);
      if ( *(_DWORD *)a6 && *((_QWORD *)a6 + 1) )
      {
        CoTaskMemFree(*((LPVOID *)a6 + 1));
        *((_QWORD *)a6 + 1) = 0;
        *(_DWORD *)a6 = 0;
      }
      if ( *(_DWORD *)a7 )
      {
        if ( *((_QWORD *)a7 + 1) )
        {
          CoTaskMemFree(*((LPVOID *)a7 + 1));
          *((_QWORD *)a7 + 1) = 0;
          *(_DWORD *)a7 = 0;
        }
      }
      return (unsigned int)wil::ResultFromCaughtException(v9);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgkeyprotection.cpp",
      (const char *)0x80070057LL,
      v10);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000b020  push    rbx
0x18000b022  sub     rsp, 40h
0x18000b026  mov     r10d, r8d
0x18000b029  xor     eax, eax
0x18000b02b  test    rdx, rdx
0x18000b02e  jz      short loc_18000B0A7
0x18000b030  cmp     [rdx], eax
0x18000b032  jbe     short loc_18000B0A7
0x18000b034  cmp     [rdx+8], rax
0x18000b038  jz      short loc_18000B0A7
0x18000b03a  test    r9, r9
0x18000b03d  jz      short loc_18000B0A7
0x18000b03f  cmp     [r9], eax
0x18000b042  jbe     short loc_18000B0A7
0x18000b044  cmp     [r9+8], rax
0x18000b048  jz      short loc_18000B0A7
0x18000b04a  mov     rcx, [rsp+48h+arg_28]
0x18000b04f  test    rcx, rcx
0x18000b052  jz      short loc_18000B0A7
0x18000b054  mov     r8, [rsp+48h+arg_30]
0x18000b05c  test    r8, r8
0x18000b05f  jz      short loc_18000B0A7
0x18000b061  xorps   xmm0, xmm0
0x18000b064  movdqu  xmmword ptr [r8], xmm0
0x18000b069  xorps   xmm1, xmm1
0x18000b06c  movdqu  xmmword ptr [rcx], xmm1
0x18000b070  cmp     [rsp+48h+arg_20], 1
0x18000b075  setz    al
0x18000b078  mov     [rsp+48h+var_18], r8; struct HgBlob *
0x18000b07d  mov     [rsp+48h+var_20], rcx; struct HgBlob *
0x18000b082  mov     [rsp+48h+var_28], al; bool
0x18000b086  mov     r8d, r10d; unsigned int
0x18000b089  mov     rcx, cs:?g_service@@3PEAVHgService@Client@HostGuardian@Microsoft@@EA; Microsoft::HostGuardian::Client::HgService * g_service
0x18000b090  mov     rcx, [rcx+0C0h]; this
0x18000b097  call    ?EncryptWithKeyProtector@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXPEAUHgBlob@@I0_N00@Z; Microsoft::HostGuardian::Client::HgServiceController::EncryptWithKeyProtector(HgBlob *,uint,HgBlob *,bool,HgBlob *,HgBlob *)
0x18000b09c  nop
0x18000b09d  xor     eax, eax
0x18000b09f  jmp     short loc_18000B0C7
0x18000b0a1  mov     eax, [rsp+48h+arg_8]
0x18000b0a5  jmp     short loc_18000B0C7
0x18000b0a7  mov     rcx, [rsp+48h]; this
0x18000b0ac  mov     ebx, 80070057h
0x18000b0b1  mov     r9d, ebx; char *
0x18000b0b4  lea     r8, aServercommonBa_6; "servercommon\\base\\securehostingservic"...
0x18000b0bb  mov     edx, 6Eh ; 'n'; void *
0x18000b0c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b0c5  mov     eax, ebx
0x18000b0c7  add     rsp, 40h
0x18000b0cb  pop     rbx
0x18000b0cc  retn
```

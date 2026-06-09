# Microsoft::HostGuardian::Client::HgKeyProtection::DecryptWithKeyProtector(HgBlob *,HgBlob *,HgBlob *)

- ea: `0x18000af90`
- end: `0x18000b00c`
- name: `?DecryptWithKeyProtector@HgKeyProtection@Client@HostGuardian@Microsoft@@UEAAJPEAUHgBlob@@00@Z`
- size: `124`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::HgKeyProtection *this, struct HgBlob *, struct HgBlob *, struct HgBlob *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800064b4`
- `0x18000af90`
- `0x18000d0b8`

## string_xrefs

- `0x18000aff3`: `servercommon\base\securehostingservice\common\service\lib\hgkeyprotection.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgKeyProtection::DecryptWithKeyProtector(
        Microsoft::HostGuardian::Client::HgKeyProtection *this,
        struct HgBlob *a2,
        struct HgBlob *a3,
        struct HgBlob *a4)
{
  const char *v4; // r9
  __int64 result; // rax
  wil *v6; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 && *(_DWORD *)a2 && *((_QWORD *)a2 + 1) && a3 && *(_DWORD *)a3 && *((_QWORD *)a3 + 1) && a4 )
  {
    try
    {
      *(_OWORD *)a4 = 0;
      Microsoft::HostGuardian::Client::HgServiceController::DecryptWithKeyProtector(
        *((Microsoft::HostGuardian::Client::HgServiceController **)g_service + 24),
        a2,
        a3,
        a4);
      result = 0;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xAE,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgkeyprotection.cpp",
        v4);
      if ( *(_DWORD *)a4 )
      {
        if ( *((_QWORD *)a4 + 1) )
        {
          CoTaskMemFree(*((LPVOID *)a4 + 1));
          *((_QWORD *)a4 + 1) = 0;
          *(_DWORD *)a4 = 0;
        }
      }
      return (unsigned int)wil::ResultFromCaughtException(v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgkeyprotection.cpp",
      (const char *)0x80070057LL,
      v7);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000af90  mov     [rsp+arg_18], r9
0x18000af95  push    rbx; int
0x18000af96  sub     rsp, 20h
0x18000af9a  xor     eax, eax
0x18000af9c  test    rdx, rdx
0x18000af9f  jz      short loc_18000AFE6
0x18000afa1  cmp     [rdx], eax
0x18000afa3  jbe     short loc_18000AFE6
0x18000afa5  cmp     [rdx+8], rax
0x18000afa9  jz      short loc_18000AFE6
0x18000afab  test    r8, r8
0x18000afae  jz      short loc_18000AFE6
0x18000afb0  cmp     [r8], eax
0x18000afb3  jbe     short loc_18000AFE6
0x18000afb5  cmp     [r8+8], rax
0x18000afb9  jz      short loc_18000AFE6
0x18000afbb  test    r9, r9
0x18000afbe  jz      short loc_18000AFE6
0x18000afc0  xorps   xmm0, xmm0
0x18000afc3  movdqu  xmmword ptr [r9], xmm0
0x18000afc8  mov     rcx, cs:?g_service@@3PEAVHgService@Client@HostGuardian@Microsoft@@EA; Microsoft::HostGuardian::Client::HgService * g_service
0x18000afcf  mov     rcx, [rcx+0C0h]; this
0x18000afd6  call    ?DecryptWithKeyProtector@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXPEAUHgBlob@@00@Z; Microsoft::HostGuardian::Client::HgServiceController::DecryptWithKeyProtector(HgBlob *,HgBlob *,HgBlob *)
0x18000afdb  nop
0x18000afdc  xor     eax, eax
0x18000afde  jmp     short loc_18000B006
0x18000afe0  mov     eax, [rsp+28h+arg_8]
0x18000afe4  jmp     short loc_18000B006
0x18000afe6  mov     rcx, [rsp+28h]; this
0x18000afeb  mov     ebx, 80070057h
0x18000aff0  mov     r9d, ebx; char *
0x18000aff3  lea     r8, aServercommonBa_6; "servercommon\\base\\securehostingservic"...
0x18000affa  mov     edx, 0A0h; void *
0x18000afff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b004  mov     eax, ebx
0x18000b006  add     rsp, 20h
0x18000b00a  pop     rbx
0x18000b00b  retn
```

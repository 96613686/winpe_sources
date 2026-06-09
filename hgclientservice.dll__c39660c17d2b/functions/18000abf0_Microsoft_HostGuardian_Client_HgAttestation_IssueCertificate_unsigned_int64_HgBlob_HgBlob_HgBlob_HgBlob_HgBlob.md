# Microsoft::HostGuardian::Client::HgAttestation::IssueCertificate(unsigned __int64,HgBlob *,HgBlob *,HgBlob *,HgBlob *,HgBlob *)

- ea: `0x18000abf0`
- end: `0x18000acb4`
- name: `?IssueCertificate@HgAttestation@Client@HostGuardian@Microsoft@@UEAAJ_KPEAUHgBlob@@1111@Z`
- size: `196`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::HgAttestation *__hidden this, unsigned __int64, struct HgBlob *, struct HgBlob *, struct HgBlob *, struct HgBlob *, struct HgBlob *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800064b4`
- `0x18000abf0`
- `0x18000d348`

## string_xrefs

- `0x18000ac9b`: `servercommon\base\securehostingservice\common\service\lib\hgattestation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgAttestation::IssueCertificate(
        Microsoft::HostGuardian::Client::HgAttestation *this,
        unsigned __int64 a2,
        struct HgBlob *a3,
        struct HgBlob *a4,
        struct HgBlob *a5,
        struct HgBlob *a6,
        struct HgBlob *a7)
{
  const char *v7; // r9
  __int64 result; // rax
  wil *v9; // rcx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a3
    && *(_DWORD *)a3
    && *((_QWORD *)a3 + 1)
    && a4
    && *(_DWORD *)a4
    && *((_QWORD *)a4 + 1)
    && a5
    && *(_DWORD *)a5
    && *((_QWORD *)a5 + 1)
    && a6
    && a7 )
  {
    try
    {
      *(_OWORD *)a6 = 0;
      *(_OWORD *)a7 = 0;
      Microsoft::HostGuardian::Client::HgServiceController::IssueCertificate(
        *((Microsoft::HostGuardian::Client::HgServiceController **)g_service + 24),
        a2,
        a3,
        a4,
        a5,
        a6,
        a7);
      result = 0;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x6C,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgattestation.cpp",
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
      (void *)0x60,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgattestation.cpp",
      (const char *)0x80070057LL,
      v10);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000abf0  push    rbx
0x18000abf2  sub     rsp, 40h
0x18000abf6  mov     r10, rdx
0x18000abf9  xor     r11d, r11d
0x18000abfc  test    r8, r8
0x18000abff  jz      loc_18000AC8E
0x18000ac05  cmp     [r8], r11d
0x18000ac08  jbe     loc_18000AC8E
0x18000ac0e  cmp     [r8+8], r11
0x18000ac12  jz      short loc_18000AC8E
0x18000ac14  test    r9, r9
0x18000ac17  jz      short loc_18000AC8E
0x18000ac19  cmp     [r9], r11d
0x18000ac1c  jbe     short loc_18000AC8E
0x18000ac1e  cmp     [r9+8], r11
0x18000ac22  jz      short loc_18000AC8E
0x18000ac24  mov     rax, [rsp+48h+arg_20]
0x18000ac29  test    rax, rax
0x18000ac2c  jz      short loc_18000AC8E
0x18000ac2e  cmp     [rax], r11d
0x18000ac31  jbe     short loc_18000AC8E
0x18000ac33  cmp     [rax+8], r11
0x18000ac37  jz      short loc_18000AC8E
0x18000ac39  mov     rcx, [rsp+48h+arg_28]
0x18000ac3e  test    rcx, rcx
0x18000ac41  jz      short loc_18000AC8E
0x18000ac43  mov     rdx, [rsp+48h+arg_30]
0x18000ac4b  test    rdx, rdx
0x18000ac4e  jz      short loc_18000AC8E
0x18000ac50  xorps   xmm0, xmm0
0x18000ac53  movdqu  xmmword ptr [rcx], xmm0
0x18000ac57  xorps   xmm1, xmm1
0x18000ac5a  movdqu  xmmword ptr [rdx], xmm1
0x18000ac5e  mov     [rsp+48h+var_18], rdx; struct HgBlob *
0x18000ac63  mov     [rsp+48h+var_20], rcx; struct HgBlob *
0x18000ac68  mov     [rsp+48h+var_28], rax; struct HgBlob *
0x18000ac6d  mov     rdx, r10; unsigned __int64
0x18000ac70  mov     rcx, cs:?g_service@@3PEAVHgService@Client@HostGuardian@Microsoft@@EA; Microsoft::HostGuardian::Client::HgService * g_service
0x18000ac77  mov     rcx, [rcx+0C0h]; this
0x18000ac7e  call    ?IssueCertificate@HgServiceController@Client@HostGuardian@Microsoft@@QEAAX_KPEAUHgBlob@@1111@Z; Microsoft::HostGuardian::Client::HgServiceController::IssueCertificate(unsigned __int64,HgBlob *,HgBlob *,HgBlob *,HgBlob *,HgBlob *)
0x18000ac83  nop
0x18000ac84  xor     eax, eax
0x18000ac86  jmp     short loc_18000ACAE
0x18000ac88  mov     eax, [rsp+48h+arg_10]
0x18000ac8c  jmp     short loc_18000ACAE
0x18000ac8e  mov     rcx, [rsp+48h]; this
0x18000ac93  mov     ebx, 80070057h
0x18000ac98  mov     r9d, ebx; char *
0x18000ac9b  lea     r8, aServercommonBa_5; "servercommon\\base\\securehostingservic"...
0x18000aca2  mov     edx, 60h ; '`'; void *
0x18000aca7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000acac  mov     eax, ebx
0x18000acae  add     rsp, 40h
0x18000acb2  pop     rbx
0x18000acb3  retn
```

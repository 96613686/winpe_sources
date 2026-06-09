# AES_PROVIDER_ENTRY::CheckAccessInternal(void)

- ea: `0x180048f30`
- end: `0x1800491a7`
- name: `?CheckAccessInternal@AES_PROVIDER_ENTRY@@UEAAJXZ`
- size: `631`
- prototype: `__int64 __fastcall(AES_PROVIDER_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180048f30`
- `0x180059bea`
- `0x180059c30`
- `0x180059cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004913a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004913a`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180049045`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800490a9`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180049045`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800490a9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004916f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180049179`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004916f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180049179`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180049184`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180049184`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180049108`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180049115`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180049108`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180049115`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049006`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049038`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049069`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004909b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800490cd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800490fb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049006`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049038`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049069`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004909b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800490cd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800490fb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180048fbb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180048fe1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180048fbb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180048fe1`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180048f7d`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180048f7d`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180048f88`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004905a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800490be`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180048f88`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004905a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800490be`
- `CRYPTSP!CryptAcquireContextW` at `0x180049130`
- `CRYPTSP!CryptAcquireContextW` at `0x180049130`
- `CRYPTSP!CryptReleaseContext` at `0x18004915b`
- `CRYPTSP!CryptReleaseContext` at `0x18004915b`
- `CRYPTSP!CryptGetProvParam` at `0x180049025`
- `CRYPTSP!CryptGetProvParam` at `0x180049088`
- `CRYPTSP!CryptGetProvParam` at `0x1800490ec`
- `CRYPTSP!CryptGetProvParam` at `0x180049025`
- `CRYPTSP!CryptGetProvParam` at `0x180049088`
- `CRYPTSP!CryptGetProvParam` at `0x1800490ec`

## pseudocode

```c
__int64 __fastcall AES_PROVIDER_ENTRY::CheckAccessInternal(AES_PROVIDER_ENTRY *this)
{
  bool v2; // zf
  signed int v3; // esi
  BYTE *Ptr; // rax
  const char *v5; // rax
  BYTE *v6; // rax
  const char *v7; // rax
  BYTE *v8; // rax
  DWORD dwFlags; // edi
  const WCHAR *Str; // rbx
  const WCHAR *v11; // rax
  signed int LastError; // eax
  DWORD pdwDataLen; // [rsp+30h] [rbp-D0h] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v16[48]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[56]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 v19[4096]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v20[256]; // [rsp+10E0h] [rbp+FE0h] BYREF
  unsigned __int16 v21[256]; // [rsp+12E0h] [rbp+11E0h] BYREF

  memset_0(v19, 0, sizeof(v19));
  BUFFER::BUFFER((BUFFER *)v16, v19, 0x1000u);
  pdwDataLen = BUFFER::QuerySize((BUFFER *)v16);
  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v18, v20, 0x100u);
  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v17, v21, 0x100u);
  v2 = *((_QWORD *)this + 5) == 0;
  phProv = 0;
  if ( v2 )
  {
    v3 = -2146893802;
  }
  else
  {
    Ptr = (BYTE *)BUFFER::QueryPtr((BUFFER *)v16);
    if ( !CryptGetProvParam(*((_QWORD *)this + 5), 6u, Ptr, &pdwDataLen, 0) )
      goto LABEL_16;
    v5 = (const char *)BUFFER::QueryPtr((BUFFER *)v16);
    v3 = STRU::CopyA((STRU *)v18, v5);
    if ( v3 >= 0 )
    {
      pdwDataLen = BUFFER::QuerySize((BUFFER *)v16);
      v6 = (BYTE *)BUFFER::QueryPtr((BUFFER *)v16);
      if ( !CryptGetProvParam(*((_QWORD *)this + 5), 4u, v6, &pdwDataLen, 0)
        || (v7 = (const char *)BUFFER::QueryPtr((BUFFER *)v16), v3 = STRU::CopyA((STRU *)v17, v7), v3 >= 0)
        && ((pdwDataLen = BUFFER::QuerySize((BUFFER *)v16),
             v8 = (BYTE *)BUFFER::QueryPtr((BUFFER *)v16),
             !CryptGetProvParam(*((_QWORD *)this + 5), 0x1Bu, v8, &pdwDataLen, 0))
         || (dwFlags = *(_DWORD *)BUFFER::QueryPtr((BUFFER *)v16),
             Str = STRU::QueryStr((STRU *)v17),
             v11 = STRU::QueryStr((STRU *)v18),
             !CryptAcquireContextW(&phProv, v11, Str, 0x18u, dwFlags))) )
      {
LABEL_16:
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    if ( phProv )
    {
      CryptReleaseContext(phProv, 0);
      phProv = 0;
    }
  }
  STRU::~STRU((STRU *)v17);
  STRU::~STRU((STRU *)v18);
  BUFFER::~BUFFER((BUFFER *)v16);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180048f30  push    rbp
0x180048f32  push    rbx
0x180048f33  push    rsi
0x180048f34  push    rdi
0x180048f35  lea     rbp, [rsp-13F8h]
0x180048f3d  mov     eax, 14F8h
0x180048f42  call    _alloca_probe
0x180048f47  sub     rsp, rax
0x180048f4a  mov     rax, cs:__security_cookie
0x180048f51  xor     rax, rsp
0x180048f54  mov     [rbp+1410h+var_30], rax
0x180048f5b  mov     rbx, rcx
0x180048f5e  mov     edi, 1000h
0x180048f63  mov     r8d, edi; Size
0x180048f66  lea     rcx, [rbp+1410h+var_1430]; void *
0x180048f6a  xor     edx, edx; Val
0x180048f6c  call    memset_0
0x180048f71  mov     r8d, edi
0x180048f74  lea     rdx, [rbp+1410h+var_1430]
0x180048f78  lea     rcx, [rsp+1510h+var_14D0]
0x180048f7d  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180048f83  lea     rcx, [rsp+1510h+var_14D0]
0x180048f88  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180048f8e  mov     esi, 200h
0x180048f93  lea     rcx, [rbp+1410h+var_430]; void *
0x180048f9a  mov     r8d, esi; Size
0x180048f9d  mov     [rsp+1510h+pdwDataLen], eax
0x180048fa1  xor     edx, edx; Val
0x180048fa3  call    memset_0
0x180048fa8  mov     edi, 100h
0x180048fad  lea     rdx, [rbp+1410h+var_430]
0x180048fb4  mov     r8d, edi
0x180048fb7  lea     rcx, [rbp+1410h+var_1468]
0x180048fbb  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180048fc1  mov     r8d, esi; Size
0x180048fc4  lea     rcx, [rbp+1410h+var_230]; void *
0x180048fcb  xor     edx, edx; Val
0x180048fcd  call    memset_0
0x180048fd2  mov     r8d, edi
0x180048fd5  lea     rdx, [rbp+1410h+var_230]
0x180048fdc  lea     rcx, [rsp+1510h+var_14A0]
0x180048fe1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180048fe7  cmp     qword ptr [rbx+28h], 0
0x180048fec  mov     [rsp+1510h+phProv], 0
0x180048ff5  jnz     short loc_180049001
0x180048ff7  mov     esi, 80090016h
0x180048ffc  jmp     loc_18004916A
0x180049001  lea     rcx, [rsp+1510h+var_14D0]
0x180049006  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004900c  mov     rcx, [rbx+28h]; hProv
0x180049010  lea     r9, [rsp+1510h+pdwDataLen]; pdwDataLen
0x180049015  mov     r8, rax; pbData
0x180049018  mov     [rsp+1510h+dwFlags], 0; dwFlags
0x180049020  mov     edx, 6; dwParam
0x180049025  call    cs:__imp_CryptGetProvParam
0x18004902b  test    eax, eax
0x18004902d  jz      loc_18004913A
0x180049033  lea     rcx, [rsp+1510h+var_14D0]
0x180049038  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004903e  mov     rdx, rax
0x180049041  lea     rcx, [rbp+1410h+var_1468]
0x180049045  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18004904b  mov     esi, eax
0x18004904d  test    eax, eax
0x18004904f  js      loc_18004914F
0x180049055  lea     rcx, [rsp+1510h+var_14D0]
0x18004905a  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180049060  lea     rcx, [rsp+1510h+var_14D0]
0x180049065  mov     [rsp+1510h+pdwDataLen], eax
0x180049069  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004906f  mov     rcx, [rbx+28h]; hProv
0x180049073  lea     r9, [rsp+1510h+pdwDataLen]; pdwDataLen
0x180049078  mov     r8, rax; pbData
0x18004907b  mov     [rsp+1510h+dwFlags], 0; dwFlags
0x180049083  mov     edx, 4; dwParam
0x180049088  call    cs:__imp_CryptGetProvParam
0x18004908e  test    eax, eax
0x180049090  jz      loc_18004913A
0x180049096  lea     rcx, [rsp+1510h+var_14D0]
0x18004909b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800490a1  mov     rdx, rax
0x1800490a4  lea     rcx, [rsp+1510h+var_14A0]
0x1800490a9  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x1800490af  mov     esi, eax
0x1800490b1  test    eax, eax
0x1800490b3  js      loc_18004914F
0x1800490b9  lea     rcx, [rsp+1510h+var_14D0]
0x1800490be  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800490c4  lea     rcx, [rsp+1510h+var_14D0]
0x1800490c9  mov     [rsp+1510h+pdwDataLen], eax
0x1800490cd  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800490d3  mov     rcx, [rbx+28h]; hProv
0x1800490d7  lea     r9, [rsp+1510h+pdwDataLen]; pdwDataLen
0x1800490dc  mov     r8, rax; pbData
0x1800490df  mov     [rsp+1510h+dwFlags], 0; dwFlags
0x1800490e7  mov     edx, 1Bh; dwParam
0x1800490ec  call    cs:__imp_CryptGetProvParam
0x1800490f2  test    eax, eax
0x1800490f4  jz      short loc_18004913A
0x1800490f6  lea     rcx, [rsp+1510h+var_14D0]
0x1800490fb  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180049101  lea     rcx, [rsp+1510h+var_14A0]
0x180049106  mov     edi, [rax]
0x180049108  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004910e  lea     rcx, [rbp+1410h+var_1468]
0x180049112  mov     rbx, rax
0x180049115  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004911b  mov     r9d, 18h; dwProvType
0x180049121  mov     [rsp+1510h+dwFlags], edi; dwFlags
0x180049125  mov     rdx, rax; szContainer
0x180049128  lea     rcx, [rsp+1510h+phProv]; phProv
0x18004912d  mov     r8, rbx; szProvider
0x180049130  call    cs:__imp_CryptAcquireContextW
0x180049136  test    eax, eax
0x180049138  jnz     short loc_18004914F
0x18004913a  call    cs:__imp_GetLastError
0x180049140  mov     esi, eax
0x180049142  test    eax, eax
0x180049144  jle     short loc_18004914F
0x180049146  movzx   esi, ax
0x180049149  or      esi, 80070000h
0x18004914f  mov     rcx, [rsp+1510h+phProv]; hProv
0x180049154  test    rcx, rcx
0x180049157  jz      short loc_18004916A
0x180049159  xor     edx, edx; dwFlags
0x18004915b  call    cs:__imp_CryptReleaseContext
0x180049161  mov     [rsp+1510h+phProv], 0
0x18004916a  lea     rcx, [rsp+1510h+var_14A0]
0x18004916f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180049175  lea     rcx, [rbp+1410h+var_1468]
0x180049179  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004917f  lea     rcx, [rsp+1510h+var_14D0]
0x180049184  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004918a  mov     eax, esi
0x18004918c  mov     rcx, [rbp+1410h+var_30]
0x180049193  xor     rcx, rsp; StackCookie
0x180049196  call    __security_check_cookie
0x18004919b  add     rsp, 14F8h
0x1800491a2  pop     rdi
0x1800491a3  pop     rsi
0x1800491a4  pop     rbx
0x1800491a5  pop     rbp
0x1800491a6  retn
```

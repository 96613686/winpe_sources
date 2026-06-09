# FTP_USER::Initialize(USER_SESSION *,TOKEN_CACHE_ENTRY *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x180015928`
- end: `0x180015b4e`
- name: `?Initialize@FTP_USER@@QEAAJPEAVUSER_SESSION@@PEAVTOKEN_CACHE_ENTRY@@PEBG22H@Z`
- size: `550`
- prototype: `__int64 __fastcall(FTP_USER *this, struct USER_SESSION *, struct TOKEN_CACHE_ENTRY *, const unsigned __int16 *, const unsigned __int16 *, wchar_t *String1, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001af2c`
- `0x18001b3ac`
- `0x18001b90c`
- `0x18001ccec`

## callees

- `0x180015928`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800159d1`
- `msvcrt!_wcsnicmp` at `0x1800159d1`
- `msvcrt!wcschr` at `0x180015a11`
- `msvcrt!wcschr` at `0x180015a11`
- `msvcrt!_wcsicmp` at `0x18001597c`
- `msvcrt!_wcsicmp` at `0x18001597c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015994`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800159f4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015a2d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015a6e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015a8f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015afe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015b15`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015994`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800159f4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015a2d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015a6e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015a8f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015afe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180015b15`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180015a4e`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180015a4e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180015ab4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180015aca`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180015aeb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180015ab4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180015aca`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180015aeb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_USER::Initialize(
        FTP_USER *this,
        struct USER_SESSION *a2,
        struct TOKEN_CACHE_ENTRY *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        wchar_t *String1,
        int a7)
{
  __int64 v11; // rax
  __int64 v12; // rsi
  int v13; // ecx
  const unsigned __int16 *v14; // rdx
  const wchar_t *v15; // rax
  wchar_t *v16; // rax
  STRU *v17; // rcx
  __int64 v18; // rsi
  const unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // rax

  v11 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 152LL))(g_pFtpServer);
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(v11 + 2 * v12) );
  if ( _wcsicmp(String1, L"AnonymousAuth") )
  {
    v15 = (const wchar_t *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 152LL))(g_pFtpServer);
    if ( _wcsnicmp(a4, v15, (unsigned int)v12) || a4[(unsigned int)v12] != 92 )
    {
      v16 = wcschr(a4, 0x5Cu);
      v17 = (FTP_USER *)((char *)this + 208);
      if ( v16 )
      {
        v18 = v16 - a4;
        v13 = STRU::Copy(v17, a4, v18);
        if ( v13 < 0 )
          return (unsigned int)v13;
        v14 = &a4[(unsigned int)v18 + 1];
      }
      else
      {
        v13 = STRU::Copy(v17, L"LocalUser");
        if ( v13 < 0 )
          return (unsigned int)v13;
        v14 = a4;
      }
    }
    else
    {
      v13 = STRU::Copy((FTP_USER *)((char *)this + 208), L"LocalUser");
      if ( v13 < 0 )
        return (unsigned int)v13;
      v14 = &a4[(unsigned int)v12 + 1];
    }
  }
  else
  {
    v13 = STRU::Copy((FTP_USER *)((char *)this + 208), L"LocalUser");
    if ( v13 < 0 )
      return (unsigned int)v13;
    v14 = L"Public";
  }
  v13 = STRU::Copy((FTP_USER *)((char *)this + 152), v14);
  if ( v13 >= 0 )
  {
    v13 = STRU::Copy((FTP_USER *)((char *)this + 264), L"/");
    if ( v13 >= 0 )
    {
      v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(FTP_USER *))(*(_QWORD *)this + 96LL))(this);
      v13 = STRU::Append((FTP_USER *)((char *)this + 264), v19);
      if ( v13 >= 0 )
      {
        v13 = STRU::Append((FTP_USER *)((char *)this + 264), L"/");
        if ( v13 >= 0 )
        {
          v20 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(FTP_USER *))(*(_QWORD *)this + 88LL))(this);
          v13 = STRU::Append((FTP_USER *)((char *)this + 264), v20);
          if ( v13 >= 0 )
          {
            v13 = STRU::Copy((FTP_USER *)((char *)this + 24), a4);
            if ( v13 >= 0 )
            {
              v13 = STRU::Copy((FTP_USER *)((char *)this + 80), &WideCharStr);
              if ( v13 >= 0 )
              {
                *((_DWORD *)this + 36) = a7;
                *((_QWORD *)this + 17) = String1;
                *((_QWORD *)this + 1) = a2;
                *((_QWORD *)this + 2) = a3;
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180015928  push    rbx
0x18001592a  push    rbp
0x18001592b  push    rsi
0x18001592c  push    rdi
0x18001592d  push    r12
0x18001592f  push    r14
0x180015931  push    r15
0x180015933  sub     rsp, 20h
0x180015937  mov     rbx, rcx
0x18001593a  mov     rdi, r9
0x18001593d  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180015944  mov     r14, r8
0x180015947  mov     r15, rdx
0x18001594a  mov     rax, [rcx]
0x18001594d  mov     rax, [rax+98h]
0x180015954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015959  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001595d  xor     r12d, r12d
0x180015960  inc     rsi
0x180015963  cmp     [rax+rsi*2], r12w
0x180015968  jnz     short loc_180015960
0x18001596a  mov     rbp, [rsp+58h+String1]
0x180015972  lea     rdx, aAnonymousauth; "AnonymousAuth"
0x180015979  mov     rcx, rbp; String1
0x18001597c  call    cs:__imp__wcsicmp
0x180015982  test    eax, eax
0x180015984  jnz     short loc_1800159B0
0x180015986  lea     rcx, [rbx+0D0h]
0x18001598d  lea     rdx, aLocaluser; "LocalUser"
0x180015994  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001599a  mov     ecx, eax
0x18001599c  test    eax, eax
0x18001599e  js      loc_180015B3D
0x1800159a4  lea     rdx, aPublic; "Public"
0x1800159ab  jmp     loc_180015A67
0x1800159b0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800159b7  mov     esi, esi
0x1800159b9  mov     rax, [rcx]
0x1800159bc  mov     rax, [rax+98h]
0x1800159c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159c8  mov     rdx, rax; String2
0x1800159cb  mov     r8d, esi; MaxCount
0x1800159ce  mov     rcx, rdi; String1
0x1800159d1  call    cs:__imp__wcsnicmp
0x1800159d7  mov     edx, 5Ch ; '\'; Ch
0x1800159dc  test    eax, eax
0x1800159de  jnz     short loc_180015A0E
0x1800159e0  cmp     [rdi+rsi*2], dx
0x1800159e4  jnz     short loc_180015A0E
0x1800159e6  lea     rcx, [rbx+0D0h]
0x1800159ed  lea     rdx, aLocaluser; "LocalUser"
0x1800159f4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800159fa  mov     ecx, eax
0x1800159fc  test    eax, eax
0x1800159fe  js      loc_180015B3D
0x180015a04  lea     rdx, [rdi+2]
0x180015a08  lea     rdx, [rdx+rsi*2]
0x180015a0c  jmp     short loc_180015A67
0x180015a0e  mov     rcx, rdi; Str
0x180015a11  call    cs:__imp_wcschr
0x180015a17  lea     rcx, [rbx+0D0h]
0x180015a1e  mov     rsi, rax
0x180015a21  test    rax, rax
0x180015a24  jnz     short loc_180015A42
0x180015a26  lea     rdx, aLocaluser; "LocalUser"
0x180015a2d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180015a33  mov     ecx, eax
0x180015a35  test    eax, eax
0x180015a37  js      loc_180015B3D
0x180015a3d  mov     rdx, rdi
0x180015a40  jmp     short loc_180015A67
0x180015a42  sub     rsi, rdi
0x180015a45  mov     rdx, rdi
0x180015a48  sar     rsi, 1
0x180015a4b  mov     r8d, esi
0x180015a4e  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180015a54  mov     ecx, eax
0x180015a56  test    eax, eax
0x180015a58  js      loc_180015B3D
0x180015a5e  mov     eax, esi
0x180015a60  inc     rax
0x180015a63  lea     rdx, [rdi+rax*2]
0x180015a67  lea     rcx, [rbx+98h]
0x180015a6e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180015a74  mov     ecx, eax
0x180015a76  test    eax, eax
0x180015a78  js      loc_180015B3D
0x180015a7e  lea     rsi, [rbx+108h]
0x180015a85  mov     rcx, rsi
0x180015a88  lea     rdx, asc_18004BD14; "/"
0x180015a8f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180015a95  mov     ecx, eax
0x180015a97  test    eax, eax
0x180015a99  js      loc_180015B3D
0x180015a9f  mov     rax, [rbx]
0x180015aa2  mov     rcx, rbx
0x180015aa5  mov     rax, [rax+60h]
0x180015aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aae  mov     rdx, rax
0x180015ab1  mov     rcx, rsi
0x180015ab4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180015aba  mov     ecx, eax
0x180015abc  test    eax, eax
0x180015abe  js      short loc_180015B3D
0x180015ac0  lea     rdx, asc_18004BD14; "/"
0x180015ac7  mov     rcx, rsi
0x180015aca  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180015ad0  mov     ecx, eax
0x180015ad2  test    eax, eax
0x180015ad4  js      short loc_180015B3D
0x180015ad6  mov     rax, [rbx]
0x180015ad9  mov     rcx, rbx
0x180015adc  mov     rax, [rax+58h]
0x180015ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ae5  mov     rdx, rax
0x180015ae8  mov     rcx, rsi
0x180015aeb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180015af1  mov     ecx, eax
0x180015af3  test    eax, eax
0x180015af5  js      short loc_180015B3D
0x180015af7  lea     rcx, [rbx+18h]
0x180015afb  mov     rdx, rdi
0x180015afe  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180015b04  mov     ecx, eax
0x180015b06  test    eax, eax
0x180015b08  js      short loc_180015B3D
0x180015b0a  lea     rcx, [rbx+50h]
0x180015b0e  lea     rdx, WideCharStr
0x180015b15  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180015b1b  mov     ecx, eax
0x180015b1d  test    eax, eax
0x180015b1f  js      short loc_180015B3D
0x180015b21  mov     eax, [rsp+58h+arg_30]
0x180015b28  mov     [rbx+90h], eax
0x180015b2e  mov     [rbx+88h], rbp
0x180015b35  mov     [rbx+8], r15
0x180015b39  mov     [rbx+10h], r14
0x180015b3d  mov     eax, ecx
0x180015b3f  add     rsp, 20h
0x180015b43  pop     r15
0x180015b45  pop     r14
0x180015b47  pop     r12
0x180015b49  pop     rdi
0x180015b4a  pop     rsi
0x180015b4b  pop     rbp
0x180015b4c  pop     rbx
0x180015b4d  retn
```

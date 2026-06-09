# CacheDirMonitorEntry::ActOnNotification(ulong,ulong)

- ea: `0x180008c10`
- end: `0x180008d53`
- name: `?ActOnNotification@CacheDirMonitorEntry@@EEAAHKK@Z`
- size: `323`
- prototype: `__int64 __fastcall(CacheDirMonitorEntry *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180008c10`
- `0x180008d60`
- `0x180019094`
- `0x18003439a`
- `0x1800343f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008cae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008cae`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008cbb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008cbb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008d13`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008d13`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008c61`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008c61`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180008c9b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180008c9b`

## pseudocode

```c
__int64 __fastcall CacheDirMonitorEntry::ActOnNotification(CacheDirMonitorEntry *this, int a2, int a3)
{
  unsigned int v6; // esi
  const unsigned __int16 *v7; // rbx
  __int64 v8; // r14
  int v9; // eax
  DWORD v10; // eax
  unsigned int v12; // edx
  unsigned int *v13; // rbp
  unsigned int v14; // edx
  unsigned __int16 *Str; // rax
  _BYTE v16[64]; // [rsp+20h] [rbp-278h] BYREF
  unsigned __int16 v17[264]; // [rsp+60h] [rbp-238h] BYREF

  memset_0(v17, 0, 0x208u);
  STRU::STRU((STRU *)v16, v17, 0x104u);
  v6 = 1;
  if ( a2 )
  {
    if ( a2 == 5 || (++*((_DWORD *)this + 30), *((_DWORD *)this + 30) > 3u) )
      v6 = 0;
  }
  else
  {
    *((_DWORD *)this + 30) = 0;
  }
  if ( a3 )
  {
    v7 = (const unsigned __int16 *)*((_QWORD *)this + 3);
    while ( v7 )
    {
      v8 = *(unsigned int *)v7;
      v9 = STRU::Copy((STRU *)v16, v7 + 6, *((_DWORD *)v7 + 2) >> 1);
      if ( v9 < 0 )
      {
        v10 = WIN32_FROM_HRESULT(v9);
        SetLastError(v10);
        v6 = 0;
        break;
      }
      v12 = *((_DWORD *)v7 + 1);
      v13 = (unsigned int *)v7;
      v7 = (const unsigned __int16 *)((char *)v7 + v8);
      v14 = v12 - 2;
      if ( !v14 || v14 - 1 < 2 )
      {
        Str = STRU::QueryStr((STRU *)v16);
        CacheDirMonitorEntry::FileChanged((const unsigned __int16 **)this, Str);
      }
      if ( v13 == (unsigned int *)v7 )
        break;
    }
  }
  else
  {
    CacheDirMonitorEntry::FileChanged((const unsigned __int16 **)this, (unsigned __int16 *)&dword_180039134);
  }
  STRU::~STRU((STRU *)v16);
  return v6;
}

```

## disassembly

```asm
0x180008c10  mov     [rsp+arg_8], rbx
0x180008c15  mov     [rsp+arg_10], rbp
0x180008c1a  push    rsi
0x180008c1b  push    rdi
0x180008c1c  push    r14
0x180008c1e  sub     rsp, 280h
0x180008c25  mov     rax, cs:__security_cookie
0x180008c2c  xor     rax, rsp
0x180008c2f  mov     [rsp+298h+var_28], rax
0x180008c37  mov     ebp, r8d
0x180008c3a  mov     ebx, edx
0x180008c3c  mov     rdi, rcx
0x180008c3f  xor     edx, edx; Val
0x180008c41  mov     r8d, 208h; Size
0x180008c47  lea     rcx, [rsp+298h+var_238]; void *
0x180008c4c  call    memset_0
0x180008c51  mov     r8d, 104h
0x180008c57  lea     rdx, [rsp+298h+var_238]
0x180008c5c  lea     rcx, [rsp+298h+var_278]
0x180008c61  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008c67  mov     esi, 1
0x180008c6c  test    ebx, ebx
0x180008c6e  jnz     loc_180008D26
0x180008c74  mov     [rdi+78h], ebx
0x180008c77  test    ebp, ebp
0x180008c79  jz      loc_180008D3F
0x180008c7f  mov     rbx, [rdi+18h]
0x180008c83  test    rbx, rbx
0x180008c86  jz      short loc_180008CB6
0x180008c88  mov     r8d, [rbx+8]
0x180008c8c  lea     rdx, [rbx+0Ch]
0x180008c90  mov     r14d, [rbx]
0x180008c93  lea     rcx, [rsp+298h+var_278]
0x180008c98  shr     r8d, 1
0x180008c9b  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180008ca1  test    eax, eax
0x180008ca3  jns     short loc_180008CEB
0x180008ca5  mov     ecx, eax; int
0x180008ca7  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180008cac  mov     ecx, eax; dwErrCode
0x180008cae  call    cs:__imp_SetLastError
0x180008cb4  xor     esi, esi
0x180008cb6  lea     rcx, [rsp+298h+var_278]
0x180008cbb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008cc1  mov     eax, esi
0x180008cc3  mov     rcx, [rsp+298h+var_28]
0x180008ccb  xor     rcx, rsp; StackCookie
0x180008cce  call    __security_check_cookie
0x180008cd3  lea     r11, [rsp+298h+var_18]
0x180008cdb  mov     rbx, [r11+28h]
0x180008cdf  mov     rbp, [r11+30h]
0x180008ce3  mov     rsp, r11
0x180008ce6  pop     r14
0x180008ce8  pop     rdi
0x180008ce9  pop     rsi
0x180008cea  retn
0x180008ceb  mov     edx, [rbx+4]
0x180008cee  mov     rbp, rbx
0x180008cf1  add     rbx, r14
0x180008cf4  sub     edx, 2
0x180008cf7  jz      short loc_180008D0E
0x180008cf9  sub     edx, 1
0x180008cfc  jz      short loc_180008D0E
0x180008cfe  cmp     edx, 1
0x180008d01  jz      short loc_180008D0E
0x180008d03  cmp     rbp, rbx
0x180008d06  jnz     loc_180008C83
0x180008d0c  jmp     short loc_180008CB6
0x180008d0e  lea     rcx, [rsp+298h+var_278]
0x180008d13  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008d19  mov     rdx, rax; unsigned __int16 *
0x180008d1c  mov     rcx, rdi; this
0x180008d1f  call    ?FileChanged@CacheDirMonitorEntry@@AEAAXPEAG@Z; CacheDirMonitorEntry::FileChanged(ushort *)
0x180008d24  jmp     short loc_180008D03
0x180008d26  cmp     ebx, 5
0x180008d29  jz      short loc_180008D38
0x180008d2b  add     [rdi+78h], esi
0x180008d2e  cmp     dword ptr [rdi+78h], 3
0x180008d32  jbe     loc_180008C77
0x180008d38  xor     esi, esi
0x180008d3a  jmp     loc_180008C77
0x180008d3f  lea     rdx, dword_180039134; unsigned __int16 *
0x180008d46  mov     rcx, rdi; this
0x180008d49  call    ?FileChanged@CacheDirMonitorEntry@@AEAAXPEAG@Z; CacheDirMonitorEntry::FileChanged(ushort *)
0x180008d4e  jmp     loc_180008CB6
```

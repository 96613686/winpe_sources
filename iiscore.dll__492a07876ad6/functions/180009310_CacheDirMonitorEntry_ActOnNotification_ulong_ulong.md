# CacheDirMonitorEntry::ActOnNotification(ulong,ulong)

- ea: `0x180009310`
- end: `0x180009472`
- name: `?ActOnNotification@CacheDirMonitorEntry@@EEAAHKK@Z`
- size: `354`
- prototype: `__int64 __fastcall(CacheDirMonitorEntry *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180009310`
- `0x180009480`
- `0x18001a64c`
- `0x18003773a`
- `0x180037790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093ba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800093cd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800093cd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000942c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000942c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009361`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009361`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800093a1`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800093a1`

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
    CacheDirMonitorEntry::FileChanged((const unsigned __int16 **)this, (unsigned __int16 *)&dword_18003C134);
  }
  STRU::~STRU((STRU *)v16);
  return v6;
}

```

## disassembly

```asm
0x180009310  mov     [rsp+arg_8], rbx
0x180009315  mov     [rsp+arg_10], rbp
0x18000931a  push    rsi
0x18000931b  push    rdi
0x18000931c  push    r14
0x18000931e  sub     rsp, 280h
0x180009325  mov     rax, cs:__security_cookie
0x18000932c  xor     rax, rsp
0x18000932f  mov     [rsp+298h+var_28], rax
0x180009337  mov     ebp, r8d
0x18000933a  mov     ebx, edx
0x18000933c  mov     rdi, rcx
0x18000933f  xor     edx, edx; Val
0x180009341  mov     r8d, 208h; Size
0x180009347  lea     rcx, [rsp+298h+var_238]; void *
0x18000934c  call    memset_0
0x180009351  mov     r8d, 104h
0x180009357  lea     rdx, [rsp+298h+var_238]
0x18000935c  lea     rcx, [rsp+298h+var_278]
0x180009361  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009368  nop     dword ptr [rax+rax+00h]
0x18000936d  mov     esi, 1
0x180009372  test    ebx, ebx
0x180009374  jnz     loc_180009445
0x18000937a  mov     [rdi+78h], ebx
0x18000937d  test    ebp, ebp
0x18000937f  jz      loc_18000945E
0x180009385  mov     rbx, [rdi+18h]
0x180009389  test    rbx, rbx
0x18000938c  jz      short loc_1800093C8
0x18000938e  mov     r8d, [rbx+8]
0x180009392  lea     rdx, [rbx+0Ch]
0x180009396  mov     r14d, [rbx]
0x180009399  lea     rcx, [rsp+298h+var_278]
0x18000939e  shr     r8d, 1
0x1800093a1  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800093a8  nop     dword ptr [rax+rax+00h]
0x1800093ad  test    eax, eax
0x1800093af  jns     short loc_180009404
0x1800093b1  mov     ecx, eax; int
0x1800093b3  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800093b8  mov     ecx, eax; dwErrCode
0x1800093ba  call    cs:__imp_SetLastError
0x1800093c1  nop     dword ptr [rax+rax+00h]
0x1800093c6  xor     esi, esi
0x1800093c8  lea     rcx, [rsp+298h+var_278]
0x1800093cd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800093d4  nop     dword ptr [rax+rax+00h]
0x1800093d9  mov     eax, esi
0x1800093db  mov     rcx, [rsp+298h+var_28]
0x1800093e3  xor     rcx, rsp; StackCookie
0x1800093e6  call    __security_check_cookie
0x1800093eb  lea     r11, [rsp+298h+var_18]
0x1800093f3  mov     rbx, [r11+28h]
0x1800093f7  mov     rbp, [r11+30h]
0x1800093fb  mov     rsp, r11
0x1800093fe  pop     r14
0x180009400  pop     rdi
0x180009401  pop     rsi
0x180009402  retn
0x180009404  mov     edx, [rbx+4]
0x180009407  mov     rbp, rbx
0x18000940a  add     rbx, r14
0x18000940d  sub     edx, 2
0x180009410  jz      short loc_180009427
0x180009412  sub     edx, 1
0x180009415  jz      short loc_180009427
0x180009417  cmp     edx, 1
0x18000941a  jz      short loc_180009427
0x18000941c  cmp     rbp, rbx
0x18000941f  jnz     loc_180009389
0x180009425  jmp     short loc_1800093C8
0x180009427  lea     rcx, [rsp+298h+var_278]
0x18000942c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180009433  nop     dword ptr [rax+rax+00h]
0x180009438  mov     rdx, rax; unsigned __int16 *
0x18000943b  mov     rcx, rdi; this
0x18000943e  call    ?FileChanged@CacheDirMonitorEntry@@AEAAXPEAG@Z; CacheDirMonitorEntry::FileChanged(ushort *)
0x180009443  jmp     short loc_18000941C
0x180009445  cmp     ebx, 5
0x180009448  jz      short loc_180009457
0x18000944a  add     [rdi+78h], esi
0x18000944d  cmp     dword ptr [rdi+78h], 3
0x180009451  jbe     loc_18000937D
0x180009457  xor     esi, esi
0x180009459  jmp     loc_18000937D
0x18000945e  lea     rdx, dword_18003C134; unsigned __int16 *
0x180009465  mov     rcx, rdi; this
0x180009468  call    ?FileChanged@CacheDirMonitorEntry@@AEAAXPEAG@Z; CacheDirMonitorEntry::FileChanged(ushort *)
0x18000946d  jmp     loc_1800093C8
```

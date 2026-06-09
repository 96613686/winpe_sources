# CDDPDEV::DestroyResidencyState(void)

- ea: `0x14002d228`
- end: `0x14002d39e`
- name: `?DestroyResidencyState@CDDPDEV@@QEAAJXZ`
- size: `374`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140011510`
- `0x14002d088`

## callees

- `0x1400023c0`
- `0x140002420`
- `0x14002d228`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x14002d2a3`
- `watchdog!WdLogSingleEntry2` at `0x14002d335`
- `watchdog!WdLogSingleEntry2` at `0x14002d2a3`
- `watchdog!WdLogSingleEntry2` at `0x14002d335`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002d2ba`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002d34b`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002d2ba`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002d34b`

## pseudocode

```c
__int64 __fastcall CDDPDEV::DestroyResidencyState(CDDPDEV *this)
{
  int v2; // edi
  int v3; // eax
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rax
  int v8; // eax
  int v9; // esi
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rax
  int v14; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  CDDPDEV::AcquireResidencyLock(this);
  v3 = *((_DWORD *)this + 3180);
  *((_QWORD *)this + 1594) = 0;
  *((_QWORD *)this + 1595) = 0;
  *((_QWORD *)this + 1596) = 0;
  if ( v3 )
  {
    v14 = v3;
    v4 = (*((__int64 (__fastcall **)(int *))this + 61))(&v14);
    v2 = v4;
    if ( v4 < 0 )
    {
      WdLogSingleEntry2(2, this, v4);
      WdLogGlobalForLineNumber = 1403;
      v7 = (_QWORD *)WdLogNewEntry5_WdError(v6, v5);
      v7[3] = gCddImageInfo;
      v7[4] = (unsigned int)dword_14003E570;
      v7[5] = 215857758;
      WdLogGlobalForLineNumber = 1403;
    }
    else
    {
      *((_QWORD *)this + 1590) = 0;
      *((_QWORD *)this + 1591) = 0;
    }
  }
  if ( *((_DWORD *)this + 3184) )
  {
    v14 = *((_DWORD *)this + 3184);
    v8 = (*((__int64 (__fastcall **)(int *))this + 45))(&v14);
    v9 = v8;
    if ( v8 < 0 )
    {
      WdLogSingleEntry2(2, this, v8);
      WdLogGlobalForLineNumber = 1421;
      v12 = (_QWORD *)WdLogNewEntry5_WdError(v11, v10);
      v12[3] = gCddImageInfo;
      v12[4] = (unsigned int)dword_14003E570;
      v12[5] = 215857758;
      WdLogGlobalForLineNumber = 1421;
    }
    else
    {
      *((_DWORD *)this + 3184) = 0;
      *((_QWORD *)this + 1593) = 0;
    }
    if ( v2 >= 0 )
      v2 = v9;
  }
  CDDPDEV::ReleaseResidencyLock(this);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002d228  mov     [rsp+arg_8], rbx
0x14002d22d  mov     [rsp+arg_10], rsi
0x14002d232  push    rdi
0x14002d233  sub     rsp, 20h
0x14002d237  mov     rbx, rcx
0x14002d23a  xor     edi, edi
0x14002d23c  call    ?AcquireResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::AcquireResidencyLock(void)
0x14002d241  mov     eax, [rbx+31B0h]
0x14002d247  mov     [rbx+31D0h], rdi
0x14002d24e  mov     [rbx+31D8h], rdi
0x14002d255  mov     [rbx+31E0h], rdi
0x14002d25c  test    eax, eax
0x14002d25e  jz      loc_14002D2E9
0x14002d264  mov     [rsp+28h+arg_0], eax
0x14002d268  lea     rcx, [rsp+28h+arg_0]
0x14002d26d  mov     rax, [rbx+1E8h]
0x14002d274  call    _guard_dispatch_icall
0x14002d279  movsxd  rdi, eax
0x14002d27c  test    eax, eax
0x14002d27e  js      short loc_14002D298
0x14002d280  mov     qword ptr [rbx+31B0h], 0
0x14002d28b  mov     qword ptr [rbx+31B8h], 0
0x14002d296  jmp     short loc_14002D2E9
0x14002d298  mov     r8, rdi
0x14002d29b  mov     rdx, rbx
0x14002d29e  mov     ecx, 2
0x14002d2a3  call    cs:__imp_WdLogSingleEntry2
0x14002d2aa  nop     dword ptr [rax+rax+00h]
0x14002d2af  mov     esi, 57Bh
0x14002d2b4  mov     cs:WdLogGlobalForLineNumber, esi
0x14002d2ba  call    cs:__imp_WdLogNewEntry5_WdError
0x14002d2c1  nop     dword ptr [rax+rax+00h]
0x14002d2c6  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d2cd  mov     [rax+18h], rcx
0x14002d2d1  mov     ecx, cs:dword_14003E570
0x14002d2d7  mov     [rax+20h], rcx
0x14002d2db  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002d2e3  mov     cs:WdLogGlobalForLineNumber, esi
0x14002d2e9  mov     eax, [rbx+31C0h]
0x14002d2ef  test    eax, eax
0x14002d2f1  jz      loc_14002D383
0x14002d2f7  mov     [rsp+28h+arg_0], eax
0x14002d2fb  lea     rcx, [rsp+28h+arg_0]
0x14002d300  mov     rax, [rbx+168h]
0x14002d307  call    _guard_dispatch_icall
0x14002d30c  movsxd  rsi, eax
0x14002d30f  test    eax, eax
0x14002d311  js      short loc_14002D32A
0x14002d313  mov     dword ptr [rbx+31C0h], 0
0x14002d31d  mov     qword ptr [rbx+31C8h], 0
0x14002d328  jmp     short loc_14002D37E
0x14002d32a  mov     r8, rsi
0x14002d32d  mov     rdx, rbx
0x14002d330  mov     ecx, 2
0x14002d335  call    cs:__imp_WdLogSingleEntry2
0x14002d33c  nop     dword ptr [rax+rax+00h]
0x14002d341  mov     cs:WdLogGlobalForLineNumber, 58Dh
0x14002d34b  call    cs:__imp_WdLogNewEntry5_WdError
0x14002d352  nop     dword ptr [rax+rax+00h]
0x14002d357  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d35e  mov     [rax+18h], rcx
0x14002d362  mov     ecx, cs:dword_14003E570
0x14002d368  mov     [rax+20h], rcx
0x14002d36c  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002d374  mov     cs:WdLogGlobalForLineNumber, 58Dh
0x14002d37e  test    edi, edi
0x14002d380  cmovns  edi, esi
0x14002d383  mov     rcx, rbx; this
0x14002d386  call    ?ReleaseResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::ReleaseResidencyLock(void)
0x14002d38b  mov     rbx, [rsp+28h+arg_8]
0x14002d390  mov     eax, edi
0x14002d392  mov     rsi, [rsp+28h+arg_10]
0x14002d397  add     rsp, 20h
0x14002d39b  pop     rdi
0x14002d39c  retn
```

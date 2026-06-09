# CRpcWatchDog::RemoveEntry(_WatchDogEntry *)

- ea: `0x1800020d0`
- end: `0x1800021b9`
- name: `?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z`
- size: `233`
- prototype: `void __fastcall(CRpcWatchDog *__hidden this, struct _WatchDogEntry *)`
- caller_count: `85`
- callee_count: `3`
- tags: ``

## callers

- `0x1800014f0`
- `0x180001670`
- `0x180001980`
- `0x180001a70`
- `0x180001cf0`
- `0x1800198c0`
- `0x180027410`
- `0x180027558`
- `0x180027680`
- `0x180027750`
- `0x180027810`
- `0x1800278e0`
- `0x1800279a0`
- `0x180027aa0`
- `0x180027b80`
- `0x180027c70`
- `0x180027f74`
- `0x180028240`
- `0x180028318`
- `0x1800283e0`
- `0x1800284c0`
- `0x180028590`
- `0x180028724`
- `0x180028890`
- `0x180028a44`
- `0x180028bd0`
- `0x180028c78`
- `0x180028d40`
- `0x180028f10`
- `0x1800290e0`
- `0x1800291b4`
- `0x180029260`
- `0x18002939c`
- `0x1800294c0`
- `0x180029678`
- `0x180029840`
- `0x180029b54`
- `0x180029d50`
- `0x180029e90`
- `0x180029fb0`
- `0x18002a0a8`
- `0x18002a190`
- `0x18002a308`
- `0x18002a450`
- `0x18002a540`
- `0x18002a634`
- `0x18002a710`
- `0x18002a818`
- `0x18002a910`
- `0x18002aa30`

## callees

- `0x1800020d0`
- `0x1800022d0`
- `0x18004e160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002159`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002159`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002113`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002113`

## pseudocode

```c
void __fastcall CRpcWatchDog::RemoveEntry(CRpcWatchDog *this, struct _WatchDogEntry *a2)
{
  unsigned int v3; // r8d
  __int64 v4; // rcx
  _QWORD *v5; // rax
  _QWORD *v6; // rdx

  if ( (BYTE1(xmmword_1800616A0) & 0x40) != 0 )
    WPP_SF_qq(1038, 16, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, a2, *(_QWORD *)a2);
  if ( dword_18006192C )
  {
    EnterCriticalSection(&CriticalSection);
    v4 = *((_QWORD *)a2 + 2);
    v5 = (_QWORD *)((char *)a2 + 16);
    if ( *(struct _WatchDogEntry **)(v4 + 8) != (struct _WatchDogEntry *)((char *)a2 + 16)
      || (v6 = (_QWORD *)*((_QWORD *)a2 + 3), (_QWORD *)*v6 != v5) )
    {
      __fastfail(3u);
    }
    *v6 = v4;
    *(_QWORD *)(v4 + 8) = v6;
    *((_QWORD *)a2 + 3) = (char *)a2 + 16;
    *v5 = v5;
    if ( (__int64 *)qword_1800618D8 == &qword_1800618D8 && *(unsigned int **)&qword_1800618E8 == &qword_1800618E8 )
      WxSetThreadpoolTimer(g_RpcWatchDog, 0, v3, 0);
    LeaveCriticalSection(&CriticalSection);
  }
  if ( (BYTE1(xmmword_1800616A0) & 0x40) != 0 )
    WPP_SF_qq(1038, 17, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, a2, *(_QWORD *)a2);
}

```

## disassembly

```asm
0x1800020d0  push    rbx
0x1800020d2  sub     rsp, 30h
0x1800020d6  mov     rbx, rdx
0x1800020d9  test    byte ptr cs:xmmword_1800616A0+1, 40h
0x1800020e0  jz      short loc_180002103
0x1800020e2  mov     rax, [rbx]
0x1800020e5  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x1800020ec  mov     edx, 10h
0x1800020f1  mov     [rsp+38h+var_18], rax
0x1800020f6  mov     ecx, 40Eh
0x1800020fb  mov     r9, rbx
0x1800020fe  call    WPP_SF_qq
0x180002103  cmp     cs:dword_18006192C, 0
0x18000210a  jz      short loc_18000215F
0x18000210c  lea     rcx, CriticalSection; lpCriticalSection
0x180002113  call    cs:__imp_EnterCriticalSection
0x180002119  mov     rcx, [rbx+10h]
0x18000211d  lea     rax, [rbx+10h]
0x180002121  cmp     [rcx+8], rax
0x180002125  jnz     loc_1800021B2
0x18000212b  mov     rdx, [rax+8]
0x18000212f  cmp     [rdx], rax
0x180002132  jnz     short loc_1800021B2
0x180002134  mov     [rdx], rcx
0x180002137  mov     [rcx+8], rdx
0x18000213b  mov     [rax+8], rax
0x18000213f  mov     [rax], rax
0x180002142  lea     rax, qword_1800618D8
0x180002149  cmp     cs:qword_1800618D8, rax
0x180002150  jz      short loc_18000218F
0x180002152  lea     rcx, CriticalSection; lpCriticalSection
0x180002159  call    cs:__imp_LeaveCriticalSection
0x18000215f  test    byte ptr cs:xmmword_1800616A0+1, 40h
0x180002166  jz      short loc_180002189
0x180002168  mov     rax, [rbx]
0x18000216b  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x180002172  mov     edx, 11h
0x180002177  mov     [rsp+38h+var_18], rax
0x18000217c  mov     ecx, 40Eh
0x180002181  mov     r9, rbx
0x180002184  call    WPP_SF_qq
0x180002189  add     rsp, 30h
0x18000218d  pop     rbx
0x18000218e  retn
0x18000218f  lea     rax, qword_1800618E8
0x180002196  cmp     cs:qword_1800618E8, rax
0x18000219d  jnz     short loc_180002152
0x18000219f  mov     rcx, cs:?g_RpcWatchDog@@3VCRpcWatchDog@@A; struct _TP_TIMER *
0x1800021a6  xor     r9d, r9d; unsigned int
0x1800021a9  xor     edx, edx; struct _FILETIME *
0x1800021ab  call    ?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z; WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)
0x1800021b0  jmp     short loc_180002152
0x1800021b2  mov     ecx, 3
0x1800021b7  int     29h; Win8: RtlFailFast(ecx)
```

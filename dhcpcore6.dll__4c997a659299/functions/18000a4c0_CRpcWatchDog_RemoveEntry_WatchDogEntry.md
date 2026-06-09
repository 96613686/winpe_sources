# CRpcWatchDog::RemoveEntry(_WatchDogEntry *)

- ea: `0x18000a4c0`
- end: `0x18000a5ba`
- name: `?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z`
- size: `250`
- prototype: `void __fastcall(CRpcWatchDog *__hidden this, struct _WatchDogEntry *)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x180009520`
- `0x180009a70`
- `0x18000a170`
- `0x180026aa0`
- `0x180026b80`
- `0x180026d40`
- `0x180026e30`
- `0x180027120`
- `0x180027440`
- `0x180027540`
- `0x1800276b0`
- `0x180027900`
- `0x180027a08`

## callees

- `0x18000a4c0`
- `0x18000b310`
- `0x180033920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a503`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a503`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a553`

## pseudocode

```c
void __fastcall CRpcWatchDog::RemoveEntry(CRpcWatchDog *this, struct _WatchDogEntry *a2)
{
  unsigned int v3; // r8d
  __int64 v4; // rcx
  _QWORD *v5; // rax
  _QWORD *v6; // rdx

  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qq(1038, 16, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, a2, *(_QWORD *)a2);
  if ( dword_18004271C )
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
    if ( (__int64 *)qword_1800426C8 == &qword_1800426C8 && *(unsigned int **)&qword_1800426D8 == &qword_1800426D8 )
      WxSetThreadpoolTimer(g_RpcWatchDog, 0, v3, 0);
    LeaveCriticalSection(&CriticalSection);
  }
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qq(1038, 17, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, a2, *(_QWORD *)a2);
}

```

## disassembly

```asm
0x18000a4c0  push    rbx
0x18000a4c2  sub     rsp, 30h
0x18000a4c6  mov     rbx, rdx
0x18000a4c9  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000a4d0  jz      short loc_18000A4F3
0x18000a4d2  mov     rax, [rbx]
0x18000a4d5  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x18000a4dc  mov     edx, 10h
0x18000a4e1  mov     [rsp+38h+var_18], rax
0x18000a4e6  mov     ecx, 40Eh
0x18000a4eb  mov     r9, rbx
0x18000a4ee  call    WPP_SF_qq
0x18000a4f3  cmp     cs:dword_18004271C, 0
0x18000a4fa  jz      short loc_18000A55F
0x18000a4fc  lea     rcx, CriticalSection; lpCriticalSection
0x18000a503  call    cs:__imp_EnterCriticalSection
0x18000a50a  nop     dword ptr [rax+rax+00h]
0x18000a50f  mov     rcx, [rbx+10h]
0x18000a513  lea     rax, [rbx+10h]
0x18000a517  cmp     [rcx+8], rax
0x18000a51b  jnz     loc_18000A5B3
0x18000a521  mov     rdx, [rax+8]
0x18000a525  cmp     [rdx], rax
0x18000a528  jnz     loc_18000A5B3
0x18000a52e  mov     [rdx], rcx
0x18000a531  mov     [rcx+8], rdx
0x18000a535  mov     [rax+8], rax
0x18000a539  mov     [rax], rax
0x18000a53c  lea     rax, qword_1800426C8
0x18000a543  cmp     cs:qword_1800426C8, rax
0x18000a54a  jz      short loc_18000A590
0x18000a54c  lea     rcx, CriticalSection; lpCriticalSection
0x18000a553  call    cs:__imp_LeaveCriticalSection
0x18000a55a  nop     dword ptr [rax+rax+00h]
0x18000a55f  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000a566  jz      short loc_18000A589
0x18000a568  mov     rax, [rbx]
0x18000a56b  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x18000a572  mov     edx, 11h
0x18000a577  mov     [rsp+38h+var_18], rax
0x18000a57c  mov     ecx, 40Eh
0x18000a581  mov     r9, rbx
0x18000a584  call    WPP_SF_qq
0x18000a589  add     rsp, 30h
0x18000a58d  pop     rbx
0x18000a58e  retn
0x18000a590  lea     rax, qword_1800426D8
0x18000a597  cmp     cs:qword_1800426D8, rax
0x18000a59e  jnz     short loc_18000A54C
0x18000a5a0  mov     rcx, cs:?g_RpcWatchDog@@3VCRpcWatchDog@@A; struct _TP_TIMER *
0x18000a5a7  xor     r9d, r9d; unsigned int
0x18000a5aa  xor     edx, edx; struct _FILETIME *
0x18000a5ac  call    ?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z; WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)
0x18000a5b1  jmp     short loc_18000A54C
0x18000a5b3  mov     ecx, 3
0x18000a5b8  int     29h; Win8: RtlFailFast(ecx)
```

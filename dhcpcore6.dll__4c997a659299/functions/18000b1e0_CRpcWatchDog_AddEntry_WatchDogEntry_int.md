# CRpcWatchDog::AddEntry(_WatchDogEntry *,int)

- ea: `0x18000b1e0`
- end: `0x18000b2fd`
- name: `?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z`
- size: `285`
- prototype: `void __fastcall(CRpcWatchDog *__hidden this, struct _WatchDogEntry *, int)`
- caller_count: `13`
- callee_count: `4`
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

- `0x18000b1e0`
- `0x18000b310`
- `0x180033830`
- `0x180033920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b244`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b244`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b2c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b2c1`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000b229`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000b229`

## pseudocode

```c
void __fastcall CRpcWatchDog::AddEntry(CRpcWatchDog *this, struct _WatchDogEntry *a2, int a3)
{
  BOOL v4; // ecx
  _QWORD *v5; // rdx

  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qq(1038, 14, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, a2, *(_QWORD *)a2);
  if ( dword_18004271C && QueryUnbiasedInterruptTime((PULONGLONG)a2 + 1) )
  {
    EnterCriticalSection(&CriticalSection);
    v4 = *(unsigned int **)&qword_1800426D8 == &qword_1800426D8 && (__int64 *)qword_1800426C8 == &qword_1800426C8;
    v5 = (_QWORD *)qword_1800426E0;
    if ( *(unsigned int **)qword_1800426E0 != &qword_1800426D8 )
      __fastfail(3u);
    *((_QWORD *)a2 + 2) = &qword_1800426D8;
    *((_QWORD *)a2 + 3) = v5;
    *v5 = (char *)a2 + 16;
    qword_1800426E0 = (__int64)a2 + 16;
    if ( v4 )
      WxSetThreadpoolTimer(g_RpcWatchDog, &stru_180042710, (unsigned int)&qword_1800426D8, 0x7530u);
    LeaveCriticalSection(&CriticalSection);
  }
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qql((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a2, *(_QWORD *)a2);
}

```

## disassembly

```asm
0x18000b1e0  mov     [rsp+arg_0], rbx
0x18000b1e5  push    rdi
0x18000b1e6  sub     rsp, 30h
0x18000b1ea  mov     rbx, rdx
0x18000b1ed  xor     edi, edi
0x18000b1ef  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000b1f6  jz      short loc_18000B219
0x18000b1f8  mov     rax, [rbx]
0x18000b1fb  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x18000b202  mov     edx, 0Eh
0x18000b207  mov     [rsp+38h+var_18], rax
0x18000b20c  mov     ecx, 40Eh
0x18000b211  mov     r9, rbx
0x18000b214  call    WPP_SF_qq
0x18000b219  cmp     cs:dword_18004271C, edi
0x18000b21f  jz      loc_18000B2CD
0x18000b225  lea     rcx, [rbx+8]; UnbiasedTime
0x18000b229  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000b230  nop     dword ptr [rax+rax+00h]
0x18000b235  test    eax, eax
0x18000b237  jz      loc_18000B2CD
0x18000b23d  lea     rcx, CriticalSection; lpCriticalSection
0x18000b244  call    cs:__imp_EnterCriticalSection
0x18000b24b  nop     dword ptr [rax+rax+00h]
0x18000b250  lea     r8, qword_1800426D8; unsigned int
0x18000b257  mov     edi, 1
0x18000b25c  cmp     cs:qword_1800426D8, r8
0x18000b263  lea     rax, qword_1800426C8
0x18000b26a  jnz     short loc_18000B275
0x18000b26c  cmp     cs:qword_1800426C8, rax
0x18000b273  jz      short loc_18000B279
0x18000b275  xor     ecx, ecx
0x18000b277  jmp     short loc_18000B27B
0x18000b279  mov     ecx, edi
0x18000b27b  mov     rdx, cs:qword_1800426E0
0x18000b282  cmp     [rdx], r8
0x18000b285  jnz     short loc_18000B2F6
0x18000b287  mov     [rbx+10h], r8
0x18000b28b  lea     rax, [rbx+10h]
0x18000b28f  mov     [rax+8], rdx
0x18000b293  mov     [rdx], rax
0x18000b296  mov     cs:qword_1800426E0, rax
0x18000b29d  test    ecx, ecx
0x18000b29f  jz      short loc_18000B2BA
0x18000b2a1  mov     rcx, cs:?g_RpcWatchDog@@3VCRpcWatchDog@@A; struct _TP_TIMER *
0x18000b2a8  lea     rdx, stru_180042710; struct _FILETIME *
0x18000b2af  mov     r9d, 7530h; unsigned int
0x18000b2b5  call    ?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z; WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)
0x18000b2ba  lea     rcx, CriticalSection; lpCriticalSection
0x18000b2c1  call    cs:__imp_LeaveCriticalSection
0x18000b2c8  nop     dword ptr [rax+rax+00h]
0x18000b2cd  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000b2d4  jz      short loc_18000B2EA
0x18000b2d6  mov     rax, [rbx]
0x18000b2d9  mov     r9, rbx
0x18000b2dc  mov     [rsp+38h+var_10], edi
0x18000b2e0  mov     [rsp+38h+var_18], rax
0x18000b2e5  call    WPP_SF_qql
0x18000b2ea  mov     rbx, [rsp+38h+arg_0]
0x18000b2ef  add     rsp, 30h
0x18000b2f3  pop     rdi
0x18000b2f4  retn
0x18000b2f6  mov     ecx, 3
0x18000b2fb  int     29h; Win8: RtlFailFast(ecx)
```

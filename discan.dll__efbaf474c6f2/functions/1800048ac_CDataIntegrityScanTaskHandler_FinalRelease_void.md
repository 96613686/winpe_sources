# CDataIntegrityScanTaskHandler::FinalRelease(void)

- ea: `0x1800048ac`
- end: `0x180004a3a`
- name: `?FinalRelease@CDataIntegrityScanTaskHandler@@QEAAXXZ`
- size: `398`
- prototype: `void __fastcall(CDataIntegrityScanTaskHandler *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000306c`
- `0x1800030b8`

## callees

- `0x1800048ac`
- `0x180006874`

## import_xrefs

- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18000490b`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18000497f`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18000490b`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18000497f`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800049f3`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800049f3`

## pseudocode

```c
void __fastcall CDataIntegrityScanTaskHandler::FinalRelease(CDataIntegrityScanTaskHandler *this)
{
  __int64 v1; // r9
  PVOID *v3; // rcx
  __int64 v4; // r9
  __int64 v5; // r9

  v1 = *((_QWORD *)this + 31);
  if ( !v1 )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, v1);
  }
  WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 31), 0);
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
      *((_QWORD *)this + 31));
LABEL_10:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = *((_QWORD *)this + 33);
  if ( v4 )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 4u )
      WPP_SF_q(v3[2], 21, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, v4);
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 33), 0);
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        *((_QWORD *)this + 33));
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v5 = *((_QWORD *)this + 21);
  if ( v5 )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 4u )
      WPP_SF_q(v3[2], 23, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, v5);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 21), 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        *((_QWORD *)this + 21));
    }
  }
}

```

## disassembly

```asm
0x1800048ac  mov     [rsp+arg_0], rbx
0x1800048b1  mov     [rsp+arg_8], rbp
0x1800048b6  push    r14
0x1800048b8  sub     rsp, 20h
0x1800048bc  mov     r9, [rcx+0F8h]
0x1800048c3  lea     rbp, WPP_GLOBAL_Control
0x1800048ca  lea     r14, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x1800048d1  mov     rbx, rcx
0x1800048d4  test    r9, r9
0x1800048d7  jz      short loc_180004941
0x1800048d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048e0  cmp     rcx, rbp
0x1800048e3  jz      short loc_180004902
0x1800048e5  test    byte ptr [rcx+1Ch], 1
0x1800048e9  jz      short loc_180004902
0x1800048eb  cmp     byte ptr [rcx+19h], 4
0x1800048ef  jb      short loc_180004902
0x1800048f1  mov     rcx, [rcx+10h]
0x1800048f5  mov     edx, 13h
0x1800048fa  mov     r8, r14
0x1800048fd  call    WPP_SF_q
0x180004902  mov     rcx, [rbx+0F8h]; pwk
0x180004909  xor     edx, edx; fCancelPendingCallbacks
0x18000490b  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180004911  mov     rcx, cs:WPP_GLOBAL_Control
0x180004918  cmp     rcx, rbp
0x18000491b  jz      short loc_180004948
0x18000491d  test    byte ptr [rcx+1Ch], 1
0x180004921  jz      short loc_180004948
0x180004923  cmp     byte ptr [rcx+19h], 4
0x180004927  jb      short loc_180004948
0x180004929  mov     r9, [rbx+0F8h]
0x180004930  mov     edx, 14h
0x180004935  mov     rcx, [rcx+10h]
0x180004939  mov     r8, r14
0x18000493c  call    WPP_SF_q
0x180004941  mov     rcx, cs:WPP_GLOBAL_Control
0x180004948  mov     r9, [rbx+108h]
0x18000494f  test    r9, r9
0x180004952  jz      short loc_1800049BC
0x180004954  cmp     rcx, rbp
0x180004957  jz      short loc_180004976
0x180004959  test    byte ptr [rcx+1Ch], 1
0x18000495d  jz      short loc_180004976
0x18000495f  cmp     byte ptr [rcx+19h], 4
0x180004963  jb      short loc_180004976
0x180004965  mov     rcx, [rcx+10h]
0x180004969  mov     edx, 15h
0x18000496e  mov     r8, r14
0x180004971  call    WPP_SF_q
0x180004976  mov     rcx, [rbx+108h]; pwk
0x18000497d  xor     edx, edx; fCancelPendingCallbacks
0x18000497f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180004985  mov     rcx, cs:WPP_GLOBAL_Control
0x18000498c  cmp     rcx, rbp
0x18000498f  jz      short loc_1800049BC
0x180004991  test    byte ptr [rcx+1Ch], 1
0x180004995  jz      short loc_1800049BC
0x180004997  cmp     byte ptr [rcx+19h], 4
0x18000499b  jb      short loc_1800049BC
0x18000499d  mov     r9, [rbx+108h]
0x1800049a4  mov     edx, 16h
0x1800049a9  mov     rcx, [rcx+10h]
0x1800049ad  mov     r8, r14
0x1800049b0  call    WPP_SF_q
0x1800049b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049bc  mov     r9, [rbx+0A8h]
0x1800049c3  test    r9, r9
0x1800049c6  jz      short loc_180004A29
0x1800049c8  cmp     rcx, rbp
0x1800049cb  jz      short loc_1800049EA
0x1800049cd  test    byte ptr [rcx+1Ch], 1
0x1800049d1  jz      short loc_1800049EA
0x1800049d3  cmp     byte ptr [rcx+19h], 4
0x1800049d7  jb      short loc_1800049EA
0x1800049d9  mov     rcx, [rcx+10h]
0x1800049dd  mov     edx, 17h
0x1800049e2  mov     r8, r14
0x1800049e5  call    WPP_SF_q
0x1800049ea  mov     rcx, [rbx+0A8h]; pwa
0x1800049f1  xor     edx, edx; fCancelPendingCallbacks
0x1800049f3  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800049f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a00  cmp     rcx, rbp
0x180004a03  jz      short loc_180004A29
0x180004a05  test    byte ptr [rcx+1Ch], 1
0x180004a09  jz      short loc_180004A29
0x180004a0b  cmp     byte ptr [rcx+19h], 4
0x180004a0f  jb      short loc_180004A29
0x180004a11  mov     r9, [rbx+0A8h]
0x180004a18  mov     edx, 18h
0x180004a1d  mov     rcx, [rcx+10h]
0x180004a21  mov     r8, r14
0x180004a24  call    WPP_SF_q
0x180004a29  mov     rbx, [rsp+28h+arg_0]
0x180004a2e  mov     rbp, [rsp+28h+arg_8]
0x180004a33  add     rsp, 20h
0x180004a37  pop     r14
0x180004a39  retn
```

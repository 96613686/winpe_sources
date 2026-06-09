# PCW_QUERY_ITEM::~PCW_QUERY_ITEM(void)

- ea: `0x14000930c`
- end: `0x140009475`
- name: `??1PCW_QUERY_ITEM@@QEAA@XZ`
- size: `361`
- prototype: `void __fastcall(PCW_QUERY_ITEM *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140009284`
- `0x14000947c`
- `0x140009750`

## callees

- `0x140008140`
- `0x14000930c`
- `0x1400099e0`
- `0x14000d7d0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000935a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000935a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009348`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009397`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009348`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009397`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009415`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000943b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009415`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000943b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000942f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000942f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400093a9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400093a9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009409`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009409`

## pseudocode

```c
void __fastcall PCW_QUERY_ITEM::~PCW_QUERY_ITEM(PCW_QUERY_ITEM *this)
{
  ULONG64 v1; // rax
  AllocatedUnicodeString *v2; // rsi
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rbx
  PCW_QUERY_ITEM **v7; // rdx
  PCW_QUERY_ITEM **v8; // rax
  PCW_QUERY_ITEM **v9; // rdx
  PCW_QUERY_ITEM **v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  union _PCW_CALLBACK_INFORMATION v13; // [rsp+20h] [rbp-38h] BYREF

  v1 = *((_QWORD *)this + 6);
  v2 = (PCW_QUERY_ITEM *)((char *)this + 88);
  memset(&v13.CollectData.InstanceId, 0, 24);
  v13.AddCounter.CounterMask = v1;
  v4 = *((_QWORD *)this + 10);
  v13.AddCounter.InstanceMask = (PCUNICODE_STRING)((char *)this + 88);
  v5 = *(_QWORD *)(v4 + 80);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v5 + 80, 0);
  PCW_COUNTERSET_BASE::Notify(*(PCW_COUNTERSET_BASE **)(*((_QWORD *)this + 10) + 80LL), PcwCallbackRemoveCounter, &v13);
  PCW_COUNTERSET_BASE::Notify(*((PCW_COUNTERSET_BASE **)this + 10), PcwCallbackRemoveCounter, &v13);
  v6 = *(_QWORD *)(*((_QWORD *)this + 10) + 80LL);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v6 + 104, 0);
  v7 = (PCW_QUERY_ITEM **)*((_QWORD *)this + 2);
  if ( v7[1] != (PCW_QUERY_ITEM *)((char *)this + 16)
    || (v8 = (PCW_QUERY_ITEM **)*((_QWORD *)this + 3), *v8 != (PCW_QUERY_ITEM *)((char *)this + 16))
    || (*v8 = (PCW_QUERY_ITEM *)v7,
        v7[1] = (PCW_QUERY_ITEM *)v8,
        v9 = (PCW_QUERY_ITEM **)*((_QWORD *)this + 4),
        v9[1] != (PCW_QUERY_ITEM *)((char *)this + 32))
    || (v10 = (PCW_QUERY_ITEM **)*((_QWORD *)this + 5), *v10 != (PCW_QUERY_ITEM *)((char *)this + 32)) )
  {
    __fastfail(3u);
  }
  *v10 = (PCW_QUERY_ITEM *)v9;
  v9[1] = (PCW_QUERY_ITEM *)v10;
  ExReleasePushLockExclusiveEx(*(_QWORD *)(*((_QWORD *)this + 10) + 80LL) + 104LL, 0);
  KeLeaveCriticalRegion();
  ExReleasePushLockSharedEx(*(_QWORD *)(*((_QWORD *)this + 10) + 80LL) + 80LL, 0);
  KeLeaveCriticalRegion();
  AllocatedUnicodeString::~AllocatedUnicodeString(v2);
  v12 = *((_QWORD *)this + 10);
  if ( v12 )
    ReleaseDeleter<PCW_COUNTERSET>::operator()(v11, v12);
}

```

## disassembly

```asm
0x14000930c  mov     r11, rsp
0x14000930f  mov     [r11+8], rbx
0x140009313  mov     [r11+10h], rsi
0x140009317  push    rdi
0x140009318  sub     rsp, 50h
0x14000931c  mov     rax, [rcx+30h]
0x140009320  lea     rsi, [rcx+58h]
0x140009324  xorps   xmm0, xmm0
0x140009327  mov     rdi, rcx
0x14000932a  movdqu  xmmword ptr [rsp+58h+var_38+10h], xmm0
0x140009330  mov     [r11-38h], rax
0x140009334  mov     rax, [rcx+50h]
0x140009338  mov     qword ptr [r11-18h], 0
0x140009340  mov     [r11-30h], rsi
0x140009344  mov     rbx, [rax+50h]
0x140009348  call    cs:__imp_KeEnterCriticalRegion
0x14000934f  nop     dword ptr [rax+rax+00h]
0x140009354  xor     edx, edx
0x140009356  lea     rcx, [rbx+50h]
0x14000935a  call    cs:__imp_ExAcquirePushLockSharedEx
0x140009361  nop     dword ptr [rax+rax+00h]
0x140009366  mov     rcx, [rdi+50h]
0x14000936a  lea     r8, [rsp+58h+var_38]; union _PCW_CALLBACK_INFORMATION *
0x14000936f  mov     ebx, 1
0x140009374  mov     edx, ebx; enum _PCW_CALLBACK_TYPE
0x140009376  mov     rcx, [rcx+50h]; this
0x14000937a  call    ?Notify@PCW_COUNTERSET_BASE@@QEBAXW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@@Z; PCW_COUNTERSET_BASE::Notify(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *)
0x14000937f  mov     rcx, [rdi+50h]; this
0x140009383  lea     r8, [rsp+58h+var_38]; union _PCW_CALLBACK_INFORMATION *
0x140009388  mov     edx, ebx; enum _PCW_CALLBACK_TYPE
0x14000938a  call    ?Notify@PCW_COUNTERSET_BASE@@QEBAXW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@@Z; PCW_COUNTERSET_BASE::Notify(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *)
0x14000938f  mov     rax, [rdi+50h]
0x140009393  mov     rbx, [rax+50h]
0x140009397  call    cs:__imp_KeEnterCriticalRegion
0x14000939e  nop     dword ptr [rax+rax+00h]
0x1400093a3  xor     edx, edx
0x1400093a5  lea     rcx, [rbx+68h]
0x1400093a9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400093b0  nop     dword ptr [rax+rax+00h]
0x1400093b5  lea     rcx, [rdi+10h]
0x1400093b9  mov     rdx, [rcx]
0x1400093bc  cmp     [rdx+8], rcx
0x1400093c0  jnz     loc_14000946E
0x1400093c6  mov     rax, [rcx+8]
0x1400093ca  cmp     [rax], rcx
0x1400093cd  jnz     loc_14000946E
0x1400093d3  mov     [rax], rdx
0x1400093d6  mov     [rdx+8], rax
0x1400093da  lea     rax, [rdi+20h]
0x1400093de  mov     rdx, [rax]
0x1400093e1  cmp     [rdx+8], rax
0x1400093e5  jnz     loc_14000946E
0x1400093eb  mov     rcx, [rax+8]
0x1400093ef  cmp     [rcx], rax
0x1400093f2  jnz     short loc_14000946E
0x1400093f4  mov     [rcx], rdx
0x1400093f7  mov     [rdx+8], rcx
0x1400093fb  xor     edx, edx
0x1400093fd  mov     rax, [rdi+50h]
0x140009401  mov     rcx, [rax+50h]
0x140009405  add     rcx, 68h ; 'h'
0x140009409  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140009410  nop     dword ptr [rax+rax+00h]
0x140009415  call    cs:__imp_KeLeaveCriticalRegion
0x14000941c  nop     dword ptr [rax+rax+00h]
0x140009421  mov     rax, [rdi+50h]
0x140009425  xor     edx, edx
0x140009427  mov     rcx, [rax+50h]
0x14000942b  add     rcx, 50h ; 'P'
0x14000942f  call    cs:__imp_ExReleasePushLockSharedEx
0x140009436  nop     dword ptr [rax+rax+00h]
0x14000943b  call    cs:__imp_KeLeaveCriticalRegion
0x140009442  nop     dword ptr [rax+rax+00h]
0x140009447  mov     rcx, rsi; this
0x14000944a  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000944f  mov     rdx, [rdi+50h]
0x140009453  test    rdx, rdx
0x140009456  jz      short loc_14000945D
0x140009458  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000945d  mov     rbx, [rsp+58h+arg_0]
0x140009462  mov     rsi, [rsp+58h+arg_8]
0x140009467  add     rsp, 50h
0x14000946b  pop     rdi
0x14000946c  retn
0x14000946e  mov     ecx, 3
0x140009473  int     29h; Win8: RtlFailFast(ecx)
```

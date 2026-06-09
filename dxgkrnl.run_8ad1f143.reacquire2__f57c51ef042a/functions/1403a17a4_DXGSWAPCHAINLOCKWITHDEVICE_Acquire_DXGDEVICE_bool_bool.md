# DXGSWAPCHAINLOCKWITHDEVICE::Acquire(DXGDEVICE * *,bool,bool)

- ea: `0x1403a17a4`
- end: `0x1403a1c83`
- name: `?Acquire@DXGSWAPCHAINLOCKWITHDEVICE@@QEAAJPEAPEAVDXGDEVICE@@_N1@Z`
- size: `1247`
- prototype: `__int64 __fastcall(DXGSWAPCHAINLOCKWITHDEVICE *__hidden this, struct DXGDEVICE **, bool, bool)`
- caller_count: `7`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401ad540`
- `0x1401c2980`
- `0x1401d3380`
- `0x1401dacf0`
- `0x140268250`
- `0x1403a0fc0`
- `0x1403a1110`

## callees

- `0x1400144ec`
- `0x140014714`
- `0x1400159a0`
- `0x1400160e4`
- `0x14001b890`
- `0x14001d070`
- `0x14001d0e4`
- `0x14001f6fc`
- `0x140042a60`
- `0x140047b74`
- `0x1400a0100`
- `0x140321790`
- `0x140323854`
- `0x140323bf4`
- `0x14036729c`
- `0x1403a17a4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a19d6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a1ad7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a19d6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a1ad7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403a18f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403a18f9`
- `ntoskrnl!KeReadStateEvent` at `0x1403a1999`
- `ntoskrnl!KeReadStateEvent` at `0x1403a1999`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403a18ed`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403a18ed`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403a1a7f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403a1a7f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1403a19eb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1403a1b55`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1403a19eb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1403a1b55`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403a1aec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403a1b1f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403a1aec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403a1b1f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1403a1a94`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1403a1a94`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403a19bd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403a19bd`
- `watchdog!WdLogSingleEntry2` at `0x1403a18c8`
- `watchdog!WdLogSingleEntry2` at `0x1403a1926`
- `watchdog!WdLogSingleEntry2` at `0x1403a1aac`
- `watchdog!WdLogSingleEntry2` at `0x1403a18c8`
- `watchdog!WdLogSingleEntry2` at `0x1403a1926`
- `watchdog!WdLogSingleEntry2` at `0x1403a1aac`
- `watchdog!WdLogSingleEntry0` at `0x1403a1c0c`
- `watchdog!WdLogSingleEntry0` at `0x1403a1c0c`
- `watchdog!WdLogSingleEntry1` at `0x1403a1be7`
- `watchdog!WdLogSingleEntry1` at `0x1403a1c5c`
- `watchdog!WdLogSingleEntry1` at `0x1403a1be7`
- `watchdog!WdLogSingleEntry1` at `0x1403a1c5c`

## pseudocode

```c
__int64 __fastcall DXGSWAPCHAINLOCKWITHDEVICE::Acquire(
        DXGSWAPCHAINLOCKWITHDEVICE *this,
        struct DXGDEVICE **a2,
        char a3,
        char a4)
{
  __int64 v7; // rcx
  __int64 v8; // rax
  _BYTE *v9; // r15
  struct DXGPROCESS *Current; // rax
  struct DXGPROCESS *v11; // rbp
  volatile signed __int32 *v12; // r14
  __int64 v13; // rdx
  __int64 v14; // r12
  unsigned int v15; // eax
  __int64 v16; // r8
  int v17; // edx
  __int64 v18; // rbx
  signed __int64 v19; // rax
  signed __int64 v20; // rtt
  int v21; // ebp
  __int64 result; // rax
  struct _KEVENT *v23; // r14
  __int64 v24; // rcx
  __int64 *v25; // rbx
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rdx
  char v34[8]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v35; // [rsp+68h] [rbp-80h]
  __int64 v36; // [rsp+70h] [rbp-78h]
  char v37; // [rsp+78h] [rbp-70h]
  __int64 v38; // [rsp+80h] [rbp-68h]

  DXGAUTOMUTEX::Acquire((DXGSWAPCHAINLOCKWITHDEVICE *)((char *)this + 24));
  v8 = *((_QWORD *)this + 1);
  *((_BYTE *)this + 40) = 1;
  if ( *(_DWORD *)(v8 + 48) )
  {
    WdLogSingleEntry1(3);
    result = 3221225558LL;
    WdLogGlobalForLineNumber = 4332;
  }
  else
  {
    v9 = (char *)this + 16;
    if ( *(_BYTE *)this == 1 )
    {
      v25 = (__int64 *)(v8 + 160);
      if ( !*v9 )
        v25 = (__int64 *)(v8 + 112);
      v26 = *v25;
      if ( PsGetCurrentProcess(v7) != v26 )
      {
        PsGetCurrentProcessId();
        WdLogSingleEntry2(3, *((_QWORD *)this + 1));
        result = 3221225506LL;
        WdLogGlobalForLineNumber = 4341;
        return result;
      }
    }
    Current = DXGPROCESS::GetCurrent();
    v11 = Current;
    if ( a2 )
    {
      *a2 = 0;
      v12 = (volatile signed __int32 *)((char *)Current + 248);
      DXGPUSHLOCK::AcquireShared((struct DXGPROCESS *)((char *)Current + 248));
      v13 = *v9 != 0 ? 0x30 : 0;
      v14 = *(unsigned int *)(v13 + *((_QWORD *)this + 1) + 96);
      v15 = (*(_DWORD *)(v13 + *((_QWORD *)this + 1) + 96) >> 6) & 0xFFFFFF;
      if ( v15 < *((_DWORD *)v11 + 74) )
      {
        v16 = *((_QWORD *)v11 + 35);
        if ( (((unsigned int)v14 >> 25) & 0x60) == (*(_BYTE *)(v16 + 16LL * v15 + 8) & 0x60)
          && (*(_DWORD *)(v16 + 16LL * v15 + 8) & 0x2000) == 0 )
        {
          v17 = *(_DWORD *)(v16 + 16LL * v15 + 8) & 0x1F;
          if ( v17 )
          {
            if ( v17 != 3 )
            {
              WdLogSingleEntry0(2);
              v18 = 0;
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
              goto LABEL_15;
            }
            v18 = *(_QWORD *)(v16 + 16LL * v15);
            if ( !v18 )
            {
LABEL_15:
              WdLogSingleEntry2(3, v14);
              WdLogGlobalForLineNumber = 4381;
              v21 = -1073741811;
LABEL_16:
              _InterlockedDecrement(v12 + 4);
              ExReleasePushLockSharedEx(v12, 0);
              KeLeaveCriticalRegion();
              if ( !v18 || !a3 )
              {
LABEL_20:
                if ( v21 >= 0 )
                {
                  v31 = *((_QWORD *)this + 1);
                  if ( !*(_DWORD *)(v31 + 48) )
                  {
                    *(_QWORD *)((*v9 != 0 ? 0x30 : 0) + v31 + 104) = v18;
                    *a2 = (struct DXGDEVICE *)v18;
                    return (unsigned int)v21;
                  }
                  WdLogSingleEntry1(3);
                  WdLogGlobalForLineNumber = 4438;
                  v21 = -1073741738;
                }
                DXGSWAPCHAINLOCKWITHDEVICE::Release(this);
                return (unsigned int)v21;
              }
              DXGAUTOMUTEX::Release((DXGSWAPCHAINLOCKWITHDEVICE *)((char *)this + 24));
              v23 = *(struct _KEVENT **)(v18 + 16);
              if ( !KeReadStateEvent(v23 + 4) )
                KeWaitForSingleObject(&v23[4], Executive, 0, 0, 0);
              if ( (unsigned int)Feature_IdSwapChainUserModeSync__private_IsEnabledDeviceUsageNoInline() && a4 )
              {
                KeEnterCriticalRegion();
                if ( !ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v18 + 136), 0) )
                {
                  DXGADAPTER::TryWakeUpFromD3State(*(DXGADAPTER **)(*(_QWORD *)(v18 + 16) + 16LL));
                  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                    McTemplateK0q_EtwWriteTransfer(v27, EventBlockThread, v28, 40);
                  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v18 + 136), 1u);
LABEL_42:
                  DXGADAPTER::EnableD3Requests(*(DXGADAPTER **)(*(_QWORD *)(v18 + 16) + 16LL));
                }
              }
              else
              {
                KeEnterCriticalRegion();
                if ( !ExAcquireResourceSharedLite(*(PERESOURCE *)(v18 + 136), 0) )
                {
                  DXGADAPTER::TryWakeUpFromD3State(*(DXGADAPTER **)(*(_QWORD *)(v18 + 16) + 16LL));
                  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                    McTemplateK0q_EtwWriteTransfer(v29, EventBlockThread, v30, 40);
                  ExAcquireResourceSharedLite(*(PERESOURCE *)(v18 + 136), 1u);
                  goto LABEL_42;
                }
              }
              *((_BYTE *)this + 41) = 1;
              v24 = *(_QWORD *)(*(_QWORD *)(v18 + 16) + 16LL);
              v36 = v24;
              v37 = 0;
              v38 = 0;
              if ( v24 )
              {
                _InterlockedIncrement64((volatile signed __int64 *)(v24 + 24));
                v35 = -1;
              }
              COREACCESS::operator=((char *)this + 56, v34);
              COREACCESS::~COREACCESS((COREACCESS *)v34);
              COREACCESS::AcquireShared((DXGSWAPCHAINLOCKWITHDEVICE *)((char *)this + 56), 0);
              if ( *(_DWORD *)(v18 + 608) == 1 )
              {
                *((_BYTE *)this + 43) = 1;
              }
              else
              {
                COREACCESS::Release((DXGSWAPCHAINLOCKWITHDEVICE *)((char *)this + 56));
                v21 = -1073741130;
                WdLogSingleEntry2(3, v18);
                WdLogGlobalForLineNumber = 4422;
              }
              DXGAUTOMUTEX::Acquire((DXGSWAPCHAINLOCKWITHDEVICE *)((char *)this + 24));
              goto LABEL_20;
            }
            _m_prefetchw((const void *)(v18 + 64));
            v19 = *(_QWORD *)(v18 + 64);
            while ( v19 )
            {
              v20 = v19;
              v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(v18 + 64), v19 + 1, v19);
              if ( v20 == v19 )
              {
                v21 = 0;
                *((_BYTE *)this + 42) = 1;
                *((_QWORD *)this + 6) = v18;
                goto LABEL_16;
              }
            }
          }
        }
      }
      v18 = 0;
      goto LABEL_15;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1403a17a4  mov     [rsp+arg_10], rbx
0x1403a17a9  push    rbp
0x1403a17aa  push    rsi
0x1403a17ab  push    rdi
0x1403a17ac  push    r12
0x1403a17ae  push    r13
0x1403a17b0  push    r14
0x1403a17b2  push    r15
0x1403a17b4  sub     rsp, 0B0h
0x1403a17bb  mov     rax, cs:__security_cookie
0x1403a17c2  xor     rax, rsp
0x1403a17c5  mov     [rsp+0E8h+var_48], rax
0x1403a17cd  mov     rdi, rcx
0x1403a17d0  mov     [rsp+0E8h+var_98], r9b
0x1403a17d5  add     rcx, 18h; this
0x1403a17d9  mov     [rsp+0E8h+var_90], rdx
0x1403a17de  mov     r13b, r8b
0x1403a17e1  mov     rsi, rdx
0x1403a17e4  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1403a17e9  mov     rax, [rdi+8]
0x1403a17ed  xor     r14d, r14d
0x1403a17f0  mov     byte ptr [rdi+28h], 1
0x1403a17f4  cmp     [rax+30h], r14d
0x1403a17f8  jnz     loc_1403A1BDF
0x1403a17fe  cmp     byte ptr [rdi], 1
0x1403a1801  lea     r15, [rdi+10h]
0x1403a1805  jz      loc_1403A1A6C
0x1403a180b  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1403a1810  mov     rbp, rax
0x1403a1813  test    rsi, rsi
0x1403a1816  jz      loc_1403A1C7C
0x1403a181c  mov     [rsi], r14
0x1403a181f  lea     r14, [rax+0F8h]
0x1403a1826  mov     rcx, r14; this
0x1403a1829  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x1403a182e  mov     rax, [rdi+8]
0x1403a1832  mov     esi, 3
0x1403a1837  mov     cl, [r15]
0x1403a183a  neg     cl
0x1403a183c  sbb     rdx, rdx
0x1403a183f  and     edx, 30h
0x1403a1842  mov     r12d, [rdx+rax+60h]
0x1403a1847  mov     eax, r12d
0x1403a184a  shr     eax, 6
0x1403a184d  and     eax, 0FFFFFFh
0x1403a1852  cmp     eax, [rbp+128h]
0x1403a1858  jnb     short loc_1403A18BE
0x1403a185a  mov     r8, [rbp+118h]
0x1403a1861  mov     ecx, r12d
0x1403a1864  mov     ebx, eax
0x1403a1866  add     rbx, rbx
0x1403a1869  shr     ecx, 19h
0x1403a186c  and     ecx, 60h
0x1403a186f  mov     edx, [r8+rbx*8+8]
0x1403a1874  mov     eax, edx
0x1403a1876  and     eax, 60h
0x1403a1879  cmp     cl, al
0x1403a187b  jnz     short loc_1403A18BE
0x1403a187d  bt      edx, 0Dh
0x1403a1881  jb      short loc_1403A18BE
0x1403a1883  and     edx, 1Fh
0x1403a1886  jz      short loc_1403A18BE
0x1403a1888  cmp     edx, esi
0x1403a188a  jnz     loc_1403A1C07
0x1403a1890  mov     rbx, [r8+rbx*8]
0x1403a1894  test    rbx, rbx
0x1403a1897  jz      short loc_1403A18C0
0x1403a1899  prefetchw byte ptr [rbx+40h]
0x1403a189d  mov     rax, [rbx+40h]
0x1403a18a1  test    rax, rax
0x1403a18a4  jz      short loc_1403A18BE
0x1403a18a6  lea     rcx, [rax+1]
0x1403a18aa  lock cmpxchg [rbx+40h], rcx
0x1403a18b0  jnz     short loc_1403A18A1
0x1403a18b2  xor     ebp, ebp
0x1403a18b4  mov     byte ptr [rdi+2Ah], 1
0x1403a18b8  mov     [rdi+30h], rbx
0x1403a18bc  jmp     short loc_1403A18E3
0x1403a18be  xor     ebx, ebx
0x1403a18c0  mov     rdx, r12
0x1403a18c3  mov     r8, rbp
0x1403a18c6  mov     ecx, esi
0x1403a18c8  call    cs:__imp_WdLogSingleEntry2
0x1403a18cf  nop     dword ptr [rax+rax+00h]
0x1403a18d4  mov     cs:WdLogGlobalForLineNumber, 111Dh
0x1403a18de  mov     ebp, 0C000000Dh
0x1403a18e3  lock dec dword ptr [r14+10h]
0x1403a18e8  xor     edx, edx
0x1403a18ea  mov     rcx, r14
0x1403a18ed  call    cs:__imp_ExReleasePushLockSharedEx
0x1403a18f4  nop     dword ptr [rax+rax+00h]
0x1403a18f9  call    cs:__imp_KeLeaveCriticalRegion
0x1403a1900  nop     dword ptr [rax+rax+00h]
0x1403a1905  test    rbx, rbx
0x1403a1908  jnz     short loc_1403A1983
0x1403a190a  xor     r13d, r13d
0x1403a190d  jmp     short loc_1403A1945
0x1403a190f  mov     rcx, r14; this
0x1403a1912  call    ?Release@COREACCESS@@QEAAXXZ; COREACCESS::Release(void)
0x1403a1917  mov     rbp, 0FFFFFFFFC00002B6h
0x1403a191e  mov     r8, rbp
0x1403a1921  mov     rdx, rbx
0x1403a1924  mov     ecx, esi
0x1403a1926  call    cs:__imp_WdLogSingleEntry2
0x1403a192d  nop     dword ptr [rax+rax+00h]
0x1403a1932  mov     cs:WdLogGlobalForLineNumber, 1146h
0x1403a193c  lea     rcx, [rdi+18h]; this
0x1403a1940  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1403a1945  test    ebp, ebp
0x1403a1947  jns     loc_1403A1BB4
0x1403a194d  mov     rcx, rdi; this
0x1403a1950  call    ?Release@DXGSWAPCHAINLOCKWITHDEVICE@@QEAAXXZ; DXGSWAPCHAINLOCKWITHDEVICE::Release(void)
0x1403a1955  mov     eax, ebp
0x1403a1957  mov     rcx, [rsp+0E8h+var_48]
0x1403a195f  xor     rcx, rsp; StackCookie
0x1403a1962  call    __security_check_cookie
0x1403a1967  mov     rbx, [rsp+0E8h+arg_10]
0x1403a196f  add     rsp, 0B0h
0x1403a1976  pop     r15
0x1403a1978  pop     r14
0x1403a197a  pop     r13
0x1403a197c  pop     r12
0x1403a197e  pop     rdi
0x1403a197f  pop     rsi
0x1403a1980  pop     rbp
0x1403a1981  retn
0x1403a1983  test    r13b, r13b
0x1403a1986  jz      short loc_1403A190A
0x1403a1988  lea     rcx, [rdi+18h]; this
0x1403a198c  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x1403a1991  mov     r14, [rbx+10h]
0x1403a1995  lea     rcx, [r14+60h]; Event
0x1403a1999  call    cs:__imp_KeReadStateEvent
0x1403a19a0  nop     dword ptr [rax+rax+00h]
0x1403a19a5  xor     r13d, r13d
0x1403a19a8  test    eax, eax
0x1403a19aa  jnz     short loc_1403A19C9
0x1403a19ac  xor     r9d, r9d; Alertable
0x1403a19af  mov     [rsp+0E8h+Timeout], r13; Timeout
0x1403a19b4  xor     r8d, r8d; WaitMode
0x1403a19b7  lea     rcx, [r14+60h]; Object
0x1403a19bb  xor     edx, edx; WaitReason
0x1403a19bd  call    cs:__imp_KeWaitForSingleObject
0x1403a19c4  nop     dword ptr [rax+rax+00h]
0x1403a19c9  call    Feature_IdSwapChainUserModeSync__private_IsEnabledDeviceUsageNoInline
0x1403a19ce  test    eax, eax
0x1403a19d0  jnz     loc_1403A1ACC
0x1403a19d6  call    cs:__imp_KeEnterCriticalRegion
0x1403a19dd  nop     dword ptr [rax+rax+00h]
0x1403a19e2  mov     rcx, [rbx+88h]; Resource
0x1403a19e9  xor     edx, edx; Wait
0x1403a19eb  call    cs:__imp_ExAcquireResourceSharedLite
0x1403a19f2  nop     dword ptr [rax+rax+00h]
0x1403a19f7  test    al, al
0x1403a19f9  jz      loc_1403A1B36
0x1403a19ff  mov     byte ptr [rdi+29h], 1
0x1403a1a03  mov     rax, [rbx+10h]
0x1403a1a07  mov     rcx, [rax+10h]
0x1403a1a0b  mov     [rsp+0E8h+var_78], rcx
0x1403a1a10  mov     [rsp+0E8h+var_70], r13b
0x1403a1a15  mov     [rsp+0E8h+var_68], r13
0x1403a1a1d  test    rcx, rcx
0x1403a1a20  jz      short loc_1403A1A30
0x1403a1a22  lock inc qword ptr [rcx+18h]
0x1403a1a27  mov     [rsp+0E8h+var_80], 0FFFFFFFFFFFFFFFFh
0x1403a1a30  lea     r14, [rdi+38h]
0x1403a1a34  mov     rcx, r14
0x1403a1a37  lea     rdx, [rsp+0E8h+var_88]
0x1403a1a3c  call    ??4COREACCESS@@QEAAAEAV0@$$QEAV0@@Z; COREACCESS::operator=(COREACCESS &&)
0x1403a1a41  lea     rcx, [rsp+0E8h+var_88]; this
0x1403a1a46  call    ??1COREACCESS@@QEAA@XZ; COREACCESS::~COREACCESS(void)
0x1403a1a4b  xor     edx, edx; char *
0x1403a1a4d  mov     rcx, r14; this
0x1403a1a50  call    ?AcquireShared@COREACCESS@@QEAAXPEBD@Z; COREACCESS::AcquireShared(char const *)
0x1403a1a55  mov     eax, [rbx+260h]
0x1403a1a5b  cmp     eax, 1
0x1403a1a5e  jnz     loc_1403A190F
0x1403a1a64  mov     [rdi+2Bh], al
0x1403a1a67  jmp     loc_1403A193C
0x1403a1a6c  lea     rbx, [rax+0A0h]
0x1403a1a73  cmp     [r15], r14b
0x1403a1a76  jz      loc_1403A1B2D
0x1403a1a7c  mov     rbx, [rbx]
0x1403a1a7f  call    cs:__imp_PsGetCurrentProcess
0x1403a1a86  nop     dword ptr [rax+rax+00h]
0x1403a1a8b  cmp     rax, rbx
0x1403a1a8e  jz      loc_1403A180B
0x1403a1a94  call    cs:__imp_PsGetCurrentProcessId
0x1403a1a9b  nop     dword ptr [rax+rax+00h]
0x1403a1aa0  mov     rdx, [rdi+8]
0x1403a1aa4  mov     ecx, 3
0x1403a1aa9  mov     r8, rax
0x1403a1aac  call    cs:__imp_WdLogSingleEntry2
0x1403a1ab3  nop     dword ptr [rax+rax+00h]
0x1403a1ab8  mov     eax, 0C0000022h
0x1403a1abd  mov     cs:WdLogGlobalForLineNumber, 10F5h
0x1403a1ac7  jmp     loc_1403A1957
0x1403a1acc  cmp     [rsp+0E8h+var_98], r13b
0x1403a1ad1  jz      loc_1403A19D6
0x1403a1ad7  call    cs:__imp_KeEnterCriticalRegion
0x1403a1ade  nop     dword ptr [rax+rax+00h]
0x1403a1ae3  mov     rcx, [rbx+88h]; Resource
0x1403a1aea  xor     edx, edx; Wait
0x1403a1aec  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403a1af3  nop     dword ptr [rax+rax+00h]
0x1403a1af8  test    al, al
0x1403a1afa  jnz     loc_1403A19FF
0x1403a1b00  mov     rcx, [rbx+10h]
0x1403a1b04  mov     rcx, [rcx+10h]; this
0x1403a1b08  call    ?TryWakeUpFromD3State@DXGADAPTER@@QEAAEXZ; DXGADAPTER::TryWakeUpFromD3State(void)
0x1403a1b0d  cmp     cs:bTracingEnabled, r13b
0x1403a1b14  jnz     short loc_1403A1B90
0x1403a1b16  mov     rcx, [rbx+88h]; Resource
0x1403a1b1d  mov     dl, 1; Wait
0x1403a1b1f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403a1b26  nop     dword ptr [rax+rax+00h]
0x1403a1b2b  jmp     short loc_1403A1B61
0x1403a1b2d  lea     rbx, [rax+70h]
0x1403a1b31  jmp     loc_1403A1A7C
0x1403a1b36  mov     rcx, [rbx+10h]
0x1403a1b3a  mov     rcx, [rcx+10h]; this
0x1403a1b3e  call    ?TryWakeUpFromD3State@DXGADAPTER@@QEAAEXZ; DXGADAPTER::TryWakeUpFromD3State(void)
0x1403a1b43  cmp     cs:bTracingEnabled, r13b
0x1403a1b4a  jnz     short loc_1403A1B73
0x1403a1b4c  mov     rcx, [rbx+88h]; Resource
0x1403a1b53  mov     dl, 1; Wait
0x1403a1b55  call    cs:__imp_ExAcquireResourceSharedLite
0x1403a1b5c  nop     dword ptr [rax+rax+00h]
0x1403a1b61  mov     rcx, [rbx+10h]
0x1403a1b65  mov     rcx, [rcx+10h]; this
0x1403a1b69  call    ?EnableD3Requests@DXGADAPTER@@QEAAXXZ; DXGADAPTER::EnableD3Requests(void)
0x1403a1b6e  jmp     loc_1403A19FF
0x1403a1b73  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403a1b7a  jz      short loc_1403A1B4C
0x1403a1b7c  mov     r9d, 28h ; '('
0x1403a1b82  lea     rdx, EventBlockThread
0x1403a1b89  call    McTemplateK0q_EtwWriteTransfer
0x1403a1b8e  jmp     short loc_1403A1B4C
0x1403a1b90  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403a1b97  jz      loc_1403A1B16
0x1403a1b9d  mov     r9d, 28h ; '('
0x1403a1ba3  lea     rdx, EventBlockThread
0x1403a1baa  call    McTemplateK0q_EtwWriteTransfer
0x1403a1baf  jmp     loc_1403A1B16
0x1403a1bb4  mov     rdx, [rdi+8]
0x1403a1bb8  cmp     [rdx+30h], r13d
0x1403a1bbc  jnz     loc_1403A1C5A
0x1403a1bc2  mov     al, [r15]
0x1403a1bc5  neg     al
0x1403a1bc7  mov     rax, [rsp+0E8h+var_90]
0x1403a1bcc  sbb     rcx, rcx
0x1403a1bcf  and     ecx, 30h
0x1403a1bd2  mov     [rcx+rdx+68h], rbx
0x1403a1bd7  mov     [rax], rbx
0x1403a1bda  jmp     loc_1403A1955
0x1403a1bdf  mov     rdx, rax
0x1403a1be2  mov     ecx, 3
0x1403a1be7  call    cs:__imp_WdLogSingleEntry1
0x1403a1bee  nop     dword ptr [rax+rax+00h]
0x1403a1bf3  mov     eax, 0C0000056h
0x1403a1bf8  mov     cs:WdLogGlobalForLineNumber, 10ECh
0x1403a1c02  jmp     loc_1403A1957
0x1403a1c07  mov     ecx, 2
0x1403a1c0c  call    cs:__imp_WdLogSingleEntry0
0x1403a1c13  nop     dword ptr [rax+rax+00h]
0x1403a1c18  xor     ebx, ebx
0x1403a1c1a  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x1403a1c21  mov     [rsp+0E8h+var_A8], rbx
0x1403a1c26  mov     eax, 13Eh
0x1403a1c2b  mov     [rsp+0E8h+var_B0], rbx
0x1403a1c30  or      r8d, 0FFFFFFFFh
0x1403a1c34  mov     [rsp+0E8h+var_B8], rbx
0x1403a1c39  mov     edx, 40000h
0x1403a1c3e  mov     [rsp+0E8h+var_C0], rbx
0x1403a1c43  xor     ecx, ecx
0x1403a1c45  mov     [rsp+0E8h+Timeout], rax
0x1403a1c4a  mov     cs:WdLogGlobalForLineNumber, eax
0x1403a1c50  call    DxgkLogInternalTriageEvent
0x1403a1c55  jmp     loc_1403A18C0
0x1403a1c5a  mov     ecx, esi
0x1403a1c5c  call    cs:__imp_WdLogSingleEntry1
0x1403a1c63  nop     dword ptr [rax+rax+00h]
0x1403a1c68  mov     cs:WdLogGlobalForLineNumber, 1156h
0x1403a1c72  mov     ebp, 0C0000056h
0x1403a1c77  jmp     loc_1403A194D
0x1403a1c7c  xor     eax, eax
0x1403a1c7e  jmp     loc_1403A1957
```

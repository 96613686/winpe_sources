# InitializeServerQuota(void)

- ea: `0x14000b544`
- end: `0x14000b8eb`
- name: `?InitializeServerQuota@@YAKXZ`
- size: `935`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400472a0`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140008d50`
- `0x14000b484`
- `0x14000b544`
- `0x14000c5ec`
- `0x14004ecd4`
- `0x140065df8`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000b5ba`
- `KERNEL32!GetLastError` at `0x14000b746`
- `KERNEL32!GetLastError` at `0x14000b79d`
- `KERNEL32!GetLastError` at `0x14000b7f6`
- `KERNEL32!GetLastError` at `0x14000b845`
- `KERNEL32!GetLastError` at `0x14000b89c`
- `KERNEL32!GetLastError` at `0x14000b5ba`
- `KERNEL32!GetLastError` at `0x14000b746`
- `KERNEL32!GetLastError` at `0x14000b79d`
- `KERNEL32!GetLastError` at `0x14000b7f6`
- `KERNEL32!GetLastError` at `0x14000b845`
- `KERNEL32!GetLastError` at `0x14000b89c`
- `KERNEL32!CloseHandle` at `0x14000b7d4`
- `KERNEL32!CloseHandle` at `0x14000b823`
- `KERNEL32!CloseHandle` at `0x14000b87a`
- `KERNEL32!CloseHandle` at `0x14000b7d4`
- `KERNEL32!CloseHandle` at `0x14000b823`
- `KERNEL32!CloseHandle` at `0x14000b87a`
- `KERNEL32!EnterCriticalSection` at `0x14000b6aa`
- `KERNEL32!EnterCriticalSection` at `0x14000b6aa`
- `KERNEL32!LeaveCriticalSection` at `0x14000b6c2`
- `KERNEL32!LeaveCriticalSection` at `0x14000b6c2`
- `KERNEL32!CreateEventW` at `0x14000b5a8`
- `KERNEL32!CreateEventW` at `0x14000b5a8`

## pseudocode

```c
__int64 InitializeServerQuota(void)
{
  CFaxArchiving *v0; // rcx
  DWORD v1; // eax
  unsigned int v2; // ebx
  CMapDeviceId *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  CFaxArchiving *v6; // rcx
  CFaxConfiguration *v7; // rdx
  unsigned int FullArchiveSize; // eax
  __int64 v9; // rdx
  struct _SECURITY_ATTRIBUTES *v10; // rcx
  HANDLE ThreadAndRefCount; // rsi
  HANDLE v12; // rdi
  DWORD LastError; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  __int64 v18; // [rsp+20h] [rbp-68h]
  unsigned int v19; // [rsp+20h] [rbp-68h]
  unsigned int v20[3]; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int16 v21[14]; // [rsp+3Ch] [rbp-4Ch] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  v20[0] = 0;
  g_hArchiveQuotaWarningEvent = CreateEventW(0, 0, 0, 0);
  if ( g_hArchiveQuotaWarningEvent )
  {
    *((_QWORD *)g_pFaxConfig + 7) = -1;
    v5 = CFaxArchiving::Init(v0);
    v2 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v5);
      }
      v20[2] = v2;
      v21[0] = 0;
      StringCchPrintfW(v21, 0xCu, L"%ld", v2);
      v18 = *((_QWORD *)g_pFaxConfig + 6);
      FaxLog(1, 1, 2, 3221257584LL);
      EnterCriticalSection(&g_CsConfig);
      *((_DWORD *)g_pFaxConfig + 2) |= 7u;
      LeaveCriticalSection(&g_CsConfig);
      v2 = 0;
    }
    else
    {
      v7 = g_pFaxConfig;
      if ( *((_DWORD *)g_pFaxConfig + 11) )
      {
        FullArchiveSize = CFaxArchiving::GetFullArchiveSize(v6, (unsigned __int64 *)g_pFaxConfig + 7, 0, 0);
        v2 = FullArchiveSize;
        if ( FullArchiveSize )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              168,
              &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
              FullArchiveSize);
          }
          *((_QWORD *)g_pFaxConfig + 7) = -1;
        }
      }
    }
    ThreadAndRefCount = CreateThreadAndRefCount(
                          (struct _SECURITY_ATTRIBUTES *)v6,
                          (__int64)v7,
                          (unsigned int (*)(void *))FaxArchiveQuotaWarningThread,
                          0,
                          v18,
                          v20);
    if ( ThreadAndRefCount )
    {
      v12 = CreateThreadAndRefCount(v10, v9, (unsigned int (*)(void *))FaxArchiveQuotaAutoDeleteThread, 0, v19, v20);
      if ( !v12 )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            170,
            &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
            LastError);
        }
      }
      if ( !CloseHandle(ThreadAndRefCount)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = GetLastError();
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          171,
          &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
          ThreadAndRefCount,
          v14);
      }
      if ( v12
        && !CloseHandle(v12)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = GetLastError();
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v12, v15);
      }
    }
    else
    {
      v1 = GetLastError();
      v2 = v1;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v4 = 169;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 166;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v1);
    }
  }
  if ( v2 && g_hArchiveQuotaWarningEvent )
  {
    if ( !CloseHandle(g_hArchiveQuotaWarningEvent)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = GetLastError();
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        173,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        g_hArchiveQuotaWarningEvent,
        v16);
    }
    g_hArchiveQuotaWarningEvent = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x14000b544  push    rbx
0x14000b546  push    rsi
0x14000b547  push    rdi
0x14000b548  push    r13
0x14000b54a  push    r15
0x14000b54c  sub     rsp, 60h
0x14000b550  mov     rax, cs:__security_cookie
0x14000b557  xor     rax, rsp
0x14000b55a  mov     [rsp+88h+var_30], rax
0x14000b55f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b566  lea     r15, WPP_GLOBAL_Control
0x14000b56d  lea     r13, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000b574  cmp     rcx, r15
0x14000b577  jz      short loc_14000B596
0x14000b579  test    byte ptr [rcx+1Ch], 4
0x14000b57d  jz      short loc_14000B596
0x14000b57f  cmp     byte ptr [rcx+19h], 5
0x14000b583  jb      short loc_14000B596
0x14000b585  mov     rcx, [rcx+10h]
0x14000b589  mov     edx, 0A5h
0x14000b58e  mov     r8, r13
0x14000b591  call    WPP_SF_
0x14000b596  xor     r9d, r9d; lpName
0x14000b599  mov     [rsp+88h+var_58], 0
0x14000b5a1  xor     r8d, r8d; bInitialState
0x14000b5a4  xor     edx, edx; bManualReset
0x14000b5a6  xor     ecx, ecx; lpEventAttributes
0x14000b5a8  call    cs:__imp_CreateEventW
0x14000b5ae  mov     cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA, rax; void * g_hArchiveQuotaWarningEvent
0x14000b5b5  test    rax, rax
0x14000b5b8  jnz     short loc_14000B5FF
0x14000b5ba  call    cs:__imp_GetLastError
0x14000b5c0  mov     ebx, eax
0x14000b5c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b5c9  cmp     rcx, r15
0x14000b5cc  jz      loc_14000B86A
0x14000b5d2  test    byte ptr [rcx+1Ch], 4
0x14000b5d6  jz      loc_14000B86A
0x14000b5dc  cmp     byte ptr [rcx+19h], 2
0x14000b5e0  jb      loc_14000B86A
0x14000b5e6  mov     edx, 0A6h
0x14000b5eb  mov     rcx, [rcx+10h]
0x14000b5ef  mov     r9d, eax
0x14000b5f2  mov     r8, r13
0x14000b5f5  call    WPP_SF_d
0x14000b5fa  jmp     loc_14000B86A
0x14000b5ff  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000b606  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000b60a  mov     [rax+38h], rdi
0x14000b60e  call    ?Init@CFaxArchiving@@QEAAKXZ; CFaxArchiving::Init(void)
0x14000b613  mov     ebx, eax
0x14000b615  test    eax, eax
0x14000b617  jz      loc_14000B6CC
0x14000b61d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b624  cmp     rcx, r15
0x14000b627  jz      short loc_14000B649
0x14000b629  test    byte ptr [rcx+1Ch], 4
0x14000b62d  jz      short loc_14000B649
0x14000b62f  cmp     byte ptr [rcx+19h], 2
0x14000b633  jb      short loc_14000B649
0x14000b635  mov     rcx, [rcx+10h]
0x14000b639  mov     edx, 0A7h
0x14000b63e  mov     r9d, eax
0x14000b641  mov     r8, r13
0x14000b644  call    WPP_SF_d
0x14000b649  xor     eax, eax
0x14000b64b  mov     [rsp+88h+var_50], ebx
0x14000b64f  mov     r9d, ebx
0x14000b652  mov     [rsp+88h+var_4C], ax
0x14000b657  lea     r8, aLd; "%ld"
0x14000b65e  lea     rcx, [rsp+88h+var_4C]; unsigned __int16 *
0x14000b663  lea     edx, [rax+0Ch]; unsigned __int64
0x14000b666  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b66b  xor     ecx, ecx
0x14000b66d  lea     rdx, [rsp+88h+var_4C]
0x14000b672  test    eax, eax
0x14000b674  mov     r9d, 0C0007D70h
0x14000b67a  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000b681  cmovs   rdx, rcx
0x14000b685  mov     [rsp+88h+var_60], rdx
0x14000b68a  mov     rcx, [rax+30h]
0x14000b68e  mov     [rsp+88h+var_68], rcx
0x14000b693  mov     ecx, 1
0x14000b698  mov     edx, ecx
0x14000b69a  lea     r8d, [rcx+1]
0x14000b69e  call    FaxLog
0x14000b6a3  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000b6aa  call    cs:__imp_EnterCriticalSection
0x14000b6b0  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000b6b7  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000b6be  or      dword ptr [rax+8], 7
0x14000b6c2  call    cs:__imp_LeaveCriticalSection
0x14000b6c8  xor     ebx, ebx
0x14000b6ca  jmp     short loc_14000B725
0x14000b6cc  mov     rdx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000b6d3  cmp     dword ptr [rdx+2Ch], 0
0x14000b6d7  jz      short loc_14000B725
0x14000b6d9  add     rdx, 38h ; '8'; unsigned __int64 *
0x14000b6dd  xor     r9d, r9d; unsigned int
0x14000b6e0  xor     r8d, r8d; unsigned __int16 *
0x14000b6e3  call    ?GetFullArchiveSize@CFaxArchiving@@QEAAKPEA_KPEAGK@Z; CFaxArchiving::GetFullArchiveSize(unsigned __int64 *,ushort *,ulong)
0x14000b6e8  mov     ebx, eax
0x14000b6ea  test    eax, eax
0x14000b6ec  jz      short loc_14000B725
0x14000b6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6f5  cmp     rcx, r15
0x14000b6f8  jz      short loc_14000B71A
0x14000b6fa  test    byte ptr [rcx+1Ch], 4
0x14000b6fe  jz      short loc_14000B71A
0x14000b700  cmp     byte ptr [rcx+19h], 2
0x14000b704  jb      short loc_14000B71A
0x14000b706  mov     rcx, [rcx+10h]
0x14000b70a  mov     edx, 0A8h
0x14000b70f  mov     r9d, eax
0x14000b712  mov     r8, r13
0x14000b715  call    WPP_SF_d
0x14000b71a  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000b721  mov     [rax+38h], rdi
0x14000b725  lea     rax, [rsp+88h+var_58]
0x14000b72a  xor     r9d, r9d; void *
0x14000b72d  lea     r8, ?FaxArchiveQuotaWarningThread@@YAKPEAX@Z; unsigned int (*)(void *)
0x14000b734  mov     [rsp+88h+var_60], rax; unsigned int *
0x14000b739  call    ?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z; CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)
0x14000b73e  mov     rsi, rax
0x14000b741  test    rax, rax
0x14000b744  jnz     short loc_14000B77C
0x14000b746  call    cs:__imp_GetLastError
0x14000b74c  mov     ebx, eax
0x14000b74e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b755  cmp     rcx, r15
0x14000b758  jz      loc_14000B86A
0x14000b75e  test    byte ptr [rcx+1Ch], 4
0x14000b762  jz      loc_14000B86A
0x14000b768  cmp     byte ptr [rcx+19h], 2
0x14000b76c  jb      loc_14000B86A
0x14000b772  mov     edx, 0A9h
0x14000b777  jmp     loc_14000B5EB
0x14000b77c  lea     rax, [rsp+88h+var_58]
0x14000b781  xor     r9d, r9d; void *
0x14000b784  lea     r8, ?FaxArchiveQuotaAutoDeleteThread@@YAKPEAX@Z; unsigned int (*)(void *)
0x14000b78b  mov     [rsp+88h+var_60], rax; unsigned int *
0x14000b790  call    ?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z; CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)
0x14000b795  mov     rdi, rax
0x14000b798  test    rax, rax
0x14000b79b  jnz     short loc_14000B7D1
0x14000b79d  call    cs:__imp_GetLastError
0x14000b7a3  mov     ebx, eax
0x14000b7a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b7ac  cmp     rcx, r15
0x14000b7af  jz      short loc_14000B7D1
0x14000b7b1  test    byte ptr [rcx+1Ch], 4
0x14000b7b5  jz      short loc_14000B7D1
0x14000b7b7  cmp     byte ptr [rcx+19h], 2
0x14000b7bb  jb      short loc_14000B7D1
0x14000b7bd  mov     rcx, [rcx+10h]
0x14000b7c1  mov     edx, 0AAh
0x14000b7c6  mov     r9d, eax
0x14000b7c9  mov     r8, r13
0x14000b7cc  call    WPP_SF_d
0x14000b7d1  mov     rcx, rsi; hObject
0x14000b7d4  call    cs:__imp_CloseHandle
0x14000b7da  test    eax, eax
0x14000b7dc  jnz     short loc_14000B81B
0x14000b7de  mov     rax, cs:WPP_GLOBAL_Control
0x14000b7e5  cmp     rax, r15
0x14000b7e8  jz      short loc_14000B81B
0x14000b7ea  test    byte ptr [rax+1Ch], 4
0x14000b7ee  jz      short loc_14000B81B
0x14000b7f0  cmp     byte ptr [rax+19h], 2
0x14000b7f4  jb      short loc_14000B81B
0x14000b7f6  call    cs:__imp_GetLastError
0x14000b7fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b803  mov     edx, 0ABh
0x14000b808  mov     r9, rsi
0x14000b80b  mov     dword ptr [rsp+88h+var_68], eax
0x14000b80f  mov     r8, r13
0x14000b812  mov     rcx, [rcx+10h]
0x14000b816  call    WPP_SF_qD
0x14000b81b  test    rdi, rdi
0x14000b81e  jz      short loc_14000B86A
0x14000b820  mov     rcx, rdi; hObject
0x14000b823  call    cs:__imp_CloseHandle
0x14000b829  test    eax, eax
0x14000b82b  jnz     short loc_14000B86A
0x14000b82d  mov     rax, cs:WPP_GLOBAL_Control
0x14000b834  cmp     rax, r15
0x14000b837  jz      short loc_14000B86A
0x14000b839  test    byte ptr [rax+1Ch], 4
0x14000b83d  jz      short loc_14000B86A
0x14000b83f  cmp     byte ptr [rax+19h], 2
0x14000b843  jb      short loc_14000B86A
0x14000b845  call    cs:__imp_GetLastError
0x14000b84b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b852  mov     edx, 0ACh
0x14000b857  mov     r9, rdi
0x14000b85a  mov     dword ptr [rsp+88h+var_68], eax
0x14000b85e  mov     r8, r13
0x14000b861  mov     rcx, [rcx+10h]
0x14000b865  call    WPP_SF_qD
0x14000b86a  test    ebx, ebx
0x14000b86c  jz      short loc_14000B8D0
0x14000b86e  mov     rcx, cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA; hObject
0x14000b875  test    rcx, rcx
0x14000b878  jz      short loc_14000B8D0
0x14000b87a  call    cs:__imp_CloseHandle
0x14000b880  test    eax, eax
0x14000b882  jnz     short loc_14000B8C5
0x14000b884  mov     rax, cs:WPP_GLOBAL_Control
0x14000b88b  cmp     rax, r15
0x14000b88e  jz      short loc_14000B8C5
0x14000b890  test    byte ptr [rax+1Ch], 4
0x14000b894  jz      short loc_14000B8C5
0x14000b896  cmp     byte ptr [rax+19h], 2
0x14000b89a  jb      short loc_14000B8C5
0x14000b89c  call    cs:__imp_GetLastError
0x14000b8a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b8a9  mov     edx, 0ADh
0x14000b8ae  mov     r9, cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA; void * g_hArchiveQuotaWarningEvent
0x14000b8b5  mov     r8, r13
0x14000b8b8  mov     dword ptr [rsp+88h+var_68], eax
0x14000b8bc  mov     rcx, [rcx+10h]
0x14000b8c0  call    WPP_SF_qD
0x14000b8c5  mov     cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA, 0; void * g_hArchiveQuotaWarningEvent
0x14000b8d0  mov     eax, ebx
0x14000b8d2  mov     rcx, [rsp+88h+var_30]
0x14000b8d7  xor     rcx, rsp; StackCookie
0x14000b8da  call    __security_check_cookie
0x14000b8df  add     rsp, 60h
0x14000b8e3  pop     r15
0x14000b8e5  pop     r13
0x14000b8e7  pop     rdi
0x14000b8e8  pop     rsi
0x14000b8e9  pop     rbx
0x14000b8ea  retn
```

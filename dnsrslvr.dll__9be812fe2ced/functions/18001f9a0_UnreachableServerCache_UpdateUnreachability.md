# UnreachableServerCache_UpdateUnreachability

- ea: `0x18001f9a0`
- end: `0x18001fe6b`
- name: `UnreachableServerCache_UpdateUnreachability`
- size: `1227`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int16, __int64, int, int, int, int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001ec50`
- `0x18001f9a0`
- `0x1800213b0`
- `0x1800226e0`
- `0x18007a8a8`
- `0x180086700`
- `0x180086b1c`
- `0x180087f74`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x18001f9b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fbbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fe27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fbbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fe27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fb95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fbd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fb95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fbd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fa91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fa91`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001fc09`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001fc09`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fba8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fba8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fb4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fb4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fcde`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fcfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fd62`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fcde`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fcfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fd62`

## string_xrefs

- `0x18001fbfc`: `dnsrslvr.dll`
- `0x18001fc62`: `dns.msftncsi.com`

## pseudocode

```c
__int64 __fastcall UnreachableServerCache_UpdateUnreachability(
        _WORD *a1,
        unsigned __int16 a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        unsigned __int64 a8,
        __int64 a9)
{
  DWORD LastError; // edi
  unsigned int v11; // ebp
  _WORD *v12; // rbx
  int v13; // r8d
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 *v16; // rcx
  __int64 *i; // rax
  HANDLE ProcessHeap; // rax
  _WORD *v19; // rax
  __int64 v20; // r13
  _WORD *v21; // rcx
  void *v22; // rbx
  HANDLE v23; // rax
  HANDLE v24; // rax
  wchar_t *v26; // rcx
  void *StringCopy_W; // rax
  unsigned int v28; // ebp
  unsigned __int64 v29; // rsi
  __int64 v30; // rcx
  _WORD *v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rcx
  HMODULE hLibModule; // [rsp+58h] [rbp-50h]

  LastError = 0;
  v11 = a2;
  v12 = a1;
  if ( !DnsGlobals[94] && (a3 & 0x2000000000000LL) == 0 && (a3 & 0x400) == 0 && a7 != 1223 && dword_1800AB914 )
  {
    hLibModule = 0;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_Sdidddd((_DWORD)a1, a2, a3, (_DWORD)a1, a2, a3, a4, a5, a6, a7);
    EnterCriticalSection(&stru_1800ABD68);
    LODWORD(v14) = dword_1800ABD9C;
    v15 = 16LL * (v11 % 0x35);
    v16 = (__int64 *)((char *)qword_1800ABD90 + v15);
    for ( i = *(__int64 **)((char *)qword_1800ABD90 + v15); i != v16; i = (__int64 *)*i )
    {
      v20 = (__int64)(i - 1);
      if ( *((_DWORD *)i + 4) == dword_1800ABD9C
        && *(_WORD *)(v20 + 28) == (_WORD)v11
        && *(_DWORD *)(v20 + 32) == a4
        && (!a4 || *(_DWORD *)(v20 + 36) == a5)
        && *(_DWORD *)(v20 + 40) == a6 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v20);
        goto LABEL_56;
      }
    }
    ProcessHeap = g_hProcessHeap;
    if ( !g_hProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      g_hProcessHeap = ProcessHeap;
    }
    v19 = HeapAlloc(ProcessHeap, 8u, 0x2F0u);
    v20 = (__int64)v19;
    if ( !v19 )
    {
      LastError = 14;
      goto LABEL_47;
    }
    v19[14] = v11;
    *((_DWORD *)v19 + 8) = a4;
    *((_DWORD *)v19 + 9) = a5;
    *((_DWORD *)v19 + 10) = a6;
    *((_DWORD *)v19 + 6) = dword_1800ABD9C;
    *(_DWORD *)v19 = 1;
    _InterlockedIncrement((volatile signed __int32 *)v19);
    v16 = (__int64 *)((char *)qword_1800ABD90 + v15);
    v14 = *(_QWORD *)((char *)qword_1800ABD90 + v15);
    if ( *(void **)(v14 + 8) != (char *)qword_1800ABD90 + v15 )
      __fastfail(3u);
    *((_QWORD *)v19 + 1) = v14;
    *((_QWORD *)v19 + 2) = v16;
    *(_QWORD *)(v14 + 8) = v19 + 4;
    *v16 = (__int64)(v19 + 4);
LABEL_56:
    v28 = 0;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SDlq((_DWORD)v16, v14, v13, (_DWORD)v12, a7, 0, v20);
    if ( *(_DWORD *)(v20 + 24) == dword_1800ABD9C )
    {
      if ( a7 == 1460
        || (v29 = (unsigned int)(a7 - 10014), (unsigned int)v29 <= 0x33)
        && (v33 = 0xC003301000001LL, _bittest64(&v33, v29)) )
      {
        *(_QWORD *)(v20 + 744) = GetTickCount64();
        if ( a8 > *(_QWORD *)(v20 + 64) && !*(_DWORD *)(v20 + 52) && !(unsigned int)IsAnyInterfaceInDormantMode() )
        {
          *(_DWORD *)(v20 + 56) = 1;
          v28 = 1;
        }
      }
      else
      {
        *(_QWORD *)(v20 + 744) = GetTickCount64();
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_(1035, 20, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids);
        *(_QWORD *)(v20 + 52) = 0;
        *(_QWORD *)(v20 + 64) = GetTickCount64();
        if ( v12 )
        {
          v30 = 2147483646;
          v31 = (_WORD *)(v20 + 72);
          v32 = 256;
          do
          {
            if ( !v30 )
              break;
            if ( !*v12 )
              break;
            *v31++ = *v12++;
            --v30;
            --v32;
          }
          while ( v32 );
          v21 = v31 - 1;
          if ( v32 )
            v21 = v31;
          *v21 = 0;
        }
      }
    }
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 22, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids, v28);
    if ( v28 )
    {
      hLibModule = LoadLibraryExW(L"dnsrslvr.dll", 0, 0x800u);
      if ( !hLibModule )
      {
        LastError = GetLastError();
LABEL_47:
        LeaveCriticalSection(&stru_1800ABD68);
        v22 = 0;
        goto LABEL_31;
      }
    }
    LeaveCriticalSection(&stru_1800ABD68);
    LastError = 0;
    if ( v28 )
    {
      v26 = (wchar_t *)(v20 + 72);
      if ( !*(_WORD *)(v20 + 72) && (!a9 || !*(_DWORD *)(a9 + 68) || (v26 = *(wchar_t **)(a9 + 112)) == 0) )
        v26 = L"dns.msftncsi.com";
      StringCopy_W = (void *)Dns_CreateStringCopy_W(v26);
      v22 = StringCopy_W;
      if ( StringCopy_W )
        UnreachableServerCache_InitiateBackgroundQuery((LPVOID)v20, StringCopy_W);
      else
        LastError = 14;
    }
    else
    {
      v22 = 0;
    }
LABEL_31:
    if ( v20 && _InterlockedExchangeAdd((volatile signed __int32 *)v20, 0xFFFFFFFF) == 1 )
    {
      v23 = g_hProcessHeap;
      if ( !g_hProcessHeap )
      {
        v23 = GetProcessHeap();
        g_hProcessHeap = v23;
      }
      HeapFree(v23, 0, (LPVOID)v20);
    }
    if ( hLibModule )
      FreeLibrary(hLibModule);
    if ( v22 )
    {
      v24 = g_hProcessHeap;
      if ( !g_hProcessHeap )
      {
        v24 = GetProcessHeap();
        g_hProcessHeap = v24;
      }
      HeapFree(v24, 0, v22);
    }
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 38, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18001f9a0  mov     [rsp+arg_10], r8
0x18001f9a5  push    rbx
0x18001f9a6  push    rbp
0x18001f9a7  push    rsi
0x18001f9a8  push    rdi
0x18001f9a9  push    r12
0x18001f9ab  push    r13
0x18001f9ad  push    r14
0x18001f9af  push    r15
0x18001f9b1  sub     rsp, 68h
0x18001f9b5  mov     rax, cs:__imp_DnsGlobals
0x18001f9bc  xor     edi, edi
0x18001f9be  mov     r12d, r9d
0x18001f9c1  movzx   ebp, dx
0x18001f9c4  mov     rbx, rcx
0x18001f9c7  cmp     [rax+178h], edi
0x18001f9cd  jnz     loc_18001FBDA
0x18001f9d3  bt      r8, 31h ; '1'
0x18001f9d8  jb      loc_18001FBDA
0x18001f9de  bt      r8, 0Ah
0x18001f9e3  jb      loc_18001FBDA
0x18001f9e9  mov     esi, [rsp+0A8h+arg_30]
0x18001f9f0  cmp     esi, 4C7h
0x18001f9f6  jz      loc_18001FBDA
0x18001f9fc  cmp     cs:dword_1800AB914, edi
0x18001fa02  jz      loc_18001FBDA
0x18001fa08  xor     eax, eax
0x18001fa0a  mov     [rsp+0A8h+var_58], rdi
0x18001fa0f  mov     [rsp+0A8h+hLibModule], rax
0x18001fa14  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001fa1b  mov     edi, ebp
0x18001fa1d  mov     r15d, [rsp+0A8h+arg_28]
0x18001fa25  mov     r14d, [rsp+0A8h+arg_20]
0x18001fa2d  jnz     loc_18001FDE0
0x18001fa33  lea     rcx, stru_1800ABD68; lpCriticalSection
0x18001fa3a  call    cs:__imp_EnterCriticalSection
0x18001fa40  mov     rcx, cs:qword_1800ABD90
0x18001fa47  mov     eax, 3521CFB3h
0x18001fa4c  mul     edi
0x18001fa4e  mov     eax, edi
0x18001fa50  sub     eax, edx
0x18001fa52  shr     eax, 1
0x18001fa54  add     eax, edx
0x18001fa56  mov     edx, cs:dword_1800ABD9C
0x18001fa5c  shr     eax, 5
0x18001fa5f  imul    eax, 35h ; '5'
0x18001fa62  sub     edi, eax
0x18001fa64  shl     rdi, 4
0x18001fa68  add     rcx, rdi
0x18001fa6b  mov     rax, [rcx]
0x18001fa6e  cmp     rax, rcx
0x18001fa71  jnz     short loc_18001FAE8
0x18001fa73  mov     rax, cs:g_hProcessHeap
0x18001fa7a  test    rax, rax
0x18001fa7d  jz      loc_18001FE27
0x18001fa83  mov     edx, 8; dwFlags
0x18001fa88  mov     r8d, 2F0h; dwBytes
0x18001fa8e  mov     rcx, rax; hHeap
0x18001fa91  call    cs:__imp_HeapAlloc
0x18001fa97  mov     r13, rax
0x18001fa9a  test    rax, rax
0x18001fa9d  jz      loc_18001FE39
0x18001faa3  mov     [rax+1Ch], bp
0x18001faa7  mov     [rax+20h], r12d
0x18001faab  mov     [rax+24h], r14d
0x18001faaf  mov     [rax+28h], r15d
0x18001fab3  mov     eax, cs:dword_1800ABD9C
0x18001fab9  mov     [r13+18h], eax
0x18001fabd  mov     dword ptr [r13+0], 1
0x18001fac5  lock inc dword ptr [r13+0]
0x18001faca  mov     rcx, cs:qword_1800ABD90
0x18001fad1  add     rcx, rdi
0x18001fad4  mov     rdx, [rcx]
0x18001fad7  cmp     [rdx+8], rcx
0x18001fadb  jz      loc_18001FC92
0x18001fae1  mov     ecx, 3
0x18001fae6  int     29h; Win8: RtlFailFast(ecx)
0x18001fae8  cmp     [rax+10h], edx
0x18001faeb  lea     r13, [rax-8]
0x18001faef  jnz     short loc_18001FAF8
0x18001faf1  cmp     [r13+1Ch], bp
0x18001faf6  jz      short loc_18001FB00
0x18001faf8  mov     rax, [rax]
0x18001fafb  jmp     loc_18001FA6E
0x18001fb00  cmp     [r13+20h], r12d
0x18001fb04  jnz     short loc_18001FAF8
0x18001fb06  test    r12d, r12d
0x18001fb09  jz      short loc_18001FB11
0x18001fb0b  cmp     [r13+24h], r14d
0x18001fb0f  jnz     short loc_18001FAF8
0x18001fb11  cmp     [r13+28h], r15d
0x18001fb15  jnz     short loc_18001FAF8
0x18001fb17  lock inc dword ptr [r13+0]
0x18001fb1c  jmp     loc_18001FCA4
0x18001fb21  test    r8, r8
0x18001fb24  lea     rcx, [rdx-2]
0x18001fb28  cmovnz  rcx, rdx
0x18001fb2c  mov     [rcx], r14w
0x18001fb30  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001fb37  jnz     loc_18001FE43
0x18001fb3d  test    ebp, ebp
0x18001fb3f  jnz     loc_18001FBFA
0x18001fb45  lea     rcx, stru_1800ABD68; lpCriticalSection
0x18001fb4c  call    cs:__imp_LeaveCriticalSection
0x18001fb52  mov     edi, r14d
0x18001fb55  test    ebp, ebp
0x18001fb57  jnz     loc_18001FC3C
0x18001fb5d  mov     ebx, edi
0x18001fb5f  test    r13, r13
0x18001fb62  jz      short loc_18001FB9B
0x18001fb64  mov     eax, 0FFFFFFFFh
0x18001fb69  lock xadd [r13+0], eax
0x18001fb6f  cmp     eax, 1
0x18001fb72  jnz     short loc_18001FB9B
0x18001fb74  mov     rax, cs:g_hProcessHeap
0x18001fb7b  test    rax, rax
0x18001fb7e  jnz     short loc_18001FB8D
0x18001fb80  call    cs:__imp_GetProcessHeap
0x18001fb86  mov     cs:g_hProcessHeap, rax
0x18001fb8d  mov     r8, r13; lpMem
0x18001fb90  xor     edx, edx; dwFlags
0x18001fb92  mov     rcx, rax; hHeap
0x18001fb95  call    cs:__imp_HeapFree
0x18001fb9b  mov     rax, [rsp+0A8h+hLibModule]
0x18001fba0  test    rax, rax
0x18001fba3  jz      short loc_18001FBAE
0x18001fba5  mov     rcx, rax; hLibModule
0x18001fba8  call    cs:__imp_FreeLibrary
0x18001fbae  test    rbx, rbx
0x18001fbb1  jz      short loc_18001FBDA
0x18001fbb3  mov     rax, cs:g_hProcessHeap
0x18001fbba  test    rax, rax
0x18001fbbd  jnz     short loc_18001FBCC
0x18001fbbf  call    cs:__imp_GetProcessHeap
0x18001fbc5  mov     cs:g_hProcessHeap, rax
0x18001fbcc  mov     r8, rbx; lpMem
0x18001fbcf  xor     edx, edx; dwFlags
0x18001fbd1  mov     rcx, rax; hHeap
0x18001fbd4  call    cs:__imp_HeapFree
0x18001fbda  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001fbe1  jnz     loc_18001FE09
0x18001fbe7  mov     eax, edi
0x18001fbe9  add     rsp, 68h
0x18001fbed  pop     r15
0x18001fbef  pop     r14
0x18001fbf1  pop     r13
0x18001fbf3  pop     r12
0x18001fbf5  pop     rdi
0x18001fbf6  pop     rsi
0x18001fbf7  pop     rbp
0x18001fbf8  pop     rbx
0x18001fbf9  retn
0x18001fbfa  xor     edx, edx; hFile
0x18001fbfc  lea     rcx, LibFileName; "dnsrslvr.dll"
0x18001fc03  mov     r8d, 800h; dwFlags
0x18001fc09  call    cs:__imp_LoadLibraryExW
0x18001fc0f  mov     [rsp+0A8h+hLibModule], rax
0x18001fc14  test    rax, rax
0x18001fc17  jnz     loc_18001FB45
0x18001fc1d  call    cs:__imp_GetLastError
0x18001fc23  mov     edi, eax
0x18001fc25  lea     rcx, stru_1800ABD68; lpCriticalSection
0x18001fc2c  call    cs:__imp_LeaveCriticalSection
0x18001fc32  mov     rbx, [rsp+0A8h+var_58]
0x18001fc37  jmp     loc_18001FB5F
0x18001fc3c  cmp     [r13+48h], di
0x18001fc41  lea     rcx, [r13+48h]
0x18001fc45  jnz     short loc_18001FC69
0x18001fc47  mov     rcx, [rsp+0A8h+arg_40]
0x18001fc4f  test    rcx, rcx
0x18001fc52  jz      short loc_18001FC62
0x18001fc54  cmp     [rcx+44h], edi
0x18001fc57  jz      short loc_18001FC62
0x18001fc59  mov     rcx, [rcx+70h]
0x18001fc5d  test    rcx, rcx
0x18001fc60  jnz     short loc_18001FC69
0x18001fc62  lea     rcx, aDnsMsftncsiCom; "dns.msftncsi.com"
0x18001fc69  call    Dns_CreateStringCopy_W
0x18001fc6e  mov     rbx, rax
0x18001fc71  test    rax, rax
0x18001fc74  jz      loc_18001FE61
0x18001fc7a  mov     r8, [rsp+0A8h+arg_10]
0x18001fc82  mov     rdx, rax
0x18001fc85  mov     rcx, r13
0x18001fc88  call    UnreachableServerCache_InitiateBackgroundQuery
0x18001fc8d  jmp     loc_18001FB5F
0x18001fc92  lea     rax, [r13+8]
0x18001fc96  mov     [rax], rdx
0x18001fc99  mov     [rax+8], rcx
0x18001fc9d  mov     [rdx+8], rax
0x18001fca1  mov     [rcx], rax
0x18001fca4  xor     r14d, r14d
0x18001fca7  mov     ebp, r14d
0x18001fcaa  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001fcb1  jnz     loc_18001FDC5
0x18001fcb7  mov     eax, cs:dword_1800ABD9C
0x18001fcbd  cmp     [r13+18h], eax
0x18001fcc1  jnz     loc_18001FB30
0x18001fcc7  cmp     esi, 5B4h
0x18001fccd  jz      loc_18001FD62
0x18001fcd3  add     esi, 0FFFFD8E2h
0x18001fcd9  cmp     esi, 33h ; '3'
0x18001fcdc  jbe     short loc_18001FD4E
0x18001fcde  call    cs:__imp_GetTickCount64
0x18001fce4  mov     [r13+2E8h], rax
0x18001fceb  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001fcf2  jnz     loc_18001FDAA
0x18001fcf8  mov     [r13+34h], r14
0x18001fcfc  call    cs:__imp_GetTickCount64
0x18001fd02  mov     [r13+40h], rax
0x18001fd06  test    rbx, rbx
0x18001fd09  jz      loc_18001FB30
0x18001fd0f  mov     ecx, 7FFFFFFEh
0x18001fd14  lea     rdx, [r13+48h]
0x18001fd18  mov     r8d, 100h
0x18001fd1e  xchg    ax, ax
0x18001fd20  test    rcx, rcx
0x18001fd23  jz      loc_18001FB21
0x18001fd29  movzx   eax, word ptr [rbx]
0x18001fd2c  test    ax, ax
0x18001fd2f  jz      loc_18001FB21
0x18001fd35  mov     [rdx], ax
0x18001fd38  add     rbx, 2
0x18001fd3c  add     rdx, 2
0x18001fd40  dec     rcx
0x18001fd43  sub     r8, 1
0x18001fd47  jnz     short loc_18001FD20
0x18001fd49  jmp     loc_18001FB21
0x18001fd4e  mov     rcx, 0C003301000001h
0x18001fd58  bt      rcx, rsi
0x18001fd5c  jnb     loc_18001FCDE
0x18001fd62  call    cs:__imp_GetTickCount64
0x18001fd68  mov     rcx, [rsp+0A8h+arg_38]
0x18001fd70  mov     [r13+2E8h], rax
0x18001fd77  cmp     rcx, [r13+40h]
0x18001fd7b  jbe     loc_18001FB30
0x18001fd81  cmp     [r13+34h], r14d
0x18001fd85  jnz     loc_18001FB30
0x18001fd8b  call    IsAnyInterfaceInDormantMode
0x18001fd90  test    eax, eax
0x18001fd92  jnz     loc_18001FB30
0x18001fd98  mov     dword ptr [r13+38h], 1
0x18001fda0  mov     ebp, 1
0x18001fda5  jmp     loc_18001FB30
0x18001fdaa  mov     edx, 14h
0x18001fdaf  lea     r8, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids
0x18001fdb6  mov     ecx, 40Bh
0x18001fdbb  call    WPP_SF_
0x18001fdc0  jmp     loc_18001FCF8
0x18001fdc5  mov     [rsp+0A8h+var_78], r13
0x18001fdca  mov     r9, rbx
0x18001fdcd  mov     dword ptr [rsp+0A8h+var_80], r14d
0x18001fdd2  mov     [rsp+0A8h+var_88], esi
0x18001fdd6  call    WPP_SF_SDlq
0x18001fddb  jmp     loc_18001FCB7
0x18001fde0  mov     [rsp+0A8h+var_60], esi
0x18001fde4  mov     r9, rbx
0x18001fde7  mov     [rsp+0A8h+var_68], r15d
0x18001fdec  mov     [rsp+0A8h+var_70], r14d
0x18001fdf1  mov     dword ptr [rsp+0A8h+var_78], r12d
0x18001fdf6  mov     [rsp+0A8h+var_80], r8
0x18001fdfb  mov     [rsp+0A8h+var_88], edi
0x18001fdff  call    WPP_SF_Sdidddd
0x18001fe04  jmp     loc_18001FA33
0x18001fe09  mov     edx, 26h ; '&'
0x18001fe0e  lea     r8, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids
0x18001fe15  mov     ecx, 40Bh
0x18001fe1a  mov     r9d, edi
0x18001fe1d  call    WPP_SF_d
0x18001fe22  jmp     loc_18001FBE7
0x18001fe27  call    cs:__imp_GetProcessHeap
0x18001fe2d  mov     cs:g_hProcessHeap, rax
0x18001fe34  jmp     loc_18001FA83
0x18001fe39  mov     edi, 0Eh
0x18001fe3e  jmp     loc_18001FC25
0x18001fe43  mov     edx, 16h
0x18001fe48  lea     r8, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids
0x18001fe4f  mov     ecx, 40Bh
0x18001fe54  mov     r9d, ebp
0x18001fe57  call    WPP_SF_d
0x18001fe5c  jmp     loc_18001FB3D
0x18001fe61  mov     edi, 0Eh
0x18001fe66  jmp     loc_18001FB5F
```

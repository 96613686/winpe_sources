# UnreachableServerCache_IsUnreachable

- ea: `0x18002a8a0`
- end: `0x18002ab6a`
- name: `UnreachableServerCache_IsUnreachable`
- size: `714`
- prototype: `__int64 __fastcall(void *, unsigned __int16, __int64, int, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800213b0`
- `0x18002a8a0`
- `0x18007ab28`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x18002a8cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002aa9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002aa9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002aab3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002aab3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002aa5a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002aa5a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002aa12`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002aa12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a9fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aa75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aadb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a9fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aa75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aadb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a94e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a94e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002aae6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002aae6`

## string_xrefs

- `0x18002aa4d`: `dnsrslvr.dll`

## pseudocode

```c
__int64 __fastcall UnreachableServerCache_IsUnreachable(
        void *a1,
        unsigned __int16 a2,
        __int64 a3,
        int a4,
        int a5,
        int a6)
{
  unsigned int v6; // esi
  unsigned int v9; // ebp
  __int64 *v11; // rbx
  HMODULE Library; // rdi
  __int64 **v13; // rdx
  __int64 *i; // rax
  int v15; // ebp
  HANDLE ProcessHeap; // rax
  ULONGLONG TickCount64; // rax
  ULONGLONG v18; // rcx

  v6 = 0;
  v9 = a2;
  if ( dword_1800AB914 && !DnsGlobals[94] && (a3 & 0x2000000000408LL) == 0 )
  {
    v11 = 0;
    Library = 0;
    if ( (BYTE3(xmmword_1800AB5A0) & 1) != 0 )
      WPP_SF_Sddddd((_DWORD)a1, a2, a3, (_DWORD)a1, a2, a3, a4, a5, a6);
    EnterCriticalSection(&stru_1800ABD68);
    v13 = (__int64 **)((char *)qword_1800ABD90 + 16 * (v9 % 0x35));
    for ( i = *v13; ; i = (__int64 *)*i )
    {
      if ( i == (__int64 *)v13 )
        goto LABEL_23;
      v11 = i - 1;
      if ( *((_DWORD *)i + 4) == dword_1800ABD9C
        && *((_WORD *)v11 + 14) == (_WORD)v9
        && *((_DWORD *)v11 + 8) == a4
        && (!a4 || *((_DWORD *)v11 + 9) == a5)
        && *((_DWORD *)v11 + 10) == a6 )
      {
        break;
      }
    }
    TickCount64 = GetTickCount64();
    v18 = v11[93];
    if ( v18 < TickCount64 && TickCount64 - v18 > 0x1388 || g_IsArgon )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        WPP_SF_(1035, 35, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids);
        LeaveCriticalSection(&stru_1800ABD68);
        goto LABEL_2;
      }
LABEL_23:
      v15 = 0;
      goto LABEL_18;
    }
    v6 = *((_DWORD *)v11 + 13);
    if ( !v6 || *((_DWORD *)v11 + 11) )
    {
      v15 = 0;
    }
    else
    {
      v15 = 1;
      _InterlockedIncrement((volatile signed __int32 *)v11);
      Library = LoadLibraryExW(L"dnsrslvr.dll", 0, 0x800u);
      if ( !Library )
      {
        GetLastError();
        LeaveCriticalSection(&stru_1800ABD68);
        goto LABEL_27;
      }
    }
LABEL_18:
    LeaveCriticalSection(&stru_1800ABD68);
    if ( !v15 )
      goto LABEL_19;
    UnreachableServerCache_InitiateBackgroundQuery(v11, a1);
LABEL_27:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11, 0xFFFFFFFF) == 1 && v11 )
    {
      ProcessHeap = g_hProcessHeap;
      if ( !g_hProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        g_hProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v11);
    }
LABEL_19:
    if ( Library )
      FreeLibrary(Library);
  }
LABEL_2:
  if ( (BYTE3(xmmword_1800AB5A0) & 1) != 0 )
    WPP_SF_d(1048, 36, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18002a8a0  mov     rax, rsp
0x18002a8a3  push    rsi
0x18002a8a4  sub     rsp, 80h
0x18002a8ab  mov     [rax+10h], rbp
0x18002a8af  xor     esi, esi
0x18002a8b1  cmp     cs:dword_1800AB914, esi
0x18002a8b7  mov     [rax-18h], r13
0x18002a8bb  mov     r13, rcx
0x18002a8be  mov     [rax-20h], r14
0x18002a8c2  mov     r14d, r9d
0x18002a8c5  mov     [rax-28h], r15
0x18002a8c9  mov     r15, r8
0x18002a8cc  mov     rax, cs:__imp_DnsGlobals
0x18002a8d3  movzx   ebp, dx
0x18002a8d6  jnz     short loc_18002A907
0x18002a8d8  test    byte ptr cs:xmmword_1800AB5A0+3, 1
0x18002a8df  mov     r15, [rsp+88h+var_28]
0x18002a8e4  mov     r14, [rsp+88h+var_20]
0x18002a8e9  mov     r13, [rsp+88h+var_18]
0x18002a8ee  mov     rbp, [rsp+88h+arg_8]
0x18002a8f6  jnz     loc_18002A9BB
0x18002a8fc  mov     eax, esi
0x18002a8fe  add     rsp, 80h
0x18002a905  pop     rsi
0x18002a906  retn
0x18002a907  cmp     [rax+178h], esi
0x18002a90d  jnz     short loc_18002A8D8
0x18002a90f  mov     rax, 2000000000408h
0x18002a919  test    rax, r15
0x18002a91c  jnz     short loc_18002A8D8
0x18002a91e  mov     [rsp+88h+arg_0], rbx
0x18002a926  xor     ebx, ebx
0x18002a928  mov     [rsp+88h+arg_10], rdi
0x18002a930  xor     edi, edi
0x18002a932  mov     [rsp+88h+var_10], r12
0x18002a937  test    byte ptr cs:xmmword_1800AB5A0+3, 1
0x18002a93e  mov     r12d, ebp
0x18002a941  jnz     loc_18002AB25
0x18002a947  lea     rcx, stru_1800ABD68; lpCriticalSection
0x18002a94e  call    cs:__imp_EnterCriticalSection
0x18002a954  mov     ecx, cs:dword_1800ABD9C
0x18002a95a  mov     eax, 3521CFB3h
0x18002a95f  mov     r8d, [rsp+88h+arg_28]
0x18002a967  mov     r9d, [rsp+88h+arg_20]
0x18002a96f  mul     r12d
0x18002a972  mov     eax, r12d
0x18002a975  sub     eax, edx
0x18002a977  shr     eax, 1
0x18002a979  add     eax, edx
0x18002a97b  shr     eax, 5
0x18002a97e  imul    eax, 35h ; '5'
0x18002a981  sub     r12d, eax
0x18002a984  mov     edx, r12d
0x18002a987  mov     r12, [rsp+88h+var_10]
0x18002a98c  shl     rdx, 4
0x18002a990  add     rdx, cs:qword_1800ABD90
0x18002a997  mov     rax, [rdx]
0x18002a99a  cmp     rax, rdx
0x18002a99d  jz      loc_18002AA3A
0x18002a9a3  cmp     [rax+10h], ecx
0x18002a9a6  lea     rbx, [rax-8]
0x18002a9aa  jnz     short loc_18002A9B6
0x18002a9ac  cmp     [rbx+1Ch], bp
0x18002a9b0  jz      loc_18002AB01
0x18002a9b6  mov     rax, [rax]
0x18002a9b9  jmp     short loc_18002A99A
0x18002a9bb  mov     edx, 24h ; '$'
0x18002a9c0  lea     r8, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids
0x18002a9c7  mov     ecx, 418h
0x18002a9cc  mov     r9d, esi
0x18002a9cf  call    WPP_SF_d
0x18002a9d4  jmp     loc_18002A8FC
0x18002a9d9  sub     rax, rcx
0x18002a9dc  cmp     rax, 1388h
0x18002a9e2  ja      short loc_18002AA2D
0x18002a9e4  cmp     cs:g_IsArgon, esi
0x18002a9ea  jnz     short loc_18002AA2D
0x18002a9ec  mov     esi, [rbx+34h]
0x18002a9ef  test    esi, esi
0x18002a9f1  jnz     short loc_18002AA3E
0x18002a9f3  mov     ebp, edi
0x18002a9f5  lea     rcx, stru_1800ABD68; lpCriticalSection
0x18002a9fc  call    cs:__imp_LeaveCriticalSection
0x18002aa02  test    ebp, ebp
0x18002aa04  jnz     loc_18002AB57
0x18002aa0a  test    rdi, rdi
0x18002aa0d  jz      short loc_18002AA18
0x18002aa0f  mov     rcx, rdi; hLibModule
0x18002aa12  call    cs:__imp_FreeLibrary
0x18002aa18  mov     rbx, [rsp+88h+arg_0]
0x18002aa20  mov     rdi, [rsp+88h+arg_10]
0x18002aa28  jmp     loc_18002A8D8
0x18002aa2d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002aa34  jnz     loc_18002AABE
0x18002aa3a  mov     ebp, esi
0x18002aa3c  jmp     short loc_18002A9F5
0x18002aa3e  cmp     [rbx+2Ch], edi
0x18002aa41  jnz     short loc_18002A9F3
0x18002aa43  mov     ebp, 1
0x18002aa48  lock inc dword ptr [rbx]
0x18002aa4b  xor     edx, edx; hFile
0x18002aa4d  lea     rcx, LibFileName; "dnsrslvr.dll"
0x18002aa54  mov     r8d, 800h; dwFlags
0x18002aa5a  call    cs:__imp_LoadLibraryExW
0x18002aa60  mov     rdi, rax
0x18002aa63  test    rax, rax
0x18002aa66  jnz     short loc_18002A9F5
0x18002aa68  call    cs:__imp_GetLastError
0x18002aa6e  lea     rcx, stru_1800ABD68; lpCriticalSection
0x18002aa75  call    cs:__imp_LeaveCriticalSection
0x18002aa7b  mov     eax, 0FFFFFFFFh
0x18002aa80  lock xadd [rbx], eax
0x18002aa84  cmp     eax, 1
0x18002aa87  jnz     short loc_18002AA0A
0x18002aa89  test    rbx, rbx
0x18002aa8c  jz      loc_18002AA0A
0x18002aa92  mov     rax, cs:g_hProcessHeap
0x18002aa99  test    rax, rax
0x18002aa9c  jnz     short loc_18002AAAB
0x18002aa9e  call    cs:__imp_GetProcessHeap
0x18002aaa4  mov     cs:g_hProcessHeap, rax
0x18002aaab  mov     r8, rbx; lpMem
0x18002aaae  xor     edx, edx; dwFlags
0x18002aab0  mov     rcx, rax; hHeap
0x18002aab3  call    cs:__imp_HeapFree
0x18002aab9  jmp     loc_18002AA0A
0x18002aabe  mov     edx, 23h ; '#'
0x18002aac3  lea     r8, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids
0x18002aaca  mov     ecx, 40Bh
0x18002aacf  call    WPP_SF_
0x18002aad4  lea     rcx, stru_1800ABD68; lpCriticalSection
0x18002aadb  call    cs:__imp_LeaveCriticalSection
0x18002aae1  jmp     loc_18002AA18
0x18002aae6  call    cs:__imp_GetTickCount64
0x18002aaec  mov     rcx, [rbx+2E8h]
0x18002aaf3  cmp     rcx, rax
0x18002aaf6  jb      loc_18002A9D9
0x18002aafc  jmp     loc_18002A9E4
0x18002ab01  cmp     [rbx+20h], r14d
0x18002ab05  jnz     loc_18002A9B6
0x18002ab0b  test    r14d, r14d
0x18002ab0e  jz      short loc_18002AB1A
0x18002ab10  cmp     [rbx+24h], r9d
0x18002ab14  jnz     loc_18002A9B6
0x18002ab1a  cmp     [rbx+28h], r8d
0x18002ab1e  jz      short loc_18002AAE6
0x18002ab20  jmp     loc_18002A9B6
0x18002ab25  mov     eax, [rsp+88h+arg_28]
0x18002ab2c  mov     r9, r13
0x18002ab2f  mov     [rsp+88h+var_48], eax
0x18002ab33  mov     eax, [rsp+88h+arg_20]
0x18002ab3a  mov     [rsp+88h+var_50], eax
0x18002ab3e  mov     [rsp+88h+var_58], r14d
0x18002ab43  mov     [rsp+88h+var_60], r15d
0x18002ab48  mov     [rsp+88h+var_68], r12d
0x18002ab4d  call    WPP_SF_Sddddd
0x18002ab52  jmp     loc_18002A947
0x18002ab57  mov     r8, r15
0x18002ab5a  mov     rdx, r13
0x18002ab5d  mov     rcx, rbx
0x18002ab60  call    UnreachableServerCache_InitiateBackgroundQuery
0x18002ab65  jmp     loc_18002AA7B
```

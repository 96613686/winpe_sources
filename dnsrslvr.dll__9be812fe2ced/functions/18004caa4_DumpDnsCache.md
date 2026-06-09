# DumpDnsCache

- ea: `0x18004caa4`
- end: `0x18004cc7a`
- name: `DumpDnsCache`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180049590`

## callees

- `0x1800111d4`
- `0x180015a90`
- `0x18002a1b0`
- `0x1800352a8`
- `0x180046ec0`
- `0x18004caa4`
- `0x18007d5d8`
- `0x180086700`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004cb97`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004cb97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cc3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cc3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cace`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cace`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004cb0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004cb0e`

## pseudocode

```c
void DumpDnsCache()
{
  unsigned int v0; // ebp
  __int64 v1; // rdx
  __int64 v2; // rcx
  unsigned int v3; // ecx
  unsigned int v4; // edi
  char *v5; // rdx
  __int64 v6; // rsi
  char *v7; // rbx
  __int64 PreferedEntry; // rbx
  _QWORD *v9; // r14
  int v10; // edx
  int v11; // r8d
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-38h] BYREF

  SystemTimeAsFileTime = 0;
  EnterCriticalSection(&g_csCache);
  if ( !g_HashTable )
  {
    v0 = 0;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_24;
    v1 = 83;
    v2 = 1035;
    goto LABEL_23;
  }
  v0 = Cache_InitializeIfNotInitialized();
  if ( !v0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_q)(
        1055,
        v0 + 84,
        WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids,
        SystemTimeAsFileTime);
    v3 = g_HashTableSize;
    v4 = 0;
    if ( g_HashTableSize )
    {
      v5 = (char *)g_HashTable;
      do
      {
        v6 = 16LL * v4;
        v7 = *(char **)&v5[v6];
        if ( v7 != &v5[v6] )
        {
          do
          {
            if ( (unsigned int)Cache_IsInvalidNetworkVersion(v7 - 8) )
            {
              v7 = *(char **)v7;
            }
            else
            {
              PreferedEntry = GetPreferedEntry(v7 - 8, (char *)g_HashTable + v6);
              v9 = (_QWORD *)(PreferedEntry + 112);
              if ( CompareFileTime((const FILETIME *)(PreferedEntry + 112), &SystemTimeAsFileTime) >= 0
                || *(_QWORD *)&SystemTimeAsFileTime - *v9 < 0xB2D05E00 )
              {
                if ( SBYTE3(xmmword_1800AB5A0) < 0 )
                  WPP_SF_iSdDd(
                    *(unsigned __int16 *)(PreferedEntry + 104),
                    v10,
                    v11,
                    *v9,
                    *(_QWORD *)(PreferedEntry + 40),
                    *(_WORD *)(PreferedEntry + 104),
                    *(_DWORD *)(PreferedEntry + 96),
                    *(_DWORD *)(PreferedEntry + 100));
                DumpDnsRecord(*(_QWORD *)(PreferedEntry + 120));
              }
              v7 = *(char **)(PreferedEntry + 8);
            }
            v5 = (char *)g_HashTable;
          }
          while ( v7 != (char *)g_HashTable + v6 );
          v3 = g_HashTableSize;
        }
        ++v4;
      }
      while ( v4 < v3 );
    }
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
    {
      v1 = 86;
      v2 = 1055;
LABEL_23:
      WPP_SF_(v2, v1, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids);
    }
  }
LABEL_24:
  LeaveCriticalSection(&g_csCache);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 87, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids, v0);
}

```

## disassembly

```asm
0x18004caa4  push    rbx
0x18004caa6  push    rbp
0x18004caa7  push    rsi
0x18004caa8  push    rdi
0x18004caa9  push    r14
0x18004caab  sub     rsp, 50h
0x18004caaf  mov     rax, cs:__security_cookie
0x18004cab6  xor     rax, rsp
0x18004cab9  mov     [rsp+78h+var_30], rax
0x18004cabe  lea     rcx, g_csCache; lpCriticalSection
0x18004cac5  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18004cace  call    cs:__imp_EnterCriticalSection
0x18004cad4  cmp     cs:g_HashTable, 0
0x18004cadc  jnz     short loc_18004CAFA
0x18004cade  xor     ebp, ebp
0x18004cae0  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004cae7  jz      loc_18004CC33
0x18004caed  lea     edx, [rbp+53h]
0x18004caf0  mov     ecx, 40Bh
0x18004caf5  jmp     loc_18004CC27
0x18004cafa  call    Cache_InitializeIfNotInitialized
0x18004caff  mov     ebp, eax
0x18004cb01  test    eax, eax
0x18004cb03  jnz     loc_18004CC33
0x18004cb09  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004cb0e  call    cs:__imp_GetSystemTimeAsFileTime
0x18004cb14  cmp     byte ptr cs:xmmword_1800AB5A0+3, bpl
0x18004cb1b  jge     short loc_18004CB36
0x18004cb1d  mov     r9, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x18004cb22  lea     edx, [rbp+54h]
0x18004cb25  mov     ecx, 41Fh
0x18004cb2a  lea     r8, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids
0x18004cb31  call    WPP_SF_q
0x18004cb36  mov     ecx, cs:g_HashTableSize
0x18004cb3c  xor     edi, edi
0x18004cb3e  test    ecx, ecx
0x18004cb40  jz      loc_18004CC14
0x18004cb46  mov     rdx, cs:g_HashTable
0x18004cb4d  mov     esi, edi
0x18004cb4f  shl     rsi, 4
0x18004cb53  lea     rax, [rsi+rdx]
0x18004cb57  mov     rbx, [rax]
0x18004cb5a  cmp     rbx, rax
0x18004cb5d  jz      loc_18004CC0A
0x18004cb63  lea     rcx, [rbx-8]
0x18004cb67  call    Cache_IsInvalidNetworkVersion
0x18004cb6c  test    eax, eax
0x18004cb6e  jz      short loc_18004CB75
0x18004cb70  mov     rbx, [rbx]
0x18004cb73  jmp     short loc_18004CBF0
0x18004cb75  mov     rdx, cs:g_HashTable
0x18004cb7c  lea     rcx, [rbx-8]
0x18004cb80  add     rdx, rsi
0x18004cb83  call    GetPreferedEntry
0x18004cb88  lea     rdx, [rsp+78h+SystemTimeAsFileTime]; lpFileTime2
0x18004cb8d  mov     rbx, rax
0x18004cb90  lea     r14, [rax+70h]
0x18004cb94  mov     rcx, r14; lpFileTime1
0x18004cb97  call    cs:__imp_CompareFileTime
0x18004cb9d  test    eax, eax
0x18004cb9f  jns     short loc_18004CBB3
0x18004cba1  mov     rcx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x18004cba6  mov     eax, 0B2D05E00h
0x18004cbab  sub     rcx, [r14]
0x18004cbae  cmp     rcx, rax
0x18004cbb1  jnb     short loc_18004CBEC
0x18004cbb3  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18004cbba  jge     short loc_18004CBE3
0x18004cbbc  mov     eax, [rbx+64h]
0x18004cbbf  movzx   ecx, word ptr [rbx+68h]
0x18004cbc3  mov     r9, [r14]
0x18004cbc6  mov     [rsp+78h+var_40], eax
0x18004cbca  mov     eax, [rbx+60h]
0x18004cbcd  mov     [rsp+78h+var_48], eax
0x18004cbd1  mov     rax, [rbx+28h]
0x18004cbd5  mov     [rsp+78h+var_50], ecx
0x18004cbd9  mov     [rsp+78h+var_58], rax
0x18004cbde  call    WPP_SF_iSdDd
0x18004cbe3  mov     rcx, [rbx+78h]
0x18004cbe7  call    DumpDnsRecord
0x18004cbec  mov     rbx, [rbx+8]
0x18004cbf0  mov     rdx, cs:g_HashTable
0x18004cbf7  lea     rax, [rsi+rdx]
0x18004cbfb  cmp     rbx, rax
0x18004cbfe  jnz     loc_18004CB63
0x18004cc04  mov     ecx, cs:g_HashTableSize
0x18004cc0a  inc     edi
0x18004cc0c  cmp     edi, ecx
0x18004cc0e  jb      loc_18004CB4D
0x18004cc14  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18004cc1b  jge     short loc_18004CC33
0x18004cc1d  mov     edx, 56h ; 'V'
0x18004cc22  mov     ecx, 41Fh
0x18004cc27  lea     r8, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids
0x18004cc2e  call    WPP_SF_
0x18004cc33  lea     rcx, g_csCache; lpCriticalSection
0x18004cc3a  call    cs:__imp_LeaveCriticalSection
0x18004cc40  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004cc47  jz      short loc_18004CC62
0x18004cc49  mov     edx, 57h ; 'W'
0x18004cc4e  lea     r8, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids
0x18004cc55  mov     ecx, 40Bh
0x18004cc5a  mov     r9d, ebp
0x18004cc5d  call    WPP_SF_d
0x18004cc62  mov     rcx, [rsp+78h+var_30]
0x18004cc67  xor     rcx, rsp; StackCookie
0x18004cc6a  call    __security_check_cookie
0x18004cc6f  add     rsp, 50h
0x18004cc73  pop     r14
0x18004cc75  pop     rdi
0x18004cc76  pop     rsi
0x18004cc77  pop     rbp
0x18004cc78  pop     rbx
0x18004cc79  retn
```

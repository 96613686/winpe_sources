# Cache_FlushRecords

- ea: `0x18002996c`
- end: `0x180029b10`
- name: `Cache_FlushRecords`
- size: `420`
- prototype: `__int64 __fastcall(LPCWSTR lpSrcStr)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180029870`

## callees

- `0x1800113b0`
- `0x180012970`
- `0x180013e20`
- `0x18002996c`
- `0x180029b20`
- `0x180029cc0`
- `0x180046ec0`
- `0x180086384`
- `0x180086700`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x180029a85`
- `DNSAPI!DnsNameCompare_W` at `0x180029a85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029ac4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800299ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800299ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800299fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800299fc`

## pseudocode

```c
void __fastcall Cache_FlushRecords(WCHAR *lpSrcStr)
{
  __int64 Entry; // rax
  __int64 v3; // rsi
  _QWORD *v4; // rdi
  _QWORD *v5; // rbx
  WCHAR pName1[264]; // [rsp+40h] [rbp-248h] BYREF

  pName1[0] = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_SD(1035, 46, (unsigned int)WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids, (_DWORD)lpSrcStr, 2);
  if ( (unsigned int)makeCanonicalCacheName(pName1, 256, lpSrcStr) )
  {
    EnterCriticalSection(&g_csCache);
    if ( g_fCacheInitialized )
    {
      g_CurrentCacheTime = GetTickCount64() / 0x3E8;
      Entry = Cache_FindEntry(lpSrcStr, 0, 0, 0, 0, 1, 0);
      if ( Entry )
      {
        v3 = 16LL * (unsigned int)GetHashIndex(*(_QWORD *)(Entry + 40), 0);
        v4 = *(_QWORD **)((char *)g_HashTable + v3);
        while ( v4 != (_QWORD *)((char *)g_HashTable + v3) )
        {
          v5 = v4 - 1;
          if ( !v4[14] )
            break;
          v4 = (_QWORD *)*v4;
          if ( !DnsNameCompare_W(pName1, (PCWSTR)v5[5]) || *((_WORD *)v5 + 24) )
            break;
          if ( (unsigned int)Cache_FlushEntryRecords(v5, 2) )
            Cache_RemoveEntryFromHashTable(v5);
        }
      }
    }
    LeaveCriticalSection(&g_csCache);
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 47, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids);
}

```

## disassembly

```asm
0x18002996c  push    rbx
0x18002996e  push    rbp
0x18002996f  push    rsi
0x180029970  push    rdi
0x180029971  sub     rsp, 268h
0x180029978  mov     rax, cs:__security_cookie
0x18002997f  xor     rax, rsp
0x180029982  mov     [rsp+288h+var_38], rax
0x18002998a  xor     ebp, ebp
0x18002998c  mov     rbx, rcx
0x18002998f  mov     [rsp+288h+pName1], bp
0x180029994  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002999b  jnz     loc_180029ACF
0x1800299a1  xor     r9d, r9d
0x1800299a4  lea     rcx, [rsp+288h+pName1]; lpDestStr
0x1800299a9  mov     r8, rbx; lpSrcStr
0x1800299ac  mov     edx, 100h; cchDest
0x1800299b1  call    makeCanonicalCacheName
0x1800299b6  test    eax, eax
0x1800299b8  jnz     short loc_1800299E3
0x1800299ba  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800299c1  jnz     loc_180029AF5
0x1800299c7  mov     rcx, [rsp+288h+var_38]
0x1800299cf  xor     rcx, rsp; StackCookie
0x1800299d2  call    __security_check_cookie
0x1800299d7  add     rsp, 268h
0x1800299de  pop     rdi
0x1800299df  pop     rsi
0x1800299e0  pop     rbp
0x1800299e1  pop     rbx
0x1800299e2  retn
0x1800299e3  lea     rcx, g_csCache; lpCriticalSection
0x1800299ea  call    cs:__imp_EnterCriticalSection
0x1800299f0  cmp     cs:g_fCacheInitialized, ebp
0x1800299f6  jz      loc_180029ABD
0x1800299fc  call    cs:__imp_GetTickCount64
0x180029a02  mov     [rsp+288h+var_258], ebp; int
0x180029a06  xor     r9d, r9d
0x180029a09  mov     r8, rax
0x180029a0c  mov     [rsp+288h+var_260], 1; int
0x180029a14  mov     rax, 624DD2F1A9FBE77h
0x180029a1e  mov     [rsp+288h+var_268], bp; __int16
0x180029a23  mul     r8
0x180029a26  mov     rcx, rbx; lpSrcStr
0x180029a29  sub     r8, rdx
0x180029a2c  shr     r8, 1
0x180029a2f  add     r8, rdx
0x180029a32  xor     edx, edx
0x180029a34  shr     r8, 9
0x180029a38  mov     cs:g_CurrentCacheTime, r8d
0x180029a3f  xor     r8d, r8d
0x180029a42  call    Cache_FindEntry
0x180029a47  test    rax, rax
0x180029a4a  jz      short loc_180029ABD
0x180029a4c  mov     rcx, [rax+28h]
0x180029a50  xor     edx, edx
0x180029a52  call    GetHashIndex
0x180029a57  mov     rcx, cs:g_HashTable
0x180029a5e  mov     esi, eax
0x180029a60  shl     rsi, 4
0x180029a64  add     rcx, rsi
0x180029a67  mov     rdi, [rcx]
0x180029a6a  cmp     rdi, rcx
0x180029a6d  jz      short loc_180029ABD
0x180029a6f  lea     rbx, [rdi-8]
0x180029a73  cmp     [rbx+78h], rbp
0x180029a77  jz      short loc_180029ABD
0x180029a79  mov     rdx, [rbx+28h]; pName2
0x180029a7d  lea     rcx, [rsp+288h+pName1]; pName1
0x180029a82  mov     rdi, [rdi]
0x180029a85  call    cs:__imp_DnsNameCompare_W
0x180029a8b  test    eax, eax
0x180029a8d  jz      short loc_180029ABD
0x180029a8f  cmp     [rbx+30h], bp
0x180029a93  jnz     short loc_180029ABD
0x180029a95  mov     edx, 2
0x180029a9a  mov     rcx, rbx
0x180029a9d  call    Cache_FlushEntryRecords
0x180029aa2  test    eax, eax
0x180029aa4  jz      short loc_180029AAE
0x180029aa6  mov     rcx, rbx; lpMem
0x180029aa9  call    Cache_RemoveEntryFromHashTable
0x180029aae  mov     rdx, cs:g_HashTable
0x180029ab5  add     rdx, rsi
0x180029ab8  cmp     rdi, rdx
0x180029abb  jnz     short loc_180029A6F
0x180029abd  lea     rcx, g_csCache; lpCriticalSection
0x180029ac4  call    cs:__imp_LeaveCriticalSection
0x180029aca  jmp     loc_1800299BA
0x180029acf  mov     edx, 2Eh ; '.'
0x180029ad4  mov     dword ptr [rsp+288h+var_268], 2
0x180029adc  mov     ecx, 40Bh
0x180029ae1  lea     r8, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids
0x180029ae8  mov     r9, rbx
0x180029aeb  call    WPP_SF_SD
0x180029af0  jmp     loc_1800299A1
0x180029af5  mov     edx, 2Fh ; '/'
0x180029afa  lea     r8, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids
0x180029b01  mov     ecx, 40Bh
0x180029b06  call    WPP_SF_
0x180029b0b  jmp     loc_1800299C7
```

# R_ReadCache

- ea: `0x1800084e0`
- end: `0x18000885f`
- name: `R_ReadCache`
- size: `895`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800078e8`
- `0x180008490`
- `0x1800084e0`
- `0x180008870`
- `0x1800088f0`
- `0x18000b130`
- `0x1800111d4`
- `0x180040cd4`
- `0x18007af64`
- `0x18008841c`
- `0x180088578`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x1800086f7`
- `DNSAPI!DnsNameCompare_W` at `0x1800086f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008828`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008828`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000864d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000864d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800085e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800085e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800085f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800085f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008746`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008854`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008746`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008854`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008565`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008565`

## pseudocode

```c
__int64 __fastcall R_ReadCache(int a1, char a2, _QWORD *a3)
{
  void *v4; // rdi
  unsigned int v5; // r12d
  bool v7; // zf
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // r15d
  unsigned int v13; // esi
  __int64 v14; // rdi
  _BYTE *v15; // r14
  char *v16; // rcx
  __int64 *v17; // r13
  unsigned int v18; // ebx
  const wchar_t *v19; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v21; // rbp
  __int64 v22; // rcx
  size_t v23; // r14
  wchar_t *v24; // rax
  char *v25; // rbx
  char *v26; // r15
  __int64 v27; // rcx
  __int64 v28; // r9
  void *v30; // [rsp+30h] [rbp-48h]
  _QWORD *v31; // [rsp+38h] [rbp-40h]
  unsigned int v33; // [rsp+98h] [rbp+20h]

  v4 = 0;
  v5 = 0;
  v30 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qiq(a1, 10, (_DWORD)a3, a1, a2, (__int64)a3);
  if ( a3 )
  {
    *a3 = 0;
    if ( (unsigned int)Rpc_AccessCheck(2u) )
    {
      v7 = (a2 & 1) == 0;
      v8 = -1;
      if ( v7 )
        v8 = 15000;
      v33 = v8;
      EnterCriticalSection(&g_csCache);
      v12 = Cache_InitializeIfNotInitialized();
      if ( !v12 )
      {
        v31 = 0;
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_dd(
            1035,
            11,
            WPP_19079b4fdf5130d1a4d307ec0fef1a81_Traceguids,
            (unsigned int)g_EntryCount,
            g_RecordSetCount);
        v13 = 0;
LABEL_11:
        if ( v13 >= g_HashTableSize || v5 >= v8 )
        {
          LeaveCriticalSection(&g_csCache);
          v4 = 0;
          *a3 = v30;
          goto LABEL_44;
        }
        v14 = 16LL * v13;
        v15 = *(_BYTE **)((char *)g_HashTable + v14);
        while ( 1 )
        {
          while ( 1 )
          {
            v16 = (char *)g_HashTable + v14;
            if ( v15 == (char *)g_HashTable + v14 || v5 >= v8 )
            {
              ++v13;
              goto LABEL_11;
            }
            v17 = (__int64 *)(v15 - 8);
            if ( (v15[88] & 3) != 0 )
              break;
            AcquireSRWLockShared(&SRWLock);
            v18 = dword_1800ABC2C;
            ReleaseSRWLockShared(&SRWLock);
            if ( *((_DWORD *)v17 + 22) >= v18 )
              break;
            v15 = *(_BYTE **)v15;
            v8 = v33;
          }
          if ( *((_DWORD *)v17 + 25) || (v17[12] & 0x40) == 0 )
          {
            v25 = *(char **)v15;
            v26 = (char *)g_HashTable + v14;
            while ( v25 != v26 )
            {
              if ( DnsNameCompare_W(*((PCWSTR *)v25 + 4), (PCWSTR)v17[5])
                && !*((_DWORD *)v25 + 23)
                && (v25[88] & 0x40) != 0
                && *((_WORD *)v25 + 48) == *((_WORD *)v17 + 52) )
              {
                v17 = (__int64 *)(v25 - 8);
                break;
              }
              v25 = *(char **)v25;
            }
          }
          if ( !v17 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v16, v9, v10, v11);
          v19 = (const wchar_t *)v17[5];
          if ( !v19 )
            break;
          ProcessHeap = g_hProcessHeap;
          if ( !g_hProcessHeap )
          {
            ProcessHeap = GetProcessHeap();
            g_hProcessHeap = ProcessHeap;
          }
          v21 = HeapAlloc(ProcessHeap, 8u, 0x18u);
          if ( !v21 )
            break;
          v22 = -1;
          do
            v7 = v19[++v22] == 0;
          while ( !v7 );
          v23 = v22 + 1;
          v24 = (wchar_t *)Dns_Allocate(2 * (v22 + 1));
          v21[1] = v24;
          if ( !v24 )
          {
            MIDL_user_free(v21);
            break;
          }
          StringCchCopyW(v24, v23, v19);
          v12 = 0;
          if ( v31 )
            *v31 = v21;
          else
            v30 = v21;
          ++v5;
          v8 = v33;
          *((_WORD *)v21 + 8) = *((_WORD *)v17 + 52);
          v15 = (_BYTE *)v17[1];
          v31 = v21;
        }
        v4 = v30;
        v12 = 14;
      }
      LeaveCriticalSection(&g_csCache);
    }
    else
    {
      v12 = 5;
    }
  }
  else
  {
    v12 = 87;
  }
LABEL_44:
  FreeCacheTableEntryList(v4);
  v28 = 0;
  if ( !v12 )
    v28 = v5;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_Dd(v27, 12, WPP_19079b4fdf5130d1a4d307ec0fef1a81_Traceguids, v28, v12);
  return v12;
}

```

## disassembly

```asm
0x1800084e0  mov     rax, rsp
0x1800084e3  mov     [rax+18h], r8
0x1800084e7  push    r15
0x1800084e9  sub     rsp, 70h
0x1800084ed  mov     [rax+8], rbx
0x1800084f1  mov     rbx, rdx
0x1800084f4  mov     [rax-20h], rdi
0x1800084f8  xor     edi, edi
0x1800084fa  mov     [rax-28h], r12
0x1800084fe  xor     r12d, r12d
0x180008501  mov     [rax-38h], r14
0x180008505  mov     r14, r8
0x180008508  mov     [rsp+78h+var_48], rdi
0x18000850d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180008514  jnz     loc_1800087D3
0x18000851a  test    r14, r14
0x18000851d  jz      loc_1800087B3
0x180008523  mov     ecx, 2
0x180008528  mov     [r14], rdi
0x18000852b  call    Rpc_AccessCheck
0x180008530  test    eax, eax
0x180008532  jz      loc_18000881D
0x180008538  test    bl, 1
0x18000853b  mov     [rsp+78h+var_10], rbp
0x180008540  mov     eax, 3A98h
0x180008545  mov     [rsp+78h+var_18], rsi
0x18000854a  mov     ebx, 0FFFFFFFFh
0x18000854f  mov     [rsp+78h+var_30], r13
0x180008554  cmovz   ebx, eax
0x180008557  lea     rcx, g_csCache; lpCriticalSection
0x18000855e  mov     [rsp+78h+arg_18], ebx
0x180008565  call    cs:__imp_EnterCriticalSection
0x18000856b  call    Cache_InitializeIfNotInitialized
0x180008570  mov     r15d, eax
0x180008573  test    eax, eax
0x180008575  jnz     loc_18000884D
0x18000857b  mov     [rsp+78h+var_40], rdi
0x180008580  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180008587  jnz     loc_1800087EF
0x18000858d  xor     esi, esi
0x18000858f  nop
0x180008590  cmp     esi, cs:g_HashTableSize
0x180008596  jnb     loc_18000873F
0x18000859c  cmp     r12d, ebx
0x18000859f  jnb     loc_18000873F
0x1800085a5  mov     rax, cs:g_HashTable
0x1800085ac  mov     edi, esi
0x1800085ae  shl     rdi, 4
0x1800085b2  mov     r14, [rdi+rax]
0x1800085b6  mov     rcx, cs:g_HashTable
0x1800085bd  add     rcx, rdi
0x1800085c0  cmp     r14, rcx
0x1800085c3  jnz     short loc_1800085C9
0x1800085c5  inc     esi
0x1800085c7  jmp     short loc_180008590
0x1800085c9  cmp     r12d, ebx
0x1800085cc  jnb     short loc_1800085C5
0x1800085ce  test    byte ptr [r14+58h], 3
0x1800085d3  lea     r13, [r14-8]
0x1800085d7  jnz     short loc_180008603
0x1800085d9  lea     rcx, SRWLock; SRWLock
0x1800085e0  call    cs:__imp_AcquireSRWLockShared
0x1800085e6  mov     ebx, cs:dword_1800ABC2C
0x1800085ec  lea     rcx, SRWLock; SRWLock
0x1800085f3  call    cs:__imp_ReleaseSRWLockShared
0x1800085f9  cmp     [r13+58h], ebx
0x1800085fd  jb      loc_180008726
0x180008603  cmp     dword ptr [r13+64h], 0
0x180008608  jnz     loc_1800086D9
0x18000860e  test    byte ptr [r13+60h], 40h
0x180008613  jz      loc_1800086D9
0x180008619  test    r13, r13
0x18000861c  jz      loc_1800087A9
0x180008622  mov     rbx, [r13+28h]
0x180008626  test    rbx, rbx
0x180008629  jz      loc_180008842
0x18000862f  mov     rax, cs:g_hProcessHeap
0x180008636  test    rax, rax
0x180008639  jz      loc_180008828
0x18000863f  mov     edx, 8; dwFlags
0x180008644  mov     r8d, 18h; dwBytes
0x18000864a  mov     rcx, rax; hHeap
0x18000864d  call    cs:__imp_HeapAlloc
0x180008653  mov     rbp, rax
0x180008656  test    rax, rax
0x180008659  jz      loc_180008842
0x18000865f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008666  nop     word ptr [rax+rax+00000000h]
0x180008670  cmp     word ptr [rbx+rcx*2+2], 0
0x180008676  lea     rcx, [rcx+1]
0x18000867a  jnz     short loc_180008670
0x18000867c  lea     r14, [rcx+1]
0x180008680  lea     rcx, [r14+r14]
0x180008684  call    Dns_Allocate
0x180008689  mov     [rbp+8], rax
0x18000868d  test    rax, rax
0x180008690  jz      loc_18000883A
0x180008696  mov     r8, rbx; pszSrc
0x180008699  mov     rdx, r14; cchDest
0x18000869c  mov     rcx, rax; pszDest
0x18000869f  call    StringCchCopyW
0x1800086a4  mov     rax, [rsp+78h+var_40]
0x1800086a9  xor     r15d, r15d
0x1800086ac  test    rax, rax
0x1800086af  jz      loc_180008735
0x1800086b5  mov     [rax], rbp
0x1800086b8  movzx   eax, word ptr [r13+68h]
0x1800086bd  inc     r12d
0x1800086c0  mov     ebx, [rsp+78h+arg_18]
0x1800086c7  mov     [rbp+10h], ax
0x1800086cb  mov     r14, [r13+8]
0x1800086cf  mov     [rsp+78h+var_40], rbp
0x1800086d4  jmp     loc_1800085B6
0x1800086d9  mov     r15, cs:g_HashTable
0x1800086e0  mov     rbx, [r14]
0x1800086e3  add     r15, rdi
0x1800086e6  cmp     rbx, r15
0x1800086e9  jz      loc_180008619
0x1800086ef  mov     rdx, [r13+28h]; pName2
0x1800086f3  mov     rcx, [rbx+20h]; pName1
0x1800086f7  call    cs:__imp_DnsNameCompare_W
0x1800086fd  test    eax, eax
0x1800086ff  jnz     short loc_180008706
0x180008701  mov     rbx, [rbx]
0x180008704  jmp     short loc_1800086E6
0x180008706  cmp     dword ptr [rbx+5Ch], 0
0x18000870a  jnz     short loc_180008701
0x18000870c  test    byte ptr [rbx+58h], 40h
0x180008710  jz      short loc_180008701
0x180008712  movzx   eax, word ptr [r13+68h]
0x180008717  cmp     [rbx+60h], ax
0x18000871b  jnz     short loc_180008701
0x18000871d  lea     r13, [rbx-8]
0x180008721  jmp     loc_180008619
0x180008726  mov     r14, [r14]
0x180008729  mov     ebx, [rsp+78h+arg_18]
0x180008730  jmp     loc_1800085B6
0x180008735  mov     [rsp+78h+var_48], rbp
0x18000873a  jmp     loc_1800086B8
0x18000873f  lea     rcx, g_csCache; lpCriticalSection
0x180008746  call    cs:__imp_LeaveCriticalSection
0x18000874c  mov     rcx, [rsp+78h+arg_10]
0x180008754  xor     edi, edi
0x180008756  mov     rax, [rsp+78h+var_48]
0x18000875b  mov     [rcx], rax
0x18000875e  mov     rsi, [rsp+78h+var_18]
0x180008763  mov     rbp, [rsp+78h+var_10]
0x180008768  mov     r13, [rsp+78h+var_30]
0x18000876d  mov     rcx, rdi; void *
0x180008770  call    FreeCacheTableEntryList
0x180008775  mov     r14, [rsp+78h+var_38]
0x18000877a  xor     r9d, r9d
0x18000877d  mov     rdi, [rsp+78h+var_20]
0x180008782  test    r15d, r15d
0x180008785  mov     rbx, [rsp+78h+arg_0]
0x18000878d  cmovz   r9d, r12d
0x180008791  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180008798  mov     r12, [rsp+78h+var_28]
0x18000879d  jnz     short loc_1800087BB
0x18000879f  mov     eax, r15d
0x1800087a2  add     rsp, 70h
0x1800087a6  pop     r15
0x1800087a8  retn
0x1800087a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800087ae  jmp     loc_180008622
0x1800087b3  mov     r15d, 57h ; 'W'
0x1800087b9  jmp     short loc_18000876D
0x1800087bb  mov     edx, 0Ch
0x1800087c0  mov     dword ptr [rsp+78h+var_58], r15d
0x1800087c5  lea     r8, WPP_19079b4fdf5130d1a4d307ec0fef1a81_Traceguids
0x1800087cc  call    WPP_SF_Dd
0x1800087d1  jmp     short loc_18000879F
0x1800087d3  mov     edx, 0Ah
0x1800087d8  mov     [rsp+78h+var_50], r14
0x1800087dd  mov     r9, rcx
0x1800087e0  mov     [rsp+78h+var_58], rbx
0x1800087e5  call    WPP_SF_qiq
0x1800087ea  jmp     loc_18000851A
0x1800087ef  mov     r8d, cs:g_RecordSetCount
0x1800087f6  mov     edx, 0Bh
0x1800087fb  mov     r9d, cs:g_EntryCount
0x180008802  mov     ecx, 40Bh
0x180008807  mov     dword ptr [rsp+78h+var_58], r8d
0x18000880c  lea     r8, WPP_19079b4fdf5130d1a4d307ec0fef1a81_Traceguids
0x180008813  call    WPP_SF_dd
0x180008818  jmp     loc_18000858D
0x18000881d  mov     r15d, 5
0x180008823  jmp     loc_18000876D
0x180008828  call    cs:__imp_GetProcessHeap
0x18000882e  mov     cs:g_hProcessHeap, rax
0x180008835  jmp     loc_18000863F
0x18000883a  mov     rcx, rbp; void *
0x18000883d  call    MIDL_user_free
0x180008842  mov     rdi, [rsp+78h+var_48]
0x180008847  mov     r15d, 0Eh
0x18000884d  lea     rcx, g_csCache; lpCriticalSection
0x180008854  call    cs:__imp_LeaveCriticalSection
0x18000885a  jmp     loc_18000875E
```

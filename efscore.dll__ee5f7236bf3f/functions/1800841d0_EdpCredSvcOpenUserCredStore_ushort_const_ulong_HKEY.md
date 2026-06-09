# EdpCredSvcOpenUserCredStore(ushort const *,ulong,HKEY__ * *)

- ea: `0x1800841d0`
- end: `0x180084501`
- name: `?EdpCredSvcOpenUserCredStore@@YAJPEBGKPEAPEAUHKEY__@@@Z`
- size: `817`
- prototype: `__int64 __fastcall(const unsigned __int16 *, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `13`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040484`
- `0x180095594`
- `0x18009f128`
- `0x18009f958`
- `0x1800a2178`
- `0x1800aa5a4`
- `0x1800ab620`
- `0x1800ae00c`
- `0x1800b4c78`
- `0x1800b5a5c`
- `0x1800b845c`
- `0x1800bbae0`
- `0x1800bc2ec`

## callees

- `0x18001312c`
- `0x18001318c`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800841d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084360`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084360`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008434f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800844a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008434f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800844a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800844ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800844ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084435`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084435`

## pseudocode

```c
__int64 __fastcall EdpCredSvcOpenUserCredStore(const unsigned __int16 *a1, REGSAM samDesired, PHKEY phkResult)
{
  int v6; // ecx
  unsigned int v7; // ebx
  int v8; // ecx
  SIZE_T v9; // rbp
  HANDLE ProcessHeap; // rax
  int v11; // ecx
  unsigned __int16 *v12; // rsi
  int Key; // eax
  HANDLE v14; // rax
  unsigned __int64 v16; // [rsp+80h] [rbp+8h] BYREF

  v16 = 0;
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 38, 77);
  if ( phkResult )
    *phkResult = 0;
  if ( a1 )
  {
    if ( phkResult )
    {
      fnEfsLogTrace1Strings(v6, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 90);
      v7 = StringCbLengthW(a1, 0xFFFFFFFE, &v16);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v7,
                  38,
                  90) >= 0 )
      {
        fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 94);
        v9 = v16 + 134;
        if ( v16 + 134 < v16 )
        {
          v9 = -1;
          v7 = -2147024362;
        }
        else
        {
          v7 = 0;
        }
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v7,
                    38,
                    94) >= 0 )
        {
          ProcessHeap = GetProcessHeap();
          v12 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v9);
          if ( v12 )
          {
            fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 103);
            v7 = StringCbPrintfW(
                   v12,
                   v9,
                   L"%s\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\EFS\\EdpCredentials",
                   a1);
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        v7,
                        38,
                        103) >= 0 )
            {
              Key = RegCreateKeyExW(HKEY_USERS, v12, 0, 0, 0, samDesired, 0, phkResult, 0);
              if ( Key )
              {
                if ( Key > 0 )
                  Key = (unsigned __int16)Key | 0x80070000;
                if ( Key == -2147024809 )
                {
                  v7 = -2147023643;
                  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, -2147023643, 38, 129);
                }
                else
                {
                  v7 = Key;
                }
                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 38, 132);
              }
            }
            v14 = GetProcessHeap();
            HeapFree(v14, 0, v12);
          }
          else
          {
            v7 = -2147024882;
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 38, 98);
          }
        }
      }
    }
    else
    {
      v7 = -2147467261;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147467261, 38, 82);
    }
  }
  else
  {
    v7 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 38, 81);
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v7,
    38,
    139);
  return v7;
}

```

## disassembly

```asm
0x1800841d0  mov     rax, rsp
0x1800841d3  mov     [rax+10h], rbx
0x1800841d7  mov     [rax+18h], rbp
0x1800841db  push    rsi
0x1800841dc  push    rdi
0x1800841dd  push    r12
0x1800841df  push    r14
0x1800841e1  push    r15
0x1800841e3  sub     rsp, 50h
0x1800841e7  mov     rdi, r8
0x1800841ea  mov     qword ptr [rax+8], 0
0x1800841f2  mov     r15d, edx
0x1800841f5  mov     dword ptr [rax-58h], 54Dh
0x1800841fc  mov     r12d, 26h ; '&'
0x180084202  lea     r8, sourceString
0x180084209  mov     r9d, r12d
0x18008420c  lea     rdx, EFS_TRACE_ENTER_EVENT
0x180084213  mov     r14, rcx
0x180084216  call    fnEfsLogTrace1Strings
0x18008421b  test    rdi, rdi
0x18008421e  jz      short loc_180084225
0x180084220  xor     eax, eax
0x180084222  mov     [rdi], rax
0x180084225  mov     r9d, r12d
0x180084228  test    r14, r14
0x18008422b  jnz     short loc_180084258
0x18008422d  mov     ebx, 80070057h
0x180084232  mov     [rsp+78h+dwOptions], 551h
0x18008423a  mov     r8d, 80070057h
0x180084240  mov     rcx, cs:g_hPublisher
0x180084247  lea     rdx, EFS_TRACE_ERROR
0x18008424e  call    fnEfsLogTrace1
0x180084253  jmp     loc_1800844B4
0x180084258  test    rdi, rdi
0x18008425b  jnz     short loc_180084272
0x18008425d  mov     ebx, 80004003h
0x180084262  mov     [rsp+78h+dwOptions], 552h
0x18008426a  mov     r8d, 80004003h
0x180084270  jmp     short loc_180084240
0x180084272  mov     esi, 55Ah
0x180084277  lea     r8, sourceString
0x18008427e  lea     rdx, EFS_TRACE_START_EVENT
0x180084285  mov     [rsp+78h+dwOptions], esi
0x180084289  call    fnEfsLogTrace1Strings
0x18008428e  lea     r8, [rsp+78h+arg_0]; unsigned __int64 *
0x180084296  mov     edx, 0FFFFFFFEh; unsigned __int64
0x18008429b  mov     rcx, r14; unsigned __int16 *
0x18008429e  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800842a3  mov     rcx, cs:g_hPublisher
0x1800842aa  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800842b1  mov     dword ptr [rsp+78h+lpSecurityAttributes], esi
0x1800842b5  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800842bc  lea     rsi, sourceString
0x1800842c3  mov     [rsp+78h+samDesired], r12d
0x1800842c8  mov     r9, rsi
0x1800842cb  mov     [rsp+78h+dwOptions], eax
0x1800842cf  mov     ebx, eax
0x1800842d1  call    fnEfsLogTrace1String1Dword
0x1800842d6  test    eax, eax
0x1800842d8  js      loc_1800844B4
0x1800842de  mov     r9d, r12d
0x1800842e1  mov     [rsp+78h+dwOptions], 55Eh
0x1800842e9  mov     r8, rsi
0x1800842ec  lea     rdx, EFS_TRACE_START_EVENT
0x1800842f3  call    fnEfsLogTrace1Strings
0x1800842f8  mov     rax, [rsp+78h+arg_0]
0x180084300  lea     rbp, [rax+86h]
0x180084307  cmp     rbp, rax
0x18008430a  jb      short loc_180084310
0x18008430c  xor     ebx, ebx
0x18008430e  jmp     short loc_180084319
0x180084310  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180084314  mov     ebx, 80070216h
0x180084319  mov     rcx, cs:g_hPublisher
0x180084320  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180084327  mov     dword ptr [rsp+78h+lpSecurityAttributes], 55Eh
0x18008432f  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180084336  mov     [rsp+78h+samDesired], r12d
0x18008433b  mov     r9, rsi
0x18008433e  mov     [rsp+78h+dwOptions], ebx
0x180084342  call    fnEfsLogTrace1String1Dword
0x180084347  test    eax, eax
0x180084349  js      loc_1800844B4
0x18008434f  call    cs:__imp_GetProcessHeap
0x180084355  mov     r8, rbp; dwBytes
0x180084358  mov     edx, 8; dwFlags
0x18008435d  mov     rcx, rax; hHeap
0x180084360  call    cs:__imp_HeapAlloc
0x180084366  mov     rsi, rax
0x180084369  test    rax, rax
0x18008436c  jnz     short loc_180084389
0x18008436e  mov     ebx, 8007000Eh
0x180084373  mov     [rsp+78h+dwOptions], 562h
0x18008437b  mov     r9d, r12d
0x18008437e  mov     r8d, 8007000Eh
0x180084384  jmp     loc_180084240
0x180084389  mov     r12d, 567h
0x18008438f  lea     r8, sourceString
0x180084396  mov     r9d, 26h ; '&'
0x18008439c  mov     [rsp+78h+dwOptions], r12d
0x1800843a1  lea     rdx, EFS_TRACE_START_EVENT
0x1800843a8  call    fnEfsLogTrace1Strings
0x1800843ad  mov     r9, r14
0x1800843b0  lea     r8, aSSoftwareMicro; "%s\\SOFTWARE\\Microsoft\\Windows NT\\Cu"...
0x1800843b7  mov     rdx, rbp; unsigned __int64
0x1800843ba  mov     rcx, rsi; unsigned __int16 *
0x1800843bd  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800843c2  mov     rcx, cs:g_hPublisher
0x1800843c9  lea     r9, sourceString
0x1800843d0  mov     dword ptr [rsp+78h+lpSecurityAttributes], r12d
0x1800843d5  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800843dc  mov     r12d, 26h ; '&'
0x1800843e2  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800843e9  mov     [rsp+78h+samDesired], r12d
0x1800843ee  mov     ebx, eax
0x1800843f0  mov     [rsp+78h+dwOptions], eax
0x1800843f4  call    fnEfsLogTrace1String1Dword
0x1800843f9  test    eax, eax
0x1800843fb  js      loc_1800844A0
0x180084401  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18008440a  xor     r9d, r9d; lpClass
0x18008440d  mov     [rsp+78h+phkResult], rdi; phkResult
0x180084412  xor     r8d, r8d; Reserved
0x180084415  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008441e  mov     rdx, rsi; lpSubKey
0x180084421  mov     [rsp+78h+samDesired], r15d; samDesired
0x180084426  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18008442d  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180084435  call    cs:__imp_RegCreateKeyExW
0x18008443b  test    eax, eax
0x18008443d  jz      short loc_1800844A0
0x18008443f  jle     short loc_180084449
0x180084441  movzx   eax, ax
0x180084444  or      eax, 80070000h
0x180084449  mov     ebx, 80070057h
0x18008444e  cmp     eax, ebx
0x180084450  jnz     short loc_18008447D
0x180084452  mov     rcx, cs:g_hPublisher
0x180084459  lea     rdx, EFS_TRACE_STATUS
0x180084460  mov     r9d, r12d
0x180084463  mov     [rsp+78h+dwOptions], 581h
0x18008446b  mov     r8d, 800704E5h
0x180084471  mov     ebx, 800704E5h
0x180084476  call    fnEfsLogTrace1
0x18008447b  jmp     short loc_18008447F
0x18008447d  mov     ebx, eax
0x18008447f  mov     rcx, cs:g_hPublisher
0x180084486  lea     rdx, EFS_TRACE_ERROR
0x18008448d  mov     r9d, r12d
0x180084490  mov     [rsp+78h+dwOptions], 584h
0x180084498  mov     r8d, ebx
0x18008449b  call    fnEfsLogTrace1
0x1800844a0  call    cs:__imp_GetProcessHeap
0x1800844a6  mov     r8, rsi; lpMem
0x1800844a9  xor     edx, edx; dwFlags
0x1800844ab  mov     rcx, rax; hHeap
0x1800844ae  call    cs:__imp_HeapFree
0x1800844b4  mov     rcx, cs:g_hPublisher
0x1800844bb  lea     r9, sourceString
0x1800844c2  mov     dword ptr [rsp+78h+lpSecurityAttributes], 58Bh
0x1800844ca  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800844d1  mov     [rsp+78h+samDesired], r12d
0x1800844d6  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800844dd  mov     [rsp+78h+dwOptions], ebx
0x1800844e1  call    fnEfsLogTrace1String1Dword
0x1800844e6  lea     r11, [rsp+78h+var_28]
0x1800844eb  mov     eax, ebx
0x1800844ed  mov     rbx, [r11+38h]
0x1800844f1  mov     rbp, [r11+40h]
0x1800844f5  mov     rsp, r11
0x1800844f8  pop     r15
0x1800844fa  pop     r14
0x1800844fc  pop     r12
0x1800844fe  pop     rdi
0x1800844ff  pop     rsi
0x180084500  retn
```

# DwmpQueryThumbnailType

- ea: `0x180005060`
- end: `0x18000522f`
- name: `DwmpQueryThumbnailType`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000352c`
- `0x180003820`
- `0x18000387c`
- `0x180005060`
- `0x18000b05c`
- `0x18000b880`
- `0x18000bab0`
- `0x18000d0a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005163`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005163`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005120`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005120`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000509d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000509d`

## pseudocode

```c
__int64 __fastcall DwmpQueryThumbnailType(unsigned int a1, _DWORD *a2)
{
  int v3; // ebx
  CApiPortClient *v4; // rcx
  int v5; // eax
  int v6; // edi
  int v7; // edi
  int v8; // eax
  void *v10; // [rsp+28h] [rbp-58h]
  void *v11; // [rsp+28h] [rbp-58h]
  int v12; // [rsp+40h] [rbp-40h] BYREF
  void **v13; // [rsp+48h] [rbp-38h]
  __int128 v14; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v15[4]; // [rsp+60h] [rbp-20h] BYREF

  if ( a2 )
  {
    *(__m128i *)v15 = _mm_load_si128((const __m128i *)&_xmm);
    v15[1] = a1;
    v15[2] = GetCurrentProcessId();
    v3 = 0;
    v14 = 0;
    EnterCriticalSection(&CriticalSection);
    v12 = 0;
    v5 = CApiPortClient::EnsureConnected(v4);
    v6 = v5;
    if ( v5 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(4u, &CApiPortClient::MILINSTRUMENTATIONHRESULTLIST, 2u, v5, 0xACu, v10);
    }
    else
    {
      ++dword_18001F948;
      LeaveCriticalSection(&CriticalSection);
      v7 = CPortClient::SendComplexSyncRequest(g_PortClient, v15[0], v15, 16, 0, v15, 16, &v12);
      EnterCriticalSection(&CriticalSection);
      if ( !--dword_18001F948 && *(_DWORD *)(g_PortClient + 8LL) )
        CApiPortClient::Disconnect((CApiPortClient *)&g_PortClient);
      v8 = CApiPortClient::Translate(v7);
      v6 = v8;
      if ( v8 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(4u, &CApiPortClient::MILINSTRUMENTATIONHRESULTLIST, 2u, v8, 0xC1u, v11);
      else
        v3 = CApiPortClient::Translate(v12);
    }
    LeaveCriticalSection(&CriticalSection);
    v13 = &CStandardData::`vftable';
    std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((char *)&v14 + 8);
    if ( v6 < 0 )
    {
      v3 = v6;
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019288, 3u, v6, 0x257u, v11);
    }
    else if ( v3 >= 0 )
    {
      *a2 = v15[3];
    }
    else
    {
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019288, 3u, v3, 0x258u, v11);
    }
  }
  else
  {
    v3 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019288, 3u, -2147024809, 0x24Eu, v10);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180005060  mov     [rsp-18h+arg_10], rbx
0x180005065  push    rbp
0x180005066  push    rdi
0x180005067  push    r14
0x180005069  mov     rbp, rsp
0x18000506c  sub     rsp, 80h
0x180005073  mov     rax, cs:__security_cookie
0x18000507a  xor     rax, rsp
0x18000507d  mov     [rbp+var_10], rax
0x180005081  mov     r14, rdx
0x180005084  test    rdx, rdx
0x180005087  jz      loc_1800051D7
0x18000508d  movdqa  xmm0, cs:__xmm@0000000000000000000000004000003c
0x180005095  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18000509a  mov     [rbp+var_20+4], ecx
0x18000509d  call    cs:__imp_GetCurrentProcessId
0x1800050a3  xorps   xmm0, xmm0
0x1800050a6  lea     rcx, CriticalSection; lpCriticalSection
0x1800050ad  mov     [rbp+var_20+8], eax
0x1800050b0  xor     ebx, ebx
0x1800050b2  movdqu  [rbp+var_30], xmm0
0x1800050b7  call    cs:__imp_EnterCriticalSection
0x1800050bd  mov     [rbp+var_40], ebx
0x1800050c0  call    ?EnsureConnected@CApiPortClient@@AEAAJXZ; CApiPortClient::EnsureConnected(void)
0x1800050c5  mov     edi, eax
0x1800050c7  test    eax, eax
0x1800050c9  js      loc_180005209
0x1800050cf  inc     cs:dword_18001F948
0x1800050d5  lea     rcx, CriticalSection; lpCriticalSection
0x1800050dc  call    cs:__imp_LeaveCriticalSection
0x1800050e2  mov     edx, [rbp+var_20]; unsigned int
0x1800050e5  lea     ecx, [rbx+10h]
0x1800050e8  lea     rax, [rbp+var_40]
0x1800050ec  mov     r9d, ecx; __int16
0x1800050ef  mov     [rsp+80h+var_48], rax; int *
0x1800050f4  lea     r8, [rbp+var_20]; void *
0x1800050f8  mov     [rsp+80h+var_50], cx; __int16
0x1800050fd  lea     rax, [rbp+var_20]
0x180005101  mov     rcx, cs:?g_PortClient@@3VCApiPortClient@@A; this
0x180005108  mov     [rsp+80h+var_58], rax; void *
0x18000510d  mov     [rsp+80h+var_60], rbx; struct CAlpcView *
0x180005112  call    ?SendComplexSyncRequest@CPortClient@@QEAAJKPEBXFPEBVCAlpcView@@PEAXFPEAJ@Z; CPortClient::SendComplexSyncRequest(ulong,void const *,short,CAlpcView const *,void *,short,long *)
0x180005117  lea     rcx, CriticalSection; lpCriticalSection
0x18000511e  mov     edi, eax
0x180005120  call    cs:__imp_EnterCriticalSection
0x180005126  add     cs:dword_18001F948, 0FFFFFFFFh
0x18000512d  jnz     short loc_180005141
0x18000512f  mov     rax, cs:?g_PortClient@@3VCApiPortClient@@A; CApiPortClient g_PortClient
0x180005136  mov     ecx, [rax+8]
0x180005139  test    ecx, ecx
0x18000513b  jnz     loc_1800051EE
0x180005141  mov     ecx, edi; int
0x180005143  call    ?Translate@CApiPortClient@@CAJJ@Z; CApiPortClient::Translate(long)
0x180005148  mov     edi, eax
0x18000514a  test    eax, eax
0x18000514c  js      loc_1800051FF
0x180005152  mov     ecx, [rbp+var_40]; int
0x180005155  call    ?Translate@CApiPortClient@@CAJJ@Z; CApiPortClient::Translate(long)
0x18000515a  mov     ebx, eax
0x18000515c  lea     rcx, CriticalSection; lpCriticalSection
0x180005163  call    cs:__imp_LeaveCriticalSection
0x180005169  lea     rax, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x180005170  lea     rcx, [rbp+var_30+8]
0x180005174  mov     [rbp+var_38], rax
0x180005178  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x18000517d  test    edi, edi
0x18000517f  js      short loc_1800051C8
0x180005181  test    ebx, ebx
0x180005183  jns     short loc_1800051E6
0x180005185  mov     dword ptr [rsp+80h+var_60], 258h; unsigned int
0x18000518d  mov     r9d, ebx; int
0x180005190  mov     r8d, 3; unsigned int
0x180005196  lea     rdx, qword_180019288; int *
0x18000519d  lea     ecx, [r8+1]; unsigned int
0x1800051a1  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800051a6  mov     eax, ebx
0x1800051a8  mov     rcx, [rbp+var_10]
0x1800051ac  xor     rcx, rsp; StackCookie
0x1800051af  call    __security_check_cookie
0x1800051b4  mov     rbx, [rsp+80h+arg_10]
0x1800051bc  add     rsp, 80h
0x1800051c3  pop     r14
0x1800051c5  pop     rdi
0x1800051c6  pop     rbp
0x1800051c7  retn
0x1800051c8  mov     ebx, edi
0x1800051ca  mov     dword ptr [rsp+80h+var_60], 257h
0x1800051d2  mov     r9d, edi
0x1800051d5  jmp     short loc_180005190
0x1800051d7  mov     ebx, 80070057h
0x1800051dc  mov     dword ptr [rsp+80h+var_60], 24Eh
0x1800051e4  jmp     short loc_18000518D
0x1800051e6  mov     eax, [rbp+var_20+0Ch]
0x1800051e9  mov     [r14], eax
0x1800051ec  jmp     short loc_1800051A6
0x1800051ee  lea     rcx, ?g_PortClient@@3VCApiPortClient@@A; this
0x1800051f5  call    ?Disconnect@CApiPortClient@@AEAAXXZ; CApiPortClient::Disconnect(void)
0x1800051fa  jmp     loc_180005141
0x1800051ff  mov     dword ptr [rsp+80h+var_60], 0C1h
0x180005207  jmp     short loc_180005211
0x180005209  mov     dword ptr [rsp+80h+var_60], 0ACh; unsigned int
0x180005211  mov     r8d, 2; unsigned int
0x180005217  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CApiPortClient@@0QBJB; int *
0x18000521e  mov     r9d, eax; int
0x180005221  lea     ecx, [r8+2]; unsigned int
0x180005225  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000522a  jmp     loc_18000515C
```

# CBackgroundSyncHandler::_ShouldSyncScope(ushort *,uchar,uchar,_FILETIME *)

- ea: `0x180024720`
- end: `0x180024927`
- name: `?_ShouldSyncScope@CBackgroundSyncHandler@@AEAAEPEAGEEPEAU_FILETIME@@@Z`
- size: `519`
- prototype: `unsigned __int8 __usercall@<al>(CBackgroundSyncHandler *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023728`

## callees

- `0x180010ff4`
- `0x180023f0c`
- `0x180024100`
- `0x180024720`
- `0x1800249c8`
- `0x18003fe40`
- `0x18004c198`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_GUIDFromStringW` at `0x180024768`
- `SHELL32!__imp_GUIDFromStringW` at `0x180024768`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247d1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180024828`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180024828`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002483f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002483f`

## pseudocode

```c
char __fastcall CBackgroundSyncHandler::_ShouldSyncScope(
        CBackgroundSyncHandler *this,
        unsigned __int16 *a2,
        char a3,
        char a4,
        struct _FILETIME *lpFileTime2)
{
  char v8; // bl
  __int64 v9; // r8
  __int64 v10; // r9
  CSyncItemLog *v11; // rcx
  unsigned __int8 IsNetworkHighCost; // al
  struct _FILETIME v13; // r14
  __int64 v14; // rbx
  const unsigned __int16 *v16; // [rsp+20h] [rbp-50h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-38h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-30h] BYREF
  struct _FILETIME v20; // [rsp+48h] [rbp-28h]
  FILETIME v21; // [rsp+50h] [rbp-20h]
  struct _GUID v22; // [rsp+58h] [rbp-18h] BYREF

  v22 = 0;
  v8 = 0;
  if ( (unsigned int)GUIDFromStringW(a2, &v22) )
  {
    v11 = (CSyncItemLog *)*((_QWORD *)this + 11);
    pv = 0;
    FileTime1 = 0;
    SystemTimeAsFileTime = 0;
    if ( (int)CSyncItemLog::QueryEntryByID(
                v11,
                &v22,
                (unsigned __int16 **)&pv,
                (struct IOfflineFilesSyncItem **)&SystemTimeAsFileTime,
                v16) >= 0 )
    {
      IsNetworkHighCost = CBackgroundSyncHandler::_IsNetworkHighCost(this, (const unsigned __int16 *)pv);
      v13 = SystemTimeAsFileTime;
      if ( !IsNetworkHighCost )
      {
        if ( !*((_BYTE *)this + 104) )
        {
          if ( !CBackgroundSyncHandler::_IsSlowlinkOrForcedOffline(this, (unsigned __int16 *)pv)
            || (*(int (__fastcall **)(struct _FILETIME, FILETIME *))(**(_QWORD **)&v13 + 120LL))(v13, &FileTime1) < 0 )
          {
            goto LABEL_6;
          }
          if ( a3 || a4 )
          {
            if ( lpFileTime2 && CompareFileTime(&FileTime1, lpFileTime2) == -1 )
            {
              SystemTimeAsFileTime = 0;
              GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
              v20 = SystemTimeAsFileTime;
              v21 = FileTime1;
              v14 = (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&FileTime1) / 600000000LL;
              if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids);
              }
              CscEvt_BGSyncIgnoredBlockout((const unsigned __int16 *)pv, v14);
              v8 = 1;
            }
            goto LABEL_6;
          }
        }
        v8 = 1;
      }
LABEL_6:
      CoTaskMemFree(pv);
      (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v13 + 16LL))(v13);
    }
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
  {
    LOBYTE(v10) = v8 != 0 ? 89 : 78;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v9, v10);
  }
  return v8;
}

```

## disassembly

```asm
0x180024720  mov     [rsp-28h+arg_10], rbx
0x180024725  mov     [rsp-28h+arg_18], rdi
0x18002472a  push    rbp
0x18002472b  push    r12
0x18002472d  push    r13
0x18002472f  push    r14
0x180024731  push    r15
0x180024733  mov     rbp, rsp
0x180024736  sub     rsp, 70h
0x18002473a  mov     rax, cs:__security_cookie
0x180024741  xor     rax, rsp
0x180024744  mov     [rbp+var_8], rax
0x180024748  mov     r15, [rbp+lpFileTime2]
0x18002474c  mov     rax, rdx
0x18002474f  mov     rdi, rcx
0x180024752  lea     rdx, [rbp+var_18]
0x180024756  xorps   xmm0, xmm0
0x180024759  mov     rcx, rax
0x18002475c  mov     r13b, r9b
0x18002475f  mov     r12b, r8b
0x180024762  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x180024766  xor     bl, bl
0x180024768  call    cs:__imp_GUIDFromStringW
0x18002476e  test    eax, eax
0x180024770  jz      loc_1800248C6
0x180024776  mov     rcx, [rdi+58h]; this
0x18002477a  lea     r9, [rbp+SystemTimeAsFileTime]; struct IOfflineFilesSyncItem **
0x18002477e  lea     r8, [rbp+pv]; unsigned __int16 **
0x180024782  mov     [rbp+pv], 0
0x18002478a  lea     rdx, [rbp+var_18]; struct _GUID *
0x18002478e  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x180024796  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002479e  call    ?QueryEntryByID@CSyncItemLog@@QEAAJPEAU_GUID@@PEAPEAGPEAPEAUIOfflineFilesSyncItem@@PEBG@Z; CSyncItemLog::QueryEntryByID(_GUID *,ushort * *,IOfflineFilesSyncItem * *,ushort const *)
0x1800247a3  test    eax, eax
0x1800247a5  js      loc_1800248C6
0x1800247ab  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800247af  mov     rcx, rdi; this
0x1800247b2  call    ?_IsNetworkHighCost@CBackgroundSyncHandler@@AEAAEPEBG@Z; CBackgroundSyncHandler::_IsNetworkHighCost(ushort const *)
0x1800247b7  mov     r14, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800247bb  test    al, al
0x1800247bd  jnz     short loc_1800247C6
0x1800247bf  cmp     [rdi+68h], bl
0x1800247c2  jz      short loc_1800247EB
0x1800247c4  mov     bl, 1
0x1800247c6  lea     rdi, WPP_GLOBAL_Control
0x1800247cd  mov     rcx, [rbp+pv]; pv
0x1800247d1  call    cs:__imp_CoTaskMemFree
0x1800247d7  mov     rax, [r14]
0x1800247da  mov     rcx, r14
0x1800247dd  mov     rax, [rax+10h]
0x1800247e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247e6  jmp     loc_1800248CD
0x1800247eb  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800247ef  mov     rcx, rdi; this
0x1800247f2  call    ?_IsSlowlinkOrForcedOffline@CBackgroundSyncHandler@@AEAAEPEAG@Z; CBackgroundSyncHandler::_IsSlowlinkOrForcedOffline(ushort *)
0x1800247f7  test    al, al
0x1800247f9  jz      short loc_1800247C6
0x1800247fb  mov     rax, [r14]
0x1800247fe  lea     rdx, [rbp+FileTime1]
0x180024802  mov     rcx, r14
0x180024805  mov     rax, [rax+78h]
0x180024809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002480e  test    eax, eax
0x180024810  js      short loc_1800247C6
0x180024812  test    r12b, r12b
0x180024815  jnz     short loc_18002481C
0x180024817  test    r13b, r13b
0x18002481a  jz      short loc_1800247C4
0x18002481c  test    r15, r15
0x18002481f  jz      short loc_1800247C6
0x180024821  mov     rdx, r15; lpFileTime2
0x180024824  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180024828  call    cs:__imp_CompareFileTime
0x18002482e  cmp     eax, 0FFFFFFFFh
0x180024831  jnz     short loc_1800247C6
0x180024833  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180024837  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002483f  call    cs:__imp_GetSystemTimeAsFileTime
0x180024845  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x180024848  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002484b  mov     dword ptr [rbp+var_28], eax
0x18002484e  mov     eax, [rbp+FileTime1.dwLowDateTime]
0x180024851  mov     dword ptr [rbp+var_20], eax
0x180024854  mov     rax, 1CA213D840BAF7D5h
0x18002485e  mov     dword ptr [rbp+var_28+4], ecx
0x180024861  mov     ecx, [rbp+FileTime1.dwHighDateTime]
0x180024864  mov     dword ptr [rbp+var_20+4], ecx
0x180024867  mov     rcx, [rbp+var_28]
0x18002486b  sub     rcx, [rbp+var_20]
0x18002486f  imul    rcx
0x180024872  mov     rbx, rdx
0x180024875  sar     rbx, 1Ah
0x180024879  mov     rax, rbx
0x18002487c  shr     rax, 3Fh
0x180024880  add     rbx, rax
0x180024883  mov     rcx, cs:WPP_GLOBAL_Control
0x18002488a  lea     rdi, WPP_GLOBAL_Control
0x180024891  cmp     rcx, rdi
0x180024894  jz      short loc_1800248B4
0x180024896  test    dword ptr [rcx+1Ch], 100000h
0x18002489d  jz      short loc_1800248B4
0x18002489f  mov     rcx, [rcx+10h]
0x1800248a3  lea     r8, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids
0x1800248aa  mov     edx, 1Ah
0x1800248af  call    WPP_SF_
0x1800248b4  mov     rcx, [rbp+pv]; unsigned __int16 *
0x1800248b8  mov     edx, ebx; unsigned int
0x1800248ba  call    ?CscEvt_BGSyncIgnoredBlockout@@YAKPEBGK@Z; CscEvt_BGSyncIgnoredBlockout(ushort const *,ulong)
0x1800248bf  mov     bl, 1
0x1800248c1  jmp     loc_1800247CD
0x1800248c6  lea     rdi, WPP_GLOBAL_Control
0x1800248cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248d4  cmp     rcx, rdi
0x1800248d7  jz      short loc_1800248FF
0x1800248d9  test    dword ptr [rcx+1Ch], 100000h
0x1800248e0  jz      short loc_1800248FF
0x1800248e2  mov     rcx, [rcx+10h]
0x1800248e6  mov     dl, bl
0x1800248e8  neg     dl
0x1800248ea  mov     edx, 1Bh
0x1800248ef  sbb     r9b, r9b
0x1800248f2  and     r9b, 0Bh
0x1800248f6  add     r9b, 4Eh ; 'N'
0x1800248fa  call    WPP_SF_c
0x1800248ff  mov     al, bl
0x180024901  mov     rcx, [rbp+var_8]
0x180024905  xor     rcx, rsp; StackCookie
0x180024908  call    __security_check_cookie
0x18002490d  lea     r11, [rsp+70h+var_s0]
0x180024912  mov     rbx, [r11+40h]
0x180024916  mov     rdi, [r11+48h]
0x18002491a  mov     rsp, r11
0x18002491d  pop     r15
0x18002491f  pop     r14
0x180024921  pop     r13
0x180024923  pop     r12
0x180024925  pop     rbp
0x180024926  retn
```

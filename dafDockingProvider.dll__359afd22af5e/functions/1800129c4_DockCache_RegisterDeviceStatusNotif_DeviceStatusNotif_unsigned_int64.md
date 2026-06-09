# DockCache::RegisterDeviceStatusNotif(DeviceStatusNotif &,unsigned __int64 *)

- ea: `0x1800129c4`
- end: `0x180012b2c`
- name: `?RegisterDeviceStatusNotif@DockCache@@QEAAJAEAVDeviceStatusNotif@@PEA_K@Z`
- size: `360`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, wchar_t *String1, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c020`

## callees

- `0x180001588`
- `0x18000c308`
- `0x1800129c4`
- `0x180013114`
- `0x18001ca4a`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800129e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800129e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012ade`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012aed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012aff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012ade`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012aed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012aff`

## pseudocode

```c
__int64 __fastcall DockCache::RegisterDeviceStatusNotif(
        LPCRITICAL_SECTION lpCriticalSection,
        wchar_t *String1,
        unsigned __int64 *a3)
{
  void *v6; // rcx
  char *v7; // rbx
  ULONG_PTR SpinCount; // r14
  __int64 v9; // rdx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  PRTL_CRITICAL_SECTION_DEBUG v11; // rbx
  __int64 v12; // rcx

  EnterCriticalSection(lpCriticalSection);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      lpCriticalSection);
  }
  try
  {
    v7 = (char *)lpCriticalSection[2].LockSemaphore + 1;
    *((_QWORD *)String1 + 75) = v7;
    SpinCount = lpCriticalSection[1].SpinCount;
    v9 = std::_List_val<DeviceStatusNotif>::_Buynode(v6, SpinCount, *(_QWORD *)(SpinCount + 8), String1);
    DebugInfo = lpCriticalSection[2].DebugInfo;
    if ( DebugInfo == (PRTL_CRITICAL_SECTION_DEBUG)0x6BCA1AF286BCA0LL )
      std::_Xlength_error("list<T> too long");
    lpCriticalSection[2].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)&DebugInfo->Type + 1);
    *(_QWORD *)(SpinCount + 8) = v9;
    **(_QWORD **)(v9 + 8) = v9;
    lpCriticalSection[2].LockSemaphore = v7;
    *a3 = (unsigned __int64)v7;
    v11 = lpCriticalSection[1].DebugInfo;
  }
  catch ( std::bad_alloc )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
        lpCriticalSection);
    }
    LeaveCriticalSection(lpCriticalSection);
    return 2147942414LL;
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
        lpCriticalSection);
    }
    LeaveCriticalSection(lpCriticalSection);
    return 2147500037LL;
  }
  while ( v11 != *(PRTL_CRITICAL_SECTION_DEBUG *)&lpCriticalSection[1].LockCount )
  {
    if ( BYTE1(v11[60].EntryCount) )
    {
      if ( !wcsncmp_0(String1, &v11->Type, 0x125u) )
      {
        v12 = *((_QWORD *)String1 + 74);
        if ( v12 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 64LL))(
            v12,
            (((int)v11[60].ContentionCount >> 31) & 0xFFFFFFFD) + 3);
      }
    }
    v11 = (PRTL_CRITICAL_SECTION_DEBUG)((char *)v11 + 2936);
  }
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x1800129c4  mov     rax, rsp
0x1800129c7  mov     [rax+18h], rbx
0x1800129cb  mov     [rax+20h], rsi
0x1800129cf  mov     [rax+8], rcx
0x1800129d3  push    rdi
0x1800129d4  push    r14
0x1800129d6  push    r15
0x1800129d8  sub     rsp, 20h
0x1800129dc  mov     r15, r8
0x1800129df  mov     rsi, rdx
0x1800129e2  mov     rdi, rcx
0x1800129e5  mov     [rax+10h], rcx
0x1800129e9  call    cs:__imp_EnterCriticalSection
0x1800129ef  nop
0x1800129f0  lea     rax, WPP_GLOBAL_Control
0x1800129f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129fe  cmp     rcx, rax
0x180012a01  jz      short loc_180012A27
0x180012a03  cmp     byte ptr [rcx+19h], 3
0x180012a07  jb      short loc_180012A27
0x180012a09  test    byte ptr [rcx+1Ch], 1
0x180012a0d  jz      short loc_180012A27
0x180012a0f  mov     edx, 42h ; 'B'
0x180012a14  mov     r9, rdi
0x180012a17  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x180012a1e  mov     rcx, [rcx+10h]
0x180012a22  call    WPP_SF_q
0x180012a27  mov     rbx, [rdi+68h]
0x180012a2b  inc     rbx
0x180012a2e  mov     [rsi+258h], rbx
0x180012a35  mov     r14, [rdi+48h]
0x180012a39  mov     r9, rsi
0x180012a3c  mov     r8, [r14+8]
0x180012a40  mov     rdx, r14
0x180012a43  call    ?_Buynode@?$_List_val@VDeviceStatusNotif@@V?$allocator@VDeviceStatusNotif@@@std@@@std@@QEAAPEAU_Node@?$_List_nod@VDeviceStatusNotif@@V?$allocator@VDeviceStatusNotif@@@std@@@2@PEAU342@0AEBVDeviceStatusNotif@@@Z; std::_List_val<DeviceStatusNotif>::_Buynode(std::_List_nod<DeviceStatusNotif>::_Node *,std::_List_nod<DeviceStatusNotif>::_Node *,DeviceStatusNotif const &)
0x180012a48  mov     rdx, rax
0x180012a4b  mov     rax, [rdi+50h]
0x180012a4f  mov     rcx, 6BCA1AF286BCA0h
0x180012a59  sub     rcx, rax
0x180012a5c  cmp     rcx, 1
0x180012a60  jb      loc_180012B1E
0x180012a66  inc     rax
0x180012a69  mov     [rdi+50h], rax
0x180012a6d  mov     [r14+8], rdx
0x180012a71  mov     rax, [rdx+8]
0x180012a75  mov     [rax], rdx
0x180012a78  mov     [rdi+68h], rbx
0x180012a7c  mov     [r15], rbx
0x180012a7f  mov     rbx, [rdi+28h]
0x180012a83  cmp     rbx, [rdi+30h]
0x180012a87  jz      short loc_180012ADB
0x180012a89  cmp     byte ptr [rbx+0B61h], 0
0x180012a90  jz      short loc_180012AD2
0x180012a92  mov     r8d, 125h; MaxCount
0x180012a98  mov     rdx, rbx; String2
0x180012a9b  mov     rcx, rsi; String1
0x180012a9e  call    wcsncmp_0
0x180012aa3  test    eax, eax
0x180012aa5  jnz     short loc_180012AD2
0x180012aa7  mov     rcx, [rsi+250h]
0x180012aae  test    rcx, rcx
0x180012ab1  jz      short loc_180012AD2
0x180012ab3  mov     r8d, [rbx+0B64h]
0x180012aba  mov     rax, [rcx]
0x180012abd  mov     edx, r8d
0x180012ac0  sar     edx, 1Fh
0x180012ac3  and     edx, 0FFFFFFFDh
0x180012ac6  add     edx, 3
0x180012ac9  mov     rax, [rax+40h]
0x180012acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ad2  add     rbx, 0B78h
0x180012ad9  jmp     short loc_180012A83
0x180012adb  mov     rcx, rdi; lpCriticalSection
0x180012ade  call    cs:__imp_LeaveCriticalSection
0x180012ae4  xor     eax, eax
0x180012ae6  jmp     short loc_180012B0A
0x180012ae8  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180012aed  call    cs:__imp_LeaveCriticalSection
0x180012af3  mov     eax, 8007000Eh
0x180012af8  jmp     short loc_180012B0A
0x180012afa  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180012aff  call    cs:__imp_LeaveCriticalSection
0x180012b05  mov     eax, 80004005h
0x180012b0a  mov     rbx, [rsp+38h+arg_10]
0x180012b0f  mov     rsi, [rsp+38h+arg_18]
0x180012b14  add     rsp, 20h
0x180012b18  pop     r15
0x180012b1a  pop     r14
0x180012b1c  pop     rdi
0x180012b1d  retn
0x180012b1e  lea     rcx, aListTTooLong; "list<T> too long"
0x180012b25  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```

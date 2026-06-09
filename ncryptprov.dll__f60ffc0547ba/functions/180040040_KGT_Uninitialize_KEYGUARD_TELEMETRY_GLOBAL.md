# KGT_Uninitialize(KEYGUARD_TELEMETRY_GLOBAL *)

- ea: `0x180040040`
- end: `0x180040124`
- name: `?KGT_Uninitialize@@YAXPEAUKEYGUARD_TELEMETRY_GLOBAL@@@Z`
- size: `228`
- prototype: `void __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024af4`

## callees

- `0x18001d350`
- `0x180035de0`
- `0x180035fc8`
- `0x180036860`
- `0x180040040`
- `0x180040474`
- `0x1800404ec`
- `0x180062310`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180040076`
- `ntdll!RtlDeleteCriticalSection` at `0x180040086`
- `ntdll!RtlDeleteCriticalSection` at `0x180040076`
- `ntdll!RtlDeleteCriticalSection` at `0x180040086`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800400a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800400a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall KGT_Uninitialize(PRTL_CRITICAL_SECTION CriticalSection)
{
  __int64 ***v2; // rdi
  __int64 **i; // rbx
  _QWORD *SpinCount; // rdi
  _QWORD *j; // rbx
  _BYTE v6[32]; // [rsp+20h] [rbp-58h] BYREF
  struct KEYGUARD_TELEMETRY_IMAGE_T *v7; // [rsp+40h] [rbp-38h]

  TlgUnregisterAggregateProvider(&dword_180079160);
  TlgUnregisterAggregateProvider(&dword_180079128);
  RtlDeleteCriticalSection(CriticalSection);
  RtlDeleteCriticalSection(CriticalSection + 1);
  v2 = *(__int64 ****)&CriticalSection[2].LockCount;
  for ( i = *v2; i != (__int64 **)v2; i = (__int64 **)*i )
    LocalFree(i[3]);
  std::_Hash<std::_Umap_traits<unsigned long,KEYGUARD_TELEMETRY_PID *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,KEYGUARD_TELEMETRY_PID *>>,0>>::clear(&CriticalSection[2]);
  SpinCount = (_QWORD *)CriticalSection[3].SpinCount;
  for ( j = (_QWORD *)*SpinCount; j != SpinCount; j = (_QWORD *)*j )
  {
    std::wstring::wstring(v6, j + 2);
    v7 = (struct KEYGUARD_TELEMETRY_IMAGE_T *)j[6];
    KGT_FreeImage(v7);
    std::wstring::~wstring(v6);
  }
  std::_Hash<std::_Umap_traits<std::wstring,KEYGUARD_TELEMETRY_IMAGE_T *,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,KEYGUARD_TELEMETRY_IMAGE_T *>>,0>>::clear(&CriticalSection[3].LockSemaphore);
  dword_18007A77C = 0;
}

```

## disassembly

```asm
0x180040040  push    rbx
0x180040042  push    rbp
0x180040043  push    rsi
0x180040044  push    rdi
0x180040045  sub     rsp, 58h
0x180040049  mov     rax, cs:__security_cookie
0x180040050  xor     rax, rsp
0x180040053  mov     [rsp+78h+var_30], rax
0x180040058  mov     rbp, rcx
0x18004005b  lea     rcx, dword_180079160
0x180040062  call    TlgUnregisterAggregateProvider
0x180040067  lea     rcx, dword_180079128
0x18004006e  call    TlgUnregisterAggregateProvider
0x180040073  mov     rcx, rbp; CriticalSection
0x180040076  call    cs:__imp_RtlDeleteCriticalSection
0x18004007d  nop     dword ptr [rax+rax+00h]
0x180040082  lea     rcx, [rbp+28h]; CriticalSection
0x180040086  call    cs:__imp_RtlDeleteCriticalSection
0x18004008d  nop     dword ptr [rax+rax+00h]
0x180040092  mov     rdi, [rbp+58h]
0x180040096  mov     rbx, [rdi]
0x180040099  cmp     rbx, rdi
0x18004009c  jz      short loc_1800400B3
0x18004009e  mov     rcx, [rbx+18h]; hMem
0x1800400a2  call    cs:__imp_LocalFree
0x1800400a9  nop     dword ptr [rax+rax+00h]
0x1800400ae  mov     rbx, [rbx]
0x1800400b1  jmp     short loc_180040099
0x1800400b3  lea     rcx, [rbp+50h]
0x1800400b7  call    ?clear@?$_Hash@V?$_Umap_traits@KPEAUKEYGUARD_TELEMETRY_PID@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUKEYGUARD_TELEMETRY_PID@@@std@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<ulong,KEYGUARD_TELEMETRY_PID *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,KEYGUARD_TELEMETRY_PID *>>,0>>::clear(void)
0x1800400bc  mov     rdi, [rbp+98h]
0x1800400c3  mov     rbx, [rdi]
0x1800400c6  cmp     rbx, rdi
0x1800400c9  jz      short loc_1800400F7
0x1800400cb  lea     rdx, [rbx+10h]
0x1800400cf  lea     rcx, [rsp+78h+var_58]
0x1800400d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800400d9  mov     rcx, [rbx+30h]; struct KEYGUARD_TELEMETRY_IMAGE_T *
0x1800400dd  mov     [rsp+78h+var_38], rcx
0x1800400e2  call    ?KGT_FreeImage@@YAXPEAUKEYGUARD_TELEMETRY_IMAGE_T@@@Z; KGT_FreeImage(KEYGUARD_TELEMETRY_IMAGE_T *)
0x1800400e7  nop
0x1800400e8  lea     rcx, [rsp+78h+var_58]
0x1800400ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800400f2  mov     rbx, [rbx]
0x1800400f5  jmp     short loc_1800400C6
0x1800400f7  lea     rcx, [rbp+90h]
0x1800400fe  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUKEYGUARD_TELEMETRY_IMAGE_T@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUKEYGUARD_TELEMETRY_IMAGE_T@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,KEYGUARD_TELEMETRY_IMAGE_T *,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,KEYGUARD_TELEMETRY_IMAGE_T *>>,0>>::clear(void)
0x180040103  mov     cs:dword_18007A77C, 0
0x18004010d  mov     rcx, [rsp+78h+var_30]
0x180040112  xor     rcx, rsp; StackCookie
0x180040115  call    __security_check_cookie
0x18004011a  add     rsp, 58h
0x18004011e  pop     rdi
0x18004011f  pop     rsi
0x180040120  pop     rbp
0x180040121  pop     rbx
0x180040122  retn
```

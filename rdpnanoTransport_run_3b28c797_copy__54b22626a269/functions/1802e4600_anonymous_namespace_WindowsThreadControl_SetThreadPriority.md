# _anonymous_namespace_::WindowsThreadControl::SetThreadPriority

- ea: `0x1802e4600`
- end: `0x1802e483b`
- name: `_anonymous_namespace_::WindowsThreadControl::SetThreadPriority`
- size: `571`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018ea4`
- `0x18004569c`
- `0x1802e4600`
- `0x1802e483c`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802e476e`
- `KERNEL32!GetLastError` at `0x1802e476e`
- `KERNEL32!GetCurrentThread` at `0x1802e4732`
- `KERNEL32!GetCurrentThread` at `0x1802e4732`
- `KERNEL32!SetThreadPriority` at `0x1802e473d`
- `KERNEL32!SetThreadPriority` at `0x1802e473d`

## string_xrefs

- `0x1802e463c`: `C:\__w\1\s\src\libbasix\pattern\windowsthreadcontrol.cpp`
- `0x1802e4635`: ``anonymous-namespace'::WindowsThreadControl::SetThreadPriority`
- `0x1802e469e`: `Unknown thread priority! Defaulting to Normal\n    %s(%d): %s()`
- `0x1802e478b`: `Failed to set thread priority to %d: %d \n    %s(%d): %s()`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
signed __int32 __fastcall anonymous_namespace_::WindowsThreadControl::SetThreadPriority(__int64 a1, int a2)
{
  int v2; // edx
  int v3; // edx
  int v4; // edi
  int v5; // r9d
  volatile signed __int32 *v6; // rbx
  HANDLE CurrentThread; // rax
  signed __int32 result; // eax
  char LastError; // bl
  int v10; // r9d
  volatile signed __int32 *v11; // rbx
  const char *v12; // [rsp+20h] [rbp-60h]
  int v13; // [rsp+28h] [rbp-58h]
  const char *v14; // [rsp+30h] [rbp-50h]
  __int128 v15; // [rsp+40h] [rbp-40h] BYREF
  __int128 v16; // [rsp+50h] [rbp-30h]
  __int128 v17; // [rsp+60h] [rbp-20h] BYREF

  if ( a2 )
  {
    v2 = a2 - 1;
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( v3 )
      {
        if ( v3 == 1 )
        {
          v4 = 15;
        }
        else
        {
          v4 = 0;
          v17 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v17);
          if ( (_QWORD)v17 && *(_BYTE *)(v17 + 128) )
          {
            v15 = 0;
            v16 = 0;
            std::string::_Construct<1,char const *>(
              &v15,
              "Unknown thread priority! Defaulting to Normal\n    %s(%d): %s()",
              (const char *)0x3E,
              v5,
              v12);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
              (unsigned int)&v17,
              (unsigned int)"BASIX_PATTERN",
              (unsigned int)&v15,
              (unsigned int)"C:\\__w\\1\\s\\src\\libbasix\\pattern\\windowsthreadcontrol.cpp",
              68,
              (__int64)"`anonymous-namespace'::WindowsThreadControl::SetThreadPriority");
            std::string::_Tidy_deallocate(&v15);
          }
          v6 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
          if ( *((_QWORD *)&v17 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
              if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
            }
          }
        }
      }
      else
      {
        v4 = 0;
      }
    }
    else
    {
      v4 = -1;
    }
  }
  else
  {
    v4 = -2;
  }
  CurrentThread = GetCurrentThread();
  result = SetThreadPriority(CurrentThread, v4);
  if ( !result )
  {
    v17 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v17);
    result = v17;
    if ( (_QWORD)v17 && *(_BYTE *)(v17 + 128) )
    {
      LastError = GetLastError();
      v15 = 0;
      v16 = 0;
      std::string::_Construct<1,char const *>(
        &v15,
        "Failed to set thread priority to %d: %d \n    %s(%d): %s()",
        57,
        v10,
        v12,
        v13,
        v14);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,unsigned long,char const *,int,char const *>(
        (unsigned int)&v17,
        (unsigned int)"BASIX_PATTERN",
        (unsigned int)&v15,
        v4,
        LastError,
        (__int64)"C:\\__w\\1\\s\\src\\libbasix\\pattern\\windowsthreadcontrol.cpp",
        74,
        (__int64)"`anonymous-namespace'::WindowsThreadControl::SetThreadPriority");
      result = std::string::_Tidy_deallocate(&v15);
    }
    v11 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
    if ( *((_QWORD *)&v17 + 1) )
    {
      result = _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL));
      if ( !result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        result = _InterlockedDecrement(v11 + 3);
        if ( !result )
          return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1802e4600  mov     [rsp-18h+arg_0], rbx
0x1802e4605  mov     [rsp-18h+arg_8], rsi
0x1802e460a  mov     [rsp-18h+arg_10], rdi
0x1802e460f  push    rbp
0x1802e4610  push    r14
0x1802e4612  push    r15
0x1802e4614  mov     rbp, rsp
0x1802e4617  mov     eax, 80h
0x1802e461c  call    _alloca_probe
0x1802e4621  sub     rsp, rax
0x1802e4624  mov     rax, cs:__security_cookie
0x1802e462b  xor     rax, rsp
0x1802e462e  mov     [rbp+var_10], rax
0x1802e4632  or      esi, 0FFFFFFFFh
0x1802e4635  lea     r14, aAnonymousNames_1; "`anonymous-namespace'::WindowsThreadCon"...
0x1802e463c  lea     r15, aCW1SSrcLibbasi_48; "C:\\__w\\1\\s\\src\\libbasix\\pattern\\"...
0x1802e4643  test    edx, edx
0x1802e4645  jz      loc_1802E472D
0x1802e464b  sub     edx, 1
0x1802e464e  jz      loc_1802E4729
0x1802e4654  sub     edx, 1
0x1802e4657  jz      loc_1802E4725
0x1802e465d  cmp     edx, 1
0x1802e4660  jz      loc_1802E471E
0x1802e4666  xor     edi, edi
0x1802e4668  xorps   xmm0, xmm0
0x1802e466b  movups  [rbp+var_20], xmm0
0x1802e466f  lea     rcx, [rbp+var_20]
0x1802e4673  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1802e4678  nop
0x1802e4679  mov     rax, qword ptr [rbp+var_20]
0x1802e467d  test    rax, rax
0x1802e4680  jz      short loc_1802E46DE
0x1802e4682  cmp     [rax+80h], dil
0x1802e4689  jz      short loc_1802E46DE
0x1802e468b  xorps   xmm0, xmm0
0x1802e468e  movups  [rbp+var_40], xmm0
0x1802e4692  xorps   xmm1, xmm1
0x1802e4695  movdqu  [rbp+var_30], xmm1
0x1802e469a  lea     r8d, [rsi+3Fh]
0x1802e469e  lea     rdx, aUnknownThreadP; "Unknown thread priority! Defaulting to "...
0x1802e46a5  lea     rcx, [rbp+var_40]
0x1802e46a9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1802e46ae  nop
0x1802e46af  mov     [rsp+80h+var_58], r14
0x1802e46b4  mov     dword ptr [rsp+80h+var_60], 44h ; 'D'
0x1802e46bc  mov     r9, r15
0x1802e46bf  lea     r8, [rbp+var_40]
0x1802e46c3  lea     rdx, aBasixPattern; "BASIX_PATTERN"
0x1802e46ca  lea     rcx, [rbp+var_20]
0x1802e46ce  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x1802e46d3  nop
0x1802e46d4  lea     rcx, [rbp+var_40]
0x1802e46d8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802e46dd  nop
0x1802e46de  mov     rbx, qword ptr [rbp+var_20+8]
0x1802e46e2  test    rbx, rbx
0x1802e46e5  jz      short loc_1802E4732
0x1802e46e7  mov     eax, esi
0x1802e46e9  lock xadd [rbx+8], eax
0x1802e46ee  add     eax, esi
0x1802e46f0  jnz     short loc_1802E4732
0x1802e46f2  mov     rax, [rbx]
0x1802e46f5  mov     rcx, rbx
0x1802e46f8  mov     rax, [rax]
0x1802e46fb  call    cs:__guard_dispatch_icall_fptr
0x1802e4701  mov     eax, esi
0x1802e4703  lock xadd [rbx+0Ch], eax
0x1802e4708  add     eax, esi
0x1802e470a  jnz     short loc_1802E4732
0x1802e470c  mov     rax, [rbx]
0x1802e470f  mov     rcx, rbx
0x1802e4712  mov     rax, [rax+8]
0x1802e4716  call    cs:__guard_dispatch_icall_fptr
0x1802e471c  jmp     short loc_1802E4732
0x1802e471e  mov     edi, 0Fh
0x1802e4723  jmp     short loc_1802E4732
0x1802e4725  xor     edi, edi
0x1802e4727  jmp     short loc_1802E4732
0x1802e4729  mov     edi, esi
0x1802e472b  jmp     short loc_1802E4732
0x1802e472d  mov     edi, 0FFFFFFFEh
0x1802e4732  call    cs:__imp_GetCurrentThread
0x1802e4738  mov     rcx, rax; hThread
0x1802e473b  mov     edx, edi; nPriority
0x1802e473d  call    cs:__imp_SetThreadPriority
0x1802e4743  test    eax, eax
0x1802e4745  jnz     loc_1802E4812
0x1802e474b  xorps   xmm0, xmm0
0x1802e474e  movups  [rbp+var_20], xmm0
0x1802e4752  lea     rcx, [rbp+var_20]
0x1802e4756  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1802e475b  nop
0x1802e475c  mov     rax, qword ptr [rbp+var_20]
0x1802e4760  test    rax, rax
0x1802e4763  jz      short loc_1802E47D4
0x1802e4765  cmp     byte ptr [rax+80h], 0
0x1802e476c  jz      short loc_1802E47D4
0x1802e476e  call    cs:__imp_GetLastError
0x1802e4774  mov     ebx, eax
0x1802e4776  xorps   xmm0, xmm0
0x1802e4779  movups  [rbp+var_40], xmm0
0x1802e477d  xorps   xmm1, xmm1
0x1802e4780  movdqu  [rbp+var_30], xmm1
0x1802e4785  mov     r8d, 39h ; '9'
0x1802e478b  lea     rdx, aFailedToSetThr_0; "Failed to set thread priority to %d: %d"...
0x1802e4792  lea     rcx, [rbp+var_40]
0x1802e4796  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1802e479b  nop
0x1802e479c  mov     [rsp+80h+var_48], r14
0x1802e47a1  mov     dword ptr [rsp+80h+var_50], 4Ah ; 'J'
0x1802e47a9  mov     [rsp+80h+var_58], r15
0x1802e47ae  mov     dword ptr [rsp+80h+var_60], ebx
0x1802e47b2  mov     r9d, edi
0x1802e47b5  lea     r8, [rbp+var_40]
0x1802e47b9  lea     rdx, aBasixPattern; "BASIX_PATTERN"
0x1802e47c0  lea     rcx, [rbp+var_20]
0x1802e47c4  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@HKPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@HK1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,ulong,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,int,ulong,char const *,int,char const *)
0x1802e47c9  nop
0x1802e47ca  lea     rcx, [rbp+var_40]
0x1802e47ce  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802e47d3  nop
0x1802e47d4  mov     rbx, qword ptr [rbp+var_20+8]
0x1802e47d8  test    rbx, rbx
0x1802e47db  jz      short loc_1802E4812
0x1802e47dd  mov     eax, esi
0x1802e47df  lock xadd [rbx+8], eax
0x1802e47e4  add     eax, esi
0x1802e47e6  jnz     short loc_1802E4812
0x1802e47e8  mov     rax, [rbx]
0x1802e47eb  mov     rcx, rbx
0x1802e47ee  mov     rax, [rax]
0x1802e47f1  call    cs:__guard_dispatch_icall_fptr
0x1802e47f7  mov     eax, esi
0x1802e47f9  lock xadd [rbx+0Ch], eax
0x1802e47fe  add     eax, esi
0x1802e4800  jnz     short loc_1802E4812
0x1802e4802  mov     rax, [rbx]
0x1802e4805  mov     rcx, rbx
0x1802e4808  mov     rax, [rax+8]
0x1802e480c  call    cs:__guard_dispatch_icall_fptr
0x1802e4812  mov     rcx, [rbp+var_10]
0x1802e4816  xor     rcx, rsp; StackCookie
0x1802e4819  call    __security_check_cookie
0x1802e481e  lea     r11, [rsp+80h+var_s0]
0x1802e4826  mov     rbx, [r11+20h]
0x1802e482a  mov     rsi, [r11+28h]
0x1802e482e  mov     rdi, [r11+30h]
0x1802e4832  mov     rsp, r11
0x1802e4835  pop     r15
0x1802e4837  pop     r14
0x1802e4839  pop     rbp
0x1802e483a  retn
```

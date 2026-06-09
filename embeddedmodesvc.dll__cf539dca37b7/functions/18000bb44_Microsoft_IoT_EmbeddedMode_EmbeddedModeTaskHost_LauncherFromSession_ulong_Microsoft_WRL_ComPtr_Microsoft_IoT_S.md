# Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LauncherFromSession(ulong,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> &)

- ea: `0x18000bb44`
- end: `0x18000bc86`
- name: `?LauncherFromSession@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@AEAAJKAEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@4@@Z`
- size: `322`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b3e8`
- `0x18000ba9c`

## callees

- `0x180008358`
- `0x180008378`
- `0x180009f34`
- `0x18000a098`
- `0x18000ba64`
- `0x18000bb44`
- `0x18000bea0`
- `0x18000c3b0`
- `0x180011290`

## string_xrefs

- `0x18000bbb1`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`
- `0x18000bbef`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`
- `0x18000bc58`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LauncherFromSession(
        __int64 a1,
        int a2,
        _QWORD *a3)
{
  __int64 v6; // rsi
  __int64 v7; // rbx
  int v8; // r9d
  int CBTLauncher; // eax
  const char *v10; // r9
  volatile int *v11; // rdx
  const char *v12; // r9
  __int64 result; // rax
  int v14; // [rsp+20h] [rbp-58h]
  wil::ResultException *v15; // [rsp+30h] [rbp-48h] BYREF
  std::bad_alloc *v16; // [rsp+38h] [rbp-40h] BYREF
  std::invalid_argument *v17; // [rsp+40h] [rbp-38h] BYREF
  std::range_error *v18; // [rsp+48h] [rbp-30h] BYREF
  std::runtime_error *v19; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v21; // [rsp+88h] [rbp+10h]

  v6 = a1 + 48;
  v7 = *(_QWORD *)(a1 + 48);
  try
  {
    while ( 1 )
    {
      if ( v7 == *(_QWORD *)(a1 + 56) )
      {
        Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(a3);
        CBTLauncher = Microsoft::IoT::ShellExtension::CCBTLauncher::CreateCBTLauncher(
                        a1 != 0 ? a1 + 32 : 0,
                        (int)a1 + 72,
                        a2,
                        v8,
                        (__int64)a3);
        if ( CBTLauncher < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
            (const char *)(unsigned int)CBTLauncher,
            v14);
        if ( !*a3 )
          wil::details::in1diag3::_FailFast_NullAlloc(
            retaddr,
            (void *)0x35,
            (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
            v10);
        if ( *(_QWORD *)(v6 + 8) == *(_QWORD *)(v6 + 16) )
        {
          std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> const &>(
            v6,
            *(_QWORD *)(v6 + 8),
            a3);
        }
        else
        {
          std::_Construct_in_place<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> const &>(
            *(_QWORD *)(v6 + 8),
            a3);
          *(_QWORD *)(v6 + 8) += 8LL;
        }
        goto LABEL_27;
      }
      if ( *(_DWORD *)(*(_QWORD *)v7 + 184LL) == a2 )
        break;
      v7 += 8;
    }
    Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(a3);
    if ( *(_QWORD *)v7 )
      Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(*(_QWORD *)v7 + 44LL), v11);
    *a3 = *(_QWORD *)v7;
  }
  catch ( wil::ResultException *v15 )
  {
    v21 = *((_DWORD *)v15 + 8);
    if ( v21 < 0 )
LABEL_17:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
        (const char *)(unsigned int)v21,
        v14);
LABEL_18:
    result = (unsigned int)v21;
  }
  catch ( std::bad_alloc *v16 )
  {
    v21 = -2147024882;
    goto LABEL_17;
  }
  catch ( std::invalid_argument *v17 )
  {
    v21 = -2147024809;
    goto LABEL_17;
  }
  catch ( std::range_error *v18 )
  {
    v21 = -2147483637;
    goto LABEL_17;
  }
  catch ( std::runtime_error *v19 )
  {
    v21 = -2147467259;
    goto LABEL_17;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
      v12);
  }
LABEL_27:
  v21 = 0;
  goto LABEL_18;
}

```

## disassembly

```asm
0x18000bb44  mov     [rsp+arg_0], rbx
0x18000bb49  mov     [rsp+arg_10], rsi
0x18000bb4e  push    rdi
0x18000bb4f  push    r14
0x18000bb51  push    r15
0x18000bb53  sub     rsp, 60h
0x18000bb57  mov     rdi, r8
0x18000bb5a  mov     r15d, edx
0x18000bb5d  mov     r14, rcx
0x18000bb60  lea     rsi, [rcx+30h]
0x18000bb64  mov     rbx, [rsi]
0x18000bb67  jmp     short loc_18000BB79
0x18000bb69  mov     rax, [rbx]
0x18000bb6c  cmp     [rax+0B8h], r15d
0x18000bb73  jz      short loc_18000BBC3
0x18000bb75  add     rbx, 8
0x18000bb79  cmp     rbx, [rcx+38h]
0x18000bb7d  jnz     short loc_18000BB69
0x18000bb7f  mov     rcx, rdi
0x18000bb82  call    ?InternalRelease@?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(void)
0x18000bb87  lea     rdx, [r14+48h]
0x18000bb8b  lea     rax, [r14+20h]
0x18000bb8f  neg     r14
0x18000bb92  sbb     rcx, rcx
0x18000bb95  and     rcx, rax
0x18000bb98  mov     qword ptr [rsp+78h+var_58], rdi; int
0x18000bb9d  mov     r8d, r15d
0x18000bba0  call    ?CreateCBTLauncher@CCBTLauncher@ShellExtension@IoT@Microsoft@@SAJPEAUILauncherControl@234@AEAV?$shared_ptr@VMTAThreadPool@Utility@IoT@Microsoft@@@std@@K_NPEAPEAV1234@@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::CreateCBTLauncher(Microsoft::IoT::ShellExtension::ILauncherControl *,std::shared_ptr<Microsoft::IoT::Utility::MTAThreadPool> &,ulong,bool,Microsoft::IoT::ShellExtension::CCBTLauncher * *)
0x18000bba5  mov     rcx, [rsp+78h]; this
0x18000bbaa  test    eax, eax
0x18000bbac  jns     short loc_18000BBE4
0x18000bbae  mov     r9d, eax; char *
0x18000bbb1  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000bbb8  mov     edx, 34h ; '4'; void *
0x18000bbbd  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000bbc3  mov     rcx, rdi
0x18000bbc6  call    ?InternalRelease@?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(void)
0x18000bbcb  mov     rcx, [rbx]
0x18000bbce  test    rcx, rcx
0x18000bbd1  jz      short loc_18000BBDC
0x18000bbd3  add     rcx, 2Ch ; ','; this
0x18000bbd7  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18000bbdc  mov     rax, [rbx]
0x18000bbdf  mov     [rdi], rax
0x18000bbe2  jmp     short loc_18000BC2C
0x18000bbe4  mov     rcx, [rsp+78h]; this
0x18000bbe9  cmp     qword ptr [rdi], 0
0x18000bbed  jnz     short loc_18000BC01
0x18000bbef  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000bbf6  mov     edx, 35h ; '5'; void *
0x18000bbfb  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18000bc01  mov     rax, [rsi+8]
0x18000bc05  cmp     rax, [rsi+10h]
0x18000bc09  jz      short loc_18000BC1D
0x18000bc0b  mov     rdx, rdi
0x18000bc0e  mov     rcx, rax
0x18000bc11  call    ??$_Construct_in_place@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@AEBV123@@std@@YAXAEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@AEBV123@@Z; std::_Construct_in_place<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> const &>(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> &,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> const &)
0x18000bc16  add     qword ptr [rsi+8], 8
0x18000bc1b  jmp     short loc_18000BC2C
0x18000bc1d  mov     r8, rdi
0x18000bc20  mov     rdx, rax
0x18000bc23  mov     rcx, rsi
0x18000bc26  call    ??$_Emplace_reallocate@AEBV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> const &>(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> const &)
0x18000bc2b  nop
0x18000bc2c  mov     dword ptr [rsp+78h+arg_8], 0
0x18000bc37  jmp     short loc_18000BC69
0x18000bc39  cmp     dword ptr [rsp+78h+arg_8], 0
0x18000bc41  jge     short loc_18000BC69
0x18000bc43  jmp     short loc_18000BC4B
0x18000bc45  jmp     short loc_18000BC4B
0x18000bc47  jmp     short loc_18000BC4B
0x18000bc49  jmp     short $+2
0x18000bc4b  mov     rcx, [rsp+78h]; this
0x18000bc50  mov     r9d, dword ptr [rsp+78h+arg_8]; char *
0x18000bc58  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000bc5f  mov     edx, 3Ah ; ':'; void *
0x18000bc64  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bc69  mov     eax, dword ptr [rsp+78h+arg_8]
0x18000bc70  lea     r11, [rsp+78h+var_18]
0x18000bc75  mov     rbx, [r11+20h]
0x18000bc79  mov     rsi, [r11+30h]
0x18000bc7d  mov     rsp, r11
0x18000bc80  pop     r15
0x18000bc82  pop     r14
0x18000bc84  pop     rdi
0x18000bc85  retn
```

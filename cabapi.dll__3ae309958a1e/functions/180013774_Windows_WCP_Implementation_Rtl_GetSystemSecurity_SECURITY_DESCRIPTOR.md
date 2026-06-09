# Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)

- ea: `0x180013774`
- end: `0x180013838`
- name: `?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180010124`

## callees

- `0x180001940`
- `0x180002350`
- `0x1800023b8`
- `0x180012fd8`
- `0x180013040`
- `0x180013774`

## string_xrefs

- `0x1800137b4`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1800137e4`: `g_SystemSecurityStatus`
- `0x1800137d0`: `Windows::WCP::Implementation::Rtl::GetSystemSecurity`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::GetSystemSecurity(
        Windows::WCP::Implementation::Rtl *this,
        struct _SECURITY_DESCRIPTOR **a2)
{
  unsigned int v3; // ebx
  _QWORD v5[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( dword_180021858 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180021858);
    if ( dword_180021858 == -1 )
    {
      Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()();
      atexit(Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__);
      Init_thread_footer(&dword_180021858);
    }
  }
  *(_QWORD *)this = P;
  v3 = dword_180021848;
  if ( dword_180021848 >= 0 )
    return 0;
  v5[2] = 194;
  v5[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
  v5[1] = "Windows::WCP::Implementation::Rtl::GetSystemSecurity";
  v5[3] = "g_SystemSecurityStatus";
  RtlReportErrorOrigination(v5, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)dword_180021848);
  return v3;
}

```

## disassembly

```asm
0x180013774  push    rbx
0x180013776  sub     rsp, 40h
0x18001377a  mov     edx, cs:_tls_index
0x180013780  mov     rbx, rcx
0x180013783  mov     rax, gs:58h
0x18001378c  mov     ecx, 4
0x180013791  mov     rax, [rax+rdx*8]
0x180013795  mov     edx, [rcx+rax]
0x180013798  cmp     cs:dword_180021858, edx
0x18001379e  jg      short loc_180013801
0x1800137a0  mov     rax, qword ptr cs:P
0x1800137a7  mov     [rbx], rax
0x1800137aa  mov     ebx, cs:dword_180021848
0x1800137b0  test    ebx, ebx
0x1800137b2  jns     short loc_1800137F9
0x1800137b4  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1800137bb  mov     [rsp+48h+var_18], 0C2h
0x1800137c4  mov     [rsp+48h+var_28], rax
0x1800137c9  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800137d0  lea     rax, aWindowsWcpImpl_0; "Windows::WCP::Implementation::Rtl::GetS"...
0x1800137d7  mov     r8d, ebx
0x1800137da  mov     [rsp+48h+var_20], rax
0x1800137df  lea     rcx, [rsp+48h+var_28]
0x1800137e4  lea     rax, aGSystemsecurit; "g_SystemSecurityStatus"
0x1800137eb  mov     [rsp+48h+var_10], rax
0x1800137f0  call    RtlReportErrorOrigination
0x1800137f5  mov     eax, ebx
0x1800137f7  jmp     short loc_1800137FB
0x1800137f9  xor     eax, eax
0x1800137fb  add     rsp, 40h
0x1800137ff  pop     rbx
0x180013800  retn
0x180013801  lea     rcx, dword_180021858
0x180013808  call    _Init_thread_header
0x18001380d  cmp     cs:dword_180021858, 0FFFFFFFFh
0x180013814  jnz     short loc_1800137A0
0x180013816  call    _Windows__WCP__Implementation__Rtl__GetSystemSecurity____5____lambda_1___operator__
0x18001381b  lea     rcx, _Windows__WCP__Implementation__Rtl__GetSystemSecurity____5____dynamic_atexit_destructor_for__g_SystemSecurity__; void (__cdecl *)()
0x180013822  call    atexit
0x180013827  lea     rcx, dword_180021858
0x18001382e  call    _Init_thread_footer
0x180013833  jmp     loc_1800137A0
```

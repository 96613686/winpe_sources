# InitializeDataPlugin(IUnknown *,HKEY__ *,IUnknown * *,IKsVideoProcessing * *)

- ea: `0x18003004c`
- end: `0x180030180`
- name: `?InitializeDataPlugin@@YAJPEAUIUnknown@@PEAUHKEY__@@PEAPEAU1@PEAPEAUIKsVideoProcessing@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnkOuter, HKEY, LPVOID *ppv, struct IKsVideoProcessing **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002cac4`

## callees

- `0x180015bc8`
- `0x18001f620`
- `0x18003004c`
- `0x180031dc8`
- `0x180045010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800300b3`
- `KERNEL32!QueryPerformanceCounter` at `0x18003012a`
- `KERNEL32!QueryPerformanceCounter` at `0x1800300b3`
- `KERNEL32!QueryPerformanceCounter` at `0x18003012a`
- `ole32!CoCreateInstance` at `0x1800300d9`
- `ole32!CoCreateInstance` at `0x1800300d9`

## pseudocode

```c
__int64 __fastcall InitializeDataPlugin(LPUNKNOWN pUnkOuter, HKEY a2, LPVOID *ppv, struct IKsVideoProcessing **a4)
{
  LSTATUS PlginCLSID; // ebx
  __int64 v8; // r8
  LARGE_INTEGER v10; // [rsp+30h] [rbp-58h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-50h] BYREF
  IID rclsid; // [rsp+40h] [rbp-48h] BYREF

  PerformanceCount.QuadPart = 0;
  v10.QuadPart = 0;
  rclsid = 0;
  PlginCLSID = GetPlginCLSID(a2, (BYTE *)&rclsid);
  if ( PlginCLSID >= 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      QueryPerformanceCounter(&PerformanceCount);
    PlginCLSID = CoCreateInstance(&rclsid, pUnkOuter, 0x401u, &GUID_00000000_0000_0000_c000_000000000046, ppv);
    if ( PlginCLSID >= 0 )
    {
      PlginCLSID = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IKsVideoProcessing **))*ppv)(
                     *ppv,
                     &GUID_2efc7721_05da_4ac6_8300_635e373d839e,
                     a4);
      if ( PlginCLSID >= 0 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 16LL))(*a4);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          QueryPerformanceCounter(&v10);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v8, v10.QuadPart - PerformanceCount.QuadPart);
        }
      }
    }
  }
  return (unsigned int)PlginCLSID;
}

```

## disassembly

```asm
0x18003004c  push    rbx
0x18003004e  push    rbp
0x18003004f  push    rsi
0x180030050  push    rdi
0x180030051  sub     rsp, 68h
0x180030055  mov     rax, cs:__security_cookie
0x18003005c  xor     rax, rsp
0x18003005f  mov     [rsp+88h+var_38], rax
0x180030064  mov     rax, rdx
0x180030067  mov     qword ptr [rsp+88h+PerformanceCount], 0
0x180030070  mov     rbp, rcx
0x180030073  mov     qword ptr [rsp+88h+var_58], 0
0x18003007c  xorps   xmm0, xmm0
0x18003007f  lea     rdx, [rsp+88h+rclsid]; struct _GUID *
0x180030084  mov     rcx, rax; HKEY
0x180030087  mov     rsi, r9
0x18003008a  mov     rdi, r8
0x18003008d  movups  xmmword ptr [rsp+88h+rclsid.Data1], xmm0
0x180030092  call    ?GetPlginCLSID@@YAJPEAUHKEY__@@PEAU_GUID@@@Z; GetPlginCLSID(HKEY__ *,_GUID *)
0x180030097  mov     ebx, eax
0x180030099  test    eax, eax
0x18003009b  js      loc_180030167
0x1800300a1  mov     rax, cs:WPP_GLOBAL_Control
0x1800300a8  test    byte ptr [rax+1Ch], 20h
0x1800300ac  jz      short loc_1800300BF
0x1800300ae  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x1800300b3  call    cs:__imp_QueryPerformanceCounter
0x1800300ba  nop     dword ptr [rax+rax+00h]
0x1800300bf  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800300c6  mov     [rsp+88h+ppv], rdi; ppv
0x1800300cb  mov     r8d, 401h; dwClsContext
0x1800300d1  lea     rcx, [rsp+88h+rclsid]; rclsid
0x1800300d6  mov     rdx, rbp; pUnkOuter
0x1800300d9  call    cs:__imp_CoCreateInstance
0x1800300e0  nop     dword ptr [rax+rax+00h]
0x1800300e5  mov     ebx, eax
0x1800300e7  test    eax, eax
0x1800300e9  js      short loc_180030167
0x1800300eb  mov     rcx, [rdi]
0x1800300ee  lea     rdx, _GUID_2efc7721_05da_4ac6_8300_635e373d839e
0x1800300f5  mov     r8, rsi
0x1800300f8  mov     rax, [rcx]
0x1800300fb  mov     rax, [rax]
0x1800300fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030103  mov     ebx, eax
0x180030105  test    eax, eax
0x180030107  js      short loc_180030167
0x180030109  mov     rcx, [rsi]
0x18003010c  mov     rax, [rcx]
0x18003010f  mov     rax, [rax+10h]
0x180030113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030118  mov     rax, cs:WPP_GLOBAL_Control
0x18003011f  test    byte ptr [rax+1Ch], 20h
0x180030123  jz      short loc_180030167
0x180030125  lea     rcx, [rsp+88h+var_58]; lpPerformanceCount
0x18003012a  call    cs:__imp_QueryPerformanceCounter
0x180030131  nop     dword ptr [rax+rax+00h]
0x180030136  mov     rcx, cs:WPP_GLOBAL_Control
0x18003013d  lea     rax, WPP_GLOBAL_Control
0x180030144  cmp     rcx, rax
0x180030147  jz      short loc_180030167
0x180030149  cmp     byte ptr [rcx+19h], 2
0x18003014d  jb      short loc_180030167
0x18003014f  mov     r9, qword ptr [rsp+88h+var_58]
0x180030154  mov     edx, 0Ah
0x180030159  sub     r9, qword ptr [rsp+88h+PerformanceCount]
0x18003015e  mov     rcx, [rcx+10h]
0x180030162  call    WPP_SF_i
0x180030167  mov     eax, ebx
0x180030169  mov     rcx, [rsp+88h+var_38]
0x18003016e  xor     rcx, rsp; StackCookie
0x180030171  call    __security_check_cookie
0x180030176  add     rsp, 68h
0x18003017a  pop     rdi
0x18003017b  pop     rsi
0x18003017c  pop     rbp
0x18003017d  pop     rbx
0x18003017e  retn
```

# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1800219a0`
- end: `0x180021ad4`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180021d70`

## callees

- `0x1800026b0`
- `0x18001a964`
- `0x1800219a0`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180021a6d`
- `KERNEL32!GetModuleHandleW` at `0x180021a6d`
- `KERNEL32!GetProcAddress` at `0x180021a8a`
- `KERNEL32!GetProcAddress` at `0x180021a8a`

## string_xrefs

- `0x180021a66`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  unsigned int v4; // esi
  __int64 v5; // rax
  unsigned int v6; // edi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v10; // [rsp+30h] [rbp-58h] BYREF
  int v11; // [rsp+34h] [rbp-54h]
  _BYTE v12[24]; // [rsp+38h] [rbp-50h] BYREF
  __int128 v13; // [rsp+50h] [rbp-38h] BYREF
  __int64 v14; // [rsp+60h] [rbp-28h]

  v3 = a2;
  v4 = a3;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(v12, &Feature_ShadowAdmin__private_reporting, a3, HIDWORD(a2));
  v6 = 0;
  v13 = *(_OWORD *)v5;
  v14 = *(_QWORD *)(v5 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(60288851, v4, 1, &Feature_ShadowAdmin__private_reporting, &v13);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v10 = 60288851;
    v11 = (unsigned __int16)v4;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v11) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_11;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_11:
      ((void (__fastcall *)(int *))ProcAddress)(&v10);
  }
  LOBYTE(v6) = (_DWORD)v14 == 0;
  return v6;
}

```

## disassembly

```asm
0x1800219a0  mov     [rsp+arg_0], rbx
0x1800219a5  push    rbp
0x1800219a6  push    rsi
0x1800219a7  push    rdi
0x1800219a8  sub     rsp, 70h
0x1800219ac  mov     rax, cs:__security_cookie
0x1800219b3  xor     rax, rsp
0x1800219b6  mov     [rsp+88h+var_20], rax
0x1800219bb  mov     r9, rdx
0x1800219be  lea     rcx, [rsp+88h+var_50]
0x1800219c3  mov     rbx, rdx
0x1800219c6  shr     r9, 20h
0x1800219ca  mov     rdx, cs:off_18002DC40
0x1800219d1  mov     esi, r8d
0x1800219d4  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800219d9  xor     edi, edi
0x1800219db  mov     ebp, 1
0x1800219e0  movups  xmm1, xmmword ptr [rax]
0x1800219e3  movups  [rsp+88h+var_38], xmm1
0x1800219e8  movsd   xmm0, qword ptr [rax+10h]
0x1800219ed  mov     rax, cs:g_wil_details_recordFeatureUsage
0x1800219f4  movsd   [rsp+88h+var_28], xmm0
0x1800219fa  test    rax, rax
0x1800219fd  jz      short loc_180021A1F
0x1800219ff  mov     r9, cs:off_18002DC40
0x180021a06  lea     rcx, [rsp+88h+var_38]
0x180021a0b  mov     [rsp+88h+var_68], rcx
0x180021a10  mov     r8d, ebp
0x180021a13  mov     ecx, 397EF53h
0x180021a18  mov     edx, esi
0x180021a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a1f  bt      ebx, 0Ah
0x180021a23  jnb     loc_180021AAC
0x180021a29  cmp     esi, 0FEh
0x180021a2f  jz      short loc_180021AAC
0x180021a31  mov     [rsp+88h+var_58], rdi
0x180021a36  mov     dword ptr [rsp+88h+var_58], 397EF53h
0x180021a3e  mov     word ptr [rsp+88h+var_58+4], si
0x180021a43  bt      ebx, 0Bh
0x180021a47  jnb     short loc_180021A4E
0x180021a49  or      word ptr [rsp+88h+var_58+6], bp
0x180021a4e  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180021a55  test    rax, rax
0x180021a58  jnz     short loc_180021AA2
0x180021a5a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180021a61  test    rax, rax
0x180021a64  jnz     short loc_180021A80
0x180021a66  lea     rcx, ModuleName; "ntdll.dll"
0x180021a6d  call    cs:__imp_GetModuleHandleW
0x180021a74  nop     dword ptr [rax+rax+00h]
0x180021a79  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180021a80  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180021a87  mov     rcx, rax; hModule
0x180021a8a  call    cs:__imp_GetProcAddress
0x180021a91  nop     dword ptr [rax+rax+00h]
0x180021a96  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180021a9d  test    rax, rax
0x180021aa0  jz      short loc_180021AAC
0x180021aa2  lea     rcx, [rsp+88h+var_58]
0x180021aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aac  cmp     dword ptr [rsp+88h+var_28], edi
0x180021ab0  setz    dil
0x180021ab4  mov     eax, edi
0x180021ab6  mov     rcx, [rsp+88h+var_20]
0x180021abb  xor     rcx, rsp; StackCookie
0x180021abe  call    __security_check_cookie
0x180021ac3  mov     rbx, [rsp+88h+arg_0]
0x180021acb  add     rsp, 70h
0x180021acf  pop     rdi
0x180021ad0  pop     rsi
0x180021ad1  pop     rbp
0x180021ad2  retn
```

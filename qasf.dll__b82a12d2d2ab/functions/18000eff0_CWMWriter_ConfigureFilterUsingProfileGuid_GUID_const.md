# CWMWriter::ConfigureFilterUsingProfileGuid(_GUID const &)

- ea: `0x18000eff0`
- end: `0x18000f13e`
- name: `?ConfigureFilterUsingProfileGuid@CWMWriter@@UEAAJAEBU_GUID@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x18000eff0`
- `0x18001f010`

## import_xrefs

- `WMVCore!WMCreateProfileManager` at `0x18000f055`
- `WMVCore!WMCreateProfileManager` at `0x18000f055`
- `KERNEL32!EnterCriticalSection` at `0x18000f041`
- `KERNEL32!EnterCriticalSection` at `0x18000f041`
- `KERNEL32!LeaveCriticalSection` at `0x18000f113`
- `KERNEL32!LeaveCriticalSection` at `0x18000f113`

## pseudocode

```c
__int64 __fastcall CWMWriter::ConfigureFilterUsingProfileGuid(CWMWriter *this, const struct _GUID *a2)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  HRESULT v7; // ebx
  CWMWriter *v8; // [rsp+40h] [rbp-38h] BYREF
  IWMProfileManager *ppProfileManager; // [rsp+48h] [rbp-30h] BYREF

  v8 = this;
  if ( *((_DWORD *)this - 28) )
    return 2147746343LL;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  ppProfileManager = 0;
  v7 = WMCreateProfileManager(&ppProfileManager);
  if ( v7 >= 0 )
  {
    v8 = 0;
    v7 = ((__int64 (__fastcall *)(IWMProfileManager *, const struct _GUID *, CWMWriter **))ppProfileManager->lpVtbl->LoadProfileByID)(
           ppProfileManager,
           a2,
           &v8);
    if ( v7 >= 0 )
      v7 = (*(__int64 (__fastcall **)(CWMWriter *, CWMWriter *))(*(_QWORD *)this + 56LL))(this, v8);
    if ( v8 )
      (*(void (__fastcall **)(CWMWriter *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  *((_DWORD *)this + 52) = -1;
  if ( v7 >= 0 )
  {
    *((_DWORD *)this + 57) = 1;
    *(struct _GUID *)((char *)this + 212) = *a2;
  }
  if ( ppProfileManager )
    ((void (__fastcall *)(IWMProfileManager *))ppProfileManager->lpVtbl->Release)(ppProfileManager);
  LeaveCriticalSection(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000eff0  mov     [rsp+arg_10], rbx
0x18000eff5  mov     [rsp+arg_18], rsi
0x18000effa  push    rdi
0x18000effb  push    r14
0x18000effd  push    r15
0x18000efff  sub     rsp, 60h
0x18000f003  mov     rax, cs:__security_cookie
0x18000f00a  xor     rax, rsp
0x18000f00d  mov     [rsp+78h+var_28], rax
0x18000f012  mov     r15, rdx
0x18000f015  mov     r14, rcx
0x18000f018  mov     rdi, rcx
0x18000f01b  mov     [rsp+78h+var_38], rcx
0x18000f020  mov     [rsp+78h+var_50], rdx
0x18000f025  cmp     dword ptr [rcx-70h], 0
0x18000f029  jz      short loc_18000F035
0x18000f02b  mov     eax, 80040227h
0x18000f030  jmp     loc_18000F11B
0x18000f035  lea     rsi, [rcx+58h]
0x18000f039  mov     [rsp+78h+var_40], rsi
0x18000f03e  mov     rcx, rsi; lpCriticalSection
0x18000f041  call    cs:__imp_EnterCriticalSection
0x18000f047  mov     [rsp+78h+ppProfileManager], 0
0x18000f050  lea     rcx, [rsp+78h+ppProfileManager]; ppProfileManager
0x18000f055  call    cs:__imp_WMCreateProfileManager
0x18000f05b  mov     ebx, eax
0x18000f05d  mov     [rsp+78h+var_58], eax
0x18000f061  jmp     short loc_18000F07E
0x18000f063  mov     ebx, 8007007Eh
0x18000f068  mov     [rsp+78h+var_58], ebx
0x18000f06c  mov     rdi, [rsp+78h+var_38]
0x18000f071  mov     r15, [rsp+78h+var_50]
0x18000f076  mov     r14, rdi
0x18000f079  mov     rsi, [rsp+78h+var_40]
0x18000f07e  test    ebx, ebx
0x18000f080  js      short loc_18000F0D6
0x18000f082  mov     [rsp+78h+var_38], 0
0x18000f08b  mov     rcx, [rsp+78h+ppProfileManager]
0x18000f090  mov     rax, [rcx]
0x18000f093  lea     r8, [rsp+78h+var_38]
0x18000f098  mov     rdx, r15
0x18000f09b  mov     rax, [rax+20h]
0x18000f09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0a4  mov     ebx, eax
0x18000f0a6  test    eax, eax
0x18000f0a8  js      short loc_18000F0C0
0x18000f0aa  mov     rax, [r14]
0x18000f0ad  mov     rdx, [rsp+78h+var_38]
0x18000f0b2  mov     rcx, rdi
0x18000f0b5  mov     rax, [rax+38h]
0x18000f0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0be  mov     ebx, eax
0x18000f0c0  mov     rcx, [rsp+78h+var_38]
0x18000f0c5  test    rcx, rcx
0x18000f0c8  jz      short loc_18000F0D6
0x18000f0ca  mov     rax, [rcx]
0x18000f0cd  mov     rax, [rax+10h]
0x18000f0d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0d6  mov     dword ptr [rdi+0D0h], 0FFFFFFFFh
0x18000f0e0  test    ebx, ebx
0x18000f0e2  js      short loc_18000F0FA
0x18000f0e4  mov     dword ptr [rdi+0E4h], 1
0x18000f0ee  movups  xmm0, xmmword ptr [r15]
0x18000f0f2  movdqu  xmmword ptr [rdi+0D4h], xmm0
0x18000f0fa  mov     rcx, [rsp+78h+ppProfileManager]
0x18000f0ff  test    rcx, rcx
0x18000f102  jz      short loc_18000F110
0x18000f104  mov     rax, [rcx]
0x18000f107  mov     rax, [rax+10h]
0x18000f10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f110  mov     rcx, rsi; lpCriticalSection
0x18000f113  call    cs:__imp_LeaveCriticalSection
0x18000f119  mov     eax, ebx
0x18000f11b  mov     rcx, [rsp+78h+var_28]
0x18000f120  xor     rcx, rsp; StackCookie
0x18000f123  call    __security_check_cookie
0x18000f128  lea     r11, [rsp+78h+var_18]
0x18000f12d  mov     rbx, [r11+30h]
0x18000f131  mov     rsi, [r11+38h]
0x18000f135  mov     rsp, r11
0x18000f138  pop     r15
0x18000f13a  pop     r14
0x18000f13c  pop     rdi
0x18000f13d  retn
```

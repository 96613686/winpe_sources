# CWMWriter::ConfigureFilterUsingProfileId(ulong)

- ea: `0x18000f150`
- end: `0x18000f2c7`
- name: `?ConfigureFilterUsingProfileId@CWMWriter@@UEAAJK@Z`
- size: `375`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x18000f150`
- `0x18001f010`

## import_xrefs

- `WMVCore!WMCreateProfileManager` at `0x18000f1b3`
- `WMVCore!WMCreateProfileManager` at `0x18000f1b3`
- `KERNEL32!EnterCriticalSection` at `0x18000f19f`
- `KERNEL32!EnterCriticalSection` at `0x18000f19f`
- `KERNEL32!LeaveCriticalSection` at `0x18000f29c`
- `KERNEL32!LeaveCriticalSection` at `0x18000f29c`

## pseudocode

```c
__int64 __fastcall CWMWriter::ConfigureFilterUsingProfileId(CWMWriter *this, unsigned int a2)
{
  unsigned int v2; // esi
  struct _RTL_CRITICAL_SECTION *v6; // r14
  HRESULT v7; // ebx
  __int64 v8; // [rsp+40h] [rbp-38h] BYREF
  IWMProfileManager *ppProfileManager; // [rsp+48h] [rbp-30h] BYREF

  v2 = a2;
  LODWORD(v8) = a2;
  if ( *((_DWORD *)this - 28) )
    return 2147746343LL;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  ppProfileManager = 0;
  v7 = WMCreateProfileManager(&ppProfileManager);
  if ( v7 < 0 )
    goto LABEL_14;
  LODWORD(v8) = 0;
  v7 = ((__int64 (__fastcall *)(IWMProfileManager *, __int64 *))ppProfileManager->lpVtbl->GetSystemProfileCount)(
         ppProfileManager,
         &v8);
  if ( v7 >= 0 && v2 >= (unsigned int)v8 )
    v7 = -2147467259;
  if ( v7 < 0 )
    goto LABEL_14;
  v8 = 0;
  v7 = ((__int64 (__fastcall *)(IWMProfileManager *, _QWORD, __int64 *))ppProfileManager->lpVtbl->LoadSystemProfile)(
         ppProfileManager,
         v2,
         &v8);
  if ( v7 >= 0 )
    v7 = (*(__int64 (__fastcall **)(CWMWriter *, __int64))(*(_QWORD *)this + 56LL))(this, v8);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v7 < 0 )
LABEL_14:
    v2 = -1;
  else
    *((_DWORD *)this + 57) = 2;
  *((_DWORD *)this + 52) = v2;
  if ( ppProfileManager )
    ((void (__fastcall *)(IWMProfileManager *))ppProfileManager->lpVtbl->Release)(ppProfileManager);
  LeaveCriticalSection(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f150  mov     [rsp+arg_10], rbx
0x18000f155  mov     [rsp+arg_18], rsi
0x18000f15a  push    rdi
0x18000f15b  push    r14
0x18000f15d  push    r15
0x18000f15f  sub     rsp, 60h
0x18000f163  mov     rax, cs:__security_cookie
0x18000f16a  xor     rax, rsp
0x18000f16d  mov     [rsp+78h+var_28], rax
0x18000f172  mov     esi, edx
0x18000f174  mov     r15, rcx
0x18000f177  mov     rdi, rcx
0x18000f17a  mov     [rsp+78h+var_50], rcx
0x18000f17f  mov     dword ptr [rsp+78h+var_38], edx
0x18000f183  cmp     dword ptr [rcx-70h], 0
0x18000f187  jz      short loc_18000F193
0x18000f189  mov     eax, 80040227h
0x18000f18e  jmp     loc_18000F2A4
0x18000f193  lea     r14, [rcx+58h]
0x18000f197  mov     [rsp+78h+var_40], r14
0x18000f19c  mov     rcx, r14; lpCriticalSection
0x18000f19f  call    cs:__imp_EnterCriticalSection
0x18000f1a5  mov     [rsp+78h+ppProfileManager], 0
0x18000f1ae  lea     rcx, [rsp+78h+ppProfileManager]; ppProfileManager
0x18000f1b3  call    cs:__imp_WMCreateProfileManager
0x18000f1b9  mov     ebx, eax
0x18000f1bb  mov     [rsp+78h+var_58], eax
0x18000f1bf  jmp     short loc_18000F1DB
0x18000f1c1  mov     ebx, 8007007Eh
0x18000f1c6  mov     [rsp+78h+var_58], ebx
0x18000f1ca  mov     rdi, [rsp+78h+var_50]
0x18000f1cf  mov     esi, dword ptr [rsp+78h+var_38]
0x18000f1d3  mov     r15, rdi
0x18000f1d6  mov     r14, [rsp+78h+var_40]
0x18000f1db  test    ebx, ebx
0x18000f1dd  js      loc_18000F27A
0x18000f1e3  mov     dword ptr [rsp+78h+var_38], 0
0x18000f1eb  mov     rcx, [rsp+78h+ppProfileManager]
0x18000f1f0  mov     rax, [rcx]
0x18000f1f3  lea     rdx, [rsp+78h+var_38]
0x18000f1f8  mov     rax, [rax+38h]
0x18000f1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f201  mov     ebx, eax
0x18000f203  test    eax, eax
0x18000f205  js      short loc_18000F213
0x18000f207  mov     eax, 80004005h
0x18000f20c  cmp     esi, dword ptr [rsp+78h+var_38]
0x18000f210  cmovnb  ebx, eax
0x18000f213  test    ebx, ebx
0x18000f215  js      short loc_18000F27A
0x18000f217  mov     [rsp+78h+var_38], 0
0x18000f220  mov     rcx, [rsp+78h+ppProfileManager]
0x18000f225  mov     rax, [rcx]
0x18000f228  lea     r8, [rsp+78h+var_38]
0x18000f22d  mov     edx, esi
0x18000f22f  mov     rax, [rax+40h]
0x18000f233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f238  mov     ebx, eax
0x18000f23a  test    eax, eax
0x18000f23c  js      short loc_18000F254
0x18000f23e  mov     rax, [r15]
0x18000f241  mov     rdx, [rsp+78h+var_38]
0x18000f246  mov     rcx, rdi
0x18000f249  mov     rax, [rax+38h]
0x18000f24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f252  mov     ebx, eax
0x18000f254  mov     rcx, [rsp+78h+var_38]
0x18000f259  test    rcx, rcx
0x18000f25c  jz      short loc_18000F26A
0x18000f25e  mov     rax, [rcx]
0x18000f261  mov     rax, [rax+10h]
0x18000f265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f26a  test    ebx, ebx
0x18000f26c  js      short loc_18000F27A
0x18000f26e  mov     dword ptr [rdi+0E4h], 2
0x18000f278  jmp     short loc_18000F27D
0x18000f27a  or      esi, 0FFFFFFFFh
0x18000f27d  mov     [rdi+0D0h], esi
0x18000f283  mov     rcx, [rsp+78h+ppProfileManager]
0x18000f288  test    rcx, rcx
0x18000f28b  jz      short loc_18000F299
0x18000f28d  mov     rax, [rcx]
0x18000f290  mov     rax, [rax+10h]
0x18000f294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f299  mov     rcx, r14; lpCriticalSection
0x18000f29c  call    cs:__imp_LeaveCriticalSection
0x18000f2a2  mov     eax, ebx
0x18000f2a4  mov     rcx, [rsp+78h+var_28]
0x18000f2a9  xor     rcx, rsp; StackCookie
0x18000f2ac  call    __security_check_cookie
0x18000f2b1  lea     r11, [rsp+78h+var_18]
0x18000f2b6  mov     rbx, [r11+30h]
0x18000f2ba  mov     rsi, [r11+38h]
0x18000f2be  mov     rsp, r11
0x18000f2c1  pop     r15
0x18000f2c3  pop     r14
0x18000f2c5  pop     rdi
0x18000f2c6  retn
```

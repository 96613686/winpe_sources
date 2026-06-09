# CPnpNotification::FinalConstruct(void)

- ea: `0x18000c144`
- end: `0x18000c334`
- name: `?FinalConstruct@CPnpNotification@@IEAAJXZ`
- size: `496`
- prototype: `__int64 __fastcall(CPnpNotification *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bfcc`

## callees

- `0x18000bce4`
- `0x18000bd30`
- `0x18000c144`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c19d`
- `KERNEL32!GetLastError` at `0x18000c19d`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000c193`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000c193`
- `ole32!CoCreateInstance` at `0x18000c1de`
- `ole32!CoCreateInstance` at `0x18000c1de`

## pseudocode

```c
__int64 __fastcall CPnpNotification::FinalConstruct(CPnpNotification *this)
{
  signed int LastError; // eax
  unsigned int Instance; // ebx
  _QWORD *v4; // rsi
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // eax
  bool v9; // cf
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF

  v11 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 72), 0) )
  {
    LastError = GetLastError();
    Instance = LastError;
    if ( LastError > 0 )
      Instance = (unsigned __int16)LastError | 0x80070000;
    if ( Instance )
      goto LABEL_15;
  }
  *((_DWORD *)this + 16) = 1;
  Instance = CoCreateInstance(
               &GUID_c72be2ec_8e90_452c_b29a_ab8ff1c071fc,
               0,
               3u,
               &IID_IFunctionDiscovery,
               (LPVOID *)this + 14);
  if ( Instance )
    goto LABEL_15;
  v4 = (_QWORD *)((char *)this + 120);
  Instance = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *, __int64, CPnpNotification *, _QWORD, char *))(**((_QWORD **)this + 14) + 40LL))(
               *((_QWORD *)this + 14),
               L"Provider\\Microsoft.Base.PnP",
               &qword_1800166A0,
               1,
               this,
               0,
               (char *)this + 120);
  if ( Instance )
    goto LABEL_15;
  Instance = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)*v4 + 24LL))(
               *v4,
               L"NotifyOnly",
               L"TRUE");
  if ( Instance )
    goto LABEL_15;
  Instance = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)*v4 + 24LL))(
               *v4,
               L"NotPresent",
               L"TRUE");
  if ( Instance )
    goto LABEL_15;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 40LL))(*v4, &v11);
  Instance = v5;
  if ( v5 == -2147483638 )
  {
    Instance = 0;
    goto LABEL_19;
  }
  if ( v5 )
  {
LABEL_15:
    v6 = *((_QWORD *)this + 15);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      *((_QWORD *)this + 15) = 0;
    }
    v7 = *((_QWORD *)this + 14);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *((_QWORD *)this + 14) = 0;
    }
  }
LABEL_19:
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v8 = 0;
  if ( Instance )
    v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v8) = !v9;
    if ( v8 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
  }
  return Instance;
}

```

## disassembly

```asm
0x18000c144  push    rbx
0x18000c146  push    rsi
0x18000c147  push    rdi
0x18000c148  push    r15
0x18000c14a  sub     rsp, 48h
0x18000c14e  mov     rdi, rcx
0x18000c151  mov     [rsp+68h+arg_0], 0
0x18000c15a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c161  lea     r15, WPP_GLOBAL_Control
0x18000c168  cmp     rcx, r15
0x18000c16b  jz      short loc_18000C18D
0x18000c16d  cmp     byte ptr [rcx+19h], 4
0x18000c171  jb      short loc_18000C18D
0x18000c173  mov     rcx, [rcx+10h]
0x18000c177  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c17e  mov     edx, 31h ; '1'
0x18000c183  mov     [rsp+68h+ppv], rdi
0x18000c188  call    WPP_SF_sq
0x18000c18d  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000c191  xor     edx, edx; dwSpinCount
0x18000c193  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000c199  test    eax, eax
0x18000c19b  jnz     short loc_18000C1BA
0x18000c19d  call    cs:__imp_GetLastError
0x18000c1a3  mov     ebx, eax
0x18000c1a5  test    eax, eax
0x18000c1a7  jle     short loc_18000C1B2
0x18000c1a9  movzx   ebx, ax
0x18000c1ac  or      ebx, 80070000h
0x18000c1b2  test    ebx, ebx
0x18000c1b4  jnz     loc_18000C297
0x18000c1ba  xor     edx, edx; pUnkOuter
0x18000c1bc  mov     dword ptr [rdi+40h], 1
0x18000c1c3  lea     rsi, [rdi+70h]
0x18000c1c7  lea     r9, IID_IFunctionDiscovery; riid
0x18000c1ce  mov     [rsp+68h+ppv], rsi; ppv
0x18000c1d3  lea     rcx, _GUID_c72be2ec_8e90_452c_b29a_ab8ff1c071fc; rclsid
0x18000c1da  lea     r8d, [rdx+3]; dwClsContext
0x18000c1de  call    cs:__imp_CoCreateInstance
0x18000c1e4  mov     ebx, eax
0x18000c1e6  test    eax, eax
0x18000c1e8  jnz     loc_18000C297
0x18000c1ee  mov     rcx, [rsi]
0x18000c1f1  lea     r9d, [rbx+1]
0x18000c1f5  lea     rsi, [rdi+78h]
0x18000c1f9  mov     [rsp+68h+var_38], rsi
0x18000c1fe  lea     r8, qword_1800166A0
0x18000c205  mov     [rsp+68h+var_40], 0
0x18000c20e  lea     rdx, aProviderMicros_1; "Provider\\Microsoft.Base.PnP"
0x18000c215  mov     rax, [rcx]
0x18000c218  mov     [rsp+68h+ppv], rdi
0x18000c21d  mov     rax, [rax+28h]
0x18000c221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c226  mov     ebx, eax
0x18000c228  test    eax, eax
0x18000c22a  jnz     short loc_18000C297
0x18000c22c  mov     rcx, [rsi]
0x18000c22f  lea     r8, aTrue; "TRUE"
0x18000c236  lea     rdx, aNotifyonly; "NotifyOnly"
0x18000c23d  mov     rax, [rcx]
0x18000c240  mov     rax, [rax+18h]
0x18000c244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c249  mov     ebx, eax
0x18000c24b  test    eax, eax
0x18000c24d  jnz     short loc_18000C297
0x18000c24f  mov     rcx, [rsi]
0x18000c252  lea     r8, aTrue; "TRUE"
0x18000c259  lea     rdx, aNotpresent; "NotPresent"
0x18000c260  mov     rax, [rcx]
0x18000c263  mov     rax, [rax+18h]
0x18000c267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c26c  mov     ebx, eax
0x18000c26e  test    eax, eax
0x18000c270  jnz     short loc_18000C297
0x18000c272  mov     rcx, [rsi]
0x18000c275  lea     rdx, [rsp+68h+arg_0]
0x18000c27a  mov     rax, [rcx]
0x18000c27d  mov     rax, [rax+28h]
0x18000c281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c286  mov     ebx, eax
0x18000c288  cmp     eax, 8000000Ah
0x18000c28d  jnz     short loc_18000C293
0x18000c28f  xor     ebx, ebx
0x18000c291  jmp     short loc_18000C2D1
0x18000c293  test    eax, eax
0x18000c295  jz      short loc_18000C2D1
0x18000c297  mov     rcx, [rdi+78h]
0x18000c29b  test    rcx, rcx
0x18000c29e  jz      short loc_18000C2B4
0x18000c2a0  mov     rax, [rcx]
0x18000c2a3  mov     rax, [rax+10h]
0x18000c2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2ac  mov     qword ptr [rdi+78h], 0
0x18000c2b4  mov     rcx, [rdi+70h]
0x18000c2b8  test    rcx, rcx
0x18000c2bb  jz      short loc_18000C2D1
0x18000c2bd  mov     rax, [rcx]
0x18000c2c0  mov     rax, [rax+10h]
0x18000c2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2c9  mov     qword ptr [rdi+70h], 0
0x18000c2d1  mov     rcx, [rsp+68h+arg_0]
0x18000c2d6  test    rcx, rcx
0x18000c2d9  jz      short loc_18000C2E7
0x18000c2db  mov     rax, [rcx]
0x18000c2de  mov     rax, [rax+10h]
0x18000c2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2ee  xor     eax, eax
0x18000c2f0  test    ebx, ebx
0x18000c2f2  jnz     short loc_18000C2FA
0x18000c2f4  cmp     byte ptr [rcx+19h], 4
0x18000c2f8  jmp     short loc_18000C2FE
0x18000c2fa  cmp     byte ptr [rcx+19h], 2
0x18000c2fe  setnb   al
0x18000c301  cmp     rcx, r15
0x18000c304  jz      short loc_18000C328
0x18000c306  test    eax, eax
0x18000c308  jz      short loc_18000C328
0x18000c30a  mov     rcx, [rcx+10h]
0x18000c30e  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c315  mov     edx, 32h ; '2'
0x18000c31a  mov     dword ptr [rsp+68h+var_40], ebx
0x18000c31e  mov     [rsp+68h+ppv], rdi
0x18000c323  call    WPP_SF_sqd
0x18000c328  mov     eax, ebx
0x18000c32a  add     rsp, 48h
0x18000c32e  pop     r15
0x18000c330  pop     rdi
0x18000c331  pop     rsi
0x18000c332  pop     rbx
0x18000c333  retn
```

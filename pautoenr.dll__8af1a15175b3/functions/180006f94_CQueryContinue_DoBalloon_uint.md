# CQueryContinue::DoBalloon(uint)

- ea: `0x180006f94`
- end: `0x1800070de`
- name: `?DoBalloon@CQueryContinue@@QEAAJI@Z`
- size: `330`
- prototype: `__int64 __fastcall(CQueryContinue *this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006604`

## callees

- `0x180006f94`
- `0x180007d20`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000703a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000703a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006ff5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006ff5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006fdb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006fdb`
- `USER32!LoadIconW` at `0x180007050`
- `USER32!LoadIconW` at `0x180007050`

## pseudocode

```c
__int64 __fastcall CQueryContinue::DoBalloon(CQueryContinue *this, int a2)
{
  _QWORD *v2; // rdi
  unsigned int Instance; // ebx
  ULONGLONG TickCount64; // rax
  __int64 v6; // rcx
  HICON IconW; // r9
  WCHAR Buffer[256]; // [rsp+30h] [rbp-218h] BYREF

  *((_DWORD *)this + 10) = a2;
  v2 = (_QWORD *)((char *)this + 16);
  Instance = CoCreateInstance(&CLSID_UserNotification, 0, 0x17u, &IID_IUserNotification, (LPVOID *)this + 2);
  if ( !Instance )
  {
    if ( !*v2 )
      goto LABEL_8;
    TickCount64 = GetTickCount64();
    v6 = *v2;
    *((_QWORD *)this + 4) = TickCount64;
    Instance = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v6 + 32LL))(
                 v6,
                 15000,
                 25200000,
                 Instance + 2);
    if ( Instance )
      goto LABEL_9;
    if ( LoadStringW(g_hmodThisDll, 0x7D5u, Buffer, 256) && (IconW = LoadIconW(g_hmodThisDll, (LPCWSTR)0x3E8)) != 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, HICON, WCHAR *))(*(_QWORD *)*v2 + 40LL))(*v2, IconW, Buffer);
      if ( !Instance )
        Instance = (*(__int64 (__fastcall **)(_QWORD, CQueryContinue *, __int64))(*(_QWORD *)*v2 + 48LL))(
                     *v2,
                     this,
                     30000);
    }
    else
    {
LABEL_8:
      Instance = -2147467259;
    }
  }
LABEL_9:
  if ( *v2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
  }
  return Instance;
}

```

## disassembly

```asm
0x180006f94  mov     [rsp+arg_8], rbx
0x180006f99  mov     [rsp+arg_10], rsi
0x180006f9e  push    rdi
0x180006f9f  sub     rsp, 240h
0x180006fa6  mov     rax, cs:__security_cookie
0x180006fad  xor     rax, rsp
0x180006fb0  mov     [rsp+248h+var_18], rax
0x180006fb8  mov     [rcx+28h], edx
0x180006fbb  lea     rdi, [rcx+10h]
0x180006fbf  xor     edx, edx; pUnkOuter
0x180006fc1  mov     [rsp+248h+ppv], rdi; ppv
0x180006fc6  mov     rsi, rcx
0x180006fc9  lea     r9, IID_IUserNotification; riid
0x180006fd0  lea     rcx, CLSID_UserNotification; rclsid
0x180006fd7  lea     r8d, [rdx+17h]; dwClsContext
0x180006fdb  call    cs:__imp_CoCreateInstance
0x180006fe1  mov     ebx, eax
0x180006fe3  test    eax, eax
0x180006fe5  jnz     loc_18000709C
0x180006feb  cmp     qword ptr [rdi], 0
0x180006fef  jz      loc_180007097
0x180006ff5  call    cs:__imp_GetTickCount64
0x180006ffb  mov     rcx, [rdi]
0x180006ffe  lea     r9d, [rbx+2]
0x180007002  mov     [rsi+20h], rax
0x180007006  mov     edx, 3A98h
0x18000700b  mov     r8d, 1808580h
0x180007011  mov     rax, [rcx]
0x180007014  mov     rax, [rax+20h]
0x180007018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000701d  mov     ebx, eax
0x18000701f  test    eax, eax
0x180007021  jnz     short loc_18000709C
0x180007023  mov     rcx, cs:g_hmodThisDll; hInstance
0x18000702a  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x18000702f  mov     r9d, 100h; cchBufferMax
0x180007035  mov     edx, 7D5h; uID
0x18000703a  call    cs:__imp_LoadStringW
0x180007040  test    eax, eax
0x180007042  jz      short loc_180007097
0x180007044  mov     rcx, cs:g_hmodThisDll; hInstance
0x18000704b  mov     edx, 3E8h; lpIconName
0x180007050  call    cs:__imp_LoadIconW
0x180007056  mov     r9, rax
0x180007059  test    rax, rax
0x18000705c  jz      short loc_180007097
0x18000705e  mov     rcx, [rdi]
0x180007061  lea     r8, [rsp+248h+Buffer]
0x180007066  mov     rdx, [rcx]
0x180007069  mov     rax, [rdx+28h]
0x18000706d  mov     rdx, r9
0x180007070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007075  mov     ebx, eax
0x180007077  test    eax, eax
0x180007079  jnz     short loc_18000709C
0x18000707b  mov     rcx, [rdi]
0x18000707e  mov     r8d, 7530h
0x180007084  mov     rdx, rsi
0x180007087  mov     rax, [rcx]
0x18000708a  mov     rax, [rax+30h]
0x18000708e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007093  mov     ebx, eax
0x180007095  jmp     short loc_18000709C
0x180007097  mov     ebx, 80004005h
0x18000709c  mov     rcx, [rdi]
0x18000709f  test    rcx, rcx
0x1800070a2  jz      short loc_1800070B7
0x1800070a4  mov     rax, [rcx]
0x1800070a7  mov     rax, [rax+10h]
0x1800070ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b0  mov     qword ptr [rdi], 0
0x1800070b7  mov     eax, ebx
0x1800070b9  mov     rcx, [rsp+248h+var_18]
0x1800070c1  xor     rcx, rsp; StackCookie
0x1800070c4  call    __security_check_cookie
0x1800070c9  lea     r11, [rsp+248h+var_8]
0x1800070d1  mov     rbx, [r11+18h]
0x1800070d5  mov     rsi, [r11+20h]
0x1800070d9  mov     rsp, r11
0x1800070dc  pop     rdi
0x1800070dd  retn
```

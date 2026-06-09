# DllMainAttach

- ea: `0x180005000`
- end: `0x18000529a`
- name: `DllMainAttach`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180005e60`

## callees

- `0x180005000`
- `0x1800052a0`
- `0x180005660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005191`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005191`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800051c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800051c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800051a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800051a9`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180005171`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180005171`

## pseudocode

```c
__int64 DllMainAttach()
{
  __int64 *v0; // rbx
  __int64 *v1; // rdi
  unsigned int v2; // esi
  __int64 v3; // r8
  char v4; // bl
  int v6; // eax
  _QWORD v7[7]; // [rsp+40h] [rbp-38h] BYREF
  int v8; // [rsp+80h] [rbp+8h] BYREF

  qword_18000EA58 = 1;
  qword_18000EA50 = 0;
  WPP_MAIN_CB = (__int64)&qword_18000EA68;
  v0 = &WPP_MAIN_CB;
  qword_18000EA78 = 0;
  qword_18000EA68 = (__int64)&qword_18000EA90;
  v1 = &WPP_REGISTRATION_GUIDS;
  qword_18000EA80 = 1;
  qword_18000EA90 = (__int64)&qword_18000EAB8;
  v2 = 1;
  qword_18000EAA0 = 0;
  qword_18000EAB8 = (__int64)&qword_18000EAE0;
  qword_18000EAE0 = (__int64)&qword_18000EB08;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CscService;
  qword_18000EA08 = (__int64)WPP_ThisDir_CTLGUID_CscDclUser;
  qword_18000EA10 = (__int64)WPP_ThisDir_CTLGUID_CscFastSync;
  qword_18000EA18 = (__int64)WPP_ThisDir_CTLGUID_CscUm;
  qword_18000EA20 = (__int64)WPP_ThisDir_CTLGUID_CscApi;
  qword_18000EA28 = (__int64)WPP_ThisDir_CTLGUID_CscNetApi;
  qword_18000EAA8 = 1;
  qword_18000EAC8 = 0;
  qword_18000EAD0 = 1;
  qword_18000EAF0 = 0;
  qword_18000EAF8 = 1;
  qword_18000EB18 = 0;
  qword_18000EB08 = 0;
  qword_18000EB20 = 1;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  do
  {
    v3 = *v1;
    v7[0] = v3;
    ++v1;
    v7[1] = 0;
    v0[4] = v3;
    ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
      WppControlCallback,
      v0,
      v3,
      1,
      v7,
      0,
      0,
      v0 + 1);
    v0 = (__int64 *)*v0;
  }
  while ( v0 );
  v4 = 1;
  v8 = 1;
  if ( !InitializeCriticalSectionAndSpinCount(&g_csInitilization, 0) )
    goto LABEL_4;
  EnterCriticalSection(&g_csInitilization);
  v4 = 17;
  v8 = 17;
  if ( _InterlockedIncrement(&dword_18000E980) <= 1 )
  {
    if ( CscUmpLibraryState )
    {
      ++CscUmpLibraryState;
    }
    else
    {
      if ( (int)CscDriverInitializeLibrary() < 0 )
      {
        _InterlockedDecrement(&dword_18000E980);
LABEL_4:
        v2 = 0;
        goto LABEL_5;
      }
      CscUmpLibraryState = 1;
    }
  }
  v4 = 19;
  v8 = 19;
  if ( _InterlockedIncrement(&dword_18000E984) <= 1 && (int)CscDriverInitializeLibrary() < 0 )
  {
    _InterlockedDecrement(&dword_18000E984);
    goto LABEL_4;
  }
  v4 = 23;
  v8 = 23;
  if ( CscUmpLibraryState )
  {
    v6 = CscUmpLibraryState + 1;
  }
  else
  {
    if ( (int)CscDriverInitializeLibrary() < 0 )
      goto LABEL_4;
    v6 = 1;
  }
  v4 = 31;
  CscUmpLibraryState = v6;
  v8 = 31;
LABEL_5:
  if ( (v4 & 0x10) != 0 )
    LeaveCriticalSection(&g_csInitilization);
  if ( !v2 )
    DllMainDetach(&v8);
  return v2;
}

```

## disassembly

```asm
0x180005000  push    rbx
0x180005002  push    rbp
0x180005003  push    rsi
0x180005004  push    rdi
0x180005005  sub     rsp, 58h
0x180005009  xor     ebp, ebp
0x18000500b  mov     cs:qword_18000EA58, 1
0x180005016  lea     rax, qword_18000EA68
0x18000501d  mov     cs:qword_18000EA50, rbp
0x180005024  mov     cs:WPP_MAIN_CB, rax
0x18000502b  lea     rbx, WPP_MAIN_CB
0x180005032  lea     rax, qword_18000EA90
0x180005039  mov     cs:qword_18000EA78, rbp
0x180005040  mov     cs:qword_18000EA68, rax
0x180005047  lea     rdi, WPP_REGISTRATION_GUIDS
0x18000504e  lea     rax, qword_18000EAB8
0x180005055  mov     cs:qword_18000EA80, 1
0x180005060  mov     cs:qword_18000EA90, rax
0x180005067  mov     esi, 1
0x18000506c  lea     rax, qword_18000EAE0
0x180005073  mov     cs:qword_18000EAA0, rbp
0x18000507a  mov     cs:qword_18000EAB8, rax
0x180005081  lea     rax, qword_18000EB08
0x180005088  mov     cs:qword_18000EAE0, rax
0x18000508f  lea     rax, WPP_ThisDir_CTLGUID_CscService
0x180005096  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000509d  lea     rax, WPP_ThisDir_CTLGUID_CscDclUser
0x1800050a4  mov     cs:qword_18000EA08, rax
0x1800050ab  lea     rax, WPP_ThisDir_CTLGUID_CscFastSync
0x1800050b2  mov     cs:qword_18000EA10, rax
0x1800050b9  lea     rax, WPP_ThisDir_CTLGUID_CscUm
0x1800050c0  mov     cs:qword_18000EA18, rax
0x1800050c7  lea     rax, WPP_ThisDir_CTLGUID_CscApi
0x1800050ce  mov     cs:qword_18000EA20, rax
0x1800050d5  lea     rax, WPP_ThisDir_CTLGUID_CscNetApi
0x1800050dc  mov     cs:qword_18000EA28, rax
0x1800050e3  mov     cs:qword_18000EAA8, 1
0x1800050ee  mov     cs:qword_18000EAC8, rbp
0x1800050f5  mov     cs:qword_18000EAD0, 1
0x180005100  mov     cs:qword_18000EAF0, rbp
0x180005107  mov     cs:qword_18000EAF8, 1
0x180005112  mov     cs:qword_18000EB18, rbp
0x180005119  mov     cs:qword_18000EB08, rbp
0x180005120  mov     cs:qword_18000EB20, 1
0x18000512b  mov     cs:WPP_GLOBAL_Control, rbx
0x180005132  mov     r8, [rdi]
0x180005135  lea     rax, [rbx+8]
0x180005139  mov     [rsp+78h+var_40], rax
0x18000513e  lea     rcx, WppControlCallback
0x180005145  mov     [rsp+78h+var_48], rbp
0x18000514a  lea     rax, [rsp+78h+var_38]
0x18000514f  mov     [rsp+78h+var_38], r8
0x180005154  lea     rdi, [rdi+8]
0x180005158  mov     [rsp+78h+var_30], rbp
0x18000515d  mov     r9d, esi
0x180005160  mov     [rsp+78h+var_50], rbp
0x180005165  mov     rdx, rbx
0x180005168  mov     [rsp+78h+var_58], rax
0x18000516d  mov     [rbx+20h], r8
0x180005171  call    cs:__imp_EtwRegisterTraceGuidsW
0x180005177  mov     rbx, [rbx]
0x18000517a  test    rbx, rbx
0x18000517d  jnz     short loc_180005132
0x18000517f  mov     ebx, esi
0x180005181  lea     rcx, g_csInitilization; lpCriticalSection
0x180005188  xor     edx, edx; dwSpinCount
0x18000518a  mov     [rsp+78h+arg_0], ebx
0x180005191  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180005197  test    eax, eax
0x180005199  jnz     short loc_1800051C2
0x18000519b  mov     esi, ebp
0x18000519d  test    bl, 10h
0x1800051a0  jz      short loc_1800051AF
0x1800051a2  lea     rcx, g_csInitilization; lpCriticalSection
0x1800051a9  call    cs:__imp_LeaveCriticalSection
0x1800051af  test    esi, esi
0x1800051b1  jz      loc_180005288
0x1800051b7  mov     eax, esi
0x1800051b9  add     rsp, 58h
0x1800051bd  pop     rdi
0x1800051be  pop     rsi
0x1800051bf  pop     rbp
0x1800051c0  pop     rbx
0x1800051c1  retn
0x1800051c2  lea     rcx, g_csInitilization; lpCriticalSection
0x1800051c9  call    cs:__imp_EnterCriticalSection
0x1800051cf  mov     ebx, 11h
0x1800051d4  mov     eax, esi
0x1800051d6  mov     [rsp+78h+arg_0], ebx
0x1800051dd  lock xadd cs:dword_18000E980, eax
0x1800051e5  inc     eax
0x1800051e7  cmp     eax, esi
0x1800051e9  jg      short loc_18000520F
0x1800051eb  mov     eax, cs:CscUmpLibraryState
0x1800051f1  test    eax, eax
0x1800051f3  jnz     short loc_180005207
0x1800051f5  call    CscDriverInitializeLibrary
0x1800051fa  test    eax, eax
0x1800051fc  jns     short loc_180005274
0x1800051fe  lock dec cs:dword_18000E980
0x180005205  jmp     short loc_18000519B
0x180005207  inc     eax
0x180005209  mov     cs:CscUmpLibraryState, eax
0x18000520f  mov     ebx, 13h
0x180005214  mov     eax, esi
0x180005216  mov     [rsp+78h+arg_0], ebx
0x18000521d  lock xadd cs:dword_18000E984, eax
0x180005225  inc     eax
0x180005227  cmp     eax, esi
0x180005229  jg      short loc_180005234
0x18000522b  call    CscDriverInitializeLibrary
0x180005230  test    eax, eax
0x180005232  js      short loc_18000527C
0x180005234  mov     eax, cs:CscUmpLibraryState
0x18000523a  mov     ebx, 17h
0x18000523f  mov     [rsp+78h+arg_0], ebx
0x180005246  test    eax, eax
0x180005248  jnz     short loc_18000525B
0x18000524a  call    CscDriverInitializeLibrary
0x18000524f  test    eax, eax
0x180005251  js      loc_18000519B
0x180005257  mov     eax, esi
0x180005259  jmp     short loc_18000525D
0x18000525b  inc     eax
0x18000525d  mov     ebx, 1Fh
0x180005262  mov     cs:CscUmpLibraryState, eax
0x180005268  mov     [rsp+78h+arg_0], ebx
0x18000526f  jmp     loc_18000519D
0x180005274  mov     cs:CscUmpLibraryState, esi
0x18000527a  jmp     short loc_18000520F
0x18000527c  lock dec cs:dword_18000E984
0x180005283  jmp     loc_18000519B
0x180005288  lea     rcx, [rsp+78h+arg_0]
0x180005290  call    DllMainDetach
0x180005295  jmp     loc_1800051B7
```

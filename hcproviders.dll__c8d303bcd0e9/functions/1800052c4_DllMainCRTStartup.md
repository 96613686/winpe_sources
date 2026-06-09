# __DllMainCRTStartup

- ea: `0x1800052c4`
- end: `0x1800054d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180005280`

## callees

- `0x180005050`
- `0x1800052c4`
- `0x1800054fa`
- `0x180005c30`
- `0x180009e80`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_1800103C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800103C4 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_1800103C4 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x1800052c4  mov     [rsp+lpvReserved], r8
0x1800052c9  mov     [rsp+arg_8], edx
0x1800052cd  mov     [rsp+arg_0], rcx
0x1800052d2  push    rbx
0x1800052d3  push    rsi
0x1800052d4  push    rdi
0x1800052d5  sub     rsp, 0F0h
0x1800052dc  mov     edi, edx
0x1800052de  mov     rsi, rcx
0x1800052e1  mov     ebx, 1
0x1800052e6  cmp     edx, ebx
0x1800052e8  ja      short loc_1800052F0
0x1800052ea  mov     cs:__native_dllmain_reason, edx
0x1800052f0  test    edx, edx
0x1800052f2  jnz     short loc_180005307
0x1800052f4  cmp     cs:dword_1800103C0, edx
0x1800052fa  jnz     short loc_180005307
0x1800052fc  xor     ebx, ebx
0x1800052fe  mov     [rsp+108h+var_E8], ebx
0x180005302  jmp     loc_1800054B4
0x180005307  lea     eax, [rdx-1]
0x18000530a  cmp     eax, 1
0x18000530d  ja      loc_180005394
0x180005313  mov     rax, cs:_pRawDllMain
0x18000531a  test    rax, rax
0x18000531d  jz      short loc_180005355
0x18000531f  cmp     edx, 1
0x180005322  jnz     short loc_18000532A
0x180005324  mov     cs:dword_1800103C4, edx
0x18000532a  mov     r8, [rsp+108h+lpvReserved]
0x180005332  call    cs:__guard_dispatch_icall_fptr
0x180005338  mov     ebx, eax
0x18000533a  mov     [rsp+108h+var_E8], eax
0x18000533e  jmp     short loc_180005355
0x180005340  xor     ebx, ebx
0x180005342  mov     [rsp+108h+var_E8], ebx
0x180005346  mov     edi, [rsp+108h+arg_8]
0x18000534d  mov     rsi, [rsp+108h+arg_0]
0x180005355  test    ebx, ebx
0x180005357  jz      loc_1800054B4
0x18000535d  mov     r8, [rsp+108h+lpvReserved]
0x180005365  mov     edx, edi
0x180005367  mov     rcx, rsi
0x18000536a  call    _CRT_INIT
0x18000536f  mov     ebx, eax
0x180005371  mov     [rsp+108h+var_E8], eax
0x180005375  jmp     short loc_18000538C
0x180005377  xor     ebx, ebx
0x180005379  mov     [rsp+108h+var_E8], ebx
0x18000537d  mov     edi, [rsp+108h+arg_8]
0x180005384  mov     rsi, [rsp+108h+arg_0]
0x18000538c  test    ebx, ebx
0x18000538e  jz      loc_1800054B4
0x180005394  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000539c  mov     edx, edi; fdwReason
0x18000539e  mov     rcx, rsi; hinstDLL
0x1800053a1  call    DllMain
0x1800053a6  mov     ebx, eax
0x1800053a8  mov     [rsp+108h+var_E8], eax
0x1800053ac  jmp     short loc_1800053C3
0x1800053ae  xor     ebx, ebx
0x1800053b0  mov     [rsp+108h+var_E8], ebx
0x1800053b4  mov     edi, [rsp+108h+arg_8]
0x1800053bb  mov     rsi, [rsp+108h+arg_0]
0x1800053c3  cmp     edi, 1
0x1800053c6  jnz     short loc_18000543F
0x1800053c8  test    ebx, ebx
0x1800053ca  jnz     short loc_18000543F
0x1800053cc  xor     r8d, r8d; lpvReserved
0x1800053cf  xor     edx, edx; fdwReason
0x1800053d1  mov     rcx, rsi; hinstDLL
0x1800053d4  call    DllMain
0x1800053d9  jmp     short loc_1800053EE
0x1800053db  mov     edi, [rsp+108h+arg_8]
0x1800053e2  mov     rsi, [rsp+108h+arg_0]
0x1800053ea  mov     ebx, [rsp+108h+var_E8]
0x1800053ee  xor     r8d, r8d
0x1800053f1  xor     edx, edx
0x1800053f3  mov     rcx, rsi
0x1800053f6  call    _CRT_INIT
0x1800053fb  jmp     short loc_180005410
0x1800053fd  mov     edi, [rsp+108h+arg_8]
0x180005404  mov     rsi, [rsp+108h+arg_0]
0x18000540c  mov     ebx, [rsp+108h+var_E8]
0x180005410  mov     rax, cs:_pRawDllMain
0x180005417  test    rax, rax
0x18000541a  jz      short loc_18000543F
0x18000541c  xor     r8d, r8d
0x18000541f  xor     edx, edx
0x180005421  mov     rcx, rsi
0x180005424  call    cs:__guard_dispatch_icall_fptr
0x18000542a  jmp     short loc_18000543F
0x18000542c  mov     edi, [rsp+108h+arg_8]
0x180005433  mov     rsi, [rsp+108h+arg_0]
0x18000543b  mov     ebx, [rsp+108h+var_E8]
0x18000543f  test    edi, edi
0x180005441  jz      short loc_180005448
0x180005443  cmp     edi, 3
0x180005446  jnz     short loc_1800054B4
0x180005448  mov     r8, [rsp+108h+lpvReserved]
0x180005450  mov     edx, edi
0x180005452  mov     rcx, rsi
0x180005455  call    _CRT_INIT
0x18000545a  mov     ebx, eax
0x18000545c  mov     [rsp+108h+var_E8], eax
0x180005460  jmp     short loc_180005477
0x180005462  xor     ebx, ebx
0x180005464  mov     [rsp+108h+var_E8], ebx
0x180005468  mov     edi, [rsp+108h+arg_8]
0x18000546f  mov     rsi, [rsp+108h+arg_0]
0x180005477  mov     rax, cs:_pRawDllMain
0x18000547e  test    rax, rax
0x180005481  jz      short loc_1800054B4
0x180005483  cmp     cs:dword_1800103C4, 0
0x18000548a  jz      short loc_1800054B4
0x18000548c  mov     r8, [rsp+108h+lpvReserved]
0x180005494  mov     edx, edi
0x180005496  mov     rcx, rsi
0x180005499  call    cs:__guard_dispatch_icall_fptr
0x18000549f  mov     ebx, eax
0x1800054a1  mov     [rsp+108h+var_E8], eax
0x1800054a5  jmp     short loc_1800054B4
0x1800054a7  xor     ebx, ebx
0x1800054a9  mov     [rsp+108h+var_E8], ebx
0x1800054ad  mov     edi, [rsp+108h+arg_8]
0x1800054b4  cmp     edi, 1
0x1800054b7  ja      short loc_1800054C3
0x1800054b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800054c3  mov     eax, ebx
0x1800054c5  add     rsp, 0F0h
0x1800054cc  pop     rdi
0x1800054cd  pop     rsi
0x1800054ce  pop     rbx
0x1800054cf  retn
0x180009f50  push    rbp
0x180009f52  sub     rsp, 20h
0x180009f56  mov     rbp, rdx
0x180009f59  mov     rax, [rcx]
0x180009f5c  mov     edx, [rax]
0x180009f5e  mov     [rbp+0A8h], rcx
0x180009f65  mov     [rbp+28h], edx
0x180009f68  mov     eax, [rbp+28h]
0x180009f6b  cmp     eax, 0E06D7363h
0x180009f70  jnz     short loc_180009F86
0x180009f72  mov     rdx, [rbp+0A8h]
0x180009f79  mov     ecx, [rbp+28h]
0x180009f7c  call    _XcptFilter_0
0x180009f81  mov     [rbp+30h], eax
0x180009f84  jmp     short loc_180009F8D
0x180009f86  mov     dword ptr [rbp+30h], 0
0x180009f8d  mov     eax, [rbp+30h]
0x180009f90  add     rsp, 20h
0x180009f94  pop     rbp
0x180009f95  retn
0x180009f97  push    rbp
0x180009f99  sub     rsp, 20h
0x180009f9d  mov     rbp, rdx
0x180009fa0  mov     rax, [rcx]
0x180009fa3  mov     edx, [rax]
0x180009fa5  mov     [rbp+0B0h], rcx
0x180009fac  mov     [rbp+38h], edx
0x180009faf  mov     eax, [rbp+38h]
0x180009fb2  cmp     eax, 0E06D7363h
0x180009fb7  jnz     short loc_180009FCD
0x180009fb9  mov     rdx, [rbp+0B0h]
0x180009fc0  mov     ecx, [rbp+38h]
0x180009fc3  call    _XcptFilter_0
0x180009fc8  mov     [rbp+40h], eax
0x180009fcb  jmp     short loc_180009FD4
0x180009fcd  mov     dword ptr [rbp+40h], 0
0x180009fd4  mov     eax, [rbp+40h]
0x180009fd7  add     rsp, 20h
0x180009fdb  pop     rbp
0x180009fdc  retn
0x180009fde  push    rbp
0x180009fe0  sub     rsp, 20h
0x180009fe4  mov     rbp, rdx
0x180009fe7  mov     rax, [rcx]
0x180009fea  mov     edx, [rax]
0x180009fec  mov     [rbp+0B8h], rcx
0x180009ff3  mov     [rbp+48h], edx
0x180009ff6  mov     eax, [rbp+48h]
0x180009ff9  cmp     eax, 0E06D7363h
0x180009ffe  jnz     short loc_18000A014
0x18000a000  mov     rdx, [rbp+0B8h]
0x18000a007  mov     ecx, [rbp+48h]
0x18000a00a  call    _XcptFilter_0
0x18000a00f  mov     [rbp+50h], eax
0x18000a012  jmp     short loc_18000A01B
0x18000a014  mov     dword ptr [rbp+50h], 0
0x18000a01b  mov     eax, [rbp+50h]
0x18000a01e  add     rsp, 20h
0x18000a022  pop     rbp
0x18000a023  retn
0x18000a025  push    rbp
0x18000a027  sub     rsp, 20h
0x18000a02b  mov     rbp, rdx
0x18000a02e  mov     rax, [rcx]
0x18000a031  mov     edx, [rax]
0x18000a033  mov     [rbp+0C0h], rcx
0x18000a03a  mov     [rbp+58h], edx
0x18000a03d  mov     eax, [rbp+58h]
0x18000a040  cmp     eax, 0E06D7363h
0x18000a045  jnz     short loc_18000A05B
0x18000a047  mov     rdx, [rbp+0C0h]
0x18000a04e  mov     ecx, [rbp+58h]
0x18000a051  call    _XcptFilter_0
0x18000a056  mov     [rbp+60h], eax
0x18000a059  jmp     short loc_18000A062
0x18000a05b  mov     dword ptr [rbp+60h], 0
0x18000a062  mov     eax, [rbp+60h]
0x18000a065  add     rsp, 20h
0x18000a069  pop     rbp
0x18000a06a  retn
0x18000a06c  push    rbp
0x18000a06e  sub     rsp, 20h
0x18000a072  mov     rbp, rdx
0x18000a075  mov     rax, [rcx]
0x18000a078  mov     edx, [rax]
0x18000a07a  mov     [rbp+0C8h], rcx
0x18000a081  mov     [rbp+68h], edx
0x18000a084  mov     eax, [rbp+68h]
0x18000a087  cmp     eax, 0E06D7363h
0x18000a08c  jnz     short loc_18000A0A2
0x18000a08e  mov     rdx, [rbp+0C8h]
0x18000a095  mov     ecx, [rbp+68h]
0x18000a098  call    _XcptFilter_0
0x18000a09d  mov     [rbp+70h], eax
0x18000a0a0  jmp     short loc_18000A0A9
0x18000a0a2  mov     dword ptr [rbp+70h], 0
0x18000a0a9  mov     eax, [rbp+70h]
0x18000a0ac  add     rsp, 20h
0x18000a0b0  pop     rbp
0x18000a0b1  retn
0x18000a0b3  push    rbp
0x18000a0b5  sub     rsp, 20h
0x18000a0b9  mov     rbp, rdx
0x18000a0bc  mov     rax, [rcx]
0x18000a0bf  mov     edx, [rax]
0x18000a0c1  mov     [rbp+0D0h], rcx
0x18000a0c8  mov     [rbp+78h], edx
0x18000a0cb  mov     eax, [rbp+78h]
0x18000a0ce  cmp     eax, 0E06D7363h
0x18000a0d3  jnz     short loc_18000A0EC
0x18000a0d5  mov     rdx, [rbp+0D0h]
0x18000a0dc  mov     ecx, [rbp+78h]
0x18000a0df  call    _XcptFilter_0
0x18000a0e4  mov     [rbp+80h], eax
0x18000a0ea  jmp     short loc_18000A0F6
0x18000a0ec  mov     dword ptr [rbp+80h], 0
0x18000a0f6  mov     eax, [rbp+80h]
0x18000a0fc  add     rsp, 20h
0x18000a100  pop     rbp
0x18000a101  retn
0x18000a103  push    rbp
0x18000a105  sub     rsp, 20h
0x18000a109  mov     rbp, rdx
0x18000a10c  mov     rax, [rcx]
0x18000a10f  mov     edx, [rax]
0x18000a111  mov     [rbp+0D8h], rcx
0x18000a118  mov     [rbp+88h], edx
0x18000a11e  mov     eax, [rbp+88h]
0x18000a124  cmp     eax, 0E06D7363h
0x18000a129  jnz     short loc_18000A145
0x18000a12b  mov     rdx, [rbp+0D8h]
0x18000a132  mov     ecx, [rbp+88h]
0x18000a138  call    _XcptFilter_0
0x18000a13d  mov     [rbp+90h], eax
0x18000a143  jmp     short loc_18000A14F
0x18000a145  mov     dword ptr [rbp+90h], 0
0x18000a14f  mov     eax, [rbp+90h]
0x18000a155  add     rsp, 20h
0x18000a159  pop     rbp
0x18000a15a  retn
0x18000a15c  push    rbp
0x18000a15e  sub     rsp, 20h
0x18000a162  mov     rbp, rdx
0x18000a165  mov     rax, [rcx]
0x18000a168  mov     edx, [rax]
0x18000a16a  mov     [rbp+0E0h], rcx
0x18000a171  mov     [rbp+98h], edx
0x18000a177  mov     eax, [rbp+98h]
0x18000a17d  cmp     eax, 0E06D7363h
0x18000a182  jnz     short loc_18000A19E
0x18000a184  mov     rdx, [rbp+0E0h]
0x18000a18b  mov     ecx, [rbp+98h]
0x18000a191  call    _XcptFilter_0
0x18000a196  mov     [rbp+0A0h], eax
0x18000a19c  jmp     short loc_18000A1A8
0x18000a19e  mov     dword ptr [rbp+0A0h], 0
0x18000a1a8  mov     eax, [rbp+0A0h]
0x18000a1ae  add     rsp, 20h
0x18000a1b2  pop     rbp
0x18000a1b3  retn
0x18000a1b5  push    rbp
0x18000a1b7  sub     rsp, 20h
0x18000a1bb  mov     rbp, rdx
0x18000a1be  cmp     dword ptr [rbp+118h], 1
0x18000a1c5  ja      short loc_18000A1D1
0x18000a1c7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

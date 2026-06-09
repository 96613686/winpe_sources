# __DllMainCRTStartup

- ea: `0x180009e34`
- end: `0x18000a040`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009df0`

## callees

- `0x180007ca8`
- `0x180009bc0`
- `0x180009e34`
- `0x18000a536`
- `0x18001b5c0`

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
  if ( (_DWORD)fdwReason || dword_18002BD10 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002BD14 = 1;
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
            if ( dword_18002BD14 )
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
0x180009e34  mov     [rsp+lpvReserved], r8
0x180009e39  mov     [rsp+arg_8], edx
0x180009e3d  mov     [rsp+arg_0], rcx
0x180009e42  push    rbx
0x180009e43  push    rsi
0x180009e44  push    rdi
0x180009e45  sub     rsp, 0F0h
0x180009e4c  mov     edi, edx
0x180009e4e  mov     rsi, rcx
0x180009e51  mov     ebx, 1
0x180009e56  cmp     edx, ebx
0x180009e58  ja      short loc_180009E60
0x180009e5a  mov     cs:__native_dllmain_reason, edx
0x180009e60  test    edx, edx
0x180009e62  jnz     short loc_180009E77
0x180009e64  cmp     cs:dword_18002BD10, edx
0x180009e6a  jnz     short loc_180009E77
0x180009e6c  xor     ebx, ebx
0x180009e6e  mov     [rsp+108h+var_E8], ebx
0x180009e72  jmp     loc_18000A024
0x180009e77  lea     eax, [rdx-1]
0x180009e7a  cmp     eax, 1
0x180009e7d  ja      loc_180009F04
0x180009e83  mov     rax, cs:_pRawDllMain
0x180009e8a  test    rax, rax
0x180009e8d  jz      short loc_180009EC5
0x180009e8f  cmp     edx, 1
0x180009e92  jnz     short loc_180009E9A
0x180009e94  mov     cs:dword_18002BD14, edx
0x180009e9a  mov     r8, [rsp+108h+lpvReserved]
0x180009ea2  call    cs:__guard_dispatch_icall_fptr
0x180009ea8  mov     ebx, eax
0x180009eaa  mov     [rsp+108h+var_E8], eax
0x180009eae  jmp     short loc_180009EC5
0x180009eb0  xor     ebx, ebx
0x180009eb2  mov     [rsp+108h+var_E8], ebx
0x180009eb6  mov     edi, [rsp+108h+arg_8]
0x180009ebd  mov     rsi, [rsp+108h+arg_0]
0x180009ec5  test    ebx, ebx
0x180009ec7  jz      loc_18000A024
0x180009ecd  mov     r8, [rsp+108h+lpvReserved]
0x180009ed5  mov     edx, edi
0x180009ed7  mov     rcx, rsi
0x180009eda  call    _CRT_INIT
0x180009edf  mov     ebx, eax
0x180009ee1  mov     [rsp+108h+var_E8], eax
0x180009ee5  jmp     short loc_180009EFC
0x180009ee7  xor     ebx, ebx
0x180009ee9  mov     [rsp+108h+var_E8], ebx
0x180009eed  mov     edi, [rsp+108h+arg_8]
0x180009ef4  mov     rsi, [rsp+108h+arg_0]
0x180009efc  test    ebx, ebx
0x180009efe  jz      loc_18000A024
0x180009f04  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180009f0c  mov     edx, edi; fdwReason
0x180009f0e  mov     rcx, rsi; hinstDLL
0x180009f11  call    DllMain
0x180009f16  mov     ebx, eax
0x180009f18  mov     [rsp+108h+var_E8], eax
0x180009f1c  jmp     short loc_180009F33
0x180009f1e  xor     ebx, ebx
0x180009f20  mov     [rsp+108h+var_E8], ebx
0x180009f24  mov     edi, [rsp+108h+arg_8]
0x180009f2b  mov     rsi, [rsp+108h+arg_0]
0x180009f33  cmp     edi, 1
0x180009f36  jnz     short loc_180009FAF
0x180009f38  test    ebx, ebx
0x180009f3a  jnz     short loc_180009FAF
0x180009f3c  xor     r8d, r8d; lpvReserved
0x180009f3f  xor     edx, edx; fdwReason
0x180009f41  mov     rcx, rsi; hinstDLL
0x180009f44  call    DllMain
0x180009f49  jmp     short loc_180009F5E
0x180009f4b  mov     edi, [rsp+108h+arg_8]
0x180009f52  mov     rsi, [rsp+108h+arg_0]
0x180009f5a  mov     ebx, [rsp+108h+var_E8]
0x180009f5e  xor     r8d, r8d
0x180009f61  xor     edx, edx
0x180009f63  mov     rcx, rsi
0x180009f66  call    _CRT_INIT
0x180009f6b  jmp     short loc_180009F80
0x180009f6d  mov     edi, [rsp+108h+arg_8]
0x180009f74  mov     rsi, [rsp+108h+arg_0]
0x180009f7c  mov     ebx, [rsp+108h+var_E8]
0x180009f80  mov     rax, cs:_pRawDllMain
0x180009f87  test    rax, rax
0x180009f8a  jz      short loc_180009FAF
0x180009f8c  xor     r8d, r8d
0x180009f8f  xor     edx, edx
0x180009f91  mov     rcx, rsi
0x180009f94  call    cs:__guard_dispatch_icall_fptr
0x180009f9a  jmp     short loc_180009FAF
0x180009f9c  mov     edi, [rsp+108h+arg_8]
0x180009fa3  mov     rsi, [rsp+108h+arg_0]
0x180009fab  mov     ebx, [rsp+108h+var_E8]
0x180009faf  test    edi, edi
0x180009fb1  jz      short loc_180009FB8
0x180009fb3  cmp     edi, 3
0x180009fb6  jnz     short loc_18000A024
0x180009fb8  mov     r8, [rsp+108h+lpvReserved]
0x180009fc0  mov     edx, edi
0x180009fc2  mov     rcx, rsi
0x180009fc5  call    _CRT_INIT
0x180009fca  mov     ebx, eax
0x180009fcc  mov     [rsp+108h+var_E8], eax
0x180009fd0  jmp     short loc_180009FE7
0x180009fd2  xor     ebx, ebx
0x180009fd4  mov     [rsp+108h+var_E8], ebx
0x180009fd8  mov     edi, [rsp+108h+arg_8]
0x180009fdf  mov     rsi, [rsp+108h+arg_0]
0x180009fe7  mov     rax, cs:_pRawDllMain
0x180009fee  test    rax, rax
0x180009ff1  jz      short loc_18000A024
0x180009ff3  cmp     cs:dword_18002BD14, 0
0x180009ffa  jz      short loc_18000A024
0x180009ffc  mov     r8, [rsp+108h+lpvReserved]
0x18000a004  mov     edx, edi
0x18000a006  mov     rcx, rsi
0x18000a009  call    cs:__guard_dispatch_icall_fptr
0x18000a00f  mov     ebx, eax
0x18000a011  mov     [rsp+108h+var_E8], eax
0x18000a015  jmp     short loc_18000A024
0x18000a017  xor     ebx, ebx
0x18000a019  mov     [rsp+108h+var_E8], ebx
0x18000a01d  mov     edi, [rsp+108h+arg_8]
0x18000a024  cmp     edi, 1
0x18000a027  ja      short loc_18000A033
0x18000a029  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000a033  mov     eax, ebx
0x18000a035  add     rsp, 0F0h
0x18000a03c  pop     rdi
0x18000a03d  pop     rsi
0x18000a03e  pop     rbx
0x18000a03f  retn
0x18001b9d8  push    rbp
0x18001b9da  sub     rsp, 20h
0x18001b9de  mov     rbp, rdx
0x18001b9e1  mov     rax, [rcx]
0x18001b9e4  mov     edx, [rax]
0x18001b9e6  mov     [rbp+0A8h], rcx
0x18001b9ed  mov     [rbp+28h], edx
0x18001b9f0  mov     eax, [rbp+28h]
0x18001b9f3  cmp     eax, 0E06D7363h
0x18001b9f8  jnz     short loc_18001BA0E
0x18001b9fa  mov     rdx, [rbp+0A8h]
0x18001ba01  mov     ecx, [rbp+28h]
0x18001ba04  call    _XcptFilter_0
0x18001ba09  mov     [rbp+30h], eax
0x18001ba0c  jmp     short loc_18001BA15
0x18001ba0e  mov     dword ptr [rbp+30h], 0
0x18001ba15  mov     eax, [rbp+30h]
0x18001ba18  add     rsp, 20h
0x18001ba1c  pop     rbp
0x18001ba1d  retn
0x18001ba1f  push    rbp
0x18001ba21  sub     rsp, 20h
0x18001ba25  mov     rbp, rdx
0x18001ba28  mov     rax, [rcx]
0x18001ba2b  mov     edx, [rax]
0x18001ba2d  mov     [rbp+0B0h], rcx
0x18001ba34  mov     [rbp+38h], edx
0x18001ba37  mov     eax, [rbp+38h]
0x18001ba3a  cmp     eax, 0E06D7363h
0x18001ba3f  jnz     short loc_18001BA55
0x18001ba41  mov     rdx, [rbp+0B0h]
0x18001ba48  mov     ecx, [rbp+38h]
0x18001ba4b  call    _XcptFilter_0
0x18001ba50  mov     [rbp+40h], eax
0x18001ba53  jmp     short loc_18001BA5C
0x18001ba55  mov     dword ptr [rbp+40h], 0
0x18001ba5c  mov     eax, [rbp+40h]
0x18001ba5f  add     rsp, 20h
0x18001ba63  pop     rbp
0x18001ba64  retn
0x18001ba66  push    rbp
0x18001ba68  sub     rsp, 20h
0x18001ba6c  mov     rbp, rdx
0x18001ba6f  mov     rax, [rcx]
0x18001ba72  mov     edx, [rax]
0x18001ba74  mov     [rbp+0B8h], rcx
0x18001ba7b  mov     [rbp+48h], edx
0x18001ba7e  mov     eax, [rbp+48h]
0x18001ba81  cmp     eax, 0E06D7363h
0x18001ba86  jnz     short loc_18001BA9C
0x18001ba88  mov     rdx, [rbp+0B8h]
0x18001ba8f  mov     ecx, [rbp+48h]
0x18001ba92  call    _XcptFilter_0
0x18001ba97  mov     [rbp+50h], eax
0x18001ba9a  jmp     short loc_18001BAA3
0x18001ba9c  mov     dword ptr [rbp+50h], 0
0x18001baa3  mov     eax, [rbp+50h]
0x18001baa6  add     rsp, 20h
0x18001baaa  pop     rbp
0x18001baab  retn
0x18001baad  push    rbp
0x18001baaf  sub     rsp, 20h
0x18001bab3  mov     rbp, rdx
0x18001bab6  mov     rax, [rcx]
0x18001bab9  mov     edx, [rax]
0x18001babb  mov     [rbp+0C0h], rcx
0x18001bac2  mov     [rbp+58h], edx
0x18001bac5  mov     eax, [rbp+58h]
0x18001bac8  cmp     eax, 0E06D7363h
0x18001bacd  jnz     short loc_18001BAE3
0x18001bacf  mov     rdx, [rbp+0C0h]
0x18001bad6  mov     ecx, [rbp+58h]
0x18001bad9  call    _XcptFilter_0
0x18001bade  mov     [rbp+60h], eax
0x18001bae1  jmp     short loc_18001BAEA
0x18001bae3  mov     dword ptr [rbp+60h], 0
0x18001baea  mov     eax, [rbp+60h]
0x18001baed  add     rsp, 20h
0x18001baf1  pop     rbp
0x18001baf2  retn
0x18001baf4  push    rbp
0x18001baf6  sub     rsp, 20h
0x18001bafa  mov     rbp, rdx
0x18001bafd  mov     rax, [rcx]
0x18001bb00  mov     edx, [rax]
0x18001bb02  mov     [rbp+0C8h], rcx
0x18001bb09  mov     [rbp+68h], edx
0x18001bb0c  mov     eax, [rbp+68h]
0x18001bb0f  cmp     eax, 0E06D7363h
0x18001bb14  jnz     short loc_18001BB2A
0x18001bb16  mov     rdx, [rbp+0C8h]
0x18001bb1d  mov     ecx, [rbp+68h]
0x18001bb20  call    _XcptFilter_0
0x18001bb25  mov     [rbp+70h], eax
0x18001bb28  jmp     short loc_18001BB31
0x18001bb2a  mov     dword ptr [rbp+70h], 0
0x18001bb31  mov     eax, [rbp+70h]
0x18001bb34  add     rsp, 20h
0x18001bb38  pop     rbp
0x18001bb39  retn
0x18001bb3b  push    rbp
0x18001bb3d  sub     rsp, 20h
0x18001bb41  mov     rbp, rdx
0x18001bb44  mov     rax, [rcx]
0x18001bb47  mov     edx, [rax]
0x18001bb49  mov     [rbp+0D0h], rcx
0x18001bb50  mov     [rbp+78h], edx
0x18001bb53  mov     eax, [rbp+78h]
0x18001bb56  cmp     eax, 0E06D7363h
0x18001bb5b  jnz     short loc_18001BB74
0x18001bb5d  mov     rdx, [rbp+0D0h]
0x18001bb64  mov     ecx, [rbp+78h]
0x18001bb67  call    _XcptFilter_0
0x18001bb6c  mov     [rbp+80h], eax
0x18001bb72  jmp     short loc_18001BB7E
0x18001bb74  mov     dword ptr [rbp+80h], 0
0x18001bb7e  mov     eax, [rbp+80h]
0x18001bb84  add     rsp, 20h
0x18001bb88  pop     rbp
0x18001bb89  retn
0x18001bb8b  push    rbp
0x18001bb8d  sub     rsp, 20h
0x18001bb91  mov     rbp, rdx
0x18001bb94  mov     rax, [rcx]
0x18001bb97  mov     edx, [rax]
0x18001bb99  mov     [rbp+0D8h], rcx
0x18001bba0  mov     [rbp+88h], edx
0x18001bba6  mov     eax, [rbp+88h]
0x18001bbac  cmp     eax, 0E06D7363h
0x18001bbb1  jnz     short loc_18001BBCD
0x18001bbb3  mov     rdx, [rbp+0D8h]
0x18001bbba  mov     ecx, [rbp+88h]
0x18001bbc0  call    _XcptFilter_0
0x18001bbc5  mov     [rbp+90h], eax
0x18001bbcb  jmp     short loc_18001BBD7
0x18001bbcd  mov     dword ptr [rbp+90h], 0
0x18001bbd7  mov     eax, [rbp+90h]
0x18001bbdd  add     rsp, 20h
0x18001bbe1  pop     rbp
0x18001bbe2  retn
0x18001bbe4  push    rbp
0x18001bbe6  sub     rsp, 20h
0x18001bbea  mov     rbp, rdx
0x18001bbed  mov     rax, [rcx]
0x18001bbf0  mov     edx, [rax]
0x18001bbf2  mov     [rbp+0E0h], rcx
0x18001bbf9  mov     [rbp+98h], edx
0x18001bbff  mov     eax, [rbp+98h]
0x18001bc05  cmp     eax, 0E06D7363h
0x18001bc0a  jnz     short loc_18001BC26
0x18001bc0c  mov     rdx, [rbp+0E0h]
0x18001bc13  mov     ecx, [rbp+98h]
0x18001bc19  call    _XcptFilter_0
0x18001bc1e  mov     [rbp+0A0h], eax
0x18001bc24  jmp     short loc_18001BC30
0x18001bc26  mov     dword ptr [rbp+0A0h], 0
0x18001bc30  mov     eax, [rbp+0A0h]
0x18001bc36  add     rsp, 20h
0x18001bc3a  pop     rbp
0x18001bc3b  retn
0x18001bc3d  push    rbp
0x18001bc3f  sub     rsp, 20h
0x18001bc43  mov     rbp, rdx
0x18001bc46  cmp     dword ptr [rbp+118h], 1
0x18001bc4d  ja      short loc_18001BC59
0x18001bc4f  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

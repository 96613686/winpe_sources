# __DllMainCRTStartup

- ea: `0x180001c34`
- end: `0x180001e40`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001bf0`

## callees

- `0x1800019c0`
- `0x180001c34`
- `0x1800023e7`
- `0x180014e08`
- `0x180023d10`

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
  if ( (_DWORD)fdwReason || dword_18003C8E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003C8E4 = 1;
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
            if ( dword_18003C8E4 )
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
0x180001c34  mov     [rsp+lpvReserved], r8
0x180001c39  mov     [rsp+arg_8], edx
0x180001c3d  mov     [rsp+arg_0], rcx
0x180001c42  push    rbx
0x180001c43  push    rsi
0x180001c44  push    rdi
0x180001c45  sub     rsp, 0F0h
0x180001c4c  mov     edi, edx
0x180001c4e  mov     rsi, rcx
0x180001c51  mov     ebx, 1
0x180001c56  cmp     edx, ebx
0x180001c58  ja      short loc_180001C60
0x180001c5a  mov     cs:__native_dllmain_reason, edx
0x180001c60  test    edx, edx
0x180001c62  jnz     short loc_180001C77
0x180001c64  cmp     cs:dword_18003C8E0, edx
0x180001c6a  jnz     short loc_180001C77
0x180001c6c  xor     ebx, ebx
0x180001c6e  mov     [rsp+108h+var_E8], ebx
0x180001c72  jmp     loc_180001E24
0x180001c77  lea     eax, [rdx-1]
0x180001c7a  cmp     eax, 1
0x180001c7d  ja      loc_180001D04
0x180001c83  mov     rax, cs:_pRawDllMain
0x180001c8a  test    rax, rax
0x180001c8d  jz      short loc_180001CC5
0x180001c8f  cmp     edx, 1
0x180001c92  jnz     short loc_180001C9A
0x180001c94  mov     cs:dword_18003C8E4, edx
0x180001c9a  mov     r8, [rsp+108h+lpvReserved]
0x180001ca2  call    cs:__guard_dispatch_icall_fptr
0x180001ca8  mov     ebx, eax
0x180001caa  mov     [rsp+108h+var_E8], eax
0x180001cae  jmp     short loc_180001CC5
0x180001cb0  xor     ebx, ebx
0x180001cb2  mov     [rsp+108h+var_E8], ebx
0x180001cb6  mov     edi, [rsp+108h+arg_8]
0x180001cbd  mov     rsi, [rsp+108h+arg_0]
0x180001cc5  test    ebx, ebx
0x180001cc7  jz      loc_180001E24
0x180001ccd  mov     r8, [rsp+108h+lpvReserved]
0x180001cd5  mov     edx, edi
0x180001cd7  mov     rcx, rsi
0x180001cda  call    _CRT_INIT
0x180001cdf  mov     ebx, eax
0x180001ce1  mov     [rsp+108h+var_E8], eax
0x180001ce5  jmp     short loc_180001CFC
0x180001ce7  xor     ebx, ebx
0x180001ce9  mov     [rsp+108h+var_E8], ebx
0x180001ced  mov     edi, [rsp+108h+arg_8]
0x180001cf4  mov     rsi, [rsp+108h+arg_0]
0x180001cfc  test    ebx, ebx
0x180001cfe  jz      loc_180001E24
0x180001d04  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001d0c  mov     edx, edi; fdwReason
0x180001d0e  mov     rcx, rsi; hinstDLL
0x180001d11  call    DllMain
0x180001d16  mov     ebx, eax
0x180001d18  mov     [rsp+108h+var_E8], eax
0x180001d1c  jmp     short loc_180001D33
0x180001d1e  xor     ebx, ebx
0x180001d20  mov     [rsp+108h+var_E8], ebx
0x180001d24  mov     edi, [rsp+108h+arg_8]
0x180001d2b  mov     rsi, [rsp+108h+arg_0]
0x180001d33  cmp     edi, 1
0x180001d36  jnz     short loc_180001DAF
0x180001d38  test    ebx, ebx
0x180001d3a  jnz     short loc_180001DAF
0x180001d3c  xor     r8d, r8d; lpvReserved
0x180001d3f  xor     edx, edx; fdwReason
0x180001d41  mov     rcx, rsi; hinstDLL
0x180001d44  call    DllMain
0x180001d49  jmp     short loc_180001D5E
0x180001d4b  mov     edi, [rsp+108h+arg_8]
0x180001d52  mov     rsi, [rsp+108h+arg_0]
0x180001d5a  mov     ebx, [rsp+108h+var_E8]
0x180001d5e  xor     r8d, r8d
0x180001d61  xor     edx, edx
0x180001d63  mov     rcx, rsi
0x180001d66  call    _CRT_INIT
0x180001d6b  jmp     short loc_180001D80
0x180001d6d  mov     edi, [rsp+108h+arg_8]
0x180001d74  mov     rsi, [rsp+108h+arg_0]
0x180001d7c  mov     ebx, [rsp+108h+var_E8]
0x180001d80  mov     rax, cs:_pRawDllMain
0x180001d87  test    rax, rax
0x180001d8a  jz      short loc_180001DAF
0x180001d8c  xor     r8d, r8d
0x180001d8f  xor     edx, edx
0x180001d91  mov     rcx, rsi
0x180001d94  call    cs:__guard_dispatch_icall_fptr
0x180001d9a  jmp     short loc_180001DAF
0x180001d9c  mov     edi, [rsp+108h+arg_8]
0x180001da3  mov     rsi, [rsp+108h+arg_0]
0x180001dab  mov     ebx, [rsp+108h+var_E8]
0x180001daf  test    edi, edi
0x180001db1  jz      short loc_180001DB8
0x180001db3  cmp     edi, 3
0x180001db6  jnz     short loc_180001E24
0x180001db8  mov     r8, [rsp+108h+lpvReserved]
0x180001dc0  mov     edx, edi
0x180001dc2  mov     rcx, rsi
0x180001dc5  call    _CRT_INIT
0x180001dca  mov     ebx, eax
0x180001dcc  mov     [rsp+108h+var_E8], eax
0x180001dd0  jmp     short loc_180001DE7
0x180001dd2  xor     ebx, ebx
0x180001dd4  mov     [rsp+108h+var_E8], ebx
0x180001dd8  mov     edi, [rsp+108h+arg_8]
0x180001ddf  mov     rsi, [rsp+108h+arg_0]
0x180001de7  mov     rax, cs:_pRawDllMain
0x180001dee  test    rax, rax
0x180001df1  jz      short loc_180001E24
0x180001df3  cmp     cs:dword_18003C8E4, 0
0x180001dfa  jz      short loc_180001E24
0x180001dfc  mov     r8, [rsp+108h+lpvReserved]
0x180001e04  mov     edx, edi
0x180001e06  mov     rcx, rsi
0x180001e09  call    cs:__guard_dispatch_icall_fptr
0x180001e0f  mov     ebx, eax
0x180001e11  mov     [rsp+108h+var_E8], eax
0x180001e15  jmp     short loc_180001E24
0x180001e17  xor     ebx, ebx
0x180001e19  mov     [rsp+108h+var_E8], ebx
0x180001e1d  mov     edi, [rsp+108h+arg_8]
0x180001e24  cmp     edi, 1
0x180001e27  ja      short loc_180001E33
0x180001e29  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001e33  mov     eax, ebx
0x180001e35  add     rsp, 0F0h
0x180001e3c  pop     rdi
0x180001e3d  pop     rsi
0x180001e3e  pop     rbx
0x180001e3f  retn
0x180023dc5  push    rbp
0x180023dc7  sub     rsp, 20h
0x180023dcb  mov     rbp, rdx
0x180023dce  mov     rax, [rcx]
0x180023dd1  mov     edx, [rax]
0x180023dd3  mov     [rbp+0A8h], rcx
0x180023dda  mov     [rbp+28h], edx
0x180023ddd  mov     eax, [rbp+28h]
0x180023de0  cmp     eax, 0E06D7363h
0x180023de5  jnz     short loc_180023DFB
0x180023de7  mov     rdx, [rbp+0A8h]
0x180023dee  mov     ecx, [rbp+28h]
0x180023df1  call    _XcptFilter_0
0x180023df6  mov     [rbp+30h], eax
0x180023df9  jmp     short loc_180023E02
0x180023dfb  mov     dword ptr [rbp+30h], 0
0x180023e02  mov     eax, [rbp+30h]
0x180023e05  add     rsp, 20h
0x180023e09  pop     rbp
0x180023e0a  retn
0x180023e0c  push    rbp
0x180023e0e  sub     rsp, 20h
0x180023e12  mov     rbp, rdx
0x180023e15  mov     rax, [rcx]
0x180023e18  mov     edx, [rax]
0x180023e1a  mov     [rbp+0B0h], rcx
0x180023e21  mov     [rbp+38h], edx
0x180023e24  mov     eax, [rbp+38h]
0x180023e27  cmp     eax, 0E06D7363h
0x180023e2c  jnz     short loc_180023E42
0x180023e2e  mov     rdx, [rbp+0B0h]
0x180023e35  mov     ecx, [rbp+38h]
0x180023e38  call    _XcptFilter_0
0x180023e3d  mov     [rbp+40h], eax
0x180023e40  jmp     short loc_180023E49
0x180023e42  mov     dword ptr [rbp+40h], 0
0x180023e49  mov     eax, [rbp+40h]
0x180023e4c  add     rsp, 20h
0x180023e50  pop     rbp
0x180023e51  retn
0x180023e53  push    rbp
0x180023e55  sub     rsp, 20h
0x180023e59  mov     rbp, rdx
0x180023e5c  mov     rax, [rcx]
0x180023e5f  mov     edx, [rax]
0x180023e61  mov     [rbp+0B8h], rcx
0x180023e68  mov     [rbp+48h], edx
0x180023e6b  mov     eax, [rbp+48h]
0x180023e6e  cmp     eax, 0E06D7363h
0x180023e73  jnz     short loc_180023E89
0x180023e75  mov     rdx, [rbp+0B8h]
0x180023e7c  mov     ecx, [rbp+48h]
0x180023e7f  call    _XcptFilter_0
0x180023e84  mov     [rbp+50h], eax
0x180023e87  jmp     short loc_180023E90
0x180023e89  mov     dword ptr [rbp+50h], 0
0x180023e90  mov     eax, [rbp+50h]
0x180023e93  add     rsp, 20h
0x180023e97  pop     rbp
0x180023e98  retn
0x180023e9a  push    rbp
0x180023e9c  sub     rsp, 20h
0x180023ea0  mov     rbp, rdx
0x180023ea3  mov     rax, [rcx]
0x180023ea6  mov     edx, [rax]
0x180023ea8  mov     [rbp+0C0h], rcx
0x180023eaf  mov     [rbp+58h], edx
0x180023eb2  mov     eax, [rbp+58h]
0x180023eb5  cmp     eax, 0E06D7363h
0x180023eba  jnz     short loc_180023ED0
0x180023ebc  mov     rdx, [rbp+0C0h]
0x180023ec3  mov     ecx, [rbp+58h]
0x180023ec6  call    _XcptFilter_0
0x180023ecb  mov     [rbp+60h], eax
0x180023ece  jmp     short loc_180023ED7
0x180023ed0  mov     dword ptr [rbp+60h], 0
0x180023ed7  mov     eax, [rbp+60h]
0x180023eda  add     rsp, 20h
0x180023ede  pop     rbp
0x180023edf  retn
0x180023ee1  push    rbp
0x180023ee3  sub     rsp, 20h
0x180023ee7  mov     rbp, rdx
0x180023eea  mov     rax, [rcx]
0x180023eed  mov     edx, [rax]
0x180023eef  mov     [rbp+0C8h], rcx
0x180023ef6  mov     [rbp+68h], edx
0x180023ef9  mov     eax, [rbp+68h]
0x180023efc  cmp     eax, 0E06D7363h
0x180023f01  jnz     short loc_180023F17
0x180023f03  mov     rdx, [rbp+0C8h]
0x180023f0a  mov     ecx, [rbp+68h]
0x180023f0d  call    _XcptFilter_0
0x180023f12  mov     [rbp+70h], eax
0x180023f15  jmp     short loc_180023F1E
0x180023f17  mov     dword ptr [rbp+70h], 0
0x180023f1e  mov     eax, [rbp+70h]
0x180023f21  add     rsp, 20h
0x180023f25  pop     rbp
0x180023f26  retn
0x180023f28  push    rbp
0x180023f2a  sub     rsp, 20h
0x180023f2e  mov     rbp, rdx
0x180023f31  mov     rax, [rcx]
0x180023f34  mov     edx, [rax]
0x180023f36  mov     [rbp+0D0h], rcx
0x180023f3d  mov     [rbp+78h], edx
0x180023f40  mov     eax, [rbp+78h]
0x180023f43  cmp     eax, 0E06D7363h
0x180023f48  jnz     short loc_180023F61
0x180023f4a  mov     rdx, [rbp+0D0h]
0x180023f51  mov     ecx, [rbp+78h]
0x180023f54  call    _XcptFilter_0
0x180023f59  mov     [rbp+80h], eax
0x180023f5f  jmp     short loc_180023F6B
0x180023f61  mov     dword ptr [rbp+80h], 0
0x180023f6b  mov     eax, [rbp+80h]
0x180023f71  add     rsp, 20h
0x180023f75  pop     rbp
0x180023f76  retn
0x180023f78  push    rbp
0x180023f7a  sub     rsp, 20h
0x180023f7e  mov     rbp, rdx
0x180023f81  mov     rax, [rcx]
0x180023f84  mov     edx, [rax]
0x180023f86  mov     [rbp+0D8h], rcx
0x180023f8d  mov     [rbp+88h], edx
0x180023f93  mov     eax, [rbp+88h]
0x180023f99  cmp     eax, 0E06D7363h
0x180023f9e  jnz     short loc_180023FBA
0x180023fa0  mov     rdx, [rbp+0D8h]
0x180023fa7  mov     ecx, [rbp+88h]
0x180023fad  call    _XcptFilter_0
0x180023fb2  mov     [rbp+90h], eax
0x180023fb8  jmp     short loc_180023FC4
0x180023fba  mov     dword ptr [rbp+90h], 0
0x180023fc4  mov     eax, [rbp+90h]
0x180023fca  add     rsp, 20h
0x180023fce  pop     rbp
0x180023fcf  retn
0x180023fd1  push    rbp
0x180023fd3  sub     rsp, 20h
0x180023fd7  mov     rbp, rdx
0x180023fda  mov     rax, [rcx]
0x180023fdd  mov     edx, [rax]
0x180023fdf  mov     [rbp+0E0h], rcx
0x180023fe6  mov     [rbp+98h], edx
0x180023fec  mov     eax, [rbp+98h]
0x180023ff2  cmp     eax, 0E06D7363h
0x180023ff7  jnz     short loc_180024013
0x180023ff9  mov     rdx, [rbp+0E0h]
0x180024000  mov     ecx, [rbp+98h]
0x180024006  call    _XcptFilter_0
0x18002400b  mov     [rbp+0A0h], eax
0x180024011  jmp     short loc_18002401D
0x180024013  mov     dword ptr [rbp+0A0h], 0
0x18002401d  mov     eax, [rbp+0A0h]
0x180024023  add     rsp, 20h
0x180024027  pop     rbp
0x180024028  retn
0x18002402a  push    rbp
0x18002402c  sub     rsp, 20h
0x180024030  mov     rbp, rdx
0x180024033  cmp     dword ptr [rbp+118h], 1
0x18002403a  ja      short loc_180024046
0x18002403c  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

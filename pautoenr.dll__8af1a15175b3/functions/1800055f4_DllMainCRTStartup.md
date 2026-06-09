# __DllMainCRTStartup

- ea: `0x1800055f4`
- end: `0x180005800`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800055b0`

## callees

- `0x1800046f0`
- `0x180005380`
- `0x1800055f4`
- `0x180005a06`
- `0x180007d60`

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
  if ( (_DWORD)fdwReason || dword_18000E0E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000E0E4 = 1;
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
            if ( dword_18000E0E4 )
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
0x1800055f4  mov     [rsp+lpvReserved], r8
0x1800055f9  mov     [rsp+arg_8], edx
0x1800055fd  mov     [rsp+arg_0], rcx
0x180005602  push    rbx
0x180005603  push    rsi
0x180005604  push    rdi
0x180005605  sub     rsp, 0F0h
0x18000560c  mov     edi, edx
0x18000560e  mov     rsi, rcx
0x180005611  mov     ebx, 1
0x180005616  cmp     edx, ebx
0x180005618  ja      short loc_180005620
0x18000561a  mov     cs:__native_dllmain_reason, edx
0x180005620  test    edx, edx
0x180005622  jnz     short loc_180005637
0x180005624  cmp     cs:dword_18000E0E0, edx
0x18000562a  jnz     short loc_180005637
0x18000562c  xor     ebx, ebx
0x18000562e  mov     [rsp+108h+var_E8], ebx
0x180005632  jmp     loc_1800057E4
0x180005637  lea     eax, [rdx-1]
0x18000563a  cmp     eax, 1
0x18000563d  ja      loc_1800056C4
0x180005643  mov     rax, cs:_pRawDllMain
0x18000564a  test    rax, rax
0x18000564d  jz      short loc_180005685
0x18000564f  cmp     edx, 1
0x180005652  jnz     short loc_18000565A
0x180005654  mov     cs:dword_18000E0E4, edx
0x18000565a  mov     r8, [rsp+108h+lpvReserved]
0x180005662  call    cs:__guard_dispatch_icall_fptr
0x180005668  mov     ebx, eax
0x18000566a  mov     [rsp+108h+var_E8], eax
0x18000566e  jmp     short loc_180005685
0x180005670  xor     ebx, ebx
0x180005672  mov     [rsp+108h+var_E8], ebx
0x180005676  mov     edi, [rsp+108h+arg_8]
0x18000567d  mov     rsi, [rsp+108h+arg_0]
0x180005685  test    ebx, ebx
0x180005687  jz      loc_1800057E4
0x18000568d  mov     r8, [rsp+108h+lpvReserved]
0x180005695  mov     edx, edi
0x180005697  mov     rcx, rsi
0x18000569a  call    _CRT_INIT
0x18000569f  mov     ebx, eax
0x1800056a1  mov     [rsp+108h+var_E8], eax
0x1800056a5  jmp     short loc_1800056BC
0x1800056a7  xor     ebx, ebx
0x1800056a9  mov     [rsp+108h+var_E8], ebx
0x1800056ad  mov     edi, [rsp+108h+arg_8]
0x1800056b4  mov     rsi, [rsp+108h+arg_0]
0x1800056bc  test    ebx, ebx
0x1800056be  jz      loc_1800057E4
0x1800056c4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800056cc  mov     edx, edi; fdwReason
0x1800056ce  mov     rcx, rsi; hinstDLL
0x1800056d1  call    DllMain
0x1800056d6  mov     ebx, eax
0x1800056d8  mov     [rsp+108h+var_E8], eax
0x1800056dc  jmp     short loc_1800056F3
0x1800056de  xor     ebx, ebx
0x1800056e0  mov     [rsp+108h+var_E8], ebx
0x1800056e4  mov     edi, [rsp+108h+arg_8]
0x1800056eb  mov     rsi, [rsp+108h+arg_0]
0x1800056f3  cmp     edi, 1
0x1800056f6  jnz     short loc_18000576F
0x1800056f8  test    ebx, ebx
0x1800056fa  jnz     short loc_18000576F
0x1800056fc  xor     r8d, r8d; lpvReserved
0x1800056ff  xor     edx, edx; fdwReason
0x180005701  mov     rcx, rsi; hinstDLL
0x180005704  call    DllMain
0x180005709  jmp     short loc_18000571E
0x18000570b  mov     edi, [rsp+108h+arg_8]
0x180005712  mov     rsi, [rsp+108h+arg_0]
0x18000571a  mov     ebx, [rsp+108h+var_E8]
0x18000571e  xor     r8d, r8d
0x180005721  xor     edx, edx
0x180005723  mov     rcx, rsi
0x180005726  call    _CRT_INIT
0x18000572b  jmp     short loc_180005740
0x18000572d  mov     edi, [rsp+108h+arg_8]
0x180005734  mov     rsi, [rsp+108h+arg_0]
0x18000573c  mov     ebx, [rsp+108h+var_E8]
0x180005740  mov     rax, cs:_pRawDllMain
0x180005747  test    rax, rax
0x18000574a  jz      short loc_18000576F
0x18000574c  xor     r8d, r8d
0x18000574f  xor     edx, edx
0x180005751  mov     rcx, rsi
0x180005754  call    cs:__guard_dispatch_icall_fptr
0x18000575a  jmp     short loc_18000576F
0x18000575c  mov     edi, [rsp+108h+arg_8]
0x180005763  mov     rsi, [rsp+108h+arg_0]
0x18000576b  mov     ebx, [rsp+108h+var_E8]
0x18000576f  test    edi, edi
0x180005771  jz      short loc_180005778
0x180005773  cmp     edi, 3
0x180005776  jnz     short loc_1800057E4
0x180005778  mov     r8, [rsp+108h+lpvReserved]
0x180005780  mov     edx, edi
0x180005782  mov     rcx, rsi
0x180005785  call    _CRT_INIT
0x18000578a  mov     ebx, eax
0x18000578c  mov     [rsp+108h+var_E8], eax
0x180005790  jmp     short loc_1800057A7
0x180005792  xor     ebx, ebx
0x180005794  mov     [rsp+108h+var_E8], ebx
0x180005798  mov     edi, [rsp+108h+arg_8]
0x18000579f  mov     rsi, [rsp+108h+arg_0]
0x1800057a7  mov     rax, cs:_pRawDllMain
0x1800057ae  test    rax, rax
0x1800057b1  jz      short loc_1800057E4
0x1800057b3  cmp     cs:dword_18000E0E4, 0
0x1800057ba  jz      short loc_1800057E4
0x1800057bc  mov     r8, [rsp+108h+lpvReserved]
0x1800057c4  mov     edx, edi
0x1800057c6  mov     rcx, rsi
0x1800057c9  call    cs:__guard_dispatch_icall_fptr
0x1800057cf  mov     ebx, eax
0x1800057d1  mov     [rsp+108h+var_E8], eax
0x1800057d5  jmp     short loc_1800057E4
0x1800057d7  xor     ebx, ebx
0x1800057d9  mov     [rsp+108h+var_E8], ebx
0x1800057dd  mov     edi, [rsp+108h+arg_8]
0x1800057e4  cmp     edi, 1
0x1800057e7  ja      short loc_1800057F3
0x1800057e9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800057f3  mov     eax, ebx
0x1800057f5  add     rsp, 0F0h
0x1800057fc  pop     rdi
0x1800057fd  pop     rsi
0x1800057fe  pop     rbx
0x1800057ff  retn
0x180007df3  push    rbp
0x180007df5  sub     rsp, 20h
0x180007df9  mov     rbp, rdx
0x180007dfc  mov     rax, [rcx]
0x180007dff  mov     edx, [rax]
0x180007e01  mov     [rbp+0A8h], rcx
0x180007e08  mov     [rbp+28h], edx
0x180007e0b  mov     eax, [rbp+28h]
0x180007e0e  cmp     eax, 0E06D7363h
0x180007e13  jnz     short loc_180007E29
0x180007e15  mov     rdx, [rbp+0A8h]
0x180007e1c  mov     ecx, [rbp+28h]
0x180007e1f  call    _XcptFilter_0
0x180007e24  mov     [rbp+30h], eax
0x180007e27  jmp     short loc_180007E30
0x180007e29  mov     dword ptr [rbp+30h], 0
0x180007e30  mov     eax, [rbp+30h]
0x180007e33  add     rsp, 20h
0x180007e37  pop     rbp
0x180007e38  retn
0x180007e3a  push    rbp
0x180007e3c  sub     rsp, 20h
0x180007e40  mov     rbp, rdx
0x180007e43  mov     rax, [rcx]
0x180007e46  mov     edx, [rax]
0x180007e48  mov     [rbp+0B0h], rcx
0x180007e4f  mov     [rbp+38h], edx
0x180007e52  mov     eax, [rbp+38h]
0x180007e55  cmp     eax, 0E06D7363h
0x180007e5a  jnz     short loc_180007E70
0x180007e5c  mov     rdx, [rbp+0B0h]
0x180007e63  mov     ecx, [rbp+38h]
0x180007e66  call    _XcptFilter_0
0x180007e6b  mov     [rbp+40h], eax
0x180007e6e  jmp     short loc_180007E77
0x180007e70  mov     dword ptr [rbp+40h], 0
0x180007e77  mov     eax, [rbp+40h]
0x180007e7a  add     rsp, 20h
0x180007e7e  pop     rbp
0x180007e7f  retn
0x180007e81  push    rbp
0x180007e83  sub     rsp, 20h
0x180007e87  mov     rbp, rdx
0x180007e8a  mov     rax, [rcx]
0x180007e8d  mov     edx, [rax]
0x180007e8f  mov     [rbp+0B8h], rcx
0x180007e96  mov     [rbp+48h], edx
0x180007e99  mov     eax, [rbp+48h]
0x180007e9c  cmp     eax, 0E06D7363h
0x180007ea1  jnz     short loc_180007EB7
0x180007ea3  mov     rdx, [rbp+0B8h]
0x180007eaa  mov     ecx, [rbp+48h]
0x180007ead  call    _XcptFilter_0
0x180007eb2  mov     [rbp+50h], eax
0x180007eb5  jmp     short loc_180007EBE
0x180007eb7  mov     dword ptr [rbp+50h], 0
0x180007ebe  mov     eax, [rbp+50h]
0x180007ec1  add     rsp, 20h
0x180007ec5  pop     rbp
0x180007ec6  retn
0x180007ec8  push    rbp
0x180007eca  sub     rsp, 20h
0x180007ece  mov     rbp, rdx
0x180007ed1  mov     rax, [rcx]
0x180007ed4  mov     edx, [rax]
0x180007ed6  mov     [rbp+0C0h], rcx
0x180007edd  mov     [rbp+58h], edx
0x180007ee0  mov     eax, [rbp+58h]
0x180007ee3  cmp     eax, 0E06D7363h
0x180007ee8  jnz     short loc_180007EFE
0x180007eea  mov     rdx, [rbp+0C0h]
0x180007ef1  mov     ecx, [rbp+58h]
0x180007ef4  call    _XcptFilter_0
0x180007ef9  mov     [rbp+60h], eax
0x180007efc  jmp     short loc_180007F05
0x180007efe  mov     dword ptr [rbp+60h], 0
0x180007f05  mov     eax, [rbp+60h]
0x180007f08  add     rsp, 20h
0x180007f0c  pop     rbp
0x180007f0d  retn
0x180007f0f  push    rbp
0x180007f11  sub     rsp, 20h
0x180007f15  mov     rbp, rdx
0x180007f18  mov     rax, [rcx]
0x180007f1b  mov     edx, [rax]
0x180007f1d  mov     [rbp+0C8h], rcx
0x180007f24  mov     [rbp+68h], edx
0x180007f27  mov     eax, [rbp+68h]
0x180007f2a  cmp     eax, 0E06D7363h
0x180007f2f  jnz     short loc_180007F45
0x180007f31  mov     rdx, [rbp+0C8h]
0x180007f38  mov     ecx, [rbp+68h]
0x180007f3b  call    _XcptFilter_0
0x180007f40  mov     [rbp+70h], eax
0x180007f43  jmp     short loc_180007F4C
0x180007f45  mov     dword ptr [rbp+70h], 0
0x180007f4c  mov     eax, [rbp+70h]
0x180007f4f  add     rsp, 20h
0x180007f53  pop     rbp
0x180007f54  retn
0x180007f56  push    rbp
0x180007f58  sub     rsp, 20h
0x180007f5c  mov     rbp, rdx
0x180007f5f  mov     rax, [rcx]
0x180007f62  mov     edx, [rax]
0x180007f64  mov     [rbp+0D0h], rcx
0x180007f6b  mov     [rbp+78h], edx
0x180007f6e  mov     eax, [rbp+78h]
0x180007f71  cmp     eax, 0E06D7363h
0x180007f76  jnz     short loc_180007F8F
0x180007f78  mov     rdx, [rbp+0D0h]
0x180007f7f  mov     ecx, [rbp+78h]
0x180007f82  call    _XcptFilter_0
0x180007f87  mov     [rbp+80h], eax
0x180007f8d  jmp     short loc_180007F99
0x180007f8f  mov     dword ptr [rbp+80h], 0
0x180007f99  mov     eax, [rbp+80h]
0x180007f9f  add     rsp, 20h
0x180007fa3  pop     rbp
0x180007fa4  retn
0x180007fa6  push    rbp
0x180007fa8  sub     rsp, 20h
0x180007fac  mov     rbp, rdx
0x180007faf  mov     rax, [rcx]
0x180007fb2  mov     edx, [rax]
0x180007fb4  mov     [rbp+0D8h], rcx
0x180007fbb  mov     [rbp+88h], edx
0x180007fc1  mov     eax, [rbp+88h]
0x180007fc7  cmp     eax, 0E06D7363h
0x180007fcc  jnz     short loc_180007FE8
0x180007fce  mov     rdx, [rbp+0D8h]
0x180007fd5  mov     ecx, [rbp+88h]
0x180007fdb  call    _XcptFilter_0
0x180007fe0  mov     [rbp+90h], eax
0x180007fe6  jmp     short loc_180007FF2
0x180007fe8  mov     dword ptr [rbp+90h], 0
0x180007ff2  mov     eax, [rbp+90h]
0x180007ff8  add     rsp, 20h
0x180007ffc  pop     rbp
0x180007ffd  retn
0x180007fff  push    rbp
0x180008001  sub     rsp, 20h
0x180008005  mov     rbp, rdx
0x180008008  mov     rax, [rcx]
0x18000800b  mov     edx, [rax]
0x18000800d  mov     [rbp+0E0h], rcx
0x180008014  mov     [rbp+98h], edx
0x18000801a  mov     eax, [rbp+98h]
0x180008020  cmp     eax, 0E06D7363h
0x180008025  jnz     short loc_180008041
0x180008027  mov     rdx, [rbp+0E0h]
0x18000802e  mov     ecx, [rbp+98h]
0x180008034  call    _XcptFilter_0
0x180008039  mov     [rbp+0A0h], eax
0x18000803f  jmp     short loc_18000804B
0x180008041  mov     dword ptr [rbp+0A0h], 0
0x18000804b  mov     eax, [rbp+0A0h]
0x180008051  add     rsp, 20h
0x180008055  pop     rbp
0x180008056  retn
0x180008058  push    rbp
0x18000805a  sub     rsp, 20h
0x18000805e  mov     rbp, rdx
0x180008061  cmp     dword ptr [rbp+118h], 1
0x180008068  ja      short loc_180008074
0x18000806a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

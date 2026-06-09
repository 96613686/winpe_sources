# __DllMainCRTStartup

- ea: `0x180001994`
- end: `0x180001ba0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001950`

## callees

- `0x180001720`
- `0x180001994`
- `0x180001dce`
- `0x180006030`
- `0x18000c670`

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
  if ( (_DWORD)fdwReason || dword_180014444 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180014448 = 1;
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
            if ( dword_180014448 )
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
0x180001994  mov     [rsp+lpvReserved], r8
0x180001999  mov     [rsp+arg_8], edx
0x18000199d  mov     [rsp+arg_0], rcx
0x1800019a2  push    rbx
0x1800019a3  push    rsi
0x1800019a4  push    rdi
0x1800019a5  sub     rsp, 0F0h
0x1800019ac  mov     edi, edx
0x1800019ae  mov     rsi, rcx
0x1800019b1  mov     ebx, 1
0x1800019b6  cmp     edx, ebx
0x1800019b8  ja      short loc_1800019C0
0x1800019ba  mov     cs:__native_dllmain_reason, edx
0x1800019c0  test    edx, edx
0x1800019c2  jnz     short loc_1800019D7
0x1800019c4  cmp     cs:dword_180014444, edx
0x1800019ca  jnz     short loc_1800019D7
0x1800019cc  xor     ebx, ebx
0x1800019ce  mov     [rsp+108h+var_E8], ebx
0x1800019d2  jmp     loc_180001B84
0x1800019d7  lea     eax, [rdx-1]
0x1800019da  cmp     eax, 1
0x1800019dd  ja      loc_180001A64
0x1800019e3  mov     rax, cs:_pRawDllMain
0x1800019ea  test    rax, rax
0x1800019ed  jz      short loc_180001A25
0x1800019ef  cmp     edx, 1
0x1800019f2  jnz     short loc_1800019FA
0x1800019f4  mov     cs:dword_180014448, edx
0x1800019fa  mov     r8, [rsp+108h+lpvReserved]
0x180001a02  call    cs:__guard_dispatch_icall_fptr
0x180001a08  mov     ebx, eax
0x180001a0a  mov     [rsp+108h+var_E8], eax
0x180001a0e  jmp     short loc_180001A25
0x180001a10  xor     ebx, ebx
0x180001a12  mov     [rsp+108h+var_E8], ebx
0x180001a16  mov     edi, [rsp+108h+arg_8]
0x180001a1d  mov     rsi, [rsp+108h+arg_0]
0x180001a25  test    ebx, ebx
0x180001a27  jz      loc_180001B84
0x180001a2d  mov     r8, [rsp+108h+lpvReserved]
0x180001a35  mov     edx, edi
0x180001a37  mov     rcx, rsi
0x180001a3a  call    _CRT_INIT
0x180001a3f  mov     ebx, eax
0x180001a41  mov     [rsp+108h+var_E8], eax
0x180001a45  jmp     short loc_180001A5C
0x180001a47  xor     ebx, ebx
0x180001a49  mov     [rsp+108h+var_E8], ebx
0x180001a4d  mov     edi, [rsp+108h+arg_8]
0x180001a54  mov     rsi, [rsp+108h+arg_0]
0x180001a5c  test    ebx, ebx
0x180001a5e  jz      loc_180001B84
0x180001a64  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001a6c  mov     edx, edi; fdwReason
0x180001a6e  mov     rcx, rsi; hinstDLL
0x180001a71  call    DllMain
0x180001a76  mov     ebx, eax
0x180001a78  mov     [rsp+108h+var_E8], eax
0x180001a7c  jmp     short loc_180001A93
0x180001a7e  xor     ebx, ebx
0x180001a80  mov     [rsp+108h+var_E8], ebx
0x180001a84  mov     edi, [rsp+108h+arg_8]
0x180001a8b  mov     rsi, [rsp+108h+arg_0]
0x180001a93  cmp     edi, 1
0x180001a96  jnz     short loc_180001B0F
0x180001a98  test    ebx, ebx
0x180001a9a  jnz     short loc_180001B0F
0x180001a9c  xor     r8d, r8d; lpvReserved
0x180001a9f  xor     edx, edx; fdwReason
0x180001aa1  mov     rcx, rsi; hinstDLL
0x180001aa4  call    DllMain
0x180001aa9  jmp     short loc_180001ABE
0x180001aab  mov     edi, [rsp+108h+arg_8]
0x180001ab2  mov     rsi, [rsp+108h+arg_0]
0x180001aba  mov     ebx, [rsp+108h+var_E8]
0x180001abe  xor     r8d, r8d
0x180001ac1  xor     edx, edx
0x180001ac3  mov     rcx, rsi
0x180001ac6  call    _CRT_INIT
0x180001acb  jmp     short loc_180001AE0
0x180001acd  mov     edi, [rsp+108h+arg_8]
0x180001ad4  mov     rsi, [rsp+108h+arg_0]
0x180001adc  mov     ebx, [rsp+108h+var_E8]
0x180001ae0  mov     rax, cs:_pRawDllMain
0x180001ae7  test    rax, rax
0x180001aea  jz      short loc_180001B0F
0x180001aec  xor     r8d, r8d
0x180001aef  xor     edx, edx
0x180001af1  mov     rcx, rsi
0x180001af4  call    cs:__guard_dispatch_icall_fptr
0x180001afa  jmp     short loc_180001B0F
0x180001afc  mov     edi, [rsp+108h+arg_8]
0x180001b03  mov     rsi, [rsp+108h+arg_0]
0x180001b0b  mov     ebx, [rsp+108h+var_E8]
0x180001b0f  test    edi, edi
0x180001b11  jz      short loc_180001B18
0x180001b13  cmp     edi, 3
0x180001b16  jnz     short loc_180001B84
0x180001b18  mov     r8, [rsp+108h+lpvReserved]
0x180001b20  mov     edx, edi
0x180001b22  mov     rcx, rsi
0x180001b25  call    _CRT_INIT
0x180001b2a  mov     ebx, eax
0x180001b2c  mov     [rsp+108h+var_E8], eax
0x180001b30  jmp     short loc_180001B47
0x180001b32  xor     ebx, ebx
0x180001b34  mov     [rsp+108h+var_E8], ebx
0x180001b38  mov     edi, [rsp+108h+arg_8]
0x180001b3f  mov     rsi, [rsp+108h+arg_0]
0x180001b47  mov     rax, cs:_pRawDllMain
0x180001b4e  test    rax, rax
0x180001b51  jz      short loc_180001B84
0x180001b53  cmp     cs:dword_180014448, 0
0x180001b5a  jz      short loc_180001B84
0x180001b5c  mov     r8, [rsp+108h+lpvReserved]
0x180001b64  mov     edx, edi
0x180001b66  mov     rcx, rsi
0x180001b69  call    cs:__guard_dispatch_icall_fptr
0x180001b6f  mov     ebx, eax
0x180001b71  mov     [rsp+108h+var_E8], eax
0x180001b75  jmp     short loc_180001B84
0x180001b77  xor     ebx, ebx
0x180001b79  mov     [rsp+108h+var_E8], ebx
0x180001b7d  mov     edi, [rsp+108h+arg_8]
0x180001b84  cmp     edi, 1
0x180001b87  ja      short loc_180001B93
0x180001b89  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001b93  mov     eax, ebx
0x180001b95  add     rsp, 0F0h
0x180001b9c  pop     rdi
0x180001b9d  pop     rsi
0x180001b9e  pop     rbx
0x180001b9f  retn
0x18000c713  push    rbp
0x18000c715  sub     rsp, 20h
0x18000c719  mov     rbp, rdx
0x18000c71c  mov     rax, [rcx]
0x18000c71f  mov     edx, [rax]
0x18000c721  mov     [rbp+0A8h], rcx
0x18000c728  mov     [rbp+28h], edx
0x18000c72b  mov     eax, [rbp+28h]
0x18000c72e  cmp     eax, 0E06D7363h
0x18000c733  jnz     short loc_18000C749
0x18000c735  mov     rdx, [rbp+0A8h]
0x18000c73c  mov     ecx, [rbp+28h]
0x18000c73f  call    _XcptFilter_0
0x18000c744  mov     [rbp+30h], eax
0x18000c747  jmp     short loc_18000C750
0x18000c749  mov     dword ptr [rbp+30h], 0
0x18000c750  mov     eax, [rbp+30h]
0x18000c753  add     rsp, 20h
0x18000c757  pop     rbp
0x18000c758  retn
0x18000c75a  push    rbp
0x18000c75c  sub     rsp, 20h
0x18000c760  mov     rbp, rdx
0x18000c763  mov     rax, [rcx]
0x18000c766  mov     edx, [rax]
0x18000c768  mov     [rbp+0B0h], rcx
0x18000c76f  mov     [rbp+38h], edx
0x18000c772  mov     eax, [rbp+38h]
0x18000c775  cmp     eax, 0E06D7363h
0x18000c77a  jnz     short loc_18000C790
0x18000c77c  mov     rdx, [rbp+0B0h]
0x18000c783  mov     ecx, [rbp+38h]
0x18000c786  call    _XcptFilter_0
0x18000c78b  mov     [rbp+40h], eax
0x18000c78e  jmp     short loc_18000C797
0x18000c790  mov     dword ptr [rbp+40h], 0
0x18000c797  mov     eax, [rbp+40h]
0x18000c79a  add     rsp, 20h
0x18000c79e  pop     rbp
0x18000c79f  retn
0x18000c7a1  push    rbp
0x18000c7a3  sub     rsp, 20h
0x18000c7a7  mov     rbp, rdx
0x18000c7aa  mov     rax, [rcx]
0x18000c7ad  mov     edx, [rax]
0x18000c7af  mov     [rbp+0B8h], rcx
0x18000c7b6  mov     [rbp+48h], edx
0x18000c7b9  mov     eax, [rbp+48h]
0x18000c7bc  cmp     eax, 0E06D7363h
0x18000c7c1  jnz     short loc_18000C7D7
0x18000c7c3  mov     rdx, [rbp+0B8h]
0x18000c7ca  mov     ecx, [rbp+48h]
0x18000c7cd  call    _XcptFilter_0
0x18000c7d2  mov     [rbp+50h], eax
0x18000c7d5  jmp     short loc_18000C7DE
0x18000c7d7  mov     dword ptr [rbp+50h], 0
0x18000c7de  mov     eax, [rbp+50h]
0x18000c7e1  add     rsp, 20h
0x18000c7e5  pop     rbp
0x18000c7e6  retn
0x18000c7e8  push    rbp
0x18000c7ea  sub     rsp, 20h
0x18000c7ee  mov     rbp, rdx
0x18000c7f1  mov     rax, [rcx]
0x18000c7f4  mov     edx, [rax]
0x18000c7f6  mov     [rbp+0C0h], rcx
0x18000c7fd  mov     [rbp+58h], edx
0x18000c800  mov     eax, [rbp+58h]
0x18000c803  cmp     eax, 0E06D7363h
0x18000c808  jnz     short loc_18000C81E
0x18000c80a  mov     rdx, [rbp+0C0h]
0x18000c811  mov     ecx, [rbp+58h]
0x18000c814  call    _XcptFilter_0
0x18000c819  mov     [rbp+60h], eax
0x18000c81c  jmp     short loc_18000C825
0x18000c81e  mov     dword ptr [rbp+60h], 0
0x18000c825  mov     eax, [rbp+60h]
0x18000c828  add     rsp, 20h
0x18000c82c  pop     rbp
0x18000c82d  retn
0x18000c82f  push    rbp
0x18000c831  sub     rsp, 20h
0x18000c835  mov     rbp, rdx
0x18000c838  mov     rax, [rcx]
0x18000c83b  mov     edx, [rax]
0x18000c83d  mov     [rbp+0C8h], rcx
0x18000c844  mov     [rbp+68h], edx
0x18000c847  mov     eax, [rbp+68h]
0x18000c84a  cmp     eax, 0E06D7363h
0x18000c84f  jnz     short loc_18000C865
0x18000c851  mov     rdx, [rbp+0C8h]
0x18000c858  mov     ecx, [rbp+68h]
0x18000c85b  call    _XcptFilter_0
0x18000c860  mov     [rbp+70h], eax
0x18000c863  jmp     short loc_18000C86C
0x18000c865  mov     dword ptr [rbp+70h], 0
0x18000c86c  mov     eax, [rbp+70h]
0x18000c86f  add     rsp, 20h
0x18000c873  pop     rbp
0x18000c874  retn
0x18000c876  push    rbp
0x18000c878  sub     rsp, 20h
0x18000c87c  mov     rbp, rdx
0x18000c87f  mov     rax, [rcx]
0x18000c882  mov     edx, [rax]
0x18000c884  mov     [rbp+0D0h], rcx
0x18000c88b  mov     [rbp+78h], edx
0x18000c88e  mov     eax, [rbp+78h]
0x18000c891  cmp     eax, 0E06D7363h
0x18000c896  jnz     short loc_18000C8AF
0x18000c898  mov     rdx, [rbp+0D0h]
0x18000c89f  mov     ecx, [rbp+78h]
0x18000c8a2  call    _XcptFilter_0
0x18000c8a7  mov     [rbp+80h], eax
0x18000c8ad  jmp     short loc_18000C8B9
0x18000c8af  mov     dword ptr [rbp+80h], 0
0x18000c8b9  mov     eax, [rbp+80h]
0x18000c8bf  add     rsp, 20h
0x18000c8c3  pop     rbp
0x18000c8c4  retn
0x18000c8c6  push    rbp
0x18000c8c8  sub     rsp, 20h
0x18000c8cc  mov     rbp, rdx
0x18000c8cf  mov     rax, [rcx]
0x18000c8d2  mov     edx, [rax]
0x18000c8d4  mov     [rbp+0D8h], rcx
0x18000c8db  mov     [rbp+88h], edx
0x18000c8e1  mov     eax, [rbp+88h]
0x18000c8e7  cmp     eax, 0E06D7363h
0x18000c8ec  jnz     short loc_18000C908
0x18000c8ee  mov     rdx, [rbp+0D8h]
0x18000c8f5  mov     ecx, [rbp+88h]
0x18000c8fb  call    _XcptFilter_0
0x18000c900  mov     [rbp+90h], eax
0x18000c906  jmp     short loc_18000C912
0x18000c908  mov     dword ptr [rbp+90h], 0
0x18000c912  mov     eax, [rbp+90h]
0x18000c918  add     rsp, 20h
0x18000c91c  pop     rbp
0x18000c91d  retn
0x18000c91f  push    rbp
0x18000c921  sub     rsp, 20h
0x18000c925  mov     rbp, rdx
0x18000c928  mov     rax, [rcx]
0x18000c92b  mov     edx, [rax]
0x18000c92d  mov     [rbp+0E0h], rcx
0x18000c934  mov     [rbp+98h], edx
0x18000c93a  mov     eax, [rbp+98h]
0x18000c940  cmp     eax, 0E06D7363h
0x18000c945  jnz     short loc_18000C961
0x18000c947  mov     rdx, [rbp+0E0h]
0x18000c94e  mov     ecx, [rbp+98h]
0x18000c954  call    _XcptFilter_0
0x18000c959  mov     [rbp+0A0h], eax
0x18000c95f  jmp     short loc_18000C96B
0x18000c961  mov     dword ptr [rbp+0A0h], 0
0x18000c96b  mov     eax, [rbp+0A0h]
0x18000c971  add     rsp, 20h
0x18000c975  pop     rbp
0x18000c976  retn
0x18000c978  push    rbp
0x18000c97a  sub     rsp, 20h
0x18000c97e  mov     rbp, rdx
0x18000c981  cmp     dword ptr [rbp+118h], 1
0x18000c988  ja      short loc_18000C994
0x18000c98a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

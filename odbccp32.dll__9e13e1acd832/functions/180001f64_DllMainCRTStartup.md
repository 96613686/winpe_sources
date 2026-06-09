# __DllMainCRTStartup

- ea: `0x180001f64`
- end: `0x180002170`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001f20`

## callees

- `0x180001cf0`
- `0x180001f64`
- `0x1800024a0`
- `0x180007394`
- `0x180014b20`

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
  if ( (_DWORD)fdwReason || dword_18001C1E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001C1E4 = 1;
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
            if ( dword_18001C1E4 )
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
0x180001f64  mov     [rsp+lpvReserved], r8
0x180001f69  mov     [rsp+arg_8], edx
0x180001f6d  mov     [rsp+arg_0], rcx
0x180001f72  push    rbx
0x180001f73  push    rsi
0x180001f74  push    rdi
0x180001f75  sub     rsp, 0F0h
0x180001f7c  mov     edi, edx
0x180001f7e  mov     rsi, rcx
0x180001f81  mov     ebx, 1
0x180001f86  cmp     edx, ebx
0x180001f88  ja      short loc_180001F90
0x180001f8a  mov     cs:__native_dllmain_reason, edx
0x180001f90  test    edx, edx
0x180001f92  jnz     short loc_180001FA7
0x180001f94  cmp     cs:dword_18001C1E0, edx
0x180001f9a  jnz     short loc_180001FA7
0x180001f9c  xor     ebx, ebx
0x180001f9e  mov     [rsp+108h+var_E8], ebx
0x180001fa2  jmp     loc_180002154
0x180001fa7  lea     eax, [rdx-1]
0x180001faa  cmp     eax, 1
0x180001fad  ja      loc_180002034
0x180001fb3  mov     rax, cs:_pRawDllMain
0x180001fba  test    rax, rax
0x180001fbd  jz      short loc_180001FF5
0x180001fbf  cmp     edx, 1
0x180001fc2  jnz     short loc_180001FCA
0x180001fc4  mov     cs:dword_18001C1E4, edx
0x180001fca  mov     r8, [rsp+108h+lpvReserved]
0x180001fd2  call    cs:__guard_dispatch_icall_fptr
0x180001fd8  mov     ebx, eax
0x180001fda  mov     [rsp+108h+var_E8], eax
0x180001fde  jmp     short loc_180001FF5
0x180001fe0  xor     ebx, ebx
0x180001fe2  mov     [rsp+108h+var_E8], ebx
0x180001fe6  mov     edi, [rsp+108h+arg_8]
0x180001fed  mov     rsi, [rsp+108h+arg_0]
0x180001ff5  test    ebx, ebx
0x180001ff7  jz      loc_180002154
0x180001ffd  mov     r8, [rsp+108h+lpvReserved]
0x180002005  mov     edx, edi
0x180002007  mov     rcx, rsi
0x18000200a  call    _CRT_INIT
0x18000200f  mov     ebx, eax
0x180002011  mov     [rsp+108h+var_E8], eax
0x180002015  jmp     short loc_18000202C
0x180002017  xor     ebx, ebx
0x180002019  mov     [rsp+108h+var_E8], ebx
0x18000201d  mov     edi, [rsp+108h+arg_8]
0x180002024  mov     rsi, [rsp+108h+arg_0]
0x18000202c  test    ebx, ebx
0x18000202e  jz      loc_180002154
0x180002034  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000203c  mov     edx, edi; fdwReason
0x18000203e  mov     rcx, rsi; hinstDLL
0x180002041  call    DllMain
0x180002046  mov     ebx, eax
0x180002048  mov     [rsp+108h+var_E8], eax
0x18000204c  jmp     short loc_180002063
0x18000204e  xor     ebx, ebx
0x180002050  mov     [rsp+108h+var_E8], ebx
0x180002054  mov     edi, [rsp+108h+arg_8]
0x18000205b  mov     rsi, [rsp+108h+arg_0]
0x180002063  cmp     edi, 1
0x180002066  jnz     short loc_1800020DF
0x180002068  test    ebx, ebx
0x18000206a  jnz     short loc_1800020DF
0x18000206c  xor     r8d, r8d; lpvReserved
0x18000206f  xor     edx, edx; fdwReason
0x180002071  mov     rcx, rsi; hinstDLL
0x180002074  call    DllMain
0x180002079  jmp     short loc_18000208E
0x18000207b  mov     edi, [rsp+108h+arg_8]
0x180002082  mov     rsi, [rsp+108h+arg_0]
0x18000208a  mov     ebx, [rsp+108h+var_E8]
0x18000208e  xor     r8d, r8d
0x180002091  xor     edx, edx
0x180002093  mov     rcx, rsi
0x180002096  call    _CRT_INIT
0x18000209b  jmp     short loc_1800020B0
0x18000209d  mov     edi, [rsp+108h+arg_8]
0x1800020a4  mov     rsi, [rsp+108h+arg_0]
0x1800020ac  mov     ebx, [rsp+108h+var_E8]
0x1800020b0  mov     rax, cs:_pRawDllMain
0x1800020b7  test    rax, rax
0x1800020ba  jz      short loc_1800020DF
0x1800020bc  xor     r8d, r8d
0x1800020bf  xor     edx, edx
0x1800020c1  mov     rcx, rsi
0x1800020c4  call    cs:__guard_dispatch_icall_fptr
0x1800020ca  jmp     short loc_1800020DF
0x1800020cc  mov     edi, [rsp+108h+arg_8]
0x1800020d3  mov     rsi, [rsp+108h+arg_0]
0x1800020db  mov     ebx, [rsp+108h+var_E8]
0x1800020df  test    edi, edi
0x1800020e1  jz      short loc_1800020E8
0x1800020e3  cmp     edi, 3
0x1800020e6  jnz     short loc_180002154
0x1800020e8  mov     r8, [rsp+108h+lpvReserved]
0x1800020f0  mov     edx, edi
0x1800020f2  mov     rcx, rsi
0x1800020f5  call    _CRT_INIT
0x1800020fa  mov     ebx, eax
0x1800020fc  mov     [rsp+108h+var_E8], eax
0x180002100  jmp     short loc_180002117
0x180002102  xor     ebx, ebx
0x180002104  mov     [rsp+108h+var_E8], ebx
0x180002108  mov     edi, [rsp+108h+arg_8]
0x18000210f  mov     rsi, [rsp+108h+arg_0]
0x180002117  mov     rax, cs:_pRawDllMain
0x18000211e  test    rax, rax
0x180002121  jz      short loc_180002154
0x180002123  cmp     cs:dword_18001C1E4, 0
0x18000212a  jz      short loc_180002154
0x18000212c  mov     r8, [rsp+108h+lpvReserved]
0x180002134  mov     edx, edi
0x180002136  mov     rcx, rsi
0x180002139  call    cs:__guard_dispatch_icall_fptr
0x18000213f  mov     ebx, eax
0x180002141  mov     [rsp+108h+var_E8], eax
0x180002145  jmp     short loc_180002154
0x180002147  xor     ebx, ebx
0x180002149  mov     [rsp+108h+var_E8], ebx
0x18000214d  mov     edi, [rsp+108h+arg_8]
0x180002154  cmp     edi, 1
0x180002157  ja      short loc_180002163
0x180002159  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002163  mov     eax, ebx
0x180002165  add     rsp, 0F0h
0x18000216c  pop     rdi
0x18000216d  pop     rsi
0x18000216e  pop     rbx
0x18000216f  retn
0x180014bf0  push    rbp
0x180014bf2  sub     rsp, 20h
0x180014bf6  mov     rbp, rdx
0x180014bf9  mov     rax, [rcx]
0x180014bfc  mov     edx, [rax]
0x180014bfe  mov     [rbp+0A8h], rcx
0x180014c05  mov     [rbp+28h], edx
0x180014c08  mov     eax, [rbp+28h]
0x180014c0b  cmp     eax, 0E06D7363h
0x180014c10  jnz     short loc_180014C26
0x180014c12  mov     rdx, [rbp+0A8h]
0x180014c19  mov     ecx, [rbp+28h]
0x180014c1c  call    _XcptFilter_0
0x180014c21  mov     [rbp+30h], eax
0x180014c24  jmp     short loc_180014C2D
0x180014c26  mov     dword ptr [rbp+30h], 0
0x180014c2d  mov     eax, [rbp+30h]
0x180014c30  add     rsp, 20h
0x180014c34  pop     rbp
0x180014c35  retn
0x180014c37  push    rbp
0x180014c39  sub     rsp, 20h
0x180014c3d  mov     rbp, rdx
0x180014c40  mov     rax, [rcx]
0x180014c43  mov     edx, [rax]
0x180014c45  mov     [rbp+0B0h], rcx
0x180014c4c  mov     [rbp+38h], edx
0x180014c4f  mov     eax, [rbp+38h]
0x180014c52  cmp     eax, 0E06D7363h
0x180014c57  jnz     short loc_180014C6D
0x180014c59  mov     rdx, [rbp+0B0h]
0x180014c60  mov     ecx, [rbp+38h]
0x180014c63  call    _XcptFilter_0
0x180014c68  mov     [rbp+40h], eax
0x180014c6b  jmp     short loc_180014C74
0x180014c6d  mov     dword ptr [rbp+40h], 0
0x180014c74  mov     eax, [rbp+40h]
0x180014c77  add     rsp, 20h
0x180014c7b  pop     rbp
0x180014c7c  retn
0x180014c7e  push    rbp
0x180014c80  sub     rsp, 20h
0x180014c84  mov     rbp, rdx
0x180014c87  mov     rax, [rcx]
0x180014c8a  mov     edx, [rax]
0x180014c8c  mov     [rbp+0B8h], rcx
0x180014c93  mov     [rbp+48h], edx
0x180014c96  mov     eax, [rbp+48h]
0x180014c99  cmp     eax, 0E06D7363h
0x180014c9e  jnz     short loc_180014CB4
0x180014ca0  mov     rdx, [rbp+0B8h]
0x180014ca7  mov     ecx, [rbp+48h]
0x180014caa  call    _XcptFilter_0
0x180014caf  mov     [rbp+50h], eax
0x180014cb2  jmp     short loc_180014CBB
0x180014cb4  mov     dword ptr [rbp+50h], 0
0x180014cbb  mov     eax, [rbp+50h]
0x180014cbe  add     rsp, 20h
0x180014cc2  pop     rbp
0x180014cc3  retn
0x180014cc5  push    rbp
0x180014cc7  sub     rsp, 20h
0x180014ccb  mov     rbp, rdx
0x180014cce  mov     rax, [rcx]
0x180014cd1  mov     edx, [rax]
0x180014cd3  mov     [rbp+0C0h], rcx
0x180014cda  mov     [rbp+58h], edx
0x180014cdd  mov     eax, [rbp+58h]
0x180014ce0  cmp     eax, 0E06D7363h
0x180014ce5  jnz     short loc_180014CFB
0x180014ce7  mov     rdx, [rbp+0C0h]
0x180014cee  mov     ecx, [rbp+58h]
0x180014cf1  call    _XcptFilter_0
0x180014cf6  mov     [rbp+60h], eax
0x180014cf9  jmp     short loc_180014D02
0x180014cfb  mov     dword ptr [rbp+60h], 0
0x180014d02  mov     eax, [rbp+60h]
0x180014d05  add     rsp, 20h
0x180014d09  pop     rbp
0x180014d0a  retn
0x180014d0c  push    rbp
0x180014d0e  sub     rsp, 20h
0x180014d12  mov     rbp, rdx
0x180014d15  mov     rax, [rcx]
0x180014d18  mov     edx, [rax]
0x180014d1a  mov     [rbp+0C8h], rcx
0x180014d21  mov     [rbp+68h], edx
0x180014d24  mov     eax, [rbp+68h]
0x180014d27  cmp     eax, 0E06D7363h
0x180014d2c  jnz     short loc_180014D42
0x180014d2e  mov     rdx, [rbp+0C8h]
0x180014d35  mov     ecx, [rbp+68h]
0x180014d38  call    _XcptFilter_0
0x180014d3d  mov     [rbp+70h], eax
0x180014d40  jmp     short loc_180014D49
0x180014d42  mov     dword ptr [rbp+70h], 0
0x180014d49  mov     eax, [rbp+70h]
0x180014d4c  add     rsp, 20h
0x180014d50  pop     rbp
0x180014d51  retn
0x180014d53  push    rbp
0x180014d55  sub     rsp, 20h
0x180014d59  mov     rbp, rdx
0x180014d5c  mov     rax, [rcx]
0x180014d5f  mov     edx, [rax]
0x180014d61  mov     [rbp+0D0h], rcx
0x180014d68  mov     [rbp+78h], edx
0x180014d6b  mov     eax, [rbp+78h]
0x180014d6e  cmp     eax, 0E06D7363h
0x180014d73  jnz     short loc_180014D8C
0x180014d75  mov     rdx, [rbp+0D0h]
0x180014d7c  mov     ecx, [rbp+78h]
0x180014d7f  call    _XcptFilter_0
0x180014d84  mov     [rbp+80h], eax
0x180014d8a  jmp     short loc_180014D96
0x180014d8c  mov     dword ptr [rbp+80h], 0
0x180014d96  mov     eax, [rbp+80h]
0x180014d9c  add     rsp, 20h
0x180014da0  pop     rbp
0x180014da1  retn
0x180014da3  push    rbp
0x180014da5  sub     rsp, 20h
0x180014da9  mov     rbp, rdx
0x180014dac  mov     rax, [rcx]
0x180014daf  mov     edx, [rax]
0x180014db1  mov     [rbp+0D8h], rcx
0x180014db8  mov     [rbp+88h], edx
0x180014dbe  mov     eax, [rbp+88h]
0x180014dc4  cmp     eax, 0E06D7363h
0x180014dc9  jnz     short loc_180014DE5
0x180014dcb  mov     rdx, [rbp+0D8h]
0x180014dd2  mov     ecx, [rbp+88h]
0x180014dd8  call    _XcptFilter_0
0x180014ddd  mov     [rbp+90h], eax
0x180014de3  jmp     short loc_180014DEF
0x180014de5  mov     dword ptr [rbp+90h], 0
0x180014def  mov     eax, [rbp+90h]
0x180014df5  add     rsp, 20h
0x180014df9  pop     rbp
0x180014dfa  retn
0x180014dfc  push    rbp
0x180014dfe  sub     rsp, 20h
0x180014e02  mov     rbp, rdx
0x180014e05  mov     rax, [rcx]
0x180014e08  mov     edx, [rax]
0x180014e0a  mov     [rbp+0E0h], rcx
0x180014e11  mov     [rbp+98h], edx
0x180014e17  mov     eax, [rbp+98h]
0x180014e1d  cmp     eax, 0E06D7363h
0x180014e22  jnz     short loc_180014E3E
0x180014e24  mov     rdx, [rbp+0E0h]
0x180014e2b  mov     ecx, [rbp+98h]
0x180014e31  call    _XcptFilter_0
0x180014e36  mov     [rbp+0A0h], eax
0x180014e3c  jmp     short loc_180014E48
0x180014e3e  mov     dword ptr [rbp+0A0h], 0
0x180014e48  mov     eax, [rbp+0A0h]
0x180014e4e  add     rsp, 20h
0x180014e52  pop     rbp
0x180014e53  retn
0x180014e55  push    rbp
0x180014e57  sub     rsp, 20h
0x180014e5b  mov     rbp, rdx
0x180014e5e  cmp     dword ptr [rbp+118h], 1
0x180014e65  ja      short loc_180014E71
0x180014e67  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

# __DllMainCRTStartup

- ea: `0x180001d74`
- end: `0x180001f80`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001d30`

## callees

- `0x180001b00`
- `0x180001d74`
- `0x180002640`
- `0x180007544`
- `0x1800316f0`

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
  if ( (_DWORD)fdwReason || dword_180040480 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180040484 = 1;
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
            if ( dword_180040484 )
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
0x180001d74  mov     [rsp+lpvReserved], r8
0x180001d79  mov     [rsp+arg_8], edx
0x180001d7d  mov     [rsp+arg_0], rcx
0x180001d82  push    rbx
0x180001d83  push    rsi
0x180001d84  push    rdi
0x180001d85  sub     rsp, 0F0h
0x180001d8c  mov     edi, edx
0x180001d8e  mov     rsi, rcx
0x180001d91  mov     ebx, 1
0x180001d96  cmp     edx, ebx
0x180001d98  ja      short loc_180001DA0
0x180001d9a  mov     cs:__native_dllmain_reason, edx
0x180001da0  test    edx, edx
0x180001da2  jnz     short loc_180001DB7
0x180001da4  cmp     cs:dword_180040480, edx
0x180001daa  jnz     short loc_180001DB7
0x180001dac  xor     ebx, ebx
0x180001dae  mov     [rsp+108h+var_E8], ebx
0x180001db2  jmp     loc_180001F64
0x180001db7  lea     eax, [rdx-1]
0x180001dba  cmp     eax, 1
0x180001dbd  ja      loc_180001E44
0x180001dc3  mov     rax, cs:_pRawDllMain
0x180001dca  test    rax, rax
0x180001dcd  jz      short loc_180001E05
0x180001dcf  cmp     edx, 1
0x180001dd2  jnz     short loc_180001DDA
0x180001dd4  mov     cs:dword_180040484, edx
0x180001dda  mov     r8, [rsp+108h+lpvReserved]
0x180001de2  call    cs:__guard_dispatch_icall_fptr
0x180001de8  mov     ebx, eax
0x180001dea  mov     [rsp+108h+var_E8], eax
0x180001dee  jmp     short loc_180001E05
0x180001df0  xor     ebx, ebx
0x180001df2  mov     [rsp+108h+var_E8], ebx
0x180001df6  mov     edi, [rsp+108h+arg_8]
0x180001dfd  mov     rsi, [rsp+108h+arg_0]
0x180001e05  test    ebx, ebx
0x180001e07  jz      loc_180001F64
0x180001e0d  mov     r8, [rsp+108h+lpvReserved]
0x180001e15  mov     edx, edi
0x180001e17  mov     rcx, rsi
0x180001e1a  call    _CRT_INIT
0x180001e1f  mov     ebx, eax
0x180001e21  mov     [rsp+108h+var_E8], eax
0x180001e25  jmp     short loc_180001E3C
0x180001e27  xor     ebx, ebx
0x180001e29  mov     [rsp+108h+var_E8], ebx
0x180001e2d  mov     edi, [rsp+108h+arg_8]
0x180001e34  mov     rsi, [rsp+108h+arg_0]
0x180001e3c  test    ebx, ebx
0x180001e3e  jz      loc_180001F64
0x180001e44  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001e4c  mov     edx, edi; fdwReason
0x180001e4e  mov     rcx, rsi; hinstDLL
0x180001e51  call    DllMain
0x180001e56  mov     ebx, eax
0x180001e58  mov     [rsp+108h+var_E8], eax
0x180001e5c  jmp     short loc_180001E73
0x180001e5e  xor     ebx, ebx
0x180001e60  mov     [rsp+108h+var_E8], ebx
0x180001e64  mov     edi, [rsp+108h+arg_8]
0x180001e6b  mov     rsi, [rsp+108h+arg_0]
0x180001e73  cmp     edi, 1
0x180001e76  jnz     short loc_180001EEF
0x180001e78  test    ebx, ebx
0x180001e7a  jnz     short loc_180001EEF
0x180001e7c  xor     r8d, r8d; lpvReserved
0x180001e7f  xor     edx, edx; fdwReason
0x180001e81  mov     rcx, rsi; hinstDLL
0x180001e84  call    DllMain
0x180001e89  jmp     short loc_180001E9E
0x180001e8b  mov     edi, [rsp+108h+arg_8]
0x180001e92  mov     rsi, [rsp+108h+arg_0]
0x180001e9a  mov     ebx, [rsp+108h+var_E8]
0x180001e9e  xor     r8d, r8d
0x180001ea1  xor     edx, edx
0x180001ea3  mov     rcx, rsi
0x180001ea6  call    _CRT_INIT
0x180001eab  jmp     short loc_180001EC0
0x180001ead  mov     edi, [rsp+108h+arg_8]
0x180001eb4  mov     rsi, [rsp+108h+arg_0]
0x180001ebc  mov     ebx, [rsp+108h+var_E8]
0x180001ec0  mov     rax, cs:_pRawDllMain
0x180001ec7  test    rax, rax
0x180001eca  jz      short loc_180001EEF
0x180001ecc  xor     r8d, r8d
0x180001ecf  xor     edx, edx
0x180001ed1  mov     rcx, rsi
0x180001ed4  call    cs:__guard_dispatch_icall_fptr
0x180001eda  jmp     short loc_180001EEF
0x180001edc  mov     edi, [rsp+108h+arg_8]
0x180001ee3  mov     rsi, [rsp+108h+arg_0]
0x180001eeb  mov     ebx, [rsp+108h+var_E8]
0x180001eef  test    edi, edi
0x180001ef1  jz      short loc_180001EF8
0x180001ef3  cmp     edi, 3
0x180001ef6  jnz     short loc_180001F64
0x180001ef8  mov     r8, [rsp+108h+lpvReserved]
0x180001f00  mov     edx, edi
0x180001f02  mov     rcx, rsi
0x180001f05  call    _CRT_INIT
0x180001f0a  mov     ebx, eax
0x180001f0c  mov     [rsp+108h+var_E8], eax
0x180001f10  jmp     short loc_180001F27
0x180001f12  xor     ebx, ebx
0x180001f14  mov     [rsp+108h+var_E8], ebx
0x180001f18  mov     edi, [rsp+108h+arg_8]
0x180001f1f  mov     rsi, [rsp+108h+arg_0]
0x180001f27  mov     rax, cs:_pRawDllMain
0x180001f2e  test    rax, rax
0x180001f31  jz      short loc_180001F64
0x180001f33  cmp     cs:dword_180040484, 0
0x180001f3a  jz      short loc_180001F64
0x180001f3c  mov     r8, [rsp+108h+lpvReserved]
0x180001f44  mov     edx, edi
0x180001f46  mov     rcx, rsi
0x180001f49  call    cs:__guard_dispatch_icall_fptr
0x180001f4f  mov     ebx, eax
0x180001f51  mov     [rsp+108h+var_E8], eax
0x180001f55  jmp     short loc_180001F64
0x180001f57  xor     ebx, ebx
0x180001f59  mov     [rsp+108h+var_E8], ebx
0x180001f5d  mov     edi, [rsp+108h+arg_8]
0x180001f64  cmp     edi, 1
0x180001f67  ja      short loc_180001F73
0x180001f69  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001f73  mov     eax, ebx
0x180001f75  add     rsp, 0F0h
0x180001f7c  pop     rdi
0x180001f7d  pop     rsi
0x180001f7e  pop     rbx
0x180001f7f  retn
0x180031793  push    rbp
0x180031795  sub     rsp, 20h
0x180031799  mov     rbp, rdx
0x18003179c  mov     rax, [rcx]
0x18003179f  mov     edx, [rax]
0x1800317a1  mov     [rbp+0A8h], rcx
0x1800317a8  mov     [rbp+28h], edx
0x1800317ab  mov     eax, [rbp+28h]
0x1800317ae  cmp     eax, 0E06D7363h
0x1800317b3  jnz     short loc_1800317C9
0x1800317b5  mov     rdx, [rbp+0A8h]
0x1800317bc  mov     ecx, [rbp+28h]
0x1800317bf  call    _XcptFilter_0
0x1800317c4  mov     [rbp+30h], eax
0x1800317c7  jmp     short loc_1800317D0
0x1800317c9  mov     dword ptr [rbp+30h], 0
0x1800317d0  mov     eax, [rbp+30h]
0x1800317d3  add     rsp, 20h
0x1800317d7  pop     rbp
0x1800317d8  retn
0x1800317da  push    rbp
0x1800317dc  sub     rsp, 20h
0x1800317e0  mov     rbp, rdx
0x1800317e3  mov     rax, [rcx]
0x1800317e6  mov     edx, [rax]
0x1800317e8  mov     [rbp+0B0h], rcx
0x1800317ef  mov     [rbp+38h], edx
0x1800317f2  mov     eax, [rbp+38h]
0x1800317f5  cmp     eax, 0E06D7363h
0x1800317fa  jnz     short loc_180031810
0x1800317fc  mov     rdx, [rbp+0B0h]
0x180031803  mov     ecx, [rbp+38h]
0x180031806  call    _XcptFilter_0
0x18003180b  mov     [rbp+40h], eax
0x18003180e  jmp     short loc_180031817
0x180031810  mov     dword ptr [rbp+40h], 0
0x180031817  mov     eax, [rbp+40h]
0x18003181a  add     rsp, 20h
0x18003181e  pop     rbp
0x18003181f  retn
0x180031821  push    rbp
0x180031823  sub     rsp, 20h
0x180031827  mov     rbp, rdx
0x18003182a  mov     rax, [rcx]
0x18003182d  mov     edx, [rax]
0x18003182f  mov     [rbp+0B8h], rcx
0x180031836  mov     [rbp+48h], edx
0x180031839  mov     eax, [rbp+48h]
0x18003183c  cmp     eax, 0E06D7363h
0x180031841  jnz     short loc_180031857
0x180031843  mov     rdx, [rbp+0B8h]
0x18003184a  mov     ecx, [rbp+48h]
0x18003184d  call    _XcptFilter_0
0x180031852  mov     [rbp+50h], eax
0x180031855  jmp     short loc_18003185E
0x180031857  mov     dword ptr [rbp+50h], 0
0x18003185e  mov     eax, [rbp+50h]
0x180031861  add     rsp, 20h
0x180031865  pop     rbp
0x180031866  retn
0x180031868  push    rbp
0x18003186a  sub     rsp, 20h
0x18003186e  mov     rbp, rdx
0x180031871  mov     rax, [rcx]
0x180031874  mov     edx, [rax]
0x180031876  mov     [rbp+0C0h], rcx
0x18003187d  mov     [rbp+58h], edx
0x180031880  mov     eax, [rbp+58h]
0x180031883  cmp     eax, 0E06D7363h
0x180031888  jnz     short loc_18003189E
0x18003188a  mov     rdx, [rbp+0C0h]
0x180031891  mov     ecx, [rbp+58h]
0x180031894  call    _XcptFilter_0
0x180031899  mov     [rbp+60h], eax
0x18003189c  jmp     short loc_1800318A5
0x18003189e  mov     dword ptr [rbp+60h], 0
0x1800318a5  mov     eax, [rbp+60h]
0x1800318a8  add     rsp, 20h
0x1800318ac  pop     rbp
0x1800318ad  retn
0x1800318af  push    rbp
0x1800318b1  sub     rsp, 20h
0x1800318b5  mov     rbp, rdx
0x1800318b8  mov     rax, [rcx]
0x1800318bb  mov     edx, [rax]
0x1800318bd  mov     [rbp+0C8h], rcx
0x1800318c4  mov     [rbp+68h], edx
0x1800318c7  mov     eax, [rbp+68h]
0x1800318ca  cmp     eax, 0E06D7363h
0x1800318cf  jnz     short loc_1800318E5
0x1800318d1  mov     rdx, [rbp+0C8h]
0x1800318d8  mov     ecx, [rbp+68h]
0x1800318db  call    _XcptFilter_0
0x1800318e0  mov     [rbp+70h], eax
0x1800318e3  jmp     short loc_1800318EC
0x1800318e5  mov     dword ptr [rbp+70h], 0
0x1800318ec  mov     eax, [rbp+70h]
0x1800318ef  add     rsp, 20h
0x1800318f3  pop     rbp
0x1800318f4  retn
0x1800318f6  push    rbp
0x1800318f8  sub     rsp, 20h
0x1800318fc  mov     rbp, rdx
0x1800318ff  mov     rax, [rcx]
0x180031902  mov     edx, [rax]
0x180031904  mov     [rbp+0D0h], rcx
0x18003190b  mov     [rbp+78h], edx
0x18003190e  mov     eax, [rbp+78h]
0x180031911  cmp     eax, 0E06D7363h
0x180031916  jnz     short loc_18003192F
0x180031918  mov     rdx, [rbp+0D0h]
0x18003191f  mov     ecx, [rbp+78h]
0x180031922  call    _XcptFilter_0
0x180031927  mov     [rbp+80h], eax
0x18003192d  jmp     short loc_180031939
0x18003192f  mov     dword ptr [rbp+80h], 0
0x180031939  mov     eax, [rbp+80h]
0x18003193f  add     rsp, 20h
0x180031943  pop     rbp
0x180031944  retn
0x180031946  push    rbp
0x180031948  sub     rsp, 20h
0x18003194c  mov     rbp, rdx
0x18003194f  mov     rax, [rcx]
0x180031952  mov     edx, [rax]
0x180031954  mov     [rbp+0D8h], rcx
0x18003195b  mov     [rbp+88h], edx
0x180031961  mov     eax, [rbp+88h]
0x180031967  cmp     eax, 0E06D7363h
0x18003196c  jnz     short loc_180031988
0x18003196e  mov     rdx, [rbp+0D8h]
0x180031975  mov     ecx, [rbp+88h]
0x18003197b  call    _XcptFilter_0
0x180031980  mov     [rbp+90h], eax
0x180031986  jmp     short loc_180031992
0x180031988  mov     dword ptr [rbp+90h], 0
0x180031992  mov     eax, [rbp+90h]
0x180031998  add     rsp, 20h
0x18003199c  pop     rbp
0x18003199d  retn
0x18003199f  push    rbp
0x1800319a1  sub     rsp, 20h
0x1800319a5  mov     rbp, rdx
0x1800319a8  mov     rax, [rcx]
0x1800319ab  mov     edx, [rax]
0x1800319ad  mov     [rbp+0E0h], rcx
0x1800319b4  mov     [rbp+98h], edx
0x1800319ba  mov     eax, [rbp+98h]
0x1800319c0  cmp     eax, 0E06D7363h
0x1800319c5  jnz     short loc_1800319E1
0x1800319c7  mov     rdx, [rbp+0E0h]
0x1800319ce  mov     ecx, [rbp+98h]
0x1800319d4  call    _XcptFilter_0
0x1800319d9  mov     [rbp+0A0h], eax
0x1800319df  jmp     short loc_1800319EB
0x1800319e1  mov     dword ptr [rbp+0A0h], 0
0x1800319eb  mov     eax, [rbp+0A0h]
0x1800319f1  add     rsp, 20h
0x1800319f5  pop     rbp
0x1800319f6  retn
0x1800319f8  push    rbp
0x1800319fa  sub     rsp, 20h
0x1800319fe  mov     rbp, rdx
0x180031a01  cmp     dword ptr [rbp+118h], 1
0x180031a08  ja      short loc_180031A14
0x180031a0a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

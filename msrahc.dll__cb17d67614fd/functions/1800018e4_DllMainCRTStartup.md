# __DllMainCRTStartup

- ea: `0x1800018e4`
- end: `0x180001af0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800018a0`

## callees

- `0x180001670`
- `0x1800018e4`
- `0x1800021de`
- `0x18000c5dc`
- `0x18001a650`

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
  if ( (_DWORD)fdwReason || dword_1800278CC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800278D0 = 1;
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
            if ( dword_1800278D0 )
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
0x1800018e4  mov     [rsp+lpvReserved], r8
0x1800018e9  mov     [rsp+arg_8], edx
0x1800018ed  mov     [rsp+arg_0], rcx
0x1800018f2  push    rbx
0x1800018f3  push    rsi
0x1800018f4  push    rdi
0x1800018f5  sub     rsp, 0F0h
0x1800018fc  mov     edi, edx
0x1800018fe  mov     rsi, rcx
0x180001901  mov     ebx, 1
0x180001906  cmp     edx, ebx
0x180001908  ja      short loc_180001910
0x18000190a  mov     cs:__native_dllmain_reason, edx
0x180001910  test    edx, edx
0x180001912  jnz     short loc_180001927
0x180001914  cmp     cs:dword_1800278CC, edx
0x18000191a  jnz     short loc_180001927
0x18000191c  xor     ebx, ebx
0x18000191e  mov     [rsp+108h+var_E8], ebx
0x180001922  jmp     loc_180001AD4
0x180001927  lea     eax, [rdx-1]
0x18000192a  cmp     eax, 1
0x18000192d  ja      loc_1800019B4
0x180001933  mov     rax, cs:_pRawDllMain
0x18000193a  test    rax, rax
0x18000193d  jz      short loc_180001975
0x18000193f  cmp     edx, 1
0x180001942  jnz     short loc_18000194A
0x180001944  mov     cs:dword_1800278D0, edx
0x18000194a  mov     r8, [rsp+108h+lpvReserved]
0x180001952  call    cs:__guard_dispatch_icall_fptr
0x180001958  mov     ebx, eax
0x18000195a  mov     [rsp+108h+var_E8], eax
0x18000195e  jmp     short loc_180001975
0x180001960  xor     ebx, ebx
0x180001962  mov     [rsp+108h+var_E8], ebx
0x180001966  mov     edi, [rsp+108h+arg_8]
0x18000196d  mov     rsi, [rsp+108h+arg_0]
0x180001975  test    ebx, ebx
0x180001977  jz      loc_180001AD4
0x18000197d  mov     r8, [rsp+108h+lpvReserved]
0x180001985  mov     edx, edi
0x180001987  mov     rcx, rsi
0x18000198a  call    _CRT_INIT
0x18000198f  mov     ebx, eax
0x180001991  mov     [rsp+108h+var_E8], eax
0x180001995  jmp     short loc_1800019AC
0x180001997  xor     ebx, ebx
0x180001999  mov     [rsp+108h+var_E8], ebx
0x18000199d  mov     edi, [rsp+108h+arg_8]
0x1800019a4  mov     rsi, [rsp+108h+arg_0]
0x1800019ac  test    ebx, ebx
0x1800019ae  jz      loc_180001AD4
0x1800019b4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800019bc  mov     edx, edi; fdwReason
0x1800019be  mov     rcx, rsi; hinstDLL
0x1800019c1  call    DllMain
0x1800019c6  mov     ebx, eax
0x1800019c8  mov     [rsp+108h+var_E8], eax
0x1800019cc  jmp     short loc_1800019E3
0x1800019ce  xor     ebx, ebx
0x1800019d0  mov     [rsp+108h+var_E8], ebx
0x1800019d4  mov     edi, [rsp+108h+arg_8]
0x1800019db  mov     rsi, [rsp+108h+arg_0]
0x1800019e3  cmp     edi, 1
0x1800019e6  jnz     short loc_180001A5F
0x1800019e8  test    ebx, ebx
0x1800019ea  jnz     short loc_180001A5F
0x1800019ec  xor     r8d, r8d; lpvReserved
0x1800019ef  xor     edx, edx; fdwReason
0x1800019f1  mov     rcx, rsi; hinstDLL
0x1800019f4  call    DllMain
0x1800019f9  jmp     short loc_180001A0E
0x1800019fb  mov     edi, [rsp+108h+arg_8]
0x180001a02  mov     rsi, [rsp+108h+arg_0]
0x180001a0a  mov     ebx, [rsp+108h+var_E8]
0x180001a0e  xor     r8d, r8d
0x180001a11  xor     edx, edx
0x180001a13  mov     rcx, rsi
0x180001a16  call    _CRT_INIT
0x180001a1b  jmp     short loc_180001A30
0x180001a1d  mov     edi, [rsp+108h+arg_8]
0x180001a24  mov     rsi, [rsp+108h+arg_0]
0x180001a2c  mov     ebx, [rsp+108h+var_E8]
0x180001a30  mov     rax, cs:_pRawDllMain
0x180001a37  test    rax, rax
0x180001a3a  jz      short loc_180001A5F
0x180001a3c  xor     r8d, r8d
0x180001a3f  xor     edx, edx
0x180001a41  mov     rcx, rsi
0x180001a44  call    cs:__guard_dispatch_icall_fptr
0x180001a4a  jmp     short loc_180001A5F
0x180001a4c  mov     edi, [rsp+108h+arg_8]
0x180001a53  mov     rsi, [rsp+108h+arg_0]
0x180001a5b  mov     ebx, [rsp+108h+var_E8]
0x180001a5f  test    edi, edi
0x180001a61  jz      short loc_180001A68
0x180001a63  cmp     edi, 3
0x180001a66  jnz     short loc_180001AD4
0x180001a68  mov     r8, [rsp+108h+lpvReserved]
0x180001a70  mov     edx, edi
0x180001a72  mov     rcx, rsi
0x180001a75  call    _CRT_INIT
0x180001a7a  mov     ebx, eax
0x180001a7c  mov     [rsp+108h+var_E8], eax
0x180001a80  jmp     short loc_180001A97
0x180001a82  xor     ebx, ebx
0x180001a84  mov     [rsp+108h+var_E8], ebx
0x180001a88  mov     edi, [rsp+108h+arg_8]
0x180001a8f  mov     rsi, [rsp+108h+arg_0]
0x180001a97  mov     rax, cs:_pRawDllMain
0x180001a9e  test    rax, rax
0x180001aa1  jz      short loc_180001AD4
0x180001aa3  cmp     cs:dword_1800278D0, 0
0x180001aaa  jz      short loc_180001AD4
0x180001aac  mov     r8, [rsp+108h+lpvReserved]
0x180001ab4  mov     edx, edi
0x180001ab6  mov     rcx, rsi
0x180001ab9  call    cs:__guard_dispatch_icall_fptr
0x180001abf  mov     ebx, eax
0x180001ac1  mov     [rsp+108h+var_E8], eax
0x180001ac5  jmp     short loc_180001AD4
0x180001ac7  xor     ebx, ebx
0x180001ac9  mov     [rsp+108h+var_E8], ebx
0x180001acd  mov     edi, [rsp+108h+arg_8]
0x180001ad4  cmp     edi, 1
0x180001ad7  ja      short loc_180001AE3
0x180001ad9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ae3  mov     eax, ebx
0x180001ae5  add     rsp, 0F0h
0x180001aec  pop     rdi
0x180001aed  pop     rsi
0x180001aee  pop     rbx
0x180001aef  retn
0x18001a6f3  push    rbp
0x18001a6f5  sub     rsp, 20h
0x18001a6f9  mov     rbp, rdx
0x18001a6fc  mov     rax, [rcx]
0x18001a6ff  mov     edx, [rax]
0x18001a701  mov     [rbp+0A8h], rcx
0x18001a708  mov     [rbp+28h], edx
0x18001a70b  mov     eax, [rbp+28h]
0x18001a70e  cmp     eax, 0E06D7363h
0x18001a713  jnz     short loc_18001A729
0x18001a715  mov     rdx, [rbp+0A8h]
0x18001a71c  mov     ecx, [rbp+28h]
0x18001a71f  call    _XcptFilter_0
0x18001a724  mov     [rbp+30h], eax
0x18001a727  jmp     short loc_18001A730
0x18001a729  mov     dword ptr [rbp+30h], 0
0x18001a730  mov     eax, [rbp+30h]
0x18001a733  add     rsp, 20h
0x18001a737  pop     rbp
0x18001a738  retn
0x18001a73a  push    rbp
0x18001a73c  sub     rsp, 20h
0x18001a740  mov     rbp, rdx
0x18001a743  mov     rax, [rcx]
0x18001a746  mov     edx, [rax]
0x18001a748  mov     [rbp+0B0h], rcx
0x18001a74f  mov     [rbp+38h], edx
0x18001a752  mov     eax, [rbp+38h]
0x18001a755  cmp     eax, 0E06D7363h
0x18001a75a  jnz     short loc_18001A770
0x18001a75c  mov     rdx, [rbp+0B0h]
0x18001a763  mov     ecx, [rbp+38h]
0x18001a766  call    _XcptFilter_0
0x18001a76b  mov     [rbp+40h], eax
0x18001a76e  jmp     short loc_18001A777
0x18001a770  mov     dword ptr [rbp+40h], 0
0x18001a777  mov     eax, [rbp+40h]
0x18001a77a  add     rsp, 20h
0x18001a77e  pop     rbp
0x18001a77f  retn
0x18001a781  push    rbp
0x18001a783  sub     rsp, 20h
0x18001a787  mov     rbp, rdx
0x18001a78a  mov     rax, [rcx]
0x18001a78d  mov     edx, [rax]
0x18001a78f  mov     [rbp+0B8h], rcx
0x18001a796  mov     [rbp+48h], edx
0x18001a799  mov     eax, [rbp+48h]
0x18001a79c  cmp     eax, 0E06D7363h
0x18001a7a1  jnz     short loc_18001A7B7
0x18001a7a3  mov     rdx, [rbp+0B8h]
0x18001a7aa  mov     ecx, [rbp+48h]
0x18001a7ad  call    _XcptFilter_0
0x18001a7b2  mov     [rbp+50h], eax
0x18001a7b5  jmp     short loc_18001A7BE
0x18001a7b7  mov     dword ptr [rbp+50h], 0
0x18001a7be  mov     eax, [rbp+50h]
0x18001a7c1  add     rsp, 20h
0x18001a7c5  pop     rbp
0x18001a7c6  retn
0x18001a7c8  push    rbp
0x18001a7ca  sub     rsp, 20h
0x18001a7ce  mov     rbp, rdx
0x18001a7d1  mov     rax, [rcx]
0x18001a7d4  mov     edx, [rax]
0x18001a7d6  mov     [rbp+0C0h], rcx
0x18001a7dd  mov     [rbp+58h], edx
0x18001a7e0  mov     eax, [rbp+58h]
0x18001a7e3  cmp     eax, 0E06D7363h
0x18001a7e8  jnz     short loc_18001A7FE
0x18001a7ea  mov     rdx, [rbp+0C0h]
0x18001a7f1  mov     ecx, [rbp+58h]
0x18001a7f4  call    _XcptFilter_0
0x18001a7f9  mov     [rbp+60h], eax
0x18001a7fc  jmp     short loc_18001A805
0x18001a7fe  mov     dword ptr [rbp+60h], 0
0x18001a805  mov     eax, [rbp+60h]
0x18001a808  add     rsp, 20h
0x18001a80c  pop     rbp
0x18001a80d  retn
0x18001a80f  push    rbp
0x18001a811  sub     rsp, 20h
0x18001a815  mov     rbp, rdx
0x18001a818  mov     rax, [rcx]
0x18001a81b  mov     edx, [rax]
0x18001a81d  mov     [rbp+0C8h], rcx
0x18001a824  mov     [rbp+68h], edx
0x18001a827  mov     eax, [rbp+68h]
0x18001a82a  cmp     eax, 0E06D7363h
0x18001a82f  jnz     short loc_18001A845
0x18001a831  mov     rdx, [rbp+0C8h]
0x18001a838  mov     ecx, [rbp+68h]
0x18001a83b  call    _XcptFilter_0
0x18001a840  mov     [rbp+70h], eax
0x18001a843  jmp     short loc_18001A84C
0x18001a845  mov     dword ptr [rbp+70h], 0
0x18001a84c  mov     eax, [rbp+70h]
0x18001a84f  add     rsp, 20h
0x18001a853  pop     rbp
0x18001a854  retn
0x18001a856  push    rbp
0x18001a858  sub     rsp, 20h
0x18001a85c  mov     rbp, rdx
0x18001a85f  mov     rax, [rcx]
0x18001a862  mov     edx, [rax]
0x18001a864  mov     [rbp+0D0h], rcx
0x18001a86b  mov     [rbp+78h], edx
0x18001a86e  mov     eax, [rbp+78h]
0x18001a871  cmp     eax, 0E06D7363h
0x18001a876  jnz     short loc_18001A88F
0x18001a878  mov     rdx, [rbp+0D0h]
0x18001a87f  mov     ecx, [rbp+78h]
0x18001a882  call    _XcptFilter_0
0x18001a887  mov     [rbp+80h], eax
0x18001a88d  jmp     short loc_18001A899
0x18001a88f  mov     dword ptr [rbp+80h], 0
0x18001a899  mov     eax, [rbp+80h]
0x18001a89f  add     rsp, 20h
0x18001a8a3  pop     rbp
0x18001a8a4  retn
0x18001a8a6  push    rbp
0x18001a8a8  sub     rsp, 20h
0x18001a8ac  mov     rbp, rdx
0x18001a8af  mov     rax, [rcx]
0x18001a8b2  mov     edx, [rax]
0x18001a8b4  mov     [rbp+0D8h], rcx
0x18001a8bb  mov     [rbp+88h], edx
0x18001a8c1  mov     eax, [rbp+88h]
0x18001a8c7  cmp     eax, 0E06D7363h
0x18001a8cc  jnz     short loc_18001A8E8
0x18001a8ce  mov     rdx, [rbp+0D8h]
0x18001a8d5  mov     ecx, [rbp+88h]
0x18001a8db  call    _XcptFilter_0
0x18001a8e0  mov     [rbp+90h], eax
0x18001a8e6  jmp     short loc_18001A8F2
0x18001a8e8  mov     dword ptr [rbp+90h], 0
0x18001a8f2  mov     eax, [rbp+90h]
0x18001a8f8  add     rsp, 20h
0x18001a8fc  pop     rbp
0x18001a8fd  retn
0x18001a8ff  push    rbp
0x18001a901  sub     rsp, 20h
0x18001a905  mov     rbp, rdx
0x18001a908  mov     rax, [rcx]
0x18001a90b  mov     edx, [rax]
0x18001a90d  mov     [rbp+0E0h], rcx
0x18001a914  mov     [rbp+98h], edx
0x18001a91a  mov     eax, [rbp+98h]
0x18001a920  cmp     eax, 0E06D7363h
0x18001a925  jnz     short loc_18001A941
0x18001a927  mov     rdx, [rbp+0E0h]
0x18001a92e  mov     ecx, [rbp+98h]
0x18001a934  call    _XcptFilter_0
0x18001a939  mov     [rbp+0A0h], eax
0x18001a93f  jmp     short loc_18001A94B
0x18001a941  mov     dword ptr [rbp+0A0h], 0
0x18001a94b  mov     eax, [rbp+0A0h]
0x18001a951  add     rsp, 20h
0x18001a955  pop     rbp
0x18001a956  retn
0x18001a958  push    rbp
0x18001a95a  sub     rsp, 20h
0x18001a95e  mov     rbp, rdx
0x18001a961  cmp     dword ptr [rbp+118h], 1
0x18001a968  ja      short loc_18001A974
0x18001a96a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

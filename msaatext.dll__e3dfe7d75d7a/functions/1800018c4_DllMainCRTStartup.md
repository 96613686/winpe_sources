# __DllMainCRTStartup

- ea: `0x1800018c4`
- end: `0x180001ad0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001880`

## callees

- `0x180001650`
- `0x1800018c4`
- `0x180001fa6`
- `0x180012718`
- `0x180012bb0`

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
  if ( (_DWORD)fdwReason || dword_18002453C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180024540 = 1;
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
            if ( dword_180024540 )
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
0x1800018c4  mov     [rsp+lpvReserved], r8
0x1800018c9  mov     [rsp+arg_8], edx
0x1800018cd  mov     [rsp+arg_0], rcx
0x1800018d2  push    rbx
0x1800018d3  push    rsi
0x1800018d4  push    rdi
0x1800018d5  sub     rsp, 0F0h
0x1800018dc  mov     edi, edx
0x1800018de  mov     rsi, rcx
0x1800018e1  mov     ebx, 1
0x1800018e6  cmp     edx, ebx
0x1800018e8  ja      short loc_1800018F0
0x1800018ea  mov     cs:__native_dllmain_reason, edx
0x1800018f0  test    edx, edx
0x1800018f2  jnz     short loc_180001907
0x1800018f4  cmp     cs:dword_18002453C, edx
0x1800018fa  jnz     short loc_180001907
0x1800018fc  xor     ebx, ebx
0x1800018fe  mov     [rsp+108h+var_E8], ebx
0x180001902  jmp     loc_180001AB4
0x180001907  lea     eax, [rdx-1]
0x18000190a  cmp     eax, 1
0x18000190d  ja      loc_180001994
0x180001913  mov     rax, cs:_pRawDllMain
0x18000191a  test    rax, rax
0x18000191d  jz      short loc_180001955
0x18000191f  cmp     edx, 1
0x180001922  jnz     short loc_18000192A
0x180001924  mov     cs:dword_180024540, edx
0x18000192a  mov     r8, [rsp+108h+lpvReserved]
0x180001932  call    cs:__guard_dispatch_icall_fptr
0x180001938  mov     ebx, eax
0x18000193a  mov     [rsp+108h+var_E8], eax
0x18000193e  jmp     short loc_180001955
0x180001940  xor     ebx, ebx
0x180001942  mov     [rsp+108h+var_E8], ebx
0x180001946  mov     edi, [rsp+108h+arg_8]
0x18000194d  mov     rsi, [rsp+108h+arg_0]
0x180001955  test    ebx, ebx
0x180001957  jz      loc_180001AB4
0x18000195d  mov     r8, [rsp+108h+lpvReserved]
0x180001965  mov     edx, edi
0x180001967  mov     rcx, rsi
0x18000196a  call    _CRT_INIT
0x18000196f  mov     ebx, eax
0x180001971  mov     [rsp+108h+var_E8], eax
0x180001975  jmp     short loc_18000198C
0x180001977  xor     ebx, ebx
0x180001979  mov     [rsp+108h+var_E8], ebx
0x18000197d  mov     edi, [rsp+108h+arg_8]
0x180001984  mov     rsi, [rsp+108h+arg_0]
0x18000198c  test    ebx, ebx
0x18000198e  jz      loc_180001AB4
0x180001994  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000199c  mov     edx, edi; fdwReason
0x18000199e  mov     rcx, rsi; hinstDLL
0x1800019a1  call    DllMain
0x1800019a6  mov     ebx, eax
0x1800019a8  mov     [rsp+108h+var_E8], eax
0x1800019ac  jmp     short loc_1800019C3
0x1800019ae  xor     ebx, ebx
0x1800019b0  mov     [rsp+108h+var_E8], ebx
0x1800019b4  mov     edi, [rsp+108h+arg_8]
0x1800019bb  mov     rsi, [rsp+108h+arg_0]
0x1800019c3  cmp     edi, 1
0x1800019c6  jnz     short loc_180001A3F
0x1800019c8  test    ebx, ebx
0x1800019ca  jnz     short loc_180001A3F
0x1800019cc  xor     r8d, r8d; lpvReserved
0x1800019cf  xor     edx, edx; fdwReason
0x1800019d1  mov     rcx, rsi; hinstDLL
0x1800019d4  call    DllMain
0x1800019d9  jmp     short loc_1800019EE
0x1800019db  mov     edi, [rsp+108h+arg_8]
0x1800019e2  mov     rsi, [rsp+108h+arg_0]
0x1800019ea  mov     ebx, [rsp+108h+var_E8]
0x1800019ee  xor     r8d, r8d
0x1800019f1  xor     edx, edx
0x1800019f3  mov     rcx, rsi
0x1800019f6  call    _CRT_INIT
0x1800019fb  jmp     short loc_180001A10
0x1800019fd  mov     edi, [rsp+108h+arg_8]
0x180001a04  mov     rsi, [rsp+108h+arg_0]
0x180001a0c  mov     ebx, [rsp+108h+var_E8]
0x180001a10  mov     rax, cs:_pRawDllMain
0x180001a17  test    rax, rax
0x180001a1a  jz      short loc_180001A3F
0x180001a1c  xor     r8d, r8d
0x180001a1f  xor     edx, edx
0x180001a21  mov     rcx, rsi
0x180001a24  call    cs:__guard_dispatch_icall_fptr
0x180001a2a  jmp     short loc_180001A3F
0x180001a2c  mov     edi, [rsp+108h+arg_8]
0x180001a33  mov     rsi, [rsp+108h+arg_0]
0x180001a3b  mov     ebx, [rsp+108h+var_E8]
0x180001a3f  test    edi, edi
0x180001a41  jz      short loc_180001A48
0x180001a43  cmp     edi, 3
0x180001a46  jnz     short loc_180001AB4
0x180001a48  mov     r8, [rsp+108h+lpvReserved]
0x180001a50  mov     edx, edi
0x180001a52  mov     rcx, rsi
0x180001a55  call    _CRT_INIT
0x180001a5a  mov     ebx, eax
0x180001a5c  mov     [rsp+108h+var_E8], eax
0x180001a60  jmp     short loc_180001A77
0x180001a62  xor     ebx, ebx
0x180001a64  mov     [rsp+108h+var_E8], ebx
0x180001a68  mov     edi, [rsp+108h+arg_8]
0x180001a6f  mov     rsi, [rsp+108h+arg_0]
0x180001a77  mov     rax, cs:_pRawDllMain
0x180001a7e  test    rax, rax
0x180001a81  jz      short loc_180001AB4
0x180001a83  cmp     cs:dword_180024540, 0
0x180001a8a  jz      short loc_180001AB4
0x180001a8c  mov     r8, [rsp+108h+lpvReserved]
0x180001a94  mov     edx, edi
0x180001a96  mov     rcx, rsi
0x180001a99  call    cs:__guard_dispatch_icall_fptr
0x180001a9f  mov     ebx, eax
0x180001aa1  mov     [rsp+108h+var_E8], eax
0x180001aa5  jmp     short loc_180001AB4
0x180001aa7  xor     ebx, ebx
0x180001aa9  mov     [rsp+108h+var_E8], ebx
0x180001aad  mov     edi, [rsp+108h+arg_8]
0x180001ab4  cmp     edi, 1
0x180001ab7  ja      short loc_180001AC3
0x180001ab9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ac3  mov     eax, ebx
0x180001ac5  add     rsp, 0F0h
0x180001acc  pop     rdi
0x180001acd  pop     rsi
0x180001ace  pop     rbx
0x180001acf  retn
0x180012c53  push    rbp
0x180012c55  sub     rsp, 20h
0x180012c59  mov     rbp, rdx
0x180012c5c  mov     rax, [rcx]
0x180012c5f  mov     edx, [rax]
0x180012c61  mov     [rbp+0A8h], rcx
0x180012c68  mov     [rbp+28h], edx
0x180012c6b  mov     eax, [rbp+28h]
0x180012c6e  cmp     eax, 0E06D7363h
0x180012c73  jnz     short loc_180012C89
0x180012c75  mov     rdx, [rbp+0A8h]
0x180012c7c  mov     ecx, [rbp+28h]
0x180012c7f  call    _XcptFilter_0
0x180012c84  mov     [rbp+30h], eax
0x180012c87  jmp     short loc_180012C90
0x180012c89  mov     dword ptr [rbp+30h], 0
0x180012c90  mov     eax, [rbp+30h]
0x180012c93  add     rsp, 20h
0x180012c97  pop     rbp
0x180012c98  retn
0x180012c9a  push    rbp
0x180012c9c  sub     rsp, 20h
0x180012ca0  mov     rbp, rdx
0x180012ca3  mov     rax, [rcx]
0x180012ca6  mov     edx, [rax]
0x180012ca8  mov     [rbp+0B0h], rcx
0x180012caf  mov     [rbp+38h], edx
0x180012cb2  mov     eax, [rbp+38h]
0x180012cb5  cmp     eax, 0E06D7363h
0x180012cba  jnz     short loc_180012CD0
0x180012cbc  mov     rdx, [rbp+0B0h]
0x180012cc3  mov     ecx, [rbp+38h]
0x180012cc6  call    _XcptFilter_0
0x180012ccb  mov     [rbp+40h], eax
0x180012cce  jmp     short loc_180012CD7
0x180012cd0  mov     dword ptr [rbp+40h], 0
0x180012cd7  mov     eax, [rbp+40h]
0x180012cda  add     rsp, 20h
0x180012cde  pop     rbp
0x180012cdf  retn
0x180012ce1  push    rbp
0x180012ce3  sub     rsp, 20h
0x180012ce7  mov     rbp, rdx
0x180012cea  mov     rax, [rcx]
0x180012ced  mov     edx, [rax]
0x180012cef  mov     [rbp+0B8h], rcx
0x180012cf6  mov     [rbp+48h], edx
0x180012cf9  mov     eax, [rbp+48h]
0x180012cfc  cmp     eax, 0E06D7363h
0x180012d01  jnz     short loc_180012D17
0x180012d03  mov     rdx, [rbp+0B8h]
0x180012d0a  mov     ecx, [rbp+48h]
0x180012d0d  call    _XcptFilter_0
0x180012d12  mov     [rbp+50h], eax
0x180012d15  jmp     short loc_180012D1E
0x180012d17  mov     dword ptr [rbp+50h], 0
0x180012d1e  mov     eax, [rbp+50h]
0x180012d21  add     rsp, 20h
0x180012d25  pop     rbp
0x180012d26  retn
0x180012d28  push    rbp
0x180012d2a  sub     rsp, 20h
0x180012d2e  mov     rbp, rdx
0x180012d31  mov     rax, [rcx]
0x180012d34  mov     edx, [rax]
0x180012d36  mov     [rbp+0C0h], rcx
0x180012d3d  mov     [rbp+58h], edx
0x180012d40  mov     eax, [rbp+58h]
0x180012d43  cmp     eax, 0E06D7363h
0x180012d48  jnz     short loc_180012D5E
0x180012d4a  mov     rdx, [rbp+0C0h]
0x180012d51  mov     ecx, [rbp+58h]
0x180012d54  call    _XcptFilter_0
0x180012d59  mov     [rbp+60h], eax
0x180012d5c  jmp     short loc_180012D65
0x180012d5e  mov     dword ptr [rbp+60h], 0
0x180012d65  mov     eax, [rbp+60h]
0x180012d68  add     rsp, 20h
0x180012d6c  pop     rbp
0x180012d6d  retn
0x180012d6f  push    rbp
0x180012d71  sub     rsp, 20h
0x180012d75  mov     rbp, rdx
0x180012d78  mov     rax, [rcx]
0x180012d7b  mov     edx, [rax]
0x180012d7d  mov     [rbp+0C8h], rcx
0x180012d84  mov     [rbp+68h], edx
0x180012d87  mov     eax, [rbp+68h]
0x180012d8a  cmp     eax, 0E06D7363h
0x180012d8f  jnz     short loc_180012DA5
0x180012d91  mov     rdx, [rbp+0C8h]
0x180012d98  mov     ecx, [rbp+68h]
0x180012d9b  call    _XcptFilter_0
0x180012da0  mov     [rbp+70h], eax
0x180012da3  jmp     short loc_180012DAC
0x180012da5  mov     dword ptr [rbp+70h], 0
0x180012dac  mov     eax, [rbp+70h]
0x180012daf  add     rsp, 20h
0x180012db3  pop     rbp
0x180012db4  retn
0x180012db6  push    rbp
0x180012db8  sub     rsp, 20h
0x180012dbc  mov     rbp, rdx
0x180012dbf  mov     rax, [rcx]
0x180012dc2  mov     edx, [rax]
0x180012dc4  mov     [rbp+0D0h], rcx
0x180012dcb  mov     [rbp+78h], edx
0x180012dce  mov     eax, [rbp+78h]
0x180012dd1  cmp     eax, 0E06D7363h
0x180012dd6  jnz     short loc_180012DEF
0x180012dd8  mov     rdx, [rbp+0D0h]
0x180012ddf  mov     ecx, [rbp+78h]
0x180012de2  call    _XcptFilter_0
0x180012de7  mov     [rbp+80h], eax
0x180012ded  jmp     short loc_180012DF9
0x180012def  mov     dword ptr [rbp+80h], 0
0x180012df9  mov     eax, [rbp+80h]
0x180012dff  add     rsp, 20h
0x180012e03  pop     rbp
0x180012e04  retn
0x180012e06  push    rbp
0x180012e08  sub     rsp, 20h
0x180012e0c  mov     rbp, rdx
0x180012e0f  mov     rax, [rcx]
0x180012e12  mov     edx, [rax]
0x180012e14  mov     [rbp+0D8h], rcx
0x180012e1b  mov     [rbp+88h], edx
0x180012e21  mov     eax, [rbp+88h]
0x180012e27  cmp     eax, 0E06D7363h
0x180012e2c  jnz     short loc_180012E48
0x180012e2e  mov     rdx, [rbp+0D8h]
0x180012e35  mov     ecx, [rbp+88h]
0x180012e3b  call    _XcptFilter_0
0x180012e40  mov     [rbp+90h], eax
0x180012e46  jmp     short loc_180012E52
0x180012e48  mov     dword ptr [rbp+90h], 0
0x180012e52  mov     eax, [rbp+90h]
0x180012e58  add     rsp, 20h
0x180012e5c  pop     rbp
0x180012e5d  retn
0x180012e5f  push    rbp
0x180012e61  sub     rsp, 20h
0x180012e65  mov     rbp, rdx
0x180012e68  mov     rax, [rcx]
0x180012e6b  mov     edx, [rax]
0x180012e6d  mov     [rbp+0E0h], rcx
0x180012e74  mov     [rbp+98h], edx
0x180012e7a  mov     eax, [rbp+98h]
0x180012e80  cmp     eax, 0E06D7363h
0x180012e85  jnz     short loc_180012EA1
0x180012e87  mov     rdx, [rbp+0E0h]
0x180012e8e  mov     ecx, [rbp+98h]
0x180012e94  call    _XcptFilter_0
0x180012e99  mov     [rbp+0A0h], eax
0x180012e9f  jmp     short loc_180012EAB
0x180012ea1  mov     dword ptr [rbp+0A0h], 0
0x180012eab  mov     eax, [rbp+0A0h]
0x180012eb1  add     rsp, 20h
0x180012eb5  pop     rbp
0x180012eb6  retn
0x180012eb8  push    rbp
0x180012eba  sub     rsp, 20h
0x180012ebe  mov     rbp, rdx
0x180012ec1  cmp     dword ptr [rbp+118h], 1
0x180012ec8  ja      short loc_180012ED4
0x180012eca  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

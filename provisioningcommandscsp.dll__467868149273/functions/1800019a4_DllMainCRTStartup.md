# __DllMainCRTStartup

- ea: `0x1800019a4`
- end: `0x180001bb0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001960`

## callees

- `0x180001730`
- `0x1800019a4`
- `0x180001dde`
- `0x180006300`
- `0x18000cd30`

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
0x1800019a4  mov     [rsp+lpvReserved], r8
0x1800019a9  mov     [rsp+arg_8], edx
0x1800019ad  mov     [rsp+arg_0], rcx
0x1800019b2  push    rbx
0x1800019b3  push    rsi
0x1800019b4  push    rdi
0x1800019b5  sub     rsp, 0F0h
0x1800019bc  mov     edi, edx
0x1800019be  mov     rsi, rcx
0x1800019c1  mov     ebx, 1
0x1800019c6  cmp     edx, ebx
0x1800019c8  ja      short loc_1800019D0
0x1800019ca  mov     cs:__native_dllmain_reason, edx
0x1800019d0  test    edx, edx
0x1800019d2  jnz     short loc_1800019E7
0x1800019d4  cmp     cs:dword_180014444, edx
0x1800019da  jnz     short loc_1800019E7
0x1800019dc  xor     ebx, ebx
0x1800019de  mov     [rsp+108h+var_E8], ebx
0x1800019e2  jmp     loc_180001B94
0x1800019e7  lea     eax, [rdx-1]
0x1800019ea  cmp     eax, 1
0x1800019ed  ja      loc_180001A74
0x1800019f3  mov     rax, cs:_pRawDllMain
0x1800019fa  test    rax, rax
0x1800019fd  jz      short loc_180001A35
0x1800019ff  cmp     edx, 1
0x180001a02  jnz     short loc_180001A0A
0x180001a04  mov     cs:dword_180014448, edx
0x180001a0a  mov     r8, [rsp+108h+lpvReserved]
0x180001a12  call    cs:__guard_dispatch_icall_fptr
0x180001a18  mov     ebx, eax
0x180001a1a  mov     [rsp+108h+var_E8], eax
0x180001a1e  jmp     short loc_180001A35
0x180001a20  xor     ebx, ebx
0x180001a22  mov     [rsp+108h+var_E8], ebx
0x180001a26  mov     edi, [rsp+108h+arg_8]
0x180001a2d  mov     rsi, [rsp+108h+arg_0]
0x180001a35  test    ebx, ebx
0x180001a37  jz      loc_180001B94
0x180001a3d  mov     r8, [rsp+108h+lpvReserved]
0x180001a45  mov     edx, edi
0x180001a47  mov     rcx, rsi
0x180001a4a  call    _CRT_INIT
0x180001a4f  mov     ebx, eax
0x180001a51  mov     [rsp+108h+var_E8], eax
0x180001a55  jmp     short loc_180001A6C
0x180001a57  xor     ebx, ebx
0x180001a59  mov     [rsp+108h+var_E8], ebx
0x180001a5d  mov     edi, [rsp+108h+arg_8]
0x180001a64  mov     rsi, [rsp+108h+arg_0]
0x180001a6c  test    ebx, ebx
0x180001a6e  jz      loc_180001B94
0x180001a74  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001a7c  mov     edx, edi; fdwReason
0x180001a7e  mov     rcx, rsi; hinstDLL
0x180001a81  call    DllMain
0x180001a86  mov     ebx, eax
0x180001a88  mov     [rsp+108h+var_E8], eax
0x180001a8c  jmp     short loc_180001AA3
0x180001a8e  xor     ebx, ebx
0x180001a90  mov     [rsp+108h+var_E8], ebx
0x180001a94  mov     edi, [rsp+108h+arg_8]
0x180001a9b  mov     rsi, [rsp+108h+arg_0]
0x180001aa3  cmp     edi, 1
0x180001aa6  jnz     short loc_180001B1F
0x180001aa8  test    ebx, ebx
0x180001aaa  jnz     short loc_180001B1F
0x180001aac  xor     r8d, r8d; lpvReserved
0x180001aaf  xor     edx, edx; fdwReason
0x180001ab1  mov     rcx, rsi; hinstDLL
0x180001ab4  call    DllMain
0x180001ab9  jmp     short loc_180001ACE
0x180001abb  mov     edi, [rsp+108h+arg_8]
0x180001ac2  mov     rsi, [rsp+108h+arg_0]
0x180001aca  mov     ebx, [rsp+108h+var_E8]
0x180001ace  xor     r8d, r8d
0x180001ad1  xor     edx, edx
0x180001ad3  mov     rcx, rsi
0x180001ad6  call    _CRT_INIT
0x180001adb  jmp     short loc_180001AF0
0x180001add  mov     edi, [rsp+108h+arg_8]
0x180001ae4  mov     rsi, [rsp+108h+arg_0]
0x180001aec  mov     ebx, [rsp+108h+var_E8]
0x180001af0  mov     rax, cs:_pRawDllMain
0x180001af7  test    rax, rax
0x180001afa  jz      short loc_180001B1F
0x180001afc  xor     r8d, r8d
0x180001aff  xor     edx, edx
0x180001b01  mov     rcx, rsi
0x180001b04  call    cs:__guard_dispatch_icall_fptr
0x180001b0a  jmp     short loc_180001B1F
0x180001b0c  mov     edi, [rsp+108h+arg_8]
0x180001b13  mov     rsi, [rsp+108h+arg_0]
0x180001b1b  mov     ebx, [rsp+108h+var_E8]
0x180001b1f  test    edi, edi
0x180001b21  jz      short loc_180001B28
0x180001b23  cmp     edi, 3
0x180001b26  jnz     short loc_180001B94
0x180001b28  mov     r8, [rsp+108h+lpvReserved]
0x180001b30  mov     edx, edi
0x180001b32  mov     rcx, rsi
0x180001b35  call    _CRT_INIT
0x180001b3a  mov     ebx, eax
0x180001b3c  mov     [rsp+108h+var_E8], eax
0x180001b40  jmp     short loc_180001B57
0x180001b42  xor     ebx, ebx
0x180001b44  mov     [rsp+108h+var_E8], ebx
0x180001b48  mov     edi, [rsp+108h+arg_8]
0x180001b4f  mov     rsi, [rsp+108h+arg_0]
0x180001b57  mov     rax, cs:_pRawDllMain
0x180001b5e  test    rax, rax
0x180001b61  jz      short loc_180001B94
0x180001b63  cmp     cs:dword_180014448, 0
0x180001b6a  jz      short loc_180001B94
0x180001b6c  mov     r8, [rsp+108h+lpvReserved]
0x180001b74  mov     edx, edi
0x180001b76  mov     rcx, rsi
0x180001b79  call    cs:__guard_dispatch_icall_fptr
0x180001b7f  mov     ebx, eax
0x180001b81  mov     [rsp+108h+var_E8], eax
0x180001b85  jmp     short loc_180001B94
0x180001b87  xor     ebx, ebx
0x180001b89  mov     [rsp+108h+var_E8], ebx
0x180001b8d  mov     edi, [rsp+108h+arg_8]
0x180001b94  cmp     edi, 1
0x180001b97  ja      short loc_180001BA3
0x180001b99  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ba3  mov     eax, ebx
0x180001ba5  add     rsp, 0F0h
0x180001bac  pop     rdi
0x180001bad  pop     rsi
0x180001bae  pop     rbx
0x180001baf  retn
0x18000cdd3  push    rbp
0x18000cdd5  sub     rsp, 20h
0x18000cdd9  mov     rbp, rdx
0x18000cddc  mov     rax, [rcx]
0x18000cddf  mov     edx, [rax]
0x18000cde1  mov     [rbp+0A8h], rcx
0x18000cde8  mov     [rbp+28h], edx
0x18000cdeb  mov     eax, [rbp+28h]
0x18000cdee  cmp     eax, 0E06D7363h
0x18000cdf3  jnz     short loc_18000CE09
0x18000cdf5  mov     rdx, [rbp+0A8h]
0x18000cdfc  mov     ecx, [rbp+28h]
0x18000cdff  call    _XcptFilter_0
0x18000ce04  mov     [rbp+30h], eax
0x18000ce07  jmp     short loc_18000CE10
0x18000ce09  mov     dword ptr [rbp+30h], 0
0x18000ce10  mov     eax, [rbp+30h]
0x18000ce13  add     rsp, 20h
0x18000ce17  pop     rbp
0x18000ce18  retn
0x18000ce1a  push    rbp
0x18000ce1c  sub     rsp, 20h
0x18000ce20  mov     rbp, rdx
0x18000ce23  mov     rax, [rcx]
0x18000ce26  mov     edx, [rax]
0x18000ce28  mov     [rbp+0B0h], rcx
0x18000ce2f  mov     [rbp+38h], edx
0x18000ce32  mov     eax, [rbp+38h]
0x18000ce35  cmp     eax, 0E06D7363h
0x18000ce3a  jnz     short loc_18000CE50
0x18000ce3c  mov     rdx, [rbp+0B0h]
0x18000ce43  mov     ecx, [rbp+38h]
0x18000ce46  call    _XcptFilter_0
0x18000ce4b  mov     [rbp+40h], eax
0x18000ce4e  jmp     short loc_18000CE57
0x18000ce50  mov     dword ptr [rbp+40h], 0
0x18000ce57  mov     eax, [rbp+40h]
0x18000ce5a  add     rsp, 20h
0x18000ce5e  pop     rbp
0x18000ce5f  retn
0x18000ce61  push    rbp
0x18000ce63  sub     rsp, 20h
0x18000ce67  mov     rbp, rdx
0x18000ce6a  mov     rax, [rcx]
0x18000ce6d  mov     edx, [rax]
0x18000ce6f  mov     [rbp+0B8h], rcx
0x18000ce76  mov     [rbp+48h], edx
0x18000ce79  mov     eax, [rbp+48h]
0x18000ce7c  cmp     eax, 0E06D7363h
0x18000ce81  jnz     short loc_18000CE97
0x18000ce83  mov     rdx, [rbp+0B8h]
0x18000ce8a  mov     ecx, [rbp+48h]
0x18000ce8d  call    _XcptFilter_0
0x18000ce92  mov     [rbp+50h], eax
0x18000ce95  jmp     short loc_18000CE9E
0x18000ce97  mov     dword ptr [rbp+50h], 0
0x18000ce9e  mov     eax, [rbp+50h]
0x18000cea1  add     rsp, 20h
0x18000cea5  pop     rbp
0x18000cea6  retn
0x18000cea8  push    rbp
0x18000ceaa  sub     rsp, 20h
0x18000ceae  mov     rbp, rdx
0x18000ceb1  mov     rax, [rcx]
0x18000ceb4  mov     edx, [rax]
0x18000ceb6  mov     [rbp+0C0h], rcx
0x18000cebd  mov     [rbp+58h], edx
0x18000cec0  mov     eax, [rbp+58h]
0x18000cec3  cmp     eax, 0E06D7363h
0x18000cec8  jnz     short loc_18000CEDE
0x18000ceca  mov     rdx, [rbp+0C0h]
0x18000ced1  mov     ecx, [rbp+58h]
0x18000ced4  call    _XcptFilter_0
0x18000ced9  mov     [rbp+60h], eax
0x18000cedc  jmp     short loc_18000CEE5
0x18000cede  mov     dword ptr [rbp+60h], 0
0x18000cee5  mov     eax, [rbp+60h]
0x18000cee8  add     rsp, 20h
0x18000ceec  pop     rbp
0x18000ceed  retn
0x18000ceef  push    rbp
0x18000cef1  sub     rsp, 20h
0x18000cef5  mov     rbp, rdx
0x18000cef8  mov     rax, [rcx]
0x18000cefb  mov     edx, [rax]
0x18000cefd  mov     [rbp+0C8h], rcx
0x18000cf04  mov     [rbp+68h], edx
0x18000cf07  mov     eax, [rbp+68h]
0x18000cf0a  cmp     eax, 0E06D7363h
0x18000cf0f  jnz     short loc_18000CF25
0x18000cf11  mov     rdx, [rbp+0C8h]
0x18000cf18  mov     ecx, [rbp+68h]
0x18000cf1b  call    _XcptFilter_0
0x18000cf20  mov     [rbp+70h], eax
0x18000cf23  jmp     short loc_18000CF2C
0x18000cf25  mov     dword ptr [rbp+70h], 0
0x18000cf2c  mov     eax, [rbp+70h]
0x18000cf2f  add     rsp, 20h
0x18000cf33  pop     rbp
0x18000cf34  retn
0x18000cf36  push    rbp
0x18000cf38  sub     rsp, 20h
0x18000cf3c  mov     rbp, rdx
0x18000cf3f  mov     rax, [rcx]
0x18000cf42  mov     edx, [rax]
0x18000cf44  mov     [rbp+0D0h], rcx
0x18000cf4b  mov     [rbp+78h], edx
0x18000cf4e  mov     eax, [rbp+78h]
0x18000cf51  cmp     eax, 0E06D7363h
0x18000cf56  jnz     short loc_18000CF6F
0x18000cf58  mov     rdx, [rbp+0D0h]
0x18000cf5f  mov     ecx, [rbp+78h]
0x18000cf62  call    _XcptFilter_0
0x18000cf67  mov     [rbp+80h], eax
0x18000cf6d  jmp     short loc_18000CF79
0x18000cf6f  mov     dword ptr [rbp+80h], 0
0x18000cf79  mov     eax, [rbp+80h]
0x18000cf7f  add     rsp, 20h
0x18000cf83  pop     rbp
0x18000cf84  retn
0x18000cf86  push    rbp
0x18000cf88  sub     rsp, 20h
0x18000cf8c  mov     rbp, rdx
0x18000cf8f  mov     rax, [rcx]
0x18000cf92  mov     edx, [rax]
0x18000cf94  mov     [rbp+0D8h], rcx
0x18000cf9b  mov     [rbp+88h], edx
0x18000cfa1  mov     eax, [rbp+88h]
0x18000cfa7  cmp     eax, 0E06D7363h
0x18000cfac  jnz     short loc_18000CFC8
0x18000cfae  mov     rdx, [rbp+0D8h]
0x18000cfb5  mov     ecx, [rbp+88h]
0x18000cfbb  call    _XcptFilter_0
0x18000cfc0  mov     [rbp+90h], eax
0x18000cfc6  jmp     short loc_18000CFD2
0x18000cfc8  mov     dword ptr [rbp+90h], 0
0x18000cfd2  mov     eax, [rbp+90h]
0x18000cfd8  add     rsp, 20h
0x18000cfdc  pop     rbp
0x18000cfdd  retn
0x18000cfdf  push    rbp
0x18000cfe1  sub     rsp, 20h
0x18000cfe5  mov     rbp, rdx
0x18000cfe8  mov     rax, [rcx]
0x18000cfeb  mov     edx, [rax]
0x18000cfed  mov     [rbp+0E0h], rcx
0x18000cff4  mov     [rbp+98h], edx
0x18000cffa  mov     eax, [rbp+98h]
0x18000d000  cmp     eax, 0E06D7363h
0x18000d005  jnz     short loc_18000D021
0x18000d007  mov     rdx, [rbp+0E0h]
0x18000d00e  mov     ecx, [rbp+98h]
0x18000d014  call    _XcptFilter_0
0x18000d019  mov     [rbp+0A0h], eax
0x18000d01f  jmp     short loc_18000D02B
0x18000d021  mov     dword ptr [rbp+0A0h], 0
0x18000d02b  mov     eax, [rbp+0A0h]
0x18000d031  add     rsp, 20h
0x18000d035  pop     rbp
0x18000d036  retn
0x18000d038  push    rbp
0x18000d03a  sub     rsp, 20h
0x18000d03e  mov     rbp, rdx
0x18000d041  cmp     dword ptr [rbp+118h], 1
0x18000d048  ja      short loc_18000D054
0x18000d04a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

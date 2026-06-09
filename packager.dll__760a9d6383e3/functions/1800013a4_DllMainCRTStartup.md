# __DllMainCRTStartup

- ea: `0x1800013a4`
- end: `0x1800015b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001360`

## callees

- `0x180001130`
- `0x1800013a4`
- `0x180001886`
- `0x18000a9e4`
- `0x18000cc30`

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
  if ( (_DWORD)fdwReason || dword_180014160 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180014164 = 1;
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
            if ( dword_180014164 )
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
0x1800013a4  mov     [rsp+lpvReserved], r8
0x1800013a9  mov     [rsp+arg_8], edx
0x1800013ad  mov     [rsp+arg_0], rcx
0x1800013b2  push    rbx
0x1800013b3  push    rsi
0x1800013b4  push    rdi
0x1800013b5  sub     rsp, 0F0h
0x1800013bc  mov     edi, edx
0x1800013be  mov     rsi, rcx
0x1800013c1  mov     ebx, 1
0x1800013c6  cmp     edx, ebx
0x1800013c8  ja      short loc_1800013D0
0x1800013ca  mov     cs:__native_dllmain_reason, edx
0x1800013d0  test    edx, edx
0x1800013d2  jnz     short loc_1800013E7
0x1800013d4  cmp     cs:dword_180014160, edx
0x1800013da  jnz     short loc_1800013E7
0x1800013dc  xor     ebx, ebx
0x1800013de  mov     [rsp+108h+var_E8], ebx
0x1800013e2  jmp     loc_180001594
0x1800013e7  lea     eax, [rdx-1]
0x1800013ea  cmp     eax, 1
0x1800013ed  ja      loc_180001474
0x1800013f3  mov     rax, cs:_pRawDllMain
0x1800013fa  test    rax, rax
0x1800013fd  jz      short loc_180001435
0x1800013ff  cmp     edx, 1
0x180001402  jnz     short loc_18000140A
0x180001404  mov     cs:dword_180014164, edx
0x18000140a  mov     r8, [rsp+108h+lpvReserved]
0x180001412  call    cs:__guard_dispatch_icall_fptr
0x180001418  mov     ebx, eax
0x18000141a  mov     [rsp+108h+var_E8], eax
0x18000141e  jmp     short loc_180001435
0x180001420  xor     ebx, ebx
0x180001422  mov     [rsp+108h+var_E8], ebx
0x180001426  mov     edi, [rsp+108h+arg_8]
0x18000142d  mov     rsi, [rsp+108h+arg_0]
0x180001435  test    ebx, ebx
0x180001437  jz      loc_180001594
0x18000143d  mov     r8, [rsp+108h+lpvReserved]
0x180001445  mov     edx, edi
0x180001447  mov     rcx, rsi
0x18000144a  call    _CRT_INIT
0x18000144f  mov     ebx, eax
0x180001451  mov     [rsp+108h+var_E8], eax
0x180001455  jmp     short loc_18000146C
0x180001457  xor     ebx, ebx
0x180001459  mov     [rsp+108h+var_E8], ebx
0x18000145d  mov     edi, [rsp+108h+arg_8]
0x180001464  mov     rsi, [rsp+108h+arg_0]
0x18000146c  test    ebx, ebx
0x18000146e  jz      loc_180001594
0x180001474  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000147c  mov     edx, edi; fdwReason
0x18000147e  mov     rcx, rsi; hinstDLL
0x180001481  call    DllMain
0x180001486  mov     ebx, eax
0x180001488  mov     [rsp+108h+var_E8], eax
0x18000148c  jmp     short loc_1800014A3
0x18000148e  xor     ebx, ebx
0x180001490  mov     [rsp+108h+var_E8], ebx
0x180001494  mov     edi, [rsp+108h+arg_8]
0x18000149b  mov     rsi, [rsp+108h+arg_0]
0x1800014a3  cmp     edi, 1
0x1800014a6  jnz     short loc_18000151F
0x1800014a8  test    ebx, ebx
0x1800014aa  jnz     short loc_18000151F
0x1800014ac  xor     r8d, r8d; lpvReserved
0x1800014af  xor     edx, edx; fdwReason
0x1800014b1  mov     rcx, rsi; hinstDLL
0x1800014b4  call    DllMain
0x1800014b9  jmp     short loc_1800014CE
0x1800014bb  mov     edi, [rsp+108h+arg_8]
0x1800014c2  mov     rsi, [rsp+108h+arg_0]
0x1800014ca  mov     ebx, [rsp+108h+var_E8]
0x1800014ce  xor     r8d, r8d
0x1800014d1  xor     edx, edx
0x1800014d3  mov     rcx, rsi
0x1800014d6  call    _CRT_INIT
0x1800014db  jmp     short loc_1800014F0
0x1800014dd  mov     edi, [rsp+108h+arg_8]
0x1800014e4  mov     rsi, [rsp+108h+arg_0]
0x1800014ec  mov     ebx, [rsp+108h+var_E8]
0x1800014f0  mov     rax, cs:_pRawDllMain
0x1800014f7  test    rax, rax
0x1800014fa  jz      short loc_18000151F
0x1800014fc  xor     r8d, r8d
0x1800014ff  xor     edx, edx
0x180001501  mov     rcx, rsi
0x180001504  call    cs:__guard_dispatch_icall_fptr
0x18000150a  jmp     short loc_18000151F
0x18000150c  mov     edi, [rsp+108h+arg_8]
0x180001513  mov     rsi, [rsp+108h+arg_0]
0x18000151b  mov     ebx, [rsp+108h+var_E8]
0x18000151f  test    edi, edi
0x180001521  jz      short loc_180001528
0x180001523  cmp     edi, 3
0x180001526  jnz     short loc_180001594
0x180001528  mov     r8, [rsp+108h+lpvReserved]
0x180001530  mov     edx, edi
0x180001532  mov     rcx, rsi
0x180001535  call    _CRT_INIT
0x18000153a  mov     ebx, eax
0x18000153c  mov     [rsp+108h+var_E8], eax
0x180001540  jmp     short loc_180001557
0x180001542  xor     ebx, ebx
0x180001544  mov     [rsp+108h+var_E8], ebx
0x180001548  mov     edi, [rsp+108h+arg_8]
0x18000154f  mov     rsi, [rsp+108h+arg_0]
0x180001557  mov     rax, cs:_pRawDllMain
0x18000155e  test    rax, rax
0x180001561  jz      short loc_180001594
0x180001563  cmp     cs:dword_180014164, 0
0x18000156a  jz      short loc_180001594
0x18000156c  mov     r8, [rsp+108h+lpvReserved]
0x180001574  mov     edx, edi
0x180001576  mov     rcx, rsi
0x180001579  call    cs:__guard_dispatch_icall_fptr
0x18000157f  mov     ebx, eax
0x180001581  mov     [rsp+108h+var_E8], eax
0x180001585  jmp     short loc_180001594
0x180001587  xor     ebx, ebx
0x180001589  mov     [rsp+108h+var_E8], ebx
0x18000158d  mov     edi, [rsp+108h+arg_8]
0x180001594  cmp     edi, 1
0x180001597  ja      short loc_1800015A3
0x180001599  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800015a3  mov     eax, ebx
0x1800015a5  add     rsp, 0F0h
0x1800015ac  pop     rdi
0x1800015ad  pop     rsi
0x1800015ae  pop     rbx
0x1800015af  retn
0x18000cd00  push    rbp
0x18000cd02  sub     rsp, 20h
0x18000cd06  mov     rbp, rdx
0x18000cd09  mov     rax, [rcx]
0x18000cd0c  mov     edx, [rax]
0x18000cd0e  mov     [rbp+0A8h], rcx
0x18000cd15  mov     [rbp+28h], edx
0x18000cd18  mov     eax, [rbp+28h]
0x18000cd1b  cmp     eax, 0E06D7363h
0x18000cd20  jnz     short loc_18000CD36
0x18000cd22  mov     rdx, [rbp+0A8h]
0x18000cd29  mov     ecx, [rbp+28h]
0x18000cd2c  call    _XcptFilter_0
0x18000cd31  mov     [rbp+30h], eax
0x18000cd34  jmp     short loc_18000CD3D
0x18000cd36  mov     dword ptr [rbp+30h], 0
0x18000cd3d  mov     eax, [rbp+30h]
0x18000cd40  add     rsp, 20h
0x18000cd44  pop     rbp
0x18000cd45  retn
0x18000cd47  push    rbp
0x18000cd49  sub     rsp, 20h
0x18000cd4d  mov     rbp, rdx
0x18000cd50  mov     rax, [rcx]
0x18000cd53  mov     edx, [rax]
0x18000cd55  mov     [rbp+0B0h], rcx
0x18000cd5c  mov     [rbp+38h], edx
0x18000cd5f  mov     eax, [rbp+38h]
0x18000cd62  cmp     eax, 0E06D7363h
0x18000cd67  jnz     short loc_18000CD7D
0x18000cd69  mov     rdx, [rbp+0B0h]
0x18000cd70  mov     ecx, [rbp+38h]
0x18000cd73  call    _XcptFilter_0
0x18000cd78  mov     [rbp+40h], eax
0x18000cd7b  jmp     short loc_18000CD84
0x18000cd7d  mov     dword ptr [rbp+40h], 0
0x18000cd84  mov     eax, [rbp+40h]
0x18000cd87  add     rsp, 20h
0x18000cd8b  pop     rbp
0x18000cd8c  retn
0x18000cd8e  push    rbp
0x18000cd90  sub     rsp, 20h
0x18000cd94  mov     rbp, rdx
0x18000cd97  mov     rax, [rcx]
0x18000cd9a  mov     edx, [rax]
0x18000cd9c  mov     [rbp+0B8h], rcx
0x18000cda3  mov     [rbp+48h], edx
0x18000cda6  mov     eax, [rbp+48h]
0x18000cda9  cmp     eax, 0E06D7363h
0x18000cdae  jnz     short loc_18000CDC4
0x18000cdb0  mov     rdx, [rbp+0B8h]
0x18000cdb7  mov     ecx, [rbp+48h]
0x18000cdba  call    _XcptFilter_0
0x18000cdbf  mov     [rbp+50h], eax
0x18000cdc2  jmp     short loc_18000CDCB
0x18000cdc4  mov     dword ptr [rbp+50h], 0
0x18000cdcb  mov     eax, [rbp+50h]
0x18000cdce  add     rsp, 20h
0x18000cdd2  pop     rbp
0x18000cdd3  retn
0x18000cdd5  push    rbp
0x18000cdd7  sub     rsp, 20h
0x18000cddb  mov     rbp, rdx
0x18000cdde  mov     rax, [rcx]
0x18000cde1  mov     edx, [rax]
0x18000cde3  mov     [rbp+0C0h], rcx
0x18000cdea  mov     [rbp+58h], edx
0x18000cded  mov     eax, [rbp+58h]
0x18000cdf0  cmp     eax, 0E06D7363h
0x18000cdf5  jnz     short loc_18000CE0B
0x18000cdf7  mov     rdx, [rbp+0C0h]
0x18000cdfe  mov     ecx, [rbp+58h]
0x18000ce01  call    _XcptFilter_0
0x18000ce06  mov     [rbp+60h], eax
0x18000ce09  jmp     short loc_18000CE12
0x18000ce0b  mov     dword ptr [rbp+60h], 0
0x18000ce12  mov     eax, [rbp+60h]
0x18000ce15  add     rsp, 20h
0x18000ce19  pop     rbp
0x18000ce1a  retn
0x18000ce1c  push    rbp
0x18000ce1e  sub     rsp, 20h
0x18000ce22  mov     rbp, rdx
0x18000ce25  mov     rax, [rcx]
0x18000ce28  mov     edx, [rax]
0x18000ce2a  mov     [rbp+0C8h], rcx
0x18000ce31  mov     [rbp+68h], edx
0x18000ce34  mov     eax, [rbp+68h]
0x18000ce37  cmp     eax, 0E06D7363h
0x18000ce3c  jnz     short loc_18000CE52
0x18000ce3e  mov     rdx, [rbp+0C8h]
0x18000ce45  mov     ecx, [rbp+68h]
0x18000ce48  call    _XcptFilter_0
0x18000ce4d  mov     [rbp+70h], eax
0x18000ce50  jmp     short loc_18000CE59
0x18000ce52  mov     dword ptr [rbp+70h], 0
0x18000ce59  mov     eax, [rbp+70h]
0x18000ce5c  add     rsp, 20h
0x18000ce60  pop     rbp
0x18000ce61  retn
0x18000ce63  push    rbp
0x18000ce65  sub     rsp, 20h
0x18000ce69  mov     rbp, rdx
0x18000ce6c  mov     rax, [rcx]
0x18000ce6f  mov     edx, [rax]
0x18000ce71  mov     [rbp+0D0h], rcx
0x18000ce78  mov     [rbp+78h], edx
0x18000ce7b  mov     eax, [rbp+78h]
0x18000ce7e  cmp     eax, 0E06D7363h
0x18000ce83  jnz     short loc_18000CE9C
0x18000ce85  mov     rdx, [rbp+0D0h]
0x18000ce8c  mov     ecx, [rbp+78h]
0x18000ce8f  call    _XcptFilter_0
0x18000ce94  mov     [rbp+80h], eax
0x18000ce9a  jmp     short loc_18000CEA6
0x18000ce9c  mov     dword ptr [rbp+80h], 0
0x18000cea6  mov     eax, [rbp+80h]
0x18000ceac  add     rsp, 20h
0x18000ceb0  pop     rbp
0x18000ceb1  retn
0x18000ceb3  push    rbp
0x18000ceb5  sub     rsp, 20h
0x18000ceb9  mov     rbp, rdx
0x18000cebc  mov     rax, [rcx]
0x18000cebf  mov     edx, [rax]
0x18000cec1  mov     [rbp+0D8h], rcx
0x18000cec8  mov     [rbp+88h], edx
0x18000cece  mov     eax, [rbp+88h]
0x18000ced4  cmp     eax, 0E06D7363h
0x18000ced9  jnz     short loc_18000CEF5
0x18000cedb  mov     rdx, [rbp+0D8h]
0x18000cee2  mov     ecx, [rbp+88h]
0x18000cee8  call    _XcptFilter_0
0x18000ceed  mov     [rbp+90h], eax
0x18000cef3  jmp     short loc_18000CEFF
0x18000cef5  mov     dword ptr [rbp+90h], 0
0x18000ceff  mov     eax, [rbp+90h]
0x18000cf05  add     rsp, 20h
0x18000cf09  pop     rbp
0x18000cf0a  retn
0x18000cf0c  push    rbp
0x18000cf0e  sub     rsp, 20h
0x18000cf12  mov     rbp, rdx
0x18000cf15  mov     rax, [rcx]
0x18000cf18  mov     edx, [rax]
0x18000cf1a  mov     [rbp+0E0h], rcx
0x18000cf21  mov     [rbp+98h], edx
0x18000cf27  mov     eax, [rbp+98h]
0x18000cf2d  cmp     eax, 0E06D7363h
0x18000cf32  jnz     short loc_18000CF4E
0x18000cf34  mov     rdx, [rbp+0E0h]
0x18000cf3b  mov     ecx, [rbp+98h]
0x18000cf41  call    _XcptFilter_0
0x18000cf46  mov     [rbp+0A0h], eax
0x18000cf4c  jmp     short loc_18000CF58
0x18000cf4e  mov     dword ptr [rbp+0A0h], 0
0x18000cf58  mov     eax, [rbp+0A0h]
0x18000cf5e  add     rsp, 20h
0x18000cf62  pop     rbp
0x18000cf63  retn
0x18000cf65  push    rbp
0x18000cf67  sub     rsp, 20h
0x18000cf6b  mov     rbp, rdx
0x18000cf6e  cmp     dword ptr [rbp+118h], 1
0x18000cf75  ja      short loc_18000CF81
0x18000cf77  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

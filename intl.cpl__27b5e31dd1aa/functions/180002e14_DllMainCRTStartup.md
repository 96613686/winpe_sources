# __DllMainCRTStartup

- ea: `0x180002e14`
- end: `0x180003020`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002dd0`

## callees

- `0x180002ba0`
- `0x180002e14`
- `0x18000355e`
- `0x180017a14`
- `0x18002a1c0`

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
  if ( (_DWORD)fdwReason || dword_18003A91C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003A920 = 1;
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
            if ( dword_18003A920 )
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
0x180002e14  mov     [rsp+lpvReserved], r8
0x180002e19  mov     [rsp+arg_8], edx
0x180002e1d  mov     [rsp+arg_0], rcx
0x180002e22  push    rbx
0x180002e23  push    rsi
0x180002e24  push    rdi
0x180002e25  sub     rsp, 0F0h
0x180002e2c  mov     edi, edx
0x180002e2e  mov     rsi, rcx
0x180002e31  mov     ebx, 1
0x180002e36  cmp     edx, ebx
0x180002e38  ja      short loc_180002E40
0x180002e3a  mov     cs:__native_dllmain_reason, edx
0x180002e40  test    edx, edx
0x180002e42  jnz     short loc_180002E57
0x180002e44  cmp     cs:dword_18003A91C, edx
0x180002e4a  jnz     short loc_180002E57
0x180002e4c  xor     ebx, ebx
0x180002e4e  mov     [rsp+108h+var_E8], ebx
0x180002e52  jmp     loc_180003004
0x180002e57  lea     eax, [rdx-1]
0x180002e5a  cmp     eax, 1
0x180002e5d  ja      loc_180002EE4
0x180002e63  mov     rax, cs:_pRawDllMain
0x180002e6a  test    rax, rax
0x180002e6d  jz      short loc_180002EA5
0x180002e6f  cmp     edx, 1
0x180002e72  jnz     short loc_180002E7A
0x180002e74  mov     cs:dword_18003A920, edx
0x180002e7a  mov     r8, [rsp+108h+lpvReserved]
0x180002e82  call    cs:__guard_dispatch_icall_fptr
0x180002e88  mov     ebx, eax
0x180002e8a  mov     [rsp+108h+var_E8], eax
0x180002e8e  jmp     short loc_180002EA5
0x180002e90  xor     ebx, ebx
0x180002e92  mov     [rsp+108h+var_E8], ebx
0x180002e96  mov     edi, [rsp+108h+arg_8]
0x180002e9d  mov     rsi, [rsp+108h+arg_0]
0x180002ea5  test    ebx, ebx
0x180002ea7  jz      loc_180003004
0x180002ead  mov     r8, [rsp+108h+lpvReserved]
0x180002eb5  mov     edx, edi
0x180002eb7  mov     rcx, rsi
0x180002eba  call    _CRT_INIT
0x180002ebf  mov     ebx, eax
0x180002ec1  mov     [rsp+108h+var_E8], eax
0x180002ec5  jmp     short loc_180002EDC
0x180002ec7  xor     ebx, ebx
0x180002ec9  mov     [rsp+108h+var_E8], ebx
0x180002ecd  mov     edi, [rsp+108h+arg_8]
0x180002ed4  mov     rsi, [rsp+108h+arg_0]
0x180002edc  test    ebx, ebx
0x180002ede  jz      loc_180003004
0x180002ee4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180002eec  mov     edx, edi; fdwReason
0x180002eee  mov     rcx, rsi; hinstDLL
0x180002ef1  call    DllMain
0x180002ef6  mov     ebx, eax
0x180002ef8  mov     [rsp+108h+var_E8], eax
0x180002efc  jmp     short loc_180002F13
0x180002efe  xor     ebx, ebx
0x180002f00  mov     [rsp+108h+var_E8], ebx
0x180002f04  mov     edi, [rsp+108h+arg_8]
0x180002f0b  mov     rsi, [rsp+108h+arg_0]
0x180002f13  cmp     edi, 1
0x180002f16  jnz     short loc_180002F8F
0x180002f18  test    ebx, ebx
0x180002f1a  jnz     short loc_180002F8F
0x180002f1c  xor     r8d, r8d; lpvReserved
0x180002f1f  xor     edx, edx; fdwReason
0x180002f21  mov     rcx, rsi; hinstDLL
0x180002f24  call    DllMain
0x180002f29  jmp     short loc_180002F3E
0x180002f2b  mov     edi, [rsp+108h+arg_8]
0x180002f32  mov     rsi, [rsp+108h+arg_0]
0x180002f3a  mov     ebx, [rsp+108h+var_E8]
0x180002f3e  xor     r8d, r8d
0x180002f41  xor     edx, edx
0x180002f43  mov     rcx, rsi
0x180002f46  call    _CRT_INIT
0x180002f4b  jmp     short loc_180002F60
0x180002f4d  mov     edi, [rsp+108h+arg_8]
0x180002f54  mov     rsi, [rsp+108h+arg_0]
0x180002f5c  mov     ebx, [rsp+108h+var_E8]
0x180002f60  mov     rax, cs:_pRawDllMain
0x180002f67  test    rax, rax
0x180002f6a  jz      short loc_180002F8F
0x180002f6c  xor     r8d, r8d
0x180002f6f  xor     edx, edx
0x180002f71  mov     rcx, rsi
0x180002f74  call    cs:__guard_dispatch_icall_fptr
0x180002f7a  jmp     short loc_180002F8F
0x180002f7c  mov     edi, [rsp+108h+arg_8]
0x180002f83  mov     rsi, [rsp+108h+arg_0]
0x180002f8b  mov     ebx, [rsp+108h+var_E8]
0x180002f8f  test    edi, edi
0x180002f91  jz      short loc_180002F98
0x180002f93  cmp     edi, 3
0x180002f96  jnz     short loc_180003004
0x180002f98  mov     r8, [rsp+108h+lpvReserved]
0x180002fa0  mov     edx, edi
0x180002fa2  mov     rcx, rsi
0x180002fa5  call    _CRT_INIT
0x180002faa  mov     ebx, eax
0x180002fac  mov     [rsp+108h+var_E8], eax
0x180002fb0  jmp     short loc_180002FC7
0x180002fb2  xor     ebx, ebx
0x180002fb4  mov     [rsp+108h+var_E8], ebx
0x180002fb8  mov     edi, [rsp+108h+arg_8]
0x180002fbf  mov     rsi, [rsp+108h+arg_0]
0x180002fc7  mov     rax, cs:_pRawDllMain
0x180002fce  test    rax, rax
0x180002fd1  jz      short loc_180003004
0x180002fd3  cmp     cs:dword_18003A920, 0
0x180002fda  jz      short loc_180003004
0x180002fdc  mov     r8, [rsp+108h+lpvReserved]
0x180002fe4  mov     edx, edi
0x180002fe6  mov     rcx, rsi
0x180002fe9  call    cs:__guard_dispatch_icall_fptr
0x180002fef  mov     ebx, eax
0x180002ff1  mov     [rsp+108h+var_E8], eax
0x180002ff5  jmp     short loc_180003004
0x180002ff7  xor     ebx, ebx
0x180002ff9  mov     [rsp+108h+var_E8], ebx
0x180002ffd  mov     edi, [rsp+108h+arg_8]
0x180003004  cmp     edi, 1
0x180003007  ja      short loc_180003013
0x180003009  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180003013  mov     eax, ebx
0x180003015  add     rsp, 0F0h
0x18000301c  pop     rdi
0x18000301d  pop     rsi
0x18000301e  pop     rbx
0x18000301f  retn
0x18002a263  push    rbp
0x18002a265  sub     rsp, 20h
0x18002a269  mov     rbp, rdx
0x18002a26c  mov     rax, [rcx]
0x18002a26f  mov     edx, [rax]
0x18002a271  mov     [rbp+0A8h], rcx
0x18002a278  mov     [rbp+28h], edx
0x18002a27b  mov     eax, [rbp+28h]
0x18002a27e  cmp     eax, 0E06D7363h
0x18002a283  jnz     short loc_18002A299
0x18002a285  mov     rdx, [rbp+0A8h]
0x18002a28c  mov     ecx, [rbp+28h]
0x18002a28f  call    _XcptFilter_0
0x18002a294  mov     [rbp+30h], eax
0x18002a297  jmp     short loc_18002A2A0
0x18002a299  mov     dword ptr [rbp+30h], 0
0x18002a2a0  mov     eax, [rbp+30h]
0x18002a2a3  add     rsp, 20h
0x18002a2a7  pop     rbp
0x18002a2a8  retn
0x18002a2aa  push    rbp
0x18002a2ac  sub     rsp, 20h
0x18002a2b0  mov     rbp, rdx
0x18002a2b3  mov     rax, [rcx]
0x18002a2b6  mov     edx, [rax]
0x18002a2b8  mov     [rbp+0B0h], rcx
0x18002a2bf  mov     [rbp+38h], edx
0x18002a2c2  mov     eax, [rbp+38h]
0x18002a2c5  cmp     eax, 0E06D7363h
0x18002a2ca  jnz     short loc_18002A2E0
0x18002a2cc  mov     rdx, [rbp+0B0h]
0x18002a2d3  mov     ecx, [rbp+38h]
0x18002a2d6  call    _XcptFilter_0
0x18002a2db  mov     [rbp+40h], eax
0x18002a2de  jmp     short loc_18002A2E7
0x18002a2e0  mov     dword ptr [rbp+40h], 0
0x18002a2e7  mov     eax, [rbp+40h]
0x18002a2ea  add     rsp, 20h
0x18002a2ee  pop     rbp
0x18002a2ef  retn
0x18002a2f1  push    rbp
0x18002a2f3  sub     rsp, 20h
0x18002a2f7  mov     rbp, rdx
0x18002a2fa  mov     rax, [rcx]
0x18002a2fd  mov     edx, [rax]
0x18002a2ff  mov     [rbp+0B8h], rcx
0x18002a306  mov     [rbp+48h], edx
0x18002a309  mov     eax, [rbp+48h]
0x18002a30c  cmp     eax, 0E06D7363h
0x18002a311  jnz     short loc_18002A327
0x18002a313  mov     rdx, [rbp+0B8h]
0x18002a31a  mov     ecx, [rbp+48h]
0x18002a31d  call    _XcptFilter_0
0x18002a322  mov     [rbp+50h], eax
0x18002a325  jmp     short loc_18002A32E
0x18002a327  mov     dword ptr [rbp+50h], 0
0x18002a32e  mov     eax, [rbp+50h]
0x18002a331  add     rsp, 20h
0x18002a335  pop     rbp
0x18002a336  retn
0x18002a338  push    rbp
0x18002a33a  sub     rsp, 20h
0x18002a33e  mov     rbp, rdx
0x18002a341  mov     rax, [rcx]
0x18002a344  mov     edx, [rax]
0x18002a346  mov     [rbp+0C0h], rcx
0x18002a34d  mov     [rbp+58h], edx
0x18002a350  mov     eax, [rbp+58h]
0x18002a353  cmp     eax, 0E06D7363h
0x18002a358  jnz     short loc_18002A36E
0x18002a35a  mov     rdx, [rbp+0C0h]
0x18002a361  mov     ecx, [rbp+58h]
0x18002a364  call    _XcptFilter_0
0x18002a369  mov     [rbp+60h], eax
0x18002a36c  jmp     short loc_18002A375
0x18002a36e  mov     dword ptr [rbp+60h], 0
0x18002a375  mov     eax, [rbp+60h]
0x18002a378  add     rsp, 20h
0x18002a37c  pop     rbp
0x18002a37d  retn
0x18002a37f  push    rbp
0x18002a381  sub     rsp, 20h
0x18002a385  mov     rbp, rdx
0x18002a388  mov     rax, [rcx]
0x18002a38b  mov     edx, [rax]
0x18002a38d  mov     [rbp+0C8h], rcx
0x18002a394  mov     [rbp+68h], edx
0x18002a397  mov     eax, [rbp+68h]
0x18002a39a  cmp     eax, 0E06D7363h
0x18002a39f  jnz     short loc_18002A3B5
0x18002a3a1  mov     rdx, [rbp+0C8h]
0x18002a3a8  mov     ecx, [rbp+68h]
0x18002a3ab  call    _XcptFilter_0
0x18002a3b0  mov     [rbp+70h], eax
0x18002a3b3  jmp     short loc_18002A3BC
0x18002a3b5  mov     dword ptr [rbp+70h], 0
0x18002a3bc  mov     eax, [rbp+70h]
0x18002a3bf  add     rsp, 20h
0x18002a3c3  pop     rbp
0x18002a3c4  retn
0x18002a3c6  push    rbp
0x18002a3c8  sub     rsp, 20h
0x18002a3cc  mov     rbp, rdx
0x18002a3cf  mov     rax, [rcx]
0x18002a3d2  mov     edx, [rax]
0x18002a3d4  mov     [rbp+0D0h], rcx
0x18002a3db  mov     [rbp+78h], edx
0x18002a3de  mov     eax, [rbp+78h]
0x18002a3e1  cmp     eax, 0E06D7363h
0x18002a3e6  jnz     short loc_18002A3FF
0x18002a3e8  mov     rdx, [rbp+0D0h]
0x18002a3ef  mov     ecx, [rbp+78h]
0x18002a3f2  call    _XcptFilter_0
0x18002a3f7  mov     [rbp+80h], eax
0x18002a3fd  jmp     short loc_18002A409
0x18002a3ff  mov     dword ptr [rbp+80h], 0
0x18002a409  mov     eax, [rbp+80h]
0x18002a40f  add     rsp, 20h
0x18002a413  pop     rbp
0x18002a414  retn
0x18002a416  push    rbp
0x18002a418  sub     rsp, 20h
0x18002a41c  mov     rbp, rdx
0x18002a41f  mov     rax, [rcx]
0x18002a422  mov     edx, [rax]
0x18002a424  mov     [rbp+0D8h], rcx
0x18002a42b  mov     [rbp+88h], edx
0x18002a431  mov     eax, [rbp+88h]
0x18002a437  cmp     eax, 0E06D7363h
0x18002a43c  jnz     short loc_18002A458
0x18002a43e  mov     rdx, [rbp+0D8h]
0x18002a445  mov     ecx, [rbp+88h]
0x18002a44b  call    _XcptFilter_0
0x18002a450  mov     [rbp+90h], eax
0x18002a456  jmp     short loc_18002A462
0x18002a458  mov     dword ptr [rbp+90h], 0
0x18002a462  mov     eax, [rbp+90h]
0x18002a468  add     rsp, 20h
0x18002a46c  pop     rbp
0x18002a46d  retn
0x18002a46f  push    rbp
0x18002a471  sub     rsp, 20h
0x18002a475  mov     rbp, rdx
0x18002a478  mov     rax, [rcx]
0x18002a47b  mov     edx, [rax]
0x18002a47d  mov     [rbp+0E0h], rcx
0x18002a484  mov     [rbp+98h], edx
0x18002a48a  mov     eax, [rbp+98h]
0x18002a490  cmp     eax, 0E06D7363h
0x18002a495  jnz     short loc_18002A4B1
0x18002a497  mov     rdx, [rbp+0E0h]
0x18002a49e  mov     ecx, [rbp+98h]
0x18002a4a4  call    _XcptFilter_0
0x18002a4a9  mov     [rbp+0A0h], eax
0x18002a4af  jmp     short loc_18002A4BB
0x18002a4b1  mov     dword ptr [rbp+0A0h], 0
0x18002a4bb  mov     eax, [rbp+0A0h]
0x18002a4c1  add     rsp, 20h
0x18002a4c5  pop     rbp
0x18002a4c6  retn
0x18002a4c8  push    rbp
0x18002a4ca  sub     rsp, 20h
0x18002a4ce  mov     rbp, rdx
0x18002a4d1  cmp     dword ptr [rbp+118h], 1
0x18002a4d8  ja      short loc_18002A4E4
0x18002a4da  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

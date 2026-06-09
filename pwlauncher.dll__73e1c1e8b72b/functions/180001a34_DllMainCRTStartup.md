# __DllMainCRTStartup

- ea: `0x180001a34`
- end: `0x180001c40`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800019f0`

## callees

- `0x1800017c0`
- `0x180001a34`
- `0x180002160`
- `0x180005134`
- `0x18000fe80`

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
  if ( (_DWORD)fdwReason || dword_180019E00 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180019E04 = 1;
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
            if ( dword_180019E04 )
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
0x180001a34  mov     [rsp+lpvReserved], r8
0x180001a39  mov     [rsp+arg_8], edx
0x180001a3d  mov     [rsp+arg_0], rcx
0x180001a42  push    rbx
0x180001a43  push    rsi
0x180001a44  push    rdi
0x180001a45  sub     rsp, 0F0h
0x180001a4c  mov     edi, edx
0x180001a4e  mov     rsi, rcx
0x180001a51  mov     ebx, 1
0x180001a56  cmp     edx, ebx
0x180001a58  ja      short loc_180001A60
0x180001a5a  mov     cs:__native_dllmain_reason, edx
0x180001a60  test    edx, edx
0x180001a62  jnz     short loc_180001A77
0x180001a64  cmp     cs:dword_180019E00, edx
0x180001a6a  jnz     short loc_180001A77
0x180001a6c  xor     ebx, ebx
0x180001a6e  mov     [rsp+108h+var_E8], ebx
0x180001a72  jmp     loc_180001C24
0x180001a77  lea     eax, [rdx-1]
0x180001a7a  cmp     eax, 1
0x180001a7d  ja      loc_180001B04
0x180001a83  mov     rax, cs:_pRawDllMain
0x180001a8a  test    rax, rax
0x180001a8d  jz      short loc_180001AC5
0x180001a8f  cmp     edx, 1
0x180001a92  jnz     short loc_180001A9A
0x180001a94  mov     cs:dword_180019E04, edx
0x180001a9a  mov     r8, [rsp+108h+lpvReserved]
0x180001aa2  call    cs:__guard_dispatch_icall_fptr
0x180001aa8  mov     ebx, eax
0x180001aaa  mov     [rsp+108h+var_E8], eax
0x180001aae  jmp     short loc_180001AC5
0x180001ab0  xor     ebx, ebx
0x180001ab2  mov     [rsp+108h+var_E8], ebx
0x180001ab6  mov     edi, [rsp+108h+arg_8]
0x180001abd  mov     rsi, [rsp+108h+arg_0]
0x180001ac5  test    ebx, ebx
0x180001ac7  jz      loc_180001C24
0x180001acd  mov     r8, [rsp+108h+lpvReserved]
0x180001ad5  mov     edx, edi
0x180001ad7  mov     rcx, rsi
0x180001ada  call    _CRT_INIT
0x180001adf  mov     ebx, eax
0x180001ae1  mov     [rsp+108h+var_E8], eax
0x180001ae5  jmp     short loc_180001AFC
0x180001ae7  xor     ebx, ebx
0x180001ae9  mov     [rsp+108h+var_E8], ebx
0x180001aed  mov     edi, [rsp+108h+arg_8]
0x180001af4  mov     rsi, [rsp+108h+arg_0]
0x180001afc  test    ebx, ebx
0x180001afe  jz      loc_180001C24
0x180001b04  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001b0c  mov     edx, edi; fdwReason
0x180001b0e  mov     rcx, rsi; hinstDLL
0x180001b11  call    DllMain
0x180001b16  mov     ebx, eax
0x180001b18  mov     [rsp+108h+var_E8], eax
0x180001b1c  jmp     short loc_180001B33
0x180001b1e  xor     ebx, ebx
0x180001b20  mov     [rsp+108h+var_E8], ebx
0x180001b24  mov     edi, [rsp+108h+arg_8]
0x180001b2b  mov     rsi, [rsp+108h+arg_0]
0x180001b33  cmp     edi, 1
0x180001b36  jnz     short loc_180001BAF
0x180001b38  test    ebx, ebx
0x180001b3a  jnz     short loc_180001BAF
0x180001b3c  xor     r8d, r8d; lpvReserved
0x180001b3f  xor     edx, edx; fdwReason
0x180001b41  mov     rcx, rsi; hinstDLL
0x180001b44  call    DllMain
0x180001b49  jmp     short loc_180001B5E
0x180001b4b  mov     edi, [rsp+108h+arg_8]
0x180001b52  mov     rsi, [rsp+108h+arg_0]
0x180001b5a  mov     ebx, [rsp+108h+var_E8]
0x180001b5e  xor     r8d, r8d
0x180001b61  xor     edx, edx
0x180001b63  mov     rcx, rsi
0x180001b66  call    _CRT_INIT
0x180001b6b  jmp     short loc_180001B80
0x180001b6d  mov     edi, [rsp+108h+arg_8]
0x180001b74  mov     rsi, [rsp+108h+arg_0]
0x180001b7c  mov     ebx, [rsp+108h+var_E8]
0x180001b80  mov     rax, cs:_pRawDllMain
0x180001b87  test    rax, rax
0x180001b8a  jz      short loc_180001BAF
0x180001b8c  xor     r8d, r8d
0x180001b8f  xor     edx, edx
0x180001b91  mov     rcx, rsi
0x180001b94  call    cs:__guard_dispatch_icall_fptr
0x180001b9a  jmp     short loc_180001BAF
0x180001b9c  mov     edi, [rsp+108h+arg_8]
0x180001ba3  mov     rsi, [rsp+108h+arg_0]
0x180001bab  mov     ebx, [rsp+108h+var_E8]
0x180001baf  test    edi, edi
0x180001bb1  jz      short loc_180001BB8
0x180001bb3  cmp     edi, 3
0x180001bb6  jnz     short loc_180001C24
0x180001bb8  mov     r8, [rsp+108h+lpvReserved]
0x180001bc0  mov     edx, edi
0x180001bc2  mov     rcx, rsi
0x180001bc5  call    _CRT_INIT
0x180001bca  mov     ebx, eax
0x180001bcc  mov     [rsp+108h+var_E8], eax
0x180001bd0  jmp     short loc_180001BE7
0x180001bd2  xor     ebx, ebx
0x180001bd4  mov     [rsp+108h+var_E8], ebx
0x180001bd8  mov     edi, [rsp+108h+arg_8]
0x180001bdf  mov     rsi, [rsp+108h+arg_0]
0x180001be7  mov     rax, cs:_pRawDllMain
0x180001bee  test    rax, rax
0x180001bf1  jz      short loc_180001C24
0x180001bf3  cmp     cs:dword_180019E04, 0
0x180001bfa  jz      short loc_180001C24
0x180001bfc  mov     r8, [rsp+108h+lpvReserved]
0x180001c04  mov     edx, edi
0x180001c06  mov     rcx, rsi
0x180001c09  call    cs:__guard_dispatch_icall_fptr
0x180001c0f  mov     ebx, eax
0x180001c11  mov     [rsp+108h+var_E8], eax
0x180001c15  jmp     short loc_180001C24
0x180001c17  xor     ebx, ebx
0x180001c19  mov     [rsp+108h+var_E8], ebx
0x180001c1d  mov     edi, [rsp+108h+arg_8]
0x180001c24  cmp     edi, 1
0x180001c27  ja      short loc_180001C33
0x180001c29  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001c33  mov     eax, ebx
0x180001c35  add     rsp, 0F0h
0x180001c3c  pop     rdi
0x180001c3d  pop     rsi
0x180001c3e  pop     rbx
0x180001c3f  retn
0x18000ff23  push    rbp
0x18000ff25  sub     rsp, 20h
0x18000ff29  mov     rbp, rdx
0x18000ff2c  mov     rax, [rcx]
0x18000ff2f  mov     edx, [rax]
0x18000ff31  mov     [rbp+0A8h], rcx
0x18000ff38  mov     [rbp+28h], edx
0x18000ff3b  mov     eax, [rbp+28h]
0x18000ff3e  cmp     eax, 0E06D7363h
0x18000ff43  jnz     short loc_18000FF59
0x18000ff45  mov     rdx, [rbp+0A8h]
0x18000ff4c  mov     ecx, [rbp+28h]
0x18000ff4f  call    _XcptFilter_0
0x18000ff54  mov     [rbp+30h], eax
0x18000ff57  jmp     short loc_18000FF60
0x18000ff59  mov     dword ptr [rbp+30h], 0
0x18000ff60  mov     eax, [rbp+30h]
0x18000ff63  add     rsp, 20h
0x18000ff67  pop     rbp
0x18000ff68  retn
0x18000ff6a  push    rbp
0x18000ff6c  sub     rsp, 20h
0x18000ff70  mov     rbp, rdx
0x18000ff73  mov     rax, [rcx]
0x18000ff76  mov     edx, [rax]
0x18000ff78  mov     [rbp+0B0h], rcx
0x18000ff7f  mov     [rbp+38h], edx
0x18000ff82  mov     eax, [rbp+38h]
0x18000ff85  cmp     eax, 0E06D7363h
0x18000ff8a  jnz     short loc_18000FFA0
0x18000ff8c  mov     rdx, [rbp+0B0h]
0x18000ff93  mov     ecx, [rbp+38h]
0x18000ff96  call    _XcptFilter_0
0x18000ff9b  mov     [rbp+40h], eax
0x18000ff9e  jmp     short loc_18000FFA7
0x18000ffa0  mov     dword ptr [rbp+40h], 0
0x18000ffa7  mov     eax, [rbp+40h]
0x18000ffaa  add     rsp, 20h
0x18000ffae  pop     rbp
0x18000ffaf  retn
0x18000ffb1  push    rbp
0x18000ffb3  sub     rsp, 20h
0x18000ffb7  mov     rbp, rdx
0x18000ffba  mov     rax, [rcx]
0x18000ffbd  mov     edx, [rax]
0x18000ffbf  mov     [rbp+0B8h], rcx
0x18000ffc6  mov     [rbp+48h], edx
0x18000ffc9  mov     eax, [rbp+48h]
0x18000ffcc  cmp     eax, 0E06D7363h
0x18000ffd1  jnz     short loc_18000FFE7
0x18000ffd3  mov     rdx, [rbp+0B8h]
0x18000ffda  mov     ecx, [rbp+48h]
0x18000ffdd  call    _XcptFilter_0
0x18000ffe2  mov     [rbp+50h], eax
0x18000ffe5  jmp     short loc_18000FFEE
0x18000ffe7  mov     dword ptr [rbp+50h], 0
0x18000ffee  mov     eax, [rbp+50h]
0x18000fff1  add     rsp, 20h
0x18000fff5  pop     rbp
0x18000fff6  retn
0x18000fff8  push    rbp
0x18000fffa  sub     rsp, 20h
0x18000fffe  mov     rbp, rdx
0x180010001  mov     rax, [rcx]
0x180010004  mov     edx, [rax]
0x180010006  mov     [rbp+0C0h], rcx
0x18001000d  mov     [rbp+58h], edx
0x180010010  mov     eax, [rbp+58h]
0x180010013  cmp     eax, 0E06D7363h
0x180010018  jnz     short loc_18001002E
0x18001001a  mov     rdx, [rbp+0C0h]
0x180010021  mov     ecx, [rbp+58h]
0x180010024  call    _XcptFilter_0
0x180010029  mov     [rbp+60h], eax
0x18001002c  jmp     short loc_180010035
0x18001002e  mov     dword ptr [rbp+60h], 0
0x180010035  mov     eax, [rbp+60h]
0x180010038  add     rsp, 20h
0x18001003c  pop     rbp
0x18001003d  retn
0x18001003f  push    rbp
0x180010041  sub     rsp, 20h
0x180010045  mov     rbp, rdx
0x180010048  mov     rax, [rcx]
0x18001004b  mov     edx, [rax]
0x18001004d  mov     [rbp+0C8h], rcx
0x180010054  mov     [rbp+68h], edx
0x180010057  mov     eax, [rbp+68h]
0x18001005a  cmp     eax, 0E06D7363h
0x18001005f  jnz     short loc_180010075
0x180010061  mov     rdx, [rbp+0C8h]
0x180010068  mov     ecx, [rbp+68h]
0x18001006b  call    _XcptFilter_0
0x180010070  mov     [rbp+70h], eax
0x180010073  jmp     short loc_18001007C
0x180010075  mov     dword ptr [rbp+70h], 0
0x18001007c  mov     eax, [rbp+70h]
0x18001007f  add     rsp, 20h
0x180010083  pop     rbp
0x180010084  retn
0x180010086  push    rbp
0x180010088  sub     rsp, 20h
0x18001008c  mov     rbp, rdx
0x18001008f  mov     rax, [rcx]
0x180010092  mov     edx, [rax]
0x180010094  mov     [rbp+0D0h], rcx
0x18001009b  mov     [rbp+78h], edx
0x18001009e  mov     eax, [rbp+78h]
0x1800100a1  cmp     eax, 0E06D7363h
0x1800100a6  jnz     short loc_1800100BF
0x1800100a8  mov     rdx, [rbp+0D0h]
0x1800100af  mov     ecx, [rbp+78h]
0x1800100b2  call    _XcptFilter_0
0x1800100b7  mov     [rbp+80h], eax
0x1800100bd  jmp     short loc_1800100C9
0x1800100bf  mov     dword ptr [rbp+80h], 0
0x1800100c9  mov     eax, [rbp+80h]
0x1800100cf  add     rsp, 20h
0x1800100d3  pop     rbp
0x1800100d4  retn
0x1800100d6  push    rbp
0x1800100d8  sub     rsp, 20h
0x1800100dc  mov     rbp, rdx
0x1800100df  mov     rax, [rcx]
0x1800100e2  mov     edx, [rax]
0x1800100e4  mov     [rbp+0D8h], rcx
0x1800100eb  mov     [rbp+88h], edx
0x1800100f1  mov     eax, [rbp+88h]
0x1800100f7  cmp     eax, 0E06D7363h
0x1800100fc  jnz     short loc_180010118
0x1800100fe  mov     rdx, [rbp+0D8h]
0x180010105  mov     ecx, [rbp+88h]
0x18001010b  call    _XcptFilter_0
0x180010110  mov     [rbp+90h], eax
0x180010116  jmp     short loc_180010122
0x180010118  mov     dword ptr [rbp+90h], 0
0x180010122  mov     eax, [rbp+90h]
0x180010128  add     rsp, 20h
0x18001012c  pop     rbp
0x18001012d  retn
0x18001012f  push    rbp
0x180010131  sub     rsp, 20h
0x180010135  mov     rbp, rdx
0x180010138  mov     rax, [rcx]
0x18001013b  mov     edx, [rax]
0x18001013d  mov     [rbp+0E0h], rcx
0x180010144  mov     [rbp+98h], edx
0x18001014a  mov     eax, [rbp+98h]
0x180010150  cmp     eax, 0E06D7363h
0x180010155  jnz     short loc_180010171
0x180010157  mov     rdx, [rbp+0E0h]
0x18001015e  mov     ecx, [rbp+98h]
0x180010164  call    _XcptFilter_0
0x180010169  mov     [rbp+0A0h], eax
0x18001016f  jmp     short loc_18001017B
0x180010171  mov     dword ptr [rbp+0A0h], 0
0x18001017b  mov     eax, [rbp+0A0h]
0x180010181  add     rsp, 20h
0x180010185  pop     rbp
0x180010186  retn
0x180010188  push    rbp
0x18001018a  sub     rsp, 20h
0x18001018e  mov     rbp, rdx
0x180010191  cmp     dword ptr [rbp+118h], 1
0x180010198  ja      short loc_1800101A4
0x18001019a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

# __DllMainCRTStartup

- ea: `0x1800100f4`
- end: `0x180010300`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800100b0`

## callees

- `0x180001210`
- `0x18000fe80`
- `0x1800100f4`
- `0x180010875`
- `0x1800498c0`

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
  if ( (_DWORD)fdwReason || dword_180061CE0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180061CE4 = 1;
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
            if ( dword_180061CE4 )
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
0x1800100f4  mov     [rsp+lpvReserved], r8
0x1800100f9  mov     [rsp+arg_8], edx
0x1800100fd  mov     [rsp+arg_0], rcx
0x180010102  push    rbx
0x180010103  push    rsi
0x180010104  push    rdi
0x180010105  sub     rsp, 0F0h
0x18001010c  mov     edi, edx
0x18001010e  mov     rsi, rcx
0x180010111  mov     ebx, 1
0x180010116  cmp     edx, ebx
0x180010118  ja      short loc_180010120
0x18001011a  mov     cs:__native_dllmain_reason, edx
0x180010120  test    edx, edx
0x180010122  jnz     short loc_180010137
0x180010124  cmp     cs:dword_180061CE0, edx
0x18001012a  jnz     short loc_180010137
0x18001012c  xor     ebx, ebx
0x18001012e  mov     [rsp+108h+var_E8], ebx
0x180010132  jmp     loc_1800102E4
0x180010137  lea     eax, [rdx-1]
0x18001013a  cmp     eax, 1
0x18001013d  ja      loc_1800101C4
0x180010143  mov     rax, cs:_pRawDllMain
0x18001014a  test    rax, rax
0x18001014d  jz      short loc_180010185
0x18001014f  cmp     edx, 1
0x180010152  jnz     short loc_18001015A
0x180010154  mov     cs:dword_180061CE4, edx
0x18001015a  mov     r8, [rsp+108h+lpvReserved]
0x180010162  call    cs:__guard_dispatch_icall_fptr
0x180010168  mov     ebx, eax
0x18001016a  mov     [rsp+108h+var_E8], eax
0x18001016e  jmp     short loc_180010185
0x180010170  xor     ebx, ebx
0x180010172  mov     [rsp+108h+var_E8], ebx
0x180010176  mov     edi, [rsp+108h+arg_8]
0x18001017d  mov     rsi, [rsp+108h+arg_0]
0x180010185  test    ebx, ebx
0x180010187  jz      loc_1800102E4
0x18001018d  mov     r8, [rsp+108h+lpvReserved]
0x180010195  mov     edx, edi
0x180010197  mov     rcx, rsi
0x18001019a  call    _CRT_INIT
0x18001019f  mov     ebx, eax
0x1800101a1  mov     [rsp+108h+var_E8], eax
0x1800101a5  jmp     short loc_1800101BC
0x1800101a7  xor     ebx, ebx
0x1800101a9  mov     [rsp+108h+var_E8], ebx
0x1800101ad  mov     edi, [rsp+108h+arg_8]
0x1800101b4  mov     rsi, [rsp+108h+arg_0]
0x1800101bc  test    ebx, ebx
0x1800101be  jz      loc_1800102E4
0x1800101c4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800101cc  mov     edx, edi; fdwReason
0x1800101ce  mov     rcx, rsi; hinstDLL
0x1800101d1  call    DllMain
0x1800101d6  mov     ebx, eax
0x1800101d8  mov     [rsp+108h+var_E8], eax
0x1800101dc  jmp     short loc_1800101F3
0x1800101de  xor     ebx, ebx
0x1800101e0  mov     [rsp+108h+var_E8], ebx
0x1800101e4  mov     edi, [rsp+108h+arg_8]
0x1800101eb  mov     rsi, [rsp+108h+arg_0]
0x1800101f3  cmp     edi, 1
0x1800101f6  jnz     short loc_18001026F
0x1800101f8  test    ebx, ebx
0x1800101fa  jnz     short loc_18001026F
0x1800101fc  xor     r8d, r8d; lpvReserved
0x1800101ff  xor     edx, edx; fdwReason
0x180010201  mov     rcx, rsi; hinstDLL
0x180010204  call    DllMain
0x180010209  jmp     short loc_18001021E
0x18001020b  mov     edi, [rsp+108h+arg_8]
0x180010212  mov     rsi, [rsp+108h+arg_0]
0x18001021a  mov     ebx, [rsp+108h+var_E8]
0x18001021e  xor     r8d, r8d
0x180010221  xor     edx, edx
0x180010223  mov     rcx, rsi
0x180010226  call    _CRT_INIT
0x18001022b  jmp     short loc_180010240
0x18001022d  mov     edi, [rsp+108h+arg_8]
0x180010234  mov     rsi, [rsp+108h+arg_0]
0x18001023c  mov     ebx, [rsp+108h+var_E8]
0x180010240  mov     rax, cs:_pRawDllMain
0x180010247  test    rax, rax
0x18001024a  jz      short loc_18001026F
0x18001024c  xor     r8d, r8d
0x18001024f  xor     edx, edx
0x180010251  mov     rcx, rsi
0x180010254  call    cs:__guard_dispatch_icall_fptr
0x18001025a  jmp     short loc_18001026F
0x18001025c  mov     edi, [rsp+108h+arg_8]
0x180010263  mov     rsi, [rsp+108h+arg_0]
0x18001026b  mov     ebx, [rsp+108h+var_E8]
0x18001026f  test    edi, edi
0x180010271  jz      short loc_180010278
0x180010273  cmp     edi, 3
0x180010276  jnz     short loc_1800102E4
0x180010278  mov     r8, [rsp+108h+lpvReserved]
0x180010280  mov     edx, edi
0x180010282  mov     rcx, rsi
0x180010285  call    _CRT_INIT
0x18001028a  mov     ebx, eax
0x18001028c  mov     [rsp+108h+var_E8], eax
0x180010290  jmp     short loc_1800102A7
0x180010292  xor     ebx, ebx
0x180010294  mov     [rsp+108h+var_E8], ebx
0x180010298  mov     edi, [rsp+108h+arg_8]
0x18001029f  mov     rsi, [rsp+108h+arg_0]
0x1800102a7  mov     rax, cs:_pRawDllMain
0x1800102ae  test    rax, rax
0x1800102b1  jz      short loc_1800102E4
0x1800102b3  cmp     cs:dword_180061CE4, 0
0x1800102ba  jz      short loc_1800102E4
0x1800102bc  mov     r8, [rsp+108h+lpvReserved]
0x1800102c4  mov     edx, edi
0x1800102c6  mov     rcx, rsi
0x1800102c9  call    cs:__guard_dispatch_icall_fptr
0x1800102cf  mov     ebx, eax
0x1800102d1  mov     [rsp+108h+var_E8], eax
0x1800102d5  jmp     short loc_1800102E4
0x1800102d7  xor     ebx, ebx
0x1800102d9  mov     [rsp+108h+var_E8], ebx
0x1800102dd  mov     edi, [rsp+108h+arg_8]
0x1800102e4  cmp     edi, 1
0x1800102e7  ja      short loc_1800102F3
0x1800102e9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800102f3  mov     eax, ebx
0x1800102f5  add     rsp, 0F0h
0x1800102fc  pop     rdi
0x1800102fd  pop     rsi
0x1800102fe  pop     rbx
0x1800102ff  retn
0x180049a49  push    rbp
0x180049a4b  sub     rsp, 20h
0x180049a4f  mov     rbp, rdx
0x180049a52  mov     rax, [rcx]
0x180049a55  mov     edx, [rax]
0x180049a57  mov     [rbp+0A8h], rcx
0x180049a5e  mov     [rbp+28h], edx
0x180049a61  mov     eax, [rbp+28h]
0x180049a64  cmp     eax, 0E06D7363h
0x180049a69  jnz     short loc_180049A7F
0x180049a6b  mov     rdx, [rbp+0A8h]
0x180049a72  mov     ecx, [rbp+28h]
0x180049a75  call    _XcptFilter_0
0x180049a7a  mov     [rbp+30h], eax
0x180049a7d  jmp     short loc_180049A86
0x180049a7f  mov     dword ptr [rbp+30h], 0
0x180049a86  mov     eax, [rbp+30h]
0x180049a89  add     rsp, 20h
0x180049a8d  pop     rbp
0x180049a8e  retn
0x180049a90  push    rbp
0x180049a92  sub     rsp, 20h
0x180049a96  mov     rbp, rdx
0x180049a99  mov     rax, [rcx]
0x180049a9c  mov     edx, [rax]
0x180049a9e  mov     [rbp+0B0h], rcx
0x180049aa5  mov     [rbp+38h], edx
0x180049aa8  mov     eax, [rbp+38h]
0x180049aab  cmp     eax, 0E06D7363h
0x180049ab0  jnz     short loc_180049AC6
0x180049ab2  mov     rdx, [rbp+0B0h]
0x180049ab9  mov     ecx, [rbp+38h]
0x180049abc  call    _XcptFilter_0
0x180049ac1  mov     [rbp+40h], eax
0x180049ac4  jmp     short loc_180049ACD
0x180049ac6  mov     dword ptr [rbp+40h], 0
0x180049acd  mov     eax, [rbp+40h]
0x180049ad0  add     rsp, 20h
0x180049ad4  pop     rbp
0x180049ad5  retn
0x180049ad7  push    rbp
0x180049ad9  sub     rsp, 20h
0x180049add  mov     rbp, rdx
0x180049ae0  mov     rax, [rcx]
0x180049ae3  mov     edx, [rax]
0x180049ae5  mov     [rbp+0B8h], rcx
0x180049aec  mov     [rbp+48h], edx
0x180049aef  mov     eax, [rbp+48h]
0x180049af2  cmp     eax, 0E06D7363h
0x180049af7  jnz     short loc_180049B0D
0x180049af9  mov     rdx, [rbp+0B8h]
0x180049b00  mov     ecx, [rbp+48h]
0x180049b03  call    _XcptFilter_0
0x180049b08  mov     [rbp+50h], eax
0x180049b0b  jmp     short loc_180049B14
0x180049b0d  mov     dword ptr [rbp+50h], 0
0x180049b14  mov     eax, [rbp+50h]
0x180049b17  add     rsp, 20h
0x180049b1b  pop     rbp
0x180049b1c  retn
0x180049b1e  push    rbp
0x180049b20  sub     rsp, 20h
0x180049b24  mov     rbp, rdx
0x180049b27  mov     rax, [rcx]
0x180049b2a  mov     edx, [rax]
0x180049b2c  mov     [rbp+0C0h], rcx
0x180049b33  mov     [rbp+58h], edx
0x180049b36  mov     eax, [rbp+58h]
0x180049b39  cmp     eax, 0E06D7363h
0x180049b3e  jnz     short loc_180049B54
0x180049b40  mov     rdx, [rbp+0C0h]
0x180049b47  mov     ecx, [rbp+58h]
0x180049b4a  call    _XcptFilter_0
0x180049b4f  mov     [rbp+60h], eax
0x180049b52  jmp     short loc_180049B5B
0x180049b54  mov     dword ptr [rbp+60h], 0
0x180049b5b  mov     eax, [rbp+60h]
0x180049b5e  add     rsp, 20h
0x180049b62  pop     rbp
0x180049b63  retn
0x180049b65  push    rbp
0x180049b67  sub     rsp, 20h
0x180049b6b  mov     rbp, rdx
0x180049b6e  mov     rax, [rcx]
0x180049b71  mov     edx, [rax]
0x180049b73  mov     [rbp+0C8h], rcx
0x180049b7a  mov     [rbp+68h], edx
0x180049b7d  mov     eax, [rbp+68h]
0x180049b80  cmp     eax, 0E06D7363h
0x180049b85  jnz     short loc_180049B9B
0x180049b87  mov     rdx, [rbp+0C8h]
0x180049b8e  mov     ecx, [rbp+68h]
0x180049b91  call    _XcptFilter_0
0x180049b96  mov     [rbp+70h], eax
0x180049b99  jmp     short loc_180049BA2
0x180049b9b  mov     dword ptr [rbp+70h], 0
0x180049ba2  mov     eax, [rbp+70h]
0x180049ba5  add     rsp, 20h
0x180049ba9  pop     rbp
0x180049baa  retn
0x180049bac  push    rbp
0x180049bae  sub     rsp, 20h
0x180049bb2  mov     rbp, rdx
0x180049bb5  mov     rax, [rcx]
0x180049bb8  mov     edx, [rax]
0x180049bba  mov     [rbp+0D0h], rcx
0x180049bc1  mov     [rbp+78h], edx
0x180049bc4  mov     eax, [rbp+78h]
0x180049bc7  cmp     eax, 0E06D7363h
0x180049bcc  jnz     short loc_180049BE5
0x180049bce  mov     rdx, [rbp+0D0h]
0x180049bd5  mov     ecx, [rbp+78h]
0x180049bd8  call    _XcptFilter_0
0x180049bdd  mov     [rbp+80h], eax
0x180049be3  jmp     short loc_180049BEF
0x180049be5  mov     dword ptr [rbp+80h], 0
0x180049bef  mov     eax, [rbp+80h]
0x180049bf5  add     rsp, 20h
0x180049bf9  pop     rbp
0x180049bfa  retn
0x180049bfc  push    rbp
0x180049bfe  sub     rsp, 20h
0x180049c02  mov     rbp, rdx
0x180049c05  mov     rax, [rcx]
0x180049c08  mov     edx, [rax]
0x180049c0a  mov     [rbp+0D8h], rcx
0x180049c11  mov     [rbp+88h], edx
0x180049c17  mov     eax, [rbp+88h]
0x180049c1d  cmp     eax, 0E06D7363h
0x180049c22  jnz     short loc_180049C3E
0x180049c24  mov     rdx, [rbp+0D8h]
0x180049c2b  mov     ecx, [rbp+88h]
0x180049c31  call    _XcptFilter_0
0x180049c36  mov     [rbp+90h], eax
0x180049c3c  jmp     short loc_180049C48
0x180049c3e  mov     dword ptr [rbp+90h], 0
0x180049c48  mov     eax, [rbp+90h]
0x180049c4e  add     rsp, 20h
0x180049c52  pop     rbp
0x180049c53  retn
0x180049c55  push    rbp
0x180049c57  sub     rsp, 20h
0x180049c5b  mov     rbp, rdx
0x180049c5e  mov     rax, [rcx]
0x180049c61  mov     edx, [rax]
0x180049c63  mov     [rbp+0E0h], rcx
0x180049c6a  mov     [rbp+98h], edx
0x180049c70  mov     eax, [rbp+98h]
0x180049c76  cmp     eax, 0E06D7363h
0x180049c7b  jnz     short loc_180049C97
0x180049c7d  mov     rdx, [rbp+0E0h]
0x180049c84  mov     ecx, [rbp+98h]
0x180049c8a  call    _XcptFilter_0
0x180049c8f  mov     [rbp+0A0h], eax
0x180049c95  jmp     short loc_180049CA1
0x180049c97  mov     dword ptr [rbp+0A0h], 0
0x180049ca1  mov     eax, [rbp+0A0h]
0x180049ca7  add     rsp, 20h
0x180049cab  pop     rbp
0x180049cac  retn
0x180049cae  push    rbp
0x180049cb0  sub     rsp, 20h
0x180049cb4  mov     rbp, rdx
0x180049cb7  cmp     dword ptr [rbp+118h], 1
0x180049cbe  ja      short loc_180049CCA
0x180049cc0  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

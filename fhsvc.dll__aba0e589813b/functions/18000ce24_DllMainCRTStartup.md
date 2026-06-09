# __DllMainCRTStartup

- ea: `0x18000ce24`
- end: `0x18000d030`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000cde0`

## callees

- `0x18000bec0`
- `0x18000cbb0`
- `0x18000ce24`
- `0x18000d270`
- `0x1800119f0`

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
  if ( (_DWORD)fdwReason || dword_180019240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180019244 = 1;
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
            if ( dword_180019244 )
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
0x18000ce24  mov     [rsp+lpvReserved], r8
0x18000ce29  mov     [rsp+arg_8], edx
0x18000ce2d  mov     [rsp+arg_0], rcx
0x18000ce32  push    rbx
0x18000ce33  push    rsi
0x18000ce34  push    rdi
0x18000ce35  sub     rsp, 0F0h
0x18000ce3c  mov     edi, edx
0x18000ce3e  mov     rsi, rcx
0x18000ce41  mov     ebx, 1
0x18000ce46  cmp     edx, ebx
0x18000ce48  ja      short loc_18000CE50
0x18000ce4a  mov     cs:__native_dllmain_reason, edx
0x18000ce50  test    edx, edx
0x18000ce52  jnz     short loc_18000CE67
0x18000ce54  cmp     cs:dword_180019240, edx
0x18000ce5a  jnz     short loc_18000CE67
0x18000ce5c  xor     ebx, ebx
0x18000ce5e  mov     [rsp+108h+var_E8], ebx
0x18000ce62  jmp     loc_18000D014
0x18000ce67  lea     eax, [rdx-1]
0x18000ce6a  cmp     eax, 1
0x18000ce6d  ja      loc_18000CEF4
0x18000ce73  mov     rax, cs:_pRawDllMain
0x18000ce7a  test    rax, rax
0x18000ce7d  jz      short loc_18000CEB5
0x18000ce7f  cmp     edx, 1
0x18000ce82  jnz     short loc_18000CE8A
0x18000ce84  mov     cs:dword_180019244, edx
0x18000ce8a  mov     r8, [rsp+108h+lpvReserved]
0x18000ce92  call    cs:__guard_dispatch_icall_fptr
0x18000ce98  mov     ebx, eax
0x18000ce9a  mov     [rsp+108h+var_E8], eax
0x18000ce9e  jmp     short loc_18000CEB5
0x18000cea0  xor     ebx, ebx
0x18000cea2  mov     [rsp+108h+var_E8], ebx
0x18000cea6  mov     edi, [rsp+108h+arg_8]
0x18000cead  mov     rsi, [rsp+108h+arg_0]
0x18000ceb5  test    ebx, ebx
0x18000ceb7  jz      loc_18000D014
0x18000cebd  mov     r8, [rsp+108h+lpvReserved]
0x18000cec5  mov     edx, edi
0x18000cec7  mov     rcx, rsi
0x18000ceca  call    _CRT_INIT
0x18000cecf  mov     ebx, eax
0x18000ced1  mov     [rsp+108h+var_E8], eax
0x18000ced5  jmp     short loc_18000CEEC
0x18000ced7  xor     ebx, ebx
0x18000ced9  mov     [rsp+108h+var_E8], ebx
0x18000cedd  mov     edi, [rsp+108h+arg_8]
0x18000cee4  mov     rsi, [rsp+108h+arg_0]
0x18000ceec  test    ebx, ebx
0x18000ceee  jz      loc_18000D014
0x18000cef4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000cefc  mov     edx, edi; fdwReason
0x18000cefe  mov     rcx, rsi; hinstDLL
0x18000cf01  call    DllMain
0x18000cf06  mov     ebx, eax
0x18000cf08  mov     [rsp+108h+var_E8], eax
0x18000cf0c  jmp     short loc_18000CF23
0x18000cf0e  xor     ebx, ebx
0x18000cf10  mov     [rsp+108h+var_E8], ebx
0x18000cf14  mov     edi, [rsp+108h+arg_8]
0x18000cf1b  mov     rsi, [rsp+108h+arg_0]
0x18000cf23  cmp     edi, 1
0x18000cf26  jnz     short loc_18000CF9F
0x18000cf28  test    ebx, ebx
0x18000cf2a  jnz     short loc_18000CF9F
0x18000cf2c  xor     r8d, r8d; lpvReserved
0x18000cf2f  xor     edx, edx; fdwReason
0x18000cf31  mov     rcx, rsi; hinstDLL
0x18000cf34  call    DllMain
0x18000cf39  jmp     short loc_18000CF4E
0x18000cf3b  mov     edi, [rsp+108h+arg_8]
0x18000cf42  mov     rsi, [rsp+108h+arg_0]
0x18000cf4a  mov     ebx, [rsp+108h+var_E8]
0x18000cf4e  xor     r8d, r8d
0x18000cf51  xor     edx, edx
0x18000cf53  mov     rcx, rsi
0x18000cf56  call    _CRT_INIT
0x18000cf5b  jmp     short loc_18000CF70
0x18000cf5d  mov     edi, [rsp+108h+arg_8]
0x18000cf64  mov     rsi, [rsp+108h+arg_0]
0x18000cf6c  mov     ebx, [rsp+108h+var_E8]
0x18000cf70  mov     rax, cs:_pRawDllMain
0x18000cf77  test    rax, rax
0x18000cf7a  jz      short loc_18000CF9F
0x18000cf7c  xor     r8d, r8d
0x18000cf7f  xor     edx, edx
0x18000cf81  mov     rcx, rsi
0x18000cf84  call    cs:__guard_dispatch_icall_fptr
0x18000cf8a  jmp     short loc_18000CF9F
0x18000cf8c  mov     edi, [rsp+108h+arg_8]
0x18000cf93  mov     rsi, [rsp+108h+arg_0]
0x18000cf9b  mov     ebx, [rsp+108h+var_E8]
0x18000cf9f  test    edi, edi
0x18000cfa1  jz      short loc_18000CFA8
0x18000cfa3  cmp     edi, 3
0x18000cfa6  jnz     short loc_18000D014
0x18000cfa8  mov     r8, [rsp+108h+lpvReserved]
0x18000cfb0  mov     edx, edi
0x18000cfb2  mov     rcx, rsi
0x18000cfb5  call    _CRT_INIT
0x18000cfba  mov     ebx, eax
0x18000cfbc  mov     [rsp+108h+var_E8], eax
0x18000cfc0  jmp     short loc_18000CFD7
0x18000cfc2  xor     ebx, ebx
0x18000cfc4  mov     [rsp+108h+var_E8], ebx
0x18000cfc8  mov     edi, [rsp+108h+arg_8]
0x18000cfcf  mov     rsi, [rsp+108h+arg_0]
0x18000cfd7  mov     rax, cs:_pRawDllMain
0x18000cfde  test    rax, rax
0x18000cfe1  jz      short loc_18000D014
0x18000cfe3  cmp     cs:dword_180019244, 0
0x18000cfea  jz      short loc_18000D014
0x18000cfec  mov     r8, [rsp+108h+lpvReserved]
0x18000cff4  mov     edx, edi
0x18000cff6  mov     rcx, rsi
0x18000cff9  call    cs:__guard_dispatch_icall_fptr
0x18000cfff  mov     ebx, eax
0x18000d001  mov     [rsp+108h+var_E8], eax
0x18000d005  jmp     short loc_18000D014
0x18000d007  xor     ebx, ebx
0x18000d009  mov     [rsp+108h+var_E8], ebx
0x18000d00d  mov     edi, [rsp+108h+arg_8]
0x18000d014  cmp     edi, 1
0x18000d017  ja      short loc_18000D023
0x18000d019  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000d023  mov     eax, ebx
0x18000d025  add     rsp, 0F0h
0x18000d02c  pop     rdi
0x18000d02d  pop     rsi
0x18000d02e  pop     rbx
0x18000d02f  retn
0x180012087  push    rbp
0x180012089  sub     rsp, 20h
0x18001208d  mov     rbp, rdx
0x180012090  mov     rax, [rcx]
0x180012093  mov     edx, [rax]
0x180012095  mov     [rbp+0A8h], rcx
0x18001209c  mov     [rbp+28h], edx
0x18001209f  mov     eax, [rbp+28h]
0x1800120a2  cmp     eax, 0E06D7363h
0x1800120a7  jnz     short loc_1800120BD
0x1800120a9  mov     rdx, [rbp+0A8h]
0x1800120b0  mov     ecx, [rbp+28h]
0x1800120b3  call    _XcptFilter_0
0x1800120b8  mov     [rbp+30h], eax
0x1800120bb  jmp     short loc_1800120C4
0x1800120bd  mov     dword ptr [rbp+30h], 0
0x1800120c4  mov     eax, [rbp+30h]
0x1800120c7  add     rsp, 20h
0x1800120cb  pop     rbp
0x1800120cc  retn
0x1800120ce  push    rbp
0x1800120d0  sub     rsp, 20h
0x1800120d4  mov     rbp, rdx
0x1800120d7  mov     rax, [rcx]
0x1800120da  mov     edx, [rax]
0x1800120dc  mov     [rbp+0B0h], rcx
0x1800120e3  mov     [rbp+38h], edx
0x1800120e6  mov     eax, [rbp+38h]
0x1800120e9  cmp     eax, 0E06D7363h
0x1800120ee  jnz     short loc_180012104
0x1800120f0  mov     rdx, [rbp+0B0h]
0x1800120f7  mov     ecx, [rbp+38h]
0x1800120fa  call    _XcptFilter_0
0x1800120ff  mov     [rbp+40h], eax
0x180012102  jmp     short loc_18001210B
0x180012104  mov     dword ptr [rbp+40h], 0
0x18001210b  mov     eax, [rbp+40h]
0x18001210e  add     rsp, 20h
0x180012112  pop     rbp
0x180012113  retn
0x180012115  push    rbp
0x180012117  sub     rsp, 20h
0x18001211b  mov     rbp, rdx
0x18001211e  mov     rax, [rcx]
0x180012121  mov     edx, [rax]
0x180012123  mov     [rbp+0B8h], rcx
0x18001212a  mov     [rbp+48h], edx
0x18001212d  mov     eax, [rbp+48h]
0x180012130  cmp     eax, 0E06D7363h
0x180012135  jnz     short loc_18001214B
0x180012137  mov     rdx, [rbp+0B8h]
0x18001213e  mov     ecx, [rbp+48h]
0x180012141  call    _XcptFilter_0
0x180012146  mov     [rbp+50h], eax
0x180012149  jmp     short loc_180012152
0x18001214b  mov     dword ptr [rbp+50h], 0
0x180012152  mov     eax, [rbp+50h]
0x180012155  add     rsp, 20h
0x180012159  pop     rbp
0x18001215a  retn
0x18001215c  push    rbp
0x18001215e  sub     rsp, 20h
0x180012162  mov     rbp, rdx
0x180012165  mov     rax, [rcx]
0x180012168  mov     edx, [rax]
0x18001216a  mov     [rbp+0C0h], rcx
0x180012171  mov     [rbp+58h], edx
0x180012174  mov     eax, [rbp+58h]
0x180012177  cmp     eax, 0E06D7363h
0x18001217c  jnz     short loc_180012192
0x18001217e  mov     rdx, [rbp+0C0h]
0x180012185  mov     ecx, [rbp+58h]
0x180012188  call    _XcptFilter_0
0x18001218d  mov     [rbp+60h], eax
0x180012190  jmp     short loc_180012199
0x180012192  mov     dword ptr [rbp+60h], 0
0x180012199  mov     eax, [rbp+60h]
0x18001219c  add     rsp, 20h
0x1800121a0  pop     rbp
0x1800121a1  retn
0x1800121a3  push    rbp
0x1800121a5  sub     rsp, 20h
0x1800121a9  mov     rbp, rdx
0x1800121ac  mov     rax, [rcx]
0x1800121af  mov     edx, [rax]
0x1800121b1  mov     [rbp+0C8h], rcx
0x1800121b8  mov     [rbp+68h], edx
0x1800121bb  mov     eax, [rbp+68h]
0x1800121be  cmp     eax, 0E06D7363h
0x1800121c3  jnz     short loc_1800121D9
0x1800121c5  mov     rdx, [rbp+0C8h]
0x1800121cc  mov     ecx, [rbp+68h]
0x1800121cf  call    _XcptFilter_0
0x1800121d4  mov     [rbp+70h], eax
0x1800121d7  jmp     short loc_1800121E0
0x1800121d9  mov     dword ptr [rbp+70h], 0
0x1800121e0  mov     eax, [rbp+70h]
0x1800121e3  add     rsp, 20h
0x1800121e7  pop     rbp
0x1800121e8  retn
0x1800121ea  push    rbp
0x1800121ec  sub     rsp, 20h
0x1800121f0  mov     rbp, rdx
0x1800121f3  mov     rax, [rcx]
0x1800121f6  mov     edx, [rax]
0x1800121f8  mov     [rbp+0D0h], rcx
0x1800121ff  mov     [rbp+78h], edx
0x180012202  mov     eax, [rbp+78h]
0x180012205  cmp     eax, 0E06D7363h
0x18001220a  jnz     short loc_180012223
0x18001220c  mov     rdx, [rbp+0D0h]
0x180012213  mov     ecx, [rbp+78h]
0x180012216  call    _XcptFilter_0
0x18001221b  mov     [rbp+80h], eax
0x180012221  jmp     short loc_18001222D
0x180012223  mov     dword ptr [rbp+80h], 0
0x18001222d  mov     eax, [rbp+80h]
0x180012233  add     rsp, 20h
0x180012237  pop     rbp
0x180012238  retn
0x18001223a  push    rbp
0x18001223c  sub     rsp, 20h
0x180012240  mov     rbp, rdx
0x180012243  mov     rax, [rcx]
0x180012246  mov     edx, [rax]
0x180012248  mov     [rbp+0D8h], rcx
0x18001224f  mov     [rbp+88h], edx
0x180012255  mov     eax, [rbp+88h]
0x18001225b  cmp     eax, 0E06D7363h
0x180012260  jnz     short loc_18001227C
0x180012262  mov     rdx, [rbp+0D8h]
0x180012269  mov     ecx, [rbp+88h]
0x18001226f  call    _XcptFilter_0
0x180012274  mov     [rbp+90h], eax
0x18001227a  jmp     short loc_180012286
0x18001227c  mov     dword ptr [rbp+90h], 0
0x180012286  mov     eax, [rbp+90h]
0x18001228c  add     rsp, 20h
0x180012290  pop     rbp
0x180012291  retn
0x180012293  push    rbp
0x180012295  sub     rsp, 20h
0x180012299  mov     rbp, rdx
0x18001229c  mov     rax, [rcx]
0x18001229f  mov     edx, [rax]
0x1800122a1  mov     [rbp+0E0h], rcx
0x1800122a8  mov     [rbp+98h], edx
0x1800122ae  mov     eax, [rbp+98h]
0x1800122b4  cmp     eax, 0E06D7363h
0x1800122b9  jnz     short loc_1800122D5
0x1800122bb  mov     rdx, [rbp+0E0h]
0x1800122c2  mov     ecx, [rbp+98h]
0x1800122c8  call    _XcptFilter_0
0x1800122cd  mov     [rbp+0A0h], eax
0x1800122d3  jmp     short loc_1800122DF
0x1800122d5  mov     dword ptr [rbp+0A0h], 0
0x1800122df  mov     eax, [rbp+0A0h]
0x1800122e5  add     rsp, 20h
0x1800122e9  pop     rbp
0x1800122ea  retn
0x1800122ec  push    rbp
0x1800122ee  sub     rsp, 20h
0x1800122f2  mov     rbp, rdx
0x1800122f5  cmp     dword ptr [rbp+118h], 1
0x1800122fc  ja      short loc_180012308
0x1800122fe  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

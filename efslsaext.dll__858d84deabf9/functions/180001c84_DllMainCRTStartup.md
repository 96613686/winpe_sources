# __DllMainCRTStartup

- ea: `0x180001c84`
- end: `0x180001e90`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001c40`

## callees

- `0x180001a10`
- `0x180001c84`
- `0x180001f6c`
- `0x180002ce0`
- `0x180012080`

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
  if ( (_DWORD)fdwReason || dword_18001E380 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001E384 = 1;
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
            if ( dword_18001E384 )
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
0x180001c84  mov     [rsp+lpvReserved], r8
0x180001c89  mov     [rsp+arg_8], edx
0x180001c8d  mov     [rsp+arg_0], rcx
0x180001c92  push    rbx
0x180001c93  push    rsi
0x180001c94  push    rdi
0x180001c95  sub     rsp, 0F0h
0x180001c9c  mov     edi, edx
0x180001c9e  mov     rsi, rcx
0x180001ca1  mov     ebx, 1
0x180001ca6  cmp     edx, ebx
0x180001ca8  ja      short loc_180001CB0
0x180001caa  mov     cs:__native_dllmain_reason, edx
0x180001cb0  test    edx, edx
0x180001cb2  jnz     short loc_180001CC7
0x180001cb4  cmp     cs:dword_18001E380, edx
0x180001cba  jnz     short loc_180001CC7
0x180001cbc  xor     ebx, ebx
0x180001cbe  mov     [rsp+108h+var_E8], ebx
0x180001cc2  jmp     loc_180001E74
0x180001cc7  lea     eax, [rdx-1]
0x180001cca  cmp     eax, 1
0x180001ccd  ja      loc_180001D54
0x180001cd3  mov     rax, cs:_pRawDllMain
0x180001cda  test    rax, rax
0x180001cdd  jz      short loc_180001D15
0x180001cdf  cmp     edx, 1
0x180001ce2  jnz     short loc_180001CEA
0x180001ce4  mov     cs:dword_18001E384, edx
0x180001cea  mov     r8, [rsp+108h+lpvReserved]
0x180001cf2  call    cs:__guard_dispatch_icall_fptr
0x180001cf8  mov     ebx, eax
0x180001cfa  mov     [rsp+108h+var_E8], eax
0x180001cfe  jmp     short loc_180001D15
0x180001d00  xor     ebx, ebx
0x180001d02  mov     [rsp+108h+var_E8], ebx
0x180001d06  mov     edi, [rsp+108h+arg_8]
0x180001d0d  mov     rsi, [rsp+108h+arg_0]
0x180001d15  test    ebx, ebx
0x180001d17  jz      loc_180001E74
0x180001d1d  mov     r8, [rsp+108h+lpvReserved]
0x180001d25  mov     edx, edi
0x180001d27  mov     rcx, rsi
0x180001d2a  call    _CRT_INIT
0x180001d2f  mov     ebx, eax
0x180001d31  mov     [rsp+108h+var_E8], eax
0x180001d35  jmp     short loc_180001D4C
0x180001d37  xor     ebx, ebx
0x180001d39  mov     [rsp+108h+var_E8], ebx
0x180001d3d  mov     edi, [rsp+108h+arg_8]
0x180001d44  mov     rsi, [rsp+108h+arg_0]
0x180001d4c  test    ebx, ebx
0x180001d4e  jz      loc_180001E74
0x180001d54  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001d5c  mov     edx, edi; fdwReason
0x180001d5e  mov     rcx, rsi; hinstDLL
0x180001d61  call    DllMain
0x180001d66  mov     ebx, eax
0x180001d68  mov     [rsp+108h+var_E8], eax
0x180001d6c  jmp     short loc_180001D83
0x180001d6e  xor     ebx, ebx
0x180001d70  mov     [rsp+108h+var_E8], ebx
0x180001d74  mov     edi, [rsp+108h+arg_8]
0x180001d7b  mov     rsi, [rsp+108h+arg_0]
0x180001d83  cmp     edi, 1
0x180001d86  jnz     short loc_180001DFF
0x180001d88  test    ebx, ebx
0x180001d8a  jnz     short loc_180001DFF
0x180001d8c  xor     r8d, r8d; lpvReserved
0x180001d8f  xor     edx, edx; fdwReason
0x180001d91  mov     rcx, rsi; hinstDLL
0x180001d94  call    DllMain
0x180001d99  jmp     short loc_180001DAE
0x180001d9b  mov     edi, [rsp+108h+arg_8]
0x180001da2  mov     rsi, [rsp+108h+arg_0]
0x180001daa  mov     ebx, [rsp+108h+var_E8]
0x180001dae  xor     r8d, r8d
0x180001db1  xor     edx, edx
0x180001db3  mov     rcx, rsi
0x180001db6  call    _CRT_INIT
0x180001dbb  jmp     short loc_180001DD0
0x180001dbd  mov     edi, [rsp+108h+arg_8]
0x180001dc4  mov     rsi, [rsp+108h+arg_0]
0x180001dcc  mov     ebx, [rsp+108h+var_E8]
0x180001dd0  mov     rax, cs:_pRawDllMain
0x180001dd7  test    rax, rax
0x180001dda  jz      short loc_180001DFF
0x180001ddc  xor     r8d, r8d
0x180001ddf  xor     edx, edx
0x180001de1  mov     rcx, rsi
0x180001de4  call    cs:__guard_dispatch_icall_fptr
0x180001dea  jmp     short loc_180001DFF
0x180001dec  mov     edi, [rsp+108h+arg_8]
0x180001df3  mov     rsi, [rsp+108h+arg_0]
0x180001dfb  mov     ebx, [rsp+108h+var_E8]
0x180001dff  test    edi, edi
0x180001e01  jz      short loc_180001E08
0x180001e03  cmp     edi, 3
0x180001e06  jnz     short loc_180001E74
0x180001e08  mov     r8, [rsp+108h+lpvReserved]
0x180001e10  mov     edx, edi
0x180001e12  mov     rcx, rsi
0x180001e15  call    _CRT_INIT
0x180001e1a  mov     ebx, eax
0x180001e1c  mov     [rsp+108h+var_E8], eax
0x180001e20  jmp     short loc_180001E37
0x180001e22  xor     ebx, ebx
0x180001e24  mov     [rsp+108h+var_E8], ebx
0x180001e28  mov     edi, [rsp+108h+arg_8]
0x180001e2f  mov     rsi, [rsp+108h+arg_0]
0x180001e37  mov     rax, cs:_pRawDllMain
0x180001e3e  test    rax, rax
0x180001e41  jz      short loc_180001E74
0x180001e43  cmp     cs:dword_18001E384, 0
0x180001e4a  jz      short loc_180001E74
0x180001e4c  mov     r8, [rsp+108h+lpvReserved]
0x180001e54  mov     edx, edi
0x180001e56  mov     rcx, rsi
0x180001e59  call    cs:__guard_dispatch_icall_fptr
0x180001e5f  mov     ebx, eax
0x180001e61  mov     [rsp+108h+var_E8], eax
0x180001e65  jmp     short loc_180001E74
0x180001e67  xor     ebx, ebx
0x180001e69  mov     [rsp+108h+var_E8], ebx
0x180001e6d  mov     edi, [rsp+108h+arg_8]
0x180001e74  cmp     edi, 1
0x180001e77  ja      short loc_180001E83
0x180001e79  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001e83  mov     eax, ebx
0x180001e85  add     rsp, 0F0h
0x180001e8c  pop     rdi
0x180001e8d  pop     rsi
0x180001e8e  pop     rbx
0x180001e8f  retn
0x180012150  push    rbp
0x180012152  sub     rsp, 20h
0x180012156  mov     rbp, rdx
0x180012159  mov     rax, [rcx]
0x18001215c  mov     edx, [rax]
0x18001215e  mov     [rbp+0A8h], rcx
0x180012165  mov     [rbp+28h], edx
0x180012168  mov     eax, [rbp+28h]
0x18001216b  cmp     eax, 0E06D7363h
0x180012170  jnz     short loc_180012186
0x180012172  mov     rdx, [rbp+0A8h]
0x180012179  mov     ecx, [rbp+28h]
0x18001217c  call    _XcptFilter_0
0x180012181  mov     [rbp+30h], eax
0x180012184  jmp     short loc_18001218D
0x180012186  mov     dword ptr [rbp+30h], 0
0x18001218d  mov     eax, [rbp+30h]
0x180012190  add     rsp, 20h
0x180012194  pop     rbp
0x180012195  retn
0x180012197  push    rbp
0x180012199  sub     rsp, 20h
0x18001219d  mov     rbp, rdx
0x1800121a0  mov     rax, [rcx]
0x1800121a3  mov     edx, [rax]
0x1800121a5  mov     [rbp+0B0h], rcx
0x1800121ac  mov     [rbp+38h], edx
0x1800121af  mov     eax, [rbp+38h]
0x1800121b2  cmp     eax, 0E06D7363h
0x1800121b7  jnz     short loc_1800121CD
0x1800121b9  mov     rdx, [rbp+0B0h]
0x1800121c0  mov     ecx, [rbp+38h]
0x1800121c3  call    _XcptFilter_0
0x1800121c8  mov     [rbp+40h], eax
0x1800121cb  jmp     short loc_1800121D4
0x1800121cd  mov     dword ptr [rbp+40h], 0
0x1800121d4  mov     eax, [rbp+40h]
0x1800121d7  add     rsp, 20h
0x1800121db  pop     rbp
0x1800121dc  retn
0x1800121de  push    rbp
0x1800121e0  sub     rsp, 20h
0x1800121e4  mov     rbp, rdx
0x1800121e7  mov     rax, [rcx]
0x1800121ea  mov     edx, [rax]
0x1800121ec  mov     [rbp+0B8h], rcx
0x1800121f3  mov     [rbp+48h], edx
0x1800121f6  mov     eax, [rbp+48h]
0x1800121f9  cmp     eax, 0E06D7363h
0x1800121fe  jnz     short loc_180012214
0x180012200  mov     rdx, [rbp+0B8h]
0x180012207  mov     ecx, [rbp+48h]
0x18001220a  call    _XcptFilter_0
0x18001220f  mov     [rbp+50h], eax
0x180012212  jmp     short loc_18001221B
0x180012214  mov     dword ptr [rbp+50h], 0
0x18001221b  mov     eax, [rbp+50h]
0x18001221e  add     rsp, 20h
0x180012222  pop     rbp
0x180012223  retn
0x180012225  push    rbp
0x180012227  sub     rsp, 20h
0x18001222b  mov     rbp, rdx
0x18001222e  mov     rax, [rcx]
0x180012231  mov     edx, [rax]
0x180012233  mov     [rbp+0C0h], rcx
0x18001223a  mov     [rbp+58h], edx
0x18001223d  mov     eax, [rbp+58h]
0x180012240  cmp     eax, 0E06D7363h
0x180012245  jnz     short loc_18001225B
0x180012247  mov     rdx, [rbp+0C0h]
0x18001224e  mov     ecx, [rbp+58h]
0x180012251  call    _XcptFilter_0
0x180012256  mov     [rbp+60h], eax
0x180012259  jmp     short loc_180012262
0x18001225b  mov     dword ptr [rbp+60h], 0
0x180012262  mov     eax, [rbp+60h]
0x180012265  add     rsp, 20h
0x180012269  pop     rbp
0x18001226a  retn
0x18001226c  push    rbp
0x18001226e  sub     rsp, 20h
0x180012272  mov     rbp, rdx
0x180012275  mov     rax, [rcx]
0x180012278  mov     edx, [rax]
0x18001227a  mov     [rbp+0C8h], rcx
0x180012281  mov     [rbp+68h], edx
0x180012284  mov     eax, [rbp+68h]
0x180012287  cmp     eax, 0E06D7363h
0x18001228c  jnz     short loc_1800122A2
0x18001228e  mov     rdx, [rbp+0C8h]
0x180012295  mov     ecx, [rbp+68h]
0x180012298  call    _XcptFilter_0
0x18001229d  mov     [rbp+70h], eax
0x1800122a0  jmp     short loc_1800122A9
0x1800122a2  mov     dword ptr [rbp+70h], 0
0x1800122a9  mov     eax, [rbp+70h]
0x1800122ac  add     rsp, 20h
0x1800122b0  pop     rbp
0x1800122b1  retn
0x1800122b3  push    rbp
0x1800122b5  sub     rsp, 20h
0x1800122b9  mov     rbp, rdx
0x1800122bc  mov     rax, [rcx]
0x1800122bf  mov     edx, [rax]
0x1800122c1  mov     [rbp+0D0h], rcx
0x1800122c8  mov     [rbp+78h], edx
0x1800122cb  mov     eax, [rbp+78h]
0x1800122ce  cmp     eax, 0E06D7363h
0x1800122d3  jnz     short loc_1800122EC
0x1800122d5  mov     rdx, [rbp+0D0h]
0x1800122dc  mov     ecx, [rbp+78h]
0x1800122df  call    _XcptFilter_0
0x1800122e4  mov     [rbp+80h], eax
0x1800122ea  jmp     short loc_1800122F6
0x1800122ec  mov     dword ptr [rbp+80h], 0
0x1800122f6  mov     eax, [rbp+80h]
0x1800122fc  add     rsp, 20h
0x180012300  pop     rbp
0x180012301  retn
0x180012303  push    rbp
0x180012305  sub     rsp, 20h
0x180012309  mov     rbp, rdx
0x18001230c  mov     rax, [rcx]
0x18001230f  mov     edx, [rax]
0x180012311  mov     [rbp+0D8h], rcx
0x180012318  mov     [rbp+88h], edx
0x18001231e  mov     eax, [rbp+88h]
0x180012324  cmp     eax, 0E06D7363h
0x180012329  jnz     short loc_180012345
0x18001232b  mov     rdx, [rbp+0D8h]
0x180012332  mov     ecx, [rbp+88h]
0x180012338  call    _XcptFilter_0
0x18001233d  mov     [rbp+90h], eax
0x180012343  jmp     short loc_18001234F
0x180012345  mov     dword ptr [rbp+90h], 0
0x18001234f  mov     eax, [rbp+90h]
0x180012355  add     rsp, 20h
0x180012359  pop     rbp
0x18001235a  retn
0x18001235c  push    rbp
0x18001235e  sub     rsp, 20h
0x180012362  mov     rbp, rdx
0x180012365  mov     rax, [rcx]
0x180012368  mov     edx, [rax]
0x18001236a  mov     [rbp+0E0h], rcx
0x180012371  mov     [rbp+98h], edx
0x180012377  mov     eax, [rbp+98h]
0x18001237d  cmp     eax, 0E06D7363h
0x180012382  jnz     short loc_18001239E
0x180012384  mov     rdx, [rbp+0E0h]
0x18001238b  mov     ecx, [rbp+98h]
0x180012391  call    _XcptFilter_0
0x180012396  mov     [rbp+0A0h], eax
0x18001239c  jmp     short loc_1800123A8
0x18001239e  mov     dword ptr [rbp+0A0h], 0
0x1800123a8  mov     eax, [rbp+0A0h]
0x1800123ae  add     rsp, 20h
0x1800123b2  pop     rbp
0x1800123b3  retn
0x1800123b5  push    rbp
0x1800123b7  sub     rsp, 20h
0x1800123bb  mov     rbp, rdx
0x1800123be  cmp     dword ptr [rbp+118h], 1
0x1800123c5  ja      short loc_1800123D1
0x1800123c7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

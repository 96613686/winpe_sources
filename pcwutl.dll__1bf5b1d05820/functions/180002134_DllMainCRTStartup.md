# __DllMainCRTStartup

- ea: `0x180002134`
- end: `0x180002340`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800020f0`

## callees

- `0x180001ec0`
- `0x180002134`
- `0x180002826`
- `0x1800029f8`
- `0x180019260`

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
  if ( (_DWORD)fdwReason || dword_1800262EC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800262F0 = 1;
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
            if ( dword_1800262F0 )
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
0x180002134  mov     [rsp+lpvReserved], r8
0x180002139  mov     [rsp+arg_8], edx
0x18000213d  mov     [rsp+arg_0], rcx
0x180002142  push    rbx
0x180002143  push    rsi
0x180002144  push    rdi
0x180002145  sub     rsp, 0F0h
0x18000214c  mov     edi, edx
0x18000214e  mov     rsi, rcx
0x180002151  mov     ebx, 1
0x180002156  cmp     edx, ebx
0x180002158  ja      short loc_180002160
0x18000215a  mov     cs:__native_dllmain_reason, edx
0x180002160  test    edx, edx
0x180002162  jnz     short loc_180002177
0x180002164  cmp     cs:dword_1800262EC, edx
0x18000216a  jnz     short loc_180002177
0x18000216c  xor     ebx, ebx
0x18000216e  mov     [rsp+108h+var_E8], ebx
0x180002172  jmp     loc_180002324
0x180002177  lea     eax, [rdx-1]
0x18000217a  cmp     eax, 1
0x18000217d  ja      loc_180002204
0x180002183  mov     rax, cs:_pRawDllMain
0x18000218a  test    rax, rax
0x18000218d  jz      short loc_1800021C5
0x18000218f  cmp     edx, 1
0x180002192  jnz     short loc_18000219A
0x180002194  mov     cs:dword_1800262F0, edx
0x18000219a  mov     r8, [rsp+108h+lpvReserved]
0x1800021a2  call    cs:__guard_dispatch_icall_fptr
0x1800021a8  mov     ebx, eax
0x1800021aa  mov     [rsp+108h+var_E8], eax
0x1800021ae  jmp     short loc_1800021C5
0x1800021b0  xor     ebx, ebx
0x1800021b2  mov     [rsp+108h+var_E8], ebx
0x1800021b6  mov     edi, [rsp+108h+arg_8]
0x1800021bd  mov     rsi, [rsp+108h+arg_0]
0x1800021c5  test    ebx, ebx
0x1800021c7  jz      loc_180002324
0x1800021cd  mov     r8, [rsp+108h+lpvReserved]
0x1800021d5  mov     edx, edi
0x1800021d7  mov     rcx, rsi
0x1800021da  call    _CRT_INIT
0x1800021df  mov     ebx, eax
0x1800021e1  mov     [rsp+108h+var_E8], eax
0x1800021e5  jmp     short loc_1800021FC
0x1800021e7  xor     ebx, ebx
0x1800021e9  mov     [rsp+108h+var_E8], ebx
0x1800021ed  mov     edi, [rsp+108h+arg_8]
0x1800021f4  mov     rsi, [rsp+108h+arg_0]
0x1800021fc  test    ebx, ebx
0x1800021fe  jz      loc_180002324
0x180002204  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000220c  mov     edx, edi; fdwReason
0x18000220e  mov     rcx, rsi; hinstDLL
0x180002211  call    DllMain
0x180002216  mov     ebx, eax
0x180002218  mov     [rsp+108h+var_E8], eax
0x18000221c  jmp     short loc_180002233
0x18000221e  xor     ebx, ebx
0x180002220  mov     [rsp+108h+var_E8], ebx
0x180002224  mov     edi, [rsp+108h+arg_8]
0x18000222b  mov     rsi, [rsp+108h+arg_0]
0x180002233  cmp     edi, 1
0x180002236  jnz     short loc_1800022AF
0x180002238  test    ebx, ebx
0x18000223a  jnz     short loc_1800022AF
0x18000223c  xor     r8d, r8d; lpvReserved
0x18000223f  xor     edx, edx; fdwReason
0x180002241  mov     rcx, rsi; hinstDLL
0x180002244  call    DllMain
0x180002249  jmp     short loc_18000225E
0x18000224b  mov     edi, [rsp+108h+arg_8]
0x180002252  mov     rsi, [rsp+108h+arg_0]
0x18000225a  mov     ebx, [rsp+108h+var_E8]
0x18000225e  xor     r8d, r8d
0x180002261  xor     edx, edx
0x180002263  mov     rcx, rsi
0x180002266  call    _CRT_INIT
0x18000226b  jmp     short loc_180002280
0x18000226d  mov     edi, [rsp+108h+arg_8]
0x180002274  mov     rsi, [rsp+108h+arg_0]
0x18000227c  mov     ebx, [rsp+108h+var_E8]
0x180002280  mov     rax, cs:_pRawDllMain
0x180002287  test    rax, rax
0x18000228a  jz      short loc_1800022AF
0x18000228c  xor     r8d, r8d
0x18000228f  xor     edx, edx
0x180002291  mov     rcx, rsi
0x180002294  call    cs:__guard_dispatch_icall_fptr
0x18000229a  jmp     short loc_1800022AF
0x18000229c  mov     edi, [rsp+108h+arg_8]
0x1800022a3  mov     rsi, [rsp+108h+arg_0]
0x1800022ab  mov     ebx, [rsp+108h+var_E8]
0x1800022af  test    edi, edi
0x1800022b1  jz      short loc_1800022B8
0x1800022b3  cmp     edi, 3
0x1800022b6  jnz     short loc_180002324
0x1800022b8  mov     r8, [rsp+108h+lpvReserved]
0x1800022c0  mov     edx, edi
0x1800022c2  mov     rcx, rsi
0x1800022c5  call    _CRT_INIT
0x1800022ca  mov     ebx, eax
0x1800022cc  mov     [rsp+108h+var_E8], eax
0x1800022d0  jmp     short loc_1800022E7
0x1800022d2  xor     ebx, ebx
0x1800022d4  mov     [rsp+108h+var_E8], ebx
0x1800022d8  mov     edi, [rsp+108h+arg_8]
0x1800022df  mov     rsi, [rsp+108h+arg_0]
0x1800022e7  mov     rax, cs:_pRawDllMain
0x1800022ee  test    rax, rax
0x1800022f1  jz      short loc_180002324
0x1800022f3  cmp     cs:dword_1800262F0, 0
0x1800022fa  jz      short loc_180002324
0x1800022fc  mov     r8, [rsp+108h+lpvReserved]
0x180002304  mov     edx, edi
0x180002306  mov     rcx, rsi
0x180002309  call    cs:__guard_dispatch_icall_fptr
0x18000230f  mov     ebx, eax
0x180002311  mov     [rsp+108h+var_E8], eax
0x180002315  jmp     short loc_180002324
0x180002317  xor     ebx, ebx
0x180002319  mov     [rsp+108h+var_E8], ebx
0x18000231d  mov     edi, [rsp+108h+arg_8]
0x180002324  cmp     edi, 1
0x180002327  ja      short loc_180002333
0x180002329  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002333  mov     eax, ebx
0x180002335  add     rsp, 0F0h
0x18000233c  pop     rdi
0x18000233d  pop     rsi
0x18000233e  pop     rbx
0x18000233f  retn
0x180019372  push    rbp
0x180019374  sub     rsp, 20h
0x180019378  mov     rbp, rdx
0x18001937b  mov     rax, [rcx]
0x18001937e  mov     edx, [rax]
0x180019380  mov     [rbp+0A8h], rcx
0x180019387  mov     [rbp+28h], edx
0x18001938a  mov     eax, [rbp+28h]
0x18001938d  cmp     eax, 0E06D7363h
0x180019392  jnz     short loc_1800193A8
0x180019394  mov     rdx, [rbp+0A8h]
0x18001939b  mov     ecx, [rbp+28h]
0x18001939e  call    _XcptFilter_0
0x1800193a3  mov     [rbp+30h], eax
0x1800193a6  jmp     short loc_1800193AF
0x1800193a8  mov     dword ptr [rbp+30h], 0
0x1800193af  mov     eax, [rbp+30h]
0x1800193b2  add     rsp, 20h
0x1800193b6  pop     rbp
0x1800193b7  retn
0x1800193b9  push    rbp
0x1800193bb  sub     rsp, 20h
0x1800193bf  mov     rbp, rdx
0x1800193c2  mov     rax, [rcx]
0x1800193c5  mov     edx, [rax]
0x1800193c7  mov     [rbp+0B0h], rcx
0x1800193ce  mov     [rbp+38h], edx
0x1800193d1  mov     eax, [rbp+38h]
0x1800193d4  cmp     eax, 0E06D7363h
0x1800193d9  jnz     short loc_1800193EF
0x1800193db  mov     rdx, [rbp+0B0h]
0x1800193e2  mov     ecx, [rbp+38h]
0x1800193e5  call    _XcptFilter_0
0x1800193ea  mov     [rbp+40h], eax
0x1800193ed  jmp     short loc_1800193F6
0x1800193ef  mov     dword ptr [rbp+40h], 0
0x1800193f6  mov     eax, [rbp+40h]
0x1800193f9  add     rsp, 20h
0x1800193fd  pop     rbp
0x1800193fe  retn
0x180019400  push    rbp
0x180019402  sub     rsp, 20h
0x180019406  mov     rbp, rdx
0x180019409  mov     rax, [rcx]
0x18001940c  mov     edx, [rax]
0x18001940e  mov     [rbp+0B8h], rcx
0x180019415  mov     [rbp+48h], edx
0x180019418  mov     eax, [rbp+48h]
0x18001941b  cmp     eax, 0E06D7363h
0x180019420  jnz     short loc_180019436
0x180019422  mov     rdx, [rbp+0B8h]
0x180019429  mov     ecx, [rbp+48h]
0x18001942c  call    _XcptFilter_0
0x180019431  mov     [rbp+50h], eax
0x180019434  jmp     short loc_18001943D
0x180019436  mov     dword ptr [rbp+50h], 0
0x18001943d  mov     eax, [rbp+50h]
0x180019440  add     rsp, 20h
0x180019444  pop     rbp
0x180019445  retn
0x180019447  push    rbp
0x180019449  sub     rsp, 20h
0x18001944d  mov     rbp, rdx
0x180019450  mov     rax, [rcx]
0x180019453  mov     edx, [rax]
0x180019455  mov     [rbp+0C0h], rcx
0x18001945c  mov     [rbp+58h], edx
0x18001945f  mov     eax, [rbp+58h]
0x180019462  cmp     eax, 0E06D7363h
0x180019467  jnz     short loc_18001947D
0x180019469  mov     rdx, [rbp+0C0h]
0x180019470  mov     ecx, [rbp+58h]
0x180019473  call    _XcptFilter_0
0x180019478  mov     [rbp+60h], eax
0x18001947b  jmp     short loc_180019484
0x18001947d  mov     dword ptr [rbp+60h], 0
0x180019484  mov     eax, [rbp+60h]
0x180019487  add     rsp, 20h
0x18001948b  pop     rbp
0x18001948c  retn
0x18001948e  push    rbp
0x180019490  sub     rsp, 20h
0x180019494  mov     rbp, rdx
0x180019497  mov     rax, [rcx]
0x18001949a  mov     edx, [rax]
0x18001949c  mov     [rbp+0C8h], rcx
0x1800194a3  mov     [rbp+68h], edx
0x1800194a6  mov     eax, [rbp+68h]
0x1800194a9  cmp     eax, 0E06D7363h
0x1800194ae  jnz     short loc_1800194C4
0x1800194b0  mov     rdx, [rbp+0C8h]
0x1800194b7  mov     ecx, [rbp+68h]
0x1800194ba  call    _XcptFilter_0
0x1800194bf  mov     [rbp+70h], eax
0x1800194c2  jmp     short loc_1800194CB
0x1800194c4  mov     dword ptr [rbp+70h], 0
0x1800194cb  mov     eax, [rbp+70h]
0x1800194ce  add     rsp, 20h
0x1800194d2  pop     rbp
0x1800194d3  retn
0x1800194d5  push    rbp
0x1800194d7  sub     rsp, 20h
0x1800194db  mov     rbp, rdx
0x1800194de  mov     rax, [rcx]
0x1800194e1  mov     edx, [rax]
0x1800194e3  mov     [rbp+0D0h], rcx
0x1800194ea  mov     [rbp+78h], edx
0x1800194ed  mov     eax, [rbp+78h]
0x1800194f0  cmp     eax, 0E06D7363h
0x1800194f5  jnz     short loc_18001950E
0x1800194f7  mov     rdx, [rbp+0D0h]
0x1800194fe  mov     ecx, [rbp+78h]
0x180019501  call    _XcptFilter_0
0x180019506  mov     [rbp+80h], eax
0x18001950c  jmp     short loc_180019518
0x18001950e  mov     dword ptr [rbp+80h], 0
0x180019518  mov     eax, [rbp+80h]
0x18001951e  add     rsp, 20h
0x180019522  pop     rbp
0x180019523  retn
0x180019525  push    rbp
0x180019527  sub     rsp, 20h
0x18001952b  mov     rbp, rdx
0x18001952e  mov     rax, [rcx]
0x180019531  mov     edx, [rax]
0x180019533  mov     [rbp+0D8h], rcx
0x18001953a  mov     [rbp+88h], edx
0x180019540  mov     eax, [rbp+88h]
0x180019546  cmp     eax, 0E06D7363h
0x18001954b  jnz     short loc_180019567
0x18001954d  mov     rdx, [rbp+0D8h]
0x180019554  mov     ecx, [rbp+88h]
0x18001955a  call    _XcptFilter_0
0x18001955f  mov     [rbp+90h], eax
0x180019565  jmp     short loc_180019571
0x180019567  mov     dword ptr [rbp+90h], 0
0x180019571  mov     eax, [rbp+90h]
0x180019577  add     rsp, 20h
0x18001957b  pop     rbp
0x18001957c  retn
0x18001957e  push    rbp
0x180019580  sub     rsp, 20h
0x180019584  mov     rbp, rdx
0x180019587  mov     rax, [rcx]
0x18001958a  mov     edx, [rax]
0x18001958c  mov     [rbp+0E0h], rcx
0x180019593  mov     [rbp+98h], edx
0x180019599  mov     eax, [rbp+98h]
0x18001959f  cmp     eax, 0E06D7363h
0x1800195a4  jnz     short loc_1800195C0
0x1800195a6  mov     rdx, [rbp+0E0h]
0x1800195ad  mov     ecx, [rbp+98h]
0x1800195b3  call    _XcptFilter_0
0x1800195b8  mov     [rbp+0A0h], eax
0x1800195be  jmp     short loc_1800195CA
0x1800195c0  mov     dword ptr [rbp+0A0h], 0
0x1800195ca  mov     eax, [rbp+0A0h]
0x1800195d0  add     rsp, 20h
0x1800195d4  pop     rbp
0x1800195d5  retn
0x1800195d7  push    rbp
0x1800195d9  sub     rsp, 20h
0x1800195dd  mov     rbp, rdx
0x1800195e0  cmp     dword ptr [rbp+118h], 1
0x1800195e7  ja      short loc_1800195F3
0x1800195e9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

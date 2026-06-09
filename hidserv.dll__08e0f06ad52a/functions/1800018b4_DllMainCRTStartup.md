# __DllMainCRTStartup

- ea: `0x1800018b4`
- end: `0x180001ac0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001870`

## callees

- `0x180001640`
- `0x1800018b4`
- `0x180001ac6`
- `0x180001f8c`
- `0x180008490`

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
  if ( (_DWORD)fdwReason || dword_18000D160 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000D164 = 1;
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
            if ( dword_18000D164 )
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
0x1800018b4  mov     [rsp+lpvReserved], r8
0x1800018b9  mov     [rsp+arg_8], edx
0x1800018bd  mov     [rsp+arg_0], rcx
0x1800018c2  push    rbx
0x1800018c3  push    rsi
0x1800018c4  push    rdi
0x1800018c5  sub     rsp, 0F0h
0x1800018cc  mov     edi, edx
0x1800018ce  mov     rsi, rcx
0x1800018d1  mov     ebx, 1
0x1800018d6  cmp     edx, ebx
0x1800018d8  ja      short loc_1800018E0
0x1800018da  mov     cs:__native_dllmain_reason, edx
0x1800018e0  test    edx, edx
0x1800018e2  jnz     short loc_1800018F7
0x1800018e4  cmp     cs:dword_18000D160, edx
0x1800018ea  jnz     short loc_1800018F7
0x1800018ec  xor     ebx, ebx
0x1800018ee  mov     [rsp+108h+var_E8], ebx
0x1800018f2  jmp     loc_180001AA4
0x1800018f7  lea     eax, [rdx-1]
0x1800018fa  cmp     eax, 1
0x1800018fd  ja      loc_180001984
0x180001903  mov     rax, cs:_pRawDllMain
0x18000190a  test    rax, rax
0x18000190d  jz      short loc_180001945
0x18000190f  cmp     edx, 1
0x180001912  jnz     short loc_18000191A
0x180001914  mov     cs:dword_18000D164, edx
0x18000191a  mov     r8, [rsp+108h+lpvReserved]
0x180001922  call    cs:__guard_dispatch_icall_fptr
0x180001928  mov     ebx, eax
0x18000192a  mov     [rsp+108h+var_E8], eax
0x18000192e  jmp     short loc_180001945
0x180001930  xor     ebx, ebx
0x180001932  mov     [rsp+108h+var_E8], ebx
0x180001936  mov     edi, [rsp+108h+arg_8]
0x18000193d  mov     rsi, [rsp+108h+arg_0]
0x180001945  test    ebx, ebx
0x180001947  jz      loc_180001AA4
0x18000194d  mov     r8, [rsp+108h+lpvReserved]
0x180001955  mov     edx, edi
0x180001957  mov     rcx, rsi
0x18000195a  call    _CRT_INIT
0x18000195f  mov     ebx, eax
0x180001961  mov     [rsp+108h+var_E8], eax
0x180001965  jmp     short loc_18000197C
0x180001967  xor     ebx, ebx
0x180001969  mov     [rsp+108h+var_E8], ebx
0x18000196d  mov     edi, [rsp+108h+arg_8]
0x180001974  mov     rsi, [rsp+108h+arg_0]
0x18000197c  test    ebx, ebx
0x18000197e  jz      loc_180001AA4
0x180001984  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000198c  mov     edx, edi; fdwReason
0x18000198e  mov     rcx, rsi; hinstDLL
0x180001991  call    DllMain
0x180001996  mov     ebx, eax
0x180001998  mov     [rsp+108h+var_E8], eax
0x18000199c  jmp     short loc_1800019B3
0x18000199e  xor     ebx, ebx
0x1800019a0  mov     [rsp+108h+var_E8], ebx
0x1800019a4  mov     edi, [rsp+108h+arg_8]
0x1800019ab  mov     rsi, [rsp+108h+arg_0]
0x1800019b3  cmp     edi, 1
0x1800019b6  jnz     short loc_180001A2F
0x1800019b8  test    ebx, ebx
0x1800019ba  jnz     short loc_180001A2F
0x1800019bc  xor     r8d, r8d; lpvReserved
0x1800019bf  xor     edx, edx; fdwReason
0x1800019c1  mov     rcx, rsi; hinstDLL
0x1800019c4  call    DllMain
0x1800019c9  jmp     short loc_1800019DE
0x1800019cb  mov     edi, [rsp+108h+arg_8]
0x1800019d2  mov     rsi, [rsp+108h+arg_0]
0x1800019da  mov     ebx, [rsp+108h+var_E8]
0x1800019de  xor     r8d, r8d
0x1800019e1  xor     edx, edx
0x1800019e3  mov     rcx, rsi
0x1800019e6  call    _CRT_INIT
0x1800019eb  jmp     short loc_180001A00
0x1800019ed  mov     edi, [rsp+108h+arg_8]
0x1800019f4  mov     rsi, [rsp+108h+arg_0]
0x1800019fc  mov     ebx, [rsp+108h+var_E8]
0x180001a00  mov     rax, cs:_pRawDllMain
0x180001a07  test    rax, rax
0x180001a0a  jz      short loc_180001A2F
0x180001a0c  xor     r8d, r8d
0x180001a0f  xor     edx, edx
0x180001a11  mov     rcx, rsi
0x180001a14  call    cs:__guard_dispatch_icall_fptr
0x180001a1a  jmp     short loc_180001A2F
0x180001a1c  mov     edi, [rsp+108h+arg_8]
0x180001a23  mov     rsi, [rsp+108h+arg_0]
0x180001a2b  mov     ebx, [rsp+108h+var_E8]
0x180001a2f  test    edi, edi
0x180001a31  jz      short loc_180001A38
0x180001a33  cmp     edi, 3
0x180001a36  jnz     short loc_180001AA4
0x180001a38  mov     r8, [rsp+108h+lpvReserved]
0x180001a40  mov     edx, edi
0x180001a42  mov     rcx, rsi
0x180001a45  call    _CRT_INIT
0x180001a4a  mov     ebx, eax
0x180001a4c  mov     [rsp+108h+var_E8], eax
0x180001a50  jmp     short loc_180001A67
0x180001a52  xor     ebx, ebx
0x180001a54  mov     [rsp+108h+var_E8], ebx
0x180001a58  mov     edi, [rsp+108h+arg_8]
0x180001a5f  mov     rsi, [rsp+108h+arg_0]
0x180001a67  mov     rax, cs:_pRawDllMain
0x180001a6e  test    rax, rax
0x180001a71  jz      short loc_180001AA4
0x180001a73  cmp     cs:dword_18000D164, 0
0x180001a7a  jz      short loc_180001AA4
0x180001a7c  mov     r8, [rsp+108h+lpvReserved]
0x180001a84  mov     edx, edi
0x180001a86  mov     rcx, rsi
0x180001a89  call    cs:__guard_dispatch_icall_fptr
0x180001a8f  mov     ebx, eax
0x180001a91  mov     [rsp+108h+var_E8], eax
0x180001a95  jmp     short loc_180001AA4
0x180001a97  xor     ebx, ebx
0x180001a99  mov     [rsp+108h+var_E8], ebx
0x180001a9d  mov     edi, [rsp+108h+arg_8]
0x180001aa4  cmp     edi, 1
0x180001aa7  ja      short loc_180001AB3
0x180001aa9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ab3  mov     eax, ebx
0x180001ab5  add     rsp, 0F0h
0x180001abc  pop     rdi
0x180001abd  pop     rsi
0x180001abe  pop     rbx
0x180001abf  retn
0x180008500  push    rbp
0x180008502  sub     rsp, 20h
0x180008506  mov     rbp, rdx
0x180008509  mov     rax, [rcx]
0x18000850c  mov     edx, [rax]
0x18000850e  mov     [rbp+0A8h], rcx
0x180008515  mov     [rbp+28h], edx
0x180008518  mov     eax, [rbp+28h]
0x18000851b  cmp     eax, 0E06D7363h
0x180008520  jnz     short loc_180008536
0x180008522  mov     rdx, [rbp+0A8h]
0x180008529  mov     ecx, [rbp+28h]
0x18000852c  call    _XcptFilter_0
0x180008531  mov     [rbp+30h], eax
0x180008534  jmp     short loc_18000853D
0x180008536  mov     dword ptr [rbp+30h], 0
0x18000853d  mov     eax, [rbp+30h]
0x180008540  add     rsp, 20h
0x180008544  pop     rbp
0x180008545  retn
0x180008547  push    rbp
0x180008549  sub     rsp, 20h
0x18000854d  mov     rbp, rdx
0x180008550  mov     rax, [rcx]
0x180008553  mov     edx, [rax]
0x180008555  mov     [rbp+0B0h], rcx
0x18000855c  mov     [rbp+38h], edx
0x18000855f  mov     eax, [rbp+38h]
0x180008562  cmp     eax, 0E06D7363h
0x180008567  jnz     short loc_18000857D
0x180008569  mov     rdx, [rbp+0B0h]
0x180008570  mov     ecx, [rbp+38h]
0x180008573  call    _XcptFilter_0
0x180008578  mov     [rbp+40h], eax
0x18000857b  jmp     short loc_180008584
0x18000857d  mov     dword ptr [rbp+40h], 0
0x180008584  mov     eax, [rbp+40h]
0x180008587  add     rsp, 20h
0x18000858b  pop     rbp
0x18000858c  retn
0x18000858e  push    rbp
0x180008590  sub     rsp, 20h
0x180008594  mov     rbp, rdx
0x180008597  mov     rax, [rcx]
0x18000859a  mov     edx, [rax]
0x18000859c  mov     [rbp+0B8h], rcx
0x1800085a3  mov     [rbp+48h], edx
0x1800085a6  mov     eax, [rbp+48h]
0x1800085a9  cmp     eax, 0E06D7363h
0x1800085ae  jnz     short loc_1800085C4
0x1800085b0  mov     rdx, [rbp+0B8h]
0x1800085b7  mov     ecx, [rbp+48h]
0x1800085ba  call    _XcptFilter_0
0x1800085bf  mov     [rbp+50h], eax
0x1800085c2  jmp     short loc_1800085CB
0x1800085c4  mov     dword ptr [rbp+50h], 0
0x1800085cb  mov     eax, [rbp+50h]
0x1800085ce  add     rsp, 20h
0x1800085d2  pop     rbp
0x1800085d3  retn
0x1800085d5  push    rbp
0x1800085d7  sub     rsp, 20h
0x1800085db  mov     rbp, rdx
0x1800085de  mov     rax, [rcx]
0x1800085e1  mov     edx, [rax]
0x1800085e3  mov     [rbp+0C0h], rcx
0x1800085ea  mov     [rbp+58h], edx
0x1800085ed  mov     eax, [rbp+58h]
0x1800085f0  cmp     eax, 0E06D7363h
0x1800085f5  jnz     short loc_18000860B
0x1800085f7  mov     rdx, [rbp+0C0h]
0x1800085fe  mov     ecx, [rbp+58h]
0x180008601  call    _XcptFilter_0
0x180008606  mov     [rbp+60h], eax
0x180008609  jmp     short loc_180008612
0x18000860b  mov     dword ptr [rbp+60h], 0
0x180008612  mov     eax, [rbp+60h]
0x180008615  add     rsp, 20h
0x180008619  pop     rbp
0x18000861a  retn
0x18000861c  push    rbp
0x18000861e  sub     rsp, 20h
0x180008622  mov     rbp, rdx
0x180008625  mov     rax, [rcx]
0x180008628  mov     edx, [rax]
0x18000862a  mov     [rbp+0C8h], rcx
0x180008631  mov     [rbp+68h], edx
0x180008634  mov     eax, [rbp+68h]
0x180008637  cmp     eax, 0E06D7363h
0x18000863c  jnz     short loc_180008652
0x18000863e  mov     rdx, [rbp+0C8h]
0x180008645  mov     ecx, [rbp+68h]
0x180008648  call    _XcptFilter_0
0x18000864d  mov     [rbp+70h], eax
0x180008650  jmp     short loc_180008659
0x180008652  mov     dword ptr [rbp+70h], 0
0x180008659  mov     eax, [rbp+70h]
0x18000865c  add     rsp, 20h
0x180008660  pop     rbp
0x180008661  retn
0x180008663  push    rbp
0x180008665  sub     rsp, 20h
0x180008669  mov     rbp, rdx
0x18000866c  mov     rax, [rcx]
0x18000866f  mov     edx, [rax]
0x180008671  mov     [rbp+0D0h], rcx
0x180008678  mov     [rbp+78h], edx
0x18000867b  mov     eax, [rbp+78h]
0x18000867e  cmp     eax, 0E06D7363h
0x180008683  jnz     short loc_18000869C
0x180008685  mov     rdx, [rbp+0D0h]
0x18000868c  mov     ecx, [rbp+78h]
0x18000868f  call    _XcptFilter_0
0x180008694  mov     [rbp+80h], eax
0x18000869a  jmp     short loc_1800086A6
0x18000869c  mov     dword ptr [rbp+80h], 0
0x1800086a6  mov     eax, [rbp+80h]
0x1800086ac  add     rsp, 20h
0x1800086b0  pop     rbp
0x1800086b1  retn
0x1800086b3  push    rbp
0x1800086b5  sub     rsp, 20h
0x1800086b9  mov     rbp, rdx
0x1800086bc  mov     rax, [rcx]
0x1800086bf  mov     edx, [rax]
0x1800086c1  mov     [rbp+0D8h], rcx
0x1800086c8  mov     [rbp+88h], edx
0x1800086ce  mov     eax, [rbp+88h]
0x1800086d4  cmp     eax, 0E06D7363h
0x1800086d9  jnz     short loc_1800086F5
0x1800086db  mov     rdx, [rbp+0D8h]
0x1800086e2  mov     ecx, [rbp+88h]
0x1800086e8  call    _XcptFilter_0
0x1800086ed  mov     [rbp+90h], eax
0x1800086f3  jmp     short loc_1800086FF
0x1800086f5  mov     dword ptr [rbp+90h], 0
0x1800086ff  mov     eax, [rbp+90h]
0x180008705  add     rsp, 20h
0x180008709  pop     rbp
0x18000870a  retn
0x18000870c  push    rbp
0x18000870e  sub     rsp, 20h
0x180008712  mov     rbp, rdx
0x180008715  mov     rax, [rcx]
0x180008718  mov     edx, [rax]
0x18000871a  mov     [rbp+0E0h], rcx
0x180008721  mov     [rbp+98h], edx
0x180008727  mov     eax, [rbp+98h]
0x18000872d  cmp     eax, 0E06D7363h
0x180008732  jnz     short loc_18000874E
0x180008734  mov     rdx, [rbp+0E0h]
0x18000873b  mov     ecx, [rbp+98h]
0x180008741  call    _XcptFilter_0
0x180008746  mov     [rbp+0A0h], eax
0x18000874c  jmp     short loc_180008758
0x18000874e  mov     dword ptr [rbp+0A0h], 0
0x180008758  mov     eax, [rbp+0A0h]
0x18000875e  add     rsp, 20h
0x180008762  pop     rbp
0x180008763  retn
0x180008765  push    rbp
0x180008767  sub     rsp, 20h
0x18000876b  mov     rbp, rdx
0x18000876e  cmp     dword ptr [rbp+118h], 1
0x180008775  ja      short loc_180008781
0x180008777  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

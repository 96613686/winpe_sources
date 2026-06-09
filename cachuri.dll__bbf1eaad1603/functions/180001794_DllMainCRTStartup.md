# __DllMainCRTStartup

- ea: `0x180001794`
- end: `0x1800019a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001750`

## callees

- `0x180001520`
- `0x180001794`
- `0x1800019ca`
- `0x180001ba8`
- `0x180002000`

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
  if ( (_DWORD)fdwReason || dword_1800060A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800060A4 = 1;
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
            if ( dword_1800060A4 )
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
0x180001794  mov     [rsp+lpvReserved], r8
0x180001799  mov     [rsp+arg_8], edx
0x18000179d  mov     [rsp+arg_0], rcx
0x1800017a2  push    rbx
0x1800017a3  push    rsi
0x1800017a4  push    rdi
0x1800017a5  sub     rsp, 0F0h
0x1800017ac  mov     edi, edx
0x1800017ae  mov     rsi, rcx
0x1800017b1  mov     ebx, 1
0x1800017b6  cmp     edx, ebx
0x1800017b8  ja      short loc_1800017C0
0x1800017ba  mov     cs:__native_dllmain_reason, edx
0x1800017c0  test    edx, edx
0x1800017c2  jnz     short loc_1800017D7
0x1800017c4  cmp     cs:dword_1800060A0, edx
0x1800017ca  jnz     short loc_1800017D7
0x1800017cc  xor     ebx, ebx
0x1800017ce  mov     [rsp+108h+var_E8], ebx
0x1800017d2  jmp     loc_180001984
0x1800017d7  lea     eax, [rdx-1]
0x1800017da  cmp     eax, 1
0x1800017dd  ja      loc_180001864
0x1800017e3  mov     rax, cs:_pRawDllMain
0x1800017ea  test    rax, rax
0x1800017ed  jz      short loc_180001825
0x1800017ef  cmp     edx, 1
0x1800017f2  jnz     short loc_1800017FA
0x1800017f4  mov     cs:dword_1800060A4, edx
0x1800017fa  mov     r8, [rsp+108h+lpvReserved]
0x180001802  call    cs:__guard_dispatch_icall_fptr
0x180001808  mov     ebx, eax
0x18000180a  mov     [rsp+108h+var_E8], eax
0x18000180e  jmp     short loc_180001825
0x180001810  xor     ebx, ebx
0x180001812  mov     [rsp+108h+var_E8], ebx
0x180001816  mov     edi, [rsp+108h+arg_8]
0x18000181d  mov     rsi, [rsp+108h+arg_0]
0x180001825  test    ebx, ebx
0x180001827  jz      loc_180001984
0x18000182d  mov     r8, [rsp+108h+lpvReserved]
0x180001835  mov     edx, edi
0x180001837  mov     rcx, rsi
0x18000183a  call    _CRT_INIT
0x18000183f  mov     ebx, eax
0x180001841  mov     [rsp+108h+var_E8], eax
0x180001845  jmp     short loc_18000185C
0x180001847  xor     ebx, ebx
0x180001849  mov     [rsp+108h+var_E8], ebx
0x18000184d  mov     edi, [rsp+108h+arg_8]
0x180001854  mov     rsi, [rsp+108h+arg_0]
0x18000185c  test    ebx, ebx
0x18000185e  jz      loc_180001984
0x180001864  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000186c  mov     edx, edi; fdwReason
0x18000186e  mov     rcx, rsi; hinstDLL
0x180001871  call    DllMain
0x180001876  mov     ebx, eax
0x180001878  mov     [rsp+108h+var_E8], eax
0x18000187c  jmp     short loc_180001893
0x18000187e  xor     ebx, ebx
0x180001880  mov     [rsp+108h+var_E8], ebx
0x180001884  mov     edi, [rsp+108h+arg_8]
0x18000188b  mov     rsi, [rsp+108h+arg_0]
0x180001893  cmp     edi, 1
0x180001896  jnz     short loc_18000190F
0x180001898  test    ebx, ebx
0x18000189a  jnz     short loc_18000190F
0x18000189c  xor     r8d, r8d; lpvReserved
0x18000189f  xor     edx, edx; fdwReason
0x1800018a1  mov     rcx, rsi; hinstDLL
0x1800018a4  call    DllMain
0x1800018a9  jmp     short loc_1800018BE
0x1800018ab  mov     edi, [rsp+108h+arg_8]
0x1800018b2  mov     rsi, [rsp+108h+arg_0]
0x1800018ba  mov     ebx, [rsp+108h+var_E8]
0x1800018be  xor     r8d, r8d
0x1800018c1  xor     edx, edx
0x1800018c3  mov     rcx, rsi
0x1800018c6  call    _CRT_INIT
0x1800018cb  jmp     short loc_1800018E0
0x1800018cd  mov     edi, [rsp+108h+arg_8]
0x1800018d4  mov     rsi, [rsp+108h+arg_0]
0x1800018dc  mov     ebx, [rsp+108h+var_E8]
0x1800018e0  mov     rax, cs:_pRawDllMain
0x1800018e7  test    rax, rax
0x1800018ea  jz      short loc_18000190F
0x1800018ec  xor     r8d, r8d
0x1800018ef  xor     edx, edx
0x1800018f1  mov     rcx, rsi
0x1800018f4  call    cs:__guard_dispatch_icall_fptr
0x1800018fa  jmp     short loc_18000190F
0x1800018fc  mov     edi, [rsp+108h+arg_8]
0x180001903  mov     rsi, [rsp+108h+arg_0]
0x18000190b  mov     ebx, [rsp+108h+var_E8]
0x18000190f  test    edi, edi
0x180001911  jz      short loc_180001918
0x180001913  cmp     edi, 3
0x180001916  jnz     short loc_180001984
0x180001918  mov     r8, [rsp+108h+lpvReserved]
0x180001920  mov     edx, edi
0x180001922  mov     rcx, rsi
0x180001925  call    _CRT_INIT
0x18000192a  mov     ebx, eax
0x18000192c  mov     [rsp+108h+var_E8], eax
0x180001930  jmp     short loc_180001947
0x180001932  xor     ebx, ebx
0x180001934  mov     [rsp+108h+var_E8], ebx
0x180001938  mov     edi, [rsp+108h+arg_8]
0x18000193f  mov     rsi, [rsp+108h+arg_0]
0x180001947  mov     rax, cs:_pRawDllMain
0x18000194e  test    rax, rax
0x180001951  jz      short loc_180001984
0x180001953  cmp     cs:dword_1800060A4, 0
0x18000195a  jz      short loc_180001984
0x18000195c  mov     r8, [rsp+108h+lpvReserved]
0x180001964  mov     edx, edi
0x180001966  mov     rcx, rsi
0x180001969  call    cs:__guard_dispatch_icall_fptr
0x18000196f  mov     ebx, eax
0x180001971  mov     [rsp+108h+var_E8], eax
0x180001975  jmp     short loc_180001984
0x180001977  xor     ebx, ebx
0x180001979  mov     [rsp+108h+var_E8], ebx
0x18000197d  mov     edi, [rsp+108h+arg_8]
0x180001984  cmp     edi, 1
0x180001987  ja      short loc_180001993
0x180001989  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001993  mov     eax, ebx
0x180001995  add     rsp, 0F0h
0x18000199c  pop     rdi
0x18000199d  pop     rsi
0x18000199e  pop     rbx
0x18000199f  retn
0x180002070  push    rbp
0x180002072  sub     rsp, 20h
0x180002076  mov     rbp, rdx
0x180002079  mov     rax, [rcx]
0x18000207c  mov     edx, [rax]
0x18000207e  mov     [rbp+0A8h], rcx
0x180002085  mov     [rbp+28h], edx
0x180002088  mov     eax, [rbp+28h]
0x18000208b  cmp     eax, 0E06D7363h
0x180002090  jnz     short loc_1800020A6
0x180002092  mov     rdx, [rbp+0A8h]
0x180002099  mov     ecx, [rbp+28h]
0x18000209c  call    _XcptFilter_0
0x1800020a1  mov     [rbp+30h], eax
0x1800020a4  jmp     short loc_1800020AD
0x1800020a6  mov     dword ptr [rbp+30h], 0
0x1800020ad  mov     eax, [rbp+30h]
0x1800020b0  add     rsp, 20h
0x1800020b4  pop     rbp
0x1800020b5  retn
0x1800020b7  push    rbp
0x1800020b9  sub     rsp, 20h
0x1800020bd  mov     rbp, rdx
0x1800020c0  mov     rax, [rcx]
0x1800020c3  mov     edx, [rax]
0x1800020c5  mov     [rbp+0B0h], rcx
0x1800020cc  mov     [rbp+38h], edx
0x1800020cf  mov     eax, [rbp+38h]
0x1800020d2  cmp     eax, 0E06D7363h
0x1800020d7  jnz     short loc_1800020ED
0x1800020d9  mov     rdx, [rbp+0B0h]
0x1800020e0  mov     ecx, [rbp+38h]
0x1800020e3  call    _XcptFilter_0
0x1800020e8  mov     [rbp+40h], eax
0x1800020eb  jmp     short loc_1800020F4
0x1800020ed  mov     dword ptr [rbp+40h], 0
0x1800020f4  mov     eax, [rbp+40h]
0x1800020f7  add     rsp, 20h
0x1800020fb  pop     rbp
0x1800020fc  retn
0x1800020fe  push    rbp
0x180002100  sub     rsp, 20h
0x180002104  mov     rbp, rdx
0x180002107  mov     rax, [rcx]
0x18000210a  mov     edx, [rax]
0x18000210c  mov     [rbp+0B8h], rcx
0x180002113  mov     [rbp+48h], edx
0x180002116  mov     eax, [rbp+48h]
0x180002119  cmp     eax, 0E06D7363h
0x18000211e  jnz     short loc_180002134
0x180002120  mov     rdx, [rbp+0B8h]
0x180002127  mov     ecx, [rbp+48h]
0x18000212a  call    _XcptFilter_0
0x18000212f  mov     [rbp+50h], eax
0x180002132  jmp     short loc_18000213B
0x180002134  mov     dword ptr [rbp+50h], 0
0x18000213b  mov     eax, [rbp+50h]
0x18000213e  add     rsp, 20h
0x180002142  pop     rbp
0x180002143  retn
0x180002145  push    rbp
0x180002147  sub     rsp, 20h
0x18000214b  mov     rbp, rdx
0x18000214e  mov     rax, [rcx]
0x180002151  mov     edx, [rax]
0x180002153  mov     [rbp+0C0h], rcx
0x18000215a  mov     [rbp+58h], edx
0x18000215d  mov     eax, [rbp+58h]
0x180002160  cmp     eax, 0E06D7363h
0x180002165  jnz     short loc_18000217B
0x180002167  mov     rdx, [rbp+0C0h]
0x18000216e  mov     ecx, [rbp+58h]
0x180002171  call    _XcptFilter_0
0x180002176  mov     [rbp+60h], eax
0x180002179  jmp     short loc_180002182
0x18000217b  mov     dword ptr [rbp+60h], 0
0x180002182  mov     eax, [rbp+60h]
0x180002185  add     rsp, 20h
0x180002189  pop     rbp
0x18000218a  retn
0x18000218c  push    rbp
0x18000218e  sub     rsp, 20h
0x180002192  mov     rbp, rdx
0x180002195  mov     rax, [rcx]
0x180002198  mov     edx, [rax]
0x18000219a  mov     [rbp+0C8h], rcx
0x1800021a1  mov     [rbp+68h], edx
0x1800021a4  mov     eax, [rbp+68h]
0x1800021a7  cmp     eax, 0E06D7363h
0x1800021ac  jnz     short loc_1800021C2
0x1800021ae  mov     rdx, [rbp+0C8h]
0x1800021b5  mov     ecx, [rbp+68h]
0x1800021b8  call    _XcptFilter_0
0x1800021bd  mov     [rbp+70h], eax
0x1800021c0  jmp     short loc_1800021C9
0x1800021c2  mov     dword ptr [rbp+70h], 0
0x1800021c9  mov     eax, [rbp+70h]
0x1800021cc  add     rsp, 20h
0x1800021d0  pop     rbp
0x1800021d1  retn
0x1800021d3  push    rbp
0x1800021d5  sub     rsp, 20h
0x1800021d9  mov     rbp, rdx
0x1800021dc  mov     rax, [rcx]
0x1800021df  mov     edx, [rax]
0x1800021e1  mov     [rbp+0D0h], rcx
0x1800021e8  mov     [rbp+78h], edx
0x1800021eb  mov     eax, [rbp+78h]
0x1800021ee  cmp     eax, 0E06D7363h
0x1800021f3  jnz     short loc_18000220C
0x1800021f5  mov     rdx, [rbp+0D0h]
0x1800021fc  mov     ecx, [rbp+78h]
0x1800021ff  call    _XcptFilter_0
0x180002204  mov     [rbp+80h], eax
0x18000220a  jmp     short loc_180002216
0x18000220c  mov     dword ptr [rbp+80h], 0
0x180002216  mov     eax, [rbp+80h]
0x18000221c  add     rsp, 20h
0x180002220  pop     rbp
0x180002221  retn
0x180002223  push    rbp
0x180002225  sub     rsp, 20h
0x180002229  mov     rbp, rdx
0x18000222c  mov     rax, [rcx]
0x18000222f  mov     edx, [rax]
0x180002231  mov     [rbp+0D8h], rcx
0x180002238  mov     [rbp+88h], edx
0x18000223e  mov     eax, [rbp+88h]
0x180002244  cmp     eax, 0E06D7363h
0x180002249  jnz     short loc_180002265
0x18000224b  mov     rdx, [rbp+0D8h]
0x180002252  mov     ecx, [rbp+88h]
0x180002258  call    _XcptFilter_0
0x18000225d  mov     [rbp+90h], eax
0x180002263  jmp     short loc_18000226F
0x180002265  mov     dword ptr [rbp+90h], 0
0x18000226f  mov     eax, [rbp+90h]
0x180002275  add     rsp, 20h
0x180002279  pop     rbp
0x18000227a  retn
0x18000227c  push    rbp
0x18000227e  sub     rsp, 20h
0x180002282  mov     rbp, rdx
0x180002285  mov     rax, [rcx]
0x180002288  mov     edx, [rax]
0x18000228a  mov     [rbp+0E0h], rcx
0x180002291  mov     [rbp+98h], edx
0x180002297  mov     eax, [rbp+98h]
0x18000229d  cmp     eax, 0E06D7363h
0x1800022a2  jnz     short loc_1800022BE
0x1800022a4  mov     rdx, [rbp+0E0h]
0x1800022ab  mov     ecx, [rbp+98h]
0x1800022b1  call    _XcptFilter_0
0x1800022b6  mov     [rbp+0A0h], eax
0x1800022bc  jmp     short loc_1800022C8
0x1800022be  mov     dword ptr [rbp+0A0h], 0
0x1800022c8  mov     eax, [rbp+0A0h]
0x1800022ce  add     rsp, 20h
0x1800022d2  pop     rbp
0x1800022d3  retn
0x1800022d5  push    rbp
0x1800022d7  sub     rsp, 20h
0x1800022db  mov     rbp, rdx
0x1800022de  cmp     dword ptr [rbp+118h], 1
0x1800022e5  ja      short loc_1800022F1
0x1800022e7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

# __DllMainCRTStartup

- ea: `0x1800015d4`
- end: `0x1800017e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001590`

## callees

- `0x180001360`
- `0x1800015d4`
- `0x180001e3e`
- `0x180013060`
- `0x180018250`

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
  if ( (_DWORD)fdwReason || dword_18002487C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180024880 = 1;
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
            if ( dword_180024880 )
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
0x1800015d4  mov     [rsp+lpvReserved], r8
0x1800015d9  mov     [rsp+arg_8], edx
0x1800015dd  mov     [rsp+arg_0], rcx
0x1800015e2  push    rbx
0x1800015e3  push    rsi
0x1800015e4  push    rdi
0x1800015e5  sub     rsp, 0F0h
0x1800015ec  mov     edi, edx
0x1800015ee  mov     rsi, rcx
0x1800015f1  mov     ebx, 1
0x1800015f6  cmp     edx, ebx
0x1800015f8  ja      short loc_180001600
0x1800015fa  mov     cs:__native_dllmain_reason, edx
0x180001600  test    edx, edx
0x180001602  jnz     short loc_180001617
0x180001604  cmp     cs:dword_18002487C, edx
0x18000160a  jnz     short loc_180001617
0x18000160c  xor     ebx, ebx
0x18000160e  mov     [rsp+108h+var_E8], ebx
0x180001612  jmp     loc_1800017C4
0x180001617  lea     eax, [rdx-1]
0x18000161a  cmp     eax, 1
0x18000161d  ja      loc_1800016A4
0x180001623  mov     rax, cs:_pRawDllMain
0x18000162a  test    rax, rax
0x18000162d  jz      short loc_180001665
0x18000162f  cmp     edx, 1
0x180001632  jnz     short loc_18000163A
0x180001634  mov     cs:dword_180024880, edx
0x18000163a  mov     r8, [rsp+108h+lpvReserved]
0x180001642  call    cs:__guard_dispatch_icall_fptr
0x180001648  mov     ebx, eax
0x18000164a  mov     [rsp+108h+var_E8], eax
0x18000164e  jmp     short loc_180001665
0x180001650  xor     ebx, ebx
0x180001652  mov     [rsp+108h+var_E8], ebx
0x180001656  mov     edi, [rsp+108h+arg_8]
0x18000165d  mov     rsi, [rsp+108h+arg_0]
0x180001665  test    ebx, ebx
0x180001667  jz      loc_1800017C4
0x18000166d  mov     r8, [rsp+108h+lpvReserved]
0x180001675  mov     edx, edi
0x180001677  mov     rcx, rsi
0x18000167a  call    _CRT_INIT
0x18000167f  mov     ebx, eax
0x180001681  mov     [rsp+108h+var_E8], eax
0x180001685  jmp     short loc_18000169C
0x180001687  xor     ebx, ebx
0x180001689  mov     [rsp+108h+var_E8], ebx
0x18000168d  mov     edi, [rsp+108h+arg_8]
0x180001694  mov     rsi, [rsp+108h+arg_0]
0x18000169c  test    ebx, ebx
0x18000169e  jz      loc_1800017C4
0x1800016a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800016ac  mov     edx, edi; fdwReason
0x1800016ae  mov     rcx, rsi; hinstDLL
0x1800016b1  call    DllMain
0x1800016b6  mov     ebx, eax
0x1800016b8  mov     [rsp+108h+var_E8], eax
0x1800016bc  jmp     short loc_1800016D3
0x1800016be  xor     ebx, ebx
0x1800016c0  mov     [rsp+108h+var_E8], ebx
0x1800016c4  mov     edi, [rsp+108h+arg_8]
0x1800016cb  mov     rsi, [rsp+108h+arg_0]
0x1800016d3  cmp     edi, 1
0x1800016d6  jnz     short loc_18000174F
0x1800016d8  test    ebx, ebx
0x1800016da  jnz     short loc_18000174F
0x1800016dc  xor     r8d, r8d; lpvReserved
0x1800016df  xor     edx, edx; fdwReason
0x1800016e1  mov     rcx, rsi; hinstDLL
0x1800016e4  call    DllMain
0x1800016e9  jmp     short loc_1800016FE
0x1800016eb  mov     edi, [rsp+108h+arg_8]
0x1800016f2  mov     rsi, [rsp+108h+arg_0]
0x1800016fa  mov     ebx, [rsp+108h+var_E8]
0x1800016fe  xor     r8d, r8d
0x180001701  xor     edx, edx
0x180001703  mov     rcx, rsi
0x180001706  call    _CRT_INIT
0x18000170b  jmp     short loc_180001720
0x18000170d  mov     edi, [rsp+108h+arg_8]
0x180001714  mov     rsi, [rsp+108h+arg_0]
0x18000171c  mov     ebx, [rsp+108h+var_E8]
0x180001720  mov     rax, cs:_pRawDllMain
0x180001727  test    rax, rax
0x18000172a  jz      short loc_18000174F
0x18000172c  xor     r8d, r8d
0x18000172f  xor     edx, edx
0x180001731  mov     rcx, rsi
0x180001734  call    cs:__guard_dispatch_icall_fptr
0x18000173a  jmp     short loc_18000174F
0x18000173c  mov     edi, [rsp+108h+arg_8]
0x180001743  mov     rsi, [rsp+108h+arg_0]
0x18000174b  mov     ebx, [rsp+108h+var_E8]
0x18000174f  test    edi, edi
0x180001751  jz      short loc_180001758
0x180001753  cmp     edi, 3
0x180001756  jnz     short loc_1800017C4
0x180001758  mov     r8, [rsp+108h+lpvReserved]
0x180001760  mov     edx, edi
0x180001762  mov     rcx, rsi
0x180001765  call    _CRT_INIT
0x18000176a  mov     ebx, eax
0x18000176c  mov     [rsp+108h+var_E8], eax
0x180001770  jmp     short loc_180001787
0x180001772  xor     ebx, ebx
0x180001774  mov     [rsp+108h+var_E8], ebx
0x180001778  mov     edi, [rsp+108h+arg_8]
0x18000177f  mov     rsi, [rsp+108h+arg_0]
0x180001787  mov     rax, cs:_pRawDllMain
0x18000178e  test    rax, rax
0x180001791  jz      short loc_1800017C4
0x180001793  cmp     cs:dword_180024880, 0
0x18000179a  jz      short loc_1800017C4
0x18000179c  mov     r8, [rsp+108h+lpvReserved]
0x1800017a4  mov     edx, edi
0x1800017a6  mov     rcx, rsi
0x1800017a9  call    cs:__guard_dispatch_icall_fptr
0x1800017af  mov     ebx, eax
0x1800017b1  mov     [rsp+108h+var_E8], eax
0x1800017b5  jmp     short loc_1800017C4
0x1800017b7  xor     ebx, ebx
0x1800017b9  mov     [rsp+108h+var_E8], ebx
0x1800017bd  mov     edi, [rsp+108h+arg_8]
0x1800017c4  cmp     edi, 1
0x1800017c7  ja      short loc_1800017D3
0x1800017c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800017d3  mov     eax, ebx
0x1800017d5  add     rsp, 0F0h
0x1800017dc  pop     rdi
0x1800017dd  pop     rsi
0x1800017de  pop     rbx
0x1800017df  retn
0x1800182f3  push    rbp
0x1800182f5  sub     rsp, 20h
0x1800182f9  mov     rbp, rdx
0x1800182fc  mov     rax, [rcx]
0x1800182ff  mov     edx, [rax]
0x180018301  mov     [rbp+0A8h], rcx
0x180018308  mov     [rbp+28h], edx
0x18001830b  mov     eax, [rbp+28h]
0x18001830e  cmp     eax, 0E06D7363h
0x180018313  jnz     short loc_180018329
0x180018315  mov     rdx, [rbp+0A8h]
0x18001831c  mov     ecx, [rbp+28h]
0x18001831f  call    _XcptFilter_0
0x180018324  mov     [rbp+30h], eax
0x180018327  jmp     short loc_180018330
0x180018329  mov     dword ptr [rbp+30h], 0
0x180018330  mov     eax, [rbp+30h]
0x180018333  add     rsp, 20h
0x180018337  pop     rbp
0x180018338  retn
0x18001833a  push    rbp
0x18001833c  sub     rsp, 20h
0x180018340  mov     rbp, rdx
0x180018343  mov     rax, [rcx]
0x180018346  mov     edx, [rax]
0x180018348  mov     [rbp+0B0h], rcx
0x18001834f  mov     [rbp+38h], edx
0x180018352  mov     eax, [rbp+38h]
0x180018355  cmp     eax, 0E06D7363h
0x18001835a  jnz     short loc_180018370
0x18001835c  mov     rdx, [rbp+0B0h]
0x180018363  mov     ecx, [rbp+38h]
0x180018366  call    _XcptFilter_0
0x18001836b  mov     [rbp+40h], eax
0x18001836e  jmp     short loc_180018377
0x180018370  mov     dword ptr [rbp+40h], 0
0x180018377  mov     eax, [rbp+40h]
0x18001837a  add     rsp, 20h
0x18001837e  pop     rbp
0x18001837f  retn
0x180018381  push    rbp
0x180018383  sub     rsp, 20h
0x180018387  mov     rbp, rdx
0x18001838a  mov     rax, [rcx]
0x18001838d  mov     edx, [rax]
0x18001838f  mov     [rbp+0B8h], rcx
0x180018396  mov     [rbp+48h], edx
0x180018399  mov     eax, [rbp+48h]
0x18001839c  cmp     eax, 0E06D7363h
0x1800183a1  jnz     short loc_1800183B7
0x1800183a3  mov     rdx, [rbp+0B8h]
0x1800183aa  mov     ecx, [rbp+48h]
0x1800183ad  call    _XcptFilter_0
0x1800183b2  mov     [rbp+50h], eax
0x1800183b5  jmp     short loc_1800183BE
0x1800183b7  mov     dword ptr [rbp+50h], 0
0x1800183be  mov     eax, [rbp+50h]
0x1800183c1  add     rsp, 20h
0x1800183c5  pop     rbp
0x1800183c6  retn
0x1800183c8  push    rbp
0x1800183ca  sub     rsp, 20h
0x1800183ce  mov     rbp, rdx
0x1800183d1  mov     rax, [rcx]
0x1800183d4  mov     edx, [rax]
0x1800183d6  mov     [rbp+0C0h], rcx
0x1800183dd  mov     [rbp+58h], edx
0x1800183e0  mov     eax, [rbp+58h]
0x1800183e3  cmp     eax, 0E06D7363h
0x1800183e8  jnz     short loc_1800183FE
0x1800183ea  mov     rdx, [rbp+0C0h]
0x1800183f1  mov     ecx, [rbp+58h]
0x1800183f4  call    _XcptFilter_0
0x1800183f9  mov     [rbp+60h], eax
0x1800183fc  jmp     short loc_180018405
0x1800183fe  mov     dword ptr [rbp+60h], 0
0x180018405  mov     eax, [rbp+60h]
0x180018408  add     rsp, 20h
0x18001840c  pop     rbp
0x18001840d  retn
0x18001840f  push    rbp
0x180018411  sub     rsp, 20h
0x180018415  mov     rbp, rdx
0x180018418  mov     rax, [rcx]
0x18001841b  mov     edx, [rax]
0x18001841d  mov     [rbp+0C8h], rcx
0x180018424  mov     [rbp+68h], edx
0x180018427  mov     eax, [rbp+68h]
0x18001842a  cmp     eax, 0E06D7363h
0x18001842f  jnz     short loc_180018445
0x180018431  mov     rdx, [rbp+0C8h]
0x180018438  mov     ecx, [rbp+68h]
0x18001843b  call    _XcptFilter_0
0x180018440  mov     [rbp+70h], eax
0x180018443  jmp     short loc_18001844C
0x180018445  mov     dword ptr [rbp+70h], 0
0x18001844c  mov     eax, [rbp+70h]
0x18001844f  add     rsp, 20h
0x180018453  pop     rbp
0x180018454  retn
0x180018456  push    rbp
0x180018458  sub     rsp, 20h
0x18001845c  mov     rbp, rdx
0x18001845f  mov     rax, [rcx]
0x180018462  mov     edx, [rax]
0x180018464  mov     [rbp+0D0h], rcx
0x18001846b  mov     [rbp+78h], edx
0x18001846e  mov     eax, [rbp+78h]
0x180018471  cmp     eax, 0E06D7363h
0x180018476  jnz     short loc_18001848F
0x180018478  mov     rdx, [rbp+0D0h]
0x18001847f  mov     ecx, [rbp+78h]
0x180018482  call    _XcptFilter_0
0x180018487  mov     [rbp+80h], eax
0x18001848d  jmp     short loc_180018499
0x18001848f  mov     dword ptr [rbp+80h], 0
0x180018499  mov     eax, [rbp+80h]
0x18001849f  add     rsp, 20h
0x1800184a3  pop     rbp
0x1800184a4  retn
0x1800184a6  push    rbp
0x1800184a8  sub     rsp, 20h
0x1800184ac  mov     rbp, rdx
0x1800184af  mov     rax, [rcx]
0x1800184b2  mov     edx, [rax]
0x1800184b4  mov     [rbp+0D8h], rcx
0x1800184bb  mov     [rbp+88h], edx
0x1800184c1  mov     eax, [rbp+88h]
0x1800184c7  cmp     eax, 0E06D7363h
0x1800184cc  jnz     short loc_1800184E8
0x1800184ce  mov     rdx, [rbp+0D8h]
0x1800184d5  mov     ecx, [rbp+88h]
0x1800184db  call    _XcptFilter_0
0x1800184e0  mov     [rbp+90h], eax
0x1800184e6  jmp     short loc_1800184F2
0x1800184e8  mov     dword ptr [rbp+90h], 0
0x1800184f2  mov     eax, [rbp+90h]
0x1800184f8  add     rsp, 20h
0x1800184fc  pop     rbp
0x1800184fd  retn
0x1800184ff  push    rbp
0x180018501  sub     rsp, 20h
0x180018505  mov     rbp, rdx
0x180018508  mov     rax, [rcx]
0x18001850b  mov     edx, [rax]
0x18001850d  mov     [rbp+0E0h], rcx
0x180018514  mov     [rbp+98h], edx
0x18001851a  mov     eax, [rbp+98h]
0x180018520  cmp     eax, 0E06D7363h
0x180018525  jnz     short loc_180018541
0x180018527  mov     rdx, [rbp+0E0h]
0x18001852e  mov     ecx, [rbp+98h]
0x180018534  call    _XcptFilter_0
0x180018539  mov     [rbp+0A0h], eax
0x18001853f  jmp     short loc_18001854B
0x180018541  mov     dword ptr [rbp+0A0h], 0
0x18001854b  mov     eax, [rbp+0A0h]
0x180018551  add     rsp, 20h
0x180018555  pop     rbp
0x180018556  retn
0x180018558  push    rbp
0x18001855a  sub     rsp, 20h
0x18001855e  mov     rbp, rdx
0x180018561  cmp     dword ptr [rbp+118h], 1
0x180018568  ja      short loc_180018574
0x18001856a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

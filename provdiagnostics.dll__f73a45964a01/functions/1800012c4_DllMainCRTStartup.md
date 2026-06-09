# __DllMainCRTStartup

- ea: `0x1800012c4`
- end: `0x1800014d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001050`
- `0x1800012c4`
- `0x1800014d6`
- `0x1800016a8`
- `0x180001710`

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
  if ( (_DWORD)fdwReason || dword_1800030A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800030A4 = 1;
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
            if ( dword_1800030A4 )
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
0x1800012c4  mov     [rsp+lpvReserved], r8
0x1800012c9  mov     [rsp+arg_8], edx
0x1800012cd  mov     [rsp+arg_0], rcx
0x1800012d2  push    rbx
0x1800012d3  push    rsi
0x1800012d4  push    rdi
0x1800012d5  sub     rsp, 0F0h
0x1800012dc  mov     edi, edx
0x1800012de  mov     rsi, rcx
0x1800012e1  mov     ebx, 1
0x1800012e6  cmp     edx, ebx
0x1800012e8  ja      short loc_1800012F0
0x1800012ea  mov     cs:__native_dllmain_reason, edx
0x1800012f0  test    edx, edx
0x1800012f2  jnz     short loc_180001307
0x1800012f4  cmp     cs:dword_1800030A0, edx
0x1800012fa  jnz     short loc_180001307
0x1800012fc  xor     ebx, ebx
0x1800012fe  mov     [rsp+108h+var_E8], ebx
0x180001302  jmp     loc_1800014B4
0x180001307  lea     eax, [rdx-1]
0x18000130a  cmp     eax, 1
0x18000130d  ja      loc_180001394
0x180001313  mov     rax, cs:_pRawDllMain
0x18000131a  test    rax, rax
0x18000131d  jz      short loc_180001355
0x18000131f  cmp     edx, 1
0x180001322  jnz     short loc_18000132A
0x180001324  mov     cs:dword_1800030A4, edx
0x18000132a  mov     r8, [rsp+108h+lpvReserved]
0x180001332  call    cs:__guard_dispatch_icall_fptr
0x180001338  mov     ebx, eax
0x18000133a  mov     [rsp+108h+var_E8], eax
0x18000133e  jmp     short loc_180001355
0x180001340  xor     ebx, ebx
0x180001342  mov     [rsp+108h+var_E8], ebx
0x180001346  mov     edi, [rsp+108h+arg_8]
0x18000134d  mov     rsi, [rsp+108h+arg_0]
0x180001355  test    ebx, ebx
0x180001357  jz      loc_1800014B4
0x18000135d  mov     r8, [rsp+108h+lpvReserved]
0x180001365  mov     edx, edi
0x180001367  mov     rcx, rsi
0x18000136a  call    _CRT_INIT
0x18000136f  mov     ebx, eax
0x180001371  mov     [rsp+108h+var_E8], eax
0x180001375  jmp     short loc_18000138C
0x180001377  xor     ebx, ebx
0x180001379  mov     [rsp+108h+var_E8], ebx
0x18000137d  mov     edi, [rsp+108h+arg_8]
0x180001384  mov     rsi, [rsp+108h+arg_0]
0x18000138c  test    ebx, ebx
0x18000138e  jz      loc_1800014B4
0x180001394  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000139c  mov     edx, edi; fdwReason
0x18000139e  mov     rcx, rsi; hinstDLL
0x1800013a1  call    DllMain
0x1800013a6  mov     ebx, eax
0x1800013a8  mov     [rsp+108h+var_E8], eax
0x1800013ac  jmp     short loc_1800013C3
0x1800013ae  xor     ebx, ebx
0x1800013b0  mov     [rsp+108h+var_E8], ebx
0x1800013b4  mov     edi, [rsp+108h+arg_8]
0x1800013bb  mov     rsi, [rsp+108h+arg_0]
0x1800013c3  cmp     edi, 1
0x1800013c6  jnz     short loc_18000143F
0x1800013c8  test    ebx, ebx
0x1800013ca  jnz     short loc_18000143F
0x1800013cc  xor     r8d, r8d; lpvReserved
0x1800013cf  xor     edx, edx; fdwReason
0x1800013d1  mov     rcx, rsi; hinstDLL
0x1800013d4  call    DllMain
0x1800013d9  jmp     short loc_1800013EE
0x1800013db  mov     edi, [rsp+108h+arg_8]
0x1800013e2  mov     rsi, [rsp+108h+arg_0]
0x1800013ea  mov     ebx, [rsp+108h+var_E8]
0x1800013ee  xor     r8d, r8d
0x1800013f1  xor     edx, edx
0x1800013f3  mov     rcx, rsi
0x1800013f6  call    _CRT_INIT
0x1800013fb  jmp     short loc_180001410
0x1800013fd  mov     edi, [rsp+108h+arg_8]
0x180001404  mov     rsi, [rsp+108h+arg_0]
0x18000140c  mov     ebx, [rsp+108h+var_E8]
0x180001410  mov     rax, cs:_pRawDllMain
0x180001417  test    rax, rax
0x18000141a  jz      short loc_18000143F
0x18000141c  xor     r8d, r8d
0x18000141f  xor     edx, edx
0x180001421  mov     rcx, rsi
0x180001424  call    cs:__guard_dispatch_icall_fptr
0x18000142a  jmp     short loc_18000143F
0x18000142c  mov     edi, [rsp+108h+arg_8]
0x180001433  mov     rsi, [rsp+108h+arg_0]
0x18000143b  mov     ebx, [rsp+108h+var_E8]
0x18000143f  test    edi, edi
0x180001441  jz      short loc_180001448
0x180001443  cmp     edi, 3
0x180001446  jnz     short loc_1800014B4
0x180001448  mov     r8, [rsp+108h+lpvReserved]
0x180001450  mov     edx, edi
0x180001452  mov     rcx, rsi
0x180001455  call    _CRT_INIT
0x18000145a  mov     ebx, eax
0x18000145c  mov     [rsp+108h+var_E8], eax
0x180001460  jmp     short loc_180001477
0x180001462  xor     ebx, ebx
0x180001464  mov     [rsp+108h+var_E8], ebx
0x180001468  mov     edi, [rsp+108h+arg_8]
0x18000146f  mov     rsi, [rsp+108h+arg_0]
0x180001477  mov     rax, cs:_pRawDllMain
0x18000147e  test    rax, rax
0x180001481  jz      short loc_1800014B4
0x180001483  cmp     cs:dword_1800030A4, 0
0x18000148a  jz      short loc_1800014B4
0x18000148c  mov     r8, [rsp+108h+lpvReserved]
0x180001494  mov     edx, edi
0x180001496  mov     rcx, rsi
0x180001499  call    cs:__guard_dispatch_icall_fptr
0x18000149f  mov     ebx, eax
0x1800014a1  mov     [rsp+108h+var_E8], eax
0x1800014a5  jmp     short loc_1800014B4
0x1800014a7  xor     ebx, ebx
0x1800014a9  mov     [rsp+108h+var_E8], ebx
0x1800014ad  mov     edi, [rsp+108h+arg_8]
0x1800014b4  cmp     edi, 1
0x1800014b7  ja      short loc_1800014C3
0x1800014b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800014c3  mov     eax, ebx
0x1800014c5  add     rsp, 0F0h
0x1800014cc  pop     rdi
0x1800014cd  pop     rsi
0x1800014ce  pop     rbx
0x1800014cf  retn
0x180001750  push    rbp
0x180001752  sub     rsp, 20h
0x180001756  mov     rbp, rdx
0x180001759  mov     rax, [rcx]
0x18000175c  mov     edx, [rax]
0x18000175e  mov     [rbp+0A8h], rcx
0x180001765  mov     [rbp+28h], edx
0x180001768  mov     eax, [rbp+28h]
0x18000176b  cmp     eax, 0E06D7363h
0x180001770  jnz     short loc_180001786
0x180001772  mov     rdx, [rbp+0A8h]
0x180001779  mov     ecx, [rbp+28h]
0x18000177c  call    _XcptFilter_0
0x180001781  mov     [rbp+30h], eax
0x180001784  jmp     short loc_18000178D
0x180001786  mov     dword ptr [rbp+30h], 0
0x18000178d  mov     eax, [rbp+30h]
0x180001790  add     rsp, 20h
0x180001794  pop     rbp
0x180001795  retn
0x180001797  push    rbp
0x180001799  sub     rsp, 20h
0x18000179d  mov     rbp, rdx
0x1800017a0  mov     rax, [rcx]
0x1800017a3  mov     edx, [rax]
0x1800017a5  mov     [rbp+0B0h], rcx
0x1800017ac  mov     [rbp+38h], edx
0x1800017af  mov     eax, [rbp+38h]
0x1800017b2  cmp     eax, 0E06D7363h
0x1800017b7  jnz     short loc_1800017CD
0x1800017b9  mov     rdx, [rbp+0B0h]
0x1800017c0  mov     ecx, [rbp+38h]
0x1800017c3  call    _XcptFilter_0
0x1800017c8  mov     [rbp+40h], eax
0x1800017cb  jmp     short loc_1800017D4
0x1800017cd  mov     dword ptr [rbp+40h], 0
0x1800017d4  mov     eax, [rbp+40h]
0x1800017d7  add     rsp, 20h
0x1800017db  pop     rbp
0x1800017dc  retn
0x1800017de  push    rbp
0x1800017e0  sub     rsp, 20h
0x1800017e4  mov     rbp, rdx
0x1800017e7  mov     rax, [rcx]
0x1800017ea  mov     edx, [rax]
0x1800017ec  mov     [rbp+0B8h], rcx
0x1800017f3  mov     [rbp+48h], edx
0x1800017f6  mov     eax, [rbp+48h]
0x1800017f9  cmp     eax, 0E06D7363h
0x1800017fe  jnz     short loc_180001814
0x180001800  mov     rdx, [rbp+0B8h]
0x180001807  mov     ecx, [rbp+48h]
0x18000180a  call    _XcptFilter_0
0x18000180f  mov     [rbp+50h], eax
0x180001812  jmp     short loc_18000181B
0x180001814  mov     dword ptr [rbp+50h], 0
0x18000181b  mov     eax, [rbp+50h]
0x18000181e  add     rsp, 20h
0x180001822  pop     rbp
0x180001823  retn
0x180001825  push    rbp
0x180001827  sub     rsp, 20h
0x18000182b  mov     rbp, rdx
0x18000182e  mov     rax, [rcx]
0x180001831  mov     edx, [rax]
0x180001833  mov     [rbp+0C0h], rcx
0x18000183a  mov     [rbp+58h], edx
0x18000183d  mov     eax, [rbp+58h]
0x180001840  cmp     eax, 0E06D7363h
0x180001845  jnz     short loc_18000185B
0x180001847  mov     rdx, [rbp+0C0h]
0x18000184e  mov     ecx, [rbp+58h]
0x180001851  call    _XcptFilter_0
0x180001856  mov     [rbp+60h], eax
0x180001859  jmp     short loc_180001862
0x18000185b  mov     dword ptr [rbp+60h], 0
0x180001862  mov     eax, [rbp+60h]
0x180001865  add     rsp, 20h
0x180001869  pop     rbp
0x18000186a  retn
0x18000186c  push    rbp
0x18000186e  sub     rsp, 20h
0x180001872  mov     rbp, rdx
0x180001875  mov     rax, [rcx]
0x180001878  mov     edx, [rax]
0x18000187a  mov     [rbp+0C8h], rcx
0x180001881  mov     [rbp+68h], edx
0x180001884  mov     eax, [rbp+68h]
0x180001887  cmp     eax, 0E06D7363h
0x18000188c  jnz     short loc_1800018A2
0x18000188e  mov     rdx, [rbp+0C8h]
0x180001895  mov     ecx, [rbp+68h]
0x180001898  call    _XcptFilter_0
0x18000189d  mov     [rbp+70h], eax
0x1800018a0  jmp     short loc_1800018A9
0x1800018a2  mov     dword ptr [rbp+70h], 0
0x1800018a9  mov     eax, [rbp+70h]
0x1800018ac  add     rsp, 20h
0x1800018b0  pop     rbp
0x1800018b1  retn
0x1800018b3  push    rbp
0x1800018b5  sub     rsp, 20h
0x1800018b9  mov     rbp, rdx
0x1800018bc  mov     rax, [rcx]
0x1800018bf  mov     edx, [rax]
0x1800018c1  mov     [rbp+0D0h], rcx
0x1800018c8  mov     [rbp+78h], edx
0x1800018cb  mov     eax, [rbp+78h]
0x1800018ce  cmp     eax, 0E06D7363h
0x1800018d3  jnz     short loc_1800018EC
0x1800018d5  mov     rdx, [rbp+0D0h]
0x1800018dc  mov     ecx, [rbp+78h]
0x1800018df  call    _XcptFilter_0
0x1800018e4  mov     [rbp+80h], eax
0x1800018ea  jmp     short loc_1800018F6
0x1800018ec  mov     dword ptr [rbp+80h], 0
0x1800018f6  mov     eax, [rbp+80h]
0x1800018fc  add     rsp, 20h
0x180001900  pop     rbp
0x180001901  retn
0x180001903  push    rbp
0x180001905  sub     rsp, 20h
0x180001909  mov     rbp, rdx
0x18000190c  mov     rax, [rcx]
0x18000190f  mov     edx, [rax]
0x180001911  mov     [rbp+0D8h], rcx
0x180001918  mov     [rbp+88h], edx
0x18000191e  mov     eax, [rbp+88h]
0x180001924  cmp     eax, 0E06D7363h
0x180001929  jnz     short loc_180001945
0x18000192b  mov     rdx, [rbp+0D8h]
0x180001932  mov     ecx, [rbp+88h]
0x180001938  call    _XcptFilter_0
0x18000193d  mov     [rbp+90h], eax
0x180001943  jmp     short loc_18000194F
0x180001945  mov     dword ptr [rbp+90h], 0
0x18000194f  mov     eax, [rbp+90h]
0x180001955  add     rsp, 20h
0x180001959  pop     rbp
0x18000195a  retn
0x18000195c  push    rbp
0x18000195e  sub     rsp, 20h
0x180001962  mov     rbp, rdx
0x180001965  mov     rax, [rcx]
0x180001968  mov     edx, [rax]
0x18000196a  mov     [rbp+0E0h], rcx
0x180001971  mov     [rbp+98h], edx
0x180001977  mov     eax, [rbp+98h]
0x18000197d  cmp     eax, 0E06D7363h
0x180001982  jnz     short loc_18000199E
0x180001984  mov     rdx, [rbp+0E0h]
0x18000198b  mov     ecx, [rbp+98h]
0x180001991  call    _XcptFilter_0
0x180001996  mov     [rbp+0A0h], eax
0x18000199c  jmp     short loc_1800019A8
0x18000199e  mov     dword ptr [rbp+0A0h], 0
0x1800019a8  mov     eax, [rbp+0A0h]
0x1800019ae  add     rsp, 20h
0x1800019b2  pop     rbp
0x1800019b3  retn
0x1800019b5  push    rbp
0x1800019b7  sub     rsp, 20h
0x1800019bb  mov     rbp, rdx
0x1800019be  cmp     dword ptr [rbp+118h], 1
0x1800019c5  ja      short loc_1800019D1
0x1800019c7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

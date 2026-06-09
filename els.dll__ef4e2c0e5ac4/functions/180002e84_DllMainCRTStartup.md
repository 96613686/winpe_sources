# __DllMainCRTStartup

- ea: `0x180002e84`
- end: `0x180003090`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002e40`

## callees

- `0x180002c10`
- `0x180002e84`
- `0x1800036be`
- `0x18000c594`
- `0x180022340`

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
  if ( (_DWORD)fdwReason || dword_18002F93C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002F940 = 1;
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
            if ( dword_18002F940 )
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
0x180002e84  mov     [rsp+lpvReserved], r8
0x180002e89  mov     [rsp+arg_8], edx
0x180002e8d  mov     [rsp+arg_0], rcx
0x180002e92  push    rbx
0x180002e93  push    rsi
0x180002e94  push    rdi
0x180002e95  sub     rsp, 0F0h
0x180002e9c  mov     edi, edx
0x180002e9e  mov     rsi, rcx
0x180002ea1  mov     ebx, 1
0x180002ea6  cmp     edx, ebx
0x180002ea8  ja      short loc_180002EB0
0x180002eaa  mov     cs:__native_dllmain_reason, edx
0x180002eb0  test    edx, edx
0x180002eb2  jnz     short loc_180002EC7
0x180002eb4  cmp     cs:dword_18002F93C, edx
0x180002eba  jnz     short loc_180002EC7
0x180002ebc  xor     ebx, ebx
0x180002ebe  mov     [rsp+108h+var_E8], ebx
0x180002ec2  jmp     loc_180003074
0x180002ec7  lea     eax, [rdx-1]
0x180002eca  cmp     eax, 1
0x180002ecd  ja      loc_180002F54
0x180002ed3  mov     rax, cs:_pRawDllMain
0x180002eda  test    rax, rax
0x180002edd  jz      short loc_180002F15
0x180002edf  cmp     edx, 1
0x180002ee2  jnz     short loc_180002EEA
0x180002ee4  mov     cs:dword_18002F940, edx
0x180002eea  mov     r8, [rsp+108h+lpvReserved]
0x180002ef2  call    cs:__guard_dispatch_icall_fptr
0x180002ef8  mov     ebx, eax
0x180002efa  mov     [rsp+108h+var_E8], eax
0x180002efe  jmp     short loc_180002F15
0x180002f00  xor     ebx, ebx
0x180002f02  mov     [rsp+108h+var_E8], ebx
0x180002f06  mov     edi, [rsp+108h+arg_8]
0x180002f0d  mov     rsi, [rsp+108h+arg_0]
0x180002f15  test    ebx, ebx
0x180002f17  jz      loc_180003074
0x180002f1d  mov     r8, [rsp+108h+lpvReserved]
0x180002f25  mov     edx, edi
0x180002f27  mov     rcx, rsi
0x180002f2a  call    _CRT_INIT
0x180002f2f  mov     ebx, eax
0x180002f31  mov     [rsp+108h+var_E8], eax
0x180002f35  jmp     short loc_180002F4C
0x180002f37  xor     ebx, ebx
0x180002f39  mov     [rsp+108h+var_E8], ebx
0x180002f3d  mov     edi, [rsp+108h+arg_8]
0x180002f44  mov     rsi, [rsp+108h+arg_0]
0x180002f4c  test    ebx, ebx
0x180002f4e  jz      loc_180003074
0x180002f54  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180002f5c  mov     edx, edi; fdwReason
0x180002f5e  mov     rcx, rsi; hinstDLL
0x180002f61  call    DllMain
0x180002f66  mov     ebx, eax
0x180002f68  mov     [rsp+108h+var_E8], eax
0x180002f6c  jmp     short loc_180002F83
0x180002f6e  xor     ebx, ebx
0x180002f70  mov     [rsp+108h+var_E8], ebx
0x180002f74  mov     edi, [rsp+108h+arg_8]
0x180002f7b  mov     rsi, [rsp+108h+arg_0]
0x180002f83  cmp     edi, 1
0x180002f86  jnz     short loc_180002FFF
0x180002f88  test    ebx, ebx
0x180002f8a  jnz     short loc_180002FFF
0x180002f8c  xor     r8d, r8d; lpvReserved
0x180002f8f  xor     edx, edx; fdwReason
0x180002f91  mov     rcx, rsi; hinstDLL
0x180002f94  call    DllMain
0x180002f99  jmp     short loc_180002FAE
0x180002f9b  mov     edi, [rsp+108h+arg_8]
0x180002fa2  mov     rsi, [rsp+108h+arg_0]
0x180002faa  mov     ebx, [rsp+108h+var_E8]
0x180002fae  xor     r8d, r8d
0x180002fb1  xor     edx, edx
0x180002fb3  mov     rcx, rsi
0x180002fb6  call    _CRT_INIT
0x180002fbb  jmp     short loc_180002FD0
0x180002fbd  mov     edi, [rsp+108h+arg_8]
0x180002fc4  mov     rsi, [rsp+108h+arg_0]
0x180002fcc  mov     ebx, [rsp+108h+var_E8]
0x180002fd0  mov     rax, cs:_pRawDllMain
0x180002fd7  test    rax, rax
0x180002fda  jz      short loc_180002FFF
0x180002fdc  xor     r8d, r8d
0x180002fdf  xor     edx, edx
0x180002fe1  mov     rcx, rsi
0x180002fe4  call    cs:__guard_dispatch_icall_fptr
0x180002fea  jmp     short loc_180002FFF
0x180002fec  mov     edi, [rsp+108h+arg_8]
0x180002ff3  mov     rsi, [rsp+108h+arg_0]
0x180002ffb  mov     ebx, [rsp+108h+var_E8]
0x180002fff  test    edi, edi
0x180003001  jz      short loc_180003008
0x180003003  cmp     edi, 3
0x180003006  jnz     short loc_180003074
0x180003008  mov     r8, [rsp+108h+lpvReserved]
0x180003010  mov     edx, edi
0x180003012  mov     rcx, rsi
0x180003015  call    _CRT_INIT
0x18000301a  mov     ebx, eax
0x18000301c  mov     [rsp+108h+var_E8], eax
0x180003020  jmp     short loc_180003037
0x180003022  xor     ebx, ebx
0x180003024  mov     [rsp+108h+var_E8], ebx
0x180003028  mov     edi, [rsp+108h+arg_8]
0x18000302f  mov     rsi, [rsp+108h+arg_0]
0x180003037  mov     rax, cs:_pRawDllMain
0x18000303e  test    rax, rax
0x180003041  jz      short loc_180003074
0x180003043  cmp     cs:dword_18002F940, 0
0x18000304a  jz      short loc_180003074
0x18000304c  mov     r8, [rsp+108h+lpvReserved]
0x180003054  mov     edx, edi
0x180003056  mov     rcx, rsi
0x180003059  call    cs:__guard_dispatch_icall_fptr
0x18000305f  mov     ebx, eax
0x180003061  mov     [rsp+108h+var_E8], eax
0x180003065  jmp     short loc_180003074
0x180003067  xor     ebx, ebx
0x180003069  mov     [rsp+108h+var_E8], ebx
0x18000306d  mov     edi, [rsp+108h+arg_8]
0x180003074  cmp     edi, 1
0x180003077  ja      short loc_180003083
0x180003079  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180003083  mov     eax, ebx
0x180003085  add     rsp, 0F0h
0x18000308c  pop     rdi
0x18000308d  pop     rsi
0x18000308e  pop     rbx
0x18000308f  retn
0x180022404  push    rbp
0x180022406  sub     rsp, 20h
0x18002240a  mov     rbp, rdx
0x18002240d  mov     rax, [rcx]
0x180022410  mov     edx, [rax]
0x180022412  mov     [rbp+0A8h], rcx
0x180022419  mov     [rbp+28h], edx
0x18002241c  mov     eax, [rbp+28h]
0x18002241f  cmp     eax, 0E06D7363h
0x180022424  jnz     short loc_18002243A
0x180022426  mov     rdx, [rbp+0A8h]
0x18002242d  mov     ecx, [rbp+28h]
0x180022430  call    _XcptFilter_0
0x180022435  mov     [rbp+30h], eax
0x180022438  jmp     short loc_180022441
0x18002243a  mov     dword ptr [rbp+30h], 0
0x180022441  mov     eax, [rbp+30h]
0x180022444  add     rsp, 20h
0x180022448  pop     rbp
0x180022449  retn
0x18002244b  push    rbp
0x18002244d  sub     rsp, 20h
0x180022451  mov     rbp, rdx
0x180022454  mov     rax, [rcx]
0x180022457  mov     edx, [rax]
0x180022459  mov     [rbp+0B0h], rcx
0x180022460  mov     [rbp+38h], edx
0x180022463  mov     eax, [rbp+38h]
0x180022466  cmp     eax, 0E06D7363h
0x18002246b  jnz     short loc_180022481
0x18002246d  mov     rdx, [rbp+0B0h]
0x180022474  mov     ecx, [rbp+38h]
0x180022477  call    _XcptFilter_0
0x18002247c  mov     [rbp+40h], eax
0x18002247f  jmp     short loc_180022488
0x180022481  mov     dword ptr [rbp+40h], 0
0x180022488  mov     eax, [rbp+40h]
0x18002248b  add     rsp, 20h
0x18002248f  pop     rbp
0x180022490  retn
0x180022492  push    rbp
0x180022494  sub     rsp, 20h
0x180022498  mov     rbp, rdx
0x18002249b  mov     rax, [rcx]
0x18002249e  mov     edx, [rax]
0x1800224a0  mov     [rbp+0B8h], rcx
0x1800224a7  mov     [rbp+48h], edx
0x1800224aa  mov     eax, [rbp+48h]
0x1800224ad  cmp     eax, 0E06D7363h
0x1800224b2  jnz     short loc_1800224C8
0x1800224b4  mov     rdx, [rbp+0B8h]
0x1800224bb  mov     ecx, [rbp+48h]
0x1800224be  call    _XcptFilter_0
0x1800224c3  mov     [rbp+50h], eax
0x1800224c6  jmp     short loc_1800224CF
0x1800224c8  mov     dword ptr [rbp+50h], 0
0x1800224cf  mov     eax, [rbp+50h]
0x1800224d2  add     rsp, 20h
0x1800224d6  pop     rbp
0x1800224d7  retn
0x1800224d9  push    rbp
0x1800224db  sub     rsp, 20h
0x1800224df  mov     rbp, rdx
0x1800224e2  mov     rax, [rcx]
0x1800224e5  mov     edx, [rax]
0x1800224e7  mov     [rbp+0C0h], rcx
0x1800224ee  mov     [rbp+58h], edx
0x1800224f1  mov     eax, [rbp+58h]
0x1800224f4  cmp     eax, 0E06D7363h
0x1800224f9  jnz     short loc_18002250F
0x1800224fb  mov     rdx, [rbp+0C0h]
0x180022502  mov     ecx, [rbp+58h]
0x180022505  call    _XcptFilter_0
0x18002250a  mov     [rbp+60h], eax
0x18002250d  jmp     short loc_180022516
0x18002250f  mov     dword ptr [rbp+60h], 0
0x180022516  mov     eax, [rbp+60h]
0x180022519  add     rsp, 20h
0x18002251d  pop     rbp
0x18002251e  retn
0x180022520  push    rbp
0x180022522  sub     rsp, 20h
0x180022526  mov     rbp, rdx
0x180022529  mov     rax, [rcx]
0x18002252c  mov     edx, [rax]
0x18002252e  mov     [rbp+0C8h], rcx
0x180022535  mov     [rbp+68h], edx
0x180022538  mov     eax, [rbp+68h]
0x18002253b  cmp     eax, 0E06D7363h
0x180022540  jnz     short loc_180022556
0x180022542  mov     rdx, [rbp+0C8h]
0x180022549  mov     ecx, [rbp+68h]
0x18002254c  call    _XcptFilter_0
0x180022551  mov     [rbp+70h], eax
0x180022554  jmp     short loc_18002255D
0x180022556  mov     dword ptr [rbp+70h], 0
0x18002255d  mov     eax, [rbp+70h]
0x180022560  add     rsp, 20h
0x180022564  pop     rbp
0x180022565  retn
0x180022567  push    rbp
0x180022569  sub     rsp, 20h
0x18002256d  mov     rbp, rdx
0x180022570  mov     rax, [rcx]
0x180022573  mov     edx, [rax]
0x180022575  mov     [rbp+0D0h], rcx
0x18002257c  mov     [rbp+78h], edx
0x18002257f  mov     eax, [rbp+78h]
0x180022582  cmp     eax, 0E06D7363h
0x180022587  jnz     short loc_1800225A0
0x180022589  mov     rdx, [rbp+0D0h]
0x180022590  mov     ecx, [rbp+78h]
0x180022593  call    _XcptFilter_0
0x180022598  mov     [rbp+80h], eax
0x18002259e  jmp     short loc_1800225AA
0x1800225a0  mov     dword ptr [rbp+80h], 0
0x1800225aa  mov     eax, [rbp+80h]
0x1800225b0  add     rsp, 20h
0x1800225b4  pop     rbp
0x1800225b5  retn
0x1800225b7  push    rbp
0x1800225b9  sub     rsp, 20h
0x1800225bd  mov     rbp, rdx
0x1800225c0  mov     rax, [rcx]
0x1800225c3  mov     edx, [rax]
0x1800225c5  mov     [rbp+0D8h], rcx
0x1800225cc  mov     [rbp+88h], edx
0x1800225d2  mov     eax, [rbp+88h]
0x1800225d8  cmp     eax, 0E06D7363h
0x1800225dd  jnz     short loc_1800225F9
0x1800225df  mov     rdx, [rbp+0D8h]
0x1800225e6  mov     ecx, [rbp+88h]
0x1800225ec  call    _XcptFilter_0
0x1800225f1  mov     [rbp+90h], eax
0x1800225f7  jmp     short loc_180022603
0x1800225f9  mov     dword ptr [rbp+90h], 0
0x180022603  mov     eax, [rbp+90h]
0x180022609  add     rsp, 20h
0x18002260d  pop     rbp
0x18002260e  retn
0x180022610  push    rbp
0x180022612  sub     rsp, 20h
0x180022616  mov     rbp, rdx
0x180022619  mov     rax, [rcx]
0x18002261c  mov     edx, [rax]
0x18002261e  mov     [rbp+0E0h], rcx
0x180022625  mov     [rbp+98h], edx
0x18002262b  mov     eax, [rbp+98h]
0x180022631  cmp     eax, 0E06D7363h
0x180022636  jnz     short loc_180022652
0x180022638  mov     rdx, [rbp+0E0h]
0x18002263f  mov     ecx, [rbp+98h]
0x180022645  call    _XcptFilter_0
0x18002264a  mov     [rbp+0A0h], eax
0x180022650  jmp     short loc_18002265C
0x180022652  mov     dword ptr [rbp+0A0h], 0
0x18002265c  mov     eax, [rbp+0A0h]
0x180022662  add     rsp, 20h
0x180022666  pop     rbp
0x180022667  retn
0x180022669  push    rbp
0x18002266b  sub     rsp, 20h
0x18002266f  mov     rbp, rdx
0x180022672  cmp     dword ptr [rbp+118h], 1
0x180022679  ja      short loc_180022685
0x18002267b  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

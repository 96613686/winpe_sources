# __DllMainCRTStartup

- ea: `0x180002084`
- end: `0x180002290`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002040`

## callees

- `0x180001e10`
- `0x180002084`
- `0x1800022ba`
- `0x180002498`
- `0x1800027a0`

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
  if ( (_DWORD)fdwReason || dword_1800090A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800090A4 = 1;
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
            if ( dword_1800090A4 )
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
0x180002084  mov     [rsp+lpvReserved], r8
0x180002089  mov     [rsp+arg_8], edx
0x18000208d  mov     [rsp+arg_0], rcx
0x180002092  push    rbx
0x180002093  push    rsi
0x180002094  push    rdi
0x180002095  sub     rsp, 0F0h
0x18000209c  mov     edi, edx
0x18000209e  mov     rsi, rcx
0x1800020a1  mov     ebx, 1
0x1800020a6  cmp     edx, ebx
0x1800020a8  ja      short loc_1800020B0
0x1800020aa  mov     cs:__native_dllmain_reason, edx
0x1800020b0  test    edx, edx
0x1800020b2  jnz     short loc_1800020C7
0x1800020b4  cmp     cs:dword_1800090A0, edx
0x1800020ba  jnz     short loc_1800020C7
0x1800020bc  xor     ebx, ebx
0x1800020be  mov     [rsp+108h+var_E8], ebx
0x1800020c2  jmp     loc_180002274
0x1800020c7  lea     eax, [rdx-1]
0x1800020ca  cmp     eax, 1
0x1800020cd  ja      loc_180002154
0x1800020d3  mov     rax, cs:_pRawDllMain
0x1800020da  test    rax, rax
0x1800020dd  jz      short loc_180002115
0x1800020df  cmp     edx, 1
0x1800020e2  jnz     short loc_1800020EA
0x1800020e4  mov     cs:dword_1800090A4, edx
0x1800020ea  mov     r8, [rsp+108h+lpvReserved]
0x1800020f2  call    cs:__guard_dispatch_icall_fptr
0x1800020f8  mov     ebx, eax
0x1800020fa  mov     [rsp+108h+var_E8], eax
0x1800020fe  jmp     short loc_180002115
0x180002100  xor     ebx, ebx
0x180002102  mov     [rsp+108h+var_E8], ebx
0x180002106  mov     edi, [rsp+108h+arg_8]
0x18000210d  mov     rsi, [rsp+108h+arg_0]
0x180002115  test    ebx, ebx
0x180002117  jz      loc_180002274
0x18000211d  mov     r8, [rsp+108h+lpvReserved]
0x180002125  mov     edx, edi
0x180002127  mov     rcx, rsi
0x18000212a  call    _CRT_INIT
0x18000212f  mov     ebx, eax
0x180002131  mov     [rsp+108h+var_E8], eax
0x180002135  jmp     short loc_18000214C
0x180002137  xor     ebx, ebx
0x180002139  mov     [rsp+108h+var_E8], ebx
0x18000213d  mov     edi, [rsp+108h+arg_8]
0x180002144  mov     rsi, [rsp+108h+arg_0]
0x18000214c  test    ebx, ebx
0x18000214e  jz      loc_180002274
0x180002154  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000215c  mov     edx, edi; fdwReason
0x18000215e  mov     rcx, rsi; hinstDLL
0x180002161  call    DllMain
0x180002166  mov     ebx, eax
0x180002168  mov     [rsp+108h+var_E8], eax
0x18000216c  jmp     short loc_180002183
0x18000216e  xor     ebx, ebx
0x180002170  mov     [rsp+108h+var_E8], ebx
0x180002174  mov     edi, [rsp+108h+arg_8]
0x18000217b  mov     rsi, [rsp+108h+arg_0]
0x180002183  cmp     edi, 1
0x180002186  jnz     short loc_1800021FF
0x180002188  test    ebx, ebx
0x18000218a  jnz     short loc_1800021FF
0x18000218c  xor     r8d, r8d; lpvReserved
0x18000218f  xor     edx, edx; fdwReason
0x180002191  mov     rcx, rsi; hinstDLL
0x180002194  call    DllMain
0x180002199  jmp     short loc_1800021AE
0x18000219b  mov     edi, [rsp+108h+arg_8]
0x1800021a2  mov     rsi, [rsp+108h+arg_0]
0x1800021aa  mov     ebx, [rsp+108h+var_E8]
0x1800021ae  xor     r8d, r8d
0x1800021b1  xor     edx, edx
0x1800021b3  mov     rcx, rsi
0x1800021b6  call    _CRT_INIT
0x1800021bb  jmp     short loc_1800021D0
0x1800021bd  mov     edi, [rsp+108h+arg_8]
0x1800021c4  mov     rsi, [rsp+108h+arg_0]
0x1800021cc  mov     ebx, [rsp+108h+var_E8]
0x1800021d0  mov     rax, cs:_pRawDllMain
0x1800021d7  test    rax, rax
0x1800021da  jz      short loc_1800021FF
0x1800021dc  xor     r8d, r8d
0x1800021df  xor     edx, edx
0x1800021e1  mov     rcx, rsi
0x1800021e4  call    cs:__guard_dispatch_icall_fptr
0x1800021ea  jmp     short loc_1800021FF
0x1800021ec  mov     edi, [rsp+108h+arg_8]
0x1800021f3  mov     rsi, [rsp+108h+arg_0]
0x1800021fb  mov     ebx, [rsp+108h+var_E8]
0x1800021ff  test    edi, edi
0x180002201  jz      short loc_180002208
0x180002203  cmp     edi, 3
0x180002206  jnz     short loc_180002274
0x180002208  mov     r8, [rsp+108h+lpvReserved]
0x180002210  mov     edx, edi
0x180002212  mov     rcx, rsi
0x180002215  call    _CRT_INIT
0x18000221a  mov     ebx, eax
0x18000221c  mov     [rsp+108h+var_E8], eax
0x180002220  jmp     short loc_180002237
0x180002222  xor     ebx, ebx
0x180002224  mov     [rsp+108h+var_E8], ebx
0x180002228  mov     edi, [rsp+108h+arg_8]
0x18000222f  mov     rsi, [rsp+108h+arg_0]
0x180002237  mov     rax, cs:_pRawDllMain
0x18000223e  test    rax, rax
0x180002241  jz      short loc_180002274
0x180002243  cmp     cs:dword_1800090A4, 0
0x18000224a  jz      short loc_180002274
0x18000224c  mov     r8, [rsp+108h+lpvReserved]
0x180002254  mov     edx, edi
0x180002256  mov     rcx, rsi
0x180002259  call    cs:__guard_dispatch_icall_fptr
0x18000225f  mov     ebx, eax
0x180002261  mov     [rsp+108h+var_E8], eax
0x180002265  jmp     short loc_180002274
0x180002267  xor     ebx, ebx
0x180002269  mov     [rsp+108h+var_E8], ebx
0x18000226d  mov     edi, [rsp+108h+arg_8]
0x180002274  cmp     edi, 1
0x180002277  ja      short loc_180002283
0x180002279  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002283  mov     eax, ebx
0x180002285  add     rsp, 0F0h
0x18000228c  pop     rdi
0x18000228d  pop     rsi
0x18000228e  pop     rbx
0x18000228f  retn
0x180002810  push    rbp
0x180002812  sub     rsp, 20h
0x180002816  mov     rbp, rdx
0x180002819  mov     rax, [rcx]
0x18000281c  mov     edx, [rax]
0x18000281e  mov     [rbp+0A8h], rcx
0x180002825  mov     [rbp+28h], edx
0x180002828  mov     eax, [rbp+28h]
0x18000282b  cmp     eax, 0E06D7363h
0x180002830  jnz     short loc_180002846
0x180002832  mov     rdx, [rbp+0A8h]
0x180002839  mov     ecx, [rbp+28h]
0x18000283c  call    _XcptFilter_0
0x180002841  mov     [rbp+30h], eax
0x180002844  jmp     short loc_18000284D
0x180002846  mov     dword ptr [rbp+30h], 0
0x18000284d  mov     eax, [rbp+30h]
0x180002850  add     rsp, 20h
0x180002854  pop     rbp
0x180002855  retn
0x180002857  push    rbp
0x180002859  sub     rsp, 20h
0x18000285d  mov     rbp, rdx
0x180002860  mov     rax, [rcx]
0x180002863  mov     edx, [rax]
0x180002865  mov     [rbp+0B0h], rcx
0x18000286c  mov     [rbp+38h], edx
0x18000286f  mov     eax, [rbp+38h]
0x180002872  cmp     eax, 0E06D7363h
0x180002877  jnz     short loc_18000288D
0x180002879  mov     rdx, [rbp+0B0h]
0x180002880  mov     ecx, [rbp+38h]
0x180002883  call    _XcptFilter_0
0x180002888  mov     [rbp+40h], eax
0x18000288b  jmp     short loc_180002894
0x18000288d  mov     dword ptr [rbp+40h], 0
0x180002894  mov     eax, [rbp+40h]
0x180002897  add     rsp, 20h
0x18000289b  pop     rbp
0x18000289c  retn
0x18000289e  push    rbp
0x1800028a0  sub     rsp, 20h
0x1800028a4  mov     rbp, rdx
0x1800028a7  mov     rax, [rcx]
0x1800028aa  mov     edx, [rax]
0x1800028ac  mov     [rbp+0B8h], rcx
0x1800028b3  mov     [rbp+48h], edx
0x1800028b6  mov     eax, [rbp+48h]
0x1800028b9  cmp     eax, 0E06D7363h
0x1800028be  jnz     short loc_1800028D4
0x1800028c0  mov     rdx, [rbp+0B8h]
0x1800028c7  mov     ecx, [rbp+48h]
0x1800028ca  call    _XcptFilter_0
0x1800028cf  mov     [rbp+50h], eax
0x1800028d2  jmp     short loc_1800028DB
0x1800028d4  mov     dword ptr [rbp+50h], 0
0x1800028db  mov     eax, [rbp+50h]
0x1800028de  add     rsp, 20h
0x1800028e2  pop     rbp
0x1800028e3  retn
0x1800028e5  push    rbp
0x1800028e7  sub     rsp, 20h
0x1800028eb  mov     rbp, rdx
0x1800028ee  mov     rax, [rcx]
0x1800028f1  mov     edx, [rax]
0x1800028f3  mov     [rbp+0C0h], rcx
0x1800028fa  mov     [rbp+58h], edx
0x1800028fd  mov     eax, [rbp+58h]
0x180002900  cmp     eax, 0E06D7363h
0x180002905  jnz     short loc_18000291B
0x180002907  mov     rdx, [rbp+0C0h]
0x18000290e  mov     ecx, [rbp+58h]
0x180002911  call    _XcptFilter_0
0x180002916  mov     [rbp+60h], eax
0x180002919  jmp     short loc_180002922
0x18000291b  mov     dword ptr [rbp+60h], 0
0x180002922  mov     eax, [rbp+60h]
0x180002925  add     rsp, 20h
0x180002929  pop     rbp
0x18000292a  retn
0x18000292c  push    rbp
0x18000292e  sub     rsp, 20h
0x180002932  mov     rbp, rdx
0x180002935  mov     rax, [rcx]
0x180002938  mov     edx, [rax]
0x18000293a  mov     [rbp+0C8h], rcx
0x180002941  mov     [rbp+68h], edx
0x180002944  mov     eax, [rbp+68h]
0x180002947  cmp     eax, 0E06D7363h
0x18000294c  jnz     short loc_180002962
0x18000294e  mov     rdx, [rbp+0C8h]
0x180002955  mov     ecx, [rbp+68h]
0x180002958  call    _XcptFilter_0
0x18000295d  mov     [rbp+70h], eax
0x180002960  jmp     short loc_180002969
0x180002962  mov     dword ptr [rbp+70h], 0
0x180002969  mov     eax, [rbp+70h]
0x18000296c  add     rsp, 20h
0x180002970  pop     rbp
0x180002971  retn
0x180002973  push    rbp
0x180002975  sub     rsp, 20h
0x180002979  mov     rbp, rdx
0x18000297c  mov     rax, [rcx]
0x18000297f  mov     edx, [rax]
0x180002981  mov     [rbp+0D0h], rcx
0x180002988  mov     [rbp+78h], edx
0x18000298b  mov     eax, [rbp+78h]
0x18000298e  cmp     eax, 0E06D7363h
0x180002993  jnz     short loc_1800029AC
0x180002995  mov     rdx, [rbp+0D0h]
0x18000299c  mov     ecx, [rbp+78h]
0x18000299f  call    _XcptFilter_0
0x1800029a4  mov     [rbp+80h], eax
0x1800029aa  jmp     short loc_1800029B6
0x1800029ac  mov     dword ptr [rbp+80h], 0
0x1800029b6  mov     eax, [rbp+80h]
0x1800029bc  add     rsp, 20h
0x1800029c0  pop     rbp
0x1800029c1  retn
0x1800029c3  push    rbp
0x1800029c5  sub     rsp, 20h
0x1800029c9  mov     rbp, rdx
0x1800029cc  mov     rax, [rcx]
0x1800029cf  mov     edx, [rax]
0x1800029d1  mov     [rbp+0D8h], rcx
0x1800029d8  mov     [rbp+88h], edx
0x1800029de  mov     eax, [rbp+88h]
0x1800029e4  cmp     eax, 0E06D7363h
0x1800029e9  jnz     short loc_180002A05
0x1800029eb  mov     rdx, [rbp+0D8h]
0x1800029f2  mov     ecx, [rbp+88h]
0x1800029f8  call    _XcptFilter_0
0x1800029fd  mov     [rbp+90h], eax
0x180002a03  jmp     short loc_180002A0F
0x180002a05  mov     dword ptr [rbp+90h], 0
0x180002a0f  mov     eax, [rbp+90h]
0x180002a15  add     rsp, 20h
0x180002a19  pop     rbp
0x180002a1a  retn
0x180002a1c  push    rbp
0x180002a1e  sub     rsp, 20h
0x180002a22  mov     rbp, rdx
0x180002a25  mov     rax, [rcx]
0x180002a28  mov     edx, [rax]
0x180002a2a  mov     [rbp+0E0h], rcx
0x180002a31  mov     [rbp+98h], edx
0x180002a37  mov     eax, [rbp+98h]
0x180002a3d  cmp     eax, 0E06D7363h
0x180002a42  jnz     short loc_180002A5E
0x180002a44  mov     rdx, [rbp+0E0h]
0x180002a4b  mov     ecx, [rbp+98h]
0x180002a51  call    _XcptFilter_0
0x180002a56  mov     [rbp+0A0h], eax
0x180002a5c  jmp     short loc_180002A68
0x180002a5e  mov     dword ptr [rbp+0A0h], 0
0x180002a68  mov     eax, [rbp+0A0h]
0x180002a6e  add     rsp, 20h
0x180002a72  pop     rbp
0x180002a73  retn
0x180002a75  push    rbp
0x180002a77  sub     rsp, 20h
0x180002a7b  mov     rbp, rdx
0x180002a7e  cmp     dword ptr [rbp+118h], 1
0x180002a85  ja      short loc_180002A91
0x180002a87  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

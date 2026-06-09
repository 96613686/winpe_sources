# __DllMainCRTStartup

- ea: `0x1800012c4`
- end: `0x1800014d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001050`
- `0x1800012c4`
- `0x1800014e6`
- `0x180001940`
- `0x180002de0`

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
  if ( (_DWORD)fdwReason || dword_180007EA0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180007EA4 = 1;
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
            if ( dword_180007EA4 )
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
0x1800012f4  cmp     cs:dword_180007EA0, edx
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
0x180001324  mov     cs:dword_180007EA4, edx
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
0x180001483  cmp     cs:dword_180007EA4, 0
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
0x180002e50  push    rbp
0x180002e52  sub     rsp, 20h
0x180002e56  mov     rbp, rdx
0x180002e59  mov     rax, [rcx]
0x180002e5c  mov     edx, [rax]
0x180002e5e  mov     [rbp+0A8h], rcx
0x180002e65  mov     [rbp+28h], edx
0x180002e68  mov     eax, [rbp+28h]
0x180002e6b  cmp     eax, 0E06D7363h
0x180002e70  jnz     short loc_180002E86
0x180002e72  mov     rdx, [rbp+0A8h]
0x180002e79  mov     ecx, [rbp+28h]
0x180002e7c  call    _XcptFilter_0
0x180002e81  mov     [rbp+30h], eax
0x180002e84  jmp     short loc_180002E8D
0x180002e86  mov     dword ptr [rbp+30h], 0
0x180002e8d  mov     eax, [rbp+30h]
0x180002e90  add     rsp, 20h
0x180002e94  pop     rbp
0x180002e95  retn
0x180002e97  push    rbp
0x180002e99  sub     rsp, 20h
0x180002e9d  mov     rbp, rdx
0x180002ea0  mov     rax, [rcx]
0x180002ea3  mov     edx, [rax]
0x180002ea5  mov     [rbp+0B0h], rcx
0x180002eac  mov     [rbp+38h], edx
0x180002eaf  mov     eax, [rbp+38h]
0x180002eb2  cmp     eax, 0E06D7363h
0x180002eb7  jnz     short loc_180002ECD
0x180002eb9  mov     rdx, [rbp+0B0h]
0x180002ec0  mov     ecx, [rbp+38h]
0x180002ec3  call    _XcptFilter_0
0x180002ec8  mov     [rbp+40h], eax
0x180002ecb  jmp     short loc_180002ED4
0x180002ecd  mov     dword ptr [rbp+40h], 0
0x180002ed4  mov     eax, [rbp+40h]
0x180002ed7  add     rsp, 20h
0x180002edb  pop     rbp
0x180002edc  retn
0x180002ede  push    rbp
0x180002ee0  sub     rsp, 20h
0x180002ee4  mov     rbp, rdx
0x180002ee7  mov     rax, [rcx]
0x180002eea  mov     edx, [rax]
0x180002eec  mov     [rbp+0B8h], rcx
0x180002ef3  mov     [rbp+48h], edx
0x180002ef6  mov     eax, [rbp+48h]
0x180002ef9  cmp     eax, 0E06D7363h
0x180002efe  jnz     short loc_180002F14
0x180002f00  mov     rdx, [rbp+0B8h]
0x180002f07  mov     ecx, [rbp+48h]
0x180002f0a  call    _XcptFilter_0
0x180002f0f  mov     [rbp+50h], eax
0x180002f12  jmp     short loc_180002F1B
0x180002f14  mov     dword ptr [rbp+50h], 0
0x180002f1b  mov     eax, [rbp+50h]
0x180002f1e  add     rsp, 20h
0x180002f22  pop     rbp
0x180002f23  retn
0x180002f25  push    rbp
0x180002f27  sub     rsp, 20h
0x180002f2b  mov     rbp, rdx
0x180002f2e  mov     rax, [rcx]
0x180002f31  mov     edx, [rax]
0x180002f33  mov     [rbp+0C0h], rcx
0x180002f3a  mov     [rbp+58h], edx
0x180002f3d  mov     eax, [rbp+58h]
0x180002f40  cmp     eax, 0E06D7363h
0x180002f45  jnz     short loc_180002F5B
0x180002f47  mov     rdx, [rbp+0C0h]
0x180002f4e  mov     ecx, [rbp+58h]
0x180002f51  call    _XcptFilter_0
0x180002f56  mov     [rbp+60h], eax
0x180002f59  jmp     short loc_180002F62
0x180002f5b  mov     dword ptr [rbp+60h], 0
0x180002f62  mov     eax, [rbp+60h]
0x180002f65  add     rsp, 20h
0x180002f69  pop     rbp
0x180002f6a  retn
0x180002f6c  push    rbp
0x180002f6e  sub     rsp, 20h
0x180002f72  mov     rbp, rdx
0x180002f75  mov     rax, [rcx]
0x180002f78  mov     edx, [rax]
0x180002f7a  mov     [rbp+0C8h], rcx
0x180002f81  mov     [rbp+68h], edx
0x180002f84  mov     eax, [rbp+68h]
0x180002f87  cmp     eax, 0E06D7363h
0x180002f8c  jnz     short loc_180002FA2
0x180002f8e  mov     rdx, [rbp+0C8h]
0x180002f95  mov     ecx, [rbp+68h]
0x180002f98  call    _XcptFilter_0
0x180002f9d  mov     [rbp+70h], eax
0x180002fa0  jmp     short loc_180002FA9
0x180002fa2  mov     dword ptr [rbp+70h], 0
0x180002fa9  mov     eax, [rbp+70h]
0x180002fac  add     rsp, 20h
0x180002fb0  pop     rbp
0x180002fb1  retn
0x180002fb3  push    rbp
0x180002fb5  sub     rsp, 20h
0x180002fb9  mov     rbp, rdx
0x180002fbc  mov     rax, [rcx]
0x180002fbf  mov     edx, [rax]
0x180002fc1  mov     [rbp+0D0h], rcx
0x180002fc8  mov     [rbp+78h], edx
0x180002fcb  mov     eax, [rbp+78h]
0x180002fce  cmp     eax, 0E06D7363h
0x180002fd3  jnz     short loc_180002FEC
0x180002fd5  mov     rdx, [rbp+0D0h]
0x180002fdc  mov     ecx, [rbp+78h]
0x180002fdf  call    _XcptFilter_0
0x180002fe4  mov     [rbp+80h], eax
0x180002fea  jmp     short loc_180002FF6
0x180002fec  mov     dword ptr [rbp+80h], 0
0x180002ff6  mov     eax, [rbp+80h]
0x180002ffc  add     rsp, 20h
0x180003000  pop     rbp
0x180003001  retn
0x180003003  push    rbp
0x180003005  sub     rsp, 20h
0x180003009  mov     rbp, rdx
0x18000300c  mov     rax, [rcx]
0x18000300f  mov     edx, [rax]
0x180003011  mov     [rbp+0D8h], rcx
0x180003018  mov     [rbp+88h], edx
0x18000301e  mov     eax, [rbp+88h]
0x180003024  cmp     eax, 0E06D7363h
0x180003029  jnz     short loc_180003045
0x18000302b  mov     rdx, [rbp+0D8h]
0x180003032  mov     ecx, [rbp+88h]
0x180003038  call    _XcptFilter_0
0x18000303d  mov     [rbp+90h], eax
0x180003043  jmp     short loc_18000304F
0x180003045  mov     dword ptr [rbp+90h], 0
0x18000304f  mov     eax, [rbp+90h]
0x180003055  add     rsp, 20h
0x180003059  pop     rbp
0x18000305a  retn
0x18000305c  push    rbp
0x18000305e  sub     rsp, 20h
0x180003062  mov     rbp, rdx
0x180003065  mov     rax, [rcx]
0x180003068  mov     edx, [rax]
0x18000306a  mov     [rbp+0E0h], rcx
0x180003071  mov     [rbp+98h], edx
0x180003077  mov     eax, [rbp+98h]
0x18000307d  cmp     eax, 0E06D7363h
0x180003082  jnz     short loc_18000309E
0x180003084  mov     rdx, [rbp+0E0h]
0x18000308b  mov     ecx, [rbp+98h]
0x180003091  call    _XcptFilter_0
0x180003096  mov     [rbp+0A0h], eax
0x18000309c  jmp     short loc_1800030A8
0x18000309e  mov     dword ptr [rbp+0A0h], 0
0x1800030a8  mov     eax, [rbp+0A0h]
0x1800030ae  add     rsp, 20h
0x1800030b2  pop     rbp
0x1800030b3  retn
0x1800030b5  push    rbp
0x1800030b7  sub     rsp, 20h
0x1800030bb  mov     rbp, rdx
0x1800030be  cmp     dword ptr [rbp+118h], 1
0x1800030c5  ja      short loc_1800030D1
0x1800030c7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

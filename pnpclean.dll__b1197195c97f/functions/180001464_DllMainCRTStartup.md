# __DllMainCRTStartup

- ea: `0x180001464`
- end: `0x180001670`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001420`

## callees

- `0x1800011f0`
- `0x180001464`
- `0x180001954`
- `0x180002afc`
- `0x180008e70`

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
  if ( (_DWORD)fdwReason || dword_180010260 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180010264 = 1;
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
            if ( dword_180010264 )
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
0x180001464  mov     [rsp+lpvReserved], r8
0x180001469  mov     [rsp+arg_8], edx
0x18000146d  mov     [rsp+arg_0], rcx
0x180001472  push    rbx
0x180001473  push    rsi
0x180001474  push    rdi
0x180001475  sub     rsp, 0F0h
0x18000147c  mov     edi, edx
0x18000147e  mov     rsi, rcx
0x180001481  mov     ebx, 1
0x180001486  cmp     edx, ebx
0x180001488  ja      short loc_180001490
0x18000148a  mov     cs:__native_dllmain_reason, edx
0x180001490  test    edx, edx
0x180001492  jnz     short loc_1800014A7
0x180001494  cmp     cs:dword_180010260, edx
0x18000149a  jnz     short loc_1800014A7
0x18000149c  xor     ebx, ebx
0x18000149e  mov     [rsp+108h+var_E8], ebx
0x1800014a2  jmp     loc_180001654
0x1800014a7  lea     eax, [rdx-1]
0x1800014aa  cmp     eax, 1
0x1800014ad  ja      loc_180001534
0x1800014b3  mov     rax, cs:_pRawDllMain
0x1800014ba  test    rax, rax
0x1800014bd  jz      short loc_1800014F5
0x1800014bf  cmp     edx, 1
0x1800014c2  jnz     short loc_1800014CA
0x1800014c4  mov     cs:dword_180010264, edx
0x1800014ca  mov     r8, [rsp+108h+lpvReserved]
0x1800014d2  call    cs:__guard_dispatch_icall_fptr
0x1800014d8  mov     ebx, eax
0x1800014da  mov     [rsp+108h+var_E8], eax
0x1800014de  jmp     short loc_1800014F5
0x1800014e0  xor     ebx, ebx
0x1800014e2  mov     [rsp+108h+var_E8], ebx
0x1800014e6  mov     edi, [rsp+108h+arg_8]
0x1800014ed  mov     rsi, [rsp+108h+arg_0]
0x1800014f5  test    ebx, ebx
0x1800014f7  jz      loc_180001654
0x1800014fd  mov     r8, [rsp+108h+lpvReserved]
0x180001505  mov     edx, edi
0x180001507  mov     rcx, rsi
0x18000150a  call    _CRT_INIT
0x18000150f  mov     ebx, eax
0x180001511  mov     [rsp+108h+var_E8], eax
0x180001515  jmp     short loc_18000152C
0x180001517  xor     ebx, ebx
0x180001519  mov     [rsp+108h+var_E8], ebx
0x18000151d  mov     edi, [rsp+108h+arg_8]
0x180001524  mov     rsi, [rsp+108h+arg_0]
0x18000152c  test    ebx, ebx
0x18000152e  jz      loc_180001654
0x180001534  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000153c  mov     edx, edi; fdwReason
0x18000153e  mov     rcx, rsi; hinstDLL
0x180001541  call    DllMain
0x180001546  mov     ebx, eax
0x180001548  mov     [rsp+108h+var_E8], eax
0x18000154c  jmp     short loc_180001563
0x18000154e  xor     ebx, ebx
0x180001550  mov     [rsp+108h+var_E8], ebx
0x180001554  mov     edi, [rsp+108h+arg_8]
0x18000155b  mov     rsi, [rsp+108h+arg_0]
0x180001563  cmp     edi, 1
0x180001566  jnz     short loc_1800015DF
0x180001568  test    ebx, ebx
0x18000156a  jnz     short loc_1800015DF
0x18000156c  xor     r8d, r8d; lpvReserved
0x18000156f  xor     edx, edx; fdwReason
0x180001571  mov     rcx, rsi; hinstDLL
0x180001574  call    DllMain
0x180001579  jmp     short loc_18000158E
0x18000157b  mov     edi, [rsp+108h+arg_8]
0x180001582  mov     rsi, [rsp+108h+arg_0]
0x18000158a  mov     ebx, [rsp+108h+var_E8]
0x18000158e  xor     r8d, r8d
0x180001591  xor     edx, edx
0x180001593  mov     rcx, rsi
0x180001596  call    _CRT_INIT
0x18000159b  jmp     short loc_1800015B0
0x18000159d  mov     edi, [rsp+108h+arg_8]
0x1800015a4  mov     rsi, [rsp+108h+arg_0]
0x1800015ac  mov     ebx, [rsp+108h+var_E8]
0x1800015b0  mov     rax, cs:_pRawDllMain
0x1800015b7  test    rax, rax
0x1800015ba  jz      short loc_1800015DF
0x1800015bc  xor     r8d, r8d
0x1800015bf  xor     edx, edx
0x1800015c1  mov     rcx, rsi
0x1800015c4  call    cs:__guard_dispatch_icall_fptr
0x1800015ca  jmp     short loc_1800015DF
0x1800015cc  mov     edi, [rsp+108h+arg_8]
0x1800015d3  mov     rsi, [rsp+108h+arg_0]
0x1800015db  mov     ebx, [rsp+108h+var_E8]
0x1800015df  test    edi, edi
0x1800015e1  jz      short loc_1800015E8
0x1800015e3  cmp     edi, 3
0x1800015e6  jnz     short loc_180001654
0x1800015e8  mov     r8, [rsp+108h+lpvReserved]
0x1800015f0  mov     edx, edi
0x1800015f2  mov     rcx, rsi
0x1800015f5  call    _CRT_INIT
0x1800015fa  mov     ebx, eax
0x1800015fc  mov     [rsp+108h+var_E8], eax
0x180001600  jmp     short loc_180001617
0x180001602  xor     ebx, ebx
0x180001604  mov     [rsp+108h+var_E8], ebx
0x180001608  mov     edi, [rsp+108h+arg_8]
0x18000160f  mov     rsi, [rsp+108h+arg_0]
0x180001617  mov     rax, cs:_pRawDllMain
0x18000161e  test    rax, rax
0x180001621  jz      short loc_180001654
0x180001623  cmp     cs:dword_180010264, 0
0x18000162a  jz      short loc_180001654
0x18000162c  mov     r8, [rsp+108h+lpvReserved]
0x180001634  mov     edx, edi
0x180001636  mov     rcx, rsi
0x180001639  call    cs:__guard_dispatch_icall_fptr
0x18000163f  mov     ebx, eax
0x180001641  mov     [rsp+108h+var_E8], eax
0x180001645  jmp     short loc_180001654
0x180001647  xor     ebx, ebx
0x180001649  mov     [rsp+108h+var_E8], ebx
0x18000164d  mov     edi, [rsp+108h+arg_8]
0x180001654  cmp     edi, 1
0x180001657  ja      short loc_180001663
0x180001659  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001663  mov     eax, ebx
0x180001665  add     rsp, 0F0h
0x18000166c  pop     rdi
0x18000166d  pop     rsi
0x18000166e  pop     rbx
0x18000166f  retn
0x180008ee0  push    rbp
0x180008ee2  sub     rsp, 20h
0x180008ee6  mov     rbp, rdx
0x180008ee9  mov     rax, [rcx]
0x180008eec  mov     edx, [rax]
0x180008eee  mov     [rbp+0A8h], rcx
0x180008ef5  mov     [rbp+28h], edx
0x180008ef8  mov     eax, [rbp+28h]
0x180008efb  cmp     eax, 0E06D7363h
0x180008f00  jnz     short loc_180008F16
0x180008f02  mov     rdx, [rbp+0A8h]
0x180008f09  mov     ecx, [rbp+28h]
0x180008f0c  call    _XcptFilter_0
0x180008f11  mov     [rbp+30h], eax
0x180008f14  jmp     short loc_180008F1D
0x180008f16  mov     dword ptr [rbp+30h], 0
0x180008f1d  mov     eax, [rbp+30h]
0x180008f20  add     rsp, 20h
0x180008f24  pop     rbp
0x180008f25  retn
0x180008f27  push    rbp
0x180008f29  sub     rsp, 20h
0x180008f2d  mov     rbp, rdx
0x180008f30  mov     rax, [rcx]
0x180008f33  mov     edx, [rax]
0x180008f35  mov     [rbp+0B0h], rcx
0x180008f3c  mov     [rbp+38h], edx
0x180008f3f  mov     eax, [rbp+38h]
0x180008f42  cmp     eax, 0E06D7363h
0x180008f47  jnz     short loc_180008F5D
0x180008f49  mov     rdx, [rbp+0B0h]
0x180008f50  mov     ecx, [rbp+38h]
0x180008f53  call    _XcptFilter_0
0x180008f58  mov     [rbp+40h], eax
0x180008f5b  jmp     short loc_180008F64
0x180008f5d  mov     dword ptr [rbp+40h], 0
0x180008f64  mov     eax, [rbp+40h]
0x180008f67  add     rsp, 20h
0x180008f6b  pop     rbp
0x180008f6c  retn
0x180008f6e  push    rbp
0x180008f70  sub     rsp, 20h
0x180008f74  mov     rbp, rdx
0x180008f77  mov     rax, [rcx]
0x180008f7a  mov     edx, [rax]
0x180008f7c  mov     [rbp+0B8h], rcx
0x180008f83  mov     [rbp+48h], edx
0x180008f86  mov     eax, [rbp+48h]
0x180008f89  cmp     eax, 0E06D7363h
0x180008f8e  jnz     short loc_180008FA4
0x180008f90  mov     rdx, [rbp+0B8h]
0x180008f97  mov     ecx, [rbp+48h]
0x180008f9a  call    _XcptFilter_0
0x180008f9f  mov     [rbp+50h], eax
0x180008fa2  jmp     short loc_180008FAB
0x180008fa4  mov     dword ptr [rbp+50h], 0
0x180008fab  mov     eax, [rbp+50h]
0x180008fae  add     rsp, 20h
0x180008fb2  pop     rbp
0x180008fb3  retn
0x180008fb5  push    rbp
0x180008fb7  sub     rsp, 20h
0x180008fbb  mov     rbp, rdx
0x180008fbe  mov     rax, [rcx]
0x180008fc1  mov     edx, [rax]
0x180008fc3  mov     [rbp+0C0h], rcx
0x180008fca  mov     [rbp+58h], edx
0x180008fcd  mov     eax, [rbp+58h]
0x180008fd0  cmp     eax, 0E06D7363h
0x180008fd5  jnz     short loc_180008FEB
0x180008fd7  mov     rdx, [rbp+0C0h]
0x180008fde  mov     ecx, [rbp+58h]
0x180008fe1  call    _XcptFilter_0
0x180008fe6  mov     [rbp+60h], eax
0x180008fe9  jmp     short loc_180008FF2
0x180008feb  mov     dword ptr [rbp+60h], 0
0x180008ff2  mov     eax, [rbp+60h]
0x180008ff5  add     rsp, 20h
0x180008ff9  pop     rbp
0x180008ffa  retn
0x180008ffc  push    rbp
0x180008ffe  sub     rsp, 20h
0x180009002  mov     rbp, rdx
0x180009005  mov     rax, [rcx]
0x180009008  mov     edx, [rax]
0x18000900a  mov     [rbp+0C8h], rcx
0x180009011  mov     [rbp+68h], edx
0x180009014  mov     eax, [rbp+68h]
0x180009017  cmp     eax, 0E06D7363h
0x18000901c  jnz     short loc_180009032
0x18000901e  mov     rdx, [rbp+0C8h]
0x180009025  mov     ecx, [rbp+68h]
0x180009028  call    _XcptFilter_0
0x18000902d  mov     [rbp+70h], eax
0x180009030  jmp     short loc_180009039
0x180009032  mov     dword ptr [rbp+70h], 0
0x180009039  mov     eax, [rbp+70h]
0x18000903c  add     rsp, 20h
0x180009040  pop     rbp
0x180009041  retn
0x180009043  push    rbp
0x180009045  sub     rsp, 20h
0x180009049  mov     rbp, rdx
0x18000904c  mov     rax, [rcx]
0x18000904f  mov     edx, [rax]
0x180009051  mov     [rbp+0D0h], rcx
0x180009058  mov     [rbp+78h], edx
0x18000905b  mov     eax, [rbp+78h]
0x18000905e  cmp     eax, 0E06D7363h
0x180009063  jnz     short loc_18000907C
0x180009065  mov     rdx, [rbp+0D0h]
0x18000906c  mov     ecx, [rbp+78h]
0x18000906f  call    _XcptFilter_0
0x180009074  mov     [rbp+80h], eax
0x18000907a  jmp     short loc_180009086
0x18000907c  mov     dword ptr [rbp+80h], 0
0x180009086  mov     eax, [rbp+80h]
0x18000908c  add     rsp, 20h
0x180009090  pop     rbp
0x180009091  retn
0x180009093  push    rbp
0x180009095  sub     rsp, 20h
0x180009099  mov     rbp, rdx
0x18000909c  mov     rax, [rcx]
0x18000909f  mov     edx, [rax]
0x1800090a1  mov     [rbp+0D8h], rcx
0x1800090a8  mov     [rbp+88h], edx
0x1800090ae  mov     eax, [rbp+88h]
0x1800090b4  cmp     eax, 0E06D7363h
0x1800090b9  jnz     short loc_1800090D5
0x1800090bb  mov     rdx, [rbp+0D8h]
0x1800090c2  mov     ecx, [rbp+88h]
0x1800090c8  call    _XcptFilter_0
0x1800090cd  mov     [rbp+90h], eax
0x1800090d3  jmp     short loc_1800090DF
0x1800090d5  mov     dword ptr [rbp+90h], 0
0x1800090df  mov     eax, [rbp+90h]
0x1800090e5  add     rsp, 20h
0x1800090e9  pop     rbp
0x1800090ea  retn
0x1800090ec  push    rbp
0x1800090ee  sub     rsp, 20h
0x1800090f2  mov     rbp, rdx
0x1800090f5  mov     rax, [rcx]
0x1800090f8  mov     edx, [rax]
0x1800090fa  mov     [rbp+0E0h], rcx
0x180009101  mov     [rbp+98h], edx
0x180009107  mov     eax, [rbp+98h]
0x18000910d  cmp     eax, 0E06D7363h
0x180009112  jnz     short loc_18000912E
0x180009114  mov     rdx, [rbp+0E0h]
0x18000911b  mov     ecx, [rbp+98h]
0x180009121  call    _XcptFilter_0
0x180009126  mov     [rbp+0A0h], eax
0x18000912c  jmp     short loc_180009138
0x18000912e  mov     dword ptr [rbp+0A0h], 0
0x180009138  mov     eax, [rbp+0A0h]
0x18000913e  add     rsp, 20h
0x180009142  pop     rbp
0x180009143  retn
0x180009145  push    rbp
0x180009147  sub     rsp, 20h
0x18000914b  mov     rbp, rdx
0x18000914e  cmp     dword ptr [rbp+118h], 1
0x180009155  ja      short loc_180009161
0x180009157  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

# __DllMainCRTStartup

- ea: `0x1800013c4`
- end: `0x1800015d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001380`

## callees

- `0x180001150`
- `0x1800013c4`
- `0x180001a2c`
- `0x180005c40`
- `0x180006070`

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
  if ( (_DWORD)fdwReason || dword_18000B220 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000B224 = 1;
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
            if ( dword_18000B224 )
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
0x1800013c4  mov     [rsp+lpvReserved], r8
0x1800013c9  mov     [rsp+arg_8], edx
0x1800013cd  mov     [rsp+arg_0], rcx
0x1800013d2  push    rbx
0x1800013d3  push    rsi
0x1800013d4  push    rdi
0x1800013d5  sub     rsp, 0F0h
0x1800013dc  mov     edi, edx
0x1800013de  mov     rsi, rcx
0x1800013e1  mov     ebx, 1
0x1800013e6  cmp     edx, ebx
0x1800013e8  ja      short loc_1800013F0
0x1800013ea  mov     cs:__native_dllmain_reason, edx
0x1800013f0  test    edx, edx
0x1800013f2  jnz     short loc_180001407
0x1800013f4  cmp     cs:dword_18000B220, edx
0x1800013fa  jnz     short loc_180001407
0x1800013fc  xor     ebx, ebx
0x1800013fe  mov     [rsp+108h+var_E8], ebx
0x180001402  jmp     loc_1800015B4
0x180001407  lea     eax, [rdx-1]
0x18000140a  cmp     eax, 1
0x18000140d  ja      loc_180001494
0x180001413  mov     rax, cs:_pRawDllMain
0x18000141a  test    rax, rax
0x18000141d  jz      short loc_180001455
0x18000141f  cmp     edx, 1
0x180001422  jnz     short loc_18000142A
0x180001424  mov     cs:dword_18000B224, edx
0x18000142a  mov     r8, [rsp+108h+lpvReserved]
0x180001432  call    cs:__guard_dispatch_icall_fptr
0x180001438  mov     ebx, eax
0x18000143a  mov     [rsp+108h+var_E8], eax
0x18000143e  jmp     short loc_180001455
0x180001440  xor     ebx, ebx
0x180001442  mov     [rsp+108h+var_E8], ebx
0x180001446  mov     edi, [rsp+108h+arg_8]
0x18000144d  mov     rsi, [rsp+108h+arg_0]
0x180001455  test    ebx, ebx
0x180001457  jz      loc_1800015B4
0x18000145d  mov     r8, [rsp+108h+lpvReserved]
0x180001465  mov     edx, edi
0x180001467  mov     rcx, rsi
0x18000146a  call    _CRT_INIT
0x18000146f  mov     ebx, eax
0x180001471  mov     [rsp+108h+var_E8], eax
0x180001475  jmp     short loc_18000148C
0x180001477  xor     ebx, ebx
0x180001479  mov     [rsp+108h+var_E8], ebx
0x18000147d  mov     edi, [rsp+108h+arg_8]
0x180001484  mov     rsi, [rsp+108h+arg_0]
0x18000148c  test    ebx, ebx
0x18000148e  jz      loc_1800015B4
0x180001494  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000149c  mov     edx, edi; fdwReason
0x18000149e  mov     rcx, rsi; hinstDLL
0x1800014a1  call    DllMain
0x1800014a6  mov     ebx, eax
0x1800014a8  mov     [rsp+108h+var_E8], eax
0x1800014ac  jmp     short loc_1800014C3
0x1800014ae  xor     ebx, ebx
0x1800014b0  mov     [rsp+108h+var_E8], ebx
0x1800014b4  mov     edi, [rsp+108h+arg_8]
0x1800014bb  mov     rsi, [rsp+108h+arg_0]
0x1800014c3  cmp     edi, 1
0x1800014c6  jnz     short loc_18000153F
0x1800014c8  test    ebx, ebx
0x1800014ca  jnz     short loc_18000153F
0x1800014cc  xor     r8d, r8d; lpvReserved
0x1800014cf  xor     edx, edx; fdwReason
0x1800014d1  mov     rcx, rsi; hinstDLL
0x1800014d4  call    DllMain
0x1800014d9  jmp     short loc_1800014EE
0x1800014db  mov     edi, [rsp+108h+arg_8]
0x1800014e2  mov     rsi, [rsp+108h+arg_0]
0x1800014ea  mov     ebx, [rsp+108h+var_E8]
0x1800014ee  xor     r8d, r8d
0x1800014f1  xor     edx, edx
0x1800014f3  mov     rcx, rsi
0x1800014f6  call    _CRT_INIT
0x1800014fb  jmp     short loc_180001510
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  mov     rsi, [rsp+108h+arg_0]
0x18000150c  mov     ebx, [rsp+108h+var_E8]
0x180001510  mov     rax, cs:_pRawDllMain
0x180001517  test    rax, rax
0x18000151a  jz      short loc_18000153F
0x18000151c  xor     r8d, r8d
0x18000151f  xor     edx, edx
0x180001521  mov     rcx, rsi
0x180001524  call    cs:__guard_dispatch_icall_fptr
0x18000152a  jmp     short loc_18000153F
0x18000152c  mov     edi, [rsp+108h+arg_8]
0x180001533  mov     rsi, [rsp+108h+arg_0]
0x18000153b  mov     ebx, [rsp+108h+var_E8]
0x18000153f  test    edi, edi
0x180001541  jz      short loc_180001548
0x180001543  cmp     edi, 3
0x180001546  jnz     short loc_1800015B4
0x180001548  mov     r8, [rsp+108h+lpvReserved]
0x180001550  mov     edx, edi
0x180001552  mov     rcx, rsi
0x180001555  call    _CRT_INIT
0x18000155a  mov     ebx, eax
0x18000155c  mov     [rsp+108h+var_E8], eax
0x180001560  jmp     short loc_180001577
0x180001562  xor     ebx, ebx
0x180001564  mov     [rsp+108h+var_E8], ebx
0x180001568  mov     edi, [rsp+108h+arg_8]
0x18000156f  mov     rsi, [rsp+108h+arg_0]
0x180001577  mov     rax, cs:_pRawDllMain
0x18000157e  test    rax, rax
0x180001581  jz      short loc_1800015B4
0x180001583  cmp     cs:dword_18000B224, 0
0x18000158a  jz      short loc_1800015B4
0x18000158c  mov     r8, [rsp+108h+lpvReserved]
0x180001594  mov     edx, edi
0x180001596  mov     rcx, rsi
0x180001599  call    cs:__guard_dispatch_icall_fptr
0x18000159f  mov     ebx, eax
0x1800015a1  mov     [rsp+108h+var_E8], eax
0x1800015a5  jmp     short loc_1800015B4
0x1800015a7  xor     ebx, ebx
0x1800015a9  mov     [rsp+108h+var_E8], ebx
0x1800015ad  mov     edi, [rsp+108h+arg_8]
0x1800015b4  cmp     edi, 1
0x1800015b7  ja      short loc_1800015C3
0x1800015b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800015c3  mov     eax, ebx
0x1800015c5  add     rsp, 0F0h
0x1800015cc  pop     rdi
0x1800015cd  pop     rsi
0x1800015ce  pop     rbx
0x1800015cf  retn
0x180006140  push    rbp
0x180006142  sub     rsp, 20h
0x180006146  mov     rbp, rdx
0x180006149  mov     rax, [rcx]
0x18000614c  mov     edx, [rax]
0x18000614e  mov     [rbp+0A8h], rcx
0x180006155  mov     [rbp+28h], edx
0x180006158  mov     eax, [rbp+28h]
0x18000615b  cmp     eax, 0E06D7363h
0x180006160  jnz     short loc_180006176
0x180006162  mov     rdx, [rbp+0A8h]
0x180006169  mov     ecx, [rbp+28h]
0x18000616c  call    _XcptFilter_0
0x180006171  mov     [rbp+30h], eax
0x180006174  jmp     short loc_18000617D
0x180006176  mov     dword ptr [rbp+30h], 0
0x18000617d  mov     eax, [rbp+30h]
0x180006180  add     rsp, 20h
0x180006184  pop     rbp
0x180006185  retn
0x180006187  push    rbp
0x180006189  sub     rsp, 20h
0x18000618d  mov     rbp, rdx
0x180006190  mov     rax, [rcx]
0x180006193  mov     edx, [rax]
0x180006195  mov     [rbp+0B0h], rcx
0x18000619c  mov     [rbp+38h], edx
0x18000619f  mov     eax, [rbp+38h]
0x1800061a2  cmp     eax, 0E06D7363h
0x1800061a7  jnz     short loc_1800061BD
0x1800061a9  mov     rdx, [rbp+0B0h]
0x1800061b0  mov     ecx, [rbp+38h]
0x1800061b3  call    _XcptFilter_0
0x1800061b8  mov     [rbp+40h], eax
0x1800061bb  jmp     short loc_1800061C4
0x1800061bd  mov     dword ptr [rbp+40h], 0
0x1800061c4  mov     eax, [rbp+40h]
0x1800061c7  add     rsp, 20h
0x1800061cb  pop     rbp
0x1800061cc  retn
0x1800061ce  push    rbp
0x1800061d0  sub     rsp, 20h
0x1800061d4  mov     rbp, rdx
0x1800061d7  mov     rax, [rcx]
0x1800061da  mov     edx, [rax]
0x1800061dc  mov     [rbp+0B8h], rcx
0x1800061e3  mov     [rbp+48h], edx
0x1800061e6  mov     eax, [rbp+48h]
0x1800061e9  cmp     eax, 0E06D7363h
0x1800061ee  jnz     short loc_180006204
0x1800061f0  mov     rdx, [rbp+0B8h]
0x1800061f7  mov     ecx, [rbp+48h]
0x1800061fa  call    _XcptFilter_0
0x1800061ff  mov     [rbp+50h], eax
0x180006202  jmp     short loc_18000620B
0x180006204  mov     dword ptr [rbp+50h], 0
0x18000620b  mov     eax, [rbp+50h]
0x18000620e  add     rsp, 20h
0x180006212  pop     rbp
0x180006213  retn
0x180006215  push    rbp
0x180006217  sub     rsp, 20h
0x18000621b  mov     rbp, rdx
0x18000621e  mov     rax, [rcx]
0x180006221  mov     edx, [rax]
0x180006223  mov     [rbp+0C0h], rcx
0x18000622a  mov     [rbp+58h], edx
0x18000622d  mov     eax, [rbp+58h]
0x180006230  cmp     eax, 0E06D7363h
0x180006235  jnz     short loc_18000624B
0x180006237  mov     rdx, [rbp+0C0h]
0x18000623e  mov     ecx, [rbp+58h]
0x180006241  call    _XcptFilter_0
0x180006246  mov     [rbp+60h], eax
0x180006249  jmp     short loc_180006252
0x18000624b  mov     dword ptr [rbp+60h], 0
0x180006252  mov     eax, [rbp+60h]
0x180006255  add     rsp, 20h
0x180006259  pop     rbp
0x18000625a  retn
0x18000625c  push    rbp
0x18000625e  sub     rsp, 20h
0x180006262  mov     rbp, rdx
0x180006265  mov     rax, [rcx]
0x180006268  mov     edx, [rax]
0x18000626a  mov     [rbp+0C8h], rcx
0x180006271  mov     [rbp+68h], edx
0x180006274  mov     eax, [rbp+68h]
0x180006277  cmp     eax, 0E06D7363h
0x18000627c  jnz     short loc_180006292
0x18000627e  mov     rdx, [rbp+0C8h]
0x180006285  mov     ecx, [rbp+68h]
0x180006288  call    _XcptFilter_0
0x18000628d  mov     [rbp+70h], eax
0x180006290  jmp     short loc_180006299
0x180006292  mov     dword ptr [rbp+70h], 0
0x180006299  mov     eax, [rbp+70h]
0x18000629c  add     rsp, 20h
0x1800062a0  pop     rbp
0x1800062a1  retn
0x1800062a3  push    rbp
0x1800062a5  sub     rsp, 20h
0x1800062a9  mov     rbp, rdx
0x1800062ac  mov     rax, [rcx]
0x1800062af  mov     edx, [rax]
0x1800062b1  mov     [rbp+0D0h], rcx
0x1800062b8  mov     [rbp+78h], edx
0x1800062bb  mov     eax, [rbp+78h]
0x1800062be  cmp     eax, 0E06D7363h
0x1800062c3  jnz     short loc_1800062DC
0x1800062c5  mov     rdx, [rbp+0D0h]
0x1800062cc  mov     ecx, [rbp+78h]
0x1800062cf  call    _XcptFilter_0
0x1800062d4  mov     [rbp+80h], eax
0x1800062da  jmp     short loc_1800062E6
0x1800062dc  mov     dword ptr [rbp+80h], 0
0x1800062e6  mov     eax, [rbp+80h]
0x1800062ec  add     rsp, 20h
0x1800062f0  pop     rbp
0x1800062f1  retn
0x1800062f3  push    rbp
0x1800062f5  sub     rsp, 20h
0x1800062f9  mov     rbp, rdx
0x1800062fc  mov     rax, [rcx]
0x1800062ff  mov     edx, [rax]
0x180006301  mov     [rbp+0D8h], rcx
0x180006308  mov     [rbp+88h], edx
0x18000630e  mov     eax, [rbp+88h]
0x180006314  cmp     eax, 0E06D7363h
0x180006319  jnz     short loc_180006335
0x18000631b  mov     rdx, [rbp+0D8h]
0x180006322  mov     ecx, [rbp+88h]
0x180006328  call    _XcptFilter_0
0x18000632d  mov     [rbp+90h], eax
0x180006333  jmp     short loc_18000633F
0x180006335  mov     dword ptr [rbp+90h], 0
0x18000633f  mov     eax, [rbp+90h]
0x180006345  add     rsp, 20h
0x180006349  pop     rbp
0x18000634a  retn
0x18000634c  push    rbp
0x18000634e  sub     rsp, 20h
0x180006352  mov     rbp, rdx
0x180006355  mov     rax, [rcx]
0x180006358  mov     edx, [rax]
0x18000635a  mov     [rbp+0E0h], rcx
0x180006361  mov     [rbp+98h], edx
0x180006367  mov     eax, [rbp+98h]
0x18000636d  cmp     eax, 0E06D7363h
0x180006372  jnz     short loc_18000638E
0x180006374  mov     rdx, [rbp+0E0h]
0x18000637b  mov     ecx, [rbp+98h]
0x180006381  call    _XcptFilter_0
0x180006386  mov     [rbp+0A0h], eax
0x18000638c  jmp     short loc_180006398
0x18000638e  mov     dword ptr [rbp+0A0h], 0
0x180006398  mov     eax, [rbp+0A0h]
0x18000639e  add     rsp, 20h
0x1800063a2  pop     rbp
0x1800063a3  retn
0x1800063a5  push    rbp
0x1800063a7  sub     rsp, 20h
0x1800063ab  mov     rbp, rdx
0x1800063ae  cmp     dword ptr [rbp+118h], 1
0x1800063b5  ja      short loc_1800063C1
0x1800063b7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

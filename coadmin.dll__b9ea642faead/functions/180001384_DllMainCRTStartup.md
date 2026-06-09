# __DllMainCRTStartup

- ea: `0x180001384`
- end: `0x180001590`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001340`

## callees

- `0x180001110`
- `0x180001384`
- `0x18000185a`
- `0x180009f30`
- `0x18000fb90`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  unsigned int v5; // ebx

  v3 = a2;
  v5 = 1;
  if ( (unsigned int)a2 <= 1 )
    _native_dllmain_reason = a2;
  if ( (_DWORD)a2 || dword_180016900 )
  {
    if ( (unsigned int)(a2 - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)a2 == 1 )
        dword_180016904 = 1;
      v5 = pRawDllMain(a1, a2, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(a1, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain();
        if ( v3 == 1 && !v5 )
        {
          DllMain();
          CRT_INIT(a1, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(a1, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(a1, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_180016904 )
              v5 = pRawDllMain(a1, v3, a3);
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
0x180001384  mov     [rsp+arg_10], r8
0x180001389  mov     [rsp+arg_8], edx
0x18000138d  mov     [rsp+arg_0], rcx
0x180001392  push    rbx
0x180001393  push    rsi
0x180001394  push    rdi
0x180001395  sub     rsp, 0F0h
0x18000139c  mov     edi, edx
0x18000139e  mov     rsi, rcx
0x1800013a1  mov     ebx, 1
0x1800013a6  cmp     edx, ebx
0x1800013a8  ja      short loc_1800013B0
0x1800013aa  mov     cs:__native_dllmain_reason, edx
0x1800013b0  test    edx, edx
0x1800013b2  jnz     short loc_1800013C7
0x1800013b4  cmp     cs:dword_180016900, edx
0x1800013ba  jnz     short loc_1800013C7
0x1800013bc  xor     ebx, ebx
0x1800013be  mov     [rsp+108h+var_E8], ebx
0x1800013c2  jmp     loc_180001574
0x1800013c7  lea     eax, [rdx-1]
0x1800013ca  cmp     eax, 1
0x1800013cd  ja      loc_180001454
0x1800013d3  mov     rax, cs:_pRawDllMain
0x1800013da  test    rax, rax
0x1800013dd  jz      short loc_180001415
0x1800013df  cmp     edx, 1
0x1800013e2  jnz     short loc_1800013EA
0x1800013e4  mov     cs:dword_180016904, edx
0x1800013ea  mov     r8, [rsp+108h+arg_10]
0x1800013f2  call    cs:__guard_dispatch_icall_fptr
0x1800013f8  mov     ebx, eax
0x1800013fa  mov     [rsp+108h+var_E8], eax
0x1800013fe  jmp     short loc_180001415
0x180001400  xor     ebx, ebx
0x180001402  mov     [rsp+108h+var_E8], ebx
0x180001406  mov     edi, [rsp+108h+arg_8]
0x18000140d  mov     rsi, [rsp+108h+arg_0]
0x180001415  test    ebx, ebx
0x180001417  jz      loc_180001574
0x18000141d  mov     r8, [rsp+108h+arg_10]
0x180001425  mov     edx, edi
0x180001427  mov     rcx, rsi
0x18000142a  call    _CRT_INIT
0x18000142f  mov     ebx, eax
0x180001431  mov     [rsp+108h+var_E8], eax
0x180001435  jmp     short loc_18000144C
0x180001437  xor     ebx, ebx
0x180001439  mov     [rsp+108h+var_E8], ebx
0x18000143d  mov     edi, [rsp+108h+arg_8]
0x180001444  mov     rsi, [rsp+108h+arg_0]
0x18000144c  test    ebx, ebx
0x18000144e  jz      loc_180001574
0x180001454  mov     r8, [rsp+108h+arg_10]
0x18000145c  mov     edx, edi
0x18000145e  mov     rcx, rsi
0x180001461  call    DllMain
0x180001466  mov     ebx, eax
0x180001468  mov     [rsp+108h+var_E8], eax
0x18000146c  jmp     short loc_180001483
0x18000146e  xor     ebx, ebx
0x180001470  mov     [rsp+108h+var_E8], ebx
0x180001474  mov     edi, [rsp+108h+arg_8]
0x18000147b  mov     rsi, [rsp+108h+arg_0]
0x180001483  cmp     edi, 1
0x180001486  jnz     short loc_1800014FF
0x180001488  test    ebx, ebx
0x18000148a  jnz     short loc_1800014FF
0x18000148c  xor     r8d, r8d
0x18000148f  xor     edx, edx
0x180001491  mov     rcx, rsi
0x180001494  call    DllMain
0x180001499  jmp     short loc_1800014AE
0x18000149b  mov     edi, [rsp+108h+arg_8]
0x1800014a2  mov     rsi, [rsp+108h+arg_0]
0x1800014aa  mov     ebx, [rsp+108h+var_E8]
0x1800014ae  xor     r8d, r8d
0x1800014b1  xor     edx, edx
0x1800014b3  mov     rcx, rsi
0x1800014b6  call    _CRT_INIT
0x1800014bb  jmp     short loc_1800014D0
0x1800014bd  mov     edi, [rsp+108h+arg_8]
0x1800014c4  mov     rsi, [rsp+108h+arg_0]
0x1800014cc  mov     ebx, [rsp+108h+var_E8]
0x1800014d0  mov     rax, cs:_pRawDllMain
0x1800014d7  test    rax, rax
0x1800014da  jz      short loc_1800014FF
0x1800014dc  xor     r8d, r8d
0x1800014df  xor     edx, edx
0x1800014e1  mov     rcx, rsi
0x1800014e4  call    cs:__guard_dispatch_icall_fptr
0x1800014ea  jmp     short loc_1800014FF
0x1800014ec  mov     edi, [rsp+108h+arg_8]
0x1800014f3  mov     rsi, [rsp+108h+arg_0]
0x1800014fb  mov     ebx, [rsp+108h+var_E8]
0x1800014ff  test    edi, edi
0x180001501  jz      short loc_180001508
0x180001503  cmp     edi, 3
0x180001506  jnz     short loc_180001574
0x180001508  mov     r8, [rsp+108h+arg_10]
0x180001510  mov     edx, edi
0x180001512  mov     rcx, rsi
0x180001515  call    _CRT_INIT
0x18000151a  mov     ebx, eax
0x18000151c  mov     [rsp+108h+var_E8], eax
0x180001520  jmp     short loc_180001537
0x180001522  xor     ebx, ebx
0x180001524  mov     [rsp+108h+var_E8], ebx
0x180001528  mov     edi, [rsp+108h+arg_8]
0x18000152f  mov     rsi, [rsp+108h+arg_0]
0x180001537  mov     rax, cs:_pRawDllMain
0x18000153e  test    rax, rax
0x180001541  jz      short loc_180001574
0x180001543  cmp     cs:dword_180016904, 0
0x18000154a  jz      short loc_180001574
0x18000154c  mov     r8, [rsp+108h+arg_10]
0x180001554  mov     edx, edi
0x180001556  mov     rcx, rsi
0x180001559  call    cs:__guard_dispatch_icall_fptr
0x18000155f  mov     ebx, eax
0x180001561  mov     [rsp+108h+var_E8], eax
0x180001565  jmp     short loc_180001574
0x180001567  xor     ebx, ebx
0x180001569  mov     [rsp+108h+var_E8], ebx
0x18000156d  mov     edi, [rsp+108h+arg_8]
0x180001574  cmp     edi, 1
0x180001577  ja      short loc_180001583
0x180001579  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001583  mov     eax, ebx
0x180001585  add     rsp, 0F0h
0x18000158c  pop     rdi
0x18000158d  pop     rsi
0x18000158e  pop     rbx
0x18000158f  retn
0x18000fc60  push    rbp
0x18000fc62  sub     rsp, 20h
0x18000fc66  mov     rbp, rdx
0x18000fc69  mov     rax, [rcx]
0x18000fc6c  mov     edx, [rax]
0x18000fc6e  mov     [rbp+0A8h], rcx
0x18000fc75  mov     [rbp+28h], edx
0x18000fc78  mov     eax, [rbp+28h]
0x18000fc7b  cmp     eax, 0E06D7363h
0x18000fc80  jnz     short loc_18000FC96
0x18000fc82  mov     rdx, [rbp+0A8h]
0x18000fc89  mov     ecx, [rbp+28h]
0x18000fc8c  call    _XcptFilter_0
0x18000fc91  mov     [rbp+30h], eax
0x18000fc94  jmp     short loc_18000FC9D
0x18000fc96  mov     dword ptr [rbp+30h], 0
0x18000fc9d  mov     eax, [rbp+30h]
0x18000fca0  add     rsp, 20h
0x18000fca4  pop     rbp
0x18000fca5  retn
0x18000fca7  push    rbp
0x18000fca9  sub     rsp, 20h
0x18000fcad  mov     rbp, rdx
0x18000fcb0  mov     rax, [rcx]
0x18000fcb3  mov     edx, [rax]
0x18000fcb5  mov     [rbp+0B0h], rcx
0x18000fcbc  mov     [rbp+38h], edx
0x18000fcbf  mov     eax, [rbp+38h]
0x18000fcc2  cmp     eax, 0E06D7363h
0x18000fcc7  jnz     short loc_18000FCDD
0x18000fcc9  mov     rdx, [rbp+0B0h]
0x18000fcd0  mov     ecx, [rbp+38h]
0x18000fcd3  call    _XcptFilter_0
0x18000fcd8  mov     [rbp+40h], eax
0x18000fcdb  jmp     short loc_18000FCE4
0x18000fcdd  mov     dword ptr [rbp+40h], 0
0x18000fce4  mov     eax, [rbp+40h]
0x18000fce7  add     rsp, 20h
0x18000fceb  pop     rbp
0x18000fcec  retn
0x18000fcee  push    rbp
0x18000fcf0  sub     rsp, 20h
0x18000fcf4  mov     rbp, rdx
0x18000fcf7  mov     rax, [rcx]
0x18000fcfa  mov     edx, [rax]
0x18000fcfc  mov     [rbp+0B8h], rcx
0x18000fd03  mov     [rbp+48h], edx
0x18000fd06  mov     eax, [rbp+48h]
0x18000fd09  cmp     eax, 0E06D7363h
0x18000fd0e  jnz     short loc_18000FD24
0x18000fd10  mov     rdx, [rbp+0B8h]
0x18000fd17  mov     ecx, [rbp+48h]
0x18000fd1a  call    _XcptFilter_0
0x18000fd1f  mov     [rbp+50h], eax
0x18000fd22  jmp     short loc_18000FD2B
0x18000fd24  mov     dword ptr [rbp+50h], 0
0x18000fd2b  mov     eax, [rbp+50h]
0x18000fd2e  add     rsp, 20h
0x18000fd32  pop     rbp
0x18000fd33  retn
0x18000fd35  push    rbp
0x18000fd37  sub     rsp, 20h
0x18000fd3b  mov     rbp, rdx
0x18000fd3e  mov     rax, [rcx]
0x18000fd41  mov     edx, [rax]
0x18000fd43  mov     [rbp+0C0h], rcx
0x18000fd4a  mov     [rbp+58h], edx
0x18000fd4d  mov     eax, [rbp+58h]
0x18000fd50  cmp     eax, 0E06D7363h
0x18000fd55  jnz     short loc_18000FD6B
0x18000fd57  mov     rdx, [rbp+0C0h]
0x18000fd5e  mov     ecx, [rbp+58h]
0x18000fd61  call    _XcptFilter_0
0x18000fd66  mov     [rbp+60h], eax
0x18000fd69  jmp     short loc_18000FD72
0x18000fd6b  mov     dword ptr [rbp+60h], 0
0x18000fd72  mov     eax, [rbp+60h]
0x18000fd75  add     rsp, 20h
0x18000fd79  pop     rbp
0x18000fd7a  retn
0x18000fd7c  push    rbp
0x18000fd7e  sub     rsp, 20h
0x18000fd82  mov     rbp, rdx
0x18000fd85  mov     rax, [rcx]
0x18000fd88  mov     edx, [rax]
0x18000fd8a  mov     [rbp+0C8h], rcx
0x18000fd91  mov     [rbp+68h], edx
0x18000fd94  mov     eax, [rbp+68h]
0x18000fd97  cmp     eax, 0E06D7363h
0x18000fd9c  jnz     short loc_18000FDB2
0x18000fd9e  mov     rdx, [rbp+0C8h]
0x18000fda5  mov     ecx, [rbp+68h]
0x18000fda8  call    _XcptFilter_0
0x18000fdad  mov     [rbp+70h], eax
0x18000fdb0  jmp     short loc_18000FDB9
0x18000fdb2  mov     dword ptr [rbp+70h], 0
0x18000fdb9  mov     eax, [rbp+70h]
0x18000fdbc  add     rsp, 20h
0x18000fdc0  pop     rbp
0x18000fdc1  retn
0x18000fdc3  push    rbp
0x18000fdc5  sub     rsp, 20h
0x18000fdc9  mov     rbp, rdx
0x18000fdcc  mov     rax, [rcx]
0x18000fdcf  mov     edx, [rax]
0x18000fdd1  mov     [rbp+0D0h], rcx
0x18000fdd8  mov     [rbp+78h], edx
0x18000fddb  mov     eax, [rbp+78h]
0x18000fdde  cmp     eax, 0E06D7363h
0x18000fde3  jnz     short loc_18000FDFC
0x18000fde5  mov     rdx, [rbp+0D0h]
0x18000fdec  mov     ecx, [rbp+78h]
0x18000fdef  call    _XcptFilter_0
0x18000fdf4  mov     [rbp+80h], eax
0x18000fdfa  jmp     short loc_18000FE06
0x18000fdfc  mov     dword ptr [rbp+80h], 0
0x18000fe06  mov     eax, [rbp+80h]
0x18000fe0c  add     rsp, 20h
0x18000fe10  pop     rbp
0x18000fe11  retn
0x18000fe13  push    rbp
0x18000fe15  sub     rsp, 20h
0x18000fe19  mov     rbp, rdx
0x18000fe1c  mov     rax, [rcx]
0x18000fe1f  mov     edx, [rax]
0x18000fe21  mov     [rbp+0D8h], rcx
0x18000fe28  mov     [rbp+88h], edx
0x18000fe2e  mov     eax, [rbp+88h]
0x18000fe34  cmp     eax, 0E06D7363h
0x18000fe39  jnz     short loc_18000FE55
0x18000fe3b  mov     rdx, [rbp+0D8h]
0x18000fe42  mov     ecx, [rbp+88h]
0x18000fe48  call    _XcptFilter_0
0x18000fe4d  mov     [rbp+90h], eax
0x18000fe53  jmp     short loc_18000FE5F
0x18000fe55  mov     dword ptr [rbp+90h], 0
0x18000fe5f  mov     eax, [rbp+90h]
0x18000fe65  add     rsp, 20h
0x18000fe69  pop     rbp
0x18000fe6a  retn
0x18000fe6c  push    rbp
0x18000fe6e  sub     rsp, 20h
0x18000fe72  mov     rbp, rdx
0x18000fe75  mov     rax, [rcx]
0x18000fe78  mov     edx, [rax]
0x18000fe7a  mov     [rbp+0E0h], rcx
0x18000fe81  mov     [rbp+98h], edx
0x18000fe87  mov     eax, [rbp+98h]
0x18000fe8d  cmp     eax, 0E06D7363h
0x18000fe92  jnz     short loc_18000FEAE
0x18000fe94  mov     rdx, [rbp+0E0h]
0x18000fe9b  mov     ecx, [rbp+98h]
0x18000fea1  call    _XcptFilter_0
0x18000fea6  mov     [rbp+0A0h], eax
0x18000feac  jmp     short loc_18000FEB8
0x18000feae  mov     dword ptr [rbp+0A0h], 0
0x18000feb8  mov     eax, [rbp+0A0h]
0x18000febe  add     rsp, 20h
0x18000fec2  pop     rbp
0x18000fec3  retn
0x18000fec5  push    rbp
0x18000fec7  sub     rsp, 20h
0x18000fecb  mov     rbp, rdx
0x18000fece  cmp     dword ptr [rbp+118h], 1
0x18000fed5  ja      short loc_18000FEE1
0x18000fed7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

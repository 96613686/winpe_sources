# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(CInetLogInformation *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000154a`
- `0x180002e00`
- `0x180003810`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(CInetLogInformation *this, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  unsigned int v5; // ebx

  v3 = a2;
  v5 = 1;
  if ( (unsigned int)a2 <= 1 )
    _native_dllmain_reason = a2;
  if ( (_DWORD)a2 || dword_1800080A0 )
  {
    if ( (unsigned int)(a2 - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)a2 == 1 )
        dword_1800080A4 = 1;
      v5 = pRawDllMain(this, a2, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(this, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = CInetLogInformation::AddRef(this);
        if ( v3 == 1 && !v5 )
        {
          CInetLogInformation::AddRef(this);
          CRT_INIT(this, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(this, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(this, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_1800080A4 )
              v5 = pRawDllMain(this, v3, a3);
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
0x180001314  mov     [rsp+arg_10], r8
0x180001319  mov     [rsp+arg_8], edx
0x18000131d  mov     [rsp+arg_0], rcx
0x180001322  push    rbx
0x180001323  push    rsi
0x180001324  push    rdi
0x180001325  sub     rsp, 0F0h
0x18000132c  mov     edi, edx
0x18000132e  mov     rsi, rcx
0x180001331  mov     ebx, 1
0x180001336  cmp     edx, ebx
0x180001338  ja      short loc_180001340
0x18000133a  mov     cs:__native_dllmain_reason, edx
0x180001340  test    edx, edx
0x180001342  jnz     short loc_180001357
0x180001344  cmp     cs:dword_1800080A0, edx
0x18000134a  jnz     short loc_180001357
0x18000134c  xor     ebx, ebx
0x18000134e  mov     [rsp+108h+var_E8], ebx
0x180001352  jmp     loc_180001504
0x180001357  lea     eax, [rdx-1]
0x18000135a  cmp     eax, 1
0x18000135d  ja      loc_1800013E4
0x180001363  mov     rax, cs:_pRawDllMain
0x18000136a  test    rax, rax
0x18000136d  jz      short loc_1800013A5
0x18000136f  cmp     edx, 1
0x180001372  jnz     short loc_18000137A
0x180001374  mov     cs:dword_1800080A4, edx
0x18000137a  mov     r8, [rsp+108h+arg_10]
0x180001382  call    cs:__guard_dispatch_icall_fptr
0x180001388  mov     ebx, eax
0x18000138a  mov     [rsp+108h+var_E8], eax
0x18000138e  jmp     short loc_1800013A5
0x180001390  xor     ebx, ebx
0x180001392  mov     [rsp+108h+var_E8], ebx
0x180001396  mov     edi, [rsp+108h+arg_8]
0x18000139d  mov     rsi, [rsp+108h+arg_0]
0x1800013a5  test    ebx, ebx
0x1800013a7  jz      loc_180001504
0x1800013ad  mov     r8, [rsp+108h+arg_10]
0x1800013b5  mov     edx, edi
0x1800013b7  mov     rcx, rsi
0x1800013ba  call    _CRT_INIT
0x1800013bf  mov     ebx, eax
0x1800013c1  mov     [rsp+108h+var_E8], eax
0x1800013c5  jmp     short loc_1800013DC
0x1800013c7  xor     ebx, ebx
0x1800013c9  mov     [rsp+108h+var_E8], ebx
0x1800013cd  mov     edi, [rsp+108h+arg_8]
0x1800013d4  mov     rsi, [rsp+108h+arg_0]
0x1800013dc  test    ebx, ebx
0x1800013de  jz      loc_180001504
0x1800013e4  mov     r8, [rsp+108h+arg_10]
0x1800013ec  mov     edx, edi
0x1800013ee  mov     rcx, rsi; this
0x1800013f1  call    ?AddRef@CInetLogInformation@@UEAAKXZ; CInetLogInformation::AddRef(void)
0x1800013f6  mov     ebx, eax
0x1800013f8  mov     [rsp+108h+var_E8], eax
0x1800013fc  jmp     short loc_180001413
0x1800013fe  xor     ebx, ebx
0x180001400  mov     [rsp+108h+var_E8], ebx
0x180001404  mov     edi, [rsp+108h+arg_8]
0x18000140b  mov     rsi, [rsp+108h+arg_0]
0x180001413  cmp     edi, 1
0x180001416  jnz     short loc_18000148F
0x180001418  test    ebx, ebx
0x18000141a  jnz     short loc_18000148F
0x18000141c  xor     r8d, r8d
0x18000141f  xor     edx, edx
0x180001421  mov     rcx, rsi; this
0x180001424  call    ?AddRef@CInetLogInformation@@UEAAKXZ; CInetLogInformation::AddRef(void)
0x180001429  jmp     short loc_18000143E
0x18000142b  mov     edi, [rsp+108h+arg_8]
0x180001432  mov     rsi, [rsp+108h+arg_0]
0x18000143a  mov     ebx, [rsp+108h+var_E8]
0x18000143e  xor     r8d, r8d
0x180001441  xor     edx, edx
0x180001443  mov     rcx, rsi
0x180001446  call    _CRT_INIT
0x18000144b  jmp     short loc_180001460
0x18000144d  mov     edi, [rsp+108h+arg_8]
0x180001454  mov     rsi, [rsp+108h+arg_0]
0x18000145c  mov     ebx, [rsp+108h+var_E8]
0x180001460  mov     rax, cs:_pRawDllMain
0x180001467  test    rax, rax
0x18000146a  jz      short loc_18000148F
0x18000146c  xor     r8d, r8d
0x18000146f  xor     edx, edx
0x180001471  mov     rcx, rsi
0x180001474  call    cs:__guard_dispatch_icall_fptr
0x18000147a  jmp     short loc_18000148F
0x18000147c  mov     edi, [rsp+108h+arg_8]
0x180001483  mov     rsi, [rsp+108h+arg_0]
0x18000148b  mov     ebx, [rsp+108h+var_E8]
0x18000148f  test    edi, edi
0x180001491  jz      short loc_180001498
0x180001493  cmp     edi, 3
0x180001496  jnz     short loc_180001504
0x180001498  mov     r8, [rsp+108h+arg_10]
0x1800014a0  mov     edx, edi
0x1800014a2  mov     rcx, rsi
0x1800014a5  call    _CRT_INIT
0x1800014aa  mov     ebx, eax
0x1800014ac  mov     [rsp+108h+var_E8], eax
0x1800014b0  jmp     short loc_1800014C7
0x1800014b2  xor     ebx, ebx
0x1800014b4  mov     [rsp+108h+var_E8], ebx
0x1800014b8  mov     edi, [rsp+108h+arg_8]
0x1800014bf  mov     rsi, [rsp+108h+arg_0]
0x1800014c7  mov     rax, cs:_pRawDllMain
0x1800014ce  test    rax, rax
0x1800014d1  jz      short loc_180001504
0x1800014d3  cmp     cs:dword_1800080A4, 0
0x1800014da  jz      short loc_180001504
0x1800014dc  mov     r8, [rsp+108h+arg_10]
0x1800014e4  mov     edx, edi
0x1800014e6  mov     rcx, rsi
0x1800014e9  call    cs:__guard_dispatch_icall_fptr
0x1800014ef  mov     ebx, eax
0x1800014f1  mov     [rsp+108h+var_E8], eax
0x1800014f5  jmp     short loc_180001504
0x1800014f7  xor     ebx, ebx
0x1800014f9  mov     [rsp+108h+var_E8], ebx
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  cmp     edi, 1
0x180001507  ja      short loc_180001513
0x180001509  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001513  mov     eax, ebx
0x180001515  add     rsp, 0F0h
0x18000151c  pop     rdi
0x18000151d  pop     rsi
0x18000151e  pop     rbx
0x18000151f  retn
0x180003880  push    rbp
0x180003882  sub     rsp, 20h
0x180003886  mov     rbp, rdx
0x180003889  mov     rax, [rcx]
0x18000388c  mov     edx, [rax]
0x18000388e  mov     [rbp+0A8h], rcx
0x180003895  mov     [rbp+28h], edx
0x180003898  mov     eax, [rbp+28h]
0x18000389b  cmp     eax, 0E06D7363h
0x1800038a0  jnz     short loc_1800038B6
0x1800038a2  mov     rdx, [rbp+0A8h]
0x1800038a9  mov     ecx, [rbp+28h]
0x1800038ac  call    _XcptFilter_0
0x1800038b1  mov     [rbp+30h], eax
0x1800038b4  jmp     short loc_1800038BD
0x1800038b6  mov     dword ptr [rbp+30h], 0
0x1800038bd  mov     eax, [rbp+30h]
0x1800038c0  add     rsp, 20h
0x1800038c4  pop     rbp
0x1800038c5  retn
0x1800038c7  push    rbp
0x1800038c9  sub     rsp, 20h
0x1800038cd  mov     rbp, rdx
0x1800038d0  mov     rax, [rcx]
0x1800038d3  mov     edx, [rax]
0x1800038d5  mov     [rbp+0B0h], rcx
0x1800038dc  mov     [rbp+38h], edx
0x1800038df  mov     eax, [rbp+38h]
0x1800038e2  cmp     eax, 0E06D7363h
0x1800038e7  jnz     short loc_1800038FD
0x1800038e9  mov     rdx, [rbp+0B0h]
0x1800038f0  mov     ecx, [rbp+38h]
0x1800038f3  call    _XcptFilter_0
0x1800038f8  mov     [rbp+40h], eax
0x1800038fb  jmp     short loc_180003904
0x1800038fd  mov     dword ptr [rbp+40h], 0
0x180003904  mov     eax, [rbp+40h]
0x180003907  add     rsp, 20h
0x18000390b  pop     rbp
0x18000390c  retn
0x18000390e  push    rbp
0x180003910  sub     rsp, 20h
0x180003914  mov     rbp, rdx
0x180003917  mov     rax, [rcx]
0x18000391a  mov     edx, [rax]
0x18000391c  mov     [rbp+0B8h], rcx
0x180003923  mov     [rbp+48h], edx
0x180003926  mov     eax, [rbp+48h]
0x180003929  cmp     eax, 0E06D7363h
0x18000392e  jnz     short loc_180003944
0x180003930  mov     rdx, [rbp+0B8h]
0x180003937  mov     ecx, [rbp+48h]
0x18000393a  call    _XcptFilter_0
0x18000393f  mov     [rbp+50h], eax
0x180003942  jmp     short loc_18000394B
0x180003944  mov     dword ptr [rbp+50h], 0
0x18000394b  mov     eax, [rbp+50h]
0x18000394e  add     rsp, 20h
0x180003952  pop     rbp
0x180003953  retn
0x180003955  push    rbp
0x180003957  sub     rsp, 20h
0x18000395b  mov     rbp, rdx
0x18000395e  mov     rax, [rcx]
0x180003961  mov     edx, [rax]
0x180003963  mov     [rbp+0C0h], rcx
0x18000396a  mov     [rbp+58h], edx
0x18000396d  mov     eax, [rbp+58h]
0x180003970  cmp     eax, 0E06D7363h
0x180003975  jnz     short loc_18000398B
0x180003977  mov     rdx, [rbp+0C0h]
0x18000397e  mov     ecx, [rbp+58h]
0x180003981  call    _XcptFilter_0
0x180003986  mov     [rbp+60h], eax
0x180003989  jmp     short loc_180003992
0x18000398b  mov     dword ptr [rbp+60h], 0
0x180003992  mov     eax, [rbp+60h]
0x180003995  add     rsp, 20h
0x180003999  pop     rbp
0x18000399a  retn
0x18000399c  push    rbp
0x18000399e  sub     rsp, 20h
0x1800039a2  mov     rbp, rdx
0x1800039a5  mov     rax, [rcx]
0x1800039a8  mov     edx, [rax]
0x1800039aa  mov     [rbp+0C8h], rcx
0x1800039b1  mov     [rbp+68h], edx
0x1800039b4  mov     eax, [rbp+68h]
0x1800039b7  cmp     eax, 0E06D7363h
0x1800039bc  jnz     short loc_1800039D2
0x1800039be  mov     rdx, [rbp+0C8h]
0x1800039c5  mov     ecx, [rbp+68h]
0x1800039c8  call    _XcptFilter_0
0x1800039cd  mov     [rbp+70h], eax
0x1800039d0  jmp     short loc_1800039D9
0x1800039d2  mov     dword ptr [rbp+70h], 0
0x1800039d9  mov     eax, [rbp+70h]
0x1800039dc  add     rsp, 20h
0x1800039e0  pop     rbp
0x1800039e1  retn
0x1800039e3  push    rbp
0x1800039e5  sub     rsp, 20h
0x1800039e9  mov     rbp, rdx
0x1800039ec  mov     rax, [rcx]
0x1800039ef  mov     edx, [rax]
0x1800039f1  mov     [rbp+0D0h], rcx
0x1800039f8  mov     [rbp+78h], edx
0x1800039fb  mov     eax, [rbp+78h]
0x1800039fe  cmp     eax, 0E06D7363h
0x180003a03  jnz     short loc_180003A1C
0x180003a05  mov     rdx, [rbp+0D0h]
0x180003a0c  mov     ecx, [rbp+78h]
0x180003a0f  call    _XcptFilter_0
0x180003a14  mov     [rbp+80h], eax
0x180003a1a  jmp     short loc_180003A26
0x180003a1c  mov     dword ptr [rbp+80h], 0
0x180003a26  mov     eax, [rbp+80h]
0x180003a2c  add     rsp, 20h
0x180003a30  pop     rbp
0x180003a31  retn
0x180003a33  push    rbp
0x180003a35  sub     rsp, 20h
0x180003a39  mov     rbp, rdx
0x180003a3c  mov     rax, [rcx]
0x180003a3f  mov     edx, [rax]
0x180003a41  mov     [rbp+0D8h], rcx
0x180003a48  mov     [rbp+88h], edx
0x180003a4e  mov     eax, [rbp+88h]
0x180003a54  cmp     eax, 0E06D7363h
0x180003a59  jnz     short loc_180003A75
0x180003a5b  mov     rdx, [rbp+0D8h]
0x180003a62  mov     ecx, [rbp+88h]
0x180003a68  call    _XcptFilter_0
0x180003a6d  mov     [rbp+90h], eax
0x180003a73  jmp     short loc_180003A7F
0x180003a75  mov     dword ptr [rbp+90h], 0
0x180003a7f  mov     eax, [rbp+90h]
0x180003a85  add     rsp, 20h
0x180003a89  pop     rbp
0x180003a8a  retn
0x180003a8c  push    rbp
0x180003a8e  sub     rsp, 20h
0x180003a92  mov     rbp, rdx
0x180003a95  mov     rax, [rcx]
0x180003a98  mov     edx, [rax]
0x180003a9a  mov     [rbp+0E0h], rcx
0x180003aa1  mov     [rbp+98h], edx
0x180003aa7  mov     eax, [rbp+98h]
0x180003aad  cmp     eax, 0E06D7363h
0x180003ab2  jnz     short loc_180003ACE
0x180003ab4  mov     rdx, [rbp+0E0h]
0x180003abb  mov     ecx, [rbp+98h]
0x180003ac1  call    _XcptFilter_0
0x180003ac6  mov     [rbp+0A0h], eax
0x180003acc  jmp     short loc_180003AD8
0x180003ace  mov     dword ptr [rbp+0A0h], 0
0x180003ad8  mov     eax, [rbp+0A0h]
0x180003ade  add     rsp, 20h
0x180003ae2  pop     rbp
0x180003ae3  retn
0x180003ae5  push    rbp
0x180003ae7  sub     rsp, 20h
0x180003aeb  mov     rbp, rdx
0x180003aee  cmp     dword ptr [rbp+118h], 1
0x180003af5  ja      short loc_180003B01
0x180003af7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

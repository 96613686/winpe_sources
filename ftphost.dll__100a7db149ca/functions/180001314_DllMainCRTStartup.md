# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000154a`
- `0x180001b60`
- `0x180004460`

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
  if ( (_DWORD)fdwReason || dword_18000A0A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000A0A4 = 1;
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
            if ( dword_18000A0A4 )
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
0x180001314  mov     [rsp+lpvReserved], r8
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
0x180001344  cmp     cs:dword_18000A0A0, edx
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
0x180001374  mov     cs:dword_18000A0A4, edx
0x18000137a  mov     r8, [rsp+108h+lpvReserved]
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
0x1800013ad  mov     r8, [rsp+108h+lpvReserved]
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
0x1800013e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013ec  mov     edx, edi; fdwReason
0x1800013ee  mov     rcx, rsi; hinstDLL
0x1800013f1  call    DllMain
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
0x18000141c  xor     r8d, r8d; lpvReserved
0x18000141f  xor     edx, edx; fdwReason
0x180001421  mov     rcx, rsi; hinstDLL
0x180001424  call    DllMain
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
0x180001498  mov     r8, [rsp+108h+lpvReserved]
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
0x1800014d3  cmp     cs:dword_18000A0A4, 0
0x1800014da  jz      short loc_180001504
0x1800014dc  mov     r8, [rsp+108h+lpvReserved]
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
0x1800044d0  push    rbp
0x1800044d2  sub     rsp, 20h
0x1800044d6  mov     rbp, rdx
0x1800044d9  mov     rax, [rcx]
0x1800044dc  mov     edx, [rax]
0x1800044de  mov     [rbp+0A8h], rcx
0x1800044e5  mov     [rbp+28h], edx
0x1800044e8  mov     eax, [rbp+28h]
0x1800044eb  cmp     eax, 0E06D7363h
0x1800044f0  jnz     short loc_180004506
0x1800044f2  mov     rdx, [rbp+0A8h]
0x1800044f9  mov     ecx, [rbp+28h]
0x1800044fc  call    _XcptFilter_0
0x180004501  mov     [rbp+30h], eax
0x180004504  jmp     short loc_18000450D
0x180004506  mov     dword ptr [rbp+30h], 0
0x18000450d  mov     eax, [rbp+30h]
0x180004510  add     rsp, 20h
0x180004514  pop     rbp
0x180004515  retn
0x180004517  push    rbp
0x180004519  sub     rsp, 20h
0x18000451d  mov     rbp, rdx
0x180004520  mov     rax, [rcx]
0x180004523  mov     edx, [rax]
0x180004525  mov     [rbp+0B0h], rcx
0x18000452c  mov     [rbp+38h], edx
0x18000452f  mov     eax, [rbp+38h]
0x180004532  cmp     eax, 0E06D7363h
0x180004537  jnz     short loc_18000454D
0x180004539  mov     rdx, [rbp+0B0h]
0x180004540  mov     ecx, [rbp+38h]
0x180004543  call    _XcptFilter_0
0x180004548  mov     [rbp+40h], eax
0x18000454b  jmp     short loc_180004554
0x18000454d  mov     dword ptr [rbp+40h], 0
0x180004554  mov     eax, [rbp+40h]
0x180004557  add     rsp, 20h
0x18000455b  pop     rbp
0x18000455c  retn
0x18000455e  push    rbp
0x180004560  sub     rsp, 20h
0x180004564  mov     rbp, rdx
0x180004567  mov     rax, [rcx]
0x18000456a  mov     edx, [rax]
0x18000456c  mov     [rbp+0B8h], rcx
0x180004573  mov     [rbp+48h], edx
0x180004576  mov     eax, [rbp+48h]
0x180004579  cmp     eax, 0E06D7363h
0x18000457e  jnz     short loc_180004594
0x180004580  mov     rdx, [rbp+0B8h]
0x180004587  mov     ecx, [rbp+48h]
0x18000458a  call    _XcptFilter_0
0x18000458f  mov     [rbp+50h], eax
0x180004592  jmp     short loc_18000459B
0x180004594  mov     dword ptr [rbp+50h], 0
0x18000459b  mov     eax, [rbp+50h]
0x18000459e  add     rsp, 20h
0x1800045a2  pop     rbp
0x1800045a3  retn
0x1800045a5  push    rbp
0x1800045a7  sub     rsp, 20h
0x1800045ab  mov     rbp, rdx
0x1800045ae  mov     rax, [rcx]
0x1800045b1  mov     edx, [rax]
0x1800045b3  mov     [rbp+0C0h], rcx
0x1800045ba  mov     [rbp+58h], edx
0x1800045bd  mov     eax, [rbp+58h]
0x1800045c0  cmp     eax, 0E06D7363h
0x1800045c5  jnz     short loc_1800045DB
0x1800045c7  mov     rdx, [rbp+0C0h]
0x1800045ce  mov     ecx, [rbp+58h]
0x1800045d1  call    _XcptFilter_0
0x1800045d6  mov     [rbp+60h], eax
0x1800045d9  jmp     short loc_1800045E2
0x1800045db  mov     dword ptr [rbp+60h], 0
0x1800045e2  mov     eax, [rbp+60h]
0x1800045e5  add     rsp, 20h
0x1800045e9  pop     rbp
0x1800045ea  retn
0x1800045ec  push    rbp
0x1800045ee  sub     rsp, 20h
0x1800045f2  mov     rbp, rdx
0x1800045f5  mov     rax, [rcx]
0x1800045f8  mov     edx, [rax]
0x1800045fa  mov     [rbp+0C8h], rcx
0x180004601  mov     [rbp+68h], edx
0x180004604  mov     eax, [rbp+68h]
0x180004607  cmp     eax, 0E06D7363h
0x18000460c  jnz     short loc_180004622
0x18000460e  mov     rdx, [rbp+0C8h]
0x180004615  mov     ecx, [rbp+68h]
0x180004618  call    _XcptFilter_0
0x18000461d  mov     [rbp+70h], eax
0x180004620  jmp     short loc_180004629
0x180004622  mov     dword ptr [rbp+70h], 0
0x180004629  mov     eax, [rbp+70h]
0x18000462c  add     rsp, 20h
0x180004630  pop     rbp
0x180004631  retn
0x180004633  push    rbp
0x180004635  sub     rsp, 20h
0x180004639  mov     rbp, rdx
0x18000463c  mov     rax, [rcx]
0x18000463f  mov     edx, [rax]
0x180004641  mov     [rbp+0D0h], rcx
0x180004648  mov     [rbp+78h], edx
0x18000464b  mov     eax, [rbp+78h]
0x18000464e  cmp     eax, 0E06D7363h
0x180004653  jnz     short loc_18000466C
0x180004655  mov     rdx, [rbp+0D0h]
0x18000465c  mov     ecx, [rbp+78h]
0x18000465f  call    _XcptFilter_0
0x180004664  mov     [rbp+80h], eax
0x18000466a  jmp     short loc_180004676
0x18000466c  mov     dword ptr [rbp+80h], 0
0x180004676  mov     eax, [rbp+80h]
0x18000467c  add     rsp, 20h
0x180004680  pop     rbp
0x180004681  retn
0x180004683  push    rbp
0x180004685  sub     rsp, 20h
0x180004689  mov     rbp, rdx
0x18000468c  mov     rax, [rcx]
0x18000468f  mov     edx, [rax]
0x180004691  mov     [rbp+0D8h], rcx
0x180004698  mov     [rbp+88h], edx
0x18000469e  mov     eax, [rbp+88h]
0x1800046a4  cmp     eax, 0E06D7363h
0x1800046a9  jnz     short loc_1800046C5
0x1800046ab  mov     rdx, [rbp+0D8h]
0x1800046b2  mov     ecx, [rbp+88h]
0x1800046b8  call    _XcptFilter_0
0x1800046bd  mov     [rbp+90h], eax
0x1800046c3  jmp     short loc_1800046CF
0x1800046c5  mov     dword ptr [rbp+90h], 0
0x1800046cf  mov     eax, [rbp+90h]
0x1800046d5  add     rsp, 20h
0x1800046d9  pop     rbp
0x1800046da  retn
0x1800046dc  push    rbp
0x1800046de  sub     rsp, 20h
0x1800046e2  mov     rbp, rdx
0x1800046e5  mov     rax, [rcx]
0x1800046e8  mov     edx, [rax]
0x1800046ea  mov     [rbp+0E0h], rcx
0x1800046f1  mov     [rbp+98h], edx
0x1800046f7  mov     eax, [rbp+98h]
0x1800046fd  cmp     eax, 0E06D7363h
0x180004702  jnz     short loc_18000471E
0x180004704  mov     rdx, [rbp+0E0h]
0x18000470b  mov     ecx, [rbp+98h]
0x180004711  call    _XcptFilter_0
0x180004716  mov     [rbp+0A0h], eax
0x18000471c  jmp     short loc_180004728
0x18000471e  mov     dword ptr [rbp+0A0h], 0
0x180004728  mov     eax, [rbp+0A0h]
0x18000472e  add     rsp, 20h
0x180004732  pop     rbp
0x180004733  retn
0x180004735  push    rbp
0x180004737  sub     rsp, 20h
0x18000473b  mov     rbp, rdx
0x18000473e  cmp     dword ptr [rbp+118h], 1
0x180004745  ja      short loc_180004751
0x180004747  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

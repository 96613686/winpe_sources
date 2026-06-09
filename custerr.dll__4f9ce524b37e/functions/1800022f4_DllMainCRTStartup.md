# __DllMainCRTStartup

- ea: `0x1800022f4`
- end: `0x180002500`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800022b0`

## callees

- `0x180002080`
- `0x1800022f4`
- `0x18000252a`
- `0x180002708`
- `0x1800078b0`

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
  if ( (_DWORD)fdwReason || dword_18000C0A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000C0A4 = 1;
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
            if ( dword_18000C0A4 )
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
0x1800022f4  mov     [rsp+lpvReserved], r8
0x1800022f9  mov     [rsp+arg_8], edx
0x1800022fd  mov     [rsp+arg_0], rcx
0x180002302  push    rbx
0x180002303  push    rsi
0x180002304  push    rdi
0x180002305  sub     rsp, 0F0h
0x18000230c  mov     edi, edx
0x18000230e  mov     rsi, rcx
0x180002311  mov     ebx, 1
0x180002316  cmp     edx, ebx
0x180002318  ja      short loc_180002320
0x18000231a  mov     cs:__native_dllmain_reason, edx
0x180002320  test    edx, edx
0x180002322  jnz     short loc_180002337
0x180002324  cmp     cs:dword_18000C0A0, edx
0x18000232a  jnz     short loc_180002337
0x18000232c  xor     ebx, ebx
0x18000232e  mov     [rsp+108h+var_E8], ebx
0x180002332  jmp     loc_1800024E4
0x180002337  lea     eax, [rdx-1]
0x18000233a  cmp     eax, 1
0x18000233d  ja      loc_1800023C4
0x180002343  mov     rax, cs:_pRawDllMain
0x18000234a  test    rax, rax
0x18000234d  jz      short loc_180002385
0x18000234f  cmp     edx, 1
0x180002352  jnz     short loc_18000235A
0x180002354  mov     cs:dword_18000C0A4, edx
0x18000235a  mov     r8, [rsp+108h+lpvReserved]
0x180002362  call    cs:__guard_dispatch_icall_fptr
0x180002368  mov     ebx, eax
0x18000236a  mov     [rsp+108h+var_E8], eax
0x18000236e  jmp     short loc_180002385
0x180002370  xor     ebx, ebx
0x180002372  mov     [rsp+108h+var_E8], ebx
0x180002376  mov     edi, [rsp+108h+arg_8]
0x18000237d  mov     rsi, [rsp+108h+arg_0]
0x180002385  test    ebx, ebx
0x180002387  jz      loc_1800024E4
0x18000238d  mov     r8, [rsp+108h+lpvReserved]
0x180002395  mov     edx, edi
0x180002397  mov     rcx, rsi
0x18000239a  call    _CRT_INIT
0x18000239f  mov     ebx, eax
0x1800023a1  mov     [rsp+108h+var_E8], eax
0x1800023a5  jmp     short loc_1800023BC
0x1800023a7  xor     ebx, ebx
0x1800023a9  mov     [rsp+108h+var_E8], ebx
0x1800023ad  mov     edi, [rsp+108h+arg_8]
0x1800023b4  mov     rsi, [rsp+108h+arg_0]
0x1800023bc  test    ebx, ebx
0x1800023be  jz      loc_1800024E4
0x1800023c4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800023cc  mov     edx, edi; fdwReason
0x1800023ce  mov     rcx, rsi; hinstDLL
0x1800023d1  call    DllMain
0x1800023d6  mov     ebx, eax
0x1800023d8  mov     [rsp+108h+var_E8], eax
0x1800023dc  jmp     short loc_1800023F3
0x1800023de  xor     ebx, ebx
0x1800023e0  mov     [rsp+108h+var_E8], ebx
0x1800023e4  mov     edi, [rsp+108h+arg_8]
0x1800023eb  mov     rsi, [rsp+108h+arg_0]
0x1800023f3  cmp     edi, 1
0x1800023f6  jnz     short loc_18000246F
0x1800023f8  test    ebx, ebx
0x1800023fa  jnz     short loc_18000246F
0x1800023fc  xor     r8d, r8d; lpvReserved
0x1800023ff  xor     edx, edx; fdwReason
0x180002401  mov     rcx, rsi; hinstDLL
0x180002404  call    DllMain
0x180002409  jmp     short loc_18000241E
0x18000240b  mov     edi, [rsp+108h+arg_8]
0x180002412  mov     rsi, [rsp+108h+arg_0]
0x18000241a  mov     ebx, [rsp+108h+var_E8]
0x18000241e  xor     r8d, r8d
0x180002421  xor     edx, edx
0x180002423  mov     rcx, rsi
0x180002426  call    _CRT_INIT
0x18000242b  jmp     short loc_180002440
0x18000242d  mov     edi, [rsp+108h+arg_8]
0x180002434  mov     rsi, [rsp+108h+arg_0]
0x18000243c  mov     ebx, [rsp+108h+var_E8]
0x180002440  mov     rax, cs:_pRawDllMain
0x180002447  test    rax, rax
0x18000244a  jz      short loc_18000246F
0x18000244c  xor     r8d, r8d
0x18000244f  xor     edx, edx
0x180002451  mov     rcx, rsi
0x180002454  call    cs:__guard_dispatch_icall_fptr
0x18000245a  jmp     short loc_18000246F
0x18000245c  mov     edi, [rsp+108h+arg_8]
0x180002463  mov     rsi, [rsp+108h+arg_0]
0x18000246b  mov     ebx, [rsp+108h+var_E8]
0x18000246f  test    edi, edi
0x180002471  jz      short loc_180002478
0x180002473  cmp     edi, 3
0x180002476  jnz     short loc_1800024E4
0x180002478  mov     r8, [rsp+108h+lpvReserved]
0x180002480  mov     edx, edi
0x180002482  mov     rcx, rsi
0x180002485  call    _CRT_INIT
0x18000248a  mov     ebx, eax
0x18000248c  mov     [rsp+108h+var_E8], eax
0x180002490  jmp     short loc_1800024A7
0x180002492  xor     ebx, ebx
0x180002494  mov     [rsp+108h+var_E8], ebx
0x180002498  mov     edi, [rsp+108h+arg_8]
0x18000249f  mov     rsi, [rsp+108h+arg_0]
0x1800024a7  mov     rax, cs:_pRawDllMain
0x1800024ae  test    rax, rax
0x1800024b1  jz      short loc_1800024E4
0x1800024b3  cmp     cs:dword_18000C0A4, 0
0x1800024ba  jz      short loc_1800024E4
0x1800024bc  mov     r8, [rsp+108h+lpvReserved]
0x1800024c4  mov     edx, edi
0x1800024c6  mov     rcx, rsi
0x1800024c9  call    cs:__guard_dispatch_icall_fptr
0x1800024cf  mov     ebx, eax
0x1800024d1  mov     [rsp+108h+var_E8], eax
0x1800024d5  jmp     short loc_1800024E4
0x1800024d7  xor     ebx, ebx
0x1800024d9  mov     [rsp+108h+var_E8], ebx
0x1800024dd  mov     edi, [rsp+108h+arg_8]
0x1800024e4  cmp     edi, 1
0x1800024e7  ja      short loc_1800024F3
0x1800024e9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800024f3  mov     eax, ebx
0x1800024f5  add     rsp, 0F0h
0x1800024fc  pop     rdi
0x1800024fd  pop     rsi
0x1800024fe  pop     rbx
0x1800024ff  retn
0x180007920  push    rbp
0x180007922  sub     rsp, 20h
0x180007926  mov     rbp, rdx
0x180007929  mov     rax, [rcx]
0x18000792c  mov     edx, [rax]
0x18000792e  mov     [rbp+0A8h], rcx
0x180007935  mov     [rbp+28h], edx
0x180007938  mov     eax, [rbp+28h]
0x18000793b  cmp     eax, 0E06D7363h
0x180007940  jnz     short loc_180007956
0x180007942  mov     rdx, [rbp+0A8h]
0x180007949  mov     ecx, [rbp+28h]
0x18000794c  call    _XcptFilter_0
0x180007951  mov     [rbp+30h], eax
0x180007954  jmp     short loc_18000795D
0x180007956  mov     dword ptr [rbp+30h], 0
0x18000795d  mov     eax, [rbp+30h]
0x180007960  add     rsp, 20h
0x180007964  pop     rbp
0x180007965  retn
0x180007967  push    rbp
0x180007969  sub     rsp, 20h
0x18000796d  mov     rbp, rdx
0x180007970  mov     rax, [rcx]
0x180007973  mov     edx, [rax]
0x180007975  mov     [rbp+0B0h], rcx
0x18000797c  mov     [rbp+38h], edx
0x18000797f  mov     eax, [rbp+38h]
0x180007982  cmp     eax, 0E06D7363h
0x180007987  jnz     short loc_18000799D
0x180007989  mov     rdx, [rbp+0B0h]
0x180007990  mov     ecx, [rbp+38h]
0x180007993  call    _XcptFilter_0
0x180007998  mov     [rbp+40h], eax
0x18000799b  jmp     short loc_1800079A4
0x18000799d  mov     dword ptr [rbp+40h], 0
0x1800079a4  mov     eax, [rbp+40h]
0x1800079a7  add     rsp, 20h
0x1800079ab  pop     rbp
0x1800079ac  retn
0x1800079ae  push    rbp
0x1800079b0  sub     rsp, 20h
0x1800079b4  mov     rbp, rdx
0x1800079b7  mov     rax, [rcx]
0x1800079ba  mov     edx, [rax]
0x1800079bc  mov     [rbp+0B8h], rcx
0x1800079c3  mov     [rbp+48h], edx
0x1800079c6  mov     eax, [rbp+48h]
0x1800079c9  cmp     eax, 0E06D7363h
0x1800079ce  jnz     short loc_1800079E4
0x1800079d0  mov     rdx, [rbp+0B8h]
0x1800079d7  mov     ecx, [rbp+48h]
0x1800079da  call    _XcptFilter_0
0x1800079df  mov     [rbp+50h], eax
0x1800079e2  jmp     short loc_1800079EB
0x1800079e4  mov     dword ptr [rbp+50h], 0
0x1800079eb  mov     eax, [rbp+50h]
0x1800079ee  add     rsp, 20h
0x1800079f2  pop     rbp
0x1800079f3  retn
0x1800079f5  push    rbp
0x1800079f7  sub     rsp, 20h
0x1800079fb  mov     rbp, rdx
0x1800079fe  mov     rax, [rcx]
0x180007a01  mov     edx, [rax]
0x180007a03  mov     [rbp+0C0h], rcx
0x180007a0a  mov     [rbp+58h], edx
0x180007a0d  mov     eax, [rbp+58h]
0x180007a10  cmp     eax, 0E06D7363h
0x180007a15  jnz     short loc_180007A2B
0x180007a17  mov     rdx, [rbp+0C0h]
0x180007a1e  mov     ecx, [rbp+58h]
0x180007a21  call    _XcptFilter_0
0x180007a26  mov     [rbp+60h], eax
0x180007a29  jmp     short loc_180007A32
0x180007a2b  mov     dword ptr [rbp+60h], 0
0x180007a32  mov     eax, [rbp+60h]
0x180007a35  add     rsp, 20h
0x180007a39  pop     rbp
0x180007a3a  retn
0x180007a3c  push    rbp
0x180007a3e  sub     rsp, 20h
0x180007a42  mov     rbp, rdx
0x180007a45  mov     rax, [rcx]
0x180007a48  mov     edx, [rax]
0x180007a4a  mov     [rbp+0C8h], rcx
0x180007a51  mov     [rbp+68h], edx
0x180007a54  mov     eax, [rbp+68h]
0x180007a57  cmp     eax, 0E06D7363h
0x180007a5c  jnz     short loc_180007A72
0x180007a5e  mov     rdx, [rbp+0C8h]
0x180007a65  mov     ecx, [rbp+68h]
0x180007a68  call    _XcptFilter_0
0x180007a6d  mov     [rbp+70h], eax
0x180007a70  jmp     short loc_180007A79
0x180007a72  mov     dword ptr [rbp+70h], 0
0x180007a79  mov     eax, [rbp+70h]
0x180007a7c  add     rsp, 20h
0x180007a80  pop     rbp
0x180007a81  retn
0x180007a83  push    rbp
0x180007a85  sub     rsp, 20h
0x180007a89  mov     rbp, rdx
0x180007a8c  mov     rax, [rcx]
0x180007a8f  mov     edx, [rax]
0x180007a91  mov     [rbp+0D0h], rcx
0x180007a98  mov     [rbp+78h], edx
0x180007a9b  mov     eax, [rbp+78h]
0x180007a9e  cmp     eax, 0E06D7363h
0x180007aa3  jnz     short loc_180007ABC
0x180007aa5  mov     rdx, [rbp+0D0h]
0x180007aac  mov     ecx, [rbp+78h]
0x180007aaf  call    _XcptFilter_0
0x180007ab4  mov     [rbp+80h], eax
0x180007aba  jmp     short loc_180007AC6
0x180007abc  mov     dword ptr [rbp+80h], 0
0x180007ac6  mov     eax, [rbp+80h]
0x180007acc  add     rsp, 20h
0x180007ad0  pop     rbp
0x180007ad1  retn
0x180007ad3  push    rbp
0x180007ad5  sub     rsp, 20h
0x180007ad9  mov     rbp, rdx
0x180007adc  mov     rax, [rcx]
0x180007adf  mov     edx, [rax]
0x180007ae1  mov     [rbp+0D8h], rcx
0x180007ae8  mov     [rbp+88h], edx
0x180007aee  mov     eax, [rbp+88h]
0x180007af4  cmp     eax, 0E06D7363h
0x180007af9  jnz     short loc_180007B15
0x180007afb  mov     rdx, [rbp+0D8h]
0x180007b02  mov     ecx, [rbp+88h]
0x180007b08  call    _XcptFilter_0
0x180007b0d  mov     [rbp+90h], eax
0x180007b13  jmp     short loc_180007B1F
0x180007b15  mov     dword ptr [rbp+90h], 0
0x180007b1f  mov     eax, [rbp+90h]
0x180007b25  add     rsp, 20h
0x180007b29  pop     rbp
0x180007b2a  retn
0x180007b2c  push    rbp
0x180007b2e  sub     rsp, 20h
0x180007b32  mov     rbp, rdx
0x180007b35  mov     rax, [rcx]
0x180007b38  mov     edx, [rax]
0x180007b3a  mov     [rbp+0E0h], rcx
0x180007b41  mov     [rbp+98h], edx
0x180007b47  mov     eax, [rbp+98h]
0x180007b4d  cmp     eax, 0E06D7363h
0x180007b52  jnz     short loc_180007B6E
0x180007b54  mov     rdx, [rbp+0E0h]
0x180007b5b  mov     ecx, [rbp+98h]
0x180007b61  call    _XcptFilter_0
0x180007b66  mov     [rbp+0A0h], eax
0x180007b6c  jmp     short loc_180007B78
0x180007b6e  mov     dword ptr [rbp+0A0h], 0
0x180007b78  mov     eax, [rbp+0A0h]
0x180007b7e  add     rsp, 20h
0x180007b82  pop     rbp
0x180007b83  retn
0x180007b85  push    rbp
0x180007b87  sub     rsp, 20h
0x180007b8b  mov     rbp, rdx
0x180007b8e  cmp     dword ptr [rbp+118h], 1
0x180007b95  ja      short loc_180007BA1
0x180007b97  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

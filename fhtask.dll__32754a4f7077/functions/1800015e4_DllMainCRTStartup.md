# __DllMainCRTStartup

- ea: `0x1800015e4`
- end: `0x1800017f0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800015a0`

## callees

- `0x180001370`
- `0x1800015e4`
- `0x180001d30`
- `0x180005bb4`
- `0x180009a70`

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
  if ( (_DWORD)fdwReason || dword_1800103C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800103C4 = 1;
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
            if ( dword_1800103C4 )
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
0x1800015e4  mov     [rsp+lpvReserved], r8
0x1800015e9  mov     [rsp+arg_8], edx
0x1800015ed  mov     [rsp+arg_0], rcx
0x1800015f2  push    rbx
0x1800015f3  push    rsi
0x1800015f4  push    rdi
0x1800015f5  sub     rsp, 0F0h
0x1800015fc  mov     edi, edx
0x1800015fe  mov     rsi, rcx
0x180001601  mov     ebx, 1
0x180001606  cmp     edx, ebx
0x180001608  ja      short loc_180001610
0x18000160a  mov     cs:__native_dllmain_reason, edx
0x180001610  test    edx, edx
0x180001612  jnz     short loc_180001627
0x180001614  cmp     cs:dword_1800103C0, edx
0x18000161a  jnz     short loc_180001627
0x18000161c  xor     ebx, ebx
0x18000161e  mov     [rsp+108h+var_E8], ebx
0x180001622  jmp     loc_1800017D4
0x180001627  lea     eax, [rdx-1]
0x18000162a  cmp     eax, 1
0x18000162d  ja      loc_1800016B4
0x180001633  mov     rax, cs:_pRawDllMain
0x18000163a  test    rax, rax
0x18000163d  jz      short loc_180001675
0x18000163f  cmp     edx, 1
0x180001642  jnz     short loc_18000164A
0x180001644  mov     cs:dword_1800103C4, edx
0x18000164a  mov     r8, [rsp+108h+lpvReserved]
0x180001652  call    cs:__guard_dispatch_icall_fptr
0x180001658  mov     ebx, eax
0x18000165a  mov     [rsp+108h+var_E8], eax
0x18000165e  jmp     short loc_180001675
0x180001660  xor     ebx, ebx
0x180001662  mov     [rsp+108h+var_E8], ebx
0x180001666  mov     edi, [rsp+108h+arg_8]
0x18000166d  mov     rsi, [rsp+108h+arg_0]
0x180001675  test    ebx, ebx
0x180001677  jz      loc_1800017D4
0x18000167d  mov     r8, [rsp+108h+lpvReserved]
0x180001685  mov     edx, edi
0x180001687  mov     rcx, rsi
0x18000168a  call    _CRT_INIT
0x18000168f  mov     ebx, eax
0x180001691  mov     [rsp+108h+var_E8], eax
0x180001695  jmp     short loc_1800016AC
0x180001697  xor     ebx, ebx
0x180001699  mov     [rsp+108h+var_E8], ebx
0x18000169d  mov     edi, [rsp+108h+arg_8]
0x1800016a4  mov     rsi, [rsp+108h+arg_0]
0x1800016ac  test    ebx, ebx
0x1800016ae  jz      loc_1800017D4
0x1800016b4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800016bc  mov     edx, edi; fdwReason
0x1800016be  mov     rcx, rsi; hinstDLL
0x1800016c1  call    DllMain
0x1800016c6  mov     ebx, eax
0x1800016c8  mov     [rsp+108h+var_E8], eax
0x1800016cc  jmp     short loc_1800016E3
0x1800016ce  xor     ebx, ebx
0x1800016d0  mov     [rsp+108h+var_E8], ebx
0x1800016d4  mov     edi, [rsp+108h+arg_8]
0x1800016db  mov     rsi, [rsp+108h+arg_0]
0x1800016e3  cmp     edi, 1
0x1800016e6  jnz     short loc_18000175F
0x1800016e8  test    ebx, ebx
0x1800016ea  jnz     short loc_18000175F
0x1800016ec  xor     r8d, r8d; lpvReserved
0x1800016ef  xor     edx, edx; fdwReason
0x1800016f1  mov     rcx, rsi; hinstDLL
0x1800016f4  call    DllMain
0x1800016f9  jmp     short loc_18000170E
0x1800016fb  mov     edi, [rsp+108h+arg_8]
0x180001702  mov     rsi, [rsp+108h+arg_0]
0x18000170a  mov     ebx, [rsp+108h+var_E8]
0x18000170e  xor     r8d, r8d
0x180001711  xor     edx, edx
0x180001713  mov     rcx, rsi
0x180001716  call    _CRT_INIT
0x18000171b  jmp     short loc_180001730
0x18000171d  mov     edi, [rsp+108h+arg_8]
0x180001724  mov     rsi, [rsp+108h+arg_0]
0x18000172c  mov     ebx, [rsp+108h+var_E8]
0x180001730  mov     rax, cs:_pRawDllMain
0x180001737  test    rax, rax
0x18000173a  jz      short loc_18000175F
0x18000173c  xor     r8d, r8d
0x18000173f  xor     edx, edx
0x180001741  mov     rcx, rsi
0x180001744  call    cs:__guard_dispatch_icall_fptr
0x18000174a  jmp     short loc_18000175F
0x18000174c  mov     edi, [rsp+108h+arg_8]
0x180001753  mov     rsi, [rsp+108h+arg_0]
0x18000175b  mov     ebx, [rsp+108h+var_E8]
0x18000175f  test    edi, edi
0x180001761  jz      short loc_180001768
0x180001763  cmp     edi, 3
0x180001766  jnz     short loc_1800017D4
0x180001768  mov     r8, [rsp+108h+lpvReserved]
0x180001770  mov     edx, edi
0x180001772  mov     rcx, rsi
0x180001775  call    _CRT_INIT
0x18000177a  mov     ebx, eax
0x18000177c  mov     [rsp+108h+var_E8], eax
0x180001780  jmp     short loc_180001797
0x180001782  xor     ebx, ebx
0x180001784  mov     [rsp+108h+var_E8], ebx
0x180001788  mov     edi, [rsp+108h+arg_8]
0x18000178f  mov     rsi, [rsp+108h+arg_0]
0x180001797  mov     rax, cs:_pRawDllMain
0x18000179e  test    rax, rax
0x1800017a1  jz      short loc_1800017D4
0x1800017a3  cmp     cs:dword_1800103C4, 0
0x1800017aa  jz      short loc_1800017D4
0x1800017ac  mov     r8, [rsp+108h+lpvReserved]
0x1800017b4  mov     edx, edi
0x1800017b6  mov     rcx, rsi
0x1800017b9  call    cs:__guard_dispatch_icall_fptr
0x1800017bf  mov     ebx, eax
0x1800017c1  mov     [rsp+108h+var_E8], eax
0x1800017c5  jmp     short loc_1800017D4
0x1800017c7  xor     ebx, ebx
0x1800017c9  mov     [rsp+108h+var_E8], ebx
0x1800017cd  mov     edi, [rsp+108h+arg_8]
0x1800017d4  cmp     edi, 1
0x1800017d7  ja      short loc_1800017E3
0x1800017d9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800017e3  mov     eax, ebx
0x1800017e5  add     rsp, 0F0h
0x1800017ec  pop     rdi
0x1800017ed  pop     rsi
0x1800017ee  pop     rbx
0x1800017ef  retn
0x180009b13  push    rbp
0x180009b15  sub     rsp, 20h
0x180009b19  mov     rbp, rdx
0x180009b1c  mov     rax, [rcx]
0x180009b1f  mov     edx, [rax]
0x180009b21  mov     [rbp+0A8h], rcx
0x180009b28  mov     [rbp+28h], edx
0x180009b2b  mov     eax, [rbp+28h]
0x180009b2e  cmp     eax, 0E06D7363h
0x180009b33  jnz     short loc_180009B49
0x180009b35  mov     rdx, [rbp+0A8h]
0x180009b3c  mov     ecx, [rbp+28h]
0x180009b3f  call    _XcptFilter_0
0x180009b44  mov     [rbp+30h], eax
0x180009b47  jmp     short loc_180009B50
0x180009b49  mov     dword ptr [rbp+30h], 0
0x180009b50  mov     eax, [rbp+30h]
0x180009b53  add     rsp, 20h
0x180009b57  pop     rbp
0x180009b58  retn
0x180009b5a  push    rbp
0x180009b5c  sub     rsp, 20h
0x180009b60  mov     rbp, rdx
0x180009b63  mov     rax, [rcx]
0x180009b66  mov     edx, [rax]
0x180009b68  mov     [rbp+0B0h], rcx
0x180009b6f  mov     [rbp+38h], edx
0x180009b72  mov     eax, [rbp+38h]
0x180009b75  cmp     eax, 0E06D7363h
0x180009b7a  jnz     short loc_180009B90
0x180009b7c  mov     rdx, [rbp+0B0h]
0x180009b83  mov     ecx, [rbp+38h]
0x180009b86  call    _XcptFilter_0
0x180009b8b  mov     [rbp+40h], eax
0x180009b8e  jmp     short loc_180009B97
0x180009b90  mov     dword ptr [rbp+40h], 0
0x180009b97  mov     eax, [rbp+40h]
0x180009b9a  add     rsp, 20h
0x180009b9e  pop     rbp
0x180009b9f  retn
0x180009ba1  push    rbp
0x180009ba3  sub     rsp, 20h
0x180009ba7  mov     rbp, rdx
0x180009baa  mov     rax, [rcx]
0x180009bad  mov     edx, [rax]
0x180009baf  mov     [rbp+0B8h], rcx
0x180009bb6  mov     [rbp+48h], edx
0x180009bb9  mov     eax, [rbp+48h]
0x180009bbc  cmp     eax, 0E06D7363h
0x180009bc1  jnz     short loc_180009BD7
0x180009bc3  mov     rdx, [rbp+0B8h]
0x180009bca  mov     ecx, [rbp+48h]
0x180009bcd  call    _XcptFilter_0
0x180009bd2  mov     [rbp+50h], eax
0x180009bd5  jmp     short loc_180009BDE
0x180009bd7  mov     dword ptr [rbp+50h], 0
0x180009bde  mov     eax, [rbp+50h]
0x180009be1  add     rsp, 20h
0x180009be5  pop     rbp
0x180009be6  retn
0x180009be8  push    rbp
0x180009bea  sub     rsp, 20h
0x180009bee  mov     rbp, rdx
0x180009bf1  mov     rax, [rcx]
0x180009bf4  mov     edx, [rax]
0x180009bf6  mov     [rbp+0C0h], rcx
0x180009bfd  mov     [rbp+58h], edx
0x180009c00  mov     eax, [rbp+58h]
0x180009c03  cmp     eax, 0E06D7363h
0x180009c08  jnz     short loc_180009C1E
0x180009c0a  mov     rdx, [rbp+0C0h]
0x180009c11  mov     ecx, [rbp+58h]
0x180009c14  call    _XcptFilter_0
0x180009c19  mov     [rbp+60h], eax
0x180009c1c  jmp     short loc_180009C25
0x180009c1e  mov     dword ptr [rbp+60h], 0
0x180009c25  mov     eax, [rbp+60h]
0x180009c28  add     rsp, 20h
0x180009c2c  pop     rbp
0x180009c2d  retn
0x180009c2f  push    rbp
0x180009c31  sub     rsp, 20h
0x180009c35  mov     rbp, rdx
0x180009c38  mov     rax, [rcx]
0x180009c3b  mov     edx, [rax]
0x180009c3d  mov     [rbp+0C8h], rcx
0x180009c44  mov     [rbp+68h], edx
0x180009c47  mov     eax, [rbp+68h]
0x180009c4a  cmp     eax, 0E06D7363h
0x180009c4f  jnz     short loc_180009C65
0x180009c51  mov     rdx, [rbp+0C8h]
0x180009c58  mov     ecx, [rbp+68h]
0x180009c5b  call    _XcptFilter_0
0x180009c60  mov     [rbp+70h], eax
0x180009c63  jmp     short loc_180009C6C
0x180009c65  mov     dword ptr [rbp+70h], 0
0x180009c6c  mov     eax, [rbp+70h]
0x180009c6f  add     rsp, 20h
0x180009c73  pop     rbp
0x180009c74  retn
0x180009c76  push    rbp
0x180009c78  sub     rsp, 20h
0x180009c7c  mov     rbp, rdx
0x180009c7f  mov     rax, [rcx]
0x180009c82  mov     edx, [rax]
0x180009c84  mov     [rbp+0D0h], rcx
0x180009c8b  mov     [rbp+78h], edx
0x180009c8e  mov     eax, [rbp+78h]
0x180009c91  cmp     eax, 0E06D7363h
0x180009c96  jnz     short loc_180009CAF
0x180009c98  mov     rdx, [rbp+0D0h]
0x180009c9f  mov     ecx, [rbp+78h]
0x180009ca2  call    _XcptFilter_0
0x180009ca7  mov     [rbp+80h], eax
0x180009cad  jmp     short loc_180009CB9
0x180009caf  mov     dword ptr [rbp+80h], 0
0x180009cb9  mov     eax, [rbp+80h]
0x180009cbf  add     rsp, 20h
0x180009cc3  pop     rbp
0x180009cc4  retn
0x180009cc6  push    rbp
0x180009cc8  sub     rsp, 20h
0x180009ccc  mov     rbp, rdx
0x180009ccf  mov     rax, [rcx]
0x180009cd2  mov     edx, [rax]
0x180009cd4  mov     [rbp+0D8h], rcx
0x180009cdb  mov     [rbp+88h], edx
0x180009ce1  mov     eax, [rbp+88h]
0x180009ce7  cmp     eax, 0E06D7363h
0x180009cec  jnz     short loc_180009D08
0x180009cee  mov     rdx, [rbp+0D8h]
0x180009cf5  mov     ecx, [rbp+88h]
0x180009cfb  call    _XcptFilter_0
0x180009d00  mov     [rbp+90h], eax
0x180009d06  jmp     short loc_180009D12
0x180009d08  mov     dword ptr [rbp+90h], 0
0x180009d12  mov     eax, [rbp+90h]
0x180009d18  add     rsp, 20h
0x180009d1c  pop     rbp
0x180009d1d  retn
0x180009d1f  push    rbp
0x180009d21  sub     rsp, 20h
0x180009d25  mov     rbp, rdx
0x180009d28  mov     rax, [rcx]
0x180009d2b  mov     edx, [rax]
0x180009d2d  mov     [rbp+0E0h], rcx
0x180009d34  mov     [rbp+98h], edx
0x180009d3a  mov     eax, [rbp+98h]
0x180009d40  cmp     eax, 0E06D7363h
0x180009d45  jnz     short loc_180009D61
0x180009d47  mov     rdx, [rbp+0E0h]
0x180009d4e  mov     ecx, [rbp+98h]
0x180009d54  call    _XcptFilter_0
0x180009d59  mov     [rbp+0A0h], eax
0x180009d5f  jmp     short loc_180009D6B
0x180009d61  mov     dword ptr [rbp+0A0h], 0
0x180009d6b  mov     eax, [rbp+0A0h]
0x180009d71  add     rsp, 20h
0x180009d75  pop     rbp
0x180009d76  retn
0x180009d78  push    rbp
0x180009d7a  sub     rsp, 20h
0x180009d7e  mov     rbp, rdx
0x180009d81  cmp     dword ptr [rbp+118h], 1
0x180009d88  ja      short loc_180009D94
0x180009d8a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

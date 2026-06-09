# __DllMainCRTStartup

- ea: `0x1800016b4`
- end: `0x1800018c0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001670`

## callees

- `0x180001440`
- `0x1800016b4`
- `0x180001ab6`
- `0x180003450`
- `0x180009970`

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
  if ( (_DWORD)fdwReason || dword_1800124C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800124C4 = 1;
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
            if ( dword_1800124C4 )
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
0x1800016b4  mov     [rsp+lpvReserved], r8
0x1800016b9  mov     [rsp+arg_8], edx
0x1800016bd  mov     [rsp+arg_0], rcx
0x1800016c2  push    rbx
0x1800016c3  push    rsi
0x1800016c4  push    rdi
0x1800016c5  sub     rsp, 0F0h
0x1800016cc  mov     edi, edx
0x1800016ce  mov     rsi, rcx
0x1800016d1  mov     ebx, 1
0x1800016d6  cmp     edx, ebx
0x1800016d8  ja      short loc_1800016E0
0x1800016da  mov     cs:__native_dllmain_reason, edx
0x1800016e0  test    edx, edx
0x1800016e2  jnz     short loc_1800016F7
0x1800016e4  cmp     cs:dword_1800124C0, edx
0x1800016ea  jnz     short loc_1800016F7
0x1800016ec  xor     ebx, ebx
0x1800016ee  mov     [rsp+108h+var_E8], ebx
0x1800016f2  jmp     loc_1800018A4
0x1800016f7  lea     eax, [rdx-1]
0x1800016fa  cmp     eax, 1
0x1800016fd  ja      loc_180001784
0x180001703  mov     rax, cs:_pRawDllMain
0x18000170a  test    rax, rax
0x18000170d  jz      short loc_180001745
0x18000170f  cmp     edx, 1
0x180001712  jnz     short loc_18000171A
0x180001714  mov     cs:dword_1800124C4, edx
0x18000171a  mov     r8, [rsp+108h+lpvReserved]
0x180001722  call    cs:__guard_dispatch_icall_fptr
0x180001728  mov     ebx, eax
0x18000172a  mov     [rsp+108h+var_E8], eax
0x18000172e  jmp     short loc_180001745
0x180001730  xor     ebx, ebx
0x180001732  mov     [rsp+108h+var_E8], ebx
0x180001736  mov     edi, [rsp+108h+arg_8]
0x18000173d  mov     rsi, [rsp+108h+arg_0]
0x180001745  test    ebx, ebx
0x180001747  jz      loc_1800018A4
0x18000174d  mov     r8, [rsp+108h+lpvReserved]
0x180001755  mov     edx, edi
0x180001757  mov     rcx, rsi
0x18000175a  call    _CRT_INIT
0x18000175f  mov     ebx, eax
0x180001761  mov     [rsp+108h+var_E8], eax
0x180001765  jmp     short loc_18000177C
0x180001767  xor     ebx, ebx
0x180001769  mov     [rsp+108h+var_E8], ebx
0x18000176d  mov     edi, [rsp+108h+arg_8]
0x180001774  mov     rsi, [rsp+108h+arg_0]
0x18000177c  test    ebx, ebx
0x18000177e  jz      loc_1800018A4
0x180001784  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000178c  mov     edx, edi; fdwReason
0x18000178e  mov     rcx, rsi; hinstDLL
0x180001791  call    DllMain
0x180001796  mov     ebx, eax
0x180001798  mov     [rsp+108h+var_E8], eax
0x18000179c  jmp     short loc_1800017B3
0x18000179e  xor     ebx, ebx
0x1800017a0  mov     [rsp+108h+var_E8], ebx
0x1800017a4  mov     edi, [rsp+108h+arg_8]
0x1800017ab  mov     rsi, [rsp+108h+arg_0]
0x1800017b3  cmp     edi, 1
0x1800017b6  jnz     short loc_18000182F
0x1800017b8  test    ebx, ebx
0x1800017ba  jnz     short loc_18000182F
0x1800017bc  xor     r8d, r8d; lpvReserved
0x1800017bf  xor     edx, edx; fdwReason
0x1800017c1  mov     rcx, rsi; hinstDLL
0x1800017c4  call    DllMain
0x1800017c9  jmp     short loc_1800017DE
0x1800017cb  mov     edi, [rsp+108h+arg_8]
0x1800017d2  mov     rsi, [rsp+108h+arg_0]
0x1800017da  mov     ebx, [rsp+108h+var_E8]
0x1800017de  xor     r8d, r8d
0x1800017e1  xor     edx, edx
0x1800017e3  mov     rcx, rsi
0x1800017e6  call    _CRT_INIT
0x1800017eb  jmp     short loc_180001800
0x1800017ed  mov     edi, [rsp+108h+arg_8]
0x1800017f4  mov     rsi, [rsp+108h+arg_0]
0x1800017fc  mov     ebx, [rsp+108h+var_E8]
0x180001800  mov     rax, cs:_pRawDllMain
0x180001807  test    rax, rax
0x18000180a  jz      short loc_18000182F
0x18000180c  xor     r8d, r8d
0x18000180f  xor     edx, edx
0x180001811  mov     rcx, rsi
0x180001814  call    cs:__guard_dispatch_icall_fptr
0x18000181a  jmp     short loc_18000182F
0x18000181c  mov     edi, [rsp+108h+arg_8]
0x180001823  mov     rsi, [rsp+108h+arg_0]
0x18000182b  mov     ebx, [rsp+108h+var_E8]
0x18000182f  test    edi, edi
0x180001831  jz      short loc_180001838
0x180001833  cmp     edi, 3
0x180001836  jnz     short loc_1800018A4
0x180001838  mov     r8, [rsp+108h+lpvReserved]
0x180001840  mov     edx, edi
0x180001842  mov     rcx, rsi
0x180001845  call    _CRT_INIT
0x18000184a  mov     ebx, eax
0x18000184c  mov     [rsp+108h+var_E8], eax
0x180001850  jmp     short loc_180001867
0x180001852  xor     ebx, ebx
0x180001854  mov     [rsp+108h+var_E8], ebx
0x180001858  mov     edi, [rsp+108h+arg_8]
0x18000185f  mov     rsi, [rsp+108h+arg_0]
0x180001867  mov     rax, cs:_pRawDllMain
0x18000186e  test    rax, rax
0x180001871  jz      short loc_1800018A4
0x180001873  cmp     cs:dword_1800124C4, 0
0x18000187a  jz      short loc_1800018A4
0x18000187c  mov     r8, [rsp+108h+lpvReserved]
0x180001884  mov     edx, edi
0x180001886  mov     rcx, rsi
0x180001889  call    cs:__guard_dispatch_icall_fptr
0x18000188f  mov     ebx, eax
0x180001891  mov     [rsp+108h+var_E8], eax
0x180001895  jmp     short loc_1800018A4
0x180001897  xor     ebx, ebx
0x180001899  mov     [rsp+108h+var_E8], ebx
0x18000189d  mov     edi, [rsp+108h+arg_8]
0x1800018a4  cmp     edi, 1
0x1800018a7  ja      short loc_1800018B3
0x1800018a9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800018b3  mov     eax, ebx
0x1800018b5  add     rsp, 0F0h
0x1800018bc  pop     rdi
0x1800018bd  pop     rsi
0x1800018be  pop     rbx
0x1800018bf  retn
0x180009a43  push    rbp
0x180009a45  sub     rsp, 20h
0x180009a49  mov     rbp, rdx
0x180009a4c  mov     rax, [rcx]
0x180009a4f  mov     edx, [rax]
0x180009a51  mov     [rbp+0A8h], rcx
0x180009a58  mov     [rbp+28h], edx
0x180009a5b  mov     eax, [rbp+28h]
0x180009a5e  cmp     eax, 0E06D7363h
0x180009a63  jnz     short loc_180009A79
0x180009a65  mov     rdx, [rbp+0A8h]
0x180009a6c  mov     ecx, [rbp+28h]
0x180009a6f  call    _XcptFilter_0
0x180009a74  mov     [rbp+30h], eax
0x180009a77  jmp     short loc_180009A80
0x180009a79  mov     dword ptr [rbp+30h], 0
0x180009a80  mov     eax, [rbp+30h]
0x180009a83  add     rsp, 20h
0x180009a87  pop     rbp
0x180009a88  retn
0x180009a8a  push    rbp
0x180009a8c  sub     rsp, 20h
0x180009a90  mov     rbp, rdx
0x180009a93  mov     rax, [rcx]
0x180009a96  mov     edx, [rax]
0x180009a98  mov     [rbp+0B0h], rcx
0x180009a9f  mov     [rbp+38h], edx
0x180009aa2  mov     eax, [rbp+38h]
0x180009aa5  cmp     eax, 0E06D7363h
0x180009aaa  jnz     short loc_180009AC0
0x180009aac  mov     rdx, [rbp+0B0h]
0x180009ab3  mov     ecx, [rbp+38h]
0x180009ab6  call    _XcptFilter_0
0x180009abb  mov     [rbp+40h], eax
0x180009abe  jmp     short loc_180009AC7
0x180009ac0  mov     dword ptr [rbp+40h], 0
0x180009ac7  mov     eax, [rbp+40h]
0x180009aca  add     rsp, 20h
0x180009ace  pop     rbp
0x180009acf  retn
0x180009ad1  push    rbp
0x180009ad3  sub     rsp, 20h
0x180009ad7  mov     rbp, rdx
0x180009ada  mov     rax, [rcx]
0x180009add  mov     edx, [rax]
0x180009adf  mov     [rbp+0B8h], rcx
0x180009ae6  mov     [rbp+48h], edx
0x180009ae9  mov     eax, [rbp+48h]
0x180009aec  cmp     eax, 0E06D7363h
0x180009af1  jnz     short loc_180009B07
0x180009af3  mov     rdx, [rbp+0B8h]
0x180009afa  mov     ecx, [rbp+48h]
0x180009afd  call    _XcptFilter_0
0x180009b02  mov     [rbp+50h], eax
0x180009b05  jmp     short loc_180009B0E
0x180009b07  mov     dword ptr [rbp+50h], 0
0x180009b0e  mov     eax, [rbp+50h]
0x180009b11  add     rsp, 20h
0x180009b15  pop     rbp
0x180009b16  retn
0x180009b18  push    rbp
0x180009b1a  sub     rsp, 20h
0x180009b1e  mov     rbp, rdx
0x180009b21  mov     rax, [rcx]
0x180009b24  mov     edx, [rax]
0x180009b26  mov     [rbp+0C0h], rcx
0x180009b2d  mov     [rbp+58h], edx
0x180009b30  mov     eax, [rbp+58h]
0x180009b33  cmp     eax, 0E06D7363h
0x180009b38  jnz     short loc_180009B4E
0x180009b3a  mov     rdx, [rbp+0C0h]
0x180009b41  mov     ecx, [rbp+58h]
0x180009b44  call    _XcptFilter_0
0x180009b49  mov     [rbp+60h], eax
0x180009b4c  jmp     short loc_180009B55
0x180009b4e  mov     dword ptr [rbp+60h], 0
0x180009b55  mov     eax, [rbp+60h]
0x180009b58  add     rsp, 20h
0x180009b5c  pop     rbp
0x180009b5d  retn
0x180009b5f  push    rbp
0x180009b61  sub     rsp, 20h
0x180009b65  mov     rbp, rdx
0x180009b68  mov     rax, [rcx]
0x180009b6b  mov     edx, [rax]
0x180009b6d  mov     [rbp+0C8h], rcx
0x180009b74  mov     [rbp+68h], edx
0x180009b77  mov     eax, [rbp+68h]
0x180009b7a  cmp     eax, 0E06D7363h
0x180009b7f  jnz     short loc_180009B95
0x180009b81  mov     rdx, [rbp+0C8h]
0x180009b88  mov     ecx, [rbp+68h]
0x180009b8b  call    _XcptFilter_0
0x180009b90  mov     [rbp+70h], eax
0x180009b93  jmp     short loc_180009B9C
0x180009b95  mov     dword ptr [rbp+70h], 0
0x180009b9c  mov     eax, [rbp+70h]
0x180009b9f  add     rsp, 20h
0x180009ba3  pop     rbp
0x180009ba4  retn
0x180009ba6  push    rbp
0x180009ba8  sub     rsp, 20h
0x180009bac  mov     rbp, rdx
0x180009baf  mov     rax, [rcx]
0x180009bb2  mov     edx, [rax]
0x180009bb4  mov     [rbp+0D0h], rcx
0x180009bbb  mov     [rbp+78h], edx
0x180009bbe  mov     eax, [rbp+78h]
0x180009bc1  cmp     eax, 0E06D7363h
0x180009bc6  jnz     short loc_180009BDF
0x180009bc8  mov     rdx, [rbp+0D0h]
0x180009bcf  mov     ecx, [rbp+78h]
0x180009bd2  call    _XcptFilter_0
0x180009bd7  mov     [rbp+80h], eax
0x180009bdd  jmp     short loc_180009BE9
0x180009bdf  mov     dword ptr [rbp+80h], 0
0x180009be9  mov     eax, [rbp+80h]
0x180009bef  add     rsp, 20h
0x180009bf3  pop     rbp
0x180009bf4  retn
0x180009bf6  push    rbp
0x180009bf8  sub     rsp, 20h
0x180009bfc  mov     rbp, rdx
0x180009bff  mov     rax, [rcx]
0x180009c02  mov     edx, [rax]
0x180009c04  mov     [rbp+0D8h], rcx
0x180009c0b  mov     [rbp+88h], edx
0x180009c11  mov     eax, [rbp+88h]
0x180009c17  cmp     eax, 0E06D7363h
0x180009c1c  jnz     short loc_180009C38
0x180009c1e  mov     rdx, [rbp+0D8h]
0x180009c25  mov     ecx, [rbp+88h]
0x180009c2b  call    _XcptFilter_0
0x180009c30  mov     [rbp+90h], eax
0x180009c36  jmp     short loc_180009C42
0x180009c38  mov     dword ptr [rbp+90h], 0
0x180009c42  mov     eax, [rbp+90h]
0x180009c48  add     rsp, 20h
0x180009c4c  pop     rbp
0x180009c4d  retn
0x180009c4f  push    rbp
0x180009c51  sub     rsp, 20h
0x180009c55  mov     rbp, rdx
0x180009c58  mov     rax, [rcx]
0x180009c5b  mov     edx, [rax]
0x180009c5d  mov     [rbp+0E0h], rcx
0x180009c64  mov     [rbp+98h], edx
0x180009c6a  mov     eax, [rbp+98h]
0x180009c70  cmp     eax, 0E06D7363h
0x180009c75  jnz     short loc_180009C91
0x180009c77  mov     rdx, [rbp+0E0h]
0x180009c7e  mov     ecx, [rbp+98h]
0x180009c84  call    _XcptFilter_0
0x180009c89  mov     [rbp+0A0h], eax
0x180009c8f  jmp     short loc_180009C9B
0x180009c91  mov     dword ptr [rbp+0A0h], 0
0x180009c9b  mov     eax, [rbp+0A0h]
0x180009ca1  add     rsp, 20h
0x180009ca5  pop     rbp
0x180009ca6  retn
0x180009ca8  push    rbp
0x180009caa  sub     rsp, 20h
0x180009cae  mov     rbp, rdx
0x180009cb1  cmp     dword ptr [rbp+118h], 1
0x180009cb8  ja      short loc_180009CC4
0x180009cba  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

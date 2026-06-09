# __DllMainCRTStartup

- ea: `0x180001874`
- end: `0x180001a80`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001830`

## callees

- `0x180001600`
- `0x180001874`
- `0x1800020d5`
- `0x18001084c`
- `0x18001cab0`

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
  if ( (_DWORD)fdwReason || dword_180026360 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180026364 = 1;
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
            if ( dword_180026364 )
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
0x180001874  mov     [rsp+lpvReserved], r8
0x180001879  mov     [rsp+arg_8], edx
0x18000187d  mov     [rsp+arg_0], rcx
0x180001882  push    rbx
0x180001883  push    rsi
0x180001884  push    rdi
0x180001885  sub     rsp, 0F0h
0x18000188c  mov     edi, edx
0x18000188e  mov     rsi, rcx
0x180001891  mov     ebx, 1
0x180001896  cmp     edx, ebx
0x180001898  ja      short loc_1800018A0
0x18000189a  mov     cs:__native_dllmain_reason, edx
0x1800018a0  test    edx, edx
0x1800018a2  jnz     short loc_1800018B7
0x1800018a4  cmp     cs:dword_180026360, edx
0x1800018aa  jnz     short loc_1800018B7
0x1800018ac  xor     ebx, ebx
0x1800018ae  mov     [rsp+108h+var_E8], ebx
0x1800018b2  jmp     loc_180001A64
0x1800018b7  lea     eax, [rdx-1]
0x1800018ba  cmp     eax, 1
0x1800018bd  ja      loc_180001944
0x1800018c3  mov     rax, cs:_pRawDllMain
0x1800018ca  test    rax, rax
0x1800018cd  jz      short loc_180001905
0x1800018cf  cmp     edx, 1
0x1800018d2  jnz     short loc_1800018DA
0x1800018d4  mov     cs:dword_180026364, edx
0x1800018da  mov     r8, [rsp+108h+lpvReserved]
0x1800018e2  call    cs:__guard_dispatch_icall_fptr
0x1800018e8  mov     ebx, eax
0x1800018ea  mov     [rsp+108h+var_E8], eax
0x1800018ee  jmp     short loc_180001905
0x1800018f0  xor     ebx, ebx
0x1800018f2  mov     [rsp+108h+var_E8], ebx
0x1800018f6  mov     edi, [rsp+108h+arg_8]
0x1800018fd  mov     rsi, [rsp+108h+arg_0]
0x180001905  test    ebx, ebx
0x180001907  jz      loc_180001A64
0x18000190d  mov     r8, [rsp+108h+lpvReserved]
0x180001915  mov     edx, edi
0x180001917  mov     rcx, rsi
0x18000191a  call    _CRT_INIT
0x18000191f  mov     ebx, eax
0x180001921  mov     [rsp+108h+var_E8], eax
0x180001925  jmp     short loc_18000193C
0x180001927  xor     ebx, ebx
0x180001929  mov     [rsp+108h+var_E8], ebx
0x18000192d  mov     edi, [rsp+108h+arg_8]
0x180001934  mov     rsi, [rsp+108h+arg_0]
0x18000193c  test    ebx, ebx
0x18000193e  jz      loc_180001A64
0x180001944  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000194c  mov     edx, edi; fdwReason
0x18000194e  mov     rcx, rsi; hinstDLL
0x180001951  call    DllMain
0x180001956  mov     ebx, eax
0x180001958  mov     [rsp+108h+var_E8], eax
0x18000195c  jmp     short loc_180001973
0x18000195e  xor     ebx, ebx
0x180001960  mov     [rsp+108h+var_E8], ebx
0x180001964  mov     edi, [rsp+108h+arg_8]
0x18000196b  mov     rsi, [rsp+108h+arg_0]
0x180001973  cmp     edi, 1
0x180001976  jnz     short loc_1800019EF
0x180001978  test    ebx, ebx
0x18000197a  jnz     short loc_1800019EF
0x18000197c  xor     r8d, r8d; lpvReserved
0x18000197f  xor     edx, edx; fdwReason
0x180001981  mov     rcx, rsi; hinstDLL
0x180001984  call    DllMain
0x180001989  jmp     short loc_18000199E
0x18000198b  mov     edi, [rsp+108h+arg_8]
0x180001992  mov     rsi, [rsp+108h+arg_0]
0x18000199a  mov     ebx, [rsp+108h+var_E8]
0x18000199e  xor     r8d, r8d
0x1800019a1  xor     edx, edx
0x1800019a3  mov     rcx, rsi
0x1800019a6  call    _CRT_INIT
0x1800019ab  jmp     short loc_1800019C0
0x1800019ad  mov     edi, [rsp+108h+arg_8]
0x1800019b4  mov     rsi, [rsp+108h+arg_0]
0x1800019bc  mov     ebx, [rsp+108h+var_E8]
0x1800019c0  mov     rax, cs:_pRawDllMain
0x1800019c7  test    rax, rax
0x1800019ca  jz      short loc_1800019EF
0x1800019cc  xor     r8d, r8d
0x1800019cf  xor     edx, edx
0x1800019d1  mov     rcx, rsi
0x1800019d4  call    cs:__guard_dispatch_icall_fptr
0x1800019da  jmp     short loc_1800019EF
0x1800019dc  mov     edi, [rsp+108h+arg_8]
0x1800019e3  mov     rsi, [rsp+108h+arg_0]
0x1800019eb  mov     ebx, [rsp+108h+var_E8]
0x1800019ef  test    edi, edi
0x1800019f1  jz      short loc_1800019F8
0x1800019f3  cmp     edi, 3
0x1800019f6  jnz     short loc_180001A64
0x1800019f8  mov     r8, [rsp+108h+lpvReserved]
0x180001a00  mov     edx, edi
0x180001a02  mov     rcx, rsi
0x180001a05  call    _CRT_INIT
0x180001a0a  mov     ebx, eax
0x180001a0c  mov     [rsp+108h+var_E8], eax
0x180001a10  jmp     short loc_180001A27
0x180001a12  xor     ebx, ebx
0x180001a14  mov     [rsp+108h+var_E8], ebx
0x180001a18  mov     edi, [rsp+108h+arg_8]
0x180001a1f  mov     rsi, [rsp+108h+arg_0]
0x180001a27  mov     rax, cs:_pRawDllMain
0x180001a2e  test    rax, rax
0x180001a31  jz      short loc_180001A64
0x180001a33  cmp     cs:dword_180026364, 0
0x180001a3a  jz      short loc_180001A64
0x180001a3c  mov     r8, [rsp+108h+lpvReserved]
0x180001a44  mov     edx, edi
0x180001a46  mov     rcx, rsi
0x180001a49  call    cs:__guard_dispatch_icall_fptr
0x180001a4f  mov     ebx, eax
0x180001a51  mov     [rsp+108h+var_E8], eax
0x180001a55  jmp     short loc_180001A64
0x180001a57  xor     ebx, ebx
0x180001a59  mov     [rsp+108h+var_E8], ebx
0x180001a5d  mov     edi, [rsp+108h+arg_8]
0x180001a64  cmp     edi, 1
0x180001a67  ja      short loc_180001A73
0x180001a69  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001a73  mov     eax, ebx
0x180001a75  add     rsp, 0F0h
0x180001a7c  pop     rdi
0x180001a7d  pop     rsi
0x180001a7e  pop     rbx
0x180001a7f  retn
0x18001cb80  push    rbp
0x18001cb82  sub     rsp, 20h
0x18001cb86  mov     rbp, rdx
0x18001cb89  mov     rax, [rcx]
0x18001cb8c  mov     edx, [rax]
0x18001cb8e  mov     [rbp+0A8h], rcx
0x18001cb95  mov     [rbp+28h], edx
0x18001cb98  mov     eax, [rbp+28h]
0x18001cb9b  cmp     eax, 0E06D7363h
0x18001cba0  jnz     short loc_18001CBB6
0x18001cba2  mov     rdx, [rbp+0A8h]
0x18001cba9  mov     ecx, [rbp+28h]
0x18001cbac  call    _XcptFilter_0
0x18001cbb1  mov     [rbp+30h], eax
0x18001cbb4  jmp     short loc_18001CBBD
0x18001cbb6  mov     dword ptr [rbp+30h], 0
0x18001cbbd  mov     eax, [rbp+30h]
0x18001cbc0  add     rsp, 20h
0x18001cbc4  pop     rbp
0x18001cbc5  retn
0x18001cbc7  push    rbp
0x18001cbc9  sub     rsp, 20h
0x18001cbcd  mov     rbp, rdx
0x18001cbd0  mov     rax, [rcx]
0x18001cbd3  mov     edx, [rax]
0x18001cbd5  mov     [rbp+0B0h], rcx
0x18001cbdc  mov     [rbp+38h], edx
0x18001cbdf  mov     eax, [rbp+38h]
0x18001cbe2  cmp     eax, 0E06D7363h
0x18001cbe7  jnz     short loc_18001CBFD
0x18001cbe9  mov     rdx, [rbp+0B0h]
0x18001cbf0  mov     ecx, [rbp+38h]
0x18001cbf3  call    _XcptFilter_0
0x18001cbf8  mov     [rbp+40h], eax
0x18001cbfb  jmp     short loc_18001CC04
0x18001cbfd  mov     dword ptr [rbp+40h], 0
0x18001cc04  mov     eax, [rbp+40h]
0x18001cc07  add     rsp, 20h
0x18001cc0b  pop     rbp
0x18001cc0c  retn
0x18001cc0e  push    rbp
0x18001cc10  sub     rsp, 20h
0x18001cc14  mov     rbp, rdx
0x18001cc17  mov     rax, [rcx]
0x18001cc1a  mov     edx, [rax]
0x18001cc1c  mov     [rbp+0B8h], rcx
0x18001cc23  mov     [rbp+48h], edx
0x18001cc26  mov     eax, [rbp+48h]
0x18001cc29  cmp     eax, 0E06D7363h
0x18001cc2e  jnz     short loc_18001CC44
0x18001cc30  mov     rdx, [rbp+0B8h]
0x18001cc37  mov     ecx, [rbp+48h]
0x18001cc3a  call    _XcptFilter_0
0x18001cc3f  mov     [rbp+50h], eax
0x18001cc42  jmp     short loc_18001CC4B
0x18001cc44  mov     dword ptr [rbp+50h], 0
0x18001cc4b  mov     eax, [rbp+50h]
0x18001cc4e  add     rsp, 20h
0x18001cc52  pop     rbp
0x18001cc53  retn
0x18001cc55  push    rbp
0x18001cc57  sub     rsp, 20h
0x18001cc5b  mov     rbp, rdx
0x18001cc5e  mov     rax, [rcx]
0x18001cc61  mov     edx, [rax]
0x18001cc63  mov     [rbp+0C0h], rcx
0x18001cc6a  mov     [rbp+58h], edx
0x18001cc6d  mov     eax, [rbp+58h]
0x18001cc70  cmp     eax, 0E06D7363h
0x18001cc75  jnz     short loc_18001CC8B
0x18001cc77  mov     rdx, [rbp+0C0h]
0x18001cc7e  mov     ecx, [rbp+58h]
0x18001cc81  call    _XcptFilter_0
0x18001cc86  mov     [rbp+60h], eax
0x18001cc89  jmp     short loc_18001CC92
0x18001cc8b  mov     dword ptr [rbp+60h], 0
0x18001cc92  mov     eax, [rbp+60h]
0x18001cc95  add     rsp, 20h
0x18001cc99  pop     rbp
0x18001cc9a  retn
0x18001cc9c  push    rbp
0x18001cc9e  sub     rsp, 20h
0x18001cca2  mov     rbp, rdx
0x18001cca5  mov     rax, [rcx]
0x18001cca8  mov     edx, [rax]
0x18001ccaa  mov     [rbp+0C8h], rcx
0x18001ccb1  mov     [rbp+68h], edx
0x18001ccb4  mov     eax, [rbp+68h]
0x18001ccb7  cmp     eax, 0E06D7363h
0x18001ccbc  jnz     short loc_18001CCD2
0x18001ccbe  mov     rdx, [rbp+0C8h]
0x18001ccc5  mov     ecx, [rbp+68h]
0x18001ccc8  call    _XcptFilter_0
0x18001cccd  mov     [rbp+70h], eax
0x18001ccd0  jmp     short loc_18001CCD9
0x18001ccd2  mov     dword ptr [rbp+70h], 0
0x18001ccd9  mov     eax, [rbp+70h]
0x18001ccdc  add     rsp, 20h
0x18001cce0  pop     rbp
0x18001cce1  retn
0x18001cce3  push    rbp
0x18001cce5  sub     rsp, 20h
0x18001cce9  mov     rbp, rdx
0x18001ccec  mov     rax, [rcx]
0x18001ccef  mov     edx, [rax]
0x18001ccf1  mov     [rbp+0D0h], rcx
0x18001ccf8  mov     [rbp+78h], edx
0x18001ccfb  mov     eax, [rbp+78h]
0x18001ccfe  cmp     eax, 0E06D7363h
0x18001cd03  jnz     short loc_18001CD1C
0x18001cd05  mov     rdx, [rbp+0D0h]
0x18001cd0c  mov     ecx, [rbp+78h]
0x18001cd0f  call    _XcptFilter_0
0x18001cd14  mov     [rbp+80h], eax
0x18001cd1a  jmp     short loc_18001CD26
0x18001cd1c  mov     dword ptr [rbp+80h], 0
0x18001cd26  mov     eax, [rbp+80h]
0x18001cd2c  add     rsp, 20h
0x18001cd30  pop     rbp
0x18001cd31  retn
0x18001cd33  push    rbp
0x18001cd35  sub     rsp, 20h
0x18001cd39  mov     rbp, rdx
0x18001cd3c  mov     rax, [rcx]
0x18001cd3f  mov     edx, [rax]
0x18001cd41  mov     [rbp+0D8h], rcx
0x18001cd48  mov     [rbp+88h], edx
0x18001cd4e  mov     eax, [rbp+88h]
0x18001cd54  cmp     eax, 0E06D7363h
0x18001cd59  jnz     short loc_18001CD75
0x18001cd5b  mov     rdx, [rbp+0D8h]
0x18001cd62  mov     ecx, [rbp+88h]
0x18001cd68  call    _XcptFilter_0
0x18001cd6d  mov     [rbp+90h], eax
0x18001cd73  jmp     short loc_18001CD7F
0x18001cd75  mov     dword ptr [rbp+90h], 0
0x18001cd7f  mov     eax, [rbp+90h]
0x18001cd85  add     rsp, 20h
0x18001cd89  pop     rbp
0x18001cd8a  retn
0x18001cd8c  push    rbp
0x18001cd8e  sub     rsp, 20h
0x18001cd92  mov     rbp, rdx
0x18001cd95  mov     rax, [rcx]
0x18001cd98  mov     edx, [rax]
0x18001cd9a  mov     [rbp+0E0h], rcx
0x18001cda1  mov     [rbp+98h], edx
0x18001cda7  mov     eax, [rbp+98h]
0x18001cdad  cmp     eax, 0E06D7363h
0x18001cdb2  jnz     short loc_18001CDCE
0x18001cdb4  mov     rdx, [rbp+0E0h]
0x18001cdbb  mov     ecx, [rbp+98h]
0x18001cdc1  call    _XcptFilter_0
0x18001cdc6  mov     [rbp+0A0h], eax
0x18001cdcc  jmp     short loc_18001CDD8
0x18001cdce  mov     dword ptr [rbp+0A0h], 0
0x18001cdd8  mov     eax, [rbp+0A0h]
0x18001cdde  add     rsp, 20h
0x18001cde2  pop     rbp
0x18001cde3  retn
0x18001cde5  push    rbp
0x18001cde7  sub     rsp, 20h
0x18001cdeb  mov     rbp, rdx
0x18001cdee  cmp     dword ptr [rbp+118h], 1
0x18001cdf5  ja      short loc_18001CE01
0x18001cdf7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

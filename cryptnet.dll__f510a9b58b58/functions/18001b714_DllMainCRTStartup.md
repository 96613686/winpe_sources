# __DllMainCRTStartup

- ea: `0x18001b714`
- end: `0x18001b920`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001b6d0`

## callees

- `0x18001b4a0`
- `0x18001b714`
- `0x18001bc44`
- `0x18001c594`
- `0x1800265f0`

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
  if ( (_DWORD)fdwReason || dword_1800321C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800321C4 = 1;
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
            if ( dword_1800321C4 )
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
0x18001b714  mov     [rsp+lpvReserved], r8
0x18001b719  mov     [rsp+arg_8], edx
0x18001b71d  mov     [rsp+arg_0], rcx
0x18001b722  push    rbx
0x18001b723  push    rsi
0x18001b724  push    rdi
0x18001b725  sub     rsp, 0F0h
0x18001b72c  mov     edi, edx
0x18001b72e  mov     rsi, rcx
0x18001b731  mov     ebx, 1
0x18001b736  cmp     edx, ebx
0x18001b738  ja      short loc_18001B740
0x18001b73a  mov     cs:__native_dllmain_reason, edx
0x18001b740  test    edx, edx
0x18001b742  jnz     short loc_18001B757
0x18001b744  cmp     cs:dword_1800321C0, edx
0x18001b74a  jnz     short loc_18001B757
0x18001b74c  xor     ebx, ebx
0x18001b74e  mov     [rsp+108h+var_E8], ebx
0x18001b752  jmp     loc_18001B904
0x18001b757  lea     eax, [rdx-1]
0x18001b75a  cmp     eax, 1
0x18001b75d  ja      loc_18001B7E4
0x18001b763  mov     rax, cs:_pRawDllMain
0x18001b76a  test    rax, rax
0x18001b76d  jz      short loc_18001B7A5
0x18001b76f  cmp     edx, 1
0x18001b772  jnz     short loc_18001B77A
0x18001b774  mov     cs:dword_1800321C4, edx
0x18001b77a  mov     r8, [rsp+108h+lpvReserved]
0x18001b782  call    cs:__guard_dispatch_icall_fptr
0x18001b788  mov     ebx, eax
0x18001b78a  mov     [rsp+108h+var_E8], eax
0x18001b78e  jmp     short loc_18001B7A5
0x18001b790  xor     ebx, ebx
0x18001b792  mov     [rsp+108h+var_E8], ebx
0x18001b796  mov     edi, [rsp+108h+arg_8]
0x18001b79d  mov     rsi, [rsp+108h+arg_0]
0x18001b7a5  test    ebx, ebx
0x18001b7a7  jz      loc_18001B904
0x18001b7ad  mov     r8, [rsp+108h+lpvReserved]
0x18001b7b5  mov     edx, edi
0x18001b7b7  mov     rcx, rsi
0x18001b7ba  call    _CRT_INIT
0x18001b7bf  mov     ebx, eax
0x18001b7c1  mov     [rsp+108h+var_E8], eax
0x18001b7c5  jmp     short loc_18001B7DC
0x18001b7c7  xor     ebx, ebx
0x18001b7c9  mov     [rsp+108h+var_E8], ebx
0x18001b7cd  mov     edi, [rsp+108h+arg_8]
0x18001b7d4  mov     rsi, [rsp+108h+arg_0]
0x18001b7dc  test    ebx, ebx
0x18001b7de  jz      loc_18001B904
0x18001b7e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18001b7ec  mov     edx, edi; fdwReason
0x18001b7ee  mov     rcx, rsi; hinstDLL
0x18001b7f1  call    DllMain
0x18001b7f6  mov     ebx, eax
0x18001b7f8  mov     [rsp+108h+var_E8], eax
0x18001b7fc  jmp     short loc_18001B813
0x18001b7fe  xor     ebx, ebx
0x18001b800  mov     [rsp+108h+var_E8], ebx
0x18001b804  mov     edi, [rsp+108h+arg_8]
0x18001b80b  mov     rsi, [rsp+108h+arg_0]
0x18001b813  cmp     edi, 1
0x18001b816  jnz     short loc_18001B88F
0x18001b818  test    ebx, ebx
0x18001b81a  jnz     short loc_18001B88F
0x18001b81c  xor     r8d, r8d; lpvReserved
0x18001b81f  xor     edx, edx; fdwReason
0x18001b821  mov     rcx, rsi; hinstDLL
0x18001b824  call    DllMain
0x18001b829  jmp     short loc_18001B83E
0x18001b82b  mov     edi, [rsp+108h+arg_8]
0x18001b832  mov     rsi, [rsp+108h+arg_0]
0x18001b83a  mov     ebx, [rsp+108h+var_E8]
0x18001b83e  xor     r8d, r8d
0x18001b841  xor     edx, edx
0x18001b843  mov     rcx, rsi
0x18001b846  call    _CRT_INIT
0x18001b84b  jmp     short loc_18001B860
0x18001b84d  mov     edi, [rsp+108h+arg_8]
0x18001b854  mov     rsi, [rsp+108h+arg_0]
0x18001b85c  mov     ebx, [rsp+108h+var_E8]
0x18001b860  mov     rax, cs:_pRawDllMain
0x18001b867  test    rax, rax
0x18001b86a  jz      short loc_18001B88F
0x18001b86c  xor     r8d, r8d
0x18001b86f  xor     edx, edx
0x18001b871  mov     rcx, rsi
0x18001b874  call    cs:__guard_dispatch_icall_fptr
0x18001b87a  jmp     short loc_18001B88F
0x18001b87c  mov     edi, [rsp+108h+arg_8]
0x18001b883  mov     rsi, [rsp+108h+arg_0]
0x18001b88b  mov     ebx, [rsp+108h+var_E8]
0x18001b88f  test    edi, edi
0x18001b891  jz      short loc_18001B898
0x18001b893  cmp     edi, 3
0x18001b896  jnz     short loc_18001B904
0x18001b898  mov     r8, [rsp+108h+lpvReserved]
0x18001b8a0  mov     edx, edi
0x18001b8a2  mov     rcx, rsi
0x18001b8a5  call    _CRT_INIT
0x18001b8aa  mov     ebx, eax
0x18001b8ac  mov     [rsp+108h+var_E8], eax
0x18001b8b0  jmp     short loc_18001B8C7
0x18001b8b2  xor     ebx, ebx
0x18001b8b4  mov     [rsp+108h+var_E8], ebx
0x18001b8b8  mov     edi, [rsp+108h+arg_8]
0x18001b8bf  mov     rsi, [rsp+108h+arg_0]
0x18001b8c7  mov     rax, cs:_pRawDllMain
0x18001b8ce  test    rax, rax
0x18001b8d1  jz      short loc_18001B904
0x18001b8d3  cmp     cs:dword_1800321C4, 0
0x18001b8da  jz      short loc_18001B904
0x18001b8dc  mov     r8, [rsp+108h+lpvReserved]
0x18001b8e4  mov     edx, edi
0x18001b8e6  mov     rcx, rsi
0x18001b8e9  call    cs:__guard_dispatch_icall_fptr
0x18001b8ef  mov     ebx, eax
0x18001b8f1  mov     [rsp+108h+var_E8], eax
0x18001b8f5  jmp     short loc_18001B904
0x18001b8f7  xor     ebx, ebx
0x18001b8f9  mov     [rsp+108h+var_E8], ebx
0x18001b8fd  mov     edi, [rsp+108h+arg_8]
0x18001b904  cmp     edi, 1
0x18001b907  ja      short loc_18001B913
0x18001b909  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18001b913  mov     eax, ebx
0x18001b915  add     rsp, 0F0h
0x18001b91c  pop     rdi
0x18001b91d  pop     rsi
0x18001b91e  pop     rbx
0x18001b91f  retn
0x1800266c0  push    rbp
0x1800266c2  sub     rsp, 20h
0x1800266c6  mov     rbp, rdx
0x1800266c9  mov     rax, [rcx]
0x1800266cc  mov     edx, [rax]
0x1800266ce  mov     [rbp+0A8h], rcx
0x1800266d5  mov     [rbp+28h], edx
0x1800266d8  mov     eax, [rbp+28h]
0x1800266db  cmp     eax, 0E06D7363h
0x1800266e0  jnz     short loc_1800266F6
0x1800266e2  mov     rdx, [rbp+0A8h]
0x1800266e9  mov     ecx, [rbp+28h]
0x1800266ec  call    _XcptFilter_0
0x1800266f1  mov     [rbp+30h], eax
0x1800266f4  jmp     short loc_1800266FD
0x1800266f6  mov     dword ptr [rbp+30h], 0
0x1800266fd  mov     eax, [rbp+30h]
0x180026700  add     rsp, 20h
0x180026704  pop     rbp
0x180026705  retn
0x180026707  push    rbp
0x180026709  sub     rsp, 20h
0x18002670d  mov     rbp, rdx
0x180026710  mov     rax, [rcx]
0x180026713  mov     edx, [rax]
0x180026715  mov     [rbp+0B0h], rcx
0x18002671c  mov     [rbp+38h], edx
0x18002671f  mov     eax, [rbp+38h]
0x180026722  cmp     eax, 0E06D7363h
0x180026727  jnz     short loc_18002673D
0x180026729  mov     rdx, [rbp+0B0h]
0x180026730  mov     ecx, [rbp+38h]
0x180026733  call    _XcptFilter_0
0x180026738  mov     [rbp+40h], eax
0x18002673b  jmp     short loc_180026744
0x18002673d  mov     dword ptr [rbp+40h], 0
0x180026744  mov     eax, [rbp+40h]
0x180026747  add     rsp, 20h
0x18002674b  pop     rbp
0x18002674c  retn
0x18002674e  push    rbp
0x180026750  sub     rsp, 20h
0x180026754  mov     rbp, rdx
0x180026757  mov     rax, [rcx]
0x18002675a  mov     edx, [rax]
0x18002675c  mov     [rbp+0B8h], rcx
0x180026763  mov     [rbp+48h], edx
0x180026766  mov     eax, [rbp+48h]
0x180026769  cmp     eax, 0E06D7363h
0x18002676e  jnz     short loc_180026784
0x180026770  mov     rdx, [rbp+0B8h]
0x180026777  mov     ecx, [rbp+48h]
0x18002677a  call    _XcptFilter_0
0x18002677f  mov     [rbp+50h], eax
0x180026782  jmp     short loc_18002678B
0x180026784  mov     dword ptr [rbp+50h], 0
0x18002678b  mov     eax, [rbp+50h]
0x18002678e  add     rsp, 20h
0x180026792  pop     rbp
0x180026793  retn
0x180026795  push    rbp
0x180026797  sub     rsp, 20h
0x18002679b  mov     rbp, rdx
0x18002679e  mov     rax, [rcx]
0x1800267a1  mov     edx, [rax]
0x1800267a3  mov     [rbp+0C0h], rcx
0x1800267aa  mov     [rbp+58h], edx
0x1800267ad  mov     eax, [rbp+58h]
0x1800267b0  cmp     eax, 0E06D7363h
0x1800267b5  jnz     short loc_1800267CB
0x1800267b7  mov     rdx, [rbp+0C0h]
0x1800267be  mov     ecx, [rbp+58h]
0x1800267c1  call    _XcptFilter_0
0x1800267c6  mov     [rbp+60h], eax
0x1800267c9  jmp     short loc_1800267D2
0x1800267cb  mov     dword ptr [rbp+60h], 0
0x1800267d2  mov     eax, [rbp+60h]
0x1800267d5  add     rsp, 20h
0x1800267d9  pop     rbp
0x1800267da  retn
0x1800267dc  push    rbp
0x1800267de  sub     rsp, 20h
0x1800267e2  mov     rbp, rdx
0x1800267e5  mov     rax, [rcx]
0x1800267e8  mov     edx, [rax]
0x1800267ea  mov     [rbp+0C8h], rcx
0x1800267f1  mov     [rbp+68h], edx
0x1800267f4  mov     eax, [rbp+68h]
0x1800267f7  cmp     eax, 0E06D7363h
0x1800267fc  jnz     short loc_180026812
0x1800267fe  mov     rdx, [rbp+0C8h]
0x180026805  mov     ecx, [rbp+68h]
0x180026808  call    _XcptFilter_0
0x18002680d  mov     [rbp+70h], eax
0x180026810  jmp     short loc_180026819
0x180026812  mov     dword ptr [rbp+70h], 0
0x180026819  mov     eax, [rbp+70h]
0x18002681c  add     rsp, 20h
0x180026820  pop     rbp
0x180026821  retn
0x180026823  push    rbp
0x180026825  sub     rsp, 20h
0x180026829  mov     rbp, rdx
0x18002682c  mov     rax, [rcx]
0x18002682f  mov     edx, [rax]
0x180026831  mov     [rbp+0D0h], rcx
0x180026838  mov     [rbp+78h], edx
0x18002683b  mov     eax, [rbp+78h]
0x18002683e  cmp     eax, 0E06D7363h
0x180026843  jnz     short loc_18002685C
0x180026845  mov     rdx, [rbp+0D0h]
0x18002684c  mov     ecx, [rbp+78h]
0x18002684f  call    _XcptFilter_0
0x180026854  mov     [rbp+80h], eax
0x18002685a  jmp     short loc_180026866
0x18002685c  mov     dword ptr [rbp+80h], 0
0x180026866  mov     eax, [rbp+80h]
0x18002686c  add     rsp, 20h
0x180026870  pop     rbp
0x180026871  retn
0x180026873  push    rbp
0x180026875  sub     rsp, 20h
0x180026879  mov     rbp, rdx
0x18002687c  mov     rax, [rcx]
0x18002687f  mov     edx, [rax]
0x180026881  mov     [rbp+0D8h], rcx
0x180026888  mov     [rbp+88h], edx
0x18002688e  mov     eax, [rbp+88h]
0x180026894  cmp     eax, 0E06D7363h
0x180026899  jnz     short loc_1800268B5
0x18002689b  mov     rdx, [rbp+0D8h]
0x1800268a2  mov     ecx, [rbp+88h]
0x1800268a8  call    _XcptFilter_0
0x1800268ad  mov     [rbp+90h], eax
0x1800268b3  jmp     short loc_1800268BF
0x1800268b5  mov     dword ptr [rbp+90h], 0
0x1800268bf  mov     eax, [rbp+90h]
0x1800268c5  add     rsp, 20h
0x1800268c9  pop     rbp
0x1800268ca  retn
0x1800268cc  push    rbp
0x1800268ce  sub     rsp, 20h
0x1800268d2  mov     rbp, rdx
0x1800268d5  mov     rax, [rcx]
0x1800268d8  mov     edx, [rax]
0x1800268da  mov     [rbp+0E0h], rcx
0x1800268e1  mov     [rbp+98h], edx
0x1800268e7  mov     eax, [rbp+98h]
0x1800268ed  cmp     eax, 0E06D7363h
0x1800268f2  jnz     short loc_18002690E
0x1800268f4  mov     rdx, [rbp+0E0h]
0x1800268fb  mov     ecx, [rbp+98h]
0x180026901  call    _XcptFilter_0
0x180026906  mov     [rbp+0A0h], eax
0x18002690c  jmp     short loc_180026918
0x18002690e  mov     dword ptr [rbp+0A0h], 0
0x180026918  mov     eax, [rbp+0A0h]
0x18002691e  add     rsp, 20h
0x180026922  pop     rbp
0x180026923  retn
0x180026925  push    rbp
0x180026927  sub     rsp, 20h
0x18002692b  mov     rbp, rdx
0x18002692e  cmp     dword ptr [rbp+118h], 1
0x180026935  ja      short loc_180026941
0x180026937  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

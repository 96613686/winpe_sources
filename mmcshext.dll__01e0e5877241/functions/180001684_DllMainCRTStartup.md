# __DllMainCRTStartup

- ea: `0x180001684`
- end: `0x180001890`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001640`

## callees

- `0x180001410`
- `0x180001684`
- `0x180001d5c`
- `0x1800066f4`
- `0x18000a620`

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
  if ( (_DWORD)fdwReason || dword_1800128F8 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800128FC = 1;
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
            if ( dword_1800128FC )
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
0x180001684  mov     [rsp+lpvReserved], r8
0x180001689  mov     [rsp+arg_8], edx
0x18000168d  mov     [rsp+arg_0], rcx
0x180001692  push    rbx
0x180001693  push    rsi
0x180001694  push    rdi
0x180001695  sub     rsp, 0F0h
0x18000169c  mov     edi, edx
0x18000169e  mov     rsi, rcx
0x1800016a1  mov     ebx, 1
0x1800016a6  cmp     edx, ebx
0x1800016a8  ja      short loc_1800016B0
0x1800016aa  mov     cs:__native_dllmain_reason, edx
0x1800016b0  test    edx, edx
0x1800016b2  jnz     short loc_1800016C7
0x1800016b4  cmp     cs:dword_1800128F8, edx
0x1800016ba  jnz     short loc_1800016C7
0x1800016bc  xor     ebx, ebx
0x1800016be  mov     [rsp+108h+var_E8], ebx
0x1800016c2  jmp     loc_180001874
0x1800016c7  lea     eax, [rdx-1]
0x1800016ca  cmp     eax, 1
0x1800016cd  ja      loc_180001754
0x1800016d3  mov     rax, cs:_pRawDllMain
0x1800016da  test    rax, rax
0x1800016dd  jz      short loc_180001715
0x1800016df  cmp     edx, 1
0x1800016e2  jnz     short loc_1800016EA
0x1800016e4  mov     cs:dword_1800128FC, edx
0x1800016ea  mov     r8, [rsp+108h+lpvReserved]
0x1800016f2  call    cs:__guard_dispatch_icall_fptr
0x1800016f8  mov     ebx, eax
0x1800016fa  mov     [rsp+108h+var_E8], eax
0x1800016fe  jmp     short loc_180001715
0x180001700  xor     ebx, ebx
0x180001702  mov     [rsp+108h+var_E8], ebx
0x180001706  mov     edi, [rsp+108h+arg_8]
0x18000170d  mov     rsi, [rsp+108h+arg_0]
0x180001715  test    ebx, ebx
0x180001717  jz      loc_180001874
0x18000171d  mov     r8, [rsp+108h+lpvReserved]
0x180001725  mov     edx, edi
0x180001727  mov     rcx, rsi
0x18000172a  call    _CRT_INIT
0x18000172f  mov     ebx, eax
0x180001731  mov     [rsp+108h+var_E8], eax
0x180001735  jmp     short loc_18000174C
0x180001737  xor     ebx, ebx
0x180001739  mov     [rsp+108h+var_E8], ebx
0x18000173d  mov     edi, [rsp+108h+arg_8]
0x180001744  mov     rsi, [rsp+108h+arg_0]
0x18000174c  test    ebx, ebx
0x18000174e  jz      loc_180001874
0x180001754  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000175c  mov     edx, edi; fdwReason
0x18000175e  mov     rcx, rsi; hinstDLL
0x180001761  call    DllMain
0x180001766  mov     ebx, eax
0x180001768  mov     [rsp+108h+var_E8], eax
0x18000176c  jmp     short loc_180001783
0x18000176e  xor     ebx, ebx
0x180001770  mov     [rsp+108h+var_E8], ebx
0x180001774  mov     edi, [rsp+108h+arg_8]
0x18000177b  mov     rsi, [rsp+108h+arg_0]
0x180001783  cmp     edi, 1
0x180001786  jnz     short loc_1800017FF
0x180001788  test    ebx, ebx
0x18000178a  jnz     short loc_1800017FF
0x18000178c  xor     r8d, r8d; lpvReserved
0x18000178f  xor     edx, edx; fdwReason
0x180001791  mov     rcx, rsi; hinstDLL
0x180001794  call    DllMain
0x180001799  jmp     short loc_1800017AE
0x18000179b  mov     edi, [rsp+108h+arg_8]
0x1800017a2  mov     rsi, [rsp+108h+arg_0]
0x1800017aa  mov     ebx, [rsp+108h+var_E8]
0x1800017ae  xor     r8d, r8d
0x1800017b1  xor     edx, edx
0x1800017b3  mov     rcx, rsi
0x1800017b6  call    _CRT_INIT
0x1800017bb  jmp     short loc_1800017D0
0x1800017bd  mov     edi, [rsp+108h+arg_8]
0x1800017c4  mov     rsi, [rsp+108h+arg_0]
0x1800017cc  mov     ebx, [rsp+108h+var_E8]
0x1800017d0  mov     rax, cs:_pRawDllMain
0x1800017d7  test    rax, rax
0x1800017da  jz      short loc_1800017FF
0x1800017dc  xor     r8d, r8d
0x1800017df  xor     edx, edx
0x1800017e1  mov     rcx, rsi
0x1800017e4  call    cs:__guard_dispatch_icall_fptr
0x1800017ea  jmp     short loc_1800017FF
0x1800017ec  mov     edi, [rsp+108h+arg_8]
0x1800017f3  mov     rsi, [rsp+108h+arg_0]
0x1800017fb  mov     ebx, [rsp+108h+var_E8]
0x1800017ff  test    edi, edi
0x180001801  jz      short loc_180001808
0x180001803  cmp     edi, 3
0x180001806  jnz     short loc_180001874
0x180001808  mov     r8, [rsp+108h+lpvReserved]
0x180001810  mov     edx, edi
0x180001812  mov     rcx, rsi
0x180001815  call    _CRT_INIT
0x18000181a  mov     ebx, eax
0x18000181c  mov     [rsp+108h+var_E8], eax
0x180001820  jmp     short loc_180001837
0x180001822  xor     ebx, ebx
0x180001824  mov     [rsp+108h+var_E8], ebx
0x180001828  mov     edi, [rsp+108h+arg_8]
0x18000182f  mov     rsi, [rsp+108h+arg_0]
0x180001837  mov     rax, cs:_pRawDllMain
0x18000183e  test    rax, rax
0x180001841  jz      short loc_180001874
0x180001843  cmp     cs:dword_1800128FC, 0
0x18000184a  jz      short loc_180001874
0x18000184c  mov     r8, [rsp+108h+lpvReserved]
0x180001854  mov     edx, edi
0x180001856  mov     rcx, rsi
0x180001859  call    cs:__guard_dispatch_icall_fptr
0x18000185f  mov     ebx, eax
0x180001861  mov     [rsp+108h+var_E8], eax
0x180001865  jmp     short loc_180001874
0x180001867  xor     ebx, ebx
0x180001869  mov     [rsp+108h+var_E8], ebx
0x18000186d  mov     edi, [rsp+108h+arg_8]
0x180001874  cmp     edi, 1
0x180001877  ja      short loc_180001883
0x180001879  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001883  mov     eax, ebx
0x180001885  add     rsp, 0F0h
0x18000188c  pop     rdi
0x18000188d  pop     rsi
0x18000188e  pop     rbx
0x18000188f  retn
0x18000a6c3  push    rbp
0x18000a6c5  sub     rsp, 20h
0x18000a6c9  mov     rbp, rdx
0x18000a6cc  mov     rax, [rcx]
0x18000a6cf  mov     edx, [rax]
0x18000a6d1  mov     [rbp+0A8h], rcx
0x18000a6d8  mov     [rbp+28h], edx
0x18000a6db  mov     eax, [rbp+28h]
0x18000a6de  cmp     eax, 0E06D7363h
0x18000a6e3  jnz     short loc_18000A6F9
0x18000a6e5  mov     rdx, [rbp+0A8h]
0x18000a6ec  mov     ecx, [rbp+28h]
0x18000a6ef  call    _XcptFilter_0
0x18000a6f4  mov     [rbp+30h], eax
0x18000a6f7  jmp     short loc_18000A700
0x18000a6f9  mov     dword ptr [rbp+30h], 0
0x18000a700  mov     eax, [rbp+30h]
0x18000a703  add     rsp, 20h
0x18000a707  pop     rbp
0x18000a708  retn
0x18000a70a  push    rbp
0x18000a70c  sub     rsp, 20h
0x18000a710  mov     rbp, rdx
0x18000a713  mov     rax, [rcx]
0x18000a716  mov     edx, [rax]
0x18000a718  mov     [rbp+0B0h], rcx
0x18000a71f  mov     [rbp+38h], edx
0x18000a722  mov     eax, [rbp+38h]
0x18000a725  cmp     eax, 0E06D7363h
0x18000a72a  jnz     short loc_18000A740
0x18000a72c  mov     rdx, [rbp+0B0h]
0x18000a733  mov     ecx, [rbp+38h]
0x18000a736  call    _XcptFilter_0
0x18000a73b  mov     [rbp+40h], eax
0x18000a73e  jmp     short loc_18000A747
0x18000a740  mov     dword ptr [rbp+40h], 0
0x18000a747  mov     eax, [rbp+40h]
0x18000a74a  add     rsp, 20h
0x18000a74e  pop     rbp
0x18000a74f  retn
0x18000a751  push    rbp
0x18000a753  sub     rsp, 20h
0x18000a757  mov     rbp, rdx
0x18000a75a  mov     rax, [rcx]
0x18000a75d  mov     edx, [rax]
0x18000a75f  mov     [rbp+0B8h], rcx
0x18000a766  mov     [rbp+48h], edx
0x18000a769  mov     eax, [rbp+48h]
0x18000a76c  cmp     eax, 0E06D7363h
0x18000a771  jnz     short loc_18000A787
0x18000a773  mov     rdx, [rbp+0B8h]
0x18000a77a  mov     ecx, [rbp+48h]
0x18000a77d  call    _XcptFilter_0
0x18000a782  mov     [rbp+50h], eax
0x18000a785  jmp     short loc_18000A78E
0x18000a787  mov     dword ptr [rbp+50h], 0
0x18000a78e  mov     eax, [rbp+50h]
0x18000a791  add     rsp, 20h
0x18000a795  pop     rbp
0x18000a796  retn
0x18000a798  push    rbp
0x18000a79a  sub     rsp, 20h
0x18000a79e  mov     rbp, rdx
0x18000a7a1  mov     rax, [rcx]
0x18000a7a4  mov     edx, [rax]
0x18000a7a6  mov     [rbp+0C0h], rcx
0x18000a7ad  mov     [rbp+58h], edx
0x18000a7b0  mov     eax, [rbp+58h]
0x18000a7b3  cmp     eax, 0E06D7363h
0x18000a7b8  jnz     short loc_18000A7CE
0x18000a7ba  mov     rdx, [rbp+0C0h]
0x18000a7c1  mov     ecx, [rbp+58h]
0x18000a7c4  call    _XcptFilter_0
0x18000a7c9  mov     [rbp+60h], eax
0x18000a7cc  jmp     short loc_18000A7D5
0x18000a7ce  mov     dword ptr [rbp+60h], 0
0x18000a7d5  mov     eax, [rbp+60h]
0x18000a7d8  add     rsp, 20h
0x18000a7dc  pop     rbp
0x18000a7dd  retn
0x18000a7df  push    rbp
0x18000a7e1  sub     rsp, 20h
0x18000a7e5  mov     rbp, rdx
0x18000a7e8  mov     rax, [rcx]
0x18000a7eb  mov     edx, [rax]
0x18000a7ed  mov     [rbp+0C8h], rcx
0x18000a7f4  mov     [rbp+68h], edx
0x18000a7f7  mov     eax, [rbp+68h]
0x18000a7fa  cmp     eax, 0E06D7363h
0x18000a7ff  jnz     short loc_18000A815
0x18000a801  mov     rdx, [rbp+0C8h]
0x18000a808  mov     ecx, [rbp+68h]
0x18000a80b  call    _XcptFilter_0
0x18000a810  mov     [rbp+70h], eax
0x18000a813  jmp     short loc_18000A81C
0x18000a815  mov     dword ptr [rbp+70h], 0
0x18000a81c  mov     eax, [rbp+70h]
0x18000a81f  add     rsp, 20h
0x18000a823  pop     rbp
0x18000a824  retn
0x18000a826  push    rbp
0x18000a828  sub     rsp, 20h
0x18000a82c  mov     rbp, rdx
0x18000a82f  mov     rax, [rcx]
0x18000a832  mov     edx, [rax]
0x18000a834  mov     [rbp+0D0h], rcx
0x18000a83b  mov     [rbp+78h], edx
0x18000a83e  mov     eax, [rbp+78h]
0x18000a841  cmp     eax, 0E06D7363h
0x18000a846  jnz     short loc_18000A85F
0x18000a848  mov     rdx, [rbp+0D0h]
0x18000a84f  mov     ecx, [rbp+78h]
0x18000a852  call    _XcptFilter_0
0x18000a857  mov     [rbp+80h], eax
0x18000a85d  jmp     short loc_18000A869
0x18000a85f  mov     dword ptr [rbp+80h], 0
0x18000a869  mov     eax, [rbp+80h]
0x18000a86f  add     rsp, 20h
0x18000a873  pop     rbp
0x18000a874  retn
0x18000a876  push    rbp
0x18000a878  sub     rsp, 20h
0x18000a87c  mov     rbp, rdx
0x18000a87f  mov     rax, [rcx]
0x18000a882  mov     edx, [rax]
0x18000a884  mov     [rbp+0D8h], rcx
0x18000a88b  mov     [rbp+88h], edx
0x18000a891  mov     eax, [rbp+88h]
0x18000a897  cmp     eax, 0E06D7363h
0x18000a89c  jnz     short loc_18000A8B8
0x18000a89e  mov     rdx, [rbp+0D8h]
0x18000a8a5  mov     ecx, [rbp+88h]
0x18000a8ab  call    _XcptFilter_0
0x18000a8b0  mov     [rbp+90h], eax
0x18000a8b6  jmp     short loc_18000A8C2
0x18000a8b8  mov     dword ptr [rbp+90h], 0
0x18000a8c2  mov     eax, [rbp+90h]
0x18000a8c8  add     rsp, 20h
0x18000a8cc  pop     rbp
0x18000a8cd  retn
0x18000a8cf  push    rbp
0x18000a8d1  sub     rsp, 20h
0x18000a8d5  mov     rbp, rdx
0x18000a8d8  mov     rax, [rcx]
0x18000a8db  mov     edx, [rax]
0x18000a8dd  mov     [rbp+0E0h], rcx
0x18000a8e4  mov     [rbp+98h], edx
0x18000a8ea  mov     eax, [rbp+98h]
0x18000a8f0  cmp     eax, 0E06D7363h
0x18000a8f5  jnz     short loc_18000A911
0x18000a8f7  mov     rdx, [rbp+0E0h]
0x18000a8fe  mov     ecx, [rbp+98h]
0x18000a904  call    _XcptFilter_0
0x18000a909  mov     [rbp+0A0h], eax
0x18000a90f  jmp     short loc_18000A91B
0x18000a911  mov     dword ptr [rbp+0A0h], 0
0x18000a91b  mov     eax, [rbp+0A0h]
0x18000a921  add     rsp, 20h
0x18000a925  pop     rbp
0x18000a926  retn
0x18000a928  push    rbp
0x18000a92a  sub     rsp, 20h
0x18000a92e  mov     rbp, rdx
0x18000a931  cmp     dword ptr [rbp+118h], 1
0x18000a938  ja      short loc_18000A944
0x18000a93a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

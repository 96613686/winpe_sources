# __DllMainCRTStartup

- ea: `0x180001564`
- end: `0x180001770`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001520`

## callees

- `0x180001160`
- `0x1800012f0`
- `0x180001564`
- `0x180001c58`
- `0x18000c560`

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
  if ( (_DWORD)fdwReason || dword_180012320 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180012324 = 1;
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
            if ( dword_180012324 )
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
0x180001564  mov     [rsp+lpvReserved], r8
0x180001569  mov     [rsp+arg_8], edx
0x18000156d  mov     [rsp+arg_0], rcx
0x180001572  push    rbx
0x180001573  push    rsi
0x180001574  push    rdi
0x180001575  sub     rsp, 0F0h
0x18000157c  mov     edi, edx
0x18000157e  mov     rsi, rcx
0x180001581  mov     ebx, 1
0x180001586  cmp     edx, ebx
0x180001588  ja      short loc_180001590
0x18000158a  mov     cs:__native_dllmain_reason, edx
0x180001590  test    edx, edx
0x180001592  jnz     short loc_1800015A7
0x180001594  cmp     cs:dword_180012320, edx
0x18000159a  jnz     short loc_1800015A7
0x18000159c  xor     ebx, ebx
0x18000159e  mov     [rsp+108h+var_E8], ebx
0x1800015a2  jmp     loc_180001754
0x1800015a7  lea     eax, [rdx-1]
0x1800015aa  cmp     eax, 1
0x1800015ad  ja      loc_180001634
0x1800015b3  mov     rax, cs:_pRawDllMain
0x1800015ba  test    rax, rax
0x1800015bd  jz      short loc_1800015F5
0x1800015bf  cmp     edx, 1
0x1800015c2  jnz     short loc_1800015CA
0x1800015c4  mov     cs:dword_180012324, edx
0x1800015ca  mov     r8, [rsp+108h+lpvReserved]
0x1800015d2  call    cs:__guard_dispatch_icall_fptr
0x1800015d8  mov     ebx, eax
0x1800015da  mov     [rsp+108h+var_E8], eax
0x1800015de  jmp     short loc_1800015F5
0x1800015e0  xor     ebx, ebx
0x1800015e2  mov     [rsp+108h+var_E8], ebx
0x1800015e6  mov     edi, [rsp+108h+arg_8]
0x1800015ed  mov     rsi, [rsp+108h+arg_0]
0x1800015f5  test    ebx, ebx
0x1800015f7  jz      loc_180001754
0x1800015fd  mov     r8, [rsp+108h+lpvReserved]
0x180001605  mov     edx, edi
0x180001607  mov     rcx, rsi
0x18000160a  call    _CRT_INIT
0x18000160f  mov     ebx, eax
0x180001611  mov     [rsp+108h+var_E8], eax
0x180001615  jmp     short loc_18000162C
0x180001617  xor     ebx, ebx
0x180001619  mov     [rsp+108h+var_E8], ebx
0x18000161d  mov     edi, [rsp+108h+arg_8]
0x180001624  mov     rsi, [rsp+108h+arg_0]
0x18000162c  test    ebx, ebx
0x18000162e  jz      loc_180001754
0x180001634  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000163c  mov     edx, edi; fdwReason
0x18000163e  mov     rcx, rsi; hinstDLL
0x180001641  call    DllMain
0x180001646  mov     ebx, eax
0x180001648  mov     [rsp+108h+var_E8], eax
0x18000164c  jmp     short loc_180001663
0x18000164e  xor     ebx, ebx
0x180001650  mov     [rsp+108h+var_E8], ebx
0x180001654  mov     edi, [rsp+108h+arg_8]
0x18000165b  mov     rsi, [rsp+108h+arg_0]
0x180001663  cmp     edi, 1
0x180001666  jnz     short loc_1800016DF
0x180001668  test    ebx, ebx
0x18000166a  jnz     short loc_1800016DF
0x18000166c  xor     r8d, r8d; lpvReserved
0x18000166f  xor     edx, edx; fdwReason
0x180001671  mov     rcx, rsi; hinstDLL
0x180001674  call    DllMain
0x180001679  jmp     short loc_18000168E
0x18000167b  mov     edi, [rsp+108h+arg_8]
0x180001682  mov     rsi, [rsp+108h+arg_0]
0x18000168a  mov     ebx, [rsp+108h+var_E8]
0x18000168e  xor     r8d, r8d
0x180001691  xor     edx, edx
0x180001693  mov     rcx, rsi
0x180001696  call    _CRT_INIT
0x18000169b  jmp     short loc_1800016B0
0x18000169d  mov     edi, [rsp+108h+arg_8]
0x1800016a4  mov     rsi, [rsp+108h+arg_0]
0x1800016ac  mov     ebx, [rsp+108h+var_E8]
0x1800016b0  mov     rax, cs:_pRawDllMain
0x1800016b7  test    rax, rax
0x1800016ba  jz      short loc_1800016DF
0x1800016bc  xor     r8d, r8d
0x1800016bf  xor     edx, edx
0x1800016c1  mov     rcx, rsi
0x1800016c4  call    cs:__guard_dispatch_icall_fptr
0x1800016ca  jmp     short loc_1800016DF
0x1800016cc  mov     edi, [rsp+108h+arg_8]
0x1800016d3  mov     rsi, [rsp+108h+arg_0]
0x1800016db  mov     ebx, [rsp+108h+var_E8]
0x1800016df  test    edi, edi
0x1800016e1  jz      short loc_1800016E8
0x1800016e3  cmp     edi, 3
0x1800016e6  jnz     short loc_180001754
0x1800016e8  mov     r8, [rsp+108h+lpvReserved]
0x1800016f0  mov     edx, edi
0x1800016f2  mov     rcx, rsi
0x1800016f5  call    _CRT_INIT
0x1800016fa  mov     ebx, eax
0x1800016fc  mov     [rsp+108h+var_E8], eax
0x180001700  jmp     short loc_180001717
0x180001702  xor     ebx, ebx
0x180001704  mov     [rsp+108h+var_E8], ebx
0x180001708  mov     edi, [rsp+108h+arg_8]
0x18000170f  mov     rsi, [rsp+108h+arg_0]
0x180001717  mov     rax, cs:_pRawDllMain
0x18000171e  test    rax, rax
0x180001721  jz      short loc_180001754
0x180001723  cmp     cs:dword_180012324, 0
0x18000172a  jz      short loc_180001754
0x18000172c  mov     r8, [rsp+108h+lpvReserved]
0x180001734  mov     edx, edi
0x180001736  mov     rcx, rsi
0x180001739  call    cs:__guard_dispatch_icall_fptr
0x18000173f  mov     ebx, eax
0x180001741  mov     [rsp+108h+var_E8], eax
0x180001745  jmp     short loc_180001754
0x180001747  xor     ebx, ebx
0x180001749  mov     [rsp+108h+var_E8], ebx
0x18000174d  mov     edi, [rsp+108h+arg_8]
0x180001754  cmp     edi, 1
0x180001757  ja      short loc_180001763
0x180001759  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001763  mov     eax, ebx
0x180001765  add     rsp, 0F0h
0x18000176c  pop     rdi
0x18000176d  pop     rsi
0x18000176e  pop     rbx
0x18000176f  retn
0x18000c603  push    rbp
0x18000c605  sub     rsp, 20h
0x18000c609  mov     rbp, rdx
0x18000c60c  mov     rax, [rcx]
0x18000c60f  mov     edx, [rax]
0x18000c611  mov     [rbp+0A8h], rcx
0x18000c618  mov     [rbp+28h], edx
0x18000c61b  mov     eax, [rbp+28h]
0x18000c61e  cmp     eax, 0E06D7363h
0x18000c623  jnz     short loc_18000C639
0x18000c625  mov     rdx, [rbp+0A8h]
0x18000c62c  mov     ecx, [rbp+28h]
0x18000c62f  call    _XcptFilter_0
0x18000c634  mov     [rbp+30h], eax
0x18000c637  jmp     short loc_18000C640
0x18000c639  mov     dword ptr [rbp+30h], 0
0x18000c640  mov     eax, [rbp+30h]
0x18000c643  add     rsp, 20h
0x18000c647  pop     rbp
0x18000c648  retn
0x18000c64a  push    rbp
0x18000c64c  sub     rsp, 20h
0x18000c650  mov     rbp, rdx
0x18000c653  mov     rax, [rcx]
0x18000c656  mov     edx, [rax]
0x18000c658  mov     [rbp+0B0h], rcx
0x18000c65f  mov     [rbp+38h], edx
0x18000c662  mov     eax, [rbp+38h]
0x18000c665  cmp     eax, 0E06D7363h
0x18000c66a  jnz     short loc_18000C680
0x18000c66c  mov     rdx, [rbp+0B0h]
0x18000c673  mov     ecx, [rbp+38h]
0x18000c676  call    _XcptFilter_0
0x18000c67b  mov     [rbp+40h], eax
0x18000c67e  jmp     short loc_18000C687
0x18000c680  mov     dword ptr [rbp+40h], 0
0x18000c687  mov     eax, [rbp+40h]
0x18000c68a  add     rsp, 20h
0x18000c68e  pop     rbp
0x18000c68f  retn
0x18000c691  push    rbp
0x18000c693  sub     rsp, 20h
0x18000c697  mov     rbp, rdx
0x18000c69a  mov     rax, [rcx]
0x18000c69d  mov     edx, [rax]
0x18000c69f  mov     [rbp+0B8h], rcx
0x18000c6a6  mov     [rbp+48h], edx
0x18000c6a9  mov     eax, [rbp+48h]
0x18000c6ac  cmp     eax, 0E06D7363h
0x18000c6b1  jnz     short loc_18000C6C7
0x18000c6b3  mov     rdx, [rbp+0B8h]
0x18000c6ba  mov     ecx, [rbp+48h]
0x18000c6bd  call    _XcptFilter_0
0x18000c6c2  mov     [rbp+50h], eax
0x18000c6c5  jmp     short loc_18000C6CE
0x18000c6c7  mov     dword ptr [rbp+50h], 0
0x18000c6ce  mov     eax, [rbp+50h]
0x18000c6d1  add     rsp, 20h
0x18000c6d5  pop     rbp
0x18000c6d6  retn
0x18000c6d8  push    rbp
0x18000c6da  sub     rsp, 20h
0x18000c6de  mov     rbp, rdx
0x18000c6e1  mov     rax, [rcx]
0x18000c6e4  mov     edx, [rax]
0x18000c6e6  mov     [rbp+0C0h], rcx
0x18000c6ed  mov     [rbp+58h], edx
0x18000c6f0  mov     eax, [rbp+58h]
0x18000c6f3  cmp     eax, 0E06D7363h
0x18000c6f8  jnz     short loc_18000C70E
0x18000c6fa  mov     rdx, [rbp+0C0h]
0x18000c701  mov     ecx, [rbp+58h]
0x18000c704  call    _XcptFilter_0
0x18000c709  mov     [rbp+60h], eax
0x18000c70c  jmp     short loc_18000C715
0x18000c70e  mov     dword ptr [rbp+60h], 0
0x18000c715  mov     eax, [rbp+60h]
0x18000c718  add     rsp, 20h
0x18000c71c  pop     rbp
0x18000c71d  retn
0x18000c71f  push    rbp
0x18000c721  sub     rsp, 20h
0x18000c725  mov     rbp, rdx
0x18000c728  mov     rax, [rcx]
0x18000c72b  mov     edx, [rax]
0x18000c72d  mov     [rbp+0C8h], rcx
0x18000c734  mov     [rbp+68h], edx
0x18000c737  mov     eax, [rbp+68h]
0x18000c73a  cmp     eax, 0E06D7363h
0x18000c73f  jnz     short loc_18000C755
0x18000c741  mov     rdx, [rbp+0C8h]
0x18000c748  mov     ecx, [rbp+68h]
0x18000c74b  call    _XcptFilter_0
0x18000c750  mov     [rbp+70h], eax
0x18000c753  jmp     short loc_18000C75C
0x18000c755  mov     dword ptr [rbp+70h], 0
0x18000c75c  mov     eax, [rbp+70h]
0x18000c75f  add     rsp, 20h
0x18000c763  pop     rbp
0x18000c764  retn
0x18000c766  push    rbp
0x18000c768  sub     rsp, 20h
0x18000c76c  mov     rbp, rdx
0x18000c76f  mov     rax, [rcx]
0x18000c772  mov     edx, [rax]
0x18000c774  mov     [rbp+0D0h], rcx
0x18000c77b  mov     [rbp+78h], edx
0x18000c77e  mov     eax, [rbp+78h]
0x18000c781  cmp     eax, 0E06D7363h
0x18000c786  jnz     short loc_18000C79F
0x18000c788  mov     rdx, [rbp+0D0h]
0x18000c78f  mov     ecx, [rbp+78h]
0x18000c792  call    _XcptFilter_0
0x18000c797  mov     [rbp+80h], eax
0x18000c79d  jmp     short loc_18000C7A9
0x18000c79f  mov     dword ptr [rbp+80h], 0
0x18000c7a9  mov     eax, [rbp+80h]
0x18000c7af  add     rsp, 20h
0x18000c7b3  pop     rbp
0x18000c7b4  retn
0x18000c7b6  push    rbp
0x18000c7b8  sub     rsp, 20h
0x18000c7bc  mov     rbp, rdx
0x18000c7bf  mov     rax, [rcx]
0x18000c7c2  mov     edx, [rax]
0x18000c7c4  mov     [rbp+0D8h], rcx
0x18000c7cb  mov     [rbp+88h], edx
0x18000c7d1  mov     eax, [rbp+88h]
0x18000c7d7  cmp     eax, 0E06D7363h
0x18000c7dc  jnz     short loc_18000C7F8
0x18000c7de  mov     rdx, [rbp+0D8h]
0x18000c7e5  mov     ecx, [rbp+88h]
0x18000c7eb  call    _XcptFilter_0
0x18000c7f0  mov     [rbp+90h], eax
0x18000c7f6  jmp     short loc_18000C802
0x18000c7f8  mov     dword ptr [rbp+90h], 0
0x18000c802  mov     eax, [rbp+90h]
0x18000c808  add     rsp, 20h
0x18000c80c  pop     rbp
0x18000c80d  retn
0x18000c80f  push    rbp
0x18000c811  sub     rsp, 20h
0x18000c815  mov     rbp, rdx
0x18000c818  mov     rax, [rcx]
0x18000c81b  mov     edx, [rax]
0x18000c81d  mov     [rbp+0E0h], rcx
0x18000c824  mov     [rbp+98h], edx
0x18000c82a  mov     eax, [rbp+98h]
0x18000c830  cmp     eax, 0E06D7363h
0x18000c835  jnz     short loc_18000C851
0x18000c837  mov     rdx, [rbp+0E0h]
0x18000c83e  mov     ecx, [rbp+98h]
0x18000c844  call    _XcptFilter_0
0x18000c849  mov     [rbp+0A0h], eax
0x18000c84f  jmp     short loc_18000C85B
0x18000c851  mov     dword ptr [rbp+0A0h], 0
0x18000c85b  mov     eax, [rbp+0A0h]
0x18000c861  add     rsp, 20h
0x18000c865  pop     rbp
0x18000c866  retn
0x18000c868  push    rbp
0x18000c86a  sub     rsp, 20h
0x18000c86e  mov     rbp, rdx
0x18000c871  cmp     dword ptr [rbp+118h], 1
0x18000c878  ja      short loc_18000C884
0x18000c87a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

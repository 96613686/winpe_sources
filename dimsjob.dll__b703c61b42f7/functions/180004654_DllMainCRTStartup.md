# __DllMainCRTStartup

- ea: `0x180004654`
- end: `0x180004860`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004610`

## callees

- `0x1800043e0`
- `0x180004654`
- `0x180004c5c`
- `0x18000a5dc`
- `0x18000ada0`

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
  if ( (_DWORD)fdwReason || dword_180011200 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180011204 = 1;
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
            if ( dword_180011204 )
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
0x180004654  mov     [rsp+lpvReserved], r8
0x180004659  mov     [rsp+arg_8], edx
0x18000465d  mov     [rsp+arg_0], rcx
0x180004662  push    rbx
0x180004663  push    rsi
0x180004664  push    rdi
0x180004665  sub     rsp, 0F0h
0x18000466c  mov     edi, edx
0x18000466e  mov     rsi, rcx
0x180004671  mov     ebx, 1
0x180004676  cmp     edx, ebx
0x180004678  ja      short loc_180004680
0x18000467a  mov     cs:__native_dllmain_reason, edx
0x180004680  test    edx, edx
0x180004682  jnz     short loc_180004697
0x180004684  cmp     cs:dword_180011200, edx
0x18000468a  jnz     short loc_180004697
0x18000468c  xor     ebx, ebx
0x18000468e  mov     [rsp+108h+var_E8], ebx
0x180004692  jmp     loc_180004844
0x180004697  lea     eax, [rdx-1]
0x18000469a  cmp     eax, 1
0x18000469d  ja      loc_180004724
0x1800046a3  mov     rax, cs:_pRawDllMain
0x1800046aa  test    rax, rax
0x1800046ad  jz      short loc_1800046E5
0x1800046af  cmp     edx, 1
0x1800046b2  jnz     short loc_1800046BA
0x1800046b4  mov     cs:dword_180011204, edx
0x1800046ba  mov     r8, [rsp+108h+lpvReserved]
0x1800046c2  call    cs:__guard_dispatch_icall_fptr
0x1800046c8  mov     ebx, eax
0x1800046ca  mov     [rsp+108h+var_E8], eax
0x1800046ce  jmp     short loc_1800046E5
0x1800046d0  xor     ebx, ebx
0x1800046d2  mov     [rsp+108h+var_E8], ebx
0x1800046d6  mov     edi, [rsp+108h+arg_8]
0x1800046dd  mov     rsi, [rsp+108h+arg_0]
0x1800046e5  test    ebx, ebx
0x1800046e7  jz      loc_180004844
0x1800046ed  mov     r8, [rsp+108h+lpvReserved]
0x1800046f5  mov     edx, edi
0x1800046f7  mov     rcx, rsi
0x1800046fa  call    _CRT_INIT
0x1800046ff  mov     ebx, eax
0x180004701  mov     [rsp+108h+var_E8], eax
0x180004705  jmp     short loc_18000471C
0x180004707  xor     ebx, ebx
0x180004709  mov     [rsp+108h+var_E8], ebx
0x18000470d  mov     edi, [rsp+108h+arg_8]
0x180004714  mov     rsi, [rsp+108h+arg_0]
0x18000471c  test    ebx, ebx
0x18000471e  jz      loc_180004844
0x180004724  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000472c  mov     edx, edi; fdwReason
0x18000472e  mov     rcx, rsi; hinstDLL
0x180004731  call    DllMain
0x180004736  mov     ebx, eax
0x180004738  mov     [rsp+108h+var_E8], eax
0x18000473c  jmp     short loc_180004753
0x18000473e  xor     ebx, ebx
0x180004740  mov     [rsp+108h+var_E8], ebx
0x180004744  mov     edi, [rsp+108h+arg_8]
0x18000474b  mov     rsi, [rsp+108h+arg_0]
0x180004753  cmp     edi, 1
0x180004756  jnz     short loc_1800047CF
0x180004758  test    ebx, ebx
0x18000475a  jnz     short loc_1800047CF
0x18000475c  xor     r8d, r8d; lpvReserved
0x18000475f  xor     edx, edx; fdwReason
0x180004761  mov     rcx, rsi; hinstDLL
0x180004764  call    DllMain
0x180004769  jmp     short loc_18000477E
0x18000476b  mov     edi, [rsp+108h+arg_8]
0x180004772  mov     rsi, [rsp+108h+arg_0]
0x18000477a  mov     ebx, [rsp+108h+var_E8]
0x18000477e  xor     r8d, r8d
0x180004781  xor     edx, edx
0x180004783  mov     rcx, rsi
0x180004786  call    _CRT_INIT
0x18000478b  jmp     short loc_1800047A0
0x18000478d  mov     edi, [rsp+108h+arg_8]
0x180004794  mov     rsi, [rsp+108h+arg_0]
0x18000479c  mov     ebx, [rsp+108h+var_E8]
0x1800047a0  mov     rax, cs:_pRawDllMain
0x1800047a7  test    rax, rax
0x1800047aa  jz      short loc_1800047CF
0x1800047ac  xor     r8d, r8d
0x1800047af  xor     edx, edx
0x1800047b1  mov     rcx, rsi
0x1800047b4  call    cs:__guard_dispatch_icall_fptr
0x1800047ba  jmp     short loc_1800047CF
0x1800047bc  mov     edi, [rsp+108h+arg_8]
0x1800047c3  mov     rsi, [rsp+108h+arg_0]
0x1800047cb  mov     ebx, [rsp+108h+var_E8]
0x1800047cf  test    edi, edi
0x1800047d1  jz      short loc_1800047D8
0x1800047d3  cmp     edi, 3
0x1800047d6  jnz     short loc_180004844
0x1800047d8  mov     r8, [rsp+108h+lpvReserved]
0x1800047e0  mov     edx, edi
0x1800047e2  mov     rcx, rsi
0x1800047e5  call    _CRT_INIT
0x1800047ea  mov     ebx, eax
0x1800047ec  mov     [rsp+108h+var_E8], eax
0x1800047f0  jmp     short loc_180004807
0x1800047f2  xor     ebx, ebx
0x1800047f4  mov     [rsp+108h+var_E8], ebx
0x1800047f8  mov     edi, [rsp+108h+arg_8]
0x1800047ff  mov     rsi, [rsp+108h+arg_0]
0x180004807  mov     rax, cs:_pRawDllMain
0x18000480e  test    rax, rax
0x180004811  jz      short loc_180004844
0x180004813  cmp     cs:dword_180011204, 0
0x18000481a  jz      short loc_180004844
0x18000481c  mov     r8, [rsp+108h+lpvReserved]
0x180004824  mov     edx, edi
0x180004826  mov     rcx, rsi
0x180004829  call    cs:__guard_dispatch_icall_fptr
0x18000482f  mov     ebx, eax
0x180004831  mov     [rsp+108h+var_E8], eax
0x180004835  jmp     short loc_180004844
0x180004837  xor     ebx, ebx
0x180004839  mov     [rsp+108h+var_E8], ebx
0x18000483d  mov     edi, [rsp+108h+arg_8]
0x180004844  cmp     edi, 1
0x180004847  ja      short loc_180004853
0x180004849  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180004853  mov     eax, ebx
0x180004855  add     rsp, 0F0h
0x18000485c  pop     rdi
0x18000485d  pop     rsi
0x18000485e  pop     rbx
0x18000485f  retn
0x18000b14c  push    rbp
0x18000b14e  sub     rsp, 20h
0x18000b152  mov     rbp, rdx
0x18000b155  mov     rax, [rcx]
0x18000b158  mov     edx, [rax]
0x18000b15a  mov     [rbp+0A8h], rcx
0x18000b161  mov     [rbp+28h], edx
0x18000b164  mov     eax, [rbp+28h]
0x18000b167  cmp     eax, 0E06D7363h
0x18000b16c  jnz     short loc_18000B182
0x18000b16e  mov     rdx, [rbp+0A8h]
0x18000b175  mov     ecx, [rbp+28h]
0x18000b178  call    _XcptFilter_0
0x18000b17d  mov     [rbp+30h], eax
0x18000b180  jmp     short loc_18000B189
0x18000b182  mov     dword ptr [rbp+30h], 0
0x18000b189  mov     eax, [rbp+30h]
0x18000b18c  add     rsp, 20h
0x18000b190  pop     rbp
0x18000b191  retn
0x18000b193  push    rbp
0x18000b195  sub     rsp, 20h
0x18000b199  mov     rbp, rdx
0x18000b19c  mov     rax, [rcx]
0x18000b19f  mov     edx, [rax]
0x18000b1a1  mov     [rbp+0B0h], rcx
0x18000b1a8  mov     [rbp+38h], edx
0x18000b1ab  mov     eax, [rbp+38h]
0x18000b1ae  cmp     eax, 0E06D7363h
0x18000b1b3  jnz     short loc_18000B1C9
0x18000b1b5  mov     rdx, [rbp+0B0h]
0x18000b1bc  mov     ecx, [rbp+38h]
0x18000b1bf  call    _XcptFilter_0
0x18000b1c4  mov     [rbp+40h], eax
0x18000b1c7  jmp     short loc_18000B1D0
0x18000b1c9  mov     dword ptr [rbp+40h], 0
0x18000b1d0  mov     eax, [rbp+40h]
0x18000b1d3  add     rsp, 20h
0x18000b1d7  pop     rbp
0x18000b1d8  retn
0x18000b1da  push    rbp
0x18000b1dc  sub     rsp, 20h
0x18000b1e0  mov     rbp, rdx
0x18000b1e3  mov     rax, [rcx]
0x18000b1e6  mov     edx, [rax]
0x18000b1e8  mov     [rbp+0B8h], rcx
0x18000b1ef  mov     [rbp+48h], edx
0x18000b1f2  mov     eax, [rbp+48h]
0x18000b1f5  cmp     eax, 0E06D7363h
0x18000b1fa  jnz     short loc_18000B210
0x18000b1fc  mov     rdx, [rbp+0B8h]
0x18000b203  mov     ecx, [rbp+48h]
0x18000b206  call    _XcptFilter_0
0x18000b20b  mov     [rbp+50h], eax
0x18000b20e  jmp     short loc_18000B217
0x18000b210  mov     dword ptr [rbp+50h], 0
0x18000b217  mov     eax, [rbp+50h]
0x18000b21a  add     rsp, 20h
0x18000b21e  pop     rbp
0x18000b21f  retn
0x18000b221  push    rbp
0x18000b223  sub     rsp, 20h
0x18000b227  mov     rbp, rdx
0x18000b22a  mov     rax, [rcx]
0x18000b22d  mov     edx, [rax]
0x18000b22f  mov     [rbp+0C0h], rcx
0x18000b236  mov     [rbp+58h], edx
0x18000b239  mov     eax, [rbp+58h]
0x18000b23c  cmp     eax, 0E06D7363h
0x18000b241  jnz     short loc_18000B257
0x18000b243  mov     rdx, [rbp+0C0h]
0x18000b24a  mov     ecx, [rbp+58h]
0x18000b24d  call    _XcptFilter_0
0x18000b252  mov     [rbp+60h], eax
0x18000b255  jmp     short loc_18000B25E
0x18000b257  mov     dword ptr [rbp+60h], 0
0x18000b25e  mov     eax, [rbp+60h]
0x18000b261  add     rsp, 20h
0x18000b265  pop     rbp
0x18000b266  retn
0x18000b268  push    rbp
0x18000b26a  sub     rsp, 20h
0x18000b26e  mov     rbp, rdx
0x18000b271  mov     rax, [rcx]
0x18000b274  mov     edx, [rax]
0x18000b276  mov     [rbp+0C8h], rcx
0x18000b27d  mov     [rbp+68h], edx
0x18000b280  mov     eax, [rbp+68h]
0x18000b283  cmp     eax, 0E06D7363h
0x18000b288  jnz     short loc_18000B29E
0x18000b28a  mov     rdx, [rbp+0C8h]
0x18000b291  mov     ecx, [rbp+68h]
0x18000b294  call    _XcptFilter_0
0x18000b299  mov     [rbp+70h], eax
0x18000b29c  jmp     short loc_18000B2A5
0x18000b29e  mov     dword ptr [rbp+70h], 0
0x18000b2a5  mov     eax, [rbp+70h]
0x18000b2a8  add     rsp, 20h
0x18000b2ac  pop     rbp
0x18000b2ad  retn
0x18000b2af  push    rbp
0x18000b2b1  sub     rsp, 20h
0x18000b2b5  mov     rbp, rdx
0x18000b2b8  mov     rax, [rcx]
0x18000b2bb  mov     edx, [rax]
0x18000b2bd  mov     [rbp+0D0h], rcx
0x18000b2c4  mov     [rbp+78h], edx
0x18000b2c7  mov     eax, [rbp+78h]
0x18000b2ca  cmp     eax, 0E06D7363h
0x18000b2cf  jnz     short loc_18000B2E8
0x18000b2d1  mov     rdx, [rbp+0D0h]
0x18000b2d8  mov     ecx, [rbp+78h]
0x18000b2db  call    _XcptFilter_0
0x18000b2e0  mov     [rbp+80h], eax
0x18000b2e6  jmp     short loc_18000B2F2
0x18000b2e8  mov     dword ptr [rbp+80h], 0
0x18000b2f2  mov     eax, [rbp+80h]
0x18000b2f8  add     rsp, 20h
0x18000b2fc  pop     rbp
0x18000b2fd  retn
0x18000b2ff  push    rbp
0x18000b301  sub     rsp, 20h
0x18000b305  mov     rbp, rdx
0x18000b308  mov     rax, [rcx]
0x18000b30b  mov     edx, [rax]
0x18000b30d  mov     [rbp+0D8h], rcx
0x18000b314  mov     [rbp+88h], edx
0x18000b31a  mov     eax, [rbp+88h]
0x18000b320  cmp     eax, 0E06D7363h
0x18000b325  jnz     short loc_18000B341
0x18000b327  mov     rdx, [rbp+0D8h]
0x18000b32e  mov     ecx, [rbp+88h]
0x18000b334  call    _XcptFilter_0
0x18000b339  mov     [rbp+90h], eax
0x18000b33f  jmp     short loc_18000B34B
0x18000b341  mov     dword ptr [rbp+90h], 0
0x18000b34b  mov     eax, [rbp+90h]
0x18000b351  add     rsp, 20h
0x18000b355  pop     rbp
0x18000b356  retn
0x18000b358  push    rbp
0x18000b35a  sub     rsp, 20h
0x18000b35e  mov     rbp, rdx
0x18000b361  mov     rax, [rcx]
0x18000b364  mov     edx, [rax]
0x18000b366  mov     [rbp+0E0h], rcx
0x18000b36d  mov     [rbp+98h], edx
0x18000b373  mov     eax, [rbp+98h]
0x18000b379  cmp     eax, 0E06D7363h
0x18000b37e  jnz     short loc_18000B39A
0x18000b380  mov     rdx, [rbp+0E0h]
0x18000b387  mov     ecx, [rbp+98h]
0x18000b38d  call    _XcptFilter_0
0x18000b392  mov     [rbp+0A0h], eax
0x18000b398  jmp     short loc_18000B3A4
0x18000b39a  mov     dword ptr [rbp+0A0h], 0
0x18000b3a4  mov     eax, [rbp+0A0h]
0x18000b3aa  add     rsp, 20h
0x18000b3ae  pop     rbp
0x18000b3af  retn
0x18000b3b1  push    rbp
0x18000b3b3  sub     rsp, 20h
0x18000b3b7  mov     rbp, rdx
0x18000b3ba  cmp     dword ptr [rbp+118h], 1
0x18000b3c1  ja      short loc_18000B3CD
0x18000b3c3  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

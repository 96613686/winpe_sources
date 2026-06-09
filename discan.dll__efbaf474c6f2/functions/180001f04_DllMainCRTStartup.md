# __DllMainCRTStartup

- ea: `0x180001f04`
- end: `0x180002110`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001ec0`

## callees

- `0x180001c90`
- `0x180001f04`
- `0x18000270a`
- `0x180007910`
- `0x180037690`

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
  if ( (_DWORD)fdwReason || dword_180047B40 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180047B44 = 1;
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
            if ( dword_180047B44 )
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
0x180001f04  mov     [rsp+lpvReserved], r8
0x180001f09  mov     [rsp+arg_8], edx
0x180001f0d  mov     [rsp+arg_0], rcx
0x180001f12  push    rbx
0x180001f13  push    rsi
0x180001f14  push    rdi
0x180001f15  sub     rsp, 0F0h
0x180001f1c  mov     edi, edx
0x180001f1e  mov     rsi, rcx
0x180001f21  mov     ebx, 1
0x180001f26  cmp     edx, ebx
0x180001f28  ja      short loc_180001F30
0x180001f2a  mov     cs:__native_dllmain_reason, edx
0x180001f30  test    edx, edx
0x180001f32  jnz     short loc_180001F47
0x180001f34  cmp     cs:dword_180047B40, edx
0x180001f3a  jnz     short loc_180001F47
0x180001f3c  xor     ebx, ebx
0x180001f3e  mov     [rsp+108h+var_E8], ebx
0x180001f42  jmp     loc_1800020F4
0x180001f47  lea     eax, [rdx-1]
0x180001f4a  cmp     eax, 1
0x180001f4d  ja      loc_180001FD4
0x180001f53  mov     rax, cs:_pRawDllMain
0x180001f5a  test    rax, rax
0x180001f5d  jz      short loc_180001F95
0x180001f5f  cmp     edx, 1
0x180001f62  jnz     short loc_180001F6A
0x180001f64  mov     cs:dword_180047B44, edx
0x180001f6a  mov     r8, [rsp+108h+lpvReserved]
0x180001f72  call    cs:__guard_dispatch_icall_fptr
0x180001f78  mov     ebx, eax
0x180001f7a  mov     [rsp+108h+var_E8], eax
0x180001f7e  jmp     short loc_180001F95
0x180001f80  xor     ebx, ebx
0x180001f82  mov     [rsp+108h+var_E8], ebx
0x180001f86  mov     edi, [rsp+108h+arg_8]
0x180001f8d  mov     rsi, [rsp+108h+arg_0]
0x180001f95  test    ebx, ebx
0x180001f97  jz      loc_1800020F4
0x180001f9d  mov     r8, [rsp+108h+lpvReserved]
0x180001fa5  mov     edx, edi
0x180001fa7  mov     rcx, rsi
0x180001faa  call    _CRT_INIT
0x180001faf  mov     ebx, eax
0x180001fb1  mov     [rsp+108h+var_E8], eax
0x180001fb5  jmp     short loc_180001FCC
0x180001fb7  xor     ebx, ebx
0x180001fb9  mov     [rsp+108h+var_E8], ebx
0x180001fbd  mov     edi, [rsp+108h+arg_8]
0x180001fc4  mov     rsi, [rsp+108h+arg_0]
0x180001fcc  test    ebx, ebx
0x180001fce  jz      loc_1800020F4
0x180001fd4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001fdc  mov     edx, edi; fdwReason
0x180001fde  mov     rcx, rsi; hinstDLL
0x180001fe1  call    DllMain
0x180001fe6  mov     ebx, eax
0x180001fe8  mov     [rsp+108h+var_E8], eax
0x180001fec  jmp     short loc_180002003
0x180001fee  xor     ebx, ebx
0x180001ff0  mov     [rsp+108h+var_E8], ebx
0x180001ff4  mov     edi, [rsp+108h+arg_8]
0x180001ffb  mov     rsi, [rsp+108h+arg_0]
0x180002003  cmp     edi, 1
0x180002006  jnz     short loc_18000207F
0x180002008  test    ebx, ebx
0x18000200a  jnz     short loc_18000207F
0x18000200c  xor     r8d, r8d; lpvReserved
0x18000200f  xor     edx, edx; fdwReason
0x180002011  mov     rcx, rsi; hinstDLL
0x180002014  call    DllMain
0x180002019  jmp     short loc_18000202E
0x18000201b  mov     edi, [rsp+108h+arg_8]
0x180002022  mov     rsi, [rsp+108h+arg_0]
0x18000202a  mov     ebx, [rsp+108h+var_E8]
0x18000202e  xor     r8d, r8d
0x180002031  xor     edx, edx
0x180002033  mov     rcx, rsi
0x180002036  call    _CRT_INIT
0x18000203b  jmp     short loc_180002050
0x18000203d  mov     edi, [rsp+108h+arg_8]
0x180002044  mov     rsi, [rsp+108h+arg_0]
0x18000204c  mov     ebx, [rsp+108h+var_E8]
0x180002050  mov     rax, cs:_pRawDllMain
0x180002057  test    rax, rax
0x18000205a  jz      short loc_18000207F
0x18000205c  xor     r8d, r8d
0x18000205f  xor     edx, edx
0x180002061  mov     rcx, rsi
0x180002064  call    cs:__guard_dispatch_icall_fptr
0x18000206a  jmp     short loc_18000207F
0x18000206c  mov     edi, [rsp+108h+arg_8]
0x180002073  mov     rsi, [rsp+108h+arg_0]
0x18000207b  mov     ebx, [rsp+108h+var_E8]
0x18000207f  test    edi, edi
0x180002081  jz      short loc_180002088
0x180002083  cmp     edi, 3
0x180002086  jnz     short loc_1800020F4
0x180002088  mov     r8, [rsp+108h+lpvReserved]
0x180002090  mov     edx, edi
0x180002092  mov     rcx, rsi
0x180002095  call    _CRT_INIT
0x18000209a  mov     ebx, eax
0x18000209c  mov     [rsp+108h+var_E8], eax
0x1800020a0  jmp     short loc_1800020B7
0x1800020a2  xor     ebx, ebx
0x1800020a4  mov     [rsp+108h+var_E8], ebx
0x1800020a8  mov     edi, [rsp+108h+arg_8]
0x1800020af  mov     rsi, [rsp+108h+arg_0]
0x1800020b7  mov     rax, cs:_pRawDllMain
0x1800020be  test    rax, rax
0x1800020c1  jz      short loc_1800020F4
0x1800020c3  cmp     cs:dword_180047B44, 0
0x1800020ca  jz      short loc_1800020F4
0x1800020cc  mov     r8, [rsp+108h+lpvReserved]
0x1800020d4  mov     edx, edi
0x1800020d6  mov     rcx, rsi
0x1800020d9  call    cs:__guard_dispatch_icall_fptr
0x1800020df  mov     ebx, eax
0x1800020e1  mov     [rsp+108h+var_E8], eax
0x1800020e5  jmp     short loc_1800020F4
0x1800020e7  xor     ebx, ebx
0x1800020e9  mov     [rsp+108h+var_E8], ebx
0x1800020ed  mov     edi, [rsp+108h+arg_8]
0x1800020f4  cmp     edi, 1
0x1800020f7  ja      short loc_180002103
0x1800020f9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002103  mov     eax, ebx
0x180002105  add     rsp, 0F0h
0x18000210c  pop     rdi
0x18000210d  pop     rsi
0x18000210e  pop     rbx
0x18000210f  retn
0x180037733  push    rbp
0x180037735  sub     rsp, 20h
0x180037739  mov     rbp, rdx
0x18003773c  mov     rax, [rcx]
0x18003773f  mov     edx, [rax]
0x180037741  mov     [rbp+0A8h], rcx
0x180037748  mov     [rbp+28h], edx
0x18003774b  mov     eax, [rbp+28h]
0x18003774e  cmp     eax, 0E06D7363h
0x180037753  jnz     short loc_180037769
0x180037755  mov     rdx, [rbp+0A8h]
0x18003775c  mov     ecx, [rbp+28h]
0x18003775f  call    _XcptFilter_0
0x180037764  mov     [rbp+30h], eax
0x180037767  jmp     short loc_180037770
0x180037769  mov     dword ptr [rbp+30h], 0
0x180037770  mov     eax, [rbp+30h]
0x180037773  add     rsp, 20h
0x180037777  pop     rbp
0x180037778  retn
0x18003777a  push    rbp
0x18003777c  sub     rsp, 20h
0x180037780  mov     rbp, rdx
0x180037783  mov     rax, [rcx]
0x180037786  mov     edx, [rax]
0x180037788  mov     [rbp+0B0h], rcx
0x18003778f  mov     [rbp+38h], edx
0x180037792  mov     eax, [rbp+38h]
0x180037795  cmp     eax, 0E06D7363h
0x18003779a  jnz     short loc_1800377B0
0x18003779c  mov     rdx, [rbp+0B0h]
0x1800377a3  mov     ecx, [rbp+38h]
0x1800377a6  call    _XcptFilter_0
0x1800377ab  mov     [rbp+40h], eax
0x1800377ae  jmp     short loc_1800377B7
0x1800377b0  mov     dword ptr [rbp+40h], 0
0x1800377b7  mov     eax, [rbp+40h]
0x1800377ba  add     rsp, 20h
0x1800377be  pop     rbp
0x1800377bf  retn
0x1800377c1  push    rbp
0x1800377c3  sub     rsp, 20h
0x1800377c7  mov     rbp, rdx
0x1800377ca  mov     rax, [rcx]
0x1800377cd  mov     edx, [rax]
0x1800377cf  mov     [rbp+0B8h], rcx
0x1800377d6  mov     [rbp+48h], edx
0x1800377d9  mov     eax, [rbp+48h]
0x1800377dc  cmp     eax, 0E06D7363h
0x1800377e1  jnz     short loc_1800377F7
0x1800377e3  mov     rdx, [rbp+0B8h]
0x1800377ea  mov     ecx, [rbp+48h]
0x1800377ed  call    _XcptFilter_0
0x1800377f2  mov     [rbp+50h], eax
0x1800377f5  jmp     short loc_1800377FE
0x1800377f7  mov     dword ptr [rbp+50h], 0
0x1800377fe  mov     eax, [rbp+50h]
0x180037801  add     rsp, 20h
0x180037805  pop     rbp
0x180037806  retn
0x180037808  push    rbp
0x18003780a  sub     rsp, 20h
0x18003780e  mov     rbp, rdx
0x180037811  mov     rax, [rcx]
0x180037814  mov     edx, [rax]
0x180037816  mov     [rbp+0C0h], rcx
0x18003781d  mov     [rbp+58h], edx
0x180037820  mov     eax, [rbp+58h]
0x180037823  cmp     eax, 0E06D7363h
0x180037828  jnz     short loc_18003783E
0x18003782a  mov     rdx, [rbp+0C0h]
0x180037831  mov     ecx, [rbp+58h]
0x180037834  call    _XcptFilter_0
0x180037839  mov     [rbp+60h], eax
0x18003783c  jmp     short loc_180037845
0x18003783e  mov     dword ptr [rbp+60h], 0
0x180037845  mov     eax, [rbp+60h]
0x180037848  add     rsp, 20h
0x18003784c  pop     rbp
0x18003784d  retn
0x18003784f  push    rbp
0x180037851  sub     rsp, 20h
0x180037855  mov     rbp, rdx
0x180037858  mov     rax, [rcx]
0x18003785b  mov     edx, [rax]
0x18003785d  mov     [rbp+0C8h], rcx
0x180037864  mov     [rbp+68h], edx
0x180037867  mov     eax, [rbp+68h]
0x18003786a  cmp     eax, 0E06D7363h
0x18003786f  jnz     short loc_180037885
0x180037871  mov     rdx, [rbp+0C8h]
0x180037878  mov     ecx, [rbp+68h]
0x18003787b  call    _XcptFilter_0
0x180037880  mov     [rbp+70h], eax
0x180037883  jmp     short loc_18003788C
0x180037885  mov     dword ptr [rbp+70h], 0
0x18003788c  mov     eax, [rbp+70h]
0x18003788f  add     rsp, 20h
0x180037893  pop     rbp
0x180037894  retn
0x180037896  push    rbp
0x180037898  sub     rsp, 20h
0x18003789c  mov     rbp, rdx
0x18003789f  mov     rax, [rcx]
0x1800378a2  mov     edx, [rax]
0x1800378a4  mov     [rbp+0D0h], rcx
0x1800378ab  mov     [rbp+78h], edx
0x1800378ae  mov     eax, [rbp+78h]
0x1800378b1  cmp     eax, 0E06D7363h
0x1800378b6  jnz     short loc_1800378CF
0x1800378b8  mov     rdx, [rbp+0D0h]
0x1800378bf  mov     ecx, [rbp+78h]
0x1800378c2  call    _XcptFilter_0
0x1800378c7  mov     [rbp+80h], eax
0x1800378cd  jmp     short loc_1800378D9
0x1800378cf  mov     dword ptr [rbp+80h], 0
0x1800378d9  mov     eax, [rbp+80h]
0x1800378df  add     rsp, 20h
0x1800378e3  pop     rbp
0x1800378e4  retn
0x1800378e6  push    rbp
0x1800378e8  sub     rsp, 20h
0x1800378ec  mov     rbp, rdx
0x1800378ef  mov     rax, [rcx]
0x1800378f2  mov     edx, [rax]
0x1800378f4  mov     [rbp+0D8h], rcx
0x1800378fb  mov     [rbp+88h], edx
0x180037901  mov     eax, [rbp+88h]
0x180037907  cmp     eax, 0E06D7363h
0x18003790c  jnz     short loc_180037928
0x18003790e  mov     rdx, [rbp+0D8h]
0x180037915  mov     ecx, [rbp+88h]
0x18003791b  call    _XcptFilter_0
0x180037920  mov     [rbp+90h], eax
0x180037926  jmp     short loc_180037932
0x180037928  mov     dword ptr [rbp+90h], 0
0x180037932  mov     eax, [rbp+90h]
0x180037938  add     rsp, 20h
0x18003793c  pop     rbp
0x18003793d  retn
0x18003793f  push    rbp
0x180037941  sub     rsp, 20h
0x180037945  mov     rbp, rdx
0x180037948  mov     rax, [rcx]
0x18003794b  mov     edx, [rax]
0x18003794d  mov     [rbp+0E0h], rcx
0x180037954  mov     [rbp+98h], edx
0x18003795a  mov     eax, [rbp+98h]
0x180037960  cmp     eax, 0E06D7363h
0x180037965  jnz     short loc_180037981
0x180037967  mov     rdx, [rbp+0E0h]
0x18003796e  mov     ecx, [rbp+98h]
0x180037974  call    _XcptFilter_0
0x180037979  mov     [rbp+0A0h], eax
0x18003797f  jmp     short loc_18003798B
0x180037981  mov     dword ptr [rbp+0A0h], 0
0x18003798b  mov     eax, [rbp+0A0h]
0x180037991  add     rsp, 20h
0x180037995  pop     rbp
0x180037996  retn
0x180037998  push    rbp
0x18003799a  sub     rsp, 20h
0x18003799e  mov     rbp, rdx
0x1800379a1  cmp     dword ptr [rbp+118h], 1
0x1800379a8  ja      short loc_1800379B4
0x1800379aa  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

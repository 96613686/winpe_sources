# __DllMainCRTStartup

- ea: `0x180006784`
- end: `0x180006990`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180006740`

## callees

- `0x180005660`
- `0x180006510`
- `0x180006784`
- `0x180006b86`
- `0x18000a840`

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
  if ( (_DWORD)fdwReason || dword_180012160 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180012164 = 1;
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
            if ( dword_180012164 )
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
0x180006784  mov     [rsp+lpvReserved], r8
0x180006789  mov     [rsp+arg_8], edx
0x18000678d  mov     [rsp+arg_0], rcx
0x180006792  push    rbx
0x180006793  push    rsi
0x180006794  push    rdi
0x180006795  sub     rsp, 0F0h
0x18000679c  mov     edi, edx
0x18000679e  mov     rsi, rcx
0x1800067a1  mov     ebx, 1
0x1800067a6  cmp     edx, ebx
0x1800067a8  ja      short loc_1800067B0
0x1800067aa  mov     cs:__native_dllmain_reason, edx
0x1800067b0  test    edx, edx
0x1800067b2  jnz     short loc_1800067C7
0x1800067b4  cmp     cs:dword_180012160, edx
0x1800067ba  jnz     short loc_1800067C7
0x1800067bc  xor     ebx, ebx
0x1800067be  mov     [rsp+108h+var_E8], ebx
0x1800067c2  jmp     loc_180006974
0x1800067c7  lea     eax, [rdx-1]
0x1800067ca  cmp     eax, 1
0x1800067cd  ja      loc_180006854
0x1800067d3  mov     rax, cs:_pRawDllMain
0x1800067da  test    rax, rax
0x1800067dd  jz      short loc_180006815
0x1800067df  cmp     edx, 1
0x1800067e2  jnz     short loc_1800067EA
0x1800067e4  mov     cs:dword_180012164, edx
0x1800067ea  mov     r8, [rsp+108h+lpvReserved]
0x1800067f2  call    cs:__guard_dispatch_icall_fptr
0x1800067f8  mov     ebx, eax
0x1800067fa  mov     [rsp+108h+var_E8], eax
0x1800067fe  jmp     short loc_180006815
0x180006800  xor     ebx, ebx
0x180006802  mov     [rsp+108h+var_E8], ebx
0x180006806  mov     edi, [rsp+108h+arg_8]
0x18000680d  mov     rsi, [rsp+108h+arg_0]
0x180006815  test    ebx, ebx
0x180006817  jz      loc_180006974
0x18000681d  mov     r8, [rsp+108h+lpvReserved]
0x180006825  mov     edx, edi
0x180006827  mov     rcx, rsi
0x18000682a  call    _CRT_INIT
0x18000682f  mov     ebx, eax
0x180006831  mov     [rsp+108h+var_E8], eax
0x180006835  jmp     short loc_18000684C
0x180006837  xor     ebx, ebx
0x180006839  mov     [rsp+108h+var_E8], ebx
0x18000683d  mov     edi, [rsp+108h+arg_8]
0x180006844  mov     rsi, [rsp+108h+arg_0]
0x18000684c  test    ebx, ebx
0x18000684e  jz      loc_180006974
0x180006854  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000685c  mov     edx, edi; fdwReason
0x18000685e  mov     rcx, rsi; hinstDLL
0x180006861  call    DllMain
0x180006866  mov     ebx, eax
0x180006868  mov     [rsp+108h+var_E8], eax
0x18000686c  jmp     short loc_180006883
0x18000686e  xor     ebx, ebx
0x180006870  mov     [rsp+108h+var_E8], ebx
0x180006874  mov     edi, [rsp+108h+arg_8]
0x18000687b  mov     rsi, [rsp+108h+arg_0]
0x180006883  cmp     edi, 1
0x180006886  jnz     short loc_1800068FF
0x180006888  test    ebx, ebx
0x18000688a  jnz     short loc_1800068FF
0x18000688c  xor     r8d, r8d; lpvReserved
0x18000688f  xor     edx, edx; fdwReason
0x180006891  mov     rcx, rsi; hinstDLL
0x180006894  call    DllMain
0x180006899  jmp     short loc_1800068AE
0x18000689b  mov     edi, [rsp+108h+arg_8]
0x1800068a2  mov     rsi, [rsp+108h+arg_0]
0x1800068aa  mov     ebx, [rsp+108h+var_E8]
0x1800068ae  xor     r8d, r8d
0x1800068b1  xor     edx, edx
0x1800068b3  mov     rcx, rsi
0x1800068b6  call    _CRT_INIT
0x1800068bb  jmp     short loc_1800068D0
0x1800068bd  mov     edi, [rsp+108h+arg_8]
0x1800068c4  mov     rsi, [rsp+108h+arg_0]
0x1800068cc  mov     ebx, [rsp+108h+var_E8]
0x1800068d0  mov     rax, cs:_pRawDllMain
0x1800068d7  test    rax, rax
0x1800068da  jz      short loc_1800068FF
0x1800068dc  xor     r8d, r8d
0x1800068df  xor     edx, edx
0x1800068e1  mov     rcx, rsi
0x1800068e4  call    cs:__guard_dispatch_icall_fptr
0x1800068ea  jmp     short loc_1800068FF
0x1800068ec  mov     edi, [rsp+108h+arg_8]
0x1800068f3  mov     rsi, [rsp+108h+arg_0]
0x1800068fb  mov     ebx, [rsp+108h+var_E8]
0x1800068ff  test    edi, edi
0x180006901  jz      short loc_180006908
0x180006903  cmp     edi, 3
0x180006906  jnz     short loc_180006974
0x180006908  mov     r8, [rsp+108h+lpvReserved]
0x180006910  mov     edx, edi
0x180006912  mov     rcx, rsi
0x180006915  call    _CRT_INIT
0x18000691a  mov     ebx, eax
0x18000691c  mov     [rsp+108h+var_E8], eax
0x180006920  jmp     short loc_180006937
0x180006922  xor     ebx, ebx
0x180006924  mov     [rsp+108h+var_E8], ebx
0x180006928  mov     edi, [rsp+108h+arg_8]
0x18000692f  mov     rsi, [rsp+108h+arg_0]
0x180006937  mov     rax, cs:_pRawDllMain
0x18000693e  test    rax, rax
0x180006941  jz      short loc_180006974
0x180006943  cmp     cs:dword_180012164, 0
0x18000694a  jz      short loc_180006974
0x18000694c  mov     r8, [rsp+108h+lpvReserved]
0x180006954  mov     edx, edi
0x180006956  mov     rcx, rsi
0x180006959  call    cs:__guard_dispatch_icall_fptr
0x18000695f  mov     ebx, eax
0x180006961  mov     [rsp+108h+var_E8], eax
0x180006965  jmp     short loc_180006974
0x180006967  xor     ebx, ebx
0x180006969  mov     [rsp+108h+var_E8], ebx
0x18000696d  mov     edi, [rsp+108h+arg_8]
0x180006974  cmp     edi, 1
0x180006977  ja      short loc_180006983
0x180006979  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180006983  mov     eax, ebx
0x180006985  add     rsp, 0F0h
0x18000698c  pop     rdi
0x18000698d  pop     rsi
0x18000698e  pop     rbx
0x18000698f  retn
0x18000a910  push    rbp
0x18000a912  sub     rsp, 20h
0x18000a916  mov     rbp, rdx
0x18000a919  mov     rax, [rcx]
0x18000a91c  mov     edx, [rax]
0x18000a91e  mov     [rbp+0A8h], rcx
0x18000a925  mov     [rbp+28h], edx
0x18000a928  mov     eax, [rbp+28h]
0x18000a92b  cmp     eax, 0E06D7363h
0x18000a930  jnz     short loc_18000A946
0x18000a932  mov     rdx, [rbp+0A8h]
0x18000a939  mov     ecx, [rbp+28h]
0x18000a93c  call    _XcptFilter_0
0x18000a941  mov     [rbp+30h], eax
0x18000a944  jmp     short loc_18000A94D
0x18000a946  mov     dword ptr [rbp+30h], 0
0x18000a94d  mov     eax, [rbp+30h]
0x18000a950  add     rsp, 20h
0x18000a954  pop     rbp
0x18000a955  retn
0x18000a957  push    rbp
0x18000a959  sub     rsp, 20h
0x18000a95d  mov     rbp, rdx
0x18000a960  mov     rax, [rcx]
0x18000a963  mov     edx, [rax]
0x18000a965  mov     [rbp+0B0h], rcx
0x18000a96c  mov     [rbp+38h], edx
0x18000a96f  mov     eax, [rbp+38h]
0x18000a972  cmp     eax, 0E06D7363h
0x18000a977  jnz     short loc_18000A98D
0x18000a979  mov     rdx, [rbp+0B0h]
0x18000a980  mov     ecx, [rbp+38h]
0x18000a983  call    _XcptFilter_0
0x18000a988  mov     [rbp+40h], eax
0x18000a98b  jmp     short loc_18000A994
0x18000a98d  mov     dword ptr [rbp+40h], 0
0x18000a994  mov     eax, [rbp+40h]
0x18000a997  add     rsp, 20h
0x18000a99b  pop     rbp
0x18000a99c  retn
0x18000a99e  push    rbp
0x18000a9a0  sub     rsp, 20h
0x18000a9a4  mov     rbp, rdx
0x18000a9a7  mov     rax, [rcx]
0x18000a9aa  mov     edx, [rax]
0x18000a9ac  mov     [rbp+0B8h], rcx
0x18000a9b3  mov     [rbp+48h], edx
0x18000a9b6  mov     eax, [rbp+48h]
0x18000a9b9  cmp     eax, 0E06D7363h
0x18000a9be  jnz     short loc_18000A9D4
0x18000a9c0  mov     rdx, [rbp+0B8h]
0x18000a9c7  mov     ecx, [rbp+48h]
0x18000a9ca  call    _XcptFilter_0
0x18000a9cf  mov     [rbp+50h], eax
0x18000a9d2  jmp     short loc_18000A9DB
0x18000a9d4  mov     dword ptr [rbp+50h], 0
0x18000a9db  mov     eax, [rbp+50h]
0x18000a9de  add     rsp, 20h
0x18000a9e2  pop     rbp
0x18000a9e3  retn
0x18000a9e5  push    rbp
0x18000a9e7  sub     rsp, 20h
0x18000a9eb  mov     rbp, rdx
0x18000a9ee  mov     rax, [rcx]
0x18000a9f1  mov     edx, [rax]
0x18000a9f3  mov     [rbp+0C0h], rcx
0x18000a9fa  mov     [rbp+58h], edx
0x18000a9fd  mov     eax, [rbp+58h]
0x18000aa00  cmp     eax, 0E06D7363h
0x18000aa05  jnz     short loc_18000AA1B
0x18000aa07  mov     rdx, [rbp+0C0h]
0x18000aa0e  mov     ecx, [rbp+58h]
0x18000aa11  call    _XcptFilter_0
0x18000aa16  mov     [rbp+60h], eax
0x18000aa19  jmp     short loc_18000AA22
0x18000aa1b  mov     dword ptr [rbp+60h], 0
0x18000aa22  mov     eax, [rbp+60h]
0x18000aa25  add     rsp, 20h
0x18000aa29  pop     rbp
0x18000aa2a  retn
0x18000aa2c  push    rbp
0x18000aa2e  sub     rsp, 20h
0x18000aa32  mov     rbp, rdx
0x18000aa35  mov     rax, [rcx]
0x18000aa38  mov     edx, [rax]
0x18000aa3a  mov     [rbp+0C8h], rcx
0x18000aa41  mov     [rbp+68h], edx
0x18000aa44  mov     eax, [rbp+68h]
0x18000aa47  cmp     eax, 0E06D7363h
0x18000aa4c  jnz     short loc_18000AA62
0x18000aa4e  mov     rdx, [rbp+0C8h]
0x18000aa55  mov     ecx, [rbp+68h]
0x18000aa58  call    _XcptFilter_0
0x18000aa5d  mov     [rbp+70h], eax
0x18000aa60  jmp     short loc_18000AA69
0x18000aa62  mov     dword ptr [rbp+70h], 0
0x18000aa69  mov     eax, [rbp+70h]
0x18000aa6c  add     rsp, 20h
0x18000aa70  pop     rbp
0x18000aa71  retn
0x18000aa73  push    rbp
0x18000aa75  sub     rsp, 20h
0x18000aa79  mov     rbp, rdx
0x18000aa7c  mov     rax, [rcx]
0x18000aa7f  mov     edx, [rax]
0x18000aa81  mov     [rbp+0D0h], rcx
0x18000aa88  mov     [rbp+78h], edx
0x18000aa8b  mov     eax, [rbp+78h]
0x18000aa8e  cmp     eax, 0E06D7363h
0x18000aa93  jnz     short loc_18000AAAC
0x18000aa95  mov     rdx, [rbp+0D0h]
0x18000aa9c  mov     ecx, [rbp+78h]
0x18000aa9f  call    _XcptFilter_0
0x18000aaa4  mov     [rbp+80h], eax
0x18000aaaa  jmp     short loc_18000AAB6
0x18000aaac  mov     dword ptr [rbp+80h], 0
0x18000aab6  mov     eax, [rbp+80h]
0x18000aabc  add     rsp, 20h
0x18000aac0  pop     rbp
0x18000aac1  retn
0x18000aac3  push    rbp
0x18000aac5  sub     rsp, 20h
0x18000aac9  mov     rbp, rdx
0x18000aacc  mov     rax, [rcx]
0x18000aacf  mov     edx, [rax]
0x18000aad1  mov     [rbp+0D8h], rcx
0x18000aad8  mov     [rbp+88h], edx
0x18000aade  mov     eax, [rbp+88h]
0x18000aae4  cmp     eax, 0E06D7363h
0x18000aae9  jnz     short loc_18000AB05
0x18000aaeb  mov     rdx, [rbp+0D8h]
0x18000aaf2  mov     ecx, [rbp+88h]
0x18000aaf8  call    _XcptFilter_0
0x18000aafd  mov     [rbp+90h], eax
0x18000ab03  jmp     short loc_18000AB0F
0x18000ab05  mov     dword ptr [rbp+90h], 0
0x18000ab0f  mov     eax, [rbp+90h]
0x18000ab15  add     rsp, 20h
0x18000ab19  pop     rbp
0x18000ab1a  retn
0x18000ab1c  push    rbp
0x18000ab1e  sub     rsp, 20h
0x18000ab22  mov     rbp, rdx
0x18000ab25  mov     rax, [rcx]
0x18000ab28  mov     edx, [rax]
0x18000ab2a  mov     [rbp+0E0h], rcx
0x18000ab31  mov     [rbp+98h], edx
0x18000ab37  mov     eax, [rbp+98h]
0x18000ab3d  cmp     eax, 0E06D7363h
0x18000ab42  jnz     short loc_18000AB5E
0x18000ab44  mov     rdx, [rbp+0E0h]
0x18000ab4b  mov     ecx, [rbp+98h]
0x18000ab51  call    _XcptFilter_0
0x18000ab56  mov     [rbp+0A0h], eax
0x18000ab5c  jmp     short loc_18000AB68
0x18000ab5e  mov     dword ptr [rbp+0A0h], 0
0x18000ab68  mov     eax, [rbp+0A0h]
0x18000ab6e  add     rsp, 20h
0x18000ab72  pop     rbp
0x18000ab73  retn
0x18000ab75  push    rbp
0x18000ab77  sub     rsp, 20h
0x18000ab7b  mov     rbp, rdx
0x18000ab7e  cmp     dword ptr [rbp+118h], 1
0x18000ab85  ja      short loc_18000AB91
0x18000ab87  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

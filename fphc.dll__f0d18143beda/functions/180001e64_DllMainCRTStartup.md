# __DllMainCRTStartup

- ea: `0x180001e64`
- end: `0x180002070`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001e20`

## callees

- `0x180001bf0`
- `0x180001e64`
- `0x1800026fe`
- `0x180005aac`
- `0x1800113b0`

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
  if ( (_DWORD)fdwReason || dword_18001C98C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001C990 = 1;
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
            if ( dword_18001C990 )
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
0x180001e64  mov     [rsp+lpvReserved], r8
0x180001e69  mov     [rsp+arg_8], edx
0x180001e6d  mov     [rsp+arg_0], rcx
0x180001e72  push    rbx
0x180001e73  push    rsi
0x180001e74  push    rdi
0x180001e75  sub     rsp, 0F0h
0x180001e7c  mov     edi, edx
0x180001e7e  mov     rsi, rcx
0x180001e81  mov     ebx, 1
0x180001e86  cmp     edx, ebx
0x180001e88  ja      short loc_180001E90
0x180001e8a  mov     cs:__native_dllmain_reason, edx
0x180001e90  test    edx, edx
0x180001e92  jnz     short loc_180001EA7
0x180001e94  cmp     cs:dword_18001C98C, edx
0x180001e9a  jnz     short loc_180001EA7
0x180001e9c  xor     ebx, ebx
0x180001e9e  mov     [rsp+108h+var_E8], ebx
0x180001ea2  jmp     loc_180002054
0x180001ea7  lea     eax, [rdx-1]
0x180001eaa  cmp     eax, 1
0x180001ead  ja      loc_180001F34
0x180001eb3  mov     rax, cs:_pRawDllMain
0x180001eba  test    rax, rax
0x180001ebd  jz      short loc_180001EF5
0x180001ebf  cmp     edx, 1
0x180001ec2  jnz     short loc_180001ECA
0x180001ec4  mov     cs:dword_18001C990, edx
0x180001eca  mov     r8, [rsp+108h+lpvReserved]
0x180001ed2  call    cs:__guard_dispatch_icall_fptr
0x180001ed8  mov     ebx, eax
0x180001eda  mov     [rsp+108h+var_E8], eax
0x180001ede  jmp     short loc_180001EF5
0x180001ee0  xor     ebx, ebx
0x180001ee2  mov     [rsp+108h+var_E8], ebx
0x180001ee6  mov     edi, [rsp+108h+arg_8]
0x180001eed  mov     rsi, [rsp+108h+arg_0]
0x180001ef5  test    ebx, ebx
0x180001ef7  jz      loc_180002054
0x180001efd  mov     r8, [rsp+108h+lpvReserved]
0x180001f05  mov     edx, edi
0x180001f07  mov     rcx, rsi
0x180001f0a  call    _CRT_INIT
0x180001f0f  mov     ebx, eax
0x180001f11  mov     [rsp+108h+var_E8], eax
0x180001f15  jmp     short loc_180001F2C
0x180001f17  xor     ebx, ebx
0x180001f19  mov     [rsp+108h+var_E8], ebx
0x180001f1d  mov     edi, [rsp+108h+arg_8]
0x180001f24  mov     rsi, [rsp+108h+arg_0]
0x180001f2c  test    ebx, ebx
0x180001f2e  jz      loc_180002054
0x180001f34  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001f3c  mov     edx, edi; fdwReason
0x180001f3e  mov     rcx, rsi; hinstDLL
0x180001f41  call    DllMain
0x180001f46  mov     ebx, eax
0x180001f48  mov     [rsp+108h+var_E8], eax
0x180001f4c  jmp     short loc_180001F63
0x180001f4e  xor     ebx, ebx
0x180001f50  mov     [rsp+108h+var_E8], ebx
0x180001f54  mov     edi, [rsp+108h+arg_8]
0x180001f5b  mov     rsi, [rsp+108h+arg_0]
0x180001f63  cmp     edi, 1
0x180001f66  jnz     short loc_180001FDF
0x180001f68  test    ebx, ebx
0x180001f6a  jnz     short loc_180001FDF
0x180001f6c  xor     r8d, r8d; lpvReserved
0x180001f6f  xor     edx, edx; fdwReason
0x180001f71  mov     rcx, rsi; hinstDLL
0x180001f74  call    DllMain
0x180001f79  jmp     short loc_180001F8E
0x180001f7b  mov     edi, [rsp+108h+arg_8]
0x180001f82  mov     rsi, [rsp+108h+arg_0]
0x180001f8a  mov     ebx, [rsp+108h+var_E8]
0x180001f8e  xor     r8d, r8d
0x180001f91  xor     edx, edx
0x180001f93  mov     rcx, rsi
0x180001f96  call    _CRT_INIT
0x180001f9b  jmp     short loc_180001FB0
0x180001f9d  mov     edi, [rsp+108h+arg_8]
0x180001fa4  mov     rsi, [rsp+108h+arg_0]
0x180001fac  mov     ebx, [rsp+108h+var_E8]
0x180001fb0  mov     rax, cs:_pRawDllMain
0x180001fb7  test    rax, rax
0x180001fba  jz      short loc_180001FDF
0x180001fbc  xor     r8d, r8d
0x180001fbf  xor     edx, edx
0x180001fc1  mov     rcx, rsi
0x180001fc4  call    cs:__guard_dispatch_icall_fptr
0x180001fca  jmp     short loc_180001FDF
0x180001fcc  mov     edi, [rsp+108h+arg_8]
0x180001fd3  mov     rsi, [rsp+108h+arg_0]
0x180001fdb  mov     ebx, [rsp+108h+var_E8]
0x180001fdf  test    edi, edi
0x180001fe1  jz      short loc_180001FE8
0x180001fe3  cmp     edi, 3
0x180001fe6  jnz     short loc_180002054
0x180001fe8  mov     r8, [rsp+108h+lpvReserved]
0x180001ff0  mov     edx, edi
0x180001ff2  mov     rcx, rsi
0x180001ff5  call    _CRT_INIT
0x180001ffa  mov     ebx, eax
0x180001ffc  mov     [rsp+108h+var_E8], eax
0x180002000  jmp     short loc_180002017
0x180002002  xor     ebx, ebx
0x180002004  mov     [rsp+108h+var_E8], ebx
0x180002008  mov     edi, [rsp+108h+arg_8]
0x18000200f  mov     rsi, [rsp+108h+arg_0]
0x180002017  mov     rax, cs:_pRawDllMain
0x18000201e  test    rax, rax
0x180002021  jz      short loc_180002054
0x180002023  cmp     cs:dword_18001C990, 0
0x18000202a  jz      short loc_180002054
0x18000202c  mov     r8, [rsp+108h+lpvReserved]
0x180002034  mov     edx, edi
0x180002036  mov     rcx, rsi
0x180002039  call    cs:__guard_dispatch_icall_fptr
0x18000203f  mov     ebx, eax
0x180002041  mov     [rsp+108h+var_E8], eax
0x180002045  jmp     short loc_180002054
0x180002047  xor     ebx, ebx
0x180002049  mov     [rsp+108h+var_E8], ebx
0x18000204d  mov     edi, [rsp+108h+arg_8]
0x180002054  cmp     edi, 1
0x180002057  ja      short loc_180002063
0x180002059  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002063  mov     eax, ebx
0x180002065  add     rsp, 0F0h
0x18000206c  pop     rdi
0x18000206d  pop     rsi
0x18000206e  pop     rbx
0x18000206f  retn
0x1800114c2  push    rbp
0x1800114c4  sub     rsp, 20h
0x1800114c8  mov     rbp, rdx
0x1800114cb  mov     rax, [rcx]
0x1800114ce  mov     edx, [rax]
0x1800114d0  mov     [rbp+0A8h], rcx
0x1800114d7  mov     [rbp+28h], edx
0x1800114da  mov     eax, [rbp+28h]
0x1800114dd  cmp     eax, 0E06D7363h
0x1800114e2  jnz     short loc_1800114F8
0x1800114e4  mov     rdx, [rbp+0A8h]
0x1800114eb  mov     ecx, [rbp+28h]
0x1800114ee  call    _XcptFilter_0
0x1800114f3  mov     [rbp+30h], eax
0x1800114f6  jmp     short loc_1800114FF
0x1800114f8  mov     dword ptr [rbp+30h], 0
0x1800114ff  mov     eax, [rbp+30h]
0x180011502  add     rsp, 20h
0x180011506  pop     rbp
0x180011507  retn
0x180011509  push    rbp
0x18001150b  sub     rsp, 20h
0x18001150f  mov     rbp, rdx
0x180011512  mov     rax, [rcx]
0x180011515  mov     edx, [rax]
0x180011517  mov     [rbp+0B0h], rcx
0x18001151e  mov     [rbp+38h], edx
0x180011521  mov     eax, [rbp+38h]
0x180011524  cmp     eax, 0E06D7363h
0x180011529  jnz     short loc_18001153F
0x18001152b  mov     rdx, [rbp+0B0h]
0x180011532  mov     ecx, [rbp+38h]
0x180011535  call    _XcptFilter_0
0x18001153a  mov     [rbp+40h], eax
0x18001153d  jmp     short loc_180011546
0x18001153f  mov     dword ptr [rbp+40h], 0
0x180011546  mov     eax, [rbp+40h]
0x180011549  add     rsp, 20h
0x18001154d  pop     rbp
0x18001154e  retn
0x180011550  push    rbp
0x180011552  sub     rsp, 20h
0x180011556  mov     rbp, rdx
0x180011559  mov     rax, [rcx]
0x18001155c  mov     edx, [rax]
0x18001155e  mov     [rbp+0B8h], rcx
0x180011565  mov     [rbp+48h], edx
0x180011568  mov     eax, [rbp+48h]
0x18001156b  cmp     eax, 0E06D7363h
0x180011570  jnz     short loc_180011586
0x180011572  mov     rdx, [rbp+0B8h]
0x180011579  mov     ecx, [rbp+48h]
0x18001157c  call    _XcptFilter_0
0x180011581  mov     [rbp+50h], eax
0x180011584  jmp     short loc_18001158D
0x180011586  mov     dword ptr [rbp+50h], 0
0x18001158d  mov     eax, [rbp+50h]
0x180011590  add     rsp, 20h
0x180011594  pop     rbp
0x180011595  retn
0x180011597  push    rbp
0x180011599  sub     rsp, 20h
0x18001159d  mov     rbp, rdx
0x1800115a0  mov     rax, [rcx]
0x1800115a3  mov     edx, [rax]
0x1800115a5  mov     [rbp+0C0h], rcx
0x1800115ac  mov     [rbp+58h], edx
0x1800115af  mov     eax, [rbp+58h]
0x1800115b2  cmp     eax, 0E06D7363h
0x1800115b7  jnz     short loc_1800115CD
0x1800115b9  mov     rdx, [rbp+0C0h]
0x1800115c0  mov     ecx, [rbp+58h]
0x1800115c3  call    _XcptFilter_0
0x1800115c8  mov     [rbp+60h], eax
0x1800115cb  jmp     short loc_1800115D4
0x1800115cd  mov     dword ptr [rbp+60h], 0
0x1800115d4  mov     eax, [rbp+60h]
0x1800115d7  add     rsp, 20h
0x1800115db  pop     rbp
0x1800115dc  retn
0x1800115de  push    rbp
0x1800115e0  sub     rsp, 20h
0x1800115e4  mov     rbp, rdx
0x1800115e7  mov     rax, [rcx]
0x1800115ea  mov     edx, [rax]
0x1800115ec  mov     [rbp+0C8h], rcx
0x1800115f3  mov     [rbp+68h], edx
0x1800115f6  mov     eax, [rbp+68h]
0x1800115f9  cmp     eax, 0E06D7363h
0x1800115fe  jnz     short loc_180011614
0x180011600  mov     rdx, [rbp+0C8h]
0x180011607  mov     ecx, [rbp+68h]
0x18001160a  call    _XcptFilter_0
0x18001160f  mov     [rbp+70h], eax
0x180011612  jmp     short loc_18001161B
0x180011614  mov     dword ptr [rbp+70h], 0
0x18001161b  mov     eax, [rbp+70h]
0x18001161e  add     rsp, 20h
0x180011622  pop     rbp
0x180011623  retn
0x180011625  push    rbp
0x180011627  sub     rsp, 20h
0x18001162b  mov     rbp, rdx
0x18001162e  mov     rax, [rcx]
0x180011631  mov     edx, [rax]
0x180011633  mov     [rbp+0D0h], rcx
0x18001163a  mov     [rbp+78h], edx
0x18001163d  mov     eax, [rbp+78h]
0x180011640  cmp     eax, 0E06D7363h
0x180011645  jnz     short loc_18001165E
0x180011647  mov     rdx, [rbp+0D0h]
0x18001164e  mov     ecx, [rbp+78h]
0x180011651  call    _XcptFilter_0
0x180011656  mov     [rbp+80h], eax
0x18001165c  jmp     short loc_180011668
0x18001165e  mov     dword ptr [rbp+80h], 0
0x180011668  mov     eax, [rbp+80h]
0x18001166e  add     rsp, 20h
0x180011672  pop     rbp
0x180011673  retn
0x180011675  push    rbp
0x180011677  sub     rsp, 20h
0x18001167b  mov     rbp, rdx
0x18001167e  mov     rax, [rcx]
0x180011681  mov     edx, [rax]
0x180011683  mov     [rbp+0D8h], rcx
0x18001168a  mov     [rbp+88h], edx
0x180011690  mov     eax, [rbp+88h]
0x180011696  cmp     eax, 0E06D7363h
0x18001169b  jnz     short loc_1800116B7
0x18001169d  mov     rdx, [rbp+0D8h]
0x1800116a4  mov     ecx, [rbp+88h]
0x1800116aa  call    _XcptFilter_0
0x1800116af  mov     [rbp+90h], eax
0x1800116b5  jmp     short loc_1800116C1
0x1800116b7  mov     dword ptr [rbp+90h], 0
0x1800116c1  mov     eax, [rbp+90h]
0x1800116c7  add     rsp, 20h
0x1800116cb  pop     rbp
0x1800116cc  retn
0x1800116ce  push    rbp
0x1800116d0  sub     rsp, 20h
0x1800116d4  mov     rbp, rdx
0x1800116d7  mov     rax, [rcx]
0x1800116da  mov     edx, [rax]
0x1800116dc  mov     [rbp+0E0h], rcx
0x1800116e3  mov     [rbp+98h], edx
0x1800116e9  mov     eax, [rbp+98h]
0x1800116ef  cmp     eax, 0E06D7363h
0x1800116f4  jnz     short loc_180011710
0x1800116f6  mov     rdx, [rbp+0E0h]
0x1800116fd  mov     ecx, [rbp+98h]
0x180011703  call    _XcptFilter_0
0x180011708  mov     [rbp+0A0h], eax
0x18001170e  jmp     short loc_18001171A
0x180011710  mov     dword ptr [rbp+0A0h], 0
0x18001171a  mov     eax, [rbp+0A0h]
0x180011720  add     rsp, 20h
0x180011724  pop     rbp
0x180011725  retn
0x180011727  push    rbp
0x180011729  sub     rsp, 20h
0x18001172d  mov     rbp, rdx
0x180011730  cmp     dword ptr [rbp+118h], 1
0x180011737  ja      short loc_180011743
0x180011739  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

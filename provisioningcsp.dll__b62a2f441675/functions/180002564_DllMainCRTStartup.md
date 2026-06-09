# __DllMainCRTStartup

- ea: `0x180002564`
- end: `0x180002770`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002520`

## callees

- `0x1800022f0`
- `0x180002564`
- `0x1800027a1`
- `0x18000340c`
- `0x180035910`

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
  if ( (_DWORD)fdwReason || dword_180049AC0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180049AC4 = 1;
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
            if ( dword_180049AC4 )
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
0x180002564  mov     [rsp+lpvReserved], r8
0x180002569  mov     [rsp+arg_8], edx
0x18000256d  mov     [rsp+arg_0], rcx
0x180002572  push    rbx
0x180002573  push    rsi
0x180002574  push    rdi
0x180002575  sub     rsp, 0F0h
0x18000257c  mov     edi, edx
0x18000257e  mov     rsi, rcx
0x180002581  mov     ebx, 1
0x180002586  cmp     edx, ebx
0x180002588  ja      short loc_180002590
0x18000258a  mov     cs:__native_dllmain_reason, edx
0x180002590  test    edx, edx
0x180002592  jnz     short loc_1800025A7
0x180002594  cmp     cs:dword_180049AC0, edx
0x18000259a  jnz     short loc_1800025A7
0x18000259c  xor     ebx, ebx
0x18000259e  mov     [rsp+108h+var_E8], ebx
0x1800025a2  jmp     loc_180002754
0x1800025a7  lea     eax, [rdx-1]
0x1800025aa  cmp     eax, 1
0x1800025ad  ja      loc_180002634
0x1800025b3  mov     rax, cs:_pRawDllMain
0x1800025ba  test    rax, rax
0x1800025bd  jz      short loc_1800025F5
0x1800025bf  cmp     edx, 1
0x1800025c2  jnz     short loc_1800025CA
0x1800025c4  mov     cs:dword_180049AC4, edx
0x1800025ca  mov     r8, [rsp+108h+lpvReserved]
0x1800025d2  call    cs:__guard_dispatch_icall_fptr
0x1800025d8  mov     ebx, eax
0x1800025da  mov     [rsp+108h+var_E8], eax
0x1800025de  jmp     short loc_1800025F5
0x1800025e0  xor     ebx, ebx
0x1800025e2  mov     [rsp+108h+var_E8], ebx
0x1800025e6  mov     edi, [rsp+108h+arg_8]
0x1800025ed  mov     rsi, [rsp+108h+arg_0]
0x1800025f5  test    ebx, ebx
0x1800025f7  jz      loc_180002754
0x1800025fd  mov     r8, [rsp+108h+lpvReserved]
0x180002605  mov     edx, edi
0x180002607  mov     rcx, rsi
0x18000260a  call    _CRT_INIT
0x18000260f  mov     ebx, eax
0x180002611  mov     [rsp+108h+var_E8], eax
0x180002615  jmp     short loc_18000262C
0x180002617  xor     ebx, ebx
0x180002619  mov     [rsp+108h+var_E8], ebx
0x18000261d  mov     edi, [rsp+108h+arg_8]
0x180002624  mov     rsi, [rsp+108h+arg_0]
0x18000262c  test    ebx, ebx
0x18000262e  jz      loc_180002754
0x180002634  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000263c  mov     edx, edi; fdwReason
0x18000263e  mov     rcx, rsi; hinstDLL
0x180002641  call    DllMain
0x180002646  mov     ebx, eax
0x180002648  mov     [rsp+108h+var_E8], eax
0x18000264c  jmp     short loc_180002663
0x18000264e  xor     ebx, ebx
0x180002650  mov     [rsp+108h+var_E8], ebx
0x180002654  mov     edi, [rsp+108h+arg_8]
0x18000265b  mov     rsi, [rsp+108h+arg_0]
0x180002663  cmp     edi, 1
0x180002666  jnz     short loc_1800026DF
0x180002668  test    ebx, ebx
0x18000266a  jnz     short loc_1800026DF
0x18000266c  xor     r8d, r8d; lpvReserved
0x18000266f  xor     edx, edx; fdwReason
0x180002671  mov     rcx, rsi; hinstDLL
0x180002674  call    DllMain
0x180002679  jmp     short loc_18000268E
0x18000267b  mov     edi, [rsp+108h+arg_8]
0x180002682  mov     rsi, [rsp+108h+arg_0]
0x18000268a  mov     ebx, [rsp+108h+var_E8]
0x18000268e  xor     r8d, r8d
0x180002691  xor     edx, edx
0x180002693  mov     rcx, rsi
0x180002696  call    _CRT_INIT
0x18000269b  jmp     short loc_1800026B0
0x18000269d  mov     edi, [rsp+108h+arg_8]
0x1800026a4  mov     rsi, [rsp+108h+arg_0]
0x1800026ac  mov     ebx, [rsp+108h+var_E8]
0x1800026b0  mov     rax, cs:_pRawDllMain
0x1800026b7  test    rax, rax
0x1800026ba  jz      short loc_1800026DF
0x1800026bc  xor     r8d, r8d
0x1800026bf  xor     edx, edx
0x1800026c1  mov     rcx, rsi
0x1800026c4  call    cs:__guard_dispatch_icall_fptr
0x1800026ca  jmp     short loc_1800026DF
0x1800026cc  mov     edi, [rsp+108h+arg_8]
0x1800026d3  mov     rsi, [rsp+108h+arg_0]
0x1800026db  mov     ebx, [rsp+108h+var_E8]
0x1800026df  test    edi, edi
0x1800026e1  jz      short loc_1800026E8
0x1800026e3  cmp     edi, 3
0x1800026e6  jnz     short loc_180002754
0x1800026e8  mov     r8, [rsp+108h+lpvReserved]
0x1800026f0  mov     edx, edi
0x1800026f2  mov     rcx, rsi
0x1800026f5  call    _CRT_INIT
0x1800026fa  mov     ebx, eax
0x1800026fc  mov     [rsp+108h+var_E8], eax
0x180002700  jmp     short loc_180002717
0x180002702  xor     ebx, ebx
0x180002704  mov     [rsp+108h+var_E8], ebx
0x180002708  mov     edi, [rsp+108h+arg_8]
0x18000270f  mov     rsi, [rsp+108h+arg_0]
0x180002717  mov     rax, cs:_pRawDllMain
0x18000271e  test    rax, rax
0x180002721  jz      short loc_180002754
0x180002723  cmp     cs:dword_180049AC4, 0
0x18000272a  jz      short loc_180002754
0x18000272c  mov     r8, [rsp+108h+lpvReserved]
0x180002734  mov     edx, edi
0x180002736  mov     rcx, rsi
0x180002739  call    cs:__guard_dispatch_icall_fptr
0x18000273f  mov     ebx, eax
0x180002741  mov     [rsp+108h+var_E8], eax
0x180002745  jmp     short loc_180002754
0x180002747  xor     ebx, ebx
0x180002749  mov     [rsp+108h+var_E8], ebx
0x18000274d  mov     edi, [rsp+108h+arg_8]
0x180002754  cmp     edi, 1
0x180002757  ja      short loc_180002763
0x180002759  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002763  mov     eax, ebx
0x180002765  add     rsp, 0F0h
0x18000276c  pop     rdi
0x18000276d  pop     rsi
0x18000276e  pop     rbx
0x18000276f  retn
0x1800359b3  push    rbp
0x1800359b5  sub     rsp, 20h
0x1800359b9  mov     rbp, rdx
0x1800359bc  mov     rax, [rcx]
0x1800359bf  mov     edx, [rax]
0x1800359c1  mov     [rbp+0A8h], rcx
0x1800359c8  mov     [rbp+28h], edx
0x1800359cb  mov     eax, [rbp+28h]
0x1800359ce  cmp     eax, 0E06D7363h
0x1800359d3  jnz     short loc_1800359E9
0x1800359d5  mov     rdx, [rbp+0A8h]
0x1800359dc  mov     ecx, [rbp+28h]
0x1800359df  call    _XcptFilter_0
0x1800359e4  mov     [rbp+30h], eax
0x1800359e7  jmp     short loc_1800359F0
0x1800359e9  mov     dword ptr [rbp+30h], 0
0x1800359f0  mov     eax, [rbp+30h]
0x1800359f3  add     rsp, 20h
0x1800359f7  pop     rbp
0x1800359f8  retn
0x1800359fa  push    rbp
0x1800359fc  sub     rsp, 20h
0x180035a00  mov     rbp, rdx
0x180035a03  mov     rax, [rcx]
0x180035a06  mov     edx, [rax]
0x180035a08  mov     [rbp+0B0h], rcx
0x180035a0f  mov     [rbp+38h], edx
0x180035a12  mov     eax, [rbp+38h]
0x180035a15  cmp     eax, 0E06D7363h
0x180035a1a  jnz     short loc_180035A30
0x180035a1c  mov     rdx, [rbp+0B0h]
0x180035a23  mov     ecx, [rbp+38h]
0x180035a26  call    _XcptFilter_0
0x180035a2b  mov     [rbp+40h], eax
0x180035a2e  jmp     short loc_180035A37
0x180035a30  mov     dword ptr [rbp+40h], 0
0x180035a37  mov     eax, [rbp+40h]
0x180035a3a  add     rsp, 20h
0x180035a3e  pop     rbp
0x180035a3f  retn
0x180035a41  push    rbp
0x180035a43  sub     rsp, 20h
0x180035a47  mov     rbp, rdx
0x180035a4a  mov     rax, [rcx]
0x180035a4d  mov     edx, [rax]
0x180035a4f  mov     [rbp+0B8h], rcx
0x180035a56  mov     [rbp+48h], edx
0x180035a59  mov     eax, [rbp+48h]
0x180035a5c  cmp     eax, 0E06D7363h
0x180035a61  jnz     short loc_180035A77
0x180035a63  mov     rdx, [rbp+0B8h]
0x180035a6a  mov     ecx, [rbp+48h]
0x180035a6d  call    _XcptFilter_0
0x180035a72  mov     [rbp+50h], eax
0x180035a75  jmp     short loc_180035A7E
0x180035a77  mov     dword ptr [rbp+50h], 0
0x180035a7e  mov     eax, [rbp+50h]
0x180035a81  add     rsp, 20h
0x180035a85  pop     rbp
0x180035a86  retn
0x180035a88  push    rbp
0x180035a8a  sub     rsp, 20h
0x180035a8e  mov     rbp, rdx
0x180035a91  mov     rax, [rcx]
0x180035a94  mov     edx, [rax]
0x180035a96  mov     [rbp+0C0h], rcx
0x180035a9d  mov     [rbp+58h], edx
0x180035aa0  mov     eax, [rbp+58h]
0x180035aa3  cmp     eax, 0E06D7363h
0x180035aa8  jnz     short loc_180035ABE
0x180035aaa  mov     rdx, [rbp+0C0h]
0x180035ab1  mov     ecx, [rbp+58h]
0x180035ab4  call    _XcptFilter_0
0x180035ab9  mov     [rbp+60h], eax
0x180035abc  jmp     short loc_180035AC5
0x180035abe  mov     dword ptr [rbp+60h], 0
0x180035ac5  mov     eax, [rbp+60h]
0x180035ac8  add     rsp, 20h
0x180035acc  pop     rbp
0x180035acd  retn
0x180035acf  push    rbp
0x180035ad1  sub     rsp, 20h
0x180035ad5  mov     rbp, rdx
0x180035ad8  mov     rax, [rcx]
0x180035adb  mov     edx, [rax]
0x180035add  mov     [rbp+0C8h], rcx
0x180035ae4  mov     [rbp+68h], edx
0x180035ae7  mov     eax, [rbp+68h]
0x180035aea  cmp     eax, 0E06D7363h
0x180035aef  jnz     short loc_180035B05
0x180035af1  mov     rdx, [rbp+0C8h]
0x180035af8  mov     ecx, [rbp+68h]
0x180035afb  call    _XcptFilter_0
0x180035b00  mov     [rbp+70h], eax
0x180035b03  jmp     short loc_180035B0C
0x180035b05  mov     dword ptr [rbp+70h], 0
0x180035b0c  mov     eax, [rbp+70h]
0x180035b0f  add     rsp, 20h
0x180035b13  pop     rbp
0x180035b14  retn
0x180035b16  push    rbp
0x180035b18  sub     rsp, 20h
0x180035b1c  mov     rbp, rdx
0x180035b1f  mov     rax, [rcx]
0x180035b22  mov     edx, [rax]
0x180035b24  mov     [rbp+0D0h], rcx
0x180035b2b  mov     [rbp+78h], edx
0x180035b2e  mov     eax, [rbp+78h]
0x180035b31  cmp     eax, 0E06D7363h
0x180035b36  jnz     short loc_180035B4F
0x180035b38  mov     rdx, [rbp+0D0h]
0x180035b3f  mov     ecx, [rbp+78h]
0x180035b42  call    _XcptFilter_0
0x180035b47  mov     [rbp+80h], eax
0x180035b4d  jmp     short loc_180035B59
0x180035b4f  mov     dword ptr [rbp+80h], 0
0x180035b59  mov     eax, [rbp+80h]
0x180035b5f  add     rsp, 20h
0x180035b63  pop     rbp
0x180035b64  retn
0x180035b66  push    rbp
0x180035b68  sub     rsp, 20h
0x180035b6c  mov     rbp, rdx
0x180035b6f  mov     rax, [rcx]
0x180035b72  mov     edx, [rax]
0x180035b74  mov     [rbp+0D8h], rcx
0x180035b7b  mov     [rbp+88h], edx
0x180035b81  mov     eax, [rbp+88h]
0x180035b87  cmp     eax, 0E06D7363h
0x180035b8c  jnz     short loc_180035BA8
0x180035b8e  mov     rdx, [rbp+0D8h]
0x180035b95  mov     ecx, [rbp+88h]
0x180035b9b  call    _XcptFilter_0
0x180035ba0  mov     [rbp+90h], eax
0x180035ba6  jmp     short loc_180035BB2
0x180035ba8  mov     dword ptr [rbp+90h], 0
0x180035bb2  mov     eax, [rbp+90h]
0x180035bb8  add     rsp, 20h
0x180035bbc  pop     rbp
0x180035bbd  retn
0x180035bbf  push    rbp
0x180035bc1  sub     rsp, 20h
0x180035bc5  mov     rbp, rdx
0x180035bc8  mov     rax, [rcx]
0x180035bcb  mov     edx, [rax]
0x180035bcd  mov     [rbp+0E0h], rcx
0x180035bd4  mov     [rbp+98h], edx
0x180035bda  mov     eax, [rbp+98h]
0x180035be0  cmp     eax, 0E06D7363h
0x180035be5  jnz     short loc_180035C01
0x180035be7  mov     rdx, [rbp+0E0h]
0x180035bee  mov     ecx, [rbp+98h]
0x180035bf4  call    _XcptFilter_0
0x180035bf9  mov     [rbp+0A0h], eax
0x180035bff  jmp     short loc_180035C0B
0x180035c01  mov     dword ptr [rbp+0A0h], 0
0x180035c0b  mov     eax, [rbp+0A0h]
0x180035c11  add     rsp, 20h
0x180035c15  pop     rbp
0x180035c16  retn
0x180035c18  push    rbp
0x180035c1a  sub     rsp, 20h
0x180035c1e  mov     rbp, rdx
0x180035c21  cmp     dword ptr [rbp+118h], 1
0x180035c28  ja      short loc_180035C34
0x180035c2a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

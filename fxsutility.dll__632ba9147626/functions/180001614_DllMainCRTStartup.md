# __DllMainCRTStartup

- ea: `0x180001614`
- end: `0x180001820`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800015d0`

## callees

- `0x1800013a0`
- `0x180001614`
- `0x180001916`
- `0x180004a74`
- `0x180015d60`

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
  if ( (_DWORD)fdwReason || dword_18001E580 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001E584 = 1;
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
            if ( dword_18001E584 )
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
0x180001614  mov     [rsp+lpvReserved], r8
0x180001619  mov     [rsp+arg_8], edx
0x18000161d  mov     [rsp+arg_0], rcx
0x180001622  push    rbx
0x180001623  push    rsi
0x180001624  push    rdi
0x180001625  sub     rsp, 0F0h
0x18000162c  mov     edi, edx
0x18000162e  mov     rsi, rcx
0x180001631  mov     ebx, 1
0x180001636  cmp     edx, ebx
0x180001638  ja      short loc_180001640
0x18000163a  mov     cs:__native_dllmain_reason, edx
0x180001640  test    edx, edx
0x180001642  jnz     short loc_180001657
0x180001644  cmp     cs:dword_18001E580, edx
0x18000164a  jnz     short loc_180001657
0x18000164c  xor     ebx, ebx
0x18000164e  mov     [rsp+108h+var_E8], ebx
0x180001652  jmp     loc_180001804
0x180001657  lea     eax, [rdx-1]
0x18000165a  cmp     eax, 1
0x18000165d  ja      loc_1800016E4
0x180001663  mov     rax, cs:_pRawDllMain
0x18000166a  test    rax, rax
0x18000166d  jz      short loc_1800016A5
0x18000166f  cmp     edx, 1
0x180001672  jnz     short loc_18000167A
0x180001674  mov     cs:dword_18001E584, edx
0x18000167a  mov     r8, [rsp+108h+lpvReserved]
0x180001682  call    cs:__guard_dispatch_icall_fptr
0x180001688  mov     ebx, eax
0x18000168a  mov     [rsp+108h+var_E8], eax
0x18000168e  jmp     short loc_1800016A5
0x180001690  xor     ebx, ebx
0x180001692  mov     [rsp+108h+var_E8], ebx
0x180001696  mov     edi, [rsp+108h+arg_8]
0x18000169d  mov     rsi, [rsp+108h+arg_0]
0x1800016a5  test    ebx, ebx
0x1800016a7  jz      loc_180001804
0x1800016ad  mov     r8, [rsp+108h+lpvReserved]
0x1800016b5  mov     edx, edi
0x1800016b7  mov     rcx, rsi
0x1800016ba  call    _CRT_INIT
0x1800016bf  mov     ebx, eax
0x1800016c1  mov     [rsp+108h+var_E8], eax
0x1800016c5  jmp     short loc_1800016DC
0x1800016c7  xor     ebx, ebx
0x1800016c9  mov     [rsp+108h+var_E8], ebx
0x1800016cd  mov     edi, [rsp+108h+arg_8]
0x1800016d4  mov     rsi, [rsp+108h+arg_0]
0x1800016dc  test    ebx, ebx
0x1800016de  jz      loc_180001804
0x1800016e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800016ec  mov     edx, edi; fdwReason
0x1800016ee  mov     rcx, rsi; hinstDLL
0x1800016f1  call    DllMain
0x1800016f6  mov     ebx, eax
0x1800016f8  mov     [rsp+108h+var_E8], eax
0x1800016fc  jmp     short loc_180001713
0x1800016fe  xor     ebx, ebx
0x180001700  mov     [rsp+108h+var_E8], ebx
0x180001704  mov     edi, [rsp+108h+arg_8]
0x18000170b  mov     rsi, [rsp+108h+arg_0]
0x180001713  cmp     edi, 1
0x180001716  jnz     short loc_18000178F
0x180001718  test    ebx, ebx
0x18000171a  jnz     short loc_18000178F
0x18000171c  xor     r8d, r8d; lpvReserved
0x18000171f  xor     edx, edx; fdwReason
0x180001721  mov     rcx, rsi; hinstDLL
0x180001724  call    DllMain
0x180001729  jmp     short loc_18000173E
0x18000172b  mov     edi, [rsp+108h+arg_8]
0x180001732  mov     rsi, [rsp+108h+arg_0]
0x18000173a  mov     ebx, [rsp+108h+var_E8]
0x18000173e  xor     r8d, r8d
0x180001741  xor     edx, edx
0x180001743  mov     rcx, rsi
0x180001746  call    _CRT_INIT
0x18000174b  jmp     short loc_180001760
0x18000174d  mov     edi, [rsp+108h+arg_8]
0x180001754  mov     rsi, [rsp+108h+arg_0]
0x18000175c  mov     ebx, [rsp+108h+var_E8]
0x180001760  mov     rax, cs:_pRawDllMain
0x180001767  test    rax, rax
0x18000176a  jz      short loc_18000178F
0x18000176c  xor     r8d, r8d
0x18000176f  xor     edx, edx
0x180001771  mov     rcx, rsi
0x180001774  call    cs:__guard_dispatch_icall_fptr
0x18000177a  jmp     short loc_18000178F
0x18000177c  mov     edi, [rsp+108h+arg_8]
0x180001783  mov     rsi, [rsp+108h+arg_0]
0x18000178b  mov     ebx, [rsp+108h+var_E8]
0x18000178f  test    edi, edi
0x180001791  jz      short loc_180001798
0x180001793  cmp     edi, 3
0x180001796  jnz     short loc_180001804
0x180001798  mov     r8, [rsp+108h+lpvReserved]
0x1800017a0  mov     edx, edi
0x1800017a2  mov     rcx, rsi
0x1800017a5  call    _CRT_INIT
0x1800017aa  mov     ebx, eax
0x1800017ac  mov     [rsp+108h+var_E8], eax
0x1800017b0  jmp     short loc_1800017C7
0x1800017b2  xor     ebx, ebx
0x1800017b4  mov     [rsp+108h+var_E8], ebx
0x1800017b8  mov     edi, [rsp+108h+arg_8]
0x1800017bf  mov     rsi, [rsp+108h+arg_0]
0x1800017c7  mov     rax, cs:_pRawDllMain
0x1800017ce  test    rax, rax
0x1800017d1  jz      short loc_180001804
0x1800017d3  cmp     cs:dword_18001E584, 0
0x1800017da  jz      short loc_180001804
0x1800017dc  mov     r8, [rsp+108h+lpvReserved]
0x1800017e4  mov     edx, edi
0x1800017e6  mov     rcx, rsi
0x1800017e9  call    cs:__guard_dispatch_icall_fptr
0x1800017ef  mov     ebx, eax
0x1800017f1  mov     [rsp+108h+var_E8], eax
0x1800017f5  jmp     short loc_180001804
0x1800017f7  xor     ebx, ebx
0x1800017f9  mov     [rsp+108h+var_E8], ebx
0x1800017fd  mov     edi, [rsp+108h+arg_8]
0x180001804  cmp     edi, 1
0x180001807  ja      short loc_180001813
0x180001809  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001813  mov     eax, ebx
0x180001815  add     rsp, 0F0h
0x18000181c  pop     rdi
0x18000181d  pop     rsi
0x18000181e  pop     rbx
0x18000181f  retn
0x180015e03  push    rbp
0x180015e05  sub     rsp, 20h
0x180015e09  mov     rbp, rdx
0x180015e0c  mov     rax, [rcx]
0x180015e0f  mov     edx, [rax]
0x180015e11  mov     [rbp+0A8h], rcx
0x180015e18  mov     [rbp+28h], edx
0x180015e1b  mov     eax, [rbp+28h]
0x180015e1e  cmp     eax, 0E06D7363h
0x180015e23  jnz     short loc_180015E39
0x180015e25  mov     rdx, [rbp+0A8h]
0x180015e2c  mov     ecx, [rbp+28h]
0x180015e2f  call    _XcptFilter_0
0x180015e34  mov     [rbp+30h], eax
0x180015e37  jmp     short loc_180015E40
0x180015e39  mov     dword ptr [rbp+30h], 0
0x180015e40  mov     eax, [rbp+30h]
0x180015e43  add     rsp, 20h
0x180015e47  pop     rbp
0x180015e48  retn
0x180015e4a  push    rbp
0x180015e4c  sub     rsp, 20h
0x180015e50  mov     rbp, rdx
0x180015e53  mov     rax, [rcx]
0x180015e56  mov     edx, [rax]
0x180015e58  mov     [rbp+0B0h], rcx
0x180015e5f  mov     [rbp+38h], edx
0x180015e62  mov     eax, [rbp+38h]
0x180015e65  cmp     eax, 0E06D7363h
0x180015e6a  jnz     short loc_180015E80
0x180015e6c  mov     rdx, [rbp+0B0h]
0x180015e73  mov     ecx, [rbp+38h]
0x180015e76  call    _XcptFilter_0
0x180015e7b  mov     [rbp+40h], eax
0x180015e7e  jmp     short loc_180015E87
0x180015e80  mov     dword ptr [rbp+40h], 0
0x180015e87  mov     eax, [rbp+40h]
0x180015e8a  add     rsp, 20h
0x180015e8e  pop     rbp
0x180015e8f  retn
0x180015e91  push    rbp
0x180015e93  sub     rsp, 20h
0x180015e97  mov     rbp, rdx
0x180015e9a  mov     rax, [rcx]
0x180015e9d  mov     edx, [rax]
0x180015e9f  mov     [rbp+0B8h], rcx
0x180015ea6  mov     [rbp+48h], edx
0x180015ea9  mov     eax, [rbp+48h]
0x180015eac  cmp     eax, 0E06D7363h
0x180015eb1  jnz     short loc_180015EC7
0x180015eb3  mov     rdx, [rbp+0B8h]
0x180015eba  mov     ecx, [rbp+48h]
0x180015ebd  call    _XcptFilter_0
0x180015ec2  mov     [rbp+50h], eax
0x180015ec5  jmp     short loc_180015ECE
0x180015ec7  mov     dword ptr [rbp+50h], 0
0x180015ece  mov     eax, [rbp+50h]
0x180015ed1  add     rsp, 20h
0x180015ed5  pop     rbp
0x180015ed6  retn
0x180015ed8  push    rbp
0x180015eda  sub     rsp, 20h
0x180015ede  mov     rbp, rdx
0x180015ee1  mov     rax, [rcx]
0x180015ee4  mov     edx, [rax]
0x180015ee6  mov     [rbp+0C0h], rcx
0x180015eed  mov     [rbp+58h], edx
0x180015ef0  mov     eax, [rbp+58h]
0x180015ef3  cmp     eax, 0E06D7363h
0x180015ef8  jnz     short loc_180015F0E
0x180015efa  mov     rdx, [rbp+0C0h]
0x180015f01  mov     ecx, [rbp+58h]
0x180015f04  call    _XcptFilter_0
0x180015f09  mov     [rbp+60h], eax
0x180015f0c  jmp     short loc_180015F15
0x180015f0e  mov     dword ptr [rbp+60h], 0
0x180015f15  mov     eax, [rbp+60h]
0x180015f18  add     rsp, 20h
0x180015f1c  pop     rbp
0x180015f1d  retn
0x180015f1f  push    rbp
0x180015f21  sub     rsp, 20h
0x180015f25  mov     rbp, rdx
0x180015f28  mov     rax, [rcx]
0x180015f2b  mov     edx, [rax]
0x180015f2d  mov     [rbp+0C8h], rcx
0x180015f34  mov     [rbp+68h], edx
0x180015f37  mov     eax, [rbp+68h]
0x180015f3a  cmp     eax, 0E06D7363h
0x180015f3f  jnz     short loc_180015F55
0x180015f41  mov     rdx, [rbp+0C8h]
0x180015f48  mov     ecx, [rbp+68h]
0x180015f4b  call    _XcptFilter_0
0x180015f50  mov     [rbp+70h], eax
0x180015f53  jmp     short loc_180015F5C
0x180015f55  mov     dword ptr [rbp+70h], 0
0x180015f5c  mov     eax, [rbp+70h]
0x180015f5f  add     rsp, 20h
0x180015f63  pop     rbp
0x180015f64  retn
0x180015f66  push    rbp
0x180015f68  sub     rsp, 20h
0x180015f6c  mov     rbp, rdx
0x180015f6f  mov     rax, [rcx]
0x180015f72  mov     edx, [rax]
0x180015f74  mov     [rbp+0D0h], rcx
0x180015f7b  mov     [rbp+78h], edx
0x180015f7e  mov     eax, [rbp+78h]
0x180015f81  cmp     eax, 0E06D7363h
0x180015f86  jnz     short loc_180015F9F
0x180015f88  mov     rdx, [rbp+0D0h]
0x180015f8f  mov     ecx, [rbp+78h]
0x180015f92  call    _XcptFilter_0
0x180015f97  mov     [rbp+80h], eax
0x180015f9d  jmp     short loc_180015FA9
0x180015f9f  mov     dword ptr [rbp+80h], 0
0x180015fa9  mov     eax, [rbp+80h]
0x180015faf  add     rsp, 20h
0x180015fb3  pop     rbp
0x180015fb4  retn
0x180015fb6  push    rbp
0x180015fb8  sub     rsp, 20h
0x180015fbc  mov     rbp, rdx
0x180015fbf  mov     rax, [rcx]
0x180015fc2  mov     edx, [rax]
0x180015fc4  mov     [rbp+0D8h], rcx
0x180015fcb  mov     [rbp+88h], edx
0x180015fd1  mov     eax, [rbp+88h]
0x180015fd7  cmp     eax, 0E06D7363h
0x180015fdc  jnz     short loc_180015FF8
0x180015fde  mov     rdx, [rbp+0D8h]
0x180015fe5  mov     ecx, [rbp+88h]
0x180015feb  call    _XcptFilter_0
0x180015ff0  mov     [rbp+90h], eax
0x180015ff6  jmp     short loc_180016002
0x180015ff8  mov     dword ptr [rbp+90h], 0
0x180016002  mov     eax, [rbp+90h]
0x180016008  add     rsp, 20h
0x18001600c  pop     rbp
0x18001600d  retn
0x18001600f  push    rbp
0x180016011  sub     rsp, 20h
0x180016015  mov     rbp, rdx
0x180016018  mov     rax, [rcx]
0x18001601b  mov     edx, [rax]
0x18001601d  mov     [rbp+0E0h], rcx
0x180016024  mov     [rbp+98h], edx
0x18001602a  mov     eax, [rbp+98h]
0x180016030  cmp     eax, 0E06D7363h
0x180016035  jnz     short loc_180016051
0x180016037  mov     rdx, [rbp+0E0h]
0x18001603e  mov     ecx, [rbp+98h]
0x180016044  call    _XcptFilter_0
0x180016049  mov     [rbp+0A0h], eax
0x18001604f  jmp     short loc_18001605B
0x180016051  mov     dword ptr [rbp+0A0h], 0
0x18001605b  mov     eax, [rbp+0A0h]
0x180016061  add     rsp, 20h
0x180016065  pop     rbp
0x180016066  retn
0x180016068  push    rbp
0x18001606a  sub     rsp, 20h
0x18001606e  mov     rbp, rdx
0x180016071  cmp     dword ptr [rbp+118h], 1
0x180016078  ja      short loc_180016084
0x18001607a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```

# CFveApiBase::VolumeNameToVolumeGuidName(ushort const *,ushort * *)

- ea: `0x180007ae0`
- end: `0x180007f77`
- name: `?VolumeNameToVolumeGuidName@CFveApiBase@@SAJPEBGPEAPEAG@Z`
- size: `1175`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x180006cc0`
- `0x180007180`
- `0x180009468`
- `0x18007d9a0`
- `0x1800caa7c`
- `0x1800d0124`

## callees

- `0x180005410`
- `0x180007ae0`
- `0x18000ba30`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180007b3d`
- `ntdll!RtlSetThreadErrorMode` at `0x180007f2a`
- `ntdll!RtlSetThreadErrorMode` at `0x18011f48d`
- `ntdll!RtlSetThreadErrorMode` at `0x180007b3d`
- `ntdll!RtlSetThreadErrorMode` at `0x180007f2a`
- `ntdll!RtlSetThreadErrorMode` at `0x18011f48d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007bdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007bdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d43`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180007d6c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180007d6c`

## pseudocode

```c
__int64 __fastcall CFveApiBase::VolumeNameToVolumeGuidName(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  WCHAR *v4; // r14
  WCHAR *v5; // r15
  __int64 v6; // rcx
  const unsigned __int16 *v7; // rax
  int v8; // edx
  unsigned int v9; // esi
  unsigned __int64 v10; // rbx
  SIZE_T v11; // r8
  int v12; // r9d
  __int64 v13; // rax
  WCHAR *v14; // rcx
  __int64 v15; // rdx
  unsigned __int16 v16; // r8
  __int64 v17; // rcx
  WCHAR *v18; // rax
  bool v19; // zf
  WCHAR *v20; // rax
  __int64 v21; // rax
  WCHAR *v22; // rcx
  bool v23; // zf
  WCHAR *v24; // rcx
  unsigned __int64 v26; // [rsp+20h] [rbp-B8h]
  __int64 v27; // [rsp+20h] [rbp-B8h]
  unsigned __int64 v28; // [rsp+20h] [rbp-B8h]
  ULONG NewMode; // [rsp+98h] [rbp-40h] BYREF

  NewMode = 0;
  v4 = 0;
  v5 = 0;
  RtlSetThreadErrorMode(0x10u, &NewMode);
  if ( !a1 )
  {
    v8 = -2147024809;
    goto LABEL_63;
  }
  v6 = 260;
  v7 = a1;
  v8 = 0;
  while ( v6 && *v7 )
  {
    ++v7;
    --v6;
  }
  v9 = -2147024809;
  if ( !v6 )
    v8 = -2147024809;
  if ( v8 < 0 )
    v26 = 0;
  else
    v26 = 260 - v6;
  if ( v8 < 0 )
    goto LABEL_63;
  if ( v26 < 2 )
    goto LABEL_72;
  v10 = v26 + 2;
  v11 = 2 * (v26 + 2);
  if ( !v11 )
    v11 = 1;
  v4 = (WCHAR *)HeapAlloc(CFveApiBase::_ProcessHeap, 0, v11);
  if ( !v4 )
  {
    v9 = -2147024882;
    goto LABEL_72;
  }
  if ( v26 == -2 || (v12 = 0, v10 > 0x7FFFFFFF) )
    v12 = -2147024809;
  if ( v12 < 0 )
  {
    if ( v26 != -2 )
      *v4 = 0;
  }
  else
  {
    v13 = 2147483646;
    v14 = v4;
    v12 = 0;
    v15 = 0;
    while ( v10 )
    {
      if ( !v13 )
        goto LABEL_23;
      v16 = *a1;
      if ( !*a1 )
        goto LABEL_23;
      ++a1;
      *v14++ = v16;
      --v10;
      --v13;
      ++v15;
    }
    --v14;
    v12 = -2147024774;
LABEL_23:
    *v14 = 0;
  }
  if ( v12 < 0 )
  {
    v9 = v12;
    goto LABEL_72;
  }
  v17 = 260;
  v18 = v4;
  v8 = 0;
  while ( 1 )
  {
    v19 = v17 == 0;
    if ( !v17 )
      break;
    if ( !*v18 )
    {
      v19 = v17 == 0;
      break;
    }
    ++v18;
    --v17;
  }
  if ( v19 )
    v8 = -2147024809;
  v27 = v8 < 0 ? 0LL : 260 - v17;
  if ( v8 < 0 )
  {
LABEL_63:
    v9 = v8;
    goto LABEL_72;
  }
  if ( v4[v27 - 1] != 92 )
  {
    v4[v27] = 92;
    v4[v27 + 1] = 0;
  }
  v20 = (WCHAR *)HeapAlloc(CFveApiBase::_ProcessHeap, 0, 0x64u);
  v5 = v20;
  if ( !v20 )
  {
    v9 = -2147024882;
    goto LABEL_72;
  }
  if ( !GetVolumeNameForVolumeMountPointW(v4, v20, 0x32u) )
  {
    if ( !HeapFree(CFveApiBase::_ProcessHeap, 0, v5) )
      GetLastHresultError();
    v5 = v4;
    v4 = 0;
  }
  if ( !v5 )
  {
    v8 = -2147024809;
    goto LABEL_63;
  }
  v21 = 260;
  v22 = v5;
  v8 = 0;
  while ( 1 )
  {
    v23 = v21 == 0;
    if ( !v21 )
      break;
    if ( !*v22 )
    {
      v23 = v21 == 0;
      break;
    }
    ++v22;
    --v21;
  }
  if ( v23 )
    v8 = -2147024809;
  if ( v8 < 0 )
    v28 = 0;
  else
    v28 = 260 - v21;
  if ( v8 < 0 )
    goto LABEL_63;
  if ( v28 >= 2 )
  {
    v24 = &v5[v28];
    if ( *(v24 - 1) == 92 )
      *(v24 - 1) = 0;
    *a2 = v5;
    v5 = 0;
    v9 = 0;
  }
LABEL_72:
  if ( v5 )
    CFveApiBase::FastFree(v5);
  if ( v4 && !HeapFree(CFveApiBase::_ProcessHeap, 0, v4) )
    GetLastHresultError();
  RtlSetThreadErrorMode(NewMode, 0);
  return v9;
}

```

## disassembly

```asm
0x180007ae0  mov     r11, rsp
0x180007ae3  mov     [r11+8], rbx
0x180007ae7  mov     [r11+18h], rsi
0x180007aeb  push    rdi
0x180007aec  push    r12
0x180007aee  push    r13
0x180007af0  push    r14
0x180007af2  push    r15
0x180007af4  sub     rsp, 0B0h
0x180007afb  mov     rax, cs:__security_cookie
0x180007b02  xor     rax, rsp
0x180007b05  mov     [rsp+0D8h+var_38], rax
0x180007b0d  mov     r13, rdx
0x180007b10  mov     rdi, rcx
0x180007b13  mov     [rsp+0D8h+var_B8], 0
0x180007b1c  mov     dword ptr [r11-40h], 0
0x180007b24  xor     r14d, r14d
0x180007b27  mov     [rsp+0D8h+var_A0], r14
0x180007b2c  xor     r15d, r15d
0x180007b2f  mov     [rsp+0D8h+var_A8], r15
0x180007b34  lea     rdx, [r11-40h]; OldMode
0x180007b38  mov     ecx, 10h; NewMode
0x180007b3d  call    cs:__imp_RtlSetThreadErrorMode
0x180007b44  nop     dword ptr [rax+rax+00h]
0x180007b49  nop
0x180007b4a  lea     r8, [rsp+0D8h+var_B8]
0x180007b4f  mov     r12d, 104h
0x180007b55  test    rdi, rdi
0x180007b58  jz      loc_180007EBB
0x180007b5e  mov     ecx, r12d
0x180007b61  mov     [rsp+0D8h+var_80], rcx
0x180007b66  mov     rax, rdi
0x180007b69  mov     [rsp+0D8h+var_88], rax
0x180007b6e  xor     edx, edx
0x180007b70  test    rcx, rcx
0x180007b73  jz      short loc_180007B8D
0x180007b75  cmp     [rax], dx
0x180007b78  jz      short loc_180007B8D
0x180007b7a  add     rax, 2
0x180007b7e  mov     [rsp+0D8h+var_88], rax
0x180007b83  dec     rcx
0x180007b86  mov     [rsp+0D8h+var_80], rcx
0x180007b8b  jmp     short loc_180007B70
0x180007b8d  mov     esi, 80070057h
0x180007b92  test    rcx, rcx
0x180007b95  cmovz   edx, esi
0x180007b98  test    edx, edx
0x180007b9a  js      loc_180007E71
0x180007ba0  mov     rax, r12
0x180007ba3  sub     rax, rcx
0x180007ba6  mov     [r8], rax
0x180007ba9  test    edx, edx
0x180007bab  js      loc_180007EAB
0x180007bb1  mov     rbx, [rsp+0D8h+var_B8]
0x180007bb6  cmp     rbx, 2
0x180007bba  jb      loc_180007EFB
0x180007bc0  add     rbx, 2
0x180007bc4  lea     r8, [rbx+rbx]
0x180007bc8  mov     eax, 1
0x180007bcd  test    r8, r8
0x180007bd0  cmovz   r8, rax; dwBytes
0x180007bd4  xor     edx, edx; dwFlags
0x180007bd6  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x180007bdd  call    cs:__imp_HeapAlloc
0x180007be4  nop     dword ptr [rax+rax+00h]
0x180007be9  mov     r14, rax
0x180007bec  mov     [rsp+0D8h+var_A0], rax
0x180007bf1  test    rax, rax
0x180007bf4  jz      loc_180007EC4
0x180007bfa  xor     r10d, r10d
0x180007bfd  mov     [rsp+0D8h+var_B0], r10d
0x180007c02  test    rbx, rbx
0x180007c05  jz      loc_180007ECB
0x180007c0b  mov     r9d, r10d
0x180007c0e  cmp     rbx, 7FFFFFFFh
0x180007c15  ja      loc_180007ECB
0x180007c1b  mov     [rsp+0D8h+var_B0], r9d
0x180007c20  test    r9d, r9d
0x180007c23  js      loc_180007ED3
0x180007c29  mov     eax, 7FFFFFFEh
0x180007c2e  mov     [rsp+0D8h+var_68], rax
0x180007c33  mov     [rsp+0D8h+var_78], rdi
0x180007c38  mov     [rsp+0D8h+var_70], rbx
0x180007c3d  mov     rcx, r14
0x180007c40  mov     [rsp+0D8h+var_98], rcx
0x180007c45  mov     r9d, r10d
0x180007c48  mov     rdx, r10
0x180007c4b  mov     [rsp+0D8h+var_90], rdx
0x180007c50  test    rbx, rbx
0x180007c53  jz      loc_180007E18
0x180007c59  test    rax, rax
0x180007c5c  jz      short loc_180007C98
0x180007c5e  movzx   r8d, word ptr [rdi]
0x180007c62  test    r8w, r8w
0x180007c66  jz      short loc_180007C98
0x180007c68  add     rdi, 2
0x180007c6c  mov     [rsp+0D8h+var_78], rdi
0x180007c71  mov     [rcx], r8w
0x180007c75  add     rcx, 2
0x180007c79  mov     [rsp+0D8h+var_98], rcx
0x180007c7e  dec     rbx
0x180007c81  mov     [rsp+0D8h+var_70], rbx
0x180007c86  dec     rax
0x180007c89  mov     [rsp+0D8h+var_68], rax
0x180007c8e  inc     rdx
0x180007c91  mov     [rsp+0D8h+var_90], rdx
0x180007c96  jmp     short loc_180007C50
0x180007c98  test    rbx, rbx
0x180007c9b  jz      loc_180007E18
0x180007ca1  mov     eax, r10d
0x180007ca4  mov     [rcx], ax
0x180007ca7  mov     [rsp+0D8h+var_B0], r9d
0x180007cac  test    r9d, r9d
0x180007caf  js      loc_180007E69
0x180007cb5  lea     r8, [rsp+0D8h+var_B8]
0x180007cba  mov     rcx, r12
0x180007cbd  mov     [rsp+0D8h+var_58], rcx
0x180007cc5  mov     rax, r14
0x180007cc8  mov     [rsp+0D8h+var_60], rax
0x180007ccd  mov     edx, r10d
0x180007cd0  test    rcx, rcx
0x180007cd3  jz      short loc_180007CF3
0x180007cd5  cmp     [rax], dx
0x180007cd8  jz      short loc_180007CF0
0x180007cda  add     rax, 2
0x180007cde  mov     [rsp+0D8h+var_60], rax
0x180007ce3  dec     rcx
0x180007ce6  mov     [rsp+0D8h+var_58], rcx
0x180007cee  jmp     short loc_180007CD0
0x180007cf0  test    rcx, rcx
0x180007cf3  cmovz   edx, esi
0x180007cf6  test    edx, edx
0x180007cf8  js      loc_180007E7D
0x180007cfe  mov     rax, r12
0x180007d01  sub     rax, rcx
0x180007d04  mov     [r8], rax
0x180007d07  test    edx, edx
0x180007d09  js      loc_180007EE8
0x180007d0f  mov     rcx, [rsp+0D8h+var_B8]
0x180007d14  cmp     word ptr [r14+rcx*2-2], 5Ch ; '\'
0x180007d1b  jz      short loc_180007D34
0x180007d1d  mov     eax, 5Ch ; '\'
0x180007d22  mov     [r14+rcx*2], ax
0x180007d27  inc     rcx
0x180007d2a  mov     [rsp+0D8h+var_B8], rcx
0x180007d2f  mov     [r14+rcx*2], r10w
0x180007d34  xor     edx, edx; dwFlags
0x180007d36  mov     r8d, 64h ; 'd'; dwBytes
0x180007d3c  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x180007d43  call    cs:__imp_HeapAlloc
0x180007d4a  nop     dword ptr [rax+rax+00h]
0x180007d4f  mov     r15, rax
0x180007d52  mov     [rsp+0D8h+var_A8], rax
0x180007d57  test    rax, rax
0x180007d5a  jz      loc_180007E91
0x180007d60  mov     r8d, 32h ; '2'; cchBufferLength
0x180007d66  mov     rdx, rax; lpszVolumeName
0x180007d69  mov     rcx, r14; lpszVolumeMountPoint
0x180007d6c  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180007d73  nop     dword ptr [rax+rax+00h]
0x180007d78  test    eax, eax
0x180007d7a  jz      loc_180007E34
0x180007d80  lea     r8, [rsp+0D8h+var_B8]
0x180007d85  test    r15, r15
0x180007d88  jz      loc_180007EF7
0x180007d8e  mov     rax, r12
0x180007d91  mov     [rsp+0D8h+var_48], rax
0x180007d99  mov     rcx, r15
0x180007d9c  mov     [rsp+0D8h+var_50], rcx
0x180007da4  xor     edx, edx
0x180007da6  test    rax, rax
0x180007da9  jz      short loc_180007DCC
0x180007dab  cmp     [rcx], dx
0x180007dae  jz      short loc_180007DC9
0x180007db0  add     rcx, 2
0x180007db4  mov     [rsp+0D8h+var_50], rcx
0x180007dbc  dec     rax
0x180007dbf  mov     [rsp+0D8h+var_48], rax
0x180007dc7  jmp     short loc_180007DA6
0x180007dc9  test    rax, rax
0x180007dcc  cmovz   edx, esi
0x180007dcf  test    edx, edx
0x180007dd1  js      loc_180007E85
0x180007dd7  sub     r12, rax
0x180007dda  mov     [r8], r12
0x180007ddd  test    edx, edx
0x180007ddf  js      loc_180007E98
0x180007de5  mov     rax, [rsp+0D8h+var_B8]
0x180007dea  cmp     rax, 2
0x180007dee  jb      loc_180007EFB
0x180007df4  lea     rcx, [r15+rax*2]
0x180007df8  cmp     word ptr [rcx-2], 5Ch ; '\'
0x180007dfd  jnz     short loc_180007E05
0x180007dff  xor     eax, eax
0x180007e01  mov     [rcx-2], ax
0x180007e05  mov     [r13+0], r15
0x180007e09  xor     r15d, r15d
0x180007e0c  mov     [rsp+0D8h+var_A8], r15
0x180007e11  xor     esi, esi
0x180007e13  jmp     loc_180007EFB
0x180007e18  sub     rcx, 2
0x180007e1c  mov     [rsp+0D8h+var_98], rcx
0x180007e21  dec     rdx
0x180007e24  mov     [rsp+0D8h+var_90], rdx
0x180007e29  mov     r9d, 8007007Ah
0x180007e2f  jmp     loc_180007CA1
0x180007e34  mov     r8, r15; lpMem
0x180007e37  xor     edx, edx; dwFlags
0x180007e39  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x180007e40  call    cs:__imp_HeapFree
0x180007e47  nop     dword ptr [rax+rax+00h]
0x180007e4c  test    eax, eax
0x180007e4e  jz      loc_180007EED
0x180007e54  mov     r15, r14
0x180007e57  mov     [rsp+0D8h+var_A8], r14
0x180007e5c  xor     r14d, r14d
0x180007e5f  mov     [rsp+0D8h+var_A0], r14
0x180007e64  jmp     loc_180007D80
0x180007e69  mov     esi, r9d
0x180007e6c  jmp     loc_180007EFB
0x180007e71  mov     qword ptr [r8], 0
0x180007e78  jmp     loc_180007BA9
0x180007e7d  mov     [r8], r10
0x180007e80  jmp     loc_180007D07
0x180007e85  mov     qword ptr [r8], 0
0x180007e8c  jmp     loc_180007DDD
0x180007e91  mov     esi, 8007000Eh
0x180007e96  jmp     short loc_180007EFB
0x180007e98  mov     qword ptr [r8], 0
0x180007e9f  test    edx, edx
0x180007ea1  jns     loc_180007DE5
0x180007ea7  mov     esi, edx
0x180007ea9  jmp     short loc_180007EFB
0x180007eab  mov     qword ptr [r8], 0
0x180007eb2  test    edx, edx
0x180007eb4  js      short loc_180007EA7
0x180007eb6  jmp     loc_180007BB1
0x180007ebb  mov     esi, 80070057h
0x180007ec0  mov     edx, esi
0x180007ec2  jmp     short loc_180007EAB
0x180007ec4  mov     esi, 8007000Eh
0x180007ec9  jmp     short loc_180007EFB
0x180007ecb  mov     r9d, esi
0x180007ece  jmp     loc_180007C1B
0x180007ed3  test    rbx, rbx
0x180007ed6  jz      loc_180007CAC
0x180007edc  mov     eax, r10d
0x180007edf  mov     [r14], ax
0x180007ee3  jmp     loc_180007CAC
0x180007ee8  mov     [r8], r10
0x180007eeb  jmp     short loc_180007EA7
0x180007eed  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x180007ef2  jmp     loc_180007E54
0x180007ef7  mov     edx, esi
0x180007ef9  jmp     short loc_180007E98
0x180007efb  test    r15, r15
0x180007efe  jnz     short loc_180007F66
0x180007f00  test    r14, r14
0x180007f03  jz      short loc_180007F21
0x180007f05  mov     r8, r14; lpMem
0x180007f08  xor     edx, edx; dwFlags
0x180007f0a  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x180007f11  call    cs:__imp_HeapFree
0x180007f18  nop     dword ptr [rax+rax+00h]
0x180007f1d  test    eax, eax
0x180007f1f  jz      short loc_180007F70
0x180007f21  xor     edx, edx; OldMode
0x180007f23  mov     ecx, [rsp+0D8h+NewMode]; NewMode
0x180007f2a  call    cs:__imp_RtlSetThreadErrorMode
0x180007f31  nop     dword ptr [rax+rax+00h]
0x180007f36  mov     eax, esi
0x180007f38  mov     rcx, [rsp+0D8h+var_38]
0x180007f40  xor     rcx, rsp; StackCookie
0x180007f43  call    __security_check_cookie
0x180007f48  lea     r11, [rsp+0D8h+var_28]
0x180007f50  mov     rbx, [r11+30h]
0x180007f54  mov     rsi, [r11+40h]
0x180007f58  mov     rsp, r11
0x180007f5b  pop     r15
0x180007f5d  pop     r14
0x180007f5f  pop     r13
0x180007f61  pop     r12
0x180007f63  pop     rdi
0x180007f64  retn
0x180007f66  mov     rcx, r15; lpMem
0x180007f69  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180007f6e  jmp     short loc_180007F00
0x180007f70  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x180007f75  jmp     short loc_180007F21
0x18011f450  push    rbp
0x18011f452  sub     rsp, 20h
0x18011f456  mov     rbp, rdx
0x18011f459  mov     rcx, [rbp+30h]; lpMem
0x18011f45d  test    rcx, rcx
0x18011f460  jz      short loc_18011F46F
0x18011f462  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18011f467  mov     qword ptr [rbp+30h], 0
0x18011f46f  mov     rcx, [rbp+38h]; lpMem
0x18011f473  test    rcx, rcx
0x18011f476  jz      short loc_18011F485
  ... truncated ...
```

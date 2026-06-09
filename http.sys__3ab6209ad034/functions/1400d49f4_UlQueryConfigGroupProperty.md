# UlQueryConfigGroupProperty

- ea: `0x1400d49f4`
- end: `0x1400d4d41`
- name: `UlQueryConfigGroupProperty`
- size: `845`
- prototype: `__int64 __usercall@<rax>(PIRP Irp@<rcx>, int@<edx>, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400f1310`

## callees

- `0x14000a350`
- `0x1400193f8`
- `0x140074ad8`
- `0x1400d49f4`
- `0x1400ef04c`
- `0x1401433d8`
- `0x1401439cc`
- `0x1401c9590`
- `0x1401da4fc`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400d4b90`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d4ba6`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d4bc2`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d4b90`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d4ba6`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d4bc2`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d4a92`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d4a92`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d4ce8`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d4ce8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d4cf4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d4cf4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d4a7d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d4a7d`

## pseudocode

```c
__int64 __fastcall UlQueryConfigGroupProperty(
        PIRP Irp,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        _DWORD *a8)
{
  int v9; // esi
  __int64 v13; // rbx
  __int64 ObjectFromOpaqueId; // rax
  volatile signed __int32 *v15; // rsi
  __int64 v16; // rcx
  unsigned int v17; // ebx
  int v18; // edi
  int v19; // edi
  int v20; // edi
  unsigned int v21; // eax
  __int64 v22; // rax
  int v23; // edi
  int v24; // edi
  int v25; // edi
  int v26; // eax
  int v28; // [rsp+20h] [rbp-88h]
  __int64 v29; // [rsp+E8h] [rbp+40h]

  v9 = a3;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqiLqLqq(1028, 122, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, Irp, a2, a3, a4, a5, a6, a7, a8);
  *a8 = 0;
  v13 = *(_QWORD *)(a2 + 56);
  KeEnterCriticalRegion();
  v29 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v13 + 1368), 0);
  ObjectFromOpaqueId = UxGetObjectFromOpaqueId(
                         v9,
                         2,
                         (unsigned int)UlReferenceServerSession,
                         (unsigned int)UlValidateConfigGroup,
                         a2);
  v15 = (volatile signed __int32 *)ObjectFromOpaqueId;
  if ( !ObjectFromOpaqueId || *(_DWORD *)ObjectFromOpaqueId != 1245932629 )
  {
    v17 = -1073741811;
    if ( !ObjectFromOpaqueId )
      goto LABEL_45;
    goto LABEL_40;
  }
  v16 = *(unsigned int *)(*(_QWORD *)(ObjectFromOpaqueId + 48) + 16LL);
  if ( (_WORD)v16 == 1 )
  {
    v16 = WORD1(v16);
    if ( !(_WORD)v16 )
    {
      v17 = -1073741637;
      goto LABEL_40;
    }
  }
  v17 = 0;
  if ( a4 > 9 )
  {
    v23 = a4 - 10;
    if ( !v23 )
    {
      v21 = UlCopyChannelBindConfigToIrp(*(_QWORD *)(a2 + 56), ObjectFromOpaqueId + 384, Irp, a8);
      goto LABEL_16;
    }
    v24 = v23 - 1;
    if ( v24 )
    {
      v25 = v24 - 7;
      if ( v25 )
      {
        if ( v25 != 1 || !UxKirBrHttpQuerySocketTtl || a6 < 0x10 )
          goto LABEL_18;
        *(_OWORD *)a5 = *(_OWORD *)(ObjectFromOpaqueId + 464);
        *a8 = 16;
        goto LABEL_40;
      }
      if ( a6 < 8 )
        goto LABEL_18;
      v22 = *(_QWORD *)(ObjectFromOpaqueId + 456);
    }
    else
    {
      if ( a6 < 8 )
        goto LABEL_18;
      v22 = *(_QWORD *)(ObjectFromOpaqueId + 440);
    }
LABEL_20:
    *(_QWORD *)a5 = v22;
    *a8 = 8;
    goto LABEL_40;
  }
  if ( a4 == 9 )
  {
    if ( a6 < 8 )
      goto LABEL_18;
    v22 = *(_QWORD *)(ObjectFromOpaqueId + 292);
    goto LABEL_20;
  }
  if ( !a4 )
  {
LABEL_15:
    v21 = UlCopyAuthConfigToIrp(v16, ObjectFromOpaqueId + 304, Irp, a8);
LABEL_16:
    v17 = v21;
    goto LABEL_40;
  }
  v18 = a4 - 2;
  if ( !v18 )
  {
    IoIs32bitProcess(Irp);
    if ( *(_DWORD *)a5 <= 1u )
    {
      IoIs32bitProcess(Irp);
      v21 = UlCopyQosSettingInfo(Irp, v28, a7, a5, a6, (__int64)a8);
      goto LABEL_16;
    }
    goto LABEL_18;
  }
  v19 = v18 - 1;
  if ( v19 )
  {
    v20 = v19 - 2;
    if ( v20 )
    {
      if ( v20 == 3 )
        goto LABEL_15;
      goto LABEL_18;
    }
    if ( a6 < 8 )
    {
LABEL_18:
      v17 = -1073741811;
      goto LABEL_40;
    }
    v22 = *(_QWORD *)(ObjectFromOpaqueId + 56);
    goto LABEL_20;
  }
  if ( a6 < 0x14 )
    goto LABEL_18;
  *(_OWORD *)a5 = *(_OWORD *)(ObjectFromOpaqueId + 272);
  *(_DWORD *)(a5 + 16) = *(_DWORD *)(ObjectFromOpaqueId + 288);
  *a8 = 20;
LABEL_40:
  v26 = _InterlockedDecrement(v15 + 1);
  if ( UxDebugCheckRefcount && v26 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v15 + 1), 0xBu, v26);
  if ( !v26 )
    UlFreeConfigGroup((PVOID)v15);
LABEL_45:
  ExReleaseCacheAwarePushLockSharedEx(v29, 0);
  KeLeaveCriticalRegion();
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qLd(1028, 123, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, a5, *a8, v17);
  return v17;
}

```

## disassembly

```asm
0x1400d49f4  mov     r11, rsp
0x1400d49f7  push    rbx
0x1400d49f8  push    rbp
0x1400d49f9  push    rsi
0x1400d49fa  push    rdi
0x1400d49fb  push    r12
0x1400d49fd  push    r13
0x1400d49ff  push    r14
0x1400d4a01  push    r15
0x1400d4a03  sub     rsp, 68h
0x1400d4a07  mov     edi, r9d
0x1400d4a0a  mov     rsi, r8
0x1400d4a0d  mov     r13, rdx
0x1400d4a10  mov     r12, rcx
0x1400d4a13  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d4a1a  mov     r14, [rsp+0A8h+arg_38]
0x1400d4a22  mov     ebp, [rsp+0A8h+arg_28]
0x1400d4a29  mov     r15, [rsp+0A8h+arg_20]
0x1400d4a31  jz      short loc_1400D4A72
0x1400d4a33  mov     rax, [rsp+0A8h+arg_30]
0x1400d4a3b  mov     edx, 7Ah ; 'z'
0x1400d4a40  mov     [r11-58h], r14
0x1400d4a44  mov     ecx, 404h
0x1400d4a49  mov     [r11-60h], rax
0x1400d4a4d  mov     dword ptr [rsp+0A8h+var_68], ebp
0x1400d4a51  mov     [r11-70h], r15
0x1400d4a55  mov     dword ptr [rsp+0A8h+var_78], r9d
0x1400d4a5a  mov     r9, r12
0x1400d4a5d  mov     [r11-80h], r8
0x1400d4a61  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400d4a68  mov     qword ptr [rsp+0A8h+var_88], r13
0x1400d4a6d  call    WPP_SF_qqiLqLqq
0x1400d4a72  mov     dword ptr [r14], 0
0x1400d4a79  mov     rbx, [r13+38h]
0x1400d4a7d  call    cs:__imp_KeEnterCriticalRegion
0x1400d4a84  nop     dword ptr [rax+rax+00h]
0x1400d4a89  mov     rcx, [rbx+558h]
0x1400d4a90  xor     edx, edx
0x1400d4a92  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400d4a99  nop     dword ptr [rax+rax+00h]
0x1400d4a9e  lea     r9, UlValidateConfigGroup
0x1400d4aa5  mov     qword ptr [rsp+0A8h+var_88], r13; int
0x1400d4aaa  lea     r8, UlReferenceServerSession
0x1400d4ab1  mov     [rsp+0A8h+arg_38], rax
0x1400d4ab9  mov     edx, 2
0x1400d4abe  mov     rcx, rsi
0x1400d4ac1  call    UxGetObjectFromOpaqueId
0x1400d4ac6  mov     rsi, rax
0x1400d4ac9  test    rax, rax
0x1400d4acc  jz      loc_1400D4C9B
0x1400d4ad2  cmp     dword ptr [rax], 4A436C55h
0x1400d4ad8  jnz     loc_1400D4C9B
0x1400d4ade  mov     rcx, [rax+30h]
0x1400d4ae2  mov     eax, 1
0x1400d4ae7  mov     ecx, [rcx+10h]
0x1400d4aea  cmp     ax, cx
0x1400d4aed  jnz     short loc_1400D4B03
0x1400d4aef  shr     ecx, 10h
0x1400d4af2  xor     eax, eax
0x1400d4af4  cmp     ax, cx
0x1400d4af7  jnz     short loc_1400D4B03
0x1400d4af9  mov     ebx, 0C00000BBh
0x1400d4afe  jmp     loc_1400D4CA5
0x1400d4b03  xor     ebx, ebx
0x1400d4b05  cmp     edi, 9
0x1400d4b08  jg      loc_1400D4C14
0x1400d4b0e  jz      loc_1400D4BFF
0x1400d4b14  test    edi, edi
0x1400d4b16  jz      short loc_1400D4B2C
0x1400d4b18  sub     edi, 2
0x1400d4b1b  jz      short loc_1400D4B8D
0x1400d4b1d  sub     edi, 1
0x1400d4b20  jz      short loc_1400D4B67
0x1400d4b22  sub     edi, 2
0x1400d4b25  jz      short loc_1400D4B45
0x1400d4b27  cmp     edi, 3
0x1400d4b2a  jnz     short loc_1400D4B4A
0x1400d4b2c  lea     rdx, [rsi+130h]
0x1400d4b33  mov     r9, r14
0x1400d4b36  mov     r8, r12
0x1400d4b39  call    UlCopyAuthConfigToIrp
0x1400d4b3e  mov     ebx, eax
0x1400d4b40  jmp     loc_1400D4CA5
0x1400d4b45  cmp     ebp, 8
0x1400d4b48  jnb     short loc_1400D4B54
0x1400d4b4a  mov     ebx, 0C000000Dh
0x1400d4b4f  jmp     loc_1400D4CA5
0x1400d4b54  mov     rax, [rsi+38h]
0x1400d4b58  mov     [r15], rax
0x1400d4b5b  mov     dword ptr [r14], 8
0x1400d4b62  jmp     loc_1400D4CA5
0x1400d4b67  cmp     ebp, 14h
0x1400d4b6a  jb      short loc_1400D4B4A
0x1400d4b6c  movups  xmm0, xmmword ptr [rsi+110h]
0x1400d4b73  movups  xmmword ptr [r15], xmm0
0x1400d4b77  mov     eax, [rsi+120h]
0x1400d4b7d  mov     [r15+10h], eax
0x1400d4b81  mov     dword ptr [r14], 14h
0x1400d4b88  jmp     loc_1400D4CA5
0x1400d4b8d  mov     rcx, r12; Irp
0x1400d4b90  call    cs:__imp_IoIs32bitProcess
0x1400d4b97  nop     dword ptr [rax+rax+00h]
0x1400d4b9c  mov     eax, [r15]
0x1400d4b9f  test    eax, eax
0x1400d4ba1  jnz     short loc_1400D4BBA
0x1400d4ba3  mov     rcx, r12; Irp
0x1400d4ba6  call    cs:__imp_IoIs32bitProcess
0x1400d4bad  nop     dword ptr [rax+rax+00h]
0x1400d4bb2  lea     r8, [rsi+50h]
0x1400d4bb6  xor     edx, edx
0x1400d4bb8  jmp     short loc_1400D4BD7
0x1400d4bba  cmp     eax, 1
0x1400d4bbd  jnz     short loc_1400D4B4A
0x1400d4bbf  mov     rcx, r12; Irp
0x1400d4bc2  call    cs:__imp_IoIs32bitProcess
0x1400d4bc9  nop     dword ptr [rax+rax+00h]
0x1400d4bce  lea     r8, [rsi+68h]
0x1400d4bd2  mov     edx, 1
0x1400d4bd7  mov     rax, [rsp+0A8h+arg_30]
0x1400d4bdf  mov     rcx, r12; Irp
0x1400d4be2  mov     [rsp+0A8h+var_68], r14; __int64
0x1400d4be7  mov     [rsp+0A8h+var_70], ebp; int
0x1400d4beb  mov     [rsp+0A8h+var_78], r15; __int64
0x1400d4bf0  mov     [rsp+0A8h+var_80], rax; __int64
0x1400d4bf5  call    UlCopyQosSettingInfo
0x1400d4bfa  jmp     loc_1400D4B3E
0x1400d4bff  cmp     ebp, 8
0x1400d4c02  jb      loc_1400D4B4A
0x1400d4c08  mov     rax, [rsi+124h]
0x1400d4c0f  jmp     loc_1400D4B58
0x1400d4c14  sub     edi, 0Ah
0x1400d4c17  jz      short loc_1400D4C80
0x1400d4c19  sub     edi, 1
0x1400d4c1c  jz      short loc_1400D4C6B
0x1400d4c1e  sub     edi, 7
0x1400d4c21  jz      short loc_1400D4C56
0x1400d4c23  cmp     edi, 1
0x1400d4c26  jnz     loc_1400D4B4A
0x1400d4c2c  cmp     cs:UxKirBrHttpQuerySocketTtl, bl
0x1400d4c32  jz      loc_1400D4B4A
0x1400d4c38  cmp     ebp, 10h
0x1400d4c3b  jb      loc_1400D4B4A
0x1400d4c41  movups  xmm0, xmmword ptr [rsi+1D0h]
0x1400d4c48  movdqu  xmmword ptr [r15], xmm0
0x1400d4c4d  mov     dword ptr [r14], 10h
0x1400d4c54  jmp     short loc_1400D4CA5
0x1400d4c56  cmp     ebp, 8
0x1400d4c59  jb      loc_1400D4B4A
0x1400d4c5f  mov     rax, [rsi+1C8h]
0x1400d4c66  jmp     loc_1400D4B58
0x1400d4c6b  cmp     ebp, 8
0x1400d4c6e  jb      loc_1400D4B4A
0x1400d4c74  mov     rax, [rsi+1B8h]
0x1400d4c7b  jmp     loc_1400D4B58
0x1400d4c80  mov     rcx, [r13+38h]
0x1400d4c84  lea     rdx, [rsi+180h]
0x1400d4c8b  mov     r9, r14
0x1400d4c8e  mov     r8, r12
0x1400d4c91  call    UlCopyChannelBindConfigToIrp
0x1400d4c96  jmp     loc_1400D4B3E
0x1400d4c9b  mov     ebx, 0C000000Dh
0x1400d4ca0  test    rsi, rsi
0x1400d4ca3  jz      short loc_1400D4CDE
0x1400d4ca5  lea     rdx, [rsi+4]; BugCheckParameter2
0x1400d4ca9  or      eax, 0FFFFFFFFh
0x1400d4cac  lock xadd [rdx], eax
0x1400d4cb0  dec     eax
0x1400d4cb2  cmp     cs:UxDebugCheckRefcount, 0
0x1400d4cb9  jz      short loc_1400D4CD2
0x1400d4cbb  cmp     eax, 0FFFFFFFFh
0x1400d4cbe  jg      short loc_1400D4CD2
0x1400d4cc0  mov     ecx, 3; BugCheckParameter1
0x1400d4cc5  movsxd  r9, eax; BugCheckParameter4
0x1400d4cc8  lea     r8d, [rcx+8]; BugCheckParameter3
0x1400d4ccc  call    UlBugCheckEx
0x1400d4cd2  test    eax, eax
0x1400d4cd4  jnz     short loc_1400D4CDE
0x1400d4cd6  mov     rcx, rsi; P
0x1400d4cd9  call    UlFreeConfigGroup
0x1400d4cde  mov     rcx, [rsp+0A8h+arg_38]
0x1400d4ce6  xor     edx, edx
0x1400d4ce8  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400d4cef  nop     dword ptr [rax+rax+00h]
0x1400d4cf4  call    cs:__imp_KeLeaveCriticalRegion
0x1400d4cfb  nop     dword ptr [rax+rax+00h]
0x1400d4d00  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d4d07  jz      short loc_1400D4D2D
0x1400d4d09  mov     eax, [r14]
0x1400d4d0c  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400d4d13  mov     edx, 7Bh ; '{'
0x1400d4d18  mov     dword ptr [rsp+0A8h+var_80], ebx
0x1400d4d1c  mov     ecx, 404h
0x1400d4d21  mov     [rsp+0A8h+var_88], eax
0x1400d4d25  mov     r9, r15
0x1400d4d28  call    WPP_SF_qLd
0x1400d4d2d  mov     eax, ebx
0x1400d4d2f  add     rsp, 68h
0x1400d4d33  pop     r15
0x1400d4d35  pop     r14
0x1400d4d37  pop     r13
0x1400d4d39  pop     r12
0x1400d4d3b  pop     rdi
0x1400d4d3c  pop     rsi
0x1400d4d3d  pop     rbp
0x1400d4d3e  pop     rbx
0x1400d4d3f  retn
```

# UlQueryConfigGroupProperty

- ea: `0x1400d4ad4`
- end: `0x1400d4e21`
- name: `UlQueryConfigGroupProperty`
- size: `845`
- prototype: `__int64 __usercall@<rax>(PIRP Irp@<rcx>, int@<edx>, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400f12e0`

## callees

- `0x14000a350`
- `0x1400193f8`
- `0x140074af8`
- `0x1400d4ad4`
- `0x1400ef01c`
- `0x1401432e8`
- `0x1401438dc`
- `0x1401c9590`
- `0x1401da4fc`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400d4c70`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d4c86`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d4ca2`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d4c70`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d4c86`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d4ca2`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d4b72`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d4b72`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d4dc8`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d4dc8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d4dd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d4dd4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d4b5d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d4b5d`

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
    WPP_SF_qqiLqLqq(1028, 122, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, Irp, a2, a3, a4, a5, a6, a7, a8);
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
    WPP_SF_qLd(1028, 123, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, a5, *a8, v17);
  return v17;
}

```

## disassembly

```asm
0x1400d4ad4  mov     r11, rsp
0x1400d4ad7  push    rbx
0x1400d4ad8  push    rbp
0x1400d4ad9  push    rsi
0x1400d4ada  push    rdi
0x1400d4adb  push    r12
0x1400d4add  push    r13
0x1400d4adf  push    r14
0x1400d4ae1  push    r15
0x1400d4ae3  sub     rsp, 68h
0x1400d4ae7  mov     edi, r9d
0x1400d4aea  mov     rsi, r8
0x1400d4aed  mov     r13, rdx
0x1400d4af0  mov     r12, rcx
0x1400d4af3  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d4afa  mov     r14, [rsp+0A8h+arg_38]
0x1400d4b02  mov     ebp, [rsp+0A8h+arg_28]
0x1400d4b09  mov     r15, [rsp+0A8h+arg_20]
0x1400d4b11  jz      short loc_1400D4B52
0x1400d4b13  mov     rax, [rsp+0A8h+arg_30]
0x1400d4b1b  mov     edx, 7Ah ; 'z'
0x1400d4b20  mov     [r11-58h], r14
0x1400d4b24  mov     ecx, 404h
0x1400d4b29  mov     [r11-60h], rax
0x1400d4b2d  mov     dword ptr [rsp+0A8h+var_68], ebp
0x1400d4b31  mov     [r11-70h], r15
0x1400d4b35  mov     dword ptr [rsp+0A8h+var_78], r9d
0x1400d4b3a  mov     r9, r12
0x1400d4b3d  mov     [r11-80h], r8
0x1400d4b41  lea     r8, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids
0x1400d4b48  mov     qword ptr [rsp+0A8h+var_88], r13
0x1400d4b4d  call    WPP_SF_qqiLqLqq
0x1400d4b52  mov     dword ptr [r14], 0
0x1400d4b59  mov     rbx, [r13+38h]
0x1400d4b5d  call    cs:__imp_KeEnterCriticalRegion
0x1400d4b64  nop     dword ptr [rax+rax+00h]
0x1400d4b69  mov     rcx, [rbx+558h]
0x1400d4b70  xor     edx, edx
0x1400d4b72  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400d4b79  nop     dword ptr [rax+rax+00h]
0x1400d4b7e  lea     r9, UlValidateConfigGroup
0x1400d4b85  mov     qword ptr [rsp+0A8h+var_88], r13; int
0x1400d4b8a  lea     r8, UlReferenceServerSession
0x1400d4b91  mov     [rsp+0A8h+arg_38], rax
0x1400d4b99  mov     edx, 2
0x1400d4b9e  mov     rcx, rsi
0x1400d4ba1  call    UxGetObjectFromOpaqueId
0x1400d4ba6  mov     rsi, rax
0x1400d4ba9  test    rax, rax
0x1400d4bac  jz      loc_1400D4D7B
0x1400d4bb2  cmp     dword ptr [rax], 4A436C55h
0x1400d4bb8  jnz     loc_1400D4D7B
0x1400d4bbe  mov     rcx, [rax+30h]
0x1400d4bc2  mov     eax, 1
0x1400d4bc7  mov     ecx, [rcx+10h]
0x1400d4bca  cmp     ax, cx
0x1400d4bcd  jnz     short loc_1400D4BE3
0x1400d4bcf  shr     ecx, 10h
0x1400d4bd2  xor     eax, eax
0x1400d4bd4  cmp     ax, cx
0x1400d4bd7  jnz     short loc_1400D4BE3
0x1400d4bd9  mov     ebx, 0C00000BBh
0x1400d4bde  jmp     loc_1400D4D85
0x1400d4be3  xor     ebx, ebx
0x1400d4be5  cmp     edi, 9
0x1400d4be8  jg      loc_1400D4CF4
0x1400d4bee  jz      loc_1400D4CDF
0x1400d4bf4  test    edi, edi
0x1400d4bf6  jz      short loc_1400D4C0C
0x1400d4bf8  sub     edi, 2
0x1400d4bfb  jz      short loc_1400D4C6D
0x1400d4bfd  sub     edi, 1
0x1400d4c00  jz      short loc_1400D4C47
0x1400d4c02  sub     edi, 2
0x1400d4c05  jz      short loc_1400D4C25
0x1400d4c07  cmp     edi, 3
0x1400d4c0a  jnz     short loc_1400D4C2A
0x1400d4c0c  lea     rdx, [rsi+130h]
0x1400d4c13  mov     r9, r14
0x1400d4c16  mov     r8, r12
0x1400d4c19  call    UlCopyAuthConfigToIrp
0x1400d4c1e  mov     ebx, eax
0x1400d4c20  jmp     loc_1400D4D85
0x1400d4c25  cmp     ebp, 8
0x1400d4c28  jnb     short loc_1400D4C34
0x1400d4c2a  mov     ebx, 0C000000Dh
0x1400d4c2f  jmp     loc_1400D4D85
0x1400d4c34  mov     rax, [rsi+38h]
0x1400d4c38  mov     [r15], rax
0x1400d4c3b  mov     dword ptr [r14], 8
0x1400d4c42  jmp     loc_1400D4D85
0x1400d4c47  cmp     ebp, 14h
0x1400d4c4a  jb      short loc_1400D4C2A
0x1400d4c4c  movups  xmm0, xmmword ptr [rsi+110h]
0x1400d4c53  movups  xmmword ptr [r15], xmm0
0x1400d4c57  mov     eax, [rsi+120h]
0x1400d4c5d  mov     [r15+10h], eax
0x1400d4c61  mov     dword ptr [r14], 14h
0x1400d4c68  jmp     loc_1400D4D85
0x1400d4c6d  mov     rcx, r12; Irp
0x1400d4c70  call    cs:__imp_IoIs32bitProcess
0x1400d4c77  nop     dword ptr [rax+rax+00h]
0x1400d4c7c  mov     eax, [r15]
0x1400d4c7f  test    eax, eax
0x1400d4c81  jnz     short loc_1400D4C9A
0x1400d4c83  mov     rcx, r12; Irp
0x1400d4c86  call    cs:__imp_IoIs32bitProcess
0x1400d4c8d  nop     dword ptr [rax+rax+00h]
0x1400d4c92  lea     r8, [rsi+50h]
0x1400d4c96  xor     edx, edx
0x1400d4c98  jmp     short loc_1400D4CB7
0x1400d4c9a  cmp     eax, 1
0x1400d4c9d  jnz     short loc_1400D4C2A
0x1400d4c9f  mov     rcx, r12; Irp
0x1400d4ca2  call    cs:__imp_IoIs32bitProcess
0x1400d4ca9  nop     dword ptr [rax+rax+00h]
0x1400d4cae  lea     r8, [rsi+68h]
0x1400d4cb2  mov     edx, 1
0x1400d4cb7  mov     rax, [rsp+0A8h+arg_30]
0x1400d4cbf  mov     rcx, r12; Irp
0x1400d4cc2  mov     [rsp+0A8h+var_68], r14; __int64
0x1400d4cc7  mov     [rsp+0A8h+var_70], ebp; int
0x1400d4ccb  mov     [rsp+0A8h+var_78], r15; __int64
0x1400d4cd0  mov     [rsp+0A8h+var_80], rax; __int64
0x1400d4cd5  call    UlCopyQosSettingInfo
0x1400d4cda  jmp     loc_1400D4C1E
0x1400d4cdf  cmp     ebp, 8
0x1400d4ce2  jb      loc_1400D4C2A
0x1400d4ce8  mov     rax, [rsi+124h]
0x1400d4cef  jmp     loc_1400D4C38
0x1400d4cf4  sub     edi, 0Ah
0x1400d4cf7  jz      short loc_1400D4D60
0x1400d4cf9  sub     edi, 1
0x1400d4cfc  jz      short loc_1400D4D4B
0x1400d4cfe  sub     edi, 7
0x1400d4d01  jz      short loc_1400D4D36
0x1400d4d03  cmp     edi, 1
0x1400d4d06  jnz     loc_1400D4C2A
0x1400d4d0c  cmp     cs:UxKirBrHttpQuerySocketTtl, bl
0x1400d4d12  jz      loc_1400D4C2A
0x1400d4d18  cmp     ebp, 10h
0x1400d4d1b  jb      loc_1400D4C2A
0x1400d4d21  movups  xmm0, xmmword ptr [rsi+1D0h]
0x1400d4d28  movdqu  xmmword ptr [r15], xmm0
0x1400d4d2d  mov     dword ptr [r14], 10h
0x1400d4d34  jmp     short loc_1400D4D85
0x1400d4d36  cmp     ebp, 8
0x1400d4d39  jb      loc_1400D4C2A
0x1400d4d3f  mov     rax, [rsi+1C8h]
0x1400d4d46  jmp     loc_1400D4C38
0x1400d4d4b  cmp     ebp, 8
0x1400d4d4e  jb      loc_1400D4C2A
0x1400d4d54  mov     rax, [rsi+1B8h]
0x1400d4d5b  jmp     loc_1400D4C38
0x1400d4d60  mov     rcx, [r13+38h]
0x1400d4d64  lea     rdx, [rsi+180h]
0x1400d4d6b  mov     r9, r14
0x1400d4d6e  mov     r8, r12
0x1400d4d71  call    UlCopyChannelBindConfigToIrp
0x1400d4d76  jmp     loc_1400D4C1E
0x1400d4d7b  mov     ebx, 0C000000Dh
0x1400d4d80  test    rsi, rsi
0x1400d4d83  jz      short loc_1400D4DBE
0x1400d4d85  lea     rdx, [rsi+4]; BugCheckParameter2
0x1400d4d89  or      eax, 0FFFFFFFFh
0x1400d4d8c  lock xadd [rdx], eax
0x1400d4d90  dec     eax
0x1400d4d92  cmp     cs:UxDebugCheckRefcount, 0
0x1400d4d99  jz      short loc_1400D4DB2
0x1400d4d9b  cmp     eax, 0FFFFFFFFh
0x1400d4d9e  jg      short loc_1400D4DB2
0x1400d4da0  mov     ecx, 3; BugCheckParameter1
0x1400d4da5  movsxd  r9, eax; BugCheckParameter4
0x1400d4da8  lea     r8d, [rcx+8]; BugCheckParameter3
0x1400d4dac  call    UlBugCheckEx
0x1400d4db2  test    eax, eax
0x1400d4db4  jnz     short loc_1400D4DBE
0x1400d4db6  mov     rcx, rsi; P
0x1400d4db9  call    UlFreeConfigGroup
0x1400d4dbe  mov     rcx, [rsp+0A8h+arg_38]
0x1400d4dc6  xor     edx, edx
0x1400d4dc8  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400d4dcf  nop     dword ptr [rax+rax+00h]
0x1400d4dd4  call    cs:__imp_KeLeaveCriticalRegion
0x1400d4ddb  nop     dword ptr [rax+rax+00h]
0x1400d4de0  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d4de7  jz      short loc_1400D4E0D
0x1400d4de9  mov     eax, [r14]
0x1400d4dec  lea     r8, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids
0x1400d4df3  mov     edx, 7Bh ; '{'
0x1400d4df8  mov     dword ptr [rsp+0A8h+var_80], ebx
0x1400d4dfc  mov     ecx, 404h
0x1400d4e01  mov     [rsp+0A8h+var_88], eax
0x1400d4e05  mov     r9, r15
0x1400d4e08  call    WPP_SF_qLd
0x1400d4e0d  mov     eax, ebx
0x1400d4e0f  add     rsp, 68h
0x1400d4e13  pop     r15
0x1400d4e15  pop     r14
0x1400d4e17  pop     r13
0x1400d4e19  pop     r12
0x1400d4e1b  pop     rdi
0x1400d4e1c  pop     rsi
0x1400d4e1d  pop     rbp
0x1400d4e1e  pop     rbx
0x1400d4e1f  retn
```

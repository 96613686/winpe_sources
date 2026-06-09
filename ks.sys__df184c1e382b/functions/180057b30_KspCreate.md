# KspCreate

- ea: `0x180057b30`
- end: `0x180057e07`
- name: `KspCreate`
- size: `727`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, char, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800503f4`
- `0x18005653c`

## callees

- `0x18000b7bc`
- `0x180019cb0`
- `0x18001a000`
- `0x180048ae8`
- `0x180057b30`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x180057bbb`
- `ntoskrnl!ObfReferenceObject` at `0x180057bbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180057de9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180057de9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180057c2c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180057c99`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180057c2c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180057c99`

## pseudocode

```c
__int64 __fastcall KspCreate(__int64 a1, int a2, __int64 a3, __int64 a4, char a5, __int64 a6, __int64 a7)
{
  __int64 v8; // r13
  __int64 v10; // r12
  __int64 v11; // rsi
  _QWORD *v12; // rcx
  _QWORD **v13; // r14
  _QWORD *v14; // rbx
  unsigned int v15; // edi
  _QWORD *PoolWithTag; // rax
  _QWORD *v17; // rdi
  _QWORD *v18; // rax
  _QWORD *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rdx
  _QWORD *v22; // rdx

  LODWORD(v8) = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      10,
      (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids);
  }
  v10 = *(_QWORD *)(a1 + 184);
  v11 = v10 + 48;
  if ( a5 )
    ObfReferenceObject(*(PVOID *)(*(_QWORD *)v11 + 64LL));
  v12 = *(_QWORD **)(a7 + 8);
  if ( *v12 != a7 )
    __fastfail(3u);
  *(_QWORD *)(a6 + 16) = a7;
  *(_QWORD *)(a6 + 24) = v12;
  *v12 = a6 + 16;
  *(_QWORD *)(a7 + 8) = a6 + 16;
  *(_QWORD *)(a6 + 32) = a7;
  v13 = *(_QWORD ***)(*(_QWORD *)v11 + 24LL);
  if ( v13 )
  {
    v14 = *v13;
    if ( *v13 )
    {
      v15 = 0;
      goto LABEL_26;
    }
  }
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x88u, 0x686F534Bu);
  v14 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
LABEL_15:
      *v14 = a4;
      v17 = v14 + 1;
      v14[15] = 0;
      v14[2] = v14 + 1;
      v14[1] = v14 + 1;
      while ( (_DWORD)v8 )
      {
        v18 = ExAllocatePoolWithTag((POOL_TYPE)1025, 0x28u, 0x6563534Bu);
        v19 = v18;
        if ( ExPoolZeroingNativelySupported )
        {
          if ( !v18 )
          {
LABEL_33:
            FreeCreateEntries(v14 + 1, v18);
            ExFreePoolWithTag(v14, 0);
            goto LABEL_34;
          }
        }
        else
        {
          if ( !v18 )
            goto LABEL_33;
          *v18 = 0;
          v18[1] = 0;
        }
        v8 = (unsigned int)(v8 - 1);
        v18[3] = 0;
        v18[4] = 1;
        v18[2] = a3 + 48 * v8;
        v20 = *v17;
        if ( *(_QWORD **)(*v17 + 8LL) != v17 )
          __fastfail(3u);
        *v19 = v20;
        v19[1] = v17;
        *(_QWORD *)(v20 + 8) = v19;
        *v17 = v19;
      }
      v15 = 0;
      v14[3] = *(_QWORD *)(a1 + 120);
      v21 = *(_QWORD *)(a1 + 184);
      *((_DWORD *)v14 + 8) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v21 + 8) + 8LL) + 20LL);
      v14[9] = *(_QWORD *)(v21 + 40);
      v14[10] = 0;
      v14[11] = 0;
      *((_DWORD *)v14 + 26) = 0;
      v14[14] = 0;
      if ( !v13 )
      {
        v13 = (_QWORD **)(v14 + 15);
        *(_QWORD *)(*(_QWORD *)v11 + 24LL) = v14 + 15;
      }
      *v13 = v14;
LABEL_26:
      v14[14] = a6;
      v22 = **(_QWORD ***)(a6 + 128);
      if ( !v22 )
        return v15;
      if ( !*v22 )
        return v15;
      v15 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))*v22)(a6 + 128, a1, 0);
      if ( (v15 & 0x80000000) == 0 )
        return v15;
      goto LABEL_29;
    }
  }
  else if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, 0x88u);
    goto LABEL_15;
  }
LABEL_34:
  v15 = -1073741670;
  v14 = 0;
LABEL_29:
  *(_DWORD *)(a1 + 48) = -1073741802;
  if ( v14 )
    (*(void (__fastcall **)(_QWORD, __int64))(a4 + 32))(*(_QWORD *)(v10 + 40), a1);
  return v15;
}

```

## disassembly

```asm
0x180057b30  mov     r11, rsp
0x180057b33  mov     [r11+10h], rbx
0x180057b37  mov     [r11+20h], r9
0x180057b3b  mov     [r11+18h], r8
0x180057b3f  push    rbp
0x180057b40  push    rsi
0x180057b41  push    rdi
0x180057b42  push    r12
0x180057b44  push    r13
0x180057b46  push    r14
0x180057b48  push    r15
0x180057b4a  sub     rsp, 30h
0x180057b4e  mov     rdi, r9
0x180057b51  mov     r13d, edx
0x180057b54  mov     rbp, rcx
0x180057b57  lea     rax, WPP_RECORDER_INITIALIZED
0x180057b5e  xor     r8d, r8d
0x180057b61  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180057b68  jz      short loc_180057B99
0x180057b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180057b71  cmp     [rcx+48h], r8w
0x180057b76  jz      short loc_180057B99
0x180057b78  mov     rcx, [rcx+40h]
0x180057b7c  lea     r9d, [r8+0Ah]
0x180057b80  lea     rax, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x180057b87  mov     dl, 5
0x180057b89  lea     r8d, [r9-9]
0x180057b8d  mov     [r11-48h], rax
0x180057b91  call    WPP_RECORDER_SF_
0x180057b96  xor     r8d, r8d
0x180057b99  mov     r12, [rbp+0B8h]
0x180057ba0  mov     [rsp+68h+arg_0], r12
0x180057ba5  lea     rsi, [r12+30h]
0x180057baa  cmp     [rsp+68h+arg_20], r8b
0x180057bb2  jz      short loc_180057BCA
0x180057bb4  mov     rcx, [rsi]
0x180057bb7  mov     rcx, [rcx+40h]; Object
0x180057bbb  call    cs:__imp_ObfReferenceObject
0x180057bc2  nop     dword ptr [rax+rax+00h]
0x180057bc7  xor     r8d, r8d
0x180057bca  mov     rdx, [rsp+68h+arg_30]
0x180057bd2  mov     r15, [rsp+68h+arg_28]
0x180057bda  mov     rcx, [rdx+8]
0x180057bde  cmp     [rcx], rdx
0x180057be1  jz      short loc_180057BEA
0x180057be3  mov     ecx, 3
0x180057be8  int     29h; Win8: RtlFailFast(ecx)
0x180057bea  lea     rax, [r15+10h]
0x180057bee  mov     [rax], rdx
0x180057bf1  mov     [rax+8], rcx
0x180057bf5  mov     [rcx], rax
0x180057bf8  mov     [rdx+8], rax
0x180057bfc  mov     [r15+20h], rdx
0x180057c00  mov     rax, [rsi]
0x180057c03  mov     r14, [rax+18h]
0x180057c07  test    r14, r14
0x180057c0a  jz      short loc_180057C1C
0x180057c0c  mov     rbx, [r14]
0x180057c0f  test    rbx, rbx
0x180057c12  jz      short loc_180057C1C
0x180057c14  mov     edi, r8d
0x180057c17  jmp     loc_180057D6C
0x180057c1c  mov     edx, 88h; NumberOfBytes
0x180057c21  mov     ecx, 600h; PoolType
0x180057c26  mov     r8d, 686F534Bh; Tag
0x180057c2c  call    cs:__imp_ExAllocatePoolWithTag
0x180057c33  nop     dword ptr [rax+rax+00h]
0x180057c38  xor     r8d, r8d
0x180057c3b  mov     rbx, rax
0x180057c3e  cmp     cs:ExPoolZeroingNativelySupported, r8b
0x180057c45  jnz     short loc_180057C65
0x180057c47  test    rax, rax
0x180057c4a  jz      loc_180057DFD
0x180057c50  xor     edx, edx; Val
0x180057c52  mov     r8d, 88h; Size
0x180057c58  mov     rcx, rax; void *
0x180057c5b  call    memset
0x180057c60  xor     r8d, r8d
0x180057c63  jmp     short loc_180057C6E
0x180057c65  test    rbx, rbx
0x180057c68  jz      loc_180057DFD
0x180057c6e  mov     [rbx], rdi
0x180057c71  lea     r12, [rbx+78h]
0x180057c75  lea     rdi, [rbx+8]
0x180057c79  mov     [r12], r8
0x180057c7d  mov     [rdi+8], rdi
0x180057c81  mov     [rdi], rdi
0x180057c84  jmp     loc_180057D14
0x180057c89  mov     edx, 28h ; '('; NumberOfBytes
0x180057c8e  mov     ecx, 401h; PoolType
0x180057c93  mov     r8d, 6563534Bh; Tag
0x180057c99  call    cs:__imp_ExAllocatePoolWithTag
0x180057ca0  nop     dword ptr [rax+rax+00h]
0x180057ca5  xor     r8d, r8d
0x180057ca8  mov     rdx, rax
0x180057cab  cmp     cs:ExPoolZeroingNativelySupported, r8b
0x180057cb2  jnz     short loc_180057CC6
0x180057cb4  test    rax, rax
0x180057cb7  jz      loc_180057DDC
0x180057cbd  mov     [rax], r8
0x180057cc0  mov     [rax+8], r8
0x180057cc4  jmp     short loc_180057CCF
0x180057cc6  test    rdx, rdx
0x180057cc9  jz      loc_180057DDC
0x180057ccf  dec     r13d
0x180057cd2  mov     [rax+18h], r8
0x180057cd6  mov     qword ptr [rax+20h], 1
0x180057cde  lea     rcx, ds:0[r13*2]
0x180057ce6  add     rcx, r13
0x180057ce9  shl     rcx, 4
0x180057ced  add     rcx, [rsp+68h+arg_10]
0x180057cf5  mov     [rax+10h], rcx
0x180057cf9  mov     rax, [rdi]
0x180057cfc  cmp     [rax+8], rdi
0x180057d00  jnz     loc_180057DD5
0x180057d06  mov     [rdx], rax
0x180057d09  mov     [rdx+8], rdi
0x180057d0d  mov     [rax+8], rdx
0x180057d11  mov     [rdi], rdx
0x180057d14  test    r13d, r13d
0x180057d17  jnz     loc_180057C89
0x180057d1d  mov     rax, [rbp+78h]
0x180057d21  mov     edi, r8d
0x180057d24  mov     [rbx+18h], rax
0x180057d28  mov     rdx, [rbp+0B8h]
0x180057d2f  mov     rax, [rdx+8]
0x180057d33  mov     rcx, [rax+8]
0x180057d37  mov     eax, [rcx+14h]
0x180057d3a  mov     [rbx+20h], eax
0x180057d3d  mov     rax, [rdx+28h]
0x180057d41  mov     [rbx+48h], rax
0x180057d45  mov     [rbx+50h], r8
0x180057d49  mov     [rbx+58h], r8
0x180057d4d  mov     [rbx+68h], r8d
0x180057d51  mov     [rbx+70h], r8
0x180057d55  test    r14, r14
0x180057d58  jnz     short loc_180057D64
0x180057d5a  mov     rax, [rsi]
0x180057d5d  mov     r14, r12
0x180057d60  mov     [rax+18h], r12
0x180057d64  mov     r12, [rsp+68h+arg_0]
0x180057d69  mov     [r14], rbx
0x180057d6c  mov     [rbx+70h], r15
0x180057d70  lea     rcx, [r15+80h]
0x180057d77  mov     rax, [rcx]
0x180057d7a  mov     rdx, [rax]
0x180057d7d  test    rdx, rdx
0x180057d80  jz      short loc_180057DBD
0x180057d82  mov     rax, [rdx]
0x180057d85  test    rax, rax
0x180057d88  jz      short loc_180057DBD
0x180057d8a  mov     rdx, rbp
0x180057d8d  call    _guard_dispatch_icall
0x180057d92  mov     edi, eax
0x180057d94  test    eax, eax
0x180057d96  jns     short loc_180057DBD
0x180057d98  mov     dword ptr [rbp+30h], 0C0000016h
0x180057d9f  test    rbx, rbx
0x180057da2  jz      short loc_180057DBD
0x180057da4  mov     rax, [rsp+68h+arg_18]
0x180057dac  mov     rdx, rbp
0x180057daf  mov     rcx, [r12+28h]
0x180057db4  mov     rax, [rax+20h]
0x180057db8  call    _guard_dispatch_icall
0x180057dbd  mov     rbx, [rsp+68h+arg_8]
0x180057dc2  mov     eax, edi
0x180057dc4  add     rsp, 30h
0x180057dc8  pop     r15
0x180057dca  pop     r14
0x180057dcc  pop     r13
0x180057dce  pop     r12
0x180057dd0  pop     rdi
0x180057dd1  pop     rsi
0x180057dd2  pop     rbp
0x180057dd3  retn
0x180057dd5  mov     ecx, 3
0x180057dda  int     29h; Win8: RtlFailFast(ecx)
0x180057ddc  mov     rcx, rdi
0x180057ddf  call    FreeCreateEntries
0x180057de4  xor     edx, edx; Tag
0x180057de6  mov     rcx, rbx; P
0x180057de9  call    cs:__imp_ExFreePoolWithTag
0x180057df0  nop     dword ptr [rax+rax+00h]
0x180057df5  mov     r12, [rsp+68h+arg_0]
0x180057dfa  xor     r8d, r8d
0x180057dfd  mov     edi, 0C000009Ah
0x180057e02  mov     rbx, r8
0x180057e05  jmp     short loc_180057D98
```

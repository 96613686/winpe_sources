# KsecInstallBuiltinPackages

- ea: `0x18002267c`
- end: `0x18002274e`
- name: `KsecInstallBuiltinPackages`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180022b94`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x18002267c`

## pseudocode

```c
__int64 __fastcall KsecInstallBuiltinPackages(__int64 a1)
{
  __int64 v2; // rbp
  void *v3; // rdi
  __int128 v4; // xmm6
  void *v5; // rsi
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // r10
  __int64 v9; // rdx
  void *v10; // r8
  void *v11; // rcx
  __int64 v12; // rax
  __int128 v13; // xmm0
  char v15; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  v3 = &NegFunctionTable;
  v4 = 0;
  v5 = &NegotiateName;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v15);
  if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&v15) )
  {
    v7 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v15);
    if ( *(_QWORD *)(v7 + 472) )
    {
      v6 = -1073741768;
    }
    else
    {
      v8 = 0;
      if ( &NegFunctionTable )
      {
        do
        {
          v9 = 5 * v8;
          v8 = (unsigned int)(v8 + 1);
          v10 = *(void **)(a1 + 8 * v9);
          v11 = *(void **)(a1 + 8 * v9 + 8);
          v12 = *(_QWORD *)(a1 + 8 * v9 + 16);
          *(_QWORD *)(a1 + 8 * v9) = v3;
          v3 = v10;
          *(_QWORD *)(a1 + 8 * v9 + 8) = v5;
          v5 = v11;
          *(_QWORD *)(a1 + 8 * v9 + 16) = v2;
          v2 = v12;
          v13 = *(_OWORD *)(a1 + 8 * v9 + 24);
          *(_OWORD *)(a1 + 8 * v9 + 24) = v4;
          v4 = v13;
        }
        while ( v10 );
      }
      *(_QWORD *)(v7 + 472) = a1;
      v6 = 0;
      *(_DWORD *)(v7 + 480) = v8;
    }
  }
  else
  {
    v6 = -1073741058;
  }
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v15);
  return v6;
}

```

## disassembly

```asm
0x18002267c  push    rbx
0x18002267e  push    rbp
0x18002267f  push    rsi
0x180022680  push    rdi
0x180022681  sub     rsp, 38h
0x180022685  mov     rbx, rcx
0x180022688  movaps  [rsp+58h+var_38], xmm6
0x18002268d  lea     rcx, [rsp+58h+arg_8]; this
0x180022692  xor     ebp, ebp
0x180022694  lea     rdi, ?NegFunctionTable@@3U_SECPKG_KERNEL_FUNCTION_TABLE@@A; _SECPKG_KERNEL_FUNCTION_TABLE NegFunctionTable
0x18002269b  xorps   xmm6, xmm6
0x18002269e  lea     rsi, ?NegotiateName@@3U_UNICODE_STRING@@A; _UNICODE_STRING NegotiateName
0x1800226a5  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800226aa  lea     rcx, [rsp+58h+arg_8]; this
0x1800226af  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x1800226b4  test    al, al
0x1800226b6  jnz     short loc_1800226BF
0x1800226b8  mov     ebx, 0C00002FEh
0x1800226bd  jmp     short loc_180022733
0x1800226bf  lea     rcx, [rsp+58h+arg_8]
0x1800226c4  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800226c9  mov     r9, rax
0x1800226cc  cmp     [rax+1D8h], rbp
0x1800226d3  jz      short loc_1800226DC
0x1800226d5  mov     ebx, 0C0000038h
0x1800226da  jmp     short loc_180022733
0x1800226dc  xor     r10d, r10d
0x1800226df  test    rdi, rdi
0x1800226e2  jz      short loc_180022723
0x1800226e4  lea     rdx, [r10+r10*4]
0x1800226e8  inc     r10d
0x1800226eb  mov     r8, [rbx+rdx*8]
0x1800226ef  mov     rcx, [rbx+rdx*8+8]
0x1800226f4  mov     rax, [rbx+rdx*8+10h]
0x1800226f9  mov     [rbx+rdx*8], rdi
0x1800226fd  mov     rdi, r8
0x180022700  mov     [rbx+rdx*8+8], rsi
0x180022705  mov     rsi, rcx
0x180022708  mov     [rbx+rdx*8+10h], rbp
0x18002270d  mov     rbp, rax
0x180022710  movups  xmm0, xmmword ptr [rbx+rdx*8+18h]
0x180022715  movdqu  xmmword ptr [rbx+rdx*8+18h], xmm6
0x18002271b  movups  xmm6, xmm0
0x18002271e  test    r8, r8
0x180022721  jnz     short loc_1800226E4
0x180022723  mov     [r9+1D8h], rbx
0x18002272a  xor     ebx, ebx
0x18002272c  mov     [r9+1E0h], r10d
0x180022733  lea     rcx, [rsp+58h+arg_8]; this
0x180022738  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18002273d  movaps  xmm6, [rsp+58h+var_38]
0x180022742  mov     eax, ebx
0x180022744  add     rsp, 38h
0x180022748  pop     rdi
0x180022749  pop     rsi
0x18002274a  pop     rbp
0x18002274b  pop     rbx
0x18002274c  retn
```

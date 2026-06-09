# RtlLCIDToCultureName

- ea: `0x180009d60`
- end: `0x18000a05e`
- name: `RtlLCIDToCultureName`
- size: `766`
- prototype: ``
- caller_count: `27`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000908c`
- `0x1800094d0`
- `0x18000a360`
- `0x18000acb0`
- `0x18000aff0`
- `0x18000b400`
- `0x18000be70`
- `0x18000c3f0`
- `0x18000d3e0`
- `0x18000e7c0`
- `0x18000ee60`
- `0x18000f760`
- `0x1800145b0`
- `0x1800555a0`
- `0x18005d8e0`
- `0x1800c0000`
- `0x1800c8c50`
- `0x180110324`
- `0x180124a40`
- `0x180141c60`
- `0x180141fd8`
- `0x1801422a0`
- `0x1801428e0`
- `0x180143470`
- `0x18014ca30`
- `0x18014d654`
- `0x18014daa8`

## callees

- `0x180009d60`
- `0x18000a2d0`
- `0x18000a360`
- `0x18000a5f0`
- `0x18000ba2c`
- `0x1800bfc20`
- `0x18010e9a0`
- `0x18012c830`
- `0x180162000`
- `0x180163a80`

## pseudocode

```c
__int64 __fastcall RtlLCIDToCultureName(unsigned int a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  unsigned __int16 v5; // cx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rax
  _WORD *v9; // rbx
  size_t v10; // r9
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  _WORD *v13; // r8
  __int64 v14; // rcx
  _WORD *v15; // rdx
  unsigned __int8 v16; // si
  bool v18; // zf
  int LcidIndex; // eax
  __int64 v20; // rcx
  wchar_t *Buffer; // rdx
  _WORD *v22; // rax
  __int64 v23; // rcx
  int inited; // eax
  __int64 v25; // r8
  unsigned __int64 v26; // r14
  __int16 v27; // bx
  __int16 v28; // [rsp+20h] [rbp-F8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+28h] [rbp-F0h] BYREF
  unsigned __int64 v30; // [rsp+38h] [rbp-E0h] BYREF
  _BYTE Src[176]; // [rsp+40h] [rbp-D8h] BYREF

  v28 = 0;
  v3 = a1;
  if ( !a1 || !a2 || a1 == 4096 )
    return 0;
  if ( g_RegInfo )
  {
    if ( (int)RtlpMuiRegGetInstalledLanguageIndexByLangId(g_RegInfo, (unsigned __int16)a1, 0, &v28) >= 0 )
    {
      v4 = *(__int16 *)(*(_QWORD *)(*(_QWORD *)(g_RegInfo + 24) + 16LL) + 28LL * v28 + 6);
      if ( (__int16)v4 > 0 )
      {
        _mm_lfence();
        v5 = 0;
        DestinationString = 0;
        v6 = *(_QWORD *)(g_RegInfo + 32);
        v7 = *(__int16 *)(*(_QWORD *)(v6 + 16) + 2 * v4);
        v8 = *(_QWORD *)(v6 + 24);
        v9 = (_WORD *)(v8 + 2 * v7);
        if ( v9 )
        {
          v10 = 2 * wcslen((const wchar_t *)(v8 + 2 * v7));
          if ( v10 >= 0xFFFE )
            LOWORD(v10) = -4;
          v5 = v10;
        }
        else
        {
          LOWORD(v10) = DestinationString.Length;
        }
        v11 = *(unsigned __int16 *)(a2 + 2);
        if ( v5 > (unsigned __int16)v11 )
          return 0;
        v12 = v11 >> 1;
        if ( !v12 )
          return 0;
        v13 = *(_WORD **)(a2 + 8);
        v14 = 2147483646;
        do
        {
          if ( !v14 )
            break;
          if ( !*v9 )
            break;
          *v13++ = *v9++;
          --v14;
          --v12;
        }
        while ( v12 );
        v15 = v13 - 1;
        if ( v12 )
          v15 = v13;
        *v15 = 0;
        if ( !v12 )
          return 0;
        *(_WORD *)a2 = v10;
        return 1;
      }
    }
  }
  v16 = 0;
  v30 = 85;
  v18 = *(_QWORD *)(a2 + 8) == 0;
  DestinationString = 0;
  if ( v18 )
    return v16;
  if ( v3 == 5120 )
  {
    if ( (int)RtlpGetUserOrMachineUILanguage4NLS(1, (__int64)Src, &v30) < 0 )
      return v16;
    if ( (unsigned int)v30 >= 0x55 || (v26 = 2LL * (unsigned int)v30, *(unsigned __int16 *)(a2 + 2) <= v26) )
    {
      inited = -1073741789;
    }
    else
    {
      v27 = 2 * v30;
      memmove(*(void **)(a2 + 8), Src, (unsigned __int16)(2 * v30));
      inited = 0;
      *(_WORD *)(v26 + *(_QWORD *)(a2 + 8)) = 0;
      *(_WORD *)a2 = v27;
    }
LABEL_35:
    if ( inited < 0 )
      return v16;
    return 1;
  }
  if ( ((v3 - 1024) & 0xFFFFF7FF) == 0 )
  {
    DestinationString.Buffer = (wchar_t *)Src;
    DestinationString.MaximumLength = 170;
    if ( (int)RtlpGetUserLocaleName(&DestinationString) < 0 )
      return v16;
    Buffer = DestinationString.Buffer;
    v25 = DestinationString.Length >> 1;
    goto LABEL_34;
  }
  if ( pTblPtrs || (unsigned __int8)RtlpLoadNlsData() )
  {
    if ( v3 == 2048 )
      v3 = gSystemLocale;
    LcidIndex = RtlpNlsGetLcidIndex(v3);
    if ( LcidIndex >= 0 )
    {
      _mm_lfence();
      v20 = *(unsigned __int16 *)(*(_QWORD *)(pTblPtrs + 16) + 8LL * LcidIndex + 6);
      Buffer = (wchar_t *)(*(_QWORD *)(pTblPtrs + 32) + 2LL + 2 * v20);
      if ( Buffer )
      {
        v22 = (_WORD *)(*(_QWORD *)(pTblPtrs + 32) + 2LL + 2 * v20);
        v23 = 84;
        while ( *v22 )
        {
          ++v22;
          if ( !--v23 )
            return v16;
        }
        v25 = 84 - v23;
LABEL_34:
        inited = RtlpInitUnicodeStringUsingBuffer(0, Buffer, v25, a2);
        goto LABEL_35;
      }
    }
  }
  return v16;
}

```

## disassembly

```asm
0x180009d60  push    rbx
0x180009d62  push    rsi
0x180009d63  push    rdi
0x180009d64  sub     rsp, 100h
0x180009d6b  mov     rax, cs:__security_cookie
0x180009d72  xor     rax, rsp
0x180009d75  mov     [rsp+118h+var_28], rax
0x180009d7d  xor     eax, eax
0x180009d7f  mov     rdi, rdx
0x180009d82  mov     [rsp+118h+var_F8], ax
0x180009d87  mov     ebx, ecx
0x180009d89  test    ecx, ecx
0x180009d8b  jz      loc_180009E9C
0x180009d91  test    rdx, rdx
0x180009d94  jz      loc_180009E9C
0x180009d9a  cmp     ecx, 1000h
0x180009da0  jz      loc_180009E9C
0x180009da6  mov     rcx, cs:g_RegInfo
0x180009dad  test    rcx, rcx
0x180009db0  jz      loc_180009EBF
0x180009db6  movzx   edx, bx
0x180009db9  lea     r9, [rsp+118h+var_F8]
0x180009dbe  xor     r8d, r8d
0x180009dc1  call    RtlpMuiRegGetInstalledLanguageIndexByLangId
0x180009dc6  test    eax, eax
0x180009dc8  js      loc_180009EBF
0x180009dce  mov     rax, cs:g_RegInfo
0x180009dd5  mov     rdx, [rax+18h]
0x180009dd9  movsx   rax, [rsp+118h+var_F8]
0x180009ddf  imul    rcx, rax, 1Ch
0x180009de3  mov     rax, [rdx+10h]
0x180009de7  movsx   rdx, word ptr [rax+rcx+6]
0x180009ded  test    dx, dx
0x180009df0  jle     loc_180009EBF
0x180009df6  lfence
0x180009df9  mov     rax, cs:g_RegInfo
0x180009e00  xor     ecx, ecx
0x180009e02  xorps   xmm0, xmm0
0x180009e05  movups  xmmword ptr [rsp+118h+DestinationString.Length], xmm0
0x180009e0a  mov     r8, [rax+20h]
0x180009e0e  mov     rax, [r8+10h]
0x180009e12  movsx   rdx, word ptr [rax+rdx*2]
0x180009e17  mov     rax, [r8+18h]
0x180009e1b  lea     rbx, [rax+rdx*2]
0x180009e1f  test    rbx, rbx
0x180009e22  jz      loc_180009F95
0x180009e28  mov     rcx, rbx; String
0x180009e2b  call    wcslen
0x180009e30  mov     r9, rax
0x180009e33  mov     eax, 0FFFCh
0x180009e38  add     r9, r9
0x180009e3b  cmp     r9, 0FFFEh
0x180009e42  cmovnb  r9, rax
0x180009e46  movzx   ecx, r9w
0x180009e4a  movzx   eax, word ptr [rdi+2]
0x180009e4e  cmp     cx, ax
0x180009e51  ja      short loc_180009E9C
0x180009e53  shr     rax, 1
0x180009e56  jz      short loc_180009E9C
0x180009e58  mov     r8, [rdi+8]
0x180009e5c  mov     ecx, 7FFFFFFEh
0x180009e61  test    rcx, rcx
0x180009e64  jz      short loc_180009E83
0x180009e66  movzx   edx, word ptr [rbx]
0x180009e69  test    dx, dx
0x180009e6c  jz      short loc_180009E83
0x180009e6e  mov     [r8], dx
0x180009e72  add     rbx, 2
0x180009e76  add     r8, 2
0x180009e7a  dec     rcx
0x180009e7d  sub     rax, 1
0x180009e81  jnz     short loc_180009E61
0x180009e83  test    rax, rax
0x180009e86  lea     rdx, [r8-2]
0x180009e8a  cmovnz  rdx, r8
0x180009e8e  xor     ecx, ecx
0x180009e90  mov     [rdx], cx
0x180009e93  test    rax, rax
0x180009e96  jnz     loc_180009F89
0x180009e9c  xor     sil, sil
0x180009e9f  movzx   eax, sil
0x180009ea3  mov     rcx, [rsp+118h+var_28]
0x180009eab  xor     rcx, rsp; StackCookie
0x180009eae  call    __security_check_cookie
0x180009eb3  add     rsp, 100h
0x180009eba  pop     rdi
0x180009ebb  pop     rsi
0x180009ebc  pop     rbx
0x180009ebd  retn
0x180009ebf  xor     sil, sil
0x180009ec2  mov     [rsp+118h+var_E0], 55h ; 'U'
0x180009ecb  cmp     qword ptr [rdi+8], 0
0x180009ed0  xorps   xmm0, xmm0
0x180009ed3  movups  xmmword ptr [rsp+118h+DestinationString.Length], xmm0
0x180009ed8  jz      short loc_180009E9F
0x180009eda  cmp     ebx, 1400h
0x180009ee0  jz      loc_180009FB2
0x180009ee6  lea     eax, [rbx-400h]
0x180009eec  test    eax, 0FFFFF7FFh
0x180009ef1  jz      loc_18000A01E
0x180009ef7  cmp     cs:pTblPtrs, 0
0x180009eff  jz      loc_180009FA0
0x180009f05  cmp     ebx, 800h
0x180009f0b  cmovz   ebx, cs:gSystemLocale
0x180009f12  mov     ecx, ebx
0x180009f14  call    RtlpNlsGetLcidIndex
0x180009f19  test    eax, eax
0x180009f1b  js      short loc_180009E9F
0x180009f1d  movsxd  rcx, eax
0x180009f20  lfence
0x180009f23  mov     rdx, cs:pTblPtrs
0x180009f2a  mov     rax, [rdx+10h]
0x180009f2e  mov     rdx, [rdx+20h]
0x180009f32  add     rdx, 2
0x180009f36  movzx   ecx, word ptr [rax+rcx*8+6]
0x180009f3b  lea     rdx, [rdx+rcx*2]
0x180009f3f  test    rdx, rdx
0x180009f42  jz      loc_180009E9F
0x180009f48  mov     r8d, 54h ; 'T'
0x180009f4e  mov     rax, rdx
0x180009f51  mov     ecx, r8d
0x180009f54  cmp     word ptr [rax], 0
0x180009f58  jz      short loc_180009F84
0x180009f5a  add     rax, 2
0x180009f5e  sub     rcx, 1
0x180009f62  jnz     short loc_180009F54
0x180009f64  xor     r8d, r8d
0x180009f67  test    rcx, rcx
0x180009f6a  jz      loc_180009E9F
0x180009f70  mov     r9, rdi
0x180009f73  xor     ecx, ecx
0x180009f75  call    RtlpInitUnicodeStringUsingBuffer
0x180009f7a  test    eax, eax
0x180009f7c  js      loc_180009E9F
0x180009f82  jmp     short loc_180009F8D
0x180009f84  sub     r8, rcx
0x180009f87  jmp     short loc_180009F70
0x180009f89  mov     [rdi], r9w
0x180009f8d  mov     sil, 1
0x180009f90  jmp     loc_180009E9F
0x180009f95  movzx   r9d, [rsp+118h+DestinationString.Length]
0x180009f9b  jmp     loc_180009E4A
0x180009fa0  call    RtlpLoadNlsData
0x180009fa5  test    al, al
0x180009fa7  jnz     loc_180009F05
0x180009fad  jmp     loc_180009E9F
0x180009fb2  lea     r8, [rsp+118h+var_E0]
0x180009fb7  mov     ecx, 1
0x180009fbc  lea     rdx, [rsp+118h+Src]
0x180009fc1  call    RtlpGetUserOrMachineUILanguage4NLS
0x180009fc6  test    eax, eax
0x180009fc8  js      loc_180009E9F
0x180009fce  mov     ecx, dword ptr [rsp+118h+var_E0]
0x180009fd2  mov     [rsp+118h+arg_10], r14
0x180009fda  cmp     ecx, 55h ; 'U'
0x180009fdd  jnb     short loc_18000A057
0x180009fdf  movzx   eax, word ptr [rdi+2]
0x180009fe3  lea     r14, [rcx+rcx]
0x180009fe7  cmp     rax, r14
0x180009fea  jbe     short loc_18000A057
0x180009fec  add     cx, cx
0x180009fef  lea     rdx, [rsp+118h+Src]; Src
0x180009ff4  movzx   ebx, cx
0x180009ff7  mov     rcx, [rdi+8]; void *
0x180009ffb  mov     r8d, ebx; Size
0x180009ffe  call    memmove
0x18000a003  mov     rcx, [rdi+8]
0x18000a007  xor     eax, eax
0x18000a009  mov     [r14+rcx], ax
0x18000a00e  mov     [rdi], bx
0x18000a011  mov     r14, [rsp+118h+arg_10]
0x18000a019  jmp     loc_180009F7A
0x18000a01e  lea     rax, [rsp+118h+Src]
0x18000a023  mov     [rsp+118h+DestinationString.Buffer], rax
0x18000a028  lea     rcx, [rsp+118h+DestinationString]; DestinationString
0x18000a02d  mov     eax, 0AAh
0x18000a032  mov     [rsp+118h+DestinationString.MaximumLength], ax
0x18000a037  call    RtlpGetUserLocaleName
0x18000a03c  test    eax, eax
0x18000a03e  js      loc_180009E9F
0x18000a044  movzx   r8d, [rsp+118h+DestinationString.Length]
0x18000a04a  mov     rdx, [rsp+118h+DestinationString.Buffer]
0x18000a04f  shr     r8d, 1
0x18000a052  jmp     loc_180009F70
0x18000a057  mov     eax, 0C0000023h
0x18000a05c  jmp     short loc_18000A011
```

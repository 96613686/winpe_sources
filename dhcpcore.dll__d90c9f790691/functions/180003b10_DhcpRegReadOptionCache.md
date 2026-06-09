# DhcpRegReadOptionCache

- ea: `0x180003b10`
- end: `0x180003cd4`
- name: `DhcpRegReadOptionCache`
- size: `452`
- prototype: `__int64 __fastcall(int, HKEY, const WCHAR *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180003544`
- `0x180003910`
- `0x1800227ac`

## callees

- `0x180003b10`
- `0x180005994`
- `0x18001b2bc`
- `0x180040eb4`
- `0x180041224`
- `0x18004d1a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c8b`

## pseudocode

```c
__int64 __fastcall DhcpRegReadOptionCache(int a1, HKEY a2, const WCHAR *a3)
{
  unsigned int v3; // edi
  unsigned int v4; // esi
  _DWORD *v5; // r14
  void *v6; // r15
  _DWORD *v7; // r8
  __int64 v8; // rbp
  __int64 v9; // r12
  unsigned int v10; // r9d
  _DWORD *v11; // rcx
  __int64 v12; // rbx
  char *v13; // rax
  int v14; // r13d
  __int64 v15; // rcx
  size_t Size; // [rsp+38h] [rbp-70h]
  DWORD v18; // [rsp+50h] [rbp-58h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-50h] BYREF
  void *Src; // [rsp+60h] [rbp-48h]
  __int64 v22; // [rsp+C8h] [rbp+20h] BYREF

  v18 = 0;
  lpMem = 0;
  LODWORD(v22) = 1024;
  v3 = DhcpQueryRegistryValue(a2, a3, &v18, (DWORD *)&v22, (BYTE **)&lpMem);
  if ( v3 )
  {
LABEL_20:
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 39, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, v3);
    return v3;
  }
  v4 = v22;
  if ( !(_DWORD)v22 || v18 != 3 )
  {
    v3 = 87;
    goto LABEL_20;
  }
  v5 = lpMem;
  v6 = lpMem;
  while ( v4 >= 0x14 )
  {
    v7 = v5 + 1;
    v8 = (unsigned int)v5[1];
    v9 = (unsigned int)v5[2];
    LODWORD(lpMem) = *v5;
    v10 = (v9 + v8 + 23) & 0xFFFFFFFC;
    if ( v10 > v4 )
      break;
    v11 = v5 + 5;
    v12 = 0;
    LODWORD(v22) = v5[4];
    if ( (_DWORD)v8 )
      v12 = (__int64)(v5 + 5);
    v13 = 0;
    if ( (_DWORD)v9 )
      v13 = (char *)v5 + v8 + 20;
    v5 = (_DWORD *)(((unsigned __int64)v5 + v8 + v9 + 23) & 0xFFFFFFFFFFFFFFFCuLL);
    Src = v13;
    v4 -= v10;
    if ( (_DWORD)v9 )
    {
      v14 = v7[2];
      if ( v12 )
      {
        v12 = DhcpAddClass(v11, v12, (unsigned int)v8);
        if ( !v12 )
          break;
      }
      LODWORD(Size) = v9;
      v3 = DhcpAddOption(a1, (unsigned __int8)lpMem, v14, v12, v8, 0, Src, Size, (unsigned int)v22);
      if ( v3 )
      {
        if ( v12 )
          DhcpDelClass(v15, v12, v8);
        break;
      }
    }
  }
  if ( v6 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v6);
  return v3;
}

```

## disassembly

```asm
0x180003b10  mov     r11, rsp
0x180003b13  mov     [r11+10h], rbx
0x180003b17  mov     [r11+20h], r9b
0x180003b1b  mov     [r11+8], rcx
0x180003b1f  push    rbp
0x180003b20  push    rsi
0x180003b21  push    rdi
0x180003b22  push    r12
0x180003b24  push    r13
0x180003b26  push    r14
0x180003b28  push    r15
0x180003b2a  sub     rsp, 70h
0x180003b2e  lea     rcx, [r11-50h]
0x180003b32  mov     [rsp+0A8h+var_58], 0
0x180003b3a  mov     rax, r8
0x180003b3d  mov     qword ptr [rsp+0A8h+var_88], rcx
0x180003b42  mov     r10, rdx
0x180003b45  mov     qword ptr [r11-50h], 0
0x180003b4d  mov     rcx, r10
0x180003b50  mov     dword ptr [r11+20h], 400h
0x180003b58  lea     r9, [r11+20h]
0x180003b5c  mov     rdx, rax
0x180003b5f  lea     r8, [r11-58h]
0x180003b63  call    DhcpQueryRegistryValue
0x180003b68  mov     edi, eax
0x180003b6a  test    eax, eax
0x180003b6c  jnz     loc_180003C98
0x180003b72  mov     esi, dword ptr [rsp+0A8h+arg_18]
0x180003b79  test    esi, esi
0x180003b7b  jz      loc_180003C93
0x180003b81  cmp     [rsp+0A8h+var_58], 3
0x180003b86  jnz     loc_180003C93
0x180003b8c  mov     r14, [rsp+0A8h+lpMem]
0x180003b91  mov     r15, r14
0x180003b94  cmp     esi, 14h
0x180003b97  jb      loc_180003C74
0x180003b9d  mov     eax, [r14]
0x180003ba0  lea     r8, [r14+4]
0x180003ba4  mov     ebp, [r8]
0x180003ba7  mov     r12d, [r8+4]
0x180003bab  mov     dword ptr [rsp+0A8h+lpMem], eax
0x180003baf  lea     r9d, [rbp+17h]
0x180003bb3  add     r9d, r12d
0x180003bb6  and     r9d, 0FFFFFFFCh
0x180003bba  cmp     r9d, esi
0x180003bbd  ja      loc_180003C74
0x180003bc3  mov     eax, [r8+0Ch]
0x180003bc7  lea     rcx, [r8+10h]
0x180003bcb  xor     ebx, ebx
0x180003bcd  mov     dword ptr [rsp+0A8h+arg_18], eax
0x180003bd4  test    ebp, ebp
0x180003bd6  lea     rdx, [rcx+rbp]
0x180003bda  lea     r14, [rdx+3]
0x180003bde  cmovnz  rbx, rcx
0x180003be2  xor     eax, eax
0x180003be4  test    r12d, r12d
0x180003be7  cmovnz  rax, rdx
0x180003beb  add     r14, r12
0x180003bee  and     r14, 0FFFFFFFFFFFFFFFCh
0x180003bf2  mov     [rsp+0A8h+var_48], rax
0x180003bf7  sub     esi, r9d
0x180003bfa  test    r12d, r12d
0x180003bfd  jz      short loc_180003B94
0x180003bff  mov     r13d, [r8+8]
0x180003c03  test    rbx, rbx
0x180003c06  jz      short loc_180003C1B
0x180003c08  mov     r8d, ebp
0x180003c0b  mov     rdx, rbx
0x180003c0e  call    DhcpAddClass
0x180003c13  mov     rbx, rax
0x180003c16  test    rax, rax
0x180003c19  jz      short loc_180003C74
0x180003c1b  mov     eax, dword ptr [rsp+0A8h+arg_18]
0x180003c22  mov     r9, rbx; int
0x180003c25  movzx   edx, byte ptr [rsp+0A8h+lpMem]; int
0x180003c2a  mov     r8d, r13d; int
0x180003c2d  mov     rcx, qword ptr [rsp+0A8h+arg_0]; int
0x180003c35  mov     [rsp+0A8h+var_68], rax; __int64
0x180003c3a  mov     rax, [rsp+0A8h+var_48]
0x180003c3f  mov     dword ptr [rsp+0A8h+Size], r12d; Size
0x180003c44  mov     [rsp+0A8h+Src], rax; Src
0x180003c49  mov     [rsp+0A8h+var_80], 0; int
0x180003c51  mov     [rsp+0A8h+var_88], ebp; int
0x180003c55  call    DhcpAddOption
0x180003c5a  mov     edi, eax
0x180003c5c  test    eax, eax
0x180003c5e  jz      loc_180003B94
0x180003c64  test    rbx, rbx
0x180003c67  jz      short loc_180003C74
0x180003c69  mov     r8d, ebp
0x180003c6c  mov     rdx, rbx
0x180003c6f  call    DhcpDelClass
0x180003c74  test    r15, r15
0x180003c77  jz      short loc_180003CBA
0x180003c79  mov     rcx, gs:60h
0x180003c82  mov     r8, r15; lpMem
0x180003c85  xor     edx, edx; dwFlags
0x180003c87  mov     rcx, [rcx+30h]; hHeap
0x180003c8b  call    cs:__imp_HeapFree
0x180003c91  jmp     short loc_180003CBA
0x180003c93  mov     edi, 57h ; 'W'
0x180003c98  test    byte ptr cs:xmmword_1800616A0, 2
0x180003c9f  jz      short loc_180003CBA
0x180003ca1  mov     edx, 27h ; '''
0x180003ca6  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x180003cad  mov     ecx, 401h
0x180003cb2  mov     r9d, edi
0x180003cb5  call    WPP_SF_D
0x180003cba  mov     rbx, [rsp+0A8h+arg_8]
0x180003cc2  mov     eax, edi
0x180003cc4  add     rsp, 70h
0x180003cc8  pop     r15
0x180003cca  pop     r14
0x180003ccc  pop     r13
0x180003cce  pop     r12
0x180003cd0  pop     rdi
0x180003cd1  pop     rsi
0x180003cd2  pop     rbp
0x180003cd3  retn
```

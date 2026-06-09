# HsmiBitmapNORMALVerifyBitmapPages

- ea: `0x140018660`
- end: `0x1400187f5`
- name: `HsmiBitmapNORMALVerifyBitmapPages`
- size: `405`
- prototype: `__int64 __fastcall(__int64, _QWORD *, char, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140072880`

## callees

- `0x140003c50`
- `0x140018660`
- `0x140019634`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x1400186dd`
- `ntoskrnl!RtlComputeCrc32` at `0x1400186dd`

## pseudocode

```c
__int64 __fastcall HsmiBitmapNORMALVerifyBitmapPages(__int64 a1, _QWORD *a2, char a3, __int64 a4, unsigned int a5)
{
  unsigned int v8; // edi
  unsigned int i; // ebx
  __int64 v10; // r13
  ULONG v11; // eax
  char v12; // r12
  unsigned int v13; // ebx
  __int64 j; // r8
  __int64 v15; // r10
  unsigned int v16; // r9d
  unsigned int v17; // eax
  int v18; // eax

  if ( a2 && (a4 & 0xFFF) == 0 && (a5 & 0xFFF) == 0 && a5 )
  {
    v8 = 0;
    for ( i = 0; i < a5; i += 4096 )
    {
      v10 = a4 + i;
      v11 = RtlComputeCrc32(0, (PUCHAR)v10, 0xFFCu);
      v12 = v11;
      if ( v11 != *(_DWORD *)(v10 + 4092) )
      {
        v8 = -1073741761;
        LOBYTE(v13) = 0;
        HsmDbgBreakOnStatus(-1073741761);
        for ( j = 0; !(_DWORD)j; j = 1 )
        {
          v15 = a2[20];
          if ( *(_QWORD *)(v15 + 8 * j) == a1 )
          {
            LOBYTE(v13) = -1;
            break;
          }
          v13 = 0;
          v16 = *(_DWORD *)(a2[5] + 108LL);
          while ( 1 )
          {
            v17 = 3;
            if ( v16 < 3 )
              v17 = *(_DWORD *)(a2[5] + 108LL);
            if ( v13 >= v17 || *(_QWORD *)(v15 + 8 * (v13 + 3 * j) + 16) == a1 )
              break;
            ++v13;
          }
          v18 = 3;
          if ( v16 < 3 )
            v18 = *(_DWORD *)(a2[5] + 108LL);
          if ( v13 != v18 )
            break;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qisddiddd(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)a2 + 32,
            j,
            (_DWORD)a2,
            *a2,
            (__int64)(a2 + 4),
            j,
            v13,
            a3,
            *(_DWORD *)(v10 + 4092),
            v12);
        }
        return v8;
      }
    }
  }
  else
  {
    v8 = -1073741595;
    HsmDbgBreakOnStatus(-1073741595);
  }
  return v8;
}

```

## disassembly

```asm
0x140018660  mov     [rsp+arg_0], rbx
0x140018665  mov     [rsp+arg_8], rbp
0x14001866a  mov     [rsp+arg_10], r8
0x14001866f  push    rdi
0x140018670  push    r12
0x140018672  push    r13
0x140018674  push    r14
0x140018676  push    r15
0x140018678  sub     rsp, 60h
0x14001867c  mov     rbp, r9
0x14001867f  mov     r14, rdx
0x140018682  mov     r15, rcx
0x140018685  test    rdx, rdx
0x140018688  jz      loc_1400187CC
0x14001868e  mov     eax, 0FFFh
0x140018693  test    rax, r9
0x140018696  setz    r10b
0x14001869a  test    [rsp+88h+arg_20], eax
0x1400186a1  setz    al
0x1400186a4  test    al, r10b
0x1400186a7  jz      loc_1400187CC
0x1400186ad  cmp     [rsp+88h+arg_20], 0
0x1400186b5  jz      loc_1400187CC
0x1400186bb  xor     edi, edi
0x1400186bd  xor     ebx, ebx
0x1400186bf  cmp     ebx, [rsp+88h+arg_20]
0x1400186c6  jnb     loc_1400187D8
0x1400186cc  mov     r13d, ebx
0x1400186cf  mov     r8d, 0FFCh; Length
0x1400186d5  add     r13, rbp
0x1400186d8  xor     ecx, ecx; InitialCrc
0x1400186da  mov     rdx, r13; Buffer
0x1400186dd  call    cs:__imp_RtlComputeCrc32
0x1400186e4  nop     dword ptr [rax+rax+00h]
0x1400186e9  mov     r12d, eax
0x1400186ec  cmp     eax, [r13+0FFCh]
0x1400186f3  jnz     short loc_1400186FD
0x1400186f5  add     ebx, 1000h
0x1400186fb  jmp     short loc_1400186BF
0x1400186fd  mov     edi, 0C000003Fh
0x140018702  xor     ebx, ebx
0x140018704  mov     ecx, edi
0x140018706  call    HsmDbgBreakOnStatus
0x14001870b  xor     r8d, r8d
0x14001870e  lea     r11d, [rbx+3]
0x140018712  cmp     r8d, 1
0x140018716  jnb     short loc_140018767
0x140018718  mov     r10, [r14+0A0h]
0x14001871f  cmp     [r10+r8*8], r15
0x140018723  jz      short loc_140018764
0x140018725  mov     rax, [r14+28h]
0x140018729  xor     ebx, ebx
0x14001872b  mov     r9d, [rax+6Ch]
0x14001872f  cmp     r9d, r11d
0x140018732  mov     eax, r11d
0x140018735  cmovb   eax, r9d
0x140018739  cmp     ebx, eax
0x14001873b  jnb     short loc_140018751
0x14001873d  lea     rcx, [r8+r8*2]
0x140018741  mov     eax, ebx
0x140018743  add     rcx, rax
0x140018746  cmp     [r10+rcx*8+10h], r15
0x14001874b  jz      short loc_140018751
0x14001874d  inc     ebx
0x14001874f  jmp     short loc_14001872F
0x140018751  cmp     r9d, r11d
0x140018754  mov     eax, r11d
0x140018757  cmovb   eax, r9d
0x14001875b  cmp     ebx, eax
0x14001875d  jnz     short loc_140018767
0x14001875f  inc     r8d
0x140018762  jmp     short loc_140018712
0x140018764  or      ebx, 0FFFFFFFFh
0x140018767  mov     rcx, cs:WPP_GLOBAL_Control
0x14001876e  lea     rax, WPP_GLOBAL_Control
0x140018775  cmp     rcx, rax
0x140018778  jz      short loc_1400187D8
0x14001877a  mov     eax, [rcx+2Ch]
0x14001877d  test    al, 1
0x14001877f  jz      short loc_1400187D8
0x140018781  cmp     byte ptr [rcx+29h], 2
0x140018785  jb      short loc_1400187D8
0x140018787  mov     eax, [r13+0FFCh]
0x14001878e  lea     rdx, [r14+20h]
0x140018792  mov     rcx, [rcx+18h]
0x140018796  mov     r9, r14
0x140018799  mov     [rsp+88h+var_38], r12d
0x14001879e  mov     [rsp+88h+var_40], eax
0x1400187a2  mov     rax, [rsp+88h+arg_10]
0x1400187aa  mov     [rsp+88h+var_48], rax
0x1400187af  mov     rax, [r14]
0x1400187b2  mov     [rsp+88h+var_50], ebx
0x1400187b6  mov     [rsp+88h+var_58], r8d
0x1400187bb  mov     [rsp+88h+var_60], rdx
0x1400187c0  mov     [rsp+88h+var_68], rax
0x1400187c5  call    WPP_SF_qisddiddd
0x1400187ca  jmp     short loc_1400187D8
0x1400187cc  mov     edi, 0C00000E5h
0x1400187d1  mov     ecx, edi
0x1400187d3  call    HsmDbgBreakOnStatus
0x1400187d8  lea     r11, [rsp+88h+var_28]
0x1400187dd  mov     eax, edi
0x1400187df  mov     rbx, [r11+30h]
0x1400187e3  mov     rbp, [r11+38h]
0x1400187e7  mov     rsp, r11
0x1400187ea  pop     r15
0x1400187ec  pop     r14
0x1400187ee  pop     r13
0x1400187f0  pop     r12
0x1400187f2  pop     rdi
0x1400187f3  retn
```

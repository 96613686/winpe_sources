# HsmiBitmapNORMALVerifyBitmapPages

- ea: `0x1400185e0`
- end: `0x140018775`
- name: `HsmiBitmapNORMALVerifyBitmapPages`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140072760`

## callees

- `0x140003c50`
- `0x1400185e0`
- `0x1400195b4`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14001865d`
- `ntoskrnl!RtlComputeCrc32` at `0x14001865d`

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
        HsmDbgBreakOnStatus(3221225535LL);
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
    HsmDbgBreakOnStatus(3221225701LL);
  }
  return v8;
}

```

## disassembly

```asm
0x1400185e0  mov     [rsp+arg_0], rbx
0x1400185e5  mov     [rsp+arg_8], rbp
0x1400185ea  mov     [rsp+arg_10], r8
0x1400185ef  push    rdi
0x1400185f0  push    r12
0x1400185f2  push    r13
0x1400185f4  push    r14
0x1400185f6  push    r15
0x1400185f8  sub     rsp, 60h
0x1400185fc  mov     rbp, r9
0x1400185ff  mov     r14, rdx
0x140018602  mov     r15, rcx
0x140018605  test    rdx, rdx
0x140018608  jz      loc_14001874C
0x14001860e  mov     eax, 0FFFh
0x140018613  test    rax, r9
0x140018616  setz    r10b
0x14001861a  test    [rsp+88h+arg_20], eax
0x140018621  setz    al
0x140018624  test    al, r10b
0x140018627  jz      loc_14001874C
0x14001862d  cmp     [rsp+88h+arg_20], 0
0x140018635  jz      loc_14001874C
0x14001863b  xor     edi, edi
0x14001863d  xor     ebx, ebx
0x14001863f  cmp     ebx, [rsp+88h+arg_20]
0x140018646  jnb     loc_140018758
0x14001864c  mov     r13d, ebx
0x14001864f  mov     r8d, 0FFCh; Length
0x140018655  add     r13, rbp
0x140018658  xor     ecx, ecx; InitialCrc
0x14001865a  mov     rdx, r13; Buffer
0x14001865d  call    cs:__imp_RtlComputeCrc32
0x140018664  nop     dword ptr [rax+rax+00h]
0x140018669  mov     r12d, eax
0x14001866c  cmp     eax, [r13+0FFCh]
0x140018673  jnz     short loc_14001867D
0x140018675  add     ebx, 1000h
0x14001867b  jmp     short loc_14001863F
0x14001867d  mov     edi, 0C000003Fh
0x140018682  xor     ebx, ebx
0x140018684  mov     ecx, edi
0x140018686  call    HsmDbgBreakOnStatus
0x14001868b  xor     r8d, r8d
0x14001868e  lea     r11d, [rbx+3]
0x140018692  cmp     r8d, 1
0x140018696  jnb     short loc_1400186E7
0x140018698  mov     r10, [r14+0A0h]
0x14001869f  cmp     [r10+r8*8], r15
0x1400186a3  jz      short loc_1400186E4
0x1400186a5  mov     rax, [r14+28h]
0x1400186a9  xor     ebx, ebx
0x1400186ab  mov     r9d, [rax+6Ch]
0x1400186af  cmp     r9d, r11d
0x1400186b2  mov     eax, r11d
0x1400186b5  cmovb   eax, r9d
0x1400186b9  cmp     ebx, eax
0x1400186bb  jnb     short loc_1400186D1
0x1400186bd  lea     rcx, [r8+r8*2]
0x1400186c1  mov     eax, ebx
0x1400186c3  add     rcx, rax
0x1400186c6  cmp     [r10+rcx*8+10h], r15
0x1400186cb  jz      short loc_1400186D1
0x1400186cd  inc     ebx
0x1400186cf  jmp     short loc_1400186AF
0x1400186d1  cmp     r9d, r11d
0x1400186d4  mov     eax, r11d
0x1400186d7  cmovb   eax, r9d
0x1400186db  cmp     ebx, eax
0x1400186dd  jnz     short loc_1400186E7
0x1400186df  inc     r8d
0x1400186e2  jmp     short loc_140018692
0x1400186e4  or      ebx, 0FFFFFFFFh
0x1400186e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400186ee  lea     rax, WPP_GLOBAL_Control
0x1400186f5  cmp     rcx, rax
0x1400186f8  jz      short loc_140018758
0x1400186fa  mov     eax, [rcx+2Ch]
0x1400186fd  test    al, 1
0x1400186ff  jz      short loc_140018758
0x140018701  cmp     byte ptr [rcx+29h], 2
0x140018705  jb      short loc_140018758
0x140018707  mov     eax, [r13+0FFCh]
0x14001870e  lea     rdx, [r14+20h]
0x140018712  mov     rcx, [rcx+18h]
0x140018716  mov     r9, r14
0x140018719  mov     [rsp+88h+var_38], r12d
0x14001871e  mov     [rsp+88h+var_40], eax
0x140018722  mov     rax, [rsp+88h+arg_10]
0x14001872a  mov     [rsp+88h+var_48], rax
0x14001872f  mov     rax, [r14]
0x140018732  mov     [rsp+88h+var_50], ebx
0x140018736  mov     [rsp+88h+var_58], r8d
0x14001873b  mov     [rsp+88h+var_60], rdx
0x140018740  mov     [rsp+88h+var_68], rax
0x140018745  call    WPP_SF_qisddiddd
0x14001874a  jmp     short loc_140018758
0x14001874c  mov     edi, 0C00000E5h
0x140018751  mov     ecx, edi
0x140018753  call    HsmDbgBreakOnStatus
0x140018758  lea     r11, [rsp+88h+var_28]
0x14001875d  mov     eax, edi
0x14001875f  mov     rbx, [r11+30h]
0x140018763  mov     rbp, [r11+38h]
0x140018767  mov     rsp, r11
0x14001876a  pop     r15
0x14001876c  pop     r14
0x14001876e  pop     r13
0x140018770  pop     r12
0x140018772  pop     rdi
0x140018773  retn
```

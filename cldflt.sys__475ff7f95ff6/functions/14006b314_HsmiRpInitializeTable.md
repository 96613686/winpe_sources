# HsmiRpInitializeTable

- ea: `0x14006b314`
- end: `0x14006b840`
- name: `HsmiRpInitializeTable`
- size: `1324`
- prototype: `__int64 __fastcall(__int64, int, const void *, unsigned __int16, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006ad44`
- `0x14006b848`

## callees

- `0x140003c50`
- `0x14000d95c`
- `0x14001e300`
- `0x14001e600`
- `0x14006a8b0`
- `0x14006b314`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14006b52e`
- `ntoskrnl!RtlComputeCrc32` at `0x14006b52e`

## pseudocode

```c
__int64 __fastcall HsmiRpInitializeTable(
        __int64 a1,
        int a2,
        const void *a3,
        unsigned __int16 a4,
        __int64 a5,
        unsigned __int16 *a6)
{
  __int64 v6; // rdi
  int v10; // eax
  unsigned int v11; // ebp
  unsigned int *v12; // r15
  __int64 v13; // rdx
  unsigned int v14; // ecx
  int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // eax
  void *v20; // rcx
  unsigned int v21; // r8d
  unsigned __int16 v22; // cx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  int v31; // [rsp+68h] [rbp+10h] BYREF

  v6 = a5;
  v10 = *a6;
  if ( (unsigned __int16)v10 <= 4u )
    v11 = 0;
  else
    v11 = v10 - 4;
  *(_QWORD *)(a5 + 4) = 1884448070;
  v12 = (unsigned int *)(v6 + 12);
  *(_DWORD *)(v6 + 16) = 655360;
  *(_DWORD *)(v6 + 12) = 96;
  memset((void *)(v6 + 20), 0, 0x50u);
  if ( v11 < 0x18 )
  {
LABEL_62:
    v15 = -1073741789;
    goto LABEL_7;
  }
  if ( *(_WORD *)(v6 + 18) )
  {
    v13 = *v12;
    if ( ((v13 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= v11 )
    {
      v14 = (v13 + 3) & 0xFFFFFFFC;
      *v12 = v14;
      *(_DWORD *)(v6 + 20) = 65543;
      *(_DWORD *)(v6 + 24) = v14;
      *(_BYTE *)(v14 + v6 + 4) = 1;
      ++*v12;
      v15 = 0;
      goto LABEL_7;
    }
    goto LABEL_62;
  }
  v15 = -1073741811;
LABEL_7:
  HsmDbgBreakOnStatus(v15);
  if ( v15 < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return (unsigned int)v15;
    }
    v29 = 10;
    goto LABEL_53;
  }
  if ( v11 >= 0x18 )
  {
    if ( *(_WORD *)(v6 + 18) <= 1u )
    {
      v15 = -1073741811;
      goto LABEL_15;
    }
    if ( v11 >= 0x20 )
    {
      v16 = *v12;
      if ( ((v16 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v11 )
      {
        v17 = ((_DWORD)v16 + 3) & 0xFFFFFFFC;
        *v12 = v17;
        if ( *(_WORD *)(v6 + 28) )
          *(_WORD *)(v6 + 16) |= 1u;
        *(_DWORD *)(v6 + 28) = 262154;
        v15 = 0;
        *(_DWORD *)(v6 + 32) = v17;
        *(_DWORD *)(v17 + v6 + 4) = a2;
        *v12 += 4;
        goto LABEL_15;
      }
    }
  }
  v15 = -1073741789;
LABEL_15:
  HsmDbgBreakOnStatus(v15);
  if ( v15 < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return (unsigned int)v15;
    }
    v29 = 11;
    goto LABEL_53;
  }
  if ( v11 < 0x18 )
    goto LABEL_60;
  if ( *(_WORD *)(v6 + 18) <= 3u )
  {
    v15 = -1073741811;
    goto LABEL_26;
  }
  if ( v11 < 0x30 || (v18 = *v12, a4 + ((v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v11) )
  {
LABEL_60:
    v15 = -1073741789;
    goto LABEL_26;
  }
  if ( *(_WORD *)(v6 + 44) )
    *(_WORD *)(v6 + 16) |= 1u;
  v19 = (v18 + 3) & 0xFFFFFFFC;
  *v12 = v19;
  *(_WORD *)(v6 + 44) = 17;
  *(_WORD *)(v6 + 46) = a4;
  *(_DWORD *)(v6 + 48) = v19;
  if ( a3 )
  {
    v20 = (void *)(v6 + v19 + 4LL);
    if ( v20 != a3 )
      memmove(v20, a3, a4);
  }
  v15 = 0;
  *v12 += *(unsigned __int16 *)(v6 + 46);
LABEL_26:
  HsmDbgBreakOnStatus(v15);
  if ( v15 < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return (unsigned int)v15;
    }
    v29 = 12;
    goto LABEL_53;
  }
  if ( (a2 & 0x10) == 0 )
  {
    if ( v11 >= 0x18 )
    {
      if ( *(_WORD *)(v6 + 18) <= 2u )
      {
        v15 = -1073741811;
        goto LABEL_40;
      }
      if ( v11 >= 0x28 )
      {
        v24 = *v12;
        if ( ((v24 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= v11 )
        {
          v25 = ((_DWORD)v24 + 3) & 0xFFFFFFFC;
          *v12 = v25;
          if ( *(_WORD *)(v6 + 36) )
            *(_WORD *)(v6 + 16) |= 1u;
          v15 = 0;
          *(_DWORD *)(v6 + 36) = 524294;
          *(_DWORD *)(v6 + 40) = v25;
          *(_QWORD *)(v25 + v6 + 4) = a1;
          *v12 += 8;
LABEL_40:
          HsmDbgBreakOnStatus(v15);
          if ( v15 < 0 )
          {
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              return (unsigned int)v15;
            }
            v29 = 13;
            goto LABEL_53;
          }
          if ( v11 >= 0x18 )
          {
            if ( *(_WORD *)(v6 + 18) <= 9u )
            {
              v15 = -1073741811;
              goto LABEL_48;
            }
            if ( v11 >= 0x60 )
            {
              v26 = *v12;
              if ( ((v26 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v11 )
              {
                v27 = ((_DWORD)v26 + 3) & 0xFFFFFFFC;
                *v12 = v27;
                if ( *(_WORD *)(v6 + 92) )
                  *(_WORD *)(v6 + 16) |= 1u;
                *(_DWORD *)(v6 + 92) = 262154;
                v15 = 0;
                *(_DWORD *)(v6 + 96) = v27;
                *(_DWORD *)(v27 + v6 + 4) = 0;
                *v12 += 4;
                goto LABEL_48;
              }
            }
          }
          v15 = -1073741789;
LABEL_48:
          HsmDbgBreakOnStatus(v15);
          if ( v15 >= 0 )
            goto LABEL_28;
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            return (unsigned int)v15;
          }
          v29 = 14;
LABEL_53:
          WPP_SF_d(v28->AttachedDevice, v29, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, (unsigned int)v15);
          return (unsigned int)v15;
        }
      }
    }
    v15 = -1073741789;
    goto LABEL_40;
  }
LABEL_28:
  v21 = *v12;
  *(_WORD *)(v6 + 16) |= 2u;
  *(_DWORD *)(v6 + 8) = RtlComputeCrc32(0, (PUCHAR)(v6 + 12), v21 - 8);
  *(_DWORD *)v6 = *(_DWORD *)v6 & 0xFFFFFFF0 | 1;
  v22 = *(_WORD *)v12 + 4;
  *(_WORD *)(v6 + 2) = v22;
  v31 = v22;
  if ( (_Config & 2) != 0 )
  {
    HsmiRpCompressBuffer((UCHAR *)v6, &v31);
    v22 = v31;
  }
  *a6 = v22;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14006b314  mov     [rsp+arg_10], rbx
0x14006b319  mov     [rsp+arg_0], rcx
0x14006b31e  push    rbp
0x14006b31f  push    rsi
0x14006b320  push    rdi
0x14006b321  push    r12
0x14006b323  push    r13
0x14006b325  push    r14
0x14006b327  push    r15
0x14006b329  sub     rsp, 20h
0x14006b32d  mov     rax, [rsp+58h+arg_28]
0x14006b335  xor     r14d, r14d
0x14006b338  mov     rdi, [rsp+58h+arg_20]
0x14006b340  mov     rsi, r8
0x14006b343  mov     r12d, r9d
0x14006b346  mov     r13d, edx
0x14006b349  movzx   eax, word ptr [rax]
0x14006b34c  lea     ecx, [r14+4]
0x14006b350  cmp     ax, cx
0x14006b353  jbe     loc_14006B599
0x14006b359  mov     ebp, eax
0x14006b35b  sub     ebp, ecx
0x14006b35d  xor     edx, edx; Val
0x14006b35f  mov     qword ptr [rdi+4], 70526546h
0x14006b367  lea     r15, [rdi+0Ch]
0x14006b36b  mov     dword ptr [rdi+10h], 0A0000h
0x14006b372  lea     rcx, [rdi+14h]; void *
0x14006b376  mov     dword ptr [r15], 60h ; '`'
0x14006b37d  lea     r8d, [rdx+50h]; Size
0x14006b381  call    memset
0x14006b386  mov     r8d, 1
0x14006b38c  cmp     ebp, 18h
0x14006b38f  jb      loc_14006B73D
0x14006b395  mov     eax, r14d
0x14006b398  mov     r14d, 0C0000023h
0x14006b39e  cmp     ax, [rdi+12h]
0x14006b3a2  jnb     loc_14006B74B
0x14006b3a8  mov     edx, [r15]
0x14006b3ab  mov     eax, ebp
0x14006b3ad  lea     rcx, [rdx+3]
0x14006b3b1  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14006b3b5  add     rcx, r8
0x14006b3b8  cmp     rcx, rax
0x14006b3bb  ja      loc_14006B743
0x14006b3c1  lea     eax, [rdx+3]
0x14006b3c4  and     eax, 0FFFFFFFCh
0x14006b3c7  mov     ecx, eax
0x14006b3c9  mov     [r15], ecx
0x14006b3cc  mov     dword ptr [rdi+14h], 10007h
0x14006b3d3  mov     [rdi+18h], ecx
0x14006b3d6  mov     [rax+rdi+4], r8b
0x14006b3db  add     [r15], r8d
0x14006b3de  xor     ebx, ebx
0x14006b3e0  mov     ecx, ebx
0x14006b3e2  call    HsmDbgBreakOnStatus
0x14006b3e7  xor     r8d, r8d
0x14006b3ea  test    ebx, ebx
0x14006b3ec  js      loc_14006B6DB
0x14006b3f2  cmp     ebp, 18h
0x14006b3f5  jb      loc_14006B725
0x14006b3fb  lea     r9d, [r8+1]
0x14006b3ff  cmp     r9w, [rdi+12h]
0x14006b404  jnb     loc_14006B755
0x14006b40a  cmp     ebp, 20h ; ' '
0x14006b40d  jb      loc_14006B725
0x14006b413  mov     edx, [r15]
0x14006b416  lea     r10d, [r8+4]
0x14006b41a  mov     eax, ebp
0x14006b41c  lea     rcx, [rdx+3]
0x14006b420  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14006b424  add     rcx, r10
0x14006b427  cmp     rcx, rax
0x14006b42a  ja      loc_14006B725
0x14006b430  lea     eax, [rdx+3]
0x14006b433  and     eax, 0FFFFFFFCh
0x14006b436  mov     [r15], eax
0x14006b439  cmp     [rdi+1Ch], r8w
0x14006b43e  jz      short loc_14006B445
0x14006b440  or      [rdi+10h], r9w
0x14006b445  mov     dword ptr [rdi+1Ch], 4000Ah
0x14006b44c  mov     ebx, r8d
0x14006b44f  mov     [rdi+20h], eax
0x14006b452  mov     [rax+rdi+4], r13d
0x14006b457  add     [r15], r10d
0x14006b45a  mov     ecx, ebx
0x14006b45c  call    HsmDbgBreakOnStatus
0x14006b461  xor     r9d, r9d
0x14006b464  test    ebx, ebx
0x14006b466  js      loc_14006B75F
0x14006b46c  cmp     ebp, 18h
0x14006b46f  jb      loc_14006B72D
0x14006b475  lea     eax, [r9+3]
0x14006b479  cmp     ax, [rdi+12h]
0x14006b47d  jnb     loc_14006B79E
0x14006b483  cmp     ebp, 30h ; '0'
0x14006b486  jb      loc_14006B72D
0x14006b48c  mov     edx, [r15]
0x14006b48f  movzx   r8d, r12w; Size
0x14006b493  lea     rcx, [rax+rdx]
0x14006b497  mov     eax, ebp
0x14006b499  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14006b49d  add     rcx, r8
0x14006b4a0  cmp     rcx, rax
0x14006b4a3  ja      loc_14006B72D
0x14006b4a9  cmp     [rdi+2Ch], r9w
0x14006b4ae  jnz     loc_14006B7A8
0x14006b4b4  lea     eax, [rdx+3]
0x14006b4b7  and     eax, 0FFFFFFFCh
0x14006b4ba  mov     [r15], eax
0x14006b4bd  mov     word ptr [rdi+2Ch], 11h
0x14006b4c3  mov     [rdi+2Eh], r8w
0x14006b4c8  mov     [rdi+30h], eax
0x14006b4cb  test    rsi, rsi
0x14006b4ce  jz      short loc_14006B4E9
0x14006b4d0  mov     ecx, eax
0x14006b4d2  add     rcx, 4
0x14006b4d6  add     rcx, rdi; void *
0x14006b4d9  cmp     rcx, rsi
0x14006b4dc  jz      short loc_14006B4E9
0x14006b4de  mov     rdx, rsi; Src
0x14006b4e1  call    memmove
0x14006b4e6  xor     r9d, r9d
0x14006b4e9  movzx   eax, word ptr [rdi+2Eh]
0x14006b4ed  mov     ebx, r9d
0x14006b4f0  add     [r15], eax
0x14006b4f3  mov     ecx, ebx
0x14006b4f5  call    HsmDbgBreakOnStatus
0x14006b4fa  xor     r12d, r12d
0x14006b4fd  test    ebx, ebx
0x14006b4ff  js      loc_14006B7B6
0x14006b505  lea     esi, [r12+2]
0x14006b50a  lea     r8d, [r12+8]
0x14006b50f  test    r13b, 10h
0x14006b513  jz      loc_14006B5A1
0x14006b519  lea     r13d, [r12+1]
0x14006b51e  mov     r8d, [r15]
0x14006b521  mov     rdx, r15; Buffer
0x14006b524  or      [rdi+10h], si
0x14006b528  sub     r8d, 8; Length
0x14006b52c  xor     ecx, ecx; InitialCrc
0x14006b52e  call    cs:__imp_RtlComputeCrc32
0x14006b535  nop     dword ptr [rax+rax+00h]
0x14006b53a  mov     [rdi+8], eax
0x14006b53d  mov     eax, [rdi]
0x14006b53f  and     eax, 0FFFFFFF1h
0x14006b542  or      eax, r13d
0x14006b545  mov     [rdi], eax
0x14006b547  movzx   eax, word ptr [r15]
0x14006b54b  add     ax, 4
0x14006b54f  movzx   ecx, ax
0x14006b552  mov     [rdi+2], cx
0x14006b556  mov     edx, dword ptr cs:__Config
0x14006b55c  mov     [rsp+58h+arg_8], ecx
0x14006b560  test    sil, dl
0x14006b563  jz      short loc_14006B576
0x14006b565  lea     rdx, [rsp+58h+arg_8]
0x14006b56a  mov     rcx, rdi
0x14006b56d  call    HsmiRpCompressBuffer
0x14006b572  mov     ecx, [rsp+58h+arg_8]
0x14006b576  mov     rax, [rsp+58h+arg_28]
0x14006b57e  mov     [rax], cx
0x14006b581  mov     eax, ebx
0x14006b583  mov     rbx, [rsp+58h+arg_10]
0x14006b588  add     rsp, 20h
0x14006b58c  pop     r15
0x14006b58e  pop     r14
0x14006b590  pop     r13
0x14006b592  pop     r12
0x14006b594  pop     rdi
0x14006b595  pop     rsi
0x14006b596  pop     rbp
0x14006b597  retn
0x14006b599  mov     ebp, r14d
0x14006b59c  jmp     loc_14006B35D
0x14006b5a1  cmp     ebp, 18h
0x14006b5a4  jb      loc_14006B717
0x14006b5aa  cmp     si, [rdi+12h]
0x14006b5ae  jnb     loc_14006B7F5
0x14006b5b4  cmp     ebp, 28h ; '('
0x14006b5b7  jb      loc_14006B717
0x14006b5bd  mov     edx, [r15]
0x14006b5c0  mov     eax, ebp
0x14006b5c2  lea     rcx, [rdx+3]
0x14006b5c6  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14006b5ca  add     rcx, r8
0x14006b5cd  cmp     rcx, rax
0x14006b5d0  ja      loc_14006B717
0x14006b5d6  lea     eax, [rdx+3]
0x14006b5d9  mov     r13d, 1
0x14006b5df  and     eax, 0FFFFFFFCh
0x14006b5e2  mov     [r15], eax
0x14006b5e5  cmp     [rdi+24h], r12w
0x14006b5ea  jz      short loc_14006B5F1
0x14006b5ec  or      [rdi+10h], r13w
0x14006b5f1  mov     rcx, [rsp+58h+arg_0]
0x14006b5f6  mov     ebx, r12d
0x14006b5f9  mov     dword ptr [rdi+24h], 80006h
0x14006b600  mov     [rdi+28h], eax
0x14006b603  mov     [rax+rdi+4], rcx
0x14006b608  add     [r15], r8d
0x14006b60b  mov     ecx, ebx
0x14006b60d  call    HsmDbgBreakOnStatus
0x14006b612  test    ebx, ebx
0x14006b614  js      loc_14006B7FF
0x14006b61a  cmp     ebp, 18h
0x14006b61d  jb      loc_14006B735
0x14006b623  mov     eax, 9
0x14006b628  cmp     ax, [rdi+12h]
0x14006b62c  jnb     loc_14006B836
0x14006b632  cmp     ebp, 60h ; '`'
0x14006b635  jb      loc_14006B735
0x14006b63b  mov     edx, [r15]
0x14006b63e  lea     r8d, [rax-5]
0x14006b642  mov     eax, ebp
0x14006b644  lea     rcx, [rdx+3]
0x14006b648  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14006b64c  add     rcx, r8
0x14006b64f  cmp     rcx, rax
0x14006b652  ja      loc_14006B735
0x14006b658  lea     eax, [rdx+3]
0x14006b65b  and     eax, 0FFFFFFFCh
0x14006b65e  mov     [r15], eax
0x14006b661  cmp     [rdi+5Ch], r12w
0x14006b666  jz      short loc_14006B66D
0x14006b668  or      [rdi+10h], r13w
0x14006b66d  mov     dword ptr [rdi+5Ch], 4000Ah
0x14006b674  mov     ebx, r12d
0x14006b677  mov     [rdi+60h], eax
0x14006b67a  mov     [rax+rdi+4], r12d
0x14006b67f  add     [r15], r8d
0x14006b682  mov     ecx, ebx
0x14006b684  call    HsmDbgBreakOnStatus
0x14006b689  test    ebx, ebx
0x14006b68b  jns     loc_14006B51E
0x14006b691  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b698  lea     rax, WPP_GLOBAL_Control
0x14006b69f  cmp     rcx, rax
0x14006b6a2  jz      loc_14006B581
0x14006b6a8  mov     eax, [rcx+2Ch]
0x14006b6ab  test    r13b, al
0x14006b6ae  jz      loc_14006B581
0x14006b6b4  cmp     [rcx+29h], sil
0x14006b6b8  jb      loc_14006B581
0x14006b6be  mov     edx, 0Eh
0x14006b6c3  mov     rcx, [rcx+18h]
0x14006b6c7  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14006b6ce  mov     r9d, ebx
0x14006b6d1  call    WPP_SF_d
0x14006b6d6  jmp     loc_14006B581
0x14006b6db  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b6e2  lea     rax, WPP_GLOBAL_Control
0x14006b6e9  cmp     rcx, rax
0x14006b6ec  jz      loc_14006B581
0x14006b6f2  mov     eax, [rcx+2Ch]
0x14006b6f5  mov     r13d, 1
0x14006b6fb  test    r13b, al
0x14006b6fe  jz      loc_14006B581
0x14006b704  lea     esi, [r13+1]
0x14006b708  cmp     [rcx+29h], sil
0x14006b70c  jb      loc_14006B581
0x14006b712  lea     edx, [rsi+8]
0x14006b715  jmp     short loc_14006B6C3
0x14006b717  mov     ebx, r14d
0x14006b71a  mov     r13d, 1
0x14006b720  jmp     loc_14006B60B
0x14006b725  mov     ebx, r14d
0x14006b728  jmp     loc_14006B45A
0x14006b72d  mov     ebx, r14d
0x14006b730  jmp     loc_14006B4F3
0x14006b735  mov     ebx, r14d
0x14006b738  jmp     loc_14006B682
0x14006b73d  mov     r14d, 0C0000023h
0x14006b743  mov     ebx, r14d
0x14006b746  jmp     loc_14006B3E0
0x14006b74b  mov     ebx, 0C000000Dh
0x14006b750  jmp     loc_14006B3E0
0x14006b755  mov     ebx, 0C000000Dh
0x14006b75a  jmp     loc_14006B45A
0x14006b75f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b766  lea     rax, WPP_GLOBAL_Control
0x14006b76d  cmp     rcx, rax
0x14006b770  jz      loc_14006B581
0x14006b776  mov     eax, [rcx+2Ch]
0x14006b779  mov     r13d, 1
0x14006b77f  test    r13b, al
0x14006b782  jz      loc_14006B581
0x14006b788  lea     esi, [r13+1]
0x14006b78c  cmp     [rcx+29h], sil
0x14006b790  jb      loc_14006B581
0x14006b796  lea     edx, [rsi+9]
0x14006b799  jmp     loc_14006B6C3
0x14006b79e  mov     ebx, 0C000000Dh
0x14006b7a3  jmp     loc_14006B4F3
0x14006b7a8  mov     eax, 1
0x14006b7ad  or      [rdi+10h], ax
0x14006b7b1  jmp     loc_14006B4B4
0x14006b7b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b7bd  lea     rax, WPP_GLOBAL_Control
0x14006b7c4  cmp     rcx, rax
0x14006b7c7  jz      loc_14006B581
  ... truncated ...
```

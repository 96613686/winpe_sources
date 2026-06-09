# CscSidMappAddSid

- ea: `0x14005c8a8`
- end: `0x14005cabd`
- name: `CscSidMappAddSid`
- size: `533`
- prototype: `__int64 __fastcall(__int64, void *, unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400720fc`
- `0x140080c40`

## callees

- `0x14001a494`
- `0x14001b568`
- `0x1400287bc`
- `0x14002f140`
- `0x14005c8a8`
- `0x14005cac4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005c95f`
- `ntoskrnl!ExAllocatePool2` at `0x14005c9ea`
- `ntoskrnl!ExAllocatePool2` at `0x14005c95f`
- `ntoskrnl!ExAllocatePool2` at `0x14005c9ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ca41`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ca41`
- `ntoskrnl!RtlLengthSid` at `0x14005c9c5`
- `ntoskrnl!RtlLengthSid` at `0x14005c9c5`

## pseudocode

```c
__int64 __fastcall CscSidMappAddSid(__int64 a1, void *a2, unsigned __int16 *a3, __int64 a4)
{
  unsigned int *v4; // rbx
  unsigned __int16 v8; // r15
  unsigned int v9; // eax
  int v10; // ecx
  unsigned int v11; // esi
  unsigned int *v12; // rdi
  int v13; // ebx
  int v14; // esi
  unsigned __int64 v15; // rax
  unsigned int *Pool2; // rax
  unsigned int v17; // eax
  unsigned int i; // ecx
  __int64 v19; // rax
  ULONG v20; // eax
  __int64 v21; // rbp
  size_t v22; // rbx
  __int64 v23; // r9
  void *v24; // rax

  v4 = *(unsigned int **)(a1 + 56);
  v8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids, a1, a2);
  if ( !v4 )
  {
    v9 = 0;
    v10 = 4;
LABEL_10:
    v11 = v10;
    goto LABEL_11;
  }
  v9 = v4[1];
  if ( *v4 != v9 )
  {
    v12 = v4;
    goto LABEL_24;
  }
  v10 = v9 + 4;
  v11 = 0xFFFF;
  if ( v9 + 4 <= 0xFFFF )
    goto LABEL_10;
LABEL_11:
  if ( v11 == v9 )
  {
    v13 = -1073741442;
    v14 = 652;
    goto LABEL_31;
  }
  v15 = 16LL * v11;
  if ( v15 > 0xFFFFFFFF )
  {
    v13 = -1073741675;
    goto LABEL_30;
  }
  Pool2 = (unsigned int *)ExAllocatePool2(256, (unsigned int)(v15 + 8), 591426371, a4);
  v12 = Pool2;
  if ( !Pool2 )
  {
    v13 = -1073741670;
LABEL_30:
    v14 = 661;
    goto LABEL_31;
  }
  *Pool2 = v11;
  if ( v4 )
    v17 = v4[1];
  else
    v17 = 0;
  v12[1] = v17;
  if ( v4 )
  {
    for ( i = 0; i < v4[1]; *(_QWORD *)&v4[2 * v19 + 4] = 0 )
    {
      v19 = i++;
      v19 *= 2;
      *(_OWORD *)&v12[2 * v19 + 2] = *(_OWORD *)&v4[2 * v19 + 2];
    }
    CscSidMappDestroySidArray(v4);
  }
  *(_QWORD *)(a1 + 56) = v12;
LABEL_24:
  v20 = RtlLengthSid(a2);
  v21 = 2LL * v12[1];
  v22 = v20;
  v12[4 * v12[1] + 2] = v20;
  v24 = (void *)ExAllocatePool2(258, v20, 591426371, v23);
  *(_QWORD *)&v12[2 * v21 + 4] = v24;
  if ( v24 )
  {
    v14 = 0;
    memmove(v24, a2, v22);
    ++v12[1];
    v13 = CscSidMappSave(a1, 1);
    if ( v13 >= 0 )
    {
      v8 = *((_WORD *)v12 + 2);
      v13 = 0;
    }
    else
    {
      --v12[1];
      ExFreePoolWithTag(*(PVOID *)&v12[2 * v21 + 4], 0x23407343u);
      *(_QWORD *)&v12[2 * v21 + 4] = 0;
    }
  }
  else
  {
    v13 = -1073741670;
    v14 = 706;
  }
LABEL_31:
  *a3 = v8;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids, v8, v13, v14);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14005c8a8  push    rbx
0x14005c8aa  push    rbp
0x14005c8ab  push    rsi
0x14005c8ac  push    rdi
0x14005c8ad  push    r12
0x14005c8af  push    r13
0x14005c8b1  push    r14
0x14005c8b3  push    r15
0x14005c8b5  sub     rsp, 38h
0x14005c8b9  mov     rbx, [rcx+38h]
0x14005c8bd  mov     r13, r8
0x14005c8c0  mov     r12, rdx
0x14005c8c3  mov     r14, rcx
0x14005c8c6  xor     r15d, r15d
0x14005c8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c8d0  lea     rax, WPP_GLOBAL_Control
0x14005c8d7  cmp     rcx, rax
0x14005c8da  jz      short loc_14005C901
0x14005c8dc  test    dword ptr [rcx+2Ch], 40000h
0x14005c8e3  jz      short loc_14005C901
0x14005c8e5  mov     rcx, [rcx+18h]
0x14005c8e9  lea     edx, [r15+0Eh]
0x14005c8ed  mov     r9, r14
0x14005c8f0  mov     [rsp+78h+var_58], r12
0x14005c8f5  lea     r8, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids
0x14005c8fc  call    WPP_SF_qq
0x14005c901  mov     edx, 0FFFFFFFFh
0x14005c906  test    rbx, rbx
0x14005c909  jz      short loc_14005C928
0x14005c90b  mov     eax, [rbx+4]
0x14005c90e  cmp     [rbx], eax
0x14005c910  jnz     short loc_14005C920
0x14005c912  lea     ecx, [rax+4]
0x14005c915  mov     esi, 0FFFFh
0x14005c91a  cmp     ecx, esi
0x14005c91c  ja      short loc_14005C92F
0x14005c91e  jmp     short loc_14005C92D
0x14005c920  mov     rdi, rbx
0x14005c923  jmp     loc_14005C9C2
0x14005c928  xor     eax, eax
0x14005c92a  lea     ecx, [rax+4]
0x14005c92d  mov     esi, ecx
0x14005c92f  cmp     esi, eax
0x14005c931  jnz     short loc_14005C942
0x14005c933  mov     ebx, 0C000017Eh
0x14005c938  mov     esi, 28Ch
0x14005c93d  jmp     loc_14005CA67
0x14005c942  mov     eax, esi
0x14005c944  shl     rax, 4
0x14005c948  cmp     rax, rdx
0x14005c94b  ja      loc_14005CA5D
0x14005c951  lea     edx, [rax+8]
0x14005c954  mov     ecx, 100h
0x14005c959  mov     r8d, 23407343h
0x14005c95f  call    cs:__imp_ExAllocatePool2
0x14005c966  nop     dword ptr [rax+rax+00h]
0x14005c96b  mov     rdi, rax
0x14005c96e  test    rax, rax
0x14005c971  jnz     short loc_14005C97D
0x14005c973  mov     ebx, 0C000009Ah
0x14005c978  jmp     loc_14005CA62
0x14005c97d  mov     [rax], esi
0x14005c97f  test    rbx, rbx
0x14005c982  jz      short loc_14005C989
0x14005c984  mov     eax, [rbx+4]
0x14005c987  jmp     short loc_14005C98B
0x14005c989  xor     eax, eax
0x14005c98b  mov     [rdi+4], eax
0x14005c98e  test    rbx, rbx
0x14005c991  jz      short loc_14005C9BE
0x14005c993  xor     ecx, ecx
0x14005c995  cmp     [rbx+4], ecx
0x14005c998  jbe     short loc_14005C9B6
0x14005c99a  mov     eax, ecx
0x14005c99c  inc     ecx
0x14005c99e  add     rax, rax
0x14005c9a1  movups  xmm0, xmmword ptr [rbx+rax*8+8]
0x14005c9a6  movdqu  xmmword ptr [rdi+rax*8+8], xmm0
0x14005c9ac  mov     [rbx+rax*8+10h], r15
0x14005c9b1  cmp     ecx, [rbx+4]
0x14005c9b4  jb      short loc_14005C99A
0x14005c9b6  mov     rcx, rbx; P
0x14005c9b9  call    CscSidMappDestroySidArray
0x14005c9be  mov     [r14+38h], rdi
0x14005c9c2  mov     rcx, r12; Sid
0x14005c9c5  call    cs:__imp_RtlLengthSid
0x14005c9cc  nop     dword ptr [rax+rax+00h]
0x14005c9d1  mov     ebp, [rdi+4]
0x14005c9d4  mov     r8d, 23407343h
0x14005c9da  add     rbp, rbp
0x14005c9dd  mov     edx, eax
0x14005c9df  mov     ecx, 102h
0x14005c9e4  mov     ebx, eax
0x14005c9e6  mov     [rdi+rbp*8+8], eax
0x14005c9ea  call    cs:__imp_ExAllocatePool2
0x14005c9f1  nop     dword ptr [rax+rax+00h]
0x14005c9f6  mov     [rdi+rbp*8+10h], rax
0x14005c9fb  test    rax, rax
0x14005c9fe  jnz     short loc_14005CA0C
0x14005ca00  mov     ebx, 0C000009Ah
0x14005ca05  mov     esi, 2C2h
0x14005ca0a  jmp     short loc_14005CA67
0x14005ca0c  mov     r8, rbx; Size
0x14005ca0f  mov     rdx, r12; Src
0x14005ca12  mov     rcx, rax; void *
0x14005ca15  xor     esi, esi
0x14005ca17  call    memmove
0x14005ca1c  inc     dword ptr [rdi+4]
0x14005ca1f  mov     dl, 1
0x14005ca21  mov     rcx, r14
0x14005ca24  call    CscSidMappSave
0x14005ca29  mov     ebx, eax
0x14005ca2b  test    eax, eax
0x14005ca2d  jns     short loc_14005CA54
0x14005ca2f  mov     eax, 0FFFFFFFFh
0x14005ca34  mov     edx, 23407343h; Tag
0x14005ca39  add     [rdi+4], eax
0x14005ca3c  mov     rcx, [rdi+rbp*8+10h]; P
0x14005ca41  call    cs:__imp_ExFreePoolWithTag
0x14005ca48  nop     dword ptr [rax+rax+00h]
0x14005ca4d  mov     [rdi+rbp*8+10h], rsi
0x14005ca52  jmp     short loc_14005CA67
0x14005ca54  movzx   r15d, word ptr [rdi+4]
0x14005ca59  xor     ebx, ebx
0x14005ca5b  jmp     short loc_14005CA67
0x14005ca5d  mov     ebx, 0C0000095h
0x14005ca62  mov     esi, 295h
0x14005ca67  mov     [r13+0], r15w
0x14005ca6c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ca73  lea     rax, WPP_GLOBAL_Control
0x14005ca7a  cmp     rcx, rax
0x14005ca7d  jz      short loc_14005CAA9
0x14005ca7f  test    dword ptr [rcx+2Ch], 40000h
0x14005ca86  jz      short loc_14005CAA9
0x14005ca88  mov     rcx, [rcx+18h]
0x14005ca8c  lea     r8, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids
0x14005ca93  movzx   r9d, r15w
0x14005ca97  mov     edx, 0Fh
0x14005ca9c  mov     [rsp+78h+var_50], esi
0x14005caa0  mov     dword ptr [rsp+78h+var_58], ebx
0x14005caa4  call    WPP_SF_DDd
0x14005caa9  mov     eax, ebx
0x14005caab  add     rsp, 38h
0x14005caaf  pop     r15
0x14005cab1  pop     r14
0x14005cab3  pop     r13
0x14005cab5  pop     r12
0x14005cab7  pop     rdi
0x14005cab8  pop     rsi
0x14005cab9  pop     rbp
0x14005caba  pop     rbx
0x14005cabb  retn
```

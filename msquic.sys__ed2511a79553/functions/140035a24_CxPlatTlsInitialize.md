# CxPlatTlsInitialize

- ea: `0x140035a24`
- end: `0x140035c44`
- name: `CxPlatTlsInitialize`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000554c`

## callees

- `0x140035a24`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003ec10`
- `0x14003ed00`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140035b5f`
- `ntoskrnl!_snprintf_s` at `0x140035b5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035c07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035c07`
- `ntoskrnl!ExAllocatePool2` at `0x140035ab4`
- `ntoskrnl!ExAllocatePool2` at `0x140035ab4`

## string_xrefs

- `0x140035a8c`: `Mismatched SEC_CONFIG IsServer state`
- `0x140035b4e`: `TLS context Created`

## pseudocode

```c
__int64 __fastcall CxPlatTlsInitialize(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v4; // ebp
  _BOOL8 v7; // rcx
  unsigned int v8; // esi
  _QWORD *Pool2; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rbx
  char v13; // al
  __int64 v14; // rcx
  _WORD *v15; // rcx
  void *v16; // rcx
  char DstBuf[128]; // [rsp+20h] [rbp-C8h] BYREF

  v4 = *(unsigned __int16 *)(a1 + 40) + 10;
  v7 = (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 16LL) & 1) == 0;
  if ( *(_BYTE *)a1 == v7 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(66, v4 + 2192LL, 1160864593);
    v8 = 0;
    v12 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, 0x890u);
      v13 = *(_BYTE *)v12;
      v12[3] = -1;
      v12[2] = -1;
      *(_BYTE *)v12 = v13 ^ (*(_BYTE *)a1 ^ v13) & 1;
      v12[9] = *(_QWORD *)(a1 + 8);
      v12[5] = *(_QWORD *)(a1 + 16);
      *((_WORD *)v12 + 1) = *(_WORD *)(a1 + 42);
      v12[1] = *(_QWORD *)(a1 + 48);
      v12[4] = *(_QWORD *)(a1 + 24);
      v12[273] = *(_QWORD *)(a1 + 88);
      if ( (byte_14005C48C & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TLS context Created");
        McTemplateU0ps_EtwWriteTransfer(v14, QuicConnLogVerbose, v12[9], DstBuf);
      }
      *((_DWORD *)v12 + 14) = v4;
      v12[6] = v12 + 274;
      *((_DWORD *)v12 + 548) = *(unsigned __int16 *)(a1 + 40) + 6;
      *((_DWORD *)v12 + 549) = 2;
      *((_WORD *)v12 + 1100) = *(_WORD *)(a1 + 40);
      memmove((char *)v12 + 2202, *(const void **)(a1 + 32), *(unsigned __int16 *)(a1 + 40));
      v15 = *(_WORD **)(a1 + 72);
      v12[8] = v15;
      *v15 = *(_WORD *)(a1 + 42);
      *(_WORD *)(v12[8] + 2LL) = *(_BYTE *)a1 != 0 ? 8 : 1;
      *(_DWORD *)(v12[8] + 4LL) = 0;
      *(_WORD *)(v12[8] + 8LL) = *(_WORD *)(a1 + 80) - 10;
      *(_DWORD *)(a2 + 4) = 1;
      v16 = *(void **)(a1 + 56);
      if ( v16 )
        ExFreePoolWithTag(v16, 0x38336351u);
      *a3 = v12;
    }
    else
    {
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(v11, v10, "CXPLAT_TLS", 2192);
      return (unsigned int)-1073741801;
    }
  }
  else
  {
    if ( byte_14005C48D < 0 )
      McTemplateU0ps_EtwWriteTransfer(v7, QuicTlsError, *(_QWORD *)(a1 + 8), "Mismatched SEC_CONFIG IsServer state");
    return (unsigned int)-1073741811;
  }
  return v8;
}

```

## disassembly

```asm
0x140035a24  mov     [rsp+arg_18], rbx
0x140035a29  push    rbp
0x140035a2a  push    rsi
0x140035a2b  push    rdi
0x140035a2c  push    r12
0x140035a2e  push    r13
0x140035a30  push    r14
0x140035a32  push    r15
0x140035a34  sub     rsp, 0B0h
0x140035a3b  mov     rax, cs:__security_cookie
0x140035a42  xor     rax, rsp
0x140035a45  mov     [rsp+0E8h+var_48], rax
0x140035a4d  movzx   ebp, word ptr [rcx+28h]
0x140035a51  mov     rdi, rcx
0x140035a54  mov     rax, [rcx+18h]
0x140035a58  add     ebp, 0Ah
0x140035a5b  mov     r15, rdx
0x140035a5e  mov     r12d, 890h
0x140035a64  mov     edx, ebp
0x140035a66  mov     r13d, 1
0x140035a6c  add     rdx, r12
0x140035a6f  mov     r14, r8
0x140035a72  mov     ecx, [rax+10h]
0x140035a75  not     ecx
0x140035a77  and     ecx, r13d
0x140035a7a  cmp     [rdi], cl
0x140035a7c  jz      short loc_140035AA9
0x140035a7e  mov     al, cs:byte_14005C48D
0x140035a84  test    al, al
0x140035a86  jns     short loc_140035A9F
0x140035a88  mov     r8, [rdi+8]
0x140035a8c  lea     r9, aMismatchedSecC; "Mismatched SEC_CONFIG IsServer state"
0x140035a93  lea     rdx, QuicTlsError
0x140035a9a  call    McTemplateU0ps_EtwWriteTransfer
0x140035a9f  mov     esi, 0C000000Dh
0x140035aa4  jmp     loc_140035C16
0x140035aa9  mov     ecx, 42h ; 'B'
0x140035aae  mov     r8d, 45316351h
0x140035ab4  call    cs:__imp_ExAllocatePool2
0x140035abb  nop     dword ptr [rax+rax+00h]
0x140035ac0  xor     esi, esi
0x140035ac2  mov     rbx, rax
0x140035ac5  test    rax, rax
0x140035ac8  jnz     short loc_140035AEC
0x140035aca  test    cs:Microsoft_QuicEnableBits, 2
0x140035ad1  jz      short loc_140035AE2
0x140035ad3  mov     r9, r12
0x140035ad6  lea     r8, aCxplatTls; "CXPLAT_TLS"
0x140035add  call    McTemplateU0sx_EtwWriteTransfer
0x140035ae2  mov     esi, 0C0000017h
0x140035ae7  jmp     loc_140035C16
0x140035aec  mov     r8, r12; Size
0x140035aef  xor     edx, edx; Val
0x140035af1  mov     rcx, rbx; void *
0x140035af4  call    memset
0x140035af9  mov     al, [rbx]
0x140035afb  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140035aff  mov     [rbx+18h], r8
0x140035b03  mov     cl, al
0x140035b05  mov     [rbx+10h], r8
0x140035b09  xor     cl, [rdi]
0x140035b0b  and     cl, r13b
0x140035b0e  xor     cl, al
0x140035b10  mov     [rbx], cl
0x140035b12  mov     rax, [rdi+8]
0x140035b16  mov     [rbx+48h], rax
0x140035b1a  mov     rax, [rdi+10h]
0x140035b1e  mov     [rbx+28h], rax
0x140035b22  movzx   eax, word ptr [rdi+2Ah]
0x140035b26  mov     [rbx+2], ax
0x140035b2a  mov     rax, [rdi+30h]
0x140035b2e  mov     [rbx+8], rax
0x140035b32  mov     rax, [rdi+18h]
0x140035b36  mov     [rbx+20h], rax
0x140035b3a  mov     rax, [rdi+58h]
0x140035b3e  mov     [rbx+888h], rax
0x140035b45  test    cs:byte_14005C48C, r13b
0x140035b4c  jz      short loc_140035B80
0x140035b4e  lea     r9, aTlsContextCrea; "TLS context Created"
0x140035b55  mov     edx, 80h; SizeInBytes
0x140035b5a  lea     rcx, [rsp+0E8h+DstBuf]; DstBuf
0x140035b5f  call    cs:__imp__snprintf_s
0x140035b66  nop     dword ptr [rax+rax+00h]
0x140035b6b  mov     r8, [rbx+48h]
0x140035b6f  lea     r9, [rsp+0E8h+DstBuf]
0x140035b74  lea     rdx, QuicConnLogVerbose
0x140035b7b  call    McTemplateU0ps_EtwWriteTransfer
0x140035b80  mov     [rbx+38h], ebp
0x140035b83  lea     rcx, [rbx+890h]
0x140035b8a  mov     [rbx+30h], rcx
0x140035b8e  movzx   eax, word ptr [rdi+28h]
0x140035b92  add     eax, 6
0x140035b95  mov     [rcx], eax
0x140035b97  mov     dword ptr [rcx+4], 2
0x140035b9e  movzx   eax, word ptr [rdi+28h]
0x140035ba2  mov     [rcx+8], ax
0x140035ba6  add     rcx, 0Ah; void *
0x140035baa  movzx   r8d, word ptr [rdi+28h]; Size
0x140035baf  mov     rdx, [rdi+20h]; Src
0x140035bb3  call    memmove
0x140035bb8  mov     rcx, [rdi+48h]
0x140035bbc  mov     [rbx+40h], rcx
0x140035bc0  movzx   eax, word ptr [rdi+2Ah]
0x140035bc4  mov     [rcx], ax
0x140035bc7  mov     al, [rdi]
0x140035bc9  neg     al
0x140035bcb  mov     rax, [rbx+40h]
0x140035bcf  sbb     cx, cx
0x140035bd2  and     cx, 7
0x140035bd6  add     cx, r13w
0x140035bda  mov     [rax+2], cx
0x140035bde  mov     rax, [rbx+40h]
0x140035be2  mov     [rax+4], esi
0x140035be5  movzx   ecx, word ptr [rdi+50h]
0x140035be9  mov     rax, [rbx+40h]
0x140035bed  sub     cx, 0Ah
0x140035bf1  mov     [rax+8], cx
0x140035bf5  mov     [r15+4], r13d
0x140035bf9  mov     rcx, [rdi+38h]; P
0x140035bfd  test    rcx, rcx
0x140035c00  jz      short loc_140035C13
0x140035c02  mov     edx, 38336351h; Tag
0x140035c07  call    cs:__imp_ExFreePoolWithTag
0x140035c0e  nop     dword ptr [rax+rax+00h]
0x140035c13  mov     [r14], rbx
0x140035c16  mov     eax, esi
0x140035c18  mov     rcx, [rsp+0E8h+var_48]
0x140035c20  xor     rcx, rsp; StackCookie
0x140035c23  call    __security_check_cookie
0x140035c28  mov     rbx, [rsp+0E8h+arg_18]
0x140035c30  add     rsp, 0B0h
0x140035c37  pop     r15
0x140035c39  pop     r14
0x140035c3b  pop     r13
0x140035c3d  pop     r12
0x140035c3f  pop     rdi
0x140035c40  pop     rsi
0x140035c41  pop     rbp
0x140035c42  retn
```

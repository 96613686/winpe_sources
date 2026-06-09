# CfpExecuteAckDelete

- ea: `0x18000a9a0`
- end: `0x18000ac4a`
- name: `CfpExecuteAckDelete`
- size: `682`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006010`

## callees

- `0x180001aa0`
- `0x1800092f8`
- `0x18000a9a0`
- `0x18000b5a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000abfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000abfc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aa2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aa2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac10`
- `FLTLIB!FilterSendMessage` at `0x18000abdf`
- `FLTLIB!FilterSendMessage` at `0x18000abdf`

## pseudocode

```c
__int64 __fastcall CfpExecuteAckDelete(__int64 a1, __int64 a2)
{
  _BYTE *v2; // rdi
  unsigned int v3; // esi
  int MessageHeaderSize; // eax
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  HANDLE ProcessHeap; // rax
  int v10; // ebx
  int v11; // r15d
  int v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  HANDLE v19; // rax
  DWORD BytesReturned[4]; // [rsp+30h] [rbp-158h] BYREF
  _BYTE InBuffer[256]; // [rsp+40h] [rbp-148h] BYREF

  v2 = InBuffer;
  v3 = 256;
  BytesReturned[0] = 0;
  MessageHeaderSize = CfpGetMessageHeaderSize();
  if ( ((MessageHeaderSize + 3) & 0xFFFFFFFC) + 12 < v7 )
    goto LABEL_8;
  v3 = ((CfpGetMessageHeaderSize() + 11) & 0xFFFFFFFC) + 4;
  if ( v3 <= v8 )
  {
    v10 = 87;
    if ( v3 < 0xC8 )
      goto LABEL_9;
    goto LABEL_8;
  }
  ProcessHeap = GetProcessHeap();
  v2 = HeapAlloc(ProcessHeap, 0, v3);
  v10 = v2 == 0 ? 8 : 0;
  if ( !v2 )
    v10 |= 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_8:
    v10 = 0;
LABEL_9:
    if ( v10 )
      v10 |= 0x80070000;
    if ( v10 < 0 )
      goto LABEL_31;
    v11 = *(_DWORD *)(a2 + 12);
    v12 = *(_DWORD *)(a2 + 8);
    v10 = CfpBuildMessageHeader((__int64)v2, v3, a1, 513);
    if ( v10 < 0 )
      goto LABEL_31;
    if ( v3 >= 0x18 )
    {
      if ( *((_WORD *)v2 + 7) <= 0xAu )
        goto LABEL_16;
      if ( v3 < 0x68 )
        goto LABEL_14;
      v13 = *((unsigned int *)v2 + 2);
      if ( ((v13 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v3 )
        goto LABEL_14;
      v14 = ((_DWORD)v13 + 3) & 0xFFFFFFFC;
      *((_DWORD *)v2 + 2) = v14;
      if ( *((_WORD *)v2 + 48) )
        *((_WORD *)v2 + 6) |= 1u;
      *((_DWORD *)v2 + 25) = v14;
      *((_DWORD *)v2 + 24) = 262154;
      *(_DWORD *)&v2[v14] = v11;
      *((_DWORD *)v2 + 2) += 4;
      if ( *((_WORD *)v2 + 7) <= 5u )
        goto LABEL_16;
      v15 = *((unsigned int *)v2 + 2);
      if ( ((v15 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v3 )
        goto LABEL_14;
      v16 = ((_DWORD)v15 + 3) & 0xFFFFFFFC;
      *((_DWORD *)v2 + 2) = v16;
      if ( *((_WORD *)v2 + 28) )
        *((_WORD *)v2 + 6) |= 1u;
      *((_DWORD *)v2 + 15) = v16;
      *((_DWORD *)v2 + 14) = 262154;
      *(_DWORD *)&v2[v16] = v12;
      *((_DWORD *)v2 + 2) += 4;
      if ( *((_WORD *)v2 + 7) <= 0xDu )
      {
LABEL_16:
        v10 = -1073741811;
        goto LABEL_31;
      }
      if ( v3 >= 0x80 )
      {
        v17 = *((unsigned int *)v2 + 2);
        if ( ((v17 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v3 )
        {
          v18 = ((_DWORD)v17 + 3) & 0xFFFFFFFC;
          *((_DWORD *)v2 + 2) = v18;
          if ( *((_WORD *)v2 + 60) )
            *((_WORD *)v2 + 6) |= 1u;
          *((_DWORD *)v2 + 31) = v18;
          *((_DWORD *)v2 + 30) = 262154;
          *(_DWORD *)&v2[v18] = 4;
          *((_DWORD *)v2 + 2) += 4;
          *((_WORD *)v2 + 6) &= ~2u;
          *((_DWORD *)v2 + 1) = 0;
          v10 = FilterSendMessage(hPort, v2, *((_DWORD *)v2 + 2), 0, 0, BytesReturned);
          goto LABEL_31;
        }
      }
    }
LABEL_14:
    v10 = -1073741789;
  }
LABEL_31:
  if ( v2 && v2 != InBuffer )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v2);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a9a0  mov     [rsp+arg_10], rbx
0x18000a9a5  push    rbp
0x18000a9a6  push    rsi
0x18000a9a7  push    rdi
0x18000a9a8  push    r12
0x18000a9aa  push    r13
0x18000a9ac  push    r14
0x18000a9ae  push    r15
0x18000a9b0  sub     rsp, 150h
0x18000a9b7  mov     rax, cs:__security_cookie
0x18000a9be  xor     rax, rsp
0x18000a9c1  mov     [rsp+188h+var_48], rax
0x18000a9c9  mov     r8d, 100h
0x18000a9cf  lea     rdi, [rsp+188h+InBuffer]
0x18000a9d4  xor     r12d, r12d
0x18000a9d7  mov     esi, r8d
0x18000a9da  mov     [rsp+188h+BytesReturned], r12d
0x18000a9df  mov     r14, rdx
0x18000a9e2  mov     rbp, rcx
0x18000a9e5  call    CfpGetMessageHeaderSize
0x18000a9ea  add     eax, 3
0x18000a9ed  mov     r13d, 0FFFFFFFCh
0x18000a9f3  and     eax, r13d
0x18000a9f6  mov     r15d, 80070000h
0x18000a9fc  add     eax, 0Ch
0x18000a9ff  cmp     eax, r8d
0x18000aa02  jb      short loc_18000AA65
0x18000aa04  call    CfpGetMessageHeaderSize
0x18000aa09  lea     esi, [rax+0Bh]
0x18000aa0c  and     esi, r13d
0x18000aa0f  add     esi, 4
0x18000aa12  cmp     esi, r8d
0x18000aa15  jbe     short loc_18000AA58
0x18000aa17  call    cs:__imp_GetProcessHeap
0x18000aa1e  nop     dword ptr [rax+rax+00h]
0x18000aa23  mov     r8d, esi; dwBytes
0x18000aa26  xor     edx, edx; dwFlags
0x18000aa28  mov     rcx, rax; hHeap
0x18000aa2b  call    cs:__imp_HeapAlloc
0x18000aa32  nop     dword ptr [rax+rax+00h]
0x18000aa37  mov     rdi, rax
0x18000aa3a  neg     rax
0x18000aa3d  sbb     ebx, ebx
0x18000aa3f  not     ebx
0x18000aa41  and     ebx, 8
0x18000aa44  mov     eax, ebx
0x18000aa46  or      eax, r15d
0x18000aa49  test    rdi, rdi
0x18000aa4c  cmovz   ebx, eax
0x18000aa4f  test    ebx, ebx
0x18000aa51  jns     short loc_18000AA65
0x18000aa53  jmp     loc_18000ABED
0x18000aa58  mov     ebx, 57h ; 'W'
0x18000aa5d  cmp     esi, 0C8h
0x18000aa63  jb      short loc_18000AA68
0x18000aa65  mov     ebx, r12d
0x18000aa68  mov     eax, ebx
0x18000aa6a  or      eax, r15d
0x18000aa6d  test    ebx, ebx
0x18000aa6f  cmovnz  ebx, eax
0x18000aa72  test    ebx, ebx
0x18000aa74  js      loc_18000ABED
0x18000aa7a  mov     r15d, [r14+0Ch]
0x18000aa7e  mov     r9d, 201h
0x18000aa84  mov     r14d, [r14+8]
0x18000aa88  mov     r8, rbp
0x18000aa8b  mov     edx, esi
0x18000aa8d  mov     rcx, rdi
0x18000aa90  call    CfpBuildMessageHeader
0x18000aa95  mov     ebx, eax
0x18000aa97  test    eax, eax
0x18000aa99  js      loc_18000ABED
0x18000aa9f  cmp     esi, 18h
0x18000aaa2  jnb     short loc_18000AAAE
0x18000aaa4  mov     ebx, 0C0000023h
0x18000aaa9  jmp     loc_18000ABED
0x18000aaae  mov     r9d, 0Ah
0x18000aab4  cmp     r9w, [rdi+0Eh]
0x18000aab9  jb      short loc_18000AAC5
0x18000aabb  mov     ebx, 0C000000Dh
0x18000aac0  jmp     loc_18000ABED
0x18000aac5  cmp     esi, 68h ; 'h'
0x18000aac8  jb      short loc_18000AAA4
0x18000aaca  mov     edx, [rdi+8]
0x18000aacd  mov     r8d, 4
0x18000aad3  mov     eax, esi
0x18000aad5  lea     rcx, [rdx+3]
0x18000aad9  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000aadd  add     rcx, r8
0x18000aae0  cmp     rcx, rax
0x18000aae3  ja      short loc_18000AAA4
0x18000aae5  lea     eax, [rdx+3]
0x18000aae8  and     eax, r13d
0x18000aaeb  mov     [rdi+8], eax
0x18000aaee  cmp     [rdi+60h], r12w
0x18000aaf3  jz      short loc_18000AAFA
0x18000aaf5  or      word ptr [rdi+0Ch], 1
0x18000aafa  mov     [rdi+64h], eax
0x18000aafd  mov     dword ptr [rdi+60h], 4000Ah
0x18000ab04  mov     [rax+rdi], r15d
0x18000ab08  mov     eax, 5
0x18000ab0d  add     [rdi+8], r8d
0x18000ab11  cmp     ax, [rdi+0Eh]
0x18000ab15  jnb     short loc_18000AABB
0x18000ab17  mov     edx, [rdi+8]
0x18000ab1a  mov     eax, esi
0x18000ab1c  lea     rcx, [rdx+3]
0x18000ab20  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000ab24  add     rcx, r8
0x18000ab27  cmp     rcx, rax
0x18000ab2a  ja      loc_18000AAA4
0x18000ab30  lea     eax, [rdx+3]
0x18000ab33  and     eax, r13d
0x18000ab36  mov     [rdi+8], eax
0x18000ab39  cmp     [rdi+38h], r12w
0x18000ab3e  jz      short loc_18000AB45
0x18000ab40  or      word ptr [rdi+0Ch], 1
0x18000ab45  mov     [rdi+3Ch], eax
0x18000ab48  mov     dword ptr [rdi+38h], 4000Ah
0x18000ab4f  mov     [rax+rdi], r14d
0x18000ab53  mov     eax, 0Dh
0x18000ab58  add     [rdi+8], r8d
0x18000ab5c  cmp     ax, [rdi+0Eh]
0x18000ab60  jnb     loc_18000AABB
0x18000ab66  cmp     esi, 80h
0x18000ab6c  jb      loc_18000AAA4
0x18000ab72  mov     edx, [rdi+8]
0x18000ab75  mov     eax, esi
0x18000ab77  lea     rcx, [rdx+3]
0x18000ab7b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000ab7f  add     rcx, r8
0x18000ab82  cmp     rcx, rax
0x18000ab85  ja      loc_18000AAA4
0x18000ab8b  lea     eax, [rdx+3]
0x18000ab8e  and     eax, r13d
0x18000ab91  mov     [rdi+8], eax
0x18000ab94  cmp     [rdi+78h], r12w
0x18000ab99  jz      short loc_18000ABA0
0x18000ab9b  or      word ptr [rdi+0Ch], 1
0x18000aba0  mov     [rdi+7Ch], eax
0x18000aba3  mov     dword ptr [rdi+78h], 4000Ah
0x18000abaa  mov     [rax+rdi], r8d
0x18000abae  mov     eax, 0FFFDh
0x18000abb3  add     [rdi+8], r8d
0x18000abb7  and     [rdi+0Ch], ax
0x18000abbb  mov     [rdi+4], r12d
0x18000abbf  mov     r8d, [rdi+8]; dwInBufferSize
0x18000abc3  lea     rax, [rsp+188h+BytesReturned]
0x18000abc8  mov     rcx, qword ptr cs:hPort; hPort
0x18000abcf  xor     r9d, r9d; lpOutBuffer
0x18000abd2  mov     [rsp+188h+lpBytesReturned], rax; lpBytesReturned
0x18000abd7  mov     rdx, rdi; lpInBuffer
0x18000abda  mov     [rsp+188h+dwOutBufferSize], r12d; dwOutBufferSize
0x18000abdf  call    cs:__imp_FilterSendMessage
0x18000abe6  nop     dword ptr [rax+rax+00h]
0x18000abeb  mov     ebx, eax
0x18000abed  test    rdi, rdi
0x18000abf0  jz      short loc_18000AC1C
0x18000abf2  lea     rax, [rsp+188h+InBuffer]
0x18000abf7  cmp     rdi, rax
0x18000abfa  jz      short loc_18000AC1C
0x18000abfc  call    cs:__imp_GetProcessHeap
0x18000ac03  nop     dword ptr [rax+rax+00h]
0x18000ac08  mov     r8, rdi; lpMem
0x18000ac0b  xor     edx, edx; dwFlags
0x18000ac0d  mov     rcx, rax; hHeap
0x18000ac10  call    cs:__imp_HeapFree
0x18000ac17  nop     dword ptr [rax+rax+00h]
0x18000ac1c  mov     eax, ebx
0x18000ac1e  mov     rcx, [rsp+188h+var_48]
0x18000ac26  xor     rcx, rsp; StackCookie
0x18000ac29  call    __security_check_cookie
0x18000ac2e  mov     rbx, [rsp+188h+arg_10]
0x18000ac36  add     rsp, 150h
0x18000ac3d  pop     r15
0x18000ac3f  pop     r14
0x18000ac41  pop     r13
0x18000ac43  pop     r12
0x18000ac45  pop     rdi
0x18000ac46  pop     rsi
0x18000ac47  pop     rbp
0x18000ac48  retn
```

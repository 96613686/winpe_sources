# GetAttribute

- ea: `0x1401b5778`
- end: `0x1401b5b58`
- name: `GetAttribute`
- size: `992`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1401b5d34`

## callees

- `0x1400d7bfc`
- `0x1401b5530`
- `0x1401b5778`
- `0x1401b5b60`
- `0x1401b5e14`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1401b5964`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401b5964`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1401b5860`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1401b5860`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1401b584e`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1401b584e`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1401b582d`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1401b582d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b588c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b5b0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b5b23`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b588c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b5b0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b5b23`
- `ntoskrnl!ExAllocatePool2` at `0x1401b57ec`
- `ntoskrnl!ExAllocatePool2` at `0x1401b5910`
- `ntoskrnl!ExAllocatePool2` at `0x1401b5a3d`
- `ntoskrnl!ExAllocatePool2` at `0x1401b57ec`
- `ntoskrnl!ExAllocatePool2` at `0x1401b5910`
- `ntoskrnl!ExAllocatePool2` at `0x1401b5a3d`

## pseudocode

```c
__int64 __fastcall GetAttribute(
        _QWORD *a1,
        __int64 a2,
        unsigned __int16 a3,
        struct _UNICODE_STRING **a4,
        unsigned int i)
{
  struct _UNICODE_STRING **v5; // r14
  unsigned int v9; // ecx
  PVOID v10; // r15
  int v11; // eax
  __int64 v12; // rcx
  NTSTATUS FqbnString; // esi
  __int64 v14; // rax
  unsigned __int16 *v15; // r12
  __int64 v16; // rax
  struct _UNICODE_STRING *v17; // r15
  WCHAR *v18; // rdi
  USHORT v19; // bx
  unsigned int v20; // eax
  unsigned int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rbx
  unsigned int v24; // ecx
  wchar_t *v25; // rdi
  size_t v26; // r13
  bool v27; // zf
  unsigned int v28; // r15d
  __int64 v30; // [rsp+30h] [rbp-30h]
  NTSTRSAFE_PWSTR ppszDestEnd; // [rsp+40h] [rbp-20h] BYREF
  _QWORD *Pool2; // [rsp+48h] [rbp-18h]
  size_t pcbRemaining[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int pusResult; // [rsp+A8h] [rbp+48h] BYREF
  struct _UNICODE_STRING **v35; // [rsp+B8h] [rbp+58h]

  v35 = a4;
  v5 = a4;
  LODWORD(ppszDestEnd) = 0;
  if ( !a2 || a3 >= 5u )
    return 3221225485LL;
  if ( a4 )
    *a4 = 0;
  v9 = 128;
  if ( (unsigned __int16)(a3 - 3) > 1u )
    v9 = 256;
  for ( i = v9; ; v9 = i )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(66, v9, 1097884741);
    v10 = Pool2;
    if ( !Pool2 )
      break;
    if ( *a1 )
    {
      v11 = SeQuerySecurityAttributesToken(*a1, a2, 1, Pool2, i, &i);
    }
    else
    {
      v12 = a1[2];
      if ( v12 )
        v11 = SeQuerySecurityAttributesTokenAccessInformation(v12, a2, 1, Pool2, i, &i);
      else
        v11 = ZwQuerySecurityAttributesToken(a1[3], a2, 1, Pool2, i, &i);
    }
    FqbnString = v11;
    if ( v11 >= 0 )
    {
      if ( *((_DWORD *)Pool2 + 1) )
      {
        v14 = Pool2[1];
        if ( *(_DWORD *)(v14 + 24) )
        {
          v15 = *(unsigned __int16 **)(v14 + 32);
          if ( v15 )
          {
            if ( a3 )
            {
              switch ( a3 )
              {
                case 1u:
                  if ( !v5 || *(_WORD *)(v14 + 16) != 4 )
                    goto LABEL_52;
                  FqbnString = CreateFqbnString(*(_QWORD *)(v14 + 32), v5);
                  break;
                case 3u:
                case 4u:
                  goto LABEL_52;
                case 2u:
                  if ( *(_WORD *)(v14 + 16) == 16 && v5 )
                  {
                    v20 = *((_DWORD *)v15 + 2);
                    if ( v20 > 0xFFFF || (v21 = 4 * (unsigned __int16)v20, v21 > 0xFFFF) )
                    {
                      FqbnString = -1073741675;
                    }
                    else
                    {
                      LOWORD(pusResult) = 4 * v20;
                      FqbnString = RtlUShortAdd(v21, 2u, (USHORT *)&pusResult);
                      if ( FqbnString >= 0 )
                      {
                        FqbnString = CalcStringContiguousBufferSizeFromLength((unsigned __int16)pusResult, &ppszDestEnd);
                        if ( FqbnString >= 0 )
                        {
                          v22 = ExAllocatePool2(66, (unsigned int)ppszDestEnd, 1097884741);
                          v23 = v22;
                          if ( v22 )
                          {
                            v24 = (unsigned __int16)pusResult;
                            v25 = (wchar_t *)(v22 + 16);
                            *(_QWORD *)(v22 + 8) = v22 + 16;
                            *(_WORD *)(v22 + 2) = v24;
                            ppszDestEnd = (NTSTRSAFE_PWSTR)(v22 + 16);
                            v26 = v24;
                            *(_WORD *)v22 = v24 - 2;
                            memset((void *)(v22 + 16), 0, v24);
                            v27 = *((_DWORD *)v15 + 2) == 0;
                            pcbRemaining[0] = v26;
                            pusResult = 0;
                            if ( !v27 )
                            {
                              v28 = pusResult;
                              while ( 1 )
                              {
                                LODWORD(v30) = *(unsigned __int8 *)(v28 + *(_QWORD *)v15);
                                RtlStringCbPrintfExW(v25, v26, &ppszDestEnd, pcbRemaining, 0, L"%02x", v30);
                                if ( ++v28 >= *((_DWORD *)v15 + 2) )
                                  break;
                                v25 = ppszDestEnd;
                                v26 = pcbRemaining[0];
                              }
                              v5 = v35;
                              v10 = Pool2;
                            }
                            *v5 = (struct _UNICODE_STRING *)v23;
                          }
                          else
                          {
                            FqbnString = -1073741801;
                          }
                        }
                      }
                    }
                    break;
                  }
                  goto LABEL_52;
              }
            }
            else
            {
              if ( v5 && *(_WORD *)(v14 + 16) == 3 )
              {
                FqbnString = CalcStringContiguousBufferSizeFromLength(*v15, &ppszDestEnd);
                if ( FqbnString >= 0 )
                {
                  v16 = ExAllocatePool2(66, (unsigned int)ppszDestEnd, 1097884741);
                  v17 = (struct _UNICODE_STRING *)v16;
                  if ( v16 )
                  {
                    v18 = (WCHAR *)(v16 + 16);
                    v19 = *v15 + 2;
                    memset((void *)(v16 + 16), 0, v19);
                    v17->MaximumLength = v19;
                    v17->Length = 0;
                    v17->Buffer = v18;
                    RtlCopyUnicodeString(v17, (PCUNICODE_STRING)v15);
                    *v5 = v17;
                  }
                  else
                  {
                    FqbnString = -1073741801;
                  }
                  v10 = Pool2;
                }
                goto LABEL_53;
              }
LABEL_52:
              FqbnString = -1073741811;
            }
          }
        }
      }
LABEL_53:
      ExFreePoolWithTag(v10, 0);
      return (unsigned int)FqbnString;
    }
    if ( v11 == -1073741275 )
    {
      FqbnString = 0;
      goto LABEL_53;
    }
    if ( v11 != -1073741789 )
      goto LABEL_53;
    ExFreePoolWithTag(Pool2, 0);
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x1401b5778  mov     [rsp-38h+arg_0], rbx
0x1401b577d  mov     [rsp-38h+arg_18], r9
0x1401b5782  push    rbp
0x1401b5783  push    rsi
0x1401b5784  push    rdi
0x1401b5785  push    r12
0x1401b5787  push    r13
0x1401b5789  push    r14
0x1401b578b  push    r15
0x1401b578d  mov     rbp, rsp
0x1401b5790  sub     rsp, 60h
0x1401b5794  xor     esi, esi
0x1401b5796  mov     r14, r9
0x1401b5799  mov     dword ptr [rbp+ppszDestEnd], esi
0x1401b579c  movzx   edi, r8w
0x1401b57a0  mov     r12, rdx
0x1401b57a3  mov     r13, rcx
0x1401b57a6  test    rdx, rdx
0x1401b57a9  jz      loc_1401B5B3A
0x1401b57af  cmp     r8w, 5
0x1401b57b4  jnb     loc_1401B5B3A
0x1401b57ba  mov     ebx, esi
0x1401b57bc  test    r9, r9
0x1401b57bf  jz      short loc_1401B57C4
0x1401b57c1  mov     [r9], rsi
0x1401b57c4  mov     ecx, 80h
0x1401b57c9  lea     eax, [rdi-3]
0x1401b57cc  mov     edx, 100h
0x1401b57d1  lea     r8d, [rcx-7Fh]
0x1401b57d5  cmp     ax, r8w
0x1401b57d9  cmova   ecx, edx
0x1401b57dc  mov     [rbp+arg_20], ecx
0x1401b57df  mov     edx, ecx
0x1401b57e1  mov     r8d, 41706445h
0x1401b57e7  mov     ecx, 42h ; 'B'
0x1401b57ec  call    cs:__imp_ExAllocatePool2
0x1401b57f3  nop     dword ptr [rax+rax+00h]
0x1401b57f8  mov     [rbp+var_18], rax
0x1401b57fc  mov     r15, rax
0x1401b57ff  test    rax, rax
0x1401b5802  jz      loc_1401B5B31
0x1401b5808  mov     rcx, [r13+0]
0x1401b580c  lea     rax, [rbp+arg_20]
0x1401b5810  mov     [rsp+60h+pszFormat], rax
0x1401b5815  mov     r9, r15
0x1401b5818  mov     r8d, 1
0x1401b581e  test    rcx, rcx
0x1401b5821  jz      short loc_1401B583B
0x1401b5823  mov     edx, [rbp+arg_20]
0x1401b5826  mov     [rsp+60h+dwFlags], edx
0x1401b582a  mov     rdx, r12
0x1401b582d  call    cs:__imp_SeQuerySecurityAttributesToken
0x1401b5834  nop     dword ptr [rax+rax+00h]
0x1401b5839  jmp     short loc_1401B586C
0x1401b583b  mov     rcx, [r13+10h]
0x1401b583f  mov     rdx, r12
0x1401b5842  mov     eax, [rbp+arg_20]
0x1401b5845  mov     [rsp+60h+dwFlags], eax
0x1401b5849  test    rcx, rcx
0x1401b584c  jz      short loc_1401B585C
0x1401b584e  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x1401b5855  nop     dword ptr [rax+rax+00h]
0x1401b585a  jmp     short loc_1401B586C
0x1401b585c  mov     rcx, [r13+18h]
0x1401b5860  call    cs:__imp_ZwQuerySecurityAttributesToken
0x1401b5867  nop     dword ptr [rax+rax+00h]
0x1401b586c  xor     r10d, r10d
0x1401b586f  mov     esi, eax
0x1401b5871  test    eax, eax
0x1401b5873  jns     short loc_1401B58A8
0x1401b5875  cmp     eax, 0C0000225h
0x1401b587a  jz      short loc_1401B58A0
0x1401b587c  cmp     eax, 0C0000023h
0x1401b5881  jnz     loc_1401B5B08
0x1401b5887  xor     edx, edx; Tag
0x1401b5889  mov     rcx, r15; P
0x1401b588c  call    cs:__imp_ExFreePoolWithTag
0x1401b5893  nop     dword ptr [rax+rax+00h]
0x1401b5898  mov     ecx, [rbp+arg_20]
0x1401b589b  jmp     loc_1401B57DF
0x1401b58a0  mov     esi, r10d
0x1401b58a3  jmp     loc_1401B5B08
0x1401b58a8  cmp     [r15+4], r10d
0x1401b58ac  jz      loc_1401B5B08
0x1401b58b2  mov     rax, [r15+8]
0x1401b58b6  cmp     [rax+18h], r10d
0x1401b58ba  jz      loc_1401B5B08
0x1401b58c0  mov     r12, [rax+20h]
0x1401b58c4  test    r12, r12
0x1401b58c7  jz      loc_1401B5B08
0x1401b58cd  test    di, di
0x1401b58d0  jnz     loc_1401B5977
0x1401b58d6  test    r14, r14
0x1401b58d9  jz      loc_1401B5B03
0x1401b58df  cmp     word ptr [rax+10h], 3
0x1401b58e4  jnz     loc_1401B5B03
0x1401b58ea  movzx   ecx, word ptr [r12]
0x1401b58ef  lea     rdx, [rbp+ppszDestEnd]
0x1401b58f3  call    CalcStringContiguousBufferSizeFromLength
0x1401b58f8  mov     esi, eax
0x1401b58fa  test    eax, eax
0x1401b58fc  js      loc_1401B5B08
0x1401b5902  mov     edx, dword ptr [rbp+ppszDestEnd]
0x1401b5905  mov     ecx, 42h ; 'B'
0x1401b590a  mov     r8d, 41706445h
0x1401b5910  call    cs:__imp_ExAllocatePool2
0x1401b5917  nop     dword ptr [rax+rax+00h]
0x1401b591c  mov     r15, rax
0x1401b591f  test    rax, rax
0x1401b5922  jnz     short loc_1401B5932
0x1401b5924  mov     esi, 0C0000017h
0x1401b5929  mov     r15, [rbp+var_18]
0x1401b592d  jmp     loc_1401B5B08
0x1401b5932  lea     rdi, [rax+10h]
0x1401b5936  xor     edx, edx; Val
0x1401b5938  movzx   eax, word ptr [r12]
0x1401b593d  mov     rcx, rdi; void *
0x1401b5940  add     ax, 2
0x1401b5944  movzx   ebx, ax
0x1401b5947  mov     r8d, ebx; Size
0x1401b594a  call    memset
0x1401b594f  xor     eax, eax
0x1401b5951  mov     [r15+2], bx
0x1401b5956  mov     rdx, r12; SourceString
0x1401b5959  mov     [r15], ax
0x1401b595d  mov     rcx, r15; DestinationString
0x1401b5960  mov     [r15+8], rdi
0x1401b5964  call    cs:__imp_RtlCopyUnicodeString
0x1401b596b  nop     dword ptr [rax+rax+00h]
0x1401b5970  xor     ebx, ebx
0x1401b5972  mov     [r14], r15
0x1401b5975  jmp     short loc_1401B5929
0x1401b5977  mov     ecx, 1
0x1401b597c  cmp     di, cx
0x1401b597f  jnz     short loc_1401B59A7
0x1401b5981  test    r14, r14
0x1401b5984  jz      loc_1401B5B03
0x1401b598a  cmp     word ptr [rax+10h], 4
0x1401b598f  jnz     loc_1401B5B03
0x1401b5995  mov     rdx, r14
0x1401b5998  mov     rcx, r12
0x1401b599b  call    CreateFqbnString
0x1401b59a0  mov     esi, eax
0x1401b59a2  jmp     loc_1401B5B08
0x1401b59a7  cmp     di, 3
0x1401b59ab  jz      loc_1401B5B03
0x1401b59b1  cmp     di, 4
0x1401b59b5  jz      loc_1401B5B03
0x1401b59bb  mov     r13d, 2
0x1401b59c1  cmp     di, r13w
0x1401b59c5  jnz     loc_1401B5B08
0x1401b59cb  cmp     word ptr [rax+10h], 10h
0x1401b59d0  jnz     loc_1401B5B03
0x1401b59d6  test    r14, r14
0x1401b59d9  jz      loc_1401B5B03
0x1401b59df  mov     eax, [r12+8]
0x1401b59e4  mov     edx, 0FFFFh
0x1401b59e9  cmp     eax, edx
0x1401b59eb  ja      loc_1401B5AFC
0x1401b59f1  movzx   ecx, ax
0x1401b59f4  shl     ecx, 2; usAugend
0x1401b59f7  cmp     ecx, edx
0x1401b59f9  ja      loc_1401B5AFC
0x1401b59ff  mov     edx, r13d; usAddend
0x1401b5a02  mov     word ptr [rbp+pusResult], cx
0x1401b5a06  lea     r8, [rbp+pusResult]; pusResult
0x1401b5a0a  call    RtlUShortAdd
0x1401b5a0f  mov     esi, eax
0x1401b5a11  test    eax, eax
0x1401b5a13  js      loc_1401B5B08
0x1401b5a19  movzx   ecx, word ptr [rbp+pusResult]
0x1401b5a1d  lea     rdx, [rbp+ppszDestEnd]
0x1401b5a21  call    CalcStringContiguousBufferSizeFromLength
0x1401b5a26  mov     esi, eax
0x1401b5a28  test    eax, eax
0x1401b5a2a  js      loc_1401B5B08
0x1401b5a30  mov     edx, dword ptr [rbp+ppszDestEnd]
0x1401b5a33  lea     ecx, [r13+40h]
0x1401b5a37  mov     r8d, 41706445h
0x1401b5a3d  call    cs:__imp_ExAllocatePool2
0x1401b5a44  nop     dword ptr [rax+rax+00h]
0x1401b5a49  mov     rbx, rax
0x1401b5a4c  test    rax, rax
0x1401b5a4f  jnz     short loc_1401B5A5B
0x1401b5a51  mov     esi, 0C0000017h
0x1401b5a56  jmp     loc_1401B5B08
0x1401b5a5b  movzx   ecx, word ptr [rbp+pusResult]
0x1401b5a5f  lea     rdi, [rax+10h]
0x1401b5a63  mov     [rax+8], rdi
0x1401b5a67  mov     r8d, ecx; Size
0x1401b5a6a  movzx   eax, cx
0x1401b5a6d  mov     [rbx+2], cx
0x1401b5a71  sub     ax, r13w
0x1401b5a75  mov     [rbp+ppszDestEnd], rdi
0x1401b5a79  mov     r13d, ecx
0x1401b5a7c  mov     [rbx], ax
0x1401b5a7f  mov     rcx, rdi; void *
0x1401b5a82  xor     edx, edx; Val
0x1401b5a84  call    memset
0x1401b5a89  cmp     dword ptr [r12+8], 0
0x1401b5a8f  mov     [rbp+pcbRemaining], r13
0x1401b5a93  mov     [rbp+pusResult], 0
0x1401b5a9a  jbe     short loc_1401B5AF5
0x1401b5a9c  mov     r15d, [rbp+pusResult]
0x1401b5aa0  mov     rax, [r12]
0x1401b5aa4  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x1401b5aa8  mov     r8d, r15d
0x1401b5aab  mov     rdx, r13; cbDest
0x1401b5aae  mov     rcx, rdi; pszDest
0x1401b5ab1  movzx   r8d, byte ptr [r8+rax]
0x1401b5ab6  lea     rax, a02x; "%02x"
0x1401b5abd  mov     [rsp+60h+var_30], r8d
0x1401b5ac2  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x1401b5ac6  mov     [rsp+60h+pszFormat], rax; pszFormat
0x1401b5acb  mov     qword ptr [rsp+60h+dwFlags], 0; dwFlags
0x1401b5ad4  call    RtlStringCbPrintfExW
0x1401b5ad9  inc     r15d
0x1401b5adc  cmp     r15d, [r12+8]
0x1401b5ae1  jnb     short loc_1401B5AED
0x1401b5ae3  mov     rdi, [rbp+ppszDestEnd]
0x1401b5ae7  mov     r13, [rbp+pcbRemaining]
0x1401b5aeb  jmp     short loc_1401B5AA0
0x1401b5aed  mov     r14, [rbp+arg_18]
0x1401b5af1  mov     r15, [rbp+var_18]
0x1401b5af5  mov     [r14], rbx
0x1401b5af8  xor     ebx, ebx
0x1401b5afa  jmp     short loc_1401B5B08
0x1401b5afc  mov     esi, 0C0000095h
0x1401b5b01  jmp     short loc_1401B5B08
0x1401b5b03  mov     esi, 0C000000Dh
0x1401b5b08  xor     edx, edx; Tag
0x1401b5b0a  mov     rcx, r15; P
0x1401b5b0d  call    cs:__imp_ExFreePoolWithTag
0x1401b5b14  nop     dword ptr [rax+rax+00h]
0x1401b5b19  test    rbx, rbx
0x1401b5b1c  jz      short loc_1401B5B36
0x1401b5b1e  xor     edx, edx; Tag
0x1401b5b20  mov     rcx, rbx; P
0x1401b5b23  call    cs:__imp_ExFreePoolWithTag
0x1401b5b2a  nop     dword ptr [rax+rax+00h]
0x1401b5b2f  jmp     short loc_1401B5B36
0x1401b5b31  mov     esi, 0C0000017h
0x1401b5b36  mov     eax, esi
0x1401b5b38  jmp     short loc_1401B5B3F
0x1401b5b3a  mov     eax, 0C000000Dh
0x1401b5b3f  mov     rbx, [rsp+60h+arg_0]
0x1401b5b47  add     rsp, 60h
0x1401b5b4b  pop     r15
0x1401b5b4d  pop     r14
0x1401b5b4f  pop     r13
0x1401b5b51  pop     r12
0x1401b5b53  pop     rdi
0x1401b5b54  pop     rsi
0x1401b5b55  pop     rbp
0x1401b5b56  retn
```

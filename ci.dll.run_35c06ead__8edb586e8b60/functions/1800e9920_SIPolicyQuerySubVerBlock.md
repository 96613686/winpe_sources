# SIPolicyQuerySubVerBlock

- ea: `0x1800e9920`
- end: `0x1800e9aa0`
- name: `SIPolicyQuerySubVerBlock`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a46e0`

## callees

- `0x1800a63dc`
- `0x1800e9920`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800e99e2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800e99e2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e9a11`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e9a11`

## pseudocode

```c
__int64 __fastcall SIPolicyQuerySubVerBlock(unsigned __int16 *a1, WCHAR *a2, _QWORD *a3, _QWORD *a4)
{
  unsigned __int16 *v7; // rbx
  unsigned int v8; // r14d
  unsigned __int16 v9; // cx
  unsigned __int16 *v10; // rsi
  WCHAR *v11; // r15
  int v12; // ebp
  __int64 v13; // rax
  unsigned __int16 v14; // cx
  __int64 v15; // rax
  UNICODE_STRING String1; // [rsp+20h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF

  v7 = a1;
  v8 = -1073741275;
  String1 = 0;
  DestinationString = 0;
  if ( !a1[2] )
  {
    v9 = *a1;
    if ( (unsigned __int16)(v9 - 8) <= 0x7FF8u && (v9 & 1) == 0 )
    {
LABEL_6:
      while ( *a2 == 92 )
        ++a2;
      v10 = (unsigned __int16 *)SIPolicyCheckVerBlock(v7, *v7);
      if ( v10 )
      {
        if ( *a2 )
        {
          v11 = a2;
          do
          {
            if ( *a2 == 92 )
              break;
            ++a2;
          }
          while ( *a2 );
          v12 = (_DWORD)v7 + *v7;
          while ( SIPolicyCheckVerBlock(v10, (unsigned int)(v12 - (_DWORD)v10)) )
          {
            RtlInitUnicodeString(&DestinationString, v10 + 3);
            String1.Buffer = v11;
            String1.Length = (_WORD)a2 - (_WORD)v11;
            String1.MaximumLength = (_WORD)a2 - (_WORD)v11;
            if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
            {
              v7 = v10;
              goto LABEL_6;
            }
            v10 = (unsigned __int16 *)((char *)v10 + ((*v10 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
          }
        }
        else
        {
          *a4 = v7[1];
          v13 = -1;
          do
            ++v13;
          while ( v7[v13 + 3] );
          v14 = v7[1];
          if ( v14 && (v7[2] || v14 >= 2u) )
            v15 = (2 * (_DWORD)v13 + 11) & 0xFFFFFFFC;
          else
            v15 = 2LL * (unsigned int)v13 + 6;
          v8 = 0;
          *a3 = (char *)v7 + v15;
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800e9920  push    rbx
0x1800e9922  push    rbp
0x1800e9923  push    rsi
0x1800e9924  push    rdi
0x1800e9925  push    r12
0x1800e9927  push    r13
0x1800e9929  push    r14
0x1800e992b  push    r15
0x1800e992d  sub     rsp, 48h
0x1800e9931  xor     ebp, ebp
0x1800e9933  xorps   xmm0, xmm0
0x1800e9936  xorps   xmm1, xmm1
0x1800e9939  mov     r12, r9
0x1800e993c  mov     r13, r8
0x1800e993f  mov     rdi, rdx
0x1800e9942  mov     rbx, rcx
0x1800e9945  mov     r14d, 0C0000225h
0x1800e994b  movups  xmmword ptr [rsp+88h+String1.Length], xmm0
0x1800e9950  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm1
0x1800e9955  cmp     [rcx+4], bp
0x1800e9959  jnz     loc_1800E9A8B
0x1800e995f  movzx   ecx, word ptr [rcx]
0x1800e9962  mov     edx, 7FF8h
0x1800e9967  lea     eax, [rcx-8]
0x1800e996a  cmp     ax, dx
0x1800e996d  ja      loc_1800E9A8B
0x1800e9973  test    cl, 1
0x1800e9976  jnz     loc_1800E9A8B
0x1800e997c  mov     r15d, 2
0x1800e9982  jmp     short loc_1800E9987
0x1800e9984  add     rdi, r15
0x1800e9987  cmp     word ptr [rdi], 5Ch ; '\'
0x1800e998b  jz      short loc_1800E9984
0x1800e998d  movzx   edx, word ptr [rbx]
0x1800e9990  mov     rcx, rbx
0x1800e9993  call    SIPolicyCheckVerBlock
0x1800e9998  mov     rsi, rax
0x1800e999b  test    rax, rax
0x1800e999e  jz      loc_1800E9A8B
0x1800e99a4  cmp     [rdi], bp
0x1800e99a7  jz      loc_1800E9A3B
0x1800e99ad  mov     r15, rdi
0x1800e99b0  cmp     word ptr [rdi], 5Ch ; '\'
0x1800e99b4  jz      short loc_1800E99BF
0x1800e99b6  add     rdi, 2
0x1800e99ba  cmp     [rdi], bp
0x1800e99bd  jnz     short loc_1800E99B0
0x1800e99bf  movzx   ebp, word ptr [rbx]
0x1800e99c2  add     ebp, ebx
0x1800e99c4  mov     edx, ebp
0x1800e99c6  mov     rcx, rsi
0x1800e99c9  sub     edx, esi
0x1800e99cb  call    SIPolicyCheckVerBlock
0x1800e99d0  test    rax, rax
0x1800e99d3  jz      loc_1800E9A8B
0x1800e99d9  lea     rdx, [rsi+6]; SourceString
0x1800e99dd  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x1800e99e2  call    cs:__imp_RtlInitUnicodeString
0x1800e99e9  nop     dword ptr [rax+rax+00h]
0x1800e99ee  movzx   eax, di
0x1800e99f1  mov     [rsp+88h+String1.Buffer], r15
0x1800e99f6  sub     ax, r15w
0x1800e99fa  lea     rdx, [rsp+88h+DestinationString]; String2
0x1800e99ff  mov     r8b, 1; CaseInSensitive
0x1800e9a02  mov     [rsp+88h+String1.Length], ax
0x1800e9a07  lea     rcx, [rsp+88h+String1]; String1
0x1800e9a0c  mov     [rsp+88h+String1.MaximumLength], ax
0x1800e9a11  call    cs:__imp_RtlCompareUnicodeString
0x1800e9a18  nop     dword ptr [rax+rax+00h]
0x1800e9a1d  test    eax, eax
0x1800e9a1f  jz      short loc_1800E9A31
0x1800e9a21  movzx   eax, word ptr [rsi]
0x1800e9a24  add     rax, 3
0x1800e9a28  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800e9a2c  add     rsi, rax
0x1800e9a2f  jmp     short loc_1800E99C4
0x1800e9a31  mov     rbx, rsi
0x1800e9a34  xor     ebp, ebp
0x1800e9a36  jmp     loc_1800E997C
0x1800e9a3b  movzx   eax, word ptr [rbx+2]
0x1800e9a3f  mov     [r12], rax
0x1800e9a43  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e9a47  inc     rax
0x1800e9a4a  cmp     [rbx+rax*2+6], bp
0x1800e9a4f  jnz     short loc_1800E9A47
0x1800e9a51  movzx   ecx, word ptr [rbx+2]
0x1800e9a55  test    cx, cx
0x1800e9a58  jz      short loc_1800E9A77
0x1800e9a5a  cmp     [rbx+4], bp
0x1800e9a5e  jnz     short loc_1800E9A66
0x1800e9a60  cmp     cx, r15w
0x1800e9a64  jb      short loc_1800E9A77
0x1800e9a66  lea     eax, ds:0Bh[rax*2]
0x1800e9a6d  mov     ecx, 0FFFFFFFCh
0x1800e9a72  and     rax, rcx
0x1800e9a75  jmp     short loc_1800E9A81
0x1800e9a77  mov     eax, eax
0x1800e9a79  lea     rax, ds:6[rax*2]
0x1800e9a81  add     rax, rbx
0x1800e9a84  mov     r14d, ebp
0x1800e9a87  mov     [r13+0], rax
0x1800e9a8b  mov     eax, r14d
0x1800e9a8e  add     rsp, 48h
0x1800e9a92  pop     r15
0x1800e9a94  pop     r14
0x1800e9a96  pop     r13
0x1800e9a98  pop     r12
0x1800e9a9a  pop     rdi
0x1800e9a9b  pop     rsi
0x1800e9a9c  pop     rbp
0x1800e9a9d  pop     rbx
0x1800e9a9e  retn
```

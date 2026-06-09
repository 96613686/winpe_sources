# PrepareAceDataForEvent

- ea: `0x14000c944`
- end: `0x14000cc2c`
- name: `PrepareAceDataForEvent`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000c514`

## callees

- `0x140009b80`
- `0x14000c944`
- `0x140011610`
- `0x140011650`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000caf0`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000caf0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000cab6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000cab6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c9f0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ca46`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c9f0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ca46`

## pseudocode

```c
__int64 __fastcall PrepareAceDataForEvent(__int64 a1, PVOID *a2, _DWORD *a3, __int64 a4)
{
  __int16 v4; // r12
  unsigned __int64 v5; // rax
  _DWORD *v6; // rsi
  __int64 v8; // rdi
  int v9; // ebx
  SIZE_T v10; // rdx
  PVOID PoolWithTag; // rax
  WCHAR *v12; // rdi
  unsigned int v13; // esi
  unsigned int *v14; // r15
  WCHAR *v15; // rax
  unsigned int v16; // r14d
  WCHAR *v17; // rcx
  NTSTATUS v18; // eax
  USHORT Length; // dx
  unsigned __int64 v20; // rcx
  USHORT v21; // cx
  unsigned int v22; // edx
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-30h] BYREF
  UNICODE_STRING SourceString; // [rsp+58h] [rbp-20h] BYREF

  v4 = 0;
  *a2 = 0;
  *a3 = 0;
  SourceString.Buffer = L";";
  v5 = *(_QWORD *)(a1 + 16);
  v6 = a3;
  v8 = a1;
  *(_QWORD *)&SourceString.Length = 262146;
  v9 = 0;
  DestinationString = 0;
  if ( v5 < 2 )
    return 3221226021LL;
  v10 = (unsigned int)(4 * *(_DWORD *)(a1 + 8));
  *a3 = v10;
  if ( qword_140020008 )
    PoolWithTag = (PVOID)qword_140020008(256, v10, 1682203475);
  else
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v10, 0x64446353u);
  *a2 = PoolWithTag;
  if ( PoolWithTag )
  {
    LOWORD(v13) = 256;
    while ( 1 )
    {
      v14 = *(unsigned int **)(v8 + 16);
      if ( qword_140020008 )
        v15 = (WCHAR *)qword_140020008(256, (unsigned __int16)v13, 1953719123);
      else
        v15 = (WCHAR *)ExAllocatePoolWithTag(PagedPool, (unsigned __int16)v13, 0x74736353u);
      v12 = v15;
      if ( !v15 )
      {
        v9 = -1073741670;
        goto LABEL_31;
      }
      memset(v15, 0, (unsigned __int16)v13);
      DestinationString.Buffer = v12;
      v16 = 0;
      DestinationString.Length = 0;
      DestinationString.MaximumLength = v13;
      if ( *(_DWORD *)(a1 + 8) )
      {
        while ( 1 )
        {
          *((_DWORD *)*a2 + v16) = v14[1];
          if ( v16 )
          {
            if ( DestinationString.MaximumLength < 2u )
              goto LABEL_21;
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            DestinationString.MaximumLength -= DestinationString.Length;
            v4 += DestinationString.Length;
            v17 = &DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1];
            DestinationString.Length = 0;
            DestinationString.Buffer = v17;
          }
          v18 = RtlConvertSidToUnicodeString(&DestinationString, v14 + 2, 0);
          v9 = v18;
          if ( v18 < 0 )
            break;
          Length = DestinationString.Length;
          v20 = (unsigned __int64)DestinationString.Length >> 1;
          v4 += DestinationString.Length;
          DestinationString.Length = 0;
          DestinationString.Buffer += v20;
          v21 = DestinationString.MaximumLength - Length;
          v22 = *(_DWORD *)(a1 + 8);
          DestinationString.MaximumLength = v21;
          if ( v16 == v22 - 1 && v21 < 2u )
          {
LABEL_21:
            v9 = -2147483643;
            goto LABEL_24;
          }
          ++v16;
          v14 = (unsigned int *)((char *)v14 + *v14);
          if ( v16 >= v22 )
            goto LABEL_29;
        }
        if ( v18 != -2147483643 )
          goto LABEL_31;
      }
      if ( v9 != -2147483643 )
        break;
LABEL_24:
      if ( (_WORD)v13 == 0xFFFF )
        goto LABEL_31;
      SecFreePool(v12, 0x74736353u);
      v8 = a1;
      v4 = 0;
      v13 = 2 * (unsigned __int16)v13;
      if ( v13 > 0xFFFF )
      {
        v9 = -1073741675;
        LOWORD(v13) = -1;
      }
      else
      {
        v9 = 0;
      }
    }
    if ( v9 >= 0 )
    {
LABEL_29:
      *(_QWORD *)(a4 + 8) = v12;
      *(_WORD *)a4 = v4;
      *(_WORD *)(a4 + 2) = v13;
      return 0;
    }
LABEL_31:
    v6 = a3;
  }
  else
  {
    v12 = 0;
    v9 = -1073741670;
  }
  if ( *a2 )
    SecFreePool(*a2, 0x64446353u);
  if ( v12 )
    SecFreePool(v12, 0x74736353u);
  *a2 = 0;
  result = (unsigned int)v9;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x14000c944  push    rbp
0x14000c946  push    rbx
0x14000c947  push    rsi
0x14000c948  push    rdi
0x14000c949  push    r12
0x14000c94b  push    r13
0x14000c94d  push    r14
0x14000c94f  push    r15
0x14000c951  mov     rbp, rsp
0x14000c954  sub     rsp, 78h
0x14000c958  mov     rax, cs:__security_cookie
0x14000c95f  xor     rax, rsp
0x14000c962  mov     [rbp+var_10], rax
0x14000c966  xor     r12d, r12d
0x14000c969  mov     [rbp+var_48], r9
0x14000c96d  lea     rax, asc_140016A6C; ";"
0x14000c974  mov     [rdx], r12
0x14000c977  mov     [r8], r12d
0x14000c97a  xorps   xmm0, xmm0
0x14000c97d  mov     [rbp+SourceString.Buffer], rax
0x14000c981  xorps   xmm1, xmm1
0x14000c984  mov     rax, [rcx+10h]
0x14000c988  mov     rsi, r8
0x14000c98b  mov     [rbp+var_50], r8
0x14000c98f  mov     r13, rdx
0x14000c992  mov     [rbp+var_58], rcx
0x14000c996  mov     rdi, rcx
0x14000c999  mov     qword ptr [rbp+SourceString.Length], 40002h
0x14000c9a1  mov     ebx, r12d
0x14000c9a4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000c9a8  movups  xmmword ptr [rbp+P], xmm1
0x14000c9ac  test    rax, rax
0x14000c9af  jz      loc_14000CC09
0x14000c9b5  cmp     rax, 1
0x14000c9b9  jz      loc_14000CC09
0x14000c9bf  mov     edx, [rcx+8]
0x14000c9c2  mov     r14d, 100h
0x14000c9c8  shl     edx, 2; NumberOfBytes
0x14000c9cb  mov     [r8], edx
0x14000c9ce  mov     r8d, 64446353h; Tag
0x14000c9d4  mov     rax, cs:qword_140020008
0x14000c9db  test    rax, rax
0x14000c9de  jz      short loc_14000C9EB
0x14000c9e0  mov     ecx, r14d
0x14000c9e3  call    cs:__guard_dispatch_icall_fptr
0x14000c9e9  jmp     short loc_14000C9FC
0x14000c9eb  mov     ecx, 1; PoolType
0x14000c9f0  call    cs:__imp_ExAllocatePoolWithTag
0x14000c9f7  nop     dword ptr [rax+rax+00h]
0x14000c9fc  mov     [r13+0], rax
0x14000ca00  test    rax, rax
0x14000ca03  jnz     short loc_14000CA13
0x14000ca05  mov     rdi, [rbp+P+8]
0x14000ca09  mov     ebx, 0C000009Ah
0x14000ca0e  jmp     loc_14000CBD9
0x14000ca13  movzx   esi, r14w
0x14000ca17  mov     rax, cs:qword_140020008
0x14000ca1e  mov     r8d, 74736353h; Tag
0x14000ca24  mov     r15, [rdi+10h]
0x14000ca28  movzx   r14d, si
0x14000ca2c  mov     edx, r14d; NumberOfBytes
0x14000ca2f  test    rax, rax
0x14000ca32  jz      short loc_14000CA41
0x14000ca34  mov     ecx, 100h
0x14000ca39  call    cs:__guard_dispatch_icall_fptr
0x14000ca3f  jmp     short loc_14000CA52
0x14000ca41  mov     ecx, 1; PoolType
0x14000ca46  call    cs:__imp_ExAllocatePoolWithTag
0x14000ca4d  nop     dword ptr [rax+rax+00h]
0x14000ca52  mov     rdi, rax
0x14000ca55  test    rax, rax
0x14000ca58  jz      loc_14000CBCB
0x14000ca5e  mov     r8, r14; Size
0x14000ca61  xor     edx, edx; Val
0x14000ca63  mov     rcx, rax; void *
0x14000ca66  call    memset
0x14000ca6b  mov     rax, [rbp+var_58]
0x14000ca6f  xor     r8d, r8d
0x14000ca72  mov     [rbp+DestinationString.Buffer], rdi
0x14000ca76  mov     r14d, r8d
0x14000ca79  mov     [rbp+DestinationString.Length], r8w
0x14000ca7e  mov     [rbp+DestinationString.MaximumLength], si
0x14000ca82  cmp     [rax+8], r8d
0x14000ca86  jbe     loc_14000CB68
0x14000ca8c  mov     rcx, [r13+0]
0x14000ca90  mov     eax, [r15+4]
0x14000ca94  mov     edx, r14d
0x14000ca97  mov     [rcx+rdx*4], eax
0x14000ca9a  test    r14d, r14d
0x14000ca9d  jz      short loc_14000CAE5
0x14000ca9f  mov     eax, 2
0x14000caa4  cmp     [rbp+DestinationString.MaximumLength], ax
0x14000caa8  jb      loc_14000CB5A
0x14000caae  lea     rdx, [rbp+SourceString]; SourceString
0x14000cab2  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000cab6  call    cs:__imp_RtlCopyUnicodeString
0x14000cabd  nop     dword ptr [rax+rax+00h]
0x14000cac2  movzx   edx, [rbp+DestinationString.Length]
0x14000cac6  mov     rax, [rbp+DestinationString.Buffer]
0x14000caca  mov     ecx, edx
0x14000cacc  sub     [rbp+DestinationString.MaximumLength], dx
0x14000cad0  add     r12w, dx
0x14000cad4  shr     rcx, 1
0x14000cad7  lea     rcx, [rax+rcx*2]
0x14000cadb  xor     eax, eax
0x14000cadd  mov     [rbp+DestinationString.Length], ax
0x14000cae1  mov     [rbp+DestinationString.Buffer], rcx
0x14000cae5  lea     rdx, [r15+8]; Sid
0x14000cae9  xor     r8d, r8d; AllocateDestinationString
0x14000caec  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14000caf0  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000caf7  nop     dword ptr [rax+rax+00h]
0x14000cafc  xor     r8d, r8d
0x14000caff  mov     ebx, eax
0x14000cb01  test    eax, eax
0x14000cb03  js      short loc_14000CB61
0x14000cb05  movzx   edx, [rbp+DestinationString.Length]
0x14000cb09  mov     rax, [rbp+DestinationString.Buffer]
0x14000cb0d  mov     ecx, edx
0x14000cb0f  shr     rcx, 1
0x14000cb12  add     r12w, dx
0x14000cb16  mov     [rbp+DestinationString.Length], r8w
0x14000cb1b  lea     rcx, [rax+rcx*2]
0x14000cb1f  mov     rax, [rbp+var_58]
0x14000cb23  mov     [rbp+DestinationString.Buffer], rcx
0x14000cb27  movzx   ecx, [rbp+DestinationString.MaximumLength]
0x14000cb2b  sub     cx, dx
0x14000cb2e  mov     edx, [rax+8]
0x14000cb31  mov     [rbp+DestinationString.MaximumLength], cx
0x14000cb35  lea     eax, [rdx-1]
0x14000cb38  cmp     r14d, eax
0x14000cb3b  jnz     short loc_14000CB46
0x14000cb3d  lea     eax, [r8+2]
0x14000cb41  cmp     cx, ax
0x14000cb44  jb      short loc_14000CB5A
0x14000cb46  mov     eax, [r15]
0x14000cb49  inc     r14d
0x14000cb4c  add     r15, rax
0x14000cb4f  cmp     r14d, edx
0x14000cb52  jb      loc_14000CA8C
0x14000cb58  jmp     short loc_14000CBB7
0x14000cb5a  mov     ebx, 80000005h
0x14000cb5f  jmp     short loc_14000CB72
0x14000cb61  cmp     eax, 80000005h
0x14000cb66  jnz     short loc_14000CBD2
0x14000cb68  mov     eax, ebx
0x14000cb6a  cmp     ebx, 80000005h
0x14000cb70  jnz     short loc_14000CBB3
0x14000cb72  mov     eax, 0FFFFh
0x14000cb77  cmp     ax, si
0x14000cb7a  jbe     short loc_14000CBD2
0x14000cb7c  mov     edx, 74736353h; Tag
0x14000cb81  mov     rcx, rdi; P
0x14000cb84  call    SecFreePool
0x14000cb89  mov     rdi, [rbp+var_58]
0x14000cb8d  mov     ecx, 0FFFFh
0x14000cb92  movzx   esi, si
0x14000cb95  xor     r12d, r12d
0x14000cb98  add     esi, esi
0x14000cb9a  cmp     esi, ecx
0x14000cb9c  ja      short loc_14000CBA6
0x14000cb9e  mov     ebx, r12d
0x14000cba1  jmp     loc_14000CA17
0x14000cba6  mov     ebx, 0C0000095h
0x14000cbab  movzx   esi, cx
0x14000cbae  jmp     loc_14000CA17
0x14000cbb3  test    eax, eax
0x14000cbb5  js      short loc_14000CBD2
0x14000cbb7  mov     rax, [rbp+var_48]
0x14000cbbb  mov     [rax+8], rdi
0x14000cbbf  mov     [rax], r12w
0x14000cbc3  mov     [rax+2], si
0x14000cbc7  xor     eax, eax
0x14000cbc9  jmp     short loc_14000CC0E
0x14000cbcb  mov     ebx, 0C000009Ah
0x14000cbd0  jmp     short loc_14000CBD5
0x14000cbd2  xor     r12d, r12d
0x14000cbd5  mov     rsi, [rbp+var_50]
0x14000cbd9  mov     rcx, [r13+0]; P
0x14000cbdd  test    rcx, rcx
0x14000cbe0  jz      short loc_14000CBEC
0x14000cbe2  mov     edx, 64446353h; Tag
0x14000cbe7  call    SecFreePool
0x14000cbec  test    rdi, rdi
0x14000cbef  jz      short loc_14000CBFE
0x14000cbf1  mov     edx, 74736353h; Tag
0x14000cbf6  mov     rcx, rdi; P
0x14000cbf9  call    SecFreePool
0x14000cbfe  mov     [r13+0], r12
0x14000cc02  mov     eax, ebx
0x14000cc04  mov     [rsi], r12d
0x14000cc07  jmp     short loc_14000CC0E
0x14000cc09  mov     eax, 0C0000225h
0x14000cc0e  mov     rcx, [rbp+var_10]
0x14000cc12  xor     rcx, rsp; StackCookie
0x14000cc15  call    __security_check_cookie
0x14000cc1a  add     rsp, 78h
0x14000cc1e  pop     r15
0x14000cc20  pop     r14
0x14000cc22  pop     r13
0x14000cc24  pop     r12
0x14000cc26  pop     rdi
0x14000cc27  pop     rsi
0x14000cc28  pop     rbx
0x14000cc29  pop     rbp
0x14000cc2a  retn
```

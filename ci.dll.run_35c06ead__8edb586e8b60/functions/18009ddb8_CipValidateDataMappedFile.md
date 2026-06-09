# CipValidateDataMappedFile

- ea: `0x18009ddb8`
- end: `0x18009df42`
- name: `CipValidateDataMappedFile`
- size: `394`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180064284`
- `0x18009daf0`

## callees

- `0x18009ddb8`
- `0x18009df48`
- `0x18009df84`
- `0x18009e170`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18009de4c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18009de4c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009ddf5`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009ddf5`

## pseudocode

```c
__int64 __fastcall CipValidateDataMappedFile(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        unsigned int a4,
        char a5,
        char a6,
        int a7,
        _DWORD *a8,
        _OWORD *a9,
        int a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        _DWORD *a14)
{
  unsigned int v15; // esi
  struct _UNICODE_STRING *v17; // rax
  struct _UNICODE_STRING *v18; // rdi
  int v19; // ebx
  _OWORD *v21; // rdx
  _OWORD *v22; // rax
  char v23; // [rsp+28h] [rbp-30h]
  char v24; // [rsp+30h] [rbp-28h]
  __int64 v25; // [rsp+70h] [rbp+18h] BYREF

  v25 = 0;
  v15 = a2;
  if ( a2 > 0xFFFFFFFF )
  {
    return (unsigned int)-1073741701;
  }
  else
  {
    v17 = (struct _UNICODE_STRING *)ExAllocateFromPagedLookasideList(&g_CiValidationLookasideList);
    v18 = v17;
    if ( v17 )
    {
      v19 = CiInitializeValidationContext(a4, 0, v17);
      v18[190].Buffer = 0;
      *(_QWORD *)&v18[208].Length = 0;
      *(_QWORD *)&v18[190].Length = &off_18002EEF0;
      if ( v19 >= 0 )
      {
        RtlInitUnicodeString(v18 + 53, 0);
        *(_DWORD *)&v18[191].Length |= 0x80u;
        v24 = a6;
        v23 = a5;
        v18[42].Buffer = 0;
        *(_QWORD *)&v18[207].Length = 0;
        v19 = CipValidateDataMappedFileWithContext(v18, a1, v15, 0, a4, v23, v24, &v25);
        if ( v19 >= 0 )
        {
          v21 = (_OWORD *)v25;
          if ( a8 )
            *a8 = *(_DWORD *)(v25 + 48);
          v22 = a9;
          if ( a9 )
          {
            *a9 = *v21;
            v22[1] = v21[1];
            v22[2] = v21[2];
            *v21 = 0;
            v21[1] = 0;
            v21[2] = 0;
          }
          if ( a14 )
            *a14 = v18[188].Buffer;
        }
      }
      CiFreeValidationContext((void (***)(void))v18);
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18009ddb8  mov     rax, rsp
0x18009ddbb  mov     [rax+8], rbx
0x18009ddbf  mov     [rax+10h], rbp
0x18009ddc3  mov     [rax+18h], r8
0x18009ddc7  push    rsi
0x18009ddc8  push    rdi
0x18009ddc9  push    r14
0x18009ddcb  sub     rsp, 40h
0x18009ddcf  mov     qword ptr [rax+18h], 0
0x18009ddd7  mov     ebp, r9d
0x18009ddda  mov     eax, 0FFFFFFFFh
0x18009dddf  mov     rsi, rdx
0x18009dde2  mov     r14, rcx
0x18009dde5  cmp     rdx, rax
0x18009dde8  ja      loc_18009DECF
0x18009ddee  lea     rcx, g_CiValidationLookasideList; Lookaside
0x18009ddf5  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18009ddfc  nop     dword ptr [rax+rax+00h]
0x18009de01  mov     rdi, rax
0x18009de04  test    rax, rax
0x18009de07  jz      loc_18009DF38
0x18009de0d  mov     r8, rax
0x18009de10  xor     edx, edx
0x18009de12  mov     ecx, ebp
0x18009de14  call    CiInitializeValidationContext
0x18009de19  mov     ebx, eax
0x18009de1b  mov     qword ptr [rdi+0BE8h], 0
0x18009de26  mov     qword ptr [rdi+0D00h], 0
0x18009de31  lea     rax, off_18002EEF0
0x18009de38  mov     [rdi+0BE0h], rax
0x18009de3f  test    ebx, ebx
0x18009de41  js      short loc_18009DEB1
0x18009de43  lea     rcx, [rdi+350h]; DestinationString
0x18009de4a  xor     edx, edx; SourceString
0x18009de4c  call    cs:__imp_RtlInitUnicodeString
0x18009de53  nop     dword ptr [rax+rax+00h]
0x18009de58  bts     dword ptr [rdi+0BF0h], 7
0x18009de60  lea     rax, [rsp+58h+arg_10]
0x18009de65  mov     [rsp+58h+var_20], rax
0x18009de6a  xor     r9d, r9d
0x18009de6d  mov     al, [rsp+58h+arg_28]
0x18009de74  mov     rdx, r14
0x18009de77  mov     [rsp+58h+var_28], al
0x18009de7b  mov     rcx, rdi
0x18009de7e  mov     al, [rsp+58h+arg_20]
0x18009de85  mov     [rsp+58h+var_30], al
0x18009de89  mov     r8d, esi
0x18009de8c  mov     [rsp+58h+var_38], ebp
0x18009de90  mov     qword ptr [rdi+2A8h], 0
0x18009de9b  mov     qword ptr [rdi+0CF0h], 0
0x18009dea6  call    CipValidateDataMappedFileWithContext
0x18009deab  mov     ebx, eax
0x18009dead  test    eax, eax
0x18009deaf  jns     short loc_18009DED6
0x18009deb1  mov     rcx, rdi; Entry
0x18009deb4  call    CiFreeValidationContext
0x18009deb9  mov     rbp, [rsp+58h+arg_8]
0x18009debe  mov     eax, ebx
0x18009dec0  mov     rbx, [rsp+58h+arg_0]
0x18009dec5  add     rsp, 40h
0x18009dec9  pop     r14
0x18009decb  pop     rdi
0x18009decc  pop     rsi
0x18009decd  retn
0x18009decf  mov     ebx, 0C000007Bh
0x18009ded4  jmp     short loc_18009DEB9
0x18009ded6  mov     rax, [rsp+58h+arg_38]
0x18009dede  mov     rdx, [rsp+58h+arg_10]
0x18009dee3  test    rax, rax
0x18009dee6  jz      short loc_18009DEED
0x18009dee8  mov     ecx, [rdx+30h]
0x18009deeb  mov     [rax], ecx
0x18009deed  mov     rax, [rsp+58h+arg_40]
0x18009def5  test    rax, rax
0x18009def8  jz      short loc_18009DF1E
0x18009defa  movups  xmm0, xmmword ptr [rdx]
0x18009defd  movups  xmmword ptr [rax], xmm0
0x18009df00  movups  xmm1, xmmword ptr [rdx+10h]
0x18009df04  movups  xmmword ptr [rax+10h], xmm1
0x18009df08  movups  xmm0, xmmword ptr [rdx+20h]
0x18009df0c  xorps   xmm1, xmm1
0x18009df0f  movups  xmmword ptr [rax+20h], xmm0
0x18009df13  movups  xmmword ptr [rdx], xmm1
0x18009df16  movups  xmmword ptr [rdx+10h], xmm1
0x18009df1a  movups  xmmword ptr [rdx+20h], xmm1
0x18009df1e  mov     rcx, [rsp+58h+arg_68]
0x18009df26  test    rcx, rcx
0x18009df29  jz      short loc_18009DEB1
0x18009df2b  mov     eax, [rdi+0BC8h]
0x18009df31  mov     [rcx], eax
0x18009df33  jmp     loc_18009DEB1
0x18009df38  mov     ebx, 0C0000017h
0x18009df3d  jmp     loc_18009DEB9
```

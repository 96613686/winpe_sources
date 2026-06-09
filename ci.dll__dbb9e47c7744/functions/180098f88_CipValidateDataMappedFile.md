# CipValidateDataMappedFile

- ea: `0x180098f88`
- end: `0x180099112`
- name: `CipValidateDataMappedFile`
- size: `394`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180064114`
- `0x180098cc0`

## callees

- `0x180098f88`
- `0x180099118`
- `0x180099154`
- `0x180099340`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18009901c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18009901c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180098fc5`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180098fc5`

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
      *(_QWORD *)&v18[190].Length = 0;
      *(_QWORD *)&v18[207].Length = 0;
      v18[189].Buffer = (PWSTR)&off_18002EE80;
      if ( v19 >= 0 )
      {
        RtlInitUnicodeString(v18 + 53, 0);
        LODWORD(v18[190].Buffer) |= 0x80u;
        v24 = a6;
        v23 = a5;
        v18[42].Buffer = 0;
        *(_QWORD *)&v18[206].Length = 0;
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
            *a14 = *(_DWORD *)&v18[188].Length;
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
0x180098f88  mov     rax, rsp
0x180098f8b  mov     [rax+8], rbx
0x180098f8f  mov     [rax+10h], rbp
0x180098f93  mov     [rax+18h], r8
0x180098f97  push    rsi
0x180098f98  push    rdi
0x180098f99  push    r14
0x180098f9b  sub     rsp, 40h
0x180098f9f  mov     qword ptr [rax+18h], 0
0x180098fa7  mov     ebp, r9d
0x180098faa  mov     eax, 0FFFFFFFFh
0x180098faf  mov     rsi, rdx
0x180098fb2  mov     r14, rcx
0x180098fb5  cmp     rdx, rax
0x180098fb8  ja      loc_18009909F
0x180098fbe  lea     rcx, g_CiValidationLookasideList; Lookaside
0x180098fc5  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180098fcc  nop     dword ptr [rax+rax+00h]
0x180098fd1  mov     rdi, rax
0x180098fd4  test    rax, rax
0x180098fd7  jz      loc_180099108
0x180098fdd  mov     r8, rax
0x180098fe0  xor     edx, edx
0x180098fe2  mov     ecx, ebp
0x180098fe4  call    CiInitializeValidationContext
0x180098fe9  mov     ebx, eax
0x180098feb  mov     qword ptr [rdi+0BE0h], 0
0x180098ff6  mov     qword ptr [rdi+0CF0h], 0
0x180099001  lea     rax, off_18002EE80
0x180099008  mov     [rdi+0BD8h], rax
0x18009900f  test    ebx, ebx
0x180099011  js      short loc_180099081
0x180099013  lea     rcx, [rdi+350h]; DestinationString
0x18009901a  xor     edx, edx; SourceString
0x18009901c  call    cs:__imp_RtlInitUnicodeString
0x180099023  nop     dword ptr [rax+rax+00h]
0x180099028  bts     dword ptr [rdi+0BE8h], 7
0x180099030  lea     rax, [rsp+58h+arg_10]
0x180099035  mov     [rsp+58h+var_20], rax
0x18009903a  xor     r9d, r9d
0x18009903d  mov     al, [rsp+58h+arg_28]
0x180099044  mov     rdx, r14
0x180099047  mov     [rsp+58h+var_28], al
0x18009904b  mov     rcx, rdi
0x18009904e  mov     al, [rsp+58h+arg_20]
0x180099055  mov     [rsp+58h+var_30], al
0x180099059  mov     r8d, esi
0x18009905c  mov     [rsp+58h+var_38], ebp
0x180099060  mov     qword ptr [rdi+2A8h], 0
0x18009906b  mov     qword ptr [rdi+0CE0h], 0
0x180099076  call    CipValidateDataMappedFileWithContext
0x18009907b  mov     ebx, eax
0x18009907d  test    eax, eax
0x18009907f  jns     short loc_1800990A6
0x180099081  mov     rcx, rdi; Entry
0x180099084  call    CiFreeValidationContext
0x180099089  mov     rbp, [rsp+58h+arg_8]
0x18009908e  mov     eax, ebx
0x180099090  mov     rbx, [rsp+58h+arg_0]
0x180099095  add     rsp, 40h
0x180099099  pop     r14
0x18009909b  pop     rdi
0x18009909c  pop     rsi
0x18009909d  retn
0x18009909f  mov     ebx, 0C000007Bh
0x1800990a4  jmp     short loc_180099089
0x1800990a6  mov     rax, [rsp+58h+arg_38]
0x1800990ae  mov     rdx, [rsp+58h+arg_10]
0x1800990b3  test    rax, rax
0x1800990b6  jz      short loc_1800990BD
0x1800990b8  mov     ecx, [rdx+30h]
0x1800990bb  mov     [rax], ecx
0x1800990bd  mov     rax, [rsp+58h+arg_40]
0x1800990c5  test    rax, rax
0x1800990c8  jz      short loc_1800990EE
0x1800990ca  movups  xmm0, xmmword ptr [rdx]
0x1800990cd  movups  xmmword ptr [rax], xmm0
0x1800990d0  movups  xmm1, xmmword ptr [rdx+10h]
0x1800990d4  movups  xmmword ptr [rax+10h], xmm1
0x1800990d8  movups  xmm0, xmmword ptr [rdx+20h]
0x1800990dc  xorps   xmm1, xmm1
0x1800990df  movups  xmmword ptr [rax+20h], xmm0
0x1800990e3  movups  xmmword ptr [rdx], xmm1
0x1800990e6  movups  xmmword ptr [rdx+10h], xmm1
0x1800990ea  movups  xmmword ptr [rdx+20h], xmm1
0x1800990ee  mov     rcx, [rsp+58h+arg_68]
0x1800990f6  test    rcx, rcx
0x1800990f9  jz      short loc_180099081
0x1800990fb  mov     eax, [rdi+0BC0h]
0x180099101  mov     [rcx], eax
0x180099103  jmp     loc_180099081
0x180099108  mov     ebx, 0C0000017h
0x18009910d  jmp     loc_180099089
```

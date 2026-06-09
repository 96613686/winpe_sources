# RtlpOpenImageFileOptionsKeyEx

- ea: `0x1800737f8`
- end: `0x180073ab7`
- name: `RtlpOpenImageFileOptionsKeyEx`
- size: `703`
- prototype: ``
- caller_count: `8`
- callee_count: `11`
- tags: ``

## callers

- `0x180071ff8`
- `0x18007248c`
- `0x1800731f0`
- `0x180073320`
- `0x180074d08`
- `0x1801128e0`
- `0x1801133b0`
- `0x18013afcc`

## callees

- `0x180073744`
- `0x1800737f8`
- `0x180073ac0`
- `0x180073f14`
- `0x180073fb0`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e670`
- `0x18015eec0`
- `0x18015fe40`

## string_xrefs

- `0x180073988`: `FilterFullPath`

## pseudocode

```c
__int64 __fastcall RtlpOpenImageFileOptionsKeyEx(unsigned __int16 *a1, unsigned int a2, char a3, _QWORD *a4)
{
  __int64 v7; // rdx
  _WORD *v8; // r8
  int v9; // ecx
  char v10; // r12
  int v11; // ecx
  char v12; // r15
  __int64 result; // rax
  HANDLE v14; // rdi
  int v15; // eax
  int v16; // ebx
  int v17; // eax
  HANDLE v18; // rdi
  size_t v19; // rax
  size_t v20; // rax
  int v21; // eax
  HANDLE Handle; // [rsp+40h] [rbp-29h] BYREF
  const wchar_t *v23; // [rsp+48h] [rbp-21h]
  __int128 v24; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v25[96]; // [rsp+60h] [rbp-9h] BYREF
  HANDLE v26; // [rsp+D0h] [rbp+67h] BYREF
  int v27; // [rsp+E0h] [rbp+77h] BYREF
  _QWORD *v28; // [rsp+E8h] [rbp+7Fh]

  v28 = a4;
  *a4 = 0;
  Handle = 0;
  v26 = 0;
  v7 = *a1;
  v8 = (_WORD *)(v7 + *((_QWORD *)a1 + 1));
  v24 = 0;
  memset(v25, 0, 44);
  if ( a3 && (v7 + 2 > (unsigned __int64)a1[1] || *v8) )
    return 3221225485LL;
  v9 = v7;
  v10 = 0;
  while ( (_DWORD)v7 )
  {
    if ( *(v8 - 1) == 92 )
    {
      v10 = 1;
      break;
    }
    --v8;
    LODWORD(v7) = v7 - 2;
  }
  v11 = v9 - v7;
  *((_QWORD *)&v24 + 1) = v8;
  LOWORD(v24) = v11;
  if ( (unsigned __int16)v11 != v11 )
    return 3221225507LL;
  if ( a3 )
  {
    LOBYTE(v8) = a3;
    v12 = 1;
    result = RtlpOpenBaseImageFileOptionsKeyEx(&Handle, a2, v8);
  }
  else
  {
    v12 = 0;
    result = RtlpOpenBaseImageFileOptionsKey(&Handle);
  }
  if ( (int)result >= 0 )
  {
    v14 = Handle;
    *(_QWORD *)&v25[8] = Handle;
    *(_QWORD *)&v25[16] = &v24;
    *(_DWORD *)v25 = 48;
    *(_DWORD *)&v25[24] = 576;
    *(_OWORD *)&v25[32] = 0;
    if ( a3 )
      v15 = ZwCreateKey(&v26, a2, v25, 0, 0, 0, 0);
    else
      v15 = NtOpenKey(&v26, a2, v25);
    v16 = v15;
    if ( v12 )
      NtClose(v14);
    if ( v16 < 0 )
      return (unsigned int)v16;
    Handle = v26;
    v21 = RtlpProcessIFEOKeyFilter(&Handle, a2, a1);
    v18 = Handle;
    v16 = v21;
    if ( v21 < 0 )
      goto LABEL_38;
    if ( Handle != v26 || !v10 || !a3 )
      goto LABEL_32;
    Handle = 0;
    v17 = RtlpCreateIFEOKeyFilterKey(&Handle, v26, a2 | 0x10000);
    v18 = Handle;
    v16 = v17;
    if ( v17 < 0 )
    {
LABEL_31:
      NtClose(v26);
      if ( v16 >= 0 )
      {
LABEL_32:
        *v28 = v18;
        return (unsigned int)v16;
      }
LABEL_38:
      if ( v18 )
        NtClose(v18);
      return (unsigned int)v16;
    }
    Handle = 0;
    v23 = L"FilterFullPath";
    v19 = wcslen(L"FilterFullPath");
    if ( v19 <= 0x7FFE )
    {
      LOWORD(Handle) = 2 * v19;
      WORD1(Handle) = 2 * v19 + 2;
      v16 = ZwSetValueKey(v18, &Handle, 0, 1, *((_QWORD *)a1 + 1), a1[1]);
      if ( v16 < 0 )
      {
LABEL_30:
        NtDeleteKey(v18);
        goto LABEL_31;
      }
      v27 = 1;
      v23 = L"UseFilter";
      Handle = 0;
      v20 = wcslen(L"UseFilter");
      if ( v20 <= 0x7FFE )
      {
        LOWORD(Handle) = 2 * v20;
        WORD1(Handle) = 2 * v20 + 2;
        v16 = ZwSetValueKey(v26, &Handle, 0, 4, &v27, 4);
        if ( v16 >= 0 )
          goto LABEL_31;
        goto LABEL_30;
      }
    }
    v16 = -1073741562;
    goto LABEL_30;
  }
  return result;
}

```

## disassembly

```asm
0x1800737f8  mov     [rsp-8+arg_8], rbx
0x1800737fd  mov     [rsp-8+arg_18], r9
0x180073802  push    rbp
0x180073803  push    rsi
0x180073804  push    rdi
0x180073805  push    r12
0x180073807  push    r13
0x180073809  push    r14
0x18007380b  push    r15
0x18007380d  lea     rbp, [rsp-27h]
0x180073812  sub     rsp, 90h
0x180073819  xor     ebx, ebx
0x18007381b  xorps   xmm0, xmm0
0x18007381e  mov     r13, rcx
0x180073821  mov     [r9], rbx
0x180073824  mov     r14b, r8b
0x180073827  mov     [rbp+57h+Handle], rbx
0x18007382b  mov     esi, edx
0x18007382d  mov     [rbp+57h+arg_0], rbx
0x180073831  xor     ecx, ecx
0x180073833  movzx   edx, word ptr [r13+0]
0x180073838  mov     r8, [r13+8]
0x18007383c  add     r8, rdx
0x18007383f  movups  [rbp+57h+var_50], xmm0
0x180073843  movups  [rbp+57h+var_70], xmm0
0x180073847  movups  [rbp+57h+var_60], xmm0
0x18007384b  movups  [rbp+57h+var_50+0Ch], xmm0
0x18007384f  test    r14b, r14b
0x180073852  jnz     loc_180073915
0x180073858  mov     ecx, edx
0x18007385a  mov     r12b, bl
0x18007385d  test    edx, edx
0x18007385f  jz      short loc_180073875
0x180073861  cmp     word ptr [r8-2], 5Ch ; '\'
0x180073867  jz      short loc_180073872
0x180073869  add     r8, 0FFFFFFFFFFFFFFFEh
0x18007386d  add     edx, 0FFFFFFFEh
0x180073870  jmp     short loc_18007385D
0x180073872  mov     r12b, 1
0x180073875  sub     ecx, edx
0x180073877  mov     qword ptr [rbp+57h+var_70+8], r8
0x18007387b  movzx   eax, cx
0x18007387e  mov     word ptr [rbp+57h+var_70], ax
0x180073882  cmp     eax, ecx
0x180073884  jnz     loc_180073954
0x18007388a  lea     rcx, [rbp+57h+Handle]
0x18007388e  test    r14b, r14b
0x180073891  jnz     loc_180073942
0x180073897  mov     r15b, bl
0x18007389a  call    RtlpOpenBaseImageFileOptionsKey
0x18007389f  test    eax, eax
0x1800738a1  js      short loc_1800738F9
0x1800738a3  mov     rdi, [rbp+57h+Handle]
0x1800738a7  lea     rax, [rbp+57h+var_70]
0x1800738ab  mov     qword ptr [rbp+57h+var_60+8], rdi
0x1800738af  xorps   xmm0, xmm0
0x1800738b2  mov     qword ptr [rbp+57h+var_50], rax
0x1800738b6  lea     r8, [rbp+57h+var_60]
0x1800738ba  mov     dword ptr [rbp+57h+var_60], 30h ; '0'
0x1800738c1  mov     edx, esi
0x1800738c3  mov     dword ptr [rbp+57h+var_50+8], 240h
0x1800738ca  lea     rcx, [rbp+57h+arg_0]
0x1800738ce  movdqu  [rbp+57h+var_40], xmm0
0x1800738d3  test    r14b, r14b
0x1800738d6  jnz     short loc_18007392A
0x1800738d8  call    NtOpenKey
0x1800738dd  mov     ebx, eax
0x1800738df  test    r15b, r15b
0x1800738e2  jz      short loc_1800738EC
0x1800738e4  mov     rcx, rdi; Handle
0x1800738e7  call    NtClose
0x1800738ec  xor     r15d, r15d
0x1800738ef  test    ebx, ebx
0x1800738f1  jns     loc_180073A62
0x1800738f7  mov     eax, ebx
0x1800738f9  mov     rbx, [rsp+0C0h+arg_8]
0x180073901  add     rsp, 90h
0x180073908  pop     r15
0x18007390a  pop     r14
0x18007390c  pop     r13
0x18007390e  pop     r12
0x180073910  pop     rdi
0x180073911  pop     rsi
0x180073912  pop     rbp
0x180073913  retn
0x180073915  movzx   ecx, word ptr [r13+2]
0x18007391a  lea     rax, [rdx+2]
0x18007391e  cmp     rax, rcx
0x180073921  jbe     short loc_18007395B
0x180073923  mov     eax, 0C000000Dh
0x180073928  jmp     short loc_1800738F9
0x18007392a  mov     [rsp+0C0h+var_90], rbx
0x18007392f  xor     r9d, r9d
0x180073932  mov     [rsp+0C0h+var_98], ebx
0x180073936  mov     [rsp+0C0h+var_A0], rbx
0x18007393b  call    ZwCreateKey
0x180073940  jmp     short loc_1800738DD
0x180073942  mov     r8b, r14b
0x180073945  mov     edx, esi
0x180073947  mov     r15b, 1
0x18007394a  call    RtlpOpenBaseImageFileOptionsKeyEx
0x18007394f  jmp     loc_18007389F
0x180073954  mov     eax, 0C0000023h
0x180073959  jmp     short loc_1800738F9
0x18007395b  cmp     [r8], bx
0x18007395f  jnz     short loc_180073923
0x180073961  jmp     loc_180073858
0x180073966  bts     esi, 10h
0x18007396a  mov     [rbp+57h+Handle], r15
0x18007396e  mov     r8d, esi
0x180073971  lea     rcx, [rbp+57h+Handle]
0x180073975  call    RtlpCreateIFEOKeyFilterKey
0x18007397a  mov     rdi, [rbp+57h+Handle]
0x18007397e  mov     ebx, eax
0x180073980  test    eax, eax
0x180073982  js      loc_180073A49
0x180073988  lea     rcx, aFilterfullpath; "FilterFullPath"
0x18007398f  mov     [rbp+57h+Handle], r15
0x180073993  mov     [rbp+57h+var_78], rcx
0x180073997  call    wcslen
0x18007399c  mov     esi, 7FFEh
0x1800739a1  cmp     rax, rsi
0x1800739a4  ja      loc_180073AB0
0x1800739aa  add     ax, ax
0x1800739ad  lea     rdx, [rbp+57h+Handle]
0x1800739b1  mov     word ptr [rbp+57h+Handle], ax
0x1800739b5  mov     r14d, 1
0x1800739bb  add     ax, 2
0x1800739bf  mov     r9d, r14d
0x1800739c2  mov     word ptr [rbp+57h+Handle+2], ax
0x1800739c6  xor     r8d, r8d
0x1800739c9  movzx   eax, word ptr [r13+2]
0x1800739ce  mov     rcx, rdi
0x1800739d1  mov     [rsp+0C0h+var_98], eax
0x1800739d5  mov     rax, [r13+8]
0x1800739d9  mov     [rsp+0C0h+var_A0], rax
0x1800739de  call    ZwSetValueKey
0x1800739e3  mov     ebx, eax
0x1800739e5  test    eax, eax
0x1800739e7  js      short loc_180073A41
0x1800739e9  lea     rcx, aUsefilter; "UseFilter"
0x1800739f0  mov     [rbp+57h+arg_10], r14d
0x1800739f4  mov     [rbp+57h+var_78], rcx
0x1800739f8  mov     [rbp+57h+Handle], r15
0x1800739fc  call    wcslen
0x180073a01  cmp     rax, rsi
0x180073a04  ja      loc_180073AB0
0x180073a0a  mov     rcx, [rbp+57h+arg_0]
0x180073a0e  lea     r9d, [r14+3]
0x180073a12  add     ax, ax
0x180073a15  mov     [rsp+0C0h+var_98], r9d
0x180073a1a  mov     word ptr [rbp+57h+Handle], ax
0x180073a1e  lea     rdx, [rbp+57h+Handle]
0x180073a22  add     ax, 2
0x180073a26  xor     r8d, r8d
0x180073a29  mov     word ptr [rbp+57h+Handle+2], ax
0x180073a2d  lea     rax, [rbp+57h+arg_10]
0x180073a31  mov     [rsp+0C0h+var_A0], rax
0x180073a36  call    ZwSetValueKey
0x180073a3b  mov     ebx, eax
0x180073a3d  test    eax, eax
0x180073a3f  jns     short loc_180073A49
0x180073a41  mov     rcx, rdi
0x180073a44  call    NtDeleteKey
0x180073a49  mov     rcx, [rbp+57h+arg_0]; Handle
0x180073a4d  call    NtClose
0x180073a52  test    ebx, ebx
0x180073a54  js      short loc_180073A9A
0x180073a56  mov     rax, [rbp+57h+arg_18]
0x180073a5a  mov     [rax], rdi
0x180073a5d  jmp     loc_1800738F7
0x180073a62  mov     rax, [rbp+57h+arg_0]
0x180073a66  lea     rcx, [rbp+57h+Handle]
0x180073a6a  mov     r8, r13
0x180073a6d  mov     [rbp+57h+Handle], rax
0x180073a71  mov     edx, esi
0x180073a73  call    RtlpProcessIFEOKeyFilter
0x180073a78  mov     rdi, [rbp+57h+Handle]
0x180073a7c  mov     ebx, eax
0x180073a7e  test    eax, eax
0x180073a80  js      short loc_180073A9A
0x180073a82  mov     rdx, [rbp+57h+arg_0]
0x180073a86  cmp     rdi, rdx
0x180073a89  jnz     short loc_180073A56
0x180073a8b  test    r12b, r12b
0x180073a8e  jz      short loc_180073A56
0x180073a90  test    r14b, r14b
0x180073a93  jz      short loc_180073A56
0x180073a95  jmp     loc_180073966
0x180073a9a  test    rdi, rdi
0x180073a9d  jz      loc_1800738F7
0x180073aa3  mov     rcx, rdi; Handle
0x180073aa6  call    NtClose
0x180073aab  jmp     loc_1800738F7
0x180073ab0  mov     ebx, 0C0000106h
0x180073ab5  jmp     short loc_180073A41
```

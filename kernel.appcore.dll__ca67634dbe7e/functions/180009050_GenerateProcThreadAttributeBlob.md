# GenerateProcThreadAttributeBlob

- ea: `0x180009050`
- end: `0x180009171`
- name: `GenerateProcThreadAttributeBlob`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180008d78`
- `0x180009050`
- `0x180009d92`
- `0x180009d9e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009097`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009097`

## pseudocode

```c
signed int __fastcall GenerateProcThreadAttributeBlob(
        unsigned int a1,
        struct _PROC_THREAD_ATTRIBUTE_BLOB_ENTRY *a2,
        _QWORD *a3,
        _DWORD *a4)
{
  __int64 v4; // rdi
  signed int result; // eax
  size_t v9; // rbx
  HLOCAL v10; // rax
  __int64 v11; // r12
  void *v12; // rcx
  char *v13; // r13
  unsigned int v14; // ebp
  __int64 v15; // r15
  SIZE_T uBytes; // [rsp+80h] [rbp+18h] BYREF

  v4 = a1;
  *a3 = 0;
  *a4 = 0;
  LODWORD(uBytes) = 0;
  result = ValidateAttributeListAndDetermineBlobSize(a1, a2, (unsigned int *)&uBytes);
  if ( !result )
  {
    v9 = (unsigned int)uBytes;
    v10 = LocalAlloc(0, (unsigned int)uBytes);
    *a3 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, v9);
      *a4 = v9;
      if ( (_DWORD)v4 )
      {
        v11 = *a3;
        v12 = (void *)(*a3 + 8LL);
        *(_DWORD *)*a3 = v4;
        memcpy_0(v12, a2, 16 * v4);
        v13 = (char *)(16LL * (unsigned int)(v4 - 1) + *a3 + 24LL);
        v14 = 0;
        v15 = 0;
        do
        {
          if ( *((_DWORD *)a2 + 4 * v15 + 1) > 8u || *((_DWORD *)a2 + 4 * v15) == 131088 )
          {
            memcpy_0(v13, *((const void **)a2 + 2 * v15 + 1), *((unsigned int *)a2 + 4 * v15 + 1));
            *(_QWORD *)(v11 + 16 * v15 + 16) = 0;
            *(_DWORD *)(v11 + 16 * v15 + 16) = (_DWORD)v13 - *(_DWORD *)a3;
            *(_DWORD *)(v11 + 4) += *((_DWORD *)a2 + 4 * v15 + 1);
            v13 += *((unsigned int *)a2 + 4 * v15 + 1);
          }
          ++v14;
          ++v15;
        }
        while ( v14 < (unsigned int)v4 );
      }
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009050  mov     rax, rsp
0x180009053  push    rbx
0x180009054  push    rbp
0x180009055  push    rsi
0x180009056  push    rdi
0x180009057  push    r12
0x180009059  push    r13
0x18000905b  push    r14
0x18000905d  push    r15
0x18000905f  sub     rsp, 28h
0x180009063  xor     r12d, r12d
0x180009066  mov     edi, ecx
0x180009068  mov     [r8], r12
0x18000906b  mov     r14, r8
0x18000906e  lea     r8, [rax+18h]; unsigned int *
0x180009072  mov     [r9], r12d
0x180009075  mov     r15, r9
0x180009078  mov     [rax+18h], r12d
0x18000907c  mov     rsi, rdx
0x18000907f  call    ?ValidateAttributeListAndDetermineBlobSize@@YAJKPEAU_PROC_THREAD_ATTRIBUTE_BLOB_ENTRY@@PEAK@Z; ValidateAttributeListAndDetermineBlobSize(ulong,_PROC_THREAD_ATTRIBUTE_BLOB_ENTRY *,ulong *)
0x180009084  test    eax, eax
0x180009086  jnz     loc_180009160
0x18000908c  mov     ebx, dword ptr [rsp+68h+uBytes]
0x180009093  xor     ecx, ecx; uFlags
0x180009095  mov     edx, ebx; uBytes
0x180009097  call    cs:__imp_LocalAlloc
0x18000909d  mov     [r14], rax
0x1800090a0  test    rax, rax
0x1800090a3  jnz     short loc_1800090C0
0x1800090a5  call    cs:__imp_GetLastError
0x1800090ab  test    eax, eax
0x1800090ad  jle     loc_180009160
0x1800090b3  movzx   eax, ax
0x1800090b6  or      eax, 80070000h
0x1800090bb  jmp     loc_180009160
0x1800090c0  mov     r8, rbx; Size
0x1800090c3  xor     edx, edx; Val
0x1800090c5  mov     rcx, rax; void *
0x1800090c8  call    memset_0
0x1800090cd  mov     [r15], ebx
0x1800090d0  test    edi, edi
0x1800090d2  jz      loc_18000915E
0x1800090d8  mov     r12, [r14]
0x1800090db  mov     r8, rdi
0x1800090de  shl     r8, 4; Size
0x1800090e2  mov     rdx, rsi; Src
0x1800090e5  lea     rcx, [r12+8]; void *
0x1800090ea  mov     [r12], edi
0x1800090ee  call    memcpy_0
0x1800090f3  mov     r13, [r14]
0x1800090f6  lea     ecx, [rdi-1]
0x1800090f9  shl     rcx, 4
0x1800090fd  add     r13, 18h
0x180009101  add     r13, rcx
0x180009104  xor     ebp, ebp
0x180009106  xor     r15d, r15d
0x180009109  mov     rbx, r15
0x18000910c  add     rbx, rbx
0x18000910f  cmp     dword ptr [rsi+rbx*8+4], 8
0x180009114  ja      short loc_18000911F
0x180009116  cmp     dword ptr [rsi+rbx*8], 20010h
0x18000911d  jnz     short loc_180009155
0x18000911f  mov     r8d, [rsi+rbx*8+4]; Size
0x180009124  mov     rcx, r13; void *
0x180009127  mov     rdx, [rsi+rbx*8+8]; Src
0x18000912c  call    memcpy_0
0x180009131  mov     qword ptr [r12+rbx*8+10h], 0
0x18000913a  mov     eax, r13d
0x18000913d  sub     eax, [r14]
0x180009140  mov     [r12+rbx*8+10h], eax
0x180009145  mov     eax, [rsi+rbx*8+4]
0x180009149  add     [r12+4], eax
0x18000914e  mov     eax, [rsi+rbx*8+4]
0x180009152  add     r13, rax
0x180009155  inc     ebp
0x180009157  inc     r15
0x18000915a  cmp     ebp, edi
0x18000915c  jb      short loc_180009109
0x18000915e  xor     eax, eax
0x180009160  add     rsp, 28h
0x180009164  pop     r15
0x180009166  pop     r14
0x180009168  pop     r13
0x18000916a  pop     r12
0x18000916c  pop     rdi
0x18000916d  pop     rsi
0x18000916e  pop     rbp
0x18000916f  pop     rbx
0x180009170  retn
```

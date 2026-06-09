# ControlEventLogParser::LoadSlimEtlEvents(void *,_SLEEPSTUDY_CONTROL_ETL_HEADER *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800592d4`
- end: `0x180059439`
- name: `?LoadSlimEtlEvents@ControlEventLogParser@@AEAAKPEAXPEAU_SLEEPSTUDY_CONTROL_ETL_HEADER@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800597b8`

## callees

- `0x180027c30`
- `0x18004d8fc`
- `0x1800592d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18005939a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800593eb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18005939a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800593eb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800593c4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005940f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800593c4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005940f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800593a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800593a5`

## pseudocode

```c
DWORD __fastcall ControlEventLogParser::LoadSlimEtlEvents(__int64 a1, void *a2, _DWORD *a3, LPVOID *a4)
{
  char *v5; // r9
  char *v8; // r14
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rcx
  char *v11; // rax
  unsigned __int64 v12; // rbx
  DWORD v13; // ebx
  DWORD v15; // edi
  __int64 NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int64 v17; // [rsp+70h] [rbp+18h] BYREF

  NumberOfBytesRead = a1;
  v17 = 0;
  v5 = (char *)*a4;
  LODWORD(NumberOfBytesRead) = 0;
  v8 = (char *)a4[1];
  v9 = (unsigned int)(a3[4] - a3[3]);
  v10 = v8 - v5;
  if ( v9 >= v8 - v5 )
  {
    if ( v9 <= v10 )
      goto LABEL_8;
    if ( v9 > (_BYTE *)a4[2] - v5 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a4, (unsigned int)(a3[4] - a3[3]));
      goto LABEL_8;
    }
    v12 = v9 - v10;
    memset_0(a4[1], 0, v9 - v10);
    v11 = &v8[v12];
  }
  else
  {
    v11 = &v5[a3[4] - a3[3]];
  }
  a4[1] = v11;
LABEL_8:
  v13 = v9;
  if ( (unsigned int)v9 >= a3[5] - a3[3] % a3[5] )
    v13 = a3[5] - a3[3] % a3[5];
  if ( v13 )
  {
    v17 = (unsigned int)a3[3] % (unsigned __int64)(unsigned int)a3[5] + 4096;
    if ( SetFilePointer(a2, v17, (PLONG)&v17 + 1, 0) == -1 || !ReadFile(a2, *a4, v13, (LPDWORD)&NumberOfBytesRead, 0) )
      return GetLastError();
    if ( (_DWORD)NumberOfBytesRead != v13 )
      return 1100;
  }
  v15 = v9 - v13;
  if ( !v15 )
    return 0;
  v17 = 4096;
  if ( SetFilePointer(a2, 4096, (PLONG)&v17 + 1, 0) == -1
    || !ReadFile(a2, (char *)*a4 + v13, v15, (LPDWORD)&NumberOfBytesRead, 0) )
  {
    return GetLastError();
  }
  if ( (_DWORD)NumberOfBytesRead != v15 )
    return 1100;
  return 0;
}

```

## disassembly

```asm
0x1800592d4  mov     rax, rsp
0x1800592d7  mov     [rax+10h], rbx
0x1800592db  mov     [rax+8], rcx
0x1800592df  push    rbp
0x1800592e0  push    rsi
0x1800592e1  push    rdi
0x1800592e2  push    r14
0x1800592e4  push    r15
0x1800592e6  sub     rsp, 30h
0x1800592ea  mov     rsi, r9
0x1800592ed  mov     qword ptr [rax+18h], 0
0x1800592f5  mov     r9, [r9]
0x1800592f8  mov     r15, r8
0x1800592fb  mov     dword ptr [rax+8], 0
0x180059302  mov     rbp, rdx
0x180059305  mov     eax, [r8+10h]
0x180059309  sub     eax, [r8+0Ch]
0x18005930d  mov     r14, [rsi+8]
0x180059311  mov     rcx, r14
0x180059314  mov     edi, eax
0x180059316  sub     rcx, r9
0x180059319  cmp     rdi, rcx
0x18005931c  jnb     short loc_180059323
0x18005931e  add     rax, r9
0x180059321  jmp     short loc_180059355
0x180059323  jbe     short loc_180059359
0x180059325  mov     rax, [rsi+10h]
0x180059329  sub     rax, r9
0x18005932c  cmp     rdi, rax
0x18005932f  jbe     short loc_18005933E
0x180059331  mov     rdx, rdi
0x180059334  mov     rcx, rsi
0x180059337  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005933c  jmp     short loc_180059359
0x18005933e  mov     rbx, rdi
0x180059341  xor     edx, edx; Val
0x180059343  sub     rbx, rcx
0x180059346  mov     rcx, r14; void *
0x180059349  mov     r8, rbx; Size
0x18005934c  call    memset_0
0x180059351  lea     rax, [rbx+r14]
0x180059355  mov     [rsi+8], rax
0x180059359  mov     eax, [r15+0Ch]
0x18005935d  xor     edx, edx
0x18005935f  div     dword ptr [r15+14h]
0x180059363  mov     eax, [r15+14h]
0x180059367  mov     ebx, edi
0x180059369  sub     eax, edx
0x18005936b  mov     r14d, 1000h
0x180059371  cmp     edi, eax
0x180059373  cmovnb  ebx, eax
0x180059376  test    ebx, ebx
0x180059378  jz      short loc_1800593D4
0x18005937a  mov     ecx, [r15+14h]
0x18005937e  lea     r8, [rsp+58h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180059383  mov     eax, [r15+0Ch]
0x180059387  xor     edx, edx
0x180059389  div     rcx
0x18005938c  xor     r9d, r9d; dwMoveMethod
0x18005938f  mov     rcx, rbp; hFile
0x180059392  add     rdx, r14; lDistanceToMove
0x180059395  mov     [rsp+70h], rdx
0x18005939a  call    cs:__imp_SetFilePointer
0x1800593a0  cmp     eax, 0FFFFFFFFh
0x1800593a3  jnz     short loc_1800593AD
0x1800593a5  call    cs:__imp_GetLastError
0x1800593ab  jmp     short loc_180059428
0x1800593ad  mov     rdx, [rsi]; lpBuffer
0x1800593b0  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800593b5  mov     r8d, ebx; nNumberOfBytesToRead
0x1800593b8  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800593c1  mov     rcx, rbp; hFile
0x1800593c4  call    cs:__imp_ReadFile
0x1800593ca  test    eax, eax
0x1800593cc  jz      short loc_1800593A5
0x1800593ce  cmp     dword ptr [rsp+58h+NumberOfBytesRead], ebx
0x1800593d2  jnz     short loc_18005941F
0x1800593d4  sub     edi, ebx
0x1800593d6  jz      short loc_180059426
0x1800593d8  xor     r9d, r9d; dwMoveMethod
0x1800593db  mov     [rsp+70h], r14
0x1800593e0  lea     r8, [rsp+58h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1800593e5  mov     edx, r14d; lDistanceToMove
0x1800593e8  mov     rcx, rbp; hFile
0x1800593eb  call    cs:__imp_SetFilePointer
0x1800593f1  cmp     eax, 0FFFFFFFFh
0x1800593f4  jz      short loc_1800593A5
0x1800593f6  mov     edx, ebx
0x1800593f8  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800593fd  add     rdx, [rsi]; lpBuffer
0x180059400  mov     r8d, edi; nNumberOfBytesToRead
0x180059403  mov     rcx, rbp; hFile
0x180059406  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18005940f  call    cs:__imp_ReadFile
0x180059415  test    eax, eax
0x180059417  jz      short loc_1800593A5
0x180059419  cmp     dword ptr [rsp+58h+NumberOfBytesRead], edi
0x18005941d  jz      short loc_180059426
0x18005941f  mov     eax, 44Ch
0x180059424  jmp     short loc_180059428
0x180059426  xor     eax, eax
0x180059428  mov     rbx, [rsp+58h+arg_8]
0x18005942d  add     rsp, 30h
0x180059431  pop     r15
0x180059433  pop     r14
0x180059435  pop     rdi
0x180059436  pop     rsi
0x180059437  pop     rbp
0x180059438  retn
```

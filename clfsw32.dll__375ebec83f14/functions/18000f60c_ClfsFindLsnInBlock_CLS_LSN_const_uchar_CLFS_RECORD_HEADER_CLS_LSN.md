# ClfsFindLsnInBlock(_CLS_LSN const &,uchar *,_CLFS_RECORD_HEADER * &,_CLS_LSN &)

- ea: `0x18000f60c`
- end: `0x18000f767`
- name: `?ClfsFindLsnInBlock@@YAKAEBT_CLS_LSN@@PEAEAEAPEAU_CLFS_RECORD_HEADER@@AEAT1@@Z`
- size: `347`
- prototype: `unsigned int __fastcall(const union _CLS_LSN *, unsigned __int8 *, struct _CLFS_RECORD_HEADER **, union _CLS_LSN *)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001195c`
- `0x180011cfc`
- `0x1800124f0`
- `0x1800136a0`
- `0x180014328`

## callees

- `0x18000f60c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000f627`
- `ntdll!RtlNtStatusToDosError` at `0x18000f68a`
- `ntdll!RtlNtStatusToDosError` at `0x18000f74a`
- `ntdll!RtlNtStatusToDosError` at `0x18000f627`
- `ntdll!RtlNtStatusToDosError` at `0x18000f68a`
- `ntdll!RtlNtStatusToDosError` at `0x18000f74a`

## pseudocode

```c
ULONG __fastcall ClfsFindLsnInBlock(
        const union _CLS_LSN *a1,
        unsigned __int8 *a2,
        struct _CLFS_RECORD_HEADER **a3,
        union _CLS_LSN *a4)
{
  ULONG v8; // eax
  CLFS_RECORD_INDEX v9; // r10d
  ULONG v10; // r11d
  __int64 v11; // r10
  __int64 v12; // rdx
  NTSTATUS v13; // ecx
  unsigned int v15; // r8d
  unsigned __int8 *v16; // rdx
  unsigned int v17; // r9d
  NTSTATUS v18; // ecx

  v8 = RtlNtStatusToDosError(-1073741275);
  *a3 = 0;
  v9 = -1;
  v10 = v8;
  *a4 = CLFS_LSN_INVALID;
  if ( a1 )
    v9 = a1->offset.idxRecord & 0x1FF;
  v11 = v9 / 0x1F;
  if ( (unsigned int)v11 >= 0x10 )
    v11 = 15;
  v12 = *(unsigned int *)&a2[4 * v11 + 40];
  if ( !(_DWORD)v12 )
  {
    v13 = -1073741275;
    return RtlNtStatusToDosError(v13);
  }
  v15 = *((unsigned __int16 *)a2 + 2) << 9;
  if ( (unsigned int)v12 > v15 )
  {
    v13 = -1072037878;
    return RtlNtStatusToDosError(v13);
  }
  v16 = &a2[v12];
  if ( v16 )
  {
    while ( (*(_DWORD *)v16 & 0x1FF) != 0x1FF )
    {
      if ( (v16[36] & 0x3F) == 0 )
        break;
      if ( (v16[36] & 0xC0) != 0 )
        break;
      if ( *((_WORD *)v16 + 17) < 0x28u )
        break;
      v17 = *((_DWORD *)v16 + 6);
      if ( *((unsigned __int16 *)v16 + 17) > v17 || (unsigned __int64)&v16[v17 - (_QWORD)a2] > v15 )
        break;
      if ( !a1 || a1->ullOffset <= *(_QWORD *)v16 )
      {
        v18 = 0;
        *a4 = *(union _CLS_LSN *)v16;
        *a3 = (struct _CLFS_RECORD_HEADER *)v16;
        return RtlNtStatusToDosError(v18);
      }
      if ( (v16[36] & 0x20) != 0 )
      {
        v18 = -1073741275;
        return RtlNtStatusToDosError(v18);
      }
      v16 += (v17 + 7) & 0xFFFFFFF8;
      if ( !v16 )
        return v10;
    }
    v18 = -1072037878;
    return RtlNtStatusToDosError(v18);
  }
  return v10;
}

```

## disassembly

```asm
0x18000f60c  push    rbx
0x18000f60e  push    rsi
0x18000f60f  push    rdi
0x18000f610  push    r14
0x18000f612  sub     rsp, 28h
0x18000f616  mov     rbx, rcx
0x18000f619  mov     rsi, r9
0x18000f61c  mov     ecx, 0C0000225h; Status
0x18000f621  mov     r14, r8
0x18000f624  mov     rdi, rdx
0x18000f627  call    cs:__imp_RtlNtStatusToDosError
0x18000f62e  nop     dword ptr [rax+rax+00h]
0x18000f633  mov     qword ptr [r14], 0
0x18000f63a  or      r10d, 0FFFFFFFFh
0x18000f63e  mov     r11d, eax
0x18000f641  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000f648  mov     [rsi], rax
0x18000f64b  test    rbx, rbx
0x18000f64e  jz      short loc_18000F65A
0x18000f650  mov     r10d, [rbx]
0x18000f653  and     r10d, 1FFh
0x18000f65a  mov     eax, 8421085h
0x18000f65f  mul     r10d
0x18000f662  mov     eax, 0Fh
0x18000f667  sub     r10d, edx
0x18000f66a  shr     r10d, 1
0x18000f66d  add     r10d, edx
0x18000f670  shr     r10d, 4
0x18000f674  cmp     r10d, 10h
0x18000f678  cmovnb  r10d, eax
0x18000f67c  mov     edx, [rdi+r10*4+28h]
0x18000f681  test    edx, edx
0x18000f683  jnz     short loc_18000F69B
0x18000f685  mov     ecx, 0C0000225h; Status
0x18000f68a  call    cs:__imp_RtlNtStatusToDosError
0x18000f691  nop     dword ptr [rax+rax+00h]
0x18000f696  jmp     loc_18000F75C
0x18000f69b  movzx   r8d, word ptr [rdi+4]
0x18000f6a0  shl     r8d, 9
0x18000f6a4  cmp     edx, r8d
0x18000f6a7  jbe     short loc_18000F6B0
0x18000f6a9  mov     ecx, 0C01A000Ah
0x18000f6ae  jmp     short loc_18000F68A
0x18000f6b0  add     rdx, rdi
0x18000f6b3  jz      loc_18000F759
0x18000f6b9  mov     r10d, [rdx]
0x18000f6bc  mov     eax, r10d
0x18000f6bf  and     eax, 1FFh
0x18000f6c4  cmp     eax, 1FFh
0x18000f6c9  jnb     short loc_18000F745
0x18000f6cb  test    byte ptr [rdx+24h], 3Fh
0x18000f6cf  jz      short loc_18000F745
0x18000f6d1  test    byte ptr [rdx+24h], 0C0h
0x18000f6d5  jnz     short loc_18000F745
0x18000f6d7  cmp     word ptr [rdx+22h], 28h ; '('
0x18000f6dc  jb      short loc_18000F745
0x18000f6de  mov     r9d, [rdx+18h]
0x18000f6e2  movzx   eax, word ptr [rdx+22h]
0x18000f6e6  cmp     eax, r9d
0x18000f6e9  ja      short loc_18000F745
0x18000f6eb  mov     eax, r9d
0x18000f6ee  sub     rax, rdi
0x18000f6f1  add     rax, rdx
0x18000f6f4  mov     rcx, rax
0x18000f6f7  shr     rcx, 20h
0x18000f6fb  test    ecx, ecx
0x18000f6fd  jnz     short loc_18000F745
0x18000f6ff  cmp     eax, r8d
0x18000f702  ja      short loc_18000F745
0x18000f704  test    rbx, rbx
0x18000f707  jz      short loc_18000F738
0x18000f709  mov     eax, [rbx+4]
0x18000f70c  cmp     eax, [rdx+4]
0x18000f70f  jb      short loc_18000F738
0x18000f711  jnz     short loc_18000F718
0x18000f713  cmp     [rbx], r10d
0x18000f716  jbe     short loc_18000F738
0x18000f718  test    byte ptr [rdx+24h], 20h
0x18000f71c  jnz     short loc_18000F731
0x18000f71e  lea     eax, [r9+7]
0x18000f722  mov     ecx, 0FFFFFFF8h
0x18000f727  and     rax, rcx
0x18000f72a  add     rdx, rax
0x18000f72d  jnz     short loc_18000F6B9
0x18000f72f  jmp     short loc_18000F759
0x18000f731  mov     ecx, 0C0000225h
0x18000f736  jmp     short loc_18000F74A
0x18000f738  mov     rax, [rdx]
0x18000f73b  xor     ecx, ecx
0x18000f73d  mov     [rsi], rax
0x18000f740  mov     [r14], rdx
0x18000f743  jmp     short loc_18000F74A
0x18000f745  mov     ecx, 0C01A000Ah; Status
0x18000f74a  call    cs:__imp_RtlNtStatusToDosError
0x18000f751  nop     dword ptr [rax+rax+00h]
0x18000f756  mov     r11d, eax
0x18000f759  mov     eax, r11d
0x18000f75c  add     rsp, 28h
0x18000f760  pop     r14
0x18000f762  pop     rdi
0x18000f763  pop     rsi
0x18000f764  pop     rbx
0x18000f765  retn
```

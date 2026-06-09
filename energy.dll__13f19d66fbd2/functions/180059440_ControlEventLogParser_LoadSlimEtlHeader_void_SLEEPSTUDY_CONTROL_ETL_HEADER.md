# ControlEventLogParser::LoadSlimEtlHeader(void *,_SLEEPSTUDY_CONTROL_ETL_HEADER *)

- ea: `0x180059440`
- end: `0x18005950c`
- name: `?LoadSlimEtlHeader@ControlEventLogParser@@AEAAKPEAXPEAU_SLEEPSTUDY_CONTROL_ETL_HEADER@@@Z`
- size: `204`
- prototype: `unsigned int(ControlEventLogParser *__hidden this, void *, struct _SLEEPSTUDY_CONTROL_ETL_HEADER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800597b8`

## callees

- `0x180059440`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180059468`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180059468`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180059498`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180059498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059473`

## pseudocode

```c
DWORD __fastcall ControlEventLogParser::LoadSlimEtlHeader(
        ControlEventLogParser *this,
        void *a2,
        struct _SLEEPSTUDY_CONTROL_ETL_HEADER *a3)
{
  unsigned int v6; // r8d
  _DWORD *v7; // rdx
  unsigned int v8; // r10d
  unsigned int v9; // r9d
  int v10; // ecx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF
  int v12; // [rsp+44h] [rbp+Ch]

  v12 = HIDWORD(this);
  NumberOfBytesRead = 0;
  if ( SetFilePointer(a2, 0, 0, 0) == -1 )
    return GetLastError();
  if ( ReadFile(a2, a3, 0x18u, &NumberOfBytesRead, 0) )
  {
    v6 = *((_DWORD *)a3 + 4);
    v7 = (_DWORD *)((char *)a3 + 8);
    v8 = *((_DWORD *)a3 + 5);
    v9 = *((_DWORD *)a3 + 3);
    v10 = *((_DWORD *)a3 + 2);
    if ( v10 == ~(*(_DWORD *)a3 + *((_DWORD *)a3 + 1) + v9 + v8 + v6)
      && *(_DWORD *)a3 == 1380995935
      && *((_DWORD *)a3 + 1) == 1
      && v8 - 0x100000 <= 0x3F00000
      && v9 <= v6
      && v6 - v9 <= v8
      && v9 < v8 )
    {
      *v7 = v10;
      return 0;
    }
    *v7 = v10;
  }
  return 13;
}

```

## disassembly

```asm
0x180059440  mov     [rsp+arg_8], rbx
0x180059445  mov     qword ptr [rsp+NumberOfBytesRead], rcx
0x18005944a  push    rdi
0x18005944b  sub     rsp, 30h
0x18005944f  mov     rdi, rdx
0x180059452  mov     [rsp+38h+NumberOfBytesRead], 0
0x18005945a  mov     rbx, r8
0x18005945d  mov     rcx, rdi; hFile
0x180059460  xor     r9d, r9d; dwMoveMethod
0x180059463  xor     r8d, r8d; lpDistanceToMoveHigh
0x180059466  xor     edx, edx; lDistanceToMove
0x180059468  call    cs:__imp_SetFilePointer
0x18005946e  cmp     eax, 0FFFFFFFFh
0x180059471  jnz     short loc_18005947E
0x180059473  call    cs:__imp_GetLastError
0x180059479  jmp     loc_180059501
0x18005947e  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180059483  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18005948c  mov     r8d, 18h; nNumberOfBytesToRead
0x180059492  mov     rdx, rbx; lpBuffer
0x180059495  mov     rcx, rdi; hFile
0x180059498  call    cs:__imp_ReadFile
0x18005949e  test    eax, eax
0x1800594a0  jz      short loc_1800594FC
0x1800594a2  mov     r8d, [rbx+10h]
0x1800594a6  lea     rdx, [rbx+8]
0x1800594aa  mov     r10d, [rbx+14h]
0x1800594ae  mov     r9d, [rbx+0Ch]
0x1800594b2  mov     ecx, [rdx]
0x1800594b4  lea     eax, [r10+r8]
0x1800594b8  add     eax, r9d
0x1800594bb  add     eax, [rbx+4]
0x1800594be  add     eax, [rbx]
0x1800594c0  not     eax
0x1800594c2  cmp     ecx, eax
0x1800594c4  jnz     short loc_1800594FA
0x1800594c6  cmp     dword ptr [rbx], 5250535Fh
0x1800594cc  jnz     short loc_1800594FA
0x1800594ce  cmp     dword ptr [rbx+4], 1
0x1800594d2  jnz     short loc_1800594FA
0x1800594d4  lea     eax, [r10-100000h]
0x1800594db  cmp     eax, 3F00000h
0x1800594e0  ja      short loc_1800594FA
0x1800594e2  cmp     r9d, r8d
0x1800594e5  ja      short loc_1800594FA
0x1800594e7  sub     r8d, r9d
0x1800594ea  cmp     r8d, r10d
0x1800594ed  ja      short loc_1800594FA
0x1800594ef  cmp     r9d, r10d
0x1800594f2  jnb     short loc_1800594FA
0x1800594f4  mov     [rdx], ecx
0x1800594f6  xor     eax, eax
0x1800594f8  jmp     short loc_180059501
0x1800594fa  mov     [rdx], ecx
0x1800594fc  mov     eax, 0Dh
0x180059501  mov     rbx, [rsp+38h+arg_8]
0x180059506  add     rsp, 30h
0x18005950a  pop     rdi
0x18005950b  retn
```

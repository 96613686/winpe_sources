# PEDecoder::CheckILOnlyImportDlls(void)

- ea: `0x18003d87c`
- end: `0x18003da21`
- name: `?CheckILOnlyImportDlls@PEDecoder@@AEBA?AVCHECK@@XZ`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d4a0`

## callees

- `0x180029a84`
- `0x18002a7f4`
- `0x180039e3c`
- `0x18003d370`
- `0x18003d794`
- `0x18003d87c`
- `0x18003dd8c`
- `0x18003e0e0`

## string_xrefs

- `0x18003d9b7`: `mscoree.dll`

## pseudocode

```c
_QWORD *__fastcall PEDecoder::CheckILOnlyImportDlls(PEDecoder *a1, _QWORD *a2)
{
  struct _IMAGE_DATA_DIRECTORY *DirectoryEntry; // rax
  unsigned int *RvaData; // rax
  unsigned int *v6; // rbx
  const char *v7; // rax
  unsigned int v8; // r8d
  const unsigned __int16 *v9; // r9
  char v11; // [rsp+50h] [rbp+8h] BYREF

  *a2 = ((*((_BYTE *)a1 + 12) & 1) == 0 || (unsigned int)PEDecoder::HasDirectoryEntry(a1, 1))
     && (!(unsigned int)PEDecoder::HasDirectoryEntry(a1, 1)
      || *(_QWORD *)PEDecoder::CheckDirectoryEntry(a1, &v11, 1, 0x80000000LL)
      || (DirectoryEntry = PEDecoder::GetDirectoryEntry(a1, 1)) == 0
      || DirectoryEntry->Size < 0x28
      || (RvaData = (unsigned int *)PEDecoder::GetRvaData(a1, DirectoryEntry->VirtualAddress), (v6 = RvaData) == 0)
      || !*RvaData
      || RvaData[1]
      || ((RvaData[2] + 1) & 0xFFFFFFFE) != 0
      || !RvaData[3]
      || !RvaData[4]
      || RvaData[5]
      || RvaData[6]
      || RvaData[7]
      || RvaData[8]
      || RvaData[9]
      || *(_QWORD *)PEDecoder::CheckRva(a1, &v11, RvaData[3], 12)
      || (v7 = (const char *)PEDecoder::GetRvaData(a1, v6[3]),
          (unsigned int)SString::CaseCompareHelperA(v7, "mscoree.dll", v8, v9, 0, 0))
      || *(_QWORD *)PEDecoder::CheckILOnlyImportByNameTable(a1, &v11, *v6)
      || *(_QWORD *)PEDecoder::CheckRva(a1, &v11, v6[4], 8));
  return a2;
}

```

## disassembly

```asm
0x18003d87c  mov     [rsp+arg_8], rbx
0x18003d881  mov     [rsp+arg_10], rsi
0x18003d886  push    rdi
0x18003d887  push    r14
0x18003d889  push    r15
0x18003d88b  sub     rsp, 30h
0x18003d88f  xor     r14d, r14d
0x18003d892  mov     rsi, rdx
0x18003d895  mov     rdi, rcx
0x18003d898  lea     r15d, [r14+1]
0x18003d89c  test    [rcx+0Ch], r15b
0x18003d8a0  jz      short loc_18003D8B2
0x18003d8a2  mov     edx, r15d; int
0x18003d8a5  call    ?HasDirectoryEntry@PEDecoder@@QEBAHH@Z; PEDecoder::HasDirectoryEntry(int)
0x18003d8aa  test    eax, eax
0x18003d8ac  jz      loc_18003DA02
0x18003d8b2  mov     edx, r15d; int
0x18003d8b5  mov     rcx, rdi; this
0x18003d8b8  call    ?HasDirectoryEntry@PEDecoder@@QEBAHH@Z; PEDecoder::HasDirectoryEntry(int)
0x18003d8bd  test    eax, eax
0x18003d8bf  jz      loc_18003DA07
0x18003d8c5  mov     r9d, 80000000h
0x18003d8cb  lea     rdx, [rsp+48h+arg_0]
0x18003d8d0  mov     r8d, r15d
0x18003d8d3  mov     rcx, rdi
0x18003d8d6  call    ?CheckDirectoryEntry@PEDecoder@@QEBA?AVCHECK@@HHW4IsNullOK@@@Z; PEDecoder::CheckDirectoryEntry(int,int,IsNullOK)
0x18003d8db  cmp     [rax], r14
0x18003d8de  jnz     loc_18003DA07
0x18003d8e4  mov     edx, r15d; int
0x18003d8e7  mov     rcx, rdi; this
0x18003d8ea  call    ?GetDirectoryEntry@PEDecoder@@QEBAPEAU_IMAGE_DATA_DIRECTORY@@H@Z; PEDecoder::GetDirectoryEntry(int)
0x18003d8ef  test    rax, rax
0x18003d8f2  jz      loc_18003DA07
0x18003d8f8  cmp     dword ptr [rax+4], 28h ; '('
0x18003d8fc  jb      loc_18003DA07
0x18003d902  mov     edx, [rax]
0x18003d904  mov     rcx, rdi
0x18003d907  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x18003d90c  mov     rbx, rax
0x18003d90f  test    rax, rax
0x18003d912  jz      loc_18003DA07
0x18003d918  cmp     [rax], r14d
0x18003d91b  jz      loc_18003DA07
0x18003d921  cmp     [rax+4], r14d
0x18003d925  jnz     loc_18003DA07
0x18003d92b  mov     ecx, [rax+8]
0x18003d92e  add     ecx, r15d
0x18003d931  test    ecx, 0FFFFFFFEh
0x18003d937  jnz     loc_18003DA07
0x18003d93d  cmp     [rax+0Ch], r14d
0x18003d941  jz      loc_18003DA07
0x18003d947  cmp     [rax+10h], r14d
0x18003d94b  jz      loc_18003DA07
0x18003d951  cmp     [rax+14h], r14d
0x18003d955  jnz     loc_18003DA07
0x18003d95b  cmp     [rax+18h], r14d
0x18003d95f  jnz     loc_18003DA07
0x18003d965  cmp     [rax+1Ch], r14d
0x18003d969  jnz     loc_18003DA07
0x18003d96f  cmp     [rax+20h], r14d
0x18003d973  jnz     loc_18003DA07
0x18003d979  cmp     [rax+24h], r14d
0x18003d97d  jnz     loc_18003DA07
0x18003d983  mov     r8d, [rax+0Ch]
0x18003d987  lea     rdx, [rsp+48h+arg_0]
0x18003d98c  mov     [rsp+48h+var_20], r14d; int
0x18003d991  mov     r9d, 0Ch
0x18003d997  mov     rcx, rdi
0x18003d99a  mov     [rsp+48h+var_28], r14d; int
0x18003d99f  call    ?CheckRva@PEDecoder@@QEBA?AVCHECK@@KIHW4IsNullOK@@@Z; PEDecoder::CheckRva(ulong,uint,int,IsNullOK)
0x18003d9a4  cmp     [rax], r14
0x18003d9a7  jnz     short loc_18003DA07
0x18003d9a9  mov     edx, [rbx+0Ch]
0x18003d9ac  mov     rcx, rdi
0x18003d9af  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x18003d9b4  mov     rcx, rax; char *
0x18003d9b7  lea     rdx, aMscoreeDll_1; "mscoree.dll"
0x18003d9be  call    ?CaseCompareHelperA@SString@@CAHPEBD0IPEBGHH@Z; SString::CaseCompareHelperA(char const *,char const *,uint,ushort const *,int,int)
0x18003d9c3  test    eax, eax
0x18003d9c5  jnz     short loc_18003DA07
0x18003d9c7  mov     r8d, [rbx]
0x18003d9ca  lea     rdx, [rsp+48h+arg_0]
0x18003d9cf  mov     rcx, rdi
0x18003d9d2  call    ?CheckILOnlyImportByNameTable@PEDecoder@@AEBA?AVCHECK@@K@Z; PEDecoder::CheckILOnlyImportByNameTable(ulong)
0x18003d9d7  cmp     [rax], r14
0x18003d9da  jnz     short loc_18003DA07
0x18003d9dc  mov     r8d, [rbx+10h]
0x18003d9e0  lea     rdx, [rsp+48h+arg_0]
0x18003d9e5  mov     [rsp+48h+var_20], r14d
0x18003d9ea  mov     r9d, 8
0x18003d9f0  mov     rcx, rdi
0x18003d9f3  mov     [rsp+48h+var_28], r14d
0x18003d9f8  call    ?CheckRva@PEDecoder@@QEBA?AVCHECK@@KIHW4IsNullOK@@@Z; PEDecoder::CheckRva(ulong,uint,int,IsNullOK)
0x18003d9fd  cmp     [rax], r14
0x18003da00  jnz     short loc_18003DA07
0x18003da02  mov     [rsi], r14
0x18003da05  jmp     short loc_18003DA0A
0x18003da07  mov     [rsi], r15
0x18003da0a  mov     rbx, [rsp+48h+arg_8]
0x18003da0f  mov     rax, rsi
0x18003da12  mov     rsi, [rsp+48h+arg_10]
0x18003da17  add     rsp, 30h
0x18003da1b  pop     r15
0x18003da1d  pop     r14
0x18003da1f  pop     rdi
0x18003da20  retn
```

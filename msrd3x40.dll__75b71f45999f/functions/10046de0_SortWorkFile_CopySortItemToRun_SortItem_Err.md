# SortWorkFile::CopySortItemToRun(SortItem *,Err &)

- ea: `0x10046de0`
- end: `0x10046f2d`
- name: `?CopySortItemToRun@SortWorkFile@@QAEXPAVSortItem@@AAVErr@@@Z`
- size: `333`
- prototype: `void __thiscall(SortWorkFile *__hidden this, struct SortItem *Src, struct Err *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x10045640`
- `0x10046080`

## callees

- `0x1000eb60`
- `0x10024b00`
- `0x10042d20`
- `0x10046de0`
- `0x100481d0`
- `0x1005f07c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10046e45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10046e45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10046e76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10046e76`

## pseudocode

```c
void __thiscall SortWorkFile::CopySortItemToRun(SortWorkFile *this, struct SortItem *Src, void **a3)
{
  struct SortItem *v3; // edi
  unsigned __int16 *v5; // esi
  int v6; // esi
  PageDesc *v7; // ecx
  int v8; // eax
  int v9; // edx
  unsigned int v10; // eax
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [esp+Ch] [ebp-Ch]
  struct Transaction *v12; // [esp+10h] [ebp-8h]
  int v13; // [esp+14h] [ebp-4h]

  v3 = Src;
  v5 = (unsigned __int16 *)((char *)Src + 2);
  if ( *(unsigned __int16 *)Src + 4 + (unsigned int)*((unsigned __int16 *)Src + 1) <= *((_DWORD *)this + 37) )
    goto LABEL_8;
  v13 = (*(int (__thiscall **)(_DWORD, char *, void **))(**((_DWORD **)this + 2) + 4))(
          *((_DWORD *)this + 2),
          (char *)this + 16,
          a3);
  if ( (*(_BYTE *)a3 & 8) == 0 )
  {
    v6 = *((_DWORD *)this + 2);
    v12 = (struct Transaction *)*((_DWORD *)this + 3);
    lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(v6 + 112);
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 112));
    v7 = Database::FindOrCreate((Database *)v6, v13, a3);
    if ( (*(_BYTE *)a3 & 8) == 0 )
      PageDesc::DontReadPage(v7, (SortWorkFile *)((char *)this + 136), v12, (struct Err *)a3);
    v5 = (unsigned __int16 *)((char *)Src + 2);
    LeaveCriticalSection(lpCriticalSection);
    if ( (*(_BYTE *)a3 & 8) == 0 )
    {
      **((_WORD **)this + 35) = 263;
      *(_WORD *)(*((_DWORD *)this + 35) + 2) = 0;
      v8 = *((_DWORD *)this + 35) + 4;
      *((_DWORD *)this + 37) = 2044;
      *((_DWORD *)this + 38) = v8;
      *((_WORD *)this + 78) = 0;
      v9 = *((_DWORD *)this + 34);
      *(_DWORD *)(v9 + 4 * *(_DWORD *)(v9 + 24) + 28) |= 8u;
      ++*(_DWORD *)(v9 + 64);
      AbstractSpacemap::AddPage(v13, a3, (char *)this + 140);
      if ( (*(_BYTE *)a3 & 8) == 0 )
      {
        v3 = Src;
LABEL_8:
        memcpy(*((void **)this + 38), v3, *v5 + 4 + *(unsigned __int16 *)v3);
        v10 = (*v5 + *(unsigned __int16 *)v3 + 5) & 0xFFFFFFFE;
        *((_DWORD *)this + 38) += v10;
        *((_DWORD *)this + 37) -= v10;
        ++*(_WORD *)(*((_DWORD *)this + 35) + 2);
      }
    }
  }
}

```

## disassembly

```asm
0x10046de0  mov     edi, edi
0x10046de2  push    ebp
0x10046de3  mov     ebp, esp
0x10046de5  sub     esp, 0Ch
0x10046de8  push    ebx
0x10046de9  push    esi
0x10046dea  push    edi
0x10046deb  mov     edi, [ebp+Src]
0x10046dee  mov     ebx, ecx
0x10046df0  movzx   eax, word ptr [edi+2]
0x10046df4  lea     esi, [edi+2]
0x10046df7  movzx   ecx, word ptr [edi]
0x10046dfa  add     ecx, 4
0x10046dfd  add     eax, ecx
0x10046dff  cmp     eax, [ebx+94h]
0x10046e05  jbe     loc_10046EE5
0x10046e0b  mov     edi, [ebx+8]
0x10046e0e  push    [ebp+arg_4]; unsigned int
0x10046e11  mov     eax, [edi]
0x10046e13  mov     esi, [eax+4]
0x10046e16  lea     eax, [ebx+10h]
0x10046e19  push    eax; void *
0x10046e1a  mov     ecx, esi
0x10046e1c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10046e22  mov     ecx, edi
0x10046e24  call    esi
0x10046e26  mov     edi, [ebp+arg_4]
0x10046e29  mov     [ebp+var_4], eax
0x10046e2c  test    byte ptr [edi], 8
0x10046e2f  jnz     loc_10046F24
0x10046e35  mov     esi, [ebx+8]
0x10046e38  mov     eax, [ebx+0Ch]
0x10046e3b  mov     [ebp+var_8], eax
0x10046e3e  lea     eax, [esi+70h]
0x10046e41  push    eax; lpCriticalSection
0x10046e42  mov     [ebp+lpCriticalSection], eax
0x10046e45  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10046e4b  push    edi; struct Err *
0x10046e4c  push    [ebp+var_4]; unsigned int
0x10046e4f  mov     ecx, esi; this
0x10046e51  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x10046e56  test    byte ptr [edi], 8
0x10046e59  mov     ecx, eax; this
0x10046e5b  jnz     short loc_10046E6D
0x10046e5d  push    edi; struct Err *
0x10046e5e  push    [ebp+var_8]; struct Transaction *
0x10046e61  lea     eax, [ebx+88h]
0x10046e67  push    eax; struct PageRef *
0x10046e68  call    ?DontReadPage@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@AAVErr@@@Z; PageDesc::DontReadPage(PageRef &,Transaction *,Err &)
0x10046e6d  mov     esi, [ebp+Src]
0x10046e70  push    [ebp+lpCriticalSection]; lpCriticalSection
0x10046e73  add     esi, 2
0x10046e76  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10046e7c  test    byte ptr [edi], 8
0x10046e7f  jnz     loc_10046F24
0x10046e85  mov     eax, [ebx+8Ch]
0x10046e8b  lea     ecx, [ebx+8Ch]
0x10046e91  mov     edx, 107h
0x10046e96  push    ecx
0x10046e97  push    edi
0x10046e98  mov     [eax], dx
0x10046e9b  xor     edx, edx
0x10046e9d  mov     eax, [ecx]
0x10046e9f  push    [ebp+var_4]
0x10046ea2  mov     [eax+2], dx
0x10046ea6  mov     eax, [ecx]
0x10046ea8  lea     ecx, [ebx+10h]
0x10046eab  add     eax, 4
0x10046eae  mov     dword ptr [ebx+94h], 7FCh
0x10046eb8  mov     [ebx+98h], eax
0x10046ebe  xor     eax, eax
0x10046ec0  mov     [ebx+9Ch], ax
0x10046ec7  mov     edx, [ebx+88h]
0x10046ecd  mov     eax, [edx+18h]
0x10046ed0  or      dword ptr [edx+eax*4+1Ch], 8
0x10046ed5  inc     dword ptr [edx+40h]
0x10046ed8  call    ?AddPage@AbstractSpacemap@@QAEXKAAVErr@@W4SMAssertAction@@@Z; AbstractSpacemap::AddPage(ulong,Err &,SMAssertAction)
0x10046edd  test    byte ptr [edi], 8
0x10046ee0  jnz     short loc_10046F24
0x10046ee2  mov     edi, [ebp+Src]
0x10046ee5  movzx   ecx, word ptr [esi]
0x10046ee8  movzx   eax, word ptr [edi]
0x10046eeb  add     ecx, 4
0x10046eee  add     eax, ecx
0x10046ef0  push    eax; Size
0x10046ef1  push    edi; Src
0x10046ef2  push    dword ptr [ebx+98h]; void *
0x10046ef8  call    _memcpy
0x10046efd  movzx   eax, word ptr [edi]
0x10046f00  add     esp, 0Ch
0x10046f03  movzx   ecx, word ptr [esi]
0x10046f06  add     eax, 5
0x10046f09  add     eax, ecx
0x10046f0b  and     eax, 0FFFFFFFEh
0x10046f0e  add     [ebx+98h], eax
0x10046f14  sub     [ebx+94h], eax
0x10046f1a  mov     eax, [ebx+8Ch]
0x10046f20  inc     word ptr [eax+2]
0x10046f24  pop     edi
0x10046f25  pop     esi
0x10046f26  pop     ebx
0x10046f27  mov     esp, ebp
0x10046f29  pop     ebp
0x10046f2a  retn    8
```

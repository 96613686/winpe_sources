# PageDesc::ReadPage(PageRef &,Transaction *,uint,Err &)

- ea: `0x100429a0`
- end: `0x10042ad8`
- name: `?ReadPage@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@IAAVErr@@@Z`
- size: `312`
- prototype: `void __thiscall(PageDesc *__hidden this, struct PageRef *, struct Transaction *, char, struct Err *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x10023690`
- `0x10042ae0`

## callees

- `0x10012e50`
- `0x10025ee0`
- `0x10041e80`
- `0x10042130`
- `0x100422a0`
- `0x100429a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100429ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100429ab`

## pseudocode

```c
void __thiscall PageDesc::ReadPage(PageDesc *this, struct PageRef *a2, struct Transaction *a3, char a4, struct Err *a5)
{
  DWORD TickCount; // eax
  char v7; // bl
  struct Err *v8; // edi
  struct Transaction *v9; // ecx
  int v10; // eax
  unsigned int v11; // edx
  int v12; // eax
  int v13; // eax
  bool v14; // zf
  struct PageVersion *v15; // eax
  int v16; // ecx
  int v17; // eax
  Collection *v18; // [esp+Ch] [ebp-4h]
  Collection *v19; // [esp+Ch] [ebp-4h]

  TickCount = GetTickCount();
  v7 = a4;
  v8 = a5;
  v9 = a3;
  *((_DWORD *)this + 18) = TickCount;
  if ( (a4 & 0x10) != 0 )
  {
    v7 = a4 & 0xEF;
    if ( *(int *)a3 <= 0 )
    {
      if ( (*((_BYTE *)this + 82) & 1) == 0 )
      {
        Err::SetError(a5, -1054, a3);
        return;
      }
    }
    else
    {
      v10 = 0;
      v18 = (struct Transaction *)((char *)a3 + 24);
      v11 = *((_DWORD *)a3 + 8);
      if ( v11 )
      {
        while ( 1 )
        {
          v8 = a5;
          v9 = a3;
          if ( *(PageDesc **)(*(_DWORD *)v18 + 4 * v10) == this )
            break;
          if ( ++v10 >= v11 )
            goto LABEL_6;
        }
      }
      else
      {
LABEL_6:
        if ( v10 == v11 )
        {
          PageDesc::IncrementLock(this, 0x10u, v9, v8);
          if ( (*(_BYTE *)v8 & 8) != 0 )
            return;
          Collection::AddObject(v18, this, v8);
          if ( (*(_BYTE *)v8 & 8) != 0 )
          {
            PageDesc::DecrementLock(this, a3, v8, 0);
            return;
          }
          v9 = a3;
        }
      }
    }
  }
  v12 = *((_DWORD *)this + 6);
  if ( v12 && v9 == *((struct Transaction **)this + 15) )
  {
    v13 = v12 + 7;
    v14 = (*((_BYTE *)this + 4 * v13) & 7) == 0;
    v15 = (PageDesc *)((char *)this + 4 * v13);
    v19 = v15;
    if ( !v14 )
    {
      PageDesc::WireCurrentPage(this, v15, v7, v8);
      if ( (*(_BYTE *)v8 & 8) != 0 )
        return;
      v15 = v19;
    }
  }
  else
  {
    v16 = *((_DWORD *)this + 7);
    v15 = (PageDesc *)((char *)this + 28);
    if ( (v16 & 7) != 0 || (v7 & 4) != 0 && (v16 & 8) == 0 )
    {
      PageDesc::WireCurrentPage(this, (PageDesc *)((char *)this + 28), v7, v8);
      if ( (*(_BYTE *)v8 & 8) != 0 )
        return;
      v15 = (PageDesc *)((char *)this + 28);
    }
  }
  *((_DWORD *)a2 + 1) = *(_DWORD *)v15 & 0xFFFFFF00;
  v17 = *(_DWORD *)a2;
  if ( *(PageDesc **)a2 != this )
  {
    if ( v17 )
      --*(_WORD *)(v17 + 76);
    *(_DWORD *)a2 = this;
    ++*((_WORD *)this + 38);
    *((_DWORD *)a2 + 2) = 0;
  }
}

```

## disassembly

```asm
0x100429a0  mov     edi, edi
0x100429a2  push    ebp
0x100429a3  mov     ebp, esp
0x100429a5  push    ecx
0x100429a6  push    ebx
0x100429a7  push    esi
0x100429a8  push    edi
0x100429a9  mov     esi, ecx
0x100429ab  call    ds:__imp__GetTickCount@0; GetTickCount()
0x100429b1  mov     ebx, dword ptr [ebp+arg_8]
0x100429b4  mov     edi, [ebp+arg_C]
0x100429b7  mov     ecx, [ebp+arg_4]
0x100429ba  mov     [esi+48h], eax
0x100429bd  test    bl, 10h
0x100429c0  jz      loc_10042A51
0x100429c6  and     ebx, 0FFFFFFEFh
0x100429c9  cmp     dword ptr [ecx], 0
0x100429cc  jle     short loc_10042A32
0x100429ce  lea     edx, [ecx+18h]
0x100429d1  xor     eax, eax
0x100429d3  mov     [ebp+var_4], edx
0x100429d6  mov     edx, [edx+8]
0x100429d9  test    edx, edx
0x100429db  jz      short loc_100429F5
0x100429dd  nop     dword ptr [eax]
0x100429e0  mov     edi, [ebp+var_4]
0x100429e3  mov     ecx, [edi]
0x100429e5  mov     edi, [ebp+arg_C]
0x100429e8  cmp     [ecx+eax*4], esi
0x100429eb  mov     ecx, [ebp+arg_4]
0x100429ee  jz      short loc_10042A51
0x100429f0  inc     eax
0x100429f1  cmp     eax, edx
0x100429f3  jb      short loc_100429E0
0x100429f5  cmp     eax, edx
0x100429f7  jnz     short loc_10042A51
0x100429f9  push    edi; struct Err *
0x100429fa  push    ecx; struct Transaction *
0x100429fb  push    10h; unsigned int
0x100429fd  mov     ecx, esi; this
0x100429ff  call    ?IncrementLock@PageDesc@@QAEXIPAVTransaction@@AAVErr@@@Z; PageDesc::IncrementLock(uint,Transaction *,Err &)
0x10042a04  test    byte ptr [edi], 8
0x10042a07  jnz     loc_10042ACF
0x10042a0d  mov     ecx, [ebp+var_4]; this
0x10042a10  push    edi; struct Err *
0x10042a11  push    esi; void *
0x10042a12  call    ?AddObject@Collection@@QAEXPBXAAVErr@@@Z; Collection::AddObject(void const *,Err &)
0x10042a17  test    byte ptr [edi], 8
0x10042a1a  jz      short loc_10042A4E
0x10042a1c  push    0
0x10042a1e  push    edi
0x10042a1f  push    [ebp+arg_4]
0x10042a22  mov     ecx, esi
0x10042a24  call    ?DecrementLock@PageDesc@@QAEXPAVTransaction@@AAVErr@@W4UnlockType@@@Z; PageDesc::DecrementLock(Transaction *,Err &,UnlockType)
0x10042a29  pop     edi
0x10042a2a  pop     esi
0x10042a2b  pop     ebx
0x10042a2c  mov     esp, ebp
0x10042a2e  pop     ebp
0x10042a2f  retn    10h
0x10042a32  test    byte ptr [esi+52h], 1
0x10042a36  jnz     short loc_10042A51
0x10042a38  push    ecx
0x10042a39  push    0FFFFFBE2h
0x10042a3e  mov     ecx, edi
0x10042a40  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10042a45  pop     edi
0x10042a46  pop     esi
0x10042a47  pop     ebx
0x10042a48  mov     esp, ebp
0x10042a4a  pop     ebp
0x10042a4b  retn    10h
0x10042a4e  mov     ecx, [ebp+arg_4]
0x10042a51  mov     eax, [esi+18h]
0x10042a54  test    eax, eax
0x10042a56  jz      short loc_10042A80
0x10042a58  cmp     ecx, [esi+3Ch]
0x10042a5b  jnz     short loc_10042A80
0x10042a5d  add     eax, 7
0x10042a60  test    byte ptr [esi+eax*4], 7
0x10042a64  lea     eax, [esi+eax*4]
0x10042a67  mov     [ebp+var_4], eax
0x10042a6a  jz      short loc_10042AA7
0x10042a6c  push    edi; struct Err *
0x10042a6d  push    ebx; char
0x10042a6e  push    eax; struct PageVersion *
0x10042a6f  mov     ecx, esi; this
0x10042a71  call    ?WireCurrentPage@PageDesc@@QAEXAAVPageVersion@@IAAVErr@@@Z; PageDesc::WireCurrentPage(PageVersion &,uint,Err &)
0x10042a76  test    byte ptr [edi], 8
0x10042a79  jnz     short loc_10042ACF
0x10042a7b  mov     eax, [ebp+var_4]
0x10042a7e  jmp     short loc_10042AA7
0x10042a80  mov     ecx, [esi+1Ch]
0x10042a83  lea     eax, [esi+1Ch]
0x10042a86  test    cl, 7
0x10042a89  jnz     short loc_10042A95
0x10042a8b  test    bl, 4
0x10042a8e  jz      short loc_10042AA7
0x10042a90  test    cl, 8
0x10042a93  jnz     short loc_10042AA7
0x10042a95  push    edi; struct Err *
0x10042a96  push    ebx; char
0x10042a97  push    eax; struct PageVersion *
0x10042a98  mov     ecx, esi; this
0x10042a9a  call    ?WireCurrentPage@PageDesc@@QAEXAAVPageVersion@@IAAVErr@@@Z; PageDesc::WireCurrentPage(PageVersion &,uint,Err &)
0x10042a9f  test    byte ptr [edi], 8
0x10042aa2  jnz     short loc_10042ACF
0x10042aa4  lea     eax, [esi+1Ch]
0x10042aa7  mov     eax, [eax]
0x10042aa9  mov     ecx, [ebp+arg_0]
0x10042aac  and     eax, 0FFFFFF00h
0x10042ab1  mov     [ecx+4], eax
0x10042ab4  mov     eax, [ecx]
0x10042ab6  cmp     eax, esi
0x10042ab8  jz      short loc_10042ACF
0x10042aba  test    eax, eax
0x10042abc  jz      short loc_10042AC2
0x10042abe  dec     word ptr [eax+4Ch]
0x10042ac2  mov     [ecx], esi
0x10042ac4  inc     word ptr [esi+4Ch]
0x10042ac8  mov     dword ptr [ecx+8], 0
0x10042acf  pop     edi
0x10042ad0  pop     esi
0x10042ad1  pop     ebx
0x10042ad2  mov     esp, ebp
0x10042ad4  pop     ebp
0x10042ad5  retn    10h
```

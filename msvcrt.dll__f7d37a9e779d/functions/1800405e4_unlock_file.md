# _unlock_file

- ea: `0x1800405e4`
- end: `0x180040632`
- name: `_unlock_file`
- size: `78`
- prototype: `void __cdecl(FILE *Stream)`
- caller_count: `37`
- callee_count: `2`
- tags: ``

## callers

- `0x18004a430`
- `0x18004aa50`
- `0x18004ac50`
- `0x18004af24`
- `0x18004b070`
- `0x18004b170`
- `0x18004b3b0`
- `0x18004b5a4`
- `0x18004b7d0`
- `0x18004c460`
- `0x18004dba0`
- `0x18004dcfc`
- `0x18004df6c`
- `0x18004e0ec`
- `0x18004ef30`
- `0x18004f1d0`
- `0x18004f2f8`
- `0x180050580`
- `0x1800506e0`
- `0x180050800`
- `0x180050980`
- `0x180050d00`
- `0x180050d80`
- `0x180050e50`
- `0x180050f80`
- `0x180051280`
- `0x180051310`
- `0x180051674`
- `0x18005171c`
- `0x180051910`
- `0x180051bc0`
- `0x180051dd0`
- `0x180052250`
- `0x180052350`
- `0x180052478`
- `0x180052d00`
- `0x180059650`

## callees

- `0x18003e8e0`
- `0x1800405e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004062b`

## pseudocode

```c
void __cdecl unlock_file(FILE *Stream)
{
  unsigned __int64 v1; // rdx

  if ( Stream < iob || Stream > (FILE *)qword_18009CD90 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)&Stream[1]);
  }
  else
  {
    Stream->_flag &= ~0x8000u;
    v1 = (__int64)((unsigned __int128)(((char *)Stream - (char *)iob) * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64) >> 3;
    unlock((unsigned int)v1 + (v1 >> 63) + 16);
  }
}

```

## disassembly

```asm
0x1800405e4  lea     rdx, _iob
0x1800405eb  cmp     rcx, rdx
0x1800405ee  jb      short loc_180040627
0x1800405f0  lea     rax, qword_18009CD90
0x1800405f7  cmp     rcx, rax
0x1800405fa  ja      short loc_180040627
0x1800405fc  btr     dword ptr [rcx+18h], 0Fh
0x180040601  mov     rax, 2AAAAAAAAAAAAAABh
0x18004060b  sub     rcx, rdx
0x18004060e  imul    rcx
0x180040611  sar     rdx, 3
0x180040615  mov     rcx, rdx
0x180040618  shr     rcx, 3Fh
0x18004061c  add     rcx, rdx
0x18004061f  add     ecx, 10h
0x180040622  jmp     _unlock
0x180040627  add     rcx, 30h ; '0'
0x18004062b  jmp     cs:__imp_LeaveCriticalSection
```

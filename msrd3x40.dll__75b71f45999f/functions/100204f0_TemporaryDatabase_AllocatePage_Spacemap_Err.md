# TemporaryDatabase::AllocatePage(Spacemap *,Err &)

- ea: `0x100204f0`
- end: `0x100206ca`
- name: `?AllocatePage@TemporaryDatabase@@UAEKPAVSpacemap@@AAVErr@@@Z`
- size: `474`
- prototype: `unsigned int __thiscall(TemporaryDatabase *__hidden this, struct Spacemap *, struct Err *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1000ffb0`
- `0x100204f0`
- `0x10025ee0`
- `0x10048c00`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f07c`
- `0x1005f180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1002054b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10020630`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1002054b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10020630`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10020569`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002064f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10020569`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002064f`

## pseudocode

```c
unsigned int __thiscall TemporaryDatabase::AllocatePage(TemporaryDatabase *this, struct Spacemap *a2, void **a3)
{
  unsigned int v4; // ebx
  unsigned int Page; // eax
  unsigned int v6; // eax
  struct _RTL_CRITICAL_SECTION *v7; // ebx
  unsigned int v9; // ecx
  unsigned int v10; // [esp+Ch] [ebp-8h]
  unsigned int v11; // [esp+Ch] [ebp-8h]
  unsigned int v12; // [esp+10h] [ebp-4h]
  char *v13; // [esp+10h] [ebp-4h]

  while ( 1 )
  {
    v4 = *((_DWORD *)this + 247);
    v10 = 0;
    if ( a2 )
    {
      if ( *((_DWORD *)a2 + 14) == 2 )
      {
        Page = AbstractSpacemap::LastPage(a2, (struct Err *)a3);
        v10 = Page;
        if ( Page )
        {
          if ( Page > v4 )
            v4 = Page;
        }
      }
    }
    if ( v4 <= *((_DWORD *)this + 246) + 8 * *((_DWORD *)this + 245) - 1 )
      break;
    v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 996);
LABEL_13:
    v9 = *((_DWORD *)this + 248);
    v11 = v9;
    if ( v9 >= 0x10000 )
    {
      if ( (int)*a3 < 8 )
      {
        if ( ((unsigned int)*a3 & 0xFFFFFFFE) != 0 )
        {
          if ( a3[3] )
            operator delete[](a3[3]);
          if ( a3[4] )
            operator delete[](a3[4]);
        }
        *a3 = (void *)8;
        a3[1] = (void *)-1812;
        a3[2] = 0;
        a3[3] = 0;
        a3[4] = 0;
      }
    }
    else if ( v9 + 0x4000 > 0x10000 || v9 + 0x4000 <= v9 )
    {
      Err::SetError(a3, -1003, v9);
    }
    else
    {
      v13 = (char *)operator new[](v9 + 0x4000);
      memcpy(v13, *((const void **)this + 243), *((_DWORD *)this + 248));
      memset(&v13[*((_DWORD *)this + 248)], -1, v11 + 0x4000 - *((_DWORD *)this + 248));
      if ( *((_DWORD *)this + 243) )
        operator delete[](*((void **)this + 243));
      *((_DWORD *)this + 243) = v13;
      *((_DWORD *)this + 248) = v11 + 0x4000;
      EnterCriticalSection(v7);
      *((_DWORD *)this + 244) = *((_DWORD *)this + 243);
      *((_DWORD *)this + 245) = *((_DWORD *)this + 248);
      LeaveCriticalSection(v7);
    }
    if ( (*(_BYTE *)a3 & 8) != 0 )
      return 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 996));
  v6 = Bitmap::Allocate((TemporaryDatabase *)((char *)this + 976), 1u, v4);
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 996);
  v12 = v6;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 996));
  if ( v12 == -1 || !v12 )
    goto LABEL_13;
  if ( !v10 )
    *((_DWORD *)this + 247) = v12 + 1;
  return v12;
}

```

## disassembly

```asm
0x100204f0  mov     edi, edi
0x100204f2  push    ebp
0x100204f3  mov     ebp, esp
0x100204f5  sub     esp, 8
0x100204f8  push    ebx
0x100204f9  push    esi
0x100204fa  mov     esi, [ebp+arg_4]
0x100204fd  push    edi
0x100204fe  mov     edi, ecx
0x10020500  mov     eax, [ebp+arg_0]
0x10020503  mov     ebx, [edi+3DCh]
0x10020509  mov     [ebp+var_8], 0
0x10020510  test    eax, eax
0x10020512  jz      short loc_10020530
0x10020514  cmp     dword ptr [eax+38h], 2
0x10020518  jnz     short loc_10020530
0x1002051a  push    esi; struct Err *
0x1002051b  mov     ecx, eax; this
0x1002051d  call    ?LastPage@AbstractSpacemap@@QAEKAAVErr@@@Z; AbstractSpacemap::LastPage(Err &)
0x10020522  mov     edx, eax
0x10020524  mov     [ebp+var_8], edx
0x10020527  test    edx, edx
0x10020529  jz      short loc_10020530
0x1002052b  cmp     edx, ebx
0x1002052d  cmova   ebx, edx
0x10020530  mov     ecx, [edi+3D4h]
0x10020536  mov     eax, [edi+3D8h]
0x1002053c  lea     eax, [eax+ecx*8]
0x1002053f  dec     eax
0x10020540  cmp     ebx, eax
0x10020542  ja      short loc_10020595
0x10020544  lea     eax, [edi+3E4h]
0x1002054a  push    eax; lpCriticalSection
0x1002054b  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10020551  push    ebx; unsigned int
0x10020552  push    1; unsigned int
0x10020554  lea     ecx, [edi+3D0h]; this
0x1002055a  call    ?Allocate@Bitmap@@QAEKKK@Z; Bitmap::Allocate(ulong,ulong)
0x1002055f  lea     ebx, [edi+3E4h]
0x10020565  mov     [ebp+var_4], eax
0x10020568  push    ebx; lpCriticalSection
0x10020569  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1002056f  mov     ecx, [ebp+var_4]
0x10020572  cmp     ecx, 0FFFFFFFFh
0x10020575  jz      short loc_1002059B
0x10020577  test    ecx, ecx
0x10020579  jz      short loc_1002059B
0x1002057b  cmp     [ebp+var_8], 0
0x1002057f  jnz     short loc_1002058A
0x10020581  lea     eax, [ecx+1]
0x10020584  mov     [edi+3DCh], eax
0x1002058a  pop     edi
0x1002058b  pop     esi
0x1002058c  mov     eax, ecx
0x1002058e  pop     ebx
0x1002058f  mov     esp, ebp
0x10020591  pop     ebp
0x10020592  retn    8
0x10020595  lea     ebx, [edi+3E4h]
0x1002059b  mov     ecx, [edi+3E0h]
0x100205a1  mov     [ebp+var_8], ecx
0x100205a4  cmp     ecx, 10000h
0x100205aa  jnb     loc_10020666
0x100205b0  lea     eax, [ecx+4000h]
0x100205b6  cmp     eax, 10000h
0x100205bb  ja      loc_10020657
0x100205c1  cmp     eax, ecx
0x100205c3  jbe     loc_10020657
0x100205c9  push    eax; unsigned int
0x100205ca  call    ??_U@YAPAXI@Z; operator new[](uint)
0x100205cf  push    dword ptr [edi+3E0h]; Size
0x100205d5  mov     [ebp+var_4], eax
0x100205d8  push    dword ptr [edi+3CCh]; Src
0x100205de  push    eax; void *
0x100205df  call    _memcpy
0x100205e4  mov     eax, [ebp+var_8]
0x100205e7  mov     ecx, [edi+3E0h]
0x100205ed  add     eax, 4000h
0x100205f2  sub     eax, ecx
0x100205f4  push    eax; Size
0x100205f5  mov     eax, [ebp+var_4]
0x100205f8  add     eax, ecx
0x100205fa  push    0FFFFFFFFh; Val
0x100205fc  push    eax; void *
0x100205fd  call    _memset
0x10020602  mov     eax, [edi+3CCh]
0x10020608  add     esp, 1Ch
0x1002060b  test    eax, eax
0x1002060d  jz      short loc_10020618
0x1002060f  push    eax; Block
0x10020610  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10020615  add     esp, 4
0x10020618  mov     eax, [ebp+var_4]
0x1002061b  mov     [edi+3CCh], eax
0x10020621  mov     eax, [ebp+var_8]
0x10020624  add     eax, 4000h
0x10020629  push    ebx; lpCriticalSection
0x1002062a  mov     [edi+3E0h], eax
0x10020630  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10020636  mov     eax, [edi+3CCh]
0x1002063c  mov     [edi+3D0h], eax
0x10020642  mov     eax, [edi+3E0h]
0x10020648  push    ebx; lpCriticalSection
0x10020649  mov     [edi+3D4h], eax
0x1002064f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10020655  jmp     short loc_100206B6
0x10020657  push    ecx
0x10020658  push    0FFFFFC15h
0x1002065d  mov     ecx, esi
0x1002065f  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10020664  jmp     short loc_100206B6
0x10020666  mov     eax, [esi]
0x10020668  cmp     eax, 8
0x1002066b  jge     short loc_100206B6
0x1002066d  test    eax, 0FFFFFFFEh
0x10020672  jz      short loc_10020694
0x10020674  mov     eax, [esi+0Ch]
0x10020677  test    eax, eax
0x10020679  jz      short loc_10020684
0x1002067b  push    eax; Block
0x1002067c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10020681  add     esp, 4
0x10020684  mov     eax, [esi+10h]
0x10020687  test    eax, eax
0x10020689  jz      short loc_10020694
0x1002068b  push    eax; Block
0x1002068c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10020691  add     esp, 4
0x10020694  mov     dword ptr [esi], 8
0x1002069a  mov     dword ptr [esi+4], 0FFFFF8ECh
0x100206a1  mov     dword ptr [esi+8], 0
0x100206a8  mov     dword ptr [esi+0Ch], 0
0x100206af  mov     dword ptr [esi+10h], 0
0x100206b6  test    byte ptr [esi], 8
0x100206b9  jz      loc_10020500
0x100206bf  pop     edi
0x100206c0  pop     esi
0x100206c1  xor     eax, eax
0x100206c3  pop     ebx
0x100206c4  mov     esp, ebp
0x100206c6  pop     ebp
0x100206c7  retn    8
```

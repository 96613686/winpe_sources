# Database::AssignUserNumber(DBHeaderPage *,ushort const *,Err &)

- ea: `0x100223b0`
- end: `0x10022699`
- name: `?AssignUserNumber@Database@@IAEXPAVDBHeaderPage@@PBGAAVErr@@@Z`
- size: `745`
- prototype: `void __thiscall(Database *__hidden this, struct DBHeaderPage *, const unsigned __int16 *, struct Err *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10020080`

## callees

- `0x100081e0`
- `0x100223b0`
- `0x1002e740`
- `0x1004eda0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f180`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100223d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100224bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100223d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100224bb`
- `api-ms-win-core-file-l1-1-0!LockFile` at `0x10022436`
- `api-ms-win-core-file-l1-1-0!LockFile` at `0x10022436`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x100225b8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x100225b8`

## pseudocode

```c
void __thiscall Database::AssignUserNumber(
        Database *this,
        struct DBHeaderPage *a2,
        const unsigned __int16 *a3,
        struct Err *a4)
{
  unsigned int v5; // ecx
  int v6; // ebx
  int v7; // esi
  struct Err *v8; // ecx
  void *v9; // esi
  void *v10; // eax
  int v11; // ecx
  struct Err *v12; // ebx
  struct Err *v13; // ecx
  DWORD nSize; // [esp+10h] [ebp-68h] BYREF
  struct Err *v15; // [esp+14h] [ebp-64h]
  int v16; // [esp+18h] [ebp-60h]
  int v17; // [esp+1Ch] [ebp-5Ch]
  void *Block; // [esp+24h] [ebp-54h]
  void *v19; // [esp+28h] [ebp-50h]
  LPCWCH lpWideCharStr; // [esp+2Ch] [ebp-4Ch]
  CHAR Buffer[68]; // [esp+30h] [ebp-48h] BYREF

  lpWideCharStr = a3;
  v15 = a4;
  nSize = GetTickCount();
  do
  {
    *((_DWORD *)this + 27) = 1;
    v5 = 1;
    while ( 1 )
    {
      v6 = 1;
      v16 = 1;
      if ( *(_WORD *)(*((_DWORD *)a2 + 1) + 2 * v5 + 1536) >= 0x100u )
        break;
      v9 = v19;
      v10 = Block;
LABEL_27:
      if ( (v6 & 0xFFFFFFFE) != 0 )
      {
        if ( v10 )
          operator delete[](v10);
        if ( v9 )
          operator delete[](v9);
      }
      v5 = *((_DWORD *)this + 27) + 1;
      *((_DWORD *)this + 27) = v5;
      if ( v5 >= 0x100 )
        goto LABEL_16;
    }
    v7 = *((_DWORD *)this + 16);
    if ( *(_DWORD *)(v7 + 8) >= *(_DWORD *)(v7 + 12) )
    {
      v10 = 0;
      v6 = 8;
      v11 = -1033;
      v9 = 0;
    }
    else if ( LockFile(*(HANDLE *)v7, v5 + 0x10000000, 0, 1u, 0) )
    {
      ++*(_DWORD *)(v7 + 8);
      v9 = v19;
      v10 = Block;
      v11 = v17;
    }
    else
    {
      System::ErrGetLastError(v8);
      v9 = v19;
      v10 = Block;
      v11 = v17;
      v6 = v16;
    }
    if ( (v6 & 1) == 0 && v11 == -1025 )
      goto LABEL_27;
    if ( (v6 & 0xFFFFFFFE) != 0 )
    {
      if ( v10 )
        operator delete[](v10);
      if ( v9 )
        operator delete[](v9);
    }
LABEL_16:
    if ( *((_DWORD *)this + 27) < 0x100u )
      goto LABEL_34;
  }
  while ( nSize - GetTickCount() + 5000 < 0x80000000 );
  if ( *((_DWORD *)this + 27) < 0x100u )
  {
LABEL_34:
    v12 = v15;
    goto LABEL_35;
  }
  v12 = v15;
  if ( *(int *)v15 < 8 )
  {
    if ( (*(_DWORD *)v15 & 0xFFFFFFFE) != 0 )
    {
      if ( *((_DWORD *)v15 + 3) )
        operator delete[](*((void **)v15 + 3));
      if ( *((_DWORD *)v15 + 4) )
        operator delete[](*((void **)v15 + 4));
    }
    *(_DWORD *)v15 = 8;
    *((_DWORD *)v12 + 1) = -1059;
    *((_DWORD *)v12 + 2) = 0;
    *((_DWORD *)v12 + 3) = 0;
    *((_DWORD *)v12 + 4) = 0;
  }
LABEL_35:
  if ( (*(_BYTE *)v12 & 8) == 0 )
  {
    memset(Buffer, 32, 0x40u);
    nSize = 32;
    if ( !GetComputerNameA(Buffer, &nSize) )
      System::ErrGetLastError(v13);
    if ( (*(_BYTE *)v12 & 8) == 0 )
    {
      nSize = 32;
      if ( ErrWideNToCbMultiByte(lpWideCharStr, wcslen(lpWideCharStr) + 1, &Buffer[32], (int)&nSize) < 0 )
      {
        if ( *(int *)v12 < 8 )
        {
          if ( (*(_DWORD *)v12 & 0xFFFFFFFE) != 0 )
          {
            if ( *((_DWORD *)v12 + 3) )
              operator delete[](*((void **)v12 + 3));
            if ( *((_DWORD *)v12 + 4) )
              operator delete[](*((void **)v12 + 4));
          }
          *(_DWORD *)v12 = 8;
          *((_DWORD *)v12 + 1) = -1003;
          *((_DWORD *)v12 + 2) = 0;
          *((_DWORD *)v12 + 3) = 0;
          *((_DWORD *)v12 + 4) = 0;
        }
      }
      else
      {
        File::Write(*((File **)this + 16), (*((_DWORD *)this + 27) << 6) - 64, Buffer, 0x40u, v12);
      }
    }
  }
}

```

## disassembly

```asm
0x100223b0  mov     edi, edi
0x100223b2  push    ebp
0x100223b3  mov     ebp, esp
0x100223b5  and     esp, 0FFFFFFF8h
0x100223b8  sub     esp, 6Ch
0x100223bb  mov     eax, ___security_cookie
0x100223c0  xor     eax, esp
0x100223c2  mov     [esp+6Ch+var_4], eax
0x100223c6  mov     eax, [ebp+arg_4]
0x100223c9  push    ebx
0x100223ca  push    esi
0x100223cb  mov     [esp+74h+lpWideCharStr], eax
0x100223cf  mov     eax, [ebp+arg_8]
0x100223d2  push    edi
0x100223d3  mov     edi, ecx
0x100223d5  mov     [esp+78h+var_64], eax
0x100223d9  call    ds:__imp__GetTickCount@0; GetTickCount()
0x100223df  mov     [esp+78h+nSize], eax
0x100223e3  mov     edx, 100h
0x100223e8  nop     dword ptr [eax+eax+00000000h]
0x100223f0  mov     dword ptr [edi+6Ch], 1
0x100223f7  mov     ecx, 1
0x100223fc  nop     dword ptr [eax+00h]
0x10022400  mov     eax, [ebp+arg_0]
0x10022403  mov     ebx, 1
0x10022408  mov     [esp+78h+var_60], ebx
0x1002240c  mov     eax, [eax+4]
0x1002240f  cmp     [eax+ecx*2+600h], dx
0x10022417  jb      loc_10022541
0x1002241d  mov     esi, [edi+40h]
0x10022420  mov     eax, [esi+8]
0x10022423  cmp     eax, [esi+0Ch]
0x10022426  jnb     short loc_1002246D
0x10022428  push    0; nNumberOfBytesToLockHigh
0x1002242a  push    ebx; nNumberOfBytesToLockLow
0x1002242b  push    0; dwFileOffsetHigh
0x1002242d  lea     eax, [ecx+10000000h]
0x10022433  push    eax; dwFileOffsetLow
0x10022434  push    dword ptr [esi]; hFile
0x10022436  call    ds:__imp__LockFile@20; LockFile(x,x,x,x,x)
0x1002243c  test    eax, eax
0x1002243e  jz      short loc_10022451
0x10022440  inc     dword ptr [esi+8]
0x10022443  mov     esi, [esp+78h+var_50]
0x10022447  mov     eax, [esp+78h+Block]
0x1002244b  mov     ecx, [esp+78h+var_5C]
0x1002244f  jmp     short loc_1002247B
0x10022451  lea     eax, [esp+78h+var_60]
0x10022455  push    eax
0x10022456  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1002245b  mov     esi, [esp+78h+var_50]
0x1002245f  mov     eax, [esp+78h+Block]
0x10022463  mov     ecx, [esp+78h+var_5C]
0x10022467  mov     ebx, [esp+78h+var_60]
0x1002246b  jmp     short loc_1002247B
0x1002246d  xor     eax, eax
0x1002246f  mov     ebx, 8
0x10022474  mov     ecx, 0FFFFFBF7h
0x10022479  xor     esi, esi
0x1002247b  test    bl, 1
0x1002247e  jnz     short loc_1002248C
0x10022480  cmp     ecx, 0FFFFFBFFh
0x10022486  jz      loc_10022549
0x1002248c  test    ebx, 0FFFFFFFEh
0x10022492  jz      short loc_100224AE
0x10022494  test    eax, eax
0x10022496  jz      short loc_100224A1
0x10022498  push    eax; Block
0x10022499  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002249e  add     esp, 4
0x100224a1  test    esi, esi
0x100224a3  jz      short loc_100224AE
0x100224a5  push    esi; Block
0x100224a6  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100224ab  add     esp, 4
0x100224ae  cmp     dword ptr [edi+6Ch], 100h
0x100224b5  jb      loc_10022588
0x100224bb  call    ds:__imp__GetTickCount@0; GetTickCount()
0x100224c1  mov     ecx, [esp+78h+nSize]
0x100224c5  mov     edx, 100h
0x100224ca  sub     ecx, eax
0x100224cc  add     ecx, 1388h
0x100224d2  cmp     ecx, 80000000h
0x100224d8  jb      loc_100223F0
0x100224de  cmp     [edi+6Ch], edx
0x100224e1  jb      loc_10022588
0x100224e7  mov     ebx, [esp+78h+var_64]
0x100224eb  mov     eax, [ebx]
0x100224ed  cmp     eax, 8
0x100224f0  jge     loc_1002258C
0x100224f6  test    eax, 0FFFFFFFEh
0x100224fb  jz      short loc_1002251D
0x100224fd  mov     eax, [ebx+0Ch]
0x10022500  test    eax, eax
0x10022502  jz      short loc_1002250D
0x10022504  push    eax; Block
0x10022505  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002250a  add     esp, 4
0x1002250d  mov     eax, [ebx+10h]
0x10022510  test    eax, eax
0x10022512  jz      short loc_1002251D
0x10022514  push    eax; Block
0x10022515  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002251a  add     esp, 4
0x1002251d  mov     dword ptr [ebx], 8
0x10022523  mov     dword ptr [ebx+4], 0FFFFFBDDh
0x1002252a  mov     dword ptr [ebx+8], 0
0x10022531  mov     dword ptr [ebx+0Ch], 0
0x10022538  mov     dword ptr [ebx+10h], 0
0x1002253f  jmp     short loc_1002258C
0x10022541  mov     esi, [esp+78h+var_50]
0x10022545  mov     eax, [esp+78h+Block]
0x10022549  test    ebx, 0FFFFFFFEh
0x1002254f  jz      short loc_1002256B
0x10022551  test    eax, eax
0x10022553  jz      short loc_1002255E
0x10022555  push    eax; Block
0x10022556  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002255b  add     esp, 4
0x1002255e  test    esi, esi
0x10022560  jz      short loc_1002256B
0x10022562  push    esi; Block
0x10022563  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10022568  add     esp, 4
0x1002256b  mov     ecx, [edi+6Ch]
0x1002256e  inc     ecx
0x1002256f  mov     [edi+6Ch], ecx
0x10022572  cmp     ecx, 100h
0x10022578  jnb     loc_100224AE
0x1002257e  mov     edx, 100h
0x10022583  jmp     loc_10022400
0x10022588  mov     ebx, [esp+78h+var_64]
0x1002258c  test    byte ptr [ebx], 8
0x1002258f  jnz     loc_10022685
0x10022595  push    40h ; '@'; Size
0x10022597  lea     eax, [esp+7Ch+Buffer]
0x1002259b  push    20h ; ' '; Val
0x1002259d  push    eax; void *
0x1002259e  call    _memset
0x100225a3  add     esp, 0Ch
0x100225a6  mov     [esp+78h+nSize], 20h ; ' '
0x100225ae  lea     eax, [esp+78h+nSize]
0x100225b2  push    eax; nSize
0x100225b3  lea     eax, [esp+7Ch+Buffer]
0x100225b7  push    eax; lpBuffer
0x100225b8  call    ds:__imp__GetComputerNameA@8; GetComputerNameA(x,x)
0x100225be  test    eax, eax
0x100225c0  jnz     short loc_100225C8
0x100225c2  push    ebx
0x100225c3  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x100225c8  test    byte ptr [ebx], 8
0x100225cb  jnz     loc_10022685
0x100225d1  mov     esi, [esp+78h+lpWideCharStr]
0x100225d5  mov     edx, esi
0x100225d7  mov     [esp+78h+nSize], 20h ; ' '
0x100225df  lea     ecx, [edx+2]
0x100225e2  mov     ax, [edx]
0x100225e5  add     edx, 2
0x100225e8  test    ax, ax
0x100225eb  jnz     short loc_100225E2
0x100225ed  sub     edx, ecx
0x100225ef  lea     eax, [esp+78h+nSize]
0x100225f3  push    eax; int
0x100225f4  sar     edx, 1
0x100225f6  lea     eax, [esp+7Ch+MultiByteStr]
0x100225fa  push    eax; lpMultiByteStr
0x100225fb  inc     edx; cchWideChar
0x100225fc  mov     ecx, esi; lpWideCharStr
0x100225fe  call    _ErrWideNToCbMultiByte@16; ErrWideNToCbMultiByte(x,x,x,x)
0x10022603  test    eax, eax
0x10022605  js      short loc_10022635
0x10022607  mov     ecx, [edi+40h]; this
0x1002260a  lea     eax, [esp+78h+Buffer]
0x1002260e  push    ebx; struct Err *
0x1002260f  push    40h ; '@'; nNumberOfBytesToWrite
0x10022611  push    eax; lpBuffer
0x10022612  mov     eax, [edi+6Ch]
0x10022615  shl     eax, 6
0x10022618  sub     eax, 40h ; '@'
0x1002261b  push    eax; lDistanceToMove
0x1002261c  call    ?Write@File@@QAEXKPAXKAAVErr@@@Z; File::Write(ulong,void *,ulong,Err &)
0x10022621  pop     edi
0x10022622  pop     esi
0x10022623  pop     ebx
0x10022624  mov     ecx, [esp+6Ch+var_4]
0x10022628  xor     ecx, esp; StackCookie
0x1002262a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002262f  mov     esp, ebp
0x10022631  pop     ebp
0x10022632  retn    0Ch
0x10022635  mov     eax, [ebx]
0x10022637  cmp     eax, 8
0x1002263a  jge     short loc_10022685
0x1002263c  test    eax, 0FFFFFFFEh
0x10022641  jz      short loc_10022663
0x10022643  mov     eax, [ebx+0Ch]
0x10022646  test    eax, eax
0x10022648  jz      short loc_10022653
0x1002264a  push    eax; Block
0x1002264b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10022650  add     esp, 4
0x10022653  mov     eax, [ebx+10h]
0x10022656  test    eax, eax
0x10022658  jz      short loc_10022663
0x1002265a  push    eax; Block
0x1002265b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10022660  add     esp, 4
0x10022663  mov     dword ptr [ebx], 8
0x10022669  mov     dword ptr [ebx+4], 0FFFFFC15h
0x10022670  mov     dword ptr [ebx+8], 0
0x10022677  mov     dword ptr [ebx+0Ch], 0
0x1002267e  mov     dword ptr [ebx+10h], 0
0x10022685  mov     ecx, [esp+78h+var_4]
0x10022689  pop     edi
0x1002268a  pop     esi
0x1002268b  pop     ebx
0x1002268c  xor     ecx, esp; StackCookie
0x1002268e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10022693  mov     esp, ebp
0x10022695  pop     ebp
0x10022696  retn    0Ch
```

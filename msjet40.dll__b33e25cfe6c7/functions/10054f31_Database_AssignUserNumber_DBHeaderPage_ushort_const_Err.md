# Database::AssignUserNumber(DBHeaderPage *,ushort * const,Err &)

- ea: `0x10054f31`
- end: `0x10055145`
- name: `?AssignUserNumber@Database@@IAEXPAVDBHeaderPage@@QAGAAVErr@@@Z`
- size: `532`
- prototype: `void __thiscall(Database *__hidden this, struct DBHeaderPage *, unsigned __int16 *const, struct Err *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10053680`

## callees

- `0x10045d3b`
- `0x1004791f`
- `0x10051197`
- `0x100512f2`
- `0x10054f31`
- `0x10055532`
- `0x1005563d`
- `0x100610f0`
- `0x10074b2c`
- `0x10074bb1`
- `0x10074c8c`
- `0x10122f60`
- `0x1012398c`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10054f4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10055093`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10054f4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10055093`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x100550ea`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x100550ea`

## pseudocode

```c
void __thiscall Database::AssignUserNumber(
        Database *this,
        struct DBHeaderPage *a2,
        unsigned __int16 *const a3,
        struct Err *a4)
{
  DWORD TickCount; // eax
  bool v6; // zf
  int v7; // edx
  int v8; // ecx
  int v9; // eax
  unsigned int v10; // eax
  bool v11; // cf
  DWORD v12; // eax
  struct Err *v13; // ebx
  struct Err *v14; // ecx
  int v15; // ecx
  _DWORD v16[5]; // [esp+10h] [ebp-7Ch] BYREF
  unsigned __int16 *v17; // [esp+24h] [ebp-68h]
  DWORD v18; // [esp+28h] [ebp-64h]
  int v19; // [esp+2Ch] [ebp-60h]
  DWORD nSize; // [esp+30h] [ebp-5Ch] BYREF
  int v21; // [esp+34h] [ebp-58h]
  CHAR Buffer[80]; // [esp+38h] [ebp-54h] BYREF
  int v23; // [esp+88h] [ebp-4h]

  v17 = a3;
  nSize = (DWORD)a4;
  TickCount = GetTickCount();
  v6 = (*((_BYTE *)this + 236) & 0x10) == 0;
  v18 = TickCount;
  if ( v6 )
  {
    if ( Database::LockAllRowLock(this, 1) )
    {
      v21 = 0;
      Database::UnlockAllRowLock(this, 1);
    }
    else
    {
      v21 = 1;
      Err::SetWarning(a4, 3812);
      *((_DWORD *)this + 59) |= 0x10u;
    }
  }
  else if ( Database::LockAllRowLock(this, 0) )
  {
    v21 = 1;
    Database::UnlockAllRowLock(this, 0);
  }
  else if ( Database::LockAllRowLock(this, 1) )
  {
    v21 = 0;
    Database::UnlockAllRowLock(this, 1);
    *((_DWORD *)this + 59) &= ~0x10u;
    Err::SetWarning(a4, 3811);
  }
  else
  {
    v21 = 1;
  }
  while ( 1 )
  {
    *((_DWORD *)this + 25) = 1;
    v19 = 1;
    while ( 1 )
    {
      v7 = 1;
      v16[0] = 1;
      v23 = 0;
      v8 = v21;
      if ( *(_WORD *)(*((_DWORD *)a2 + 1) + 2 * v19 + 3584) >= 0x100u )
      {
        if ( v21 == 1 )
        {
          File::LockRange(*((File **)this + 17), v19 + 268435711, 1u, (struct Err *)v16);
          v9 = *((_DWORD *)this + 25);
        }
        else
        {
          v9 = v19;
        }
        File::LockRange(*((File **)this + 17), v9 + 0x10000000, 1u, (struct Err *)v16);
        v7 = v16[0];
        if ( (v16[0] & 1) != 0 || v16[1] != -1025 )
          break;
      }
      v23 = -1;
      if ( (v7 & 0xFFFFFFFE) != 0 )
        Err::Delete((Err *)v16);
      v10 = *((_DWORD *)this + 25) + 1;
      v19 = v10;
      *((_DWORD *)this + 25) = v10;
      if ( v10 >= 0x100 )
        goto LABEL_24;
    }
    v23 = -1;
    if ( (v16[0] & 0xFFFFFFFE) != 0 )
      Err::Delete((Err *)v16);
LABEL_24:
    v11 = *((_DWORD *)this + 25) < 0x100u;
    if ( *((_DWORD *)this + 25) < 0x100u )
      break;
    v12 = GetTickCount();
    v8 = v21;
    if ( v18 - v12 + 5000 >= 0x80000000 )
    {
      v11 = *((_DWORD *)this + 25) < 0x100u;
      break;
    }
  }
  v13 = (struct Err *)nSize;
  if ( !v11 )
    Err::SetError(nSize, -1059, v8);
  if ( (*(_BYTE *)v13 & 8) == 0 )
  {
    memset(Buffer, 32, 0x40u);
    nSize = 32;
    if ( !GetComputerNameA(Buffer, &nSize) )
      System::ErrGetLastError(v14);
    if ( (*(_BYTE *)v13 & 8) == 0 )
    {
      nSize = 32;
      if ( ErrWideToCbMultiByte(v17, &Buffer[32], &nSize) < 0 )
        Err::SetError(v13, -1003, v15);
      else
        File::Write(*((File **)this + 17), (*((_DWORD *)this + 25) << 6) - 64, Buffer, 0x40u, v13);
    }
  }
}

```

## disassembly

```asm
0x10054f31  push    70h
0x10054f33  mov     eax, offset loc_1012547F
0x10054f38  call    __EH_prolog3_GS
0x10054f3d  mov     esi, ecx
0x10054f3f  mov     eax, [ebp+arg_4]
0x10054f42  mov     ebx, [ebp+arg_8]
0x10054f45  mov     [ebp+var_68], eax
0x10054f48  mov     [ebp+nSize], ebx
0x10054f4b  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10054f51  test    byte ptr [esi+0ECh], 10h
0x10054f58  mov     ecx, esi
0x10054f5a  mov     [ebp+var_64], eax
0x10054f5d  jz      short loc_10054FA7
0x10054f5f  push    0
0x10054f61  call    ?LockAllRowLock@Database@@IAE?AW4DBBool@@W4DBLockMode@@@Z; Database::LockAllRowLock(DBLockMode)
0x10054f66  xor     edi, edi
0x10054f68  mov     ecx, esi
0x10054f6a  inc     edi
0x10054f6b  test    eax, eax
0x10054f6d  jz      short loc_10054F76
0x10054f6f  mov     [ebp+var_58], edi
0x10054f72  push    0
0x10054f74  jmp     short loc_10054FBC
0x10054f76  push    edi
0x10054f77  call    ?LockAllRowLock@Database@@IAE?AW4DBBool@@W4DBLockMode@@@Z; Database::LockAllRowLock(DBLockMode)
0x10054f7c  test    eax, eax
0x10054f7e  jz      short loc_10054FA2
0x10054f80  xor     eax, eax
0x10054f82  mov     ecx, esi
0x10054f84  push    edi
0x10054f85  mov     [ebp+var_58], eax
0x10054f88  call    ?UnlockAllRowLock@Database@@IAEXW4DBLockMode@@@Z; Database::UnlockAllRowLock(DBLockMode)
0x10054f8d  and     dword ptr [esi+0ECh], 0FFFFFFEFh
0x10054f94  mov     ecx, ebx; this
0x10054f96  push    0EE3h; int
0x10054f9b  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x10054fa0  jmp     short loc_10054FD9
0x10054fa2  mov     [ebp+var_58], edi
0x10054fa5  jmp     short loc_10054FD9
0x10054fa7  xor     edi, edi
0x10054fa9  inc     edi
0x10054faa  push    edi
0x10054fab  call    ?LockAllRowLock@Database@@IAE?AW4DBBool@@W4DBLockMode@@@Z; Database::LockAllRowLock(DBLockMode)
0x10054fb0  test    eax, eax
0x10054fb2  jz      short loc_10054FC3
0x10054fb4  xor     eax, eax
0x10054fb6  mov     ecx, esi
0x10054fb8  mov     [ebp+var_58], eax
0x10054fbb  push    edi
0x10054fbc  call    ?UnlockAllRowLock@Database@@IAEXW4DBLockMode@@@Z; Database::UnlockAllRowLock(DBLockMode)
0x10054fc1  jmp     short loc_10054FD9
0x10054fc3  push    0EE4h; int
0x10054fc8  mov     ecx, ebx; this
0x10054fca  mov     [ebp+var_58], edi
0x10054fcd  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x10054fd2  or      dword ptr [esi+0ECh], 10h
0x10054fd9  mov     ebx, 100h
0x10054fde  mov     [esi+64h], edi
0x10054fe1  mov     [ebp+var_60], edi
0x10054fe4  mov     edx, edi
0x10054fe6  mov     [ebp+var_7C], edx
0x10054fe9  mov     eax, [ebp+arg_0]
0x10054fec  mov     ecx, [ebp+var_60]
0x10054fef  mov     [ebp+var_4], 0
0x10054ff6  mov     eax, [eax+4]
0x10054ff9  cmp     [eax+ecx*2+0E00h], bx
0x10055001  mov     ecx, [ebp+var_58]
0x10055004  jb      short loc_1005504C
0x10055006  cmp     ecx, edi
0x10055008  jnz     short loc_10055025
0x1005500a  mov     ecx, [esi+44h]; this
0x1005500d  lea     eax, [ebp+var_7C]
0x10055010  push    eax; struct Err *
0x10055011  mov     eax, [ebp+var_60]
0x10055014  push    edi; nNumberOfBytesToLockLow
0x10055015  add     eax, 100000FFh
0x1005501a  push    eax; dwFileOffsetLow
0x1005501b  call    ?LockRange@File@@QAEXKKAAVErr@@@Z; File::LockRange(ulong,ulong,Err &)
0x10055020  mov     eax, [esi+64h]
0x10055023  jmp     short loc_10055028
0x10055025  mov     eax, [ebp+var_60]
0x10055028  lea     ecx, [ebp+var_7C]
0x1005502b  add     eax, 10000000h
0x10055030  push    ecx; struct Err *
0x10055031  mov     ecx, [esi+44h]; this
0x10055034  push    edi; nNumberOfBytesToLockLow
0x10055035  push    eax; dwFileOffsetLow
0x10055036  call    ?LockRange@File@@QAEXKKAAVErr@@@Z; File::LockRange(ulong,ulong,Err &)
0x1005503b  mov     edx, [ebp+var_7C]
0x1005503e  test    dl, 1
0x10055041  jnz     short loc_10055077
0x10055043  cmp     [ebp+var_78], 0FFFFFBFFh
0x1005504a  jnz     short loc_10055077
0x1005504c  mov     [ebp+var_4], 0FFFFFFFFh
0x10055053  test    edx, 0FFFFFFFEh
0x10055059  jz      short loc_10055063
0x1005505b  lea     ecx, [ebp+var_7C]; this
0x1005505e  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10055063  mov     eax, [esi+64h]
0x10055066  inc     eax
0x10055067  mov     [ebp+var_60], eax
0x1005506a  mov     [esi+64h], eax
0x1005506d  cmp     eax, ebx
0x1005506f  jb      loc_10054FE4
0x10055075  jmp     short loc_1005508E
0x10055077  mov     [ebp+var_4], 0FFFFFFFFh
0x1005507e  test    edx, 0FFFFFFFEh
0x10055084  jz      short loc_1005508E
0x10055086  lea     ecx, [ebp+var_7C]; this
0x10055089  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x1005508e  cmp     [esi+64h], ebx
0x10055091  jb      short loc_100550B6
0x10055093  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10055099  mov     ecx, [ebp+var_64]
0x1005509c  sub     ecx, eax
0x1005509e  add     ecx, 1388h
0x100550a4  cmp     ecx, 80000000h
0x100550aa  mov     ecx, [ebp+var_58]
0x100550ad  jb      loc_10054FDE
0x100550b3  cmp     [esi+64h], ebx
0x100550b6  mov     ebx, [ebp+nSize]
0x100550b9  jb      short loc_100550C8
0x100550bb  push    ecx
0x100550bc  push    0FFFFFBDDh
0x100550c1  mov     ecx, ebx
0x100550c3  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100550c8  test    byte ptr [ebx], 8
0x100550cb  jnz     short loc_1005513D
0x100550cd  push    40h ; '@'; Size
0x100550cf  push    20h ; ' '
0x100550d1  pop     edi
0x100550d2  lea     eax, [ebp+Buffer]
0x100550d5  push    edi; Val
0x100550d6  push    eax; void *
0x100550d7  call    _memset
0x100550dc  add     esp, 0Ch
0x100550df  mov     [ebp+nSize], edi
0x100550e2  lea     eax, [ebp+nSize]
0x100550e5  push    eax; nSize
0x100550e6  lea     eax, [ebp+Buffer]
0x100550e9  push    eax; lpBuffer
0x100550ea  call    ds:__imp__GetComputerNameA@8; GetComputerNameA(x,x)
0x100550f0  test    eax, eax
0x100550f2  jnz     short loc_100550FA
0x100550f4  push    ebx
0x100550f5  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x100550fa  test    byte ptr [ebx], 8
0x100550fd  jnz     short loc_1005513D
0x100550ff  mov     ecx, [ebp+var_68]
0x10055102  lea     eax, [ebp+nSize]
0x10055105  push    eax
0x10055106  lea     edx, [ebp+var_34]
0x10055109  mov     [ebp+nSize], edi
0x1005510c  call    _ErrWideToCbMultiByte@12; ErrWideToCbMultiByte(x,x,x)
0x10055111  test    eax, eax
0x10055113  js      short loc_10055130
0x10055115  mov     ecx, [esi+44h]; this
0x10055118  lea     eax, [ebp+Buffer]
0x1005511b  push    ebx; struct Err *
0x1005511c  push    40h ; '@'; nNumberOfBytesToWrite
0x1005511e  push    eax; lpBuffer
0x1005511f  mov     eax, [esi+64h]
0x10055122  shl     eax, 6
0x10055125  sub     eax, 40h ; '@'
0x10055128  push    eax; lDistanceToMove
0x10055129  call    ?Write@File@@QAEXKPAXKAAVErr@@@Z; File::Write(ulong,void *,ulong,Err &)
0x1005512e  jmp     short loc_1005513D
0x10055130  push    ecx
0x10055131  push    0FFFFFC15h
0x10055136  mov     ecx, ebx
0x10055138  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005513d  call    __EH_epilog3_GS
0x10055142  retn    0Ch
0x10125472  lea     ecx, [ebp+var_7C]; this
0x10125475  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x1012547f  nop
0x10125480  nop
0x10125481  mov     edx, [esp-4+arg_4]
0x10125485  lea     eax, [edx+0Ch]
0x10125488  mov     ecx, [edx-80h]
0x1012548b  xor     ecx, eax; StackCookie
0x1012548d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10125492  mov     ecx, [edx-4]
0x10125495  xor     ecx, eax; StackCookie
0x10125497  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1012549c  mov     eax, offset stru_10127EDC
0x101254a1  jmp     ___CxxFrameHandler3
```

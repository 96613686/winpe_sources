# Database::AssignUserNumber(DBHeaderPage *,ushort * const,Err &)

- ea: `0x100550c1`
- end: `0x100552d5`
- name: `?AssignUserNumber@Database@@IAEXPAVDBHeaderPage@@QAGAAVErr@@@Z`
- size: `532`
- prototype: `void __thiscall(Database *__hidden this, struct DBHeaderPage *, unsigned __int16 *const, struct Err *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10053810`

## callees

- `0x10045ebb`
- `0x10047a9f`
- `0x10051327`
- `0x10051482`
- `0x100550c1`
- `0x100556c2`
- `0x100557cd`
- `0x10061284`
- `0x10074cbc`
- `0x10074d41`
- `0x10074e1c`
- `0x10123110`
- `0x10123b3c`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100550db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10055223`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100550db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10055223`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x1005527a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x1005527a`

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
0x100550c1  push    70h
0x100550c3  mov     eax, offset loc_1012562F
0x100550c8  call    __EH_prolog3_GS
0x100550cd  mov     esi, ecx
0x100550cf  mov     eax, [ebp+arg_4]
0x100550d2  mov     ebx, [ebp+arg_8]
0x100550d5  mov     [ebp+var_68], eax
0x100550d8  mov     [ebp+nSize], ebx
0x100550db  call    ds:__imp__GetTickCount@0; GetTickCount()
0x100550e1  test    byte ptr [esi+0ECh], 10h
0x100550e8  mov     ecx, esi
0x100550ea  mov     [ebp+var_64], eax
0x100550ed  jz      short loc_10055137
0x100550ef  push    0
0x100550f1  call    ?LockAllRowLock@Database@@IAE?AW4DBBool@@W4DBLockMode@@@Z; Database::LockAllRowLock(DBLockMode)
0x100550f6  xor     edi, edi
0x100550f8  mov     ecx, esi
0x100550fa  inc     edi
0x100550fb  test    eax, eax
0x100550fd  jz      short loc_10055106
0x100550ff  mov     [ebp+var_58], edi
0x10055102  push    0
0x10055104  jmp     short loc_1005514C
0x10055106  push    edi
0x10055107  call    ?LockAllRowLock@Database@@IAE?AW4DBBool@@W4DBLockMode@@@Z; Database::LockAllRowLock(DBLockMode)
0x1005510c  test    eax, eax
0x1005510e  jz      short loc_10055132
0x10055110  xor     eax, eax
0x10055112  mov     ecx, esi
0x10055114  push    edi
0x10055115  mov     [ebp+var_58], eax
0x10055118  call    ?UnlockAllRowLock@Database@@IAEXW4DBLockMode@@@Z; Database::UnlockAllRowLock(DBLockMode)
0x1005511d  and     dword ptr [esi+0ECh], 0FFFFFFEFh
0x10055124  mov     ecx, ebx; this
0x10055126  push    0EE3h; int
0x1005512b  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x10055130  jmp     short loc_10055169
0x10055132  mov     [ebp+var_58], edi
0x10055135  jmp     short loc_10055169
0x10055137  xor     edi, edi
0x10055139  inc     edi
0x1005513a  push    edi
0x1005513b  call    ?LockAllRowLock@Database@@IAE?AW4DBBool@@W4DBLockMode@@@Z; Database::LockAllRowLock(DBLockMode)
0x10055140  test    eax, eax
0x10055142  jz      short loc_10055153
0x10055144  xor     eax, eax
0x10055146  mov     ecx, esi
0x10055148  mov     [ebp+var_58], eax
0x1005514b  push    edi
0x1005514c  call    ?UnlockAllRowLock@Database@@IAEXW4DBLockMode@@@Z; Database::UnlockAllRowLock(DBLockMode)
0x10055151  jmp     short loc_10055169
0x10055153  push    0EE4h; int
0x10055158  mov     ecx, ebx; this
0x1005515a  mov     [ebp+var_58], edi
0x1005515d  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x10055162  or      dword ptr [esi+0ECh], 10h
0x10055169  mov     ebx, 100h
0x1005516e  mov     [esi+64h], edi
0x10055171  mov     [ebp+var_60], edi
0x10055174  mov     edx, edi
0x10055176  mov     [ebp+var_7C], edx
0x10055179  mov     eax, [ebp+arg_0]
0x1005517c  mov     ecx, [ebp+var_60]
0x1005517f  mov     [ebp+var_4], 0
0x10055186  mov     eax, [eax+4]
0x10055189  cmp     [eax+ecx*2+0E00h], bx
0x10055191  mov     ecx, [ebp+var_58]
0x10055194  jb      short loc_100551DC
0x10055196  cmp     ecx, edi
0x10055198  jnz     short loc_100551B5
0x1005519a  mov     ecx, [esi+44h]; this
0x1005519d  lea     eax, [ebp+var_7C]
0x100551a0  push    eax; struct Err *
0x100551a1  mov     eax, [ebp+var_60]
0x100551a4  push    edi; nNumberOfBytesToLockLow
0x100551a5  add     eax, 100000FFh
0x100551aa  push    eax; dwFileOffsetLow
0x100551ab  call    ?LockRange@File@@QAEXKKAAVErr@@@Z; File::LockRange(ulong,ulong,Err &)
0x100551b0  mov     eax, [esi+64h]
0x100551b3  jmp     short loc_100551B8
0x100551b5  mov     eax, [ebp+var_60]
0x100551b8  lea     ecx, [ebp+var_7C]
0x100551bb  add     eax, 10000000h
0x100551c0  push    ecx; struct Err *
0x100551c1  mov     ecx, [esi+44h]; this
0x100551c4  push    edi; nNumberOfBytesToLockLow
0x100551c5  push    eax; dwFileOffsetLow
0x100551c6  call    ?LockRange@File@@QAEXKKAAVErr@@@Z; File::LockRange(ulong,ulong,Err &)
0x100551cb  mov     edx, [ebp+var_7C]
0x100551ce  test    dl, 1
0x100551d1  jnz     short loc_10055207
0x100551d3  cmp     [ebp+var_78], 0FFFFFBFFh
0x100551da  jnz     short loc_10055207
0x100551dc  mov     [ebp+var_4], 0FFFFFFFFh
0x100551e3  test    edx, 0FFFFFFFEh
0x100551e9  jz      short loc_100551F3
0x100551eb  lea     ecx, [ebp+var_7C]; this
0x100551ee  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100551f3  mov     eax, [esi+64h]
0x100551f6  inc     eax
0x100551f7  mov     [ebp+var_60], eax
0x100551fa  mov     [esi+64h], eax
0x100551fd  cmp     eax, ebx
0x100551ff  jb      loc_10055174
0x10055205  jmp     short loc_1005521E
0x10055207  mov     [ebp+var_4], 0FFFFFFFFh
0x1005520e  test    edx, 0FFFFFFFEh
0x10055214  jz      short loc_1005521E
0x10055216  lea     ecx, [ebp+var_7C]; this
0x10055219  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x1005521e  cmp     [esi+64h], ebx
0x10055221  jb      short loc_10055246
0x10055223  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10055229  mov     ecx, [ebp+var_64]
0x1005522c  sub     ecx, eax
0x1005522e  add     ecx, 1388h
0x10055234  cmp     ecx, 80000000h
0x1005523a  mov     ecx, [ebp+var_58]
0x1005523d  jb      loc_1005516E
0x10055243  cmp     [esi+64h], ebx
0x10055246  mov     ebx, [ebp+nSize]
0x10055249  jb      short loc_10055258
0x1005524b  push    ecx
0x1005524c  push    0FFFFFBDDh
0x10055251  mov     ecx, ebx
0x10055253  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10055258  test    byte ptr [ebx], 8
0x1005525b  jnz     short loc_100552CD
0x1005525d  push    40h ; '@'; Size
0x1005525f  push    20h ; ' '
0x10055261  pop     edi
0x10055262  lea     eax, [ebp+Buffer]
0x10055265  push    edi; Val
0x10055266  push    eax; void *
0x10055267  call    _memset
0x1005526c  add     esp, 0Ch
0x1005526f  mov     [ebp+nSize], edi
0x10055272  lea     eax, [ebp+nSize]
0x10055275  push    eax; nSize
0x10055276  lea     eax, [ebp+Buffer]
0x10055279  push    eax; lpBuffer
0x1005527a  call    ds:__imp__GetComputerNameA@8; GetComputerNameA(x,x)
0x10055280  test    eax, eax
0x10055282  jnz     short loc_1005528A
0x10055284  push    ebx
0x10055285  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1005528a  test    byte ptr [ebx], 8
0x1005528d  jnz     short loc_100552CD
0x1005528f  mov     ecx, [ebp+var_68]
0x10055292  lea     eax, [ebp+nSize]
0x10055295  push    eax
0x10055296  lea     edx, [ebp+var_34]
0x10055299  mov     [ebp+nSize], edi
0x1005529c  call    _ErrWideToCbMultiByte@12; ErrWideToCbMultiByte(x,x,x)
0x100552a1  test    eax, eax
0x100552a3  js      short loc_100552C0
0x100552a5  mov     ecx, [esi+44h]; this
0x100552a8  lea     eax, [ebp+Buffer]
0x100552ab  push    ebx; struct Err *
0x100552ac  push    40h ; '@'; nNumberOfBytesToWrite
0x100552ae  push    eax; lpBuffer
0x100552af  mov     eax, [esi+64h]
0x100552b2  shl     eax, 6
0x100552b5  sub     eax, 40h ; '@'
0x100552b8  push    eax; lDistanceToMove
0x100552b9  call    ?Write@File@@QAEXKPAXKAAVErr@@@Z; File::Write(ulong,void *,ulong,Err &)
0x100552be  jmp     short loc_100552CD
0x100552c0  push    ecx
0x100552c1  push    0FFFFFC15h
0x100552c6  mov     ecx, ebx
0x100552c8  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100552cd  call    __EH_epilog3_GS
0x100552d2  retn    0Ch
0x10125622  lea     ecx, [ebp+var_7C]; this
0x10125625  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x1012562f  nop
0x10125630  nop
0x10125631  mov     edx, [esp-4+arg_4]
0x10125635  lea     eax, [edx+0Ch]
0x10125638  mov     ecx, [edx-80h]
0x1012563b  xor     ecx, eax; StackCookie
0x1012563d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10125642  mov     ecx, [edx-4]
0x10125645  xor     ecx, eax; StackCookie
0x10125647  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1012564c  mov     eax, offset stru_1012808C
0x10125651  jmp     ___CxxFrameHandler3
```

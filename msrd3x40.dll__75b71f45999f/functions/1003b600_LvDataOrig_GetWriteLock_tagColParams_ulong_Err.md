# LvDataOrig::GetWriteLock(tagColParams *,ulong,Err &)

- ea: `0x1003b600`
- end: `0x1003b7f3`
- name: `?GetWriteLock@LvDataOrig@@AAEXPAUtagColParams@@KAAVErr@@@Z`
- size: `499`
- prototype: `void __thiscall(LvDataOrig *__hidden this, struct tagColParams *, unsigned int, struct Err *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1003b2d0`
- `0x1003d300`

## callees

- `0x1000eb60`
- `0x10024b00`
- `0x10025ee0`
- `0x1003b600`
- `0x10042130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1003b645`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1003b6af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1003b7a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1003b645`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1003b6af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1003b7a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003b673`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003b6d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003b73c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003b7d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003b673`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003b6d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003b73c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003b7d1`

## pseudocode

```c
void __thiscall LvDataOrig::GetWriteLock(LvDataOrig *this, struct tagColParams *a2, unsigned int a3, void **a4)
{
  int v5; // edi
  int v6; // esi
  _DWORD *v7; // eax
  LvDataOrig *v8; // eax
  int v9; // esi
  void **v10; // edi
  PageDesc *v11; // ecx
  int v12; // ecx
  int v13; // eax
  unsigned int v14; // edx
  int v15; // ecx
  PageDesc *v16; // eax
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [esp+10h] [ebp-Ch]
  struct Transaction *lpCriticalSectiona; // [esp+10h] [ebp-Ch]
  struct Transaction *lpCriticalSectionb; // [esp+10h] [ebp-Ch]
  int v20; // [esp+14h] [ebp-8h]

  v5 = 0;
  v6 = *(_DWORD *)((*(int (__thiscall **)(_DWORD))(**(_DWORD **)(*((_DWORD *)this + 517) + 8) + 56))(*(_DWORD *)(*((_DWORD *)this + 517) + 8))
                 + 16);
  v20 = *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 517) + 8) + 40);
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(v6 + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 112));
  v7 = *(_DWORD **)(*(_DWORD *)(v6 + 160) + 4 * (a3 & (*(_DWORD *)(v6 + 164) - 1)));
  if ( !v7 )
  {
LABEL_4:
    LeaveCriticalSection(lpCriticalSection);
LABEL_5:
    v8 = this;
LABEL_6:
    v9 = *(_DWORD *)((*(int (__thiscall **)(_DWORD))(**(_DWORD **)(*((_DWORD *)v8 + 517) + 8) + 56))(*(_DWORD *)(*((_DWORD *)v8 + 517) + 8))
                   + 16);
    lpCriticalSectiona = *(struct Transaction **)(*(_DWORD *)(*((_DWORD *)this + 517) + 8) + 40);
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 112));
    v10 = a4;
    v11 = Database::FindOrCreate((Database *)v9, a3, a4);
    if ( (*(_BYTE *)a4 & 8) == 0 )
      PageDesc::IncrementLock(v11, 0, lpCriticalSectiona, (struct Err *)a4);
LABEL_8:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 112));
    goto LABEL_28;
  }
  while ( a3 != v7[3] )
  {
    v7 = (_DWORD *)v7[1];
    if ( !v7 )
      goto LABEL_4;
  }
  v12 = v7[4];
  if ( v12 )
  {
    v5 = 0;
    if ( *(_BYTE *)(v12 + 81) != 1 )
    {
      if ( (unsigned int)*(unsigned __int8 *)(v12 + 81) - 2 <= 1 )
      {
        v5 = *(unsigned __int8 *)(v12 + 81);
        if ( *(_DWORD *)(v12 + 60) != v20 )
          v5 = 0;
      }
      goto LABEL_21;
    }
    if ( *(__int16 *)(v12 + 78) > 0 )
    {
      v13 = 0;
      v14 = *(_DWORD *)(v20 + 20);
      if ( v14 )
      {
        while ( *(_DWORD *)(*(_DWORD *)(v20 + 12) + 4 * v13) != v12 )
        {
          if ( ++v13 >= v14 )
            goto LABEL_19;
        }
      }
      else
      {
LABEL_19:
        if ( v13 == v14 )
          goto LABEL_21;
      }
      v5 = 1;
    }
  }
LABEL_21:
  LeaveCriticalSection(lpCriticalSection);
  switch ( v5 )
  {
    case 0:
      goto LABEL_5;
    case 1:
      v8 = this;
      if ( *((_DWORD *)this + 520) == a3 )
        goto LABEL_6;
      v10 = a4;
      Err::SetError(a4, -1107, v15);
      break;
    case 2:
    case 3:
      v9 = *(_DWORD *)((*(int (__thiscall **)(_DWORD))(**(_DWORD **)(*((_DWORD *)this + 517) + 8) + 56))(*(_DWORD *)(*((_DWORD *)this + 517) + 8))
                     + 16);
      lpCriticalSectionb = *(struct Transaction **)(*(_DWORD *)(*((_DWORD *)this + 517) + 8) + 40);
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 112));
      v10 = a4;
      v16 = Database::FindOrCreate((Database *)v9, a3, a4);
      if ( (*(_BYTE *)a4 & 8) == 0 )
        PageDesc::IncrementLock(v16, 0, lpCriticalSectionb, (struct Err *)a4);
      goto LABEL_8;
    default:
      v10 = a4;
      break;
  }
LABEL_28:
  if ( (*(_BYTE *)v10 & 8) == 0 )
    *((_DWORD *)this + 521) = a3;
}

```

## disassembly

```asm
0x1003b600  mov     edi, edi
0x1003b602  push    ebp
0x1003b603  mov     ebp, esp
0x1003b605  sub     esp, 10h
0x1003b608  push    ebx
0x1003b609  mov     ebx, ecx
0x1003b60b  push    esi; unsigned int
0x1003b60c  push    edi; void *
0x1003b60d  mov     [ebp+var_4], ebx
0x1003b610  mov     eax, [ebx+814h]
0x1003b616  mov     edi, [eax+8]
0x1003b619  mov     eax, [edi]
0x1003b61b  mov     esi, [eax+38h]
0x1003b61e  mov     ecx, esi
0x1003b620  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003b626  mov     ecx, edi
0x1003b628  call    esi
0x1003b62a  xor     edi, edi
0x1003b62c  mov     esi, [eax+10h]
0x1003b62f  mov     eax, [ebx+814h]
0x1003b635  mov     eax, [eax+8]
0x1003b638  mov     eax, [eax+28h]
0x1003b63b  mov     [ebp+var_8], eax
0x1003b63e  lea     eax, [esi+70h]
0x1003b641  push    eax; lpCriticalSection
0x1003b642  mov     [ebp+lpCriticalSection], eax
0x1003b645  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1003b64b  mov     ecx, [esi+0A4h]
0x1003b651  mov     ebx, [ebp+arg_4]
0x1003b654  dec     ecx
0x1003b655  mov     eax, [esi+0A0h]
0x1003b65b  and     ecx, ebx
0x1003b65d  mov     eax, [eax+ecx*4]
0x1003b660  test    eax, eax
0x1003b662  jz      short loc_1003B670
0x1003b664  cmp     ebx, [eax+0Ch]
0x1003b667  jz      short loc_1003B6E4
0x1003b669  mov     eax, [eax+4]
0x1003b66c  test    eax, eax
0x1003b66e  jnz     short loc_1003B664
0x1003b670  push    [ebp+lpCriticalSection]; lpCriticalSection
0x1003b673  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003b679  mov     eax, [ebp+var_4]; jumptable 1003B74B case 0
0x1003b67c  mov     eax, [eax+814h]
0x1003b682  mov     edi, [eax+8]
0x1003b685  mov     eax, [edi]
0x1003b687  mov     esi, [eax+38h]
0x1003b68a  mov     ecx, esi
0x1003b68c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003b692  mov     ecx, edi
0x1003b694  call    esi
0x1003b696  mov     esi, [eax+10h]
0x1003b699  mov     eax, [ebp+var_4]
0x1003b69c  mov     eax, [eax+814h]
0x1003b6a2  mov     eax, [eax+8]
0x1003b6a5  mov     eax, [eax+28h]
0x1003b6a8  mov     [ebp+lpCriticalSection], eax
0x1003b6ab  lea     eax, [esi+70h]
0x1003b6ae  push    eax; lpCriticalSection
0x1003b6af  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1003b6b5  mov     edi, [ebp+arg_8]
0x1003b6b8  mov     ecx, esi; this
0x1003b6ba  push    edi; struct Err *
0x1003b6bb  push    ebx; unsigned int
0x1003b6bc  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x1003b6c1  mov     ecx, eax; this
0x1003b6c3  mov     eax, edi
0x1003b6c5  test    byte ptr [eax], 8
0x1003b6c8  jnz     short loc_1003B6D5
0x1003b6ca  push    eax; struct Err *
0x1003b6cb  push    [ebp+lpCriticalSection]; struct Transaction *
0x1003b6ce  push    0; unsigned int
0x1003b6d0  call    ?IncrementLock@PageDesc@@QAEXIPAVTransaction@@AAVErr@@@Z; PageDesc::IncrementLock(uint,Transaction *,Err &)
0x1003b6d5  lea     eax, [esi+70h]
0x1003b6d8  push    eax; lpCriticalSection
0x1003b6d9  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003b6df  jmp     loc_1003B7DC
0x1003b6e4  mov     ecx, [eax+10h]
0x1003b6e7  test    ecx, ecx
0x1003b6e9  jz      short loc_1003B739
0x1003b6eb  movzx   edx, byte ptr [ecx+51h]
0x1003b6ef  xor     edi, edi
0x1003b6f1  mov     eax, edx
0x1003b6f3  sub     eax, 1
0x1003b6f6  jz      short loc_1003B711
0x1003b6f8  sub     eax, 1
0x1003b6fb  jz      short loc_1003B702
0x1003b6fd  sub     eax, 1
0x1003b700  jnz     short loc_1003B739
0x1003b702  mov     esi, [ebp+var_8]
0x1003b705  xor     eax, eax
0x1003b707  cmp     [ecx+3Ch], esi
0x1003b70a  mov     edi, edx
0x1003b70c  cmovnz  edi, eax
0x1003b70f  jmp     short loc_1003B739
0x1003b711  cmp     [ecx+4Eh], di
0x1003b715  jle     short loc_1003B739
0x1003b717  mov     esi, [ebp+var_8]
0x1003b71a  xor     eax, eax
0x1003b71c  mov     edx, [esi+14h]
0x1003b71f  test    edx, edx
0x1003b721  jz      short loc_1003B730
0x1003b723  mov     esi, [esi+0Ch]
0x1003b726  cmp     [esi+eax*4], ecx
0x1003b729  jz      short loc_1003B734
0x1003b72b  inc     eax
0x1003b72c  cmp     eax, edx
0x1003b72e  jb      short loc_1003B726
0x1003b730  cmp     eax, edx
0x1003b732  jz      short loc_1003B739
0x1003b734  mov     edi, 1
0x1003b739  push    [ebp+lpCriticalSection]; lpCriticalSection
0x1003b73c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003b742  cmp     edi, 3; switch 4 cases
0x1003b745  ja      def_1003B74B; jumptable 1003B74B default case
0x1003b74b  jmp     ds:jpt_1003B74B[edi*4]; switch jump
0x1003b752  mov     eax, [ebp+var_4]; jumptable 1003B74B case 1
0x1003b755  cmp     [eax+820h], ebx
0x1003b75b  jz      loc_1003B67C
0x1003b761  mov     edi, [ebp+arg_8]
0x1003b764  push    ecx
0x1003b765  push    0FFFFFBADh
0x1003b76a  mov     ecx, edi
0x1003b76c  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003b771  jmp     short loc_1003B7DC
0x1003b773  mov     eax, [ebp+var_4]; jumptable 1003B74B cases 2,3
0x1003b776  mov     eax, [eax+814h]
0x1003b77c  mov     edi, [eax+8]
0x1003b77f  mov     eax, [edi]
0x1003b781  mov     esi, [eax+38h]
0x1003b784  mov     ecx, esi
0x1003b786  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003b78c  mov     ecx, edi
0x1003b78e  call    esi
0x1003b790  mov     esi, [eax+10h]
0x1003b793  mov     eax, [ebp+var_4]
0x1003b796  mov     eax, [eax+814h]
0x1003b79c  mov     eax, [eax+8]
0x1003b79f  mov     eax, [eax+28h]
0x1003b7a2  mov     [ebp+lpCriticalSection], eax
0x1003b7a5  lea     eax, [esi+70h]
0x1003b7a8  push    eax; lpCriticalSection
0x1003b7a9  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1003b7af  mov     edi, [ebp+arg_8]
0x1003b7b2  mov     ecx, esi; this
0x1003b7b4  push    edi; struct Err *
0x1003b7b5  push    ebx; unsigned int
0x1003b7b6  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x1003b7bb  test    byte ptr [edi], 8
0x1003b7be  jnz     short loc_1003B7CD
0x1003b7c0  push    edi; struct Err *
0x1003b7c1  push    [ebp+lpCriticalSection]; struct Transaction *
0x1003b7c4  mov     ecx, eax; this
0x1003b7c6  push    0; unsigned int
0x1003b7c8  call    ?IncrementLock@PageDesc@@QAEXIPAVTransaction@@AAVErr@@@Z; PageDesc::IncrementLock(uint,Transaction *,Err &)
0x1003b7cd  lea     eax, [esi+70h]
0x1003b7d0  push    eax; lpCriticalSection
0x1003b7d1  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003b7d7  jmp     short loc_1003B7DC
0x1003b7d9  mov     edi, [ebp+arg_8]; jumptable 1003B74B default case
0x1003b7dc  test    byte ptr [edi], 8
0x1003b7df  jnz     short loc_1003B7EA
0x1003b7e1  mov     eax, [ebp+var_4]
0x1003b7e4  mov     [eax+824h], ebx
0x1003b7ea  pop     edi
0x1003b7eb  pop     esi
0x1003b7ec  pop     ebx
0x1003b7ed  mov     esp, ebp
0x1003b7ef  pop     ebp
0x1003b7f0  retn    0Ch
```

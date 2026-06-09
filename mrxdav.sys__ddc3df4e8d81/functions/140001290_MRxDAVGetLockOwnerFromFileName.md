# MRxDAVGetLockOwnerFromFileName

- ea: `0x140001290`
- end: `0x1400015ea`
- name: `MRxDAVGetLockOwnerFromFileName`
- size: `858`
- prototype: `void __fastcall(__int64, const wchar_t *, unsigned int, _WORD *, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f120`
- `0x14000f780`

## callees

- `0x140001188`
- `0x140001290`
- `0x14000163c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400013b5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001423`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001505`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001558`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400013b5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001423`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001505`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001558`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400012e1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400012e1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400015b7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400015b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400012c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400012c5`
- `ntoskrnl!_wcsnicmp` at `0x140001341`
- `ntoskrnl!_wcsnicmp` at `0x140001341`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400015c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400015c3`

## pseudocode

```c
void __fastcall MRxDAVGetLockOwnerFromFileName(
        __int64 a1,
        const wchar_t *a2,
        unsigned int a3,
        _WORD *a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v8; // rdi
  PVOID *v9; // r13
  int v10; // ebx
  PVOID *v11; // r14
  __int64 v12; // r15
  size_t v13; // r8
  __int64 v14; // rax
  __int64 v15; // rbx
  HANDLE CurrentThreadId; // rax
  _WORD *v17; // r8
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  int v20; // esi
  __int64 v21; // rbx
  HANDLE v22; // rax
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rbx
  HANDLE v27; // rax

  v8 = 0;
  v9 = 0;
  v10 = 0;
  KeEnterCriticalRegion();
  MRxDAVCleanUpTheLockConflictList(0);
  ExAcquireResourceExclusiveLite(&LockConflictEntryListLock, 1u);
  v11 = (PVOID *)LockConflictEntryList;
  v12 = -1;
  while ( v11 != &LockConflictEntryList )
  {
    v9 = v11;
    v11 = (PVOID *)*v11;
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v9[2] + v13) );
    if ( 2 * v13 + 2 <= a3 && !_wcsnicmp((const wchar_t *)v9[2], a2, v13) )
    {
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)v9[2] + v14) );
      if ( !a2[v14] )
      {
        v10 = 1;
        break;
      }
    }
  }
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v15, 56, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, CurrentThreadId);
    }
    v17 = v9[3];
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    v19 = 2 * v18 + 2;
    if ( a5 >= v19 )
    {
      v23 = (unsigned __int64)a5 >> 1;
      if ( v23 )
      {
        v24 = v19 >> 1;
        if ( v24 <= 0x7FFFFFFE )
        {
          v25 = 0;
          while ( v23 )
          {
            if ( !v24 || !*v17 )
              goto LABEL_31;
            *a4++ = *v17++;
            --v23;
            --v24;
            ++v25;
          }
          --a4;
        }
LABEL_31:
        *a4 = 0;
      }
      v20 = 0;
    }
    else
    {
      v20 = -1073741789;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v22 = PsGetCurrentThreadId();
        WPP_SF_q(v21, 57, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v22);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v26 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v27 = PsGetCurrentThreadId();
      WPP_SF_q(v26, 59, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v27);
    }
    v20 = -1073741809;
  }
  *(_DWORD *)a6 = v20;
  if ( !v20 || v20 == -1073741789 )
  {
    do
      ++v12;
    while ( *((_WORD *)v9[3] + v12) );
    v8 = 2 * v12 + 2;
  }
  *(_QWORD *)(a6 + 8) = v8;
  ExReleaseResourceLite(&LockConflictEntryListLock);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140001290  mov     rax, rsp
0x140001293  mov     [rax+10h], rbx
0x140001297  mov     [rax+20h], rsi
0x14000129b  mov     [rax+18h], r8d
0x14000129f  mov     [rax+8], rcx
0x1400012a3  push    rdi
0x1400012a4  push    r12
0x1400012a6  push    r13
0x1400012a8  push    r14
0x1400012aa  push    r15
0x1400012ac  sub     rsp, 50h
0x1400012b0  mov     rsi, r9
0x1400012b3  mov     r12, rdx
0x1400012b6  xor     edi, edi
0x1400012b8  mov     r13d, edi
0x1400012bb  mov     [rsp+78h+arg_0], rdi
0x1400012c3  mov     ebx, edi
0x1400012c5  call    cs:__imp_KeEnterCriticalRegion
0x1400012cc  nop     dword ptr [rax+rax+00h]
0x1400012d1  xor     ecx, ecx
0x1400012d3  call    MRxDAVCleanUpTheLockConflictList
0x1400012d8  mov     dl, 1; Wait
0x1400012da  lea     rcx, LockConflictEntryListLock; Resource
0x1400012e1  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400012e8  nop     dword ptr [rax+rax+00h]
0x1400012ed  mov     r14, cs:LockConflictEntryList
0x1400012f4  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400012f8  lea     rax, LockConflictEntryList
0x1400012ff  cmp     r14, rax
0x140001302  jz      loc_14000138D
0x140001308  mov     r13, r14
0x14000130b  mov     [rsp+78h+arg_0], r14
0x140001313  mov     r14, [r14]
0x140001316  mov     r9, [r13+10h]
0x14000131a  mov     r8, r15
0x14000131d  inc     r8; MaxCount
0x140001320  cmp     [r9+r8*2], di
0x140001325  jnz     short loc_14000131D
0x140001327  lea     rcx, ds:2[r8*2]
0x14000132f  mov     eax, [rsp+78h+arg_10]
0x140001336  cmp     rcx, rax
0x140001339  ja      short loc_1400012F8
0x14000133b  mov     rdx, r12; Str2
0x14000133e  mov     rcx, r9; Str1
0x140001341  call    cs:__imp__wcsnicmp
0x140001348  nop     dword ptr [rax+rax+00h]
0x14000134d  test    eax, eax
0x14000134f  jnz     short loc_140001373
0x140001351  mov     rcx, [r13+10h]
0x140001355  mov     rax, r15
0x140001358  inc     rax
0x14000135b  cmp     [rcx+rax*2], di
0x14000135f  jnz     short loc_140001358
0x140001361  cmp     [r12+rax*2], di
0x140001366  jnz     short loc_140001373
0x140001368  mov     ebx, 1
0x14000136d  mov     [rsp+78h+var_58], ebx
0x140001371  jmp     short loc_14000138D
0x140001373  jmp     short loc_1400012F8
0x140001375  mov     esi, 0C00000E8h
0x14000137a  xor     edi, edi
0x14000137c  or      r15, 0FFFFFFFFFFFFFFFFh
0x140001380  mov     r13, [rsp+78h+arg_0]
0x140001388  jmp     loc_140001580
0x14000138d  test    ebx, ebx
0x14000138f  jz      loc_140001538
0x140001395  lea     r14, WPP_GLOBAL_Control
0x14000139c  mov     rbx, cs:WPP_GLOBAL_Control
0x1400013a3  cmp     rbx, r14
0x1400013a6  jz      short loc_1400013D8
0x1400013a8  test    dword ptr [rbx+2Ch], 4000h
0x1400013af  jz      short loc_1400013D8
0x1400013b1  mov     rbx, [rbx+18h]
0x1400013b5  call    cs:__imp_PsGetCurrentThreadId
0x1400013bc  nop     dword ptr [rax+rax+00h]
0x1400013c1  mov     r9, rax
0x1400013c4  mov     edx, 38h ; '8'
0x1400013c9  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x1400013d0  mov     rcx, rbx
0x1400013d3  call    WPP_SF_q
0x1400013d8  mov     r8, [r13+18h]
0x1400013dc  mov     rcx, r15
0x1400013df  inc     rcx
0x1400013e2  cmp     [r8+rcx*2], di
0x1400013e7  jnz     short loc_1400013DF
0x1400013e9  lea     rcx, ds:2[rcx*2]
0x1400013f1  mov     eax, [rsp+78h+arg_20]
0x1400013f8  cmp     rax, rcx
0x1400013fb  jnb     short loc_14000144B
0x1400013fd  mov     esi, 0C0000023h
0x140001402  mov     rbx, cs:WPP_GLOBAL_Control
0x140001409  cmp     rbx, r14
0x14000140c  jz      loc_140001580
0x140001412  test    dword ptr [rbx+2Ch], 2000h
0x140001419  jz      loc_140001580
0x14000141f  mov     rbx, [rbx+18h]
0x140001423  call    cs:__imp_PsGetCurrentThreadId
0x14000142a  nop     dword ptr [rax+rax+00h]
0x14000142f  mov     r9, rax
0x140001432  mov     edx, 39h ; '9'
0x140001437  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000143e  mov     rcx, rbx
0x140001441  call    WPP_SF_q
0x140001446  jmp     loc_140001580
0x14000144b  shr     rax, 1
0x14000144e  jz      loc_1400014D9
0x140001454  shr     rcx, 1
0x140001457  cmp     rcx, 7FFFFFFEh
0x14000145e  ja      short loc_1400014D6
0x140001460  mov     [rsp+78h+var_30], rcx
0x140001465  mov     [rsp+78h+var_40], r8
0x14000146a  mov     [rsp+78h+var_38], rax
0x14000146f  mov     [rsp+78h+var_50], rsi
0x140001474  mov     rdx, rdi
0x140001477  mov     [rsp+78h+var_48], rdx
0x14000147c  test    rax, rax
0x14000147f  jz      short loc_1400014C5
0x140001481  test    rcx, rcx
0x140001484  jz      short loc_1400014C0
0x140001486  movzx   r9d, word ptr [r8]
0x14000148a  test    r9w, r9w
0x14000148e  jz      short loc_1400014C0
0x140001490  mov     [rsi], r9w
0x140001494  add     rsi, 2
0x140001498  mov     [rsp+78h+var_50], rsi
0x14000149d  add     r8, 2
0x1400014a1  mov     [rsp+78h+var_40], r8
0x1400014a6  dec     rax
0x1400014a9  mov     [rsp+78h+var_38], rax
0x1400014ae  dec     rcx
0x1400014b1  mov     [rsp+78h+var_30], rcx
0x1400014b6  inc     rdx
0x1400014b9  mov     [rsp+78h+var_48], rdx
0x1400014be  jmp     short loc_14000147C
0x1400014c0  test    rax, rax
0x1400014c3  jnz     short loc_1400014D6
0x1400014c5  sub     rsi, 2
0x1400014c9  mov     [rsp+78h+var_50], rsi
0x1400014ce  dec     rdx
0x1400014d1  mov     [rsp+78h+var_48], rdx
0x1400014d6  mov     [rsi], di
0x1400014d9  mov     esi, edi
0x1400014db  jmp     loc_140001580
0x1400014e0  mov     esi, 0C00000E8h
0x1400014e5  lea     rax, WPP_GLOBAL_Control
0x1400014ec  mov     rbx, cs:WPP_GLOBAL_Control
0x1400014f3  cmp     rbx, rax
0x1400014f6  jz      short loc_140001528
0x1400014f8  test    dword ptr [rbx+2Ch], 2000h
0x1400014ff  jz      short loc_140001528
0x140001501  mov     rbx, [rbx+18h]
0x140001505  call    cs:__imp_PsGetCurrentThreadId
0x14000150c  nop     dword ptr [rax+rax+00h]
0x140001511  mov     r9, rax
0x140001514  mov     edx, 3Ah ; ':'
0x140001519  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x140001520  mov     rcx, rbx
0x140001523  call    WPP_SF_q
0x140001528  xor     edi, edi
0x14000152a  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000152e  mov     r13, [rsp+78h+arg_0]
0x140001536  jmp     short loc_140001580
0x140001538  lea     r14, WPP_GLOBAL_Control
0x14000153f  mov     rbx, cs:WPP_GLOBAL_Control
0x140001546  cmp     rbx, r14
0x140001549  jz      short loc_14000157B
0x14000154b  test    dword ptr [rbx+2Ch], 4000h
0x140001552  jz      short loc_14000157B
0x140001554  mov     rbx, [rbx+18h]
0x140001558  call    cs:__imp_PsGetCurrentThreadId
0x14000155f  nop     dword ptr [rax+rax+00h]
0x140001564  mov     r9, rax
0x140001567  mov     edx, 3Bh ; ';'
0x14000156c  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x140001573  mov     rcx, rbx
0x140001576  call    WPP_SF_q
0x14000157b  mov     esi, 0C000000Fh
0x140001580  mov     rax, [rsp+78h+arg_28]
0x140001588  mov     [rax], esi
0x14000158a  test    esi, esi
0x14000158c  jz      short loc_140001596
0x14000158e  cmp     esi, 0C0000023h
0x140001594  jnz     short loc_1400015AC
0x140001596  mov     rdx, [r13+18h]
0x14000159a  inc     r15
0x14000159d  cmp     [rdx+r15*2], di
0x1400015a2  jnz     short loc_14000159A
0x1400015a4  lea     rdi, ds:2[r15*2]
0x1400015ac  mov     [rax+8], rdi
0x1400015b0  lea     rcx, LockConflictEntryListLock; Resource
0x1400015b7  call    cs:__imp_ExReleaseResourceLite
0x1400015be  nop     dword ptr [rax+rax+00h]
0x1400015c3  call    cs:__imp_KeLeaveCriticalRegion
0x1400015ca  nop     dword ptr [rax+rax+00h]
0x1400015cf  lea     r11, [rsp+78h+var_28]
0x1400015d4  mov     rbx, [r11+38h]
0x1400015d8  mov     rsi, [r11+48h]
0x1400015dc  mov     rsp, r11
0x1400015df  pop     r15
0x1400015e1  pop     r14
0x1400015e3  pop     r13
0x1400015e5  pop     r12
0x1400015e7  pop     rdi
0x1400015e8  retn
```

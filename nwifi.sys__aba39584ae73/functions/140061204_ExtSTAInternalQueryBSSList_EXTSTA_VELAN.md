# ExtSTAInternalQueryBSSList(EXTSTA_VELAN *)

- ea: `0x140061204`
- end: `0x140061421`
- name: `?ExtSTAInternalQueryBSSList@@YAPEAUEXTSTA_BSS_LIST@@PEAUEXTSTA_VELAN@@@Z`
- size: `541`
- prototype: `struct EXTSTA_BSS_LIST *__fastcall(struct EXTSTA_VELAN *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14005fd28`
- `0x140063d84`

## callees

- `0x14000d21c`
- `0x14001588c`
- `0x140020dc0`
- `0x140061204`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140061294`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140061294`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006138b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400613f3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006138b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400613f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006139f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061404`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006139f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061404`

## pseudocode

```c
struct EXTSTA_BSS_LIST *__fastcall ExtSTAInternalQueryBSSList(struct EXTSTA_VELAN *a1, unsigned int a2)
{
  _VELAN *pGenVElan; // rcx
  struct _ADAPT *pAdapt; // rcx
  unsigned int v4; // eax
  struct DOT11_BYTE_ARRAY *v5; // rsi
  _DWORD *v6; // rbx
  _DWORD *v7; // rax
  PNPAGED_LOOKASIDE_LIST *v8; // rdi
  __int64 v9; // rbp
  int uNumOfBytes; // r8d
  unsigned __int8 *i; // r9
  unsigned int v12; // edx
  __int64 v13; // rcx
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int16 v17; // [rsp+50h] [rbp+8h] BYREF
  char v18; // [rsp+52h] [rbp+Ah]
  struct DOT11_BYTE_ARRAY *v19; // [rsp+58h] [rbp+10h] BYREF

  pGenVElan = a1->pGenVElan;
  v17 = 0;
  v18 = 0;
  pAdapt = pGenVElan->pAdapt;
  v19 = 0;
  v4 = NwfCallByteArray(pAdapt, a2, 3u, (unsigned __int8 *)&v17, 0xFFFFFFFF, &v19);
  v5 = v19;
  if ( v4 )
  {
    v6 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 147, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids, v4);
  }
  else
  {
    v7 = ExAllocateFromNPagedLookasideList(&stru_1400B31C0);
    v8 = (PNPAGED_LOOKASIDE_LIST *)v7;
    if ( v7 )
    {
      *(_QWORD *)v7 = &stru_1400B31C0;
      v9 = 0;
      v6 = v7 + 4;
      v7[2] = 845771639;
      memset(v7 + 4, 0, 0x604u);
      uNumOfBytes = v5->uNumOfBytes;
      for ( i = v5->ucBuffer; ; i += v12 )
      {
        if ( uNumOfBytes <= 0 )
        {
          *v6 = v9;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              151,
              WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids,
              (unsigned int)v9);
          goto LABEL_25;
        }
        v12 = *((_DWORD *)i + 15) + 64;
        if ( *((_DWORD *)i + 15) >= 0xFFFFFFC0 )
          break;
        if ( v12 > uNumOfBytes )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_18;
          v15 = 149;
          goto LABEL_17;
        }
        v13 = 3 * v9;
        v9 = (unsigned int)(v9 + 1);
        *(_DWORD *)((char *)v6 + 2 * v13 + 4) = *((_DWORD *)i + 4);
        *((_WORD *)v6 + v13 + 4) = *((_WORD *)i + 10);
        if ( (unsigned int)v9 >= 0x100 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_18;
          v15 = 150;
          goto LABEL_17;
        }
        uNumOfBytes -= v12;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_18;
      v15 = 148;
LABEL_17:
      WPP_SF_(v14->AttachedDevice, v15, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
LABEL_18:
      if ( !v6 )
        goto LABEL_25;
      if ( *v8 )
        ExFreeToNPagedLookasideList(*v8, v8);
      else
        ExFreePoolWithTag(v8, *((_DWORD *)v8 + 2));
    }
    v6 = 0;
  }
LABEL_25:
  if ( v5 )
  {
    if ( *(_QWORD *)&v5[-1].Header.Type )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v5[-1].Header.Type, &v5[-1]);
    else
      ExFreePoolWithTag(&v5[-1], v5[-1].uTotalNumOfBytes);
  }
  return (struct EXTSTA_BSS_LIST *)v6;
}

```

## disassembly

```asm
0x140061204  mov     r11, rsp
0x140061207  mov     [r11+18h], rbx
0x14006120b  push    rbp
0x14006120c  push    rsi
0x14006120d  push    rdi
0x14006120e  sub     rsp, 30h
0x140061212  mov     rcx, [rcx+0A38h]
0x140061219  lea     r9, [r11+8]; unsigned __int8 *
0x14006121d  xor     eax, eax
0x14006121f  mov     r8d, 3; unsigned int
0x140061225  mov     [rsp+48h+arg_0], ax
0x14006122a  mov     [rsp+48h+arg_2], al
0x14006122e  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140061232  mov     [r11+10h], rax
0x140061236  lea     rax, [r11+10h]
0x14006123a  mov     [r11-20h], rax
0x14006123e  mov     [rsp+48h+var_28], 0FFFFFFFFh; unsigned int
0x140061246  call    ?NwfCallByteArray@@YAHPEAU_ADAPT@@KKPEAEKPEAPEAUDOT11_BYTE_ARRAY@@@Z; NwfCallByteArray(_ADAPT *,ulong,ulong,uchar *,ulong,DOT11_BYTE_ARRAY * *)
0x14006124b  mov     rsi, [rsp+48h+arg_8]
0x140061250  test    eax, eax
0x140061252  jz      short loc_14006128A
0x140061254  xor     ebx, ebx
0x140061256  mov     rcx, cs:WPP_GLOBAL_Control
0x14006125d  lea     rdx, WPP_GLOBAL_Control
0x140061264  cmp     rcx, rdx
0x140061267  jz      loc_1400613DC
0x14006126d  mov     rcx, [rcx+18h]
0x140061271  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x140061278  mov     edx, 93h
0x14006127d  mov     r9d, eax
0x140061280  call    WPP_SF_d
0x140061285  jmp     loc_1400613DC
0x14006128a  lea     rbx, stru_1400B31C0
0x140061291  mov     rcx, rbx; Lookaside
0x140061294  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006129b  nop     dword ptr [rax+rax+00h]
0x1400612a0  mov     rdi, rax
0x1400612a3  test    rax, rax
0x1400612a6  jz      loc_1400613AB
0x1400612ac  mov     [rax], rbx
0x1400612af  xor     ebp, ebp
0x1400612b1  lea     rbx, [rax+10h]
0x1400612b5  mov     dword ptr [rax+8], 32697377h
0x1400612bc  mov     rcx, rbx; void *
0x1400612bf  xor     edx, edx; Val
0x1400612c1  mov     r8d, 604h; Size
0x1400612c7  call    memset
0x1400612cc  mov     r8d, [rsi+4]
0x1400612d0  lea     r9, [rsi+0Ch]
0x1400612d4  test    r8d, r8d
0x1400612d7  jle     loc_1400613AF
0x1400612dd  mov     edx, [r9+3Ch]
0x1400612e1  add     edx, 40h ; '@'
0x1400612e4  cmp     edx, 40h ; '@'
0x1400612e7  jb      short loc_140061353
0x1400612e9  cmp     edx, r8d
0x1400612ec  ja      short loc_140061339
0x1400612ee  mov     eax, [r9+10h]
0x1400612f2  lea     rcx, ds:0[rbp*2]
0x1400612fa  add     rcx, rbp
0x1400612fd  inc     ebp
0x1400612ff  mov     [rbx+rcx*2+4], eax
0x140061303  movzx   eax, word ptr [r9+14h]
0x140061308  mov     [rbx+rcx*2+8], ax
0x14006130d  cmp     ebp, 100h
0x140061313  jnb     short loc_14006131F
0x140061315  sub     r8d, edx
0x140061318  mov     eax, edx
0x14006131a  add     r9, rax
0x14006131d  jmp     short loc_1400612D4
0x14006131f  mov     rcx, cs:WPP_GLOBAL_Control
0x140061326  lea     rdx, WPP_GLOBAL_Control
0x14006132d  cmp     rcx, rdx
0x140061330  jz      short loc_14006137B
0x140061332  mov     edx, 96h
0x140061337  jmp     short loc_14006136B
0x140061339  mov     rcx, cs:WPP_GLOBAL_Control
0x140061340  lea     rdx, WPP_GLOBAL_Control
0x140061347  cmp     rcx, rdx
0x14006134a  jz      short loc_14006137B
0x14006134c  mov     edx, 95h
0x140061351  jmp     short loc_14006136B
0x140061353  mov     rcx, cs:WPP_GLOBAL_Control
0x14006135a  lea     rdx, WPP_GLOBAL_Control
0x140061361  cmp     rcx, rdx
0x140061364  jz      short loc_14006137B
0x140061366  mov     edx, 94h
0x14006136b  mov     rcx, [rcx+18h]
0x14006136f  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x140061376  call    WPP_SF_
0x14006137b  test    rbx, rbx
0x14006137e  jz      short loc_1400613DC
0x140061380  mov     rcx, [rdi]; Lookaside
0x140061383  test    rcx, rcx
0x140061386  jz      short loc_140061399
0x140061388  mov     rdx, rdi; Entry
0x14006138b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140061392  nop     dword ptr [rax+rax+00h]
0x140061397  jmp     short loc_1400613AB
0x140061399  mov     edx, [rdi+8]; Tag
0x14006139c  mov     rcx, rdi; P
0x14006139f  call    cs:__imp_ExFreePoolWithTag
0x1400613a6  nop     dword ptr [rax+rax+00h]
0x1400613ab  xor     ebx, ebx
0x1400613ad  jmp     short loc_1400613DC
0x1400613af  mov     [rbx], ebp
0x1400613b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400613b8  lea     rdx, WPP_GLOBAL_Control
0x1400613bf  cmp     rcx, rdx
0x1400613c2  jz      short loc_1400613DC
0x1400613c4  mov     rcx, [rcx+18h]
0x1400613c8  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x1400613cf  mov     edx, 97h
0x1400613d4  mov     r9d, ebp
0x1400613d7  call    WPP_SF_d
0x1400613dc  test    rsi, rsi
0x1400613df  jz      short loc_140061410
0x1400613e1  lea     rcx, [rsi-10h]; P
0x1400613e5  mov     rax, [rcx]
0x1400613e8  test    rax, rax
0x1400613eb  jz      short loc_140061401
0x1400613ed  mov     rdx, rcx; Entry
0x1400613f0  mov     rcx, rax; Lookaside
0x1400613f3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400613fa  nop     dword ptr [rax+rax+00h]
0x1400613ff  jmp     short loc_140061410
0x140061401  mov     edx, [rcx+8]; Tag
0x140061404  call    cs:__imp_ExFreePoolWithTag
0x14006140b  nop     dword ptr [rax+rax+00h]
0x140061410  mov     rax, rbx
0x140061413  mov     rbx, [rsp+48h+arg_10]
0x140061418  add     rsp, 30h
0x14006141c  pop     rdi
0x14006141d  pop     rsi
0x14006141e  pop     rbp
0x14006141f  retn
```

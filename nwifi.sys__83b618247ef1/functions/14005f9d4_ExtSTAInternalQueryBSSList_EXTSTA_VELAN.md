# ExtSTAInternalQueryBSSList(EXTSTA_VELAN *)

- ea: `0x14005f9d4`
- end: `0x14005fbf1`
- name: `?ExtSTAInternalQueryBSSList@@YAPEAUEXTSTA_BSS_LIST@@PEAUEXTSTA_VELAN@@@Z`
- size: `541`
- prototype: `struct EXTSTA_BSS_LIST *__fastcall(struct EXTSTA_VELAN *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14005e4f8`
- `0x140062554`

## callees

- `0x14000d22c`
- `0x14001589c`
- `0x140020dc0`
- `0x14005f9d4`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005fa64`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005fa64`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005fb5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005fbc3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005fb5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005fbc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fb6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fbd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fb6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fbd4`

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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 148, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids, v4);
  }
  else
  {
    v7 = ExAllocateFromNPagedLookasideList(&stru_1400B0180);
    v8 = (PNPAGED_LOOKASIDE_LIST *)v7;
    if ( v7 )
    {
      *(_QWORD *)v7 = &stru_1400B0180;
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
              152,
              WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids,
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
          v15 = 150;
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
          v15 = 151;
          goto LABEL_17;
        }
        uNumOfBytes -= v12;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_18;
      v15 = 149;
LABEL_17:
      WPP_SF_(v14->AttachedDevice, v15, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
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
0x14005f9d4  mov     r11, rsp
0x14005f9d7  mov     [r11+18h], rbx
0x14005f9db  push    rbp
0x14005f9dc  push    rsi
0x14005f9dd  push    rdi
0x14005f9de  sub     rsp, 30h
0x14005f9e2  mov     rcx, [rcx+0A38h]
0x14005f9e9  lea     r9, [r11+8]; unsigned __int8 *
0x14005f9ed  xor     eax, eax
0x14005f9ef  mov     r8d, 3; unsigned int
0x14005f9f5  mov     [rsp+48h+arg_0], ax
0x14005f9fa  mov     [rsp+48h+arg_2], al
0x14005f9fe  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14005fa02  mov     [r11+10h], rax
0x14005fa06  lea     rax, [r11+10h]
0x14005fa0a  mov     [r11-20h], rax
0x14005fa0e  mov     [rsp+48h+var_28], 0FFFFFFFFh; unsigned int
0x14005fa16  call    ?NwfCallByteArray@@YAHPEAU_ADAPT@@KKPEAEKPEAPEAUDOT11_BYTE_ARRAY@@@Z; NwfCallByteArray(_ADAPT *,ulong,ulong,uchar *,ulong,DOT11_BYTE_ARRAY * *)
0x14005fa1b  mov     rsi, [rsp+48h+arg_8]
0x14005fa20  test    eax, eax
0x14005fa22  jz      short loc_14005FA5A
0x14005fa24  xor     ebx, ebx
0x14005fa26  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fa2d  lea     rdx, WPP_GLOBAL_Control
0x14005fa34  cmp     rcx, rdx
0x14005fa37  jz      loc_14005FBAC
0x14005fa3d  mov     rcx, [rcx+18h]
0x14005fa41  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005fa48  mov     edx, 94h
0x14005fa4d  mov     r9d, eax
0x14005fa50  call    WPP_SF_d
0x14005fa55  jmp     loc_14005FBAC
0x14005fa5a  lea     rbx, stru_1400B0180
0x14005fa61  mov     rcx, rbx; Lookaside
0x14005fa64  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14005fa6b  nop     dword ptr [rax+rax+00h]
0x14005fa70  mov     rdi, rax
0x14005fa73  test    rax, rax
0x14005fa76  jz      loc_14005FB7B
0x14005fa7c  mov     [rax], rbx
0x14005fa7f  xor     ebp, ebp
0x14005fa81  lea     rbx, [rax+10h]
0x14005fa85  mov     dword ptr [rax+8], 32697377h
0x14005fa8c  mov     rcx, rbx; void *
0x14005fa8f  xor     edx, edx; Val
0x14005fa91  mov     r8d, 604h; Size
0x14005fa97  call    memset
0x14005fa9c  mov     r8d, [rsi+4]
0x14005faa0  lea     r9, [rsi+0Ch]
0x14005faa4  test    r8d, r8d
0x14005faa7  jle     loc_14005FB7F
0x14005faad  mov     edx, [r9+3Ch]
0x14005fab1  add     edx, 40h ; '@'
0x14005fab4  cmp     edx, 40h ; '@'
0x14005fab7  jb      short loc_14005FB23
0x14005fab9  cmp     edx, r8d
0x14005fabc  ja      short loc_14005FB09
0x14005fabe  mov     eax, [r9+10h]
0x14005fac2  lea     rcx, ds:0[rbp*2]
0x14005faca  add     rcx, rbp
0x14005facd  inc     ebp
0x14005facf  mov     [rbx+rcx*2+4], eax
0x14005fad3  movzx   eax, word ptr [r9+14h]
0x14005fad8  mov     [rbx+rcx*2+8], ax
0x14005fadd  cmp     ebp, 100h
0x14005fae3  jnb     short loc_14005FAEF
0x14005fae5  sub     r8d, edx
0x14005fae8  mov     eax, edx
0x14005faea  add     r9, rax
0x14005faed  jmp     short loc_14005FAA4
0x14005faef  mov     rcx, cs:WPP_GLOBAL_Control
0x14005faf6  lea     rdx, WPP_GLOBAL_Control
0x14005fafd  cmp     rcx, rdx
0x14005fb00  jz      short loc_14005FB4B
0x14005fb02  mov     edx, 97h
0x14005fb07  jmp     short loc_14005FB3B
0x14005fb09  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fb10  lea     rdx, WPP_GLOBAL_Control
0x14005fb17  cmp     rcx, rdx
0x14005fb1a  jz      short loc_14005FB4B
0x14005fb1c  mov     edx, 96h
0x14005fb21  jmp     short loc_14005FB3B
0x14005fb23  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fb2a  lea     rdx, WPP_GLOBAL_Control
0x14005fb31  cmp     rcx, rdx
0x14005fb34  jz      short loc_14005FB4B
0x14005fb36  mov     edx, 95h
0x14005fb3b  mov     rcx, [rcx+18h]
0x14005fb3f  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005fb46  call    WPP_SF_
0x14005fb4b  test    rbx, rbx
0x14005fb4e  jz      short loc_14005FBAC
0x14005fb50  mov     rcx, [rdi]; Lookaside
0x14005fb53  test    rcx, rcx
0x14005fb56  jz      short loc_14005FB69
0x14005fb58  mov     rdx, rdi; Entry
0x14005fb5b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005fb62  nop     dword ptr [rax+rax+00h]
0x14005fb67  jmp     short loc_14005FB7B
0x14005fb69  mov     edx, [rdi+8]; Tag
0x14005fb6c  mov     rcx, rdi; P
0x14005fb6f  call    cs:__imp_ExFreePoolWithTag
0x14005fb76  nop     dword ptr [rax+rax+00h]
0x14005fb7b  xor     ebx, ebx
0x14005fb7d  jmp     short loc_14005FBAC
0x14005fb7f  mov     [rbx], ebp
0x14005fb81  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fb88  lea     rdx, WPP_GLOBAL_Control
0x14005fb8f  cmp     rcx, rdx
0x14005fb92  jz      short loc_14005FBAC
0x14005fb94  mov     rcx, [rcx+18h]
0x14005fb98  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005fb9f  mov     edx, 98h
0x14005fba4  mov     r9d, ebp
0x14005fba7  call    WPP_SF_d
0x14005fbac  test    rsi, rsi
0x14005fbaf  jz      short loc_14005FBE0
0x14005fbb1  lea     rcx, [rsi-10h]; P
0x14005fbb5  mov     rax, [rcx]
0x14005fbb8  test    rax, rax
0x14005fbbb  jz      short loc_14005FBD1
0x14005fbbd  mov     rdx, rcx; Entry
0x14005fbc0  mov     rcx, rax; Lookaside
0x14005fbc3  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005fbca  nop     dword ptr [rax+rax+00h]
0x14005fbcf  jmp     short loc_14005FBE0
0x14005fbd1  mov     edx, [rcx+8]; Tag
0x14005fbd4  call    cs:__imp_ExFreePoolWithTag
0x14005fbdb  nop     dword ptr [rax+rax+00h]
0x14005fbe0  mov     rax, rbx
0x14005fbe3  mov     rbx, [rsp+48h+arg_10]
0x14005fbe8  add     rsp, 30h
0x14005fbec  pop     rdi
0x14005fbed  pop     rsi
0x14005fbee  pop     rbp
0x14005fbef  retn
```

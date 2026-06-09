# ExtSTASetWEPKeyMapping(EXTSTA_VELAN *,_DOT11_KM_WEP_KEY_MAPPING *,ulong)

- ea: `0x14006f040`
- end: `0x14006f2b4`
- name: `?ExtSTASetWEPKeyMapping@@YAJPEAUEXTSTA_VELAN@@PEAU_DOT11_KM_WEP_KEY_MAPPING@@K@Z`
- size: `628`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, struct _DOT11_KM_WEP_KEY_MAPPING *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x14006f040`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006f158`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006f158`
- `ntoskrnl!ExAllocatePool2` at `0x14006f16d`
- `ntoskrnl!ExAllocatePool2` at `0x14006f16d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006f263`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006f263`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f274`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f274`

## pseudocode

```c
__int64 __fastcall ExtSTASetWEPKeyMapping(
        struct EXTSTA_VELAN *a1,
        struct _DOT11_KM_WEP_KEY_MAPPING *a2,
        unsigned int a3)
{
  size_t v4; // r13
  unsigned int v6; // r10d
  _DOT11_BSS_TYPE DesiredBSSType; // ecx
  _DWORD *v8; // rdi
  int v9; // r9d
  __int64 v10; // rax
  __int64 v11; // rdx
  unsigned int v12; // r11d
  __int64 v13; // r8
  __int64 i; // rdx
  unsigned int v15; // r15d
  unsigned int v16; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  _DWORD *v19; // rsi
  size_t v20; // r8
  unsigned int v21; // ebx

  v4 = a3;
  if ( *(_DWORD *)a2 != 1 )
    goto LABEL_41;
  v6 = *((_DWORD *)a2 + 9);
  if ( a3 - 40 < v6 )
  {
    v21 = -1073741789;
    goto LABEL_42;
  }
  if ( v6 > 0xFFFF )
  {
LABEL_41:
    v21 = -1073741811;
    goto LABEL_42;
  }
  DesiredBSSType = a1->Rw.DesiredBSSType;
  v8 = (_DWORD *)((char *)a2 + 20);
  v9 = *((_DWORD *)a2 + 5);
  if ( a2 != (struct _DOT11_KM_WEP_KEY_MAPPING *)-20LL )
    *v8 = v9;
  v10 = 1960;
  v11 = 0;
  if ( DesiredBSSType != dot11_BSS_type_infrastructure )
    v10 = 2072;
  v12 = *(unsigned int *)((char *)&a1->ModuleStatus.uValue + v10);
  v13 = 1968;
  if ( DesiredBSSType != dot11_BSS_type_infrastructure )
    v13 = 2080;
  while ( 1 )
  {
    if ( (unsigned int)v11 >= v12 )
    {
      if ( ((v9 - 1) & 0xFFFFFFFB) == 0 )
      {
        for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
        {
          if ( *(_DWORD *)(*(_QWORD *)((char *)&a1->ModuleStatus.0 + v13) + 4 * i) == 257 )
          {
            if ( v8 )
              *v8 = 257;
            goto LABEL_20;
          }
        }
      }
      goto LABEL_41;
    }
    if ( *(_DWORD *)(*(_QWORD *)((char *)&a1->ModuleStatus.0 + v13) + 4 * v11) == v9 )
      break;
    v11 = (unsigned int)(v11 + 1);
  }
LABEL_20:
  v15 = v6 + 32;
  v16 = v6 + 48;
  if ( v6 + 48 < 0x10 )
    goto LABEL_39;
  if ( v16 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    goto LABEL_29;
  }
  if ( v16 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_29;
  }
  if ( v16 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_29;
  }
  if ( v16 > 0x800 )
  {
    p_DeviceQueue = 0;
    Pool2 = (_DWORD *)ExAllocatePool2(64, v16, 808464432);
  }
  else
  {
    p_DeviceQueue = &stru_1400B31C0;
LABEL_29:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
  }
  if ( !Pool2 )
  {
LABEL_39:
    v21 = -1073741670;
    goto LABEL_42;
  }
  Pool2[2] = 808464432;
  v19 = Pool2 + 4;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memset(Pool2 + 4, 0, v15);
  *v19 = 1048960;
  v19[1] = v15 - 12;
  v19[2] = v15 - 12;
  v19[3] = *((_DWORD *)a2 + 3);
  *((_WORD *)v19 + 8) = *((_WORD *)a2 + 8);
  *((_BYTE *)v19 + 28) = *((_DWORD *)a2 + 8) != 1;
  v19[5] = *v8;
  v19[6] = *((_DWORD *)a2 + 6);
  *((_BYTE *)v19 + 29) = *((_DWORD *)a2 + 7) != 0;
  v20 = *((unsigned __int16 *)a2 + 18);
  *((_WORD *)v19 + 15) = *((_WORD *)a2 + 18);
  memmove(v19 + 8, (char *)a2 + 40, v20);
  v21 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE01018Cu, v19, v15);
  if ( v21 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids);
  if ( v19 )
  {
    memset(v19, 0, v15);
    if ( *((_QWORD *)v19 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v19 - 2), v19 - 4);
    else
      ExFreePoolWithTag(v19 - 4, *(v19 - 2));
  }
LABEL_42:
  memset(a2, 0, v4);
  return v21;
}

```

## disassembly

```asm
0x14006f040  push    rbx
0x14006f042  push    rbp
0x14006f043  push    rsi
0x14006f044  push    rdi
0x14006f045  push    r13
0x14006f047  push    r14
0x14006f049  push    r15
0x14006f04b  sub     rsp, 30h
0x14006f04f  cmp     dword ptr [rdx], 1
0x14006f052  mov     rbp, rdx
0x14006f055  mov     r13d, r8d
0x14006f058  mov     r14, rcx
0x14006f05b  jnz     loc_14006F290
0x14006f061  mov     r10d, [rdx+24h]
0x14006f065  lea     eax, [r13-28h]
0x14006f069  cmp     eax, r10d
0x14006f06c  jb      loc_14006F289
0x14006f072  cmp     r10d, 0FFFFh
0x14006f079  ja      loc_14006F290
0x14006f07f  mov     ecx, [rcx+6BCh]
0x14006f085  lea     rdi, [rdx+14h]
0x14006f089  mov     r9d, [rdi]
0x14006f08c  test    rdi, rdi
0x14006f08f  jz      short loc_14006F094
0x14006f091  mov     [rdi], r9d
0x14006f094  mov     eax, 7A8h
0x14006f099  xor     edx, edx
0x14006f09b  cmp     ecx, 1
0x14006f09e  lea     r8d, [rax+70h]
0x14006f0a2  cmovnz  eax, r8d
0x14006f0a6  mov     r11d, [rax+r14]
0x14006f0aa  lea     eax, [r8+8]
0x14006f0ae  lea     r8d, [rax-70h]
0x14006f0b2  cmovnz  r8d, eax
0x14006f0b6  cmp     edx, r11d
0x14006f0b9  jnb     short loc_14006F0C9
0x14006f0bb  mov     rax, [r8+r14]
0x14006f0bf  cmp     [rax+rdx*4], r9d
0x14006f0c3  jz      short loc_14006F0FF
0x14006f0c5  inc     edx
0x14006f0c7  jmp     short loc_14006F0B6
0x14006f0c9  lea     eax, [r9-1]
0x14006f0cd  test    eax, 0FFFFFFFBh
0x14006f0d2  jnz     loc_14006F290
0x14006f0d8  xor     edx, edx
0x14006f0da  mov     r9d, 101h
0x14006f0e0  cmp     edx, r11d
0x14006f0e3  jnb     loc_14006F290
0x14006f0e9  mov     rax, [r8+r14]
0x14006f0ed  cmp     [rax+rdx*4], r9d
0x14006f0f1  jz      short loc_14006F0F7
0x14006f0f3  inc     edx
0x14006f0f5  jmp     short loc_14006F0E0
0x14006f0f7  test    rdi, rdi
0x14006f0fa  jz      short loc_14006F0FF
0x14006f0fc  mov     [rdi], r9d
0x14006f0ff  lea     r15d, [r10+20h]
0x14006f103  lea     eax, [r15+10h]
0x14006f107  cmp     eax, 10h
0x14006f10a  jb      loc_14006F282
0x14006f110  mov     ecx, 40h ; '@'
0x14006f115  mov     esi, 30303030h
0x14006f11a  cmp     eax, ecx
0x14006f11c  ja      short loc_14006F127
0x14006f11e  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14006f125  jmp     short loc_14006F155
0x14006f127  cmp     eax, 100h
0x14006f12c  ja      short loc_14006F137
0x14006f12e  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006f135  jmp     short loc_14006F155
0x14006f137  cmp     eax, 400h
0x14006f13c  ja      short loc_14006F147
0x14006f13e  lea     rbx, Lookaside
0x14006f145  jmp     short loc_14006F155
0x14006f147  cmp     eax, 800h
0x14006f14c  ja      short loc_14006F166
0x14006f14e  lea     rbx, stru_1400B31C0
0x14006f155  mov     rcx, rbx; Lookaside
0x14006f158  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006f15f  nop     dword ptr [rax+rax+00h]
0x14006f164  jmp     short loc_14006F179
0x14006f166  xor     ebx, ebx
0x14006f168  mov     edx, eax
0x14006f16a  mov     r8d, esi
0x14006f16d  call    cs:__imp_ExAllocatePool2
0x14006f174  nop     dword ptr [rax+rax+00h]
0x14006f179  test    rax, rax
0x14006f17c  jz      loc_14006F282
0x14006f182  mov     [rax+8], esi
0x14006f185  xor     edx, edx; Val
0x14006f187  lea     rsi, [rax+10h]
0x14006f18b  mov     r8d, r15d; Size
0x14006f18e  mov     rcx, rsi; void *
0x14006f191  mov     [rax], rbx
0x14006f194  call    memset
0x14006f199  mov     dword ptr [rsi], 100180h
0x14006f19f  lea     eax, [r15-0Ch]
0x14006f1a3  mov     [rsi+4], eax
0x14006f1a6  lea     rdx, [rbp+28h]; Src
0x14006f1aa  mov     [rsi+8], eax
0x14006f1ad  lea     rcx, [rsi+20h]; void *
0x14006f1b1  mov     eax, [rbp+0Ch]
0x14006f1b4  mov     [rsi+0Ch], eax
0x14006f1b7  movzx   eax, word ptr [rbp+10h]
0x14006f1bb  mov     [rsi+10h], ax
0x14006f1bf  cmp     dword ptr [rbp+20h], 1
0x14006f1c3  setnz   al
0x14006f1c6  mov     [rsi+1Ch], al
0x14006f1c9  mov     eax, [rdi]
0x14006f1cb  mov     [rsi+14h], eax
0x14006f1ce  mov     eax, [rbp+18h]
0x14006f1d1  mov     [rsi+18h], eax
0x14006f1d4  cmp     dword ptr [rbp+1Ch], 0
0x14006f1d8  setnz   al
0x14006f1db  mov     [rsi+1Dh], al
0x14006f1de  movzx   eax, word ptr [rbp+24h]
0x14006f1e2  mov     r8d, eax; Size
0x14006f1e5  mov     [rsi+1Eh], ax
0x14006f1e9  call    memmove
0x14006f1ee  mov     rcx, [r14+0A38h]
0x14006f1f5  mov     r9, rsi; void *
0x14006f1f8  mov     edx, 1; unsigned int
0x14006f1fd  mov     [rsp+68h+var_48], r15d; unsigned int
0x14006f202  mov     r8d, 0E01018Ch; unsigned int
0x14006f208  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006f20c  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006f211  mov     ebx, eax
0x14006f213  test    eax, eax
0x14006f215  jz      short loc_14006F23F
0x14006f217  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f21e  lea     rax, WPP_GLOBAL_Control
0x14006f225  cmp     rcx, rax
0x14006f228  jz      short loc_14006F23F
0x14006f22a  mov     rcx, [rcx+18h]
0x14006f22e  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006f235  mov     edx, 1Bh
0x14006f23a  call    WPP_SF_
0x14006f23f  test    rsi, rsi
0x14006f242  jz      short loc_14006F295
0x14006f244  mov     r8d, r15d; Size
0x14006f247  xor     edx, edx; Val
0x14006f249  mov     rcx, rsi; void *
0x14006f24c  call    memset
0x14006f251  lea     rcx, [rsi-10h]; P
0x14006f255  mov     rax, [rcx]
0x14006f258  test    rax, rax
0x14006f25b  jz      short loc_14006F271
0x14006f25d  mov     rdx, rcx; Entry
0x14006f260  mov     rcx, rax; Lookaside
0x14006f263  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006f26a  nop     dword ptr [rax+rax+00h]
0x14006f26f  jmp     short loc_14006F295
0x14006f271  mov     edx, [rcx+8]; Tag
0x14006f274  call    cs:__imp_ExFreePoolWithTag
0x14006f27b  nop     dword ptr [rax+rax+00h]
0x14006f280  jmp     short loc_14006F295
0x14006f282  mov     ebx, 0C000009Ah
0x14006f287  jmp     short loc_14006F295
0x14006f289  mov     ebx, 0C0000023h
0x14006f28e  jmp     short loc_14006F295
0x14006f290  mov     ebx, 0C000000Dh
0x14006f295  mov     r8, r13; Size
0x14006f298  xor     edx, edx; Val
0x14006f29a  mov     rcx, rbp; void *
0x14006f29d  call    memset
0x14006f2a2  mov     eax, ebx
0x14006f2a4  add     rsp, 30h
0x14006f2a8  pop     r15
0x14006f2aa  pop     r14
0x14006f2ac  pop     r13
0x14006f2ae  pop     rdi
0x14006f2af  pop     rsi
0x14006f2b0  pop     rbp
0x14006f2b1  pop     rbx
0x14006f2b2  retn
```
